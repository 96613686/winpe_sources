# Windows::Internal::AssignedAccess::RegistryDataStore::MigrateIfNeeded(void)

- ea: `0x180054f30`
- end: `0x1800552ef`
- name: `?MigrateIfNeeded@RegistryDataStore@AssignedAccess@Internal@Windows@@AEAAJXZ`
- size: `959`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::RegistryDataStore *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054c10`
- `0x180054d30`
- `0x1800555a0`

## callees

- `0x1800088bc`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000f8dc`
- `0x1800147fc`
- `0x18001492c`
- `0x180014aa0`
- `0x180014ad0`
- `0x180014b00`
- `0x180015300`
- `0x180019ae0`
- `0x180019b60`
- `0x18001a660`
- `0x18001a898`
- `0x1800200e4`
- `0x180051f48`
- `0x180054f30`
- `0x18005590c`
- `0x180096010`

## string_xrefs

- `0x180054fe8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055044`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055085`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x18005512b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055182`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x1800551f3`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`
- `0x180055238`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AssignedAccess::RegistryDataStore::MigrateIfNeeded(
        Windows::Internal::AssignedAccess::RegistryDataStore *this)
{
  const enum StoreVersion *v2; // r12
  __int64 v4; // rbx
  void *v5; // rax
  __int64 v6; // r15
  int v7; // r14d
  int v8; // edi
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // r13
  __int64 v14; // r9
  int v15; // eax
  int v16; // r15d
  int View; // eax
  __int64 v18; // rdx
  __int64 v19; // rbx
  void *v20; // rax
  __int64 v21; // rdi
  int v22; // eax
  _QWORD *v23; // rdi
  _QWORD *v24; // r15
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  _QWORD v29[3]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v30[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  void *v32; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+50h] BYREF
  void *v34; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v35; // [rsp+B8h] [rbp+60h] BYREF

  v2 = (Windows::Internal::AssignedAccess::RegistryDataStore *)((char *)this + 56);
  if ( *((_DWORD *)this + 10) == *((_DWORD *)this + 14) )
    return 0;
  std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(v30);
  v4 = 0;
  v35 = 0;
  v5 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v32 = v5;
  v6 = 0;
  if ( v5 )
  {
    v6 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>(v5);
    v32 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(&v32);
  v7 = -2147024882;
  if ( v6 )
  {
    v8 = 0;
    v4 = v6;
    v35 = v6;
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v8 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(Windows::Internal::AssignedAccess::RegistryDataStore *, _QWORD *))(*(_QWORD *)this + 32LL))(
            this,
            v30);
    v8 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v10 = 178;
      goto LABEL_12;
    }
    v12 = v30[0];
    v13 = v30[1];
    while ( v12 != v13 )
    {
      wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>(
        &v32,
        v12);
      LOBYTE(v14) = 1;
      v15 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::InsertAtInternal(
              v4,
              0,
              v32,
              v14);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
          (const char *)(unsigned int)v15,
          v29[0]);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
        v8 = v16;
        goto LABEL_47;
      }
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
      v12 += 8;
    }
    v32 = 0;
    View = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::GetView(
             v4,
             &v32);
    v8 = View;
    if ( View >= 0 )
    {
      View = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v32);
      v8 = View;
      if ( View >= 0 )
      {
        std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(v29);
        v19 = 0;
        v33 = 0;
        v20 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
        v34 = v20;
        v21 = 0;
        if ( v20 )
        {
          v21 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>(v20);
          v34 = 0;
        }
        Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(&v34);
        if ( v21 )
        {
          v7 = 0;
          v19 = v21;
          v33 = v21;
        }
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBE,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
            (const char *)(unsigned int)v7,
            v29[0]);
LABEL_30:
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v33);
          std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v29);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
          v8 = v7;
          goto LABEL_47;
        }
        v22 = (*(__int64 (__fastcall **)(Windows::Internal::AssignedAccess::RegistryDataStore *, _QWORD *))(*(_QWORD *)this + 48LL))(
                this,
                v29);
        v8 = v22;
        if ( v22 >= 0 )
        {
          v23 = (_QWORD *)v29[0];
          v24 = (_QWORD *)v29[1];
          while ( v23 != v24 )
          {
            wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>(
              &v34,
              *v23);
            LOBYTE(v25) = 1;
            v26 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::InsertAtInternal(
                    v19,
                    0,
                    v34,
                    v25);
            v7 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC2,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
                (const char *)(unsigned int)v26,
                v29[0]);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
              goto LABEL_30;
            }
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
            ++v23;
          }
          v34 = 0;
          v27 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::GetView(
                  v19,
                  &v34);
          v8 = v27;
          if ( v27 >= 0 )
          {
            v27 = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)this + 6) + 40LL))(
                    *((_QWORD *)this + 6),
                    v34);
            v8 = v27;
            if ( v27 >= 0 )
            {
              v27 = Windows::Internal::AssignedAccess::RegistryDataStore::SetVersion(this, v2);
              v8 = v27;
              if ( v27 >= 0 )
              {
                *((_DWORD *)this + 10) = *(_DWORD *)v2;
                wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(
                  (char *)this + 32,
                  (char *)this + 48);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
                wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v33);
                std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v29);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
                v8 = 0;
                goto LABEL_47;
              }
              v28 = 200;
            }
            else
            {
              v28 = 198;
            }
          }
          else
          {
            v28 = 197;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
            (const char *)(unsigned int)v27,
            v29[0]);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
            (const char *)(unsigned int)v22,
            v29[0]);
        }
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v33);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v29);
        goto LABEL_21;
      }
      v18 = 185;
    }
    else
    {
      v18 = 184;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
      (const char *)(unsigned int)View,
      v29[0]);
LABEL_21:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
    goto LABEL_47;
  }
  v9 = (unsigned int)v8;
  v10 = 177;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastore.cpp",
    (const char *)v9,
    v29[0]);
LABEL_47:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v35);
  std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180054f30  push    rbp
0x180054f32  push    rbx
0x180054f33  push    rsi
0x180054f34  push    rdi
0x180054f35  push    r12
0x180054f37  push    r13
0x180054f39  push    r14
0x180054f3b  push    r15
0x180054f3d  mov     rbp, rsp
0x180054f40  sub     rsp, 58h
0x180054f44  mov     rsi, rcx
0x180054f47  lea     r12, [rcx+38h]
0x180054f4b  mov     eax, [r12]
0x180054f4f  cmp     [rcx+28h], eax
0x180054f52  jnz     short loc_180054F5B
0x180054f54  xor     eax, eax
0x180054f56  jmp     loc_1800552DE
0x180054f5b  lea     rcx, [rbp+var_20]
0x180054f5f  call    ??0?$vector@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@V?$allocator@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@@2@@std@@QEAA@XZ; std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(void)
0x180054f64  nop
0x180054f65  xor     ebx, ebx
0x180054f67  mov     [rbp+arg_18], rbx
0x180054f6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180054f72  mov     ecx, 0B8h; unsigned __int64
0x180054f77  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180054f7c  mov     [rbp+arg_0], rax
0x180054f80  xor     r15d, r15d
0x180054f83  test    rax, rax
0x180054f86  jz      short loc_180054F97
0x180054f88  mov     rcx, rax
0x180054f8b  call    ??0?$Vector@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::permission)
0x180054f90  mov     r15, rax
0x180054f93  mov     [rbp+arg_0], rbx
0x180054f97  lea     rcx, [rbp+arg_0]
0x180054f9b  call    ??1?$MakeAllocator@U?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(void)
0x180054fa0  mov     r14d, 8007000Eh
0x180054fa6  test    r15, r15
0x180054fa9  jnz     short loc_180054FB0
0x180054fab  mov     edi, r14d
0x180054fae  jmp     short loc_180054FB9
0x180054fb0  xor     edi, edi
0x180054fb2  mov     rbx, r15
0x180054fb5  mov     [rbp+arg_18], rbx
0x180054fb9  test    edi, edi
0x180054fbb  jns     short loc_180054FC7
0x180054fbd  mov     r9d, edi
0x180054fc0  mov     edx, 0B1h
0x180054fc5  jmp     short loc_180054FE8
0x180054fc7  mov     rax, [rsi]
0x180054fca  lea     rdx, [rbp+var_20]
0x180054fce  mov     rcx, rsi
0x180054fd1  mov     rax, [rax+20h]
0x180054fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fda  mov     edi, eax
0x180054fdc  test    eax, eax
0x180054fde  jns     short loc_180054FFD
0x180054fe0  mov     r9d, eax; char *
0x180054fe3  mov     edx, 0B2h; void *
0x180054fe8  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180054fef  mov     rcx, [rbp+40h]; this
0x180054ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ff8  jmp     loc_1800552C9
0x180054ffd  mov     rdi, [rbp+var_20]
0x180055001  mov     r13, [rbp+var_18]
0x180055005  cmp     rdi, r13
0x180055008  jz      short loc_180055066
0x18005500a  mov     rdx, rdi
0x18005500d  lea     rcx, [rbp+arg_0]
0x180055011  call    ??0?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>(wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> const &)
0x180055016  mov     r9b, 1
0x180055019  mov     r8, [rbp+arg_0]
0x18005501d  xor     edx, edx
0x18005501f  mov     rcx, rbx
0x180055022  call    ?InsertAtInternal@?$Vector@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIAssignedAccessProfile@AssignedAccess@25@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::InsertAtInternal(uint,Windows::Internal::AssignedAccess::IAssignedAccessProfile *,bool)
0x180055027  mov     r15d, eax
0x18005502a  test    eax, eax
0x18005502c  js      short loc_18005503D
0x18005502e  lea     rcx, [rbp+arg_0]
0x180055032  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180055037  add     rdi, 8
0x18005503b  jmp     short loc_180055005
0x18005503d  mov     rcx, [rbp+40h]; this
0x180055041  mov     r9d, r15d; char *
0x180055044  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005504b  mov     edx, 0B5h; void *
0x180055050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055055  lea     rcx, [rbp+arg_0]
0x180055059  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005505e  mov     edi, r15d
0x180055061  jmp     loc_1800552C9
0x180055066  mov     [rbp+arg_0], 0
0x18005506e  lea     rdx, [rbp+arg_0]
0x180055072  mov     rcx, rbx
0x180055075  call    ?GetView@?$Vector@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessProfile *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessProfile *,1,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *> * *)
0x18005507a  mov     edi, eax
0x18005507c  test    eax, eax
0x18005507e  jns     short loc_1800550A7
0x180055080  mov     edx, 0B8h; void *
0x180055085  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005508c  mov     r9d, eax; char *
0x18005508f  mov     rcx, [rbp+40h]; this
0x180055093  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055098  nop
0x180055099  lea     rcx, [rbp+arg_0]
0x18005509d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800550a2  jmp     loc_1800552C9
0x1800550a7  lea     r13, [rsi+30h]
0x1800550ab  mov     rcx, [r13+0]
0x1800550af  mov     rax, [rcx]
0x1800550b2  mov     rdx, [rbp+arg_0]
0x1800550b6  mov     rax, [rax+18h]
0x1800550ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550bf  mov     edi, eax
0x1800550c1  test    eax, eax
0x1800550c3  jns     short loc_1800550CC
0x1800550c5  mov     edx, 0B9h
0x1800550ca  jmp     short loc_180055085
0x1800550cc  lea     rcx, [rbp+var_38]
0x1800550d0  call    ??0?$vector@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@V?$allocator@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@@2@@std@@QEAA@XZ; std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(void)
0x1800550d5  nop
0x1800550d6  xor     ebx, ebx
0x1800550d8  mov     [rbp+arg_8], rbx
0x1800550dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800550e3  mov     ecx, 0B8h; unsigned __int64
0x1800550e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800550ed  mov     [rbp+arg_10], rax
0x1800550f1  xor     edi, edi
0x1800550f3  test    rax, rax
0x1800550f6  jz      short loc_180055107
0x1800550f8  mov     rcx, rax
0x1800550fb  call    ??0?$Vector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::permission)
0x180055100  mov     rdi, rax
0x180055103  mov     [rbp+arg_10], rbx
0x180055107  lea     rcx, [rbp+arg_10]
0x18005510b  call    ??1?$MakeAllocator@U?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(void)
0x180055110  test    rdi, rdi
0x180055113  jz      short loc_18005511F
0x180055115  xor     r14d, r14d
0x180055118  mov     rbx, rdi
0x18005511b  mov     [rbp+arg_8], rbx
0x18005511f  test    r14d, r14d
0x180055122  jns     short loc_180055162
0x180055124  mov     rcx, [rbp+40h]; this
0x180055128  mov     r9d, r14d; char *
0x18005512b  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055132  mov     edx, 0BEh; void *
0x180055137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005513c  nop
0x18005513d  lea     rcx, [rbp+arg_8]
0x180055141  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x180055146  nop
0x180055147  lea     rcx, [rbp+var_38]
0x18005514b  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x180055150  nop
0x180055151  lea     rcx, [rbp+arg_0]
0x180055155  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005515a  mov     edi, r14d
0x18005515d  jmp     loc_1800552C9
0x180055162  mov     rax, [rsi]
0x180055165  lea     rdx, [rbp+var_38]
0x180055169  mov     rcx, rsi
0x18005516c  mov     rax, [rax+30h]
0x180055170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055175  mov     edi, eax
0x180055177  test    eax, eax
0x180055179  jns     short loc_1800551AC
0x18005517b  mov     rcx, [rbp+40h]; this
0x18005517f  mov     r9d, eax; char *
0x180055182  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055189  mov     edx, 0BFh; void *
0x18005518e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055193  nop
0x180055194  lea     rcx, [rbp+arg_8]
0x180055198  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x18005519d  nop
0x18005519e  lea     rcx, [rbp+var_38]
0x1800551a2  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x1800551a7  jmp     loc_180055099
0x1800551ac  mov     rdi, [rbp+var_38]
0x1800551b0  mov     r15, [rbp+var_30]
0x1800551b4  cmp     rdi, r15
0x1800551b7  jz      short loc_180055212
0x1800551b9  mov     rdx, [rdi]
0x1800551bc  lea     rcx, [rbp+arg_10]
0x1800551c0  call    ??0?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIAssignedAccessConfig@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>(Windows::Internal::AssignedAccess::IAssignedAccessConfig *)
0x1800551c5  mov     r9b, 1
0x1800551c8  mov     r8, [rbp+arg_10]
0x1800551cc  xor     edx, edx
0x1800551ce  mov     rcx, rbx
0x1800551d1  call    ?InsertAtInternal@?$Vector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIAssignedAccessConfig@AssignedAccess@25@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::InsertAtInternal(uint,Windows::Internal::AssignedAccess::IAssignedAccessConfig *,bool)
0x1800551d6  mov     r14d, eax
0x1800551d9  test    eax, eax
0x1800551db  js      short loc_1800551EC
0x1800551dd  lea     rcx, [rbp+arg_10]
0x1800551e1  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800551e6  add     rdi, 8
0x1800551ea  jmp     short loc_1800551B4
0x1800551ec  mov     rcx, [rbp+40h]; this
0x1800551f0  mov     r9d, r14d; char *
0x1800551f3  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800551fa  mov     edx, 0C2h; void *
0x1800551ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055204  lea     rcx, [rbp+arg_10]
0x180055208  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005520d  jmp     loc_18005513D
0x180055212  mov     [rbp+arg_10], 0
0x18005521a  lea     rdx, [rbp+arg_10]
0x18005521e  mov     rcx, rbx
0x180055221  call    ?GetView@?$Vector@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@PEAVAssignedAccessConfig@AssignedAccess@Internal@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessConfig *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessConfig *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessConfig *,1,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessConfig *> * *)
0x180055226  mov     edi, eax
0x180055228  test    eax, eax
0x18005522a  jns     short loc_180055253
0x18005522c  mov     edx, 0C5h; void *
0x180055231  mov     rcx, [rbp+40h]; this
0x180055235  mov     r9d, eax; char *
0x180055238  lea     r8, aOnecoreuapBase_54; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005523f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055244  nop
0x180055245  lea     rcx, [rbp+arg_10]
0x180055249  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005524e  jmp     loc_180055194
0x180055253  mov     rcx, [r13+0]
0x180055257  mov     rax, [rcx]
0x18005525a  mov     rdx, [rbp+arg_10]
0x18005525e  mov     rax, [rax+28h]
0x180055262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055267  mov     edi, eax
0x180055269  test    eax, eax
0x18005526b  jns     short loc_180055274
0x18005526d  mov     edx, 0C6h
0x180055272  jmp     short loc_180055231
0x180055274  mov     rdx, r12; enum StoreVersion *
0x180055277  mov     rcx, rsi; this
0x18005527a  call    ?SetVersion@RegistryDataStore@AssignedAccess@Internal@Windows@@AEAAJAEBW4StoreVersion@@@Z; Windows::Internal::AssignedAccess::RegistryDataStore::SetVersion(StoreVersion const &)
0x18005527f  mov     edi, eax
0x180055281  test    eax, eax
0x180055283  jns     short loc_18005528C
0x180055285  mov     edx, 0C8h
0x18005528a  jmp     short loc_180055231
0x18005528c  mov     eax, [r12]
0x180055290  mov     [rsi+28h], eax
0x180055293  lea     rcx, [rsi+20h]
0x180055297  mov     rdx, r13
0x18005529a  call    ??4?$com_ptr_t@UIAssignedAccessDataStore@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessDataStore,wil::err_exception_policy> const &)
0x18005529f  nop
0x1800552a0  lea     rcx, [rbp+arg_10]
0x1800552a4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800552a9  nop
0x1800552aa  lea     rcx, [rbp+arg_8]
0x1800552ae  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x1800552b3  nop
0x1800552b4  lea     rcx, [rbp+var_38]
0x1800552b8  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x1800552bd  nop
0x1800552be  lea     rcx, [rbp+arg_0]
0x1800552c2  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800552c7  xor     edi, edi
0x1800552c9  lea     rcx, [rbp+arg_18]
0x1800552cd  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x1800552d2  nop
0x1800552d3  lea     rcx, [rbp+var_20]
0x1800552d7  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x1800552dc  mov     eax, edi
0x1800552de  add     rsp, 58h
0x1800552e2  pop     r15
0x1800552e4  pop     r14
0x1800552e6  pop     r13
0x1800552e8  pop     r12
0x1800552ea  pop     rdi
0x1800552eb  pop     rsi
0x1800552ec  pop     rbx
0x1800552ed  pop     rbp
0x1800552ee  retn
```
