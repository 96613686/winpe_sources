# AppReadiness::Tasks::ActivateApps::OnExecute(void)

- ea: `0x180029660`
- end: `0x180029a30`
- name: `?OnExecute@ActivateApps@Tasks@AppReadiness@@MEAAXXZ`
- size: `976`
- prototype: `void __fastcall(AppReadiness::Tasks::ActivateApps *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x180002a60`
- `0x180005270`
- `0x18000a470`
- `0x1800148b0`
- `0x180019260`
- `0x1800203d8`
- `0x180027a4c`
- `0x180027bc4`
- `0x180027bec`
- `0x180027f5c`
- `0x180029660`
- `0x180029a38`
- `0x18002a970`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002986c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002986c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002975f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002975f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002983e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002983e`

## string_xrefs

- `0x18002973e`: `Windows.System.Threading.ThreadPoolTimer`
- `0x180029784`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer).Get(), threadpool.GetAddressOf())`
- `0x180029804`: `threadpool->CreatePeriodicTimer(this, c_PulseTimeSpan, &timer)`
- `0x180029771`: `onecoreuap\shell\appreadiness\src\tasks\activateapps.cpp`
- `0x1800297f1`: `onecoreuap\shell\appreadiness\src\tasks\activateapps.cpp`
- `0x18002977d`: `AppReadiness::Tasks::ActivateApps::OnExecute`
- `0x1800297fd`: `AppReadiness::Tasks::ActivateApps::OnExecute`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AppReadiness::Tasks::ActivateApps::OnExecute(AppReadiness::Tasks::ActivateApps *this)
{
  __int64 v2; // rax
  _lambda_da01eb4ab7a923874623b28f6fc458c9_ *v3; // rax
  __int64 v4; // r9
  _BYTE *v5; // rdx
  int ActivationFactory; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, char *, __int64, __int64 *); // rbx
  int v9; // eax
  _QWORD *v10; // rbx
  _QWORD *v11; // rdi
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v16; // rdi
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h]
  _QWORD v26[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v27; // [rsp+D8h] [rbp-28h]
  _BYTE v28[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v29; // [rsp+118h] [rbp+18h]

  v2 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *, PSRWLOCK *))(*(_QWORD *)this + 80LL))(
         this,
         &SRWLock);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v2, &v21);
  if ( v20 )
    std::_Ref_count_base::_Decwref(v20);
  if ( *((_QWORD *)this + 44) )
  {
    v23 = 0;
    (*(void (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
    v3 = _lambda_da01eb4ab7a923874623b28f6fc458c9_::_lambda_da01eb4ab7a923874623b28f6fc458c9_(
           (_lambda_da01eb4ab7a923874623b28f6fc458c9_ *)&pExceptionObject,
           this,
           (enum APPREADINESS_PACKAGE_SOURCE *)&v23);
    std::function_void___cdecl_void__::function_void___cdecl_void____lambda_417e7f4a0528b38f03407608d8a7ada3__0_(
      v28,
      v3);
    AppReadiness::User::ExecuteUnderContext(v4, (__int64)v28);
    if ( v29 )
    {
      v5 = v28;
      LOBYTE(v5) = v29 != v28;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v29 + 32LL))(v29, v5);
    }
    v18 = 0;
    v25 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &pExceptionObject,
      L"Windows.System.Threading.ThreadPoolTimer",
      0x29u,
      0x28u);
    ActivationFactory = RoGetActivationFactory(v25, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v18);
    if ( ActivationFactory < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        ActivationFactory,
        "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer"
        ").Get(), threadpool.GetAddressOf())",
        "AppReadiness::Tasks::ActivateApps::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\activateapps.cpp",
        126);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v17 = 0;
    v7 = v18;
    v8 = *(__int64 (__fastcall **)(__int64, char *, __int64, __int64 *))(*(_QWORD *)v18 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    v9 = v8(v7, (char *)this + 232, 50000000, &v17);
    if ( v9 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v9,
        "threadpool->CreatePeriodicTimer(this, c_PulseTimeSpan, &timer)",
        "AppReadiness::Tasks::ActivateApps::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\activateapps.cpp",
        128);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
    GetSystemTimeAsFileTime((LPFILETIME)this + 35);
    *(_OWORD *)((char *)this + 264) = v23;
    std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>((_QWORD *)this + 41, (__int64)&v17);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v10 = (_QWORD *)(v21 + 40);
      if ( *(_QWORD *)(v21 + 64) > 7u )
        v10 = (_QWORD *)*v10;
      v11 = (_QWORD *)((char *)this + 296);
      if ( *((_QWORD *)this + 40) > 7u )
        v11 = (_QWORD *)*v11;
      (*(void (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11, (__int64)v10);
    }
    v12 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
    v26[0] = off_18007B050;
    v26[1] = this;
    v26[2] = &v23;
    v27 = v26;
    AppReadiness::User::ExecuteUnderContext(v12, (__int64)v26);
    if ( v27 )
    {
      v13 = v26;
      LOBYTE(v13) = v27 != v26;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v27 + 32LL))(v27, v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = (_QWORD *)(v21 + 40);
      if ( *(_QWORD *)(v21 + 64) > 7u )
        v15 = (_QWORD *)*v15;
      v16 = (_QWORD *)((char *)this + 296);
      if ( *((_QWORD *)this + 40) > 7u )
        v16 = (_QWORD *)*v16;
      (*(void (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v16, (__int64)v15);
    }
    AppReadiness::Impl::BaseTask::CompleteTask(this, 0);
  }
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
}

```

## disassembly

```asm
0x180029660  push    rbp
0x180029662  push    rbx
0x180029663  push    rsi
0x180029664  push    rdi
0x180029665  lea     rbp, [rsp-38h]
0x18002966a  sub     rsp, 138h
0x180029671  mov     rax, cs:__security_cookie
0x180029678  xor     rax, rsp
0x18002967b  mov     [rbp+50h+var_30], rax
0x18002967f  mov     rsi, rcx
0x180029682  mov     rax, [rcx]
0x180029685  lea     rdx, [rsp+150h+SRWLock]
0x18002968a  mov     rax, [rax+50h]
0x18002968e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029693  lea     rdx, [rsp+150h+var_100]
0x180029698  mov     rcx, rax
0x18002969b  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x1800296a0  nop
0x1800296a1  mov     rcx, [rsp+150h+var_108]; this
0x1800296a6  test    rcx, rcx
0x1800296a9  jz      short loc_1800296B0
0x1800296ab  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800296b0  cmp     qword ptr [rsi+160h], 0
0x1800296b8  jz      loc_18002997E
0x1800296be  xorps   xmm0, xmm0
0x1800296c1  movups  [rsp+150h+var_F0], xmm0
0x1800296c6  mov     rax, [rsi]
0x1800296c9  mov     rcx, rsi
0x1800296cc  mov     rax, [rax+70h]
0x1800296d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296d5  mov     r9, rax
0x1800296d8  lea     r8, [rsp+150h+var_F0]; enum APPREADINESS_PACKAGE_SOURCE *
0x1800296dd  mov     rdx, rsi; struct AppReadiness::Api *
0x1800296e0  lea     rcx, [rsp+150h+pExceptionObject]; this
0x1800296e5  call    ??0_lambda_da01eb4ab7a923874623b28f6fc458c9_@@QEAA@PEAVApi@AppReadiness@@AEAW4APPREADINESS_PACKAGE_SOURCE@@@Z; _lambda_da01eb4ab7a923874623b28f6fc458c9_::_lambda_da01eb4ab7a923874623b28f6fc458c9_(AppReadiness::Api *,APPREADINESS_PACKAGE_SOURCE &)
0x1800296ea  mov     rdx, rax
0x1800296ed  lea     rcx, [rbp+50h+var_70]
0x1800296f1  call    std__function_void___cdecl_void____function_void___cdecl_void____lambda_417e7f4a0528b38f03407608d8a7ada3__0_
0x1800296f6  nop
0x1800296f7  lea     rdx, [rbp+50h+var_70]
0x1800296fb  mov     rcx, r9
0x1800296fe  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x180029703  nop
0x180029704  mov     rcx, [rbp+50h+var_38]
0x180029708  test    rcx, rcx
0x18002970b  jz      short loc_180029723
0x18002970d  mov     rax, [rcx]
0x180029710  lea     rdx, [rbp+50h+var_70]
0x180029714  cmp     rcx, rdx
0x180029717  setnz   dl
0x18002971a  mov     rax, [rax+20h]
0x18002971e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029723  mov     [rsp+150h+var_118], 0
0x18002972c  mov     [rbp+50h+var_C8], 0
0x180029734  mov     r9d, 28h ; '('; unsigned int
0x18002973a  lea     r8d, [r9+1]; unsigned int
0x18002973e  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x180029745  lea     rcx, [rsp+150h+pExceptionObject]; hstringHeader
0x18002974a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002974f  lea     r8, [rsp+150h+var_118]
0x180029754  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x18002975b  mov     rcx, [rbp+50h+var_C8]
0x18002975f  call    cs:__imp_RoGetActivationFactory
0x180029765  test    eax, eax
0x180029767  jns     short loc_1800297A9
0x180029769  mov     dword ptr [rsp+150h+var_128], 7Eh ; '~'; int
0x180029771  lea     rcx, aOnecoreuapShel_12; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180029778  mov     [rsp+150h+var_130], rcx; char *
0x18002977d  lea     r9, aAppreadinessTa_15; "AppReadiness::Tasks::ActivateApps::OnEx"...
0x180029784  lea     r8, aWindowsFoundat_12; "Windows::Foundation::GetActivationFacto"...
0x18002978b  mov     edx, eax; int
0x18002978d  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180029792  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180029797  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002979e  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800297a3  call    _CxxThrowException_0
0x1800297a9  mov     [rsp+150h+var_120], 0
0x1800297b2  mov     rdi, [rsp+150h+var_118]
0x1800297b7  mov     rax, [rdi]
0x1800297ba  mov     rbx, [rax+30h]
0x1800297be  lea     rcx, [rsp+150h+var_120]
0x1800297c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800297c8  lea     rdx, [rsi+0E8h]
0x1800297cf  lea     r9, [rsp+150h+var_120]
0x1800297d4  mov     r8d, 2FAF080h
0x1800297da  mov     rcx, rdi
0x1800297dd  mov     rax, rbx
0x1800297e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297e5  test    eax, eax
0x1800297e7  jns     short loc_180029829
0x1800297e9  mov     dword ptr [rsp+150h+var_128], 80h; int
0x1800297f1  lea     rcx, aOnecoreuapShel_12; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x1800297f8  mov     [rsp+150h+var_130], rcx; char *
0x1800297fd  lea     r9, aAppreadinessTa_15; "AppReadiness::Tasks::ActivateApps::OnEx"...
0x180029804  lea     r8, aThreadpoolCrea; "threadpool->CreatePeriodicTimer(this, c"...
0x18002980b  mov     edx, eax; int
0x18002980d  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180029812  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180029817  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002981e  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180029823  call    _CxxThrowException_0
0x180029829  lea     rdx, [rsi+38h]
0x18002982d  lea     rcx, [rsp+150h+SRWLock]
0x180029832  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180029837  lea     rcx, [rsi+118h]; lpSystemTimeAsFileTime
0x18002983e  call    cs:__imp_GetSystemTimeAsFileTime
0x180029844  movups  xmm0, [rsp+150h+var_F0]
0x180029849  movdqu  xmmword ptr [rsi+108h], xmm0
0x180029851  lea     rcx, [rsi+148h]
0x180029858  lea     rdx, [rsp+150h+var_120]
0x18002985d  call    ??$swap@V?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@$0A@@std@@YAXAEAV?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@0@Z; std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &,Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &)
0x180029862  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x180029867  test    rcx, rcx
0x18002986a  jz      short loc_180029872
0x18002986c  call    cs:__imp_ReleaseSRWLockExclusive
0x180029872  lea     rax, WPP_GLOBAL_Control
0x180029879  mov     rcx, cs:WPP_GLOBAL_Control
0x180029880  cmp     rcx, rax
0x180029883  jz      short loc_1800298F2
0x180029885  test    byte ptr [rcx+1Ch], 4
0x180029889  jz      short loc_1800298F2
0x18002988b  mov     rbx, [rsp+150h+var_100]
0x180029890  add     rbx, 28h ; '('
0x180029894  cmp     qword ptr [rbx+18h], 7
0x180029899  jbe     short loc_18002989E
0x18002989b  mov     rbx, [rbx]
0x18002989e  lea     rdi, [rsi+128h]
0x1800298a5  cmp     qword ptr [rdi+18h], 7
0x1800298aa  jbe     short loc_1800298AF
0x1800298ac  mov     rdi, [rdi]
0x1800298af  mov     rax, [rsi]
0x1800298b2  mov     rcx, rsi
0x1800298b5  mov     rax, [rax+70h]
0x1800298b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298be  lea     r9, [rax+40h]
0x1800298c2  cmp     qword ptr [r9+18h], 7
0x1800298c7  jbe     short loc_1800298CC
0x1800298c9  mov     r9, [r9]
0x1800298cc  mov     edx, 0Ah
0x1800298d1  mov     [rsp+150h+var_128], rbx; __int64
0x1800298d6  mov     [rsp+150h+var_130], rdi; __int64
0x1800298db  lea     r8, WPP_286df770ea7b35d8f7fae2161a5b1577_Traceguids
0x1800298e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298e9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800298ed  call    WPP_SF_SSS
0x1800298f2  mov     rax, [rsi]
0x1800298f5  mov     rcx, rsi
0x1800298f8  mov     rax, [rax+70h]
0x1800298fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029901  lea     rcx, off_18007B050
0x180029908  mov     [rbp+50h+var_B0], rcx
0x18002990c  mov     [rbp+50h+var_A8], rsi
0x180029910  lea     rcx, [rsp+150h+var_F0]
0x180029915  mov     [rbp+50h+var_A0], rcx
0x180029919  lea     rcx, [rbp+50h+var_B0]
0x18002991d  mov     [rbp+50h+var_78], rcx
0x180029921  lea     rdx, [rbp+50h+var_B0]
0x180029925  mov     rcx, rax
0x180029928  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18002992d  nop
0x18002992e  mov     rcx, [rbp+50h+var_78]
0x180029932  test    rcx, rcx
0x180029935  jz      short loc_18002994E
0x180029937  mov     rax, [rcx]
0x18002993a  lea     rdx, [rbp+50h+var_B0]
0x18002993e  cmp     rcx, rdx
0x180029941  setnz   dl
0x180029944  mov     rax, [rax+20h]
0x180029948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002994d  nop
0x18002994e  lea     rcx, [rsp+150h+var_120]
0x180029953  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029958  nop
0x180029959  mov     rcx, [rsp+150h+var_118]
0x18002995e  test    rcx, rcx
0x180029961  jz      short loc_180029979
0x180029963  mov     [rsp+150h+var_118], 0
0x18002996c  mov     rax, [rcx]
0x18002996f  mov     rax, [rax+10h]
0x180029973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029978  nop
0x180029979  jmp     loc_180029A09
0x18002997e  lea     rax, WPP_GLOBAL_Control
0x180029985  mov     rcx, cs:WPP_GLOBAL_Control
0x18002998c  cmp     rcx, rax
0x18002998f  jz      short loc_1800299FE
0x180029991  test    byte ptr [rcx+1Ch], 2
0x180029995  jz      short loc_1800299FE
0x180029997  mov     rbx, [rsp+150h+var_100]
0x18002999c  add     rbx, 28h ; '('
0x1800299a0  cmp     qword ptr [rbx+18h], 7
0x1800299a5  jbe     short loc_1800299AA
0x1800299a7  mov     rbx, [rbx]
0x1800299aa  lea     rdi, [rsi+128h]
0x1800299b1  cmp     qword ptr [rdi+18h], 7
0x1800299b6  jbe     short loc_1800299BB
0x1800299b8  mov     rdi, [rdi]
0x1800299bb  mov     rax, [rsi]
0x1800299be  mov     rcx, rsi
0x1800299c1  mov     rax, [rax+70h]
0x1800299c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ca  lea     r9, [rax+40h]
0x1800299ce  cmp     qword ptr [r9+18h], 7
0x1800299d3  jbe     short loc_1800299D8
0x1800299d5  mov     r9, [r9]
0x1800299d8  mov     edx, 0Bh
0x1800299dd  mov     [rsp+150h+var_128], rbx; __int64
0x1800299e2  mov     [rsp+150h+var_130], rdi; __int64
0x1800299e7  lea     r8, WPP_286df770ea7b35d8f7fae2161a5b1577_Traceguids
0x1800299ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299f5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800299f9  call    WPP_SF_SSS
0x1800299fe  xor     edx, edx; int
0x180029a00  mov     rcx, rsi; this
0x180029a03  call    ?CompleteTask@BaseTask@Impl@AppReadiness@@IEAA_NJ@Z; AppReadiness::Impl::BaseTask::CompleteTask(long)
0x180029a08  nop
0x180029a09  mov     rcx, [rsp+150h+var_F8]; this
0x180029a0e  test    rcx, rcx
0x180029a11  jz      short loc_180029A18
0x180029a13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029a18  mov     rcx, [rbp+50h+var_30]
0x180029a1c  xor     rcx, rsp; StackCookie
0x180029a1f  call    __security_check_cookie
0x180029a24  add     rsp, 138h
0x180029a2b  pop     rdi
0x180029a2c  pop     rsi
0x180029a2d  pop     rbx
0x180029a2e  pop     rbp
0x180029a2f  retn
```
