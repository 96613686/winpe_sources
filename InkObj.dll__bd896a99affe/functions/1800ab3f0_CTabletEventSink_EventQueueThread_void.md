# CTabletEventSink::EventQueueThread(void *)

- ea: `0x1800ab3f0`
- end: `0x1800ab485`
- name: `?EventQueueThread@CTabletEventSink@@SAIPEAX@Z`
- size: `149`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800a9f84`
- `0x1800ab3f0`
- `0x1800abc68`
- `0x1800af878`

## import_xrefs

- `msvcrt!_endthreadex` at `0x1800ab46d`
- `msvcrt!_endthreadex` at `0x1800ab46d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ab43a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ab43a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab422`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ab410`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ab410`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ab465`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ab465`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ab41a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ab41a`

## pseudocode

```c
__int64 __fastcall CTabletEventSink::EventQueueThread(void *a1)
{
  HANDLE CurrentThread; // rax
  HRESULT v3; // esi
  unsigned int v4; // edx
  struct CTabletEventSinkEvent *v5; // rax
  CTabletEventSinkEvent *v6; // rbx

  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 2);
  v3 = CoInitializeEx(0, 0);
  *((_QWORD *)a1 + 16) = GetCurrentThread();
  if ( v3 >= 0 )
  {
    SetEvent(*((HANDLE *)a1 + 20));
    while ( 1 )
    {
      v5 = CPictureTabletEventSink::WaitForEvent((CPictureTabletEventSink *)a1);
      v6 = v5;
      if ( !v5 )
        break;
      CTabletEventSink::FireEvent((CTabletEventSink *)a1, v5);
      CTabletEventSinkEvent::`scalar deleting destructor'(v6, v4);
    }
    CoUninitialize();
  }
  _endthreadex(v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ab3f0  mov     [rsp+arg_0], rbx
0x1800ab3f5  mov     [rsp+arg_8], rsi
0x1800ab3fa  push    rdi
0x1800ab3fb  sub     rsp, 20h
0x1800ab3ff  mov     rdi, rcx
0x1800ab402  call    cs:__imp_GetCurrentThread
0x1800ab408  mov     rcx, rax; hThread
0x1800ab40b  mov     edx, 2; nPriority
0x1800ab410  call    cs:__imp_SetThreadPriority
0x1800ab416  xor     edx, edx; dwCoInit
0x1800ab418  xor     ecx, ecx; pvReserved
0x1800ab41a  call    cs:__imp_CoInitializeEx
0x1800ab420  mov     esi, eax
0x1800ab422  call    cs:__imp_GetCurrentThread
0x1800ab428  mov     [rdi+80h], rax
0x1800ab42f  test    esi, esi
0x1800ab431  js      short loc_1800AB46B
0x1800ab433  mov     rcx, [rdi+0A0h]; hEvent
0x1800ab43a  call    cs:__imp_SetEvent
0x1800ab440  jmp     short loc_1800AB455
0x1800ab442  mov     rdx, rbx; struct CTabletEventSinkEvent *
0x1800ab445  mov     rcx, rdi; this
0x1800ab448  call    ?FireEvent@CTabletEventSink@@QEAAXPEAVCTabletEventSinkEvent@@@Z; CTabletEventSink::FireEvent(CTabletEventSinkEvent *)
0x1800ab44d  mov     rcx, rbx; this
0x1800ab450  call    ??_GCTabletEventSinkEvent@@QEAAPEAXI@Z; CTabletEventSinkEvent::`scalar deleting destructor'(uint)
0x1800ab455  mov     rcx, rdi; this
0x1800ab458  call    ?WaitForEvent@CPictureTabletEventSink@@QEAAPEAVCTabletEventSinkEvent@@XZ; CPictureTabletEventSink::WaitForEvent(void)
0x1800ab45d  mov     rbx, rax
0x1800ab460  test    rax, rax
0x1800ab463  jnz     short loc_1800AB442
0x1800ab465  call    cs:__imp_CoUninitialize
0x1800ab46b  mov     ecx, esi; ReturnCode
0x1800ab46d  call    cs:__imp__endthreadex
0x1800ab473  mov     rbx, [rsp+28h+arg_0]
0x1800ab478  mov     eax, esi
0x1800ab47a  mov     rsi, [rsp+28h+arg_8]
0x1800ab47f  add     rsp, 20h
0x1800ab483  pop     rdi
0x1800ab484  retn
```
