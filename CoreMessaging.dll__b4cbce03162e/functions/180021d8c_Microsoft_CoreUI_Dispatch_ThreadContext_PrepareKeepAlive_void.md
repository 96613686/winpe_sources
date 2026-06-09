# Microsoft::CoreUI::Dispatch::ThreadContext::PrepareKeepAlive(void *)

- ea: `0x180021d8c`
- end: `0x180021e2f`
- name: `?PrepareKeepAlive@ThreadContext@Dispatch@CoreUI@Microsoft@@AEAAXPEAX@Z`
- size: `163`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::ThreadContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e760`

## callees

- `0x180007d80`
- `0x180020068`
- `0x180021d8c`
- `0x180021e80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021da1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021da1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021ddf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021ddf`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::ThreadContext::PrepareKeepAlive(
        Microsoft::CoreUI::Dispatch::ThreadContext *this,
        volatile signed __int64 *a2)
{
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  HANDLE v10; // rdx
  HANDLE TargetHandle; // [rsp+58h] [rbp+10h] BYREF

  CurrentProcess = GetCurrentProcess();
  TargetHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, &TargetHandle, 0, 0, 2u)
    || (v10 = TargetHandle,
        *((_QWORD *)this + 27) = TargetHandle,
        !Microsoft::CoreUI::Support::ThreadPoolWait::RegisterWait(
           (struct _TP_WAIT **)this + 26,
           v10,
           (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WAIT, TP_WAIT_RESULT))Microsoft::CoreUI::Dispatch::ThreadContext_ThreadSignaledOrInterconnectAck,
           (void *)a2)) )
  {
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v7,
      v6,
      v8,
      v9);
  }
  Microsoft::CoreUI::CoreUISession::AddRef();
  _InterlockedIncrement64(a2 + 4);
}

```

## disassembly

```asm
0x180021d8c  mov     [rsp+arg_0], rbx
0x180021d91  mov     [rsp+arg_10], rsi
0x180021d96  push    rdi
0x180021d97  sub     rsp, 40h
0x180021d9b  mov     rdi, rdx
0x180021d9e  mov     rsi, rcx
0x180021da1  call    cs:__imp_GetCurrentProcess
0x180021da7  mov     rbx, rax
0x180021daa  mov     [rsp+48h+TargetHandle], 0
0x180021db3  call    cs:__imp_GetCurrentThread
0x180021db9  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180021dc1  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180021dc6  mov     rdx, rax; hSourceHandle
0x180021dc9  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180021dd1  mov     r8, rbx; hTargetProcessHandle
0x180021dd4  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x180021ddc  mov     rcx, rbx; hSourceProcessHandle
0x180021ddf  call    cs:__imp_DuplicateHandle
0x180021de5  test    eax, eax
0x180021de7  jnz     short loc_180021DEF
0x180021de9  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180021def  mov     rdx, [rsp+48h+TargetHandle]
0x180021df4  lea     rcx, [rsi+0D0h]
0x180021dfb  mov     r9, rdi
0x180021dfe  mov     [rsi+0D8h], rdx
0x180021e05  lea     r8, ?ThreadContext_ThreadSignaledOrInterconnectAck@Dispatch@CoreUI@Microsoft@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; Microsoft::CoreUI::Dispatch::ThreadContext_ThreadSignaledOrInterconnectAck(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x180021e0c  call    ?RegisterWait@ThreadPoolWait@Support@CoreUI@Microsoft@@QEAA_NUWin32Handle@234@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z2@Z; Microsoft::CoreUI::Support::ThreadPoolWait::RegisterWait(Microsoft::CoreUI::Support::Win32Handle,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *)
0x180021e11  test    al, al
0x180021e13  jz      short loc_180021DE9
0x180021e15  call    ?AddRef@CoreUISession@CoreUI@Microsoft@@SAXXZ; Microsoft::CoreUI::CoreUISession::AddRef(void)
0x180021e1a  lock inc qword ptr [rdi+20h]
0x180021e1f  mov     rbx, [rsp+48h+arg_0]
0x180021e24  mov     rsi, [rsp+48h+arg_10]
0x180021e29  add     rsp, 40h
0x180021e2d  pop     rdi
0x180021e2e  retn
```
