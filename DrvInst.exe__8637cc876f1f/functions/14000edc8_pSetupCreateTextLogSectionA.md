# pSetupCreateTextLogSectionA

- ea: `0x14000edc8`
- end: `0x14000f31a`
- name: `pSetupCreateTextLogSectionA`
- size: `1362`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f320`

## callees

- `0x14000a570`
- `0x14000bf04`
- `0x14000c3b4`
- `0x14000cd18`
- `0x14000cdc4`
- `0x14000d2ec`
- `0x14000d4e0`
- `0x14000d644`
- `0x14000d7b4`
- `0x14000d84c`
- `0x14000d8c0`
- `0x14000d98c`
- `0x14000da54`
- `0x14000dfd4`
- `0x14000e04c`
- `0x14000e264`
- `0x14000e680`
- `0x14000edc8`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x14000f1ca`
- `ntdll!RtlGetVersion` at `0x14000f1ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000ee84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000ee84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000eed4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000eed4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f124`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f2cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f124`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f2e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f2e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x14000ef2c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x14000ef2c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14000f00e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14000f00e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14000eff8`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14000eff8`

## string_xrefs

- `0x14000f0ea`: `     Hardware Configuration: %s`
- `0x14000f225`: ` os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s`

## pseudocode

```c
_BOOL8 __fastcall pSetupCreateTextLogSectionA(const char *a1, __int64 a2, CHAR *a3, unsigned __int64 *a4)
{
  CHAR *v4; // rbx
  DWORD LastError; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // r15d
  SIZE_T v11; // r14
  char *v12; // rax
  char *v13; // r12
  int v14; // r13d
  HRESULT v15; // eax
  LPSTR CommandLineA; // rax
  int v17; // r8d
  __int64 v18; // rdi
  int LogStatus; // esi
  int IsPortableOS; // eax
  unsigned int v21; // edx
  const char *v22; // rax
  char *v23; // rdi
  int v24; // r14d
  int v25; // esi
  __int64 v26; // rdi
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+64h] [rbp-9Ch] BYREF
  _OWORD v30[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  FILETIME FileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 *v35; // [rsp+B0h] [rbp-50h]
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-48h] BYREF
  int v37; // [rsp+C8h] [rbp-38h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v39; // [rsp+1E4h] [rbp+E4h]
  unsigned __int16 v40; // [rsp+1E6h] [rbp+E6h]
  unsigned __int16 v41; // [rsp+1E8h] [rbp+E8h]
  unsigned __int8 v42; // [rsp+1EAh] [rbp+EAh]
  WCHAR WideCharStr[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  char pszDest[128]; // [rsp+240h] [rbp+140h] BYREF
  char v45[272]; // [rsp+2C0h] [rbp+1C0h] BYREF
  CHAR Filename[528]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v35 = a4;
  v32 = 0;
  v37 = 0;
  memset(v30, 0, sizeof(v30));
  v28 = 0;
  v4 = a3;
  v29 = 0;
  v31 = 0;
  SystemTime = 0;
  if ( (unsigned int)GetTextLogKeyFromStrings(a1, a3, a3, &v29)
    && (g_sputils_LogInitialized || (unsigned int)pSpUtilsLogInitialize()) )
  {
    if ( (_DWORD)GlobalDevLogData )
    {
      if ( !v4 )
      {
        v4 = Filename;
        if ( !GetModuleFileNameA(0, Filename, 0x208u) )
          v4 = "no title";
      }
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( v4[v8] );
      if ( a1 )
      {
        v9 = -1;
        do
          ++v9;
        while ( a1[v9] );
        LODWORD(v8) = v9 + v8;
      }
      v10 = v8 + 16;
      v11 = (unsigned int)(v8 + 16);
      v12 = (char *)HeapAlloc(hHeap, 0, v11);
      v13 = v12;
      if ( v12 )
      {
        v14 = 0;
        if ( a1 )
          v15 = StringCchPrintfA(v12, v11, "[%s - %s]", v4, a1);
        else
          v15 = StringCchPrintfA(v12, v11, "[%s]", v4);
        if ( v15 >= 0 )
        {
          CommandLineA = GetCommandLineA();
          do
            ++v7;
          while ( CommandLineA[v7] );
          LastError = TextLogMapFile(&GlobalDevLogData, v30, (unsigned int)(v7 + v10 + 326), 0);
          if ( !LastError )
          {
            if ( (unsigned int)TextLogFindSection(v30, 3, &SystemTime, &v28) )
            {
              TextLogWriteSectionFooter((unsigned int)v30, (unsigned int)&SystemTime, v17, 0, 0);
              TextLogDeleteCtlTag(v30, v28);
            }
            v18 = v31;
            if ( (*(_DWORD *)(v31 + 12) & 0x1000) == 0 )
            {
              LogStatus = TextLogGetLogStatus(v31);
              if ( (LogStatus & 0x1000) == 0 )
              {
                FileTime = 0;
                LocalFileTime = 0;
                SystemTime = 0;
                v28 = 0;
                if ( (unsigned int)pSetupGetSystemBootTime(&FileTime)
                  && FileTimeToLocalFileTime(&FileTime, &LocalFileTime)
                  && FileTimeToSystemTime(&LocalFileTime, &SystemTime)
                  && StringCchPrintfA(
                       pszDest,
                       0x80u,
                       "[Boot Session: %04d/%02d/%02d %02d:%02d:%02d.%03d]",
                       SystemTime.wYear,
                       SystemTime.wMonth,
                       SystemTime.wDay,
                       SystemTime.wHour,
                       SystemTime.wMinute,
                       SystemTime.wSecond,
                       SystemTime.wMilliseconds) >= 0 )
                {
                  TextLogInsertString(v30, DWORD2(v31), "\r\n");
                  TextLogInsertString(v30, DWORD2(v31), pszDest);
                  IsPortableOS = TextLogIsPortableOS(&v28);
                  v21 = v28;
                  if ( IsPortableOS )
                    v21 = 0;
                  if ( v21 )
                  {
                    if ( (unsigned int)TextLogGetHardwareConfigurationGuid(WideCharStr) )
                      WideCharStr[0] = 0;
                    v22 = (const char *)pSetupUnicodeToMultiByte(WideCharStr);
                    v23 = (char *)v22;
                    if ( v22 )
                    {
                      if ( StringCchPrintfA(pszDest, 0x80u, "     Hardware Configuration: %s", v22) >= 0 )
                        TextLogInsertString(v30, DWORD2(v31), pszDest);
                      HeapFree(hHeap, 0, v23);
                    }
                  }
                  v18 = v31;
                }
                TextLogSetLogStatus(v18, LogStatus | 0x1000u);
              }
              *(_DWORD *)(v18 + 12) |= 0x1000u;
            }
            v14 = 1;
            TextLogInsertString(v30, DWORD2(v31), "\r\n");
            v24 = DWORD2(v31);
            TextLogWriteEntry((unsigned int)v30, DWORD2(v31), (_DWORD)v13, 0, 16, 0);
            TextLogWriteEntry((unsigned int)v30, DWORD2(v31), (unsigned int)"Section start", 0, 65552, 0);
            if ( TextLogOffline )
            {
              memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
              VersionInformation.dwOSVersionInfoSize = 284;
              if ( RtlGetVersion(&VersionInformation) >= 0
                && StringCchPrintfA(
                     v45,
                     0x104u,
                     " os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s",
                     VersionInformation.dwMajorVersion,
                     VersionInformation.dwMinorVersion,
                     VersionInformation.dwBuildNumber,
                     v39,
                     v40,
                     v41,
                     v42,
                     "amd64") >= 0 )
              {
                TextLogWriteEntry((unsigned int)v30, DWORD2(v31), (unsigned int)v45, 0, 0, 0);
              }
            }
            v25 = DWORD2(v31);
            TextLogInsertString(v30, DWORD2(v31), "<ins>");
            v26 = v29;
            if ( v29 )
            {
              *(_DWORD *)&SystemTime.wYear = -522186479;
              *(_DWORD *)&SystemTime.wDayOfWeek = v29;
              *(_DWORD *)&SystemTime.wHour = v24;
              *(_DWORD *)&SystemTime.wSecond = v25;
              v37 = 0;
              TextLogInsertCtlTag(v30, &SystemTime);
            }
            if ( v35 )
              *v35 = v26 | ((unsigned __int64)(GlobalDevLogData & 0xF) << 32);
          }
        }
        else
        {
          LastError = (unsigned __int16)v15;
        }
        HeapFree(hHeap, 0, v13);
        if ( v14 )
          TextLogUnmapFile(v30);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = 4309;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14000edc8  mov     [rsp-8+arg_8], rbx
0x14000edcd  push    rbp
0x14000edce  push    rsi
0x14000edcf  push    rdi
0x14000edd0  push    r12
0x14000edd2  push    r13
0x14000edd4  push    r14
0x14000edd6  push    r15
0x14000edd8  lea     rbp, [rsp-4F0h]
0x14000ede0  sub     rsp, 5F0h
0x14000ede7  mov     rax, cs:__security_cookie
0x14000edee  xor     rax, rsp
0x14000edf1  mov     [rbp+520h+var_40], rax
0x14000edf8  xorps   xmm0, xmm0
0x14000edfb  mov     [rbp+520h+var_570], r9
0x14000edff  xor     eax, eax
0x14000ee01  lea     r9, [rsp+620h+var_5BC]
0x14000ee06  xor     r15d, r15d
0x14000ee09  mov     [rbp+520h+var_588], rax
0x14000ee0d  mov     rdx, r8
0x14000ee10  mov     [rbp+520h+var_558], eax
0x14000ee13  movups  [rsp+620h+var_5B8], xmm0
0x14000ee18  mov     [rsp+620h+var_5C0], r15d
0x14000ee1d  mov     rbx, r8
0x14000ee20  movups  [rsp+620h+var_5A8], xmm0
0x14000ee25  mov     [rsp+620h+var_5BC], r15d
0x14000ee2a  mov     rsi, rcx
0x14000ee2d  movups  [rbp+520h+var_598], xmm0
0x14000ee31  movups  xmmword ptr [rbp+520h+SystemTime.wYear], xmm0
0x14000ee35  call    GetTextLogKeyFromStrings
0x14000ee3a  test    eax, eax
0x14000ee3c  jnz     short loc_14000EE4B
0x14000ee3e  call    cs:__imp_GetLastError
0x14000ee44  mov     ebx, eax
0x14000ee46  jmp     loc_14000F2E0
0x14000ee4b  cmp     cs:g_sputils_LogInitialized, r15d
0x14000ee52  jnz     short loc_14000EE5D
0x14000ee54  call    _pSpUtilsLogInitialize
0x14000ee59  test    eax, eax
0x14000ee5b  jz      short loc_14000EE3E
0x14000ee5d  cmp     dword ptr cs:GlobalDevLogData, r15d
0x14000ee64  jnz     short loc_14000EE70
0x14000ee66  mov     ebx, 10D5h
0x14000ee6b  jmp     loc_14000F2E0
0x14000ee70  test    rbx, rbx
0x14000ee73  jnz     short loc_14000EE9E
0x14000ee75  mov     r8d, 208h; nSize
0x14000ee7b  lea     rdx, [rbp+520h+Filename]; lpFilename
0x14000ee82  xor     ecx, ecx; hModule
0x14000ee84  call    cs:__imp_GetModuleFileNameA
0x14000ee8a  test    eax, eax
0x14000ee8c  lea     rbx, [rbp+520h+Filename]
0x14000ee93  lea     rcx, aNoTitle; "no title"
0x14000ee9a  cmovz   rbx, rcx
0x14000ee9e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000eea2  mov     rax, rdi
0x14000eea5  inc     rax
0x14000eea8  cmp     [rbx+rax], r15b
0x14000eeac  jnz     short loc_14000EEA5
0x14000eeae  test    rsi, rsi
0x14000eeb1  jz      short loc_14000EEC1
0x14000eeb3  mov     rcx, rdi
0x14000eeb6  inc     rcx
0x14000eeb9  cmp     [rsi+rcx], r15b
0x14000eebd  jnz     short loc_14000EEB6
0x14000eebf  add     eax, ecx
0x14000eec1  mov     rcx, cs:hHeap; hHeap
0x14000eec8  lea     r15d, [rax+10h]
0x14000eecc  mov     r8d, r15d; dwBytes
0x14000eecf  xor     edx, edx; dwFlags
0x14000eed1  mov     r14d, r15d
0x14000eed4  call    cs:__imp_HeapAlloc
0x14000eeda  mov     r12, rax
0x14000eedd  test    rax, rax
0x14000eee0  jnz     short loc_14000EEED
0x14000eee2  lea     ebx, [rax+8]
0x14000eee5  xor     r15d, r15d
0x14000eee8  jmp     loc_14000F2E0
0x14000eeed  xor     r13d, r13d
0x14000eef0  mov     r9, rbx
0x14000eef3  mov     rdx, r14; cchDest
0x14000eef6  mov     rcx, r12; pszDest
0x14000eef9  test    rsi, rsi
0x14000eefc  jz      short loc_14000EF11
0x14000eefe  lea     r8, aSS_0; "[%s - %s]"
0x14000ef05  mov     [rsp+620h+var_600], rsi
0x14000ef0a  call    StringCchPrintfA
0x14000ef0f  jmp     short loc_14000EF1D
0x14000ef11  lea     r8, aS; "[%s]"
0x14000ef18  call    StringCchPrintfA
0x14000ef1d  test    eax, eax
0x14000ef1f  jns     short loc_14000EF2C
0x14000ef21  movzx   ebx, ax
0x14000ef24  xor     r15d, r15d
0x14000ef27  jmp     loc_14000F2BF
0x14000ef2c  call    cs:__imp_GetCommandLineA
0x14000ef32  inc     rdi
0x14000ef35  cmp     [rax+rdi], r13b
0x14000ef39  jnz     short loc_14000EF32
0x14000ef3b  lea     r8d, [r15+146h]
0x14000ef42  xor     r9d, r9d
0x14000ef45  add     r8d, edi
0x14000ef48  lea     rdx, [rsp+620h+var_5B8]
0x14000ef4d  lea     rcx, GlobalDevLogData
0x14000ef54  call    TextLogMapFile
0x14000ef59  xor     r15d, r15d
0x14000ef5c  mov     ebx, eax
0x14000ef5e  test    eax, eax
0x14000ef60  jnz     loc_14000F2BF
0x14000ef66  lea     r9, [rsp+620h+var_5C0]
0x14000ef6b  lea     r8, [rbp+520h+SystemTime]
0x14000ef6f  lea     edx, [rax+3]
0x14000ef72  lea     rcx, [rsp+620h+var_5B8]
0x14000ef77  call    TextLogFindSection
0x14000ef7c  test    eax, eax
0x14000ef7e  jz      short loc_14000EFA4
0x14000ef80  xor     r9d, r9d
0x14000ef83  mov     dword ptr [rsp+620h+var_600], r15d
0x14000ef88  lea     rdx, [rbp+520h+SystemTime]
0x14000ef8c  lea     rcx, [rsp+620h+var_5B8]
0x14000ef91  call    TextLogWriteSectionFooter
0x14000ef96  mov     edx, [rsp+620h+var_5C0]
0x14000ef9a  lea     rcx, [rsp+620h+var_5B8]
0x14000ef9f  call    TextLogDeleteCtlTag
0x14000efa4  mov     rdi, qword ptr [rbp+520h+var_598]
0x14000efa8  mov     r14d, 1000h
0x14000efae  test    [rdi+0Ch], r14d
0x14000efb2  jnz     loc_14000F13F
0x14000efb8  mov     rcx, rdi
0x14000efbb  call    TextLogGetLogStatus
0x14000efc0  mov     esi, eax
0x14000efc2  test    r14d, eax
0x14000efc5  jnz     loc_14000F13B
0x14000efcb  xorps   xmm0, xmm0
0x14000efce  mov     qword ptr [rbp+520h+FileTime.dwLowDateTime], r15
0x14000efd2  lea     rcx, [rbp+520h+FileTime]
0x14000efd6  mov     qword ptr [rbp+520h+LocalFileTime.dwLowDateTime], r15
0x14000efda  movups  xmmword ptr [rbp+520h+SystemTime.wYear], xmm0
0x14000efde  mov     [rsp+620h+var_5C0], r15d
0x14000efe3  call    pSetupGetSystemBootTime
0x14000efe8  test    eax, eax
0x14000efea  jz      loc_14000F12E
0x14000eff0  lea     rdx, [rbp+520h+LocalFileTime]; lpLocalFileTime
0x14000eff4  lea     rcx, [rbp+520h+FileTime]; lpFileTime
0x14000eff8  call    cs:__imp_FileTimeToLocalFileTime
0x14000effe  test    eax, eax
0x14000f000  jz      loc_14000F12E
0x14000f006  lea     rdx, [rbp+520h+SystemTime]; lpSystemTime
0x14000f00a  lea     rcx, [rbp+520h+LocalFileTime]; lpFileTime
0x14000f00e  call    cs:__imp_FileTimeToSystemTime
0x14000f014  test    eax, eax
0x14000f016  jz      loc_14000F12E
0x14000f01c  movzx   ecx, [rbp+520h+SystemTime.wSecond]
0x14000f020  mov     r13d, 80h
0x14000f026  movzx   edx, [rbp+520h+SystemTime.wMinute]
0x14000f02a  movzx   r8d, [rbp+520h+SystemTime.wHour]
0x14000f02f  movzx   eax, [rbp+520h+SystemTime.wMilliseconds]
0x14000f033  movzx   r10d, [rbp+520h+SystemTime.wDay]
0x14000f038  movzx   r11d, [rbp+520h+SystemTime.wMonth]
0x14000f03d  movzx   r9d, [rbp+520h+SystemTime.wYear]
0x14000f042  mov     [rsp+620h+var_5D8], eax
0x14000f046  mov     [rsp+620h+var_5E0], ecx
0x14000f04a  lea     rcx, [rbp+520h+pszDest]; pszDest
0x14000f051  mov     [rsp+620h+var_5E8], edx
0x14000f055  mov     edx, r13d; cchDest
0x14000f058  mov     [rsp+620h+var_5F0], r8d
0x14000f05d  lea     r8, aBootSession04d; "[Boot Session: %04d/%02d/%02d %02d:%02d"...
0x14000f064  mov     [rsp+620h+var_5F8], r10d
0x14000f069  mov     dword ptr [rsp+620h+var_600], r11d
0x14000f06e  call    StringCchPrintfA
0x14000f073  test    eax, eax
0x14000f075  js      loc_14000F12E
0x14000f07b  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f07e  lea     r8, asc_14004AC64; "\r\n"
0x14000f085  lea     rcx, [rsp+620h+var_5B8]
0x14000f08a  call    TextLogInsertString
0x14000f08f  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f092  lea     r8, [rbp+520h+pszDest]
0x14000f099  lea     rcx, [rsp+620h+var_5B8]
0x14000f09e  call    TextLogInsertString
0x14000f0a3  lea     rcx, [rsp+620h+var_5C0]
0x14000f0a8  call    TextLogIsPortableOS
0x14000f0ad  mov     edx, [rsp+620h+var_5C0]
0x14000f0b1  test    eax, eax
0x14000f0b3  cmovnz  edx, r15d
0x14000f0b7  test    edx, edx
0x14000f0b9  jz      short loc_14000F12A
0x14000f0bb  lea     rcx, [rbp+520h+WideCharStr]
0x14000f0c2  call    TextLogGetHardwareConfigurationGuid
0x14000f0c7  test    eax, eax
0x14000f0c9  jz      short loc_14000F0D3
0x14000f0cb  mov     [rbp+520h+WideCharStr], r15w
0x14000f0d3  lea     rcx, [rbp+520h+WideCharStr]; lpWideCharStr
0x14000f0da  call    pSetupUnicodeToMultiByte
0x14000f0df  mov     rdi, rax
0x14000f0e2  test    rax, rax
0x14000f0e5  jz      short loc_14000F12A
0x14000f0e7  mov     r9, rax
0x14000f0ea  lea     r8, aHardwareConfig; "     Hardware Configuration: %s"
0x14000f0f1  mov     rdx, r13; cchDest
0x14000f0f4  lea     rcx, [rbp+520h+pszDest]; pszDest
0x14000f0fb  call    StringCchPrintfA
0x14000f100  test    eax, eax
0x14000f102  js      short loc_14000F118
0x14000f104  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f107  lea     r8, [rbp+520h+pszDest]
0x14000f10e  lea     rcx, [rsp+620h+var_5B8]
0x14000f113  call    TextLogInsertString
0x14000f118  mov     rcx, cs:hHeap; hHeap
0x14000f11f  mov     r8, rdi; lpMem
0x14000f122  xor     edx, edx; dwFlags
0x14000f124  call    cs:__imp_HeapFree
0x14000f12a  mov     rdi, qword ptr [rbp+520h+var_598]
0x14000f12e  or      esi, r14d
0x14000f131  mov     rcx, rdi
0x14000f134  mov     edx, esi
0x14000f136  call    TextLogSetLogStatus
0x14000f13b  or      [rdi+0Ch], r14d
0x14000f13f  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f142  lea     r8, asc_14004AC64; "\r\n"
0x14000f149  lea     rcx, [rsp+620h+var_5B8]
0x14000f14e  mov     r13d, 1
0x14000f154  call    TextLogInsertString
0x14000f159  mov     r14d, dword ptr [rbp+520h+var_598+8]
0x14000f15d  lea     rcx, [rsp+620h+var_5B8]
0x14000f162  xor     r9d, r9d
0x14000f165  mov     [rsp+620h+var_5F8], r15d
0x14000f16a  mov     r8, r12
0x14000f16d  mov     dword ptr [rsp+620h+var_600], 10h
0x14000f175  mov     edx, r14d
0x14000f178  call    TextLogWriteEntry
0x14000f17d  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f180  lea     r8, aSectionStart; "Section start"
0x14000f187  xor     r9d, r9d
0x14000f18a  mov     [rsp+620h+var_5F8], r15d
0x14000f18f  lea     rcx, [rsp+620h+var_5B8]
0x14000f194  mov     dword ptr [rsp+620h+var_600], 10010h
0x14000f19c  call    TextLogWriteEntry
0x14000f1a1  cmp     cs:TextLogOffline, r15d
0x14000f1a8  jz      loc_14000F261
0x14000f1ae  xor     edx, edx; Val
0x14000f1b0  lea     rcx, [rbp+520h+VersionInformation.dwMajorVersion]; void *
0x14000f1b4  mov     r8d, 118h; Size
0x14000f1ba  call    memset_0
0x14000f1bf  lea     rcx, [rbp+520h+VersionInformation]; lpVersionInformation
0x14000f1c3  mov     [rbp+520h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000f1ca  call    cs:__imp_RtlGetVersion
0x14000f1d0  test    eax, eax
0x14000f1d2  js      loc_14000F261
0x14000f1d8  movzx   eax, [rbp+520h+var_436]
0x14000f1df  lea     r9, aAmd64; "amd64"
0x14000f1e6  movzx   ecx, [rbp+520h+var_438]
0x14000f1ed  movzx   edx, [rbp+520h+var_43A]
0x14000f1f4  movzx   r8d, [rbp+520h+var_43C]
0x14000f1fc  mov     [rsp+620h+var_5D0], r9
0x14000f201  mov     r9d, [rbp+520h+VersionInformation.dwMajorVersion]
0x14000f205  mov     [rsp+620h+var_5D8], eax
0x14000f209  mov     eax, [rbp+520h+VersionInformation.dwBuildNumber]
0x14000f20c  mov     [rsp+620h+var_5E0], ecx
0x14000f210  lea     rcx, [rbp+520h+var_360]; pszDest
0x14000f217  mov     [rsp+620h+var_5E8], edx
0x14000f21b  mov     edx, 104h; cchDest
0x14000f220  mov     [rsp+620h+var_5F0], r8d
0x14000f225  lea     r8, aOsVersionDDDSe; " os: Version = %d.%d.%d, Service Pack ="...
0x14000f22c  mov     [rsp+620h+var_5F8], eax
0x14000f230  mov     eax, [rbp+520h+VersionInformation.dwMinorVersion]
0x14000f233  mov     dword ptr [rsp+620h+var_600], eax
0x14000f237  call    StringCchPrintfA
0x14000f23c  test    eax, eax
0x14000f23e  js      short loc_14000F261
0x14000f240  mov     edx, dword ptr [rbp+520h+var_598+8]
0x14000f243  lea     r8, [rbp+520h+var_360]
0x14000f24a  mov     [rsp+620h+var_5F8], r15d
0x14000f24f  lea     rcx, [rsp+620h+var_5B8]
0x14000f254  xor     r9d, r9d
0x14000f257  mov     dword ptr [rsp+620h+var_600], r15d
0x14000f25c  call    TextLogWriteEntry
0x14000f261  mov     esi, dword ptr [rbp+520h+var_598+8]
0x14000f264  lea     r8, aIns; "<ins>"
0x14000f26b  mov     edx, esi
0x14000f26d  lea     rcx, [rsp+620h+var_5B8]
0x14000f272  call    TextLogInsertString
0x14000f277  mov     edi, [rsp+620h+var_5BC]
0x14000f27b  test    edi, edi
0x14000f27d  jz      short loc_14000F2A2
0x14000f27f  lea     rdx, [rbp+520h+SystemTime]
0x14000f283  mov     dword ptr [rbp+520h+SystemTime.wYear], 0E0E01111h
0x14000f28a  lea     rcx, [rsp+620h+var_5B8]
0x14000f28f  mov     dword ptr [rbp+520h+SystemTime.wDayOfWeek], edi
0x14000f292  mov     dword ptr [rbp+520h+SystemTime.wHour], r14d
0x14000f296  mov     dword ptr [rbp+520h+SystemTime.wSecond], esi
0x14000f299  mov     [rbp+520h+var_558], r15d
0x14000f29d  call    TextLogInsertCtlTag
0x14000f2a2  mov     rdx, [rbp+520h+var_570]
0x14000f2a6  test    rdx, rdx
0x14000f2a9  jz      short loc_14000F2BF
0x14000f2ab  mov     rcx, cs:GlobalDevLogData
0x14000f2b2  and     ecx, 0Fh
0x14000f2b5  shl     rcx, 20h
0x14000f2b9  or      rcx, rdi
  ... truncated ...
```
