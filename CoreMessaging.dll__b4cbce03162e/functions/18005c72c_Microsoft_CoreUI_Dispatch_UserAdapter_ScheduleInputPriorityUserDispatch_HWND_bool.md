# Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleInputPriorityUserDispatch(HWND__ *,bool)

- ea: `0x18005c72c`
- end: `0x18005c926`
- name: `?ScheduleInputPriorityUserDispatch@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@_N@Z`
- size: `506`
- prototype: `void __fastcall(HWND hWnd, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007550`
- `0x18005c4d0`

## callees

- `0x180007d80`
- `0x18005b068`
- `0x18005c72c`
- `0x18005c92c`
- `0x18005ca5c`
- `0x18005cb4c`
- `0x18008f584`
- `0x18009e558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c891`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c83f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c8b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c83f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c8b6`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_ScheduleDispatchNotification` at `0x18005c7b1`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_ScheduleDispatchNotification` at `0x18005c7b1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x18005c767`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x18005c767`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x18005c803`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x18005c803`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!ScheduleCoreMessagingDispatch` at `0x18005c865`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!ScheduleCoreMessagingDispatch` at `0x18005c8d7`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!ScheduleCoreMessagingDispatch` at `0x18005c865`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!ScheduleCoreMessagingDispatch` at `0x18005c8d7`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleInputPriorityUserDispatch(HWND hWnd, char a2)
{
  bool v3; // bl
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD v10; // eax
  int v11; // ebx
  bool v12; // bl
  DWORD v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  bool v18; // zf
  DWORD v19; // [rsp+50h] [rbp+20h] BYREF

  if ( a2 )
  {
    if ( (unsigned __int8)IsScheduleCoreMessagingDispatchPresent() )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) )
        CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
          v15,
          v14,
          v16,
          v17);
      v18 = (unsigned int)ScheduleCoreMessagingDispatch(hWnd, 1, 6) == 0;
      LastError = 0;
      v3 = !v18;
    }
    else if ( PostMessageW(hWnd, 0x60u, 6u, 0) )
    {
      v3 = 1;
      LastError = 0;
    }
    else
    {
      v3 = 0;
      LastError = GetLastError();
    }
    if ( !v3 )
      Microsoft::CoreUI::Dispatch::UserAdapter::OnScheduleUserDispatchFailure(hWnd, LastError);
    Microsoft::CoreUI::Dispatch::UserAdapter::SetTlsFlags(4);
    return;
  }
  if ( (unsigned __int8)IsScheduleCoreMessagingDispatchPresent() )
  {
    if ( TlsGetValue(Cn::Context::s_tlsStorage) )
      goto LABEL_32;
    v7 = ScheduleCoreMessagingDispatch(hWnd, 2, 0);
    v10 = 0;
  }
  else
  {
    v7 = ScheduleDispatchNotification(hWnd);
    if ( v7 )
      v10 = 0;
    else
      v10 = GetLastError();
  }
  if ( !v7 )
  {
    Microsoft::CoreUI::Dispatch::UserAdapter::OnScheduleUserDispatchFailure(hWnd, v10);
    return;
  }
  v11 = v7 - 1;
  if ( !v11 )
  {
    Microsoft::CoreUI::Dispatch::UserAdapter::AsyncSendMessage(hWnd, 7u, 0);
    return;
  }
  if ( v11 != 1 )
LABEL_32:
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v6,
      v5,
      v8,
      v9);
  v19 = 0;
  if ( (unsigned __int8)IsScheduleCoreMessagingDispatchPresent() )
  {
    v18 = (unsigned int)Microsoft::CoreUI::Dispatch::UserAdapter_ScheduleCoreMessagingDispatch(hWnd, 3, 1, 0, &v19) == 0;
    v13 = v19;
    v12 = !v18;
  }
  else
  {
    v12 = 1;
    if ( SetTimer(hWnd, 1u, 0, 0) )
    {
      v13 = 0;
    }
    else
    {
      v12 = 0;
      v13 = GetLastError();
    }
    v19 = v13;
  }
  if ( !v12 && v13 != 1400 )
    Cn::FailFast::ForWin32();
}

```

## disassembly

```asm
0x18005c72c  mov     [rsp-8+arg_0], rbx
0x18005c731  mov     [rsp-8+arg_18], rdi
0x18005c736  push    rbp
0x18005c737  mov     rbp, rsp
0x18005c73a  sub     rsp, 30h
0x18005c73e  mov     [rbp+arg_8], 0
0x18005c745  mov     rdi, rcx
0x18005c748  test    dl, dl
0x18005c74a  jz      short loc_18005C7A1
0x18005c74c  call    IsScheduleCoreMessagingDispatchPresent
0x18005c751  test    al, al
0x18005c753  jnz     loc_18005C839
0x18005c759  xor     r9d, r9d; lParam
0x18005c75c  mov     rcx, rdi; hWnd
0x18005c75f  lea     edx, [r9+60h]; Msg
0x18005c763  lea     r8d, [r9+6]; wParam
0x18005c767  call    cs:__imp_PostMessageW
0x18005c76d  test    eax, eax
0x18005c76f  jz      loc_18005C82C
0x18005c775  mov     ebx, 1
0x18005c77a  xor     eax, eax
0x18005c77c  mov     [rbp+arg_8], eax
0x18005c77f  test    bl, bl
0x18005c781  jz      loc_18005C8ED
0x18005c787  mov     ecx, 4
0x18005c78c  call    ?SetTlsFlags@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXW4UserAdapter$TlsFlags@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::SetTlsFlags(Microsoft::CoreUI::Dispatch::UserAdapter$TlsFlags)
0x18005c791  mov     rbx, [rsp+30h+arg_0]
0x18005c796  mov     rdi, [rsp+30h+arg_18]
0x18005c79b  add     rsp, 30h
0x18005c79f  pop     rbp
0x18005c7a0  retn
0x18005c7a1  call    IsScheduleCoreMessagingDispatchPresent
0x18005c7a6  test    al, al
0x18005c7a8  jnz     loc_18005C8B0
0x18005c7ae  mov     rcx, rdi
0x18005c7b1  call    cs:__imp_ScheduleDispatchNotification
0x18005c7b7  mov     ebx, eax
0x18005c7b9  test    eax, eax
0x18005c7bb  jz      loc_18005C891
0x18005c7c1  xor     eax, eax
0x18005c7c3  mov     [rbp+arg_8], eax
0x18005c7c6  test    ebx, ebx
0x18005c7c8  jz      loc_18005C882
0x18005c7ce  sub     ebx, 1
0x18005c7d1  jz      loc_18005C89C
0x18005c7d7  cmp     ebx, 1
0x18005c7da  jnz     loc_18005C8FC
0x18005c7e0  mov     [rbp+arg_10], 0
0x18005c7e7  call    IsScheduleCoreMessagingDispatchPresent
0x18005c7ec  xor     r9d, r9d; lpTimerFunc
0x18005c7ef  mov     rcx, rdi; hWnd
0x18005c7f2  test    al, al
0x18005c7f4  jnz     loc_18005C902
0x18005c7fa  lea     ebx, [r9+1]
0x18005c7fe  xor     r8d, r8d; uElapse
0x18005c801  mov     edx, ebx; nIDEvent
0x18005c803  call    cs:__imp_SetTimer
0x18005c809  test    rax, rax
0x18005c80c  jz      short loc_18005C878
0x18005c80e  xor     eax, eax
0x18005c810  mov     [rbp+arg_10], eax
0x18005c813  test    bl, bl
0x18005c815  jnz     loc_18005C791
0x18005c81b  cmp     eax, 578h
0x18005c820  jz      loc_18005C791
0x18005c826  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18005c82c  xor     bl, bl
0x18005c82e  call    cs:__imp_GetLastError
0x18005c834  jmp     loc_18005C77C
0x18005c839  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005c83f  call    cs:__imp_TlsGetValue
0x18005c845  test    rax, rax
0x18005c848  jnz     loc_18005C8E7
0x18005c84e  xor     r9d, r9d
0x18005c851  lea     rax, [rbp+arg_8]
0x18005c855  mov     rcx, rdi
0x18005c858  mov     [rsp+30h+var_10], rax
0x18005c85d  lea     edx, [r9+1]
0x18005c861  lea     r8d, [r9+6]
0x18005c865  call    cs:__imp_ScheduleCoreMessagingDispatch
0x18005c86b  test    eax, eax
0x18005c86d  mov     eax, [rbp+arg_8]
0x18005c870  setnz   bl
0x18005c873  jmp     loc_18005C77F
0x18005c878  xor     bl, bl
0x18005c87a  call    cs:__imp_GetLastError
0x18005c880  jmp     short loc_18005C810
0x18005c882  mov     edx, eax; unsigned int
0x18005c884  mov     rcx, rdi; hWnd
0x18005c887  call    ?OnScheduleUserDispatchFailure@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAXI@Z; Microsoft::CoreUI::Dispatch::UserAdapter::OnScheduleUserDispatchFailure(void *,uint)
0x18005c88c  jmp     loc_18005C791
0x18005c891  call    cs:__imp_GetLastError
0x18005c897  jmp     loc_18005C7C3
0x18005c89c  xor     r8d, r8d; lParam
0x18005c89f  mov     rcx, rdi; hWnd
0x18005c8a2  lea     edx, [r8+7]; wParam
0x18005c8a6  call    ?AsyncSendMessage@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@_K_J@Z; Microsoft::CoreUI::Dispatch::UserAdapter::AsyncSendMessage(HWND__ *,unsigned __int64,__int64)
0x18005c8ab  jmp     loc_18005C791
0x18005c8b0  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005c8b6  call    cs:__imp_TlsGetValue
0x18005c8bc  test    rax, rax
0x18005c8bf  jnz     short loc_18005C8FC
0x18005c8c1  xor     r9d, r9d
0x18005c8c4  lea     rax, [rbp+arg_8]
0x18005c8c8  xor     r8d, r8d
0x18005c8cb  mov     [rsp+30h+var_10], rax
0x18005c8d0  mov     rcx, rdi
0x18005c8d3  lea     edx, [r9+2]
0x18005c8d7  call    cs:__imp_ScheduleCoreMessagingDispatch
0x18005c8dd  mov     ebx, eax
0x18005c8df  mov     eax, [rbp+arg_8]
0x18005c8e2  jmp     loc_18005C7C6
0x18005c8e7  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18005c8ed  mov     edx, eax; unsigned int
0x18005c8ef  mov     rcx, rdi; hWnd
0x18005c8f2  call    ?OnScheduleUserDispatchFailure@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAXI@Z; Microsoft::CoreUI::Dispatch::UserAdapter::OnScheduleUserDispatchFailure(void *,uint)
0x18005c8f7  jmp     loc_18005C787
0x18005c8fc  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18005c902  mov     edx, 3
0x18005c907  lea     rax, [rbp+arg_10]
0x18005c90b  mov     [rsp+30h+var_10], rax
0x18005c910  lea     r8d, [rdx-2]
0x18005c914  call    ?UserAdapter_ScheduleCoreMessagingDispatch@Dispatch@CoreUI@Microsoft@@YAIPEAUHWND__@@W4tagCoreMsgDispatchPriority@@_K_JPEAI@Z; Microsoft::CoreUI::Dispatch::UserAdapter_ScheduleCoreMessagingDispatch(HWND__ *,tagCoreMsgDispatchPriority,unsigned __int64,__int64,uint *)
0x18005c919  test    eax, eax
0x18005c91b  mov     eax, [rbp+arg_10]
0x18005c91e  setnz   bl
0x18005c921  jmp     loc_18005C813
```
