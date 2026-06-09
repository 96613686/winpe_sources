# OobeEasyConnectTask::RuntimeClassInitialize(_GUID const &)

- ea: `0x18001fc40`
- end: `0x180020217`
- name: `?RuntimeClassInitialize@OobeEasyConnectTask@@QEAAJAEBU_GUID@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(OobeEasyConnectTask *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019d78`

## callees

- `0x180002150`
- `0x18001b1b4`
- `0x18001bdb8`
- `0x18001cb10`
- `0x18001ec20`
- `0x18001fc40`
- `0x180020220`
- `0x1800246b4`
- `0x18002cd20`
- `0x18002d1cc`
- `0x18002d20c`
- `0x18002d6a0`
- `0x180047d08`
- `0x18004a028`
- `0x18004a514`
- `0x18004a658`
- `0x18004a680`
- `0x18004c950`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdd4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdd4`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18001fc75`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18001fc75`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fced`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fdbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fdbc`

## string_xrefs

- `0x18001fc87`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001fd04`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001fd41`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001fd73`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001fdfa`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001fec0`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001ff1e`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001ff7e`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18001ffde`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x18002004e`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x1800200c9`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180020119`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180020155`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall OobeEasyConnectTask::RuntimeClassInitialize(OobeEasyConnectTask *this, const struct _GUID *a2)
{
  const char *v3; // r9
  TraceLoggingCorrelationVector *v5; // rax
  TraceLoggingCorrelationVector *v6; // rax
  void *v7; // rcx
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  int EmbeddedSimSlot; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  HSTRING v16; // rax
  __int64 v17; // rdi
  int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, _QWORD, char *); // rbx
  int v31; // eax
  unsigned int v32; // ebx
  int updated; // eax
  int v34; // eax
  unsigned int v35; // ebx
  __int64 v36; // rax
  _QWORD *v37; // rax
  int ppv; // [rsp+20h] [rbp-88h]
  __int64 v39; // [rsp+30h] [rbp-78h] BYREF
  __int64 v40; // [rsp+38h] [rbp-70h] BYREF
  __int64 v41; // [rsp+40h] [rbp-68h] BYREF
  __int64 v42; // [rsp+48h] [rbp-60h] BYREF
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *((struct _GUID *)this + 5) = *a2;
  if ( !(unsigned int)RegisterWaitUntilOOBECompleted(
                        OobeEasyConnectTask::StaticOobeCompletedCallback,
                        this,
                        (char *)this + 120) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x10,
             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
             v3);
  v5 = (TraceLoggingCorrelationVector *)operator new(0x90u);
  v6 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v5);
  v7 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = v6;
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)0x90);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
  Instance = CoCreateInstance(
               &GUID_25d7baff_f559_4d0e_9ea4_b48f936956aa,
               0,
               1u,
               &GUID_99551656_c20f_4840_a833_989d2e861f06,
               (LPVOID *)this + 8);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, OobeEasyConnectTask *, _QWORD))(**((_QWORD **)this + 8) + 24LL))(
            *((_QWORD *)this + 8),
            this,
            0);
    v11 = v10;
    if ( v10 >= 0 )
    {
      EmbeddedSimSlot = MBUtil::GetEmbeddedSimSlot((OobeEasyConnectTask *)((char *)this + 116));
      v13 = EmbeddedSimSlot;
      if ( EmbeddedSimSlot >= 0 )
      {
        v41 = 0;
        v39 = 0;
        v40 = 0;
        if ( WindowsCreateStringReference(L"Windows.Networking.UX.UXManager", 0x1Fu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(
                string,
                &v41);
        v15 = v14;
        if ( v14 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          v39 = 0;
          v42 = 0;
          v16 = (HSTRING)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
          string = v16;
          v17 = 0;
          if ( v16 )
          {
            v17 = Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>(v16);
            v42 = v17;
            string = 0;
          }
          Microsoft::WRL::Details::MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>::~MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>(&string);
          if ( v17 )
          {
            v18 = 0;
            v42 = 0;
            v39 = v17;
          }
          else
          {
            v18 = -2147024882;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          if ( v18 >= 0 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 104LL))(v39, 1);
            v20 = v19;
            if ( v19 >= 0 )
            {
              v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 104LL))(v39, 3);
              v22 = v21;
              if ( v21 >= 0 )
              {
                v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 104LL))(v39, 2);
                v24 = v23;
                if ( v23 >= 0 )
                {
                  v25 = v39;
                  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 64LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                  v27 = v26(v25, &v40);
                  v28 = v27;
                  if ( v27 >= 0 )
                  {
                    v29 = v41;
                    v30 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)v41 + 56LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
                    v31 = v30(v29, v40, 0, (char *)this + 136);
                    v32 = v31;
                    if ( v31 >= 0 )
                    {
                      updated = OobeEasyConnectTask::UpdateConnectivity(this);
                      if ( updated < 0 )
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x26,
                          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                          (const char *)(unsigned int)updated,
                          ppv);
                      v34 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 17) + 88LL))(
                              *((_QWORD *)this + 17),
                              (char *)this + 8,
                              (char *)this + 144);
                      v35 = v34;
                      if ( v34 >= 0 )
                      {
                        v36 = *((_QWORD *)this + 149);
                        if ( v36 && (*(_QWORD *)(v36 + 248) || (*(_DWORD *)(v36 + 72) & 0x100) != 0) )
                          wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>::reset((char *)this + 1192);
                        v37 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data((char *)this + 1192);
                        tip2::details::shared_data<1,0,0>::start(*v37 + 8LL, &string);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                        return 0;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x29,
                          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                          (const char *)(unsigned int)v34,
                          ppv);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                        return v35;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x23,
                        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                        (const char *)(unsigned int)v31,
                        ppv);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                      return v32;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x22,
                      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                      (const char *)(unsigned int)v27,
                      ppv);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                    return v28;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x21,
                    (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                    (const char *)(unsigned int)v23,
                    ppv);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                  return v24;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x20,
                  (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                  (const char *)(unsigned int)v21,
                  ppv);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                return v22;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1F,
                (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                (const char *)(unsigned int)v19,
                ppv);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              return v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E,
              (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
              (const char *)(unsigned int)v18,
              ppv);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            return (unsigned int)v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
            (const char *)(unsigned int)v14,
            ppv);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
          (const char *)(unsigned int)EmbeddedSimSlot,
          ppv);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
        (const char *)(unsigned int)v10,
        ppv);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v9;
  }
}

```

## disassembly

```asm
0x18001fc40  push    rbx
0x18001fc42  push    rsi
0x18001fc43  push    rdi
0x18001fc44  push    r14
0x18001fc46  sub     rsp, 88h
0x18001fc4d  mov     rax, cs:__security_cookie
0x18001fc54  xor     rax, rsp
0x18001fc57  mov     [rsp+0A8h+var_38], rax
0x18001fc5c  mov     rsi, rcx
0x18001fc5f  movups  xmm0, xmmword ptr [rdx]
0x18001fc62  movdqu  xmmword ptr [rcx+50h], xmm0
0x18001fc67  lea     r8, [rcx+78h]
0x18001fc6b  mov     rdx, rcx
0x18001fc6e  lea     rcx, ?StaticOobeCompletedCallback@OobeEasyConnectTask@@SAXPEAX@Z; OobeEasyConnectTask::StaticOobeCompletedCallback(void *)
0x18001fc75  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x18001fc7b  test    eax, eax
0x18001fc7d  jnz     short loc_18001FC9B
0x18001fc7f  mov     rcx, [rsp+0A8h]; this
0x18001fc87  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fc8e  lea     edx, [rax+10h]; void *
0x18001fc91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fc96  jmp     loc_1800201FC
0x18001fc9b  mov     ebx, 90h
0x18001fca0  mov     ecx, ebx; Size
0x18001fca2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fca7  mov     rcx, rax; this
0x18001fcaa  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18001fcaf  mov     rcx, [rsi+68h]; void *
0x18001fcb3  mov     [rsi+68h], rax
0x18001fcb7  test    rcx, rcx
0x18001fcba  jz      short loc_18001FCC3
0x18001fcbc  mov     edx, ebx; struct std::nothrow_t *
0x18001fcbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fcc3  lea     rdi, [rsi+40h]
0x18001fcc7  mov     rcx, rdi
0x18001fcca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fccf  mov     qword ptr [rsp+0A8h+ppv], rdi; int
0x18001fcd4  lea     r9, _GUID_99551656_c20f_4840_a833_989d2e861f06; riid
0x18001fcdb  mov     r14d, 1
0x18001fce1  mov     r8d, r14d; dwClsContext
0x18001fce4  xor     edx, edx; pUnkOuter
0x18001fce6  lea     rcx, _GUID_25d7baff_f559_4d0e_9ea4_b48f936956aa; rclsid
0x18001fced  call    cs:__imp_CoCreateInstance
0x18001fcf3  mov     ebx, eax
0x18001fcf5  test    eax, eax
0x18001fcf7  jns     short loc_18001FD1B
0x18001fcf9  mov     rcx, [rsp+0A8h]; this
0x18001fd01  mov     r9d, eax; char *
0x18001fd04  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fd0b  lea     edx, [r14+13h]; void *
0x18001fd0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd14  mov     eax, ebx
0x18001fd16  jmp     loc_1800201FC
0x18001fd1b  mov     rcx, [rdi]
0x18001fd1e  mov     rax, [rcx]
0x18001fd21  xor     r8d, r8d
0x18001fd24  mov     rdx, rsi
0x18001fd27  mov     rax, [rax+18h]
0x18001fd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd30  mov     ebx, eax
0x18001fd32  test    eax, eax
0x18001fd34  jns     short loc_18001FD59
0x18001fd36  mov     rcx, [rsp+0A8h]; this
0x18001fd3e  mov     r9d, eax; char *
0x18001fd41  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fd48  mov     edx, 15h; void *
0x18001fd4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd52  mov     eax, ebx
0x18001fd54  jmp     loc_1800201FC
0x18001fd59  lea     rcx, [rsi+74h]; enum SimSlot *
0x18001fd5d  call    ?GetEmbeddedSimSlot@MBUtil@@SAJPEAW4SimSlot@@@Z; MBUtil::GetEmbeddedSimSlot(SimSlot *)
0x18001fd62  mov     ebx, eax
0x18001fd64  test    eax, eax
0x18001fd66  jns     short loc_18001FD8B
0x18001fd68  mov     rcx, [rsp+0A8h]; this
0x18001fd70  mov     r9d, eax; char *
0x18001fd73  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fd7a  mov     edx, 17h; void *
0x18001fd7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd84  mov     eax, ebx
0x18001fd86  jmp     loc_1800201FC
0x18001fd8b  mov     [rsp+0A8h+var_68], 0
0x18001fd94  mov     [rsp+0A8h+var_78], 0
0x18001fd9d  mov     [rsp+0A8h+var_70], 0
0x18001fda6  lea     r9, [rsp+0A8h+string]; string
0x18001fdab  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x18001fdb0  mov     edx, 1Fh; length
0x18001fdb5  lea     rcx, ?RuntimeClass_Windows_Networking_UX_UXManager@@3QBGB; "Windows.Networking.UX.UXManager"
0x18001fdbc  call    cs:__imp_WindowsCreateStringReference
0x18001fdc2  test    eax, eax
0x18001fdc4  jns     short loc_18001FDDA
0x18001fdc6  xor     r9d, r9d; lpArguments
0x18001fdc9  xor     r8d, r8d; nNumberOfArguments
0x18001fdcc  mov     edx, r14d; dwExceptionFlags
0x18001fdcf  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001fdd4  call    cs:__imp_RaiseException
0x18001fdda  lea     rdx, [rsp+0A8h+var_68]
0x18001fddf  mov     rcx, [rsp+0A8h+string]
0x18001fde4  call    ??$ActivateInstance@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>)
0x18001fde9  mov     ebx, eax
0x18001fdeb  test    eax, eax
0x18001fded  jns     short loc_18001FE33
0x18001fdef  mov     rcx, [rsp+0A8h]; this
0x18001fdf7  mov     r9d, eax; char *
0x18001fdfa  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fe01  mov     edx, 1Dh; void *
0x18001fe06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe0b  nop
0x18001fe0c  lea     rcx, [rsp+0A8h+var_70]
0x18001fe11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe16  nop
0x18001fe17  lea     rcx, [rsp+0A8h+var_78]
0x18001fe1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe21  nop
0x18001fe22  lea     rcx, [rsp+0A8h+var_68]
0x18001fe27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe2c  mov     eax, ebx
0x18001fe2e  jmp     loc_1800201FC
0x18001fe33  lea     rcx, [rsp+0A8h+var_78]
0x18001fe38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe3d  mov     [rsp+0A8h+var_78], 0
0x18001fe46  mov     [rsp+0A8h+var_60], 0
0x18001fe4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fe56  mov     ecx, 70h ; 'p'; unsigned __int64
0x18001fe5b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fe60  mov     [rsp+0A8h+string], rax
0x18001fe65  xor     edi, edi
0x18001fe67  test    rax, rax
0x18001fe6a  jz      short loc_18001FE85
0x18001fe6c  mov     rcx, rax
0x18001fe6f  call    ??0?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::permission)
0x18001fe74  mov     rdi, rax
0x18001fe77  mov     [rsp+0A8h+var_60], rax
0x18001fe7c  mov     [rsp+0A8h+string], 0
0x18001fe85  lea     rcx, [rsp+0A8h+string]
0x18001fe8a  call    ??1?$MakeAllocator@VMBMediaManager@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>::~MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>(void)
0x18001fe8f  test    rdi, rdi
0x18001fe92  jz      short loc_18001FEA2
0x18001fe94  xor     ebx, ebx
0x18001fe96  mov     [rsp+0A8h+var_60], rbx
0x18001fe9b  mov     [rsp+0A8h+var_78], rdi
0x18001fea0  jmp     short loc_18001FEA7
0x18001fea2  mov     ebx, 8007000Eh
0x18001fea7  lea     rcx, [rsp+0A8h+var_60]
0x18001feac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001feb1  test    ebx, ebx
0x18001feb3  jns     short loc_18001FEF9
0x18001feb5  mov     rcx, [rsp+0A8h]; this
0x18001febd  mov     r9d, ebx; char *
0x18001fec0  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001fec7  mov     edx, 1Eh; void *
0x18001fecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fed1  nop
0x18001fed2  lea     rcx, [rsp+0A8h+var_70]
0x18001fed7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fedc  nop
0x18001fedd  lea     rcx, [rsp+0A8h+var_78]
0x18001fee2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fee7  nop
0x18001fee8  lea     rcx, [rsp+0A8h+var_68]
0x18001feed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fef2  mov     eax, ebx
0x18001fef4  jmp     loc_1800201FC
0x18001fef9  mov     rcx, [rsp+0A8h+var_78]
0x18001fefe  mov     rax, [rcx]
0x18001ff01  mov     edx, r14d
0x18001ff04  mov     rax, [rax+68h]
0x18001ff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff0d  mov     ebx, eax
0x18001ff0f  test    eax, eax
0x18001ff11  jns     short loc_18001FF57
0x18001ff13  mov     rcx, [rsp+0A8h]; this
0x18001ff1b  mov     r9d, eax; char *
0x18001ff1e  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001ff25  mov     edx, 1Fh; void *
0x18001ff2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff2f  nop
0x18001ff30  lea     rcx, [rsp+0A8h+var_70]
0x18001ff35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff3a  nop
0x18001ff3b  lea     rcx, [rsp+0A8h+var_78]
0x18001ff40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff45  nop
0x18001ff46  lea     rcx, [rsp+0A8h+var_68]
0x18001ff4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff50  mov     eax, ebx
0x18001ff52  jmp     loc_1800201FC
0x18001ff57  mov     rcx, [rsp+0A8h+var_78]
0x18001ff5c  mov     rax, [rcx]
0x18001ff5f  mov     edx, 3
0x18001ff64  mov     rax, [rax+68h]
0x18001ff68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff6d  mov     ebx, eax
0x18001ff6f  test    eax, eax
0x18001ff71  jns     short loc_18001FFB7
0x18001ff73  mov     rcx, [rsp+0A8h]; this
0x18001ff7b  mov     r9d, eax; char *
0x18001ff7e  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001ff85  mov     edx, 20h ; ' '; void *
0x18001ff8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff8f  nop
0x18001ff90  lea     rcx, [rsp+0A8h+var_70]
0x18001ff95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff9a  nop
0x18001ff9b  lea     rcx, [rsp+0A8h+var_78]
0x18001ffa0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ffa5  nop
0x18001ffa6  lea     rcx, [rsp+0A8h+var_68]
0x18001ffab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ffb0  mov     eax, ebx
0x18001ffb2  jmp     loc_1800201FC
0x18001ffb7  mov     rcx, [rsp+0A8h+var_78]
0x18001ffbc  mov     rax, [rcx]
0x18001ffbf  mov     edx, 2
0x18001ffc4  mov     rax, [rax+68h]
0x18001ffc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffcd  mov     ebx, eax
0x18001ffcf  test    eax, eax
0x18001ffd1  jns     short loc_180020017
0x18001ffd3  mov     rcx, [rsp+0A8h]; this
0x18001ffdb  mov     r9d, eax; char *
0x18001ffde  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001ffe5  mov     edx, 21h ; '!'; void *
0x18001ffea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffef  nop
0x18001fff0  lea     rcx, [rsp+0A8h+var_70]
0x18001fff5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fffa  nop
0x18001fffb  lea     rcx, [rsp+0A8h+var_78]
0x180020000  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020005  nop
0x180020006  lea     rcx, [rsp+0A8h+var_68]
0x18002000b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020010  mov     eax, ebx
0x180020012  jmp     loc_1800201FC
0x180020017  mov     rdi, [rsp+0A8h+var_78]
0x18002001c  mov     rax, [rdi]
0x18002001f  mov     rbx, [rax+40h]
0x180020023  lea     rcx, [rsp+0A8h+var_70]
0x180020028  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002002d  lea     rdx, [rsp+0A8h+var_70]
0x180020032  mov     rcx, rdi
0x180020035  mov     rax, rbx
0x180020038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002003d  mov     ebx, eax
0x18002003f  test    eax, eax
0x180020041  jns     short loc_180020087
0x180020043  mov     rcx, [rsp+0A8h]; this
0x18002004b  mov     r9d, eax; char *
0x18002004e  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180020055  mov     edx, 22h ; '"'; void *
0x18002005a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002005f  nop
0x180020060  lea     rcx, [rsp+0A8h+var_70]
0x180020065  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002006a  nop
0x18002006b  lea     rcx, [rsp+0A8h+var_78]
0x180020070  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020075  nop
0x180020076  lea     rcx, [rsp+0A8h+var_68]
0x18002007b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020080  mov     eax, ebx
0x180020082  jmp     loc_1800201FC
0x180020087  mov     rdi, [rsp+0A8h+var_68]
0x18002008c  mov     rax, [rdi]
0x18002008f  mov     rbx, [rax+38h]
0x180020093  lea     r14, [rsi+88h]
0x18002009a  mov     rcx, r14
0x18002009d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200a2  mov     r9, r14
0x1800200a5  xor     r8d, r8d
0x1800200a8  mov     rdx, [rsp+0A8h+var_70]
0x1800200ad  mov     rcx, rdi
0x1800200b0  mov     rax, rbx
0x1800200b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200b8  mov     ebx, eax
0x1800200ba  test    eax, eax
0x1800200bc  jns     short loc_180020102
0x1800200be  mov     rcx, [rsp+0A8h]; this
0x1800200c6  mov     r9d, eax; char *
0x1800200c9  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800200d0  mov     edx, 23h ; '#'; void *
0x1800200d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200da  nop
0x1800200db  lea     rcx, [rsp+0A8h+var_70]
0x1800200e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200e5  nop
0x1800200e6  lea     rcx, [rsp+0A8h+var_78]
0x1800200eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200f0  nop
0x1800200f1  lea     rcx, [rsp+0A8h+var_68]
0x1800200f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200fb  mov     eax, ebx
0x1800200fd  jmp     loc_1800201FC
0x180020102  mov     rcx, rsi; this
0x180020105  call    ?UpdateConnectivity@OobeEasyConnectTask@@AEAAJXZ; OobeEasyConnectTask::UpdateConnectivity(void)
0x18002010a  mov     rcx, [rsp+0A8h]; this
0x180020112  test    eax, eax
0x180020114  jns     short loc_18002012A
0x180020116  mov     r9d, eax; char *
  ... truncated ...
```
