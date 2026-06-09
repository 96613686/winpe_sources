# CTnoDriver::Open(void)

- ea: `0x180010d60`
- end: `0x180010ddc`
- name: `?Open@CTnoDriver@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(CTnoDriver *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f8a4`

## callees

- `0x180010d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da5`
- `KERNEL32!CreateIoCompletionPort` at `0x180010dc5`
- `KERNEL32!CreateIoCompletionPort` at `0x180010dc5`
- `KERNEL32!CreateFileW` at `0x180010d95`
- `KERNEL32!CreateFileW` at `0x180010d95`

## pseudocode

```c
signed int __fastcall CTnoDriver::Open(CTnoDriver *this)
{
  HANDLE FileW; // rax
  signed int result; // eax
  HANDLE IoCompletionPort; // rax

  FileW = CreateFileW(L"\\\\.\\PeerDistKM", 0x1F01FFu, 3u, 0, 4u, 0x40000000u, 0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    IoCompletionPort = CreateIoCompletionPort(FileW, 0, 1u, 0);
    *((_QWORD *)this + 2) = IoCompletionPort;
    if ( IoCompletionPort )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180010d60  push    rbx
0x180010d62  sub     rsp, 40h
0x180010d66  xor     r9d, r9d; lpSecurityAttributes
0x180010d69  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180010d72  mov     rbx, rcx
0x180010d75  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180010d7d  mov     edx, 1F01FFh; dwDesiredAccess
0x180010d82  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x180010d8a  lea     rcx, FileName; "\\\\.\\PeerDistKM"
0x180010d91  lea     r8d, [r9+3]; dwShareMode
0x180010d95  call    cs:__imp_CreateFileW
0x180010d9b  mov     [rbx+8], rax
0x180010d9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010da3  jnz     short loc_180010DB9
0x180010da5  call    cs:__imp_GetLastError
0x180010dab  test    eax, eax
0x180010dad  jle     short loc_180010DD6
0x180010daf  movzx   eax, ax
0x180010db2  or      eax, 80070000h
0x180010db7  jmp     short loc_180010DD6
0x180010db9  xor     r9d, r9d; NumberOfConcurrentThreads
0x180010dbc  xor     edx, edx; ExistingCompletionPort
0x180010dbe  mov     rcx, rax; FileHandle
0x180010dc1  lea     r8d, [r9+1]; CompletionKey
0x180010dc5  call    cs:__imp_CreateIoCompletionPort
0x180010dcb  mov     [rbx+10h], rax
0x180010dcf  test    rax, rax
0x180010dd2  jz      short loc_180010DA5
0x180010dd4  xor     eax, eax
0x180010dd6  add     rsp, 40h
0x180010dda  pop     rbx
0x180010ddb  retn
```
