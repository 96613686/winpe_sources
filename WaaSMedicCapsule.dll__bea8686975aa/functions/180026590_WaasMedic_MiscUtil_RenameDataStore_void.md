# WaasMedic::MiscUtil::RenameDataStore(void)

- ea: `0x180026590`
- end: `0x180026829`
- name: `?RenameDataStore@MiscUtil@WaasMedic@@SAJXZ`
- size: `665`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180026830`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x18000a5d0`
- `0x1800250e0`
- `0x180026590`
- `0x180026920`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026650`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026650`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002674c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800267af`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002674c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800267af`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180026762`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800267c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180026762`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800267c7`

## string_xrefs

- `0x18002677d`: `Unable to rename data store file %ws to %ws.`
- `0x1800267e2`: `Unable to rename data store flush map file %ws to %ws.`

## pseudocode

```c
__int64 WaasMedic::MiscUtil::RenameDataStore(void)
{
  unsigned __int16 **v0; // r8
  int v1; // eax
  int v2; // edi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v6; // rdx
  int LastErrorMsg; // eax
  HANDLE v8; // rax
  int v9; // [rsp+20h] [rbp-E0h]
  const wchar_t *v10; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR NewFileName[264]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR v15[264]; // [rsp+670h] [rbp+570h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8B8h] [rbp+7B8h]

  memset_0(pszPath, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  memset_0(ExistingFileName, 0, 0x208u);
  memset_0(v15, 0, 0x208u);
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
      (void *)0x2A0,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v1,
      v9);
    v3 = lpMem[0];
LABEL_3:
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    return (unsigned int)v2;
  }
  v3 = lpMem[0];
  v10 = (const wchar_t *)L"DataStore.edb";
  v2 = StringCchPrintfW(pszPath, 0x104u, L"%s\\%s", lpMem[0]);
  if ( v2 < 0 )
  {
    v6 = 674;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v2,
      (int)v10);
    goto LABEL_3;
  }
  v10 = L"DataStore.edb.old";
  v2 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", v3);
  if ( v2 < 0 )
  {
    v6 = 675;
    goto LABEL_8;
  }
  v10 = L"DataStore.jfm";
  v2 = StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\%s", v3);
  if ( v2 < 0 )
  {
    v6 = 677;
    goto LABEL_8;
  }
  v10 = L"DataStore.jfm.old";
  v2 = StringCchPrintfW(v15, 0x104u, L"%s\\%s", v3);
  if ( v2 < 0 )
  {
    v6 = 678;
    goto LABEL_8;
  }
  if ( PathFileExistsW(pszPath) && !MoveFileW(pszPath, NewFileName) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x2AD,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
                     "Unable to rename data store file %ws to %ws.",
                     (const char *)pszPath,
                     NewFileName);
LABEL_18:
    v2 = LastErrorMsg;
    goto LABEL_3;
  }
  if ( PathFileExistsW(ExistingFileName) && !MoveFileW(ExistingFileName, v15) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x2B6,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
                     "Unable to rename data store flush map file %ws to %ws.",
                     (const char *)ExistingFileName,
                     v15);
    goto LABEL_18;
  }
  if ( v3 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180026590  push    rbp
0x180026592  push    rbx
0x180026593  push    rdi
0x180026594  push    r14
0x180026596  lea     rbp, [rsp-798h]
0x18002659e  sub     rsp, 898h
0x1800265a5  mov     rax, cs:__security_cookie
0x1800265ac  xor     rax, rsp
0x1800265af  mov     [rbp+7B0h+var_30], rax
0x1800265b6  mov     ebx, 208h
0x1800265bb  lea     rcx, [rsp+8B0h+pszPath]; void *
0x1800265c0  mov     r8d, ebx; Size
0x1800265c3  xor     edx, edx; Val
0x1800265c5  call    memset_0
0x1800265ca  mov     r8d, ebx; Size
0x1800265cd  lea     rcx, [rbp+7B0h+NewFileName]; void *
0x1800265d4  xor     edx, edx; Val
0x1800265d6  call    memset_0
0x1800265db  mov     r8d, ebx; Size
0x1800265de  lea     rcx, [rbp+7B0h+ExistingFileName]; void *
0x1800265e5  xor     edx, edx; Val
0x1800265e7  call    memset_0
0x1800265ec  mov     r8d, ebx; Size
0x1800265ef  lea     rcx, [rbp+7B0h+var_240]; void *
0x1800265f6  xor     edx, edx; Val
0x1800265f8  call    memset_0
0x1800265fd  lea     rdx, [rsp+8B0h+lpMem]; unsigned __int16 *
0x180026602  mov     [rsp+8B0h+lpMem], 0
0x18002660b  lea     rcx, aWindirSoftware_0; "%windir%\\SoftwareDistribution\\DataSto"...
0x180026612  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x180026617  mov     edi, eax
0x180026619  test    eax, eax
0x18002661b  jns     short loc_18002665D
0x18002661d  mov     rcx, [rbp+7B8h]; this
0x180026624  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002662b  mov     r9d, eax; char *
0x18002662e  mov     edx, 2A0h; void *
0x180026633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026638  mov     rbx, [rsp+8B0h+lpMem]
0x18002663d  test    rbx, rbx
0x180026640  jz      short loc_180026656
0x180026642  call    cs:__imp_GetProcessHeap
0x180026648  mov     r8, rbx; lpMem
0x18002664b  xor     edx, edx; dwFlags
0x18002664d  mov     rcx, rax; hHeap
0x180026650  call    cs:__imp_HeapFree
0x180026656  mov     eax, edi
0x180026658  jmp     loc_18002680D
0x18002665d  mov     rbx, [rsp+8B0h+lpMem]
0x180026662  lea     rax, aDatastoreEdb; "DataStore.edb"
0x180026669  mov     r14d, 104h
0x18002666f  mov     [rsp+8B0h+var_890], rax; int
0x180026674  mov     r9, rbx
0x180026677  lea     r8, aSS; "%s\\%s"
0x18002667e  mov     edx, r14d; unsigned __int64
0x180026681  lea     rcx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180026686  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002668b  mov     edi, eax
0x18002668d  test    eax, eax
0x18002668f  jns     short loc_1800266AE
0x180026691  mov     edx, 2A2h; void *
0x180026696  mov     rcx, [rbp+7B8h]; this
0x18002669d  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800266a4  mov     r9d, edi; char *
0x1800266a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800266ac  jmp     short loc_18002663D
0x1800266ae  lea     rax, aDatastoreEdbOl; "DataStore.edb.old"
0x1800266b5  mov     r9, rbx
0x1800266b8  lea     r8, aSS; "%s\\%s"
0x1800266bf  mov     [rsp+8B0h+var_890], rax
0x1800266c4  mov     rdx, r14; unsigned __int64
0x1800266c7  lea     rcx, [rbp+7B0h+NewFileName]; unsigned __int16 *
0x1800266ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800266d3  mov     edi, eax
0x1800266d5  test    eax, eax
0x1800266d7  jns     short loc_1800266E0
0x1800266d9  mov     edx, 2A3h
0x1800266de  jmp     short loc_180026696
0x1800266e0  lea     rax, aDatastoreJfm; "DataStore.jfm"
0x1800266e7  mov     r9, rbx
0x1800266ea  lea     r8, aSS; "%s\\%s"
0x1800266f1  mov     [rsp+8B0h+var_890], rax
0x1800266f6  mov     rdx, r14; unsigned __int64
0x1800266f9  lea     rcx, [rbp+7B0h+ExistingFileName]; unsigned __int16 *
0x180026700  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026705  mov     edi, eax
0x180026707  test    eax, eax
0x180026709  jns     short loc_180026712
0x18002670b  mov     edx, 2A5h
0x180026710  jmp     short loc_180026696
0x180026712  lea     rax, aDatastoreJfmOl; "DataStore.jfm.old"
0x180026719  mov     r9, rbx
0x18002671c  lea     r8, aSS; "%s\\%s"
0x180026723  mov     [rsp+8B0h+var_890], rax
0x180026728  mov     rdx, r14; unsigned __int64
0x18002672b  lea     rcx, [rbp+7B0h+var_240]; unsigned __int16 *
0x180026732  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026737  mov     edi, eax
0x180026739  test    eax, eax
0x18002673b  jns     short loc_180026747
0x18002673d  mov     edx, 2A6h
0x180026742  jmp     loc_180026696
0x180026747  lea     rcx, [rsp+8B0h+pszPath]; pszPath
0x18002674c  call    cs:__imp_PathFileExistsW
0x180026752  test    eax, eax
0x180026754  jz      short loc_1800267A8
0x180026756  lea     rdx, [rbp+7B0h+NewFileName]; lpNewFileName
0x18002675d  lea     rcx, [rsp+8B0h+pszPath]; lpExistingFileName
0x180026762  call    cs:__imp_MoveFileW
0x180026768  test    eax, eax
0x18002676a  jnz     short loc_1800267A8
0x18002676c  lea     rax, [rbp+7B0h+NewFileName]
0x180026773  mov     edx, 2ADh; void *
0x180026778  mov     [rsp+8B0h+var_888], rax
0x18002677d  lea     r9, aUnableToRename_1; "Unable to rename data store file %ws to"...
0x180026784  lea     rax, [rsp+8B0h+pszPath]
0x180026789  mov     rcx, [rbp+7B8h]; this
0x180026790  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026797  mov     [rsp+8B0h+var_890], rax; char *
0x18002679c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800267a1  mov     edi, eax
0x1800267a3  jmp     loc_18002663D
0x1800267a8  lea     rcx, [rbp+7B0h+ExistingFileName]; pszPath
0x1800267af  call    cs:__imp_PathFileExistsW
0x1800267b5  test    eax, eax
0x1800267b7  jz      short loc_1800267F2
0x1800267b9  lea     rdx, [rbp+7B0h+var_240]; lpNewFileName
0x1800267c0  lea     rcx, [rbp+7B0h+ExistingFileName]; lpExistingFileName
0x1800267c7  call    cs:__imp_MoveFileW
0x1800267cd  test    eax, eax
0x1800267cf  jnz     short loc_1800267F2
0x1800267d1  lea     rax, [rbp+7B0h+var_240]
0x1800267d8  mov     edx, 2B6h
0x1800267dd  mov     [rsp+8B0h+var_888], rax
0x1800267e2  lea     r9, aUnableToRename_0; "Unable to rename data store flush map f"...
0x1800267e9  lea     rax, [rbp+7B0h+ExistingFileName]
0x1800267f0  jmp     short loc_180026789
0x1800267f2  test    rbx, rbx
0x1800267f5  jz      short loc_18002680B
0x1800267f7  call    cs:__imp_GetProcessHeap
0x1800267fd  mov     r8, rbx; lpMem
0x180026800  xor     edx, edx; dwFlags
0x180026802  mov     rcx, rax; hHeap
0x180026805  call    cs:__imp_HeapFree
0x18002680b  xor     eax, eax
0x18002680d  mov     rcx, [rbp+7B0h+var_30]
0x180026814  xor     rcx, rsp; StackCookie
0x180026817  call    __security_check_cookie
0x18002681c  add     rsp, 898h
0x180026823  pop     r14
0x180026825  pop     rdi
0x180026826  pop     rbx
0x180026827  pop     rbp
0x180026828  retn
```
