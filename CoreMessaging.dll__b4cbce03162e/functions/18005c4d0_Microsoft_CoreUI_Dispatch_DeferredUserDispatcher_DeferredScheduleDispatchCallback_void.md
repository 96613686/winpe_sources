# Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)

- ea: `0x18005c4d0`
- end: `0x18005c726`
- name: `?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z`
- size: `598`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180007d80`
- `0x180039dbc`
- `0x18005b068`
- `0x18005c4d0`
- `0x18005c72c`
- `0x18005c96c`
- `0x18005cb4c`
- `0x18008ca4c`
- `0x18008f584`
- `0x18009e558`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c679`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c6c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c679`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c6c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c5fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c63c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c523`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005c5d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005c5d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c4ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c4ec`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x18005c62d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetTimer` at `0x18005c62d`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *a1)
{
  int v1; // ebp
  _DWORD *Value; // rsi
  int v3; // ebx
  __int64 v4; // rdi
  char v5; // r14
  __int64 v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  HWND v14; // rbx
  DWORD LastError; // eax
  unsigned int v16; // ebx
  DWORD v17; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  Value = TlsGetValue(Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::s_tlsIndex);
  if ( Value[52] )
  {
    while ( 1 )
    {
      v3 = *(_DWORD *)(*(_QWORD *)Value + 24LL * v1);
      v4 = *(_QWORD *)(*(_QWORD *)Value + 24LL * v1 + 8);
      v5 = *(_BYTE *)(*(_QWORD *)Value + 24LL * v1 + 16);
      v6 = *(unsigned int *)(*(_QWORD *)Value + 24LL * v1 + 20);
      if ( GetCurrentThreadId() != *(_DWORD *)(v4 + 8) )
        SetEvent(*(HANDLE *)(v4 + 16));
      if ( v3 > 10 )
        break;
      if ( v3 > 6 )
      {
        v11 = 4;
        goto LABEL_8;
      }
      if ( v3 > 1 )
      {
        v11 = 3;
        goto LABEL_8;
      }
      if ( v3 <= 0 )
      {
        v11 = 0;
        goto LABEL_8;
      }
      v11 = 1;
LABEL_9:
      if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
        McTemplateU0qq_EventWriteTransfer(v8, &Adapter_ScheduleDispatch, *(unsigned int *)(v4 + 8), v11);
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 2;
        if ( v13 )
        {
          v16 = v13 - 1;
          if ( v16 )
          {
            if ( v16 != 1 )
LABEL_38:
              CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
                v8,
                v7,
                v9,
                v10);
            Microsoft::CoreUI::Dispatch::UserAdapter::AsyncSendMessage(*(HWND *)v4, 5u, 5);
          }
          else
          {
            Microsoft::CoreUI::Dispatch::UserAdapter::AsyncPostMessage(*(HWND *)v4, 5u, 4);
          }
        }
        else
        {
          Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleInputPriorityUserDispatch(*(HWND *)v4, v5);
        }
        goto LABEL_14;
      }
      v14 = *(HWND *)v4;
      v17 = 0;
      if ( (unsigned __int8)IsScheduleCoreMessagingDispatchPresent() )
      {
        if ( !(unsigned int)Microsoft::CoreUI::Dispatch::UserAdapter_ScheduleCoreMessagingDispatch(v14, 3, 1, v6, &v17) )
        {
          LastError = v17;
LABEL_36:
          if ( LastError != 1400 )
            Cn::FailFast::ForWin32();
        }
      }
      else if ( !SetTimer(v14, 1u, v6, 0) )
      {
        LastError = GetLastError();
        v17 = LastError;
        goto LABEL_36;
      }
LABEL_14:
      if ( *(int *)(v4 + 32) < 1 )
        goto LABEL_38;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 32), 0xFFFFFFFF) == 1 )
        free((void *)v4);
      if ( (unsigned int)++v1 >= Value[52] )
        goto LABEL_18;
    }
    v11 = 5;
LABEL_8:
    if ( _interlockedbittestandset((volatile signed __int32 *)(v4 + 24), v11) )
      goto LABEL_14;
    goto LABEL_9;
  }
LABEL_18:
  Value[52] = 0;
  if ( _InterlockedCompareExchange64(
         (volatile signed __int64 *)&Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::s_cachedUserDispatcher,
         (signed __int64)Value,
         0) )
  {
    Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(Value);
    free(Value);
  }
  if ( !TlsSetValue(Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::s_tlsIndex, 0) )
    Cn::FailFast::ForWin32();
}

```

## disassembly

```asm
0x18005c4d0  mov     [rsp+arg_0], rbx
0x18005c4d5  mov     [rsp+arg_10], rbp
0x18005c4da  push    rsi
0x18005c4db  push    rdi
0x18005c4dc  push    r13
0x18005c4de  push    r14
0x18005c4e0  push    r15
0x18005c4e2  sub     rsp, 30h
0x18005c4e6  mov     ecx, cs:?s_tlsIndex@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@0KA; dwTlsIndex
0x18005c4ec  call    cs:__imp_TlsGetValue
0x18005c4f2  xor     ebp, ebp
0x18005c4f4  mov     rsi, rax
0x18005c4f7  cmp     [rax+0D0h], ebp
0x18005c4fd  jbe     loc_18005C5B2
0x18005c503  lea     r13d, [rbp+1]
0x18005c507  movsxd  rax, ebp
0x18005c50a  lea     rcx, [rax+rax*2]
0x18005c50e  mov     rax, [rsi]
0x18005c511  mov     ebx, [rax+rcx*8]
0x18005c514  mov     rdi, [rax+rcx*8+8]
0x18005c519  mov     r14b, [rax+rcx*8+10h]
0x18005c51e  mov     r15d, [rax+rcx*8+14h]
0x18005c523  call    cs:__imp_GetCurrentThreadId
0x18005c529  cmp     eax, [rdi+8]
0x18005c52c  jnz     loc_18005C5FA
0x18005c532  cmp     ebx, 0Ah
0x18005c535  jg      loc_18005C68F
0x18005c53b  cmp     ebx, 6
0x18005c53e  jg      loc_18005C64B
0x18005c544  cmp     ebx, r13d
0x18005c547  jle     loc_18005C684
0x18005c54d  mov     ebx, 3
0x18005c552  lock bts [rdi+18h], ebx
0x18005c557  setb    al
0x18005c55a  test    al, al
0x18005c55c  jnz     short loc_18005C588
0x18005c55e  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x18005c565  jnz     loc_18005C6CB
0x18005c56b  sub     ebx, r13d
0x18005c56e  jz      loc_18005C609
0x18005c574  sub     ebx, 2
0x18005c577  jnz     loc_18005C655
0x18005c57d  mov     rcx, [rdi]; hWnd
0x18005c580  mov     dl, r14b; bool
0x18005c583  call    ?ScheduleInputPriorityUserDispatch@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@_N@Z; Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleInputPriorityUserDispatch(HWND__ *,bool)
0x18005c588  cmp     [rdi+20h], r13d
0x18005c58c  jl      loc_18005C71A
0x18005c592  or      eax, 0FFFFFFFFh
0x18005c595  lock xadd [rdi+20h], eax
0x18005c59a  cmp     eax, r13d
0x18005c59d  jz      loc_18005C6BD
0x18005c5a3  add     ebp, r13d
0x18005c5a6  cmp     ebp, [rsi+0D0h]
0x18005c5ac  jb      loc_18005C507
0x18005c5b2  mov     dword ptr [rsi+0D0h], 0
0x18005c5bc  xor     eax, eax
0x18005c5be  lock cmpxchg cs:?s_cachedUserDispatcher@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@0PEAV1234@EA, rsi; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher * Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::s_cachedUserDispatcher
0x18005c5c7  jnz     loc_18005C66E
0x18005c5cd  mov     ecx, cs:?s_tlsIndex@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@0KA; dwTlsIndex
0x18005c5d3  xor     edx, edx; lpTlsValue
0x18005c5d5  call    cs:__imp_TlsSetValue
0x18005c5db  test    eax, eax
0x18005c5dd  jz      loc_18005C720
0x18005c5e3  mov     rbx, [rsp+58h+arg_0]
0x18005c5e8  mov     rbp, [rsp+58h+arg_10]
0x18005c5ed  add     rsp, 30h
0x18005c5f1  pop     r15
0x18005c5f3  pop     r14
0x18005c5f5  pop     r13
0x18005c5f7  pop     rdi
0x18005c5f8  pop     rsi
0x18005c5f9  retn
0x18005c5fa  mov     rcx, [rdi+10h]; hEvent
0x18005c5fe  call    cs:__imp_SetEvent
0x18005c604  jmp     loc_18005C532
0x18005c609  mov     rbx, [rdi]
0x18005c60c  mov     [rsp+58h+arg_8], 0
0x18005c614  call    IsScheduleCoreMessagingDispatchPresent
0x18005c619  mov     rcx, rbx; hWnd
0x18005c61c  test    al, al
0x18005c61e  jnz     loc_18005C6E3
0x18005c624  xor     r9d, r9d; lpTimerFunc
0x18005c627  mov     r8d, r15d; uElapse
0x18005c62a  mov     rdx, r13; nIDEvent
0x18005c62d  call    cs:__imp_SetTimer
0x18005c633  test    rax, rax
0x18005c636  jnz     loc_18005C588
0x18005c63c  call    cs:__imp_GetLastError
0x18005c642  mov     [rsp+58h+arg_8], eax
0x18005c646  jmp     loc_18005C709
0x18005c64b  mov     ebx, 4
0x18005c650  jmp     loc_18005C552
0x18005c655  sub     ebx, r13d
0x18005c658  jnz     short loc_18005C699
0x18005c65a  mov     rcx, [rdi]; hWnd
0x18005c65d  lea     edx, [rbx+5]; wParam
0x18005c660  lea     r8d, [rbx+4]; lParam
0x18005c664  call    ?AsyncPostMessage@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@_K_J@Z; Microsoft::CoreUI::Dispatch::UserAdapter::AsyncPostMessage(HWND__ *,unsigned __int64,__int64)
0x18005c669  jmp     loc_18005C588
0x18005c66e  mov     rcx, rsi
0x18005c671  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18005c676  mov     rcx, rsi; Block
0x18005c679  call    cs:__imp_free
0x18005c67f  jmp     loc_18005C5CD
0x18005c684  test    ebx, ebx
0x18005c686  jg      short loc_18005C6B5
0x18005c688  xor     ebx, ebx
0x18005c68a  jmp     loc_18005C552
0x18005c68f  mov     ebx, 5
0x18005c694  jmp     loc_18005C552
0x18005c699  cmp     ebx, r13d
0x18005c69c  jnz     short loc_18005C71A
0x18005c69e  mov     rcx, [rdi]; hWnd
0x18005c6a1  mov     eax, 5
0x18005c6a6  mov     r8d, eax; lParam
0x18005c6a9  mov     edx, eax; wParam
0x18005c6ab  call    ?AsyncSendMessage@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@_K_J@Z; Microsoft::CoreUI::Dispatch::UserAdapter::AsyncSendMessage(HWND__ *,unsigned __int64,__int64)
0x18005c6b0  jmp     loc_18005C588
0x18005c6b5  mov     ebx, r13d
0x18005c6b8  jmp     loc_18005C55E
0x18005c6bd  mov     rcx, rdi; Block
0x18005c6c0  call    cs:__imp_free
0x18005c6c6  jmp     loc_18005C5A3
0x18005c6cb  mov     r8d, [rdi+8]
0x18005c6cf  lea     rdx, Adapter_ScheduleDispatch
0x18005c6d6  mov     r9d, ebx
0x18005c6d9  call    McTemplateU0qq_EventWriteTransfer
0x18005c6de  jmp     loc_18005C56B
0x18005c6e3  lea     rax, [rsp+58h+arg_8]
0x18005c6e8  mov     r9, r15
0x18005c6eb  mov     r8, r13
0x18005c6ee  mov     [rsp+58h+var_38], rax
0x18005c6f3  mov     edx, 3
0x18005c6f8  call    ?UserAdapter_ScheduleCoreMessagingDispatch@Dispatch@CoreUI@Microsoft@@YAIPEAUHWND__@@W4tagCoreMsgDispatchPriority@@_K_JPEAI@Z; Microsoft::CoreUI::Dispatch::UserAdapter_ScheduleCoreMessagingDispatch(HWND__ *,tagCoreMsgDispatchPriority,unsigned __int64,__int64,uint *)
0x18005c6fd  test    eax, eax
0x18005c6ff  jnz     loc_18005C588
0x18005c705  mov     eax, [rsp+58h+arg_8]
0x18005c709  cmp     eax, 578h
0x18005c70e  jz      loc_18005C588
0x18005c714  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18005c71a  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18005c720  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
```
