# Convolve1DEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801de1d0`
- end: `0x1801de4ad`
- name: `?OnPropertyChanged@Convolve1DEffect@@UEAAJPEB_W@Z`
- size: `733`
- prototype: `int(Convolve1DEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1801de1d0`
- `0x1801de4b0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801de283`
- `KERNEL32!CompareStringW` at `0x1801de2d0`
- `KERNEL32!CompareStringW` at `0x1801de31e`
- `KERNEL32!CompareStringW` at `0x1801de34d`
- `KERNEL32!CompareStringW` at `0x1801de379`
- `KERNEL32!CompareStringW` at `0x1801de3a5`
- `KERNEL32!CompareStringW` at `0x1801de3df`
- `KERNEL32!CompareStringW` at `0x1801de283`
- `KERNEL32!CompareStringW` at `0x1801de2d0`
- `KERNEL32!CompareStringW` at `0x1801de31e`
- `KERNEL32!CompareStringW` at `0x1801de34d`
- `KERNEL32!CompareStringW` at `0x1801de379`
- `KERNEL32!CompareStringW` at `0x1801de3a5`
- `KERNEL32!CompareStringW` at `0x1801de3df`
- `OLEAUT32!__imp_VariantInit` at `0x1801de206`
- `OLEAUT32!__imp_VariantInit` at `0x1801de206`
- `OLEAUT32!__imp_VariantClear` at `0x1801de412`
- `OLEAUT32!__imp_VariantClear` at `0x1801de412`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Convolve1DEffect::OnPropertyChanged(Convolve1DEffect *this, const wchar_t *a2)
{
  int v4; // eax
  int v5; // r8d
  VARIANTARG pvarg; // [rsp+48h] [rbp-30h] BYREF

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         a2,
         &pvarg);
  if ( v4 == -2147024882 || v4 == -2045378032 || v4 == -2045312765 || v4 == -2045247216 )
    ATL::BaseAtlThrow(v4);
  if ( v4 < 0 )
    ATL::BaseAtlThrow(v4);
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterOrientation", -1) == 2 )
  {
    if ( pvarg.vt != 3 )
      ATL::BaseAtlThrow(-2147024809);
    if ( pvarg.lVal > 1u )
      ATL::BaseAtlThrow(-2147024809);
    *((_DWORD *)this + 36) = pvarg.lVal;
    goto LABEL_28;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterAnchor", -1) == 2 )
  {
    if ( pvarg.vt != 3 )
      ATL::BaseAtlThrow(-2147024809);
    if ( pvarg.lVal < 0 )
      ATL::BaseAtlThrow(-2147024809);
    *((_DWORD *)this + 37) = pvarg.lVal;
    goto LABEL_28;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterCoefficients1", -1) == 2 )
  {
    v5 = 0;
LABEL_23:
    Convolve1DEffect::GetFilterCoefficients(this, (struct ATL::CComVariant *)&pvarg, v5);
    goto LABEL_28;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterCoefficients2", -1) == 2 )
  {
    v5 = 1;
    goto LABEL_23;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterCoefficients3", -1) == 2 )
  {
    v5 = 2;
    goto LABEL_23;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterCoefficients4", -1) == 2 )
  {
    v5 = 3;
    goto LABEL_23;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilterAlphaMode", -1) == 2 )
  {
    if ( pvarg.vt != 3 )
      ATL::BaseAtlThrow(-2147024809);
    if ( pvarg.lVal > 2u )
      ATL::BaseAtlThrow(-2147024809);
    *((_DWORD *)this + 39) = pvarg.lVal;
  }
LABEL_28:
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1801de1d0  mov     [rsp+arg_0], rbx
0x1801de1d5  mov     [rsp+arg_10], rsi
0x1801de1da  push    rdi
0x1801de1db  push    r12
0x1801de1dd  push    r14
0x1801de1df  sub     rsp, 60h
0x1801de1e3  mov     rdi, rdx
0x1801de1e6  mov     rbx, rcx
0x1801de1e9  test    rdx, rdx
0x1801de1ec  jz      loc_1801DE445
0x1801de1f2  xorps   xmm0, xmm0
0x1801de1f5  xor     eax, eax
0x1801de1f7  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801de1fc  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801de201  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801de206  call    cs:__imp_VariantInit
0x1801de20c  mov     rcx, [rbx+80h]
0x1801de213  mov     rax, [rcx]
0x1801de216  lea     r8, [rsp+78h+pvarg]
0x1801de21b  mov     rdx, rdi
0x1801de21e  mov     rax, [rax+60h]
0x1801de222  call    cs:__guard_dispatch_icall_fptr
0x1801de228  cmp     eax, 8007000Eh
0x1801de22d  jz      loc_1801DE4A4
0x1801de233  cmp     eax, 86160210h
0x1801de238  jz      loc_1801DE4A4
0x1801de23e  cmp     eax, 86170103h
0x1801de243  jz      loc_1801DE4A4
0x1801de249  cmp     eax, 86180110h
0x1801de24e  jz      loc_1801DE4A4
0x1801de254  test    eax, eax
0x1801de256  js      loc_1801DE461
0x1801de25c  or      esi, 0FFFFFFFFh
0x1801de25f  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de263  lea     rax, aFilterorientat; "FilterOrientation"
0x1801de26a  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de26f  mov     r9d, esi; cchCount1
0x1801de272  mov     r8, rdi; lpString1
0x1801de275  lea     r14d, [rsi+2]
0x1801de279  mov     edx, r14d; dwCmpFlags
0x1801de27c  lea     r12d, [r14+7Eh]
0x1801de280  mov     ecx, r12d; Locale
0x1801de283  call    cs:__imp_CompareStringW
0x1801de289  cmp     eax, 2
0x1801de28c  jnz     short loc_1801DE2B4
0x1801de28e  lea     eax, [rsi+4]
0x1801de291  cmp     word ptr [rsp+78h+pvarg], ax
0x1801de296  jnz     loc_1801DE468
0x1801de29c  mov     eax, dword ptr [rsp+78h+pvarg+8]
0x1801de2a0  cmp     eax, r14d
0x1801de2a3  ja      loc_1801DE472
0x1801de2a9  mov     [rbx+90h], eax
0x1801de2af  jmp     loc_1801DE40D
0x1801de2b4  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de2b8  lea     rax, aFilteranchor; "FilterAnchor"
0x1801de2bf  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de2c4  mov     r9d, esi; cchCount1
0x1801de2c7  mov     r8, rdi; lpString1
0x1801de2ca  mov     edx, r14d; dwCmpFlags
0x1801de2cd  mov     ecx, r12d; Locale
0x1801de2d0  call    cs:__imp_CompareStringW
0x1801de2d6  cmp     eax, 2
0x1801de2d9  jnz     short loc_1801DE302
0x1801de2db  mov     eax, 3
0x1801de2e0  cmp     word ptr [rsp+78h+pvarg], ax
0x1801de2e5  jnz     loc_1801DE47C
0x1801de2eb  mov     eax, dword ptr [rsp+78h+pvarg+8]
0x1801de2ef  test    eax, eax
0x1801de2f1  js      loc_1801DE486
0x1801de2f7  mov     [rbx+94h], eax
0x1801de2fd  jmp     loc_1801DE40D
0x1801de302  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de306  lea     rax, aFiltercoeffici_0; "FilterCoefficients1"
0x1801de30d  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de312  mov     r9d, esi; cchCount1
0x1801de315  mov     r8, rdi; lpString1
0x1801de318  mov     edx, r14d; dwCmpFlags
0x1801de31b  mov     ecx, r12d; Locale
0x1801de31e  call    cs:__imp_CompareStringW
0x1801de324  cmp     eax, 2
0x1801de327  jnz     short loc_1801DE331
0x1801de329  xor     r8d, r8d
0x1801de32c  jmp     loc_1801DE3B4
0x1801de331  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de335  lea     rax, aFiltercoeffici_2; "FilterCoefficients2"
0x1801de33c  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de341  mov     r9d, esi; cchCount1
0x1801de344  mov     r8, rdi; lpString1
0x1801de347  mov     edx, r14d; dwCmpFlags
0x1801de34a  mov     ecx, r12d; Locale
0x1801de34d  call    cs:__imp_CompareStringW
0x1801de353  cmp     eax, 2
0x1801de356  jnz     short loc_1801DE35D
0x1801de358  mov     r8d, r14d
0x1801de35b  jmp     short loc_1801DE3B4
0x1801de35d  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de361  lea     rax, aFiltercoeffici_1; "FilterCoefficients3"
0x1801de368  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de36d  mov     r9d, esi; cchCount1
0x1801de370  mov     r8, rdi; lpString1
0x1801de373  mov     edx, r14d; dwCmpFlags
0x1801de376  mov     ecx, r12d; Locale
0x1801de379  call    cs:__imp_CompareStringW
0x1801de37f  cmp     eax, 2
0x1801de382  jnz     short loc_1801DE389
0x1801de384  mov     r8d, eax
0x1801de387  jmp     short loc_1801DE3B4
0x1801de389  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de38d  lea     rax, aFiltercoeffici; "FilterCoefficients4"
0x1801de394  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de399  mov     r9d, esi; cchCount1
0x1801de39c  mov     r8, rdi; lpString1
0x1801de39f  mov     edx, r14d; dwCmpFlags
0x1801de3a2  mov     ecx, r12d; Locale
0x1801de3a5  call    cs:__imp_CompareStringW
0x1801de3ab  cmp     eax, 2
0x1801de3ae  jnz     short loc_1801DE3C3
0x1801de3b0  lea     r8d, [rax+1]; int
0x1801de3b4  lea     rdx, [rsp+78h+pvarg]; struct ATL::CComVariant *
0x1801de3b9  mov     rcx, rbx; this
0x1801de3bc  call    ?GetFilterCoefficients@Convolve1DEffect@@AEAAXPEAVCComVariant@ATL@@H@Z; Convolve1DEffect::GetFilterCoefficients(ATL::CComVariant *,int)
0x1801de3c1  jmp     short loc_1801DE40D
0x1801de3c3  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801de3c7  lea     rax, aFilteralphamod; "FilterAlphaMode"
0x1801de3ce  mov     [rsp+78h+lpString2], rax; lpString2
0x1801de3d3  mov     r9d, esi; cchCount1
0x1801de3d6  mov     r8, rdi; lpString1
0x1801de3d9  mov     edx, r14d; dwCmpFlags
0x1801de3dc  mov     ecx, r12d; Locale
0x1801de3df  call    cs:__imp_CompareStringW
0x1801de3e5  cmp     eax, 2
0x1801de3e8  jnz     short loc_1801DE40D
0x1801de3ea  mov     eax, 3
0x1801de3ef  cmp     word ptr [rsp+78h+pvarg], ax
0x1801de3f4  jnz     loc_1801DE490
0x1801de3fa  mov     eax, dword ptr [rsp+78h+pvarg+8]
0x1801de3fe  cmp     eax, 2
0x1801de401  ja      loc_1801DE49A
0x1801de407  mov     [rbx+9Ch], eax
0x1801de40d  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801de412  call    cs:__imp_VariantClear
0x1801de418  xor     eax, eax
0x1801de41a  jmp     short loc_1801DE42F
0x1801de41c  mov     eax, [rsp+78h+arg_8]
0x1801de423  mov     edx, 86160101h
0x1801de428  cmp     ax, 216h
0x1801de42c  cmovz   eax, edx
0x1801de42f  lea     r11, [rsp+78h+var_18]
0x1801de434  mov     rbx, [r11+20h]
0x1801de438  mov     rsi, [r11+30h]
0x1801de43c  mov     rsp, r11
0x1801de43f  pop     r14
0x1801de441  pop     r12
0x1801de443  pop     rdi
0x1801de444  retn
0x1801de445  mov     ecx, 80004003h; int
0x1801de44a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de450  jmp     short loc_1801DE460
0x1801de460  nop
0x1801de461  mov     ecx, eax; int
0x1801de463  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de468  mov     ecx, 80070057h; int
0x1801de46d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de472  mov     ecx, 80070057h; int
0x1801de477  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de47c  mov     ecx, 80070057h; int
0x1801de481  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de486  mov     ecx, 80070057h; int
0x1801de48b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de490  mov     ecx, 80070057h; int
0x1801de495  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de49a  mov     ecx, 80070057h; int
0x1801de49f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801de4a4  mov     ecx, eax; int
0x1801de4a6  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
