# Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::ChangeNotificationWorkerCallBack(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140017470`
- end: `0x1400174c8`
- name: `?ChangeNotificationWorkerCallBack@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `88`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x1400177dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140017479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400174a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140017479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400174a3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14001748d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14001748d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400174bc`

## pseudocode

```c
void __fastcall Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::ChangeNotificationWorkerCallBack(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  HANDLE v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 0x10000);
  try
  {
    Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DispatchChangeNotification(Context);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\DataChangeListener.h",
      v5);
  }
  v6 = GetCurrentThread();
  SetThreadPriority(v6, 0x20000);
}

```

## disassembly

```asm
0x140017470  push    rbx
0x140017472  sub     rsp, 20h
0x140017476  mov     rbx, rdx
0x140017479  call    cs:__imp_GetCurrentThread
0x140017480  nop     dword ptr [rax+rax+00h]
0x140017485  mov     rcx, rax; hThread
0x140017488  mov     edx, 10000h; nPriority
0x14001748d  call    cs:__imp_SetThreadPriority
0x140017494  nop     dword ptr [rax+rax+00h]
0x140017499  nop
0x14001749a  mov     rcx, rbx
0x14001749d  call    ?DispatchChangeNotification@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@AEAAXXZ; Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DispatchChangeNotification(void)
0x1400174a2  nop
0x1400174a3  call    cs:__imp_GetCurrentThread
0x1400174aa  nop     dword ptr [rax+rax+00h]
0x1400174af  mov     rcx, rax
0x1400174b2  mov     edx, 20000h
0x1400174b7  add     rsp, 20h
0x1400174bb  pop     rbx
0x1400174bc  jmp     cs:__imp_SetThreadPriority
```
