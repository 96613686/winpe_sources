# std::future_error::what(void)

- ea: `0x180013150`
- end: `0x18001318a`
- name: `?what@future_error@std@@UEBAPEBDXZ`
- size: `58`
- prototype: `const char *__fastcall(std::future_error *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013150`

## string_xrefs

- `0x18001317a`: `future already retrieved`
- `0x180013172`: `promise already satisfied`

## pseudocode

```c
const char *__fastcall std::future_error::what(std::future_error *this)
{
  switch ( *((_DWORD *)this + 6) )
  {
    case 1:
      return "broken promise";
    case 2:
      return "future already retrieved";
    case 3:
      return "promise already satisfied";
    case 4:
      return "no state";
  }
  return 0;
}

```

## disassembly

```asm
0x180013150  mov     edx, [rcx+18h]
0x180013153  sub     edx, 1
0x180013156  jz      short loc_180013182
0x180013158  sub     edx, 1
0x18001315b  jz      short loc_18001317A
0x18001315d  sub     edx, 1
0x180013160  jz      short loc_180013172
0x180013162  cmp     edx, 1
0x180013165  jz      short loc_18001316A
0x180013167  xor     eax, eax
0x180013169  retn
0x18001316a  lea     rax, aNoState; "no state"
0x180013171  retn
0x180013172  lea     rax, aPromiseAlready; "promise already satisfied"
0x180013179  retn
0x18001317a  lea     rax, aFutureAlreadyR; "future already retrieved"
0x180013181  retn
0x180013182  lea     rax, aBrokenPromise; "broken promise"
0x180013189  retn
```
