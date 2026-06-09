# DiagHubCommon::GetFileSizeInBytes(ushort const *)

- ea: `0x18002b520`
- end: `0x18002b5aa`
- name: `?GetFileSizeInBytes@DiagHubCommon@@YA_JPEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(DiagHubCommon *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a80c`
- `0x18004317c`

## callees

- `0x18002b520`
- `0x180049b50`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002b55c`
- `KERNEL32!CreateFileW` at `0x18002b55c`
- `KERNEL32!CloseHandle` at `0x18002b589`
- `KERNEL32!CloseHandle` at `0x18002b589`
- `KERNEL32!GetFileSizeEx` at `0x18002b573`
- `KERNEL32!GetFileSizeEx` at `0x18002b573`

## pseudocode

```c
LARGE_INTEGER __fastcall DiagHubCommon::GetFileSizeInBytes(const WCHAR *this, const unsigned __int16 *a2)
{
  LARGE_INTEGER v2; // rbx
  HANDLE FileW; // rax
  void *v4; // rdi
  LARGE_INTEGER FileSize; // [rsp+40h] [rbp-18h] BYREF

  v2.QuadPart = 0;
  FileW = CreateFileW(this, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
      v2 = FileSize;
    if ( v4 )
      CloseHandle(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18002b520  mov     [rsp+arg_8], rbx
0x18002b525  push    rdi
0x18002b526  sub     rsp, 50h
0x18002b52a  mov     rax, cs:__security_cookie
0x18002b531  xor     rax, rsp
0x18002b534  mov     [rsp+58h+var_10], rax
0x18002b539  xor     ebx, ebx
0x18002b53b  xor     r9d, r9d; lpSecurityAttributes
0x18002b53e  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18002b543  mov     edx, 80000000h; dwDesiredAccess
0x18002b548  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b550  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b558  lea     r8d, [rbx+1]; dwShareMode
0x18002b55c  call    cs:__imp_CreateFileW
0x18002b562  mov     rdi, rax
0x18002b565  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b569  jz      short loc_18002B58F
0x18002b56b  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x18002b570  mov     rcx, rax; hFile
0x18002b573  call    cs:__imp_GetFileSizeEx
0x18002b579  test    eax, eax
0x18002b57b  cmovnz  rbx, qword ptr [rsp+58h+FileSize]
0x18002b581  test    rdi, rdi
0x18002b584  jz      short loc_18002B58F
0x18002b586  mov     rcx, rdi; hObject
0x18002b589  call    cs:__imp_CloseHandle
0x18002b58f  mov     rax, rbx
0x18002b592  mov     rcx, [rsp+58h+var_10]
0x18002b597  xor     rcx, rsp; StackCookie
0x18002b59a  call    __security_check_cookie
0x18002b59f  mov     rbx, [rsp+58h+arg_8]
0x18002b5a4  add     rsp, 50h
0x18002b5a8  pop     rdi
0x18002b5a9  retn
```
