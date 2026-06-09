# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x180028b0c`
- end: `0x180028c14`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180026f44`

## callees

- `0x180028b0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028bdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028b4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028b4c`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180028b84`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180028b84`

## pseudocode

```c
void **__fastcall wil::TryCreateFileCanRecurseIntoDirectory(void **a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  void *v7; // rsi
  DWORD LastError; // ebx
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
      v7 = *a1;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v7);
        SetLastError(LastError);
      }
      *a1 = (void *)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180028b0c  mov     [rsp+arg_8], rbx
0x180028b11  mov     [rsp+arg_10], rsi
0x180028b16  push    rdi
0x180028b17  sub     rsp, 40h
0x180028b1b  mov     rax, rdx
0x180028b1e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180028b27  xor     r9d, r9d; lpSecurityAttributes
0x180028b2a  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180028b32  mov     rbx, r8
0x180028b35  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180028b3d  mov     rdi, rcx
0x180028b40  mov     edx, 80010000h; dwDesiredAccess
0x180028b45  mov     rcx, rax; lpFileName
0x180028b48  lea     r8d, [r9+1]; dwShareMode
0x180028b4c  call    cs:__imp_CreateFileW
0x180028b53  nop     dword ptr [rax+rax+00h]
0x180028b58  mov     [rdi], rax
0x180028b5b  lea     rdx, [rax-1]
0x180028b5f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028b63  ja      loc_180028C00
0x180028b69  mov     r9d, 8; dwBufferSize
0x180028b6f  mov     [rsp+48h+FileInformation], 0
0x180028b78  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x180028b7d  mov     rcx, rax; hFile
0x180028b80  lea     edx, [r9+1]; FileInformationClass
0x180028b84  call    cs:__imp_GetFileInformationByHandleEx
0x180028b8b  nop     dword ptr [rax+rax+00h]
0x180028b90  test    eax, eax
0x180028b92  jz      short loc_180028BC1
0x180028b94  mov     rax, [rsp+48h+FileInformation]
0x180028b99  test    al, 10h
0x180028b9b  jz      short loc_180028BC1
0x180028b9d  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x180028ba1  bt      eax, 0Ah
0x180028ba5  jnb     short loc_180028BB5
0x180028ba7  bt      ecx, 1Ch
0x180028bab  jb      short loc_180028BB5
0x180028bad  cmp     ecx, 80000018h
0x180028bb3  jnz     short loc_180028BC1
0x180028bb5  test    rbx, rbx
0x180028bb8  jz      short loc_180028C00
0x180028bba  mov     [rbx], eax
0x180028bbc  mov     [rbx+24h], ecx
0x180028bbf  jmp     short loc_180028C00
0x180028bc1  mov     rsi, [rdi]
0x180028bc4  lea     rax, [rsi-1]
0x180028bc8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028bcc  ja      short loc_180028BF9
0x180028bce  call    cs:__imp_GetLastError
0x180028bd5  nop     dword ptr [rax+rax+00h]
0x180028bda  mov     rcx, rsi; hObject
0x180028bdd  mov     ebx, eax
0x180028bdf  call    cs:__imp_CloseHandle
0x180028be6  nop     dword ptr [rax+rax+00h]
0x180028beb  mov     ecx, ebx; dwErrCode
0x180028bed  call    cs:__imp_SetLastError
0x180028bf4  nop     dword ptr [rax+rax+00h]
0x180028bf9  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180028c00  mov     rbx, [rsp+48h+arg_8]
0x180028c05  mov     rax, rdi
0x180028c08  mov     rsi, [rsp+48h+arg_10]
0x180028c0d  add     rsp, 40h
0x180028c11  pop     rdi
0x180028c12  retn
```
