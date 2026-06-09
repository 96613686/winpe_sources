# std::future_error::what(void)

- ea: `0x18002ea20`
- end: `0x18002ea5a`
- name: `?what@future_error@std@@UEBAPEBDXZ`
- size: `58`
- prototype: `const char *__fastcall(std::future_error *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002ea20`

## string_xrefs

- `0x18002ea4a`: `future already retrieved`
- `0x18002ea42`: `promise already satisfied`

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
0x18002ea20  mov     edx, [rcx+18h]
0x18002ea23  sub     edx, 1
0x18002ea26  jz      short loc_18002EA52
0x18002ea28  sub     edx, 1
0x18002ea2b  jz      short loc_18002EA4A
0x18002ea2d  sub     edx, 1
0x18002ea30  jz      short loc_18002EA42
0x18002ea32  cmp     edx, 1
0x18002ea35  jz      short loc_18002EA3A
0x18002ea37  xor     eax, eax
0x18002ea39  retn
0x18002ea3a  lea     rax, aNoState; "no state"
0x18002ea41  retn
0x18002ea42  lea     rax, aPromiseAlready; "promise already satisfied"
0x18002ea49  retn
0x18002ea4a  lea     rax, aFutureAlreadyR; "future already retrieved"
0x18002ea51  retn
0x18002ea52  lea     rax, aBrokenPromise; "broken promise"
0x18002ea59  retn
```
