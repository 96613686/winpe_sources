# BufferWriter::CAsyncIO::IOAsyncWrite(void *,void const *,ulong,_OVERLAPPED *)

- ea: `0x1800a589c`
- end: `0x1800a59d0`
- name: `?IOAsyncWrite@CAsyncIO@BufferWriter@@QEAAHPEAXPEBXKPEAU_OVERLAPPED@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(BufferWriter::CAsyncIO *__hidden this, HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005919c`

## callees

- `0x1800a589c`
- `0x1800a6284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a593f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a593f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5952`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a59b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5952`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a59b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a58c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5929`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a58c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a598b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a598b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a5909`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a5909`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a5979`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a5979`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::IOAsyncWrite(
        BufferWriter::CAsyncIO *this,
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPOVERLAPPED lpOverlapped)
{
  bool v9; // zf
  HANDLE v10; // rax
  unsigned int v11; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = *((_QWORD *)this + 8) == 0;
  ThreadId = 0;
  if ( !v9
    || (*((_DWORD *)this + 14) = 0,
        v10 = CreateThread(0, 0, BufferWriter::CAsyncIO::ThreadEntry, this, 0, &ThreadId),
        (*((_QWORD *)this + 8) = v10) != 0) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( !*((_DWORD *)this + 20) )
      ResetEvent(*((HANDLE *)this + 9));
    ++*((_DWORD *)this + 20);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v11 = WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, lpOverlapped);
    if ( !v11 )
    {
      if ( GetLastError() == 997 )
      {
        v11 = 1;
      }
      else
      {
        v11 = 0;
        BufferWriter::COutstandingOps::OnCompletion((BufferWriter::CAsyncIO *)((char *)this + 72));
      }
    }
  }
  else
  {
    v11 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v11;
}

```

## disassembly

```asm
0x1800a589c  push    rbx
0x1800a589e  push    rbp
0x1800a589f  push    rsi
0x1800a58a0  push    rdi
0x1800a58a1  push    r14
0x1800a58a3  push    r15
0x1800a58a5  sub     rsp, 48h
0x1800a58a9  mov     rdi, rcx
0x1800a58ac  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1800a58b4  add     rcx, 10h; lpCriticalSection
0x1800a58b8  mov     ebp, r9d
0x1800a58bb  mov     r14, r8
0x1800a58be  mov     r15, rdx
0x1800a58c1  call    cs:__imp_EnterCriticalSection
0x1800a58c8  nop     dword ptr [rax+rax+00h]
0x1800a58cd  cmp     qword ptr [rdi+40h], 0
0x1800a58d2  mov     [rsp+78h+ThreadId], 0
0x1800a58dd  jnz     short loc_1800A5925
0x1800a58df  lea     rax, [rsp+78h+ThreadId]
0x1800a58e7  mov     dword ptr [rdi+38h], 0
0x1800a58ee  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x1800a58f3  lea     r8, ?ThreadEntry@CAsyncIO@BufferWriter@@SAKPEAX@Z; lpStartAddress
0x1800a58fa  mov     r9, rdi; lpParameter
0x1800a58fd  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800a5905  xor     edx, edx; dwStackSize
0x1800a5907  xor     ecx, ecx; lpThreadAttributes
0x1800a5909  call    cs:__imp_CreateThread
0x1800a5910  nop     dword ptr [rax+rax+00h]
0x1800a5915  mov     [rdi+40h], rax
0x1800a5919  test    rax, rax
0x1800a591c  jnz     short loc_1800A5925
0x1800a591e  xor     ebx, ebx
0x1800a5920  jmp     loc_1800A59B0
0x1800a5925  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800a5929  call    cs:__imp_EnterCriticalSection
0x1800a5930  nop     dword ptr [rax+rax+00h]
0x1800a5935  cmp     dword ptr [rdi+50h], 0
0x1800a5939  jnz     short loc_1800A594B
0x1800a593b  mov     rcx, [rdi+48h]; hEvent
0x1800a593f  call    cs:__imp_ResetEvent
0x1800a5946  nop     dword ptr [rax+rax+00h]
0x1800a594b  inc     dword ptr [rdi+50h]
0x1800a594e  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800a5952  call    cs:__imp_LeaveCriticalSection
0x1800a5959  nop     dword ptr [rax+rax+00h]
0x1800a595e  mov     rax, [rsp+78h+lpOverlapped]
0x1800a5966  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a596b  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a596e  mov     qword ptr [rsp+78h+dwCreationFlags], rax; lpOverlapped
0x1800a5973  mov     rdx, r14; lpBuffer
0x1800a5976  mov     rcx, r15; hFile
0x1800a5979  call    cs:__imp_WriteFile
0x1800a5980  nop     dword ptr [rax+rax+00h]
0x1800a5985  mov     ebx, eax
0x1800a5987  test    eax, eax
0x1800a5989  jnz     short loc_1800A59B0
0x1800a598b  call    cs:__imp_GetLastError
0x1800a5992  nop     dword ptr [rax+rax+00h]
0x1800a5997  cmp     eax, 3E5h
0x1800a599c  jnz     short loc_1800A59A5
0x1800a599e  mov     ebx, 1
0x1800a59a3  jmp     short loc_1800A59B0
0x1800a59a5  xor     ebx, ebx
0x1800a59a7  lea     rcx, [rdi+48h]; this
0x1800a59ab  call    ?OnCompletion@COutstandingOps@BufferWriter@@QEAAXXZ; BufferWriter::COutstandingOps::OnCompletion(void)
0x1800a59b0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800a59b4  call    cs:__imp_LeaveCriticalSection
0x1800a59bb  nop     dword ptr [rax+rax+00h]
0x1800a59c0  mov     eax, ebx
0x1800a59c2  add     rsp, 48h
0x1800a59c6  pop     r15
0x1800a59c8  pop     r14
0x1800a59ca  pop     rdi
0x1800a59cb  pop     rsi
0x1800a59cc  pop     rbp
0x1800a59cd  pop     rbx
0x1800a59ce  retn
```
