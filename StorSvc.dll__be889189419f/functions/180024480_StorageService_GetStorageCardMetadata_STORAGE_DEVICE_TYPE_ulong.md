# StorageService::GetStorageCardMetadata(_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180024480`
- end: `0x180024630`
- name: `?GetStorageCardMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180020f10`
- `0x180027080`

## callees

- `0x18000d030`
- `0x18000dd8c`
- `0x180022c28`
- `0x180023f10`
- `0x180024480`
- `0x18003b1b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800245ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800245ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800245f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800245f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024607`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800244e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800244e1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024555`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024555`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024541`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024541`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002457d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002457d`

## pseudocode

```c
__int64 __fastcall StorageService::GetStorageCardMetadata(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // r15
  __int64 v4; // r12
  signed int MetadataFilePath; // edi
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v9; // rsi
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+50h] [rbp-B0h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = a2;
  v4 = a3;
  Buffer = 0;
  v13 = 0;
  NumberOfBytesRead = 0;
  MetadataFilePath = StorageService::GetMetadataFilePath(a1, a2, a3, FileName);
  if ( MetadataFilePath >= 0 )
  {
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 )
      return (unsigned int)-2147467259;
    if ( (FileAttributesW & 0x10) == 0
      || (MetadataFilePath = RecursiveUtil::DeleteDirectoryTree(FileName, (const unsigned __int16 *)1, 0, 0, 0),
          MetadataFilePath >= 0) )
    {
      FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0, 0);
      v9 = FileW;
      if ( FileW == (HANDLE)-1LL )
        return (unsigned int)-2147467259;
      if ( GetFileSize(FileW, 0) >= 0xC
        && ReadFile(v9, &Buffer, 0xCu, &NumberOfBytesRead, 0)
        && NumberOfBytesRead >= 0xC
        && (unsigned int)Buffer >= 0xC )
      {
        MetadataFilePath = StorageService::GenerateStorageId(
                             a1,
                             (unsigned int)v3,
                             (unsigned int)v4,
                             (char *)&Buffer + 4,
                             0);
        if ( MetadataFilePath >= 0 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
          MetadataFilePath = memcmp_0(
                               &GUID_NULL,
                               (const void *)(*(_QWORD *)(a1 + 8 * v3 + 40) + 548LL + 1112 * v4),
                               0x10u) == 0
                           ? 0x80004005
                           : 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
        }
      }
      else
      {
        MetadataFilePath = -2147467259;
      }
      CloseHandle(v9);
    }
  }
  return (unsigned int)MetadataFilePath;
}

```

## disassembly

```asm
0x180024480  push    rbp
0x180024482  push    rbx
0x180024483  push    rsi
0x180024484  push    rdi
0x180024485  push    r12
0x180024487  push    r14
0x180024489  push    r15
0x18002448b  lea     rbp, [rsp-180h]
0x180024493  sub     rsp, 280h
0x18002449a  mov     rax, cs:__security_cookie
0x1800244a1  xor     rax, rsp
0x1800244a4  mov     [rbp+1B0h+var_40], rax
0x1800244ab  xor     eax, eax
0x1800244ad  movsxd  r15, edx
0x1800244b0  xor     ebx, ebx
0x1800244b2  mov     r12d, r8d
0x1800244b5  mov     edx, r15d
0x1800244b8  mov     [rsp+2B0h+Buffer], rax
0x1800244bd  lea     r9, [rsp+2B0h+FileName]
0x1800244c2  mov     [rsp+2B0h+var_260], eax
0x1800244c6  mov     r14, rcx
0x1800244c9  mov     [rsp+2B0h+NumberOfBytesRead], ebx
0x1800244cd  call    ?GetMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z; StorageService::GetMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)
0x1800244d2  mov     edi, eax
0x1800244d4  test    eax, eax
0x1800244d6  js      loc_18002460D
0x1800244dc  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x1800244e1  call    cs:__imp_GetFileAttributesW
0x1800244e7  cmp     eax, 0FFFFFFFFh
0x1800244ea  jnz     short loc_1800244F6
0x1800244ec  mov     edi, 80004005h
0x1800244f1  jmp     loc_18002460D
0x1800244f6  mov     esi, 1
0x1800244fb  test    al, 10h
0x1800244fd  jz      short loc_180024520
0x1800244ff  xor     r9d, r9d; struct _FILETIME *
0x180024502  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rbx; __int64 *
0x180024507  xor     r8d, r8d; unsigned int
0x18002450a  lea     rcx, [rsp+2B0h+FileName]; this
0x18002450f  mov     edx, esi; unsigned __int16 *
0x180024511  call    ?DeleteDirectoryTree@RecursiveUtil@@YAJPEBGKPEAU_FILETIME@@PEA_J2@Z; RecursiveUtil::DeleteDirectoryTree(ushort const *,ulong,_FILETIME *,__int64 *,__int64 *)
0x180024516  mov     edi, eax
0x180024518  test    eax, eax
0x18002451a  js      loc_18002460D
0x180024520  mov     [rsp+2B0h+hTemplateFile], rbx; hTemplateFile
0x180024525  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x18002452a  mov     [rsp+2B0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002452e  xor     r9d, r9d; lpSecurityAttributes
0x180024531  mov     r8d, esi; dwShareMode
0x180024534  mov     [rsp+2B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002453c  mov     edx, 80000000h; dwDesiredAccess
0x180024541  call    cs:__imp_CreateFileW
0x180024547  mov     rsi, rax
0x18002454a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002454e  jz      short loc_1800244EC
0x180024550  xor     edx, edx; lpFileSizeHigh
0x180024552  mov     rcx, rax; hFile
0x180024555  call    cs:__imp_GetFileSize
0x18002455b  mov     edi, 0Ch
0x180024560  cmp     eax, edi
0x180024562  jb      loc_1800245FF
0x180024568  lea     r9, [rsp+2B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002456d  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rbx; lpOverlapped
0x180024572  mov     r8d, edi; nNumberOfBytesToRead
0x180024575  lea     rdx, [rsp+2B0h+Buffer]; lpBuffer
0x18002457a  mov     rcx, rsi; hFile
0x18002457d  call    cs:__imp_ReadFile
0x180024583  test    eax, eax
0x180024585  jz      short loc_1800245FF
0x180024587  cmp     [rsp+2B0h+NumberOfBytesRead], edi
0x18002458b  jb      short loc_1800245FF
0x18002458d  cmp     dword ptr [rsp+2B0h+Buffer], edi
0x180024591  jb      short loc_1800245FF
0x180024593  lea     r9, [rsp+2B0h+Buffer+4]
0x180024598  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18002459c  mov     r8d, r12d
0x18002459f  mov     edx, r15d
0x1800245a2  mov     rcx, r14
0x1800245a5  call    ?GenerateStorageId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAEH@Z; StorageService::GenerateStorageId(_STORAGE_DEVICE_TYPE,ulong,uchar *,int)
0x1800245aa  mov     edi, eax
0x1800245ac  test    eax, eax
0x1800245ae  js      short loc_180024604
0x1800245b0  lea     rbx, [r14+658h]
0x1800245b7  mov     rcx, rbx; lpCriticalSection
0x1800245ba  call    cs:__imp_EnterCriticalSection
0x1800245c0  mov     rax, [r14+r15*8+28h]
0x1800245c5  lea     rcx, GUID_NULL; Buf1
0x1800245cc  add     rax, 224h
0x1800245d2  mov     r8d, 10h; Size
0x1800245d8  imul    rdx, r12, 458h
0x1800245df  add     rdx, rax; Buf2
0x1800245e2  call    memcmp_0
0x1800245e7  neg     eax
0x1800245e9  mov     edi, 80004005h
0x1800245ee  mov     rcx, rbx; lpCriticalSection
0x1800245f1  sbb     edx, edx
0x1800245f3  not     edx
0x1800245f5  and     edi, edx
0x1800245f7  call    cs:__imp_LeaveCriticalSection
0x1800245fd  jmp     short loc_180024604
0x1800245ff  mov     edi, 80004005h
0x180024604  mov     rcx, rsi; hObject
0x180024607  call    cs:__imp_CloseHandle
0x18002460d  mov     eax, edi
0x18002460f  mov     rcx, [rbp+1B0h+var_40]
0x180024616  xor     rcx, rsp; StackCookie
0x180024619  call    __security_check_cookie
0x18002461e  add     rsp, 280h
0x180024625  pop     r15
0x180024627  pop     r14
0x180024629  pop     r12
0x18002462b  pop     rdi
0x18002462c  pop     rsi
0x18002462d  pop     rbx
0x18002462e  pop     rbp
0x18002462f  retn
```
