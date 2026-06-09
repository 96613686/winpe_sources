# AppReadiness::User::SuspendActivity(int)

- ea: `0x180018e7c`
- end: `0x180019256`
- name: `?SuspendActivity@User@AppReadiness@@QEAAXH@Z`
- size: `986`
- prototype: `void __fastcall(AppReadiness::User *__hidden this, int)`
- caller_count: `3`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026230`
- `0x1800269e0`
- `0x180026ab0`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a470`
- `0x18000b464`
- `0x18000b488`
- `0x18000b530`
- `0x18000bb90`
- `0x18000e4f8`
- `0x180018e7c`
- `0x180019260`
- `0x1800192a0`
- `0x18001db50`
- `0x18002489c`
- `0x180026b90`
- `0x180027a4c`
- `0x180027f5c`
- `0x180036df0`
- `0x1800373a4`
- `0x180038254`
- `0x180038f14`
- `0x180039840`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800191da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800191da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001919c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001919c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001903c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001903c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019026`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019052`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019052`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001913d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001913d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001914b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001914b`

## string_xrefs

- `0x18001901f`: `Windows.System.Threading.ThreadPoolTimer`
- `0x180019064`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x1800190eb`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180019070`: `AppReadiness::User::SuspendActivity`
- `0x1800190f7`: `AppReadiness::User::SuspendActivity`
- `0x1800190fe`: `threadpool->CreateTimer(this, timeSpan, &timer)`
- `0x180019077`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer).Get(), threadpool.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AppReadiness::User::SuspendActivity(RTL_SRWLOCK *this, int a2)
{
  __int64 v2; // rbx
  struct ITask **v4; // rdi
  struct ITask **v5; // r15
  __int64 v6; // rax
  AppReadiness::PackageInfo *v7; // rbx
  RTL_SRWLOCK *v8; // r9
  HRESULT v9; // eax
  int ActivationFactory; // eax
  unsigned __int64 v11; // r15
  struct ITask *v12; // rdi
  HRESULT (__stdcall *GetTriggerString)(ITask *, WORD, LPWSTR *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  RTL_SRWLOCK *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  struct ITask *v21; // rcx
  struct ITask *v22; // [rsp+30h] [rbp-39h] BYREF
  __int64 v23; // [rsp+38h] [rbp-31h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-29h] BYREF
  AppReadiness::PackageInfo *v25; // [rsp+48h] [rbp-21h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-19h]
  struct ITask **v27; // [rsp+58h] [rbp-11h] BYREF
  struct ITask **v28; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp+2Fh] BYREF

  v2 = a2;
  AppReadiness::User::CancelSuspendTimer((AppReadiness::User *)this);
  if ( HIDWORD(this[47].Ptr) != 3 )
  {
    if ( (_DWORD)v2 == -1 )
    {
      AppReadiness::User::GetAllTasksFor(this, &v27);
      if ( v27 != v28 )
      {
        AppReadiness::Storage::PackageList::PackageList(
          (AppReadiness::Storage::PackageList *)&hstringHeader,
          (struct AppReadiness::User *)this);
        AppReadiness::Storage::PackageList::Read((AppReadiness::Storage::PackageList *)&hstringHeader);
        v22 = *v27;
        Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v22);
        v4 = v27;
        v5 = v28;
        while ( v4 != v5 )
        {
          v6 = ((__int64 (__fastcall *)(struct ITask *, _SYSTEMTIME *))(*v4)->lpVtbl->SetIdleWait)(*v4, &SystemTime);
          std::weak_ptr<AppReadiness::PackageInfo>::lock(v6, &v25);
          if ( *(_QWORD *)&SystemTime.wHour )
            std::_Ref_count_base::_Decwref(*(std::_Ref_count_base **)&SystemTime.wHour);
          v7 = v25;
          AppReadiness::PackageInfo::MarkStatus(v25, (struct AppReadiness::User *)this, 0);
          AppReadiness::Storage::PackageList::Erase(&hstringHeader, (char *)v7 + 40);
          ((void (__fastcall *)(struct ITask *))(*v4)->lpVtbl->GetTriggerCount)(*v4);
          AppReadiness::User::RemoveTask((AppReadiness::User *)this, *v4);
          if ( v26 )
            std::_Ref_count_base::_Decref(v26);
          ++v4;
        }
        AppReadiness::Storage::PackageList::Write((AppReadiness::Storage::PackageList *)&hstringHeader);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        AppReadiness::Storage::PackageList::~PackageList((AppReadiness::Storage::PackageList *)&hstringHeader);
      }
      std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(&v27);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v8 = this + 8;
        if ( this[11].Ptr > (PVOID)7 )
          v8 = (RTL_SRWLOCK *)v8->Ptr;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
          (_DWORD)v8,
          v2);
      }
      v22 = 0;
      string = 0;
      v9 = WindowsCreateStringReference(L"Windows.System.Threading.ThreadPoolTimer", 0x28u, &hstringHeader, &string);
      if ( v9 < 0 )
      {
        RaiseException(v9, 1u, 0, 0);
        __debugbreak();
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v22);
      if ( ActivationFactory < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&hstringHeader,
          ActivationFactory,
          "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTim"
          "er).Get(), threadpool.GetAddressOf())",
          "AppReadiness::User::SuspendActivity",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          422);
        throw (Windows::HResultException *)&hstringHeader;
      }
      v11 = 10000000 * v2;
      v23 = 0;
      v12 = v22;
      GetTriggerString = v22->lpVtbl->GetTriggerString;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      v14 = ((__int64 (__fastcall *)(struct ITask *, unsigned __int64, unsigned __int64, __int64 *))GetTriggerString)(
              v12,
              (unsigned __int64)&this[1] & -(__int64)(this != 0),
              v11,
              &v23);
      if ( v14 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&hstringHeader,
          v14,
          "threadpool->CreateTimer(this, timeSpan, &timer)",
          "AppReadiness::User::SuspendActivity",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          424);
        throw (Windows::HResultException *)&hstringHeader;
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
      {
        FileTime = 0;
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        SystemTimeToFileTime(&SystemTime, &FileTime);
        v16 = v11 + *(_QWORD *)&FileTime;
        if ( v11 + *(_QWORD *)&FileTime < *(_QWORD *)&FileTime )
        {
          v25 = (AppReadiness::PackageInfo *)v11;
          v16 = v11;
        }
        else
        {
          v25 = (AppReadiness::PackageInfo *)(v11 + *(_QWORD *)&FileTime);
        }
        FileTime.dwLowDateTime = v16;
        v17 = HIDWORD(v16);
        FileTime.dwHighDateTime = v17;
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
        {
          v18 = this + 8;
          if ( this[11].Ptr > (PVOID)7 )
            v18 = (RTL_SRWLOCK *)v18->Ptr;
          McTemplateU0zm_EventWriteTransfer(v17, v15, v18, &FileTime);
        }
      }
      AcquireSRWLockExclusive(this + 7);
      v25 = (AppReadiness::PackageInfo *)&this[7];
      if ( !this[28].Ptr )
      {
        std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(&this[28].Ptr, (__int64)&v23);
        if ( !this[28].Ptr )
          MicrosoftTelemetryAssertTriggeredNoArgs(v19);
      }
      LOBYTE(this[27].Ptr) = 1;
      if ( this != (RTL_SRWLOCK *)-56LL )
        ReleaseSRWLockExclusive(this + 7);
      v20 = v23;
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 64LL))(v23);
        v20 = v23;
      }
      if ( v20 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = v22;
      if ( v22 )
      {
        v22 = 0;
        ((void (__fastcall *)(struct ITask *))v21->lpVtbl->Release)(v21);
      }
    }
  }
}

```

## disassembly

```asm
0x180018e7c  mov     [rsp-8+arg_10], rbx
0x180018e81  mov     [rsp-8+arg_18], rdi
0x180018e86  push    rbp
0x180018e87  push    r14
0x180018e89  push    r15
0x180018e8b  lea     rbp, [rsp-47h]
0x180018e90  sub     rsp, 0B0h
0x180018e97  mov     rax, cs:__security_cookie
0x180018e9e  xor     rax, rsp
0x180018ea1  mov     [rbp+57h+var_18], rax
0x180018ea5  movsxd  rbx, edx
0x180018ea8  mov     r14, rcx
0x180018eab  call    ?CancelSuspendTimer@User@AppReadiness@@IEAAXXZ; AppReadiness::User::CancelSuspendTimer(void)
0x180018eb0  cmp     dword ptr [r14+17Ch], 3
0x180018eb8  jz      loc_180019231
0x180018ebe  cmp     ebx, 0FFFFFFFFh
0x180018ec1  jnz     loc_180018FC2
0x180018ec7  lea     rdx, [rbp+57h+var_68]
0x180018ecb  mov     rcx, r14
0x180018ece  call    ?GetAllTasksFor@User@AppReadiness@@QEAA?AV?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@W4PackageOperation@Storage@2@W4FindTaskFlags@2@@Z; AppReadiness::User::GetAllTasksFor(AppReadiness::Storage::PackageOperation,AppReadiness::FindTaskFlags)
0x180018ed3  nop
0x180018ed4  mov     rax, [rbp+57h+var_60]
0x180018ed8  cmp     [rbp+57h+var_68], rax
0x180018edc  jz      loc_180018FB4
0x180018ee2  mov     rdx, r14; struct AppReadiness::User *
0x180018ee5  lea     rcx, [rbp+57h+hstringHeader]; this
0x180018ee9  call    ??0PackageList@Storage@AppReadiness@@QEAA@PEAVUser@2@@Z; AppReadiness::Storage::PackageList::PackageList(AppReadiness::User *)
0x180018eee  nop
0x180018eef  lea     rcx, [rbp+57h+hstringHeader]; this
0x180018ef3  call    ?Read@PackageList@Storage@AppReadiness@@QEAAXXZ; AppReadiness::Storage::PackageList::Read(void)
0x180018ef8  mov     rax, [rbp+57h+var_68]
0x180018efc  mov     rcx, [rax]
0x180018eff  mov     [rbp+57h+var_90], rcx
0x180018f03  lea     rcx, [rbp+57h+var_90]
0x180018f07  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x180018f0c  nop
0x180018f0d  mov     rdi, [rbp+57h+var_68]
0x180018f11  mov     r15, [rbp+57h+var_60]
0x180018f15  jmp     short loc_180018F91
0x180018f17  mov     rcx, [rdi]
0x180018f1a  mov     rax, [rcx]
0x180018f1d  lea     rdx, [rbp+57h+SystemTime]
0x180018f21  mov     rax, [rax+50h]
0x180018f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f2a  lea     rdx, [rbp+57h+var_78]
0x180018f2e  mov     rcx, rax
0x180018f31  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x180018f36  nop
0x180018f37  mov     rcx, qword ptr [rbp+57h+SystemTime.wHour]; this
0x180018f3b  test    rcx, rcx
0x180018f3e  jz      short loc_180018F45
0x180018f40  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180018f45  xor     r8d, r8d; int
0x180018f48  mov     rdx, r14; struct AppReadiness::User *
0x180018f4b  mov     rbx, [rbp+57h+var_78]
0x180018f4f  mov     rcx, rbx; this
0x180018f52  call    ?MarkStatus@PackageInfo@AppReadiness@@QEBAXPEAVUser@2@J@Z; AppReadiness::PackageInfo::MarkStatus(AppReadiness::User *,long)
0x180018f57  lea     rdx, [rbx+28h]
0x180018f5b  lea     rcx, [rbp+57h+hstringHeader]
0x180018f5f  call    ?Erase@PackageList@Storage@AppReadiness@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppReadiness::Storage::PackageList::Erase(std::wstring const &)
0x180018f64  mov     rcx, [rdi]
0x180018f67  mov     rax, [rcx]
0x180018f6a  mov     rax, [rax+28h]
0x180018f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f73  mov     rdx, [rdi]; struct ITask *
0x180018f76  mov     rcx, r14; this
0x180018f79  call    ?RemoveTask@User@AppReadiness@@QEAAXPEAUITask@2@@Z; AppReadiness::User::RemoveTask(AppReadiness::ITask *)
0x180018f7e  nop
0x180018f7f  mov     rcx, [rbp+57h+var_70]; this
0x180018f83  test    rcx, rcx
0x180018f86  jz      short loc_180018F8D
0x180018f88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018f8d  add     rdi, 8
0x180018f91  cmp     rdi, r15
0x180018f94  jnz     short loc_180018F17
0x180018f96  lea     rcx, [rbp+57h+hstringHeader]; this
0x180018f9a  call    ?Write@PackageList@Storage@AppReadiness@@QEAAXXZ; AppReadiness::Storage::PackageList::Write(void)
0x180018f9f  nop
0x180018fa0  lea     rcx, [rbp+57h+var_90]
0x180018fa4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018fa9  nop
0x180018faa  lea     rcx, [rbp+57h+hstringHeader]; this
0x180018fae  call    ??1PackageList@Storage@AppReadiness@@QEAA@XZ; AppReadiness::Storage::PackageList::~PackageList(void)
0x180018fb3  nop
0x180018fb4  lea     rcx, [rbp+57h+var_68]
0x180018fb8  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x180018fbd  jmp     loc_180019231
0x180018fc2  lea     rax, WPP_GLOBAL_Control
0x180018fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fd0  cmp     rcx, rax
0x180018fd3  jz      short loc_180019002
0x180018fd5  test    byte ptr [rcx+1Ch], 4
0x180018fd9  jz      short loc_180019002
0x180018fdb  lea     r9, [r14+40h]
0x180018fdf  cmp     qword ptr [r9+18h], 7
0x180018fe4  jbe     short loc_180018FE9
0x180018fe6  mov     r9, [r9]
0x180018fe9  mov     edx, 0Dh
0x180018fee  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180018ff2  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x180018ff9  mov     rcx, [rcx+10h]
0x180018ffd  call    WPP_SF_Sd
0x180019002  mov     [rbp+57h+var_90], 0
0x18001900a  mov     [rbp+57h+string], 0
0x180019012  lea     r9, [rbp+57h+string]; string
0x180019016  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001901a  mov     edx, 28h ; '('; length
0x18001901f  lea     rcx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x180019026  call    cs:__imp_WindowsCreateStringReference
0x18001902c  test    eax, eax
0x18001902e  jns     short loc_180019043
0x180019030  xor     r9d, r9d; lpArguments
0x180019033  xor     r8d, r8d; nNumberOfArguments
0x180019036  lea     edx, [r9+1]; dwExceptionFlags
0x18001903a  mov     ecx, eax; dwExceptionCode
0x18001903c  call    cs:__imp_RaiseException
0x180019042  int     3; Trap to Debugger
0x180019043  lea     r8, [rbp+57h+var_90]
0x180019047  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x18001904e  mov     rcx, [rbp+57h+string]
0x180019052  call    cs:__imp_RoGetActivationFactory
0x180019058  test    eax, eax
0x18001905a  jns     short loc_18001909A
0x18001905c  mov     [rsp+0C0h+var_98], 1A6h; int
0x180019064  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001906b  mov     [rsp+0C0h+var_A0], rcx; char *
0x180019070  lea     r9, aAppreadinessUs_9; "AppReadiness::User::SuspendActivity"
0x180019077  lea     r8, aWindowsFoundat_12; "Windows::Foundation::GetActivationFacto"...
0x18001907e  mov     edx, eax; int
0x180019080  lea     rcx, [rbp+57h+hstringHeader]; this
0x180019084  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180019089  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180019090  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x180019094  call    _CxxThrowException_0
0x18001909a  imul    r15, rbx, 989680h
0x1800190a1  mov     [rbp+57h+var_88], 0
0x1800190a9  mov     rdi, [rbp+57h+var_90]
0x1800190ad  mov     rax, [rdi]
0x1800190b0  mov     rbx, [rax+38h]
0x1800190b4  lea     rcx, [rbp+57h+var_88]
0x1800190b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800190bd  mov     rdx, r14
0x1800190c0  lea     r8, [r14+8]
0x1800190c4  neg     rdx
0x1800190c7  sbb     rdx, rdx
0x1800190ca  and     rdx, r8
0x1800190cd  lea     r9, [rbp+57h+var_88]
0x1800190d1  mov     r8, r15
0x1800190d4  mov     rcx, rdi
0x1800190d7  mov     rax, rbx
0x1800190da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190df  test    eax, eax
0x1800190e1  jns     short loc_180019121
0x1800190e3  mov     [rsp+0C0h+var_98], 1A8h; int
0x1800190eb  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800190f2  mov     [rsp+0C0h+var_A0], rcx; char *
0x1800190f7  lea     r9, aAppreadinessUs_9; "AppReadiness::User::SuspendActivity"
0x1800190fe  lea     r8, aThreadpoolCrea_1; "threadpool->CreateTimer(this, timeSpan,"...
0x180019105  mov     edx, eax; int
0x180019107  lea     rcx, [rbp+57h+hstringHeader]; this
0x18001910b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180019110  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180019117  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x18001911b  call    _CxxThrowException_0
0x180019121  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 1
0x180019128  jz      short loc_180019195
0x18001912a  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x180019132  xorps   xmm0, xmm0
0x180019135  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180019139  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001913d  call    cs:__imp_GetLocalTime
0x180019143  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180019147  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001914b  call    cs:__imp_SystemTimeToFileTime
0x180019151  mov     rax, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180019155  lea     rcx, [r15+rax]
0x180019159  cmp     rcx, rax
0x18001915c  jb      short loc_180019164
0x18001915e  mov     [rbp+57h+var_78], rcx
0x180019162  jmp     short loc_18001916B
0x180019164  mov     [rbp+57h+var_78], r15
0x180019168  mov     rcx, r15
0x18001916b  mov     [rbp+57h+FileTime.dwLowDateTime], ecx
0x18001916e  shr     rcx, 20h
0x180019172  mov     [rbp+57h+FileTime.dwHighDateTime], ecx
0x180019175  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 1
0x18001917c  jz      short loc_180019195
0x18001917e  lea     r8, [r14+40h]
0x180019182  cmp     qword ptr [r8+18h], 7
0x180019187  jbe     short loc_18001918C
0x180019189  mov     r8, [r8]
0x18001918c  lea     r9, [rbp+57h+FileTime]
0x180019190  call    McTemplateU0zm_EventWriteTransfer
0x180019195  lea     rbx, [r14+38h]
0x180019199  mov     rcx, rbx; SRWLock
0x18001919c  call    cs:__imp_AcquireSRWLockExclusive
0x1800191a2  mov     [rbp+57h+var_78], rbx
0x1800191a6  lea     rdi, [r14+0E0h]
0x1800191ad  cmp     qword ptr [rdi], 0
0x1800191b1  jnz     short loc_1800191CA
0x1800191b3  lea     rdx, [rbp+57h+var_88]
0x1800191b7  mov     rcx, rdi
0x1800191ba  call    ??$swap@V?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@$0A@@std@@YAXAEAV?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@0@Z; std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &,Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &)
0x1800191bf  cmp     qword ptr [rdi], 0
0x1800191c3  jnz     short loc_1800191CA
0x1800191c5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_suspendTimer")
0x1800191ca  mov     byte ptr [r14+0D8h], 1
0x1800191d2  test    rbx, rbx
0x1800191d5  jz      short loc_1800191E0
0x1800191d7  mov     rcx, rbx; SRWLock
0x1800191da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800191e0  mov     rcx, [rbp+57h+var_88]
0x1800191e4  test    rcx, rcx
0x1800191e7  jz      short loc_1800191F9
0x1800191e9  mov     rax, [rcx]
0x1800191ec  mov     rax, [rax+40h]
0x1800191f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f5  mov     rcx, [rbp+57h+var_88]
0x1800191f9  test    rcx, rcx
0x1800191fc  jz      short loc_180019213
0x1800191fe  mov     [rbp+57h+var_88], 0
0x180019206  mov     rax, [rcx]
0x180019209  mov     rax, [rax+10h]
0x18001920d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019212  nop
0x180019213  mov     rcx, [rbp+57h+var_90]
0x180019217  test    rcx, rcx
0x18001921a  jz      short loc_180019231
0x18001921c  mov     [rbp+57h+var_90], 0
0x180019224  mov     rax, [rcx]
0x180019227  mov     rax, [rax+10h]
0x18001922b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019230  nop
0x180019231  mov     rcx, [rbp+57h+var_18]
0x180019235  xor     rcx, rsp; StackCookie
0x180019238  call    __security_check_cookie
0x18001923d  lea     r11, [rsp+0C0h+var_10]
0x180019245  mov     rbx, [r11+30h]
0x180019249  mov     rdi, [r11+38h]
0x18001924d  mov     rsp, r11
0x180019250  pop     r15
0x180019252  pop     r14
0x180019254  pop     rbp
0x180019255  retn
```
