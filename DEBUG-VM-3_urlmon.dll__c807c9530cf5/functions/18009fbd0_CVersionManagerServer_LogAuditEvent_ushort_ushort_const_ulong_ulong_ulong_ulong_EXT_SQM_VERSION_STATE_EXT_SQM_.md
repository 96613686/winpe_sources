# CVersionManagerServer::_LogAuditEvent(ushort *,ushort const *,ulong,ulong,ulong,ulong,EXT_SQM_VERSION_STATE,EXT_SQM_VERSION_REASON,int)

- ea: `0x18009fbd0`
- end: `0x1800a00ef`
- name: `?_LogAuditEvent@CVersionManagerServer@@AEAAJPEAGPEBGKKKKW4EXT_SQM_VERSION_STATE@@W4EXT_SQM_VERSION_REASON@@H@Z`
- size: `1311`
- prototype: `int __high(unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, enum EXT_SQM_VERSION_STATE, enum EXT_SQM_VERSION_REASON, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f9c30`

## callees

- `0x180044b84`
- `0x18005cc10`
- `0x18009fbd0`
- `0x1800a00f8`
- `0x1800f68a8`
- `0x1800f70dc`
- `0x1800f937c`
- `0x1800f9a6c`
- `0x18010e4f0`
- `0x18011a86c`
- `0x18011baa0`

## import_xrefs

- `msvcrt!strnlen` at `0x18009fdd0`
- `msvcrt!strnlen` at `0x18009fddf`
- `msvcrt!strnlen` at `0x18009fdee`
- `msvcrt!strnlen` at `0x18009fe02`
- `msvcrt!strnlen` at `0x18009fe13`
- `msvcrt!strnlen` at `0x18009fdd0`
- `msvcrt!strnlen` at `0x18009fddf`
- `msvcrt!strnlen` at `0x18009fdee`
- `msvcrt!strnlen` at `0x18009fe02`
- `msvcrt!strnlen` at `0x18009fe13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a00bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a00bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ffea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a001c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a007d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ffea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a001c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a007d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0091`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0091`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18009ff0c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18009ff0c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a0011`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a0011`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a0053`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a0053`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009ff20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009ff20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ffd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ffd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009fe38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009fe38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009feae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009feb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a00c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009feae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009feb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a00c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18009fc42`
- `OLEAUT32!__imp_SysStringLen` at `0x18009fc42`

## string_xrefs

- `0x18009fd1a`: `Not EPM Compatible`
- `0x18009fd21`: `EPM Compatible`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_LogAuditEvent(
        __int64 a1,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        unsigned int a9,
        int a10)
{
  char *v14; // r12
  SIZE_T v15; // r14
  char *v16; // r15
  unsigned int v17; // r13d
  CVersionManagerServer *v18; // rcx
  int LocalDirectory; // ebx
  int v20; // eax
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  const char *v23; // r8
  unsigned int v24; // r10d
  const char *v25; // r8
  int v26; // r10d
  int v27; // eax
  unsigned int v28; // r9d
  unsigned int v29; // esi
  unsigned int v30; // ebx
  size_t v31; // r14
  size_t v32; // rsi
  unsigned int v33; // r12d
  size_t v34; // rdi
  size_t v35; // rbx
  size_t v36; // rax
  const char *v37; // r9
  size_t v38; // rdx
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  CVersionManagerServer *v41; // rcx
  __int64 v42; // rbx
  struct _RTL_CRITICAL_SECTION *v43; // r15
  HANDLE FileW; // rsi
  signed int v45; // eax
  SIZE_T v46; // r14
  signed int v47; // eax
  signed int v48; // eax
  bool v49; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-A0h] BYREF
  char *v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h]
  char v55[40]; // [rsp+78h] [rbp-88h] BYREF
  char v56[40]; // [rsp+A0h] [rbp-60h] BYREF
  char v57[56]; // [rsp+C8h] [rbp-38h] BYREF
  char String[56]; // [rsp+100h] [rbp+0h] BYREF
  char v59[56]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR pszPath[264]; // [rsp+170h] [rbp+70h] BYREF

  v54 = a1;
  if ( !a3 )
    return 2147942487LL;
  pv = 0;
  v14 = 0;
  NumberOfBytesWritten = 0;
  v15 = 0;
  v53 = 0;
  v16 = 0;
  v52 = 0;
  v17 = 0;
  if ( a2 )
  {
    if ( SysStringLen(a2) > 0x824 )
    {
LABEL_5:
      LocalDirectory = -2147024785;
      goto LABEL_31;
    }
    v20 = CVersionManagerServer::_WideToAnsi(v18, a2, &v53, &v52);
    v16 = v53;
    LocalDirectory = v20;
    if ( v20 < 0 )
      goto LABEL_31;
    v17 = v52;
  }
  v21 = -1;
  do
    ++v21;
  while ( a3[v21] );
  if ( v21 > 0x104 )
    goto LABEL_5;
  LocalDirectory = CVersionManagerServer::_WideToAnsi(0, a3, (char **)&pv, &NumberOfBytesWritten);
  if ( LocalDirectory >= 0 )
  {
    LocalDirectory = CVersionManagerServer::_SqmReasonToString(v22, a9, String);
    if ( LocalDirectory >= 0 )
    {
      if ( a8 )
      {
        if ( a8 == 1 )
        {
          v23 = "Blocked";
          goto LABEL_20;
        }
        if ( a8 == 2 )
        {
          v23 = "Allowed";
          goto LABEL_20;
        }
      }
      v23 = "Unknown";
LABEL_20:
      LocalDirectory = StringCchCopyA(v59, 0x32u, v23);
      if ( LocalDirectory >= 0 )
      {
        v25 = "EPM Compatible";
        if ( !a10 )
          v25 = "Not EPM Compatible";
        LocalDirectory = StringCchCopyA(v57, v24, v25);
        if ( LocalDirectory >= 0 )
        {
          v27 = (unsigned __int16)a4;
          v28 = HIWORD(a4);
          v29 = v26 - 10;
          LocalDirectory = StringCchPrintfA(
                             v56,
                             (unsigned int)(v26 - 10),
                             "%d.%d.%d.%d",
                             v28,
                             v27,
                             HIWORD(a5),
                             (unsigned __int16)a5);
          if ( LocalDirectory >= 0 )
          {
            LocalDirectory = StringCchPrintfA(
                               v55,
                               v29,
                               "%d.%d.%d.%d",
                               HIWORD(a6),
                               (unsigned __int16)a6,
                               HIWORD(a7),
                               (unsigned __int16)a7);
            if ( LocalDirectory >= 0 )
            {
              v30 = v29 + 10;
              v31 = strnlen(String, v29 + 10);
              v32 = strnlen(v59, v29 + 10);
              v33 = v30 - 10;
              v34 = strnlen(v57, v30);
              v35 = strnlen(v56, v30 - 10);
              v36 = strnlen(v55, v33);
              v15 = v32 + v34 + v35 + v36 + v17 + NumberOfBytesWritten + v31 + 9;
              v14 = (char *)CoTaskMemAlloc(v15);
              if ( v14 )
              {
                v37 = (const char *)&Default;
                if ( v16 )
                  v37 = v16;
                LocalDirectory = StringCbPrintfA(
                                   v14,
                                   v15,
                                   "%s,%s,%s,%s,%s,%s,%s\r\n",
                                   v37,
                                   (const char *)pv,
                                   v56,
                                   v55,
                                   v59,
                                   String,
                                   v57);
              }
              else
              {
                LocalDirectory = -2147024882;
              }
            }
          }
        }
      }
    }
  }
LABEL_31:
  CoTaskMemFree(pv);
  CoTaskMemFree(v16);
  if ( LocalDirectory >= 0 )
  {
    if ( v14 )
    {
      if ( v15 )
      {
        LocalDirectory = GetString(SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath, pszPath, 260);
        if ( LocalDirectory >= 0 )
        {
          v38 = -1;
          do
            ++v38;
          while ( pszPath[v38] );
          LocalDirectory = PathCchRemoveFileSpec(pszPath, v38);
          if ( LocalDirectory >= 0 )
          {
            FileAttributesW = GetFileAttributesW(pszPath);
            LastError = GetLastError();
            if ( FileAttributesW == -1 )
            {
              if ( LastError != 2
                || (LocalDirectory = CVersionManagerServer::_CreateLocalDirectory(v41, pszPath), LocalDirectory >= 0) )
              {
LABEL_41:
                LocalDirectory = GetString(SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath, pszPath, 260);
                if ( LocalDirectory >= 0 )
                {
                  v42 = v54;
                  v49 = 0;
                  v43 = (struct _RTL_CRITICAL_SECTION *)(v54 + 1888);
                  EnterCriticalSection((LPCRITICAL_SECTION)(v54 + 1888));
                  pv = (LPVOID)(v42 + 2056);
                  LocalDirectory = MutexUtils::CAutoMutex::Lock((MutexUtils::CAutoMutex *)&pv, &v49);
                  if ( LocalDirectory >= 0 )
                  {
                    FileW = CreateFileW(pszPath, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
                    if ( FileW == (HANDLE)-1LL )
                    {
                      v48 = GetLastError();
                      LocalDirectory = v48;
                      if ( v48 > 0 )
                        LocalDirectory = (unsigned __int16)v48 | 0x80070000;
                    }
                    else
                    {
                      if ( GetLastError() != 183 || v49 || SetFilePointer(FileW, 0, 0, 2u) != -1 )
                        goto LABEL_50;
                      v45 = GetLastError();
                      LocalDirectory = v45;
                      if ( v45 > 0 )
                        LocalDirectory = (unsigned __int16)v45 | 0x80070000;
                      if ( LocalDirectory >= 0 )
                      {
LABEL_50:
                        v46 = v15 - 1;
                        NumberOfBytesWritten = 0;
                        if ( WriteFile(FileW, v14, v46, &NumberOfBytesWritten, 0) )
                        {
                          if ( NumberOfBytesWritten != v46 )
                            LocalDirectory = -2147024867;
                        }
                        else
                        {
                          v47 = GetLastError();
                          LocalDirectory = v47;
                          if ( v47 > 0 )
                            LocalDirectory = (unsigned __int16)v47 | 0x80070000;
                        }
                      }
                      CloseHandle(FileW);
                    }
                  }
                  MutexUtils::CAutoMutex::~CAutoMutex((MutexUtils::CAutoMutex *)&pv);
                  LeaveCriticalSection(v43);
                }
              }
            }
            else
            {
              if ( (FileAttributesW & 0x10) != 0 )
                goto LABEL_41;
              LocalDirectory = -2147024735;
            }
          }
        }
      }
    }
  }
  CoTaskMemFree(v14);
  return (unsigned int)LocalDirectory;
}

```

## disassembly

```asm
0x18009fbd0  push    rbp
0x18009fbd2  push    rbx
0x18009fbd3  push    rsi
0x18009fbd4  push    rdi
0x18009fbd5  push    r12
0x18009fbd7  push    r13
0x18009fbd9  push    r14
0x18009fbdb  push    r15
0x18009fbdd  lea     rbp, [rsp-298h]
0x18009fbe5  sub     rsp, 398h
0x18009fbec  mov     rax, cs:__security_cookie
0x18009fbf3  xor     rax, rsp
0x18009fbf6  mov     [rbp+2D0h+var_50], rax
0x18009fbfd  mov     [rsp+3D0h+var_360], rcx
0x18009fc02  mov     esi, r9d
0x18009fc05  xor     ecx, ecx
0x18009fc07  mov     rdi, r8
0x18009fc0a  mov     rbx, rdx
0x18009fc0d  test    r8, r8
0x18009fc10  jnz     short loc_18009FC1C
0x18009fc12  mov     eax, 80070057h
0x18009fc17  jmp     loc_1800A00CC
0x18009fc1c  mov     [rsp+3D0h+pv], rcx
0x18009fc21  mov     r12, rcx
0x18009fc24  mov     [rsp+3D0h+NumberOfBytesWritten], ecx
0x18009fc28  mov     r14, rcx
0x18009fc2b  mov     [rsp+3D0h+var_368], rcx
0x18009fc30  mov     r15, rcx
0x18009fc33  mov     [rsp+3D0h+var_370], ecx
0x18009fc37  mov     r13d, ecx
0x18009fc3a  test    rbx, rbx
0x18009fc3d  jz      short loc_18009FC7F
0x18009fc3f  mov     rcx, rbx; pbstr
0x18009fc42  call    cs:__imp_SysStringLen
0x18009fc48  cmp     eax, 824h
0x18009fc4d  jbe     short loc_18009FC5B
0x18009fc4f  mov     ebx, 8007006Fh
0x18009fc54  xor     edi, edi
0x18009fc56  jmp     loc_18009FEA9
0x18009fc5b  lea     r9, [rsp+3D0h+var_370]; unsigned int *
0x18009fc60  mov     rdx, rbx; unsigned __int16 *
0x18009fc63  lea     r8, [rsp+3D0h+var_368]; char **
0x18009fc68  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x18009fc6d  mov     r15, [rsp+3D0h+var_368]
0x18009fc72  xor     ecx, ecx; this
0x18009fc74  mov     ebx, eax
0x18009fc76  test    eax, eax
0x18009fc78  js      short loc_18009FC54
0x18009fc7a  mov     r13d, [rsp+3D0h+var_370]
0x18009fc7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009fc83  inc     rax
0x18009fc86  cmp     [rdi+rax*2], cx
0x18009fc8a  jnz     short loc_18009FC83
0x18009fc8c  cmp     rax, 104h
0x18009fc92  ja      short loc_18009FC4F
0x18009fc94  lea     r9, [rsp+3D0h+NumberOfBytesWritten]; unsigned int *
0x18009fc99  mov     rdx, rdi; unsigned __int16 *
0x18009fc9c  lea     r8, [rsp+3D0h+pv]; char **
0x18009fca1  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x18009fca6  xor     edi, edi
0x18009fca8  mov     ebx, eax
0x18009fcaa  test    eax, eax
0x18009fcac  js      loc_18009FEA9
0x18009fcb2  mov     edx, [rbp+2D0h+arg_40]
0x18009fcb8  lea     r8, [rbp+2D0h+String]
0x18009fcbc  call    ?_SqmReasonToString@CVersionManagerServer@@AEAAJW4EXT_SQM_VERSION_REASON@@PEAD_K@Z; CVersionManagerServer::_SqmReasonToString(EXT_SQM_VERSION_REASON,char *,unsigned __int64)
0x18009fcc1  mov     ebx, eax
0x18009fcc3  test    eax, eax
0x18009fcc5  js      loc_18009FEA9
0x18009fccb  mov     ecx, [rbp+2D0h+arg_38]
0x18009fcd1  test    ecx, ecx
0x18009fcd3  jz      short loc_18009FCF1
0x18009fcd5  sub     ecx, 1
0x18009fcd8  jz      short loc_18009FCE8
0x18009fcda  cmp     ecx, 1
0x18009fcdd  jnz     short loc_18009FCF1
0x18009fcdf  lea     r8, aAllowed; "Allowed"
0x18009fce6  jmp     short loc_18009FCF8
0x18009fce8  lea     r8, aBlocked_0; "Blocked"
0x18009fcef  jmp     short loc_18009FCF8
0x18009fcf1  lea     r8, aUnknown; "Unknown"
0x18009fcf8  mov     r10d, 32h ; '2'
0x18009fcfe  lea     rcx, [rbp+2D0h+var_298]; char *
0x18009fd02  mov     edx, r10d; unsigned __int64
0x18009fd05  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18009fd0a  mov     ebx, eax
0x18009fd0c  test    eax, eax
0x18009fd0e  js      loc_18009FEA9
0x18009fd14  cmp     [rbp+2D0h+arg_48], edi
0x18009fd1a  lea     rax, aNotEpmCompatib; "Not EPM Compatible"
0x18009fd21  lea     r8, aEpmCompatible; "EPM Compatible"
0x18009fd28  mov     edx, r10d; unsigned __int64
0x18009fd2b  cmovz   r8, rax; char *
0x18009fd2f  lea     rcx, [rbp+2D0h+var_308]; char *
0x18009fd33  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18009fd38  mov     ebx, eax
0x18009fd3a  test    eax, eax
0x18009fd3c  js      loc_18009FEA9
0x18009fd42  mov     edx, [rbp+2D0h+arg_20]
0x18009fd48  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18009fd4f  movzx   ecx, dx
0x18009fd52  movzx   eax, si
0x18009fd55  mov     dword ptr [rsp+3D0h+hTemplateFile], ecx
0x18009fd59  lea     rcx, [rbp+2D0h+var_330]; char *
0x18009fd5d  shr     esi, 10h
0x18009fd60  shr     edx, 10h
0x18009fd63  mov     r9d, esi
0x18009fd66  mov     [rsp+3D0h+dwFlagsAndAttributes], edx
0x18009fd6a  lea     esi, [r10-0Ah]
0x18009fd6e  mov     edx, esi; unsigned __int64
0x18009fd70  mov     [rsp+3D0h+dwCreationDisposition], eax
0x18009fd74  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009fd79  mov     ebx, eax
0x18009fd7b  test    eax, eax
0x18009fd7d  js      loc_18009FEA9
0x18009fd83  mov     edx, [rbp+2D0h+arg_30]
0x18009fd89  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18009fd90  mov     r9d, [rbp+2D0h+arg_28]
0x18009fd97  movzx   ecx, dx
0x18009fd9a  mov     dword ptr [rsp+3D0h+hTemplateFile], ecx
0x18009fd9e  lea     rcx, [rsp+3D0h+var_358]; char *
0x18009fda3  shr     edx, 10h
0x18009fda6  mov     [rsp+3D0h+dwFlagsAndAttributes], edx
0x18009fdaa  mov     edx, esi; unsigned __int64
0x18009fdac  movzx   eax, r9w
0x18009fdb0  shr     r9d, 10h
0x18009fdb4  mov     [rsp+3D0h+dwCreationDisposition], eax
0x18009fdb8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009fdbd  mov     ebx, eax
0x18009fdbf  test    eax, eax
0x18009fdc1  js      loc_18009FEA9
0x18009fdc7  lea     ebx, [rsi+0Ah]
0x18009fdca  mov     edx, ebx; MaxCount
0x18009fdcc  lea     rcx, [rbp+2D0h+String]; String
0x18009fdd0  call    cs:__imp_strnlen
0x18009fdd6  mov     edx, ebx; MaxCount
0x18009fdd8  lea     rcx, [rbp+2D0h+var_298]; String
0x18009fddc  mov     r14, rax
0x18009fddf  call    cs:__imp_strnlen
0x18009fde5  mov     edx, ebx; MaxCount
0x18009fde7  lea     rcx, [rbp+2D0h+var_308]; String
0x18009fdeb  mov     rsi, rax
0x18009fdee  call    cs:__imp_strnlen
0x18009fdf4  lea     r12d, [rbx-0Ah]
0x18009fdf8  mov     rdi, rax
0x18009fdfb  mov     edx, r12d; MaxCount
0x18009fdfe  lea     rcx, [rbp+2D0h+var_330]; String
0x18009fe02  call    cs:__imp_strnlen
0x18009fe08  mov     edx, r12d; MaxCount
0x18009fe0b  lea     rcx, [rsp+3D0h+var_358]; String
0x18009fe10  mov     rbx, rax
0x18009fe13  call    cs:__imp_strnlen
0x18009fe19  mov     r8d, [rsp+3D0h+NumberOfBytesWritten]
0x18009fe1e  add     r14, 9
0x18009fe22  add     r8d, r13d
0x18009fe25  lea     rcx, [rbx+rax]
0x18009fe29  add     r8, rcx
0x18009fe2c  add     r8, rdi
0x18009fe2f  add     r8, rsi
0x18009fe32  add     r14, r8
0x18009fe35  mov     rcx, r14; cb
0x18009fe38  call    cs:__imp_CoTaskMemAlloc
0x18009fe3e  xor     edi, edi
0x18009fe40  mov     r12, rax
0x18009fe43  test    rax, rax
0x18009fe46  jnz     short loc_18009FE4F
0x18009fe48  mov     ebx, 8007000Eh
0x18009fe4d  jmp     short loc_18009FEA9
0x18009fe4f  lea     rax, [rbp+2D0h+var_308]
0x18009fe53  test    r15, r15
0x18009fe56  mov     [rsp+3D0h+var_388], rax
0x18009fe5b  lea     r9, Default
0x18009fe62  lea     rax, [rbp+2D0h+String]
0x18009fe66  cmovnz  r9, r15
0x18009fe6a  mov     [rsp+3D0h+var_390], rax
0x18009fe6f  lea     r8, aSSSSSSS; "%s,%s,%s,%s,%s,%s,%s\r\n"
0x18009fe76  lea     rax, [rbp+2D0h+var_298]
0x18009fe7a  mov     rdx, r14; unsigned __int64
0x18009fe7d  mov     [rsp+3D0h+var_398], rax
0x18009fe82  mov     rcx, r12; char *
0x18009fe85  lea     rax, [rsp+3D0h+var_358]
0x18009fe8a  mov     [rsp+3D0h+hTemplateFile], rax
0x18009fe8f  lea     rax, [rbp+2D0h+var_330]
0x18009fe93  mov     qword ptr [rsp+3D0h+dwFlagsAndAttributes], rax
0x18009fe98  mov     rax, [rsp+3D0h+pv]
0x18009fe9d  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax
0x18009fea2  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18009fea7  mov     ebx, eax
0x18009fea9  mov     rcx, [rsp+3D0h+pv]; pv
0x18009feae  call    cs:__imp_CoTaskMemFree
0x18009feb4  mov     rcx, r15; pv
0x18009feb7  call    cs:__imp_CoTaskMemFree
0x18009febd  test    ebx, ebx
0x18009febf  js      loc_1800A00C1
0x18009fec5  test    r12, r12
0x18009fec8  jz      loc_1800A00C1
0x18009fece  test    r14, r14
0x18009fed1  jz      loc_1800A00C1
0x18009fed7  mov     rcx, cs:?IEVALUE_urlmon_ExtVerAuditModeFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath
0x18009fede  lea     rdx, [rbp+2D0h+pszPath]
0x18009fee2  mov     r8d, 104h
0x18009fee8  call    GetString
0x18009feed  mov     ebx, eax
0x18009feef  test    eax, eax
0x18009fef1  js      loc_1800A00C1
0x18009fef7  lea     rax, [rbp+2D0h+pszPath]
0x18009fefb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009feff  inc     rdx; cchPath
0x18009ff02  cmp     [rax+rdx*2], di
0x18009ff06  jnz     short loc_18009FEFF
0x18009ff08  lea     rcx, [rbp+2D0h+pszPath]; pszPath
0x18009ff0c  call    cs:__imp_PathCchRemoveFileSpec
0x18009ff12  mov     ebx, eax
0x18009ff14  test    eax, eax
0x18009ff16  js      loc_1800A00C1
0x18009ff1c  lea     rcx, [rbp+2D0h+pszPath]; lpFileName
0x18009ff20  call    cs:__imp_GetFileAttributesW
0x18009ff26  mov     ebx, eax
0x18009ff28  call    cs:__imp_GetLastError
0x18009ff2e  or      r13d, 0FFFFFFFFh
0x18009ff32  cmp     ebx, r13d
0x18009ff35  jnz     loc_1800A006D
0x18009ff3b  cmp     eax, 2
0x18009ff3e  jnz     short loc_18009FF53
0x18009ff40  lea     rdx, [rbp+2D0h+pszPath]; unsigned __int16 *
0x18009ff44  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x18009ff49  mov     ebx, eax
0x18009ff4b  test    eax, eax
0x18009ff4d  js      loc_1800A00C1
0x18009ff53  mov     rcx, cs:?IEVALUE_urlmon_ExtVerAuditModeFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerAuditModeFilePath
0x18009ff5a  lea     rdx, [rbp+2D0h+pszPath]
0x18009ff5e  mov     r8d, 104h
0x18009ff64  call    GetString
0x18009ff69  mov     ebx, eax
0x18009ff6b  test    eax, eax
0x18009ff6d  js      loc_1800A00C1
0x18009ff73  mov     rbx, [rsp+3D0h+var_360]
0x18009ff78  mov     [rsp+3D0h+var_380], dil
0x18009ff7d  lea     r15, [rbx+760h]
0x18009ff84  mov     rcx, r15; lpCriticalSection
0x18009ff87  call    cs:__imp_EnterCriticalSection
0x18009ff8d  lea     rax, [rbx+808h]
0x18009ff94  lea     rdx, [rsp+3D0h+var_380]; bool *
0x18009ff99  mov     [rsp+3D0h+pv], rax
0x18009ff9e  lea     rcx, [rsp+3D0h+pv]; this
0x18009ffa3  call    ?Lock@CAutoMutex@MutexUtils@@QEAAJPEA_N@Z; MutexUtils::CAutoMutex::Lock(bool *)
0x18009ffa8  mov     ebx, eax
0x18009ffaa  test    eax, eax
0x18009ffac  js      loc_1800A00AE
0x18009ffb2  xor     r9d, r9d; lpSecurityAttributes
0x18009ffb5  mov     [rsp+3D0h+hTemplateFile], rdi; hTemplateFile
0x18009ffba  mov     [rsp+3D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009ffc2  lea     rcx, [rbp+2D0h+pszPath]; lpFileName
0x18009ffc6  mov     edx, 40000000h; dwDesiredAccess
0x18009ffcb  mov     [rsp+3D0h+dwCreationDisposition], 4; dwCreationDisposition
0x18009ffd3  lea     r8d, [r9+3]; dwShareMode
0x18009ffd7  call    cs:__imp_CreateFileW
0x18009ffdd  mov     rsi, rax
0x18009ffe0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009ffe4  jz      loc_1800A0099
0x18009ffea  call    cs:__imp_GetLastError
0x18009fff0  mov     edi, 80070000h
0x18009fff5  cmp     eax, 0B7h
0x18009fffa  jnz     short loc_1800A0031
0x18009fffc  cmp     [rsp+3D0h+var_380], 0
0x1800a0001  jnz     short loc_1800A0031
0x1800a0003  mov     r9d, 2; dwMoveMethod
0x1800a0009  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a000c  xor     edx, edx; lDistanceToMove
0x1800a000e  mov     rcx, rsi; hFile
0x1800a0011  call    cs:__imp_SetFilePointer
0x1800a0017  cmp     eax, r13d
0x1800a001a  jnz     short loc_1800A0031
0x1800a001c  call    cs:__imp_GetLastError
0x1800a0022  mov     ebx, eax
0x1800a0024  test    eax, eax
0x1800a0026  jle     short loc_1800A002D
0x1800a0028  movzx   ebx, ax
0x1800a002b  or      ebx, edi
0x1800a002d  test    ebx, ebx
0x1800a002f  js      short loc_1800A008E
0x1800a0031  dec     r14
0x1800a0034  mov     [rsp+3D0h+NumberOfBytesWritten], 0
0x1800a003c  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800a003f  mov     qword ptr [rsp+3D0h+dwCreationDisposition], 0; lpOverlapped
0x1800a0048  lea     r9, [rsp+3D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a004d  mov     rdx, r12; lpBuffer
0x1800a0050  mov     rcx, rsi; hFile
0x1800a0053  call    cs:__imp_WriteFile
0x1800a0059  test    eax, eax
0x1800a005b  jz      short loc_1800A007D
0x1800a005d  mov     eax, [rsp+3D0h+NumberOfBytesWritten]
0x1800a0061  cmp     rax, r14
0x1800a0064  jz      short loc_1800A008E
0x1800a0066  mov     ebx, 8007001Dh
0x1800a006b  jmp     short loc_1800A008E
0x1800a006d  test    bl, 10h
0x1800a0070  jnz     loc_18009FF53
0x1800a0076  mov     ebx, 800700A1h
0x1800a007b  jmp     short loc_1800A00C1
  ... truncated ...
```
