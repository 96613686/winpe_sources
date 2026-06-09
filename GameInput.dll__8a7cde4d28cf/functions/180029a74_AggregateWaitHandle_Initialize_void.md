# AggregateWaitHandle::Initialize(void)

- ea: `0x180029a74`
- end: `0x180029b83`
- name: `?Initialize@AggregateWaitHandle@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026848`
- `0x180042b60`

## callees

- `0x180029a74`
- `0x18002bbd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029ac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029ac5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180029af5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180029af5`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180029b10`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180029b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b55`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180029a9b`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180029a9b`

## pseudocode

```c
signed int __fastcall AggregateWaitHandle::Initialize(AggregateWaitHandle *this)
{
  HANDLE *v1; // r14
  HANDLE IoCompletionPort; // rax
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE v7; // rax
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx

  v1 = (HANDLE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    SipcFailFast(2147549183LL);
    JUMPOUT(0x180029B82LL);
  }
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  *(_QWORD *)this = IoCompletionPort;
  if ( IoCompletionPort )
  {
    CurrentProcess = GetCurrentProcess();
    v5 = *(void **)this;
    v6 = CurrentProcess;
    v7 = GetCurrentProcess();
    if ( DuplicateHandle(v7, v5, v6, v1, 0x100000u, 0, 0) )
    {
      SetHandleInformation(*v1, 2u, 2u);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      CloseHandle(*(HANDLE *)this);
      result = v10;
      *(_QWORD *)this = 0;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180029a74  push    rbx
0x180029a76  push    rsi
0x180029a77  push    rdi
0x180029a78  push    r14
0x180029a7a  sub     rsp, 48h
0x180029a7e  lea     r14, [rcx+8]
0x180029a82  mov     rsi, rcx
0x180029a85  cmp     qword ptr [r14], 0
0x180029a89  jnz     loc_180029B78
0x180029a8f  xor     r9d, r9d; NumberOfConcurrentThreads
0x180029a92  xor     r8d, r8d; CompletionKey
0x180029a95  xor     edx, edx; ExistingCompletionPort
0x180029a97  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180029a9b  call    cs:__imp_CreateIoCompletionPort
0x180029aa2  nop     dword ptr [rax+rax+00h]
0x180029aa7  mov     [rsi], rax
0x180029aaa  test    rax, rax
0x180029aad  jz      loc_180029B55
0x180029ab3  call    cs:__imp_GetCurrentProcess
0x180029aba  nop     dword ptr [rax+rax+00h]
0x180029abf  mov     rdi, [rsi]
0x180029ac2  mov     rbx, rax
0x180029ac5  call    cs:__imp_GetCurrentProcess
0x180029acc  nop     dword ptr [rax+rax+00h]
0x180029ad1  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180029ad9  mov     r9, r14; lpTargetHandle
0x180029adc  mov     rcx, rax; hSourceProcessHandle
0x180029adf  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180029ae7  mov     r8, rbx; hTargetProcessHandle
0x180029aea  mov     [rsp+68h+dwDesiredAccess], 100000h; dwDesiredAccess
0x180029af2  mov     rdx, rdi; hSourceHandle
0x180029af5  call    cs:__imp_DuplicateHandle
0x180029afc  nop     dword ptr [rax+rax+00h]
0x180029b01  test    eax, eax
0x180029b03  jz      short loc_180029B20
0x180029b05  mov     rcx, [r14]; hObject
0x180029b08  mov     edx, 2; dwMask
0x180029b0d  mov     r8d, edx; dwFlags
0x180029b10  call    cs:__imp_SetHandleInformation
0x180029b17  nop     dword ptr [rax+rax+00h]
0x180029b1c  xor     eax, eax
0x180029b1e  jmp     short loc_180029B6D
0x180029b20  call    cs:__imp_GetLastError
0x180029b27  nop     dword ptr [rax+rax+00h]
0x180029b2c  mov     ebx, eax
0x180029b2e  test    eax, eax
0x180029b30  jle     short loc_180029B3B
0x180029b32  movzx   ebx, ax
0x180029b35  or      ebx, 80070000h
0x180029b3b  mov     rcx, [rsi]; hObject
0x180029b3e  call    cs:__imp_CloseHandle
0x180029b45  nop     dword ptr [rax+rax+00h]
0x180029b4a  mov     eax, ebx
0x180029b4c  mov     qword ptr [rsi], 0
0x180029b53  jmp     short loc_180029B6D
0x180029b55  call    cs:__imp_GetLastError
0x180029b5c  nop     dword ptr [rax+rax+00h]
0x180029b61  test    eax, eax
0x180029b63  jle     short loc_180029B6D
0x180029b65  movzx   eax, ax
0x180029b68  or      eax, 80070000h
0x180029b6d  add     rsp, 48h
0x180029b71  pop     r14
0x180029b73  pop     rdi
0x180029b74  pop     rsi
0x180029b75  pop     rbx
0x180029b76  retn
0x180029b78  mov     ecx, 8000FFFFh
0x180029b7d  call    SipcFailFast
```
