# ApplicationInstanceManager::SetHamActivityForCentennialApplication(void *,IUnknown *)

- ea: `0x180049210`
- end: `0x180049536`
- name: `?SetHamActivityForCentennialApplication@ApplicationInstanceManager@@UEAAJPEAXPEAUIUnknown@@@Z`
- size: `806`
- prototype: `int(ApplicationInstanceManager *__hidden this, void *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000cbc0`
- `0x180011328`
- `0x180017da4`
- `0x180025a20`
- `0x180027ce8`
- `0x180033b34`
- `0x180049210`
- `0x18004953c`
- `0x1800495b8`
- `0x1800496cc`
- `0x180049778`
- `0x180049dc0`
- `0x180056208`
- `0x18005ae90`
- `0x1800763ec`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800494eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800494eb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004931a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004931a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800493f9`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800493f9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18004935f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18004935f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180049392`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180049392`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ApplicationInstanceManager::SetHamActivityForCentennialApplication(
        ApplicationInstanceManager *this,
        void *a2,
        struct IUnknown *a3)
{
  __int64 v5; // rbx
  DWORD ProcessId; // ebx
  int v7; // eax
  int v8; // eax
  unsigned __int64 *v9; // r8
  int HostIdFromProcessToken; // eax
  unsigned int ApplicationUserModelIdFromToken; // eax
  unsigned int v13; // [rsp+20h] [rbp-1A8h]
  UINT32 applicationUserModelIdLength; // [rsp+40h] [rbp-188h] BYREF
  __int64 v15; // [rsp+48h] [rbp-180h] BYREF
  HANDLE token; // [rsp+50h] [rbp-178h] BYREF
  __int64 v17; // [rsp+58h] [rbp-170h] BYREF
  struct IApplicationInstanceInfo *v18; // [rsp+60h] [rbp-168h] BYREF
  __int64 v19; // [rsp+68h] [rbp-160h] BYREF
  unsigned __int64 v20[2]; // [rsp+70h] [rbp-158h] BYREF
  unsigned __int64 v21; // [rsp+80h] [rbp-148h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp-140h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+90h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)0x80070057LL,
      v13);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)0x80070057LL,
      v13);
  v15 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
         a3,
         &GUID_400c7d63_1329_4258_bd36_8e7e4d0e337a,
         &v15) < 0 )
  {
    v19 = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v15);
    v5 = 0;
  }
  else
  {
    v5 = v15;
    v15 = 0;
    v17 = 0;
    v19 = v5;
    wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(&v17);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v15);
  }
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)0x80070057LL,
      v13);
  ProcessId = GetProcessId(a2);
  LODWORD(v15) = ProcessId;
  token = 0;
  v21 = 0;
  v20[0] = -1;
  applicationUserModelIdLength = 130;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &token,
    0);
  v7 = UMgrOpenProcessTokenForQuery(ProcessId, &token);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v8 = UMgrQueryUserContext(token, &v21);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)v8,
      v13);
  HostIdFromProcessToken = DevPlat::Shared::GetHostIdFromProcessToken((DevPlat::Shared *)token, v20, v9);
  if ( HostIdFromProcessToken < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)HostIdFromProcessToken,
      v13);
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)ApplicationUserModelIdFromToken,
      v13);
  v17 = 0;
  wil::AcquireSRWLockExclusive(&SRWLock, (char *)this + 152);
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  ApplicationInstanceManager::CreateOrGetApplicationInstanceFromMap(
    (ApplicationInstanceManager *)((char *)this - 144),
    ProcessId,
    a2,
    v21,
    applicationUserModelId,
    v20[0],
    &v18);
  std::_Tree<std::_Tmap_traits<unsigned long,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>>,0>>::find(
    (char *)this + 128,
    v20,
    &v15);
  if ( v20[0] != *((_QWORD *)this + 16) )
    wil::com_ptr_t<AutoCloseHamActivity,wil::err_exception_policy>::operator=<AutoCloseHamActivity,wil::err_returncode_policy,void>(
      &v17,
      v20[0] + 40);
  std::map<unsigned long,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>::_Insert_or_assign<unsigned long const &,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>(
    (char *)this + 128,
    v20,
    &v15,
    &v19);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(&v17);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
  wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(&v19);
  return 0;
}

```

## disassembly

```asm
0x180049210  push    rbx
0x180049212  push    rsi
0x180049213  push    rdi
0x180049214  sub     rsp, 1B0h
0x18004921b  mov     rax, cs:__security_cookie
0x180049222  xor     rax, rsp
0x180049225  mov     [rsp+1C8h+var_28], rax
0x18004922d  mov     r9, r8
0x180049230  mov     rdi, rdx
0x180049233  mov     rsi, rcx
0x180049236  mov     rcx, [rsp+1C8h]; this
0x18004923e  test    rdx, rdx
0x180049241  jnz     short loc_18004925A
0x180049243  mov     r9d, 80070057h; char *
0x180049249  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180049250  mov     edx, 0BCh; void *
0x180049255  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004925a  mov     rcx, [rsp+1C8h]; this
0x180049262  test    r9, r9
0x180049265  jnz     short loc_18004927F
0x180049267  mov     r9d, 80070057h; char *
0x18004926d  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180049274  mov     edx, 0BDh; void *
0x180049279  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004927f  mov     [rsp+1C8h+var_180], 0
0x180049288  mov     rax, [r8]
0x18004928b  lea     r8, [rsp+1C8h+var_180]
0x180049290  lea     rdx, _GUID_400c7d63_1329_4258_bd36_8e7e4d0e337a
0x180049297  mov     rcx, r9
0x18004929a  mov     rax, [rax]
0x18004929d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492a2  test    eax, eax
0x1800492a4  js      short loc_1800492D9
0x1800492a6  mov     rbx, [rsp+1C8h+var_180]
0x1800492ab  mov     [rsp+1C8h+var_180], 0
0x1800492b4  mov     [rsp+1C8h+var_170], 0
0x1800492bd  mov     [rsp+1C8h+var_160], rbx
0x1800492c2  lea     rcx, [rsp+1C8h+var_170]
0x1800492c7  call    ??1?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(void)
0x1800492cc  nop
0x1800492cd  lea     rcx, [rsp+1C8h+var_180]
0x1800492d2  call    ??1?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(void)
0x1800492d7  jmp     short loc_1800492EE
0x1800492d9  mov     [rsp+1C8h+var_160], 0
0x1800492e2  lea     rcx, [rsp+1C8h+var_180]
0x1800492e7  call    ??1?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(void)
0x1800492ec  xor     ebx, ebx
0x1800492ee  test    rbx, rbx
0x1800492f1  setz    al
0x1800492f4  mov     rcx, [rsp+1C8h]; this
0x1800492fc  test    al, al
0x1800492fe  jz      short loc_180049317
0x180049300  mov     r9d, 80070057h; char *
0x180049306  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004930d  mov     edx, 0C0h; void *
0x180049312  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049317  mov     rcx, rdi; Process
0x18004931a  call    cs:__imp_GetProcessId
0x180049320  mov     ebx, eax
0x180049322  mov     dword ptr [rsp+1C8h+var_180], eax
0x180049326  mov     [rsp+1C8h+token], 0
0x18004932f  mov     [rsp+1C8h+var_148], 0
0x18004933b  mov     [rsp+1C8h+var_158], 0FFFFFFFFFFFFFFFFh
0x180049344  mov     [rsp+1C8h+applicationUserModelIdLength], 82h
0x18004934c  xor     edx, edx
0x18004934e  lea     rcx, [rsp+1C8h+token]
0x180049353  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180049358  lea     rdx, [rsp+1C8h+token]
0x18004935d  mov     ecx, ebx
0x18004935f  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180049365  mov     rcx, [rsp+1C8h]; this
0x18004936d  test    eax, eax
0x18004936f  jns     short loc_180049385
0x180049371  mov     r9d, eax; char *
0x180049374  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004937b  mov     edx, 0C9h; void *
0x180049380  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049385  lea     rdx, [rsp+1C8h+var_148]
0x18004938d  mov     rcx, [rsp+1C8h+token]
0x180049392  call    cs:__imp_UMgrQueryUserContext
0x180049398  mov     rcx, [rsp+1C8h]; this
0x1800493a0  test    eax, eax
0x1800493a2  jns     short loc_1800493B8
0x1800493a4  mov     r9d, eax; char *
0x1800493a7  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800493ae  mov     edx, 0CAh; void *
0x1800493b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800493b8  lea     rdx, [rsp+1C8h+var_158]; void *
0x1800493bd  mov     rcx, [rsp+1C8h+token]; this
0x1800493c2  call    ?GetHostIdFromProcessToken@Shared@DevPlat@@YAJPEAXPEA_K@Z; DevPlat::Shared::GetHostIdFromProcessToken(void *,unsigned __int64 *)
0x1800493c7  mov     rcx, [rsp+1C8h]; this
0x1800493cf  test    eax, eax
0x1800493d1  jns     short loc_1800493E7
0x1800493d3  mov     r9d, eax; char *
0x1800493d6  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800493dd  mov     edx, 0CBh; void *
0x1800493e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800493e7  lea     r8, [rsp+1C8h+applicationUserModelId]; applicationUserModelId
0x1800493ef  lea     rdx, [rsp+1C8h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800493f4  mov     rcx, [rsp+1C8h+token]; token
0x1800493f9  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800493ff  mov     rcx, [rsp+1C8h]; this
0x180049407  test    eax, eax
0x180049409  jz      short loc_18004941F
0x18004940b  mov     r9d, eax; char *
0x18004940e  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180049415  mov     edx, 0CCh; void *
0x18004941a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004941f  mov     [rsp+1C8h+var_170], 0
0x180049428  lea     rdx, [rsi+98h]
0x18004942f  lea     rcx, [rsp+1C8h+SRWLock]
0x180049437  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18004943c  nop
0x18004943d  mov     [rsp+1C8h+var_168], 0
0x180049446  lea     rcx, [rsp+1C8h+var_168]
0x18004944b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049450  lea     rcx, [rsi-90h]; this
0x180049457  lea     rax, [rsp+1C8h+var_168]
0x18004945c  mov     [rsp+1C8h+var_198], rax; struct IApplicationInstanceInfo **
0x180049461  mov     rax, [rsp+1C8h+var_158]
0x180049466  mov     [rsp+1C8h+var_1A0], rax; unsigned __int64
0x18004946b  lea     rax, [rsp+1C8h+applicationUserModelId]
0x180049473  mov     [rsp+1C8h+var_1A8], rax; unsigned __int16 *
0x180049478  mov     r9, [rsp+1C8h+var_148]; unsigned __int64
0x180049480  mov     r8, rdi; void *
0x180049483  mov     edx, ebx; unsigned int
0x180049485  call    ?CreateOrGetApplicationInstanceFromMap@ApplicationInstanceManager@@AEAAXKPEAX_KPEBG1PEAPEAUIApplicationInstanceInfo@@@Z; ApplicationInstanceManager::CreateOrGetApplicationInstanceFromMap(ulong,void *,unsigned __int64,ushort const *,unsigned __int64,IApplicationInstanceInfo * *)
0x18004948a  lea     rbx, [rsi+80h]
0x180049491  lea     r8, [rsp+1C8h+var_180]
0x180049496  lea     rdx, [rsp+1C8h+var_158]
0x18004949b  mov     rcx, rbx
0x18004949e  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>,std::less<ulong>,std::allocator<std::pair<ulong const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>>,0>>::find(ulong const &)
0x1800494a3  mov     rdx, [rsp+1C8h+var_158]
0x1800494a8  cmp     rdx, [rbx]
0x1800494ab  jz      short loc_1800494BB
0x1800494ad  add     rdx, 28h ; '('
0x1800494b1  lea     rcx, [rsp+1C8h+var_170]
0x1800494b6  call    ??$?4VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@X@?$com_ptr_t@VAutoCloseHamActivity@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@1@@Z; wil::com_ptr_t<AutoCloseHamActivity,wil::err_exception_policy>::operator=<AutoCloseHamActivity,wil::err_returncode_policy,void>(wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy> &&)
0x1800494bb  lea     r9, [rsp+1C8h+var_160]
0x1800494c0  lea     r8, [rsp+1C8h+var_180]
0x1800494c5  lea     rdx, [rsp+1C8h+var_158]
0x1800494ca  mov     rcx, rbx
0x1800494cd  call    ??$_Insert_or_assign@AEBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@?$map@KV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBK$$QEAV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@Z; std::map<ulong,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>::_Insert_or_assign<ulong const &,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>(ulong const &,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy> &&)
0x1800494d2  nop
0x1800494d3  lea     rcx, [rsp+1C8h+var_168]
0x1800494d8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800494dd  nop
0x1800494de  mov     rcx, [rsp+1C8h+SRWLock]; SRWLock
0x1800494e6  test    rcx, rcx
0x1800494e9  jz      short loc_1800494F2
0x1800494eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800494f1  nop
0x1800494f2  lea     rcx, [rsp+1C8h+var_170]
0x1800494f7  call    ??1?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(void)
0x1800494fc  nop
0x1800494fd  lea     rcx, [rsp+1C8h+token]
0x180049502  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049507  nop
0x180049508  lea     rcx, [rsp+1C8h+var_160]
0x18004950d  call    ??1?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(void)
0x180049512  xor     eax, eax
0x180049514  jmp     short loc_18004951A
0x180049516  mov     eax, [rsp+1C8h+applicationUserModelIdLength]
0x18004951a  mov     rcx, [rsp+1C8h+var_28]
0x180049522  xor     rcx, rsp; StackCookie
0x180049525  call    __security_check_cookie
0x18004952a  add     rsp, 1B0h
0x180049531  pop     rdi
0x180049532  pop     rsi
0x180049533  pop     rbx
0x180049534  retn
```
