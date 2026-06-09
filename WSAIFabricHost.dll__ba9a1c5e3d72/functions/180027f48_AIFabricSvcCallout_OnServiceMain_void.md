# AIFabricSvcCallout::OnServiceMain(void)

- ea: `0x180027f48`
- end: `0x180028744`
- name: `?OnServiceMain@AIFabricSvcCallout@@QEAAXXZ`
- size: `2044`
- prototype: `void __fastcall(AIFabricSvcCallout *this, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800198c8`

## callees

- `0x180004ca0`
- `0x180007ad0`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180013930`
- `0x180019c3c`
- `0x180023e9c`
- `0x180026f94`
- `0x1800270a8`
- `0x180027f48`
- `0x1800287f0`
- `0x180028c74`
- `0x180029308`
- `0x180029524`
- `0x1800295c4`
- `0x1800296a4`
- `0x1800296e4`
- `0x180029784`
- `0x180029824`
- `0x1800298c4`
- `0x180029964`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800286fa`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800286fa`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002801b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800282a1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800285f4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002801b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800282a1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800285f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002840e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002840e`
- `msvcp_win!_Thrd_detach` at `0x180028042`
- `msvcp_win!_Thrd_detach` at `0x1800282d0`
- `msvcp_win!_Thrd_detach` at `0x180028623`
- `msvcp_win!_Thrd_detach` at `0x180028042`
- `msvcp_win!_Thrd_detach` at `0x1800282d0`
- `msvcp_win!_Thrd_detach` at `0x180028623`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028050`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002807f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028090`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800282e3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028570`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028581`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028632`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028706`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028717`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028050`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002807f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028090`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800282e3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028570`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028581`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028632`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028706`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180028717`

## pseudocode

```c
void __fastcall AIFabricSvcCallout::OnServiceMain(AIFabricSvcCallout *this, unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx
  const char *v4; // r9
  AIFabricSvcCallout *v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  _QWORD *v10; // rcx
  volatile signed __int32 *v11; // rdi
  AIFabricSvcCallout *v12; // rax
  AIFabricSvcCallout *v13; // r12
  char *v14; // r15
  void *Hnd; // rax
  void (__fastcall ***v16)(_QWORD, __int64); // r13
  DWORD LastError; // ebx
  _QWORD *v18; // rax
  unsigned int v19; // edx
  struct winrt::impl::shared_hstring_header *v20; // rbx
  __int64 v21; // rdx
  signed __int32 v22; // eax
  signed __int32 v23; // ett
  _QWORD *v24; // rcx
  AIFabricSvcCallout *v25; // rax
  AIFabricSvcCallout *v26; // r12
  char *v27; // r15
  void *v28; // rax
  void (__fastcall ***v29)(_QWORD, __int64); // r13
  DWORD v30; // ebx
  AIFabricSvcCallout *v31; // rdi
  __int64 *v32; // rbx
  __int64 v33; // rcx
  _DWORD *v34; // rdi
  __int64 v35; // rcx
  int v36; // eax
  _QWORD *v37; // rax
  AIFabricSvcCallout *v38; // rdi
  __int64 *v39; // rbx
  __int64 v40; // rcx
  _DWORD *v41; // rdi
  __int64 v42; // rcx
  int v43; // eax
  _Thrd_t v44; // [rsp+30h] [rbp-108h] BYREF
  _Thrd_t v45; // [rsp+40h] [rbp-F8h] BYREF
  _Thrd_t v46; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v47[24]; // [rsp+60h] [rbp-D8h] BYREF
  char v48[8]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 (__fastcall **v49)(void *); // [rsp+88h] [rbp-B0h] BYREF
  _QWORD *v50; // [rsp+90h] [rbp-A8h]
  volatile signed __int32 *v51; // [rsp+98h] [rbp-A0h]
  __int64 (__fastcall ***v52)(void *); // [rsp+F0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x27, a2);
    memcpy_s((char *)v3 + 28, 0x4Eu, L"WindowsWorkload.Manager.1_8wekyb3d8bbwe", 0x4Eu);
    v45._Hnd = v3;
    if ( !(unsigned __int8)Utils::IsPackageRegistered(&v45) )
      return;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2));
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55993470>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55993470>::GetImpl'::`2'::impl) )
      goto LABEL_46;
    if ( AIFabricSvcCallout::IsInitialInstance(v5) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60475050>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60475050>::GetImpl'::`2'::impl) )
        goto LABEL_11;
      v6 = operator new(8u);
      *v6 = this;
      v46._Hnd = v6;
      v44._Hnd = (void *)_o__beginthreadex(
                           0,
                           0,
                           std::thread::_Invoke_std::tuple__lambda_3eeb51369deafe843a01f16d8fac8e9f____0_,
                           v6,
                           0,
                           &v44._Id);
      if ( v44._Hnd )
      {
        if ( v44._Id )
        {
          v46 = v44;
          if ( _Thrd_detach(&v46) )
            std::_Throw_Cpp_error(1);
          v44 = 0;
LABEL_11:
          v44 = 0;
          v7 = *((_QWORD *)this + 1);
          if ( v7 )
          {
            v8 = *(_DWORD *)(v7 + 8);
            do
            {
              if ( !v8 )
                goto LABEL_100;
LABEL_15:
              v9 = v8;
              v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
            }
            while ( v9 != v8 );
            v10 = *(_QWORD **)this;
            v44._Hnd = *(void **)this;
            v11 = (volatile signed __int32 *)*((_QWORD *)this + 1);
            *(_QWORD *)&v44._Id = v11;
            if ( v11 )
              _InterlockedIncrement(v11 + 2);
            v45 = v44;
            if ( v11 )
              _InterlockedIncrement(v11 + 2);
            v49 = &off_18008A890;
            v50 = v10;
            v51 = v11;
            v52 = &v49;
            v12 = (AIFabricSvcCallout *)wil::make_wnf_subscription<wil::details::empty_wnf_state>(
                                          &v46,
                                          &off_18008A890,
                                          v48);
            v13 = v12;
            v14 = (char *)this + 32;
            if ( (AIFabricSvcCallout *)((char *)this + 32) != v12 )
            {
              Hnd = *(void **)v12;
              v45._Hnd = Hnd;
              v16 = *(void (__fastcall ****)(_QWORD, __int64))v14;
              if ( *(_QWORD *)v14 )
              {
                LastError = GetLastError();
                (**v16)(v16, 1);
                SetLastError(LastError);
                Hnd = v45._Hnd;
              }
              *(_QWORD *)v14 = Hnd;
              *(_QWORD *)v13 = 0;
            }
            if ( v46._Hnd )
              (**(void (__fastcall ***)(void *, __int64))v46._Hnd)(v46._Hnd, 1);
            if ( v52 )
              (*v52)[3](v52);
            if ( v11 )
            {
              if ( !_InterlockedDecrement(v11 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
                if ( !_InterlockedDecrement(v11 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
              }
            }
LABEL_34:
            if ( v11 )
            {
              if ( !_InterlockedDecrement(v11 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
                if ( !_InterlockedDecrement(v11 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
              }
            }
            goto LABEL_38;
          }
LABEL_100:
          std::_Throw_bad_weak_ptr();
        }
        std::_Throw_Cpp_error(1);
      }
      v44._Id = 0;
      std::_Throw_Cpp_error(6);
      goto LABEL_15;
    }
    while ( 1 )
    {
LABEL_38:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311334>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56311334>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52536226>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52536226>::GetImpl'::`2'::impl) )
          return;
        v37 = operator new(8u);
        *v37 = this;
        v46._Hnd = v37;
        v44._Hnd = (void *)_o__beginthreadex(
                             0,
                             0,
                             std::thread::_Invoke_std::tuple__lambda_efb9f773e4ce6c501135c4829312431f____0_,
                             v37,
                             0,
                             &v44._Id);
        if ( v44._Hnd )
        {
          if ( v44._Id )
          {
            v46 = v44;
            if ( _Thrd_detach(&v46) )
              std::_Throw_Cpp_error(1);
            v44 = 0;
            AIFabricSvcCallout::StartListeningForNpuDriverUpdates(this);
            v38 = (AIFabricSvcCallout *)winrt::Windows::ApplicationModel::PackageCatalog::OpenForCurrentUser();
            v39 = (__int64 *)((char *)this + 56);
            if ( (AIFabricSvcCallout *)((char *)this + 56) != v38 )
            {
              if ( *v39 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref((char *)this + 56);
              v40 = *(_QWORD *)v38;
              *(_QWORD *)v38 = 0;
              *v39 = v40;
            }
            if ( v45._Hnd )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
            v41 = operator new(0x18u);
            v41[2] = 1;
            *((_QWORD *)v41 + 2) = this;
            winrt::impl::module_lock_updater<1>::module_lock_updater<1>(v41 + 6);
            *(_QWORD *)v41 = off_18008A828;
            v45._Hnd = v41;
            v46._Hnd = 0;
            v42 = *v39;
            *(_DWORD *)v47 = 0;
            *(_OWORD *)&v47[8] = 0;
            v43 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _Thrd_t *))(*(_QWORD *)v42 + 80LL))(v42, v41, &v46);
            if ( v43 < 0 )
              winrt::throw_hresult((unsigned int)v43, v47);
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
            if ( !v44._Id )
              return;
            _o_terminate();
          }
          std::_Throw_Cpp_error(1);
        }
        v44._Id = 0;
        std::_Throw_Cpp_error(6);
        goto LABEL_100;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58010279>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58010279>::GetImpl'::`2'::impl) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57170203>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57170203>::GetImpl'::`2'::impl) )
        break;
      v18 = operator new(8u);
      *v18 = this;
      v46._Hnd = v18;
      v44._Hnd = (void *)_o__beginthreadex(
                           0,
                           0,
                           std::thread::_Invoke_std::tuple__lambda_bb3611a6fe7ecd21ebec0e75a2ed1e75____0_,
                           v18,
                           0,
                           &v44._Id);
      if ( !v44._Hnd )
        goto LABEL_82;
      if ( !v44._Id )
      {
        std::_Throw_Cpp_error(1);
LABEL_82:
        v44._Id = 0;
        std::_Throw_Cpp_error(6);
LABEL_83:
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
        return;
      }
      v46 = v44;
      if ( !_Thrd_detach(&v46) )
        break;
      std::_Throw_Cpp_error(1);
LABEL_46:
      if ( AIFabricSvcCallout::IsInitialInstance(v5) )
      {
        v20 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x31, v19);
        memcpy_s((char *)v20 + 28, 0x62u, L"WindowsWorkload.LanguageModel.Qnn.1_8wekyb3d8bbwe", 0x62u);
        v45._Hnd = v20;
        if ( (unsigned __int8)Utils::IsPackageRegistered(&v45) )
        {
          v44 = 0;
          v21 = *((_QWORD *)this + 1);
          if ( !v21 )
LABEL_101:
            std::_Throw_bad_weak_ptr();
          v22 = *(_DWORD *)(v21 + 8);
          do
          {
            if ( !v22 )
              goto LABEL_101;
            v23 = v22;
            v22 = _InterlockedCompareExchange((volatile signed __int32 *)(v21 + 8), v22 + 1, v22);
          }
          while ( v23 != v22 );
          v24 = *(_QWORD **)this;
          v44 = *(_Thrd_t *)this;
          v11 = *(volatile signed __int32 **)&v44._Id;
          if ( *(_QWORD *)&v44._Id )
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v44._Id + 8LL));
          *(_Thrd_t *)v47 = v44;
          if ( v11 )
            _InterlockedIncrement(v11 + 2);
          v49 = &off_18008A868;
          v50 = v24;
          v51 = v11;
          v52 = &v49;
          v25 = (AIFabricSvcCallout *)wil::make_wnf_subscription<wil::details::empty_wnf_state>(
                                        &v45,
                                        &off_18008A868,
                                        v48);
          v26 = v25;
          v27 = (char *)this + 32;
          if ( (AIFabricSvcCallout *)((char *)this + 32) != v25 )
          {
            v28 = *(void **)v25;
            v46._Hnd = v28;
            v29 = *(void (__fastcall ****)(_QWORD, __int64))v27;
            if ( *(_QWORD *)v27 )
            {
              v30 = GetLastError();
              (**v29)(v29, 1);
              SetLastError(v30);
              v28 = v46._Hnd;
            }
            *(_QWORD *)v27 = v28;
            *(_QWORD *)v26 = 0;
          }
          if ( v45._Hnd )
            (**(void (__fastcall ***)(void *, __int64))v45._Hnd)(v45._Hnd, 1);
          if ( v52 )
            (*v52)[3](v52);
          if ( v11 && !_InterlockedDecrement(v11 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( !_InterlockedDecrement(v11 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
          goto LABEL_34;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57174164>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57174164>::GetImpl'::`2'::impl) )
      AIFabricSvcCallout::StartListeningForNpuDriverUpdates(this);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57170240>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57170240>::GetImpl'::`2'::impl) )
    {
      v31 = (AIFabricSvcCallout *)winrt::Windows::ApplicationModel::PackageCatalog::OpenForCurrentUser();
      v32 = (__int64 *)((char *)this + 56);
      if ( (AIFabricSvcCallout *)((char *)this + 56) != v31 )
      {
        if ( *v32 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref((char *)this + 56);
        v33 = *(_QWORD *)v31;
        *(_QWORD *)v31 = 0;
        *v32 = v33;
      }
      if ( v45._Hnd )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
      v34 = operator new(0x18u);
      v34[2] = 1;
      *((_QWORD *)v34 + 2) = this;
      winrt::impl::module_lock_updater<1>::module_lock_updater<1>(v34 + 6);
      *(_QWORD *)v34 = off_18008A848;
      v45._Hnd = v34;
      v46._Hnd = 0;
      v35 = *v32;
      *(_DWORD *)v47 = 0;
      *(_OWORD *)&v47[8] = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _Thrd_t *))(*(_QWORD *)v35 + 48LL))(v35, v34, &v46);
      if ( v36 < 0 )
        winrt::throw_hresult((unsigned int)v36, v47);
      goto LABEL_83;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricsvccallout.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x180027f48  push    rbx
0x180027f4a  push    rdi
0x180027f4b  push    r12
0x180027f4d  push    r13
0x180027f4f  push    r14
0x180027f51  push    r15
0x180027f53  sub     rsp, 108h
0x180027f5a  mov     rax, cs:__security_cookie
0x180027f61  xor     rax, rsp
0x180027f64  mov     [rsp+138h+var_40], rax
0x180027f6c  mov     r14, rcx
0x180027f6f  xor     r15d, r15d
0x180027f72  lea     ecx, [r15+27h]; this
0x180027f76  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180027f7b  mov     rbx, rax
0x180027f7e  lea     rcx, [rax+1Ch]; Destination
0x180027f82  lea     edx, [r15+4Eh]; DestinationSize
0x180027f86  mov     r9d, edx; SourceSize
0x180027f89  lea     r8, aWindowsworkloa_1; "WindowsWorkload.Manager.1_8wekyb3d8bbwe"
0x180027f90  call    memcpy_s
0x180027f95  mov     qword ptr [rsp+138h+var_F8], rbx
0x180027f9a  lea     rcx, [rsp+138h+var_F8]
0x180027f9f  call    ?IsPackageRegistered@Utils@@YA_NUhstring@winrt@@@Z; Utils::IsPackageRegistered(winrt::hstring)
0x180027fa4  test    al, al
0x180027fa6  jz      loc_180028593
0x180027fac  mov     rcx, [r14+10h]
0x180027fb0  mov     rax, [rcx]
0x180027fb3  mov     rax, [rax+48h]
0x180027fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fbc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55993470@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55993470@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55993470> `wil::Feature<__WilFeatureTraits_Feature_55993470>::GetImpl(void)'::`2'::impl
0x180027fc3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55993470@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55993470>::__private_IsEnabled(void)
0x180027fc8  test    al, al
0x180027fca  jz      loc_1800282EA
0x180027fd0  call    ?IsInitialInstance@AIFabricSvcCallout@@AEAA_NXZ; AIFabricSvcCallout::IsInitialInstance(void)
0x180027fd5  test    al, al
0x180027fd7  jz      loc_18002821A
0x180027fdd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60475050@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60475050@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60475050> `wil::Feature<__WilFeatureTraits_Feature_60475050>::GetImpl(void)'::`2'::impl
0x180027fe4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60475050@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60475050>::__private_IsEnabled(void)
0x180027fe9  test    al, al
0x180027feb  jnz     short loc_18002805F
0x180027fed  lea     ecx, [r15+8]; Size
0x180027ff1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027ff6  mov     [rax], r14
0x180027ff9  mov     [rsp+138h+var_E8._Hnd], rax
0x180027ffe  lea     rcx, [rsp+138h+var_108+8]
0x180028003  mov     [rsp+138h+var_110], rcx
0x180028008  mov     [rsp+138h+var_118], r15d
0x18002800d  mov     r9, rax
0x180028010  lea     r8, std__thread___Invoke_std__tuple__lambda_3eeb51369deafe843a01f16d8fac8e9f____0_
0x180028017  xor     edx, edx
0x180028019  xor     ecx, ecx
0x18002801b  call    cs:__imp__o__beginthreadex
0x180028021  mov     qword ptr [rsp+138h+var_108], rax
0x180028026  test    rax, rax
0x180028029  jz      short loc_180028086
0x18002802b  cmp     dword ptr [rsp+138h+var_108+8], r15d
0x180028030  jz      short loc_18002807A
0x180028032  movaps  xmm0, [rsp+138h+var_108]
0x180028037  movdqa  xmmword ptr [rsp+138h+var_E8._Hnd], xmm0
0x18002803d  lea     rcx, [rsp+138h+var_E8]; _Thrd_t
0x180028042  call    cs:__imp__Thrd_detach
0x180028048  test    eax, eax
0x18002804a  jz      short loc_180028056
0x18002804c  lea     ecx, [r15+1]
0x180028050  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180028056  xorps   xmm0, xmm0
0x180028059  movdqa  [rsp+138h+var_108], xmm0
0x18002805f  xorps   xmm0, xmm0
0x180028062  movdqa  [rsp+138h+var_108], xmm0
0x180028068  mov     rdx, [r14+8]
0x18002806c  test    rdx, rdx
0x18002806f  jz      loc_18002871E
0x180028075  mov     eax, [rdx+8]
0x180028078  jmp     short loc_1800280A1
0x18002807a  mov     ecx, 1
0x18002807f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180028085  nop
0x180028086  mov     dword ptr [rsp+138h+var_108+8], r15d
0x18002808b  mov     ecx, 6
0x180028090  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180028096  nop
0x180028097  lea     ecx, [rax+1]
0x18002809a  lock cmpxchg [rdx+8], ecx
0x18002809f  jz      short loc_1800280AB
0x1800280a1  test    eax, eax
0x1800280a3  jz      loc_18002871E
0x1800280a9  jmp     short loc_180028097
0x1800280ab  mov     rcx, [r14]
0x1800280ae  mov     qword ptr [rsp+138h+var_108], rcx
0x1800280b3  mov     rdi, [r14+8]
0x1800280b7  mov     qword ptr [rsp+138h+var_108+8], rdi
0x1800280bc  test    rdi, rdi
0x1800280bf  jz      short loc_1800280C5
0x1800280c1  lock inc dword ptr [rdi+8]
0x1800280c5  movaps  xmm0, [rsp+138h+var_108]
0x1800280ca  movdqa  [rsp+138h+var_F8], xmm0
0x1800280d0  mov     rax, rdi
0x1800280d3  test    rdi, rdi
0x1800280d6  jz      short loc_1800280DC
0x1800280d8  lock inc dword ptr [rdi+8]
0x1800280dc  lea     rdx, off_18008A890
0x1800280e3  mov     [rsp+138h+var_B0], rdx
0x1800280eb  mov     [rsp+138h+var_A8], rcx
0x1800280f3  mov     [rsp+138h+var_A0], rax
0x1800280fb  lea     rax, [rsp+138h+var_B0]
0x180028103  mov     [rsp+138h+var_48], rax
0x18002810b  lea     r8, [rsp+138h+var_B8]
0x180028113  lea     rcx, [rsp+138h+var_E8]
0x180028118  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18002811d  mov     r12, rax
0x180028120  lea     r15, [r14+20h]
0x180028124  cmp     r15, rax
0x180028127  jz      short loc_18002816E
0x180028129  mov     rax, [rax]
0x18002812c  mov     qword ptr [rsp+138h+var_F8], rax
0x180028131  mov     r13, [r15]
0x180028134  test    r13, r13
0x180028137  jz      short loc_180028162
0x180028139  call    cs:__imp_GetLastError
0x18002813f  mov     ebx, eax
0x180028141  mov     rdx, [r13+0]
0x180028145  mov     rax, [rdx]
0x180028148  mov     edx, 1
0x18002814d  mov     rcx, r13
0x180028150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028155  mov     ecx, ebx; dwErrCode
0x180028157  call    cs:__imp_SetLastError
0x18002815d  mov     rax, qword ptr [rsp+138h+var_F8]
0x180028162  mov     [r15], rax
0x180028165  xor     r15d, r15d
0x180028168  mov     [r12], r15
0x18002816c  jmp     short loc_180028171
0x18002816e  xor     r15d, r15d
0x180028171  mov     rcx, [rsp+138h+var_E8._Hnd]
0x180028176  test    rcx, rcx
0x180028179  jz      short loc_18002818C
0x18002817b  mov     rax, [rcx]
0x18002817e  mov     edx, 1
0x180028183  mov     rax, [rax]
0x180028186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002818b  nop
0x18002818c  mov     rcx, [rsp+138h+var_48]
0x180028194  test    rcx, rcx
0x180028197  jz      short loc_1800281A6
0x180028199  mov     rax, [rcx]
0x18002819c  mov     rax, [rax+18h]
0x1800281a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281a5  nop
0x1800281a6  or      ebx, 0FFFFFFFFh
0x1800281a9  test    rdi, rdi
0x1800281ac  jz      short loc_1800281E2
0x1800281ae  mov     eax, ebx
0x1800281b0  lock xadd [rdi+8], eax
0x1800281b5  add     eax, ebx
0x1800281b7  jnz     short loc_1800281E2
0x1800281b9  mov     rax, [rdi]
0x1800281bc  mov     rcx, rdi
0x1800281bf  mov     rax, [rax]
0x1800281c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281c7  mov     eax, ebx
0x1800281c9  lock xadd [rdi+0Ch], eax
0x1800281ce  add     eax, ebx
0x1800281d0  jnz     short loc_1800281E2
0x1800281d2  mov     rax, [rdi]
0x1800281d5  mov     rcx, rdi
0x1800281d8  mov     rax, [rax+8]
0x1800281dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e1  nop
0x1800281e2  test    rdi, rdi
0x1800281e5  jz      short loc_18002821A
0x1800281e7  mov     eax, ebx
0x1800281e9  lock xadd [rdi+8], eax
0x1800281ee  add     eax, ebx
0x1800281f0  jnz     short loc_18002821A
0x1800281f2  mov     rax, [rdi]
0x1800281f5  mov     rcx, rdi
0x1800281f8  mov     rax, [rax]
0x1800281fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028200  mov     eax, ebx
0x180028202  lock xadd [rdi+0Ch], eax
0x180028207  add     eax, ebx
0x180028209  jnz     short loc_18002821A
0x18002820b  mov     rax, [rdi]
0x18002820e  mov     rcx, rdi
0x180028211  mov     rax, [rax+8]
0x180028215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002821a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56311334@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56311334@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311334> `wil::Feature<__WilFeatureTraits_Feature_56311334>::GetImpl(void)'::`2'::impl
0x180028221  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56311334@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311334>::__private_IsEnabled(void)
0x180028226  test    al, al
0x180028228  jz      loc_1800285B5
0x18002822e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58010279@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58010279@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58010279> `wil::Feature<__WilFeatureTraits_Feature_58010279>::GetImpl(void)'::`2'::impl
0x180028235  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58010279@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58010279>::__private_IsEnabled(void)
0x18002823a  test    al, al
0x18002823c  jnz     short loc_18002825E
0x18002823e  mov     rcx, [r14+10h]
0x180028242  mov     rax, [rcx]
0x180028245  mov     rax, [rax+48h]
0x180028249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002824e  mov     rcx, [r14+10h]
0x180028252  mov     rax, [rcx]
0x180028255  mov     rax, [rax+40h]
0x180028259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002825e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57170203@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57170203@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57170203> `wil::Feature<__WilFeatureTraits_Feature_57170203>::GetImpl(void)'::`2'::impl
0x180028265  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57170203@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57170203>::__private_IsEnabled(void)
0x18002826a  test    al, al
0x18002826c  jz      loc_18002849E
0x180028272  mov     ecx, 8; Size
0x180028277  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002827c  mov     [rax], r14
0x18002827f  mov     [rsp+138h+var_E8._Hnd], rax
0x180028284  lea     rcx, [rsp+138h+var_108+8]
0x180028289  mov     [rsp+138h+var_110], rcx
0x18002828e  mov     [rsp+138h+var_118], r15d
0x180028293  mov     r9, rax
0x180028296  lea     r8, std__thread___Invoke_std__tuple__lambda_bb3611a6fe7ecd21ebec0e75a2ed1e75____0_
0x18002829d  xor     edx, edx
0x18002829f  xor     ecx, ecx
0x1800282a1  call    cs:__imp__o__beginthreadex
0x1800282a7  mov     qword ptr [rsp+138h+var_108], rax
0x1800282ac  test    rax, rax
0x1800282af  jz      loc_180028577
0x1800282b5  cmp     dword ptr [rsp+138h+var_108+8], r15d
0x1800282ba  jz      loc_18002856B
0x1800282c0  movaps  xmm0, [rsp+138h+var_108]
0x1800282c5  movdqa  xmmword ptr [rsp+138h+var_E8._Hnd], xmm0
0x1800282cb  lea     rcx, [rsp+138h+var_E8]; _Thrd_t
0x1800282d0  call    cs:__imp__Thrd_detach
0x1800282d6  test    eax, eax
0x1800282d8  jz      loc_18002849E
0x1800282de  mov     ecx, 1
0x1800282e3  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800282e9  nop
0x1800282ea  call    ?IsInitialInstance@AIFabricSvcCallout@@AEAA_NXZ; AIFabricSvcCallout::IsInitialInstance(void)
0x1800282ef  test    al, al
0x1800282f1  jz      loc_18002821A
0x1800282f7  mov     ecx, 31h ; '1'; this
0x1800282fc  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180028301  mov     rbx, rax
0x180028304  lea     rcx, [rax+1Ch]; Destination
0x180028308  mov     edx, 62h ; 'b'; DestinationSize
0x18002830d  mov     r9d, edx; SourceSize
0x180028310  lea     r8, aWindowsworkloa; "WindowsWorkload.LanguageModel.Qnn.1_8we"...
0x180028317  call    memcpy_s
0x18002831c  mov     qword ptr [rsp+138h+var_F8], rbx
0x180028321  lea     rcx, [rsp+138h+var_F8]
0x180028326  call    ?IsPackageRegistered@Utils@@YA_NUhstring@winrt@@@Z; Utils::IsPackageRegistered(winrt::hstring)
0x18002832b  test    al, al
0x18002832d  jz      loc_18002821A
0x180028333  xorps   xmm0, xmm0
0x180028336  movdqa  [rsp+138h+var_108], xmm0
0x18002833c  mov     rdx, [r14+8]
0x180028340  test    rdx, rdx
0x180028343  jz      loc_180028723
0x180028349  mov     eax, [rdx+8]
0x18002834c  jmp     short loc_180028358
0x18002834e  lea     ecx, [rax+1]
0x180028351  lock cmpxchg [rdx+8], ecx
0x180028356  jz      short loc_180028362
0x180028358  test    eax, eax
0x18002835a  jz      loc_180028723
0x180028360  jmp     short loc_18002834E
0x180028362  mov     rcx, [r14]
0x180028365  mov     qword ptr [rsp+138h+var_108], rcx
0x18002836a  mov     rdi, [r14+8]
0x18002836e  mov     qword ptr [rsp+138h+var_108+8], rdi
0x180028373  test    rdi, rdi
0x180028376  jz      short loc_18002837C
0x180028378  lock inc dword ptr [rdi+8]
0x18002837c  movaps  xmm0, [rsp+138h+var_108]
0x180028381  movdqa  [rsp+138h+var_D8], xmm0
0x180028387  mov     rax, rdi
0x18002838a  test    rdi, rdi
0x18002838d  jz      short loc_180028393
0x18002838f  lock inc dword ptr [rdi+8]
0x180028393  lea     rdx, off_18008A868
0x18002839a  mov     [rsp+138h+var_B0], rdx
0x1800283a2  mov     [rsp+138h+var_A8], rcx
0x1800283aa  mov     [rsp+138h+var_A0], rax
0x1800283b2  lea     rax, [rsp+138h+var_B0]
0x1800283ba  mov     [rsp+138h+var_48], rax
0x1800283c2  lea     r8, [rsp+138h+var_B8]
0x1800283ca  lea     rcx, [rsp+138h+var_F8]
0x1800283cf  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x1800283d4  mov     r12, rax
0x1800283d7  lea     r15, [r14+20h]
0x1800283db  cmp     r15, rax
0x1800283de  jz      short loc_180028425
0x1800283e0  mov     rax, [rax]
0x1800283e3  mov     [rsp+138h+var_E8._Hnd], rax
0x1800283e8  mov     r13, [r15]
0x1800283eb  test    r13, r13
0x1800283ee  jz      short loc_180028419
0x1800283f0  call    cs:__imp_GetLastError
0x1800283f6  mov     ebx, eax
0x1800283f8  mov     rdx, [r13+0]
0x1800283fc  mov     rax, [rdx]
0x1800283ff  mov     edx, 1
0x180028404  mov     rcx, r13
0x180028407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002840c  mov     ecx, ebx; dwErrCode
  ... truncated ...
```
