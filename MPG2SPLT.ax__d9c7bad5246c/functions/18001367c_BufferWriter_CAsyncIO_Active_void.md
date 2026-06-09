# BufferWriter::CAsyncIO::Active(void)

- ea: `0x18001367c`
- end: `0x1800136dd`
- name: `?Active@CAsyncIO@BufferWriter@@QEAAKXZ`
- size: `97`
- prototype: `unsigned int __fastcall(BufferWriter::CAsyncIO *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013d34`
- `0x180015190`

## callees

- `0x18001367c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800136bb`
- `KERNEL32!GetLastError` at `0x1800136bb`
- `KERNEL32!CreateIoCompletionPort` at `0x1800136ac`
- `KERNEL32!CreateIoCompletionPort` at `0x1800136ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800136ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800136ca`
- `KERNEL32!EnterCriticalSection` at `0x180013690`
- `KERNEL32!EnterCriticalSection` at `0x180013690`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::Active(BufferWriter::CAsyncIO *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 1)
    || (IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u),
        (*((_QWORD *)this + 1) = IoCompletionPort) != 0) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  LeaveCriticalSection(v1);
  return LastError;
}

```

## disassembly

```asm
0x18001367c  mov     [rsp+arg_0], rbx
0x180013681  push    rdi
0x180013682  sub     rsp, 20h
0x180013686  lea     rdi, [rcx+10h]
0x18001368a  mov     rbx, rcx
0x18001368d  mov     rcx, rdi; lpCriticalSection
0x180013690  call    cs:__imp_EnterCriticalSection
0x180013696  cmp     qword ptr [rbx+8], 0
0x18001369b  jnz     short loc_1800136C5
0x18001369d  mov     r9d, 1; NumberOfConcurrentThreads
0x1800136a3  xor     r8d, r8d; CompletionKey
0x1800136a6  xor     edx, edx; ExistingCompletionPort
0x1800136a8  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800136ac  call    cs:__imp_CreateIoCompletionPort
0x1800136b2  mov     [rbx+8], rax
0x1800136b6  test    rax, rax
0x1800136b9  jnz     short loc_1800136C5
0x1800136bb  call    cs:__imp_GetLastError
0x1800136c1  mov     ebx, eax
0x1800136c3  jmp     short loc_1800136C7
0x1800136c5  xor     ebx, ebx
0x1800136c7  mov     rcx, rdi; lpCriticalSection
0x1800136ca  call    cs:__imp_LeaveCriticalSection
0x1800136d0  mov     eax, ebx
0x1800136d2  mov     rbx, [rsp+28h+arg_0]
0x1800136d7  add     rsp, 20h
0x1800136db  pop     rdi
0x1800136dc  retn
```
