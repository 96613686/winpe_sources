# Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize(void)

- ea: `0x180205840`
- end: `0x180205dba`
- name: `?Initialize@InboxExeSdbDataSource@Appraiser@Compat@Windows@@QEAAJXZ`
- size: `1402`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::InboxExeSdbDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180205dc0`

## callees

- `0x180008570`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1801abfd8`
- `0x1801fd5c0`
- `0x180205840`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180205891`
- `KERNEL32!LoadLibraryExW` at `0x180205891`
- `KERNEL32!FreeLibrary` at `0x180205878`
- `KERNEL32!FreeLibrary` at `0x180205878`
- `KERNEL32!GetProcAddress` at `0x180205905`
- `KERNEL32!GetProcAddress` at `0x18020591a`
- `KERNEL32!GetProcAddress` at `0x18020592f`
- `KERNEL32!GetProcAddress` at `0x180205947`
- `KERNEL32!GetProcAddress` at `0x18020595f`
- `KERNEL32!GetProcAddress` at `0x180205977`
- `KERNEL32!GetProcAddress` at `0x18020598f`
- `KERNEL32!GetProcAddress` at `0x1802059a7`
- `KERNEL32!GetProcAddress` at `0x1802059bf`
- `KERNEL32!GetProcAddress` at `0x1802059d7`
- `KERNEL32!GetProcAddress` at `0x1802059ef`
- `KERNEL32!GetProcAddress` at `0x180205a07`
- `KERNEL32!GetProcAddress` at `0x180205a1f`
- `KERNEL32!GetProcAddress` at `0x180205a37`
- `KERNEL32!GetProcAddress` at `0x180205905`
- `KERNEL32!GetProcAddress` at `0x18020591a`
- `KERNEL32!GetProcAddress` at `0x18020592f`
- `KERNEL32!GetProcAddress` at `0x180205947`
- `KERNEL32!GetProcAddress` at `0x18020595f`
- `KERNEL32!GetProcAddress` at `0x180205977`
- `KERNEL32!GetProcAddress` at `0x18020598f`
- `KERNEL32!GetProcAddress` at `0x1802059a7`
- `KERNEL32!GetProcAddress` at `0x1802059bf`
- `KERNEL32!GetProcAddress` at `0x1802059d7`
- `KERNEL32!GetProcAddress` at `0x1802059ef`
- `KERNEL32!GetProcAddress` at `0x180205a07`
- `KERNEL32!GetProcAddress` at `0x180205a1f`
- `KERNEL32!GetProcAddress` at `0x180205a37`
- `KERNEL32!GetLastError` at `0x1802058a0`
- `KERNEL32!GetLastError` at `0x1802058bf`
- `KERNEL32!GetLastError` at `0x1802058a0`
- `KERNEL32!GetLastError` at `0x1802058bf`

## string_xrefs

- `0x1802059f9`: `SdbReadDWORDTagRef`
- `0x1802059e1`: `SdbReadDWORDTag`
- `0x1802059c9`: `SdbReadBinaryTag`
- `0x1802058e5`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x180205bb4`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x180205c16`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x180205ce3`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x180205d42`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x180205d82`: `onecore\base\appcompat\appraiser\datasource\inboxexesdb.cpp`
- `0x1802058da`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x180205bad`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x180205c0a`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x180205cdc`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x180205d36`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x180205d76`: `Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize`
- `0x1802058ce`: `Failed to load apphelp dll: [%d].`
- `0x180205884`: `apphelp.dll`
- `0x180205b7a`: `Failed to get appPatch directory.`
- `0x180205b2c`: `Failed to open exe database.`
- `0x180205c6b`: `Failed to open exe database in WOW mode.`
- `0x180205d5c`: `Corrupt apphelp dll.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize(
        Windows::Compat::Appraiser::InboxExeSdbDataSource *this)
{
  HMODULE v2; // rcx
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  char v6; // dl
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  HMODULE v20; // rcx
  FARPROC v21; // rax
  HMODULE v22; // rcx
  FARPROC v23; // rax
  HMODULE v24; // rcx
  FARPROC v25; // rax
  HMODULE v26; // rcx
  FARPROC v27; // rax
  HMODULE v28; // rcx
  FARPROC v29; // rax
  HMODULE v30; // rcx
  FARPROC v31; // rax
  HMODULE v32; // rcx
  FARPROC v33; // rcx
  void (*v34)(void); // rax
  __int64 v35; // rax
  __int64 v36; // r13
  __int64 v37; // rax
  HRESULT v38; // eax
  __int64 v39; // rax
  HRESULT v40; // eax
  char *v42; // [rsp+20h] [rbp-458h]
  const char *v43; // [rsp+28h] [rbp-450h]
  char *v44; // [rsp+30h] [rbp-448h]
  WCHAR pszPath[520]; // [rsp+40h] [rbp-438h] BYREF

  v2 = (HMODULE)*((_QWORD *)this + 13);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 13) = 0;
  }
  Library = LoadLibraryExW(L"apphelp.dll", 0, 0x800u);
  *((_QWORD *)this + 13) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      v5 = -2147467259;
    LODWORD(v44) = GetLastError();
    v6 = 91;
    v43 = "Failed to load apphelp dll: [%d].";
    goto LABEL_9;
  }
  ProcAddress = GetProcAddress(Library, "SdbFindFirstTag");
  v8 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 14) = ProcAddress;
  v9 = GetProcAddress(v8, "SdbFindFirstTagRef");
  v10 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 15) = v9;
  v11 = GetProcAddress(v10, "SdbGetAppPatchDir");
  v12 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 16) = v11;
  v13 = GetProcAddress(v12, "SdbGetFirstChild");
  v14 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 17) = v13;
  v15 = GetProcAddress(v14, "SdbGetMatchingExe");
  v16 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 18) = v15;
  v17 = GetProcAddress(v16, "SdbGetNextChild");
  v18 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 19) = v17;
  v19 = GetProcAddress(v18, "SdbGetTagFromTagID");
  v20 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 20) = v19;
  v21 = GetProcAddress(v20, "SdbInitDatabaseEx");
  v22 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 21) = v21;
  v23 = GetProcAddress(v22, "SdbIsTagrefFromLocalDB");
  v24 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 22) = v23;
  v25 = GetProcAddress(v24, "SdbReadBinaryTag");
  v26 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 23) = v25;
  v27 = GetProcAddress(v26, "SdbReadDWORDTag");
  v28 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 24) = v27;
  v29 = GetProcAddress(v28, "SdbReadDWORDTagRef");
  v30 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 25) = v29;
  v31 = GetProcAddress(v30, "SdbReleaseDatabase");
  v32 = (HMODULE)*((_QWORD *)this + 13);
  *((_QWORD *)this + 26) = v31;
  v33 = GetProcAddress(v32, "SdbTagRefToTagID");
  *((_QWORD *)this + 27) = v33;
  if ( !*((_QWORD *)this + 14)
    || !*((_QWORD *)this + 15)
    || !*((_QWORD *)this + 16)
    || !*((_QWORD *)this + 17)
    || !*((_QWORD *)this + 18)
    || !*((_QWORD *)this + 19)
    || !*((_QWORD *)this + 20)
    || !*((_QWORD *)this + 21)
    || !*((_QWORD *)this + 22)
    || !*((_QWORD *)this + 23)
    || !*((_QWORD *)this + 24)
    || !*((_QWORD *)this + 25)
    || (v34 = (void (*)(void))*((_QWORD *)this + 26)) == 0
    || !v33 )
  {
    v5 = -2147024769;
    LODWORD(v42) = -2147024769;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      123,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)"Corrupt apphelp dll.",
      v44);
    return v5;
  }
  if ( *((_QWORD *)this + 2) )
  {
    v34();
    *((_QWORD *)this + 2) = 0;
  }
  v35 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64))this + 21))(0, 0, 34404);
  *((_QWORD *)this + 2) = v35;
  if ( !v35 )
  {
    v5 = -2147467259;
    LODWORD(v42) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      140,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)"Failed to open exe database.",
      v44);
    return v5;
  }
  (*((void (__fastcall **)(__int64, WCHAR *, __int64))this + 16))(v35, pszPath, 520);
  v36 = -1;
  v37 = -1;
  do
    ++v37;
  while ( pszPath[v37] );
  if ( !v37 )
  {
    v5 = -2147467259;
    LODWORD(v42) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      150,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)"Failed to get appPatch directory.",
      v44);
    return v5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x96u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      "Failed to get appPatch directory.");
  v38 = PathCchAppend(pszPath, 0x208u, L"sysmain.sdb");
  v5 = v38;
  if ( v38 < 0 )
  {
    LODWORD(v44) = v38;
    v6 = -103;
    v43 = "Failed to append sysmain filename: [0x%x].";
LABEL_9:
    LODWORD(v42) = v5;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v6,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)v43,
      v44);
    return v5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x99u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      "Failed to append sysmain filename: [0x%x].",
      v38);
  Windows::Compat::Appraiser::SdbUtils::SendLegacySdbInfoTelemetry(pszPath);
  if ( *((_QWORD *)this + 3) )
  {
    (*((void (**)(void))this + 26))();
    *((_QWORD *)this + 3) = 0;
  }
  v39 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64))this + 21))(0, 0, 332);
  *((_QWORD *)this + 3) = v39;
  if ( !v39 )
  {
    v5 = -2147467259;
    LODWORD(v42) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      173,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)"Failed to open exe database in WOW mode.",
      v44);
    return v5;
  }
  (*((void (__fastcall **)(__int64, WCHAR *, __int64))this + 16))(v39, pszPath, 520);
  do
    ++v36;
  while ( pszPath[v36] );
  if ( !v36 )
  {
    v5 = -2147467259;
    LODWORD(v42) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      183,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      v42,
      (int)"Failed to get appPatch directory.",
      v44);
    return v5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB7u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      "Failed to get appPatch directory.");
  v40 = PathCchAppend(pszPath, 0x208u, L"sysmain.sdb");
  v5 = v40;
  if ( v40 < 0 )
  {
    LODWORD(v44) = v40;
    v6 = -70;
    v43 = "Failed to append sysmain filename: [0x%x].";
    goto LABEL_9;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xBAu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\inboxexesdb.cpp",
      "Windows::Compat::Appraiser::InboxExeSdbDataSource::Initialize",
      "Failed to append sysmain filename: [0x%x].",
      v40);
  Windows::Compat::Appraiser::SdbUtils::SendLegacySdbInfoTelemetry(pszPath);
  return 0;
}

```

## disassembly

```asm
0x180205840  mov     [rsp+arg_8], rbx
0x180205845  mov     [rsp+arg_10], rdi
0x18020584a  push    r12
0x18020584c  push    r13
0x18020584e  push    r15
0x180205850  sub     rsp, 460h
0x180205857  mov     rax, cs:__security_cookie
0x18020585e  xor     rax, rsp
0x180205861  mov     [rsp+478h+var_28], rax
0x180205869  mov     rdi, rcx
0x18020586c  xor     r15d, r15d
0x18020586f  mov     rcx, [rcx+68h]; hLibModule
0x180205873  test    rcx, rcx
0x180205876  jz      short loc_180205882
0x180205878  call    cs:__imp_FreeLibrary
0x18020587e  mov     [rdi+68h], r15
0x180205882  xor     edx, edx; hFile
0x180205884  lea     rcx, aApphelpDll; "apphelp.dll"
0x18020588b  mov     r8d, 800h; dwFlags
0x180205891  call    cs:__imp_LoadLibraryExW
0x180205897  mov     [rdi+68h], rax
0x18020589b  test    rax, rax
0x18020589e  jnz     short loc_1802058FB
0x1802058a0  call    cs:__imp_GetLastError
0x1802058a6  mov     ebx, eax
0x1802058a8  test    eax, eax
0x1802058aa  jle     short loc_1802058B5
0x1802058ac  movzx   ebx, ax
0x1802058af  or      ebx, 80070000h
0x1802058b5  test    ebx, ebx
0x1802058b7  mov     eax, 80004005h
0x1802058bc  cmovns  ebx, eax
0x1802058bf  call    cs:__imp_GetLastError
0x1802058c5  mov     dword ptr [rsp+478h+var_448], eax; char *
0x1802058c9  mov     edx, 5Bh ; '['; bool
0x1802058ce  lea     rax, aFailedToLoadAp; "Failed to load apphelp dll: [%d]."
0x1802058d5  mov     qword ptr [rsp+478h+var_450], rax; int
0x1802058da  lea     r9, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x1802058e1  mov     dword ptr [rsp+478h+var_458], ebx; char *
0x1802058e5  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x1802058ec  mov     ecx, 1; this
0x1802058f1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1802058f6  jmp     loc_180205D8E
0x1802058fb  lea     rdx, aSdbfindfirstta_0; "SdbFindFirstTag"
0x180205902  mov     rcx, rax; hModule
0x180205905  call    cs:__imp_GetProcAddress
0x18020590b  mov     rcx, [rdi+68h]; hModule
0x18020590f  lea     rdx, aSdbfindfirstta; "SdbFindFirstTagRef"
0x180205916  mov     [rdi+70h], rax
0x18020591a  call    cs:__imp_GetProcAddress
0x180205920  mov     rcx, [rdi+68h]; hModule
0x180205924  lea     rdx, aSdbgetapppatch; "SdbGetAppPatchDir"
0x18020592b  mov     [rdi+78h], rax
0x18020592f  call    cs:__imp_GetProcAddress
0x180205935  mov     rcx, [rdi+68h]; hModule
0x180205939  lea     rdx, aSdbgetfirstchi; "SdbGetFirstChild"
0x180205940  mov     [rdi+80h], rax
0x180205947  call    cs:__imp_GetProcAddress
0x18020594d  mov     rcx, [rdi+68h]; hModule
0x180205951  lea     rdx, aSdbgetmatching_4; "SdbGetMatchingExe"
0x180205958  mov     [rdi+88h], rax
0x18020595f  call    cs:__imp_GetProcAddress
0x180205965  mov     rcx, [rdi+68h]; hModule
0x180205969  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x180205970  mov     [rdi+90h], rax
0x180205977  call    cs:__imp_GetProcAddress
0x18020597d  mov     rcx, [rdi+68h]; hModule
0x180205981  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x180205988  mov     [rdi+98h], rax
0x18020598f  call    cs:__imp_GetProcAddress
0x180205995  mov     rcx, [rdi+68h]; hModule
0x180205999  lea     rdx, aSdbinitdatabas_0; "SdbInitDatabaseEx"
0x1802059a0  mov     [rdi+0A0h], rax
0x1802059a7  call    cs:__imp_GetProcAddress
0x1802059ad  mov     rcx, [rdi+68h]; hModule
0x1802059b1  lea     rdx, aSdbistagreffro; "SdbIsTagrefFromLocalDB"
0x1802059b8  mov     [rdi+0A8h], rax
0x1802059bf  call    cs:__imp_GetProcAddress
0x1802059c5  mov     rcx, [rdi+68h]; hModule
0x1802059c9  lea     rdx, aSdbreadbinaryt; "SdbReadBinaryTag"
0x1802059d0  mov     [rdi+0B0h], rax
0x1802059d7  call    cs:__imp_GetProcAddress
0x1802059dd  mov     rcx, [rdi+68h]; hModule
0x1802059e1  lea     rdx, aSdbreaddwordta_0; "SdbReadDWORDTag"
0x1802059e8  mov     [rdi+0B8h], rax
0x1802059ef  call    cs:__imp_GetProcAddress
0x1802059f5  mov     rcx, [rdi+68h]; hModule
0x1802059f9  lea     rdx, aSdbreaddwordta; "SdbReadDWORDTagRef"
0x180205a00  mov     [rdi+0C0h], rax
0x180205a07  call    cs:__imp_GetProcAddress
0x180205a0d  mov     rcx, [rdi+68h]; hModule
0x180205a11  lea     rdx, aSdbreleasedata; "SdbReleaseDatabase"
0x180205a18  mov     [rdi+0C8h], rax
0x180205a1f  call    cs:__imp_GetProcAddress
0x180205a25  mov     rcx, [rdi+68h]; hModule
0x180205a29  lea     rdx, aSdbtagreftotag; "SdbTagRefToTagID"
0x180205a30  mov     [rdi+0D0h], rax
0x180205a37  call    cs:__imp_GetProcAddress
0x180205a3d  mov     rcx, rax
0x180205a40  mov     [rdi+0D8h], rax
0x180205a47  cmp     [rdi+70h], r15
0x180205a4b  jz      loc_180205D5C
0x180205a51  cmp     [rdi+78h], r15
0x180205a55  jz      loc_180205D5C
0x180205a5b  cmp     [rdi+80h], r15
0x180205a62  jz      loc_180205D5C
0x180205a68  cmp     [rdi+88h], r15
0x180205a6f  jz      loc_180205D5C
0x180205a75  cmp     [rdi+90h], r15
0x180205a7c  jz      loc_180205D5C
0x180205a82  cmp     [rdi+98h], r15
0x180205a89  jz      loc_180205D5C
0x180205a8f  cmp     [rdi+0A0h], r15
0x180205a96  jz      loc_180205D5C
0x180205a9c  cmp     [rdi+0A8h], r15
0x180205aa3  jz      loc_180205D5C
0x180205aa9  cmp     [rdi+0B0h], r15
0x180205ab0  jz      loc_180205D5C
0x180205ab6  cmp     [rdi+0B8h], r15
0x180205abd  jz      loc_180205D5C
0x180205ac3  cmp     [rdi+0C0h], r15
0x180205aca  jz      loc_180205D5C
0x180205ad0  cmp     [rdi+0C8h], r15
0x180205ad7  jz      loc_180205D5C
0x180205add  mov     rax, [rdi+0D0h]
0x180205ae4  test    rax, rax
0x180205ae7  jz      loc_180205D5C
0x180205aed  test    rcx, rcx
0x180205af0  jz      loc_180205D5C
0x180205af6  mov     rcx, [rdi+10h]
0x180205afa  test    rcx, rcx
0x180205afd  jz      short loc_180205B08
0x180205aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205b04  mov     [rdi+10h], r15
0x180205b08  mov     rax, [rdi+0A8h]
0x180205b0f  xor     edx, edx
0x180205b11  xor     ecx, ecx
0x180205b13  mov     r8d, 8664h
0x180205b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205b1e  mov     [rdi+10h], rax
0x180205b22  test    rax, rax
0x180205b25  jnz     short loc_180205B48
0x180205b27  mov     eax, 80004005h
0x180205b2c  lea     rcx, aFailedToOpenEx_0; "Failed to open exe database."
0x180205b33  mov     qword ptr [rsp+478h+var_450], rcx
0x180205b38  mov     ebx, eax
0x180205b3a  mov     dword ptr [rsp+478h+var_458], eax
0x180205b3e  mov     edx, 8Ch
0x180205b43  jmp     loc_180205D76
0x180205b48  mov     rcx, rax
0x180205b4b  lea     rdx, [rsp+478h+pszPath]
0x180205b50  mov     rax, [rdi+80h]
0x180205b57  mov     ebx, 208h
0x180205b5c  mov     r8d, ebx
0x180205b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205b64  or      r13, 0FFFFFFFFFFFFFFFFh
0x180205b68  lea     rcx, [rsp+478h+pszPath]
0x180205b6d  mov     rax, r13
0x180205b70  inc     rax
0x180205b73  cmp     [rcx+rax*2], r15w
0x180205b78  jnz     short loc_180205B70
0x180205b7a  lea     r12, aFailedToGetApp_0; "Failed to get appPatch directory."
0x180205b81  test    rax, rax
0x180205b84  jnz     short loc_180205BA0
0x180205b86  mov     eax, 80004005h
0x180205b8b  mov     qword ptr [rsp+478h+var_450], r12
0x180205b90  mov     ebx, eax
0x180205b92  mov     dword ptr [rsp+478h+var_458], eax
0x180205b96  mov     edx, 96h
0x180205b9b  jmp     loc_180205D76
0x180205ba0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180205ba6  test    al, 1
0x180205ba8  jz      short loc_180205BC5
0x180205baa  mov     r9, r12; char *
0x180205bad  lea     r8, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x180205bb4  lea     rdx, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x180205bbb  mov     ecx, 96h; unsigned int
0x180205bc0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180205bc5  lea     r8, aSysmainSdb; "sysmain.sdb"
0x180205bcc  mov     rdx, rbx; cchPath
0x180205bcf  lea     rcx, [rsp+478h+pszPath]; pszPath
0x180205bd4  call    PathCchAppend
0x180205bd9  lea     r15, aFailedToAppend_35; "Failed to append sysmain filename: [0x%"...
0x180205be0  mov     ebx, eax
0x180205be2  test    eax, eax
0x180205be4  jns     short loc_180205BF9
0x180205be6  mov     dword ptr [rsp+478h+var_448], eax
0x180205bea  mov     edx, 99h
0x180205bef  mov     qword ptr [rsp+478h+var_450], r15
0x180205bf4  jmp     loc_1802058DA
0x180205bf9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180205bff  test    al, 1
0x180205c01  jz      short loc_180205C22
0x180205c03  mov     r9, r15; char *
0x180205c06  mov     dword ptr [rsp+478h+var_458], ebx
0x180205c0a  lea     r8, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x180205c11  mov     ecx, 99h; unsigned int
0x180205c16  lea     rdx, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x180205c1d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180205c22  lea     rcx, [rsp+478h+pszPath]; unsigned __int16 *
0x180205c27  call    ?SendLegacySdbInfoTelemetry@SdbUtils@Appraiser@Compat@Windows@@SAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::SendLegacySdbInfoTelemetry(ushort const *)
0x180205c2c  mov     rcx, [rdi+18h]
0x180205c30  xor     ebx, ebx
0x180205c32  test    rcx, rcx
0x180205c35  jz      short loc_180205C47
0x180205c37  mov     rax, [rdi+0D0h]
0x180205c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205c43  mov     [rdi+18h], rbx
0x180205c47  mov     rax, [rdi+0A8h]
0x180205c4e  xor     edx, edx
0x180205c50  xor     ecx, ecx
0x180205c52  mov     r8d, 14Ch
0x180205c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205c5d  mov     [rdi+18h], rax
0x180205c61  test    rax, rax
0x180205c64  jnz     short loc_180205C87
0x180205c66  mov     eax, 80004005h
0x180205c6b  lea     rcx, aFailedToOpenEx; "Failed to open exe database in WOW mode"...
0x180205c72  mov     qword ptr [rsp+478h+var_450], rcx
0x180205c77  mov     ebx, eax
0x180205c79  mov     dword ptr [rsp+478h+var_458], eax
0x180205c7d  mov     edx, 0ADh
0x180205c82  jmp     loc_180205D76
0x180205c87  mov     rcx, rax
0x180205c8a  lea     rdx, [rsp+478h+pszPath]
0x180205c8f  mov     rax, [rdi+80h]
0x180205c96  mov     r8d, 208h
0x180205c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180205ca1  lea     rax, [rsp+478h+pszPath]
0x180205ca6  inc     r13
0x180205ca9  cmp     [rax+r13*2], bx
0x180205cae  jnz     short loc_180205CA6
0x180205cb0  test    r13, r13
0x180205cb3  jnz     short loc_180205CCF
0x180205cb5  mov     eax, 80004005h
0x180205cba  mov     qword ptr [rsp+478h+var_450], r12
0x180205cbf  mov     ebx, eax
0x180205cc1  mov     dword ptr [rsp+478h+var_458], eax
0x180205cc5  mov     edx, 0B7h
0x180205cca  jmp     loc_180205D76
0x180205ccf  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180205cd5  test    al, 1
0x180205cd7  jz      short loc_180205CF4
0x180205cd9  mov     r9, r12; char *
0x180205cdc  lea     r8, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x180205ce3  lea     rdx, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x180205cea  mov     ecx, 0B7h; unsigned int
0x180205cef  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180205cf4  lea     r8, aSysmainSdb; "sysmain.sdb"
0x180205cfb  mov     edx, 208h; cchPath
0x180205d00  lea     rcx, [rsp+478h+pszPath]; pszPath
0x180205d05  call    PathCchAppend
0x180205d0a  xor     edi, edi
0x180205d0c  mov     ebx, eax
0x180205d0e  test    eax, eax
0x180205d10  jns     short loc_180205D25
0x180205d12  mov     dword ptr [rsp+478h+var_448], eax
0x180205d16  mov     edx, 0BAh
0x180205d1b  mov     qword ptr [rsp+478h+var_450], r15
0x180205d20  jmp     loc_1802058DA
0x180205d25  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180205d2b  test    al, 1
0x180205d2d  jz      short loc_180205D4E
0x180205d2f  mov     r9, r15; char *
0x180205d32  mov     dword ptr [rsp+478h+var_458], ebx
0x180205d36  lea     r8, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x180205d3d  mov     ecx, 0BAh; unsigned int
0x180205d42  lea     rdx, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x180205d49  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180205d4e  lea     rcx, [rsp+478h+pszPath]; unsigned __int16 *
0x180205d53  call    ?SendLegacySdbInfoTelemetry@SdbUtils@Appraiser@Compat@Windows@@SAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::SendLegacySdbInfoTelemetry(ushort const *)
0x180205d58  mov     ebx, edi
0x180205d5a  jmp     short loc_180205D8E
0x180205d5c  lea     rax, aCorruptApphelp; "Corrupt apphelp dll."
0x180205d63  mov     ebx, 8007007Fh
0x180205d68  mov     qword ptr [rsp+478h+var_450], rax; int
0x180205d6d  mov     edx, 7Bh ; '{'; bool
0x180205d72  mov     dword ptr [rsp+478h+var_458], ebx; char *
0x180205d76  lea     r9, aWindowsCompatA_569; "Windows::Compat::Appraiser::InboxExeSdb"...
0x180205d7d  mov     ecx, 1; this
0x180205d82  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appcompat\\appraiser\\da"...
0x180205d89  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180205d8e  mov     eax, ebx
0x180205d90  mov     rcx, [rsp+478h+var_28]
0x180205d98  xor     rcx, rsp; StackCookie
0x180205d9b  call    __security_check_cookie
0x180205da0  lea     r11, [rsp+478h+var_18]
0x180205da8  mov     rbx, [r11+28h]
0x180205dac  mov     rdi, [r11+30h]
0x180205db0  mov     rsp, r11
0x180205db3  pop     r15
0x180205db5  pop     r13
0x180205db7  pop     r12
0x180205db9  retn
```
