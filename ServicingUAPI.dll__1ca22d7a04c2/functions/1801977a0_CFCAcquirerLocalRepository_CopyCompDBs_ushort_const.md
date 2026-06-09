# CFCAcquirerLocalRepository::CopyCompDBs(ushort const *)

- ea: `0x1801977a0`
- end: `0x180197de3`
- name: `?CopyCompDBs@CFCAcquirerLocalRepository@@UEAAJPEBG@Z`
- size: `1603`
- prototype: `int(CFCAcquirerLocalRepository *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180068c4c`
- `0x18006fab0`
- `0x1801975bc`
- `0x180197644`
- `0x1801977a0`
- `0x18019b150`
- `0x18019cb24`
- `0x18019d714`
- `0x18019fa7c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197bc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197db5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197aa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197ce4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197aa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197ce4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197d9f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019785b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197943`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019785b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180197943`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180197b5f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180197b5f`

## string_xrefs

- `0x180197a19`: `FCAcquirerLocalRepository: Number of CompDBs found [%lu]`
- `0x180197ae5`: `FCAcquirerLocalRepository: Copying file: %s`
- `0x1801979b6`: `FCAcquirerLocalRepository: Searching *.xml.cab in [%s]`
- `0x180197832`: `CFCAcquirerLocalRepository::CopyCompDBs`
- `0x180197900`: `CFCAcquirerLocalRepository::CopyCompDBs`
- `0x180197c42`: `CFCAcquirerLocalRepository::CopyCompDBs`
- `0x180197c9d`: `CFCAcquirerLocalRepository::CopyCompDBs`

## pseudocode

```c
__int64 __fastcall CFCAcquirerLocalRepository::CopyCompDBs(
        CFCAcquirerLocalRepository *this,
        const unsigned __int16 *a2)
{
  bool v3; // zf
  LPCWSTR v4; // r12
  __int64 v5; // r15
  __int64 v6; // r13
  const WCHAR *v7; // r14
  unsigned int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  DWORD FileAttributesW; // ebx
  int v15; // ebx
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  DWORD v22; // ebx
  int v23; // ebx
  __int64 v24; // rcx
  int Files; // eax
  __int64 v26; // rcx
  int v27; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  __int64 v31; // rcx
  void **v32; // rdi
  int v33; // ebx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  signed int LastError; // eax
  __int64 v38; // rbx
  __int64 v39; // rcx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rcx
  int v44; // eax
  int v45; // eax
  HANDLE v46; // rax
  HANDLE v47; // rax
  HANDLE v48; // rax
  void *v49; // rbx
  HANDLE v50; // rax
  HANDLE v51; // rax
  __int64 v53; // [rsp+20h] [rbp-50h]
  int v54; // [rsp+28h] [rbp-48h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-40h] BYREF
  __int64 v56; // [rsp+38h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-30h]
  LPCWSTR lpNewFileName; // [rsp+48h] [rbp-28h] BYREF
  __int64 v59; // [rsp+50h] [rbp-20h]
  __int64 v60; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v61; // [rsp+60h] [rbp-10h]

  v61 = a2;
  v3 = (*((_BYTE *)this - 68) & 8) == 0;
  v4 = 0;
  lpFileName = 0;
  v5 = 0;
  v56 = 0;
  v6 = 0;
  lpMem = 0;
  v7 = 0;
  v59 = 0;
  v60 = 0;
  lpNewFileName = 0;
  if ( !v3 )
  {
    v8 = 0;
    goto LABEL_67;
  }
  if ( !a2 )
  {
    v9 = *((_QWORD *)this - 1);
    v8 = -2147024809;
    v10 = 0;
    if ( v9 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v9 + 32LL))(*((_QWORD *)this - 1), 2147942487LL);
      v54 = -2147024809;
      LODWORD(v53) = 167;
LABEL_6:
      v12 = v9;
      goto LABEL_7;
    }
    goto LABEL_9;
  }
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
    v15 = 0;
  else
    v15 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v15 )
  {
    v16 = *((_QWORD *)this - 1);
    v10 = 0;
    v8 = -2147024893;
    if ( !v16 )
      goto LABEL_9;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, 2147942403LL);
    v54 = -2147024893;
    LODWORD(v53) = 169;
LABEL_16:
    v12 = v16;
LABEL_7:
    v13 = CFCLogLiteT<CEmptyType>::LogFormat(
            v12,
            4 - (unsigned int)(v11 != 0),
            L"%s(%d): Result = 0x%X",
            L"CFCAcquirerLocalRepository::CopyCompDBs",
            v53,
            v54);
    v10 = (unsigned int)v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    goto LABEL_9;
  }
  v17 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 1), L"metadata", 0, &lpFileName);
  v8 = v17;
  if ( v17 >= 0 )
  {
    v4 = lpFileName;
    v22 = GetFileAttributesW(lpFileName);
    if ( v22 == -1 )
      v23 = 0;
    else
      v23 = (v22 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v23 )
    {
      v16 = *((_QWORD *)this - 1);
      v10 = 0;
      v8 = -2147024893;
      if ( !v16 )
        goto LABEL_9;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, 2147942403LL);
      v54 = -2147024893;
      LODWORD(v53) = 175;
      goto LABEL_16;
    }
    v24 = *((_QWORD *)this - 1);
    if ( v24 )
      CFCLogLiteT<CEmptyType>::LogFormat(v24, 2, L"FCAcquirerLocalRepository: Searching *.xml.cab in [%s]", v4);
    Files = CDlpHelpersT<CEmptyType>::FindFiles(v24, v4, &v56);
    v8 = Files;
    if ( Files < 0 )
    {
      v9 = *((_QWORD *)this - 1);
      v10 = 0;
      if ( v9 )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
                *((_QWORD *)this - 1),
                (unsigned int)Files);
        v54 = v8;
        LODWORD(v53) = 180;
        goto LABEL_6;
      }
LABEL_9:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
      goto LABEL_67;
    }
    v26 = *((_QWORD *)this - 1);
    v27 = HIDWORD(v56);
    if ( v26 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        v26,
        2,
        L"FCAcquirerLocalRepository: Number of CompDBs found [%lu]",
        HIDWORD(v56));
    LODWORD(lpFileName) = 0;
    if ( v27 )
    {
      while ( 1 )
      {
        if ( v5 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v59 = 0;
        }
        if ( v6 )
        {
          v29 = GetProcessHeap();
          HeapFree(v29, 0, (LPVOID)(v6 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v60 = 0;
        }
        if ( v7 )
        {
          v30 = GetProcessHeap();
          HeapFree(v30, 0, (LPVOID)(v7 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v7 = 0;
          lpNewFileName = 0;
        }
        v31 = *((_QWORD *)this - 1);
        v32 = (void **)lpMem;
        v33 = (int)lpFileName;
        if ( v31 )
          CFCLogLiteT<CEmptyType>::LogFormat(
            v31,
            2,
            L"FCAcquirerLocalRepository: Copying file: %s",
            *((_QWORD *)lpMem + (int)lpFileName));
        v34 = CMiscHelpersT<CEmptyType>::ParseFileName(v32[v33], (__int64)&v60);
        v8 = v34;
        if ( v34 < 0 )
        {
          v42 = *((_QWORD *)this - 1);
          v43 = 0;
          if ( v42 )
          {
            v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v42 + 32LL))(
                    *((_QWORD *)this - 1),
                    (unsigned int)v34);
            LODWORD(v53) = 192;
            v45 = CFCLogLiteT<CEmptyType>::LogFormat(
                    v42,
                    4 - (unsigned int)(v44 != 0),
                    L"%s(%d): Result = 0x%X",
                    L"CFCAcquirerLocalRepository::CopyCompDBs",
                    v53,
                    v8);
            v43 = (unsigned int)v45;
            if ( v45 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v45);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v43);
          v5 = v59;
          v6 = v60;
          goto LABEL_67;
        }
        v6 = v60;
        v5 = v59;
        v35 = CMiscHelpersT<CEmptyType>::CombinePath(v61, v59, v60, &lpNewFileName);
        v8 = v35;
        if ( v35 < 0 )
        {
          v38 = *((_QWORD *)this - 1);
          v39 = 0;
          if ( v38 )
          {
            v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v38 + 32LL))(
                    *((_QWORD *)this - 1),
                    (unsigned int)v35);
            LODWORD(v53) = 193;
            v41 = CFCLogLiteT<CEmptyType>::LogFormat(
                    v38,
                    4 - (unsigned int)(v40 != 0),
                    L"%s(%d): Result = 0x%X",
                    L"CFCAcquirerLocalRepository::CopyCompDBs",
                    v53,
                    v8);
            v39 = (unsigned int)v41;
            if ( v41 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v41);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
          v7 = lpNewFileName;
          goto LABEL_67;
        }
        v7 = lpNewFileName;
        if ( !CopyFileW(*((LPCWSTR *)lpMem + v33), lpNewFileName, 0) )
          break;
        v36 = CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(v7);
        v8 = v36;
        if ( v36 < 0 )
        {
          v9 = *((_QWORD *)this - 1);
          v10 = 0;
          if ( !v9 )
            goto LABEL_9;
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
                  *((_QWORD *)this - 1),
                  (unsigned int)v36);
          v54 = v8;
          LODWORD(v53) = 195;
          goto LABEL_6;
        }
        LODWORD(lpFileName) = v33 + 1;
        if ( (unsigned int)(v33 + 1) >= HIDWORD(v56) )
          goto LABEL_67;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v10 = 0;
        if ( (v8 & 0x80000000) == 0 )
          goto LABEL_9;
      }
      else
      {
        v8 = -2147467259;
        v10 = 0;
      }
      v9 = *((_QWORD *)this - 1);
      if ( !v9 )
        goto LABEL_9;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(*((_QWORD *)this - 1), v8);
      v54 = v8;
      LODWORD(v53) = 194;
      goto LABEL_6;
    }
  }
  else
  {
    v18 = *((_QWORD *)this - 1);
    v19 = 0;
    if ( v18 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v18 + 32LL))(
              *((_QWORD *)this - 1),
              (unsigned int)v17);
      v21 = CFCLogLiteT<CEmptyType>::LogFormat(
              v18,
              4 - (unsigned int)(v20 != 0),
              L"%s(%d): Result = 0x%X",
              L"CFCAcquirerLocalRepository::CopyCompDBs",
              173,
              v8);
      v19 = (unsigned int)v21;
      if ( v21 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
    v4 = lpFileName;
  }
LABEL_67:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v7 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v47 = GetProcessHeap();
    HeapFree(v47, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v56, 0);
  v49 = lpMem;
  if ( lpMem )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
  }
  if ( v4 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x1801977a0  mov     [rsp-38h+arg_10], rbx
0x1801977a5  push    rbp
0x1801977a6  push    rsi
0x1801977a7  push    rdi
0x1801977a8  push    r12
0x1801977aa  push    r13
0x1801977ac  push    r14
0x1801977ae  push    r15
0x1801977b0  mov     rbp, rsp
0x1801977b3  sub     rsp, 70h
0x1801977b7  mov     rax, rdx
0x1801977ba  mov     [rbp+var_10], rdx
0x1801977be  xor     edx, edx
0x1801977c0  mov     rsi, rcx
0x1801977c3  test    byte ptr [rcx-44h], 8
0x1801977c7  mov     r12d, edx
0x1801977ca  mov     [rbp+lpFileName], rdx
0x1801977ce  mov     r15d, edx
0x1801977d1  mov     [rbp+var_38], rdx
0x1801977d5  mov     r13d, edx
0x1801977d8  mov     [rbp+lpMem], rdx
0x1801977dc  mov     r14d, edx
0x1801977df  mov     [rbp+var_20], rdx
0x1801977e3  mov     [rbp+var_18], rdx
0x1801977e7  mov     [rbp+lpNewFileName], rdx
0x1801977eb  jz      short loc_1801977F4
0x1801977ed  mov     edi, edx
0x1801977ef  jmp     loc_180197CD8
0x1801977f4  test    rax, rax
0x1801977f7  jnz     short loc_180197858
0x1801977f9  mov     rbx, [rsi-8]
0x1801977fd  mov     edi, 80070057h
0x180197802  mov     ecx, edx
0x180197804  test    rbx, rbx
0x180197807  jz      short loc_18019784E
0x180197809  mov     rax, [rbx]
0x18019780c  mov     edx, edi
0x18019780e  mov     rcx, rbx
0x180197811  mov     rax, [rax+20h]
0x180197815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019781a  mov     [rsp+70h+var_48], edi
0x18019781e  mov     dword ptr [rsp+70h+var_50], 0A7h
0x180197826  mov     rcx, rbx
0x180197829  neg     eax
0x18019782b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180197832  lea     r9, aCfcacquirerloc_6; "CFCAcquirerLocalRepository::CopyCompDBs"
0x180197839  sbb     edx, edx
0x18019783b  add     edx, 4
0x18019783e  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197843  mov     ecx, eax
0x180197845  test    eax, eax
0x180197847  jns     short loc_18019784E
0x180197849  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019784e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197853  jmp     loc_180197CD8
0x180197858  mov     rcx, rax; lpFileName
0x18019785b  call    cs:__imp_GetFileAttributesW
0x180197862  nop     dword ptr [rax+rax+00h]
0x180197867  mov     ebx, eax
0x180197869  cmp     eax, 0FFFFFFFFh
0x18019786c  jz      short loc_180197876
0x18019786e  shr     ebx, 4
0x180197871  and     ebx, 1
0x180197874  jmp     short loc_180197878
0x180197876  xor     ebx, ebx
0x180197878  xor     ecx, ecx
0x18019787a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019787f  xor     ecx, ecx
0x180197881  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197886  test    ebx, ebx
0x180197888  jnz     short loc_1801978C1
0x18019788a  mov     rsi, [rsi-8]
0x18019788e  xor     ecx, ecx
0x180197890  mov     ebx, 80070003h
0x180197895  mov     edi, ebx
0x180197897  test    rsi, rsi
0x18019789a  jz      short loc_18019784E
0x18019789c  mov     rax, [rsi]
0x18019789f  mov     edx, ebx
0x1801978a1  mov     rcx, rsi
0x1801978a4  mov     rax, [rax+20h]
0x1801978a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801978ad  mov     [rsp+70h+var_48], ebx
0x1801978b1  mov     dword ptr [rsp+70h+var_50], 0A9h
0x1801978b9  mov     rcx, rsi
0x1801978bc  jmp     loc_180197829
0x1801978c1  mov     rcx, [rsi+8]
0x1801978c5  lea     r9, [rbp+lpFileName]
0x1801978c9  xor     r8d, r8d
0x1801978cc  lea     rdx, aMetadata_1; "metadata"
0x1801978d3  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1801978d8  mov     edi, eax
0x1801978da  test    eax, eax
0x1801978dc  jns     short loc_18019793C
0x1801978de  mov     rbx, [rsi-8]
0x1801978e2  xor     ecx, ecx
0x1801978e4  test    rbx, rbx
0x1801978e7  jz      short loc_18019792E
0x1801978e9  mov     rcx, [rbx]
0x1801978ec  mov     edx, edi
0x1801978ee  mov     rax, [rcx+20h]
0x1801978f2  mov     rcx, rbx
0x1801978f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801978fa  neg     eax
0x1801978fc  mov     [rsp+70h+var_48], edi
0x180197900  lea     r9, aCfcacquirerloc_6; "CFCAcquirerLocalRepository::CopyCompDBs"
0x180197907  mov     dword ptr [rsp+70h+var_50], 0ADh
0x18019790f  sbb     edx, edx
0x180197911  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180197918  add     edx, 4
0x18019791b  mov     rcx, rbx
0x18019791e  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197923  mov     ecx, eax
0x180197925  test    eax, eax
0x180197927  jns     short loc_18019792E
0x180197929  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019792e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197933  mov     r12, [rbp+lpFileName]
0x180197937  jmp     loc_180197CD8
0x18019793c  mov     r12, [rbp+lpFileName]
0x180197940  mov     rcx, r12; lpFileName
0x180197943  call    cs:__imp_GetFileAttributesW
0x18019794a  nop     dword ptr [rax+rax+00h]
0x18019794f  mov     ebx, eax
0x180197951  cmp     eax, 0FFFFFFFFh
0x180197954  jz      short loc_18019795E
0x180197956  shr     ebx, 4
0x180197959  and     ebx, 1
0x18019795c  jmp     short loc_180197960
0x18019795e  xor     ebx, ebx
0x180197960  xor     ecx, ecx
0x180197962  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197967  xor     ecx, ecx
0x180197969  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019796e  test    ebx, ebx
0x180197970  jnz     short loc_1801979AA
0x180197972  mov     rsi, [rsi-8]
0x180197976  xor     ecx, ecx
0x180197978  mov     ebx, 80070003h
0x18019797d  mov     edi, ebx
0x18019797f  test    rsi, rsi
0x180197982  jz      loc_18019784E
0x180197988  mov     rax, [rsi]
0x18019798b  mov     edx, ebx
0x18019798d  mov     rcx, rsi
0x180197990  mov     rax, [rax+20h]
0x180197994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197999  mov     [rsp+70h+var_48], ebx
0x18019799d  mov     dword ptr [rsp+70h+var_50], 0AFh
0x1801979a5  jmp     loc_1801978B9
0x1801979aa  mov     rcx, [rsi-8]
0x1801979ae  test    rcx, rcx
0x1801979b1  jz      short loc_1801979C7
0x1801979b3  mov     r9, r12
0x1801979b6  lea     r8, aFcacquirerloca_3; "FCAcquirerLocalRepository: Searching *."...
0x1801979bd  mov     edx, 2
0x1801979c2  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x1801979c7  lea     r8, [rbp+var_38]
0x1801979cb  mov     rdx, r12
0x1801979ce  call    ?FindFiles@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG0PEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z; CDlpHelpersT<CEmptyType>::FindFiles(ushort const *,ushort const *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x1801979d3  mov     edi, eax
0x1801979d5  test    eax, eax
0x1801979d7  jns     short loc_180197A0A
0x1801979d9  mov     rbx, [rsi-8]
0x1801979dd  xor     ecx, ecx
0x1801979df  test    rbx, rbx
0x1801979e2  jz      loc_18019784E
0x1801979e8  mov     rax, [rbx]
0x1801979eb  mov     edx, edi
0x1801979ed  mov     rcx, rbx
0x1801979f0  mov     rax, [rax+20h]
0x1801979f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801979f9  mov     [rsp+70h+var_48], edi
0x1801979fd  mov     dword ptr [rsp+70h+var_50], 0B4h
0x180197a05  jmp     loc_180197826
0x180197a0a  mov     rcx, [rsi-8]
0x180197a0e  mov     ebx, dword ptr [rbp+var_38+4]
0x180197a11  test    rcx, rcx
0x180197a14  jz      short loc_180197A2A
0x180197a16  mov     r9d, ebx
0x180197a19  lea     r8, aFcacquirerloca_0; "FCAcquirerLocalRepository: Number of Co"...
0x180197a20  mov     edx, 2
0x180197a25  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197a2a  mov     dword ptr [rbp+lpFileName], r13d
0x180197a2e  test    ebx, ebx
0x180197a30  jz      loc_180197CD8
0x180197a36  test    r15, r15
0x180197a39  jz      short loc_180197A6B
0x180197a3b  call    cs:__imp_GetProcessHeap
0x180197a42  nop     dword ptr [rax+rax+00h]
0x180197a47  lea     r8, [r15-4]; lpMem
0x180197a4b  xor     edx, edx; dwFlags
0x180197a4d  mov     rcx, rax; hHeap
0x180197a50  call    cs:__imp_HeapFree
0x180197a57  nop     dword ptr [rax+rax+00h]
0x180197a5c  xor     ecx, ecx
0x180197a5e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197a63  mov     [rbp+var_20], 0
0x180197a6b  test    r13, r13
0x180197a6e  jz      short loc_180197AA0
0x180197a70  call    cs:__imp_GetProcessHeap
0x180197a77  nop     dword ptr [rax+rax+00h]
0x180197a7c  lea     r8, [r13-4]; lpMem
0x180197a80  xor     edx, edx; dwFlags
0x180197a82  mov     rcx, rax; hHeap
0x180197a85  call    cs:__imp_HeapFree
0x180197a8c  nop     dword ptr [rax+rax+00h]
0x180197a91  xor     ecx, ecx
0x180197a93  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197a98  mov     [rbp+var_18], 0
0x180197aa0  test    r14, r14
0x180197aa3  jz      short loc_180197AD4
0x180197aa5  call    cs:__imp_GetProcessHeap
0x180197aac  nop     dword ptr [rax+rax+00h]
0x180197ab1  lea     r8, [r14-4]; lpMem
0x180197ab5  xor     edx, edx; dwFlags
0x180197ab7  mov     rcx, rax; hHeap
0x180197aba  call    cs:__imp_HeapFree
0x180197ac1  nop     dword ptr [rax+rax+00h]
0x180197ac6  xor     ecx, ecx
0x180197ac8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180197acd  xor     r14d, r14d
0x180197ad0  mov     [rbp+lpNewFileName], r14
0x180197ad4  mov     rcx, [rsi-8]
0x180197ad8  mov     rdi, [rbp+lpMem]
0x180197adc  test    rcx, rcx
0x180197adf  jz      short loc_180197AFC
0x180197ae1  movsxd  rbx, dword ptr [rbp+lpFileName]
0x180197ae5  lea     r8, aFcacquirerloca_2; "FCAcquirerLocalRepository: Copying file"...
0x180197aec  mov     edx, 2
0x180197af1  mov     r9, [rdi+rbx*8]
0x180197af5  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180197afa  jmp     short loc_180197AFF
0x180197afc  mov     ebx, dword ptr [rbp+lpFileName]
0x180197aff  movsxd  rax, ebx
0x180197b02  lea     rcx, [rbp+var_18]
0x180197b06  mov     [rsp+70h+var_50], rcx; __int64
0x180197b0b  lea     r9, [rbp+var_20]
0x180197b0f  xor     r8d, r8d
0x180197b12  mov     rcx, [rdi+rax*8]; Src
0x180197b16  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x180197b1b  mov     edi, eax
0x180197b1d  test    eax, eax
0x180197b1f  js      loc_180197C7B
0x180197b25  mov     r13, [rbp+var_18]
0x180197b29  lea     r9, [rbp+lpNewFileName]
0x180197b2d  mov     r15, [rbp+var_20]
0x180197b31  mov     r8, r13
0x180197b34  mov     rcx, [rbp+var_10]
0x180197b38  mov     rdx, r15
0x180197b3b  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180197b40  mov     edi, eax
0x180197b42  test    eax, eax
0x180197b44  js      loc_180197C20
0x180197b4a  mov     rcx, [rbp+lpMem]
0x180197b4e  xor     r8d, r8d; bFailIfExists
0x180197b51  mov     r14, [rbp+lpNewFileName]
0x180197b55  movsxd  rax, ebx
0x180197b58  mov     rdx, r14; lpNewFileName
0x180197b5b  mov     rcx, [rcx+rax*8]; lpExistingFileName
0x180197b5f  call    cs:__imp_CopyFileW
0x180197b66  nop     dword ptr [rax+rax+00h]
0x180197b6b  test    eax, eax
0x180197b6d  jz      short loc_180197BC1
0x180197b6f  mov     rcx, r14; lpFileName
0x180197b72  call    ?CheckAndClearFileAttribute@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGK@Z; CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(ushort const *,ulong)
0x180197b77  mov     edi, eax
0x180197b79  test    eax, eax
0x180197b7b  js      short loc_180197B90
0x180197b7d  inc     ebx
0x180197b7f  mov     dword ptr [rbp+lpFileName], ebx
0x180197b82  cmp     ebx, dword ptr [rbp+var_38+4]
0x180197b85  jb      loc_180197A36
0x180197b8b  jmp     loc_180197CD8
0x180197b90  mov     rbx, [rsi-8]
0x180197b94  xor     ecx, ecx
0x180197b96  test    rbx, rbx
0x180197b99  jz      loc_18019784E
0x180197b9f  mov     rax, [rbx]
0x180197ba2  mov     edx, edi
0x180197ba4  mov     rcx, rbx
0x180197ba7  mov     rax, [rax+20h]
0x180197bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197bb0  mov     [rsp+70h+var_48], edi
0x180197bb4  mov     dword ptr [rsp+70h+var_50], 0C3h
0x180197bbc  jmp     loc_180197826
0x180197bc1  call    cs:__imp_GetLastError
0x180197bc8  nop     dword ptr [rax+rax+00h]
0x180197bcd  mov     edi, eax
0x180197bcf  test    eax, eax
0x180197bd1  jnz     short loc_180197BDC
0x180197bd3  mov     edi, 80004005h
0x180197bd8  xor     ecx, ecx
0x180197bda  jmp     short loc_180197BF1
0x180197bdc  jle     short loc_180197BE7
0x180197bde  movzx   edi, ax
0x180197be1  or      edi, 80070000h
0x180197be7  xor     ecx, ecx
0x180197be9  test    edi, edi
0x180197beb  jns     loc_18019784E
  ... truncated ...
```
