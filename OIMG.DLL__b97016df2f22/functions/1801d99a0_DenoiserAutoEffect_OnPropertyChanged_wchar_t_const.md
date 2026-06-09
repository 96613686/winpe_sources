# DenoiserAutoEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801d99a0`
- end: `0x1801d9f97`
- name: `?OnPropertyChanged@DenoiserAutoEffect@@UEAAJPEB_W@Z`
- size: `1527`
- prototype: `__int64 __fastcall(DenoiserAutoEffect *__hidden this, PCNZWCH lpString1)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18019d308`
- `0x1801d9870`
- `0x1801d99a0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801d9a1a`
- `KERNEL32!CompareStringW` at `0x1801d9a46`
- `KERNEL32!CompareStringW` at `0x1801d9a72`
- `KERNEL32!CompareStringW` at `0x1801d9a9e`
- `KERNEL32!CompareStringW` at `0x1801d9aca`
- `KERNEL32!CompareStringW` at `0x1801d9af6`
- `KERNEL32!CompareStringW` at `0x1801d9b22`
- `KERNEL32!CompareStringW` at `0x1801d9b4e`
- `KERNEL32!CompareStringW` at `0x1801d9b7a`
- `KERNEL32!CompareStringW` at `0x1801d9c31`
- `KERNEL32!CompareStringW` at `0x1801d9d01`
- `KERNEL32!CompareStringW` at `0x1801d9a1a`
- `KERNEL32!CompareStringW` at `0x1801d9a46`
- `KERNEL32!CompareStringW` at `0x1801d9a72`
- `KERNEL32!CompareStringW` at `0x1801d9a9e`
- `KERNEL32!CompareStringW` at `0x1801d9aca`
- `KERNEL32!CompareStringW` at `0x1801d9af6`
- `KERNEL32!CompareStringW` at `0x1801d9b22`
- `KERNEL32!CompareStringW` at `0x1801d9b4e`
- `KERNEL32!CompareStringW` at `0x1801d9b7a`
- `KERNEL32!CompareStringW` at `0x1801d9c31`
- `KERNEL32!CompareStringW` at `0x1801d9d01`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9b9d`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9c61`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9dcd`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9b9d`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9c61`
- `OLEAUT32!__imp_VariantInit` at `0x1801d9dcd`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9cde`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9da6`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9eba`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9cde`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9da6`
- `OLEAUT32!__imp_VariantClear` at `0x1801d9eba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DenoiserAutoEffect::OnPropertyChanged(DenoiserAutoEffect *this, PCNZWCH lpString1)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  double dblVal; // xmm6_8
  int v8; // eax
  unsigned __int16 v9; // r8
  __int64 v10; // r9
  __int64 (__fastcall *v11)(__int64, PCNZWCH, VARIANTARG *); // r10
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  VARIANTARG pvarg; // [rsp+50h] [rbp-68h] BYREF
  VARIANTARG v19; // [rsp+70h] [rbp-48h] BYREF
  __int64 *v20; // [rsp+C8h] [rbp+10h] BYREF

  if ( !lpString1 )
    ATL::BaseAtlThrow(-2147467261);
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
  if ( v4 < 0 )
    ATL::BaseAtlThrow(v4);
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"DenoiserQuality", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"UseLocalBandNeighborhood", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"UseParentBandNeighborhoodMaxLevel", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseWaveletModel", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"SignalStatistics", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"DenoiserDomain", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v13 = (*(__int64 (__fastcall **)(_QWORD, PCNZWCH, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
            *((_QWORD *)this + 16),
            lpString1,
            &pvarg);
    if ( v13 == -2147024882 || v13 == -2045378032 || v13 == -2045312765 || v13 == -2045247216 )
      ATL::BaseAtlThrow(v13);
    if ( v13 < 0 )
      ATL::BaseAtlThrow(v13);
    v20 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
            *((_QWORD *)this + 18),
            L"DenoiserRenderEffectId",
            &v20);
    if ( v14 < 0 )
      ATL::BaseAtlThrow(v14);
    if ( !v20 )
      ATL::BaseAtlThrow(-2045247222);
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    v15 = *v20;
    v19 = pvarg;
    v16 = (*(__int64 (__fastcall **)(__int64 *, PCNZWCH, VARIANTARG *))(v15 + 104))(v20, lpString1, &v19);
    if ( v16 < 0 )
      ATL::BaseAtlThrow(v16);
    goto LABEL_41;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseLevelLuminance", -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseLevelChrominance", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = (*(__int64 (__fastcall **)(_QWORD, PCNZWCH, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           lpString1,
           &pvarg);
    if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
      ATL::BaseAtlThrow(v6);
    if ( v6 < 0 )
      ATL::BaseAtlThrow(v6);
    dblVal = pvarg.dblVal;
    if ( pvarg.dblVal < 0.0 || pvarg.dblVal > 4.0 )
      ATL::BaseAtlThrow(-2147024809);
    VariantClear(&pvarg);
    CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseLevelLuminance", -1);
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
           *((_QWORD *)this + 18),
           L"DenoiserRenderEffectId",
           &v20);
    if ( v8 < 0 )
      ATL::BaseAtlThrow(v8);
    if ( !v20 )
      ATL::BaseAtlThrow(-2045247222);
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    pvarg = *(VARIANTARG *)ATL::CComVariant::CComVariant((ATL::CComVariant *)&v19, dblVal, v9);
    v12 = v11(v10, lpString1, &pvarg);
    VariantClear(&v19);
    if ( v12 < 0 )
      ATL::BaseAtlThrow(v12);
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"ProgressCallback", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v5 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             L"ProgressCallback",
             &pvarg);
      if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
        ATL::BaseAtlThrow(v5);
      if ( v5 < 0 )
        ATL::BaseAtlThrow(v5);
      if ( pvarg.vt && pvarg.vt != 16387 )
        ATL::BaseAtlThrow(-2147024809);
LABEL_41:
      VariantClear(&pvarg);
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"_AutoFix", -1) == 2 )
      DenoiserAutoEffect::AutoFix(this);
  }
  return 0;
}

```

## disassembly

```asm
0x1801d99a0  mov     rax, rsp
0x1801d99a3  mov     [rax+8], rbx
0x1801d99a7  mov     [rax+18h], rsi
0x1801d99ab  mov     [rax+20h], rdi
0x1801d99af  push    r12
0x1801d99b1  push    r13
0x1801d99b3  push    r14
0x1801d99b5  sub     rsp, 0A0h
0x1801d99bc  movaps  xmmword ptr [rax-28h], xmm6
0x1801d99c0  mov     rbx, rdx
0x1801d99c3  mov     rdi, rcx
0x1801d99c6  xor     esi, esi
0x1801d99c8  test    rdx, rdx
0x1801d99cb  jz      loc_1801D9EFA
0x1801d99d1  mov     rcx, [rcx+80h]
0x1801d99d8  mov     rax, [rcx]
0x1801d99db  mov     rax, [rax+110h]
0x1801d99e2  call    cs:__guard_dispatch_icall_fptr
0x1801d99e8  test    eax, eax
0x1801d99ea  js      loc_1801D9F04
0x1801d99f0  or      r14d, 0FFFFFFFFh
0x1801d99f4  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d99f9  lea     rax, aDenoiserqualit; "DenoiserQuality"
0x1801d9a00  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9a05  mov     r9d, r14d; cchCount1
0x1801d9a08  mov     r8, rbx; lpString1
0x1801d9a0b  lea     r12d, [r14+2]
0x1801d9a0f  mov     edx, r12d; dwCmpFlags
0x1801d9a12  lea     r13d, [r12+7Eh]
0x1801d9a17  mov     ecx, r13d; Locale
0x1801d9a1a  call    cs:__imp_CompareStringW
0x1801d9a20  cmp     eax, 2
0x1801d9a23  jz      loc_1801D9DB9
0x1801d9a29  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9a2e  lea     rax, aUselocalbandne; "UseLocalBandNeighborhood"
0x1801d9a35  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9a3a  mov     r9d, r14d; cchCount1
0x1801d9a3d  mov     r8, rbx; lpString1
0x1801d9a40  mov     edx, r12d; dwCmpFlags
0x1801d9a43  mov     ecx, r13d; Locale
0x1801d9a46  call    cs:__imp_CompareStringW
0x1801d9a4c  cmp     eax, 2
0x1801d9a4f  jz      loc_1801D9DB9
0x1801d9a55  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9a5a  lea     rax, aUseparentbandn; "UseParentBandNeighborhoodMaxLevel"
0x1801d9a61  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9a66  mov     r9d, r14d; cchCount1
0x1801d9a69  mov     r8, rbx; lpString1
0x1801d9a6c  mov     edx, r12d; dwCmpFlags
0x1801d9a6f  mov     ecx, r13d; Locale
0x1801d9a72  call    cs:__imp_CompareStringW
0x1801d9a78  cmp     eax, 2
0x1801d9a7b  jz      loc_1801D9DB9
0x1801d9a81  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9a86  lea     rax, aNoisewaveletmo; "NoiseWaveletModel"
0x1801d9a8d  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9a92  mov     r9d, r14d; cchCount1
0x1801d9a95  mov     r8, rbx; lpString1
0x1801d9a98  mov     edx, r12d; dwCmpFlags
0x1801d9a9b  mov     ecx, r13d; Locale
0x1801d9a9e  call    cs:__imp_CompareStringW
0x1801d9aa4  cmp     eax, 2
0x1801d9aa7  jz      loc_1801D9DB9
0x1801d9aad  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9ab2  lea     rax, aSignalstatisti; "SignalStatistics"
0x1801d9ab9  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9abe  mov     r9d, r14d; cchCount1
0x1801d9ac1  mov     r8, rbx; lpString1
0x1801d9ac4  mov     edx, r12d; dwCmpFlags
0x1801d9ac7  mov     ecx, r13d; Locale
0x1801d9aca  call    cs:__imp_CompareStringW
0x1801d9ad0  cmp     eax, 2
0x1801d9ad3  jz      loc_1801D9DB9
0x1801d9ad9  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9ade  lea     rax, aDenoiserdomain; "DenoiserDomain"
0x1801d9ae5  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9aea  mov     r9d, r14d; cchCount1
0x1801d9aed  mov     r8, rbx; lpString1
0x1801d9af0  mov     edx, r12d; dwCmpFlags
0x1801d9af3  mov     ecx, r13d; Locale
0x1801d9af6  call    cs:__imp_CompareStringW
0x1801d9afc  cmp     eax, 2
0x1801d9aff  jz      loc_1801D9DB9
0x1801d9b05  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9b0a  lea     rax, aNoiselevellumi; "NoiseLevelLuminance"
0x1801d9b11  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9b16  mov     r9d, r14d; cchCount1
0x1801d9b19  mov     r8, rbx; lpString1
0x1801d9b1c  mov     edx, r12d; dwCmpFlags
0x1801d9b1f  mov     ecx, r13d; Locale
0x1801d9b22  call    cs:__imp_CompareStringW
0x1801d9b28  cmp     eax, 2
0x1801d9b2b  jz      loc_1801D9C4D
0x1801d9b31  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9b36  lea     rax, aNoiselevelchro; "NoiseLevelChrominance"
0x1801d9b3d  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9b42  mov     r9d, r14d; cchCount1
0x1801d9b45  mov     r8, rbx; lpString1
0x1801d9b48  mov     edx, r12d; dwCmpFlags
0x1801d9b4b  mov     ecx, r13d; Locale
0x1801d9b4e  call    cs:__imp_CompareStringW
0x1801d9b54  cmp     eax, 2
0x1801d9b57  jz      loc_1801D9C4D
0x1801d9b5d  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9b62  lea     rax, aProgresscallba; "ProgressCallback"
0x1801d9b69  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9b6e  mov     r9d, r14d; cchCount1
0x1801d9b71  mov     r8, rbx; lpString1
0x1801d9b74  mov     edx, r12d; dwCmpFlags
0x1801d9b77  mov     ecx, r13d; Locale
0x1801d9b7a  call    cs:__imp_CompareStringW
0x1801d9b80  cmp     eax, 2
0x1801d9b83  jnz     loc_1801D9C14
0x1801d9b89  xorps   xmm0, xmm0
0x1801d9b8c  xor     eax, eax
0x1801d9b8e  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1801d9b93  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1801d9b98  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801d9b9d  call    cs:__imp_VariantInit
0x1801d9ba3  mov     rcx, [rdi+80h]
0x1801d9baa  mov     rax, [rcx]
0x1801d9bad  lea     r8, [rsp+0B8h+pvarg]
0x1801d9bb2  lea     rdx, aProgresscallba; "ProgressCallback"
0x1801d9bb9  mov     rax, [rax+60h]
0x1801d9bbd  call    cs:__guard_dispatch_icall_fptr
0x1801d9bc3  cmp     eax, 8007000Eh
0x1801d9bc8  jz      loc_1801D9F20
0x1801d9bce  cmp     eax, 86160210h
0x1801d9bd3  jz      loc_1801D9F20
0x1801d9bd9  cmp     eax, 86170103h
0x1801d9bde  jz      loc_1801D9F20
0x1801d9be4  cmp     eax, 86180110h
0x1801d9be9  jz      loc_1801D9F20
0x1801d9bef  test    eax, eax
0x1801d9bf1  js      loc_1801D9F0F
0x1801d9bf7  movzx   eax, word ptr [rsp+0B8h+pvarg]
0x1801d9bfc  test    ax, ax
0x1801d9bff  jz      short loc_1801D9C0F
0x1801d9c01  mov     ecx, 4003h
0x1801d9c06  cmp     ax, cx
0x1801d9c09  jnz     loc_1801D9F16
0x1801d9c0f  jmp     loc_1801D9EB5
0x1801d9c14  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9c19  lea     rax, aAutofix; "_AutoFix"
0x1801d9c20  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9c25  mov     r9d, r14d; cchCount1
0x1801d9c28  mov     r8, rbx; lpString1
0x1801d9c2b  mov     edx, r12d; dwCmpFlags
0x1801d9c2e  mov     ecx, r13d; Locale
0x1801d9c31  call    cs:__imp_CompareStringW
0x1801d9c37  cmp     eax, 2
0x1801d9c3a  jnz     loc_1801D9EC0
0x1801d9c40  mov     rcx, rdi; this
0x1801d9c43  call    ?AutoFix@DenoiserAutoEffect@@AEAAXXZ; DenoiserAutoEffect::AutoFix(void)
0x1801d9c48  jmp     loc_1801D9EC0
0x1801d9c4d  xorps   xmm0, xmm0
0x1801d9c50  xor     eax, eax
0x1801d9c52  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1801d9c57  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1801d9c5c  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801d9c61  call    cs:__imp_VariantInit
0x1801d9c67  mov     rcx, [rdi+80h]
0x1801d9c6e  mov     rax, [rcx]
0x1801d9c71  lea     r8, [rsp+0B8h+pvarg]
0x1801d9c76  mov     rdx, rbx
0x1801d9c79  mov     rax, [rax+60h]
0x1801d9c7d  call    cs:__guard_dispatch_icall_fptr
0x1801d9c83  cmp     eax, 8007000Eh
0x1801d9c88  jz      loc_1801D9F63
0x1801d9c8e  cmp     eax, 86160210h
0x1801d9c93  jz      loc_1801D9F63
0x1801d9c99  cmp     eax, 86170103h
0x1801d9c9e  jz      loc_1801D9F63
0x1801d9ca4  cmp     eax, 86180110h
0x1801d9ca9  jz      loc_1801D9F63
0x1801d9caf  test    eax, eax
0x1801d9cb1  js      loc_1801D9F2B
0x1801d9cb7  movsd   xmm6, qword ptr [rsp+0B8h+pvarg+8]
0x1801d9cbd  comisd  xmm6, cs:__real@0000000000000000
0x1801d9cc5  jb      loc_1801D9F59
0x1801d9ccb  comisd  xmm6, cs:__real@4010000000000000
0x1801d9cd3  ja      loc_1801D9F59
0x1801d9cd9  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801d9cde  call    cs:__imp_VariantClear
0x1801d9ce4  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1801d9ce9  lea     rax, aNoiselevellumi; "NoiseLevelLuminance"
0x1801d9cf0  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1801d9cf5  mov     r9d, r14d; cchCount1
0x1801d9cf8  mov     r8, rbx; lpString1
0x1801d9cfb  mov     edx, r12d; dwCmpFlags
0x1801d9cfe  mov     ecx, r13d; Locale
0x1801d9d01  call    cs:__imp_CompareStringW
0x1801d9d07  mov     [rsp+0B8h+arg_8], rsi
0x1801d9d0f  mov     rcx, [rdi+90h]
0x1801d9d16  mov     rax, [rcx]
0x1801d9d19  lea     r8, [rsp+0B8h+arg_8]
0x1801d9d21  lea     rdx, aDenoiserrender_0; "DenoiserRenderEffectId"
0x1801d9d28  mov     rax, [rax+98h]
0x1801d9d2f  call    cs:__guard_dispatch_icall_fptr
0x1801d9d35  test    eax, eax
0x1801d9d37  js      loc_1801D9F36
0x1801d9d3d  mov     rcx, [rsp+0B8h+arg_8]
0x1801d9d45  test    rcx, rcx
0x1801d9d48  jz      loc_1801D9F3D
0x1801d9d4e  mov     rax, [rcx]
0x1801d9d51  mov     rax, [rax+10h]
0x1801d9d55  call    cs:__guard_dispatch_icall_fptr
0x1801d9d5b  mov     r9, [rsp+0B8h+arg_8]
0x1801d9d63  mov     rax, [r9]
0x1801d9d66  mov     r10, [rax+68h]
0x1801d9d6a  movaps  xmm1, xmm6; double
0x1801d9d6d  lea     rcx, [rsp+0B8h+var_48]; this
0x1801d9d72  call    ??0CComVariant@ATL@@QEAA@NG@Z; ATL::CComVariant::CComVariant(double,ushort)
0x1801d9d77  nop
0x1801d9d78  movups  xmm0, xmmword ptr [rax]
0x1801d9d7b  movaps  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1801d9d80  movsd   xmm1, qword ptr [rax+10h]
0x1801d9d85  movsd   qword ptr [rsp+0B8h+pvarg+10h], xmm1
0x1801d9d8b  lea     r8, [rsp+0B8h+pvarg]
0x1801d9d90  mov     rdx, rbx
0x1801d9d93  mov     rcx, r9
0x1801d9d96  mov     rax, r10
0x1801d9d99  call    cs:__guard_dispatch_icall_fptr
0x1801d9d9f  mov     ebx, eax
0x1801d9da1  lea     rcx, [rsp+0B8h+var_48]; pvarg
0x1801d9da6  call    cs:__imp_VariantClear
0x1801d9dac  test    ebx, ebx
0x1801d9dae  js      loc_1801D9F47
0x1801d9db4  jmp     loc_1801D9EC0
0x1801d9db9  xorps   xmm0, xmm0
0x1801d9dbc  xor     eax, eax
0x1801d9dbe  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1801d9dc3  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1801d9dc8  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801d9dcd  call    cs:__imp_VariantInit
0x1801d9dd3  mov     rcx, [rdi+80h]
0x1801d9dda  mov     rax, [rcx]
0x1801d9ddd  lea     r8, [rsp+0B8h+pvarg]
0x1801d9de2  mov     rdx, rbx
0x1801d9de5  mov     rax, [rax+60h]
0x1801d9de9  call    cs:__guard_dispatch_icall_fptr
0x1801d9def  cmp     eax, 8007000Eh
0x1801d9df4  jz      loc_1801D9F8E
0x1801d9dfa  cmp     eax, 86160210h
0x1801d9dff  jz      loc_1801D9F8E
0x1801d9e05  cmp     eax, 86170103h
0x1801d9e0a  jz      loc_1801D9F8E
0x1801d9e10  cmp     eax, 86180110h
0x1801d9e15  jz      loc_1801D9F8E
0x1801d9e1b  test    eax, eax
0x1801d9e1d  js      loc_1801D9F6F
0x1801d9e23  mov     [rsp+0B8h+arg_8], rsi
0x1801d9e2b  mov     rcx, [rdi+90h]
0x1801d9e32  mov     rax, [rcx]
0x1801d9e35  lea     r8, [rsp+0B8h+arg_8]
0x1801d9e3d  lea     rdx, aDenoiserrender_0; "DenoiserRenderEffectId"
0x1801d9e44  mov     rax, [rax+98h]
0x1801d9e4b  call    cs:__guard_dispatch_icall_fptr
0x1801d9e51  test    eax, eax
0x1801d9e53  js      loc_1801D9F76
0x1801d9e59  mov     rcx, [rsp+0B8h+arg_8]
0x1801d9e61  test    rcx, rcx
0x1801d9e64  jz      loc_1801D9F7D
0x1801d9e6a  mov     rax, [rcx]
0x1801d9e6d  mov     rax, [rax+10h]
0x1801d9e71  call    cs:__guard_dispatch_icall_fptr
0x1801d9e77  mov     rcx, [rsp+0B8h+arg_8]
0x1801d9e7f  mov     rax, [rcx]
0x1801d9e82  movups  xmm0, xmmword ptr [rsp+0B8h+pvarg]
0x1801d9e87  movaps  xmmword ptr [rsp+0B8h+var_48], xmm0
0x1801d9e8c  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+10h]
0x1801d9e92  movsd   qword ptr [rsp+0B8h+var_48+10h], xmm1
0x1801d9e9b  lea     r8, [rsp+0B8h+var_48]
0x1801d9ea0  mov     rdx, rbx
0x1801d9ea3  mov     rax, [rax+68h]
0x1801d9ea7  call    cs:__guard_dispatch_icall_fptr
0x1801d9ead  test    eax, eax
0x1801d9eaf  js      loc_1801D9F87
0x1801d9eb5  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801d9eba  call    cs:__imp_VariantClear
0x1801d9ec0  xor     eax, eax
0x1801d9ec2  jmp     short loc_1801D9ED7
0x1801d9ec4  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x1801d9ecb  mov     edx, 86160101h
0x1801d9ed0  cmp     ax, 216h
0x1801d9ed4  cmovz   eax, edx
0x1801d9ed7  lea     r11, [rsp+0B8h+var_18]
0x1801d9edf  mov     rbx, [r11+20h]
0x1801d9ee3  mov     rsi, [r11+30h]
0x1801d9ee7  mov     rdi, [r11+38h]
0x1801d9eeb  movaps  xmm6, xmmword ptr [r11-10h]
0x1801d9ef0  mov     rsp, r11
0x1801d9ef3  pop     r14
0x1801d9ef5  pop     r13
0x1801d9ef7  pop     r12
0x1801d9ef9  retn
0x1801d9efa  mov     ecx, 80004003h; int
0x1801d9eff  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9f04  mov     ecx, eax; int
0x1801d9f06  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
  ... truncated ...
```
