# WaasMedic::MiscUtil::DeleteOldDataStoresIfExists(void)

- ea: `0x18002589c`
- end: `0x180025ada`
- name: `?DeleteOldDataStoresIfExists@MiscUtil@WaasMedic@@SAJXZ`
- size: `574`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180026830`
- `0x180054390`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x18000a5d0`
- `0x1800250e0`
- `0x18002543c`
- `0x18002589c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002593a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800259e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ab7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002593a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800259e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002592c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800259d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025aa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002592c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800259d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a50`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180025a9e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180025a9e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180025a44`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180025a44`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025a32`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025a32`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800259b1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800259b1`

## string_xrefs

- `0x1800259c0`: `Unable to find .old data stores, nothing to delete.`
- `0x180025a6f`: `Unable to delete the file: %s hr = 0x%08x.`

## pseudocode

```c
__int64 WaasMedic::MiscUtil::DeleteOldDataStoresIfExists(void)
{
  unsigned __int16 **v0; // r8
  int v1; // eax
  unsigned int v2; // edi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  int v6; // eax
  HANDLE FirstFileW; // rdi
  HANDLE v8; // rax
  int v9; // eax
  unsigned int v10; // esi
  signed int LastError; // eax
  HANDLE v12; // rax
  int v13; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v16[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR FileName[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(FileName, 0, 0x208u);
  lpMem[0] = 0;
  v1 = WaasMedic::SafeExpandEnvironmentString(
         L"%windir%\\SoftwareDistribution\\DataStore",
         (const unsigned __int16 *)lpMem,
         v0);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C4,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v1,
      v13);
    v3 = lpMem[0];
LABEL_3:
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    return v2;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = lpMem[0];
  v6 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", lpMem[0]);
  v2 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v6,
      (int)L"*.old");
    goto LABEL_3;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LogLevelW(4u, L"Unable to find .old data stores, nothing to delete.");
    if ( v3 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v3);
    }
    return 0;
  }
  else
  {
    memset_0(v16, 0, 0x208u);
    while ( 1 )
    {
      v9 = StringCchPrintfW(v16, 0x104u, L"%s\\%s", v3, FindFileData.cFileName);
      v10 = v9;
      if ( v9 < 0 )
      {
        LogLevelW(2u, L"Unable to concatenate string. hr = 0x%08x", (unsigned int)v9);
        goto LABEL_21;
      }
      if ( !DeleteFileW(v16) )
        break;
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
        goto LABEL_21;
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Unable to delete the file: %s hr = 0x%08x.", v16, v10);
LABEL_21:
    if ( FirstFileW )
      FindClose(FirstFileW);
    if ( v3 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v3);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x18002589c  push    rbp
0x18002589e  push    rbx
0x18002589f  push    rsi
0x1800258a0  push    rdi
0x1800258a1  lea     rbp, [rsp-5C8h]
0x1800258a9  sub     rsp, 6C8h
0x1800258b0  mov     rax, cs:__security_cookie
0x1800258b7  xor     rax, rsp
0x1800258ba  mov     [rbp+5E0h+var_30], rax
0x1800258c1  mov     ebx, 250h
0x1800258c6  lea     rcx, [rsp+6E0h+FindFileData]; void *
0x1800258cb  mov     r8d, ebx; Size
0x1800258ce  xor     edx, edx; Val
0x1800258d0  call    memset_0
0x1800258d5  lea     esi, [rbx-48h]
0x1800258d8  xor     edx, edx; Val
0x1800258da  mov     r8d, esi; Size
0x1800258dd  lea     rcx, [rbp+5E0h+FileName]; void *
0x1800258e4  call    memset_0
0x1800258e9  lea     rdx, [rsp+6E0h+lpMem]; unsigned __int16 *
0x1800258ee  mov     [rsp+6E0h+lpMem], 0
0x1800258f7  lea     rcx, aWindirSoftware_0; "%windir%\\SoftwareDistribution\\DataSto"...
0x1800258fe  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x180025903  mov     edi, eax
0x180025905  test    eax, eax
0x180025907  jns     short loc_180025947
0x180025909  mov     rcx, [rbp+5E8h]; this
0x180025910  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180025917  mov     r9d, eax; char *
0x18002591a  lea     edx, [rbx+74h]; void *
0x18002591d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025922  mov     rbx, [rsp+6E0h+lpMem]
0x180025927  test    rbx, rbx
0x18002592a  jz      short loc_180025940
0x18002592c  call    cs:__imp_GetProcessHeap
0x180025932  mov     r8, rbx; lpMem
0x180025935  xor     edx, edx; dwFlags
0x180025937  mov     rcx, rax; hHeap
0x18002593a  call    cs:__imp_HeapFree
0x180025940  mov     eax, edi
0x180025942  jmp     loc_180025ABF
0x180025947  mov     r8, rbx; Size
0x18002594a  lea     rcx, [rsp+6E0h+FindFileData]; void *
0x18002594f  xor     edx, edx; Val
0x180025951  call    memset_0
0x180025956  mov     rbx, [rsp+6E0h+lpMem]
0x18002595b  lea     rax, aOld; "*.old"
0x180025962  mov     r9, rbx
0x180025965  mov     qword ptr [rsp+6E0h+var_6C0], rax; int
0x18002596a  lea     r8, aSS; "%s\\%s"
0x180025971  mov     edx, 104h; unsigned __int64
0x180025976  lea     rcx, [rbp+5E0h+FileName]; unsigned __int16 *
0x18002597d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025982  mov     edi, eax
0x180025984  test    eax, eax
0x180025986  jns     short loc_1800259A5
0x180025988  mov     rcx, [rbp+5E8h]; this
0x18002598f  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180025996  mov     r9d, eax; char *
0x180025999  mov     edx, 2C7h; void *
0x18002599e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259a3  jmp     short loc_180025927
0x1800259a5  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x1800259aa  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x1800259b1  call    cs:__imp_FindFirstFileW
0x1800259b7  mov     rdi, rax
0x1800259ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800259be  jnz     short loc_1800259EF
0x1800259c0  lea     rdx, aUnableToFindOl; "Unable to find .old data stores, nothin"...
0x1800259c7  lea     ecx, [rax+5]; unsigned __int8
0x1800259ca  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800259cf  test    rbx, rbx
0x1800259d2  jz      short loc_1800259E8
0x1800259d4  call    cs:__imp_GetProcessHeap
0x1800259da  mov     r8, rbx; lpMem
0x1800259dd  xor     edx, edx; dwFlags
0x1800259df  mov     rcx, rax; hHeap
0x1800259e2  call    cs:__imp_HeapFree
0x1800259e8  xor     eax, eax
0x1800259ea  jmp     loc_180025ABF
0x1800259ef  mov     r8, rsi; Size
0x1800259f2  lea     rcx, [rbp+5E0h+var_450]; void *
0x1800259f9  xor     edx, edx; Val
0x1800259fb  call    memset_0
0x180025a00  lea     rax, [rsp+6E0h+FindFileData.cFileName]
0x180025a05  mov     r9, rbx
0x180025a08  lea     r8, aSS; "%s\\%s"
0x180025a0f  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x180025a14  mov     edx, 104h; unsigned __int64
0x180025a19  lea     rcx, [rbp+5E0h+var_450]; unsigned __int16 *
0x180025a20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025a25  mov     esi, eax
0x180025a27  test    eax, eax
0x180025a29  js      short loc_180025A82
0x180025a2b  lea     rcx, [rbp+5E0h+var_450]; lpFileName
0x180025a32  call    cs:__imp_DeleteFileW
0x180025a38  test    eax, eax
0x180025a3a  jz      short loc_180025A50
0x180025a3c  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x180025a41  mov     rcx, rdi; hFindFile
0x180025a44  call    cs:__imp_FindNextFileW
0x180025a4a  test    eax, eax
0x180025a4c  jnz     short loc_180025A00
0x180025a4e  jmp     short loc_180025A96
0x180025a50  call    cs:__imp_GetLastError
0x180025a56  mov     esi, eax
0x180025a58  test    eax, eax
0x180025a5a  jle     short loc_180025A65
0x180025a5c  movzx   esi, ax
0x180025a5f  or      esi, 80070000h
0x180025a65  mov     r9d, esi
0x180025a68  lea     r8, [rbp+5E0h+var_450]
0x180025a6f  lea     rdx, aUnableToDelete_0; "Unable to delete the file: %s hr = 0x%0"...
0x180025a76  mov     ecx, 2; unsigned __int8
0x180025a7b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025a80  jmp     short loc_180025A96
0x180025a82  mov     r8d, eax
0x180025a85  lea     rdx, aUnableToConcat; "Unable to concatenate string. hr = 0x%0"...
0x180025a8c  mov     ecx, 2; unsigned __int8
0x180025a91  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025a96  test    rdi, rdi
0x180025a99  jz      short loc_180025AA4
0x180025a9b  mov     rcx, rdi; hFindFile
0x180025a9e  call    cs:__imp_FindClose
0x180025aa4  test    rbx, rbx
0x180025aa7  jz      short loc_180025ABD
0x180025aa9  call    cs:__imp_GetProcessHeap
0x180025aaf  mov     r8, rbx; lpMem
0x180025ab2  xor     edx, edx; dwFlags
0x180025ab4  mov     rcx, rax; hHeap
0x180025ab7  call    cs:__imp_HeapFree
0x180025abd  mov     eax, esi
0x180025abf  mov     rcx, [rbp+5E0h+var_30]
0x180025ac6  xor     rcx, rsp; StackCookie
0x180025ac9  call    __security_check_cookie
0x180025ace  add     rsp, 6C8h
0x180025ad5  pop     rdi
0x180025ad6  pop     rsi
0x180025ad7  pop     rbx
0x180025ad8  pop     rbp
0x180025ad9  retn
```
