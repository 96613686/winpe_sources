# TryRecoverFile

- ea: `0x180023dc4`
- end: `0x18002468a`
- name: `TryRecoverFile`
- size: `2246`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024690`

## callees

- `0x180005045`
- `0x180016dbc`
- `0x180017510`
- `0x1800226ec`
- `0x180022760`
- `0x18002331c`
- `0x1800234b4`
- `0x18002388c`
- `0x180023dc4`
- `0x18004e9e8`
- `0x180063600`
- `0x180063698`
- `0x1800637e8`
- `0x180063938`
- `0x1800d87ac`
- `0x1800dca3c`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002426f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002426f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002435c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002460b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002435c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800245fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002460b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023f85`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002418a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023f85`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002418a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002416e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002416e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023e48`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023f40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024260`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023e48`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023f40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024260`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180024104`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180024104`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002465b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002465b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180023fcf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180023fcf`
- `ntdll!NtCreateFile` at `0x18002431a`
- `ntdll!NtCreateFile` at `0x1800243b9`
- `ntdll!NtCreateFile` at `0x180024445`
- `ntdll!NtCreateFile` at `0x180024553`
- `ntdll!NtCreateFile` at `0x18002431a`
- `ntdll!NtCreateFile` at `0x1800243b9`
- `ntdll!NtCreateFile` at `0x180024445`
- `ntdll!NtCreateFile` at `0x180024553`
- `ntdll!NtQueryObject` at `0x18002434a`
- `ntdll!NtQueryObject` at `0x18002434a`

## pseudocode

```c
int __fastcall TryRecoverFile(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  int v3; // r13d
  HANDLE FileW; // rax
  int *v8; // rdi
  _DWORD *v9; // r15
  void *v10; // rsp
  struct _UNICODE_STRING *v11; // r14
  _DWORD *v12; // rax
  HANDLE v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // r9
  __int64 *v17; // rdx
  unsigned __int64 v18; // rbx
  __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  int *v22; // rax
  __int64 v23; // r8
  union _LARGE_INTEGER *FileAttributes; // r9
  char *v25; // rbx
  HANDLE v26; // r13
  DWORD LastError; // ebx
  union _LARGE_INTEGER *v28; // r12
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int LogFile; // eax
  int v33; // r15d
  int v34; // ecx
  _BYTE v36[32]; // [rsp-20h] [rbp-470h] BYREF
  int v37; // [rsp+40h] [rbp-410h] BYREF
  _BYTE v38[936]; // [rsp+48h] [rbp-408h] BYREF
  HANDLE v39; // [rsp+450h] [rbp+0h]
  DWORD NumberOfBytesRead; // [rsp+458h] [rbp+8h] BYREF
  void *FileHandle; // [rsp+460h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+468h] [rbp+18h] BYREF
  _DWORD *v43; // [rsp+470h] [rbp+20h]
  __int128 v44; // [rsp+478h] [rbp+28h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+488h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+4B8h] [rbp+68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+4C0h] [rbp+70h] BYREF
  _BYTE Buffer[8]; // [rsp+4D0h] [rbp+80h] BYREF
  int v49; // [rsp+4D8h] [rbp+88h]
  ULONG v50; // [rsp+4DCh] [rbp+8Ch]
  unsigned int v51; // [rsp+4E0h] [rbp+90h]
  DWORD nNumberOfBytesToRead; // [rsp+4E4h] [rbp+94h]
  char v53; // [rsp+4E8h] [rbp+98h]
  unsigned int v54; // [rsp+4ECh] [rbp+9Ch]
  unsigned int v55; // [rsp+4F4h] [rbp+A4h]
  unsigned int v56; // [rsp+4FCh] [rbp+ACh]
  unsigned int v57; // [rsp+500h] [rbp+B0h]
  union _LARGE_INTEGER v58; // [rsp+518h] [rbp+C8h] BYREF
  char v59; // [rsp+528h] [rbp+D8h] BYREF

  v3 = 0;
  FileHandle = 0;
  hObject = 0;
  memset_0(Buffer, 0, 0x60u);
  NumberOfBytesRead = 0;
  v44 = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  v39 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return (int)FileW;
  v8 = 0;
  v9 = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x400
    || (unsigned __int64)(g_ulAdditionalProbeSize + 1032) < 0x400
    || !(unsigned int)VerifyStackAvailable()
    || (v10 = alloca(1040), v36 == (_BYTE *)-96LL)
    || (v37 = 1801679955, (v11 = (struct _UNICODE_STRING *)v38) == 0) )
  {
    v12 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(1032);
    v11 = (struct _UNICODE_STRING *)v12;
    if ( !v12 || (*v12 = 1885431112, v11 = (struct _UNICODE_STRING *)(v12 + 2), v12 == (_DWORD *)-8LL) )
    {
      v15 = -1;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_81;
    }
  }
  StringCbCopyW(&v11->Length, 0x400u, a1);
  StringCbCatW(&v11->Length, 0x400u, L"\\System Volume Information");
  StringCbCatW(&v11->Length, 0x400u, L"\\");
  StringCbCatW(&v11->Length, 0x400u, (const unsigned __int16 *)(a2 + 44));
  v13 = CreateFileW(&v11->Length, 0xC0010000, 0, 0, 3u, 0, 0);
  v15 = (__int64)v13;
  if ( v13 == (HANDLE)-1LL )
  {
    v16 = 313;
    v17 = EFS_RECOVERY_OPEN_LOGFILE_ERROR;
LABEL_11:
    fnEfsLogTrace0(v14, v17, 16, v16);
LABEL_81:
    v26 = v39;
    goto LABEL_82;
  }
  if ( !ReadFile(v13, Buffer, 0x60u, &NumberOfBytesRead, 0) )
  {
    v16 = 327;
LABEL_14:
    v17 = EFS_RECOVERY_READ_LOGFILE_ERROR;
    goto LABEL_11;
  }
  if ( !NumberOfBytesRead )
  {
LABEL_16:
    MarkFileForDelete(v15);
    goto LABEL_81;
  }
  if ( NumberOfBytesRead < 0x60 || RtlCompareMemory(Buffer, L"GUJR", 8u) != 8 || (v14 = 200, v49 != 100) && v49 != 200 )
  {
    v16 = 353;
    goto LABEL_49;
  }
  if ( v49 == 200 )
  {
    if ( !a3 || !*(_DWORD *)a3 )
      goto LABEL_81;
    v3 = 1;
  }
  else if ( a3 && *(_DWORD *)a3 )
  {
    goto LABEL_81;
  }
  v18 = nNumberOfBytesToRead;
  ReturnLength = v50;
  if ( nNumberOfBytesToRead % v50 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(_DWORD)v18
    || v18 > g_ulMaxStackAllocSize
    || v18 + g_ulAdditionalProbeSize + 8 < v18
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_37;
  }
  v19 = v18 + 23;
  if ( v18 + 23 <= v18 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v14);
  v21 = alloca(v14);
  v8 = &v37;
  if ( v36 == (_BYTE *)-96LL || (v37 = 1801679955, (v8 = (int *)v38) == 0) )
  {
LABEL_37:
    v14 = v18 + 8;
    if ( v18 + 8 >= v18 )
    {
      v22 = (int *)((__int64 (*)(void))g_pfnAllocate)();
      v8 = v22;
      if ( v22 )
      {
        *v22 = 1885431112;
        v8 = v22 + 2;
      }
    }
  }
  if ( !v3 && (v53 & 2) == 0 )
  {
    if ( v57 >= v56 )
    {
      v9 = VirtualAlloc(0, v57 - v56, 0x1000u, 4u);
      goto LABEL_44;
    }
    v16 = 409;
LABEL_49:
    v17 = EFS_RECOVERY_LOGFILE_FORMAT_ERROR;
    goto LABEL_11;
  }
LABEL_44:
  v43 = v9;
  if ( (v57 - v56) % ReturnLength )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v8 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_81;
  }
  if ( !v9 && (v53 & 2) == 0 && !v3 )
    goto LABEL_81;
  SetFilePointer((HANDLE)v15, 0, 0, 0);
  if ( !ReadFile((HANDLE)v15, v8, v18, &NumberOfBytesRead, 0) || NumberOfBytesRead != (_DWORD)v18 )
  {
    v16 = 452;
    goto LABEL_14;
  }
  if ( (unsigned int)GetCheckSum(v8, v51, v23, 0) != *(int *)((char *)v8 + v18 - 4) )
    goto LABEL_16;
  v25 = (char *)v8 + v54;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( v3 )
  {
    v26 = v39;
    ReturnLength = OefsRecover(
                     (struct _EFS_RECOVERY_CONTEXT *)a3,
                     v39,
                     &v58,
                     (const unsigned __int16 *)((char *)v8 + v54),
                     (v53 & 1) == 0,
                     (void *)v15);
    if ( (ReturnLength & 0x80000000) != 0 )
      EfsTelemetry::LogOefsRecoveryFailure<long &>(&ReturnLength);
    ++*(_DWORD *)(a3 + 16);
    goto LABEL_82;
  }
  if ( (v53 & 2) != 0 )
  {
    v28 = FileAttributes;
    v26 = v39;
    v33 = v53 & 1;
    goto LABEL_74;
  }
  CloseHandle((HANDLE)v15);
  v15 = (__int64)CreateFileW(&v11->Length, 0xC0010000, 0, 0, 3u, 0x20000000u, 0);
  if ( v15 == -1 )
  {
    LastError = GetLastError();
    MicrosoftTelemetryAssertTriggeredNoArgs();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_RECOVERY_OPEN_LOGFILE_NC_ERROR, LastError, 16, 15);
    goto LABEL_81;
  }
  v26 = v39;
  *((_QWORD *)&v44 + 1) = &v59;
  v28 = (union _LARGE_INTEGER *)((char *)v8 + v55);
  ObjectAttributes.Attributes = 0;
  LODWORD(v44) = 524296;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v39;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v44;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 1u, 0x202060u, 0, 0) < 0 )
  {
    FileHandle = 0;
    goto LABEL_70;
  }
  ReturnLength = 0;
  if ( NtQueryObject(FileHandle, ObjectNameInformation, v11, 0x400u, &ReturnLength) < 0 )
  {
    fnEfsLogTrace2Strings(v29, (unsigned int)EFS_RECOVERY_TMP_FILENAME_ERROR, (_DWORD)v25, (_DWORD)v28, 16, 139);
LABEL_70:
    LogFile = ReadLogFile((HANDLE)v15, v9);
    FileAttributes = 0;
    if ( LogFile < 0 )
    {
      MarkFileForDelete(v15);
      goto LABEL_82;
    }
    v33 = v9[1];
LABEL_74:
    *((_QWORD *)&v44 + 1) = &v58;
    ObjectAttributes.Attributes = (unsigned int)FileAttributes;
    LODWORD(v44) = 524296;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v26;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v44;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtCreateFile(
           &hObject,
           0xC0100000,
           &ObjectAttributes,
           &IoStatusBlock,
           FileAttributes,
           (ULONG)FileAttributes,
           (ULONG)FileAttributes,
           1u,
           0x202020u,
           FileAttributes,
           (ULONG)FileAttributes) >= 0 )
    {
      DoRecover(hObject, FileHandle, v15, v25, v28, v57 - v56, v56, v33);
      CloseHandle(hObject);
    }
    else
    {
      fnEfsLogTrace1Strings(v34, (unsigned int)EFS_RECOVERY_TARGET_OPEN_ERROR, (_DWORD)v25, 16, 231);
      MarkFileForDelete(v15);
    }
    v9 = v43;
    goto LABEL_82;
  }
  CloseHandle(FileHandle);
  ObjectAttributes.Length = 48;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = v11;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtCreateFile(&FileHandle, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 1u, 0x200060u, 0, 0) >= 0 )
    goto LABEL_70;
  MicrosoftTelemetryAssertTriggeredNoArgs();
  fnEfsLogTrace2Strings(v30, (unsigned int)EFS_RECOVERY_TMP_OPEN_NAME_ERROR, (_DWORD)v25, (_DWORD)v28, 16, 102);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.RootDirectory = v26;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v44;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 1u, 0x202060u, 0, 0) >= 0 )
    goto LABEL_70;
  fnEfsLogTrace2Strings(v31, (unsigned int)EFS_RECOVERY_TMP_FILEID_ERROR, (_DWORD)v25, (_DWORD)v28, 16, 133);
LABEL_82:
  LODWORD(FileW) = CloseHandle(v26);
  if ( v15 != -1 )
    LODWORD(FileW) = CloseHandle((HANDLE)v15);
  if ( FileHandle )
    LODWORD(FileW) = CloseHandle(FileHandle);
  if ( v11 && LODWORD(v11[-1].Buffer) == 1885431112 )
    LODWORD(FileW) = ((__int64 (*)(void))g_pfnFree)();
  if ( v8 && *(v8 - 2) == 1885431112 )
    LODWORD(FileW) = ((__int64 (*)(void))g_pfnFree)();
  if ( v9 )
    LODWORD(FileW) = VirtualFree(v9, 0, 0x8000u);
  return (int)FileW;
}

```

## disassembly

```asm
0x180023dc4  push    rbp
0x180023dc6  push    rsi
0x180023dc7  push    rdi
0x180023dc8  push    r12
0x180023dca  push    r13
0x180023dcc  push    r14
0x180023dce  push    r15
0x180023dd0  sub     rsp, 150h
0x180023dd7  lea     rbp, [rsp+60h]
0x180023ddc  mov     [rbp+120h+arg_18], rbx
0x180023de3  mov     rax, cs:__security_cookie
0x180023dea  xor     rax, rbp
0x180023ded  mov     [rbp+120h+var_40], rax
0x180023df4  xor     r13d, r13d
0x180023df7  mov     r12, r8
0x180023dfa  mov     rsi, rdx
0x180023dfd  mov     [rbp+120h+FileHandle], r13
0x180023e01  mov     rbx, rcx
0x180023e04  mov     [rbp+120h+hObject], r13
0x180023e08  xor     edx, edx; Val
0x180023e0a  lea     rcx, [rbp+120h+Buffer]; void *
0x180023e11  lea     r8d, [r13+60h]; Size
0x180023e15  call    memset_0
0x180023e1a  lea     eax, [r13+3]
0x180023e1e  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x180023e23  xorps   xmm0, xmm0
0x180023e26  mov     [rsp+180h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180023e2e  mov     r8d, eax; dwShareMode
0x180023e31  mov     [rbp+120h+NumberOfBytesRead], r13d
0x180023e35  xor     r9d, r9d; lpSecurityAttributes
0x180023e38  mov     [rsp+180h+dwCreationDisposition], eax; dwCreationDisposition
0x180023e3c  mov     edx, 80000000h; dwDesiredAccess
0x180023e41  mov     rcx, rbx; lpFileName
0x180023e44  movups  [rbp+120h+var_F8], xmm0
0x180023e48  call    cs:__imp_CreateFileW
0x180023e4e  mov     [rbp+120h+var_120], rax
0x180023e52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023e56  jz      loc_180024661
0x180023e5c  mov     eax, 400h
0x180023e61  mov     edi, r13d
0x180023e64  cmp     cs:g_ulMaxStackAllocSize, rax
0x180023e6b  mov     r15d, r13d
0x180023e6e  jb      short loc_180023EB1
0x180023e70  mov     rcx, cs:g_ulAdditionalProbeSize
0x180023e77  add     rcx, 408h
0x180023e7e  cmp     rcx, rax
0x180023e81  jb      short loc_180023EB1
0x180023e83  call    VerifyStackAvailable
0x180023e88  test    eax, eax
0x180023e8a  jz      short loc_180023EB1
0x180023e8c  mov     eax, [rsp+180h+var_180]
0x180023e8f  mov     eax, 410h
0x180023e94  sub     rsp, rax
0x180023e97  lea     r14, [rsp+590h+var_530]
0x180023e9c  mov     eax, [r14]
0x180023e9f  test    r14, r14
0x180023ea2  jz      short loc_180023EB1
0x180023ea4  mov     dword ptr [r14], 6B637453h
0x180023eab  add     r14, 8
0x180023eaf  jnz     short loc_180023EDE
0x180023eb1  mov     rax, cs:g_pfnAllocate
0x180023eb8  mov     ecx, 408h
0x180023ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ec2  mov     r14, rax
0x180023ec5  test    rax, rax
0x180023ec8  jz      loc_1800245DD
0x180023ece  mov     dword ptr [rax], 70616548h
0x180023ed4  add     r14, 8
0x180023ed8  jz      loc_1800245DD
0x180023ede  mov     r8, rbx; unsigned __int16 *
0x180023ee1  mov     rcx, r14; unsigned __int16 *
0x180023ee4  mov     ebx, 400h
0x180023ee9  mov     edx, ebx; unsigned __int64
0x180023eeb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180023ef0  lea     r8, aSystemVolumeIn_0; "\\System Volume Information"
0x180023ef7  mov     edx, ebx; unsigned __int64
0x180023ef9  mov     rcx, r14; unsigned __int16 *
0x180023efc  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180023f01  lea     r8, Source; "\\"
0x180023f08  mov     edx, ebx; unsigned __int64
0x180023f0a  mov     rcx, r14; unsigned __int16 *
0x180023f0d  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180023f12  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x180023f16  mov     edx, ebx; unsigned __int64
0x180023f18  mov     rcx, r14; unsigned __int16 *
0x180023f1b  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180023f20  mov     [rsp+590h+var_560], r13; hTemplateFile
0x180023f25  xor     r9d, r9d; lpSecurityAttributes
0x180023f28  mov     [rsp+590h+FileAttributes], r13d; dwFlagsAndAttributes
0x180023f2d  xor     r8d, r8d; dwShareMode
0x180023f30  mov     edx, 0C0010000h; dwDesiredAccess
0x180023f35  mov     [rsp+590h+var_570], 3; dwCreationDisposition
0x180023f3d  mov     rcx, r14; lpFileName
0x180023f40  call    cs:__imp_CreateFileW
0x180023f46  mov     rsi, rax
0x180023f49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023f4d  jnz     short loc_180023F6C
0x180023f4f  mov     r9d, 139h
0x180023f55  lea     rdx, EFS_RECOVERY_OPEN_LOGFILE_ERROR
0x180023f5c  mov     r8d, 10h
0x180023f62  call    fnEfsLogTrace0
0x180023f67  jmp     loc_1800245E6
0x180023f6c  lea     r9, [rbp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180023f70  mov     qword ptr [rsp+590h+var_570], r13; lpOverlapped
0x180023f75  mov     r8d, 60h ; '`'; nNumberOfBytesToRead
0x180023f7b  lea     rdx, [rbp+120h+Buffer]; lpBuffer
0x180023f82  mov     rcx, rsi; hFile
0x180023f85  call    cs:__imp_ReadFile
0x180023f8b  test    eax, eax
0x180023f8d  jnz     short loc_180023F9E
0x180023f8f  mov     r9d, 147h
0x180023f95  lea     rdx, EFS_RECOVERY_READ_LOGFILE_ERROR
0x180023f9c  jmp     short loc_180023F5C
0x180023f9e  mov     eax, [rbp+120h+NumberOfBytesRead]
0x180023fa1  test    eax, eax
0x180023fa3  jnz     short loc_180023FB2
0x180023fa5  mov     rcx, rsi
0x180023fa8  call    MarkFileForDelete
0x180023fad  jmp     loc_1800245E6
0x180023fb2  cmp     eax, 60h ; '`'
0x180023fb5  jb      loc_1800245D2
0x180023fbb  mov     r8d, 8; Length
0x180023fc1  lea     rdx, aGujr; "GUJR"
0x180023fc8  lea     rcx, [rbp+120h+Buffer]; Source1
0x180023fcf  call    cs:__imp_RtlCompareMemory
0x180023fd5  cmp     rax, 8
0x180023fd9  jnz     loc_1800245D2
0x180023fdf  mov     eax, [rbp+120h+var_98]
0x180023fe5  mov     ecx, 0C8h
0x180023fea  cmp     eax, 64h ; 'd'
0x180023fed  jz      short loc_180023FF7
0x180023fef  cmp     eax, ecx
0x180023ff1  jnz     loc_1800245D2
0x180023ff7  cmp     eax, ecx
0x180023ff9  jnz     short loc_180024016
0x180023ffb  test    r12, r12
0x180023ffe  jz      loc_1800245E6
0x180024004  cmp     [r12], r13d
0x180024008  jz      loc_1800245E6
0x18002400e  mov     r13d, 1
0x180024014  jmp     short loc_18002402A
0x180024016  cmp     eax, 64h ; 'd'
0x180024019  jnz     short loc_18002402A
0x18002401b  test    r12, r12
0x18002401e  jz      short loc_18002402A
0x180024020  cmp     [r12], r13d
0x180024024  jnz     loc_1800245E6
0x18002402a  mov     ecx, [rbp+120h+var_94]
0x180024030  xor     edx, edx
0x180024032  mov     ebx, [rbp+120h+nNumberOfBytesToRead]
0x180024038  mov     eax, ebx
0x18002403a  mov     [rbp+120h+ReturnLength], ecx
0x18002403d  div     ecx
0x18002403f  test    edx, edx
0x180024041  jz      short loc_180024048
0x180024043  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BufferSize % SectorSize == 0")
0x180024048  test    ebx, ebx
0x18002404a  jz      short loc_1800240AD
0x18002404c  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180024053  ja      short loc_1800240AD
0x180024055  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002405c  add     rcx, 8
0x180024060  add     rcx, rbx
0x180024063  cmp     rcx, rbx
0x180024066  jb      short loc_1800240AD
0x180024068  call    VerifyStackAvailable
0x18002406d  test    eax, eax
0x18002406f  jz      short loc_1800240AD
0x180024071  lea     rax, [rbx+8]
0x180024075  lea     rcx, [rax+0Fh]
0x180024079  cmp     rcx, rax
0x18002407c  ja      short loc_180024088
0x18002407e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180024088  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002408c  mov     rax, rcx
0x18002408f  call    _alloca_probe
0x180024094  sub     rsp, rcx
0x180024097  lea     rdi, [rsp+590h+var_530]
0x18002409c  test    rdi, rdi
0x18002409f  jz      short loc_1800240AD
0x1800240a1  mov     dword ptr [rdi], 6B637453h
0x1800240a7  add     rdi, 8
0x1800240ab  jnz     short loc_1800240D4
0x1800240ad  lea     rcx, [rbx+8]
0x1800240b1  cmp     rcx, rbx
0x1800240b4  jb      short loc_1800240D4
0x1800240b6  mov     rax, cs:g_pfnAllocate
0x1800240bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240c2  mov     rdi, rax
0x1800240c5  test    rax, rax
0x1800240c8  jz      short loc_1800240D4
0x1800240ca  mov     dword ptr [rax], 70616548h
0x1800240d0  add     rdi, 8
0x1800240d4  test    r13d, r13d
0x1800240d7  jnz     short loc_18002410D
0x1800240d9  test    [rbp+120h+var_88], 2
0x1800240e0  jnz     short loc_18002410D
0x1800240e2  mov     eax, [rbp+120h+var_70]
0x1800240e8  cmp     eax, [rbp+120h+var_74]
0x1800240ee  jb      short loc_18002413A
0x1800240f0  sub     eax, [rbp+120h+var_74]
0x1800240f6  lea     r9d, [r13+4]; flProtect
0x1800240fa  mov     edx, eax; dwSize
0x1800240fc  xor     ecx, ecx; lpAddress
0x1800240fe  mov     r8d, 1000h; flAllocationType
0x180024104  call    cs:__imp_VirtualAlloc
0x18002410a  mov     r15, rax
0x18002410d  mov     eax, [rbp+120h+var_70]
0x180024113  xor     edx, edx
0x180024115  sub     eax, [rbp+120h+var_74]
0x18002411b  div     [rbp+120h+ReturnLength]
0x18002411e  mov     [rbp+120h+var_100], r15
0x180024122  test    edx, edx
0x180024124  jz      short loc_18002412B
0x180024126  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(FileHeader.OffsetStatus2 - FileHeader.OffsetStatus1) % SectorSize == 0")
0x18002412b  test    rdi, rdi
0x18002412e  jnz     short loc_18002414C
0x180024130  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ReadBuffer")
0x180024135  jmp     loc_1800245E6
0x18002413a  mov     r9d, 199h
0x180024140  lea     rdx, EFS_RECOVERY_LOGFILE_FORMAT_ERROR
0x180024147  jmp     loc_180023F5C
0x18002414c  test    r15, r15
0x18002414f  jnz     short loc_180024163
0x180024151  test    [rbp+120h+var_88], 2
0x180024158  jnz     short loc_180024163
0x18002415a  test    r13d, r13d
0x18002415d  jz      loc_1800245E6
0x180024163  xor     r9d, r9d; dwMoveMethod
0x180024166  xor     r8d, r8d; lpDistanceToMoveHigh
0x180024169  xor     edx, edx; lDistanceToMove
0x18002416b  mov     rcx, rsi; hFile
0x18002416e  call    cs:__imp_SetFilePointer
0x180024174  lea     r9, [rbp+120h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180024178  mov     qword ptr [rsp+590h+var_570], 0; lpOverlapped
0x180024181  mov     r8d, ebx; nNumberOfBytesToRead
0x180024184  mov     rdx, rdi; lpBuffer
0x180024187  mov     rcx, rsi; hFile
0x18002418a  call    cs:__imp_ReadFile
0x180024190  xor     r9d, r9d
0x180024193  test    eax, eax
0x180024195  jz      loc_1800245C7
0x18002419b  cmp     [rbp+120h+NumberOfBytesRead], ebx
0x18002419e  jnz     loc_1800245C7
0x1800241a4  mov     edx, [rbp+120h+var_90]
0x1800241aa  mov     rcx, rdi
0x1800241ad  call    GetCheckSum
0x1800241b2  cmp     eax, [rbx+rdi-4]
0x1800241b6  jnz     loc_180023FA5
0x1800241bc  mov     ebx, [rbp+120h+var_84]
0x1800241c2  xorps   xmm0, xmm0
0x1800241c5  add     rbx, rdi
0x1800241c8  movups  xmmword ptr [rbp+120h+ObjectAttributes.Length], xmm0
0x1800241cc  movups  xmmword ptr [rbp+120h+ObjectAttributes.ObjectName], xmm0
0x1800241d0  movups  xmmword ptr [rbp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800241d4  movups  xmmword ptr [rbp+120h+IoStatusBlock], xmm0
0x1800241d8  test    r13d, r13d
0x1800241db  jz      short loc_180024223
0x1800241dd  mov     al, [rbp+120h+var_88]
0x1800241e3  lea     r8, [rbp+120h+var_58]; union _LARGE_INTEGER *
0x1800241ea  mov     r13, [rbp+120h+var_120]
0x1800241ee  not     al
0x1800241f0  and     al, 1
0x1800241f2  mov     qword ptr [rsp+590h+FileAttributes], rsi; void *
0x1800241f7  mov     r9, rbx; unsigned __int16 *
0x1800241fa  mov     byte ptr [rsp+590h+var_570], al; bool
0x1800241fe  mov     rdx, r13; void *
0x180024201  mov     rcx, r12; struct _EFS_RECOVERY_CONTEXT *
0x180024204  call    ?OefsRecover@@YAJPEAU_EFS_RECOVERY_CONTEXT@@PEAXPEAT_LARGE_INTEGER@@PEBG_N1@Z; OefsRecover(_EFS_RECOVERY_CONTEXT *,void *,_LARGE_INTEGER *,ushort const *,bool,void *)
0x180024209  mov     [rbp+120h+ReturnLength], eax
0x18002420c  test    eax, eax
0x18002420e  jns     short loc_180024219
0x180024210  lea     rcx, [rbp+120h+ReturnLength]
0x180024214  call    ??$LogOefsRecoveryFailure@AEAJ@EfsTelemetry@@SAXAEAJ@Z; EfsTelemetry::LogOefsRecoveryFailure<long &>(long &)
0x180024219  inc     dword ptr [r12+10h]
0x18002421e  jmp     loc_1800245EA
0x180024223  test    [rbp+120h+var_88], 2
0x18002422a  jnz     loc_1800244D5
0x180024230  mov     rcx, rsi; hObject
0x180024233  call    cs:__imp_CloseHandle
0x180024239  mov     [rsp+590h+var_560], 0; hTemplateFile
0x180024242  xor     r9d, r9d; lpSecurityAttributes
0x180024245  mov     [rsp+590h+FileAttributes], 20000000h; dwFlagsAndAttributes
0x18002424d  xor     r8d, r8d; dwShareMode
0x180024250  mov     edx, 0C0010000h; dwDesiredAccess
0x180024255  mov     [rsp+590h+var_570], 3; dwCreationDisposition
0x18002425d  mov     rcx, r14; lpFileName
0x180024260  call    cs:__imp_CreateFileW
0x180024266  mov     rsi, rax
0x180024269  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002426d  jnz     short loc_1800242A3
0x18002426f  call    cs:__imp_GetLastError
0x180024275  mov     ebx, eax
0x180024277  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x18002427c  mov     rcx, cs:g_hPublisher
0x180024283  lea     r9d, [rsi+11h]
0x180024287  mov     r8d, ebx
0x18002428a  mov     [rsp+590h+var_570], 20Fh
0x180024292  lea     rdx, EFS_RECOVERY_OPEN_LOGFILE_NC_ERROR
0x180024299  call    fnEfsLogTrace1
  ... truncated ...
```
