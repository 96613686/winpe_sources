# WindowsMidiServicesInternal::IsFileCatalogSigned(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800446f4`
- end: `0x180044b10`
- name: `?IsFileCatalogSigned@WindowsMidiServicesInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180044458`

## callees

- `0x180005020`
- `0x180005044`
- `0x180005824`
- `0x180005e9c`
- `0x18000b374`
- `0x18000b394`
- `0x1800446f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180044947`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180044947`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004487b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004487b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044acb`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180044995`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180044995`
- `WINTRUST!WinVerifyTrust` at `0x1800449d2`
- `WINTRUST!WinVerifyTrust` at `0x1800449eb`
- `WINTRUST!WinVerifyTrust` at `0x180044a52`
- `WINTRUST!WinVerifyTrust` at `0x1800449d2`
- `WINTRUST!WinVerifyTrust` at `0x1800449eb`
- `WINTRUST!WinVerifyTrust` at `0x180044a52`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044864`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044888`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044a42`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044a78`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044add`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044864`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044888`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044a42`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044a78`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180044add`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800448a9`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800448a9`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800448d5`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180044a10`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800448d5`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180044a10`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800447d1`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180044822`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800447d1`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180044822`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800447ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800447ad`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::IsFileCatalogSigned(wchar_t *Str)
{
  const WCHAR *v2; // rcx
  char *FileW; // rbx
  const char *v4; // r9
  const char *v5; // r9
  unsigned int LastError; // edi
  BYTE *v7; // rax
  BYTE *v8; // rdi
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // esi
  HCATADMIN v13; // r15
  DWORD v14; // esi
  HCATINFO v15; // rsi
  bool v16; // cc
  const wchar_t *v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  LONG v20; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  HCATADMIN hCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HCATINFO phPrevCatInfo[2]; // [rsp+50h] [rbp-B0h] BYREF
  int pWVTData; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h]
  int *v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR *wszCatalogFile; // [rsp+C8h] [rbp-38h]
  wchar_t *v33; // [rsp+D0h] [rbp-30h]
  BYTE *v34; // [rsp+E8h] [rbp-18h]
  DWORD v35; // [rsp+F0h] [rbp-10h]
  GUID pgActionID; // [rsp+110h] [rbp+10h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v38[276]; // [rsp+330h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7B8h] [rbp+6B8h]

  pcbHash = 0;
  hCatAdmin = 0;
  phPrevCatInfo[0] = 0;
  memset_0(v38, 0, sizeof(v38));
  memset_0(&pWVTData, 0, 0x58u);
  memset_0(&v31, 0, 0x48u);
  if ( *((_QWORD *)Str + 3) <= 7u )
    v2 = Str;
  else
    v2 = *(const WCHAR **)Str;
  FileW = (char *)CreateFileW(v2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x49,
                  (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
                  v4);
LABEL_41:
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return LastError;
  }
  if ( !CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, 0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
                  v5);
LABEL_40:
    CloseHandle(FileW);
    goto LABEL_41;
  }
  v7 = (BYTE *)operator new[](pcbHash, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    goto LABEL_40;
  }
  if ( !CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, v7, 0) )
  {
    v10 = 83;
LABEL_10:
    v11 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v10,
            (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
            v9);
    CloseHandle(FileW);
    operator delete(v8);
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return v11;
  }
  v13 = hCatAdmin;
  if ( hCatAdmin )
  {
    v14 = GetLastError();
    CryptCATAdminReleaseContext(v13, 0);
    SetLastError(v14);
  }
  hCatAdmin = 0;
  if ( !CryptCATAdminAcquireContext(&hCatAdmin, 0, 0) )
  {
    v10 = 86;
    goto LABEL_10;
  }
  v15 = CryptCATAdminEnumCatalogFromHash(hCatAdmin, v8, pcbHash, 0, phPrevCatInfo);
  if ( v15 == (HCATINFO)-1LL )
  {
    v10 = 93;
    goto LABEL_10;
  }
  v16 = *((_QWORD *)Str + 3) <= 7u;
  v26 = v38;
  v38[0] = 1104;
  v29 = &v31;
  v35 = pcbHash;
  pWVTData = 88;
  v27 = 2;
  v28 = 2;
  v31 = 72;
  v34 = v8;
  if ( v16 )
    v17 = Str;
  else
    v17 = *(const wchar_t **)Str;
  v18 = wcsrchr(v17, 0x5Cu);
  if ( v18 )
  {
    v19 = v18 + 1;
  }
  else if ( *((_QWORD *)Str + 3) <= 7u )
  {
    v19 = Str;
  }
  else
  {
    v19 = *(wchar_t **)Str;
  }
  v33 = v19;
  if ( !v15 )
  {
LABEL_32:
    CloseHandle(FileW);
    operator delete(v8);
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return 2147500037LL;
  }
  while ( 1 )
  {
    memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
    psCatInfo.cbStruct = 524;
    if ( CryptCATCatalogInfoFromContext(v15, &psCatInfo, 0) )
      break;
LABEL_31:
    phPrevCatInfo[0] = v15;
    v15 = CryptCATAdminEnumCatalogFromHash(hCatAdmin, v8, pcbHash, 0, phPrevCatInfo);
    if ( !v15 )
      goto LABEL_32;
  }
  pgActionID.Data1 = -145692989;
  wszCatalogFile = psCatInfo.wszCatalogFile;
  *(_DWORD *)&pgActionID.Data2 = 298924270;
  *(_DWORD *)pgActionID.Data4 = -1073683067;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  v30 = 1;
  v20 = WinVerifyTrust(0, &pgActionID, &pWVTData);
  v30 = 2;
  if ( v20 )
  {
    WinVerifyTrust(0, &pgActionID, &pWVTData);
    goto LABEL_31;
  }
  WinVerifyTrust(0, &pgActionID, &pWVTData);
  CloseHandle(FileW);
  operator delete(v8);
  if ( hCatAdmin )
    CryptCATAdminReleaseContext(hCatAdmin, 0);
  return 0;
}

```

## disassembly

```asm
0x1800446f4  mov     [rsp-8+arg_8], rbx
0x1800446f9  mov     [rsp-8+arg_10], rsi
0x1800446fe  push    rbp
0x1800446ff  push    rdi
0x180044700  push    r13
0x180044702  push    r14
0x180044704  push    r15
0x180044706  lea     rbp, [rsp-690h]
0x18004470e  sub     rsp, 790h
0x180044715  mov     rax, cs:__security_cookie
0x18004471c  xor     rax, rsp
0x18004471f  mov     [rbp+6B0h+var_30], rax
0x180044726  mov     r14, rcx
0x180044729  mov     [rsp+7B0h+pcbHash], 0
0x180044731  lea     rcx, [rbp+6B0h+var_480]; void *
0x180044738  mov     [rsp+7B0h+hCatAdmin], 0
0x180044741  xor     edx, edx; Val
0x180044743  mov     [rsp+7B0h+phPrevCatInfo], 0
0x18004474c  mov     r8d, 450h; Size
0x180044752  call    memset_0
0x180044757  xor     edx, edx; Val
0x180044759  lea     rcx, [rsp+7B0h+pWVTData]; void *
0x18004475e  lea     r8d, [rdx+58h]; Size
0x180044762  call    memset_0
0x180044767  xor     edx, edx; Val
0x180044769  lea     rcx, [rbp+6B0h+var_6F0]; void *
0x18004476d  lea     r8d, [rdx+48h]; Size
0x180044771  call    memset_0
0x180044776  cmp     qword ptr [r14+18h], 7
0x18004477b  jbe     short loc_180044782
0x18004477d  mov     rcx, [r14]
0x180044780  jmp     short loc_180044785
0x180044782  mov     rcx, r14; lpFileName
0x180044785  xor     r9d, r9d; lpSecurityAttributes
0x180044788  mov     [rsp+7B0h+hTemplateFile], 0; hTemplateFile
0x180044791  mov     [rsp+7B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180044799  mov     edx, 80000000h; dwDesiredAccess
0x18004479e  mov     [rsp+7B0h+dwCreationDisposition], 3; int
0x1800447a6  lea     r13d, [r9+1]
0x1800447aa  mov     r8d, r13d; dwShareMode
0x1800447ad  call    cs:__imp_CreateFileW
0x1800447b3  mov     rbx, rax
0x1800447b6  dec     rax
0x1800447b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800447bd  ja      loc_180044AA4
0x1800447c3  xor     r9d, r9d; dwFlags
0x1800447c6  lea     rdx, [rsp+7B0h+pcbHash]; pcbHash
0x1800447cb  xor     r8d, r8d; pbHash
0x1800447ce  mov     rcx, rbx; hFile
0x1800447d1  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x1800447d7  test    eax, eax
0x1800447d9  jnz     short loc_1800447F8
0x1800447db  mov     rcx, [rbp+6B8h]; this
0x1800447e2  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x1800447e9  lea     edx, [rax+4Ch]; void *
0x1800447ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800447f1  mov     edi, eax
0x1800447f3  jmp     loc_180044AC8
0x1800447f8  mov     ecx, [rsp+7B0h+pcbHash]; unsigned __int64
0x1800447fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044803  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180044808  mov     rdi, rax
0x18004480b  test    rax, rax
0x18004480e  jz      loc_180044A82
0x180044814  xor     r9d, r9d; dwFlags
0x180044817  lea     rdx, [rsp+7B0h+pcbHash]; pcbHash
0x18004481c  mov     r8, rax; pbHash
0x18004481f  mov     rcx, rbx; hFile
0x180044822  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180044828  test    eax, eax
0x18004482a  jnz     short loc_180044871
0x18004482c  lea     edx, [rax+53h]; void *
0x18004482f  mov     rcx, [rbp+6B8h]; this
0x180044836  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x18004483d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044842  mov     rcx, rbx; hObject
0x180044845  mov     esi, eax
0x180044847  call    cs:__imp_CloseHandle
0x18004484d  mov     rdx, r13
0x180044850  mov     rcx, rdi; Block
0x180044853  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044858  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x18004485d  test    rcx, rcx
0x180044860  jz      short loc_18004486A
0x180044862  xor     edx, edx; dwFlags
0x180044864  call    cs:__imp_CryptCATAdminReleaseContext
0x18004486a  mov     eax, esi
0x18004486c  jmp     loc_180044AE5
0x180044871  mov     r15, [rsp+7B0h+hCatAdmin]
0x180044876  test    r15, r15
0x180044879  jz      short loc_180044896
0x18004487b  call    cs:__imp_GetLastError
0x180044881  xor     edx, edx; dwFlags
0x180044883  mov     rcx, r15; hCatAdmin
0x180044886  mov     esi, eax
0x180044888  call    cs:__imp_CryptCATAdminReleaseContext
0x18004488e  mov     ecx, esi; dwErrCode
0x180044890  call    cs:__imp_SetLastError
0x180044896  xor     r8d, r8d; dwFlags
0x180044899  mov     [rsp+7B0h+hCatAdmin], 0
0x1800448a2  xor     edx, edx; pgSubsystem
0x1800448a4  lea     rcx, [rsp+7B0h+hCatAdmin]; phCatAdmin
0x1800448a9  call    cs:__imp_CryptCATAdminAcquireContext
0x1800448af  test    eax, eax
0x1800448b1  jnz     short loc_1800448BB
0x1800448b3  lea     edx, [rax+56h]
0x1800448b6  jmp     loc_18004482F
0x1800448bb  mov     r8d, [rsp+7B0h+pcbHash]; cbHash
0x1800448c0  lea     rax, [rsp+7B0h+phPrevCatInfo]
0x1800448c5  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x1800448ca  xor     r9d, r9d; dwFlags
0x1800448cd  mov     rdx, rdi; pbHash
0x1800448d0  mov     qword ptr [rsp+7B0h+dwCreationDisposition], rax; phPrevCatInfo
0x1800448d5  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x1800448db  mov     rsi, rax
0x1800448de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800448e2  jnz     short loc_1800448EC
0x1800448e4  lea     edx, [rax+5Eh]
0x1800448e7  jmp     loc_18004482F
0x1800448ec  cmp     qword ptr [r14+18h], 7
0x1800448f1  lea     rax, [rbp+6B0h+var_480]
0x1800448f8  mov     [rsp+7B0h+var_748], rax
0x1800448fd  mov     r15d, 2
0x180044903  lea     rax, [rbp+6B0h+var_6F0]
0x180044907  mov     [rbp+6B0h+var_480], 450h
0x180044911  mov     [rbp+6B0h+var_728], rax
0x180044915  mov     eax, [rsp+7B0h+pcbHash]
0x180044919  mov     [rbp+6B0h+var_6C0], eax
0x18004491c  mov     [rsp+7B0h+pWVTData], 58h ; 'X'
0x180044924  mov     [rsp+7B0h+var_738], r15
0x180044929  mov     [rbp+6B0h+var_730], r15d
0x18004492d  mov     [rbp+6B0h+var_6F0], 48h ; 'H'
0x180044934  mov     [rbp+6B0h+var_6C8], rdi
0x180044938  jbe     short loc_18004493F
0x18004493a  mov     rcx, [r14]
0x18004493d  jmp     short loc_180044942
0x18004493f  mov     rcx, r14; Str
0x180044942  mov     edx, 5Ch ; '\'; Ch
0x180044947  call    cs:__imp_wcsrchr
0x18004494d  test    rax, rax
0x180044950  jnz     short loc_180044963
0x180044952  cmp     qword ptr [r14+18h], 7
0x180044957  jbe     short loc_18004495E
0x180044959  mov     rax, [r14]
0x18004495c  jmp     short loc_180044966
0x18004495e  mov     rax, r14
0x180044961  jmp     short loc_180044966
0x180044963  add     rax, r15
0x180044966  mov     [rbp+6B0h+var_6E0], rax
0x18004496a  test    rsi, rsi
0x18004496d  jz      loc_180044A22
0x180044973  xor     edx, edx; Val
0x180044975  lea     rcx, [rbp+6B0h+psCatInfo.wszCatalogFile]; void *
0x180044979  mov     r8d, 208h; Size
0x18004497f  call    memset_0
0x180044984  xor     r8d, r8d; dwFlags
0x180044987  mov     [rbp+6B0h+psCatInfo.cbStruct], 20Ch
0x18004498e  lea     rdx, [rbp+6B0h+psCatInfo]; psCatInfo
0x180044992  mov     rcx, rsi; hCatInfo
0x180044995  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18004499b  test    eax, eax
0x18004499d  jz      short loc_1800449F1
0x18004499f  lea     rax, [rbp+6B0h+psCatInfo.wszCatalogFile]
0x1800449a3  mov     [rbp+6B0h+pgActionID.Data1], 0F750E6C3h
0x1800449aa  lea     r8, [rsp+7B0h+pWVTData]; pWVTData
0x1800449af  mov     [rbp+6B0h+var_6E8], rax
0x1800449b3  lea     rdx, [rbp+6B0h+pgActionID]; pgActionID
0x1800449b7  mov     dword ptr [rbp+6B0h+pgActionID.Data2], 11D138EEh
0x1800449be  xor     ecx, ecx; hwnd
0x1800449c0  mov     dword ptr [rbp+6B0h+pgActionID.Data4], 0C000E585h
0x1800449c7  mov     dword ptr [rbp+6B0h+pgActionID.Data4+4], 0EE95C24Fh
0x1800449ce  mov     [rbp+6B0h+var_720], r13d
0x1800449d2  call    cs:__imp_WinVerifyTrust
0x1800449d8  xor     ecx, ecx; hwnd
0x1800449da  mov     [rbp+6B0h+var_720], r15d
0x1800449de  lea     r8, [rsp+7B0h+pWVTData]; pWVTData
0x1800449e3  lea     rdx, [rbp+6B0h+pgActionID]; pgActionID
0x1800449e7  test    eax, eax
0x1800449e9  jz      short loc_180044A52
0x1800449eb  call    cs:__imp_WinVerifyTrust
0x1800449f1  mov     r8d, [rsp+7B0h+pcbHash]; cbHash
0x1800449f6  lea     rax, [rsp+7B0h+phPrevCatInfo]
0x1800449fb  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x180044a00  xor     r9d, r9d; dwFlags
0x180044a03  mov     rdx, rdi; pbHash
0x180044a06  mov     qword ptr [rsp+7B0h+dwCreationDisposition], rax; phPrevCatInfo
0x180044a0b  mov     [rsp+7B0h+phPrevCatInfo], rsi
0x180044a10  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x180044a16  mov     rsi, rax
0x180044a19  test    rax, rax
0x180044a1c  jnz     loc_180044973
0x180044a22  mov     rcx, rbx; hObject
0x180044a25  call    cs:__imp_CloseHandle
0x180044a2b  mov     rdx, r13
0x180044a2e  mov     rcx, rdi; Block
0x180044a31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044a36  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x180044a3b  test    rcx, rcx
0x180044a3e  jz      short loc_180044A48
0x180044a40  xor     edx, edx; dwFlags
0x180044a42  call    cs:__imp_CryptCATAdminReleaseContext
0x180044a48  mov     eax, 80004005h
0x180044a4d  jmp     loc_180044AE5
0x180044a52  call    cs:__imp_WinVerifyTrust
0x180044a58  mov     rcx, rbx; hObject
0x180044a5b  call    cs:__imp_CloseHandle
0x180044a61  mov     rdx, r13
0x180044a64  mov     rcx, rdi; Block
0x180044a67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044a6c  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x180044a71  test    rcx, rcx
0x180044a74  jz      short loc_180044A7E
0x180044a76  xor     edx, edx; dwFlags
0x180044a78  call    cs:__imp_CryptCATAdminReleaseContext
0x180044a7e  xor     eax, eax
0x180044a80  jmp     short loc_180044AE5
0x180044a82  mov     rcx, [rbp+6B8h]; this
0x180044a89  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x180044a90  mov     edi, 8007000Eh
0x180044a95  mov     edx, 50h ; 'P'; void *
0x180044a9a  mov     r9d, edi; char *
0x180044a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044aa2  jmp     short loc_180044AC8
0x180044aa4  mov     rcx, [rbp+6B8h]; this
0x180044aab  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x180044ab2  mov     edx, 49h ; 'I'; void *
0x180044ab7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044abc  lea     rcx, [rbx-1]
0x180044ac0  mov     edi, eax
0x180044ac2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180044ac6  ja      short loc_180044AD1
0x180044ac8  mov     rcx, rbx; hObject
0x180044acb  call    cs:__imp_CloseHandle
0x180044ad1  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x180044ad6  test    rcx, rcx
0x180044ad9  jz      short loc_180044AE3
0x180044adb  xor     edx, edx; dwFlags
0x180044add  call    cs:__imp_CryptCATAdminReleaseContext
0x180044ae3  mov     eax, edi
0x180044ae5  mov     rcx, [rbp+6B0h+var_30]
0x180044aec  xor     rcx, rsp; StackCookie
0x180044aef  call    __security_check_cookie
0x180044af4  lea     r11, [rsp+7B0h+var_20]
0x180044afc  mov     rbx, [r11+38h]
0x180044b00  mov     rsi, [r11+40h]
0x180044b04  mov     rsp, r11
0x180044b07  pop     r15
0x180044b09  pop     r14
0x180044b0b  pop     r13
0x180044b0d  pop     rdi
0x180044b0e  pop     rbp
0x180044b0f  retn
```
