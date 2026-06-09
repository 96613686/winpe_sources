# CFCAcquirerLocalRepository::CopyPayloadBinaries(ushort const *,ushort const *,ushort const *)

- ea: `0x1801985b0`
- end: `0x180198a74`
- name: `?CopyPayloadBinaries@CFCAcquirerLocalRepository@@UEAAJPEBG00@Z`
- size: `1220`
- prototype: `int(CFCAcquirerLocalRepository *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180068c4c`
- `0x18006fab0`
- `0x1801975bc`
- `0x180197644`
- `0x1801985b0`
- `0x18019cb24`
- `0x1801ac020`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019890d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019890d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801989ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198a19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198a46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801989ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198a19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180198a46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801989d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198a04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198a31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801989d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198a04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180198a31`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198669`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801987f6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180198669`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801987f6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801988fd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801988fd`

## string_xrefs

- `0x180198760`: `Target file already exists. Skipping copy for %ws`
- `0x180198708`: `CFCAcquirerLocalRepository::CopyPayloadBinaries`
- `0x1801987b3`: `CFCAcquirerLocalRepository::CopyPayloadBinaries`
- `0x180198897`: `CFCAcquirerLocalRepository::CopyPayloadBinaries`
- `0x1801989a0`: `CFCAcquirerLocalRepository::CopyPayloadBinaries`
- `0x1801988df`: `FCAcquirerLocalRepository: Copying file: %ws`

## pseudocode

```c
__int64 __fastcall CFCAcquirerLocalRepository::CopyPayloadBinaries(
        CFCAcquirerLocalRepository *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r15
  __int64 v6; // r13
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // edi
  int v13; // eax
  DWORD FileAttributesW; // edi
  int v15; // edi
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  BOOL v28; // edi
  int v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  signed int LastError; // eax
  int v36; // eax
  int v37; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v42; // [rsp+20h] [rbp-30h]
  int v43; // [rsp+28h] [rbp-28h]
  __int64 v44; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-10h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  lpFileName = 0;
  lpNewFileName[0] = 0;
  v44 = 0;
  if ( !a3 )
  {
    v10 = *((_QWORD *)this - 1);
    v11 = 0;
    v12 = -2147024809;
    if ( v10 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, 2147942487LL);
      v43 = -2147024809;
      v42 = 302;
      goto LABEL_51;
    }
LABEL_53:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
    goto LABEL_54;
  }
  if ( !a4 )
  {
    v10 = *((_QWORD *)this - 1);
    v11 = 0;
    v12 = -2147024809;
    if ( !v10 )
      goto LABEL_53;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, 2147942487LL);
    v43 = -2147024809;
    v42 = 303;
    goto LABEL_51;
  }
  FileAttributesW = GetFileAttributesW(a4);
  if ( FileAttributesW == -1 )
    v15 = 0;
  else
    v15 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v15 )
  {
    v10 = *((_QWORD *)this - 1);
    v11 = 0;
    v12 = -2147024893;
    if ( !v10 )
      goto LABEL_53;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, 2147942403LL);
    v43 = -2147024893;
    v42 = 308;
    goto LABEL_51;
  }
  v16 = CMiscHelpersT<CEmptyType>::CombinePath(a4, a3, 0, &v44);
  v12 = v16;
  if ( v16 >= 0 )
  {
    v6 = v44;
    if ( (unsigned int)FileExists(v44) )
    {
      v21 = *((_QWORD *)this - 1);
      if ( v21 )
        CFCLogLiteT<CEmptyType>::LogFormat(v21, 2, L"Target file already exists. Skipping copy for %ws", a3);
      v12 = 0;
    }
    else
    {
      v22 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 1), a3, 0, &lpFileName);
      v12 = v22;
      if ( v22 >= 0 )
      {
        v4 = lpFileName;
        v27 = GetFileAttributesW(lpFileName);
        v28 = v27 != -1 && (v27 & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v28 )
        {
          v10 = *((_QWORD *)this - 1);
          v11 = 0;
          v12 = -2147024894;
          if ( !v10 )
            goto LABEL_53;
          v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, 2147942402LL);
          v43 = -2147024894;
          v42 = 321;
          goto LABEL_51;
        }
        v29 = CMiscHelpersT<CEmptyType>::CombinePath(a4, a3, 0, lpNewFileName);
        v12 = v29;
        if ( v29 >= 0 )
        {
          v34 = *((_QWORD *)this - 1);
          if ( v34 )
            CFCLogLiteT<CEmptyType>::LogFormat(v34, 2, L"FCAcquirerLocalRepository: Copying file: %ws", v4);
          v5 = lpNewFileName[0];
          if ( CopyFileW(v4, lpNewFileName[0], 0) )
          {
            v36 = CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(v5);
            v12 = v36;
            if ( v36 >= 0 )
              goto LABEL_54;
            v10 = *((_QWORD *)this - 1);
            v11 = 0;
            if ( !v10 )
              goto LABEL_53;
            v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, (unsigned int)v36);
            v43 = v12;
            v42 = 327;
            goto LABEL_51;
          }
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v12 = (unsigned __int16)LastError | 0x80070000;
            v11 = 0;
            if ( (v12 & 0x80000000) == 0 )
              goto LABEL_53;
          }
          else
          {
            v12 = -2147467259;
            v11 = 0;
          }
          v10 = *((_QWORD *)this - 1);
          if ( !v10 )
            goto LABEL_53;
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, v12);
          v43 = v12;
          v42 = 326;
LABEL_51:
          v37 = CFCLogLiteT<CEmptyType>::LogFormat(
                  v10,
                  4 - (unsigned int)(v13 != 0),
                  L"%s(%d): Result = 0x%X",
                  L"CFCAcquirerLocalRepository::CopyPayloadBinaries",
                  v42,
                  v43);
          v11 = (unsigned int)v37;
          if ( v37 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
          goto LABEL_53;
        }
        v30 = *((_QWORD *)this - 1);
        v31 = 0;
        if ( v30 )
        {
          v32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 32LL))(v30, (unsigned int)v29);
          v33 = CFCLogLiteT<CEmptyType>::LogFormat(
                  v30,
                  4 - (unsigned int)(v32 != 0),
                  L"%s(%d): Result = 0x%X",
                  L"CFCAcquirerLocalRepository::CopyPayloadBinaries",
                  323,
                  v12);
          v31 = (unsigned int)v33;
          if ( v33 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v33);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v31);
        v5 = lpNewFileName[0];
      }
      else
      {
        v23 = *((_QWORD *)this - 1);
        v24 = 0;
        if ( v23 )
        {
          v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 32LL))(v23, (unsigned int)v22);
          v26 = CFCLogLiteT<CEmptyType>::LogFormat(
                  v23,
                  4 - (unsigned int)(v25 != 0),
                  L"%s(%d): Result = 0x%X",
                  L"CFCAcquirerLocalRepository::CopyPayloadBinaries",
                  319,
                  v12);
          v24 = (unsigned int)v26;
          if ( v26 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v26);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
        v4 = lpFileName;
      }
    }
  }
  else
  {
    v17 = *((_QWORD *)this - 1);
    v18 = 0;
    if ( v17 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, (unsigned int)v16);
      v20 = CFCLogLiteT<CEmptyType>::LogFormat(
              v17,
              4 - (unsigned int)(v19 != 0),
              L"%s(%d): Result = 0x%X",
              L"CFCAcquirerLocalRepository::CopyPayloadBinaries",
              310,
              v12);
      v18 = (unsigned int)v20;
      if ( v20 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
    v6 = v44;
  }
LABEL_54:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v12;
}

```

## disassembly

```asm
0x1801985b0  mov     [rsp-38h+arg_8], rbx
0x1801985b5  push    rbp
0x1801985b6  push    rsi
0x1801985b7  push    rdi
0x1801985b8  push    r12
0x1801985ba  push    r13
0x1801985bc  push    r14
0x1801985be  push    r15
0x1801985c0  mov     rbp, rsp
0x1801985c3  sub     rsp, 50h
0x1801985c7  xor     esi, esi
0x1801985c9  xor     r15d, r15d
0x1801985cc  xor     r13d, r13d
0x1801985cf  mov     [rbp+lpFileName], rsi
0x1801985d3  mov     [rbp+lpNewFileName], r15
0x1801985d7  mov     r12, r9
0x1801985da  mov     [rbp+var_20], r13
0x1801985de  mov     r14, r8
0x1801985e1  mov     rbx, rcx
0x1801985e4  test    r8, r8
0x1801985e7  jnz     short loc_180198625
0x1801985e9  mov     rbx, [rbx-8]
0x1801985ed  xor     ecx, ecx
0x1801985ef  mov     r14d, 80070057h
0x1801985f5  mov     edi, r14d
0x1801985f8  test    rbx, rbx
0x1801985fb  jz      loc_1801989C6
0x180198601  mov     rax, [rbx]
0x180198604  mov     edx, r14d
0x180198607  mov     rcx, rbx
0x18019860a  mov     rax, [rax+20h]
0x18019860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198613  mov     [rsp+50h+var_28], r14d
0x180198618  mov     [rsp+50h+var_30], 12Eh
0x180198620  jmp     loc_18019899E
0x180198625  test    r12, r12
0x180198628  jnz     short loc_180198666
0x18019862a  mov     rbx, [rbx-8]
0x18019862e  xor     ecx, ecx
0x180198630  mov     r14d, 80070057h
0x180198636  mov     edi, r14d
0x180198639  test    rbx, rbx
0x18019863c  jz      loc_1801989C6
0x180198642  mov     rax, [rbx]
0x180198645  mov     edx, r14d
0x180198648  mov     rcx, rbx
0x18019864b  mov     rax, [rax+20h]
0x18019864f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198654  mov     [rsp+50h+var_28], r14d
0x180198659  mov     [rsp+50h+var_30], 12Fh
0x180198661  jmp     loc_18019899E
0x180198666  mov     rcx, r12; lpFileName
0x180198669  call    cs:__imp_GetFileAttributesW
0x180198670  nop     dword ptr [rax+rax+00h]
0x180198675  mov     edi, eax
0x180198677  cmp     eax, 0FFFFFFFFh
0x18019867a  jz      short loc_180198684
0x18019867c  shr     edi, 4
0x18019867f  and     edi, 1
0x180198682  jmp     short loc_180198686
0x180198684  xor     edi, edi
0x180198686  xor     ecx, ecx
0x180198688  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019868d  xor     ecx, ecx
0x18019868f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180198694  test    edi, edi
0x180198696  jnz     short loc_1801986CE
0x180198698  mov     rbx, [rbx-8]
0x18019869c  xor     ecx, ecx
0x18019869e  mov     edi, 80070003h
0x1801986a3  test    rbx, rbx
0x1801986a6  jz      loc_1801989C6
0x1801986ac  mov     rax, [rbx]
0x1801986af  mov     edx, edi
0x1801986b1  mov     rcx, rbx
0x1801986b4  mov     rax, [rax+20h]
0x1801986b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986bd  mov     [rsp+50h+var_28], edi
0x1801986c1  mov     [rsp+50h+var_30], 134h
0x1801986c9  jmp     loc_18019899E
0x1801986ce  lea     r9, [rbp+var_20]
0x1801986d2  xor     r8d, r8d
0x1801986d5  mov     rdx, r14
0x1801986d8  mov     rcx, r12
0x1801986db  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1801986e0  mov     edi, eax
0x1801986e2  test    eax, eax
0x1801986e4  jns     short loc_180198744
0x1801986e6  mov     rbx, [rbx-8]
0x1801986ea  xor     ecx, ecx
0x1801986ec  test    rbx, rbx
0x1801986ef  jz      short loc_180198736
0x1801986f1  mov     rcx, [rbx]
0x1801986f4  mov     edx, edi
0x1801986f6  mov     rax, [rcx+20h]
0x1801986fa  mov     rcx, rbx
0x1801986fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198702  neg     eax
0x180198704  mov     [rsp+50h+var_28], edi
0x180198708  lea     r9, aCfcacquirerloc_2; "CFCAcquirerLocalRepository::CopyPayload"...
0x18019870f  mov     [rsp+50h+var_30], 136h
0x180198717  sbb     edx, edx
0x180198719  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180198720  add     edx, 4
0x180198723  mov     rcx, rbx
0x180198726  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18019872b  mov     ecx, eax
0x18019872d  test    eax, eax
0x18019872f  jns     short loc_180198736
0x180198731  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180198736  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019873b  mov     r13, [rbp+var_20]
0x18019873f  jmp     loc_1801989CB
0x180198744  mov     r13, [rbp+var_20]
0x180198748  mov     rcx, r13
0x18019874b  call    FileExists
0x180198750  test    eax, eax
0x180198752  jz      short loc_180198778
0x180198754  mov     rcx, [rbx-8]
0x180198758  test    rcx, rcx
0x18019875b  jz      short loc_180198771
0x18019875d  mov     r9, r14
0x180198760  lea     r8, aTargetFileAlre; "Target file already exists. Skipping co"...
0x180198767  mov     edx, 2
0x18019876c  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180198771  xor     edi, edi
0x180198773  jmp     loc_1801989CB
0x180198778  mov     rcx, [rbx+8]
0x18019877c  lea     r9, [rbp+lpFileName]
0x180198780  xor     r8d, r8d
0x180198783  mov     rdx, r14
0x180198786  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18019878b  mov     edi, eax
0x18019878d  test    eax, eax
0x18019878f  jns     short loc_1801987EF
0x180198791  mov     rbx, [rbx-8]
0x180198795  xor     ecx, ecx
0x180198797  test    rbx, rbx
0x18019879a  jz      short loc_1801987E1
0x18019879c  mov     rax, [rbx]
0x18019879f  mov     edx, edi
0x1801987a1  mov     rcx, rbx
0x1801987a4  mov     rax, [rax+20h]
0x1801987a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801987ad  neg     eax
0x1801987af  mov     [rsp+50h+var_28], edi
0x1801987b3  lea     r9, aCfcacquirerloc_2; "CFCAcquirerLocalRepository::CopyPayload"...
0x1801987ba  mov     [rsp+50h+var_30], 13Fh
0x1801987c2  sbb     edx, edx
0x1801987c4  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1801987cb  add     edx, 4
0x1801987ce  mov     rcx, rbx
0x1801987d1  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x1801987d6  mov     ecx, eax
0x1801987d8  test    eax, eax
0x1801987da  jns     short loc_1801987E1
0x1801987dc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1801987e1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801987e6  mov     rsi, [rbp+lpFileName]
0x1801987ea  jmp     loc_1801989CB
0x1801987ef  mov     rsi, [rbp+lpFileName]
0x1801987f3  mov     rcx, rsi; lpFileName
0x1801987f6  call    cs:__imp_GetFileAttributesW
0x1801987fd  nop     dword ptr [rax+rax+00h]
0x180198802  mov     edi, eax
0x180198804  cmp     eax, 0FFFFFFFFh
0x180198807  jz      short loc_180198813
0x180198809  shr     edi, 4
0x18019880c  not     edi
0x18019880e  and     edi, 1
0x180198811  jmp     short loc_180198815
0x180198813  xor     edi, edi
0x180198815  xor     ecx, ecx
0x180198817  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019881c  xor     ecx, ecx
0x18019881e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180198823  test    edi, edi
0x180198825  jnz     short loc_18019885D
0x180198827  mov     rbx, [rbx-8]
0x18019882b  xor     ecx, ecx
0x18019882d  mov     edi, 80070002h
0x180198832  test    rbx, rbx
0x180198835  jz      loc_1801989C6
0x18019883b  mov     rax, [rbx]
0x18019883e  mov     edx, edi
0x180198840  mov     rcx, rbx
0x180198843  mov     rax, [rax+20h]
0x180198847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019884c  mov     [rsp+50h+var_28], edi
0x180198850  mov     [rsp+50h+var_30], 141h
0x180198858  jmp     loc_18019899E
0x18019885d  lea     r9, [rbp+lpNewFileName]
0x180198861  xor     r8d, r8d
0x180198864  mov     rdx, r14
0x180198867  mov     rcx, r12
0x18019886a  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18019886f  mov     edi, eax
0x180198871  test    eax, eax
0x180198873  jns     short loc_1801988D3
0x180198875  mov     rbx, [rbx-8]
0x180198879  xor     ecx, ecx
0x18019887b  test    rbx, rbx
0x18019887e  jz      short loc_1801988C5
0x180198880  mov     rax, [rbx]
0x180198883  mov     edx, edi
0x180198885  mov     rcx, rbx
0x180198888  mov     rax, [rax+20h]
0x18019888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198891  neg     eax
0x180198893  mov     [rsp+50h+var_28], edi
0x180198897  lea     r9, aCfcacquirerloc_2; "CFCAcquirerLocalRepository::CopyPayload"...
0x18019889e  mov     [rsp+50h+var_30], 143h
0x1801988a6  sbb     edx, edx
0x1801988a8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1801988af  add     edx, 4
0x1801988b2  mov     rcx, rbx
0x1801988b5  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x1801988ba  mov     ecx, eax
0x1801988bc  test    eax, eax
0x1801988be  jns     short loc_1801988C5
0x1801988c0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1801988c5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801988ca  mov     r15, [rbp+lpNewFileName]
0x1801988ce  jmp     loc_1801989CB
0x1801988d3  mov     rcx, [rbx-8]
0x1801988d7  test    rcx, rcx
0x1801988da  jz      short loc_1801988F0
0x1801988dc  mov     r9, rsi
0x1801988df  lea     r8, aFcacquirerloca_6; "FCAcquirerLocalRepository: Copying file"...
0x1801988e6  mov     edx, 2
0x1801988eb  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x1801988f0  mov     r15, [rbp+lpNewFileName]
0x1801988f4  xor     r8d, r8d; bFailIfExists
0x1801988f7  mov     rdx, r15; lpNewFileName
0x1801988fa  mov     rcx, rsi; lpExistingFileName
0x1801988fd  call    cs:__imp_CopyFileW
0x180198904  nop     dword ptr [rax+rax+00h]
0x180198909  test    eax, eax
0x18019890b  jnz     short loc_180198968
0x18019890d  call    cs:__imp_GetLastError
0x180198914  nop     dword ptr [rax+rax+00h]
0x180198919  mov     edi, eax
0x18019891b  test    eax, eax
0x18019891d  jnz     short loc_180198928
0x18019891f  mov     edi, 80004005h
0x180198924  xor     ecx, ecx
0x180198926  jmp     short loc_18019893D
0x180198928  jle     short loc_180198933
0x18019892a  movzx   edi, ax
0x18019892d  or      edi, 80070000h
0x180198933  xor     ecx, ecx
0x180198935  test    edi, edi
0x180198937  jns     loc_1801989C6
0x18019893d  mov     rbx, [rbx-8]
0x180198941  mov     r14d, edi
0x180198944  test    rbx, rbx
0x180198947  jz      short loc_1801989C6
0x180198949  mov     rax, [rbx]
0x18019894c  mov     edx, edi
0x18019894e  mov     rcx, rbx
0x180198951  mov     rax, [rax+20h]
0x180198955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019895a  mov     [rsp+50h+var_28], edi
0x18019895e  mov     [rsp+50h+var_30], 146h
0x180198966  jmp     short loc_18019899E
0x180198968  mov     rcx, r15; lpFileName
0x18019896b  call    ?CheckAndClearFileAttribute@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGK@Z; CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(ushort const *,ulong)
0x180198970  mov     edi, eax
0x180198972  test    eax, eax
0x180198974  jns     short loc_1801989CB
0x180198976  mov     rbx, [rbx-8]
0x18019897a  xor     ecx, ecx
0x18019897c  test    rbx, rbx
0x18019897f  jz      short loc_1801989C6
0x180198981  mov     rax, [rbx]
0x180198984  mov     edx, edi
0x180198986  mov     rcx, rbx
0x180198989  mov     rax, [rax+20h]
0x18019898d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198992  mov     [rsp+50h+var_28], edi
0x180198996  mov     [rsp+50h+var_30], 147h
0x18019899e  neg     eax
0x1801989a0  lea     r9, aCfcacquirerloc_2; "CFCAcquirerLocalRepository::CopyPayload"...
0x1801989a7  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1801989ae  mov     rcx, rbx
0x1801989b1  sbb     edx, edx
0x1801989b3  add     edx, 4
0x1801989b6  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x1801989bb  mov     ecx, eax
0x1801989bd  test    eax, eax
0x1801989bf  jns     short loc_1801989C6
0x1801989c1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1801989c6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801989cb  mov     ecx, edi
0x1801989cd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1801989d2  test    r13, r13
0x1801989d5  jz      short loc_1801989FF
0x1801989d7  call    cs:__imp_GetProcessHeap
0x1801989de  nop     dword ptr [rax+rax+00h]
0x1801989e3  lea     r8, [r13-4]; lpMem
  ... truncated ...
```
