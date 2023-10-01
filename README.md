# template double_integer <LO, HI>
*Formerly simple int128 class for a bytecode interpreter project long forgotten. Rewritten several times, now supporting much more that originally envisioned, most importantly being usable transparently as if intrinsic integer type.*

## Usage

    #include <double_integer.hpp>
    
    typedef double_integer <unsigned long long,   signed long long>  int128_t;
    typedef double_integer <unsigned long long, unsigned long long> uint128_t;
    
    typedef double_integer <uint128_t,  int128_t>  int256_t;
    typedef double_integer <uint128_t, uint128_t> uint256_t;

    // ...

## Key features
* Binary layout of objects is the same as the data type they simulate for little-endian platform, P.O.D. aka “standard layout type”.
   * copy in/out using `std::memcpy`
* The std::numeric_limits is correctly overloaded for every instantiated double_integer.
* Nesting instantiations is valid way to create 256-bit integers, 512-bit integers and even arbitrarily larger ones.

## Notes
* Review needed for constexpr correctness and for possible simplifications with latest C++.
* Features that I don't use in my projects may not be as thoroughly tested as the rest of the code.

## License
This project is a free software available under the zlib license.
