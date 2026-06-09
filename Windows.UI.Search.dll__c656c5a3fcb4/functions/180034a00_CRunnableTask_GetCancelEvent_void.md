# CRunnableTask::GetCancelEvent(void * *)

- ea: `0x180034a00`
- end: `0x180034ab2`
- name: `?GetCancelEvent@CRunnableTask@@UEAAJPEAPEAX@Z`
- size: `178`
- prototype: `int(CRunnableTask *__hidden this, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180010fd0`
- `0x180034a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034a49`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034a49`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180034a51`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180034a51`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034a2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a67`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180034a92`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180034a92`

## pseudocode

```c
__int64 __fastcall CRunnableTask::GetCancelEvent(CRunnableTask *this, void **a2)
{
  unsigned int Error; // edi
  int v5; // ebp
  HANDLE EventW; // rax
  void *v7; // rcx
  HANDLE CurrentProcess; // rax

  Error = 0;
  *a2 = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v5 = *((_DWORD *)this + 10);
    EventW = CreateEventW(0, 1, v5, 0);
    if ( EventW )
    {
      _InterlockedExchange64((volatile __int64 *)this + 4, (__int64)EventW);
      if ( v5 != *((_DWORD *)this + 10) )
      {
        v7 = (void *)*((_QWORD *)this + 4);
        if ( *((_DWORD *)this + 10) )
          SetEvent(v7);
        else
          ResetEvent(v7);
      }
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
  }
  if ( *((_QWORD *)this + 4) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, *((HANDLE *)this + 4), CurrentProcess, a2, 0, 0, 2u) )
      return 0;
    else
      return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x180034a00  push    rbx
0x180034a02  push    rbp
0x180034a03  push    rsi
0x180034a04  push    rdi
0x180034a05  sub     rsp, 48h
0x180034a09  xor     edi, edi
0x180034a0b  mov     qword ptr [rdx], 0
0x180034a12  mov     rsi, rdx
0x180034a15  mov     rbx, rcx
0x180034a18  cmp     [rcx+20h], rdi
0x180034a1c  jnz     short loc_180034A60
0x180034a1e  mov     ebp, [rcx+28h]
0x180034a21  lea     edx, [rdi+1]; bManualReset
0x180034a24  mov     r8d, ebp; bInitialState
0x180034a27  xor     ecx, ecx; lpEventAttributes
0x180034a29  xor     r9d, r9d; lpName
0x180034a2c  call    cs:__imp_CreateEventW
0x180034a32  test    rax, rax
0x180034a35  jz      short loc_180034A59
0x180034a37  xchg    rax, [rbx+20h]
0x180034a3b  cmp     ebp, [rbx+28h]
0x180034a3e  jz      short loc_180034A60
0x180034a40  mov     rcx, [rbx+20h]; hEvent
0x180034a44  cmp     [rbx+28h], edi
0x180034a47  jz      short loc_180034A51
0x180034a49  call    cs:__imp_SetEvent
0x180034a4f  jmp     short loc_180034A60
0x180034a51  call    cs:__imp_ResetEvent
0x180034a57  jmp     short loc_180034A60
0x180034a59  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180034a5e  mov     edi, eax
0x180034a60  cmp     qword ptr [rbx+20h], 0
0x180034a65  jz      short loc_180034AA7
0x180034a67  call    cs:__imp_GetCurrentProcess
0x180034a6d  mov     rdx, [rbx+20h]; hSourceHandle
0x180034a71  mov     r9, rsi; lpTargetHandle
0x180034a74  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180034a7c  mov     r8, rax; hTargetProcessHandle
0x180034a7f  mov     rcx, rax; hSourceProcessHandle
0x180034a82  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180034a8a  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180034a92  call    cs:__imp_DuplicateHandle
0x180034a98  test    eax, eax
0x180034a9a  jz      short loc_180034AA0
0x180034a9c  xor     edi, edi
0x180034a9e  jmp     short loc_180034AA7
0x180034aa0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180034aa5  mov     edi, eax
0x180034aa7  mov     eax, edi
0x180034aa9  add     rsp, 48h
0x180034aad  pop     rdi
0x180034aae  pop     rsi
0x180034aaf  pop     rbp
0x180034ab0  pop     rbx
0x180034ab1  retn
```
