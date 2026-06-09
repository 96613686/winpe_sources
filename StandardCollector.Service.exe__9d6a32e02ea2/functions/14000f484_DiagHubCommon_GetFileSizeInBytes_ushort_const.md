# DiagHubCommon::GetFileSizeInBytes(ushort const *)

- ea: `0x14000f484`
- end: `0x14000f50e`
- name: `?GetFileSizeInBytes@DiagHubCommon@@YA_JPEBG@Z`
- size: `138`
- prototype: `LARGE_INTEGER __fastcall(const WCHAR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f838`

## callees

- `0x14000f484`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14000f4c0`
- `KERNEL32!CreateFileW` at `0x14000f4c0`
- `KERNEL32!GetFileSizeEx` at `0x14000f4d7`
- `KERNEL32!GetFileSizeEx` at `0x14000f4d7`
- `KERNEL32!CloseHandle` at `0x14000f4ed`
- `KERNEL32!CloseHandle` at `0x14000f4ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
0x14000f484  mov     [rsp+arg_8], rbx
0x14000f489  push    rdi
0x14000f48a  sub     rsp, 50h
0x14000f48e  mov     rax, cs:__security_cookie
0x14000f495  xor     rax, rsp
0x14000f498  mov     [rsp+58h+var_10], rax
0x14000f49d  xor     ebx, ebx
0x14000f49f  xor     r9d, r9d; lpSecurityAttributes
0x14000f4a2  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x14000f4a7  mov     edx, 80000000h; dwDesiredAccess
0x14000f4ac  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000f4b4  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f4bc  lea     r8d, [rbx+1]; dwShareMode
0x14000f4c0  call    cs:__imp_CreateFileW
0x14000f4c6  mov     rdi, rax
0x14000f4c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f4cd  jz      short loc_14000F4F3
0x14000f4cf  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x14000f4d4  mov     rcx, rax; hFile
0x14000f4d7  call    cs:__imp_GetFileSizeEx
0x14000f4dd  test    eax, eax
0x14000f4df  cmovnz  rbx, qword ptr [rsp+58h+FileSize]
0x14000f4e5  test    rdi, rdi
0x14000f4e8  jz      short loc_14000F4F3
0x14000f4ea  mov     rcx, rdi; hObject
0x14000f4ed  call    cs:__imp_CloseHandle
0x14000f4f3  mov     rax, rbx
0x14000f4f6  mov     rcx, [rsp+58h+var_10]
0x14000f4fb  xor     rcx, rsp; StackCookie
0x14000f4fe  call    __security_check_cookie
0x14000f503  mov     rbx, [rsp+58h+arg_8]
0x14000f508  add     rsp, 50h
0x14000f50c  pop     rdi
0x14000f50d  retn
```
