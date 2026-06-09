# GetSystemFont

- ea: `0x180017ff0`
- end: `0x18001806d`
- name: `GetSystemFont`
- size: `125`
- prototype: `HFONT()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b0d0`

## callees

- `0x180017ff0`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180018030`
- `USER32!SystemParametersInfoW` at `0x180018030`
- `GDI32!GetStockObject` at `0x18001804f`
- `GDI32!GetStockObject` at `0x18001804f`
- `GDI32!CreateFontIndirectW` at `0x180018042`
- `GDI32!CreateFontIndirectW` at `0x180018042`

## pseudocode

```c
HFONT GetSystemFont()
{
  int pvParam; // [rsp+20h] [rbp-218h] BYREF
  _BYTE v2[404]; // [rsp+24h] [rbp-214h] BYREF
  LOGFONTW lf; // [rsp+1B8h] [rbp-80h] BYREF

  memset_0(v2, 0, 0x1F4u);
  pvParam = 504;
  if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    return CreateFontIndirectW(&lf);
  else
    return (HFONT)GetStockObject(17);
}

```

## disassembly

```asm
0x180017ff0  sub     rsp, 238h
0x180017ff7  mov     rax, cs:__security_cookie
0x180017ffe  xor     rax, rsp
0x180018001  mov     [rsp+238h+var_18], rax
0x180018009  xor     edx, edx; Val
0x18001800b  lea     rcx, [rsp+238h+var_214]; void *
0x180018010  mov     r8d, 1F4h; Size
0x180018016  call    memset_0
0x18001801b  xor     r9d, r9d; fWinIni
0x18001801e  lea     r8, [rsp+238h+pvParam]; pvParam
0x180018023  mov     edx, 1F8h; uiParam
0x180018028  mov     [rsp+238h+pvParam], edx
0x18001802c  lea     ecx, [r9+29h]; uiAction
0x180018030  call    cs:__imp_SystemParametersInfoW
0x180018036  test    eax, eax
0x180018038  jz      short loc_18001804A
0x18001803a  lea     rcx, [rsp+238h+lf]; lplf
0x180018042  call    cs:__imp_CreateFontIndirectW
0x180018048  jmp     short loc_180018055
0x18001804a  mov     ecx, 11h; i
0x18001804f  call    cs:__imp_GetStockObject
0x180018055  mov     rcx, [rsp+238h+var_18]
0x18001805d  xor     rcx, rsp; StackCookie
0x180018060  call    __security_check_cookie
0x180018065  add     rsp, 238h
0x18001806c  retn
```
