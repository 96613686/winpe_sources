# UserOobeHostAppManager::v_OnExperienceExit(void)

- ea: `0x18003f6b0`
- end: `0x18003f813`
- name: `?v_OnExperienceExit@UserOobeHostAppManager@@MEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(UserOobeHostAppManager *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004acc`
- `0x18000876c`
- `0x18000a664`
- `0x18000a684`
- `0x18000b418`
- `0x18000d400`
- `0x1800157d0`
- `0x18003378c`
- `0x180038ee4`
- `0x18003f6b0`
- `0x18003fc18`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003f7c3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003f7c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f773`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18003f743`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18003f743`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003f758`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003f758`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserOobeHostAppManager::v_OnExperienceExit(wil::details **this)
{
  unsigned int UserOOBEExitReason; // eax
  void *v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // esi
  char v6; // bl
  void *v7; // rdx
  HWND WindowW; // rax
  __int64 v9; // rbx
  DWORD CurrentThreadId; // edi
  __int64 *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  char v16; // [rsp+60h] [rbp+18h] BYREF

  UserOOBEExitReason = GetUserOOBEExitReason();
  v5 = UserOOBEExitReason;
  if ( UserOOBEExitReason )
  {
    if ( UserOOBEExitReason - 1 <= 1 )
LABEL_3:
      wil::details::SetEvent(this[4], v3);
  }
  else
  {
    wil::AcquireSRWLockShared(&v15, this + 2);
    v6 = *((_BYTE *)this + 24);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
    if ( v6 )
    {
      wil::AcquireSRWLockExclusive(&v15, this + 2);
      *((_BYTE *)this + 25) = 1;
      wil::details::SetEvent(this[4], v7);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
      goto LABEL_13;
    }
    if ( *((_BYTE *)this + 200) )
      goto LABEL_3;
    WindowW = FindWindowW(L"Shell_TrayWnd", 0);
    if ( !WindowW || !GetPropW(WindowW, L"IsExplorerShuttingDown") )
    {
      v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v16, this);
      CurrentThreadId = GetCurrentThreadId();
      v11 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f6fe95fbd0e579a934da851dfbdc5e9e_____lambda_f6fe95fbd0e579a934da851dfbdc5e9e___(
                         &v15,
                         v9);
      v12 = *v11;
      *v11 = 0;
      v13 = v15;
      if ( v15 )
      {
        v15 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v13);
      }
      SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0, v12, 0);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, v5);
  return 0;
}

```

## disassembly

```asm
0x18003f6b0  mov     [rsp+arg_0], rbx
0x18003f6b5  push    rbp
0x18003f6b6  push    rsi
0x18003f6b7  push    rdi
0x18003f6b8  sub     rsp, 30h
0x18003f6bc  mov     rdi, rcx
0x18003f6bf  call    ?GetUserOOBEExitReason@@YA?AW4UserOOBEExitReason@@XZ; GetUserOOBEExitReason(void)
0x18003f6c4  mov     esi, eax
0x18003f6c6  mov     ecx, eax
0x18003f6c8  test    eax, eax
0x18003f6ca  jz      short loc_18003F6E8
0x18003f6cc  sub     ecx, 1
0x18003f6cf  jz      short loc_18003F6DA
0x18003f6d1  cmp     ecx, 1
0x18003f6d4  jnz     loc_18003F7DF
0x18003f6da  mov     rcx, [rdi+20h]; this
0x18003f6de  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18003f6e3  jmp     loc_18003F7DF
0x18003f6e8  lea     rdx, [rdi+10h]
0x18003f6ec  lea     rcx, [rsp+48h+arg_8]
0x18003f6f1  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18003f6f6  mov     bl, [rdi+18h]
0x18003f6f9  lea     rcx, [rsp+48h+arg_8]
0x18003f6fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003f703  test    bl, bl
0x18003f705  jz      short loc_18003F731
0x18003f707  lea     rdx, [rdi+10h]
0x18003f70b  lea     rcx, [rsp+48h+arg_8]
0x18003f710  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003f715  mov     byte ptr [rdi+19h], 1
0x18003f719  mov     rcx, [rdi+20h]; this
0x18003f71d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18003f722  lea     rcx, [rsp+48h+arg_8]
0x18003f727  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003f72c  jmp     loc_18003F7DF
0x18003f731  cmp     byte ptr [rdi+0C8h], 0
0x18003f738  jnz     short loc_18003F6DA
0x18003f73a  xor     edx, edx; lpWindowName
0x18003f73c  lea     rcx, ClassName; "Shell_TrayWnd"
0x18003f743  call    cs:__imp_FindWindowW
0x18003f749  test    rax, rax
0x18003f74c  jz      short loc_18003F763
0x18003f74e  lea     rdx, String; "IsExplorerShuttingDown"
0x18003f755  mov     rcx, rax; hWnd
0x18003f758  call    cs:__imp_GetPropW
0x18003f75e  test    rax, rax
0x18003f761  jnz     short loc_18003F7DF
0x18003f763  mov     rdx, rdi
0x18003f766  lea     rcx, [rsp+48h+arg_10]
0x18003f76b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003f770  mov     rbx, rax
0x18003f773  call    cs:__imp_GetCurrentThreadId
0x18003f779  mov     edi, eax
0x18003f77b  mov     rdx, rbx
0x18003f77e  lea     rcx, [rsp+48h+arg_8]
0x18003f783  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f6fe95fbd0e579a934da851dfbdc5e9e_____lambda_f6fe95fbd0e579a934da851dfbdc5e9e___
0x18003f788  mov     rbx, [rax]
0x18003f78b  mov     qword ptr [rax], 0
0x18003f792  mov     rcx, [rsp+48h+arg_8]
0x18003f797  test    rcx, rcx
0x18003f79a  jz      short loc_18003F7AA
0x18003f79c  mov     [rsp+48h+arg_8], 0
0x18003f7a5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x18003f7aa  mov     [rsp+48h+var_20], 0
0x18003f7b3  mov     [rsp+48h+var_28], rbx
0x18003f7b8  xor     r9d, r9d
0x18003f7bb  mov     r8d, edi
0x18003f7be  xor     edx, edx
0x18003f7c0  lea     ecx, [rdx+1]
0x18003f7c3  call    cs:__imp_SHTaskPoolQueueTask
0x18003f7c9  nop
0x18003f7ca  test    rbx, rbx
0x18003f7cd  jz      short loc_18003F7DF
0x18003f7cf  mov     rax, [rbx]
0x18003f7d2  mov     rcx, rbx
0x18003f7d5  mov     rax, [rax+10h]
0x18003f7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7de  nop
0x18003f7df  lea     rax, WPP_GLOBAL_Control
0x18003f7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f7ed  cmp     rcx, rax
0x18003f7f0  jz      short loc_18003F804
0x18003f7f2  test    byte ptr [rcx+1Ch], 8
0x18003f7f6  jz      short loc_18003F804
0x18003f7f8  mov     r9d, esi
0x18003f7fb  mov     rcx, [rcx+10h]
0x18003f7ff  call    WPP_SF_d
0x18003f804  xor     eax, eax
0x18003f806  mov     rbx, [rsp+48h+arg_0]
0x18003f80b  add     rsp, 30h
0x18003f80f  pop     rdi
0x18003f810  pop     rsi
0x18003f811  pop     rbp
0x18003f812  retn
```
