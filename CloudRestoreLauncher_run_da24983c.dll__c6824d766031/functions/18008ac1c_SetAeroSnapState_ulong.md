# SetAeroSnapState(ulong)

- ea: `0x18008ac1c`
- end: `0x18008ac7f`
- name: `?SetAeroSnapState@@YAKK@Z`
- size: `99`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008a850`

## callees

- `0x18008ac1c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18008ac3e`
- `USER32!SystemParametersInfoW` at `0x18008ac61`
- `USER32!SystemParametersInfoW` at `0x18008ac3e`
- `USER32!SystemParametersInfoW` at `0x18008ac61`

## pseudocode

```c
__int64 __fastcall SetAeroSnapState(unsigned int a1)
{
  UINT v1; // edx
  __int64 result; // rax
  unsigned int pvParam; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( a1 != 1 )
  {
    LOBYTE(v1) = a1 != 0;
    if ( SystemParametersInfoW(0x83u, v1, 0, 3u) )
      return a1;
    return 1;
  }
  pvParam = 0;
  if ( !SystemParametersInfoW(0x82u, 0, &pvParam, 0) )
    return 1;
  result = pvParam;
  if ( pvParam == 1 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18008ac1c  push    rbx
0x18008ac1e  sub     rsp, 20h
0x18008ac22  xor     edx, edx; uiParam
0x18008ac24  mov     ebx, ecx
0x18008ac26  cmp     ecx, 1
0x18008ac29  jz      short loc_18008AC4C
0x18008ac2b  test    ecx, ecx
0x18008ac2d  mov     r9d, 3; fWinIni
0x18008ac33  mov     ecx, 83h; uiAction
0x18008ac38  setnz   dl; uiParam
0x18008ac3b  xor     r8d, r8d; pvParam
0x18008ac3e  call    cs:__imp_SystemParametersInfoW
0x18008ac44  test    eax, eax
0x18008ac46  jz      short loc_18008AC74
0x18008ac48  mov     eax, ebx
0x18008ac4a  jmp     short loc_18008AC79
0x18008ac4c  xor     r9d, r9d; fWinIni
0x18008ac4f  mov     [rsp+28h+pvParam], 0
0x18008ac57  lea     r8, [rsp+28h+pvParam]; pvParam
0x18008ac5c  mov     ecx, 82h; uiAction
0x18008ac61  call    cs:__imp_SystemParametersInfoW
0x18008ac67  test    eax, eax
0x18008ac69  jz      short loc_18008AC74
0x18008ac6b  mov     eax, [rsp+28h+pvParam]
0x18008ac6f  cmp     eax, 1
0x18008ac72  jnz     short loc_18008AC79
0x18008ac74  mov     eax, 1
0x18008ac79  add     rsp, 20h
0x18008ac7d  pop     rbx
0x18008ac7e  retn
```
