# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x18002c898`
- end: `0x18002c952`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18002c258`

## callees

- `0x180024518`
- `0x18002c898`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c8d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c8d3`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002c901`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002c901`

## pseudocode

```c
_QWORD *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(_QWORD *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  __int64 FileInformation; // [rsp+50h] [rbp+8h] BYREF

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
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        -1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002c898  mov     [rsp+arg_8], rbx
0x18002c89d  push    rdi
0x18002c89e  sub     rsp, 40h
0x18002c8a2  mov     rax, rdx
0x18002c8a5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002c8ae  xor     r9d, r9d; lpSecurityAttributes
0x18002c8b1  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002c8b9  mov     rbx, r8
0x18002c8bc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c8c4  mov     rdi, rcx
0x18002c8c7  mov     edx, 80010000h; dwDesiredAccess
0x18002c8cc  mov     rcx, rax; lpFileName
0x18002c8cf  lea     r8d, [r9+1]; dwShareMode
0x18002c8d3  call    cs:__imp_CreateFileW
0x18002c8d9  mov     [rdi], rax
0x18002c8dc  lea     rdx, [rax-1]
0x18002c8e0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002c8e4  ja      short loc_18002C944
0x18002c8e6  mov     r9d, 8; dwBufferSize
0x18002c8ec  mov     [rsp+48h+FileInformation], 0
0x18002c8f5  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x18002c8fa  mov     rcx, rax; hFile
0x18002c8fd  lea     edx, [r9+1]; FileInformationClass
0x18002c901  call    cs:__imp_GetFileInformationByHandleEx
0x18002c907  test    eax, eax
0x18002c909  jz      short loc_18002C938
0x18002c90b  mov     rax, [rsp+48h+FileInformation]
0x18002c910  test    al, 10h
0x18002c912  jz      short loc_18002C938
0x18002c914  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x18002c918  bt      eax, 0Ah
0x18002c91c  jnb     short loc_18002C92C
0x18002c91e  bt      ecx, 1Ch
0x18002c922  jb      short loc_18002C92C
0x18002c924  cmp     ecx, 80000018h
0x18002c92a  jnz     short loc_18002C938
0x18002c92c  test    rbx, rbx
0x18002c92f  jz      short loc_18002C944
0x18002c931  mov     [rbx], eax
0x18002c933  mov     [rbx+24h], ecx
0x18002c936  jmp     short loc_18002C944
0x18002c938  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002c93c  mov     rcx, rdi
0x18002c93f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002c944  mov     rbx, [rsp+48h+arg_8]
0x18002c949  mov     rax, rdi
0x18002c94c  add     rsp, 40h
0x18002c950  pop     rdi
0x18002c951  retn
```
