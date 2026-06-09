# Windows::UI::Input::Inking::CInkDrawingAttributes::Initialize(IInkDrawingAttributes *)

- ea: `0x180045950`
- end: `0x180046092`
- name: `?Initialize@CInkDrawingAttributes@Inking@Input@UI@Windows@@UEAAJPEAUIInkDrawingAttributes@@@Z`
- size: `1858`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkDrawingAttributes *__hidden this, struct IInkDrawingAttributes *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001043c`
- `0x18001332c`
- `0x180044674`
- `0x1800448b8`
- `0x180045950`
- `0x1800468e0`
- `0x180057e8c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800459a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045b23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045d1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046053`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004607b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800459a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045b23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045d1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046053`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004607b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800459fa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800459fa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045a4e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045a4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::UI::Input::Inking::CInkDrawingAttributes::Initialize(
        Windows::UI::Input::Inking::CInkDrawingAttributes *this,
        struct IInkDrawingAttributes *a2)
{
  HRESULT InkDrawingAttributesExtendedProperty; // ebx
  __int64 v5; // rdx
  int v7; // xmm2_4
  int v8; // xmm1_4
  int v9; // xmm0_4
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // r14d
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  char v17; // r14
  char v18; // al
  int v19; // eax
  unsigned int v20; // r15d
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  float v25; // xmm1_4
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int ExtendedProperties; // eax
  unsigned int v30; // edi
  struct tagVARIANT *v31; // [rsp+20h] [rbp-40h] BYREF
  PSRWLOCK SRWLock; // [rsp+28h] [rbp-38h] BYREF
  __int64 v33; // [rsp+30h] [rbp-30h] BYREF
  __int64 v34; // [rsp+38h] [rbp-28h] BYREF
  SAFEARRAY *psa[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  void *ppvData; // [rsp+A0h] [rbp+40h] BYREF
  __int16 v39; // [rsp+A8h] [rbp+48h] BYREF
  __int16 v40; // [rsp+B0h] [rbp+50h] BYREF
  int v41; // [rsp+B8h] [rbp+58h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 352);
  if ( !a2 )
  {
    InkDrawingAttributesExtendedProperty = -2147467261;
    v5 = 159;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)InkDrawingAttributesExtendedProperty,
      (int)v31);
LABEL_4:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)InkDrawingAttributesExtendedProperty;
  }
  LOBYTE(ppvData) = 0;
  *(_OWORD *)psa = 0;
  v36 = 0;
  InkDrawingAttributesExtendedProperty = Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(
                                           (Windows::UI::Input::Inking *)a2,
                                           (struct IInkDrawingAttributes *)&stru_180117230,
                                           (unsigned __int16 *)&ppvData,
                                           (unsigned __int8 *)psa,
                                           v31);
  if ( InkDrawingAttributesExtendedProperty < 0 )
  {
    v5 = 163;
    goto LABEL_3;
  }
  if ( (_BYTE)ppvData )
  {
    ppvData = 0;
    InkDrawingAttributesExtendedProperty = SafeArrayAccessData(psa[1], &ppvData);
    if ( InkDrawingAttributesExtendedProperty < 0 )
    {
      v5 = 169;
      goto LABEL_3;
    }
    v7 = *((_DWORD *)ppvData + 3);
    v8 = *((_DWORD *)ppvData + 2);
    v9 = *((_DWORD *)ppvData + 1);
    *((_DWORD *)this + 33) = *(_DWORD *)ppvData;
    *((_DWORD *)this + 34) = v9;
    *((_DWORD *)this + 35) = v8;
    *((_DWORD *)this + 36) = v7;
    *(_QWORD *)((char *)this + 148) = 0;
    InkDrawingAttributesExtendedProperty = SafeArrayUnaccessData(psa[1]);
    if ( InkDrawingAttributesExtendedProperty < 0 )
    {
      v5 = 175;
      goto LABEL_3;
    }
  }
  else
  {
    *(_QWORD *)((char *)this + 132) = 1065353216;
    *((_DWORD *)this + 35) = 0;
    *((_QWORD *)this + 18) = 1065353216;
    *((_DWORD *)this + 38) = 0;
  }
  Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkModelerAttributes,>(&v34);
  v10 = v34;
  if ( !v34 )
  {
    InkDrawingAttributesExtendedProperty = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    goto LABEL_4;
  }
  LOBYTE(ppvData) = 0;
  *(_OWORD *)psa = 0;
  v36 = 0;
  v11 = Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(
          (Windows::UI::Input::Inking *)a2,
          (struct IInkDrawingAttributes *)&stru_180117370,
          (unsigned __int16 *)&ppvData,
          (unsigned __int8 *)psa,
          v31);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v11,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_20:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v12;
  }
  if ( (_BYTE)ppvData )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
    v12 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
        (const char *)(unsigned int)v13,
        (int)v31);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_20;
    }
  }
  LOBYTE(ppvData) = 0;
  *(_OWORD *)psa = 0;
  v36 = 0;
  v14 = Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(
          (Windows::UI::Input::Inking *)a2,
          (struct IInkDrawingAttributes *)&stru_180117410,
          (unsigned __int16 *)&ppvData,
          (unsigned __int8 *)psa,
          v31);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v14,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_20;
  }
  if ( (_BYTE)ppvData )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 56LL))(
            v10,
            (unsigned int)(10 * LODWORD(psa[1])));
    v12 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
        (const char *)(unsigned int)v15,
        (int)v31);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_20;
    }
  }
  Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkModelerAttributes>::operator=<Windows::UI::Input::Inking::CInkModelerAttributes>(
    (char *)this + 184,
    &v34);
  LOBYTE(ppvData) = 0;
  *(_OWORD *)psa = 0;
  v36 = 0;
  v16 = Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(
          (Windows::UI::Input::Inking *)a2,
          (struct IInkDrawingAttributes *)&stru_180117280,
          (unsigned __int16 *)&ppvData,
          (unsigned __int8 *)psa,
          v31);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v16,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_20;
  }
  v17 = 1;
  if ( !(_BYTE)ppvData || (v18 = 1, LOBYTE(psa[1]) != 1) )
    v18 = 0;
  *((_BYTE *)this + 156) = v18;
  v41 = 0;
  v19 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, int *))a2->lpVtbl->get_Color)(a2, &v41);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v19,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_47:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v20;
  }
  *(_WORD *)((char *)&ppvData + 1) = v41;
  BYTE3(ppvData) = BYTE2(v41);
  LODWORD(v31) = 0;
  v21 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, struct tagVARIANT **))a2->lpVtbl->get_Transparency)(
          a2,
          &v31);
  v20 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v21,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  LOBYTE(ppvData) = -1 - (_BYTE)v31;
  *((_DWORD *)this + 28) = (_DWORD)ppvData;
  HIDWORD(v31) = 0;
  v22 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, char *))a2->lpVtbl->get_PenTip)(a2, (char *)&v31 + 4);
  v20 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v22,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  *((_DWORD *)this + 29) = HIDWORD(v31) != 0;
  v33 = 0;
  v23 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, __int64 *))a2->lpVtbl->get_Width)(a2, &v33);
  v20 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v23,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  v24 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, char *))a2->lpVtbl->get_Height)(a2, (char *)&v33 + 4);
  v20 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v24,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  *(float *)&v33 = *(float *)&v33 / 26.0;
  *((float *)&v33 + 1) = *((float *)&v33 + 1) / 26.0;
  v25 = *((float *)&v33 + 1);
  *((_DWORD *)this + 30) = v33;
  *((float *)this + 31) = v25;
  v39 = 0;
  v26 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, __int16 *))a2->lpVtbl->get_IgnorePressure)(a2, &v39);
  v20 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v26,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  *((_BYTE *)this + 128) = v39 == -1;
  v40 = 0;
  v27 = ((__int64 (__fastcall *)(struct IInkDrawingAttributes *, __int16 *))a2->lpVtbl->get_FitToCurve)(a2, &v40);
  v20 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v27,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  *((_BYTE *)this + 129) = v40 == -1;
  LOBYTE(ppvData) = 0;
  *(_OWORD *)psa = 0;
  v36 = 0;
  v28 = Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(
          (Windows::UI::Input::Inking *)a2,
          (struct IInkDrawingAttributes *)&stru_1801173C0,
          (unsigned __int16 *)&ppvData,
          (unsigned __int8 *)psa,
          v31);
  v20 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)v28,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_47;
  }
  if ( (_BYTE)ppvData && !LOBYTE(psa[1]) )
    v17 = 0;
  *((_BYTE *)this + 176) = v17;
  ExtendedProperties = Windows::UI::Input::Inking::CInkDrawingAttributes::RetrieveExtendedProperties(this, a2);
  v30 = ExtendedProperties;
  if ( ExtendedProperties >= 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\drawingattributes.cpp",
      (const char *)(unsigned int)ExtendedProperties,
      (int)v31);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v30;
  }
}

```

## disassembly

```asm
0x180045950  push    rbp
0x180045952  push    rbx
0x180045953  push    rsi
0x180045954  push    rdi
0x180045955  push    r12
0x180045957  push    r14
0x180045959  push    r15
0x18004595b  mov     rbp, rsp
0x18004595e  sub     rsp, 60h
0x180045962  mov     rsi, rdx
0x180045965  mov     rdi, rcx
0x180045968  lea     rdx, [rcx+160h]
0x18004596f  lea     rcx, [rbp+SRWLock]
0x180045973  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180045978  xor     r12d, r12d
0x18004597b  test    rsi, rsi
0x18004597e  jnz     short loc_1800459B3
0x180045980  mov     ebx, 80004003h
0x180045985  mov     edx, 9Fh; void *
0x18004598a  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045991  mov     r9d, ebx; char *
0x180045994  mov     rcx, [rbp+38h]; this
0x180045998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004599d  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800459a1  test    rcx, rcx
0x1800459a4  jz      short loc_1800459AC
0x1800459a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800459ac  mov     eax, ebx
0x1800459ae  jmp     loc_180046083
0x1800459b3  mov     byte ptr [rbp+ppvData], r12b
0x1800459b7  xorps   xmm0, xmm0
0x1800459ba  xor     eax, eax
0x1800459bc  movups  xmmword ptr [rbp+psa], xmm0
0x1800459c0  mov     [rbp+var_10], rax
0x1800459c4  lea     r9, [rbp+psa]; unsigned __int8 *
0x1800459c8  lea     r8, [rbp+ppvData]; unsigned __int16 *
0x1800459cc  lea     rdx, stru_180117230; struct IInkDrawingAttributes *
0x1800459d3  mov     rcx, rsi; this
0x1800459d6  call    ?GetInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJPEAUIInkDrawingAttributes@@PEAGPEAEPEAUtagVARIANT@@@Z; Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(IInkDrawingAttributes *,ushort *,uchar *,tagVARIANT *)
0x1800459db  mov     ebx, eax
0x1800459dd  test    eax, eax
0x1800459df  jns     short loc_1800459E8
0x1800459e1  mov     edx, 0A3h
0x1800459e6  jmp     short loc_18004598A
0x1800459e8  cmp     byte ptr [rbp+ppvData], r12b
0x1800459ec  jz      short loc_180045A64
0x1800459ee  mov     [rbp+ppvData], r12
0x1800459f2  lea     rdx, [rbp+ppvData]; ppvData
0x1800459f6  mov     rcx, [rbp+psa+8]; psa
0x1800459fa  call    cs:__imp_SafeArrayAccessData
0x180045a00  mov     ebx, eax
0x180045a02  test    eax, eax
0x180045a04  jns     short loc_180045A10
0x180045a06  mov     edx, 0A9h
0x180045a0b  jmp     loc_18004598A
0x180045a10  mov     rax, [rbp+ppvData]
0x180045a14  movss   xmm2, dword ptr [rax+0Ch]
0x180045a19  movss   xmm1, dword ptr [rax+8]
0x180045a1e  movss   xmm0, dword ptr [rax+4]
0x180045a23  mov     eax, [rax]
0x180045a25  mov     [rdi+84h], eax
0x180045a2b  movss   dword ptr [rdi+88h], xmm0
0x180045a33  movss   dword ptr [rdi+8Ch], xmm1
0x180045a3b  movss   dword ptr [rdi+90h], xmm2
0x180045a43  mov     [rdi+94h], r12
0x180045a4a  mov     rcx, [rbp+psa+8]; psa
0x180045a4e  call    cs:__imp_SafeArrayUnaccessData
0x180045a54  mov     ebx, eax
0x180045a56  test    eax, eax
0x180045a58  jns     short loc_180045A88
0x180045a5a  mov     edx, 0AFh
0x180045a5f  jmp     loc_18004598A
0x180045a64  mov     qword ptr [rdi+84h], 3F800000h
0x180045a6f  mov     [rdi+8Ch], r12d
0x180045a76  mov     qword ptr [rdi+90h], 3F800000h
0x180045a81  mov     [rdi+98h], r12d
0x180045a88  lea     rcx, [rbp+var_28]
0x180045a8c  call    ??$Make@VCInkModelerAttributes@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkModelerAttributes@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkModelerAttributes,>(void)
0x180045a91  mov     rbx, [rbp+var_28]
0x180045a95  test    rbx, rbx
0x180045a98  jnz     short loc_180045ABD
0x180045a9a  mov     rcx, [rbp+38h]; this
0x180045a9e  mov     ebx, 8007000Eh
0x180045aa3  mov     r9d, ebx; char *
0x180045aa6  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045aad  mov     edx, 0B7h; void *
0x180045ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045ab7  nop
0x180045ab8  jmp     loc_18004599D
0x180045abd  mov     byte ptr [rbp+ppvData], r12b
0x180045ac1  xorps   xmm0, xmm0
0x180045ac4  xor     eax, eax
0x180045ac6  movups  xmmword ptr [rbp+psa], xmm0
0x180045aca  mov     [rbp+var_10], rax
0x180045ace  lea     r9, [rbp+psa]; unsigned __int8 *
0x180045ad2  lea     r8, [rbp+ppvData]; unsigned __int16 *
0x180045ad6  lea     rdx, stru_180117370; struct IInkDrawingAttributes *
0x180045add  mov     rcx, rsi; this
0x180045ae0  call    ?GetInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJPEAUIInkDrawingAttributes@@PEAGPEAEPEAUtagVARIANT@@@Z; Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(IInkDrawingAttributes *,ushort *,uchar *,tagVARIANT *)
0x180045ae5  mov     r14d, eax
0x180045ae8  test    eax, eax
0x180045aea  jns     short loc_180045B31
0x180045aec  mov     rcx, [rbp+38h]; this
0x180045af0  mov     r9d, eax; char *
0x180045af3  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045afa  mov     edx, 0BBh; void *
0x180045aff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b04  nop
0x180045b05  test    rbx, rbx
0x180045b08  jz      short loc_180045B1A
0x180045b0a  mov     rax, [rbx]
0x180045b0d  mov     rcx, rbx
0x180045b10  mov     rax, [rax+10h]
0x180045b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b19  nop
0x180045b1a  mov     rcx, [rbp+SRWLock]; SRWLock
0x180045b1e  test    rcx, rcx
0x180045b21  jz      short loc_180045B29
0x180045b23  call    cs:__imp_ReleaseSRWLockExclusive
0x180045b29  mov     eax, r14d
0x180045b2c  jmp     loc_180046083
0x180045b31  cmp     byte ptr [rbp+ppvData], r12b
0x180045b35  jz      short loc_180045B82
0x180045b37  mov     rax, [rbx]
0x180045b3a  movss   xmm1, dword ptr [rbp+psa+8]
0x180045b3f  mov     rcx, rbx
0x180045b42  mov     rax, [rax+48h]
0x180045b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b4b  mov     r14d, eax
0x180045b4e  test    eax, eax
0x180045b50  jns     short loc_180045B82
0x180045b52  mov     rcx, [rbp+38h]; this
0x180045b56  mov     r9d, eax; char *
0x180045b59  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045b60  mov     edx, 0BEh; void *
0x180045b65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b6a  nop
0x180045b6b  test    rbx, rbx
0x180045b6e  jz      short loc_180045B80
0x180045b70  mov     rax, [rbx]
0x180045b73  mov     rcx, rbx
0x180045b76  mov     rax, [rax+10h]
0x180045b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b7f  nop
0x180045b80  jmp     short loc_180045B1A
0x180045b82  mov     byte ptr [rbp+ppvData], r12b
0x180045b86  xorps   xmm0, xmm0
0x180045b89  xor     eax, eax
0x180045b8b  movups  xmmword ptr [rbp+psa], xmm0
0x180045b8f  mov     [rbp+var_10], rax
0x180045b93  lea     r9, [rbp+psa]; unsigned __int8 *
0x180045b97  lea     r8, [rbp+ppvData]; unsigned __int16 *
0x180045b9b  lea     rdx, stru_180117410; struct IInkDrawingAttributes *
0x180045ba2  mov     rcx, rsi; this
0x180045ba5  call    ?GetInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJPEAUIInkDrawingAttributes@@PEAGPEAEPEAUtagVARIANT@@@Z; Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(IInkDrawingAttributes *,ushort *,uchar *,tagVARIANT *)
0x180045baa  mov     r14d, eax
0x180045bad  test    eax, eax
0x180045baf  jns     short loc_180045BE4
0x180045bb1  mov     rcx, [rbp+38h]; this
0x180045bb5  mov     r9d, eax; char *
0x180045bb8  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045bbf  mov     edx, 0C4h; void *
0x180045bc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045bc9  nop
0x180045bca  test    rbx, rbx
0x180045bcd  jz      short loc_180045BDF
0x180045bcf  mov     rax, [rbx]
0x180045bd2  mov     rcx, rbx
0x180045bd5  mov     rax, [rax+10h]
0x180045bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bde  nop
0x180045bdf  jmp     loc_180045B1A
0x180045be4  cmp     byte ptr [rbp+ppvData], r12b
0x180045be8  jz      short loc_180045C3C
0x180045bea  mov     eax, dword ptr [rbp+psa+8]
0x180045bed  lea     ecx, [rax+rax*4]
0x180045bf0  lea     edx, [rcx+rcx]
0x180045bf3  mov     rax, [rbx]
0x180045bf6  mov     rcx, rbx
0x180045bf9  mov     rax, [rax+38h]
0x180045bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c02  mov     r14d, eax
0x180045c05  test    eax, eax
0x180045c07  jns     short loc_180045C3C
0x180045c09  mov     rcx, [rbp+38h]; this
0x180045c0d  mov     r9d, eax; char *
0x180045c10  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045c17  mov     edx, 0C9h; void *
0x180045c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c21  nop
0x180045c22  test    rbx, rbx
0x180045c25  jz      short loc_180045C37
0x180045c27  mov     rax, [rbx]
0x180045c2a  mov     rcx, rbx
0x180045c2d  mov     rax, [rax+10h]
0x180045c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c36  nop
0x180045c37  jmp     loc_180045B1A
0x180045c3c  lea     rcx, [rdi+0B8h]
0x180045c43  lea     rdx, [rbp+var_28]
0x180045c47  call    ??$?4VCInkModelerAttributes@Inking@Input@UI@Windows@@@?$ComPtr@UIInkModelerAttributes@Inking@Input@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@VCInkModelerAttributes@Inking@Input@UI@Windows@@@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkModelerAttributes>::operator=<Windows::UI::Input::Inking::CInkModelerAttributes>(Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::CInkModelerAttributes> const &)
0x180045c4c  mov     byte ptr [rbp+ppvData], r12b
0x180045c50  xorps   xmm0, xmm0
0x180045c53  xor     eax, eax
0x180045c55  movups  xmmword ptr [rbp+psa], xmm0
0x180045c59  mov     [rbp+var_10], rax
0x180045c5d  lea     r9, [rbp+psa]; unsigned __int8 *
0x180045c61  lea     r8, [rbp+ppvData]; unsigned __int16 *
0x180045c65  lea     rdx, stru_180117280; struct IInkDrawingAttributes *
0x180045c6c  mov     rcx, rsi; this
0x180045c6f  call    ?GetInkDrawingAttributesExtendedProperty@Inking@Input@UI@Windows@@YAJPEAUIInkDrawingAttributes@@PEAGPEAEPEAUtagVARIANT@@@Z; Windows::UI::Input::Inking::GetInkDrawingAttributesExtendedProperty(IInkDrawingAttributes *,ushort *,uchar *,tagVARIANT *)
0x180045c74  mov     r14d, eax
0x180045c77  test    eax, eax
0x180045c79  jns     short loc_180045CAE
0x180045c7b  mov     rcx, [rbp+38h]; this
0x180045c7f  mov     r9d, eax; char *
0x180045c82  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045c89  mov     edx, 0D1h; void *
0x180045c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c93  nop
0x180045c94  test    rbx, rbx
0x180045c97  jz      short loc_180045CA9
0x180045c99  mov     rax, [rbx]
0x180045c9c  mov     rcx, rbx
0x180045c9f  mov     rax, [rax+10h]
0x180045ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ca8  nop
0x180045ca9  jmp     loc_180045B1A
0x180045cae  mov     r14b, 1
0x180045cb1  cmp     byte ptr [rbp+ppvData], r12b
0x180045cb5  jz      short loc_180045CC0
0x180045cb7  cmp     byte ptr [rbp+psa+8], r14b
0x180045cbb  mov     al, r14b
0x180045cbe  jz      short loc_180045CC3
0x180045cc0  mov     al, r12b
0x180045cc3  mov     [rdi+9Ch], al
0x180045cc9  mov     [rbp+arg_18], r12d
0x180045ccd  mov     rax, [rsi]
0x180045cd0  lea     rdx, [rbp+arg_18]
0x180045cd4  mov     rcx, rsi
0x180045cd7  mov     rax, [rax+38h]
0x180045cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ce0  mov     r15d, eax
0x180045ce3  test    eax, eax
0x180045ce5  jns     short loc_180045D2C
0x180045ce7  mov     rcx, [rbp+38h]; this
0x180045ceb  mov     r9d, eax; char *
0x180045cee  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045cf5  mov     edx, 0D8h; void *
0x180045cfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045cff  nop
0x180045d00  test    rbx, rbx
0x180045d03  jz      short loc_180045D15
0x180045d05  mov     rax, [rbx]
0x180045d08  mov     rcx, rbx
0x180045d0b  mov     rax, [rax+10h]
0x180045d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d14  nop
0x180045d15  mov     rcx, [rbp+SRWLock]; SRWLock
0x180045d19  test    rcx, rcx
0x180045d1c  jz      short loc_180045D24
0x180045d1e  call    cs:__imp_ReleaseSRWLockExclusive
0x180045d24  mov     eax, r15d
0x180045d27  jmp     loc_180046083
0x180045d2c  mov     ecx, [rbp+arg_18]
0x180045d2f  mov     byte ptr [rbp+ppvData+1], cl
0x180045d32  movzx   eax, cx
0x180045d35  shr     ax, 8
0x180045d39  mov     byte ptr [rbp+ppvData+2], al
0x180045d3c  sar     ecx, 10h
0x180045d3f  mov     byte ptr [rbp+ppvData+3], cl
0x180045d42  mov     [rbp+var_40], r12d
0x180045d46  mov     rax, [rsi]
0x180045d49  lea     rdx, [rbp+var_40]
0x180045d4d  mov     rcx, rsi
0x180045d50  mov     rax, [rax+98h]
0x180045d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d5c  mov     r15d, eax
0x180045d5f  test    eax, eax
0x180045d61  jns     short loc_180045D93
0x180045d63  mov     rcx, [rbp+38h]; this
0x180045d67  mov     r9d, eax; char *
0x180045d6a  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180045d71  mov     edx, 0E1h; void *
0x180045d76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045d7b  nop
0x180045d7c  test    rbx, rbx
0x180045d7f  jz      short loc_180045D91
0x180045d81  mov     rax, [rbx]
0x180045d84  mov     rcx, rbx
0x180045d87  mov     rax, [rax+10h]
0x180045d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d90  nop
0x180045d91  jmp     short loc_180045D15
0x180045d93  mov     eax, 0FFh
0x180045d98  sub     al, byte ptr [rbp+var_40]
0x180045d9b  mov     byte ptr [rbp+ppvData], al
0x180045d9e  mov     eax, dword ptr [rbp+ppvData]
0x180045da1  mov     [rdi+70h], eax
0x180045da4  mov     [rbp+var_3C], r12d
  ... truncated ...
```
