# BufferWriter::CAsyncIO::IOCreateFile(unsigned __int64,ushort const *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180015190`
- end: `0x180015259`
- name: `?IOCreateFile@CAsyncIO@BufferWriter@@QEAAPEAX_KPEBGPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `201`
- prototype: `void *__fastcall(BufferWriter::CAsyncIO *__hidden this, ULONG_PTR CompletionKey, LPCWSTR lpFileName, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013d34`

## callees

- `0x18001367c`
- `0x180015190`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x180015214`
- `KERNEL32!CreateIoCompletionPort` at `0x180015214`
- `KERNEL32!CreateFileW` at `0x1800151f5`
- `KERNEL32!CreateFileW` at `0x1800151f5`
- `KERNEL32!SetLastError` at `0x1800151c5`
- `KERNEL32!SetLastError` at `0x1800151c5`
- `KERNEL32!CloseHandle` at `0x180015226`
- `KERNEL32!CloseHandle` at `0x18001523d`
- `KERNEL32!CloseHandle` at `0x180015226`
- `KERNEL32!CloseHandle` at `0x18001523d`
- `KERNEL32!LeaveCriticalSection` at `0x180015247`
- `KERNEL32!LeaveCriticalSection` at `0x180015247`
- `KERNEL32!EnterCriticalSection` at `0x1800151a6`
- `KERNEL32!EnterCriticalSection` at `0x1800151a6`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::IOCreateFile(
        BufferWriter::CAsyncIO *this,
        ULONG_PTR CompletionKey,
        LPCWSTR lpFileName,
        struct _SECURITY_ATTRIBUTES *a4)
{
  DWORD v7; // eax
  __int64 v8; // rbx
  HANDLE FileW; // rax
  char *IoCompletionPort; // rsi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 1) || (v7 = BufferWriter::CAsyncIO::Active(this)) == 0 )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 1u, 0x40000080u, 0);
    v8 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      IoCompletionPort = (char *)CreateIoCompletionPort(FileW, *((HANDLE *)this + 1), CompletionKey, 1u);
      if ( IoCompletionPort != *((char **)this + 1) )
      {
        CloseHandle((HANDLE)v8);
        v8 = -1;
        if ( (unsigned __int64)(IoCompletionPort - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(IoCompletionPort);
      }
    }
  }
  else
  {
    v8 = -1;
    SetLastError(v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x180015190  push    rbx
0x180015192  push    rbp
0x180015193  push    rsi
0x180015194  push    rdi
0x180015195  sub     rsp, 48h
0x180015199  mov     rdi, rcx
0x18001519c  mov     rbx, r8
0x18001519f  add     rcx, 10h; lpCriticalSection
0x1800151a3  mov     rsi, rdx
0x1800151a6  call    cs:__imp_EnterCriticalSection
0x1800151ac  cmp     qword ptr [rdi+8], 0
0x1800151b1  jnz     short loc_1800151CD
0x1800151b3  mov     rcx, rdi; this
0x1800151b6  call    ?Active@CAsyncIO@BufferWriter@@QEAAKXZ; BufferWriter::CAsyncIO::Active(void)
0x1800151bb  test    eax, eax
0x1800151bd  jz      short loc_1800151CD
0x1800151bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800151c3  mov     ecx, eax; dwErrCode
0x1800151c5  call    cs:__imp_SetLastError
0x1800151cb  jmp     short loc_180015243
0x1800151cd  xor     r9d, r9d; lpSecurityAttributes
0x1800151d0  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800151d9  mov     [rsp+68h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1800151e1  mov     edx, 40000000h; dwDesiredAccess
0x1800151e6  mov     rcx, rbx; lpFileName
0x1800151e9  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x1800151f1  lea     r8d, [r9+1]; dwShareMode
0x1800151f5  call    cs:__imp_CreateFileW
0x1800151fb  mov     rbx, rax
0x1800151fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015202  jz      short loc_180015243
0x180015204  mov     rdx, [rdi+8]; ExistingCompletionPort
0x180015208  mov     r9d, 1; NumberOfConcurrentThreads
0x18001520e  mov     r8, rsi; CompletionKey
0x180015211  mov     rcx, rax; FileHandle
0x180015214  call    cs:__imp_CreateIoCompletionPort
0x18001521a  mov     rsi, rax
0x18001521d  cmp     rax, [rdi+8]
0x180015221  jz      short loc_180015243
0x180015223  mov     rcx, rbx; hObject
0x180015226  call    cs:__imp_CloseHandle
0x18001522c  lea     rdx, [rsi-1]
0x180015230  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015234  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180015238  ja      short loc_180015243
0x18001523a  mov     rcx, rsi; hObject
0x18001523d  call    cs:__imp_CloseHandle
0x180015243  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015247  call    cs:__imp_LeaveCriticalSection
0x18001524d  mov     rax, rbx
0x180015250  add     rsp, 48h
0x180015254  pop     rdi
0x180015255  pop     rsi
0x180015256  pop     rbp
0x180015257  pop     rbx
0x180015258  retn
```
