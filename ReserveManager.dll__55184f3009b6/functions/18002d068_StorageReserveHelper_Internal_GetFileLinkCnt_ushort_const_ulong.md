# StorageReserveHelper::Internal::GetFileLinkCnt(ushort const *,ulong *)

- ea: `0x18002d068`
- end: `0x18002d124`
- name: `?GetFileLinkCnt@Internal@StorageReserveHelper@@YAEPEBGPEAK@Z`
- size: `188`
- prototype: `char __fastcall(const WCHAR *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18002d6a0`

## callees

- `0x180003870`
- `0x18002d068`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18002d0e8`
- `ntdll!NtQueryInformationFile` at `0x18002d0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d101`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d0ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d0ba`

## pseudocode

```c
char __fastcall StorageReserveHelper::Internal::GetFileLinkCnt(
        const WCHAR *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  char v7; // bl
  __int128 FileInformation; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-20h] BYREF

  *(_DWORD *)a2 = 0;
  v9 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  FileW = CreateFileW(this, 0x80u, 7u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation) >= 0 )
  {
    *(_DWORD *)a2 = v9;
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x18002d068  mov     [rsp+arg_10], rbx
0x18002d06d  push    rdi
0x18002d06e  sub     rsp, 70h
0x18002d072  mov     rax, cs:__security_cookie
0x18002d079  xor     rax, rsp
0x18002d07c  mov     [rsp+78h+var_10], rax
0x18002d081  xor     eax, eax
0x18002d083  mov     rbx, rdx
0x18002d086  mov     [rsp+78h+hTemplateFile], rax; hTemplateFile
0x18002d08b  xorps   xmm0, xmm0
0x18002d08e  mov     [rdx], eax
0x18002d090  xorps   xmm1, xmm1
0x18002d093  mov     edx, 80h; dwDesiredAccess
0x18002d098  mov     [rsp+78h+var_28], rax
0x18002d09d  mov     [rsp+78h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x18002d0a1  lea     r8d, [rax+7]; dwShareMode
0x18002d0a5  xor     r9d, r9d; lpSecurityAttributes
0x18002d0a8  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d0b0  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x18002d0b5  movups  [rsp+78h+FileInformation], xmm1
0x18002d0ba  call    cs:__imp_CreateFileW
0x18002d0c0  mov     rdi, rax
0x18002d0c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d0c7  jnz     short loc_18002D0CD
0x18002d0c9  xor     al, al
0x18002d0cb  jmp     short loc_18002D109
0x18002d0cd  mov     r9d, 18h; Length
0x18002d0d3  mov     [rsp+78h+dwCreationDisposition], 5; FileInformationClass
0x18002d0db  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x18002d0e0  mov     rcx, rdi; FileHandle
0x18002d0e3  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x18002d0e8  call    cs:__imp_NtQueryInformationFile
0x18002d0ee  test    eax, eax
0x18002d0f0  jns     short loc_18002D0F6
0x18002d0f2  xor     ebx, ebx
0x18002d0f4  jmp     short loc_18002D0FE
0x18002d0f6  mov     eax, dword ptr [rsp+78h+var_28]
0x18002d0fa  mov     [rbx], eax
0x18002d0fc  mov     bl, 1
0x18002d0fe  mov     rcx, rdi; hObject
0x18002d101  call    cs:__imp_CloseHandle
0x18002d107  mov     al, bl
0x18002d109  mov     rcx, [rsp+78h+var_10]
0x18002d10e  xor     rcx, rsp; StackCookie
0x18002d111  call    __security_check_cookie
0x18002d116  mov     rbx, [rsp+78h+arg_10]
0x18002d11e  add     rsp, 70h
0x18002d122  pop     rdi
0x18002d123  retn
```
