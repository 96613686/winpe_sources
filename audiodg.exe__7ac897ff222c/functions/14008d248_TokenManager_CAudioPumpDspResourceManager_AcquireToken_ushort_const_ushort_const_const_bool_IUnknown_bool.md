# TokenManager<CAudioPumpDspResourceManager>::AcquireToken<ushort const *>(ushort const * const &,bool,IUnknown * *,bool *)

- ea: `0x14008d248`
- end: `0x14008d666`
- name: `??$AcquireToken@PEBG@?$TokenManager@VCAudioPumpDspResourceManager@@@@AEAAJAEBQEBG_NPEAPEAUIUnknown@@PEA_N@Z`
- size: `1054`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14008e6d0`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x1400276f0`
- `0x14002a120`
- `0x1400378e4`
- `0x14004feb4`
- `0x1400516e8`
- `0x1400690a0`
- `0x140072e08`
- `0x140078458`
- `0x14008d204`
- `0x14008d248`
- `0x14008d7ac`
- `0x14008dac8`
- `0x14008db84`
- `0x1400902c0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008d2d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008d2d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14008d27b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14008d27b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14008d360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14008d360`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008d2e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008d4dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008d2e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14008d4dc`

## string_xrefs

- `0x14008d3fb`: `avcore\audiocore\Server\inc\ResourceTokenManager.h`
- `0x14008d441`: `avcore\audiocore\Server\inc\ResourceTokenManager.h`
- `0x14008d4ab`: `avcore\audiocore\Server\inc\ResourceTokenManager.h`
- `0x14008d519`: `avcore\audiocore\Server\inc\ResourceTokenManager.h`
- `0x14008d5a2`: `avcore\audiocore\Server\inc\ResourceTokenManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 TokenManager<CAudioPumpDspResourceManager>::AcquireToken<unsigned short const *>(
        PSRWLOCK SRWLock,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        ...)
{
  _BYTE *v6; // r13
  struct IWeakReference **Ptr; // rbx
  struct IWeakReference **v8; // r12
  _QWORD *v9; // rsi
  _QWORD *v10; // rax
  const char *v11; // r9
  __int64 result; // rax
  __int64 v13; // rcx
  char *v14; // r14
  char *i; // rbx
  char *v16; // rsi
  char *v17; // rbx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  __int64 *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // esi
  __int64 (__fastcall **v27)(__int64, GUID *, _QWORD *); // rax
  int v28; // esi
  int v29[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v30[8]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PSRWLOCK v32; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v33; // [rsp+78h] [rbp+10h]
  _QWORD *v34; // [rsp+88h] [rbp+20h]
  _QWORD *p_Ptr; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  p_Ptr = va_arg(va1, _QWORD *);
  v34 = a4;
  v33 = a2;
  *a4 = 0;
  v6 = p_Ptr;
  *(_BYTE *)p_Ptr = 0;
  AcquireSRWLockShared(SRWLock);
  v32 = SRWLock;
  Ptr = (struct IWeakReference **)SRWLock[1].Ptr;
  v8 = (struct IWeakReference **)SRWLock[2].Ptr;
  try
  {
    while ( Ptr != v8 )
    {
      p_Ptr = 0;
      if ( (int)wil::details::weak_query_policy::query(*Ptr, &GUID_00000000_0000_0000_c000_000000000046, (void **)va) >= 0 )
      {
        v9 = p_Ptr;
        if ( !(unsigned int)_o__wcsicmp(*v33, *(_QWORD *)(p_Ptr[6] + 80LL)) )
        {
          v9[5] = GetTickCount64();
          v10 = p_Ptr;
          p_Ptr = 0;
          *v34 = v10;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((_QWORD **)va);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
          return 0;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((_QWORD **)va);
      ++Ptr;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
    if ( a3 )
    {
      result = 2147943568LL;
    }
    else
    {
      AcquireSRWLockExclusive(SRWLock);
      p_Ptr = &SRWLock->Ptr;
      v14 = (char *)SRWLock[2].Ptr;
      for ( i = (char *)SRWLock[1].Ptr;
            i != v14
         && !(unsigned __int8)_lambda_f7eca69487ca4c52b1e5e9aff55109c3_::operator()<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(
                                v13,
                                i);
            i += 8 )
      {
        ;
      }
      v16 = i;
      if ( i != v14 )
      {
        while ( 1 )
        {
          i += 8;
          if ( i == v14 )
            break;
          if ( !(unsigned __int8)_lambda_f7eca69487ca4c52b1e5e9aff55109c3_::operator()<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(
                                   v13,
                                   i) )
          {
            wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::operator=<IWeakReference,wil::err_exception_policy,void>(
              v16,
              i);
            v16 += 8;
          }
        }
      }
      if ( v16 != v14 )
      {
        v17 = (char *)SRWLock[2].Ptr;
        while ( v14 != v17 )
        {
          wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::operator=<IWeakReference,wil::err_exception_policy,void>(
            v16,
            v14);
          v16 += 8;
          v14 += 8;
        }
        std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(
          v16,
          SRWLock[2].Ptr);
        SRWLock[2].Ptr = v16;
      }
      if ( *v6 )
      {
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x123,
                (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
                (const char *)0x5AA,
                v29[0]);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
        result = v18;
      }
      else if ( ((char *)SRWLock[2].Ptr - (char *)SRWLock[1].Ptr) >> 3 < (unsigned __int64)LODWORD(SRWLock[4].Ptr) )
      {
        v20 = (__int64 *)Microsoft::WRL::Details::Make<TokenManager<CAudioPumpDspResourceManager>::Token,>(v30);
        v21 = *v20;
        *v20 = 0;
        *(_QWORD *)v29 = v21;
        v22 = v30[0];
        if ( v30[0] )
        {
          v30[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        if ( v21 )
        {
          *(_QWORD *)(v21 + 40) = GetTickCount64();
          v24 = *(_QWORD *)(v21 + 48);
          *(_QWORD *)(v21 + 48) = 0;
          if ( v24 )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPumpDspResourceToken,IDeviceGraphBufferFactory,IDspAudioProcessingObjectFactory,IDspAudioEndpointFactory,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>::Release(
              v24,
              v23);
          v25 = Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext,CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext,unsigned short const * const &,CAudioPumpDspResourceManager * &>(
                  v21 + 48,
                  v33,
                  &SRWLock[5]);
          v26 = v25;
          if ( v25 >= 0 )
          {
            v32 = 0;
            v27 = *(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v21;
            v30[0] = 0;
            v28 = (*v27)(v21, &GUID_00000038_0000_0000_c000_000000000046, v30);
            if ( v28 >= 0 )
              v28 = (*(__int64 (__fastcall **)(_QWORD, PSRWLOCK *))(*(_QWORD *)v30[0] + 24LL))(v30[0], &v32);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
            if ( v28 >= 0 )
            {
              if ( SRWLock[2].Ptr == SRWLock[3].Ptr )
              {
                std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &>(
                  &SRWLock[1],
                  SRWLock[2].Ptr,
                  &v32);
              }
              else
              {
                wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>(
                  SRWLock[2].Ptr,
                  &v32);
                SRWLock[2].Ptr = (char *)SRWLock[2].Ptr + 8;
              }
              (**(void (__fastcall ***)(__int64, GUID *, _QWORD *))v21)(
                v21,
                &GUID_00000000_0000_0000_c000_000000000046,
                v34);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
              wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(v29);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x133,
                (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
                (const char *)(unsigned int)v28,
                v29[0]);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
              wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(v29);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
              result = (unsigned int)v28;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x130,
              (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
              (const char *)(unsigned int)v25,
              v29[0]);
            wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(v29);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
            result = v26;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12E,
            (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
            (const char *)0x8007000ELL,
            v29[0]);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(v29);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
          result = 2147942414LL;
        }
      }
      else
      {
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x129,
                (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
                (const char *)0x5AA,
                v29[0]);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((_QWORD **)va);
        result = v19;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v34) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x13A,
                     (unsigned int)"avcore\\audiocore\\Server\\inc\\ResourceTokenManager.h",
                     v11);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x14008d248  mov     [rsp+arg_18], r9
0x14008d24d  mov     [rsp+arg_8], rdx
0x14008d252  push    rbx
0x14008d253  push    rsi
0x14008d254  push    rdi
0x14008d255  push    r12
0x14008d257  push    r13
0x14008d259  push    r14
0x14008d25b  push    r15
0x14008d25d  sub     rsp, 30h
0x14008d261  mov     r14b, r8b
0x14008d264  mov     r15, rcx
0x14008d267  mov     qword ptr [r9], 0
0x14008d26e  mov     r13, [rsp+68h+arg_20]
0x14008d276  mov     byte ptr [r13+0], 0
0x14008d27b  call    cs:__imp_AcquireSRWLockShared
0x14008d281  mov     [rsp+68h+arg_0], r15
0x14008d286  lea     rdi, [r15+8]
0x14008d28a  mov     rbx, [rdi]
0x14008d28d  mov     r12, [rdi+8]
0x14008d291  cmp     rbx, r12
0x14008d294  jz      loc_14008D341
0x14008d29a  mov     [rsp+68h+arg_20], 0
0x14008d2a6  lea     r8, [rsp+68h+arg_20]; void **
0x14008d2ae  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14008d2b5  mov     rcx, [rbx]; struct IWeakReference *
0x14008d2b8  call    ?query@weak_query_policy@details@wil@@SAJPEAUIWeakReference@@AEBU_GUID@@PEAPEAX@Z; wil::details::weak_query_policy::query(IWeakReference *,_GUID const &,void * *)
0x14008d2bd  test    eax, eax
0x14008d2bf  js      short loc_14008D32B
0x14008d2c1  mov     rsi, [rsp+68h+arg_20]
0x14008d2c9  mov     rdx, [rsi+30h]
0x14008d2cd  mov     rdx, [rdx+50h]
0x14008d2d1  mov     rax, [rsp+68h+arg_8]
0x14008d2d6  mov     rcx, [rax]
0x14008d2d9  call    cs:__imp__o__wcsicmp
0x14008d2df  test    eax, eax
0x14008d2e1  jnz     short loc_14008D32B
0x14008d2e3  call    cs:__imp_GetTickCount64
0x14008d2e9  mov     [rsi+28h], rax
0x14008d2ed  mov     rax, [rsp+68h+arg_20]
0x14008d2f5  mov     [rsp+68h+arg_20], 0
0x14008d301  mov     r8, [rsp+68h+arg_18]
0x14008d309  mov     [r8], rax
0x14008d30c  lea     rcx, [rsp+68h+arg_20]
0x14008d314  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008d319  nop
0x14008d31a  lea     rcx, [rsp+68h+arg_0]
0x14008d31f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14008d324  xor     eax, eax
0x14008d326  jmp     loc_14008D655
0x14008d32b  lea     rcx, [rsp+68h+arg_20]
0x14008d333  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008d338  add     rbx, 8
0x14008d33c  jmp     loc_14008D291
0x14008d341  lea     rcx, [rsp+68h+arg_0]
0x14008d346  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14008d34b  xor     r12d, r12d
0x14008d34e  test    r14b, r14b
0x14008d351  jz      short loc_14008D35D
0x14008d353  mov     eax, 80070490h
0x14008d358  jmp     loc_14008D655
0x14008d35d  mov     rcx, r15; SRWLock
0x14008d360  call    cs:__imp_AcquireSRWLockExclusive
0x14008d366  mov     [rsp+68h+arg_20], r15
0x14008d36e  mov     r14, [r15+10h]
0x14008d372  mov     rbx, [rdi]
0x14008d375  cmp     rbx, r14
0x14008d378  jz      short loc_14008D38C
0x14008d37a  mov     rdx, rbx
0x14008d37d  call    ??$?RV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@_lambda_f7eca69487ca4c52b1e5e9aff55109c3_@@QEBA?A_PAEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@Z
0x14008d382  test    al, al
0x14008d384  jnz     short loc_14008D38C
0x14008d386  add     rbx, 8
0x14008d38a  jmp     short loc_14008D375
0x14008d38c  mov     rsi, rbx
0x14008d38f  cmp     rbx, r14
0x14008d392  jz      short loc_14008D3BA
0x14008d394  add     rbx, 8
0x14008d398  cmp     rbx, r14
0x14008d39b  jz      short loc_14008D3BA
0x14008d39d  mov     rdx, rbx
0x14008d3a0  call    ??$?RV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@_lambda_f7eca69487ca4c52b1e5e9aff55109c3_@@QEBA?A_PAEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@Z
0x14008d3a5  test    al, al
0x14008d3a7  jnz     short loc_14008D394
0x14008d3a9  mov     rdx, rbx
0x14008d3ac  mov     rcx, rsi
0x14008d3af  call    ??$?4UIWeakReference@@Uerr_exception_policy@wil@@X@?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@1@@Z; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::operator=<IWeakReference,wil::err_exception_policy,void>(wil::com_ptr_t<IWeakReference,wil::err_exception_policy> &&)
0x14008d3b4  add     rsi, 8
0x14008d3b8  jmp     short loc_14008D394
0x14008d3ba  cmp     rsi, r14
0x14008d3bd  jz      short loc_14008D3EA
0x14008d3bf  mov     rbx, [r15+10h]
0x14008d3c3  jmp     short loc_14008D3D5
0x14008d3c5  mov     rdx, r14
0x14008d3c8  call    ??$?4UIWeakReference@@Uerr_exception_policy@wil@@X@?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@1@@Z; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::operator=<IWeakReference,wil::err_exception_policy,void>(wil::com_ptr_t<IWeakReference,wil::err_exception_policy> &&)
0x14008d3cd  add     rsi, 8
0x14008d3d1  add     r14, 8
0x14008d3d5  mov     rcx, rsi
0x14008d3d8  cmp     r14, rbx
0x14008d3db  jnz     short loc_14008D3C5
0x14008d3dd  mov     rdx, [r15+10h]
0x14008d3e1  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x14008d3e6  mov     [r15+10h], rsi
0x14008d3ea  cmp     [r13+0], r12b
0x14008d3ee  jz      short loc_14008D422
0x14008d3f0  mov     rcx, [rsp+68h]; this
0x14008d3f5  mov     r9d, 5AAh; char *
0x14008d3fb  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\Server\\inc\\Resourc"...
0x14008d402  mov     edx, 123h; void *
0x14008d407  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14008d40c  mov     ebx, eax
0x14008d40e  lea     rcx, [rsp+68h+arg_20]
0x14008d416  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d41b  mov     eax, ebx
0x14008d41d  jmp     loc_14008D655
0x14008d422  mov     rcx, [rdi+8]
0x14008d426  sub     rcx, [rdi]
0x14008d429  sar     rcx, 3
0x14008d42d  mov     eax, [r15+20h]
0x14008d431  cmp     rcx, rax
0x14008d434  jb      short loc_14008D468
0x14008d436  mov     rcx, [rsp+68h]; this
0x14008d43b  mov     r9d, 5AAh; char *
0x14008d441  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\Server\\inc\\Resourc"...
0x14008d448  mov     edx, 129h; void *
0x14008d44d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14008d452  mov     ebx, eax
0x14008d454  lea     rcx, [rsp+68h+arg_20]
0x14008d45c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d461  mov     eax, ebx
0x14008d463  jmp     loc_14008D655
0x14008d468  lea     rcx, [rsp+68h+var_40]
0x14008d46d  call    ??$Make@VToken@?$TokenManager@VCAudioPumpDspResourceManager@@@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VToken@?$TokenManager@VCAudioPumpDspResourceManager@@@@@12@XZ; Microsoft::WRL::Details::Make<TokenManager<CAudioPumpDspResourceManager>::Token,>(void)
0x14008d472  mov     rbx, [rax]
0x14008d475  mov     [rax], r12
0x14008d478  mov     qword ptr [rsp+68h+var_48], rbx; int
0x14008d47d  mov     rcx, [rsp+68h+var_40]
0x14008d482  test    rcx, rcx
0x14008d485  jz      short loc_14008D499
0x14008d487  mov     [rsp+68h+var_40], r12
0x14008d48c  mov     rax, [rcx]
0x14008d48f  mov     rax, [rax+10h]
0x14008d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d498  nop
0x14008d499  test    rbx, rbx
0x14008d49c  jnz     short loc_14008D4DC
0x14008d49e  mov     rcx, [rsp+68h]; this
0x14008d4a3  mov     ebx, 8007000Eh
0x14008d4a8  mov     r9d, ebx; char *
0x14008d4ab  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\Server\\inc\\Resourc"...
0x14008d4b2  mov     edx, 12Eh; void *
0x14008d4b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d4bc  nop
0x14008d4bd  lea     rcx, [rsp+68h+var_48]
0x14008d4c2  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14008d4c7  nop
0x14008d4c8  lea     rcx, [rsp+68h+arg_20]
0x14008d4d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d4d5  mov     eax, ebx
0x14008d4d7  jmp     loc_14008D655
0x14008d4dc  call    cs:__imp_GetTickCount64
0x14008d4e2  mov     [rbx+28h], rax
0x14008d4e6  lea     rsi, [rbx+30h]
0x14008d4ea  mov     rcx, [rsi]
0x14008d4ed  mov     [rsi], r12
0x14008d4f0  test    rcx, rcx
0x14008d4f3  jz      short loc_14008D4FA
0x14008d4f5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioPumpDspResourceToken@@UIDeviceGraphBufferFactory@@UIDspAudioProcessingObjectFactory@@UIDspAudioEndpointFactory@@UIDspCrossProcessAudioEndpointFactory@@UIDspBridgeAudioEndpointFactory@@UIDspAudioProcessorFactory@@UIDspAudioPumpFactory@@UIDspAudioPumpContext@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPumpDspResourceToken,IDeviceGraphBufferFactory,IDspAudioProcessingObjectFactory,IDspAudioEndpointFactory,IDspCrossProcessAudioEndpointFactory,IDspBridgeAudioEndpointFactory,IDspAudioProcessorFactory,IDspAudioPumpFactory,IDspAudioPumpContext>::Release(void)
0x14008d4fa  lea     r8, [r15+28h]
0x14008d4fe  mov     rdx, [rsp+68h+arg_8]
0x14008d503  mov     rcx, rsi
0x14008d506  call    ??$MakeAndInitialize@VCAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@V12@AEBQEBGAEAPEAV2@@Details@WRL@Microsoft@@YAJPEAPEAVCAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@AEBQEBGAEAPEAV4@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext,CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext,ushort const * const &,CAudioPumpDspResourceManager * &>(CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext * *,ushort const * const &,CAudioPumpDspResourceManager * &)
0x14008d50b  mov     esi, eax
0x14008d50d  test    eax, eax
0x14008d50f  jns     short loc_14008D54A
0x14008d511  mov     rcx, [rsp+68h]; this
0x14008d516  mov     r9d, eax; char *
0x14008d519  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\Server\\inc\\Resourc"...
0x14008d520  mov     edx, 130h; void *
0x14008d525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d52a  nop
0x14008d52b  lea     rcx, [rsp+68h+var_48]
0x14008d530  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14008d535  nop
0x14008d536  lea     rcx, [rsp+68h+arg_20]
0x14008d53e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d543  mov     eax, esi
0x14008d545  jmp     loc_14008D655
0x14008d54a  mov     [rsp+68h+arg_0], r12
0x14008d54f  mov     rax, [rbx]
0x14008d552  mov     [rsp+68h+var_40], r12
0x14008d557  lea     r8, [rsp+68h+var_40]
0x14008d55c  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x14008d563  mov     rcx, rbx
0x14008d566  mov     rax, [rax]
0x14008d569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d56e  mov     esi, eax
0x14008d570  test    eax, eax
0x14008d572  js      short loc_14008D58C
0x14008d574  mov     rcx, [rsp+68h+var_40]
0x14008d579  mov     rax, [rcx]
0x14008d57c  lea     rdx, [rsp+68h+arg_0]
0x14008d581  mov     rax, [rax+18h]
0x14008d585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d58a  mov     esi, eax
0x14008d58c  lea     rcx, [rsp+68h+var_40]
0x14008d591  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008d596  test    esi, esi
0x14008d598  jns     short loc_14008D5DB
0x14008d59a  mov     rcx, [rsp+68h]; this
0x14008d59f  mov     r9d, esi; char *
0x14008d5a2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\Server\\inc\\Resourc"...
0x14008d5a9  mov     edx, 133h; void *
0x14008d5ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d5b3  nop
0x14008d5b4  lea     rcx, [rsp+68h+arg_0]
0x14008d5b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008d5be  nop
0x14008d5bf  lea     rcx, [rsp+68h+var_48]
0x14008d5c4  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14008d5c9  nop
0x14008d5ca  lea     rcx, [rsp+68h+arg_20]
0x14008d5d2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d5d7  mov     eax, esi
0x14008d5d9  jmp     short loc_14008D655
0x14008d5db  mov     rax, [rdi+8]
0x14008d5df  cmp     rax, [rdi+10h]
0x14008d5e3  jz      short loc_14008D5F9
0x14008d5e5  lea     rdx, [rsp+68h+arg_0]
0x14008d5ea  mov     rcx, rax
0x14008d5ed  call    ??0?$com_ptr_t@UIAudioMediaType@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>::com_ptr_t<IAudioMediaType,wil::err_returncode_policy>(wil::com_ptr_t<IAudioMediaType,wil::err_returncode_policy> const &)
0x14008d5f2  add     qword ptr [rdi+8], 8
0x14008d5f7  jmp     short loc_14008D609
0x14008d5f9  lea     r8, [rsp+68h+arg_0]
0x14008d5fe  mov     rdx, rax
0x14008d601  mov     rcx, rdi
0x14008d604  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &)
0x14008d609  mov     rax, [rbx]
0x14008d60c  mov     r8, [rsp+68h+arg_18]
0x14008d614  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14008d61b  mov     rcx, rbx
0x14008d61e  mov     rax, [rax]
0x14008d621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008d626  nop
0x14008d627  lea     rcx, [rsp+68h+arg_0]
0x14008d62c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008d631  nop
0x14008d632  lea     rcx, [rsp+68h+var_48]
0x14008d637  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x14008d63c  nop
0x14008d63d  lea     rcx, [rsp+68h+arg_20]
0x14008d645  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14008d64a  xor     eax, eax
0x14008d64c  jmp     short loc_14008D655
0x14008d64e  mov     eax, dword ptr [rsp+68h+arg_18]
0x14008d655  add     rsp, 30h
0x14008d659  pop     r15
0x14008d65b  pop     r14
0x14008d65d  pop     r13
0x14008d65f  pop     r12
0x14008d661  pop     rdi
0x14008d662  pop     rsi
0x14008d663  pop     rbx
0x14008d664  retn
```
