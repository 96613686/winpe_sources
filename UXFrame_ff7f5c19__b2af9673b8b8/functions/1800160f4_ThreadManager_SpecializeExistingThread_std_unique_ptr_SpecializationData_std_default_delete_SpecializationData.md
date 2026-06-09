# ThreadManager::SpecializeExistingThread(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&)

- ea: `0x1800160f4`
- end: `0x1800162a5`
- name: `?SpecializeExistingThread@ThreadManager@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1800137b8`

## callees

- `0x180002b20`
- `0x1800088ac`
- `0x180009ff0`
- `0x18000a180`
- `0x18000d504`
- `0x18000e130`
- `0x18000e2a0`
- `0x180013da4`
- `0x1800149a4`
- `0x1800160f4`
- `0x180017008`
- `0x180017124`
- `0x18001a798`
- `0x18004ada8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800161a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800161b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800161a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800161b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016143`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016143`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800161de`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800161de`

## string_xrefs

- `0x180016290`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HANDLE *__fastcall ThreadManager::SpecializeExistingThread(RTL_SRWLOCK *a1, HANDLE *a2, __int64 a3)
{
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // rcx
  void **v8; // r13
  __int64 *v9; // rdx
  __int64 v10; // rcx
  HANDLE CurrentProcess; // rbx
  void *v12; // rdi
  HANDLE v13; // rax
  const char *v14; // r9
  _BYTE v16[4]; // [rsp+40h] [rbp-40h] BYREF
  int v17; // [rsp+44h] [rbp-3Ch]
  HANDLE *v18; // [rsp+48h] [rbp-38h]
  void **v19; // [rsp+50h] [rbp-30h] BYREF
  RTL_SRWLOCK *v20; // [rsp+58h] [rbp-28h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v18 = a2;
  *a2 = 0;
  v17 = 1;
  v6 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v20 = v6;
  if ( a1[6].Ptr )
  {
    v7 = *((_QWORD *)a1[5].Ptr + 1);
    v8 = *(void ***)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    v19 = v8;
    v9 = (__int64 *)*((_QWORD *)a1[5].Ptr + 1);
    v10 = *v9;
    --a1[6].Ptr;
    *(_QWORD *)v9[1] = v10;
    *(_QWORD *)(v10 + 8) = v9[1];
    std::_List_node<std::unique_ptr<UXFrameThreadData>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<UXFrameThreadData>,void *>>>();
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a2,
      0);
    CurrentProcess = GetCurrentProcess();
    v12 = *v8;
    v13 = GetCurrentProcess();
    if ( !DuplicateHandle(v13, v12, CurrentProcess, a2, 0x100000u, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x156,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
        v14);
    *(_OWORD *)v21 = 0;
    std::shared_ptr<WindowingBehavior>::shared_ptr<WindowingBehavior>(v21, v8 + 2);
    std::list<std::unique_ptr<UXFrameThreadData>>::_Emplace<std::unique_ptr<UXFrameThreadData>>(&a1[3], a1[3].Ptr, &v19);
    UXFrame::SpecializeForExtensionAsync(v21[0], v16, a3);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    std::unique_ptr<UXFrameThreadData>::~unique_ptr<UXFrameThreadData>(&v19);
  }
  else
  {
    UXFrameTelemetry::NoIdleThreadToSpecialize();
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    ThreadManager::RefillIdleThreadPoolAfterDelay(a1, v16, 30);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  return a2;
}

```

## disassembly

```asm
0x1800160f4  mov     [rsp-38h+arg_10], rbx
0x1800160f9  push    rbp
0x1800160fa  push    rsi
0x1800160fb  push    rdi
0x1800160fc  push    r12
0x1800160fe  push    r13
0x180016100  push    r14
0x180016102  push    r15
0x180016104  mov     rbp, rsp
0x180016107  sub     rsp, 80h
0x18001610e  mov     rax, cs:__security_cookie
0x180016115  xor     rax, rsp
0x180016118  mov     [rbp+var_10], rax
0x18001611c  mov     r15, r8
0x18001611f  mov     rsi, rdx
0x180016122  mov     r14, rcx
0x180016125  mov     [rbp+var_38], rdx
0x180016129  mov     [rbp+var_3C], 0
0x180016130  xor     eax, eax
0x180016132  mov     [rdx], rax
0x180016135  mov     [rbp+var_3C], 1
0x18001613c  lea     rbx, [rcx+10h]
0x180016140  mov     rcx, rbx; SRWLock
0x180016143  call    cs:__imp_AcquireSRWLockExclusive
0x180016149  mov     [rbp+var_28], rbx
0x18001614d  cmp     qword ptr [r14+30h], 0
0x180016152  jnz     short loc_18001615E
0x180016154  call    ?NoIdleThreadToSpecialize@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::NoIdleThreadToSpecialize(void)
0x180016159  jmp     loc_18001623A
0x18001615e  mov     rax, [r14+28h]
0x180016162  mov     rcx, [rax+8]
0x180016166  mov     r13, [rcx+10h]
0x18001616a  mov     qword ptr [rcx+10h], 0
0x180016172  mov     [rbp+var_30], r13
0x180016176  mov     rax, [r14+28h]
0x18001617a  mov     rdx, [rax+8]
0x18001617e  mov     rcx, [rdx]
0x180016181  dec     qword ptr [r14+30h]
0x180016185  mov     rax, [rdx+8]
0x180016189  mov     [rax], rcx
0x18001618c  mov     rax, [rdx+8]
0x180016190  mov     [rcx+8], rax
0x180016194  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::unique_ptr<UXFrameThreadData>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<UXFrameThreadData>,void *>>>(std::allocator<std::_List_node<std::unique_ptr<UXFrameThreadData>,void *>> &,std::_List_node<std::unique_ptr<UXFrameThreadData>,void *> *)
0x180016199  xor     edx, edx
0x18001619b  mov     rcx, rsi
0x18001619e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800161a3  call    cs:__imp_GetCurrentProcess
0x1800161a9  mov     rbx, rax
0x1800161ac  mov     rdi, [r13+0]
0x1800161b0  call    cs:__imp_GetCurrentProcess
0x1800161b6  mov     r12, [rbp+38h]
0x1800161ba  mov     [rsp+80h+dwOptions], 0; dwOptions
0x1800161c2  mov     [rsp+80h+bInheritHandle], 0; bInheritHandle
0x1800161ca  mov     [rsp+80h+dwDesiredAccess], 100000h; dwDesiredAccess
0x1800161d2  mov     r9, rsi; lpTargetHandle
0x1800161d5  mov     r8, rbx; hTargetProcessHandle
0x1800161d8  mov     rdx, rdi; hSourceHandle
0x1800161db  mov     rcx, rax; hSourceProcessHandle
0x1800161de  call    cs:__imp_DuplicateHandle
0x1800161e4  test    eax, eax
0x1800161e6  jz      loc_180016290
0x1800161ec  xorps   xmm0, xmm0
0x1800161ef  movups  xmmword ptr [rbp+var_20], xmm0
0x1800161f3  lea     rdx, [r13+10h]
0x1800161f7  lea     rcx, [rbp+var_20]
0x1800161fb  call    ??0?$shared_ptr@VWindowingBehavior@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WindowingBehavior>::shared_ptr<WindowingBehavior>(std::shared_ptr<WindowingBehavior> const &)
0x180016200  nop
0x180016201  lea     rcx, [r14+18h]
0x180016205  lea     r8, [rbp+var_30]
0x180016209  mov     rdx, [rcx]
0x18001620c  call    ??$_Emplace@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@@?$list@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@V?$allocator@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@PEAX@1@QEAU21@$$QEAV?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@1@@Z; std::list<std::unique_ptr<UXFrameThreadData>>::_Emplace<std::unique_ptr<UXFrameThreadData>>(std::_List_node<std::unique_ptr<UXFrameThreadData>,void *> * const,std::unique_ptr<UXFrameThreadData> &&)
0x180016211  mov     r8, r15
0x180016214  lea     rdx, [rbp+var_40]
0x180016218  mov     rcx, [rbp+var_20]
0x18001621c  call    ?SpecializeForExtensionAsync@UXFrame@@QEAA?AUfire_and_forget@winrt@@$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@Z; UXFrame::SpecializeForExtensionAsync(std::unique_ptr<SpecializationData> &&)
0x180016221  nop
0x180016222  mov     rcx, [rbp+var_20+8]; this
0x180016226  test    rcx, rcx
0x180016229  jz      short loc_180016231
0x18001622b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016230  nop
0x180016231  lea     rcx, [rbp+var_30]
0x180016235  call    ??1?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@QEAA@XZ; std::unique_ptr<UXFrameThreadData>::~unique_ptr<UXFrameThreadData>(void)
0x18001623a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180016241  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x180016246  test    al, al
0x180016248  jz      short loc_18001625D
0x18001624a  mov     r8d, 1Eh
0x180016250  lea     rdx, [rbp+var_40]
0x180016254  mov     rcx, r14
0x180016257  call    ?RefillIdleThreadPoolAfterDelay@ThreadManager@@AEAA?AUfire_and_forget@winrt@@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@Uwrite_lock_required@wil@@@Z; ThreadManager::RefillIdleThreadPoolAfterDelay(std::chrono::duration<__int64,std::ratio<1,1>>,wil::write_lock_required)
0x18001625c  nop
0x18001625d  lea     rcx, [rbp+var_28]
0x180016261  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016266  mov     rax, rsi
0x180016269  mov     rcx, [rbp+var_10]
0x18001626d  xor     rcx, rsp; StackCookie
0x180016270  call    __security_check_cookie
0x180016275  mov     rbx, [rsp+80h+arg_10]
0x18001627d  add     rsp, 80h
0x180016284  pop     r15
0x180016286  pop     r14
0x180016288  pop     r13
0x18001628a  pop     r12
0x18001628c  pop     rdi
0x18001628d  pop     rsi
0x18001628e  pop     rbp
0x18001628f  retn
0x180016290  lea     r8, aPcshellShellUx_11; "pcshell\\shell\\uxframe\\dll\\ThreadMan"...
0x180016297  mov     edx, 156h; void *
0x18001629c  mov     rcx, r12; this
0x18001629f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
