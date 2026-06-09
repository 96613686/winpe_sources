# Art::PictureEffectBackgroundRemoval::SetMarks(Ofc::CTransaction &,Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalBackgroundMarkData>,0,4294967295> const &)

- ea: `0x18044b978`
- end: `0x18044bdeb`
- name: `?SetMarks@PictureEffectBackgroundRemoval@Art@@QEAAXAEAVCTransaction@Ofc@@AEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@4@AEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalBackgroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@4@@Z`
- size: `1139`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180449f20`
- `0x18044ad2c`
- `0x1808ab950`
- `0x1808ae660`

## callees

- `0x18000dc24`
- `0x1800501f0`
- `0x180050580`
- `0x1801b09dc`
- `0x18026ceb8`
- `0x18044a308`
- `0x18044b978`
- `0x18044db80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18044bb3d`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb47`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb51`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb5b`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb3d`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb47`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb51`
- `OLEAUT32!__imp_VariantInit` at `0x18044bb5b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044b9c0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044ba11`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044ba65`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044bab5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044b9c0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044ba11`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044ba65`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18044bab5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044b9dc`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044ba2d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044ba81`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044bad1`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044b9dc`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044ba2d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044ba81`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18044bad1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bb76`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bb9d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bbc8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bbee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bb76`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bb9d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bbc8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18044bbee`

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
0x18044b978  mov     [rsp-8+arg_0], rbx
0x18044b97d  mov     [rsp-8+arg_8], rdx
0x18044b982  push    rbp
0x18044b983  push    rsi
0x18044b984  push    rdi
0x18044b985  push    r12
0x18044b987  push    r13
0x18044b989  push    r14
0x18044b98b  push    r15
0x18044b98d  lea     rbp, [rsp-27h]
0x18044b992  sub     rsp, 100h
0x18044b999  mov     r13, r9
0x18044b99c  mov     r12, r8
0x18044b99f  mov     rsi, rcx
0x18044b9a2  mov     eax, [r8+10h]
0x18044b9a6  mov     [rbp+57h+rgsabound.cElements], eax
0x18044b9a9  xor     ebx, ebx
0x18044b9ab  mov     [rbp+57h+rgsabound.lLbound], ebx
0x18044b9ae  mov     [rbp+57h+var_A8], 4
0x18044b9b6  lea     ecx, [rbx+5]; vt
0x18044b9b9  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18044b9bd  lea     edx, [rbx+2]; cDims
0x18044b9c0  call    cs:__imp_SafeArrayCreate
0x18044b9c6  mov     r15, rax
0x18044b9c9  mov     [rbp+57h+var_D0], rax
0x18044b9cd  test    rax, rax
0x18044b9d0  jnz     short loc_18044B9D9
0x18044b9d2  mov     eax, 8007000Eh
0x18044b9d7  jmp     short loc_18044B9E6
0x18044b9d9  mov     rcx, r15; psa
0x18044b9dc  call    cs:__imp_SafeArrayLock
0x18044b9e2  test    eax, eax
0x18044b9e4  jns     short loc_18044B9F7
0x18044b9e6  mov     edx, 66336B77h; unsigned int
0x18044b9eb  mov     ecx, eax; int
0x18044b9ed  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044b9f2  nop
0x18044b9f3  jmp     short loc_18044B9F6
0x18044b9f6  nop
0x18044b9f7  mov     eax, [r12+10h]
0x18044b9fc  mov     [rsp+130h+var_E0.cElements], eax
0x18044ba00  mov     [rsp+130h+var_E0.lLbound], ebx
0x18044ba04  mov     ecx, 3; vt
0x18044ba09  lea     r8, [rsp+130h+var_E0]; rgsabound
0x18044ba0e  lea     edx, [rcx-2]; cDims
0x18044ba11  call    cs:__imp_SafeArrayCreate
0x18044ba17  mov     r14, rax
0x18044ba1a  mov     [rbp+57h+var_C0], rax
0x18044ba1e  test    rax, rax
0x18044ba21  jnz     short loc_18044BA2A
0x18044ba23  mov     eax, 8007000Eh
0x18044ba28  jmp     short loc_18044BA37
0x18044ba2a  mov     rcx, r14; psa
0x18044ba2d  call    cs:__imp_SafeArrayLock
0x18044ba33  test    eax, eax
0x18044ba35  jns     short loc_18044BA47
0x18044ba37  mov     edx, 66336B77h; unsigned int
0x18044ba3c  mov     ecx, eax; int
0x18044ba3e  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044ba43  nop
0x18044ba44  jmp     short $+2
0x18044ba46  nop
0x18044ba47  mov     eax, [r13+10h]
0x18044ba4b  mov     [rbp+57h+var_A0.cElements], eax
0x18044ba4e  mov     [rbp+57h+var_A0.lLbound], ebx
0x18044ba51  mov     [rbp+57h+var_98], 4
0x18044ba59  mov     ecx, 5; vt
0x18044ba5e  lea     r8, [rbp+57h+var_A0]; rgsabound
0x18044ba62  lea     edx, [rcx-3]; cDims
0x18044ba65  call    cs:__imp_SafeArrayCreate
0x18044ba6b  mov     rdi, rax
0x18044ba6e  mov     [rbp+57h+var_C8], rax
0x18044ba72  test    rax, rax
0x18044ba75  jnz     short loc_18044BA7E
0x18044ba77  mov     eax, 8007000Eh
0x18044ba7c  jmp     short loc_18044BA8B
0x18044ba7e  mov     rcx, rdi; psa
0x18044ba81  call    cs:__imp_SafeArrayLock
0x18044ba87  test    eax, eax
0x18044ba89  jns     short loc_18044BA9D
0x18044ba8b  mov     edx, 66336B77h; unsigned int
0x18044ba90  mov     ecx, eax; int
0x18044ba92  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044ba97  nop
0x18044ba98  jmp     short loc_18044BA9C
0x18044ba9c  nop
0x18044ba9d  mov     eax, [r13+10h]
0x18044baa1  mov     [rsp+130h+var_D8.cElements], eax
0x18044baa5  mov     [rbp+57h+var_D8.lLbound], ebx
0x18044baa8  mov     ecx, 3; vt
0x18044baad  lea     r8, [rsp+130h+var_D8]; rgsabound
0x18044bab2  lea     edx, [rcx-2]; cDims
0x18044bab5  call    cs:__imp_SafeArrayCreate
0x18044babb  mov     rbx, rax
0x18044babe  mov     [rbp+57h+var_B8], rax
0x18044bac2  test    rax, rax
0x18044bac5  jnz     short loc_18044BACE
0x18044bac7  mov     eax, 8007000Eh
0x18044bacc  jmp     short loc_18044BADB
0x18044bace  mov     rcx, rbx; psa
0x18044bad1  call    cs:__imp_SafeArrayLock
0x18044bad7  test    eax, eax
0x18044bad9  jns     short loc_18044BAEB
0x18044badb  mov     edx, 66336B77h; unsigned int
0x18044bae0  mov     ecx, eax; int
0x18044bae2  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044bae7  nop
0x18044bae8  jmp     short $+2
0x18044baea  nop
0x18044baeb  lea     r9, [rbp+57h+var_C0]
0x18044baef  lea     r8, [rbp+57h+var_D0]
0x18044baf3  mov     rdx, r12
0x18044baf6  mov     rcx, rsi
0x18044baf9  call    ??$SetMarksHelper@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@@PictureEffectBackgroundRemoval@Art@@AEAAXAEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@Ofc@@AEAV?$SafeArray@N$04@@AEAV?$SafeArray@I$02@@@Z; Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,SafeArray<double,5> &,SafeArray<uint,3> &)
0x18044bafe  lea     r9, [rbp+57h+var_B8]
0x18044bb02  lea     r8, [rbp+57h+var_C8]
0x18044bb06  mov     rdx, r13
0x18044bb09  mov     rcx, rsi
0x18044bb0c  call    ??$SetMarksHelper@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@@PictureEffectBackgroundRemoval@Art@@AEAAXAEBV?$TVector@V?$BackgroundRemovalMarkMethods@VPictureEffectBackgroundRemovalForegroundMarkData@Art@@@Art@@$0A@$0PPPPPPPP@@Ofc@@AEAV?$SafeArray@N$04@@AEAV?$SafeArray@I$02@@@Z; Art::PictureEffectBackgroundRemoval::SetMarksHelper<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>>(Ofc::TVector<Art::BackgroundRemovalMarkMethods<Art::PictureEffectBackgroundRemovalForegroundMarkData>,0,4294967295> const &,SafeArray<double,5> &,SafeArray<uint,3> &)
0x18044bb11  xorps   xmm0, xmm0
0x18044bb14  xor     eax, eax
0x18044bb16  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18044bb1a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18044bb1e  xorps   xmm1, xmm1
0x18044bb21  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x18044bb25  mov     qword ptr [rbp+57h+var_78+10h], rax
0x18044bb29  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18044bb2d  mov     qword ptr [rbp+57h+var_60+10h], rax
0x18044bb31  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18044bb35  mov     qword ptr [rbp+57h+var_48+10h], rax
0x18044bb39  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18044bb3d  call    cs:__imp_VariantInit
0x18044bb43  lea     rcx, [rbp+57h+var_78]; pvarg
0x18044bb47  call    cs:__imp_VariantInit
0x18044bb4d  lea     rcx, [rbp+57h+var_60]; pvarg
0x18044bb51  call    cs:__imp_VariantInit
0x18044bb57  lea     rcx, [rbp+57h+var_48]; pvarg
0x18044bb5b  call    cs:__imp_VariantInit
0x18044bb61  xor     r12d, r12d
0x18044bb64  mov     [rbp+57h+arg_10], r12
0x18044bb68  mov     r13d, 2005h
0x18044bb6e  mov     word ptr [rbp+57h+pvarg], r13w
0x18044bb73  mov     rcx, r15; psa
0x18044bb76  call    cs:__imp_SafeArrayUnlock
0x18044bb7c  test    eax, eax
0x18044bb7e  jns     short loc_18044BB8D
0x18044bb80  mov     edx, 66336B78h; unsigned int
0x18044bb85  mov     ecx, eax; int
0x18044bb87  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044bb8c  int     3; Trap to Debugger
0x18044bb8d  mov     [rbp+57h+var_D0], r12
0x18044bb91  mov     qword ptr [rbp+57h+pvarg+8], r15
0x18044bb95  mov     word ptr [rbp+57h+var_78], r13w
0x18044bb9a  mov     rcx, rdi; psa
0x18044bb9d  call    cs:__imp_SafeArrayUnlock
0x18044bba3  test    eax, eax
0x18044bba5  jns     short loc_18044BBB4
0x18044bba7  mov     edx, 66336B78h; unsigned int
0x18044bbac  mov     ecx, eax; int
0x18044bbae  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044bbb3  int     3; Trap to Debugger
0x18044bbb4  mov     [rbp+57h+var_C8], r12
0x18044bbb8  mov     qword ptr [rbp+57h+var_78+8], rdi
0x18044bbbc  mov     edi, 2003h
0x18044bbc1  mov     word ptr [rbp+57h+var_60], di
0x18044bbc5  mov     rcx, r14; psa
0x18044bbc8  call    cs:__imp_SafeArrayUnlock
0x18044bbce  test    eax, eax
0x18044bbd0  jns     short loc_18044BBDF
0x18044bbd2  mov     edx, 66336B78h; unsigned int
0x18044bbd7  mov     ecx, eax; int
0x18044bbd9  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044bbde  int     3; Trap to Debugger
0x18044bbdf  mov     [rbp+57h+var_C0], r12
0x18044bbe3  mov     qword ptr [rbp+57h+var_60+8], r14
0x18044bbe7  mov     word ptr [rbp+57h+var_48], di
0x18044bbeb  mov     rcx, rbx; psa
0x18044bbee  call    cs:__imp_SafeArrayUnlock
0x18044bbf4  test    eax, eax
0x18044bbf6  jns     short loc_18044BC05
0x18044bbf8  mov     edx, 66336B78h; unsigned int
0x18044bbfd  mov     ecx, eax; int
0x18044bbff  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18044bc04  int     3; Trap to Debugger
0x18044bc05  mov     [rbp+57h+var_B8], r12
0x18044bc09  mov     qword ptr [rbp+57h+var_48+8], rbx
0x18044bc0d  mov     rbx, r12
0x18044bc10  mov     [rbp+57h+arg_10], rbx
0x18044bc14  mov     edi, r12d
0x18044bc17  mov     r13d, 2
0x18044bc1d  cmp     edi, [rsi+38h]
0x18044bc20  jnb     short loc_18044BC94
0x18044bc22  mov     edx, edi; unsigned int
0x18044bc24  lea     rcx, [rsi+30h]; this
0x18044bc28  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x18044bc2d  test    rax, rax
0x18044bc30  jz      short loc_18044BC37
0x18044bc32  mov     r8, [rax]
0x18044bc35  jmp     short loc_18044BC3A
0x18044bc37  mov     r8, r12
0x18044bc3a  lea     rcx, aForegroundmark_1; "ForegroundMarks"
0x18044bc41  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18044bc46  mov     r9d, eax; wchar_t *
0x18044bc49  mov     rcx, [r8+18h]; this
0x18044bc4d  mov     eax, [rcx-4]
0x18044bc50  cdq
0x18044bc51  idiv    r13d
0x18044bc54  mov     [rsp+130h+var_110], r12b; char
0x18044bc59  lea     r8, aForegroundmark_1; "ForegroundMarks"
0x18044bc60  mov     edx, eax; wchar_t *
0x18044bc62  call    ?FRgchEqual@Ofc@@YA_NPEB_WH0H_N@Z; Ofc::FRgchEqual(wchar_t const *,int,wchar_t const *,int,bool)
0x18044bc67  test    al, al
0x18044bc69  jnz     short loc_18044BC6F
0x18044bc6b  inc     edi
0x18044bc6d  jmp     short loc_18044BC1D
0x18044bc6f  mov     edx, edi; unsigned int
0x18044bc71  lea     rcx, [rsi+30h]; this
0x18044bc75  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x18044bc7a  test    rax, rax
0x18044bc7d  jz      short loc_18044BC84
0x18044bc7f  mov     rbx, [rax]
0x18044bc82  jmp     short loc_18044BC87
0x18044bc84  mov     rbx, r12
0x18044bc87  test    rbx, rbx
0x18044bc8a  jz      short loc_18044BC90
0x18044bc8c  lock inc dword ptr [rbx+8]
0x18044bc90  mov     [rbp+57h+arg_10], rbx
0x18044bc94  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18044bc98  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x18044bc9d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18044bca2  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x18044bca8  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x18044bcad  mov     r15, [rbp+57h+arg_8]
0x18044bcb1  mov     rdx, r15; struct Ofc::CTransaction *
0x18044bcb4  mov     rcx, rbx; this
0x18044bcb7  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x18044bcbc  test    rbx, rbx
0x18044bcbf  jz      short loc_18044BCCA
0x18044bcc1  lea     rcx, [rbx+8]
0x18044bcc5  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x18044bcca  mov     rbx, r12
0x18044bccd  mov     [rbp+57h+arg_10], rbx
0x18044bcd1  mov     edi, r12d
0x18044bcd4  cmp     edi, [rsi+38h]
0x18044bcd7  jnb     short loc_18044BD4B
0x18044bcd9  mov     edx, edi; unsigned int
0x18044bcdb  lea     rcx, [rsi+30h]; this
0x18044bcdf  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x18044bce4  test    rax, rax
0x18044bce7  jz      short loc_18044BCEE
0x18044bce9  mov     r8, [rax]
0x18044bcec  jmp     short loc_18044BCF1
0x18044bcee  mov     r8, r12
0x18044bcf1  lea     rcx, aBackgroundmark_1; "BackgroundMarks"
0x18044bcf8  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18044bcfd  mov     r9d, eax; wchar_t *
0x18044bd00  mov     rcx, [r8+18h]; this
0x18044bd04  mov     eax, [rcx-4]
0x18044bd07  cdq
0x18044bd08  idiv    r13d
0x18044bd0b  mov     [rsp+130h+var_110], r12b; char
0x18044bd10  lea     r8, aBackgroundmark_1; "BackgroundMarks"
0x18044bd17  mov     edx, eax; wchar_t *
0x18044bd19  call    ?FRgchEqual@Ofc@@YA_NPEB_WH0H_N@Z; Ofc::FRgchEqual(wchar_t const *,int,wchar_t const *,int,bool)
0x18044bd1e  test    al, al
0x18044bd20  jnz     short loc_18044BD26
0x18044bd22  inc     edi
0x18044bd24  jmp     short loc_18044BCD4
0x18044bd26  mov     edx, edi; unsigned int
0x18044bd28  lea     rcx, [rsi+30h]; this
0x18044bd2c  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x18044bd31  test    rax, rax
0x18044bd34  jz      short loc_18044BD3B
0x18044bd36  mov     rbx, [rax]
0x18044bd39  jmp     short loc_18044BD3E
0x18044bd3b  mov     rbx, r12
0x18044bd3e  test    rbx, rbx
0x18044bd41  jz      short loc_18044BD47
0x18044bd43  lock inc dword ptr [rbx+8]
0x18044bd47  mov     [rbp+57h+arg_10], rbx
0x18044bd4b  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18044bd4f  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x18044bd54  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18044bd59  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x18044bd5f  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x18044bd64  mov     rdx, r15; struct Ofc::CTransaction *
0x18044bd67  mov     rcx, rbx; this
0x18044bd6a  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x18044bd6f  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x18044bd73  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x18044bd78  movsd   xmm1, qword ptr [rbp+57h+var_60+10h]
0x18044bd7d  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
0x18044bd83  lea     rcx, [rsi+90h]; this
0x18044bd8a  lea     r8, [rsp+130h+var_100]; struct tagVARIANT
0x18044bd8f  mov     rdx, r15; struct Ofc::CTransaction *
0x18044bd92  call    ?SetValue@PictureEffectParam@Art@@QEAAXAEAVCTransaction@Ofc@@UtagVARIANT@@@Z; Art::PictureEffectParam::SetValue(Ofc::CTransaction &,tagVARIANT)
0x18044bd97  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x18044bd9b  movaps  xmmword ptr [rsp+130h+var_100], xmm0
0x18044bda0  movsd   xmm1, qword ptr [rbp+57h+var_48+10h]
0x18044bda5  movsd   qword ptr [rsp+130h+var_100+10h], xmm1
  ... truncated ...
```
