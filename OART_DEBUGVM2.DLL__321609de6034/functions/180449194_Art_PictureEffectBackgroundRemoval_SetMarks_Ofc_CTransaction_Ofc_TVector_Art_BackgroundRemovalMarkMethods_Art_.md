# Art::PictureEffectBackgroundRemoval::SetMarks(Ofc::CTransaction &,Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalBackgroundMarkData>,0,4294967295> const &)

- ea: `0x180449194`
- end: `0x180449606`
- name: `?SetMarks@PictureEffectBackgroundRemoval@Art@@QEAAXAEAVCTransaction@Ofc@@AEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@4@AEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalBackgroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@4@@Z`
- size: `1138`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18044780c`
- `0x18044ca30`
- `0x1808ba1b0`
- `0x1808bcf30`

## callees

- `0x18000e1e0`
- `0x180025430`
- `0x180139ca0`
- `0x1801dce3c`
- `0x1802d56d0`
- `0x180449194`
- `0x18044b1d0`
- `0x18044cda8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180449359`
- `OLEAUT32!__imp_VariantInit` at `0x180449363`
- `OLEAUT32!__imp_VariantInit` at `0x18044936d`
- `OLEAUT32!__imp_VariantInit` at `0x180449377`
- `OLEAUT32!__imp_VariantInit` at `0x180449359`
- `OLEAUT32!__imp_VariantInit` at `0x180449363`
- `OLEAUT32!__imp_VariantInit` at `0x18044936d`
- `OLEAUT32!__imp_VariantInit` at `0x180449377`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804491dc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044922d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180449281`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804492d1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804491dc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044922d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180449281`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804492d1`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804491f8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180449249`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044929d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804492ed`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804491f8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180449249`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044929d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804492ed`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180449392`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804493b9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804493e4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044940a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180449392`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804493b9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804493e4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044940a`

## pseudocode

```c
void __fastcall Art::PictureEffectBackgroundRemoval::SetMarks(
        _DWORD *a1,
        struct Ofc::CTransaction *a2,
        __int64 a3,
        __int64 a4)
{
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // r15
  HRESULT v9; // eax
  SAFEARRAY *v10; // rax
  SAFEARRAY *v11; // r14
  HRESULT v12; // eax
  SAFEARRAY *v13; // rax
  SAFEARRAY *v14; // rdi
  HRESULT v15; // eax
  SAFEARRAY *v16; // rax
  SAFEARRAY *v17; // rbx
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  volatile signed __int32 *v23; // rbx
  unsigned int i; // edi
  const wchar_t *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // r8
  volatile signed __int32 **v28; // rax
  volatile signed __int32 *v29; // rbx
  unsigned int j; // edi
  const wchar_t *v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // r8
  volatile signed __int32 **v34; // rax
  bool v35; // [rsp+28h] [rbp-B1h]
  struct tagVARIANT v36; // [rsp+30h] [rbp-A9h] BYREF
  SAFEARRAYBOUND v37; // [rsp+50h] [rbp-89h] BYREF
  SAFEARRAYBOUND v38; // [rsp+58h] [rbp-81h] BYREF
  SAFEARRAY *v39; // [rsp+60h] [rbp-79h] BYREF
  SAFEARRAY *v40; // [rsp+68h] [rbp-71h] BYREF
  SAFEARRAY *v41; // [rsp+70h] [rbp-69h] BYREF
  SAFEARRAY *v42; // [rsp+78h] [rbp-61h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp-59h] BYREF
  __int64 v44; // [rsp+88h] [rbp-51h]
  SAFEARRAYBOUND v45; // [rsp+90h] [rbp-49h] BYREF
  __int64 v46; // [rsp+98h] [rbp-41h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-39h] BYREF
  VARIANTARG v48; // [rsp+B8h] [rbp-21h] BYREF
  VARIANTARG v49; // [rsp+D0h] [rbp-9h] BYREF
  VARIANTARG v50; // [rsp+E8h] [rbp+Fh] BYREF

  rgsabound.cElements = *(_DWORD *)(a3 + 16);
  rgsabound.lLbound = 0;
  v44 = 4;
  v7 = SafeArrayCreate(5u, 2u, &rgsabound);
  v8 = v7;
  v39 = v7;
  if ( v7 )
  {
    v9 = SafeArrayLock(v7);
    if ( v9 >= 0 )
      goto LABEL_5;
  }
  else
  {
    v9 = -2147024882;
  }
  Ofc::CHResultException::ThrowTag(v9, 0x66336B77u);
LABEL_5:
  v37.cElements = *(_DWORD *)(a3 + 16);
  v37.lLbound = 0;
  v10 = SafeArrayCreate(3u, 1u, &v37);
  v11 = v10;
  v41 = v10;
  if ( v10 )
  {
    v12 = SafeArrayLock(v10);
    if ( v12 >= 0 )
      goto LABEL_9;
  }
  else
  {
    v12 = -2147024882;
  }
  Ofc::CHResultException::ThrowTag(v12, 0x66336B77u);
LABEL_9:
  v45.cElements = *(_DWORD *)(a4 + 16);
  v45.lLbound = 0;
  v46 = 4;
  v13 = SafeArrayCreate(5u, 2u, &v45);
  v14 = v13;
  v40 = v13;
  if ( v13 )
  {
    v15 = SafeArrayLock(v13);
    if ( v15 >= 0 )
      goto LABEL_13;
  }
  else
  {
    v15 = -2147024882;
  }
  Ofc::CHResultException::ThrowTag(v15, 0x66336B77u);
LABEL_13:
  v38.cElements = *(_DWORD *)(a4 + 16);
  v38.lLbound = 0;
  v16 = SafeArrayCreate(3u, 1u, &v38);
  v17 = v16;
  v42 = v16;
  if ( !v16 )
  {
    v18 = -2147024882;
LABEL_16:
    Ofc::CHResultException::ThrowTag(v18, 0x66336B77u);
    goto LABEL_17;
  }
  v18 = SafeArrayLock(v16);
  if ( v18 < 0 )
    goto LABEL_16;
LABEL_17:
  Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(
    a1,
    a3,
    &v39,
    &v41);
  Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(
    a1,
    a4,
    &v40,
    &v42);
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v48, 0, sizeof(v48));
  memset(&v49, 0, sizeof(v49));
  memset(&v50, 0, sizeof(v50));
  VariantInit(&pvarg);
  VariantInit(&v48);
  VariantInit(&v49);
  VariantInit(&v50);
  pvarg.vt = 8197;
  v19 = SafeArrayUnlock(v8);
  if ( v19 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v19, 0x66336B78u);
    __debugbreak();
  }
  v39 = 0;
  pvarg.llVal = (LONGLONG)v8;
  v48.vt = 8197;
  v20 = SafeArrayUnlock(v14);
  if ( v20 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v20, 0x66336B78u);
    __debugbreak();
  }
  v40 = 0;
  v48.llVal = (LONGLONG)v14;
  v49.vt = 8195;
  v21 = SafeArrayUnlock(v11);
  if ( v21 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v21, 0x66336B78u);
    __debugbreak();
  }
  v41 = 0;
  v49.llVal = (LONGLONG)v11;
  v50.vt = 8195;
  v22 = SafeArrayUnlock(v17);
  if ( v22 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v22, 0x66336B78u);
    __debugbreak();
  }
  v42 = 0;
  v50.llVal = (LONGLONG)v17;
  v23 = 0;
  for ( i = 0; i < a1[14]; ++i )
  {
    Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 12), i);
    v26 = Ofc::CchWzLen((Ofc *)L"ForegroundMarks", v25);
    if ( Ofc::FRgchEqual(
           *(Ofc **)(v27 + 24),
           (const wchar_t *)(unsigned int)(*(_DWORD *)(*(_QWORD *)(v27 + 24) - 4LL) / 2),
           (int)L"ForegroundMarks",
           (const wchar_t *)v26,
           0,
           v35) )
    {
      v28 = (volatile signed __int32 **)Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 12), i);
      if ( v28 )
        v23 = *v28;
      else
        v23 = 0;
      if ( v23 )
        _InterlockedIncrement(v23 + 2);
      break;
    }
  }
  v36 = pvarg;
  Art::PictureEffectParam::SetValue((Art::PictureEffectParam *)v23, a2, &v36);
  if ( v23 )
    Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v23 + 2);
  v29 = 0;
  for ( j = 0; j < a1[14]; ++j )
  {
    Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 12), j);
    v32 = Ofc::CchWzLen((Ofc *)L"BackgroundMarks", v31);
    if ( Ofc::FRgchEqual(
           *(Ofc **)(v33 + 24),
           (const wchar_t *)(unsigned int)(*(_DWORD *)(*(_QWORD *)(v33 + 24) - 4LL) / 2),
           (int)L"BackgroundMarks",
           (const wchar_t *)v32,
           0,
           v35) )
    {
      v34 = (volatile signed __int32 **)Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 12), j);
      if ( v34 )
        v29 = *v34;
      else
        v29 = 0;
      if ( v29 )
        _InterlockedIncrement(v29 + 2);
      break;
    }
  }
  v36 = v48;
  Art::PictureEffectParam::SetValue((Art::PictureEffectParam *)v29, a2, &v36);
  v36 = v49;
  Art::PictureEffectParam::SetValue((Art::PictureEffectParam *)(a1 + 36), a2, &v36);
  v36 = v50;
  Art::PictureEffectParam::SetValue((Art::PictureEffectParam *)(a1 + 56), a2, &v36);
  if ( v29 )
    Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v29 + 2);
}

```

## disassembly

```asm
0x180449194  mov     [rsp-8+arg_0], rbx
0x180449199  mov     [rsp-8+arg_8], rdx
0x18044919e  push    rbp
0x18044919f  push    rsi
0x1804491a0  push    rdi
0x1804491a1  push    r12
0x1804491a3  push    r13
0x1804491a5  push    r14
0x1804491a7  push    r15
0x1804491a9  lea     rbp, [rsp-27h]
0x1804491ae  sub     rsp, 100h
0x1804491b5  mov     r13, r9
0x1804491b8  mov     r12, r8
0x1804491bb  mov     rsi, rcx
0x1804491be  mov     eax, [r8+10h]
0x1804491c2  mov     [rbp+57h+rgsabound.cElements], eax
0x1804491c5  xor     ebx, ebx
0x1804491c7  mov     [rbp+57h+rgsabound.lLbound], ebx
0x1804491ca  mov     [rbp+57h+var_A8], 4
0x1804491d2  lea     ecx, [rbx+5]; vt
0x1804491d5  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1804491d9  lea     edx, [rbx+2]; cDims
0x1804491dc  call    cs:__imp_SafeArrayCreate
0x1804491e2  mov     r15, rax
0x1804491e5  mov     [rbp+57h+var_D0], rax
0x1804491e9  test    rax, rax
0x1804491ec  jnz     short loc_1804491F5
0x1804491ee  mov     eax, 8007000Eh
0x1804491f3  jmp     short loc_180449202
0x1804491f5  mov     rcx, r15; psa
0x1804491f8  call    cs:__imp_SafeArrayLock
0x1804491fe  test    eax, eax
0x180449200  jns     short loc_180449213
0x180449202  mov     edx, 66336B77h; unsigned int
0x180449207  mov     ecx, eax; int
0x180449209  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044920e  nop
0x18044920f  jmp     short loc_180449212
0x180449212  nop
0x180449213  mov     eax, [r12+10h]
0x180449218  mov     [rsp+130h+var_E0.cElements], eax
0x18044921c  mov     [rsp+130h+var_E0.lLbound], ebx
0x180449220  mov     ecx, 3; vt
0x180449225  lea     r8, [rsp+130h+var_E0]; rgsabound
0x18044922a  lea     edx, [rcx-2]; cDims
0x18044922d  call    cs:__imp_SafeArrayCreate
0x180449233  mov     r14, rax
0x180449236  mov     [rbp+57h+var_C0], rax
0x18044923a  test    rax, rax
0x18044923d  jnz     short loc_180449246
0x18044923f  mov     eax, 8007000Eh
0x180449244  jmp     short loc_180449253
0x180449246  mov     rcx, r14; psa
0x180449249  call    cs:__imp_SafeArrayLock
0x18044924f  test    eax, eax
0x180449251  jns     short loc_180449263
0x180449253  mov     edx, 66336B77h; unsigned int
0x180449258  mov     ecx, eax; int
0x18044925a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044925f  nop
0x180449260  jmp     short $+2
0x180449262  nop
0x180449263  mov     eax, [r13+10h]
0x180449267  mov     [rbp+57h+var_A0.cElements], eax
0x18044926a  mov     [rbp+57h+var_A0.lLbound], ebx
0x18044926d  mov     [rbp+57h+var_98], 4
0x180449275  mov     ecx, 5; vt
0x18044927a  lea     r8, [rbp+57h+var_A0]; rgsabound
0x18044927e  lea     edx, [rcx-3]; cDims
0x180449281  call    cs:__imp_SafeArrayCreate
0x180449287  mov     rdi, rax
0x18044928a  mov     [rbp+57h+var_C8], rax
0x18044928e  test    rax, rax
0x180449291  jnz     short loc_18044929A
0x180449293  mov     eax, 8007000Eh
0x180449298  jmp     short loc_1804492A7
0x18044929a  mov     rcx, rdi; psa
0x18044929d  call    cs:__imp_SafeArrayLock
0x1804492a3  test    eax, eax
0x1804492a5  jns     short loc_1804492B9
0x1804492a7  mov     edx, 66336B77h; unsigned int
0x1804492ac  mov     ecx, eax; int
0x1804492ae  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1804492b3  nop
0x1804492b4  jmp     short loc_1804492B8
0x1804492b8  nop
0x1804492b9  mov     eax, [r13+10h]
0x1804492bd  mov     [rsp+130h+var_D8.cElements], eax
0x1804492c1  mov     [rbp+57h+var_D8.lLbound], ebx
0x1804492c4  mov     ecx, 3; vt
0x1804492c9  lea     r8, [rsp+130h+var_D8]; rgsabound
0x1804492ce  lea     edx, [rcx-2]; cDims
0x1804492d1  call    cs:__imp_SafeArrayCreate
0x1804492d7  mov     rbx, rax
0x1804492da  mov     [rbp+57h+var_B8], rax
0x1804492de  test    rax, rax
0x1804492e1  jnz     short loc_1804492EA
0x1804492e3  mov     eax, 8007000Eh
0x1804492e8  jmp     short loc_1804492F7
0x1804492ea  mov     rcx, rbx; psa
0x1804492ed  call    cs:__imp_SafeArrayLock
0x1804492f3  test    eax, eax
0x1804492f5  jns     short loc_180449307
0x1804492f7  mov     edx, 66336B77h; unsigned int
0x1804492fc  mov     ecx, eax; int
0x1804492fe  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180449303  nop
0x180449304  jmp     short $+2
0x180449306  nop
0x180449307  lea     r9, [rbp+57h+var_C0]
0x18044930b  lea     r8, [rbp+57h+var_D0]
0x18044930f  mov     rdx, r12
0x180449312  mov     rcx, rsi
0x180449315  call    ??$SetMarksHelper@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@@PictureEffectBackgroundRemoval@Art@@AEAAXAEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@Ofc@@AEAV?$SafeArray@N$04@@AEAV?$SafeArray@I$02@@@Z; Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,SafeArray<double,5> &,SafeArray<uint,3> &)
0x18044931a  lea     r9, [rbp+57h+var_B8]
0x18044931e  lea     r8, [rbp+57h+var_C8]
0x180449322  mov     rdx, r13
0x180449325  mov     rcx, rsi
0x180449328  call    ??$SetMarksHelper@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@@PictureEffectBackgroundRemoval@Art@@AEAAXAEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@Ofc@@AEAV?$SafeArray@N$04@@AEAV?$SafeArray@I$02@@@Z; Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,SafeArray<double,5> &,SafeArray<uint,3> &)
0x18044932d  xorps   xmm0, xmm0
0x180449330  xor     eax, eax
0x180449332  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180449336  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18044933a  xorps   xmm1, xmm1
0x18044933d  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x180449341  mov     qword ptr [rbp+57h+var_78+10h], rax
0x180449345  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180449349  mov     qword ptr [rbp+57h+var_60+10h], rax
0x18044934d  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x180449351  mov     qword ptr [rbp+57h+var_48+10h], rax
0x180449355  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180449359  call    cs:__imp_VariantInit
0x18044935f  lea     rcx, [rbp+57h+var_78]; pvarg
0x180449363  call    cs:__imp_VariantInit
0x180449369  lea     rcx, [rbp+57h+var_60]; pvarg
0x18044936d  call    cs:__imp_VariantInit
0x180449373  lea     rcx, [rbp+57h+var_48]; pvarg
0x180449377  call    cs:__imp_VariantInit
0x18044937d  xor     r12d, r12d
0x180449380  mov     [rbp+57h+arg_10], r12
0x180449384  mov     r13d, 2005h
0x18044938a  mov     word ptr [rbp+57h+pvarg], r13w
0x18044938f  mov     rcx, r15; psa
0x180449392  call    cs:__imp_SafeArrayUnlock
0x180449398  test    eax, eax
0x18044939a  jns     short loc_1804493A9
0x18044939c  mov     edx, 66336B78h; unsigned int
0x1804493a1  mov     ecx, eax; int
0x1804493a3  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1804493a8  int     3; Trap to Debugger
0x1804493a9  mov     [rbp+57h+var_D0], r12
0x1804493ad  mov     qword ptr [rbp+57h+pvarg+8], r15
0x1804493b1  mov     word ptr [rbp+57h+var_78], r13w
0x1804493b6  mov     rcx, rdi; psa
0x1804493b9  call    cs:__imp_SafeArrayUnlock
0x1804493bf  test    eax, eax
0x1804493c1  jns     short loc_1804493D0
0x1804493c3  mov     edx, 66336B78h; unsigned int
0x1804493c8  mov     ecx, eax; int
0x1804493ca  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1804493cf  int     3; Trap to Debugger
0x1804493d0  mov     [rbp+57h+var_C8], r12
0x1804493d4  mov     qword ptr [rbp+57h+var_78+8], rdi
0x1804493d8  mov     edi, 2003h
0x1804493dd  mov     word ptr [rbp+57h+var_60], di
0x1804493e1  mov     rcx, r14; psa
0x1804493e4  call    cs:__imp_SafeArrayUnlock
0x1804493ea  test    eax, eax
0x1804493ec  jns     short loc_1804493FB
0x1804493ee  mov     edx, 66336B78h; unsigned int
0x1804493f3  mov     ecx, eax; int
0x1804493f5  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1804493fa  int     3; Trap to Debugger
0x1804493fb  mov     [rbp+57h+var_C0], r12
0x1804493ff  mov     qword ptr [rbp+57h+var_60+8], r14
0x180449403  mov     word ptr [rbp+57h+var_48], di
0x180449407  mov     rcx, rbx; psa
0x18044940a  call    cs:__imp_SafeArrayUnlock
0x180449410  test    eax, eax
0x180449412  jns     short loc_180449421
0x180449414  mov     edx, 66336B78h; unsigned int
0x180449419  mov     ecx, eax; int
0x18044941b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180449420  int     3; Trap to Debugger
0x180449421  mov     [rbp+57h+var_B8], r12
0x180449425  mov     qword ptr [rbp+57h+var_48+8], rbx
0x180449429  mov     rbx, r12
0x18044942c  mov     [rbp+57h+arg_10], rbx
0x180449430  mov     edi, r12d
0x180449433  mov     r13d, 2
0x180449439  cmp     edi, [rsi+38h]
0x18044943c  jnb     short loc_1804494B0
0x18044943e  mov     edx, edi; unsigned int
0x180449440  lea     rcx, [rsi+30h]; this
0x180449444  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x180449449  test    rax, rax
0x18044944c  jz      short loc_180449453
0x18044944e  mov     r8, [rax]
0x180449451  jmp     short loc_180449456
0x180449453  mov     r8, r12
0x180449456  lea     rcx, aForegroundmark_1; "ForegroundMarks"
0x18044945d  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x180449462  mov     r9d, eax; wchar_t *
0x180449465  mov     rcx, [r8+18h]; this
0x180449469  mov     eax, [rcx-4]
0x18044946c  cdq
0x18044946d  idiv    r13d
0x180449470  mov     [rsp+130h+var_110], r12b; char
0x180449475  lea     r8, aForegroundmark_1; "ForegroundMarks"
0x18044947c  mov     edx, eax; wchar_t *
0x18044947e  call    ?FRgchEqual@Ofc@@YA_NPEB_WH0H_N@Z; Ofc::FRgchEqual(wchar_t const *,int,wchar_t const *,int,bool)
0x180449483  test    al, al
0x180449485  jnz     short loc_18044948B
0x180449487  inc     edi
0x180449489  jmp     short loc_180449439
0x18044948b  mov     edx, edi; unsigned int
0x18044948d  lea     rcx, [rsi+30h]; this
0x180449491  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x180449496  test    rax, rax
0x180449499  jz      short loc_1804494A0
0x18044949b  mov     rbx, [rax]
0x18044949e  jmp     short loc_1804494A3
0x1804494a0  mov     rbx, r12
0x1804494a3  test    rbx, rbx
0x1804494a6  jz      short loc_1804494AC
0x1804494a8  lock inc dword ptr [rbx+8]
0x1804494ac  mov     [rbp+57h+arg_10], rbx
0x1804494b0  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1804494b4  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x1804494b9  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1804494be  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x1804494c4  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x1804494c9  mov     r15, [rbp+57h+arg_8]
0x1804494cd  mov     rdx, r15; struct Ofc::CTransaction *
0x1804494d0  mov     rcx, rbx; this
0x1804494d3  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x1804494d8  test    rbx, rbx
0x1804494db  jz      short loc_1804494E6
0x1804494dd  lea     rcx, [rbx+8]
0x1804494e1  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x1804494e6  mov     rbx, r12
0x1804494e9  mov     [rbp+57h+arg_10], rbx
0x1804494ed  mov     edi, r12d
0x1804494f0  cmp     edi, [rsi+38h]
0x1804494f3  jnb     short loc_180449567
0x1804494f5  mov     edx, edi; unsigned int
0x1804494f7  lea     rcx, [rsi+30h]; this
0x1804494fb  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x180449500  test    rax, rax
0x180449503  jz      short loc_18044950A
0x180449505  mov     r8, [rax]
0x180449508  jmp     short loc_18044950D
0x18044950a  mov     r8, r12
0x18044950d  lea     rcx, aBackgroundmark_1; "BackgroundMarks"
0x180449514  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x180449519  mov     r9d, eax; wchar_t *
0x18044951c  mov     rcx, [r8+18h]; this
0x180449520  mov     eax, [rcx-4]
0x180449523  cdq
0x180449524  idiv    r13d
0x180449527  mov     [rsp+130h+var_110], r12b; char
0x18044952c  lea     r8, aBackgroundmark_1; "BackgroundMarks"
0x180449533  mov     edx, eax; wchar_t *
0x180449535  call    ?FRgchEqual@Ofc@@YA_NPEB_WH0H_N@Z; Ofc::FRgchEqual(wchar_t const *,int,wchar_t const *,int,bool)
0x18044953a  test    al, al
0x18044953c  jnz     short loc_180449542
0x18044953e  inc     edi
0x180449540  jmp     short loc_1804494F0
0x180449542  mov     edx, edi; unsigned int
0x180449544  lea     rcx, [rsi+30h]; this
0x180449548  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x18044954d  test    rax, rax
0x180449550  jz      short loc_180449557
0x180449552  mov     rbx, [rax]
0x180449555  jmp     short loc_18044955A
0x180449557  mov     rbx, r12
0x18044955a  test    rbx, rbx
0x18044955d  jz      short loc_180449563
0x18044955f  lock inc dword ptr [rbx+8]
0x180449563  mov     [rbp+57h+arg_10], rbx
0x180449567  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18044956b  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x180449570  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x180449575  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x18044957b  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x180449580  mov     rdx, r15; struct Ofc::CTransaction *
0x180449583  mov     rcx, rbx; this
0x180449586  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x18044958b  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x18044958f  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x180449594  movsd   xmm1, qword ptr [rbp+57h+var_60+10h]
0x180449599  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x18044959f  lea     rcx, [rsi+90h]; this
0x1804495a6  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x1804495ab  mov     rdx, r15; struct Ofc::CTransaction *
0x1804495ae  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x1804495b3  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x1804495b7  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x1804495bc  movsd   xmm1, qword ptr [rbp+57h+var_48+10h]
0x1804495c1  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
  ... truncated ...
```
