# WindowsMidiServicesInternal::IsFileCatalogSigned(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140025554`
- end: `0x140025970`
- name: `?IsFileCatalogSigned@WindowsMidiServicesInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1400252b8`

## callees

- `0x1400054c0`
- `0x140005868`
- `0x1400058d0`
- `0x1400060f8`
- `0x14000a694`
- `0x14000a6b4`
- `0x140025554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400257a7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400257a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400256f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400256f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400256db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400256db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400256a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400258bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002592b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400256a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400258bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002592b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002560d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002560d`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140025735`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140025870`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140025735`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140025870`
- `WINTRUST!WinVerifyTrust` at `0x140025832`
- `WINTRUST!WinVerifyTrust` at `0x14002584b`
- `WINTRUST!WinVerifyTrust` at `0x1400258b2`
- `WINTRUST!WinVerifyTrust` at `0x140025832`
- `WINTRUST!WinVerifyTrust` at `0x14002584b`
- `WINTRUST!WinVerifyTrust` at `0x1400258b2`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140025709`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140025709`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1400257f5`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1400257f5`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400256c4`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400256e8`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400258a2`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400258d8`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002593d`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400256c4`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400256e8`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400258a2`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400258d8`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002593d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140025631`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140025682`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140025631`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140025682`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
                  (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
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
                  (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
                  v5);
LABEL_40:
    CloseHandle(FileW);
    goto LABEL_41;
  }
  v7 = (BYTE *)operator new[](pcbHash, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
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
            (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
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
0x140025554  mov     [rsp-8+arg_8], rbx
0x140025559  mov     [rsp-8+arg_10], rsi
0x14002555e  push    rbp
0x14002555f  push    rdi
0x140025560  push    r13
0x140025562  push    r14
0x140025564  push    r15
0x140025566  lea     rbp, [rsp-690h]
0x14002556e  sub     rsp, 790h
0x140025575  mov     rax, cs:__security_cookie
0x14002557c  xor     rax, rsp
0x14002557f  mov     [rbp+6B0h+var_30], rax
0x140025586  mov     r14, rcx
0x140025589  mov     [rsp+7B0h+pcbHash], 0
0x140025591  lea     rcx, [rbp+6B0h+var_480]; void *
0x140025598  mov     [rsp+7B0h+hCatAdmin], 0
0x1400255a1  xor     edx, edx; Val
0x1400255a3  mov     [rsp+7B0h+phPrevCatInfo], 0
0x1400255ac  mov     r8d, 450h; Size
0x1400255b2  call    memset_0
0x1400255b7  xor     edx, edx; Val
0x1400255b9  lea     rcx, [rsp+7B0h+pWVTData]; void *
0x1400255be  lea     r8d, [rdx+58h]; Size
0x1400255c2  call    memset_0
0x1400255c7  xor     edx, edx; Val
0x1400255c9  lea     rcx, [rbp+6B0h+var_6F0]; void *
0x1400255cd  lea     r8d, [rdx+48h]; Size
0x1400255d1  call    memset_0
0x1400255d6  cmp     qword ptr [r14+18h], 7
0x1400255db  jbe     short loc_1400255E2
0x1400255dd  mov     rcx, [r14]
0x1400255e0  jmp     short loc_1400255E5
0x1400255e2  mov     rcx, r14; lpFileName
0x1400255e5  xor     r9d, r9d; lpSecurityAttributes
0x1400255e8  mov     [rsp+7B0h+hTemplateFile], 0; hTemplateFile
0x1400255f1  mov     [rsp+7B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400255f9  mov     edx, 80000000h; dwDesiredAccess
0x1400255fe  mov     [rsp+7B0h+dwCreationDisposition], 3; int
0x140025606  lea     r13d, [r9+1]
0x14002560a  mov     r8d, r13d; dwShareMode
0x14002560d  call    cs:__imp_CreateFileW
0x140025613  mov     rbx, rax
0x140025616  dec     rax
0x140025619  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002561d  ja      loc_140025904
0x140025623  xor     r9d, r9d; dwFlags
0x140025626  lea     rdx, [rsp+7B0h+pcbHash]; pcbHash
0x14002562b  xor     r8d, r8d; pbHash
0x14002562e  mov     rcx, rbx; hFile
0x140025631  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x140025637  test    eax, eax
0x140025639  jnz     short loc_140025658
0x14002563b  mov     rcx, [rbp+6B8h]; this
0x140025642  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x140025649  lea     edx, [rax+4Ch]; void *
0x14002564c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140025651  mov     edi, eax
0x140025653  jmp     loc_140025928
0x140025658  mov     ecx, [rsp+7B0h+pcbHash]; unsigned __int64
0x14002565c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140025663  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140025668  mov     rdi, rax
0x14002566b  test    rax, rax
0x14002566e  jz      loc_1400258E2
0x140025674  xor     r9d, r9d; dwFlags
0x140025677  lea     rdx, [rsp+7B0h+pcbHash]; pcbHash
0x14002567c  mov     r8, rax; pbHash
0x14002567f  mov     rcx, rbx; hFile
0x140025682  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x140025688  test    eax, eax
0x14002568a  jnz     short loc_1400256D1
0x14002568c  lea     edx, [rax+53h]; void *
0x14002568f  mov     rcx, [rbp+6B8h]; this
0x140025696  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x14002569d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400256a2  mov     rcx, rbx; hObject
0x1400256a5  mov     esi, eax
0x1400256a7  call    cs:__imp_CloseHandle
0x1400256ad  mov     rdx, r13
0x1400256b0  mov     rcx, rdi; Block
0x1400256b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400256b8  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x1400256bd  test    rcx, rcx
0x1400256c0  jz      short loc_1400256CA
0x1400256c2  xor     edx, edx; dwFlags
0x1400256c4  call    cs:__imp_CryptCATAdminReleaseContext
0x1400256ca  mov     eax, esi
0x1400256cc  jmp     loc_140025945
0x1400256d1  mov     r15, [rsp+7B0h+hCatAdmin]
0x1400256d6  test    r15, r15
0x1400256d9  jz      short loc_1400256F6
0x1400256db  call    cs:__imp_GetLastError
0x1400256e1  xor     edx, edx; dwFlags
0x1400256e3  mov     rcx, r15; hCatAdmin
0x1400256e6  mov     esi, eax
0x1400256e8  call    cs:__imp_CryptCATAdminReleaseContext
0x1400256ee  mov     ecx, esi; dwErrCode
0x1400256f0  call    cs:__imp_SetLastError
0x1400256f6  xor     r8d, r8d; dwFlags
0x1400256f9  mov     [rsp+7B0h+hCatAdmin], 0
0x140025702  xor     edx, edx; pgSubsystem
0x140025704  lea     rcx, [rsp+7B0h+hCatAdmin]; phCatAdmin
0x140025709  call    cs:__imp_CryptCATAdminAcquireContext
0x14002570f  test    eax, eax
0x140025711  jnz     short loc_14002571B
0x140025713  lea     edx, [rax+56h]
0x140025716  jmp     loc_14002568F
0x14002571b  mov     r8d, [rsp+7B0h+pcbHash]; cbHash
0x140025720  lea     rax, [rsp+7B0h+phPrevCatInfo]
0x140025725  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x14002572a  xor     r9d, r9d; dwFlags
0x14002572d  mov     rdx, rdi; pbHash
0x140025730  mov     qword ptr [rsp+7B0h+dwCreationDisposition], rax; phPrevCatInfo
0x140025735  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x14002573b  mov     rsi, rax
0x14002573e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140025742  jnz     short loc_14002574C
0x140025744  lea     edx, [rax+5Eh]
0x140025747  jmp     loc_14002568F
0x14002574c  cmp     qword ptr [r14+18h], 7
0x140025751  lea     rax, [rbp+6B0h+var_480]
0x140025758  mov     [rsp+7B0h+var_748], rax
0x14002575d  mov     r15d, 2
0x140025763  lea     rax, [rbp+6B0h+var_6F0]
0x140025767  mov     [rbp+6B0h+var_480], 450h
0x140025771  mov     [rbp+6B0h+var_728], rax
0x140025775  mov     eax, [rsp+7B0h+pcbHash]
0x140025779  mov     [rbp+6B0h+var_6C0], eax
0x14002577c  mov     [rsp+7B0h+pWVTData], 58h ; 'X'
0x140025784  mov     [rsp+7B0h+var_738], r15
0x140025789  mov     [rbp+6B0h+var_730], r15d
0x14002578d  mov     [rbp+6B0h+var_6F0], 48h ; 'H'
0x140025794  mov     [rbp+6B0h+var_6C8], rdi
0x140025798  jbe     short loc_14002579F
0x14002579a  mov     rcx, [r14]
0x14002579d  jmp     short loc_1400257A2
0x14002579f  mov     rcx, r14; Str
0x1400257a2  mov     edx, 5Ch ; '\'; Ch
0x1400257a7  call    cs:__imp_wcsrchr
0x1400257ad  test    rax, rax
0x1400257b0  jnz     short loc_1400257C3
0x1400257b2  cmp     qword ptr [r14+18h], 7
0x1400257b7  jbe     short loc_1400257BE
0x1400257b9  mov     rax, [r14]
0x1400257bc  jmp     short loc_1400257C6
0x1400257be  mov     rax, r14
0x1400257c1  jmp     short loc_1400257C6
0x1400257c3  add     rax, r15
0x1400257c6  mov     [rbp+6B0h+var_6E0], rax
0x1400257ca  test    rsi, rsi
0x1400257cd  jz      loc_140025882
0x1400257d3  xor     edx, edx; Val
0x1400257d5  lea     rcx, [rbp+6B0h+psCatInfo.wszCatalogFile]; void *
0x1400257d9  mov     r8d, 208h; Size
0x1400257df  call    memset_0
0x1400257e4  xor     r8d, r8d; dwFlags
0x1400257e7  mov     [rbp+6B0h+psCatInfo.cbStruct], 20Ch
0x1400257ee  lea     rdx, [rbp+6B0h+psCatInfo]; psCatInfo
0x1400257f2  mov     rcx, rsi; hCatInfo
0x1400257f5  call    cs:__imp_CryptCATCatalogInfoFromContext
0x1400257fb  test    eax, eax
0x1400257fd  jz      short loc_140025851
0x1400257ff  lea     rax, [rbp+6B0h+psCatInfo.wszCatalogFile]
0x140025803  mov     [rbp+6B0h+pgActionID.Data1], 0F750E6C3h
0x14002580a  lea     r8, [rsp+7B0h+pWVTData]; pWVTData
0x14002580f  mov     [rbp+6B0h+var_6E8], rax
0x140025813  lea     rdx, [rbp+6B0h+pgActionID]; pgActionID
0x140025817  mov     dword ptr [rbp+6B0h+pgActionID.Data2], 11D138EEh
0x14002581e  xor     ecx, ecx; hwnd
0x140025820  mov     dword ptr [rbp+6B0h+pgActionID.Data4], 0C000E585h
0x140025827  mov     dword ptr [rbp+6B0h+pgActionID.Data4+4], 0EE95C24Fh
0x14002582e  mov     [rbp+6B0h+var_720], r13d
0x140025832  call    cs:__imp_WinVerifyTrust
0x140025838  xor     ecx, ecx; hwnd
0x14002583a  mov     [rbp+6B0h+var_720], r15d
0x14002583e  lea     r8, [rsp+7B0h+pWVTData]; pWVTData
0x140025843  lea     rdx, [rbp+6B0h+pgActionID]; pgActionID
0x140025847  test    eax, eax
0x140025849  jz      short loc_1400258B2
0x14002584b  call    cs:__imp_WinVerifyTrust
0x140025851  mov     r8d, [rsp+7B0h+pcbHash]; cbHash
0x140025856  lea     rax, [rsp+7B0h+phPrevCatInfo]
0x14002585b  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x140025860  xor     r9d, r9d; dwFlags
0x140025863  mov     rdx, rdi; pbHash
0x140025866  mov     qword ptr [rsp+7B0h+dwCreationDisposition], rax; phPrevCatInfo
0x14002586b  mov     [rsp+7B0h+phPrevCatInfo], rsi
0x140025870  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x140025876  mov     rsi, rax
0x140025879  test    rax, rax
0x14002587c  jnz     loc_1400257D3
0x140025882  mov     rcx, rbx; hObject
0x140025885  call    cs:__imp_CloseHandle
0x14002588b  mov     rdx, r13
0x14002588e  mov     rcx, rdi; Block
0x140025891  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140025896  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x14002589b  test    rcx, rcx
0x14002589e  jz      short loc_1400258A8
0x1400258a0  xor     edx, edx; dwFlags
0x1400258a2  call    cs:__imp_CryptCATAdminReleaseContext
0x1400258a8  mov     eax, 80004005h
0x1400258ad  jmp     loc_140025945
0x1400258b2  call    cs:__imp_WinVerifyTrust
0x1400258b8  mov     rcx, rbx; hObject
0x1400258bb  call    cs:__imp_CloseHandle
0x1400258c1  mov     rdx, r13
0x1400258c4  mov     rcx, rdi; Block
0x1400258c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400258cc  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x1400258d1  test    rcx, rcx
0x1400258d4  jz      short loc_1400258DE
0x1400258d6  xor     edx, edx; dwFlags
0x1400258d8  call    cs:__imp_CryptCATAdminReleaseContext
0x1400258de  xor     eax, eax
0x1400258e0  jmp     short loc_140025945
0x1400258e2  mov     rcx, [rbp+6B8h]; this
0x1400258e9  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x1400258f0  mov     edi, 8007000Eh
0x1400258f5  mov     edx, 50h ; 'P'; void *
0x1400258fa  mov     r9d, edi; char *
0x1400258fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025902  jmp     short loc_140025928
0x140025904  mov     rcx, [rbp+6B8h]; this
0x14002590b  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x140025912  mov     edx, 49h ; 'I'; void *
0x140025917  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002591c  lea     rcx, [rbx-1]
0x140025920  mov     edi, eax
0x140025922  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140025926  ja      short loc_140025931
0x140025928  mov     rcx, rbx; hObject
0x14002592b  call    cs:__imp_CloseHandle
0x140025931  mov     rcx, [rsp+7B0h+hCatAdmin]; hCatAdmin
0x140025936  test    rcx, rcx
0x140025939  jz      short loc_140025943
0x14002593b  xor     edx, edx; dwFlags
0x14002593d  call    cs:__imp_CryptCATAdminReleaseContext
0x140025943  mov     eax, edi
0x140025945  mov     rcx, [rbp+6B0h+var_30]
0x14002594c  xor     rcx, rsp; StackCookie
0x14002594f  call    __security_check_cookie
0x140025954  lea     r11, [rsp+7B0h+var_20]
0x14002595c  mov     rbx, [r11+38h]
0x140025960  mov     rsi, [r11+40h]
0x140025964  mov     rsp, r11
0x140025967  pop     r15
0x140025969  pop     r14
0x14002596b  pop     r13
0x14002596d  pop     rdi
0x14002596e  pop     rbp
0x14002596f  retn
```
