# MosStorageGetTotalMapDataInBytes(unsigned __int64 *)

- ea: `0x180009220`
- end: `0x18000935c`
- name: `?MosStorageGetTotalMapDataInBytes@@YAJPEA_K@Z`
- size: `316`
- prototype: `int __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009cc0`

## callees

- `0x180001c80`
- `0x18000733c`
- `0x180009220`
- `0x18000d260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000928f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000929a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000928f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000929a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009279`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009279`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092c4`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092f8`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092c4`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092f8`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009260`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009324`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009260`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009324`

## string_xrefs

- `0x1800092ec`: `DirectorySize`
- `0x18000931b`: `DirectorySize`

## pseudocode

```c
int __fastcall MosStorageGetTotalMapDataInBytes(unsigned __int64 *a1)
{
  int CachedCurrentMapDataDirectory; // eax
  int v3; // r8d
  DWORD FileAttributesW; // eax
  int (__high *v6)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *); // r8
  signed int LastError; // eax
  int v8; // eax
  char v9; // cl
  int v10; // r8d
  unsigned __int64 v11; // [rsp+20h] [rbp-238h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  CachedCurrentMapDataDirectory = GetCachedCurrentMapDataDirectory((__int16 *)FileName, 0x104u);
  if ( CachedCurrentMapDataDirectory < 0 )
  {
    v3 = 560;
    return ZTraceReportPropagationNoThis(CachedCurrentMapDataDirectory, "MosStorageGetTotalMapDataInBytes", v3);
  }
  v11 = 0;
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
    {
      v9 = 1;
      goto LABEL_16;
    }
LABEL_15:
    v9 = 0;
    goto LABEL_16;
  }
  if ( GetLastError() == 2 || GetLastError() == 3 )
    goto LABEL_15;
  LastError = GetLastError();
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    LastError = -2143748092;
  }
  v8 = ZTraceReportOriginationNoThis(LastError, "FolderExists", 68);
  v9 = 0;
  if ( v8 < 0 )
  {
    v10 = 810;
    goto LABEL_20;
  }
LABEL_16:
  if ( !v9 )
  {
    CachedCurrentMapDataDirectory = ZTraceReportOriginationNoThis(-2147024893, "DirectorySize", 811);
    goto LABEL_21;
  }
  v8 = RecursiveScanDirectory(FileName, 0, v6, &v11);
  if ( v8 >= 0 )
  {
    *a1 = v11;
    return 0;
  }
  v10 = 813;
LABEL_20:
  CachedCurrentMapDataDirectory = ZTraceReportPropagationNoThis(v8, "DirectorySize", v10);
LABEL_21:
  if ( CachedCurrentMapDataDirectory < 0 )
  {
    v3 = 561;
    return ZTraceReportPropagationNoThis(CachedCurrentMapDataDirectory, "MosStorageGetTotalMapDataInBytes", v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180009220  push    rbx
0x180009222  sub     rsp, 250h
0x180009229  mov     rax, cs:__security_cookie
0x180009230  xor     rax, rsp
0x180009233  mov     [rsp+258h+var_18], rax
0x18000923b  mov     rbx, rcx
0x18000923e  mov     edx, 104h
0x180009243  lea     rcx, [rsp+258h+FileName]
0x180009248  call    GetCachedCurrentMapDataDirectory
0x18000924d  test    eax, eax
0x18000924f  jns     short loc_18000926B
0x180009251  mov     r8d, 230h
0x180009257  lea     rdx, aMosstoragegett_0; "MosStorageGetTotalMapDataInBytes"
0x18000925e  mov     ecx, eax
0x180009260  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009266  jmp     loc_180009343
0x18000926b  lea     rcx, [rsp+258h+FileName]; lpFileName
0x180009270  mov     [rsp+258h+var_238], 0
0x180009279  call    cs:__imp_GetFileAttributesW
0x18000927f  cmp     eax, 0FFFFFFFFh
0x180009282  jnz     short loc_1800092D8
0x180009284  call    cs:__imp_GetLastError
0x18000928a  cmp     eax, 2
0x18000928d  jz      short loc_1800092E0
0x18000928f  call    cs:__imp_GetLastError
0x180009295  cmp     eax, 3
0x180009298  jz      short loc_1800092E0
0x18000929a  call    cs:__imp_GetLastError
0x1800092a0  test    eax, eax
0x1800092a2  jz      short loc_1800092B0
0x1800092a4  jle     short loc_1800092B5
0x1800092a6  movzx   eax, ax
0x1800092a9  or      eax, 80070000h
0x1800092ae  jmp     short loc_1800092B5
0x1800092b0  mov     eax, 80390004h
0x1800092b5  mov     r8d, 44h ; 'D'
0x1800092bb  lea     rdx, aFolderexists; "FolderExists"
0x1800092c2  mov     ecx, eax
0x1800092c4  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800092ca  xor     cl, cl
0x1800092cc  test    eax, eax
0x1800092ce  jns     short loc_1800092E2
0x1800092d0  mov     r8d, 32Ah
0x1800092d6  jmp     short loc_18000931B
0x1800092d8  test    al, 10h
0x1800092da  jz      short loc_1800092E0
0x1800092dc  mov     cl, 1
0x1800092de  jmp     short loc_1800092E2
0x1800092e0  xor     cl, cl
0x1800092e2  test    cl, cl
0x1800092e4  jnz     short loc_180009300
0x1800092e6  mov     r8d, 32Bh
0x1800092ec  lea     rdx, aDirectorysize; "DirectorySize"
0x1800092f3  mov     ecx, 80070003h
0x1800092f8  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800092fe  jmp     short loc_18000932A
0x180009300  lea     r9, [rsp+258h+var_238]; void *
0x180009305  xor     edx, edx; int
0x180009307  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x18000930c  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x180009311  test    eax, eax
0x180009313  jns     short loc_180009339
0x180009315  mov     r8d, 32Dh
0x18000931b  lea     rdx, aDirectorysize; "DirectorySize"
0x180009322  mov     ecx, eax
0x180009324  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000932a  test    eax, eax
0x18000932c  jns     short loc_180009341
0x18000932e  mov     r8d, 231h
0x180009334  jmp     loc_180009257
0x180009339  mov     rax, [rsp+258h+var_238]
0x18000933e  mov     [rbx], rax
0x180009341  xor     eax, eax
0x180009343  mov     rcx, [rsp+258h+var_18]
0x18000934b  xor     rcx, rsp; StackCookie
0x18000934e  call    __security_check_cookie
0x180009353  add     rsp, 250h
0x18000935a  pop     rbx
0x18000935b  retn
```
