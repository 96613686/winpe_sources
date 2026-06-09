# ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder>::Get(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &)

- ea: `0x180021e54`
- end: `0x1800222ab`
- name: `?Get@?$ComStaticStoreSingleton@U_ActiveMediaAppManagerSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@@Z`
- size: `1111`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021db8`

## callees

- `0x18000d11c`
- `0x180010a90`
- `0x1800214e0`
- `0x180021e54`
- `0x1800222b4`
- `0x180022520`
- `0x180022a6c`
- `0x180022b28`
- `0x180022bdc`
- `0x18006baa4`
- `0x180087e80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ee3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ee3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ef0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021e80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021e80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021ef9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800220cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800220cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021ff6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022046`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021ff6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021fe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021fe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022030`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022061`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022061`

## string_xrefs

- `0x180021f91`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x180022078`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x180022116`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x180022180`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder>::Get(__int64 a1, _QWORD *a2)
{
  int ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  HRESULT v7; // eax
  HRESULT v8; // eax
  int ActivationFactory; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, std::_Ref_count_base **); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  volatile signed __int32 *v18; // rax
  __int64 v19; // rcx
  std::_Ref_count_base *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  std::_Ref_count_base *v24; // rcx
  int v25; // [rsp+20h] [rbp-C8h]
  _BYTE v26[8]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+50h] [rbp-98h] BYREF
  std::_Ref_count_base *v31[2]; // [rsp+60h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-78h] BYREF
  HSTRING string; // [rsp+88h] [rbp-60h] BYREF
  HSTRING_HEADER v34; // [rsp+90h] [rbp-58h] BYREF
  HSTRING v35; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  AcquireSRWLockShared(&ActiveMediaAppManagerSingleton);
  *(_OWORD *)v31 = 0;
  if ( qword_1801903B0 && std::_Ref_count_base::_Incref_nz(qword_1801903B0) )
  {
    v31[0] = (std::_Ref_count_base *)qword_1801903A8;
    v31[1] = qword_1801903B0;
  }
  std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(a2, v31);
  if ( v31[1] )
    std::_Ref_count_base::_Decref(v31[1]);
  if ( *a2 )
  {
    ReleaseSRWLockShared(&ActiveMediaAppManagerSingleton);
    return 0;
  }
  ReleaseSRWLockShared(&ActiveMediaAppManagerSingleton);
  AcquireSRWLockExclusive(&ActiveMediaAppManagerSingleton);
  v31[0] = (std::_Ref_count_base *)&ActiveMediaAppManagerSingleton;
  *(_OWORD *)v30 = 0;
  if ( qword_1801903B0 && std::_Ref_count_base::_Incref_nz(qword_1801903B0) )
  {
    v30[0] = (std::_Ref_count_base *)qword_1801903A8;
    v30[1] = qword_1801903B0;
  }
  std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(a2, v30);
  if ( v30[1] )
    std::_Ref_count_base::_Decref(v30[1]);
  if ( *a2 )
  {
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
    return 0;
  }
  v27 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
  try
  {
    ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z = ___MakeAndInitialize_UInspectableContainer__1__Get___ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z_U1_1__23_QEAAJ0_Z___V_Details_WRL_Microsoft__YAJPEAPEAUInspectableContainer__1__Get___ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z(&v27);
  }
  catch ( ... )
  {
    LODWORD(v28) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x34,
                     (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
                     v5);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
    return (unsigned int)v28;
  }
  v6 = ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z;
  if ( ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z >= 0 )
  {
    string = 0;
    v7 = WindowsCreateStringReference(
           L"Windows::Media::Internal::ActiveMediaAppManager",
           0x2Fu,
           &hstringHeader,
           &string);
    if ( v7 < 0 )
      RaiseException(v7, 1u, 0, 0);
    v28 = 0;
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
    v35 = 0;
    v8 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &v34, &v35);
    if ( v8 < 0 )
    {
      RaiseException(v8, 1u, 0, 0);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(v35, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, &v28);
    v10 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v30[0] = 0;
      v13 = v28;
      v14 = *(__int64 (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)v28 + 56LL);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v30);
      v15 = v14(v13, v30);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v29 = 0;
        v16 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                v30,
                &v29);
        v10 = v16;
        if ( v16 >= 0 )
        {
          v26[0] = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v29 + 80LL))(
                  v29,
                  string,
                  v27,
                  v26);
          v10 = v16;
          if ( v16 >= 0 )
          {
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v30);
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
            v18 = *(volatile signed __int32 **)(v27 + 40);
            if ( v18 )
            {
              v19 = *(_QWORD *)(v27 + 32);
              _InterlockedIncrement(v18 + 3);
            }
            else
            {
              v18 = 0;
              v19 = 0;
            }
            qword_1801903A8 = v19;
            v20 = qword_1801903B0;
            qword_1801903B0 = (std::_Ref_count_base *)v18;
            if ( v20 )
              std::_Ref_count_base::_Decwref(v20);
            v21 = v27;
            v22 = *(_QWORD *)(v27 + 40);
            if ( v22 )
              _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
            v23 = *(_QWORD *)(v21 + 40);
            *a2 = *(_QWORD *)(v21 + 32);
            v24 = (std::_Ref_count_base *)a2[1];
            a2[1] = v23;
            if ( v24 )
              std::_Ref_count_base::_Decref(v24);
            Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
            goto LABEL_15;
          }
          v17 = 70;
        }
        else
        {
          v17 = 67;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
          (const char *)(unsigned int)v16,
          v25);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
          (const char *)(unsigned int)v15,
          v25);
      }
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v30);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
      string = 0;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
        (const char *)(unsigned int)ActivationFactory,
        v25);
      v11 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      string = 0;
      v12 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      ReleaseSRWLockExclusive(&ActiveMediaAppManagerSingleton);
    }
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
      (const char *)(unsigned int)ComStaticStoreSingleton_U_ActiveMediaAppManagerSingletonHolder____QEAAJAEAV__shared_ptr_U_ActiveMediaAppManagerSingletonHolder___std___Z__Z,
      v25);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
    return v6;
  }
}

```

## disassembly

```asm
0x180021e54  push    rbx
0x180021e56  push    rsi
0x180021e57  push    rdi
0x180021e58  push    r14
0x180021e5a  sub     rsp, 0C8h
0x180021e61  mov     rax, cs:__security_cookie
0x180021e68  xor     rax, rsp
0x180021e6b  mov     [rsp+0E8h+var_38], rax
0x180021e73  mov     rsi, rdx
0x180021e76  lea     rdi, ?ActiveMediaAppManagerSingleton@@3V?$ComStaticStoreSingleton@U_ActiveMediaAppManagerSingletonHolder@@@@A; ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder> ActiveMediaAppManagerSingleton
0x180021e7d  mov     rcx, rdi; SRWLock
0x180021e80  call    cs:__imp_AcquireSRWLockShared
0x180021e86  xorps   xmm0, xmm0
0x180021e89  movdqu  xmmword ptr [rsp+0E8h+var_88], xmm0
0x180021e8f  mov     rcx, cs:qword_1801903B0; this
0x180021e96  xor     r14d, r14d
0x180021e99  test    rcx, rcx
0x180021e9c  jz      short loc_180021EBF
0x180021e9e  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180021ea3  test    al, al
0x180021ea5  jz      short loc_180021EBF
0x180021ea7  mov     rax, cs:qword_1801903A8
0x180021eae  mov     [rsp+0E8h+var_88], rax
0x180021eb3  mov     rax, cs:qword_1801903B0
0x180021eba  mov     [rsp+0E8h+var_88+8], rax
0x180021ebf  lea     rdx, [rsp+0E8h+var_88]
0x180021ec4  mov     rcx, rsi
0x180021ec7  call    ??4?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &&)
0x180021ecc  mov     rcx, [rsp+0E8h+var_88+8]; this
0x180021ed1  test    rcx, rcx
0x180021ed4  jz      short loc_180021EDB
0x180021ed6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021edb  mov     rcx, rdi; SRWLock
0x180021ede  cmp     [rsi], r14
0x180021ee1  jz      short loc_180021EF0
0x180021ee3  call    cs:__imp_ReleaseSRWLockShared
0x180021ee9  xor     eax, eax
0x180021eeb  jmp     loc_18002228E
0x180021ef0  call    cs:__imp_ReleaseSRWLockShared
0x180021ef6  mov     rcx, rdi; SRWLock
0x180021ef9  call    cs:__imp_AcquireSRWLockExclusive
0x180021eff  mov     [rsp+0E8h+var_88], rdi
0x180021f04  xorps   xmm0, xmm0
0x180021f07  movdqu  xmmword ptr [rsp+0E8h+var_98], xmm0
0x180021f0d  mov     rcx, cs:qword_1801903B0; this
0x180021f14  test    rcx, rcx
0x180021f17  jz      short loc_180021F3A
0x180021f19  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180021f1e  test    al, al
0x180021f20  jz      short loc_180021F3A
0x180021f22  mov     rax, cs:qword_1801903A8
0x180021f29  mov     [rsp+0E8h+var_98], rax
0x180021f2e  mov     rax, cs:qword_1801903B0
0x180021f35  mov     [rsp+0E8h+var_98+8], rax
0x180021f3a  lea     rdx, [rsp+0E8h+var_98]
0x180021f3f  mov     rcx, rsi
0x180021f42  call    ??4?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &&)
0x180021f47  mov     rcx, [rsp+0E8h+var_98+8]; this
0x180021f4c  test    rcx, rcx
0x180021f4f  jz      short loc_180021F56
0x180021f51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021f56  cmp     [rsi], r14
0x180021f59  jz      short loc_180021F67
0x180021f5b  lea     rcx, [rsp+0E8h+var_88]
0x180021f60  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021f65  jmp     short loc_180021EE9
0x180021f67  mov     [rsp+0E8h+var_B0], r14
0x180021f6c  lea     rcx, [rsp+0E8h+var_B0]
0x180021f71  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180021f76  lea     rcx, [rsp+0E8h+var_B0]
0x180021f7b  call    ??$MakeAndInitialize@UInspectableContainer@?1??Get@?$ComStaticStoreSingleton@U_ActiveMediaAppManagerSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@@Z@U1?1??23@QEAAJ0@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAUInspectableContainer@?1??Get@?$ComStaticStoreSingleton@U_ActiveMediaAppManagerSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder>::Get(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &)'::`2'::InspectableContainer,`ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder>::Get(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &)'::`2'::InspectableContainer,>(`ComStaticStoreSingleton<_ActiveMediaAppManagerSingletonHolder>::Get(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &)'::`2'::InspectableContainer * *)
0x180021f80  mov     ebx, eax
0x180021f82  test    eax, eax
0x180021f84  jns     short loc_180021FBF
0x180021f86  mov     rcx, [rsp+0E8h]; this
0x180021f8e  mov     r9d, eax; char *
0x180021f91  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x180021f98  mov     edx, 32h ; '2'; void *
0x180021f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fa2  nop
0x180021fa3  lea     rcx, [rsp+0E8h+var_B0]
0x180021fa8  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180021fad  nop
0x180021fae  lea     rcx, [rsp+0E8h+var_88]
0x180021fb3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021fb8  mov     eax, ebx
0x180021fba  jmp     loc_18002228E
0x180021fbf  mov     [rsp+0E8h+string], r14
0x180021fc7  lea     r9, [rsp+0E8h+string]; string
0x180021fcf  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x180021fd4  mov     edx, 2Fh ; '/'; length
0x180021fd9  lea     rcx, sourceString; "Windows::Media::Internal::ActiveMediaAp"...
0x180021fe0  call    cs:__imp_WindowsCreateStringReference
0x180021fe6  test    eax, eax
0x180021fe8  jns     short loc_180021FFD
0x180021fea  xor     r9d, r9d; lpArguments
0x180021fed  xor     r8d, r8d; nNumberOfArguments
0x180021ff0  lea     edx, [r9+1]; dwExceptionFlags
0x180021ff4  mov     ecx, eax; dwExceptionCode
0x180021ff6  call    cs:__imp_RaiseException
0x180021ffc  nop
0x180021ffd  mov     [rsp+0E8h+var_A8], r14
0x180022002  lea     rcx, [rsp+0E8h+var_A8]
0x180022007  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002200c  mov     [rsp+0E8h+var_40], r14
0x180022014  lea     r9, [rsp+0E8h+var_40]; string
0x18002201c  lea     r8, [rsp+0E8h+var_58]; hstringHeader
0x180022024  mov     edx, 2Dh ; '-'; length
0x180022029  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180022030  call    cs:__imp_WindowsCreateStringReference
0x180022036  test    eax, eax
0x180022038  jns     short loc_18002204D
0x18002203a  xor     r9d, r9d; lpArguments
0x18002203d  xor     r8d, r8d; nNumberOfArguments
0x180022040  lea     edx, [r9+1]; dwExceptionFlags
0x180022044  mov     ecx, eax; dwExceptionCode
0x180022046  call    cs:__imp_RaiseException
0x18002204c  int     3; Trap to Debugger
0x18002204d  lea     r8, [rsp+0E8h+var_A8]
0x180022052  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180022059  mov     rcx, [rsp+0E8h+var_40]
0x180022061  call    cs:__imp_RoGetActivationFactory
0x180022067  mov     ebx, eax
0x180022069  test    eax, eax
0x18002206b  jns     short loc_1800220DA
0x18002206d  mov     rcx, [rsp+0E8h]; this
0x180022075  mov     r9d, eax; char *
0x180022078  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x18002207f  mov     edx, 3Bh ; ';'; void *
0x180022084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022089  nop
0x18002208a  mov     rcx, [rsp+0E8h+var_A8]
0x18002208f  test    rcx, rcx
0x180022092  jz      short loc_1800220A6
0x180022094  mov     [rsp+0E8h+var_A8], r14
0x180022099  mov     rax, [rcx]
0x18002209c  mov     rax, [rax+10h]
0x1800220a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220a5  nop
0x1800220a6  mov     [rsp+0E8h+string], r14
0x1800220ae  mov     rcx, [rsp+0E8h+var_B0]
0x1800220b3  test    rcx, rcx
0x1800220b6  jz      short loc_1800220CA
0x1800220b8  mov     [rsp+0E8h+var_B0], r14
0x1800220bd  mov     rax, [rcx]
0x1800220c0  mov     rax, [rax+10h]
0x1800220c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220c9  nop
0x1800220ca  mov     rcx, rdi; SRWLock
0x1800220cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800220d3  mov     eax, ebx
0x1800220d5  jmp     loc_18002228E
0x1800220da  mov     [rsp+0E8h+var_98], r14
0x1800220df  mov     rdi, [rsp+0E8h+var_A8]
0x1800220e4  mov     rax, [rdi]
0x1800220e7  mov     rbx, [rax+38h]
0x1800220eb  lea     rcx, [rsp+0E8h+var_98]
0x1800220f0  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800220f5  lea     rdx, [rsp+0E8h+var_98]
0x1800220fa  mov     rcx, rdi
0x1800220fd  mov     rax, rbx
0x180022100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022105  mov     ebx, eax
0x180022107  test    eax, eax
0x180022109  jns     short loc_180022129
0x18002210b  mov     rcx, [rsp+0E8h]; this
0x180022113  mov     r9d, eax; char *
0x180022116  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x18002211d  mov     edx, 3Fh ; '?'; void *
0x180022122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022127  jmp     short loc_1800221A0
0x180022129  mov     [rsp+0E8h+var_A0], r14
0x18002212e  lea     rdx, [rsp+0E8h+var_A0]
0x180022133  lea     rcx, [rsp+0E8h+var_98]
0x180022138  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18002213d  mov     ebx, eax
0x18002213f  test    eax, eax
0x180022141  jns     short loc_18002214A
0x180022143  mov     edx, 43h ; 'C'
0x180022148  jmp     short loc_18002217D
0x18002214a  mov     [rsp+0E8h+var_B8], r14b
0x18002214f  mov     rcx, [rsp+0E8h+var_A0]
0x180022154  mov     rax, [rcx]
0x180022157  lea     r9, [rsp+0E8h+var_B8]
0x18002215c  mov     r8, [rsp+0E8h+var_B0]
0x180022161  mov     rdx, [rsp+0E8h+string]
0x180022169  mov     rax, [rax+50h]
0x18002216d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022172  mov     ebx, eax
0x180022174  test    eax, eax
0x180022176  jns     short loc_1800221D8
0x180022178  mov     edx, 46h ; 'F'; void *
0x18002217d  mov     r9d, eax; char *
0x180022180  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x180022187  mov     rcx, [rsp+0E8h]; this
0x18002218f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022194  nop
0x180022195  lea     rcx, [rsp+0E8h+var_A0]
0x18002219a  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002219f  nop
0x1800221a0  lea     rcx, [rsp+0E8h+var_98]
0x1800221a5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221aa  nop
0x1800221ab  lea     rcx, [rsp+0E8h+var_A8]
0x1800221b0  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221b5  nop
0x1800221b6  mov     [rsp+0E8h+string], r14
0x1800221be  lea     rcx, [rsp+0E8h+var_B0]
0x1800221c3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221c8  nop
0x1800221c9  lea     rcx, [rsp+0E8h+var_88]
0x1800221ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800221d3  jmp     loc_1800220D3
0x1800221d8  lea     rcx, [rsp+0E8h+var_A0]
0x1800221dd  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221e2  nop
0x1800221e3  lea     rcx, [rsp+0E8h+var_98]
0x1800221e8  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221ed  nop
0x1800221ee  lea     rcx, [rsp+0E8h+var_A8]
0x1800221f3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800221f8  nop
0x1800221f9  mov     rcx, [rsp+0E8h+var_B0]
0x1800221fe  mov     rax, [rcx+28h]
0x180022202  test    rax, rax
0x180022205  jz      short loc_180022211
0x180022207  mov     rcx, [rcx+20h]
0x18002220b  lock inc dword ptr [rax+0Ch]
0x18002220f  jmp     short loc_180022217
0x180022211  mov     rax, r14
0x180022214  mov     rcx, r14
0x180022217  mov     cs:qword_1801903A8, rcx
0x18002221e  mov     rcx, cs:qword_1801903B0; this
0x180022225  mov     cs:qword_1801903B0, rax
0x18002222c  test    rcx, rcx
0x18002222f  jz      short loc_180022236
0x180022231  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180022236  mov     rcx, [rsp+0E8h+var_B0]
0x18002223b  mov     rax, [rcx+28h]
0x18002223f  test    rax, rax
0x180022242  jz      short loc_180022248
0x180022244  lock inc dword ptr [rax+8]
0x180022248  mov     rdx, [rcx+28h]
0x18002224c  mov     rax, [rcx+20h]
0x180022250  mov     [rsi], rax
0x180022253  mov     rcx, [rsi+8]; this
0x180022257  mov     [rsi+8], rdx
0x18002225b  test    rcx, rcx
0x18002225e  jz      short loc_180022266
0x180022260  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022265  nop
0x180022266  lea     rcx, [rsp+0E8h+var_B0]
0x18002226b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022270  jmp     loc_180021F5B
0x180022275  lea     rcx, [rsp+0E8h+var_B0]
0x18002227a  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002227f  nop
0x180022280  lea     rcx, [rsp+0E8h+var_88]
0x180022285  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002228a  mov     eax, dword ptr [rsp+0E8h+var_A8]
0x18002228e  mov     rcx, [rsp+0E8h+var_38]
0x180022296  xor     rcx, rsp; StackCookie
0x180022299  call    __security_check_cookie
0x18002229e  add     rsp, 0C8h
0x1800222a5  pop     r14
0x1800222a7  pop     rdi
0x1800222a8  pop     rsi
0x1800222a9  pop     rbx
0x1800222aa  retn
```
