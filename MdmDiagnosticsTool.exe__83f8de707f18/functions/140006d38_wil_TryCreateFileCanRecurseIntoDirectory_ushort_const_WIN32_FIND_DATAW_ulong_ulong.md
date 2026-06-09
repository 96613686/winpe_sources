# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x140006d38`
- end: `0x140006e2e`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140005e44`

## callees

- `0x140003218`
- `0x140003618`
- `0x140006d38`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006d73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006d73`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140006dab`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140006dab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006e02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006e02`

## pseudocode

```c
void **__fastcall wil::TryCreateFileCanRecurseIntoDirectory(void **a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  void *v7; // rdi
  _BYTE v9[24]; // [rsp+40h] [rbp-18h] BYREF
  __int64 FileInformation; // [rsp+60h] [rbp+8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v6 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v6;
      }
    }
    else
    {
      v7 = *a1;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        CloseHandle(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      *a1 = (void *)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140006d38  mov     [rsp+arg_8], rbx
0x140006d3d  push    rdi
0x140006d3e  sub     rsp, 50h
0x140006d42  mov     rax, rdx
0x140006d45  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x140006d4e  xor     r9d, r9d; lpSecurityAttributes
0x140006d51  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140006d59  mov     rdi, r8
0x140006d5c  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x140006d64  mov     rbx, rcx
0x140006d67  mov     edx, 80010000h; dwDesiredAccess
0x140006d6c  mov     rcx, rax; lpFileName
0x140006d6f  lea     r8d, [r9+1]; dwShareMode
0x140006d73  call    cs:__imp_CreateFileW
0x140006d7a  nop     dword ptr [rax+rax+00h]
0x140006d7f  mov     [rbx], rax
0x140006d82  lea     rdx, [rax-1]
0x140006d86  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140006d8a  ja      loc_140006E1F
0x140006d90  mov     r9d, 8; dwBufferSize
0x140006d96  mov     [rsp+58h+FileInformation], 0
0x140006d9f  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x140006da4  mov     rcx, rax; hFile
0x140006da7  lea     edx, [r9+1]; FileInformationClass
0x140006dab  call    cs:__imp_GetFileInformationByHandleEx
0x140006db2  nop     dword ptr [rax+rax+00h]
0x140006db7  test    eax, eax
0x140006db9  jz      short loc_140006DE8
0x140006dbb  mov     rax, [rsp+58h+FileInformation]
0x140006dc0  test    al, 10h
0x140006dc2  jz      short loc_140006DE8
0x140006dc4  mov     ecx, dword ptr [rsp+58h+FileInformation+4]
0x140006dc8  bt      eax, 0Ah
0x140006dcc  jnb     short loc_140006DDC
0x140006dce  bt      ecx, 1Ch
0x140006dd2  jb      short loc_140006DDC
0x140006dd4  cmp     ecx, 80000018h
0x140006dda  jnz     short loc_140006DE8
0x140006ddc  test    rdi, rdi
0x140006ddf  jz      short loc_140006E1F
0x140006de1  mov     [rdi], eax
0x140006de3  mov     [rdi+24h], ecx
0x140006de6  jmp     short loc_140006E1F
0x140006de8  mov     rdi, [rbx]
0x140006deb  lea     rax, [rdi-1]
0x140006def  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006df3  ja      short loc_140006E18
0x140006df5  lea     rcx, [rsp+58h+var_18]; this
0x140006dfa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140006dff  mov     rcx, rdi; hObject
0x140006e02  call    cs:__imp_CloseHandle
0x140006e09  nop     dword ptr [rax+rax+00h]
0x140006e0e  lea     rcx, [rsp+58h+var_18]; this
0x140006e13  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140006e18  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x140006e1f  mov     rax, rbx
0x140006e22  mov     rbx, [rsp+58h+arg_8]
0x140006e27  add     rsp, 50h
0x140006e2b  pop     rdi
0x140006e2c  retn
```
