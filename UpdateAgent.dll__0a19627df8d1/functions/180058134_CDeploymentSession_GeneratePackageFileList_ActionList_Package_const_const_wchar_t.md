# CDeploymentSession::GeneratePackageFileList(ActionList::Package const * const,wchar_t * *)

- ea: `0x180058134`
- end: `0x1800585bf`
- name: `?GeneratePackageFileList@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z`
- size: `1163`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, const struct ActionList::Package *const, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180062e60`

## callees

- `0x1800059d0`
- `0x180009660`
- `0x180039f90`
- `0x18003c418`
- `0x180058134`
- `0x180077664`
- `0x180078b9c`
- `0x18008c4c4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005832d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005832d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800582c4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800582c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005856c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005856c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005854b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180058581`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005854b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180058581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005833d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005833d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800583d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800583d2`

## string_xrefs

- `0x18005821b`: `PFL_%s.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDeploymentSession::GeneratePackageFileList(
        CDeploymentSession *this,
        const struct ActionList::Package *a2,
        wchar_t **a3)
{
  wchar_t *v5; // r14
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 updated; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  DWORD FileAttributesW; // eax
  BOOL v15; // esi
  __int64 v16; // rcx
  signed int LastError; // eax
  HRESULT v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  LPVOID v21; // rcx
  char v22; // r8
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  wchar_t *v26; // rax
  const char *v27; // r9
  LPCWSTR v28; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v30; // rax
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-A8h]
  LPVOID *ppva; // [rsp+20h] [rbp-A8h]
  int v34; // [rsp+28h] [rbp-A0h]
  wchar_t *v35; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v36[6]; // [rsp+38h] [rbp-90h] BYREF
  __int64 v37; // [rsp+68h] [rbp-60h] BYREF
  const struct ActionList::Package *v38; // [rsp+70h] [rbp-58h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-50h] BYREF
  int v40; // [rsp+80h] [rbp-48h] BYREF
  LPVOID v41; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v36[5] = -2;
  try
  {
    v38 = a2;
    v40 = 0;
    v5 = 0;
    v35 = 0;
    lpFileName = 0;
    v37 = 0;
    if ( !a2 )
    {
      v6 = *((_QWORD *)this + 75);
      v7 = -2147024809;
      if ( !v6 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_53:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
        v28 = lpFileName;
        if ( lpFileName )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v28 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          lpFileName = 0;
        }
        if ( v5 )
        {
          v30 = GetProcessHeap();
          HeapFree(v30, 0, v5 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        return v7;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v6,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GeneratePackageFileList",
                                2887,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
      goto LABEL_8;
    }
    if ( !a3 )
    {
      v9 = *((_QWORD *)this + 75);
      v7 = -2147024809;
      if ( !v9 )
        goto LABEL_4;
      v34 = -2147024809;
      ppv = 2888;
      goto LABEL_12;
    }
    v37 = *((_QWORD *)a2 + 7);
    v10 = STRAPI_Format(&v35, L"PFL_%s.xml");
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = *((_QWORD *)this + 75);
      if ( v11 )
      {
        v12 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v11,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::GeneratePackageFileList",
                2891,
                v10);
        v11 = (unsigned int)v12;
        if ( v12 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      v5 = v35;
      goto LABEL_53;
    }
    v5 = v35;
    v13 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)v35, 0);
    v7 = v13;
    if ( v13 < 0 )
    {
      v9 = *((_QWORD *)this + 75);
      if ( !v9 )
        goto LABEL_4;
      v34 = v13;
      ppv = 2892;
      goto LABEL_12;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    v15 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( *((_DWORD *)this + 66) )
    {
      if ( v15 )
      {
        v16 = *((_QWORD *)this + 75);
        if ( v16 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v16, 2, L"Deleting previous PackageFileList: [%s].", lpFileName);
        if ( !DeleteFileW(lpFileName) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v7 = -2147467259;
          }
          updated = 0;
          if ( (v7 & 0x80000000) == 0 || !*((_QWORD *)this + 75) )
            goto LABEL_8;
          v34 = v7;
          ppv = 2898;
          v9 = *((_QWORD *)this + 75);
LABEL_12:
          updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                    v9,
                                    4,
                                    L"%s(%d): Result = 0x%X",
                                    L"CDeploymentSession::GeneratePackageFileList",
                                    ppv,
                                    v34);
          goto LABEL_6;
        }
        *((_DWORD *)this + 67) = 1;
      }
    }
    else
    {
      v7 = 0;
      if ( v15 )
        goto LABEL_52;
    }
    v41 = 0;
    v18 = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &v41);
    v7 = v18;
    if ( v18 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( v19 )
      {
        LODWORD(ppva) = 2905;
        v20 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v19,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::GeneratePackageFileList",
                ppva,
                v18);
        v19 = (unsigned int)v20;
        if ( v20 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
      v21 = v41;
      if ( !v41 )
        goto LABEL_53;
      goto LABEL_43;
    }
    v22 = *((_QWORD *)this + 70) != 0;
    v36[0] = this;
    v36[1] = &v40;
    v36[2] = &v38;
    v36[3] = &v37;
    v36[4] = &lpFileName;
    v23 = Z::InvokeInContext<`CDeploymentSession::GeneratePackageFileList'::`48'::_lambda_1_,ActionList::AJQEBUPackage * const,wchar_t * *>(
            (__int64)v41,
            (__int64)v36,
            v22);
    v7 = v23;
    if ( v23 < 0 )
    {
      v24 = *((_QWORD *)this + 75);
      if ( v24 )
      {
        LODWORD(ppva) = 3029;
        v25 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v24,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::GeneratePackageFileList",
                ppva,
                v23);
        v24 = (unsigned int)v25;
        if ( v25 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v25);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
      v21 = v41;
      if ( !v41 )
        goto LABEL_53;
LABEL_43:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v21);
      goto LABEL_53;
    }
    if ( v41 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_52:
    v26 = (wchar_t *)lpFileName;
    lpFileName = 0;
    *a3 = v26;
    goto LABEL_53;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBDB,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x180058134  mov     r11, rsp
0x180058137  push    rbx
0x180058138  push    rsi
0x180058139  push    rdi
0x18005813a  push    r14
0x18005813c  push    r15
0x18005813e  sub     rsp, 0A0h
0x180058145  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x18005814d  mov     rax, cs:__security_cookie
0x180058154  xor     rax, rsp
0x180058157  mov     [rsp+0C8h+var_38], rax
0x18005815f  mov     r15, r8
0x180058162  mov     rbx, rcx
0x180058165  mov     [r11-58h], rdx
0x180058169  mov     dword ptr [r11-48h], 0
0x180058171  xor     r14d, r14d
0x180058174  mov     [rsp+0C8h+var_98], r14
0x180058179  mov     [r11-50h], r14
0x18005817d  mov     [r11-60h], r14
0x180058181  test    rdx, rdx
0x180058184  jnz     short loc_1800581D4
0x180058186  mov     rcx, [rcx+258h]
0x18005818d  mov     edi, 80070057h
0x180058192  test    rcx, rcx
0x180058195  jnz     short loc_18005819B
0x180058197  xor     ecx, ecx
0x180058199  jmp     short loc_1800581CA
0x18005819b  mov     [rsp+0C8h+var_A0], edi
0x18005819f  mov     dword ptr [rsp+0C8h+ppv], 0B47h
0x1800581a7  lea     r9, aCdeploymentses_63; "CDeploymentSession::GeneratePackageFile"...
0x1800581ae  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800581b5  mov     edx, 4
0x1800581ba  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800581bf  mov     ecx, eax
0x1800581c1  test    ecx, ecx
0x1800581c3  jns     short loc_1800581CA
0x1800581c5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800581ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800581cf  jmp     loc_180058524
0x1800581d4  test    r15, r15
0x1800581d7  jnz     short loc_180058212
0x1800581d9  mov     rcx, [rcx+258h]
0x1800581e0  mov     edi, 80070057h
0x1800581e5  test    rcx, rcx
0x1800581e8  jz      short loc_180058197
0x1800581ea  mov     [rsp+0C8h+var_A0], edi
0x1800581ee  mov     dword ptr [rsp+0C8h+ppv], 0B48h
0x1800581f6  mov     edx, 4
0x1800581fb  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180058202  lea     r9, aCdeploymentses_63; "CDeploymentSession::GeneratePackageFile"...
0x180058209  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18005820e  mov     ecx, eax
0x180058210  jmp     short loc_1800581C1
0x180058212  mov     r8, [rdx+38h]
0x180058216  mov     [rsp+0C8h+var_60], r8
0x18005821b  lea     rdx, aPflSXml; "PFL_%s.xml"
0x180058222  lea     rcx, [rsp+0C8h+var_98]; wchar_t **
0x180058227  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18005822c  mov     edi, eax
0x18005822e  test    eax, eax
0x180058230  jns     short loc_18005827C
0x180058232  mov     rcx, [rbx+258h]
0x180058239  test    rcx, rcx
0x18005823c  jz      short loc_18005826D
0x18005823e  mov     [rsp+0C8h+var_A0], eax
0x180058242  mov     dword ptr [rsp+0C8h+ppv], 0B4Bh
0x18005824a  lea     r9, aCdeploymentses_63; "CDeploymentSession::GeneratePackageFile"...
0x180058251  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180058258  mov     edx, 4
0x18005825d  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180058262  mov     ecx, eax
0x180058264  test    eax, eax
0x180058266  jns     short loc_18005826D
0x180058268  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005826d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180058272  mov     r14, [rsp+0C8h+var_98]
0x180058277  jmp     loc_180058524
0x18005827c  mov     r14, [rsp+0C8h+var_98]
0x180058281  lea     r9, [rsp+0C8h+lpFileName]
0x180058286  xor     r8d, r8d
0x180058289  mov     rdx, r14
0x18005828c  mov     rcx, [rbx+1E8h]
0x180058293  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180058298  mov     edi, eax
0x18005829a  test    eax, eax
0x18005829c  jns     short loc_1800582BF
0x18005829e  mov     rcx, [rbx+258h]
0x1800582a5  test    rcx, rcx
0x1800582a8  jz      loc_180058197
0x1800582ae  mov     [rsp+0C8h+var_A0], eax
0x1800582b2  mov     dword ptr [rsp+0C8h+ppv], 0B4Ch
0x1800582ba  jmp     loc_1800581F6
0x1800582bf  mov     rcx, [rsp+0C8h+lpFileName]; lpFileName
0x1800582c4  call    cs:__imp_GetFileAttributesW
0x1800582cb  nop     dword ptr [rax+rax+00h]
0x1800582d0  mov     esi, eax
0x1800582d2  cmp     eax, 0FFFFFFFFh
0x1800582d5  jz      short loc_1800582E1
0x1800582d7  shr     esi, 4
0x1800582da  not     esi
0x1800582dc  and     esi, 1
0x1800582df  jmp     short loc_1800582E3
0x1800582e1  xor     esi, esi
0x1800582e3  xor     ecx, ecx
0x1800582e5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800582ea  xor     ecx, ecx
0x1800582ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800582f1  cmp     dword ptr [rbx+108h], 0
0x1800582f8  jz      loc_18005839B
0x1800582fe  test    esi, esi
0x180058300  jz      loc_1800583A5
0x180058306  mov     rcx, [rbx+258h]
0x18005830d  test    rcx, rcx
0x180058310  jz      short loc_180058328
0x180058312  mov     r9, [rsp+0C8h+lpFileName]
0x180058317  lea     r8, aDeletingPrevio; "Deleting previous PackageFileList: [%s]"...
0x18005831e  mov     edx, 2
0x180058323  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180058328  mov     rcx, [rsp+0C8h+lpFileName]; lpFileName
0x18005832d  call    cs:__imp_DeleteFileW
0x180058334  nop     dword ptr [rax+rax+00h]
0x180058339  test    eax, eax
0x18005833b  jnz     short loc_18005838F
0x18005833d  call    cs:__imp_GetLastError
0x180058344  nop     dword ptr [rax+rax+00h]
0x180058349  mov     edi, eax
0x18005834b  test    eax, eax
0x18005834d  jnz     short loc_180058356
0x18005834f  mov     edi, 80004005h
0x180058354  jmp     short loc_180058361
0x180058356  jle     short loc_180058361
0x180058358  movzx   edi, ax
0x18005835b  or      edi, 80070000h
0x180058361  mov     rax, [rbx+258h]
0x180058368  xor     ecx, ecx
0x18005836a  test    edi, edi
0x18005836c  jns     loc_1800581CA
0x180058372  test    rax, rax
0x180058375  jz      loc_1800581CA
0x18005837b  mov     [rsp+0C8h+var_A0], edi
0x18005837f  mov     dword ptr [rsp+0C8h+ppv], 0B52h
0x180058387  mov     rcx, rax
0x18005838a  jmp     loc_1800581F6
0x18005838f  mov     dword ptr [rbx+10Ch], 1
0x180058399  jmp     short loc_1800583A5
0x18005839b  xor     edi, edi
0x18005839d  test    esi, esi
0x18005839f  jnz     loc_180058513
0x1800583a5  mov     [rsp+0C8h+var_40], 0
0x1800583b1  lea     rax, [rsp+0C8h+var_40]
0x1800583b9  mov     [rsp+0C8h+ppv], rax; ppv
0x1800583be  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800583c5  xor     edx, edx; pUnkOuter
0x1800583c7  lea     r8d, [rdx+1]; dwClsContext
0x1800583cb  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800583d2  call    cs:__imp_CoCreateInstance
0x1800583d9  nop     dword ptr [rax+rax+00h]
0x1800583de  mov     edi, eax
0x1800583e0  test    eax, eax
0x1800583e2  jns     short loc_180058448
0x1800583e4  mov     rcx, [rbx+258h]
0x1800583eb  test    rcx, rcx
0x1800583ee  jz      short loc_18005841F
0x1800583f0  mov     [rsp+0C8h+var_A0], eax
0x1800583f4  mov     dword ptr [rsp+0C8h+ppv], 0B59h
0x1800583fc  lea     r9, aCdeploymentses_63; "CDeploymentSession::GeneratePackageFile"...
0x180058403  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18005840a  mov     edx, 4
0x18005840f  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180058414  mov     ecx, eax
0x180058416  test    eax, eax
0x180058418  jns     short loc_18005841F
0x18005841a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005841f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180058424  nop
0x180058425  mov     rcx, [rsp+0C8h+var_40]
0x18005842d  test    rcx, rcx
0x180058430  jz      loc_180058524
0x180058436  mov     rax, [rcx]
0x180058439  mov     rax, [rax+10h]
0x18005843d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058442  nop
0x180058443  jmp     loc_180058524
0x180058448  cmp     qword ptr [rbx+230h], 0
0x180058450  setnz   r8b
0x180058454  mov     [rsp+0C8h+var_90], rbx
0x180058459  lea     rax, [rsp+0C8h+var_48]
0x180058461  mov     [rsp+0C8h+var_88], rax
0x180058466  lea     rax, [rsp+0C8h+var_58]
0x18005846b  mov     [rsp+0C8h+var_80], rax
0x180058470  lea     rax, [rsp+0C8h+var_60]
0x180058475  mov     [rsp+0C8h+var_78], rax
0x18005847a  lea     rax, [rsp+0C8h+lpFileName]
0x18005847f  mov     [rsp+0C8h+var_70], rax
0x180058484  lea     rdx, [rsp+0C8h+var_90]
0x180058489  mov     rcx, [rsp+0C8h+var_40]
0x180058491  call    ??$InvokeInContext@V_lambda_1_@?DA@??GeneratePackageFileList@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z@@UpdateAgentMisc@@YAJPEAUIContextCallback@@$$QEAV_lambda_1_@?DA@??GeneratePackageFileList@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z@_N@Z; UpdateAgentMisc::InvokeInContext<`CDeploymentSession::GeneratePackageFileList(ActionList::Package const * const,wchar_t * *)'::`48'::_lambda_1_>(IContextCallback *,`CDeploymentSession::GeneratePackageFileList(ActionList::Package const * const,wchar_t * *)'::`48'::_lambda_1_ &&,bool)
0x180058496  mov     edi, eax
0x180058498  test    eax, eax
0x18005849a  jns     short loc_1800584F9
0x18005849c  mov     rcx, [rbx+258h]
0x1800584a3  test    rcx, rcx
0x1800584a6  jz      short loc_1800584D7
0x1800584a8  mov     [rsp+0C8h+var_A0], eax
0x1800584ac  mov     dword ptr [rsp+0C8h+ppv], 0BD5h
0x1800584b4  lea     r9, aCdeploymentses_63; "CDeploymentSession::GeneratePackageFile"...
0x1800584bb  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800584c2  mov     edx, 4
0x1800584c7  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800584cc  mov     ecx, eax
0x1800584ce  test    eax, eax
0x1800584d0  jns     short loc_1800584D7
0x1800584d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800584d7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800584dc  nop
0x1800584dd  mov     rcx, [rsp+0C8h+var_40]
0x1800584e5  test    rcx, rcx
0x1800584e8  jz      short loc_180058524
0x1800584ea  mov     rax, [rcx]
0x1800584ed  mov     rax, [rax+10h]
0x1800584f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584f6  nop
0x1800584f7  jmp     short loc_180058524
0x1800584f9  mov     rcx, [rsp+0C8h+var_40]
0x180058501  test    rcx, rcx
0x180058504  jz      short loc_180058513
0x180058506  mov     rax, [rcx]
0x180058509  mov     rax, [rax+10h]
0x18005850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058512  nop
0x180058513  mov     rax, [rsp+0C8h+lpFileName]
0x180058518  mov     [rsp+0C8h+lpFileName], 0
0x180058521  mov     [r15], rax
0x180058524  mov     ecx, edi
0x180058526  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005852b  nop
0x18005852c  mov     rbx, [rsp+0C8h+lpFileName]
0x180058531  test    rbx, rbx
0x180058534  jz      short loc_180058567
0x180058536  call    cs:__imp_GetProcessHeap
0x18005853d  nop     dword ptr [rax+rax+00h]
0x180058542  mov     rcx, rax; hHeap
0x180058545  lea     r8, [rbx-4]; lpMem
0x180058549  xor     edx, edx; dwFlags
0x18005854b  call    cs:__imp_HeapFree
0x180058552  nop     dword ptr [rax+rax+00h]
0x180058557  xor     ecx, ecx
0x180058559  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005855e  mov     [rsp+0C8h+lpFileName], 0
0x180058567  test    r14, r14
0x18005856a  jz      short loc_180058594
0x18005856c  call    cs:__imp_GetProcessHeap
0x180058573  nop     dword ptr [rax+rax+00h]
0x180058578  mov     rcx, rax; hHeap
0x18005857b  lea     r8, [r14-4]; lpMem
0x18005857f  xor     edx, edx; dwFlags
0x180058581  call    cs:__imp_HeapFree
0x180058588  nop     dword ptr [rax+rax+00h]
0x18005858d  xor     ecx, ecx
0x18005858f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180058594  mov     eax, edi
0x180058596  jmp     short loc_18005859F
0x180058598  mov     eax, [rsp+0C8h+var_48]
0x18005859f  mov     rcx, [rsp+0C8h+var_38]
0x1800585a7  xor     rcx, rsp; StackCookie
0x1800585aa  call    __security_check_cookie
0x1800585af  add     rsp, 0A0h
0x1800585b6  pop     r15
0x1800585b8  pop     r14
0x1800585ba  pop     rdi
0x1800585bb  pop     rsi
0x1800585bc  pop     rbx
0x1800585bd  retn
```
