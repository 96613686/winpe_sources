# StorageService::SetStorageCardAppMetadata(_STORAGE_DEVICE_TYPE,ulong,_GUID *)

- ea: `0x1800298cc`
- end: `0x180029aa1`
- name: `?SetStorageCardAppMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAU_GUID@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18002675c`
- `0x180027858`

## callees

- `0x1800010a8`
- `0x18000d030`
- `0x180022e78`
- `0x1800298cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800299ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800299ef`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029927`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029927`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029973`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029973`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800299c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800299c6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002993b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002993b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029945`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029945`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageService::SetStorageCardAppMetadata(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  int v5; // r15d
  int v6; // r14d
  signed int AppMetadataFilePath; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  signed int LastError; // eax
  __int128 v11; // xmm0
  signed int v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  signed int v15; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  _OWORD Buffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v19[32]; // [rsp+70h] [rbp-90h] BYREF
  int *v20; // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  int *v22; // [rsp+A0h] [rbp-60h]
  __int64 v23; // [rsp+A8h] [rbp-58h]
  _OWORD *v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  signed int *v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  WCHAR FileName[264]; // [rsp+D0h] [rbp-30h] BYREF

  NumberOfBytesWritten = 0;
  memset(Buffer, 0, 20);
  v5 = a3;
  v6 = a2;
  AppMetadataFilePath = StorageService::GetAppMetadataFilePath(a1, a2, a3, FileName);
  if ( AppMetadataFilePath < 0 )
    goto LABEL_13;
  if ( GetFileAttributesW(FileName) != -1 )
  {
    SetFileAttributesW(FileName, 0x80u);
    DeleteFileW(FileName);
  }
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    AppMetadataFilePath = LastError;
    if ( LastError > 0 )
      AppMetadataFilePath = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v11 = *a4;
    LODWORD(Buffer[0]) = 20;
    *(_OWORD *)((char *)Buffer + 4) = v11;
    if ( !WriteFile(FileW, Buffer, 0x14u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 20 )
    {
      v12 = GetLastError();
      AppMetadataFilePath = v12;
      if ( v12 > 0 )
        AppMetadataFilePath = (unsigned __int16)v12 | 0x80070000;
    }
    CloseHandle(v9);
  }
  if ( AppMetadataFilePath < 0 )
  {
LABEL_13:
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      v15 = AppMetadataFilePath;
      v26 = &v15;
      v16 = v5;
      v22 = &v16;
      v17 = v6;
      v20 = &v17;
      v27 = 4;
      v24 = a4;
      v25 = 16;
      v23 = 4;
      v21 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800BF000, &dword_1800A5E7C, 0, 0, 6, v19);
    }
  }
  return (unsigned int)AppMetadataFilePath;
}

```

## disassembly

```asm
0x1800298cc  push    rbp
0x1800298ce  push    rbx
0x1800298cf  push    rsi
0x1800298d0  push    rdi
0x1800298d1  push    r14
0x1800298d3  push    r15
0x1800298d5  lea     rbp, [rsp-1F8h]
0x1800298dd  sub     rsp, 2F8h
0x1800298e4  mov     rax, cs:__security_cookie
0x1800298eb  xor     rax, rsp
0x1800298ee  mov     [rbp+220h+var_40], rax
0x1800298f5  xor     eax, eax
0x1800298f7  mov     rsi, r9
0x1800298fa  xorps   xmm0, xmm0
0x1800298fd  mov     [rsp+320h+var_2C0], eax
0x180029901  lea     r9, [rbp+220h+FileName]
0x180029905  mov     [rsp+320h+NumberOfBytesWritten], eax
0x180029909  movups  [rsp+320h+Buffer], xmm0
0x18002990e  mov     r15d, r8d
0x180029911  mov     r14d, edx
0x180029914  call    ?GetAppMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z; StorageService::GetAppMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)
0x180029919  mov     ebx, eax
0x18002991b  test    eax, eax
0x18002991d  js      loc_1800299FD
0x180029923  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180029927  call    cs:__imp_GetFileAttributesW
0x18002992d  cmp     eax, 0FFFFFFFFh
0x180029930  jz      short loc_18002994B
0x180029932  mov     edx, 80h; dwFileAttributes
0x180029937  lea     rcx, [rbp+220h+FileName]; lpFileName
0x18002993b  call    cs:__imp_SetFileAttributesW
0x180029941  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180029945  call    cs:__imp_DeleteFileW
0x18002994b  mov     [rsp+320h+hTemplateFile], 0; hTemplateFile
0x180029954  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180029958  mov     [rsp+320h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180029960  xor     r9d, r9d; lpSecurityAttributes
0x180029963  xor     r8d, r8d; dwShareMode
0x180029966  mov     [rsp+320h+dwCreationDisposition], 2; dwCreationDisposition
0x18002996e  mov     edx, 40000000h; dwDesiredAccess
0x180029973  call    cs:__imp_CreateFileW
0x180029979  mov     rdi, rax
0x18002997c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029980  jnz     short loc_180029999
0x180029982  call    cs:__imp_GetLastError
0x180029988  mov     ebx, eax
0x18002998a  test    eax, eax
0x18002998c  jle     short loc_1800299F5
0x18002998e  movzx   ebx, ax
0x180029991  or      ebx, 80070000h
0x180029997  jmp     short loc_1800299F5
0x180029999  movups  xmm0, xmmword ptr [rsi]
0x18002999c  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800299a1  mov     dword ptr [rsp+320h+Buffer], 14h
0x1800299a9  mov     r8d, 14h; nNumberOfBytesToWrite
0x1800299af  mov     qword ptr [rsp+320h+dwCreationDisposition], 0; lpOverlapped
0x1800299b8  lea     rdx, [rsp+320h+Buffer]; lpBuffer
0x1800299bd  mov     rcx, rdi; hFile
0x1800299c0  movdqu  [rsp+320h+Buffer+4], xmm0
0x1800299c6  call    cs:__imp_WriteFile
0x1800299cc  test    eax, eax
0x1800299ce  jz      short loc_1800299D7
0x1800299d0  cmp     [rsp+320h+NumberOfBytesWritten], 14h
0x1800299d5  jz      short loc_1800299EC
0x1800299d7  call    cs:__imp_GetLastError
0x1800299dd  mov     ebx, eax
0x1800299df  test    eax, eax
0x1800299e1  jle     short loc_1800299EC
0x1800299e3  movzx   ebx, ax
0x1800299e6  or      ebx, 80070000h
0x1800299ec  mov     rcx, rdi; hObject
0x1800299ef  call    cs:__imp_CloseHandle
0x1800299f5  test    ebx, ebx
0x1800299f7  jns     loc_180029A80
0x1800299fd  mov     eax, cs:dword_1800BF000
0x180029a03  cmp     eax, 5
0x180029a06  jbe     short loc_180029A80
0x180029a08  lea     rax, [rsp+320h+var_2DC]
0x180029a0d  mov     [rsp+320h+var_2DC], ebx
0x180029a11  mov     [rbp+220h+var_260], rax
0x180029a15  lea     rdx, dword_1800A5E7C
0x180029a1c  lea     rax, [rsp+320h+var_2D8]
0x180029a21  mov     [rsp+320h+var_2D8], r15d
0x180029a26  mov     [rbp+220h+var_280], rax
0x180029a2a  lea     rcx, dword_1800BF000
0x180029a31  lea     rax, [rsp+320h+var_2D4]
0x180029a36  mov     [rsp+320h+var_2D4], r14d
0x180029a3b  mov     [rbp+220h+var_290], rax
0x180029a3f  xor     r9d, r9d
0x180029a42  lea     rax, [rsp+320h+var_2B0]
0x180029a47  mov     [rbp+220h+var_258], 4
0x180029a4f  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x180029a54  xor     r8d, r8d
0x180029a57  mov     [rsp+320h+dwCreationDisposition], 6
0x180029a5f  mov     [rbp+220h+var_270], rsi
0x180029a63  mov     [rbp+220h+var_268], 10h
0x180029a6b  mov     [rbp+220h+var_278], 4
0x180029a73  mov     [rbp+220h+var_288], 4
0x180029a7b  call    _tlgWriteTransfer_EventWriteTransfer
0x180029a80  mov     eax, ebx
0x180029a82  mov     rcx, [rbp+220h+var_40]
0x180029a89  xor     rcx, rsp; StackCookie
0x180029a8c  call    __security_check_cookie
0x180029a91  add     rsp, 2F8h
0x180029a98  pop     r15
0x180029a9a  pop     r14
0x180029a9c  pop     rdi
0x180029a9d  pop     rsi
0x180029a9e  pop     rbx
0x180029a9f  pop     rbp
0x180029aa0  retn
```
