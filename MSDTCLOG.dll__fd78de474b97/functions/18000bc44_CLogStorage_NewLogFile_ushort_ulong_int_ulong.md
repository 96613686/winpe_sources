# CLogStorage::_NewLogFile(ushort *,ulong,int,ulong *)

- ea: `0x18000bc44`
- end: `0x18000c349`
- name: `?_NewLogFile@CLogStorage@@AEAAJPEAGKHPEAK@Z`
- size: `1797`
- prototype: `__int64 __fastcall(CLogStorage *this, LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800065c8`

## callees

- `0x18000abd4`
- `0x18000ad90`
- `0x18000adf8`
- `0x18000afa8`
- `0x18000b974`
- `0x18000bc44`
- `0x18000c6b8`
- `0x18000d998`
- `0x18000dc8c`
- `0x18001280a`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000c1c0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000c1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000befc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000befc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c277`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c0f8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c0f8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c0cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c0cf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000c04c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000c04c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18000bfc5`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18000bfc5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bee9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bee9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000bda0`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000bda0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18000be94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18000be94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000be7e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000be7e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000be3b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000be3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c10f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c11c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c10f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c11c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c152`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c152`
- `msvcrt!malloc` at `0x18000c083`
- `msvcrt!malloc` at `0x18000c083`
- `msvcrt!free` at `0x18000c0ea`
- `msvcrt!free` at `0x18000c2c4`
- `msvcrt!free` at `0x18000c0ea`
- `msvcrt!free` at `0x18000c2c4`

## string_xrefs

- `0x18000c2ff`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000c327`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000bd75`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000bf40`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c184`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c2ae`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000bdbf`: `GetFullPathName failed`
- `0x18000be5a`: `InitializeSecurityDescriptor failed`
- `0x18000bf1e`: `CreateFile(%s) failed`
- `0x18000c06c`: `SetFilePointer failed`
- `0x18000c28c`: `WriteFile failed`
- `0x18000c115`: `decompressing DTC log file on create\n`
- `0x18000c1f2`: `CreateFileMapping failed`

## pseudocode

```c
__int64 __fastcall CLogStorage::_NewLogFile(CLogStorage *this, LPCWSTR lpFileName, int a3, int a4)
{
  unsigned int v8; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  unsigned int v11; // r8d
  signed int LastError; // eax
  unsigned int v13; // ecx
  unsigned int v14; // r12d
  signed int v15; // eax
  HANDLE v16; // rax
  signed int v17; // eax
  const wchar_t *v18; // rax
  __int64 v19; // r9
  int v20; // eax
  int v21; // eax
  signed int v22; // eax
  DWORD v23; // ebx
  LONG v24; // r14d
  signed int v25; // eax
  void *v26; // rax
  void *v27; // r14
  DWORD v28; // eax
  HANDLE FileMappingW; // rax
  signed int v30; // eax
  unsigned int v31; // r15d
  unsigned int v32; // edx
  struct CBuffer *v33; // r9
  _DWORD *v34; // rdx
  unsigned int i; // r14d
  signed int v36; // eax
  unsigned int hTemplateFile; // [rsp+30h] [rbp-4E8h]
  unsigned __int16 *lpOverlapped; // [rsp+38h] [rbp-4E0h]
  unsigned int v40; // [rsp+40h] [rbp-4D8h]
  _WORD InBuffer[2]; // [rsp+50h] [rbp-4C8h] BYREF
  DWORD BytesPerSector; // [rsp+54h] [rbp-4C4h] BYREF
  DWORD SectorsPerCluster; // [rsp+58h] [rbp-4C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+5Ch] [rbp-4BCh] BYREF
  DWORD TotalNumberOfClusters; // [rsp+60h] [rbp-4B8h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+64h] [rbp-4B4h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp-4B0h] BYREF
  int v48; // [rsp+6Ch] [rbp-4ACh] BYREF
  ulong v49; // [rsp+70h] [rbp-4A8h] BYREF
  LPWSTR FilePart; // [rsp+78h] [rbp-4A0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-498h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-480h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-460h]
  unsigned __int16 v54[4]; // [rsp+C0h] [rbp-458h] BYREF
  WCHAR RootPathName; // [rsp+C8h] [rbp-450h] BYREF
  int v56; // [rsp+CAh] [rbp-44Eh]
  __int16 v57; // [rsp+CEh] [rbp-44Ah]
  WCHAR Buffer; // [rsp+D0h] [rbp-448h] BYREF
  _BYTE v59[526]; // [rsp+D2h] [rbp-446h] BYREF
  unsigned __int16 v60; // [rsp+2E0h] [rbp-238h] BYREF
  _BYTE v61[6]; // [rsp+2E2h] [rbp-236h] BYREF

  v54[0] = 0;
  *(_DWORD *)&v54[1] = 0;
  v60 = 0;
  memset_0(v61, 0, 0x1FEu);
  Buffer = 0;
  memset_0(v59, 0, 0x200u);
  FilePart = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v53 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  NumberOfBytesWritten = 0;
  RootPathName = 0;
  v56 = 0;
  v57 = 0;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  InBuffer[0] = 0;
  BytesReturned = 0;
  *((_QWORD *)this + 19) = -1;
  if ( !lpFileName )
  {
    v8 = -2147024809;
    v9 = L"Invalid argument- ptstrFullFileSpec is NULL";
    v10 = 2001;
LABEL_3:
    TraceStringInline(
      12,
      1,
      L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
      v10,
      L"CLogStorage::_NewLogFile",
      v8,
      v9);
    return v8;
  }
  if ( !GetFullPathNameW(lpFileName, 0x101u, &Buffer, &FilePart) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = L"GetFullPathName failed";
    v10 = 2009;
    goto LABEL_3;
  }
  TracedSafeSplitPathW(&Buffer, v54, v11, &v60, 0x100u, (unsigned __int16 *)this + 84, hTemplateFile, lpOverlapped, v40);
  *(_DWORD *)this = 2;
  *((_DWORD *)this + 6) = 5;
  v13 = *((_DWORD *)this + 10);
  v14 = (a3 & (unsigned int)-*((_DWORD *)this + 11)) / v13;
  *((_DWORD *)this + 8) = v14 * v13;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    v9 = L"InitializeSecurityDescriptor failed";
    v10 = 2047;
    goto LABEL_3;
  }
  SetSecurityDescriptorDacl(pSecurityDescriptor, 0, 0, 1);
  SetSecurityDescriptorSacl(pSecurityDescriptor, 0, 0, 1);
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  SecurityAttributes.bInheritHandle = 0;
  v16 = CreateFileW(&Buffer, 0xC0000000, 3u, &SecurityAttributes, (unsigned int)(a4 != 0) + 1, 0xB0000080, 0);
  *((_QWORD *)this + 19) = v16;
  if ( v16 == (HANDLE)-1LL )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    v18 = L"CreateFile(%s) failed";
    v19 = 2071;
    goto LABEL_16;
  }
  RootPathName = 0;
  v20 = StringCchCatW(&RootPathName, 4u, v54);
  if ( v20 < 0 )
  {
    TraceFile(v20, "failed in TracedStringCchCatW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0x111u);
    DtcInternalErrorW(L"failed in TracedStringCchCatW");
  }
  v21 = StringCchCatW(&RootPathName, 4u, L"\\");
  if ( v21 < 0 )
  {
    TraceFile(v21, "failed in TracedStringCchCatW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0x111u);
    DtcInternalErrorW(L"failed in TracedStringCchCatW");
  }
  if ( !GetDiskFreeSpaceW(
          &RootPathName,
          &SectorsPerCluster,
          &BytesPerSector,
          &NumberOfFreeClusters,
          &TotalNumberOfClusters) )
  {
    v22 = GetLastError();
    v8 = v22;
    if ( v22 > 0 )
      v8 = (unsigned __int16)v22 | 0x80070000;
    v18 = L"GetDiskFreeSpace(%s) failed";
    v19 = 2091;
    goto LABEL_16;
  }
  v23 = SectorsPerCluster * BytesPerSector;
  v24 = *((_DWORD *)this + 8) - SectorsPerCluster * BytesPerSector;
  if ( v24 < (int)(0x100000 - SectorsPerCluster * BytesPerSector) )
  {
    v8 = -2147467259;
    v18 = L"File size(%lu) is incorrect";
    v19 = 2101;
LABEL_16:
    TraceStringInline(
      12,
      1,
      L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
      v19,
      L"CLogStorage::_NewLogFile",
      v8,
      v18);
    return v8;
  }
  if ( SetFilePointer(*((HANDLE *)this + 19), v24, 0, 0) != v24 )
  {
    v25 = GetLastError();
    v8 = v25;
    if ( v25 > 0 )
      v8 = (unsigned __int16)v25 | 0x80070000;
    v9 = L"SetFilePointer failed";
    v10 = 2113;
    goto LABEL_3;
  }
  v26 = malloc(v23);
  v27 = v26;
  if ( !v26 )
  {
    v8 = -2147024882;
    v9 = L"DtcAllocateMemory failed";
    v10 = 2123;
    goto LABEL_3;
  }
  memset_0(v26, 254, v23);
  if ( WriteFile(*((HANDLE *)this + 19), v27, v23, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v23 )
  {
    free(v27);
    if ( (GetFileAttributesW(&Buffer) & 0x800) != 0 )
    {
      OutputDebugStringA("\r\n");
      OutputDebugStringA("decompressing DTC log file on create\r\n");
      if ( !DeviceIoControl(*((HANDLE *)this + 19), 0x9C040u, InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      {
        v28 = GetLastError();
        TraceStringInline(
          12,
          1,
          L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
          2165,
          L"CLogStorage::_NewLogFile",
          v28,
          L"DeviceIoControl failed");
        return (unsigned int)-1073737700;
      }
    }
    v8 = 0;
    FileMappingW = CreateFileMappingW(*((HANDLE *)this + 19), 0, 4u, 0, *((_DWORD *)this + 8), 0);
    *((_QWORD *)this + 20) = FileMappingW;
    if ( !FileMappingW )
    {
      *((_QWORD *)this + 20) = -1;
      v30 = GetLastError();
      v8 = v30;
      if ( v30 > 0 )
        v8 = (unsigned __int16)v30 | 0x80070000;
      v9 = L"CreateFileMapping failed";
      v10 = 2184;
      goto LABEL_3;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v31 = *((_DWORD *)this + 10);
      for ( i = 0; ; ++i )
      {
        v32 = *((_DWORD *)this + 10);
        if ( i >= v14 )
          break;
        v33 = CLogStorage::_MapBuffer(this, i * v32, v31, 0, 0);
        v34 = (_DWORD *)*((_QWORD *)v33 + 3);
        v34[2] = 1;
        v34[3] = *((_DWORD *)this + 10) * i;
        v34[4] = 65537;
        if ( i <= 1 )
          *v34 = *((_DWORD *)this + 14);
        CLogStorage::_UnmapBuffer(this, v33, 0);
      }
      CLogStorage::_CommonInit(this, v32, *((_DWORD *)this + 29));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v48) )
      {
        *(_DWORD *)v54 = v48;
        TraceStringInline(
          12,
          1,
          L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
          2197,
          L"CLogStorage::_NewLogFile",
          v48,
          L"_InitLogPages failed");
        v8 = *(_DWORD *)v54;
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000C26E);
        return v8;
      }
      if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v49) )
      {
        *(_DWORD *)v54 = v49;
        TraceStringInline(
          12,
          1,
          L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
          2203,
          L"CLogStorage::_NewLogFile",
          v49,
          L"_InitLogPages failed");
        v8 = *(_DWORD *)v54;
        __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_18000C26E);
      }
    }
  }
  else
  {
    v36 = GetLastError();
    v8 = v36;
    if ( v36 > 0 )
      v8 = (unsigned __int16)v36 | 0x80070000;
    TraceStringInline(
      12,
      1,
      L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
      2139,
      L"CLogStorage::_NewLogFile",
      v8,
      L"WriteFile failed");
    free(v27);
  }
  return v8;
}

```

## disassembly

```asm
0x18000bc44  mov     r11, rsp
0x18000bc47  mov     [r11+18h], rbx
0x18000bc4b  mov     [r11+20h], rsi
0x18000bc4f  push    rdi
0x18000bc50  push    r12
0x18000bc52  push    r13
0x18000bc54  push    r14
0x18000bc56  push    r15
0x18000bc58  sub     rsp, 4F0h
0x18000bc5f  mov     rax, cs:__security_cookie
0x18000bc66  xor     rax, rsp
0x18000bc69  mov     [rsp+518h+var_38], rax
0x18000bc71  mov     edi, r9d
0x18000bc74  mov     r14d, r8d
0x18000bc77  mov     rbx, rdx
0x18000bc7a  mov     rsi, rcx
0x18000bc7d  xor     r13d, r13d
0x18000bc80  mov     [r11-458h], r13w
0x18000bc88  xor     eax, eax
0x18000bc8a  mov     dword ptr [rsp+518h+var_458+2], eax
0x18000bc91  mov     [r11-238h], r13w
0x18000bc99  xor     edx, edx; Val
0x18000bc9b  mov     r8d, 1FEh; Size
0x18000bca1  lea     rcx, [r11-236h]; void *
0x18000bca8  call    memset_0
0x18000bcad  mov     [rsp+518h+Buffer], r13w
0x18000bcb6  xor     edx, edx; Val
0x18000bcb8  mov     r8d, 200h; Size
0x18000bcbe  lea     rcx, [rsp+518h+var_446]; void *
0x18000bcc6  call    memset_0
0x18000bccb  mov     [rsp+518h+FilePart], r13
0x18000bcd0  xorps   xmm0, xmm0
0x18000bcd3  xor     eax, eax
0x18000bcd5  movups  [rsp+518h+pSecurityDescriptor], xmm0
0x18000bcdd  movups  [rsp+518h+var_470], xmm0
0x18000bce5  mov     [rsp+518h+var_460], rax
0x18000bced  movups  xmmword ptr [rsp+518h+SecurityAttributes.nLength], xmm0
0x18000bcf5  mov     qword ptr [rsp+518h+SecurityAttributes.bInheritHandle], rax
0x18000bcfd  mov     [rsp+518h+NumberOfBytesWritten], r13d
0x18000bd02  mov     [rsp+518h+RootPathName], r13w
0x18000bd0b  mov     [rsp+518h+var_44E], eax
0x18000bd12  mov     [rsp+518h+var_44A], ax
0x18000bd1a  mov     [rsp+518h+SectorsPerCluster], r13d
0x18000bd1f  mov     [rsp+518h+BytesPerSector], r13d
0x18000bd24  mov     [rsp+518h+NumberOfFreeClusters], r13d
0x18000bd29  mov     [rsp+518h+TotalNumberOfClusters], r13d
0x18000bd2e  mov     [rsp+518h+InBuffer], r13w
0x18000bd34  mov     [rsp+518h+BytesReturned], r13d
0x18000bd39  mov     qword ptr [rsi+98h], 0FFFFFFFFFFFFFFFFh
0x18000bd44  test    rbx, rbx
0x18000bd47  jnz     short loc_18000BD8B
0x18000bd49  mov     ebx, 80070057h
0x18000bd4e  lea     rax, aInvalidArgumen; "Invalid argument- ptstrFullFileSpec is "...
0x18000bd55  mov     r9d, 7D1h
0x18000bd5b  mov     edx, 1
0x18000bd60  mov     [rsp+518h+hTemplateFile], rax
0x18000bd65  mov     [rsp+518h+dwFlagsAndAttributes], ebx
0x18000bd69  lea     rax, aClogstorageNew; "CLogStorage::_NewLogFile"
0x18000bd70  mov     qword ptr [rsp+518h+dwCreationDisposition], rax
0x18000bd75  lea     r8, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000bd7c  mov     ecx, 0Ch
0x18000bd81  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000bd86  jmp     loc_18000C2CA
0x18000bd8b  lea     r9, [rsp+518h+FilePart]; lpFilePart
0x18000bd90  lea     r8, [rsp+518h+Buffer]; lpBuffer
0x18000bd98  mov     edx, 101h; nBufferLength
0x18000bd9d  mov     rcx, rbx; lpFileName
0x18000bda0  call    cs:__imp_GetFullPathNameW
0x18000bda6  test    eax, eax
0x18000bda8  jnz     short loc_18000BDCE
0x18000bdaa  call    cs:__imp_GetLastError
0x18000bdb0  mov     ebx, eax
0x18000bdb2  test    eax, eax
0x18000bdb4  jle     short loc_18000BDBF
0x18000bdb6  movzx   ebx, ax
0x18000bdb9  or      ebx, 80070000h
0x18000bdbf  lea     rax, aGetfullpathnam; "GetFullPathName failed"
0x18000bdc6  mov     r9d, 7D9h
0x18000bdcc  jmp     short loc_18000BD5B
0x18000bdce  lea     rax, [rsi+0A8h]
0x18000bdd5  mov     qword ptr [rsp+518h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18000bdda  mov     [rsp+518h+dwCreationDisposition], 100h; unsigned int
0x18000bde2  lea     r9, [rsp+518h+var_238]; unsigned __int16 *
0x18000bdea  lea     rdx, [rsp+518h+var_458]; unsigned __int16 *
0x18000bdf2  lea     rcx, [rsp+518h+Buffer]; unsigned __int16 *
0x18000bdfa  call    ?TracedSafeSplitPathW@@YAJPEAG0K0K0K0K@Z; TracedSafeSplitPathW(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong)
0x18000bdff  mov     dword ptr [rsi], 2
0x18000be05  mov     dword ptr [rsi+18h], 5
0x18000be0c  neg     edi
0x18000be0e  sbb     ebx, ebx
0x18000be10  neg     ebx
0x18000be12  mov     edi, 1
0x18000be17  add     ebx, edi
0x18000be19  mov     ecx, [rsi+28h]
0x18000be1c  mov     eax, [rsi+2Ch]
0x18000be1f  neg     eax
0x18000be21  and     eax, r14d
0x18000be24  xor     edx, edx
0x18000be26  div     ecx
0x18000be28  mov     r12d, eax
0x18000be2b  imul    ecx, eax
0x18000be2e  mov     [rsi+20h], ecx
0x18000be31  mov     edx, edi; dwRevision
0x18000be33  lea     rcx, [rsp+518h+pSecurityDescriptor]; pSecurityDescriptor
0x18000be3b  call    cs:__imp_InitializeSecurityDescriptor
0x18000be41  test    eax, eax
0x18000be43  jnz     short loc_18000BE6E
0x18000be45  call    cs:__imp_GetLastError
0x18000be4b  mov     ebx, eax
0x18000be4d  test    eax, eax
0x18000be4f  jle     short loc_18000BE5A
0x18000be51  movzx   ebx, ax
0x18000be54  or      ebx, 80070000h
0x18000be5a  lea     rax, aInitializesecu; "InitializeSecurityDescriptor failed"
0x18000be61  mov     r9d, 7FFh
0x18000be67  mov     edx, edi
0x18000be69  jmp     loc_18000BD60
0x18000be6e  mov     r9d, edi; bDaclDefaulted
0x18000be71  xor     r8d, r8d; pDacl
0x18000be74  xor     edx, edx; bDaclPresent
0x18000be76  lea     rcx, [rsp+518h+pSecurityDescriptor]; pSecurityDescriptor
0x18000be7e  call    cs:__imp_SetSecurityDescriptorDacl
0x18000be84  mov     r9d, edi; bSaclDefaulted
0x18000be87  xor     r8d, r8d; pSacl
0x18000be8a  xor     edx, edx; bSaclPresent
0x18000be8c  lea     rcx, [rsp+518h+pSecurityDescriptor]; pSecurityDescriptor
0x18000be94  call    cs:__imp_SetSecurityDescriptorSacl
0x18000be9a  mov     [rsp+518h+SecurityAttributes.nLength], 18h
0x18000bea5  lea     rax, [rsp+518h+pSecurityDescriptor]
0x18000bead  mov     [rsp+518h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000beb5  mov     [rsp+518h+SecurityAttributes.bInheritHandle], r13d
0x18000bebd  mov     [rsp+518h+hTemplateFile], r13; hTemplateFile
0x18000bec2  mov     [rsp+518h+dwFlagsAndAttributes], 0B0000080h; dwFlagsAndAttributes
0x18000beca  mov     [rsp+518h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000bece  lea     r9, [rsp+518h+SecurityAttributes]; lpSecurityAttributes
0x18000bed6  mov     edx, 0C0000000h; dwDesiredAccess
0x18000bedb  mov     r8d, 3; dwShareMode
0x18000bee1  lea     rcx, [rsp+518h+Buffer]; lpFileName
0x18000bee9  call    cs:__imp_CreateFileW
0x18000beef  mov     [rsi+98h], rax
0x18000bef6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000befa  jnz     short loc_18000BF58
0x18000befc  call    cs:__imp_GetLastError
0x18000bf02  mov     ebx, eax
0x18000bf04  test    eax, eax
0x18000bf06  jle     short loc_18000BF11
0x18000bf08  movzx   ebx, ax
0x18000bf0b  or      ebx, 80070000h
0x18000bf11  lea     rax, [rsp+518h+Buffer]
0x18000bf19  mov     [rsp+518h+lpOverlapped], rax
0x18000bf1e  lea     rax, aCreatefileSFai; "CreateFile(%s) failed"
0x18000bf25  mov     r9d, 817h
0x18000bf2b  mov     [rsp+518h+hTemplateFile], rax
0x18000bf30  mov     [rsp+518h+dwFlagsAndAttributes], ebx
0x18000bf34  lea     rax, aClogstorageNew; "CLogStorage::_NewLogFile"
0x18000bf3b  mov     qword ptr [rsp+518h+dwCreationDisposition], rax
0x18000bf40  lea     r8, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000bf47  mov     edx, edi
0x18000bf49  mov     ecx, 0Ch
0x18000bf4e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000bf53  jmp     loc_18000C2CA
0x18000bf58  mov     [rsp+518h+RootPathName], r13w
0x18000bf61  lea     r8, [rsp+518h+var_458]; unsigned __int16 *
0x18000bf69  mov     ebx, 4
0x18000bf6e  mov     edx, ebx; unsigned __int64
0x18000bf70  lea     rcx, [rsp+518h+RootPathName]; unsigned __int16 *
0x18000bf78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bf7d  test    eax, eax
0x18000bf7f  js      loc_18000C2F9
0x18000bf85  lea     r8, asc_180018224; "\\"
0x18000bf8c  mov     rdx, rbx; unsigned __int64
0x18000bf8f  lea     rcx, [rsp+518h+RootPathName]; unsigned __int16 *
0x18000bf97  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bf9c  test    eax, eax
0x18000bf9e  js      loc_18000C321
0x18000bfa4  lea     rax, [rsp+518h+TotalNumberOfClusters]
0x18000bfa9  mov     qword ptr [rsp+518h+dwCreationDisposition], rax; lpTotalNumberOfClusters
0x18000bfae  lea     r9, [rsp+518h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x18000bfb3  lea     r8, [rsp+518h+BytesPerSector]; lpBytesPerSector
0x18000bfb8  lea     rdx, [rsp+518h+SectorsPerCluster]; lpSectorsPerCluster
0x18000bfbd  lea     rcx, [rsp+518h+RootPathName]; lpRootPathName
0x18000bfc5  call    cs:__imp_GetDiskFreeSpaceW
0x18000bfcb  test    eax, eax
0x18000bfcd  jnz     short loc_18000C003
0x18000bfcf  call    cs:__imp_GetLastError
0x18000bfd5  mov     ebx, eax
0x18000bfd7  test    eax, eax
0x18000bfd9  jle     short loc_18000BFE4
0x18000bfdb  movzx   ebx, ax
0x18000bfde  or      ebx, 80070000h
0x18000bfe4  lea     rax, [rsp+518h+RootPathName]
0x18000bfec  mov     [rsp+518h+lpOverlapped], rax
0x18000bff1  lea     rax, aGetdiskfreespa; "GetDiskFreeSpace(%s) failed"
0x18000bff8  mov     r9d, 82Bh
0x18000bffe  jmp     loc_18000BF2B
0x18000c003  mov     ebx, [rsp+518h+BytesPerSector]
0x18000c007  imul    ebx, [rsp+518h+SectorsPerCluster]
0x18000c00c  mov     ecx, [rsi+20h]
0x18000c00f  mov     r14d, ecx
0x18000c012  sub     r14d, ebx
0x18000c015  mov     eax, 100000h
0x18000c01a  sub     eax, ebx
0x18000c01c  cmp     r14d, eax
0x18000c01f  jge     short loc_18000C03C
0x18000c021  mov     ebx, 80004005h
0x18000c026  mov     dword ptr [rsp+518h+lpOverlapped], ecx
0x18000c02a  lea     rax, aFileSizeLuIsIn; "File size(%lu) is incorrect"
0x18000c031  mov     r9d, 835h
0x18000c037  jmp     loc_18000BF2B
0x18000c03c  xor     r9d, r9d; dwMoveMethod
0x18000c03f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000c042  mov     edx, r14d; lDistanceToMove
0x18000c045  mov     rcx, [rsi+98h]; hFile
0x18000c04c  call    cs:__imp_SetFilePointer
0x18000c052  cmp     eax, r14d
0x18000c055  jz      short loc_18000C07E
0x18000c057  call    cs:__imp_GetLastError
0x18000c05d  mov     ebx, eax
0x18000c05f  test    eax, eax
0x18000c061  jle     short loc_18000C06C
0x18000c063  movzx   ebx, ax
0x18000c066  or      ebx, 80070000h
0x18000c06c  lea     rax, aSetfilepointer; "SetFilePointer failed"
0x18000c073  mov     r9d, 841h
0x18000c079  jmp     loc_18000BE67
0x18000c07e  mov     r15d, ebx
0x18000c081  mov     ecx, ebx; Size
0x18000c083  call    cs:__imp_malloc
0x18000c089  mov     r14, rax
0x18000c08c  test    rax, rax
0x18000c08f  jnz     short loc_18000C0A8
0x18000c091  mov     ebx, 8007000Eh
0x18000c096  lea     rax, aDtcallocatemem; "DtcAllocateMemory failed"
0x18000c09d  mov     r9d, 84Bh
0x18000c0a3  jmp     loc_18000BE67
0x18000c0a8  mov     r8, r15; Size
0x18000c0ab  mov     edx, 0FEh; Val
0x18000c0b0  mov     rcx, r14; void *
0x18000c0b3  call    memset_0
0x18000c0b8  mov     qword ptr [rsp+518h+dwCreationDisposition], r13; lpOverlapped
0x18000c0bd  lea     r9, [rsp+518h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c0c2  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000c0c5  mov     rdx, r14; lpBuffer
0x18000c0c8  mov     rcx, [rsi+98h]; hFile
0x18000c0cf  call    cs:__imp_WriteFile
0x18000c0d5  test    eax, eax
0x18000c0d7  jz      loc_18000C277
0x18000c0dd  cmp     [rsp+518h+NumberOfBytesWritten], ebx
0x18000c0e1  jnz     loc_18000C277
0x18000c0e7  mov     rcx, r14; Block
0x18000c0ea  call    cs:__imp_free
0x18000c0f0  lea     rcx, [rsp+518h+Buffer]; lpFileName
0x18000c0f8  call    cs:__imp_GetFileAttributesW
0x18000c0fe  bt      eax, 0Bh
0x18000c102  jnb     loc_18000C1A1
0x18000c108  lea     rcx, OutputString; "\r\n"
0x18000c10f  call    cs:__imp_OutputDebugStringA
0x18000c115  lea     rcx, aDecompressingD; "decompressing DTC log file on create\r"...
0x18000c11c  call    cs:__imp_OutputDebugStringA
0x18000c122  mov     [rsp+518h+lpOverlapped], r13; lpOverlapped
0x18000c127  lea     rax, [rsp+518h+BytesReturned]
0x18000c12c  mov     [rsp+518h+hTemplateFile], rax; lpBytesReturned
0x18000c131  mov     [rsp+518h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x18000c136  mov     qword ptr [rsp+518h+dwCreationDisposition], r13; lpOutBuffer
0x18000c13b  mov     r9d, 2; nInBufferSize
0x18000c141  lea     r8, [rsp+518h+InBuffer]; lpInBuffer
0x18000c146  mov     edx, 9C040h; dwIoControlCode
0x18000c14b  mov     rcx, [rsi+98h]; hDevice
0x18000c152  call    cs:__imp_DeviceIoControl
0x18000c158  test    eax, eax
0x18000c15a  jnz     short loc_18000C1A1
0x18000c15c  call    cs:__imp_GetLastError
0x18000c162  lea     rcx, aDeviceiocontro; "DeviceIoControl failed"
0x18000c169  mov     [rsp+518h+hTemplateFile], rcx
0x18000c16e  mov     [rsp+518h+dwFlagsAndAttributes], eax
0x18000c172  lea     rax, aClogstorageNew; "CLogStorage::_NewLogFile"
0x18000c179  mov     qword ptr [rsp+518h+dwCreationDisposition], rax
0x18000c17e  mov     r9d, 875h
0x18000c184  lea     r8, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c18b  mov     edx, edi
0x18000c18d  mov     ecx, 0Ch
0x18000c192  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000c197  mov     ebx, 0C000101Ch
0x18000c19c  jmp     loc_18000C2CA
0x18000c1a1  mov     ebx, r13d
0x18000c1a4  mov     qword ptr [rsp+518h+dwFlagsAndAttributes], r13; lpName
0x18000c1a9  mov     eax, [rsi+20h]
0x18000c1ac  mov     [rsp+518h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18000c1b0  xor     r9d, r9d; dwMaximumSizeHigh
0x18000c1b3  xor     edx, edx; lpFileMappingAttributes
0x18000c1b5  lea     r8d, [r9+4]; flProtect
0x18000c1b9  mov     rcx, [rsi+98h]; hFile
0x18000c1c0  call    cs:__imp_CreateFileMappingW
0x18000c1c6  mov     [rsi+0A0h], rax
0x18000c1cd  test    rax, rax
0x18000c1d0  jnz     short loc_18000C204
0x18000c1d2  mov     qword ptr [rsi+0A0h], 0FFFFFFFFFFFFFFFFh
0x18000c1dd  call    cs:__imp_GetLastError
0x18000c1e3  mov     ebx, eax
0x18000c1e5  test    eax, eax
  ... truncated ...
```
