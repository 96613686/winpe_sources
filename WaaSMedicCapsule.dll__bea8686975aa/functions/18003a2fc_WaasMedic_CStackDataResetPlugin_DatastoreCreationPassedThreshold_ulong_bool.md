# WaasMedic::CStackDataResetPlugin::DatastoreCreationPassedThreshold(ulong,bool &)

- ea: `0x18003a2fc`
- end: `0x18003a4ee`
- name: `?DatastoreCreationPassedThreshold@CStackDataResetPlugin@WaasMedic@@AEAAJKAEA_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(WaasMedic::CStackDataResetPlugin *__hidden this, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18003afc8`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a34`
- `0x180009a54`
- `0x18000a5d0`
- `0x18000b308`
- `0x1800250e0`
- `0x180030954`
- `0x18003a2fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a394`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a394`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a386`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a386`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a493`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a493`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18003a40d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18003a40d`

## string_xrefs

- `0x18003a368`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003a3d8`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003a44d`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`

## pseudocode

```c
__int64 __fastcall WaasMedic::CStackDataResetPlugin::DatastoreCreationPassedThreshold(
        WaasMedic::CStackDataResetPlugin *this,
        unsigned int a2,
        bool *a3)
{
  unsigned __int16 **v5; // r8
  int v6; // eax
  unsigned int v7; // edi
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  int v11; // eax
  const char *v12; // r9
  struct _FILETIME v13; // rdi
  int LastError; // esi
  HANDLE v15; // rax
  HANDLE v16; // rax
  int v17; // [rsp+20h] [rbp-E0h]
  const char *v18; // [rsp+28h] [rbp-D8h]
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a3 = 0;
  memset_0(FileName, 0, 0x208u);
  lpMem = 0;
  v6 = WaasMedic::SafeExpandEnvironmentString(
         L"%windir%\\SoftwareDistribution\\DataStore",
         (const unsigned __int16 *)&lpMem,
         v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)(unsigned int)v6,
      v17);
    v8 = lpMem;
LABEL_3:
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    return v7;
  }
  v8 = lpMem;
  v11 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", lpMem);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)(unsigned int)v11,
      (int)L"DataStore.edb");
    goto LABEL_3;
  }
  v23 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
  {
    v13 = *(struct _FILETIME *)((char *)FileInformation + 4);
  }
  else
  {
    v13 = 0;
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x239,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v12);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
        (const char *)(unsigned int)LastError,
        (int)"Failed to get creation time of Datastore.edb",
        v18);
      if ( v8 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v8);
      }
      return (unsigned int)LastError;
    }
  }
  SystemTimeAsFileTime = 0;
  v19 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *a3 = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v13, SystemTimeAsFileTime, &v19) >= a2;
  if ( v8 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18003a2fc  push    rbp
0x18003a2fe  push    rbx
0x18003a2ff  push    rsi
0x18003a300  push    rdi
0x18003a301  push    r14
0x18003a303  push    r15
0x18003a305  lea     rbp, [rsp-198h]
0x18003a30d  sub     rsp, 298h
0x18003a314  mov     rax, cs:__security_cookie
0x18003a31b  xor     rax, rsp
0x18003a31e  mov     [rbp+1C0h+var_40], rax
0x18003a325  mov     r14, r8
0x18003a328  mov     byte ptr [r8], 0
0x18003a32c  mov     r15d, edx
0x18003a32f  lea     rcx, [rsp+2C0h+FileName]; void *
0x18003a334  xor     edx, edx; Val
0x18003a336  mov     r8d, 208h; Size
0x18003a33c  call    memset_0
0x18003a341  lea     rdx, [rsp+2C0h+lpMem]; unsigned __int16 *
0x18003a346  mov     [rsp+2C0h+lpMem], 0
0x18003a34f  lea     rcx, aWindirSoftware_0; "%windir%\\SoftwareDistribution\\DataSto"...
0x18003a356  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x18003a35b  mov     edi, eax
0x18003a35d  test    eax, eax
0x18003a35f  jns     short loc_18003A3A1
0x18003a361  mov     rcx, [rbp+1C8h]; this
0x18003a368  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a36f  mov     r9d, eax; char *
0x18003a372  mov     edx, 1BDh; void *
0x18003a377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a37c  mov     rbx, [rsp+2C0h+lpMem]
0x18003a381  test    rbx, rbx
0x18003a384  jz      short loc_18003A39A
0x18003a386  call    cs:__imp_GetProcessHeap
0x18003a38c  mov     r8, rbx; lpMem
0x18003a38f  xor     edx, edx; dwFlags
0x18003a391  mov     rcx, rax; hHeap
0x18003a394  call    cs:__imp_HeapFree
0x18003a39a  mov     eax, edi
0x18003a39c  jmp     loc_18003A4CF
0x18003a3a1  mov     rbx, [rsp+2C0h+lpMem]
0x18003a3a6  lea     rax, aDatastoreEdb; "DataStore.edb"
0x18003a3ad  mov     r9, rbx
0x18003a3b0  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18003a3b5  lea     r8, aSS; "%s\\%s"
0x18003a3bc  mov     edx, 104h; unsigned __int64
0x18003a3c1  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x18003a3c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a3cb  mov     edi, eax
0x18003a3cd  test    eax, eax
0x18003a3cf  jns     short loc_18003A3EE
0x18003a3d1  mov     rcx, [rbp+1C8h]; this
0x18003a3d8  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a3df  mov     r9d, eax; char *
0x18003a3e2  mov     edx, 1BFh; void *
0x18003a3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a3ec  jmp     short loc_18003A381
0x18003a3ee  xorps   xmm0, xmm0
0x18003a3f1  lea     r8, [rsp+2C0h+FileInformation]; lpFileInformation
0x18003a3f6  xor     eax, eax
0x18003a3f8  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18003a3fd  xor     edx, edx; fInfoLevelId
0x18003a3ff  mov     [rsp+2C0h+var_258], eax
0x18003a403  movups  [rsp+2C0h+FileInformation], xmm0
0x18003a408  movups  [rsp+2C0h+var_268], xmm0
0x18003a40d  call    cs:__imp_GetFileAttributesExW
0x18003a413  test    eax, eax
0x18003a415  jnz     short loc_18003A47B
0x18003a417  mov     rcx, [rbp+1C8h]; this
0x18003a41e  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003a425  mov     edx, 239h; void *
0x18003a42a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a42f  xor     edi, edi
0x18003a431  mov     esi, eax
0x18003a433  test    eax, eax
0x18003a435  jns     short loc_18003A480
0x18003a437  mov     rcx, [rbp+1C8h]; this
0x18003a43e  lea     rax, aFailedToGetCre; "Failed to get creation time of Datastor"...
0x18003a445  mov     r9d, esi; char *
0x18003a448  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18003a44d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003a454  mov     edx, 1C2h; void *
0x18003a459  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a45e  test    rbx, rbx
0x18003a461  jz      short loc_18003A477
0x18003a463  call    cs:__imp_GetProcessHeap
0x18003a469  mov     r8, rbx; lpMem
0x18003a46c  xor     edx, edx; dwFlags
0x18003a46e  mov     rcx, rax; hHeap
0x18003a471  call    cs:__imp_HeapFree
0x18003a477  mov     eax, esi
0x18003a479  jmp     short loc_18003A4CF
0x18003a47b  mov     rdi, qword ptr [rsp+2C0h+FileInformation+4]
0x18003a480  lea     rcx, [rsp+2C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003a485  mov     qword ptr [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003a48e  mov     [rsp+2C0h+var_290], 0
0x18003a493  call    cs:__imp_GetSystemTimeAsFileTime
0x18003a499  mov     rdx, qword ptr [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18003a49e  lea     r8, [rsp+2C0h+var_290]; bool *
0x18003a4a3  mov     rcx, rdi; struct _FILETIME
0x18003a4a6  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18003a4ab  cmp     eax, r15d
0x18003a4ae  setnb   al
0x18003a4b1  mov     [r14], al
0x18003a4b4  test    rbx, rbx
0x18003a4b7  jz      short loc_18003A4CD
0x18003a4b9  call    cs:__imp_GetProcessHeap
0x18003a4bf  mov     r8, rbx; lpMem
0x18003a4c2  xor     edx, edx; dwFlags
0x18003a4c4  mov     rcx, rax; hHeap
0x18003a4c7  call    cs:__imp_HeapFree
0x18003a4cd  xor     eax, eax
0x18003a4cf  mov     rcx, [rbp+1C0h+var_40]
0x18003a4d6  xor     rcx, rsp; StackCookie
0x18003a4d9  call    __security_check_cookie
0x18003a4de  add     rsp, 298h
0x18003a4e5  pop     r15
0x18003a4e7  pop     r14
0x18003a4e9  pop     rdi
0x18003a4ea  pop     rsi
0x18003a4eb  pop     rbx
0x18003a4ec  pop     rbp
0x18003a4ed  retn
```
