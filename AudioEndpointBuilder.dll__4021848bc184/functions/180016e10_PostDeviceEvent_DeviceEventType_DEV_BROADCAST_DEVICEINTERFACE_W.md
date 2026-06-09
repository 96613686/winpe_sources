# PostDeviceEvent(DeviceEventType,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x180016e10`
- end: `0x180016f03`
- name: `?PostDeviceEvent@@YAJW4DeviceEventType@@PEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016c68`
- `0x180016dac`

## callees

- `0x180016e10`
- `0x18003edc0`
- `0x18003edfc`
- `0x18003f78c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016e33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016e33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016edd`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180016e9f`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180016e9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PostDeviceEvent(int a1, unsigned int *a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rdi
  void *v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  unsigned int v9; // ebx
  signed int LastError; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x18u);
  if ( !v5 )
    return (unsigned int)-2147024882;
  *v5 = &DEVICE_EVENT::`vftable';
  v5[2] = 0;
  *((_DWORD *)v5 + 2) = a1;
  if ( a2 )
  {
    v6 = operator new[](*a2, (const struct std::nothrow_t *)&std::nothrow);
    v7 = (void *)v5[2];
    v5[2] = v6;
    if ( v7 )
      operator delete(v7, 0x20u);
    v8 = (void *)v5[2];
    if ( !v8 )
    {
      v9 = -2147024882;
LABEL_10:
      (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 8LL))(v5, 1);
      return v9;
    }
    memcpy_0(v8, a2, *a2);
  }
  v9 = 0;
  if ( !PostQueuedCompletionStatus(g_WorkerEventPort, 0, (ULONG_PTR)v5, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_10;
  }
  return v9;
}

```

## disassembly

```asm
0x180016e10  mov     [rsp+arg_0], rbx
0x180016e15  mov     [rsp+arg_8], rsi
0x180016e1a  push    rdi
0x180016e1b  sub     rsp, 20h
0x180016e1f  mov     rbx, rdx
0x180016e22  mov     esi, ecx
0x180016e24  call    cs:__imp_GetProcessHeap
0x180016e2a  xor     edx, edx; dwFlags
0x180016e2c  mov     rcx, rax; hHeap
0x180016e2f  lea     r8d, [rdx+18h]; dwBytes
0x180016e33  call    cs:__imp_HeapAlloc
0x180016e39  mov     rdi, rax
0x180016e3c  test    rax, rax
0x180016e3f  jz      loc_180016ED6
0x180016e45  lea     rax, ??_7DEVICE_EVENT@@6B@; const DEVICE_EVENT::`vftable'
0x180016e4c  mov     [rdi], rax
0x180016e4f  mov     qword ptr [rdi+10h], 0
0x180016e57  mov     [rdi+8], esi
0x180016e5a  test    rbx, rbx
0x180016e5d  jz      short loc_180016E8E
0x180016e5f  mov     ecx, [rbx]; unsigned __int64
0x180016e61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016e6d  mov     rcx, [rdi+10h]; void *
0x180016e71  mov     [rdi+10h], rax
0x180016e75  test    rcx, rcx
0x180016e78  jnz     short loc_180016EF4
0x180016e7a  mov     rcx, [rdi+10h]; void *
0x180016e7e  test    rcx, rcx
0x180016e81  jz      short loc_180016EBB
0x180016e83  mov     r8d, [rbx]; Size
0x180016e86  mov     rdx, rbx; Src
0x180016e89  call    memcpy_0
0x180016e8e  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x180016e95  xor     r9d, r9d; lpOverlapped
0x180016e98  mov     r8, rdi; dwCompletionKey
0x180016e9b  xor     edx, edx; dwNumberOfBytesTransferred
0x180016e9d  xor     ebx, ebx
0x180016e9f  call    cs:__imp_PostQueuedCompletionStatus
0x180016ea5  test    eax, eax
0x180016ea7  jz      short loc_180016EDD
0x180016ea9  mov     rsi, [rsp+28h+arg_8]
0x180016eae  mov     eax, ebx
0x180016eb0  mov     rbx, [rsp+28h+arg_0]
0x180016eb5  add     rsp, 20h
0x180016eb9  pop     rdi
0x180016eba  retn
0x180016ebb  mov     ebx, 8007000Eh
0x180016ec0  mov     rax, [rdi]
0x180016ec3  mov     edx, 1
0x180016ec8  mov     rcx, rdi
0x180016ecb  mov     rax, [rax+8]
0x180016ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed4  jmp     short loc_180016EA9
0x180016ed6  mov     ebx, 8007000Eh
0x180016edb  jmp     short loc_180016EA9
0x180016edd  call    cs:__imp_GetLastError
0x180016ee3  mov     ebx, eax
0x180016ee5  test    eax, eax
0x180016ee7  jle     short loc_180016EC0
0x180016ee9  movzx   ebx, ax
0x180016eec  or      ebx, 80070000h
0x180016ef2  jmp     short loc_180016EC0
0x180016ef4  mov     edx, 20h ; ' '; unsigned __int64
0x180016ef9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016efe  jmp     loc_180016E7A
```
