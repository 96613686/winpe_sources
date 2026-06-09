# CApplicationFrame::SetApplicationId(ushort const *,int)

- ea: `0x1800111d0`
- end: `0x1800116ba`
- name: `?SetApplicationId@CApplicationFrame@@UEAAJPEBGH@Z`
- size: `1258`
- prototype: `__int64 __fastcall(CApplicationFrame *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003380`
- `0x180003e30`
- `0x180004c98`
- `0x180004e8c`
- `0x1800111d0`
- `0x1800116c0`
- `0x1800118e0`
- `0x180011940`
- `0x180011bb4`
- `0x18001e260`
- `0x180031a20`
- `0x180039990`
- `0x18003e8e4`
- `0x180040270`
- `0x18004d490`
- `0x18004dfbc`
- `0x18004e09c`
- `0x18004e9a4`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001149b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001149b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011581`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18001135b`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18001135b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CApplicationFrame::SetApplicationId(CApplicationFrame *this, unsigned __int16 *a2, unsigned int a3)
{
  _QWORD *v5; // r15
  int v6; // eax
  int v7; // ebx
  __int64 *v8; // r14
  PSRWLOCK v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r10
  int v15; // eax
  HRESULT v16; // eax
  void *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  void *v20; // rcx
  RTL_SRWLOCK *v21; // rcx
  __int64 v22; // rcx
  void *v23; // rcx
  RTL_SRWLOCK *v24; // rcx
  __int64 v25; // rcx
  void *v27; // rcx
  RTL_SRWLOCK *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  void *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // [rsp+20h] [rbp-49h]
  int v35; // [rsp+20h] [rbp-49h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-39h] BYREF
  void *v37; // [rsp+38h] [rbp-31h] BYREF
  RTL_SRWLOCK *v38; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv[3]; // [rsp+48h] [rbp-21h] BYREF
  int v40[4]; // [rsp+60h] [rbp-9h] BYREF
  __int16 v41; // [rsp+70h] [rbp+7h] BYREF
  LPVOID v42; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v44; // [rsp+D0h] [rbp+67h] BYREF
  void *ppv; // [rsp+E8h] [rbp+7Fh] BYREF

  v5 = (_QWORD *)((char *)this + 160);
  if ( *((_QWORD *)this + 20) )
    return 0;
  memset(pv, 0, sizeof(pv));
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         (__int64)pv,
         a2,
         0xFFFFFFFFFFFFFFFFuLL);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v6,
      v34);
LABEL_31:
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return (unsigned int)v7;
  }
  v44 = 0;
  SRWLock = (PSRWLOCK)&v44;
  v8 = (__int64 *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&SRWLock);
  SRWLock = 0;
  v7 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>>(
         (char *)this - 8,
         &GUID_00000038_0000_0000_c000_000000000046,
         &SRWLock);
  if ( v7 < 0 )
  {
    if ( SRWLock )
      (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
  }
  else
  {
    v37 = 0;
    v9 = SRWLock;
    v7 = (*((__int64 (__fastcall **)(PSRWLOCK, void **))SRWLock->Ptr + 3))(SRWLock, &v37);
    if ( v7 < 0 )
    {
      v31 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      if ( v9 )
        (*((void (__fastcall **)(PSRWLOCK))v9->Ptr + 2))(v9);
    }
    else
    {
      v10 = (__int64)v37;
      if ( v37 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 8LL))(v37);
      v11 = *v8;
      *v8 = v10;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v12 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
      if ( v9 )
        (*((void (__fastcall **)(PSRWLOCK))v9->Ptr + 2))(v9);
      v7 = 0;
    }
  }
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x354,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v7,
      v34);
    v30 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_53;
  }
  lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_::_lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_(v40, (char *)this - 40, &v44);
  v38 = 0;
  v13 = lambda_8cc2cbc74f704ed75a122f8fb45b3b71_::_lambda_8cc2cbc74f704ed75a122f8fb45b3b71_(
          (unsigned int)&v41,
          (unsigned int)pv,
          (int)this - 40,
          (unsigned int)&v38,
          (__int64)v40);
  v15 = CreationThreadDispatcher::RunSync__lambda_8cc2cbc74f704ed75a122f8fb45b3b71___(v14, v13);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x385,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v15,
      v35);
    Microsoft::WRL::ComPtr<CSystemVisuals>::InternalRelease(&v38);
    lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_::__lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_(v40);
    v32 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
LABEL_53:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    return (unsigned int)v7;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppv);
  v16 = SHGetPropertyStoreForWindow(*((HWND *)this - 2), &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x389,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v16,
      v35);
    v23 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v38;
    if ( v38 )
    {
      v38 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(v24);
    }
    lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_::__lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_(v40);
    v25 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_31;
  }
  v17 = ppv;
  v37 = ppv;
  Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v37);
  v41 = 31;
  v42 = pv[0];
  v18 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)v17 + 48LL))(
          v17,
          &PKEY_AppUserModel_ID,
          &v41);
  v7 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38E,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v18,
      v35);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v37);
    v20 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v38;
    if ( v38 )
    {
      v38 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(v21);
    }
    lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_::__lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_(v40);
    v22 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    goto LABEL_31;
  }
  LOBYTE(v19) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl'::`2'::impl,
    v19);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 96);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::operator=(v5, pv);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( *((RTL_SRWLOCK **)this + 13) != v38 )
  {
    SRWLock = v38;
    Microsoft::WRL::ComPtr<CSystemVisuals>::InternalAddRef(&SRWLock);
    SRWLock = (PSRWLOCK)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v33;
    Microsoft::WRL::ComPtr<CSystemVisuals>::InternalRelease(&SRWLock);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 19) + 272LL))(*((_QWORD *)this + 19), *v5, a3);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v37);
  v27 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v38;
  if ( v38 )
  {
    v38 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(v28);
  }
  lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_::__lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_(v40);
  v29 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return 0;
}

```

## disassembly

```asm
0x1800111d0  mov     [rsp-8+arg_8], rbx
0x1800111d5  push    rbp
0x1800111d6  push    rsi
0x1800111d7  push    rdi
0x1800111d8  push    r12
0x1800111da  push    r13
0x1800111dc  push    r14
0x1800111de  push    r15
0x1800111e0  lea     rbp, [rsp-27h]
0x1800111e5  sub     rsp, 90h
0x1800111ec  mov     r12d, r8d
0x1800111ef  mov     rsi, rcx
0x1800111f2  lea     r15, [rcx+0A0h]
0x1800111f9  xor     r13d, r13d
0x1800111fc  cmp     [r15], r13
0x1800111ff  jnz     loc_180011587
0x180011205  mov     [rbp+57h+pv], r13
0x180011209  mov     [rbp+57h+var_70], r13
0x18001120d  mov     [rbp+57h+var_68], r13
0x180011211  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011215  lea     rcx, [rbp+57h+pv]
0x180011219  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001121e  mov     ebx, eax
0x180011220  test    eax, eax
0x180011222  js      loc_1800115A9
0x180011228  mov     [rbp+57h+arg_0], r13
0x18001122c  lea     rax, [rbp+57h+arg_0]
0x180011230  mov     [rbp+57h+SRWLock], rax
0x180011234  lea     rcx, [rbp+57h+SRWLock]
0x180011238  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18001123d  mov     r14, rax
0x180011240  mov     [rbp+57h+SRWLock], r13
0x180011244  lea     rcx, [rsi-8]
0x180011248  lea     r8, [rbp+57h+SRWLock]
0x18001124c  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180011253  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180011258  mov     ebx, eax
0x18001125a  test    eax, eax
0x18001125c  js      loc_18001158E
0x180011262  mov     [rbp+57h+var_88], r13
0x180011266  mov     rdi, [rbp+57h+SRWLock]
0x18001126a  mov     rax, [rdi]
0x18001126d  lea     rdx, [rbp+57h+var_88]
0x180011271  mov     rcx, rdi
0x180011274  mov     rax, [rax+18h]
0x180011278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001127d  mov     ebx, eax
0x18001127f  test    eax, eax
0x180011281  js      loc_180011612
0x180011287  mov     rbx, [rbp+57h+var_88]
0x18001128b  test    rbx, rbx
0x18001128e  jz      short loc_1800112A0
0x180011290  mov     rax, [rbx]
0x180011293  mov     rcx, rbx
0x180011296  mov     rax, [rax+8]
0x18001129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129f  nop
0x1800112a0  mov     rcx, [r14]
0x1800112a3  mov     [r14], rbx
0x1800112a6  test    rcx, rcx
0x1800112a9  jz      short loc_1800112B8
0x1800112ab  mov     rax, [rcx]
0x1800112ae  mov     rax, [rax+10h]
0x1800112b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b7  nop
0x1800112b8  mov     rcx, [rbp+57h+var_88]
0x1800112bc  test    rcx, rcx
0x1800112bf  jz      short loc_1800112D2
0x1800112c1  mov     [rbp+57h+var_88], r13
0x1800112c5  mov     rax, [rcx]
0x1800112c8  mov     rax, [rax+10h]
0x1800112cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d1  nop
0x1800112d2  test    rdi, rdi
0x1800112d5  jz      short loc_1800112E7
0x1800112d7  mov     rax, [rdi]
0x1800112da  mov     rcx, rdi
0x1800112dd  mov     rax, [rax+10h]
0x1800112e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e6  nop
0x1800112e7  mov     ebx, r13d
0x1800112ea  test    ebx, ebx
0x1800112ec  js      loc_1800115D1
0x1800112f2  lea     r8, [rbp+57h+arg_0]
0x1800112f6  lea     rdx, [rsi-28h]
0x1800112fa  lea     rcx, [rbp+57h+var_60]
0x1800112fe  call    _lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_
0x180011303  nop
0x180011304  mov     [rbp+57h+var_80], r13
0x180011308  mov     r10, [rsi+70h]
0x18001130c  lea     rax, [rbp+57h+var_60]
0x180011310  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180011315  lea     r9, [rbp+57h+var_80]
0x180011319  lea     r8, [rsi-28h]
0x18001131d  lea     rdx, [rbp+57h+pv]
0x180011321  lea     rcx, [rbp+57h+var_50]
0x180011325  call    _lambda_8cc2cbc74f704ed75a122f8fb45b3b71____lambda_8cc2cbc74f704ed75a122f8fb45b3b71_
0x18001132a  mov     rdx, rax
0x18001132d  mov     rcx, r10
0x180011330  call    CreationThreadDispatcher__RunSync__lambda_8cc2cbc74f704ed75a122f8fb45b3b71___
0x180011335  mov     ebx, eax
0x180011337  test    eax, eax
0x180011339  js      loc_180011646
0x18001133f  mov     [rbp+57h+ppv], r13
0x180011343  lea     rcx, [rbp+57h+ppv]
0x180011347  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001134c  lea     r8, [rbp+57h+ppv]; ppv
0x180011350  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180011357  mov     rcx, [rsi-10h]; hwnd
0x18001135b  call    cs:__imp_SHGetPropertyStoreForWindow
0x180011361  mov     ebx, eax
0x180011363  test    eax, eax
0x180011365  js      loc_180011428
0x18001136b  mov     rbx, [rbp+57h+ppv]
0x18001136f  mov     [rbp+57h+var_88], rbx
0x180011373  lea     rcx, [rbp+57h+var_88]
0x180011377  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18001137c  nop
0x18001137d  mov     eax, 1Fh
0x180011382  mov     [rbp+57h+var_50], ax
0x180011386  mov     rax, [rbp+57h+pv]
0x18001138a  mov     [rbp+57h+var_48], rax
0x18001138e  mov     rax, [rbx]
0x180011391  lea     r8, [rbp+57h+var_50]
0x180011395  lea     rdx, PKEY_AppUserModel_ID
0x18001139c  mov     rcx, rbx
0x18001139f  mov     rax, [rax+30h]
0x1800113a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113a8  mov     ebx, eax
0x1800113aa  test    eax, eax
0x1800113ac  jns     loc_1800114BE
0x1800113b2  mov     rcx, [rbp+5Fh]; this
0x1800113b6  mov     r9d, eax; char *
0x1800113b9  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800113c0  mov     edx, 38Eh; void *
0x1800113c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113ca  nop
0x1800113cb  lea     rcx, [rbp+57h+var_88]
0x1800113cf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800113d4  nop
0x1800113d5  mov     rcx, [rbp+57h+ppv]
0x1800113d9  test    rcx, rcx
0x1800113dc  jz      short loc_1800113EF
0x1800113de  mov     [rbp+57h+ppv], r13
0x1800113e2  mov     rax, [rcx]
0x1800113e5  mov     rax, [rax+10h]
0x1800113e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ee  nop
0x1800113ef  mov     rcx, [rbp+57h+var_80]
0x1800113f3  test    rcx, rcx
0x1800113f6  jz      short loc_180011402
0x1800113f8  mov     [rbp+57h+var_80], r13
0x1800113fc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(void)
0x180011401  nop
0x180011402  lea     rcx, [rbp+57h+var_60]
0x180011406  call    _lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_
0x18001140b  nop
0x18001140c  mov     rcx, [rbp+57h+arg_0]
0x180011410  test    rcx, rcx
0x180011413  jz      short loc_180011426
0x180011415  mov     [rbp+57h+arg_0], r13
0x180011419  mov     rax, [rcx]
0x18001141c  mov     rax, [rax+10h]
0x180011420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011425  nop
0x180011426  jmp     short loc_180011492
0x180011428  mov     rcx, [rbp+5Fh]; this
0x18001142c  mov     r9d, ebx; char *
0x18001142f  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x180011436  mov     edx, 389h; void *
0x18001143b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011440  nop
0x180011441  mov     rcx, [rbp+57h+ppv]
0x180011445  test    rcx, rcx
0x180011448  jz      short loc_18001145B
0x18001144a  mov     [rbp+57h+ppv], r13
0x18001144e  mov     rax, [rcx]
0x180011451  mov     rax, [rax+10h]
0x180011455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145a  nop
0x18001145b  mov     rcx, [rbp+57h+var_80]
0x18001145f  test    rcx, rcx
0x180011462  jz      short loc_18001146E
0x180011464  mov     [rbp+57h+var_80], r13
0x180011468  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(void)
0x18001146d  nop
0x18001146e  lea     rcx, [rbp+57h+var_60]
0x180011472  call    _lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_
0x180011477  nop
0x180011478  mov     rcx, [rbp+57h+arg_0]
0x18001147c  test    rcx, rcx
0x18001147f  jz      short loc_180011492
0x180011481  mov     [rbp+57h+arg_0], r13
0x180011485  mov     rax, [rcx]
0x180011488  mov     rax, [rax+10h]
0x18001148c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011491  nop
0x180011492  mov     rcx, [rbp+57h+pv]; pv
0x180011496  test    rcx, rcx
0x180011499  jz      short loc_1800114A1
0x18001149b  call    cs:__imp_CoTaskMemFree
0x1800114a1  mov     eax, ebx
0x1800114a3  mov     rbx, [rsp+0C0h+arg_8]
0x1800114ab  add     rsp, 90h
0x1800114b2  pop     r15
0x1800114b4  pop     r14
0x1800114b6  pop     r13
0x1800114b8  pop     r12
0x1800114ba  pop     rdi
0x1800114bb  pop     rsi
0x1800114bc  pop     rbp
0x1800114bd  retn
0x1800114be  mov     dl, 1
0x1800114c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens> `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl(void)'::`2'::impl
0x1800114c7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800114cc  lea     rdx, [rsi+60h]
0x1800114d0  lea     rcx, [rbp+57h+SRWLock]
0x1800114d4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800114d9  lea     rdx, [rbp+57h+pv]
0x1800114dd  mov     rcx, r15
0x1800114e0  call    ??4?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAAEAV012@$$QEAV012@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::operator=(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &&)
0x1800114e5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800114e9  test    rcx, rcx
0x1800114ec  jnz     loc_1800115C6
0x1800114f2  mov     r8, [rbp+57h+var_80]
0x1800114f6  cmp     [rsi+68h], r8
0x1800114fa  jnz     loc_180011692
0x180011500  mov     rcx, [rsi+98h]
0x180011507  mov     rax, [rcx]
0x18001150a  mov     r8d, r12d
0x18001150d  mov     rdx, [r15]
0x180011510  mov     rax, [rax+110h]
0x180011517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001151c  nop
0x18001151d  lea     rcx, [rbp+57h+var_88]
0x180011521  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180011526  nop
0x180011527  mov     rcx, [rbp+57h+ppv]
0x18001152b  test    rcx, rcx
0x18001152e  jz      short loc_180011541
0x180011530  mov     [rbp+57h+ppv], r13
0x180011534  mov     rax, [rcx]
0x180011537  mov     rax, [rax+10h]
0x18001153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011540  nop
0x180011541  mov     rcx, [rbp+57h+var_80]
0x180011545  test    rcx, rcx
0x180011548  jz      short loc_180011554
0x18001154a  mov     [rbp+57h+var_80], r13
0x18001154e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase>::Release(void)
0x180011553  nop
0x180011554  lea     rcx, [rbp+57h+var_60]
0x180011558  call    _lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2_
0x18001155d  nop
0x18001155e  mov     rcx, [rbp+57h+arg_0]
0x180011562  test    rcx, rcx
0x180011565  jz      short loc_180011578
0x180011567  mov     [rbp+57h+arg_0], r13
0x18001156b  mov     rax, [rcx]
0x18001156e  mov     rax, [rax+10h]
0x180011572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011577  nop
0x180011578  mov     rcx, [rbp+57h+pv]; pv
0x18001157c  test    rcx, rcx
0x18001157f  jz      short loc_180011587
0x180011581  call    cs:__imp_CoTaskMemFree
0x180011587  xor     eax, eax
0x180011589  jmp     loc_1800114A3
0x18001158e  mov     rcx, [rbp+57h+SRWLock]
0x180011592  test    rcx, rcx
0x180011595  jz      short loc_1800115A4
0x180011597  mov     rdx, [rcx]
0x18001159a  mov     rax, [rdx+10h]
0x18001159e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115a3  nop
0x1800115a4  jmp     loc_1800112EA
0x1800115a9  mov     rcx, [rbp+5Fh]; this
0x1800115ad  mov     r9d, ebx; char *
0x1800115b0  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800115b7  mov     edx, 34Eh; void *
0x1800115bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115c1  jmp     loc_180011492
0x1800115c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800115cc  jmp     loc_1800114F2
0x1800115d1  mov     rcx, [rbp+5Fh]; this
0x1800115d5  mov     r9d, ebx; char *
0x1800115d8  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x1800115df  mov     edx, 354h; void *
0x1800115e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115e9  nop
0x1800115ea  mov     rcx, [rbp+57h+arg_0]
0x1800115ee  test    rcx, rcx
0x1800115f1  jz      short loc_180011604
0x1800115f3  mov     [rbp+57h+arg_0], r13
0x1800115f7  mov     rax, [rcx]
0x1800115fa  mov     rax, [rax+10h]
0x1800115fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011603  nop
0x180011604  lea     rcx, [rbp+57h+pv]
0x180011608  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```
