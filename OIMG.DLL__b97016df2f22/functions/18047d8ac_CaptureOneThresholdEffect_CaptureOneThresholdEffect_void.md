# CaptureOneThresholdEffect::CaptureOneThresholdEffect(void)

- ea: `0x18047d8ac`
- end: `0x18047dda1`
- name: `??0CaptureOneThresholdEffect@@IEAA@XZ`
- size: `1269`
- prototype: `CaptureOneThresholdEffect *__fastcall(CaptureOneThresholdEffect *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180466550`
- `0x180469150`
- `0x180469310`

## callees

- `0x18019a570`
- `0x18047d8ac`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x18047d902`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18047d902`
- `KERNEL32!GetLastError` at `0x18047dd23`
- `KERNEL32!GetLastError` at `0x18047dd23`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18047d9e8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18047db84`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18047d9e8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18047db84`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047da4a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dabf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047db38`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dbe6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dc5e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dcca`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047da4a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dabf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047db38`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dbe6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dc5e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047dcca`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047da1e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047da95`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047db0a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dbba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dc34`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dca5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047da1e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047da95`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047db0a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dbba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dc34`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047dca5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18047d9fd`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18047db99`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18047d9fd`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18047db99`

## string_xrefs

- `0x18047d95a`: `CaptureOneThresholdEffect.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
CaptureOneThresholdEffect *__fastcall CaptureOneThresholdEffect::CaptureOneThresholdEffect(
        CaptureOneThresholdEffect *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  int v4; // eax
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rcx
  HRESULT LBound; // eax
  __int64 cElements; // rdi
  HRESULT UBound; // eax
  SAFEARRAY *v10; // rcx
  HRESULT v11; // eax
  HRESULT v12; // eax
  SAFEARRAY *v13; // rcx
  HRESULT v14; // eax
  HRESULT v15; // eax
  SAFEARRAY *v16; // rax
  SAFEARRAY *v17; // rcx
  HRESULT v18; // eax
  __int64 v19; // rsi
  HRESULT v20; // eax
  SAFEARRAY *v21; // rcx
  HRESULT v22; // eax
  HRESULT v23; // eax
  SAFEARRAY *v24; // rcx
  HRESULT v25; // eax
  HRESULT v26; // eax
  signed int LastError; // eax
  unsigned int v29; // ecx
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp+38h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+40h] BYREF

  *((_DWORD *)this + 14) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_BYTE *)this + 104) = 0;
  v2 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &SingleThreadingModel::`vftable';
  rgsabound = (SAFEARRAYBOUND)((char *)this + 16);
  if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0) )
  {
    LastError = GetLastError();
    v29 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v29 = LastError;
    ATL::BaseAtlThrow(v29);
  }
  *(_QWORD *)this = &EffectBase<CaptureOneThresholdEffect,1233,1,&__s_GUID const _GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67>::`vftable'{for `IEffectRender'};
  *v2 = &EffectBase<CaptureOneThresholdEffect,1233,1,&__s_GUID const _GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67>::`vftable'{for `SingleThreadingModel'};
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  v4 = DaVinciObjectFactory::CreateInstance<IEffectImpl>(v3, (char *)this + 136);
  *((_DWORD *)this + 30) = v4;
  if ( v4 >= 0 )
    *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, __int64, const WCHAR *, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 17) + 232LL))(
                               *((_QWORD *)this + 17),
                               &GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67,
                               11,
                               15,
                               &psz,
                               L"CaptureOneThresholdEffect.xml",
                               L"CaptureOneThresholdEffect.fx");
  *(_QWORD *)this = &CaptureOneThresholdEffect::`vftable'{for `IEffectRender'};
  *v2 = &CaptureOneThresholdEffect::`vftable'{for `SingleThreadingModel'};
  *((_WORD *)this + 72) = 257;
  *((_DWORD *)this + 37) = 0;
  *((_DWORD *)this + 38) = 1065353216;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v5 = SafeArrayCreate(4u, 1u, &rgsabound);
  *((_QWORD *)this + 20) = v5;
  if ( v5 )
    SafeArrayLock(v5);
  v6 = (SAFEARRAY *)*((_QWORD *)this + 20);
  if ( !v6 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  LBound = SafeArrayGetLBound(v6, 1u, (LONG *)&rgsabound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_40;
  rgsabound.cElements = 0;
  UBound = SafeArrayGetUBound(*((SAFEARRAY **)this + 20), 1u, (LONG *)&rgsabound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_40;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 20) + 16LL) - 4 * cElements) = 0;
  v10 = (SAFEARRAY *)*((_QWORD *)this + 20);
  if ( !v10 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  v11 = SafeArrayGetLBound(v10, 1u, (LONG *)&rgsabound);
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  if ( (int)rgsabound.cElements > 1 )
    goto LABEL_40;
  plUbound = 0;
  v12 = SafeArrayGetUBound(*((SAFEARRAY **)this + 20), 1u, &plUbound);
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  if ( plUbound < 1 )
    goto LABEL_40;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 20) + 16LL) + 4LL * (1 - rgsabound.cElements)) = 0;
  v13 = (SAFEARRAY *)*((_QWORD *)this + 20);
  if ( !v13 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  v14 = SafeArrayGetLBound(v13, 1u, (LONG *)&rgsabound);
  if ( v14 < 0 )
    ATL::BaseAtlThrow(v14);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_40;
  plUbound = 0;
  v15 = SafeArrayGetUBound(*((SAFEARRAY **)this + 20), 1u, &plUbound);
  if ( v15 < 0 )
    ATL::BaseAtlThrow(v15);
  if ( plUbound < 2 )
    goto LABEL_40;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 20) + 16LL) + 4LL * (2 - rgsabound.cElements)) = 1065353216;
  rgsabound = (SAFEARRAYBOUND)3LL;
  if ( !*((_QWORD *)this + 21) )
  {
    v16 = SafeArrayCreate(4u, 1u, &rgsabound);
    *((_QWORD *)this + 21) = v16;
    if ( v16 )
      SafeArrayLock(v16);
  }
  v17 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( !v17 )
LABEL_41:
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  v18 = SafeArrayGetLBound(v17, 1u, (LONG *)&rgsabound);
  if ( v18 < 0 )
    ATL::BaseAtlThrow(v18);
  v19 = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_40;
  rgsabound.cElements = 0;
  v20 = SafeArrayGetUBound(*((SAFEARRAY **)this + 21), 1u, (LONG *)&rgsabound);
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_40;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 21) + 16LL) - 4 * v19) = 1065353216;
  v21 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( !v21 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  v22 = SafeArrayGetLBound(v21, 1u, (LONG *)&rgsabound);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  if ( (int)rgsabound.cElements > 1 )
    goto LABEL_40;
  plUbound = 0;
  v23 = SafeArrayGetUBound(*((SAFEARRAY **)this + 21), 1u, &plUbound);
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  if ( plUbound < 1 )
LABEL_40:
    ATL::BaseAtlThrow(-2147024809);
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 21) + 16LL) + 4LL * (1 - rgsabound.cElements)) = 0;
  v24 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( !v24 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  v25 = SafeArrayGetLBound(v24, 1u, (LONG *)&rgsabound);
  if ( v25 < 0 )
    ATL::BaseAtlThrow(v25);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_40;
  plUbound = 0;
  v26 = SafeArrayGetUBound(*((SAFEARRAY **)this + 21), 1u, &plUbound);
  if ( v26 < 0 )
    ATL::BaseAtlThrow(v26);
  if ( plUbound < 2 )
    goto LABEL_40;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 21) + 16LL) + 4LL * (2 - rgsabound.cElements)) = 0;
  return this;
}

```

## disassembly

```asm
0x18047d8ac  mov     [rsp-28h+arg_18], rbx
0x18047d8b1  mov     [rsp-28h+arg_0], rcx
0x18047d8b6  push    rbp
0x18047d8b7  push    rsi
0x18047d8b8  push    rdi
0x18047d8b9  push    r14
0x18047d8bb  push    r15
0x18047d8bd  mov     rbp, rsp
0x18047d8c0  sub     rsp, 40h
0x18047d8c4  mov     rbx, rcx
0x18047d8c7  xor     r14d, r14d
0x18047d8ca  mov     [rcx+38h], r14d
0x18047d8ce  xorps   xmm0, xmm0
0x18047d8d1  xor     eax, eax
0x18047d8d3  movups  xmmword ptr [rcx+40h], xmm0
0x18047d8d7  movups  xmmword ptr [rcx+50h], xmm0
0x18047d8db  mov     [rcx+60h], rax
0x18047d8df  mov     [rcx+68h], r14b
0x18047d8e3  lea     rsi, [rcx+8]
0x18047d8e7  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x18047d8eb  lea     rax, ??_7SingleThreadingModel@@6B@; const SingleThreadingModel::`vftable'
0x18047d8f2  mov     [rsi], rax
0x18047d8f5  lea     rcx, [rsi+8]; lpCriticalSection
0x18047d8f9  mov     qword ptr [rbp+rgsabound.cElements], rcx
0x18047d8fd  xor     r8d, r8d; Flags
0x18047d900  xor     edx, edx; dwSpinCount
0x18047d902  call    cs:__imp_InitializeCriticalSectionEx
0x18047d908  test    eax, eax
0x18047d90a  jz      loc_18047DD23
0x18047d910  lea     rax, ??_7?$EffectBase@VCaptureOneThresholdEffect@@$0ENB@$00$1?_GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67@@3U__s_GUID@@B@@6BIEffectRender@@@; const EffectBase<CaptureOneThresholdEffect,1233,1,&__s_GUID const _GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67>::`vftable'{for `IEffectRender'}
0x18047d917  mov     [rbx], rax
0x18047d91a  lea     rax, ??_7?$EffectBase@VCaptureOneThresholdEffect@@$0ENB@$00$1?_GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67@@3U__s_GUID@@B@@6BSingleThreadingModel@@@; const EffectBase<CaptureOneThresholdEffect,1233,1,&__s_GUID const _GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67>::`vftable'{for `SingleThreadingModel'}
0x18047d921  mov     [rsi], rax
0x18047d924  mov     [rbx+70h], r14
0x18047d928  lea     rdi, [rbx+88h]
0x18047d92f  mov     [rdi], r14
0x18047d932  mov     [rbx+80h], r14
0x18047d939  mov     rdx, rdi
0x18047d93c  call    ??$CreateInstance@UIEffectImpl@@@DaVinciObjectFactory@@SAJAEBU_GUID@@PEAPEAUIEffectImpl@@PEAUIUnknown@@@Z; DaVinciObjectFactory::CreateInstance<IEffectImpl>(_GUID const &,IEffectImpl * *,IUnknown *)
0x18047d941  mov     [rbx+78h], eax
0x18047d944  test    eax, eax
0x18047d946  js      short loc_18047D991
0x18047d948  mov     rcx, [rdi]
0x18047d94b  mov     rax, [rcx]
0x18047d94e  lea     rdx, aCaptureonethre; "CaptureOneThresholdEffect.fx"
0x18047d955  mov     [rsp+40h+var_10], rdx
0x18047d95a  lea     rdx, aCaptureonethre_0; "CaptureOneThresholdEffect.xml"
0x18047d961  mov     [rsp+40h+var_18], rdx
0x18047d966  lea     rdx, psz
0x18047d96d  mov     [rsp+40h+var_20], rdx
0x18047d972  lea     r9d, [r14+0Fh]
0x18047d976  lea     r8d, [r14+0Bh]
0x18047d97a  lea     rdx, _GUID_63b23621_e3e3_4842_81fe_4afe8ce6de67
0x18047d981  mov     rax, [rax+0E8h]
0x18047d988  call    cs:__guard_dispatch_icall_fptr
0x18047d98e  mov     [rbx+78h], eax
0x18047d991  lea     rax, ??_7CaptureOneThresholdEffect@@6BIEffectRender@@@; const CaptureOneThresholdEffect::`vftable'{for `IEffectRender'}
0x18047d998  mov     [rbx], rax
0x18047d99b  lea     rax, ??_7CaptureOneThresholdEffect@@6BSingleThreadingModel@@@; const CaptureOneThresholdEffect::`vftable'{for `SingleThreadingModel'}
0x18047d9a2  mov     [rsi], rax
0x18047d9a5  mov     r15d, 1
0x18047d9ab  mov     word ptr [rbx+90h], 101h
0x18047d9b4  mov     [rbx+94h], r14d
0x18047d9bb  mov     dword ptr [rbx+98h], 3F800000h
0x18047d9c5  mov     [rbx+0A0h], r14
0x18047d9cc  mov     [rbx+0A8h], r14
0x18047d9d3  mov     qword ptr [rbp+rgsabound.cElements], 3
0x18047d9db  lea     esi, [r15+3]
0x18047d9df  mov     ecx, esi; vt
0x18047d9e1  lea     r8, [rbp+rgsabound]; rgsabound
0x18047d9e5  mov     edx, r15d; cDims
0x18047d9e8  call    cs:__imp_SafeArrayCreate
0x18047d9ee  mov     [rbx+0A0h], rax
0x18047d9f5  test    rax, rax
0x18047d9f8  jz      short loc_18047DA03
0x18047d9fa  mov     rcx, rax; psa
0x18047d9fd  call    cs:__imp_SafeArrayLock
0x18047da03  mov     rcx, [rbx+0A0h]; psa
0x18047da0a  test    rcx, rcx
0x18047da0d  jz      loc_18047DD14
0x18047da13  mov     [rbp+rgsabound.cElements], r14d
0x18047da17  lea     r8, [rbp+rgsabound]; plLbound
0x18047da1b  mov     edx, r15d; nDim
0x18047da1e  call    cs:__imp_SafeArrayGetLBound
0x18047da24  test    eax, eax
0x18047da26  js      loc_18047DD41
0x18047da2c  movsxd  rdi, [rbp+rgsabound.cElements]
0x18047da30  test    edi, edi
0x18047da32  jg      loc_18047DD09
0x18047da38  mov     [rbp+rgsabound.cElements], r14d
0x18047da3c  lea     r8, [rbp+rgsabound]; plUbound
0x18047da40  mov     edx, r15d; nDim
0x18047da43  mov     rcx, [rbx+0A0h]; psa
0x18047da4a  call    cs:__imp_SafeArrayGetUBound
0x18047da50  test    eax, eax
0x18047da52  js      loc_18047DD49
0x18047da58  cmp     [rbp+rgsabound.cElements], r14d
0x18047da5c  jl      loc_18047DD09
0x18047da62  mov     rdx, rdi
0x18047da65  shl     rdx, 2
0x18047da69  mov     rax, [rbx+0A0h]
0x18047da70  mov     rcx, [rax+10h]
0x18047da74  sub     rcx, rdx
0x18047da77  mov     [rcx], r14d
0x18047da7a  mov     rcx, [rbx+0A0h]; psa
0x18047da81  test    rcx, rcx
0x18047da84  jz      loc_18047DD14
0x18047da8a  mov     [rbp+rgsabound.cElements], r14d
0x18047da8e  lea     r8, [rbp+rgsabound]; plLbound
0x18047da92  mov     edx, r15d; nDim
0x18047da95  call    cs:__imp_SafeArrayGetLBound
0x18047da9b  test    eax, eax
0x18047da9d  js      loc_18047DD51
0x18047daa3  cmp     [rbp+rgsabound.cElements], r15d
0x18047daa7  jg      loc_18047DD09
0x18047daad  mov     [rbp+plUbound], r14d
0x18047dab1  lea     r8, [rbp+plUbound]; plUbound
0x18047dab5  mov     edx, r15d; nDim
0x18047dab8  mov     rcx, [rbx+0A0h]; psa
0x18047dabf  call    cs:__imp_SafeArrayGetUBound
0x18047dac5  test    eax, eax
0x18047dac7  js      loc_18047DD59
0x18047dacd  cmp     [rbp+plUbound], r15d
0x18047dad1  jl      loc_18047DD09
0x18047dad7  mov     eax, r15d
0x18047dada  sub     eax, [rbp+rgsabound.cElements]
0x18047dadd  movsxd  rdx, eax
0x18047dae0  mov     rax, [rbx+0A0h]
0x18047dae7  mov     rcx, [rax+10h]
0x18047daeb  mov     [rcx+rdx*4], r14d
0x18047daef  mov     rcx, [rbx+0A0h]; psa
0x18047daf6  test    rcx, rcx
0x18047daf9  jz      loc_18047DD14
0x18047daff  mov     [rbp+rgsabound.cElements], r14d
0x18047db03  lea     r8, [rbp+rgsabound]; plLbound
0x18047db07  mov     edx, r15d; nDim
0x18047db0a  call    cs:__imp_SafeArrayGetLBound
0x18047db10  test    eax, eax
0x18047db12  js      loc_18047DD61
0x18047db18  mov     edi, 2
0x18047db1d  cmp     [rbp+rgsabound.cElements], edi
0x18047db20  jg      loc_18047DD09
0x18047db26  mov     [rbp+plUbound], r14d
0x18047db2a  lea     r8, [rbp+plUbound]; plUbound
0x18047db2e  mov     edx, r15d; nDim
0x18047db31  mov     rcx, [rbx+0A0h]; psa
0x18047db38  call    cs:__imp_SafeArrayGetUBound
0x18047db3e  test    eax, eax
0x18047db40  js      loc_18047DD69
0x18047db46  cmp     [rbp+plUbound], edi
0x18047db49  jl      loc_18047DD09
0x18047db4f  mov     eax, edi
0x18047db51  sub     eax, [rbp+rgsabound.cElements]
0x18047db54  movsxd  r8, eax
0x18047db57  mov     rax, [rbx+0A0h]
0x18047db5e  mov     rdx, [rax+10h]
0x18047db62  mov     dword ptr [rdx+r8*4], 3F800000h
0x18047db6a  mov     qword ptr [rbp+rgsabound.cElements], 3
0x18047db72  cmp     [rbx+0A8h], r14
0x18047db79  jnz     short loc_18047DB9F
0x18047db7b  mov     ecx, esi; vt
0x18047db7d  lea     r8, [rbp+rgsabound]; rgsabound
0x18047db81  mov     edx, r15d; cDims
0x18047db84  call    cs:__imp_SafeArrayCreate
0x18047db8a  mov     [rbx+0A8h], rax
0x18047db91  test    rax, rax
0x18047db94  jz      short loc_18047DB9F
0x18047db96  mov     rcx, rax; psa
0x18047db99  call    cs:__imp_SafeArrayLock
0x18047db9f  mov     rcx, [rbx+0A8h]; psa
0x18047dba6  test    rcx, rcx
0x18047dba9  jz      loc_18047DD14
0x18047dbaf  mov     [rbp+rgsabound.cElements], r14d
0x18047dbb3  lea     r8, [rbp+rgsabound]; plLbound
0x18047dbb7  mov     edx, r15d; nDim
0x18047dbba  call    cs:__imp_SafeArrayGetLBound
0x18047dbc0  test    eax, eax
0x18047dbc2  js      loc_18047DD71
0x18047dbc8  movsxd  rsi, [rbp+rgsabound.cElements]
0x18047dbcc  test    esi, esi
0x18047dbce  jg      loc_18047DD09
0x18047dbd4  mov     [rbp+rgsabound.cElements], r14d
0x18047dbd8  lea     r8, [rbp+rgsabound]; plUbound
0x18047dbdc  mov     edx, r15d; nDim
0x18047dbdf  mov     rcx, [rbx+0A8h]; psa
0x18047dbe6  call    cs:__imp_SafeArrayGetUBound
0x18047dbec  test    eax, eax
0x18047dbee  js      loc_18047DD79
0x18047dbf4  cmp     [rbp+rgsabound.cElements], r14d
0x18047dbf8  jl      loc_18047DD09
0x18047dbfe  mov     rdx, rsi
0x18047dc01  shl     rdx, 2
0x18047dc05  mov     rax, [rbx+0A8h]
0x18047dc0c  mov     rcx, [rax+10h]
0x18047dc10  sub     rcx, rdx
0x18047dc13  mov     dword ptr [rcx], 3F800000h
0x18047dc19  mov     rcx, [rbx+0A8h]; psa
0x18047dc20  test    rcx, rcx
0x18047dc23  jz      loc_18047DD14
0x18047dc29  mov     [rbp+rgsabound.cElements], r14d
0x18047dc2d  lea     r8, [rbp+rgsabound]; plLbound
0x18047dc31  mov     edx, r15d; nDim
0x18047dc34  call    cs:__imp_SafeArrayGetLBound
0x18047dc3a  test    eax, eax
0x18047dc3c  js      loc_18047DD81
0x18047dc42  cmp     [rbp+rgsabound.cElements], r15d
0x18047dc46  jg      loc_18047DD09
0x18047dc4c  mov     [rbp+plUbound], r14d
0x18047dc50  lea     r8, [rbp+plUbound]; plUbound
0x18047dc54  mov     edx, r15d; nDim
0x18047dc57  mov     rcx, [rbx+0A8h]; psa
0x18047dc5e  call    cs:__imp_SafeArrayGetUBound
0x18047dc64  test    eax, eax
0x18047dc66  js      loc_18047DD89
0x18047dc6c  cmp     [rbp+plUbound], r15d
0x18047dc70  jl      loc_18047DD09
0x18047dc76  mov     eax, r15d
0x18047dc79  sub     eax, [rbp+rgsabound.cElements]
0x18047dc7c  movsxd  rdx, eax
0x18047dc7f  mov     rax, [rbx+0A8h]
0x18047dc86  mov     rcx, [rax+10h]
0x18047dc8a  mov     [rcx+rdx*4], r14d
0x18047dc8e  mov     rcx, [rbx+0A8h]; psa
0x18047dc95  test    rcx, rcx
0x18047dc98  jz      short loc_18047DD14
0x18047dc9a  mov     [rbp+rgsabound.cElements], r14d
0x18047dc9e  lea     r8, [rbp+rgsabound]; plLbound
0x18047dca2  mov     edx, r15d; nDim
0x18047dca5  call    cs:__imp_SafeArrayGetLBound
0x18047dcab  test    eax, eax
0x18047dcad  js      loc_18047DD91
0x18047dcb3  cmp     [rbp+rgsabound.cElements], edi
0x18047dcb6  jg      short loc_18047DD09
0x18047dcb8  mov     [rbp+plUbound], r14d
0x18047dcbc  lea     r8, [rbp+plUbound]; plUbound
0x18047dcc0  mov     edx, r15d; nDim
0x18047dcc3  mov     rcx, [rbx+0A8h]; psa
0x18047dcca  call    cs:__imp_SafeArrayGetUBound
0x18047dcd0  test    eax, eax
0x18047dcd2  js      loc_18047DD99
0x18047dcd8  cmp     [rbp+plUbound], edi
0x18047dcdb  jl      short loc_18047DD09
0x18047dcdd  sub     edi, [rbp+rgsabound.cElements]
0x18047dce0  movsxd  rdx, edi
0x18047dce3  mov     rax, [rbx+0A8h]
0x18047dcea  mov     rcx, [rax+10h]
0x18047dcee  mov     [rcx+rdx*4], r14d
0x18047dcf2  mov     rax, rbx
0x18047dcf5  mov     rbx, [rsp+40h+arg_18]
0x18047dcfd  add     rsp, 40h
0x18047dd01  pop     r15
0x18047dd03  pop     r14
0x18047dd05  pop     rdi
0x18047dd06  pop     rsi
0x18047dd07  pop     rbp
0x18047dd08  retn
0x18047dd09  mov     ecx, 80070057h; int
0x18047dd0e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd14  mov     ecx, 80004005h; int
0x18047dd19  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd1f  jmp     short loc_18047DD22
0x18047dd22  nop
0x18047dd23  call    cs:__imp_GetLastError
0x18047dd29  movzx   ecx, ax
0x18047dd2c  or      ecx, 80070000h
0x18047dd32  test    eax, eax
0x18047dd34  cmovle  ecx, eax; int
0x18047dd37  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd41  mov     ecx, eax; int
0x18047dd43  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd49  mov     ecx, eax; int
0x18047dd4b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd51  mov     ecx, eax; int
0x18047dd53  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd59  mov     ecx, eax; int
0x18047dd5b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd61  mov     ecx, eax; int
0x18047dd63  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd69  mov     ecx, eax; int
0x18047dd6b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd71  mov     ecx, eax; int
0x18047dd73  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd79  mov     ecx, eax; int
0x18047dd7b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd81  mov     ecx, eax; int
0x18047dd83  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd89  mov     ecx, eax; int
0x18047dd8b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd91  mov     ecx, eax; int
0x18047dd93  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18047dd99  mov     ecx, eax; int
0x18047dd9b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
