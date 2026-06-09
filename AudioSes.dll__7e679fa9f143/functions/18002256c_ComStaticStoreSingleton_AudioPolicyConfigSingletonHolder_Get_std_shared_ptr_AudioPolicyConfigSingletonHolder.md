# ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder>::Get(std::shared_ptr<_AudioPolicyConfigSingletonHolder> &)

- ea: `0x18002256c`
- end: `0x180022a66`
- name: `?Get@?$ComStaticStoreSingleton@U_AudioPolicyConfigSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_AudioPolicyConfigSingletonHolder@@@std@@@Z`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800223cc`

## callees

- `0x18000d11c`
- `0x180010a90`
- `0x1800214e0`
- `0x1800222b4`
- `0x180022520`
- `0x18002256c`
- `0x180022a6c`
- `0x180022a8c`
- `0x18006baa4`
- `0x180087e80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022611`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022611`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800225a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800225a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002261a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002261a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022860`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022860`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022717`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022767`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022717`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022751`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022782`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022782`

## string_xrefs

- `0x1800226fa`: `Windows.Media.Internal.AudioPolicyConfig`
- `0x1800226b2`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x180022799`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x1800227ef`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`
- `0x1800228df`: `avcore\audiocore\Include\ComStaticStoreSingleton.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder>::Get(__int64 a1, _QWORD *a2)
{
  int ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  HRESULT v7; // eax
  HRESULT v8; // eax
  int ActivationFactory; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, std::_Ref_count_base **)); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, std::_Ref_count_base **); // rdi
  int v19; // eax
  __int64 v20; // rdx
  std::_Ref_count_base *v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rax
  __int64 v25; // rdx
  std::_Ref_count_base *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rdx
  std::_Ref_count_base *v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-B8h]
  _BYTE v33[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+38h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, std::_Ref_count_base **); // [rsp+40h] [rbp-98h] BYREF
  __int64 v36; // [rsp+48h] [rbp-90h] BYREF
  std::_Ref_count_base *v37[2]; // [rsp+50h] [rbp-88h] BYREF
  std::_Ref_count_base *v38[2]; // [rsp+60h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-68h] BYREF
  HSTRING string; // [rsp+88h] [rbp-50h] BYREF
  HSTRING_HEADER v41; // [rsp+90h] [rbp-48h] BYREF
  HSTRING v42; // [rsp+A8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  AcquireSRWLockShared(&AudioPolicyConfigSingleton);
  *(_OWORD *)v38 = 0;
  if ( qword_180190398 && std::_Ref_count_base::_Incref_nz(qword_180190398) )
  {
    v38[0] = (std::_Ref_count_base *)qword_180190390;
    v38[1] = qword_180190398;
  }
  std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(a2, v38);
  if ( v38[1] )
    std::_Ref_count_base::_Decref(v38[1]);
  if ( *a2 )
  {
    ReleaseSRWLockShared(&AudioPolicyConfigSingleton);
    return 0;
  }
  ReleaseSRWLockShared(&AudioPolicyConfigSingleton);
  AcquireSRWLockExclusive(&AudioPolicyConfigSingleton);
  v38[0] = (std::_Ref_count_base *)&AudioPolicyConfigSingleton;
  *(_OWORD *)v37 = 0;
  if ( qword_180190398 && std::_Ref_count_base::_Incref_nz(qword_180190398) )
  {
    v37[0] = (std::_Ref_count_base *)qword_180190390;
    v37[1] = qword_180190398;
  }
  std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(a2, v37);
  if ( v37[1] )
    std::_Ref_count_base::_Decref(v37[1]);
  if ( *a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
    return 0;
  }
  v34 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v34);
  try
  {
    ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z = ___MakeAndInitialize_UInspectableContainer__1__Get___ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z_U1_1__23_QEAAJ0_Z___V_Details_WRL_Microsoft__YAJPEAPEAUInspectableContainer__1__Get___ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z(&v34);
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x34,
                     (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
                     v5);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v34);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
    return (unsigned int)v35;
  }
  v6 = ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z;
  if ( ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
      (const char *)(unsigned int)ComStaticStoreSingleton_U_AudioPolicyConfigSingletonHolder____QEAAJAEAV__shared_ptr_U_AudioPolicyConfigSingletonHolder___std___Z__Z,
      v32);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v34);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
    return v6;
  }
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Media.Internal.AudioPolicyConfig", 0x28u, &hstringHeader, &string);
  if ( v7 < 0 )
    RaiseException(v7, 1u, 0, 0);
  v36 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v36);
  v42 = 0;
  v8 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &v41, &v42);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v42, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, &v36);
  v10 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v35 = 0;
    v11 = v36;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, std::_Ref_count_base **)))(*(_QWORD *)v36 + 56LL);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v35);
    v13 = v12(v11, &v35);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
        (const char *)(unsigned int)v13,
        v32);
      v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
      if ( v35 )
      {
        v35 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
      }
      v15 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      string = 0;
      v16 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      ReleaseSRWLockExclusive(&AudioPolicyConfigSingleton);
      return v10;
    }
    v37[0] = 0;
    v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
    v18 = **v35;
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v37);
    v19 = v18(v17, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, v37);
    v10 = v19;
    if ( v19 >= 0 )
    {
      v33[0] = 0;
      v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, HSTRING, __int64, _BYTE *))(*(_QWORD *)v37[0] + 80LL))(
              v37[0],
              string,
              v34,
              v33);
      v10 = v19;
      if ( v19 >= 0 )
      {
        v21 = v37[0];
        if ( v37[0] )
        {
          v37[0] = 0;
          (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
        if ( v35 )
        {
          v35 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
        }
        v23 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = *(volatile signed __int32 **)(v34 + 40);
        if ( v24 )
        {
          v25 = *(_QWORD *)(v34 + 32);
          _InterlockedIncrement(v24 + 3);
        }
        else
        {
          v24 = 0;
          v25 = 0;
        }
        qword_180190390 = v25;
        v26 = qword_180190398;
        qword_180190398 = (std::_Ref_count_base *)v24;
        if ( v26 )
          std::_Ref_count_base::_Decwref(v26);
        v27 = v34;
        v28 = *(_QWORD *)(v34 + 40);
        if ( v28 )
          _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
        v29 = *(_QWORD *)(v27 + 40);
        *a2 = *(_QWORD *)(v27 + 32);
        v30 = (std::_Ref_count_base *)a2[1];
        a2[1] = v29;
        if ( v30 )
          std::_Ref_count_base::_Decref(v30);
        v31 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        ReleaseSRWLockExclusive(&AudioPolicyConfigSingleton);
        return 0;
      }
      v20 = 70;
    }
    else
    {
      v20 = 67;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
      (const char *)(unsigned int)v19,
      v32);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v37);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v35);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"avcore\\audiocore\\Include\\ComStaticStoreSingleton.h",
      (const char *)(unsigned int)ActivationFactory,
      v32);
  }
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v36);
  string = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v34);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
  return v10;
}

```

## disassembly

```asm
0x18002256c  mov     [rsp+arg_0], rbx
0x180022571  mov     [rsp+arg_10], rsi
0x180022576  push    rdi
0x180022577  push    r14
0x180022579  push    r15
0x18002257b  sub     rsp, 0C0h
0x180022582  mov     rax, cs:__security_cookie
0x180022589  xor     rax, rsp
0x18002258c  mov     [rsp+0D8h+var_28], rax
0x180022594  mov     rsi, rdx
0x180022597  lea     r15, ?AudioPolicyConfigSingleton@@3V?$ComStaticStoreSingleton@U_AudioPolicyConfigSingletonHolder@@@@A; ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder> AudioPolicyConfigSingleton
0x18002259e  mov     rcx, r15; SRWLock
0x1800225a1  call    cs:__imp_AcquireSRWLockShared
0x1800225a7  xorps   xmm0, xmm0
0x1800225aa  movdqu  xmmword ptr [rsp+0D8h+var_78], xmm0
0x1800225b0  mov     rcx, cs:qword_180190398; this
0x1800225b7  xor     r14d, r14d
0x1800225ba  test    rcx, rcx
0x1800225bd  jz      short loc_1800225E0
0x1800225bf  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x1800225c4  test    al, al
0x1800225c6  jz      short loc_1800225E0
0x1800225c8  mov     rax, cs:qword_180190390
0x1800225cf  mov     [rsp+0D8h+var_78], rax
0x1800225d4  mov     rax, cs:qword_180190398
0x1800225db  mov     [rsp+0D8h+var_78+8], rax
0x1800225e0  lea     rdx, [rsp+0D8h+var_78]
0x1800225e5  mov     rcx, rsi
0x1800225e8  call    ??4?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &&)
0x1800225ed  mov     rcx, [rsp+0D8h+var_78+8]; this
0x1800225f2  test    rcx, rcx
0x1800225f5  jz      short loc_1800225FC
0x1800225f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800225fc  mov     rcx, r15; SRWLock
0x1800225ff  cmp     [rsi], r14
0x180022602  jz      short loc_180022611
0x180022604  call    cs:__imp_ReleaseSRWLockShared
0x18002260a  xor     eax, eax
0x18002260c  jmp     loc_180022A3D
0x180022611  call    cs:__imp_ReleaseSRWLockShared
0x180022617  mov     rcx, r15; SRWLock
0x18002261a  call    cs:__imp_AcquireSRWLockExclusive
0x180022620  mov     [rsp+0D8h+var_78], r15
0x180022625  xorps   xmm0, xmm0
0x180022628  movdqu  xmmword ptr [rsp+0D8h+var_88], xmm0
0x18002262e  mov     rcx, cs:qword_180190398; this
0x180022635  test    rcx, rcx
0x180022638  jz      short loc_18002265B
0x18002263a  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18002263f  test    al, al
0x180022641  jz      short loc_18002265B
0x180022643  mov     rax, cs:qword_180190390
0x18002264a  mov     [rsp+0D8h+var_88], rax
0x18002264f  mov     rax, cs:qword_180190398
0x180022656  mov     [rsp+0D8h+var_88+8], rax
0x18002265b  lea     rdx, [rsp+0D8h+var_88]
0x180022660  mov     rcx, rsi
0x180022663  call    ??4?$shared_ptr@U_ActiveMediaAppManagerSingletonHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_ActiveMediaAppManagerSingletonHolder>::operator=(std::shared_ptr<_ActiveMediaAppManagerSingletonHolder> &&)
0x180022668  mov     rcx, [rsp+0D8h+var_88+8]; this
0x18002266d  test    rcx, rcx
0x180022670  jz      short loc_180022677
0x180022672  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022677  cmp     [rsi], r14
0x18002267a  jz      short loc_180022688
0x18002267c  lea     rcx, [rsp+0D8h+var_78]
0x180022681  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022686  jmp     short loc_18002260A
0x180022688  mov     [rsp+0D8h+var_A0], r14
0x18002268d  lea     rcx, [rsp+0D8h+var_A0]
0x180022692  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022697  lea     rcx, [rsp+0D8h+var_A0]
0x18002269c  call    ??$MakeAndInitialize@UInspectableContainer@?1??Get@?$ComStaticStoreSingleton@U_AudioPolicyConfigSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_AudioPolicyConfigSingletonHolder@@@std@@@Z@U1?1??23@QEAAJ0@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAUInspectableContainer@?1??Get@?$ComStaticStoreSingleton@U_AudioPolicyConfigSingletonHolder@@@@QEAAJAEAV?$shared_ptr@U_AudioPolicyConfigSingletonHolder@@@std@@@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder>::Get(std::shared_ptr<_AudioPolicyConfigSingletonHolder> &)'::`2'::InspectableContainer,`ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder>::Get(std::shared_ptr<_AudioPolicyConfigSingletonHolder> &)'::`2'::InspectableContainer,>(`ComStaticStoreSingleton<_AudioPolicyConfigSingletonHolder>::Get(std::shared_ptr<_AudioPolicyConfigSingletonHolder> &)'::`2'::InspectableContainer * *)
0x1800226a1  mov     ebx, eax
0x1800226a3  test    eax, eax
0x1800226a5  jns     short loc_1800226E0
0x1800226a7  mov     rcx, [rsp+0D8h]; this
0x1800226af  mov     r9d, eax; char *
0x1800226b2  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x1800226b9  mov     edx, 32h ; '2'; void *
0x1800226be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226c3  nop
0x1800226c4  lea     rcx, [rsp+0D8h+var_A0]
0x1800226c9  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800226ce  nop
0x1800226cf  lea     rcx, [rsp+0D8h+var_78]
0x1800226d4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800226d9  mov     eax, ebx
0x1800226db  jmp     loc_180022A3D
0x1800226e0  mov     [rsp+0D8h+string], r14
0x1800226e8  lea     r9, [rsp+0D8h+string]; string
0x1800226f0  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x1800226f5  mov     edx, 28h ; '('; length
0x1800226fa  lea     rcx, aWindowsMediaIn; "Windows.Media.Internal.AudioPolicyConfi"...
0x180022701  call    cs:__imp_WindowsCreateStringReference
0x180022707  test    eax, eax
0x180022709  jns     short loc_18002271E
0x18002270b  xor     r9d, r9d; lpArguments
0x18002270e  xor     r8d, r8d; nNumberOfArguments
0x180022711  lea     edx, [r9+1]; dwExceptionFlags
0x180022715  mov     ecx, eax; dwExceptionCode
0x180022717  call    cs:__imp_RaiseException
0x18002271d  nop
0x18002271e  mov     [rsp+0D8h+var_90], r14
0x180022723  lea     rcx, [rsp+0D8h+var_90]
0x180022728  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002272d  mov     [rsp+0D8h+var_30], r14
0x180022735  lea     r9, [rsp+0D8h+var_30]; string
0x18002273d  lea     r8, [rsp+0D8h+var_48]; hstringHeader
0x180022745  mov     edx, 2Dh ; '-'; length
0x18002274a  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180022751  call    cs:__imp_WindowsCreateStringReference
0x180022757  test    eax, eax
0x180022759  jns     short loc_18002276E
0x18002275b  xor     r9d, r9d; lpArguments
0x18002275e  xor     r8d, r8d; nNumberOfArguments
0x180022761  lea     edx, [r9+1]; dwExceptionFlags
0x180022765  mov     ecx, eax; dwExceptionCode
0x180022767  call    cs:__imp_RaiseException
0x18002276d  int     3; Trap to Debugger
0x18002276e  lea     r8, [rsp+0D8h+var_90]
0x180022773  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x18002277a  mov     rcx, [rsp+0D8h+var_30]
0x180022782  call    cs:__imp_RoGetActivationFactory
0x180022788  mov     ebx, eax
0x18002278a  test    eax, eax
0x18002278c  jns     short loc_1800227AF
0x18002278e  mov     rcx, [rsp+0D8h]; this
0x180022796  mov     r9d, eax; char *
0x180022799  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x1800227a0  mov     edx, 3Bh ; ';'; void *
0x1800227a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227aa  jmp     loc_18002290A
0x1800227af  mov     [rsp+0D8h+var_98], r14
0x1800227b4  mov     rdi, [rsp+0D8h+var_90]
0x1800227b9  mov     rax, [rdi]
0x1800227bc  mov     rbx, [rax+38h]
0x1800227c0  lea     rcx, [rsp+0D8h+var_98]
0x1800227c5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800227ca  lea     rdx, [rsp+0D8h+var_98]
0x1800227cf  mov     rcx, rdi
0x1800227d2  mov     rax, rbx
0x1800227d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227da  mov     ebx, eax
0x1800227dc  test    eax, eax
0x1800227de  jns     loc_18002286B
0x1800227e4  mov     rcx, [rsp+0D8h]; this
0x1800227ec  mov     r9d, eax; char *
0x1800227ef  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x1800227f6  mov     edx, 3Fh ; '?'; void *
0x1800227fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022800  nop
0x180022801  mov     rcx, [rsp+0D8h+var_98]
0x180022806  test    rcx, rcx
0x180022809  jz      short loc_18002281D
0x18002280b  mov     [rsp+0D8h+var_98], r14
0x180022810  mov     rax, [rcx]
0x180022813  mov     rax, [rax+10h]
0x180022817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002281c  nop
0x18002281d  mov     rcx, [rsp+0D8h+var_90]
0x180022822  test    rcx, rcx
0x180022825  jz      short loc_180022839
0x180022827  mov     [rsp+0D8h+var_90], r14
0x18002282c  mov     rax, [rcx]
0x18002282f  mov     rax, [rax+10h]
0x180022833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022838  nop
0x180022839  mov     [rsp+0D8h+string], r14
0x180022841  mov     rcx, [rsp+0D8h+var_A0]
0x180022846  test    rcx, rcx
0x180022849  jz      short loc_18002285D
0x18002284b  mov     [rsp+0D8h+var_A0], r14
0x180022850  mov     rax, [rcx]
0x180022853  mov     rax, [rax+10h]
0x180022857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002285c  nop
0x18002285d  mov     rcx, r15; SRWLock
0x180022860  call    cs:__imp_ReleaseSRWLockExclusive
0x180022866  jmp     loc_180022932
0x18002286b  mov     [rsp+0D8h+var_88], r14
0x180022870  mov     rbx, [rsp+0D8h+var_98]
0x180022875  mov     rax, [rbx]
0x180022878  mov     rdi, [rax]
0x18002287b  lea     rcx, [rsp+0D8h+var_88]
0x180022880  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022885  lea     r8, [rsp+0D8h+var_88]
0x18002288a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180022891  mov     rcx, rbx
0x180022894  mov     rax, rdi
0x180022897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002289c  mov     ebx, eax
0x18002289e  test    eax, eax
0x1800228a0  jns     short loc_1800228A9
0x1800228a2  mov     edx, 43h ; 'C'
0x1800228a7  jmp     short loc_1800228DC
0x1800228a9  mov     [rsp+0D8h+var_A8], r14b
0x1800228ae  mov     rcx, [rsp+0D8h+var_88]
0x1800228b3  mov     rax, [rcx]
0x1800228b6  lea     r9, [rsp+0D8h+var_A8]
0x1800228bb  mov     r8, [rsp+0D8h+var_A0]
0x1800228c0  mov     rdx, [rsp+0D8h+string]
0x1800228c8  mov     rax, [rax+50h]
0x1800228cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228d1  mov     ebx, eax
0x1800228d3  test    eax, eax
0x1800228d5  jns     short loc_180022939
0x1800228d7  mov     edx, 46h ; 'F'; void *
0x1800228dc  mov     r9d, eax; char *
0x1800228df  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\Include\\ComStaticSt"...
0x1800228e6  mov     rcx, [rsp+0D8h]; this
0x1800228ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228f3  nop
0x1800228f4  lea     rcx, [rsp+0D8h+var_88]
0x1800228f9  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800228fe  nop
0x1800228ff  lea     rcx, [rsp+0D8h+var_98]
0x180022904  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022909  nop
0x18002290a  lea     rcx, [rsp+0D8h+var_90]
0x18002290f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022914  nop
0x180022915  mov     [rsp+0D8h+string], r14
0x18002291d  lea     rcx, [rsp+0D8h+var_A0]
0x180022922  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022927  nop
0x180022928  lea     rcx, [rsp+0D8h+var_78]
0x18002292d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022932  mov     eax, ebx
0x180022934  jmp     loc_180022A3D
0x180022939  mov     rcx, [rsp+0D8h+var_88]
0x18002293e  test    rcx, rcx
0x180022941  jz      short loc_180022955
0x180022943  mov     [rsp+0D8h+var_88], r14
0x180022948  mov     rax, [rcx]
0x18002294b  mov     rax, [rax+10h]
0x18002294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022954  nop
0x180022955  mov     rcx, [rsp+0D8h+var_98]
0x18002295a  test    rcx, rcx
0x18002295d  jz      short loc_180022971
0x18002295f  mov     [rsp+0D8h+var_98], r14
0x180022964  mov     rax, [rcx]
0x180022967  mov     rax, [rax+10h]
0x18002296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022970  nop
0x180022971  mov     rcx, [rsp+0D8h+var_90]
0x180022976  test    rcx, rcx
0x180022979  jz      short loc_18002298D
0x18002297b  mov     [rsp+0D8h+var_90], r14
0x180022980  mov     rax, [rcx]
0x180022983  mov     rax, [rax+10h]
0x180022987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002298c  nop
0x18002298d  mov     rcx, [rsp+0D8h+var_A0]
0x180022992  mov     rax, [rcx+28h]
0x180022996  test    rax, rax
0x180022999  jz      short loc_1800229A5
0x18002299b  mov     rdx, [rcx+20h]
0x18002299f  lock inc dword ptr [rax+0Ch]
0x1800229a3  jmp     short loc_1800229AB
0x1800229a5  mov     rax, r14
0x1800229a8  mov     rdx, r14
0x1800229ab  mov     cs:qword_180190390, rdx
0x1800229b2  mov     rcx, cs:qword_180190398; this
0x1800229b9  mov     cs:qword_180190398, rax
0x1800229c0  test    rcx, rcx
0x1800229c3  jz      short loc_1800229CA
0x1800229c5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800229ca  mov     rcx, [rsp+0D8h+var_A0]
0x1800229cf  mov     rax, [rcx+28h]
0x1800229d3  test    rax, rax
0x1800229d6  jz      short loc_1800229DC
0x1800229d8  lock inc dword ptr [rax+8]
0x1800229dc  mov     rdx, [rcx+28h]
0x1800229e0  mov     rax, [rcx+20h]
0x1800229e4  mov     [rsi], rax
0x1800229e7  mov     rcx, [rsi+8]; this
0x1800229eb  mov     [rsi+8], rdx
0x1800229ef  test    rcx, rcx
0x1800229f2  jz      short loc_1800229FA
0x1800229f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800229f9  nop
0x1800229fa  mov     rcx, [rsp+0D8h+var_A0]
0x1800229ff  test    rcx, rcx
0x180022a02  jz      short loc_180022A16
0x180022a04  mov     [rsp+0D8h+var_A0], r14
0x180022a09  mov     rax, [rcx]
0x180022a0c  mov     rax, [rax+10h]
0x180022a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a15  nop
0x180022a16  mov     rcx, r15; SRWLock
0x180022a19  call    cs:__imp_ReleaseSRWLockExclusive
0x180022a1f  jmp     loc_18002260A
0x180022a24  lea     rcx, [rsp+0D8h+var_A0]
0x180022a29  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180022a2e  nop
0x180022a2f  lea     rcx, [rsp+0D8h+var_78]
0x180022a34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022a39  mov     eax, dword ptr [rsp+0D8h+var_98]
0x180022a3d  mov     rcx, [rsp+0D8h+var_28]
  ... truncated ...
```
