# COverlayTabletEventSink::EventQueueThread(void *)

- ea: `0x1800d9d10`
- end: `0x1800d9da5`
- name: `?EventQueueThread@COverlayTabletEventSink@@SAIPEAX@Z`
- size: `149`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800a9f84`
- `0x1800af878`
- `0x1800d9d10`
- `0x1800da510`

## import_xrefs

- `msvcrt!_endthreadex` at `0x1800d9d8d`
- `msvcrt!_endthreadex` at `0x1800d9d8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d9d5a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d9d5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9d22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9d42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9d22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9d42`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800d9d30`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800d9d30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d9d85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d9d85`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d9d3a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d9d3a`

## pseudocode

```c
__int64 __fastcall COverlayTabletEventSink::EventQueueThread(void *a1)
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
      COverlayTabletEventSink::FireEvent((COverlayTabletEventSink *)a1, v5);
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
0x1800d9d10  mov     [rsp+arg_0], rbx
0x1800d9d15  mov     [rsp+arg_8], rsi
0x1800d9d1a  push    rdi
0x1800d9d1b  sub     rsp, 20h
0x1800d9d1f  mov     rdi, rcx
0x1800d9d22  call    cs:__imp_GetCurrentThread
0x1800d9d28  mov     rcx, rax; hThread
0x1800d9d2b  mov     edx, 2; nPriority
0x1800d9d30  call    cs:__imp_SetThreadPriority
0x1800d9d36  xor     edx, edx; dwCoInit
0x1800d9d38  xor     ecx, ecx; pvReserved
0x1800d9d3a  call    cs:__imp_CoInitializeEx
0x1800d9d40  mov     esi, eax
0x1800d9d42  call    cs:__imp_GetCurrentThread
0x1800d9d48  mov     [rdi+80h], rax
0x1800d9d4f  test    esi, esi
0x1800d9d51  js      short loc_1800D9D8B
0x1800d9d53  mov     rcx, [rdi+0A0h]; hEvent
0x1800d9d5a  call    cs:__imp_SetEvent
0x1800d9d60  jmp     short loc_1800D9D75
0x1800d9d62  mov     rdx, rbx; struct CTabletEventSinkEvent *
0x1800d9d65  mov     rcx, rdi; this
0x1800d9d68  call    ?FireEvent@COverlayTabletEventSink@@QEAAXPEAVCTabletEventSinkEvent@@@Z; COverlayTabletEventSink::FireEvent(CTabletEventSinkEvent *)
0x1800d9d6d  mov     rcx, rbx; this
0x1800d9d70  call    ??_GCTabletEventSinkEvent@@QEAAPEAXI@Z; CTabletEventSinkEvent::`scalar deleting destructor'(uint)
0x1800d9d75  mov     rcx, rdi; this
0x1800d9d78  call    ?WaitForEvent@CPictureTabletEventSink@@QEAAPEAVCTabletEventSinkEvent@@XZ; CPictureTabletEventSink::WaitForEvent(void)
0x1800d9d7d  mov     rbx, rax
0x1800d9d80  test    rax, rax
0x1800d9d83  jnz     short loc_1800D9D62
0x1800d9d85  call    cs:__imp_CoUninitialize
0x1800d9d8b  mov     ecx, esi; ReturnCode
0x1800d9d8d  call    cs:__imp__endthreadex
0x1800d9d93  mov     rbx, [rsp+28h+arg_0]
0x1800d9d98  mov     eax, esi
0x1800d9d9a  mov     rsi, [rsp+28h+arg_8]
0x1800d9d9f  add     rsp, 20h
0x1800d9da3  pop     rdi
0x1800d9da4  retn
```
