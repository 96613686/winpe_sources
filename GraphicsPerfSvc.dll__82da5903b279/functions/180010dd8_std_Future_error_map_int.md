# std::_Future_error_map(int)

- ea: `0x180010dd8`
- end: `0x180010e0f`
- name: `?_Future_error_map@std@@YAPEBDH@Z`
- size: `55`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011480`
- `0x180011620`

## callees

- `0x180010dd8`

## string_xrefs

- `0x180010dff`: `future already retrieved`
- `0x180010df7`: `promise already satisfied`

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
0x180010dd8  sub     ecx, 1
0x180010ddb  jz      short loc_180010E07
0x180010ddd  sub     ecx, 1
0x180010de0  jz      short loc_180010DFF
0x180010de2  sub     ecx, 1
0x180010de5  jz      short loc_180010DF7
0x180010de7  cmp     ecx, 1
0x180010dea  jz      short loc_180010DEF
0x180010dec  xor     eax, eax
0x180010dee  retn
0x180010def  lea     rax, aNoState; "no state"
0x180010df6  retn
0x180010df7  lea     rax, aPromiseAlready; "promise already satisfied"
0x180010dfe  retn
0x180010dff  lea     rax, aFutureAlreadyR; "future already retrieved"
0x180010e06  retn
0x180010e07  lea     rax, aBrokenPromise; "broken promise"
0x180010e0e  retn
```
