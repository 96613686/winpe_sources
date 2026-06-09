# AppReadiness::Tasks::StoreInstall::OnStarted(void)

- ea: `0x180027c30`
- end: `0x180027e40`
- name: `?OnStarted@StoreInstall@Tasks@AppReadiness@@MEAAXXZ`
- size: `528`
- prototype: `void __fastcall(AppReadiness::Tasks::StoreInstall *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x1800148b0`
- `0x1800203d8`
- `0x180027a4c`
- `0x180027bec`
- `0x180027c00`
- `0x180027c30`
- `0x180027f5c`
- `0x18002a970`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027df0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027df0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027cf3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027cf3`
- `ntdll!NtQuerySystemTime` at `0x180027de1`
- `ntdll!NtQuerySystemTime` at `0x180027de1`

## string_xrefs

- `0x180027cd4`: `Windows.System.Threading.ThreadPoolTimer`
- `0x180027d18`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer).Get(), threadpool.GetAddressOf())`
- `0x180027d05`: `onecoreuap\shell\appreadiness\src\tasks\storeinstall.cpp`
- `0x180027d77`: `onecoreuap\shell\appreadiness\src\tasks\storeinstall.cpp`
- `0x180027d11`: `AppReadiness::Tasks::StoreInstall::OnStarted`
- `0x180027d83`: `AppReadiness::Tasks::StoreInstall::OnStarted`
- `0x180027d8a`: `threadpool->CreatePeriodicTimer(this, c_HeartbeatTimer, &timer)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall AppReadiness::Tasks::StoreInstall::OnStarted(AppReadiness::Tasks::StoreInstall *this)
{
  _lambda_da01eb4ab7a923874623b28f6fc458c9_ *v2; // rax
  __int64 v3; // r9
  _BYTE *v4; // rdx
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, char *, __int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // [rsp+30h] [rbp-59h] BYREF
  __int64 v11; // [rsp+38h] [rbp-51h] BYREF
  __int64 v12; // [rsp+40h] [rbp-49h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+48h] [rbp-41h] BYREF
  __int64 v14; // [rsp+60h] [rbp-29h]
  _BYTE v15[56]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE *v16; // [rsp+A8h] [rbp+1Fh]

  v12 = 0;
  v11 = 0;
  (*(void (__fastcall **)(AppReadiness::Tasks::StoreInstall *))(*(_QWORD *)this + 112LL))(this);
  v2 = _lambda_da01eb4ab7a923874623b28f6fc458c9_::_lambda_da01eb4ab7a923874623b28f6fc458c9_(
         (_lambda_da01eb4ab7a923874623b28f6fc458c9_ *)&pExceptionObject,
         (struct AppReadiness::Api *)&v12,
         this);
  std::function_void___cdecl_void__::function_void___cdecl_void____lambda_5f1a8c03a16694e881af1c8ac0401acd__0_(v15, v2);
  AppReadiness::User::ExecuteUnderContext(v3, (__int64)v15);
  if ( v16 )
  {
    v4 = v15;
    LOBYTE(v4) = v16 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v4);
  }
  v10 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &pExceptionObject,
    L"Windows.System.Threading.ThreadPoolTimer",
    0x29u,
    0x28u);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v10);
  if ( ActivationFactory < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      ActivationFactory,
      "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer)."
      "Get(), threadpool.GetAddressOf())",
      "AppReadiness::Tasks::StoreInstall::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storeinstall.cpp",
      53);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v6 = v10;
  v7 = *(__int64 (__fastcall **)(__int64, char *, __int64, __int64 *))(*(_QWORD *)v10 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  v8 = v7(v6, (char *)this + 320, 1500000000, &v11);
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v8,
      "threadpool->CreatePeriodicTimer(this, c_HeartbeatTimer, &timer)",
      "AppReadiness::Tasks::StoreInstall::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storeinstall.cpp",
      54);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&pExceptionObject, (char *)this + 56);
  std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>((_QWORD *)this + 43, (__int64)&v11);
  std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>((_QWORD *)this + 42, (__int64)&v12);
  NtQuerySystemTime((PLARGE_INTEGER)this + 44);
  if ( pExceptionObject.Reserved.Reserved1 )
    ReleaseSRWLockExclusive((PSRWLOCK)pExceptionObject.Reserved.Reserved1);
  v9 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
}

```

## disassembly

```asm
0x180027c30  push    rbp
0x180027c32  push    rbx
0x180027c33  push    rsi
0x180027c34  push    rdi
0x180027c35  lea     rbp, [rsp-3Fh]
0x180027c3a  sub     rsp, 0C8h
0x180027c41  mov     rax, cs:__security_cookie
0x180027c48  xor     rax, rsp
0x180027c4b  mov     [rbp+57h+var_30], rax
0x180027c4f  mov     rsi, rcx
0x180027c52  mov     [rbp+57h+var_A0], 0
0x180027c5a  mov     [rbp+57h+var_A8], 0
0x180027c62  mov     rax, [rcx]
0x180027c65  mov     rax, [rax+70h]
0x180027c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c6e  mov     r9, rax
0x180027c71  mov     r8, rsi; enum APPREADINESS_PACKAGE_SOURCE *
0x180027c74  lea     rdx, [rbp+57h+var_A0]; struct AppReadiness::Api *
0x180027c78  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027c7c  call    ??0_lambda_da01eb4ab7a923874623b28f6fc458c9_@@QEAA@PEAVApi@AppReadiness@@AEAW4APPREADINESS_PACKAGE_SOURCE@@@Z; _lambda_da01eb4ab7a923874623b28f6fc458c9_::_lambda_da01eb4ab7a923874623b28f6fc458c9_(AppReadiness::Api *,APPREADINESS_PACKAGE_SOURCE &)
0x180027c81  mov     rdx, rax
0x180027c84  lea     rcx, [rbp+57h+var_70]
0x180027c88  call    std__function_void___cdecl_void____function_void___cdecl_void____lambda_5f1a8c03a16694e881af1c8ac0401acd__0_
0x180027c8d  nop
0x180027c8e  lea     rdx, [rbp+57h+var_70]
0x180027c92  mov     rcx, r9
0x180027c95  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x180027c9a  nop
0x180027c9b  mov     rcx, [rbp+57h+var_38]
0x180027c9f  test    rcx, rcx
0x180027ca2  jz      short loc_180027CBA
0x180027ca4  mov     rax, [rcx]
0x180027ca7  lea     rdx, [rbp+57h+var_70]
0x180027cab  cmp     rcx, rdx
0x180027cae  setnz   dl
0x180027cb1  mov     rax, [rax+20h]
0x180027cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cba  mov     [rbp+57h+var_B0], 0
0x180027cc2  mov     [rbp+57h+var_80], 0
0x180027cca  mov     r9d, 28h ; '('; unsigned int
0x180027cd0  lea     r8d, [r9+1]; unsigned int
0x180027cd4  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x180027cdb  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x180027cdf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027ce4  lea     r8, [rbp+57h+var_B0]
0x180027ce8  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x180027cef  mov     rcx, [rbp+57h+var_80]
0x180027cf3  call    cs:__imp_RoGetActivationFactory
0x180027cf9  test    eax, eax
0x180027cfb  jns     short loc_180027D3B
0x180027cfd  mov     [rsp+0E0h+var_B8], 35h ; '5'; int
0x180027d05  lea     rcx, aOnecoreuapShel_30; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180027d0c  mov     [rsp+0E0h+var_C0], rcx; char *
0x180027d11  lea     r9, aAppreadinessTa_7; "AppReadiness::Tasks::StoreInstall::OnSt"...
0x180027d18  lea     r8, aWindowsFoundat_12; "Windows::Foundation::GetActivationFacto"...
0x180027d1f  mov     edx, eax; int
0x180027d21  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027d25  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180027d2a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180027d31  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027d35  call    _CxxThrowException_0
0x180027d3b  mov     rdi, [rbp+57h+var_B0]
0x180027d3f  mov     rax, [rdi]
0x180027d42  mov     rbx, [rax+30h]
0x180027d46  lea     rcx, [rbp+57h+var_A8]
0x180027d4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027d4f  lea     rdx, [rsi+140h]
0x180027d56  lea     r9, [rbp+57h+var_A8]
0x180027d5a  mov     r8d, 59682F00h
0x180027d60  mov     rcx, rdi
0x180027d63  mov     rax, rbx
0x180027d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d6b  test    eax, eax
0x180027d6d  jns     short loc_180027DAD
0x180027d6f  mov     [rsp+0E0h+var_B8], 36h ; '6'; int
0x180027d77  lea     rcx, aOnecoreuapShel_30; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180027d7e  mov     [rsp+0E0h+var_C0], rcx; char *
0x180027d83  lea     r9, aAppreadinessTa_7; "AppReadiness::Tasks::StoreInstall::OnSt"...
0x180027d8a  lea     r8, aThreadpoolCrea_0; "threadpool->CreatePeriodicTimer(this, c"...
0x180027d91  mov     edx, eax; int
0x180027d93  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027d97  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180027d9c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180027da3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027da7  call    _CxxThrowException_0
0x180027dad  lea     rdx, [rsi+38h]
0x180027db1  lea     rcx, [rbp+57h+pExceptionObject]
0x180027db5  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180027dba  lea     rcx, [rsi+158h]
0x180027dc1  lea     rdx, [rbp+57h+var_A8]
0x180027dc5  call    ??$swap@V?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@$0A@@std@@YAXAEAV?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@0@Z; std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &,Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &)
0x180027dca  lea     rcx, [rsi+150h]
0x180027dd1  lea     rdx, [rbp+57h+var_A0]
0x180027dd5  call    ??$swap@V?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@$0A@@std@@YAXAEAV?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@0@Z; std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &,Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &)
0x180027dda  lea     rcx, [rsi+160h]; SystemTime
0x180027de1  call    cs:__imp_NtQuerySystemTime
0x180027de7  mov     rcx, qword ptr [rbp+57h+pExceptionObject]; SRWLock
0x180027deb  test    rcx, rcx
0x180027dee  jz      short loc_180027DF7
0x180027df0  call    cs:__imp_ReleaseSRWLockExclusive
0x180027df6  nop
0x180027df7  mov     rcx, [rbp+57h+var_B0]
0x180027dfb  test    rcx, rcx
0x180027dfe  jz      short loc_180027E15
0x180027e00  mov     [rbp+57h+var_B0], 0
0x180027e08  mov     rax, [rcx]
0x180027e0b  mov     rax, [rax+10h]
0x180027e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e14  nop
0x180027e15  lea     rcx, [rbp+57h+var_A8]
0x180027e19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027e1e  nop
0x180027e1f  lea     rcx, [rbp+57h+var_A0]
0x180027e23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027e28  mov     rcx, [rbp+57h+var_30]
0x180027e2c  xor     rcx, rsp; StackCookie
0x180027e2f  call    __security_check_cookie
0x180027e34  add     rsp, 0C8h
0x180027e3b  pop     rdi
0x180027e3c  pop     rsi
0x180027e3d  pop     rbx
0x180027e3e  pop     rbp
0x180027e3f  retn
```
