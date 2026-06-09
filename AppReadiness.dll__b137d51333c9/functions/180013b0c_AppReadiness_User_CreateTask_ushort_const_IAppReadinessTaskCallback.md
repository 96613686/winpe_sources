# AppReadiness::User::CreateTask(ushort const *,IAppReadinessTaskCallback *)

- ea: `0x180013b0c`
- end: `0x180014217`
- name: `?CreateTask@User@AppReadiness@@QEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@PEBGPEAUIAppReadinessTaskCallback@@@Z`
- size: `1803`
- prototype: `struct ITask **__fastcall(AppReadiness::User *this, struct ITask **, const WCHAR *, __int64)`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180045b14`
- `0x180045f74`
- `0x180047640`

## callees

- `0x180002958`
- `0x180006ce0`
- `0x18000a520`
- `0x18000c000`
- `0x18000d17c`
- `0x18000e5b4`
- `0x180012784`
- `0x180013b0c`
- `0x180014220`
- `0x180014384`
- `0x180016d80`
- `0x1800203d8`
- `0x1800244a0`
- `0x180026518`
- `0x180027a4c`
- `0x18003235c`
- `0x180033f30`
- `0x180037d18`
- `0x18003e210`
- `0x18003ecb4`
- `0x180049b10`
- `0x180049d38`
- `0x180049f8c`
- `0x18004cdec`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014028`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800141c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800141c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800140a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800140a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013b74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013c6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ceb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013de7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013eec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013b74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013c6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ceb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013de7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013eec`

## string_xrefs

- `0x180014085`: `Windows.System.Threading.ThreadPool`
- `0x180013bab`: `AppReadiness::User::CreateTask`
- `0x180013cac`: `AppReadiness::User::CreateTask`
- `0x180013d2a`: `AppReadiness::User::CreateTask`
- `0x180013da8`: `AppReadiness::User::CreateTask`
- `0x180013e26`: `AppReadiness::User::CreateTask`
- `0x180013ea4`: `AppReadiness::User::CreateTask`
- `0x180013f30`: `AppReadiness::User::CreateTask`
- `0x180013f8e`: `AppReadiness::User::CreateTask`
- `0x180013fe3`: `AppReadiness::User::CreateTask`
- `0x1800140c2`: `AppReadiness::User::CreateTask`
- `0x18001415a`: `AppReadiness::User::CreateTask`
- `0x180013b9f`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013ca0`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013d1e`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013d9c`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013e1a`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013e98`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013f24`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013f82`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013fd7`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x1800140b6`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001414e`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180013f95`: `task.As(&taskInf)`
- `0x180013bb2`: `MakeAndInitialize<Groups::OnDemandSyncGroup>(&task, this)`
- `0x180013cb3`: `MakeAndInitialize<Groups::UserLogon>(&task, this)`
- `0x180013d31`: `MakeAndInitialize<Groups::PreRoamingGroup>(&task, this)`
- `0x180013daf`: `MakeAndInitialize<Groups::InboxGroup>(&task, this)`
- `0x180013e2d`: `MakeAndInitialize<Groups::FirstLogonGroup>(&task, this)`
- `0x180013eab`: `MakeAndInitialize<Groups::OemFirstRun>(&task, this)`
- `0x1800140c9`: `Windows::Foundation::GetActivationFactory( HStringReference(RuntimeClass_Windows_System_Threading_ThreadPool).Get(), threadpool.GetAddressOf())`
- `0x180013fea`: `taskInf->SetCallback(callback)`
- `0x180014161`: `threadpool->RunAsync( Microsoft::WRL::Callback<IWorkItemHandler>(wistd::move(asyncAction)).Get(), action.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct ITask **__fastcall AppReadiness::User::CreateTask(
        AppReadiness::User *this,
        struct ITask **a2,
        const WCHAR *a3,
        __int64 a4)
{
  int v8; // eax
  __int64 v9; // r8
  __int64 Task; // rax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 AppxPrepareTask; // rax
  int v18; // eax
  int v19; // eax
  void *v20; // rsi
  DWORD v21; // eax
  DWORD v22; // r14d
  AppReadiness::Service *v23; // rax
  int ActivationFactory; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, AppReadiness::User *, AppReadiness::User **); // r12
  AppReadiness::User **v27; // rax
  AppReadiness::User *v28; // r15
  int v29; // edi
  __int64 v30; // rcx
  int LastError; // eax
  AppReadiness::User *v33; // [rsp+30h] [rbp-69h] BYREF
  __int64 v34; // [rsp+38h] [rbp-61h] BYREF
  int v35; // [rsp+40h] [rbp-59h]
  AppReadiness::User *v36; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v37[2]; // [rsp+50h] [rbp-49h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+60h] [rbp-39h] BYREF
  __int64 v39; // [rsp+78h] [rbp-21h]
  __int128 v40; // [rsp+88h] [rbp-11h] BYREF
  __int128 v41; // [rsp+98h] [rbp-1h]

  v37[1] = a2;
  *a2 = 0;
  v35 = 1;
  if ( *((_BYTE *)this + 177) || CompareStringOrdinal(L"ART:OnDemandSyncGroup", -1, a3, -1, 1) != 2 )
  {
    v40 = 0;
    v41 = 0;
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    std::wstring::_Construct<1,unsigned short const *>(&v40);
    Task = AppReadiness::User::FindTask(this, &v34, &v40);
    Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(a2, Task);
    v11 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( *((_QWORD *)&v41 + 1) > 7u )
      std::_Deallocate<16>(v40, 2LL * *((_QWORD *)&v41 + 1) + 2);
    if ( !*a2 )
    {
      if ( CompareStringOrdinal(L"ART:UserLogon", -1, a3, -1, 1) == 2 )
      {
        v33 = this;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        v12 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::UserLogon,AppReadiness::ITask,AppReadiness::User *>(
                a2,
                &v33);
        if ( v12 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v12,
            "MakeAndInitialize<Groups::UserLogon>(&task, this)",
            "AppReadiness::User::CreateTask",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            2306);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      else if ( CompareStringOrdinal(L"ART:PreRoamingGroup", -1, a3, -1, 1) == 2 )
      {
        v33 = this;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        v13 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::PreRoamingGroup,AppReadiness::ITask,AppReadiness::User *>(
                a2,
                &v33);
        if ( v13 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v13,
            "MakeAndInitialize<Groups::PreRoamingGroup>(&task, this)",
            "AppReadiness::User::CreateTask",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            2310);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      else if ( CompareStringOrdinal(L"ART:InboxGroup", -1, a3, -1, 1) == 2 )
      {
        v33 = this;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        v14 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::InboxGroup,AppReadiness::ITask,AppReadiness::User *>(
                a2,
                &v33);
        if ( v14 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v14,
            "MakeAndInitialize<Groups::InboxGroup>(&task, this)",
            "AppReadiness::User::CreateTask",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            2314);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      else if ( CompareStringOrdinal(L"ART:UserFirstLogon", -1, a3, -1, 1) == 2 )
      {
        v33 = this;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        v15 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::FirstLogonGroup,AppReadiness::ITask,AppReadiness::User *>(
                a2,
                &v33);
        if ( v15 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v15,
            "MakeAndInitialize<Groups::FirstLogonGroup>(&task, this)",
            "AppReadiness::User::CreateTask",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            2318);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      else if ( CompareStringOrdinal(L"ART:OemFirstRun", -1, a3, -1, 1) == 2 )
      {
        v33 = this;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        v16 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OemFirstRun,AppReadiness::ITask,AppReadiness::User *>(
                a2,
                &v33);
        if ( v16 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v16,
            "MakeAndInitialize<Groups::OemFirstRun>(&task, this)",
            "AppReadiness::User::CreateTask",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            2322);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      else if ( *((_BYTE *)this + 176) && CompareStringOrdinal(L"ART:AppxPreRegistration", -1, a3, -1, 1) == 2 )
      {
        AppxPrepareTask = AppReadiness::User::CreateAppxPrepareTask(this);
        Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(a2, AppxPrepareTask);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      }
      if ( !*a2 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          -2147024809,
          "task",
          "AppReadiness::User::CreateTask",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          2329);
        throw (Windows::HResultException *)&pExceptionObject;
      }
    }
  }
  else
  {
    v33 = this;
    v8 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OnDemandSyncGroup,AppReadiness::ITask,AppReadiness::User *>(
           a2,
           &v33);
    if ( v8 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v8,
        "MakeAndInitialize<Groups::OnDemandSyncGroup>(&task, this)",
        "AppReadiness::User::CreateTask",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2297);
      throw (Windows::HResultException *)&pExceptionObject;
    }
  }
  if ( a4 )
  {
    v34 = 0;
    v18 = Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(a2, &v34);
    if ( v18 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v18,
        "task.As(&taskInf)",
        "AppReadiness::User::CreateTask",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2337);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 64LL))(v34, a4);
    if ( v19 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v19,
        "taskInf->SetCallback(callback)",
        "AppReadiness::User::CreateTask",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2338);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  }
  v20 = (void *)*((_QWORD *)this + 19);
  v21 = WaitForSingleObjectEx(v20, 0xFAu, 0);
  v22 = v21;
  LODWORD(v40) = v21;
  *((_QWORD *)&v40 + 1) = v20;
  if ( !v20 || (v21 & 0xFFFFFF7F) != 0 )
  {
    AppReadiness::User::AddFutureTask(this, *a2);
    v36 = this;
    v34 = 0;
    v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &pExceptionObject,
      L"Windows.System.Threading.ThreadPool",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v39, &GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91, &v34);
    if ( ActivationFactory < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        ActivationFactory,
        "Windows::Foundation::GetActivationFactory( HStringReference(RuntimeClass_Windows_System_Threading_ThreadPool).Ge"
        "t(), threadpool.GetAddressOf())",
        "AppReadiness::User::CreateTask",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2361);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v33 = 0;
    v25 = v34;
    v26 = *(__int64 (__fastcall **)(__int64, AppReadiness::User *, AppReadiness::User **))(*(_QWORD *)v34 + 48LL);
    v27 = (AppReadiness::User **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::System::Threading::IWorkItemHandler::___Windows::Foundation::IAsyncAction____::DelegateInvokeHelper_Windows::System::Threading::IWorkItemHandler__lambda_45948862b8d5ea1203e6b1281488ed7e___1_Windows::Foundation::IAsyncAction_____lambda_45948862b8d5ea1203e6b1281488ed7e___(
                                   v37,
                                   &v36);
    v28 = *v27;
    v36 = *v27;
    *v27 = 0;
    if ( v37[0] )
    {
      v37[0] = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release();
    }
    v29 = v26(v25, v28, &v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    if ( v29 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v29,
        "threadpool->RunAsync( Microsoft::WRL::Callback<IWorkItemHandler>(wistd::move(asyncAction)).Get(), action.GetAddressOf())",
        "AppReadiness::User::CreateTask",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2365);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  else
  {
    AppReadiness::User::AddTask(this, *a2);
    v23 = AppReadiness::Service::Get();
    AppReadiness::Service::ProcessUserTasks(v23, this);
  }
  if ( v20 && (v22 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(v20, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return a2;
}

```

## disassembly

```asm
0x180013b0c  push    rbp
0x180013b0e  push    rbx
0x180013b0f  push    rsi
0x180013b10  push    rdi
0x180013b11  push    r12
0x180013b13  push    r13
0x180013b15  push    r14
0x180013b17  push    r15
0x180013b19  lea     rbp, [rsp-1Fh]
0x180013b1e  sub     rsp, 0B8h
0x180013b25  mov     rax, cs:__security_cookie
0x180013b2c  xor     rax, rsp
0x180013b2f  mov     [rbp+57h+var_48], rax
0x180013b33  mov     r14, r9
0x180013b36  mov     rsi, r8
0x180013b39  mov     rbx, rdx
0x180013b3c  mov     rdi, rcx
0x180013b3f  mov     [rbp+57h+var_98], rdx
0x180013b43  xor     r13d, r13d
0x180013b46  mov     [rbp+57h+var_B0], r13d
0x180013b4a  mov     [rdx], r13
0x180013b4d  lea     r12d, [r13+1]
0x180013b51  mov     [rbp+57h+var_B0], r12d
0x180013b55  or      r15, 0FFFFFFFFFFFFFFFFh
0x180013b59  cmp     [rcx+0B1h], r13b
0x180013b60  jnz     short loc_180013BD5
0x180013b62  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013b67  mov     r9d, r15d; cchCount2
0x180013b6a  mov     edx, r15d; cchCount1
0x180013b6d  lea     rcx, String1; "ART:OnDemandSyncGroup"
0x180013b74  call    cs:__imp_CompareStringOrdinal
0x180013b7a  cmp     eax, 2
0x180013b7d  jnz     short loc_180013BD5
0x180013b7f  mov     [rbp+57h+var_C0], rdi
0x180013b83  lea     rdx, [rbp+57h+var_C0]
0x180013b87  mov     rcx, rbx
0x180013b8a  call    ??$MakeAndInitialize@VOnDemandSyncGroup@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@012@$$QEAPEAVUser@AppReadiness@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OnDemandSyncGroup,AppReadiness::ITask,AppReadiness::User *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppReadiness::ITask>>,AppReadiness::User * &&)
0x180013b8f  test    eax, eax
0x180013b91  jns     loc_180013F5D
0x180013b97  mov     [rsp+0F0h+var_C8], 8F9h; int
0x180013b9f  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013ba6  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013bab  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013bb2  lea     r8, aMakeandinitial_12; "MakeAndInitialize<Groups::OnDemandSyncG"...
0x180013bb9  mov     edx, eax; int
0x180013bbb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013bbf  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013bc4  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013bcb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013bcf  call    _CxxThrowException_0
0x180013bd5  xorps   xmm0, xmm0
0x180013bd8  movups  [rbp+57h+var_68], xmm0
0x180013bdc  xorps   xmm1, xmm1
0x180013bdf  movdqu  [rbp+57h+var_58], xmm1
0x180013be4  mov     r8, r15
0x180013be7  inc     r8
0x180013bea  cmp     [rsi+r8*2], r13w
0x180013bef  jnz     short loc_180013BE7
0x180013bf1  mov     rdx, rsi
0x180013bf4  lea     rcx, [rbp+57h+var_68]
0x180013bf8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013bfd  nop
0x180013bfe  lea     r8, [rbp+57h+var_68]
0x180013c02  lea     rdx, [rbp+57h+var_B8]
0x180013c06  mov     rcx, rdi
0x180013c09  call    ?FindTask@User@AppReadiness@@QEBA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FindTaskFlags@2@@Z; AppReadiness::User::FindTask(std::wstring const &,AppReadiness::FindTaskFlags)
0x180013c0e  mov     rdx, rax
0x180013c11  mov     rcx, rbx
0x180013c14  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180013c19  nop
0x180013c1a  mov     rcx, [rbp+57h+var_B8]
0x180013c1e  test    rcx, rcx
0x180013c21  jz      short loc_180013C34
0x180013c23  mov     [rbp+57h+var_B8], r13
0x180013c27  mov     rax, [rcx]
0x180013c2a  mov     rax, [rax+10h]
0x180013c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c33  nop
0x180013c34  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180013c38  cmp     rdx, 7
0x180013c3c  jbe     short loc_180013C4F
0x180013c3e  lea     rdx, ds:2[rdx*2]
0x180013c46  mov     rcx, qword ptr [rbp+57h+var_68]
0x180013c4a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013c4f  cmp     [rbx], r13
0x180013c52  jnz     loc_180013F5D
0x180013c58  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013c5d  mov     r9d, r15d; cchCount2
0x180013c60  mov     r8, rsi; lpString2
0x180013c63  mov     edx, r15d; cchCount1
0x180013c66  lea     rcx, aArtUserlogon; "ART:UserLogon"
0x180013c6d  call    cs:__imp_CompareStringOrdinal
0x180013c73  cmp     eax, 2
0x180013c76  jnz     short loc_180013CD6
0x180013c78  mov     [rbp+57h+var_C0], rdi
0x180013c7c  mov     rcx, rbx
0x180013c7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c84  lea     rdx, [rbp+57h+var_C0]
0x180013c88  mov     rcx, rbx
0x180013c8b  call    ??$MakeAndInitialize@VUserLogon@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::UserLogon,AppReadiness::ITask,AppReadiness::User *>(AppReadiness::ITask * *,AppReadiness::User * &&)
0x180013c90  test    eax, eax
0x180013c92  jns     loc_180013F17
0x180013c98  mov     [rsp+0F0h+var_C8], 902h; int
0x180013ca0  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013ca7  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013cac  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013cb3  lea     r8, aMakeandinitial_14; "MakeAndInitialize<Groups::UserLogon>(&t"...
0x180013cba  mov     edx, eax; int
0x180013cbc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013cc0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013cc5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013ccc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013cd0  call    _CxxThrowException_0
0x180013cd6  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013cdb  mov     r9d, r15d; cchCount2
0x180013cde  mov     r8, rsi; lpString2
0x180013ce1  mov     edx, r15d; cchCount1
0x180013ce4  lea     rcx, aArtPreroamingg; "ART:PreRoamingGroup"
0x180013ceb  call    cs:__imp_CompareStringOrdinal
0x180013cf1  cmp     eax, 2
0x180013cf4  jnz     short loc_180013D54
0x180013cf6  mov     [rbp+57h+var_C0], rdi
0x180013cfa  mov     rcx, rbx
0x180013cfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d02  lea     rdx, [rbp+57h+var_C0]
0x180013d06  mov     rcx, rbx
0x180013d09  call    ??$MakeAndInitialize@VPreRoamingGroup@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::PreRoamingGroup,AppReadiness::ITask,AppReadiness::User *>(AppReadiness::ITask * *,AppReadiness::User * &&)
0x180013d0e  test    eax, eax
0x180013d10  jns     loc_180013F17
0x180013d16  mov     [rsp+0F0h+var_C8], 906h; int
0x180013d1e  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013d25  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013d2a  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013d31  lea     r8, aMakeandinitial_15; "MakeAndInitialize<Groups::PreRoamingGro"...
0x180013d38  mov     edx, eax; int
0x180013d3a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013d3e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013d43  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013d4a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013d4e  call    _CxxThrowException_0
0x180013d54  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013d59  mov     r9d, r15d; cchCount2
0x180013d5c  mov     r8, rsi; lpString2
0x180013d5f  mov     edx, r15d; cchCount1
0x180013d62  lea     rcx, aArtInboxgroup; "ART:InboxGroup"
0x180013d69  call    cs:__imp_CompareStringOrdinal
0x180013d6f  cmp     eax, 2
0x180013d72  jnz     short loc_180013DD2
0x180013d74  mov     [rbp+57h+var_C0], rdi
0x180013d78  mov     rcx, rbx
0x180013d7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d80  lea     rdx, [rbp+57h+var_C0]
0x180013d84  mov     rcx, rbx
0x180013d87  call    ??$MakeAndInitialize@VInboxGroup@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::InboxGroup,AppReadiness::ITask,AppReadiness::User *>(AppReadiness::ITask * *,AppReadiness::User * &&)
0x180013d8c  test    eax, eax
0x180013d8e  jns     loc_180013F17
0x180013d94  mov     [rsp+0F0h+var_C8], 90Ah; int
0x180013d9c  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013da3  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013da8  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013daf  lea     r8, aMakeandinitial; "MakeAndInitialize<Groups::InboxGroup>(&"...
0x180013db6  mov     edx, eax; int
0x180013db8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013dbc  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013dc1  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013dc8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013dcc  call    _CxxThrowException_0
0x180013dd2  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013dd7  mov     r9d, r15d; cchCount2
0x180013dda  mov     r8, rsi; lpString2
0x180013ddd  mov     edx, r15d; cchCount1
0x180013de0  lea     rcx, aArtUserfirstlo; "ART:UserFirstLogon"
0x180013de7  call    cs:__imp_CompareStringOrdinal
0x180013ded  cmp     eax, 2
0x180013df0  jnz     short loc_180013E50
0x180013df2  mov     [rbp+57h+var_C0], rdi
0x180013df6  mov     rcx, rbx
0x180013df9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013dfe  lea     rdx, [rbp+57h+var_C0]
0x180013e02  mov     rcx, rbx
0x180013e05  call    ??$MakeAndInitialize@VFirstLogonGroup@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::FirstLogonGroup,AppReadiness::ITask,AppReadiness::User *>(AppReadiness::ITask * *,AppReadiness::User * &&)
0x180013e0a  test    eax, eax
0x180013e0c  jns     loc_180013F17
0x180013e12  mov     [rsp+0F0h+var_C8], 90Eh; int
0x180013e1a  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013e21  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013e26  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013e2d  lea     r8, aMakeandinitial_4; "MakeAndInitialize<Groups::FirstLogonGro"...
0x180013e34  mov     edx, eax; int
0x180013e36  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013e3a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013e3f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013e46  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013e4a  call    _CxxThrowException_0
0x180013e50  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013e55  mov     r9d, r15d; cchCount2
0x180013e58  mov     r8, rsi; lpString2
0x180013e5b  mov     edx, r15d; cchCount1
0x180013e5e  lea     rcx, aArtOemfirstrun; "ART:OemFirstRun"
0x180013e65  call    cs:__imp_CompareStringOrdinal
0x180013e6b  cmp     eax, 2
0x180013e6e  jnz     short loc_180013ECE
0x180013e70  mov     [rbp+57h+var_C0], rdi
0x180013e74  mov     rcx, rbx
0x180013e77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e7c  lea     rdx, [rbp+57h+var_C0]
0x180013e80  mov     rcx, rbx
0x180013e83  call    ??$MakeAndInitialize@VOemFirstRun@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OemFirstRun,AppReadiness::ITask,AppReadiness::User *>(AppReadiness::ITask * *,AppReadiness::User * &&)
0x180013e88  test    eax, eax
0x180013e8a  jns     loc_180013F17
0x180013e90  mov     [rsp+0F0h+var_C8], 912h; int
0x180013e98  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013e9f  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013ea4  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013eab  lea     r8, aMakeandinitial_16; "MakeAndInitialize<Groups::OemFirstRun>("...
0x180013eb2  mov     edx, eax; int
0x180013eb4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013eb8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013ebd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013ec4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013ec8  call    _CxxThrowException_0
0x180013ece  cmp     [rdi+0B0h], r13b
0x180013ed5  jz      short loc_180013F17
0x180013ed7  mov     [rsp+0F0h+bIgnoreCase], r12d; bIgnoreCase
0x180013edc  mov     r9d, r15d; cchCount2
0x180013edf  mov     r8, rsi; lpString2
0x180013ee2  mov     edx, r15d; cchCount1
0x180013ee5  lea     rcx, aArtAppxpreregi; "ART:AppxPreRegistration"
0x180013eec  call    cs:__imp_CompareStringOrdinal
0x180013ef2  cmp     eax, 2
0x180013ef5  jnz     short loc_180013F17
0x180013ef7  lea     rdx, [rbp+57h+var_C0]
0x180013efb  mov     rcx, rdi; this
0x180013efe  call    ?CreateAppxPrepareTask@User@AppReadiness@@IEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@XZ; AppReadiness::User::CreateAppxPrepareTask(void)
0x180013f03  mov     rdx, rax
0x180013f06  mov     rcx, rbx
0x180013f09  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180013f0e  lea     rcx, [rbp+57h+var_C0]
0x180013f12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f17  cmp     [rbx], r13
0x180013f1a  jnz     short loc_180013F5D
0x180013f1c  mov     [rsp+0F0h+var_C8], 919h; int
0x180013f24  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013f2b  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013f30  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013f37  lea     r8, aTask; "task"
0x180013f3e  mov     edx, 80070057h; int
0x180013f43  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013f47  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013f4c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013f53  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013f57  call    _CxxThrowException_0
0x180013f5d  test    r14, r14
0x180013f60  jz      loc_180014016
0x180013f66  mov     [rbp+57h+var_B8], r13
0x180013f6a  lea     rdx, [rbp+57h+var_B8]
0x180013f6e  mov     rcx, rbx
0x180013f71  call    ??$As@UIAppReadinessTask@@@?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppReadinessTask@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppReadinessTask>>)
0x180013f76  test    eax, eax
0x180013f78  jns     short loc_180013FB8
0x180013f7a  mov     [rsp+0F0h+var_C8], 921h; int
0x180013f82  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013f89  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013f8e  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013f95  lea     r8, aTaskAsTaskinf; "task.As(&taskInf)"
0x180013f9c  mov     edx, eax; int
0x180013f9e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013fa2  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013fa7  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013fae  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013fb2  call    _CxxThrowException_0
0x180013fb8  mov     rcx, [rbp+57h+var_B8]
0x180013fbc  mov     rax, [rcx]
0x180013fbf  mov     rdx, r14
0x180013fc2  mov     rax, [rax+40h]
0x180013fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fcb  test    eax, eax
0x180013fcd  jns     short loc_18001400D
0x180013fcf  mov     [rsp+0F0h+var_C8], 922h; int
0x180013fd7  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013fde  mov     qword ptr [rsp+0F0h+bIgnoreCase], rcx; char *
0x180013fe3  lea     r9, aAppreadinessUs_0; "AppReadiness::User::CreateTask"
0x180013fea  lea     r8, aTaskinfSetcall; "taskInf->SetCallback(callback)"
0x180013ff1  mov     edx, eax; int
0x180013ff3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013ff7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013ffc  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180014003  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180014007  call    _CxxThrowException_0
0x18001400d  lea     rcx, [rbp+57h+var_B8]
0x180014011  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014016  mov     rsi, [rdi+98h]
0x18001401d  xor     r8d, r8d; bAlertable
0x180014020  mov     edx, 0FAh; dwMilliseconds
0x180014025  mov     rcx, rsi; hHandle
0x180014028  call    cs:__imp_WaitForSingleObjectEx
0x18001402e  mov     r14d, eax
0x180014031  mov     dword ptr [rbp+57h+var_68], eax
0x180014034  mov     qword ptr [rbp+57h+var_68+8], rsi
0x180014038  test    rsi, rsi
  ... truncated ...
```
