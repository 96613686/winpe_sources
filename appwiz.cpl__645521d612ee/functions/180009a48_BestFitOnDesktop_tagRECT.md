# BestFitOnDesktop(tagRECT *)

- ea: `0x180009a48`
- end: `0x180009b97`
- name: `?BestFitOnDesktop@@YAXPEAUtagRECT@@@Z`
- size: `335`
- prototype: `void __fastcall(struct tagRECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010204`

## callees

- `0x180009a48`
- `0x18000b1a4`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180009aec`
- `KERNEL32!MulDiv` at `0x180009b01`
- `KERNEL32!MulDiv` at `0x180009aec`
- `KERNEL32!MulDiv` at `0x180009b01`
- `USER32!SetRect` at `0x180009a87`
- `USER32!SetRect` at `0x180009a87`
- `USER32!SystemParametersInfoW` at `0x180009aae`
- `USER32!SystemParametersInfoW` at `0x180009b26`
- `USER32!SystemParametersInfoW` at `0x180009aae`
- `USER32!SystemParametersInfoW` at `0x180009b26`
- `GDI32!CreateFontIndirectW` at `0x180009abc`
- `GDI32!CreateFontIndirectW` at `0x180009abc`
- `GDI32!DeleteObject` at `0x180009b0d`
- `GDI32!DeleteObject` at `0x180009b0d`

## pseudocode

```c
void __fastcall BestFitOnDesktop(struct tagRECT *a1)
{
  HFONT v2; // rax
  HFONT v3; // rdi
  int ScreenAveCharDimensions; // eax
  LONG v5; // eax
  int v6; // edx
  LONG bottom; // ecx
  LONG v8; // eax
  LONG v9; // eax
  int nNumerator; // [rsp+30h] [rbp-49h] BYREF
  __int128 v11; // [rsp+38h] [rbp-41h] BYREF
  int pvParam; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v13[12]; // [rsp+54h] [rbp-25h] BYREF
  LOGFONTW lf; // [rsp+60h] [rbp-19h] BYREF

  SetRect(a1, 35, 10, 800, 496);
  memset_0(v13, 0, 0x68u);
  pvParam = 108;
  if ( SystemParametersInfoW(0x2Du, 0x6Cu, &pvParam, 0) )
  {
    v2 = CreateFontIndirectW(&lf);
    v3 = v2;
    if ( v2 )
    {
      nNumerator = 0;
      ScreenAveCharDimensions = GetScreenAveCharDimensions(v2, &nNumerator);
      if ( ScreenAveCharDimensions )
      {
        v5 = MulDiv(a1->right, ScreenAveCharDimensions, 7);
        v6 = nNumerator;
        bottom = a1->bottom;
        a1->right = v5;
        a1->bottom = MulDiv(bottom, v6, 16);
      }
      DeleteObject(v3);
    }
  }
  v11 = 0;
  if ( SystemParametersInfoW(0x30u, 0, &v11, 0) )
  {
    v8 = DWORD2(v11) - v11;
    if ( DWORD2(v11) - (int)v11 >= a1->right )
    {
      a1->left = v11 + (v8 - a1->right) / 2;
    }
    else
    {
      a1->left = v11;
      a1->right = v8;
    }
    v9 = HIDWORD(v11) - DWORD1(v11);
    if ( HIDWORD(v11) - DWORD1(v11) >= a1->bottom )
    {
      a1->top = DWORD1(v11) + (v9 - a1->bottom) / 2;
    }
    else
    {
      a1->top = DWORD1(v11);
      a1->bottom = v9;
    }
  }
}

```

## disassembly

```asm
0x180009a48  mov     [rsp-8+arg_8], rbx
0x180009a4d  mov     [rsp-8+arg_10], rdi
0x180009a52  push    rbp
0x180009a53  lea     rbp, [rsp-57h]
0x180009a58  sub     rsp, 0D0h
0x180009a5f  mov     rax, cs:__security_cookie
0x180009a66  xor     rax, rsp
0x180009a69  mov     [rbp+57h+var_10], rax
0x180009a6d  mov     edx, 23h ; '#'; xLeft
0x180009a72  mov     [rsp+0D0h+yBottom], 1F0h; yBottom
0x180009a7a  mov     r9d, 320h; xRight
0x180009a80  mov     rbx, rcx
0x180009a83  lea     r8d, [rdx-19h]; yTop
0x180009a87  call    cs:__imp_SetRect
0x180009a8d  xor     edx, edx; Val
0x180009a8f  lea     rcx, [rbp+57h+var_7C]; void *
0x180009a93  lea     r8d, [rdx+68h]; Size
0x180009a97  call    memset_0
0x180009a9c  mov     edx, 6Ch ; 'l'; uiParam
0x180009aa1  lea     r8, [rbp+57h+pvParam]; pvParam
0x180009aa5  xor     r9d, r9d; fWinIni
0x180009aa8  mov     [rbp+57h+pvParam], edx
0x180009aab  lea     ecx, [rdx-3Fh]; uiAction
0x180009aae  call    cs:__imp_SystemParametersInfoW
0x180009ab4  test    eax, eax
0x180009ab6  jz      short loc_180009B13
0x180009ab8  lea     rcx, [rbp+57h+lf]; lplf
0x180009abc  call    cs:__imp_CreateFontIndirectW
0x180009ac2  mov     rdi, rax
0x180009ac5  test    rax, rax
0x180009ac8  jz      short loc_180009B13
0x180009aca  lea     rdx, [rbp+57h+nNumerator]; int *
0x180009ace  mov     [rbp+57h+nNumerator], 0
0x180009ad5  mov     rcx, rax; h
0x180009ad8  call    ?GetScreenAveCharDimensions@@YAHPEAUHFONT__@@PEAH@Z; GetScreenAveCharDimensions(HFONT__ *,int *)
0x180009add  test    eax, eax
0x180009adf  jz      short loc_180009B0A
0x180009ae1  mov     ecx, [rbx+8]; nNumber
0x180009ae4  mov     r8d, 7; nDenominator
0x180009aea  mov     edx, eax; nNumerator
0x180009aec  call    cs:__imp_MulDiv
0x180009af2  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x180009af5  mov     r8d, 10h; nDenominator
0x180009afb  mov     ecx, [rbx+0Ch]; nNumber
0x180009afe  mov     [rbx+8], eax
0x180009b01  call    cs:__imp_MulDiv
0x180009b07  mov     [rbx+0Ch], eax
0x180009b0a  mov     rcx, rdi; ho
0x180009b0d  call    cs:__imp_DeleteObject
0x180009b13  xor     edx, edx; uiParam
0x180009b15  lea     r8, [rbp+57h+var_98]; pvParam
0x180009b19  xorps   xmm0, xmm0
0x180009b1c  xor     r9d, r9d; fWinIni
0x180009b1f  movups  [rbp+57h+var_98], xmm0
0x180009b23  lea     ecx, [rdx+30h]; uiAction
0x180009b26  call    cs:__imp_SystemParametersInfoW
0x180009b2c  test    eax, eax
0x180009b2e  jz      short loc_180009B76
0x180009b30  mov     eax, dword ptr [rbp+57h+var_98+8]
0x180009b33  mov     r8d, 2
0x180009b39  mov     ecx, dword ptr [rbp+57h+var_98]
0x180009b3c  sub     eax, ecx
0x180009b3e  cmp     eax, [rbx+8]
0x180009b41  jge     short loc_180009B4A
0x180009b43  mov     [rbx], ecx
0x180009b45  mov     [rbx+8], eax
0x180009b48  jmp     short loc_180009B55
0x180009b4a  sub     eax, [rbx+8]
0x180009b4d  cdq
0x180009b4e  idiv    r8d
0x180009b51  add     eax, ecx
0x180009b53  mov     [rbx], eax
0x180009b55  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x180009b58  mov     ecx, dword ptr [rbp+57h+var_98+4]
0x180009b5b  sub     eax, ecx
0x180009b5d  cmp     eax, [rbx+0Ch]
0x180009b60  jge     short loc_180009B6A
0x180009b62  mov     [rbx+4], ecx
0x180009b65  mov     [rbx+0Ch], eax
0x180009b68  jmp     short loc_180009B76
0x180009b6a  sub     eax, [rbx+0Ch]
0x180009b6d  cdq
0x180009b6e  idiv    r8d
0x180009b71  add     eax, ecx
0x180009b73  mov     [rbx+4], eax
0x180009b76  mov     rcx, [rbp+57h+var_10]
0x180009b7a  xor     rcx, rsp; StackCookie
0x180009b7d  call    __security_check_cookie
0x180009b82  lea     r11, [rsp+0D0h+var_s0]
0x180009b8a  mov     rbx, [r11+18h]
0x180009b8e  mov     rdi, [r11+20h]
0x180009b92  mov     rsp, r11
0x180009b95  pop     rbp
0x180009b96  retn
```
