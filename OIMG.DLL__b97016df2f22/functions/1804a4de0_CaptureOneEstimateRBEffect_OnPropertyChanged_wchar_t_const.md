# CaptureOneEstimateRBEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1804a4de0`
- end: `0x1804a51bd`
- name: `?OnPropertyChanged@CaptureOneEstimateRBEffect@@UEAAJPEB_W@Z`
- size: `989`
- prototype: `int(CaptureOneEstimateRBEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18019a604`
- `0x1801a2ffc`
- `0x1801b1354`
- `0x18047ee78`
- `0x18048c8c8`
- `0x1804a4de0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1804a4e9a`
- `KERNEL32!CompareStringW` at `0x1804a4f55`
- `KERNEL32!CompareStringW` at `0x1804a5075`
- `KERNEL32!CompareStringW` at `0x1804a50b0`
- `KERNEL32!CompareStringW` at `0x1804a4e9a`
- `KERNEL32!CompareStringW` at `0x1804a4f55`
- `KERNEL32!CompareStringW` at `0x1804a5075`
- `KERNEL32!CompareStringW` at `0x1804a50b0`
- `OLEAUT32!__imp_VariantInit` at `0x1804a4e1d`
- `OLEAUT32!__imp_VariantInit` at `0x1804a4e1d`
- `OLEAUT32!__imp_VariantClear` at `0x1804a504c`
- `OLEAUT32!__imp_VariantClear` at `0x1804a504c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804a4f2e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804a5040`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804a4f2e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804a5040`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804a4fbb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804a4fbb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804a4f9a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804a4f9a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804a4f1c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804a502e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804a4f1c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804a502e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CaptureOneEstimateRBEffect::OnPropertyChanged(CaptureOneEstimateRBEffect *this, const wchar_t *a2)
{
  int v5; // eax
  int i; // edi
  float v7; // xmm0_4
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  VARIANTARG pvarg; // [rsp+48h] [rbp-40h] BYREF
  SAFEARRAY *psa; // [rsp+98h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+A0h] [rbp+18h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         a2,
         &pvarg);
  if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
    ATL::BaseAtlThrow(v5);
  if ( v5 < 0 )
    ATL::BaseAtlThrow(v5);
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"WhiteBalance", -1) == 2 )
  {
    ATL::CComSafeArray<double,5>::CComSafeArray<double,5>(&psa, pvarg.parray);
    if ( (unsigned int)ATL::CComSafeArray<IUnknown *,13>::GetCount(&psa) != 3 )
      ATL::BaseAtlThrow(-2147024809);
    for ( i = 0; i < 3; ++i )
    {
      v7 = *(double *)ATL::CComSafeArray<IUnknown *,13>::GetAt(&psa, (unsigned int)i);
      *((float *)this + i + 39) = v7;
      if ( v7 < 0.0 )
        ATL::BaseAtlThrow(-2147024809);
    }
    if ( psa && SafeArrayUnlock(psa) >= 0 )
      SafeArrayDestroy(psa);
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CFALeftTopOffset", -1) == 2 )
  {
    ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(&ppsaOut, pvarg.parray);
    plLbound = 0;
    LODWORD(psa) = 0;
    LBound = SafeArrayGetLBound(ppsaOut, 1u, &plLbound);
    if ( LBound < 0 )
      ATL::BaseAtlThrow(LBound);
    UBound = SafeArrayGetUBound(ppsaOut, 1u, (LONG *)&psa);
    if ( UBound < 0 )
      ATL::BaseAtlThrow(UBound);
    if ( (_DWORD)psa - plLbound != 1 )
      ATL::BaseAtlThrow(-2147024809);
    v10 = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&ppsaOut, 0);
    *((_DWORD *)this + 43) = v10;
    if ( v10 > 1 )
      ATL::BaseAtlThrow(-2147024809);
    v11 = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&ppsaOut, 1);
    *((_DWORD *)this + 42) = v11;
    if ( v11 > 1 )
      ATL::BaseAtlThrow(-2147024809);
    if ( ppsaOut && SafeArrayUnlock(ppsaOut) >= 0 )
      SafeArrayDestroy(ppsaOut);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"PassThrough", -1) == 2 )
  {
    *((_BYTE *)this + 152) = pvarg.iVal != 0;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"ForceDisableSSE", -1) == 2 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
            *((_QWORD *)this + 16),
            L"ForceDisableSSE",
            &pvarg);
    if ( v12 == -2147024882 || v12 == -2045378032 || v12 == -2045312765 || v12 == -2045247216 )
      ATL::BaseAtlThrow(v12);
    if ( v12 < 0 )
      ATL::BaseAtlThrow(v12);
    *((_BYTE *)this + 176) = pvarg.iVal != 0;
  }
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1804a4de0  mov     [rsp+arg_0], rbx
0x1804a4de5  push    rsi
0x1804a4de6  push    rdi
0x1804a4de7  push    r12
0x1804a4de9  push    r14
0x1804a4deb  push    r15
0x1804a4ded  sub     rsp, 60h
0x1804a4df1  mov     rsi, rdx
0x1804a4df4  mov     rbx, rcx
0x1804a4df7  xor     r14d, r14d
0x1804a4dfa  test    rdx, rdx
0x1804a4dfd  jnz     short loc_1804A4E09
0x1804a4dff  mov     eax, 80004003h
0x1804a4e04  jmp     loc_1804A5132
0x1804a4e09  xorps   xmm0, xmm0
0x1804a4e0c  xor     eax, eax
0x1804a4e0e  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1804a4e13  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1804a4e18  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1804a4e1d  call    cs:__imp_VariantInit
0x1804a4e23  mov     rcx, [rbx+80h]
0x1804a4e2a  mov     rax, [rcx]
0x1804a4e2d  lea     r8, [rsp+88h+pvarg]
0x1804a4e32  mov     rdx, rsi
0x1804a4e35  mov     rax, [rax+60h]
0x1804a4e39  call    cs:__guard_dispatch_icall_fptr
0x1804a4e3f  cmp     eax, 8007000Eh
0x1804a4e44  jz      loc_1804A5189
0x1804a4e4a  cmp     eax, 86160210h
0x1804a4e4f  jz      loc_1804A5189
0x1804a4e55  cmp     eax, 86170103h
0x1804a4e5a  jz      loc_1804A5189
0x1804a4e60  cmp     eax, 86180110h
0x1804a4e65  jz      loc_1804A5189
0x1804a4e6b  test    eax, eax
0x1804a4e6d  js      loc_1804A5147
0x1804a4e73  or      r12d, 0FFFFFFFFh
0x1804a4e77  mov     [rsp+88h+cchCount2], r12d; cchCount2
0x1804a4e7c  lea     rax, aWhitebalance_0; "WhiteBalance"
0x1804a4e83  mov     [rsp+88h+lpString2], rax; lpString2
0x1804a4e88  mov     r9d, r12d; cchCount1
0x1804a4e8b  mov     r8, rsi; lpString1
0x1804a4e8e  lea     r15d, [r12+2]
0x1804a4e93  mov     edx, r15d; dwCmpFlags
0x1804a4e96  lea     ecx, [r15+7Eh]; Locale
0x1804a4e9a  call    cs:__imp_CompareStringW
0x1804a4ea0  cmp     eax, 2
0x1804a4ea3  jnz     loc_1804A4F34
0x1804a4ea9  mov     rdx, qword ptr [rsp+88h+pvarg+8]; psa
0x1804a4eae  lea     rcx, [rsp+88h+psa]; ppsaOut
0x1804a4eb6  call    ??0?$CComSafeArray@N$04@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<double,5>::CComSafeArray<double,5>(tagSAFEARRAY const *)
0x1804a4ebb  nop
0x1804a4ebc  lea     rcx, [rsp+88h+psa]
0x1804a4ec4  call    ?GetCount@?$CComSafeArray@PEAUIUnknown@@$0N@@ATL@@QEBAKI@Z; ATL::CComSafeArray<IUnknown *,13>::GetCount(uint)
0x1804a4ec9  cmp     eax, 3
0x1804a4ecc  jnz     loc_1804A5152
0x1804a4ed2  mov     edi, r14d
0x1804a4ed5  cmp     edi, 3
0x1804a4ed8  jge     short loc_1804A4F0F
0x1804a4eda  mov     edx, edi
0x1804a4edc  lea     rcx, [rsp+88h+psa]
0x1804a4ee4  call    ?GetAt@?$CComSafeArray@PEAUIUnknown@@$0N@@ATL@@QEAAAEAV?$CComPtr@UIUnknown@@@2@J@Z; ATL::CComSafeArray<IUnknown *,13>::GetAt(long)
0x1804a4ee9  movsd   xmm0, qword ptr [rax]
0x1804a4eed  cvtpd2ps xmm0, xmm0
0x1804a4ef1  movsxd  rax, edi
0x1804a4ef4  movss   dword ptr [rbx+rax*4+9Ch], xmm0
0x1804a4efd  comiss  xmm0, cs:__real@00000000
0x1804a4f04  jb      loc_1804A515C
0x1804a4f0a  add     edi, r15d
0x1804a4f0d  jmp     short loc_1804A4ED5
0x1804a4f0f  mov     rcx, [rsp+88h+psa]; psa
0x1804a4f17  test    rcx, rcx
0x1804a4f1a  jz      short loc_1804A4F34
0x1804a4f1c  call    cs:__imp_SafeArrayUnlock
0x1804a4f22  test    eax, eax
0x1804a4f24  js      short loc_1804A4F34
0x1804a4f26  mov     rcx, [rsp+88h+psa]; psa
0x1804a4f2e  call    cs:__imp_SafeArrayDestroy
0x1804a4f34  mov     [rsp+88h+cchCount2], r12d; cchCount2
0x1804a4f39  lea     rax, aCfalefttopoffs; "CFALeftTopOffset"
0x1804a4f40  mov     [rsp+88h+lpString2], rax; lpString2
0x1804a4f45  mov     r9d, r12d; cchCount1
0x1804a4f48  mov     r8, rsi; lpString1
0x1804a4f4b  mov     edx, r15d; dwCmpFlags
0x1804a4f4e  mov     edi, 7Fh
0x1804a4f53  mov     ecx, edi; Locale
0x1804a4f55  call    cs:__imp_CompareStringW
0x1804a4f5b  cmp     eax, 2
0x1804a4f5e  jnz     loc_1804A5059
0x1804a4f64  mov     rdx, qword ptr [rsp+88h+pvarg+8]; psa
0x1804a4f69  lea     rcx, [rsp+88h+ppsaOut]; ppsaOut
0x1804a4f71  call    ??0?$CComSafeArray@H$02@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(tagSAFEARRAY const *)
0x1804a4f76  nop
0x1804a4f77  mov     [rsp+88h+plLbound], r14d
0x1804a4f7f  mov     dword ptr [rsp+88h+psa], r14d
0x1804a4f87  lea     r8, [rsp+88h+plLbound]; plLbound
0x1804a4f8f  mov     edx, r15d; nDim
0x1804a4f92  mov     rcx, [rsp+88h+ppsaOut]; psa
0x1804a4f9a  call    cs:__imp_SafeArrayGetLBound
0x1804a4fa0  test    eax, eax
0x1804a4fa2  js      loc_1804A516D
0x1804a4fa8  lea     r8, [rsp+88h+psa]; plUbound
0x1804a4fb0  mov     edx, r15d; nDim
0x1804a4fb3  mov     rcx, [rsp+88h+ppsaOut]; psa
0x1804a4fbb  call    cs:__imp_SafeArrayGetUBound
0x1804a4fc1  test    eax, eax
0x1804a4fc3  js      loc_1804A5174
0x1804a4fc9  mov     eax, dword ptr [rsp+88h+psa]
0x1804a4fd0  sub     eax, [rsp+88h+plLbound]
0x1804a4fd7  cmp     eax, r15d
0x1804a4fda  jnz     loc_1804A517B
0x1804a4fe0  xor     edx, edx
0x1804a4fe2  lea     rcx, [rsp+88h+ppsaOut]
0x1804a4fea  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804a4fef  mov     eax, [rax]
0x1804a4ff1  mov     [rbx+0ACh], eax
0x1804a4ff7  cmp     eax, r15d
0x1804a4ffa  ja      loc_1804A519E
0x1804a5000  mov     edx, r15d
0x1804a5003  lea     rcx, [rsp+88h+ppsaOut]
0x1804a500b  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804a5010  mov     eax, [rax]
0x1804a5012  mov     [rbx+0A8h], eax
0x1804a5018  cmp     eax, r15d
0x1804a501b  ja      loc_1804A5194
0x1804a5021  mov     rcx, [rsp+88h+ppsaOut]; psa
0x1804a5029  test    rcx, rcx
0x1804a502c  jz      short loc_1804A5047
0x1804a502e  call    cs:__imp_SafeArrayUnlock
0x1804a5034  test    eax, eax
0x1804a5036  js      short loc_1804A5047
0x1804a5038  mov     rcx, [rsp+88h+ppsaOut]; psa
0x1804a5040  call    cs:__imp_SafeArrayDestroy
0x1804a5046  nop
0x1804a5047  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1804a504c  call    cs:__imp_VariantClear
0x1804a5052  xor     eax, eax
0x1804a5054  jmp     loc_1804A5132
0x1804a5059  mov     [rsp+88h+cchCount2], r12d; cchCount2
0x1804a505e  lea     rax, aPassthrough; "PassThrough"
0x1804a5065  mov     [rsp+88h+lpString2], rax; lpString2
0x1804a506a  mov     r9d, r12d; cchCount1
0x1804a506d  mov     r8, rsi; lpString1
0x1804a5070  mov     edx, r15d; dwCmpFlags
0x1804a5073  mov     ecx, edi; Locale
0x1804a5075  call    cs:__imp_CompareStringW
0x1804a507b  cmp     eax, 2
0x1804a507e  jnz     short loc_1804A5091
0x1804a5080  cmp     word ptr [rsp+88h+pvarg+8], r14w
0x1804a5086  setnz   al
0x1804a5089  mov     [rbx+98h], al
0x1804a508f  jmp     short loc_1804A5047
0x1804a5091  mov     [rsp+88h+cchCount2], r12d; cchCount2
0x1804a5096  lea     rdi, aForcedisabless; "ForceDisableSSE"
0x1804a509d  mov     [rsp+88h+lpString2], rdi; lpString2
0x1804a50a2  mov     r9d, r12d; cchCount1
0x1804a50a5  mov     r8, rsi; lpString1
0x1804a50a8  mov     edx, r15d; dwCmpFlags
0x1804a50ab  mov     ecx, 7Fh; Locale
0x1804a50b0  call    cs:__imp_CompareStringW
0x1804a50b6  cmp     eax, 2
0x1804a50b9  jnz     short loc_1804A5047
0x1804a50bb  mov     rcx, [rbx+80h]
0x1804a50c2  mov     rax, [rcx]
0x1804a50c5  lea     r8, [rsp+88h+pvarg]
0x1804a50ca  mov     rdx, rdi
0x1804a50cd  mov     rax, [rax+60h]
0x1804a50d1  call    cs:__guard_dispatch_icall_fptr
0x1804a50d7  cmp     eax, 8007000Eh
0x1804a50dc  jz      loc_1804A51B4
0x1804a50e2  cmp     eax, 86160210h
0x1804a50e7  jz      loc_1804A51B4
0x1804a50ed  cmp     eax, 86170103h
0x1804a50f2  jz      loc_1804A51B4
0x1804a50f8  cmp     eax, 86180110h
0x1804a50fd  jz      loc_1804A51B4
0x1804a5103  test    eax, eax
0x1804a5105  js      loc_1804A51AD
0x1804a510b  cmp     word ptr [rsp+88h+pvarg+8], r14w
0x1804a5111  setnz   al
0x1804a5114  mov     [rbx+0B0h], al
0x1804a511a  jmp     loc_1804A5047
0x1804a511f  mov     eax, dword ptr [rsp+88h+psa]
0x1804a5126  mov     edx, 86160101h
0x1804a512b  cmp     ax, 216h
0x1804a512f  cmovz   eax, edx
0x1804a5132  mov     rbx, [rsp+88h+arg_0]
0x1804a513a  add     rsp, 60h
0x1804a513e  pop     r15
0x1804a5140  pop     r14
0x1804a5142  pop     r12
0x1804a5144  pop     rdi
0x1804a5145  pop     rsi
0x1804a5146  retn
0x1804a5147  mov     ecx, eax; int
0x1804a5149  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a514f  jmp     short $+2
0x1804a5151  nop
0x1804a5152  mov     ecx, 80070057h; int
0x1804a5157  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a515c  mov     ecx, 80070057h; int
0x1804a5161  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a5167  jmp     short loc_1804A516C
0x1804a516c  nop
0x1804a516d  mov     ecx, eax; int
0x1804a516f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a5174  mov     ecx, eax; int
0x1804a5176  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a517b  mov     ecx, 80070057h; int
0x1804a5180  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a5186  jmp     short $+2
0x1804a5188  nop
0x1804a5189  mov     ecx, eax; int
0x1804a518b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a5191  jmp     short $+2
0x1804a5193  nop
0x1804a5194  mov     ecx, 80070057h; int
0x1804a5199  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a519e  mov     ecx, 80070057h; int
0x1804a51a3  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a51a9  jmp     short loc_1804A51AC
0x1804a51ac  nop
0x1804a51ad  mov     ecx, eax; int
0x1804a51af  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804a51b4  mov     ecx, eax; int
0x1804a51b6  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
