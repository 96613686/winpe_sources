# std::future_error::what(void)

- ea: `0x18001aab0`
- end: `0x18001aaea`
- name: `?what@future_error@std@@UEBAPEBDXZ`
- size: `58`
- prototype: `const char *__fastcall(std::future_error *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001aab0`

## string_xrefs

- `0x18001aada`: `future already retrieved`
- `0x18001aad2`: `promise already satisfied`

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
0x18001aab0  mov     edx, [rcx+18h]
0x18001aab3  sub     edx, 1
0x18001aab6  jz      short loc_18001AAE2
0x18001aab8  sub     edx, 1
0x18001aabb  jz      short loc_18001AADA
0x18001aabd  sub     edx, 1
0x18001aac0  jz      short loc_18001AAD2
0x18001aac2  cmp     edx, 1
0x18001aac5  jz      short loc_18001AACA
0x18001aac7  xor     eax, eax
0x18001aac9  retn
0x18001aaca  lea     rax, aNoState; "no state"
0x18001aad1  retn
0x18001aad2  lea     rax, aPromiseAlready; "promise already satisfied"
0x18001aad9  retn
0x18001aada  lea     rax, aFutureAlreadyR; "future already retrieved"
0x18001aae1  retn
0x18001aae2  lea     rax, aBrokenPromise; "broken promise"
0x18001aae9  retn
```
