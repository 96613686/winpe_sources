# std::_Future_error_map(int)

- ea: `0x180018a88`
- end: `0x180018abf`
- name: `?_Future_error_map@std@@YAPEBDH@Z`
- size: `55`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b7b0`
- `0x18001c3a0`

## callees

- `0x180018a88`

## string_xrefs

- `0x180018aaf`: `future already retrieved`
- `0x180018aa7`: `promise already satisfied`

## pseudocode

```c
const char *__fastcall std::_Future_error_map(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx

  v1 = a1 - 1;
  if ( !v1 )
    return "broken promise";
  v2 = v1 - 1;
  if ( !v2 )
    return "future already retrieved";
  v3 = v2 - 1;
  if ( !v3 )
    return "promise already satisfied";
  if ( v3 == 1 )
    return "no state";
  return 0;
}

```

## disassembly

```asm
0x180018a88  sub     ecx, 1
0x180018a8b  jz      short loc_180018AB7
0x180018a8d  sub     ecx, 1
0x180018a90  jz      short loc_180018AAF
0x180018a92  sub     ecx, 1
0x180018a95  jz      short loc_180018AA7
0x180018a97  cmp     ecx, 1
0x180018a9a  jz      short loc_180018A9F
0x180018a9c  xor     eax, eax
0x180018a9e  retn
0x180018a9f  lea     rax, aNoState; "no state"
0x180018aa6  retn
0x180018aa7  lea     rax, aPromiseAlready; "promise already satisfied"
0x180018aae  retn
0x180018aaf  lea     rax, aFutureAlreadyR; "future already retrieved"
0x180018ab6  retn
0x180018ab7  lea     rax, aBrokenPromise; "broken promise"
0x180018abe  retn
```
