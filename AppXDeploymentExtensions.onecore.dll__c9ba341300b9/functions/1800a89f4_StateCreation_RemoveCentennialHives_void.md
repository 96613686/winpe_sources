# StateCreation::RemoveCentennialHives(void)

- ea: `0x1800a89f4`
- end: `0x1800a8f7a`
- name: `?RemoveCentennialHives@StateCreation@@AEAAJXZ`
- size: `1414`
- prototype: `__int64 __fastcall(StateCreation *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a91c8`

## callees

- `0x18000e6e0`
- `0x18001c348`
- `0x18001c3c8`
- `0x180054550`
- `0x180054800`
- `0x1800550f4`
- `0x180055c68`
- `0x180055dd4`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a89f4`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800ac484`
- `0x1800ac630`
- `0x1800f0700`
- `0x1801f565c`
- `0x1801f61ac`
- `0x1801f7224`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8c42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8de1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8c42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8de1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8f3f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a8c81`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a8d85`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a8c81`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800a8d85`

## string_xrefs

- `0x1800a8c9e`: `PathCchRemoveFileSpec %ls %u`
- `0x1800a8d9f`: `PathCchRemoveFileSpec %ls %u`
- `0x1800a8e4a`: `RemoveSecureAppDataFolder %ls`
- `0x1800a8ec7`: `RemoveSecureAppDataFolder %ls`
- `0x1800a8d1a`: `RemoveDirectoryTree %ls`
- `0x1800a8bc3`: `CheckDirectoryExistenceAndLogIfNeeded %ls`
- `0x1800a8a48`: `Helium\Cache`
- `0x1800a8e07`: `RemoveEmptyCentennialStateFolders %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateCreation::RemoveCentennialHives(StateCreation *this)
{
  bool v2; // r14
  int SystemAppDataFolderPath; // eax
  struct Common::StringBuffer *v4; // r9
  DirectoryPaths *v5; // rdi
  int FullFileName; // eax
  __int64 v7; // r8
  struct Common::StringBuffer *v8; // r9
  const unsigned __int16 *v9; // r13
  __int64 v10; // r8
  bool v11; // r12
  int EffectiveToken; // eax
  int v13; // eax
  int SecureSystemAppDataFolderPath; // eax
  unsigned int v15; // ebx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  StateCreationHelpers *v18; // rbx
  const char *v19; // rsi
  void *v20; // r9
  __int64 v21; // r15
  __int64 v22; // r8
  unsigned int v23; // eax
  int v24; // eax
  int v25; // esi
  unsigned __int64 v26; // rdx
  unsigned int v27; // eax
  int v28; // ecx
  unsigned __int64 v29; // rdx
  char *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // r8
  unsigned __int64 v33; // rdx
  unsigned int v34; // eax
  unsigned __int64 v35; // rdx
  size_t v36; // r15
  StateCreation *v37; // rcx
  unsigned __int64 v38; // rdx
  unsigned int v39; // eax
  unsigned __int64 v40; // rdx
  const char *v41; // r14
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  int v45; // [rsp+20h] [rbp-49h]
  int v46; // [rsp+20h] [rbp-49h]
  bool *v47; // [rsp+28h] [rbp-41h]
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  PWSTR pszPath; // [rsp+48h] [rbp-21h] BYREF
  char *v50[2]; // [rsp+50h] [rbp-19h] BYREF
  int v51; // [rsp+60h] [rbp-9h]
  char *v52[2]; // [rsp+68h] [rbp-1h] BYREF
  int v53; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DirectoryPaths *v56; // [rsp+D8h] [rbp+6Fh] BYREF
  int v57; // [rsp+E0h] [rbp+77h]
  HANDLE hObject; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_OWORD *)v52 = 0;
  v53 = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  v2 = 0;
  v56 = 0;
  SystemAppDataFolderPath = StateCreation::GetSystemAppDataFolderPath(this, (unsigned __int16 **)&v56);
  v5 = v56;
  if ( SystemAppDataFolderPath < 0 )
  {
    v11 = 0;
    v9 = (const unsigned __int16 *)v52[1];
  }
  else
  {
    FullFileName = DirectoryPaths::CreateFullFileName(v56, L"Helium\\Cache", (const unsigned __int16 *)v52, v4);
    v9 = (const unsigned __int16 *)v52[1];
    if ( FullFileName >= 0 )
      v2 = (unsigned int)RemoveDirectoryTree(
                           (unsigned __int16 *)v52[1],
                           0,
                           v7,
                           (__int64)&DirectoryPaths::LogRemoveDirectoryTreeError,
                           0) == 5;
    if ( DirectoryPaths::CreateFullFileName(v5, L"Helium", (const unsigned __int16 *)v50, v8) < 0 || v2 )
      v11 = v2;
    else
      v11 = (unsigned int)RemoveDirectoryTree(
                            (unsigned __int16 *)v50[1],
                            0,
                            v10,
                            (__int64)&DirectoryPaths::LogRemoveDirectoryTreeError,
                            0) == 5;
  }
  hObject = 0;
  EffectiveToken = Common::ImpersonationContext::GetEffectiveToken(&hObject);
  v57 = EffectiveToken;
  if ( EffectiveToken < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFC7,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)(unsigned int)EffectiveToken,
      v45);
  TokenHandle = 0;
  v13 = Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFCC,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)(unsigned int)v13,
      v45);
  pszPath = 0;
  SecureSystemAppDataFolderPath = StateCreation::GetSecureSystemAppDataFolderPath(this, &pszPath);
  v15 = SecureSystemAppDataFolderPath;
  if ( SecureSystemAppDataFolderPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFCF,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)(unsigned int)SecureSystemAppDataFolderPath,
      v45);
    operator delete(pszPath, v16);
    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    operator delete(v5, v17);
    goto LABEL_57;
  }
  LOBYTE(v56) = 0;
  v18 = (StateCreationHelpers *)pszPath;
  v19 = (const char *)RemovePIIfromFilePath(pszPath);
  v21 = -1;
  v22 = -1;
  if ( v57 >= 0 )
    v22 = (__int64)hObject;
  LOBYTE(v20) = 1;
  v23 = StateCreationHelpers::CheckDirectoryExistenceAndLogIfNeeded(
          v18,
          L"SecureSystemAppData",
          (const unsigned __int16 *)v22,
          v20,
          (bool)&v56,
          v47);
  v24 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0xFD4,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)v23,
          (__int64)"CheckDirectoryExistenceAndLogIfNeeded %ls",
          v19);
  v25 = v24;
  v26 = 2147942583LL;
  if ( v24 != -2147024713 )
  {
    v27 = v24 + 2147024894;
    if ( v27 > 0x1E || (v28 = 1073741835, !_bittest(&v28, v27)) )
    {
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFDE,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)(unsigned int)v25,
          v46);
        operator delete(v18, v29);
        Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
LABEL_25:
        operator delete(v5, (unsigned __int64)v30);
        v15 = v25;
        goto LABEL_57;
      }
    }
  }
  if ( (_BYTE)v56 || v25 == -2147024713 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v18 + v31) );
    v56 = (DirectoryPaths *)(v31 + 1);
    v25 = PathCchRemoveFileSpec((PWSTR)v18, v31 + 1);
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xFE9,
        (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
        (const char *)(unsigned int)v25,
        (int)"PathCchRemoveFileSpec %ls %u",
        (const char *)v18,
        (_DWORD)v56);
      operator delete(v18, v33);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_25;
    }
    v34 = RemoveDirectoryTree((unsigned __int16 *)v18, 0, v32, (__int64)&DirectoryPaths::LogRemoveDirectoryTreeError, 0);
    if ( v34 )
    {
      v25 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0xFED,
              (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
              (const char *)v34,
              (unsigned int)"RemoveDirectoryTree %ls",
              (const char *)v18);
      operator delete(v18, v35);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      v30 = (char *)hObject - 1;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_25;
    }
    do
      ++v21;
    while ( *((_WORD *)v18 + v21) );
    v36 = v21 + 1;
    v25 = PathCchRemoveFileSpec((PWSTR)v18, v36);
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xFF2,
        (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
        (const char *)(unsigned int)v25,
        (int)"PathCchRemoveFileSpec %ls %u",
        (const char *)v18,
        v36);
      operator delete(v18, v38);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_25;
    }
    v39 = StateCreation::RemoveEmptyCentennialStateFolders(v37, (const unsigned __int16 *)v18);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xFF7,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)v39,
      (__int64)"RemoveEmptyCentennialStateFolders %ls",
      (const char *)v18);
  }
  if ( v2 )
  {
    v25 = StateCreation::RemoveSecureAppDataFolder(this, v9);
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xFFE,
        (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
        (const char *)(unsigned int)v25,
        (int)"RemoveSecureAppDataFolder %ls",
        (const char *)v9);
      operator delete(v18, v40);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_25;
    }
  }
  if ( v11 )
  {
    v41 = v50[1];
    v25 = StateCreation::RemoveSecureAppDataFolder(this, (const unsigned __int16 *)v50[1]);
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1005,
        (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
        (const char *)(unsigned int)v25,
        (int)"RemoveSecureAppDataFolder %ls",
        v41);
      operator delete(v18, v42);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_25;
    }
  }
  operator delete(v18, v26);
  Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  operator delete(v5, v43);
  v15 = 0;
LABEL_57:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v50);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v52);
  return v15;
}

```

## disassembly

```asm
0x1800a89f4  mov     [rsp-8+arg_0], rcx
0x1800a89f9  push    rbp
0x1800a89fa  push    rbx
0x1800a89fb  push    rsi
0x1800a89fc  push    rdi
0x1800a89fd  push    r12
0x1800a89ff  push    r13
0x1800a8a01  push    r14
0x1800a8a03  push    r15
0x1800a8a05  lea     rbp, [rsp-1Fh]
0x1800a8a0a  sub     rsp, 88h
0x1800a8a11  mov     rbx, rcx
0x1800a8a14  xorps   xmm0, xmm0
0x1800a8a17  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800a8a1b  xor     esi, esi
0x1800a8a1d  mov     [rbp+57h+var_48], esi
0x1800a8a20  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800a8a24  mov     [rbp+57h+var_60], esi
0x1800a8a27  movzx   r14d, sil
0x1800a8a2b  mov     [rbp+57h+arg_8], rsi
0x1800a8a2f  lea     rdx, [rbp+57h+arg_8]; unsigned __int16 **
0x1800a8a33  call    ?GetSystemAppDataFolderPath@StateCreation@@AEAAJPEAPEAG@Z; StateCreation::GetSystemAppDataFolderPath(ushort * *)
0x1800a8a38  lea     r15d, [rsi+1]
0x1800a8a3c  mov     rdi, [rbp+57h+arg_8]
0x1800a8a40  test    eax, eax
0x1800a8a42  js      short loc_1800A8ABD
0x1800a8a44  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800a8a48  lea     rdx, aHeliumCache; "Helium\\Cache"
0x1800a8a4f  mov     rcx, rdi; this
0x1800a8a52  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x1800a8a57  mov     r13, [rbp+57h+var_58+8]
0x1800a8a5b  test    eax, eax
0x1800a8a5d  js      short loc_1800A8A7C
0x1800a8a5f  mov     qword ptr [rsp+0C0h+var_A0], rsi; __int64
0x1800a8a64  lea     r9, ?LogRemoveDirectoryTreeError@DirectoryPaths@@YAJPEBGW4ActionType@@JPEAX@Z; DirectoryPaths::LogRemoveDirectoryTreeError(ushort const *,ActionType,long,void *)
0x1800a8a6b  xor     edx, edx
0x1800a8a6d  mov     rcx, r13; unsigned __int16 *
0x1800a8a70  call    RemoveDirectoryTree
0x1800a8a75  cmp     eax, 5
0x1800a8a78  cmovz   r14d, r15d
0x1800a8a7c  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x1800a8a80  lea     rdx, aHelium; "Helium"
0x1800a8a87  mov     rcx, rdi; this
0x1800a8a8a  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x1800a8a8f  test    eax, eax
0x1800a8a91  js      short loc_1800A8AB8
0x1800a8a93  test    r14b, r14b
0x1800a8a96  jnz     short loc_1800A8AB8
0x1800a8a98  mov     qword ptr [rsp+0C0h+var_A0], rsi; __int64
0x1800a8a9d  lea     r9, ?LogRemoveDirectoryTreeError@DirectoryPaths@@YAJPEBGW4ActionType@@JPEAX@Z; DirectoryPaths::LogRemoveDirectoryTreeError(ushort const *,ActionType,long,void *)
0x1800a8aa4  xor     edx, edx
0x1800a8aa6  mov     rcx, [rbp+57h+var_70+8]; unsigned __int16 *
0x1800a8aaa  call    RemoveDirectoryTree
0x1800a8aaf  cmp     eax, 5
0x1800a8ab2  setz    r12b
0x1800a8ab6  jmp     short loc_1800A8AC4
0x1800a8ab8  mov     r12b, r14b
0x1800a8abb  jmp     short loc_1800A8AC4
0x1800a8abd  mov     r12b, sil
0x1800a8ac0  mov     r13, [rbp+57h+var_58+8]
0x1800a8ac4  mov     [rbp+57h+hObject], rsi
0x1800a8ac8  lea     rcx, [rbp+57h+hObject]; TokenHandle
0x1800a8acc  call    ?GetEffectiveToken@ImpersonationContext@Common@@SAJPEAPEAX@Z; Common::ImpersonationContext::GetEffectiveToken(void * *)
0x1800a8ad1  mov     [rbp+57h+arg_10], eax
0x1800a8ad4  mov     rcx, [rbp+5Fh]; this
0x1800a8ad8  lea     r15, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8adf  test    eax, eax
0x1800a8ae1  jns     short loc_1800A8AF4
0x1800a8ae3  mov     r9d, eax; char *
0x1800a8ae6  mov     r8, r15; unsigned int
0x1800a8ae9  mov     edx, 0FC7h; void *
0x1800a8aee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a8af3  nop
0x1800a8af4  mov     [rbp+57h+TokenHandle], rsi
0x1800a8af8  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800a8afc  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x1800a8b01  mov     rcx, [rbp+5Fh]; this
0x1800a8b05  test    eax, eax
0x1800a8b07  jns     short loc_1800A8B1A
0x1800a8b09  mov     r9d, eax; char *
0x1800a8b0c  mov     r8, r15; unsigned int
0x1800a8b0f  mov     edx, 0FCCh; void *
0x1800a8b14  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a8b19  nop
0x1800a8b1a  mov     [rbp+57h+pszPath], rsi
0x1800a8b1e  lea     rdx, [rbp+57h+pszPath]; unsigned __int16 **
0x1800a8b22  mov     rcx, rbx; this
0x1800a8b25  call    ?GetSecureSystemAppDataFolderPath@StateCreation@@AEAAJPEAPEAG@Z; StateCreation::GetSecureSystemAppDataFolderPath(ushort * *)
0x1800a8b2a  mov     ebx, eax
0x1800a8b2c  test    eax, eax
0x1800a8b2e  jns     short loc_1800A8B7C
0x1800a8b30  mov     rcx, [rbp+5Fh]; this
0x1800a8b34  mov     r9d, eax; char *
0x1800a8b37  mov     r8, r15; unsigned int
0x1800a8b3a  mov     edx, 0FCFh; void *
0x1800a8b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8b44  nop
0x1800a8b45  mov     rcx, [rbp+57h+pszPath]; void *
0x1800a8b49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8b4e  nop
0x1800a8b4f  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800a8b53  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800a8b58  nop
0x1800a8b59  mov     rcx, [rbp+57h+hObject]; hObject
0x1800a8b5d  lea     rax, [rcx-1]
0x1800a8b61  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8b65  ja      short loc_1800A8B6E
0x1800a8b67  call    cs:__imp_CloseHandle
0x1800a8b6d  nop
0x1800a8b6e  mov     rcx, rdi; void *
0x1800a8b71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8b76  nop
0x1800a8b77  jmp     loc_1800A8F52
0x1800a8b7c  mov     byte ptr [rbp+57h+arg_8], sil
0x1800a8b80  mov     rbx, [rbp+57h+pszPath]
0x1800a8b84  mov     rcx, rbx; unsigned __int16 *
0x1800a8b87  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800a8b8c  mov     rsi, rax
0x1800a8b8f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a8b93  mov     r8, r15
0x1800a8b96  cmp     [rbp+57h+arg_10], 0
0x1800a8b9a  cmovge  r8, [rbp+57h+hObject]; unsigned __int16 *
0x1800a8b9f  lea     rax, [rbp+57h+arg_8]
0x1800a8ba3  mov     qword ptr [rsp+0C0h+var_A0], rax; bool
0x1800a8ba8  mov     r9b, 1; void *
0x1800a8bab  lea     rdx, aSecuresystemap_0; "SecureSystemAppData"
0x1800a8bb2  mov     rcx, rbx; this
0x1800a8bb5  call    ?CheckDirectoryExistenceAndLogIfNeeded@StateCreationHelpers@@YAJPEBG0PEAX_NPEA_N@Z; StateCreationHelpers::CheckDirectoryExistenceAndLogIfNeeded(ushort const *,ushort const *,void *,bool,bool *)
0x1800a8bba  mov     rcx, [rbp+5Fh]; this
0x1800a8bbe  mov     [rsp+0C0h+var_98], rsi; char *
0x1800a8bc3  lea     rdx, aCheckdirectory_3; "CheckDirectoryExistenceAndLogIfNeeded %"...
0x1800a8bca  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x1800a8bcf  mov     r9d, eax; char *
0x1800a8bd2  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8bd9  mov     edx, 0FD4h; void *
0x1800a8bde  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800a8be3  mov     esi, eax
0x1800a8be5  mov     edx, 800700B7h
0x1800a8bea  cmp     eax, edx
0x1800a8bec  jz      short loc_1800A8C59
0x1800a8bee  add     eax, 7FF8FFFEh
0x1800a8bf3  cmp     eax, 1Eh
0x1800a8bf6  ja      short loc_1800A8C02
0x1800a8bf8  mov     ecx, 4000000Bh
0x1800a8bfd  bt      ecx, eax
0x1800a8c00  jb      short loc_1800A8C59
0x1800a8c02  xor     ecx, ecx
0x1800a8c04  test    esi, esi
0x1800a8c06  jns     short loc_1800A8C5B
0x1800a8c08  mov     rcx, [rbp+5Fh]; this
0x1800a8c0c  mov     r9d, esi; char *
0x1800a8c0f  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8c16  mov     edx, 0FDEh; void *
0x1800a8c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8c20  nop
0x1800a8c21  mov     rcx, rbx; void *
0x1800a8c24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8c29  nop
0x1800a8c2a  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800a8c2e  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800a8c33  nop
0x1800a8c34  mov     rcx, [rbp+57h+hObject]; hObject
0x1800a8c38  lea     rax, [rcx-1]
0x1800a8c3c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8c40  ja      short loc_1800A8C49
0x1800a8c42  call    cs:__imp_CloseHandle
0x1800a8c48  nop
0x1800a8c49  mov     rcx, rdi; void *
0x1800a8c4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8c51  nop
0x1800a8c52  mov     ebx, esi
0x1800a8c54  jmp     loc_1800A8F52
0x1800a8c59  xor     ecx, ecx
0x1800a8c5b  cmp     byte ptr [rbp+57h+arg_8], cl
0x1800a8c5e  jnz     short loc_1800A8C68
0x1800a8c60  cmp     esi, edx
0x1800a8c62  jnz     loc_1800A8E27
0x1800a8c68  mov     rax, r15
0x1800a8c6b  inc     rax
0x1800a8c6e  cmp     [rbx+rax*2], cx
0x1800a8c72  jnz     short loc_1800A8C6B
0x1800a8c74  inc     rax
0x1800a8c77  mov     [rbp+57h+arg_8], rax
0x1800a8c7b  mov     rdx, rax; cchPath
0x1800a8c7e  mov     rcx, rbx; pszPath
0x1800a8c81  call    cs:__imp_PathCchRemoveFileSpec
0x1800a8c87  mov     esi, eax
0x1800a8c89  test    eax, eax
0x1800a8c8b  jns     short loc_1800A8CF5
0x1800a8c8d  mov     rcx, [rbp+5Fh]; this
0x1800a8c91  mov     rax, [rbp+57h+arg_8]
0x1800a8c95  mov     [rsp+0C0h+var_90], eax
0x1800a8c99  mov     [rsp+0C0h+var_98], rbx; char *
0x1800a8c9e  lea     rax, aPathcchremovef_1; "PathCchRemoveFileSpec %ls %u"
0x1800a8ca5  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800a8caa  mov     r9d, esi; char *
0x1800a8cad  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8cb4  mov     edx, 0FE9h; void *
0x1800a8cb9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8cbe  nop
0x1800a8cbf  mov     rcx, rbx; void *
0x1800a8cc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8cc7  nop
0x1800a8cc8  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800a8ccc  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800a8cd1  nop
0x1800a8cd2  mov     rcx, [rbp+57h+hObject]; hObject
0x1800a8cd6  lea     rax, [rcx-1]
0x1800a8cda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8cde  ja      short loc_1800A8CE7
0x1800a8ce0  call    cs:__imp_CloseHandle
0x1800a8ce6  nop
0x1800a8ce7  mov     rcx, rdi; void *
0x1800a8cea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8cef  nop
0x1800a8cf0  jmp     loc_1800A8C52
0x1800a8cf5  xor     esi, esi
0x1800a8cf7  mov     qword ptr [rsp+0C0h+var_A0], rsi; __int64
0x1800a8cfc  lea     r9, ?LogRemoveDirectoryTreeError@DirectoryPaths@@YAJPEBGW4ActionType@@JPEAX@Z; DirectoryPaths::LogRemoveDirectoryTreeError(ushort const *,ActionType,long,void *)
0x1800a8d03  xor     edx, edx
0x1800a8d05  mov     rcx, rbx; unsigned __int16 *
0x1800a8d08  call    RemoveDirectoryTree
0x1800a8d0d  test    eax, eax
0x1800a8d0f  jz      short loc_1800A8D72
0x1800a8d11  mov     rcx, [rbp+5Fh]; this
0x1800a8d15  mov     [rsp+0C0h+var_98], rbx; char *
0x1800a8d1a  lea     rdx, aRemovedirector; "RemoveDirectoryTree %ls"
0x1800a8d21  mov     qword ptr [rsp+0C0h+var_A0], rdx; unsigned int
0x1800a8d26  mov     r9d, eax; char *
0x1800a8d29  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8d30  mov     edx, 0FEDh; void *
0x1800a8d35  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800a8d3a  mov     esi, eax
0x1800a8d3c  mov     rcx, rbx; void *
0x1800a8d3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8d44  nop
0x1800a8d45  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800a8d49  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800a8d4e  nop
0x1800a8d4f  mov     rcx, [rbp+57h+hObject]; hObject
0x1800a8d53  lea     rdx, [rcx-1]
0x1800a8d57  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a8d5b  ja      short loc_1800A8D64
0x1800a8d5d  call    cs:__imp_CloseHandle
0x1800a8d63  nop
0x1800a8d64  mov     rcx, rdi; void *
0x1800a8d67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8d6c  nop
0x1800a8d6d  jmp     loc_1800A8C52
0x1800a8d72  inc     r15
0x1800a8d75  cmp     [rbx+r15*2], si
0x1800a8d7a  jnz     short loc_1800A8D72
0x1800a8d7c  inc     r15
0x1800a8d7f  mov     rdx, r15; cchPath
0x1800a8d82  mov     rcx, rbx; pszPath
0x1800a8d85  call    cs:__imp_PathCchRemoveFileSpec
0x1800a8d8b  mov     esi, eax
0x1800a8d8d  test    eax, eax
0x1800a8d8f  jns     short loc_1800A8DF6
0x1800a8d91  mov     rcx, [rbp+5Fh]; this
0x1800a8d95  mov     [rsp+0C0h+var_90], r15d
0x1800a8d9a  mov     [rsp+0C0h+var_98], rbx; char *
0x1800a8d9f  lea     rax, aPathcchremovef_1; "PathCchRemoveFileSpec %ls %u"
0x1800a8da6  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800a8dab  mov     r9d, esi; char *
0x1800a8dae  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8db5  mov     edx, 0FF2h; void *
0x1800a8dba  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8dbf  nop
0x1800a8dc0  mov     rcx, rbx; void *
0x1800a8dc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8dc8  nop
0x1800a8dc9  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800a8dcd  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800a8dd2  nop
0x1800a8dd3  mov     rcx, [rbp+57h+hObject]; hObject
0x1800a8dd7  lea     rax, [rcx-1]
0x1800a8ddb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8ddf  ja      short loc_1800A8DE8
0x1800a8de1  call    cs:__imp_CloseHandle
0x1800a8de7  nop
0x1800a8de8  mov     rcx, rdi; void *
0x1800a8deb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a8df0  nop
0x1800a8df1  jmp     loc_1800A8C52
0x1800a8df6  mov     rdx, rbx; unsigned __int16 *
0x1800a8df9  call    ?RemoveEmptyCentennialStateFolders@StateCreation@@AEAAJPEBG@Z; StateCreation::RemoveEmptyCentennialStateFolders(ushort const *)
0x1800a8dfe  mov     rcx, [rbp+5Fh]; this
0x1800a8e02  mov     [rsp+0C0h+var_98], rbx; char *
0x1800a8e07  lea     rdx, aRemoveemptycen; "RemoveEmptyCentennialStateFolders %ls"
0x1800a8e0e  mov     qword ptr [rsp+0C0h+var_A0], rdx; __int64
0x1800a8e13  mov     r9d, eax; char *
0x1800a8e16  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8e1d  mov     edx, 0FF7h; void *
0x1800a8e22  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800a8e27  mov     r15, [rbp+57h+arg_0]
0x1800a8e2b  test    r14b, r14b
0x1800a8e2e  jz      short loc_1800A8EA1
0x1800a8e30  mov     rdx, r13; unsigned __int16 *
0x1800a8e33  mov     rcx, r15; this
  ... truncated ...
```
