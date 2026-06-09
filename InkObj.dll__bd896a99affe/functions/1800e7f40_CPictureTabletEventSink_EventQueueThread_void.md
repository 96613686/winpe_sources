# CPictureTabletEventSink::EventQueueThread(void *)

- ea: `0x1800e7f40`
- end: `0x1800e7fd5`
- name: `?EventQueueThread@CPictureTabletEventSink@@SAIPEAX@Z`
- size: `149`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800a9f84`
- `0x1800af878`
- `0x1800e7f40`
- `0x1800e8758`

## import_xrefs

- `msvcrt!_endthreadex` at `0x1800e7fbd`
- `msvcrt!_endthreadex` at `0x1800e7fbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e7f8a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e7f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e7f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e7f72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e7f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e7f72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800e7f60`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800e7f60`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e7fb5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e7fb5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e7f6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e7f6a`

## pseudocode

```c
__int64 __fastcall CPictureTabletEventSink::EventQueueThread(void *a1)
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
      CPictureTabletEventSink::FireEvent((CPictureTabletEventSink *)a1, v5);
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
0x1800e7f40  mov     [rsp+arg_0], rbx
0x1800e7f45  mov     [rsp+arg_8], rsi
0x1800e7f4a  push    rdi
0x1800e7f4b  sub     rsp, 20h
0x1800e7f4f  mov     rdi, rcx
0x1800e7f52  call    cs:__imp_GetCurrentThread
0x1800e7f58  mov     rcx, rax; hThread
0x1800e7f5b  mov     edx, 2; nPriority
0x1800e7f60  call    cs:__imp_SetThreadPriority
0x1800e7f66  xor     edx, edx; dwCoInit
0x1800e7f68  xor     ecx, ecx; pvReserved
0x1800e7f6a  call    cs:__imp_CoInitializeEx
0x1800e7f70  mov     esi, eax
0x1800e7f72  call    cs:__imp_GetCurrentThread
0x1800e7f78  mov     [rdi+80h], rax
0x1800e7f7f  test    esi, esi
0x1800e7f81  js      short loc_1800E7FBB
0x1800e7f83  mov     rcx, [rdi+0A0h]; hEvent
0x1800e7f8a  call    cs:__imp_SetEvent
0x1800e7f90  jmp     short loc_1800E7FA5
0x1800e7f92  mov     rdx, rbx; struct CTabletEventSinkEvent *
0x1800e7f95  mov     rcx, rdi; this
0x1800e7f98  call    ?FireEvent@CPictureTabletEventSink@@QEAAXPEAVCTabletEventSinkEvent@@@Z; CPictureTabletEventSink::FireEvent(CTabletEventSinkEvent *)
0x1800e7f9d  mov     rcx, rbx; this
0x1800e7fa0  call    ??_GCTabletEventSinkEvent@@QEAAPEAXI@Z; CTabletEventSinkEvent::`scalar deleting destructor'(uint)
0x1800e7fa5  mov     rcx, rdi; this
0x1800e7fa8  call    ?WaitForEvent@CPictureTabletEventSink@@QEAAPEAVCTabletEventSinkEvent@@XZ; CPictureTabletEventSink::WaitForEvent(void)
0x1800e7fad  mov     rbx, rax
0x1800e7fb0  test    rax, rax
0x1800e7fb3  jnz     short loc_1800E7F92
0x1800e7fb5  call    cs:__imp_CoUninitialize
0x1800e7fbb  mov     ecx, esi; ReturnCode
0x1800e7fbd  call    cs:__imp__endthreadex
0x1800e7fc3  mov     rbx, [rsp+28h+arg_0]
0x1800e7fc8  mov     eax, esi
0x1800e7fca  mov     rsi, [rsp+28h+arg_8]
0x1800e7fcf  add     rsp, 20h
0x1800e7fd3  pop     rdi
0x1800e7fd4  retn
```
