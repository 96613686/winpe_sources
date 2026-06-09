# BestFitOnDesktop_OCM(tagRECT *)

- ea: `0x180031594`
- end: `0x1800316e3`
- name: `?BestFitOnDesktop_OCM@@YAXPEAUtagRECT@@@Z`
- size: `335`
- prototype: `void __fastcall(struct tagRECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003f9ec`

## callees

- `0x18000b1a4`
- `0x180031594`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180031638`
- `KERNEL32!MulDiv` at `0x18003164d`
- `KERNEL32!MulDiv` at `0x180031638`
- `KERNEL32!MulDiv` at `0x18003164d`
- `USER32!SetRect` at `0x1800315d3`
- `USER32!SetRect` at `0x1800315d3`
- `USER32!SystemParametersInfoW` at `0x1800315fa`
- `USER32!SystemParametersInfoW` at `0x180031672`
- `USER32!SystemParametersInfoW` at `0x1800315fa`
- `USER32!SystemParametersInfoW` at `0x180031672`
- `GDI32!CreateFontIndirectW` at `0x180031608`
- `GDI32!CreateFontIndirectW` at `0x180031608`
- `GDI32!DeleteObject` at `0x180031659`
- `GDI32!DeleteObject` at `0x180031659`

## pseudocode

```c
void __fastcall BestFitOnDesktop_OCM(struct tagRECT *a1)
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

  SetRect(a1, 35, 10, 500, 400);
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
0x180031594  mov     [rsp-8+arg_8], rbx
0x180031599  mov     [rsp-8+arg_10], rdi
0x18003159e  push    rbp
0x18003159f  lea     rbp, [rsp-57h]
0x1800315a4  sub     rsp, 0D0h
0x1800315ab  mov     rax, cs:__security_cookie
0x1800315b2  xor     rax, rsp
0x1800315b5  mov     [rbp+57h+var_10], rax
0x1800315b9  mov     edx, 23h ; '#'; xLeft
0x1800315be  mov     [rsp+0D0h+yBottom], 190h; yBottom
0x1800315c6  mov     r9d, 1F4h; xRight
0x1800315cc  mov     rbx, rcx
0x1800315cf  lea     r8d, [rdx-19h]; yTop
0x1800315d3  call    cs:__imp_SetRect
0x1800315d9  xor     edx, edx; Val
0x1800315db  lea     rcx, [rbp+57h+var_7C]; void *
0x1800315df  lea     r8d, [rdx+68h]; Size
0x1800315e3  call    memset_0
0x1800315e8  mov     edx, 6Ch ; 'l'; uiParam
0x1800315ed  lea     r8, [rbp+57h+pvParam]; pvParam
0x1800315f1  xor     r9d, r9d; fWinIni
0x1800315f4  mov     [rbp+57h+pvParam], edx
0x1800315f7  lea     ecx, [rdx-3Fh]; uiAction
0x1800315fa  call    cs:__imp_SystemParametersInfoW
0x180031600  test    eax, eax
0x180031602  jz      short loc_18003165F
0x180031604  lea     rcx, [rbp+57h+lf]; lplf
0x180031608  call    cs:__imp_CreateFontIndirectW
0x18003160e  mov     rdi, rax
0x180031611  test    rax, rax
0x180031614  jz      short loc_18003165F
0x180031616  lea     rdx, [rbp+57h+nNumerator]; int *
0x18003161a  mov     [rbp+57h+nNumerator], 0
0x180031621  mov     rcx, rax; h
0x180031624  call    ?GetScreenAveCharDimensions@@YAHPEAUHFONT__@@PEAH@Z; GetScreenAveCharDimensions(HFONT__ *,int *)
0x180031629  test    eax, eax
0x18003162b  jz      short loc_180031656
0x18003162d  mov     ecx, [rbx+8]; nNumber
0x180031630  mov     r8d, 7; nDenominator
0x180031636  mov     edx, eax; nNumerator
0x180031638  call    cs:__imp_MulDiv
0x18003163e  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x180031641  mov     r8d, 10h; nDenominator
0x180031647  mov     ecx, [rbx+0Ch]; nNumber
0x18003164a  mov     [rbx+8], eax
0x18003164d  call    cs:__imp_MulDiv
0x180031653  mov     [rbx+0Ch], eax
0x180031656  mov     rcx, rdi; ho
0x180031659  call    cs:__imp_DeleteObject
0x18003165f  xor     edx, edx; uiParam
0x180031661  lea     r8, [rbp+57h+var_98]; pvParam
0x180031665  xorps   xmm0, xmm0
0x180031668  xor     r9d, r9d; fWinIni
0x18003166b  movups  [rbp+57h+var_98], xmm0
0x18003166f  lea     ecx, [rdx+30h]; uiAction
0x180031672  call    cs:__imp_SystemParametersInfoW
0x180031678  test    eax, eax
0x18003167a  jz      short loc_1800316C2
0x18003167c  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18003167f  mov     r8d, 2
0x180031685  mov     ecx, dword ptr [rbp+57h+var_98]
0x180031688  sub     eax, ecx
0x18003168a  cmp     eax, [rbx+8]
0x18003168d  jge     short loc_180031696
0x18003168f  mov     [rbx], ecx
0x180031691  mov     [rbx+8], eax
0x180031694  jmp     short loc_1800316A1
0x180031696  sub     eax, [rbx+8]
0x180031699  cdq
0x18003169a  idiv    r8d
0x18003169d  add     eax, ecx
0x18003169f  mov     [rbx], eax
0x1800316a1  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x1800316a4  mov     ecx, dword ptr [rbp+57h+var_98+4]
0x1800316a7  sub     eax, ecx
0x1800316a9  cmp     eax, [rbx+0Ch]
0x1800316ac  jge     short loc_1800316B6
0x1800316ae  mov     [rbx+4], ecx
0x1800316b1  mov     [rbx+0Ch], eax
0x1800316b4  jmp     short loc_1800316C2
0x1800316b6  sub     eax, [rbx+0Ch]
0x1800316b9  cdq
0x1800316ba  idiv    r8d
0x1800316bd  add     eax, ecx
0x1800316bf  mov     [rbx+4], eax
0x1800316c2  mov     rcx, [rbp+57h+var_10]
0x1800316c6  xor     rcx, rsp; StackCookie
0x1800316c9  call    __security_check_cookie
0x1800316ce  lea     r11, [rsp+0D0h+var_s0]
0x1800316d6  mov     rbx, [r11+18h]
0x1800316da  mov     rdi, [r11+20h]
0x1800316de  mov     rsp, r11
0x1800316e1  pop     rbp
0x1800316e2  retn
```
