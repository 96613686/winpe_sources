# ThreadManager::CreateAndInitializeNewThread(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&)

- ea: `0x18000f8dc`
- end: `0x18000fa08`
- name: `?CreateAndInitializeNewThread@ThreadManager@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800137b8`

## callees

- `0x180002b20`
- `0x18000a090`
- `0x18000a360`
- `0x18000e2a0`
- `0x18000eb5c`
- `0x18000f8dc`
- `0x18000fae4`
- `0x180017008`
- `0x18001a798`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f964`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f964`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f971`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f920`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f99f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f99f`

## string_xrefs

- `0x18000f9f3`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HANDLE *__fastcall ThreadManager::CreateAndInitializeNewThread(RTL_SRWLOCK *a1, HANDLE *a2, __int64 *a3)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rdi
  HANDLE v8; // rax
  const char *v9; // r9
  RTL_SRWLOCK *v11; // [rsp+48h] [rbp-38h] BYREF
  __int64 (__fastcall *v12)(RTL_SRWLOCK *, struct SpecializationData **); // [rsp+50h] [rbp-30h] BYREF
  _QWORD v13[2]; // [rsp+58h] [rbp-28h] BYREF
  HANDLE hSourceHandle[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v13[1] = a2;
  UXFrameTelemetry::CreatingNewSpecializedThread();
  AcquireSRWLockExclusive(a1 + 2);
  v13[0] = a1 + 2;
  v11 = a1;
  v12 = ThreadManager::ThreadProc;
  std::thread::_Start<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>(
    (__int64)hSourceHandle,
    &v12,
    &v11,
    a3);
  *a2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  CurrentProcess = GetCurrentProcess();
  v7 = hSourceHandle[0];
  v8 = GetCurrentProcess();
  if ( !DuplicateHandle(v8, v7, CurrentProcess, a2, 0x100000u, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x176,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
      v9);
  std::list<std::thread>::_Emplace<std::thread>(&a1[7], a1[7].Ptr, hSourceHandle);
  std::thread::~thread((std::thread *)hSourceHandle);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
  return a2;
}

```

## disassembly

```asm
0x18000f8dc  mov     [rsp-28h+arg_18], rbx
0x18000f8e1  push    rbp
0x18000f8e2  push    rsi
0x18000f8e3  push    rdi
0x18000f8e4  push    r14
0x18000f8e6  push    r15
0x18000f8e8  mov     rbp, rsp
0x18000f8eb  sub     rsp, 80h
0x18000f8f2  mov     rax, cs:__security_cookie
0x18000f8f9  xor     rax, rsp
0x18000f8fc  mov     [rbp+var_8], rax
0x18000f900  mov     rdi, r8
0x18000f903  mov     rsi, rdx
0x18000f906  mov     r14, rcx
0x18000f909  mov     [rbp+var_20], rdx
0x18000f90d  mov     [rbp+var_40], 0
0x18000f914  call    ?CreatingNewSpecializedThread@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::CreatingNewSpecializedThread(void)
0x18000f919  lea     rbx, [r14+10h]
0x18000f91d  mov     rcx, rbx; SRWLock
0x18000f920  call    cs:__imp_AcquireSRWLockExclusive
0x18000f926  mov     [rbp+var_28], rbx
0x18000f92a  mov     [rbp+var_38], r14
0x18000f92e  lea     rax, ?ThreadProc@ThreadManager@@AEAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@Z; ThreadManager::ThreadProc(std::unique_ptr<SpecializationData> &&)
0x18000f935  mov     [rbp+var_30], rax
0x18000f939  mov     r9, rdi
0x18000f93c  lea     r8, [rbp+var_38]
0x18000f940  lea     rdx, [rbp+var_30]
0x18000f944  lea     rcx, [rbp+hSourceHandle]
0x18000f948  call    ??$_Start@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@thread@std@@AEAAX$$QEAP8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@1@@Z$$QEAPEAV2@0@Z; std::thread::_Start<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>(void (ThreadManager::*&&)(std::unique_ptr<SpecializationData> &&),ThreadManager * &&,std::unique_ptr<SpecializationData> &&)
0x18000f94d  nop
0x18000f94e  xor     eax, eax
0x18000f950  mov     [rsi], rax
0x18000f953  mov     [rbp+var_40], 1
0x18000f95a  xor     edx, edx
0x18000f95c  mov     rcx, rsi
0x18000f95f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000f964  call    cs:__imp_GetCurrentProcess
0x18000f96a  mov     rbx, rax
0x18000f96d  mov     rdi, [rbp+hSourceHandle]
0x18000f971  call    cs:__imp_GetCurrentProcess
0x18000f977  mov     r15, [rbp+28h]
0x18000f97b  mov     [rsp+80h+dwOptions], 0; dwOptions
0x18000f983  mov     [rsp+80h+bInheritHandle], 0; bInheritHandle
0x18000f98b  mov     [rsp+80h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18000f993  mov     r9, rsi; lpTargetHandle
0x18000f996  mov     r8, rbx; hTargetProcessHandle
0x18000f999  mov     rdx, rdi; hSourceHandle
0x18000f99c  mov     rcx, rax; hSourceProcessHandle
0x18000f99f  call    cs:__imp_DuplicateHandle
0x18000f9a5  test    eax, eax
0x18000f9a7  jz      short loc_18000F9F3
0x18000f9a9  lea     rcx, [r14+38h]
0x18000f9ad  lea     r8, [rbp+hSourceHandle]
0x18000f9b1  mov     rdx, [rcx]
0x18000f9b4  call    ??$_Emplace@Vthread@std@@@?$list@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAPEAU?$_List_node@Vthread@std@@PEAX@1@QEAU21@$$QEAVthread@1@@Z; std::list<std::thread>::_Emplace<std::thread>(std::_List_node<std::thread,void *> * const,std::thread &&)
0x18000f9b9  nop
0x18000f9ba  lea     rcx, [rbp+hSourceHandle]; this
0x18000f9be  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000f9c3  nop
0x18000f9c4  lea     rcx, [rbp+var_28]
0x18000f9c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f9cd  mov     rax, rsi
0x18000f9d0  mov     rcx, [rbp+var_8]
0x18000f9d4  xor     rcx, rsp; StackCookie
0x18000f9d7  call    __security_check_cookie
0x18000f9dc  mov     rbx, [rsp+80h+arg_18]
0x18000f9e4  add     rsp, 80h
0x18000f9eb  pop     r15
0x18000f9ed  pop     r14
0x18000f9ef  pop     rdi
0x18000f9f0  pop     rsi
0x18000f9f1  pop     rbp
0x18000f9f2  retn
0x18000f9f3  lea     r8, aPcshellShellUx_11; "pcshell\\shell\\uxframe\\dll\\ThreadMan"...
0x18000f9fa  mov     edx, 176h; void *
0x18000f9ff  mov     rcx, r15; this
0x18000fa02  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
