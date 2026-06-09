# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *)

- ea: `0x18005def4`
- end: `0x18005e4d2`
- name: `?CreateWorkerProcess@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus_Exp2@2345@@Z`
- size: `1502`
- prototype: `int(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *__hidden this, const wchar_t *, wchar_t *, void **, unsigned int *, enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005e6a0`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000bd98`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x1800185c0`
- `0x1800350b4`
- `0x18003c638`
- `0x1800486b8`
- `0x180048fbc`
- `0x18005def4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e3cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18005e3c5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18005e3c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e483`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e1fd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e1fd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e3f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e419`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e3f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e419`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e2d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e2d8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005e32a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005e32a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005df48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005df48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e44c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e44c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005e261`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005e261`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18005dfdb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18005dfdb`
- `USERENV!CreateEnvironmentBlock` at `0x18005e18f`
- `USERENV!CreateEnvironmentBlock` at `0x18005e18f`
- `USERENV!DestroyEnvironmentBlock` at `0x18005e2bd`
- `USERENV!DestroyEnvironmentBlock` at `0x18005e460`
- `USERENV!DestroyEnvironmentBlock` at `0x18005e2bd`
- `USERENV!DestroyEnvironmentBlock` at `0x18005e460`

## string_xrefs

- `0x18005dff9`: `WTSQueryUserToken failed for user %s (session %u): %#x`
- `0x18005e284`: `SetEntriesInAcl failed for user %s: %#x`
- `0x18005e1a7`: `CreateEnvironmentBlock failed for user %s: %#x`
- `0x18005e342`: `ImpersonateLoggedOnUser failed for user %s: %#x`
- `0x18005e407`: `Process created: %s (pid %u)`
- `0x18005e4ae`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005e4c0`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::CreateWorkerProcess(
        HSTRING *this,
        const wchar_t *a2,
        wchar_t *a3,
        void **a4,
        unsigned int *a5,
        enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *a6)
{
  const wchar_t *StringRawBuffer; // rsi
  __int64 LastError; // rdi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // r9
  WCHAR *v18; // rax
  DWORD v19; // eax
  _QWORD *v20; // r8
  const char *v21; // r9
  struct _PROCESS_INFORMATION *v22; // rdx
  WCHAR *v23; // r8
  struct _PROCESS_INFORMATION *v24; // rdx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  void *phToken; // [rsp+60h] [rbp-A0h] BYREF
  ULONG SessionId; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Environment; // [rsp+70h] [rbp-90h] BYREF
  PACL NewAcl; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  char v31; // [rsp+89h] [rbp-77h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v33; // [rsp+A8h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v37; // [rsp+118h] [rbp+18h]
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp+20h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+190h] [rbp+90h] BYREF
  __int128 Src; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v41; // [rsp+1C0h] [rbp+C0h]
  _OWORD v42[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v43[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v44[2]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v33 = a5;
  StringRawBuffer = WindowsGetStringRawBuffer(this[23], 0);
  Log(4u, L"Creating process in user %s session: %s %s", StringRawBuffer, a2, a3);
  *(_DWORD *)a6 = 1;
  *a4 = 0;
  *a5 = 0;
  if ( !this[17] )
    return 2147947423LL;
  SessionId = 0;
  if ( !FindSessionForUser(StringRawBuffer, &SessionId) )
  {
    Log(2u, L"Did not find a session for user %s", StringRawBuffer);
    *(_DWORD *)a6 = 5;
    return 2147549183LL;
  }
  phToken = 0;
  if ( !WTSQueryUserToken(SessionId, &phToken) )
  {
    LODWORD(LastError) = GetLastError();
    LODWORD(lpThreadAttributes) = LastError;
    Log(2u, L"WTSQueryUserToken failed for user %s (session %u): %#x", StringRawBuffer, SessionId, lpThreadAttributes);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  memset(v43, 0, sizeof(v43));
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  std::wstring::_Construct<1,wchar_t const *>((char **)v43, a3, v14);
  memset(v42, 0, sizeof(v42));
  do
    ++v13;
  while ( a2[v13] );
  std::wstring::_Construct<1,wchar_t const *>((char **)v42, a2, v13);
  v15 = std::wstring::_Insert<wchar_t>(v42);
  Src = 0;
  v41 = 0;
  Src = *(_OWORD *)v15;
  v41 = *(_OWORD *)(v15 + 16);
  *(_QWORD *)(v15 + 24) = 7;
  *(_WORD *)v15 = 0;
  *(_QWORD *)(v15 + 16) = 0;
  v16 = std::wstring::append(&Src, L"\" ");
  v44[0] = *(_OWORD *)v16;
  v44[1] = *(_OWORD *)(v16 + 16);
  *(_WORD *)v16 = 0;
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  std::operator+<wchar_t>(lpCommandLine, v44, v43);
  std::wstring::~wstring((char **)v44);
  std::wstring::~wstring((char **)&Src);
  std::wstring::~wstring((char **)v42);
  std::wstring::~wstring((char **)v43);
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, phToken, 0) )
  {
    LastError = GetLastError();
    Log(2u, L"CreateEnvironmentBlock failed for user %s: %#x", StringRawBuffer, LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    std::wstring::~wstring((char **)lpCommandLine);
LABEL_8:
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    return (unsigned int)LastError;
  }
  *(_QWORD *)&Src = &Environment;
  BYTE8(Src) = 1;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v37 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x16A,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      v17);
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
  pListOfExplicitEntries.grfAccessPermissions = 1052672;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  v18 = (WCHAR *)(this + 7);
  if ( (unsigned __int64)this[10] > 7 )
    v18 = *(WCHAR **)v18;
  pListOfExplicitEntries.Trustee.ptstrName = v18;
  NewAcl = 0;
  v30 = 0;
  if ( !SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
  {
    v19 = GetLastError();
    LODWORD(LastError) = v19;
    v20 = this + 11;
    if ( (unsigned __int64)this[14] > 7 )
      v20 = (_QWORD *)*v20;
    Log(2u, L"SetEntriesInAcl failed for user %s: %#x", v20, v19);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x17D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      v21);
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  *(_QWORD *)&ProcessAttributes.bInheritHandle = 0;
  ProcessAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !ImpersonateLoggedOnUser(phToken) )
  {
    LastError = GetLastError();
    Log(2u, L"ImpersonateLoggedOnUser failed for user %s: %#x", StringRawBuffer, LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v22);
LABEL_27:
    if ( NewAcl )
    {
      LocalFree(NewAcl);
      NewAcl = 0;
      v30 = 0;
    }
    DestroyEnvironmentBlock(Environment);
    goto LABEL_18;
  }
  v31 = 1;
  v23 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v23 = lpCommandLine[0];
  if ( !CreateProcessAsUserW(
          phToken,
          a2,
          v23,
          &ProcessAttributes,
          0,
          0,
          0x400u,
          Environment,
          0,
          &StartupInfo,
          &ProcessInformation) )
  {
    LastError = GetLastError();
    Log(2u, L"Process creation failed: %#x", LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    RevertToSelf();
    goto LABEL_34;
  }
  Log(4u, L"Process created: %s (pid %u)", a2, ProcessInformation.dwProcessId);
  RevertToSelf();
  *a4 = ProcessInformation.hProcess;
  ProcessInformation.hProcess = 0;
  *v33 = ProcessInformation.dwProcessId;
  *(_DWORD *)a6 = 0;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
    v30 = 0;
  }
  DestroyEnvironmentBlock(Environment);
  std::wstring::~wstring((char **)lpCommandLine);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  return 0;
}

```

## disassembly

```asm
0x18005def4  push    rbp
0x18005def6  push    rbx
0x18005def7  push    rsi
0x18005def8  push    rdi
0x18005def9  push    r12
0x18005defb  push    r13
0x18005defd  push    r14
0x18005deff  push    r15
0x18005df01  lea     rbp, [rsp-148h]
0x18005df09  sub     rsp, 248h
0x18005df10  mov     rax, cs:__security_cookie
0x18005df17  xor     rax, rsp
0x18005df1a  mov     [rbp+180h+var_50], rax
0x18005df21  mov     r13, r9
0x18005df24  mov     r15, r8
0x18005df27  mov     rdi, rdx
0x18005df2a  mov     r14, rcx
0x18005df2d  mov     rbx, [rbp+180h+arg_20]
0x18005df34  mov     [rbp+180h+var_1D8], rbx
0x18005df38  mov     r12, [rbp+180h+arg_28]
0x18005df3f  xor     edx, edx; length
0x18005df41  mov     rcx, [rcx+0B8h]; string
0x18005df48  call    cs:__imp_WindowsGetStringRawBuffer
0x18005df4e  mov     rsi, rax
0x18005df51  mov     [rsp+280h+lpThreadAttributes], r15
0x18005df56  mov     r9, rdi
0x18005df59  mov     r8, rax
0x18005df5c  lea     rdx, aCreatingProces
0x18005df63  mov     ecx, 4; unsigned __int8
0x18005df68  call    ?Log@@YAXEPEB_WZZ
0x18005df6d  mov     dword ptr [r12], 1
0x18005df75  xor     eax, eax
0x18005df77  mov     [r13+0], rax
0x18005df7b  mov     [rbx], eax
0x18005df7d  xor     ebx, ebx
0x18005df7f  cmp     [r14+88h], rbx
0x18005df86  jnz     short loc_18005DF92
0x18005df88  mov     eax, 8007139Fh
0x18005df8d  jmp     loc_18005E48B
0x18005df92  mov     [rsp+280h+SessionId], ebx
0x18005df96  lea     rdx, [rsp+280h+SessionId]; unsigned int *
0x18005df9b  mov     rcx, rsi; wchar_t *
0x18005df9e  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z
0x18005dfa3  test    al, al
0x18005dfa5  jnz     short loc_18005DFCD
0x18005dfa7  mov     r8, rsi
0x18005dfaa  lea     rdx, aDidNotFindASes
0x18005dfb1  mov     ecx, 2; unsigned __int8
0x18005dfb6  call    ?Log@@YAXEPEB_WZZ
0x18005dfbb  mov     dword ptr [r12], 5
0x18005dfc3  mov     eax, 8000FFFFh
0x18005dfc8  jmp     loc_18005E48B
0x18005dfcd  mov     [rsp+280h+phToken], rbx
0x18005dfd2  lea     rdx, [rsp+280h+phToken]; phToken
0x18005dfd7  mov     ecx, [rsp+280h+SessionId]; SessionId
0x18005dfdb  call    cs:__imp_WTSQueryUserToken
0x18005dfe1  test    eax, eax
0x18005dfe3  jnz     short loc_18005E033
0x18005dfe5  call    cs:__imp_GetLastError
0x18005dfeb  mov     edi, eax
0x18005dfed  mov     dword ptr [rsp+280h+lpThreadAttributes], eax
0x18005dff1  mov     r9d, [rsp+280h+SessionId]
0x18005dff6  mov     r8, rsi
0x18005dff9  lea     rdx, aWtsqueryuserto_0
0x18005e000  mov     ecx, 2; unsigned __int8
0x18005e005  call    ?Log@@YAXEPEB_WZZ
0x18005e00a  test    edi, edi
0x18005e00c  jle     short loc_18005E017
0x18005e00e  movzx   edi, di
0x18005e011  or      edi, 80070000h
0x18005e017  mov     rcx, [rsp+280h+phToken]; hObject
0x18005e01c  lea     rdx, [rcx-1]
0x18005e020  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005e024  ja      short loc_18005E02C
0x18005e026  call    cs:__imp_CloseHandle
0x18005e02c  mov     eax, edi
0x18005e02e  jmp     loc_18005E48B
0x18005e033  xorps   xmm0, xmm0
0x18005e036  movups  [rbp+180h+var_90], xmm0
0x18005e03d  xorps   xmm1, xmm1
0x18005e040  movdqu  [rbp+180h+var_80], xmm1
0x18005e048  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005e04c  mov     r8, rbx
0x18005e04f  xor     eax, eax
0x18005e051  inc     r8
0x18005e054  cmp     [r15+r8*2], ax
0x18005e059  jnz     short loc_18005E051
0x18005e05b  mov     rdx, r15
0x18005e05e  lea     rcx, [rbp+180h+var_90]
0x18005e065  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z
0x18005e06a  nop
0x18005e06b  xorps   xmm0, xmm0
0x18005e06e  movups  [rbp+180h+var_B0], xmm0
0x18005e075  xorps   xmm1, xmm1
0x18005e078  movdqu  [rbp+180h+var_A0], xmm1
0x18005e080  xor     r15d, r15d
0x18005e083  inc     rbx
0x18005e086  cmp     [rdi+rbx*2], r15w
0x18005e08b  jnz     short loc_18005E083
0x18005e08d  mov     r8, rbx
0x18005e090  mov     rdx, rdi
0x18005e093  lea     rcx, [rbp+180h+var_B0]
0x18005e09a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z
0x18005e09f  nop
0x18005e0a0  mov     ebx, 1
0x18005e0a5  mov     r9d, ebx
0x18005e0a8  lea     r8, asc_1800A1348
0x18005e0af  xor     edx, edx
0x18005e0b1  lea     rcx, [rbp+180h+var_B0]; Src
0x18005e0b8  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z
0x18005e0bd  xorps   xmm0, xmm0
0x18005e0c0  movups  [rbp+180h+Src], xmm0
0x18005e0c7  xorps   xmm1, xmm1
0x18005e0ca  movdqu  [rbp+180h+var_C0], xmm1
0x18005e0d2  movups  xmm0, xmmword ptr [rax]
0x18005e0d5  movups  [rbp+180h+Src], xmm0
0x18005e0dc  movups  xmm1, xmmword ptr [rax+10h]
0x18005e0e0  movups  [rbp+180h+var_C0], xmm1
0x18005e0e7  mov     qword ptr [rax+18h], 7
0x18005e0ef  mov     [rax], r15w
0x18005e0f3  mov     [rax+10h], r15
0x18005e0f7  lea     rdx, asc_1800A134C
0x18005e0fe  lea     rcx, [rbp+180h+Src]; Src
0x18005e105  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z
0x18005e10a  movups  xmm0, xmmword ptr [rax]
0x18005e10d  movups  [rbp+180h+var_70], xmm0
0x18005e114  movups  xmm1, xmmword ptr [rax+10h]
0x18005e118  movups  [rbp+180h+var_60], xmm1
0x18005e11f  mov     [rax], r15w
0x18005e123  mov     [rax+10h], r15
0x18005e127  mov     qword ptr [rax+18h], 7
0x18005e12f  lea     r8, [rbp+180h+var_90]
0x18005e136  lea     rdx, [rbp+180h+var_70]
0x18005e13d  lea     rcx, [rbp+180h+lpCommandLine]
0x18005e144  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z
0x18005e149  nop
0x18005e14a  lea     rcx, [rbp+180h+var_70]
0x18005e151  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18005e156  nop
0x18005e157  lea     rcx, [rbp+180h+Src]
0x18005e15e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18005e163  nop
0x18005e164  lea     rcx, [rbp+180h+var_B0]
0x18005e16b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18005e170  nop
0x18005e171  lea     rcx, [rbp+180h+var_90]
0x18005e178  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18005e17d  mov     [rsp+280h+Environment], r15
0x18005e182  xor     r8d, r8d; bInherit
0x18005e185  mov     rdx, [rsp+280h+phToken]; hToken
0x18005e18a  lea     rcx, [rsp+280h+Environment]; lpEnvironment
0x18005e18f  call    cs:__imp_CreateEnvironmentBlock
0x18005e195  test    eax, eax
0x18005e197  jnz     short loc_18005E1D4
0x18005e199  call    cs:__imp_GetLastError
0x18005e19f  mov     edi, eax
0x18005e1a1  mov     r9d, eax
0x18005e1a4  mov     r8, rsi
0x18005e1a7  lea     rdx, aCreateenvironm_0
0x18005e1ae  lea     ecx, [rbx+1]; unsigned __int8
0x18005e1b1  call    ?Log@@YAXEPEB_WZZ
0x18005e1b6  test    edi, edi
0x18005e1b8  jle     short loc_18005E1C3
0x18005e1ba  movzx   edi, di
0x18005e1bd  or      edi, 80070000h
0x18005e1c3  lea     rcx, [rbp+180h+lpCommandLine]
0x18005e1ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18005e1cf  jmp     loc_18005E017
0x18005e1d4  lea     rax, [rsp+280h+Environment]
0x18005e1d9  mov     qword ptr [rbp+180h+Src], rax
0x18005e1e0  mov     byte ptr [rbp+180h+Src+8], bl
0x18005e1e6  xorps   xmm0, xmm0
0x18005e1e9  xor     eax, eax
0x18005e1eb  movups  [rbp+180h+pSecurityDescriptor], xmm0
0x18005e1ef  movups  [rbp+180h+var_178], xmm0
0x18005e1f3  mov     [rbp+180h+var_168], rax
0x18005e1f7  mov     edx, ebx; dwRevision
0x18005e1f9  lea     rcx, [rbp+180h+pSecurityDescriptor]; pSecurityDescriptor
0x18005e1fd  call    cs:__imp_InitializeSecurityDescriptor
0x18005e203  mov     rcx, [rbp+188h]; this
0x18005e20a  test    eax, eax
0x18005e20c  jz      loc_18005E4C0
0x18005e212  xorps   xmm0, xmm0
0x18005e215  movdqu  xmmword ptr [rbp+180h+pListOfExplicitEntries+0Ch], xmm0
0x18005e21a  mov     qword ptr [rbp+180h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18005e222  mov     [rbp+180h+pListOfExplicitEntries.grfAccessPermissions], 101000h
0x18005e229  mov     ebx, 2
0x18005e22e  mov     qword ptr [rbp+180h+pListOfExplicitEntries.grfAccessMode], rbx
0x18005e232  mov     [rbp+180h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x18005e236  lea     rax, [r14+38h]
0x18005e23a  cmp     qword ptr [rax+18h], 7
0x18005e23f  jbe     short loc_18005E244
0x18005e241  mov     rax, [rax]
0x18005e244  mov     [rbp+180h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18005e248  mov     [rsp+280h+NewAcl], r15
0x18005e24d  mov     [rbp+180h+var_200], r15
0x18005e251  lea     r9, [rsp+280h+NewAcl]; NewAcl
0x18005e256  xor     r8d, r8d; OldAcl
0x18005e259  lea     rdx, [rbp+180h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005e25d  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x18005e261  call    cs:__imp_SetEntriesInAclW
0x18005e267  test    eax, eax
0x18005e269  jnz     short loc_18005E2C8
0x18005e26b  call    cs:__imp_GetLastError
0x18005e271  mov     edi, eax
0x18005e273  lea     r8, [r14+58h]
0x18005e277  cmp     qword ptr [r8+18h], 7
0x18005e27c  jbe     short loc_18005E281
0x18005e27e  mov     r8, [r8]
0x18005e281  mov     r9d, edi
0x18005e284  lea     rdx, aSetentriesinac
0x18005e28b  mov     ecx, ebx; unsigned __int8
0x18005e28d  call    ?Log@@YAXEPEB_WZZ
0x18005e292  test    edi, edi
0x18005e294  jle     short loc_18005E29F
0x18005e296  movzx   edi, di
0x18005e299  or      edi, 80070000h
0x18005e29f  mov     rcx, [rsp+280h+NewAcl]; hMem
0x18005e2a4  test    rcx, rcx
0x18005e2a7  jz      short loc_18005E2B8
0x18005e2a9  call    cs:__imp_LocalFree
0x18005e2af  mov     [rsp+280h+NewAcl], r15
0x18005e2b4  mov     [rbp+180h+var_200], r15
0x18005e2b8  mov     rcx, [rsp+280h+Environment]; lpEnvironment
0x18005e2bd  call    cs:__imp_DestroyEnvironmentBlock
0x18005e2c3  jmp     loc_18005E1C3
0x18005e2c8  xor     r9d, r9d; bDaclDefaulted
0x18005e2cb  mov     r8, [rsp+280h+NewAcl]; pDacl
0x18005e2d0  lea     edx, [r9+1]; bDaclPresent
0x18005e2d4  lea     rcx, [rbp+180h+pSecurityDescriptor]; pSecurityDescriptor
0x18005e2d8  call    cs:__imp_SetSecurityDescriptorDacl
0x18005e2de  mov     rcx, [rbp+188h]; this
0x18005e2e5  test    eax, eax
0x18005e2e7  jz      loc_18005E4AE
0x18005e2ed  mov     qword ptr [rbp+180h+ProcessAttributes.nLength], 18h
0x18005e2f5  mov     qword ptr [rbp+180h+ProcessAttributes.bInheritHandle], r15
0x18005e2f9  lea     rax, [rbp+180h+pSecurityDescriptor]
0x18005e2fd  mov     [rbp+180h+ProcessAttributes.lpSecurityDescriptor], rax
0x18005e301  mov     qword ptr [rbp+180h+StartupInfo.cb], 68h ; 'h'
0x18005e309  xor     edx, edx; Val
0x18005e30b  lea     r8d, [rdx+60h]; Size
0x18005e30f  lea     rcx, [rbp+180h+StartupInfo.lpReserved]; void *
0x18005e313  call    memset_0
0x18005e318  xorps   xmm0, xmm0
0x18005e31b  xor     eax, eax
0x18005e31d  movups  xmmword ptr [rbp+180h+ProcessInformation.hProcess], xmm0
0x18005e321  mov     qword ptr [rbp+180h+ProcessInformation.dwProcessId], rax
0x18005e325  mov     rcx, [rsp+280h+phToken]; hToken
0x18005e32a  call    cs:__imp_ImpersonateLoggedOnUser
0x18005e330  test    eax, eax
0x18005e332  jnz     short loc_18005E36B
0x18005e334  call    cs:__imp_GetLastError
0x18005e33a  mov     edi, eax
0x18005e33c  mov     r9d, eax
0x18005e33f  mov     r8, rsi
0x18005e342  lea     rdx, aImpersonatelog
0x18005e349  mov     ecx, ebx; unsigned __int8
0x18005e34b  call    ?Log@@YAXEPEB_WZZ
0x18005e350  test    edi, edi
0x18005e352  jle     short loc_18005E35D
0x18005e354  movzx   edi, di
0x18005e357  or      edi, 80070000h
0x18005e35d  lea     rcx, [rbp+180h+ProcessInformation]; this
0x18005e361  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z
0x18005e366  jmp     loc_18005E29F
0x18005e36b  mov     [rbp+180h+var_1F7], 1
0x18005e36f  mov     rax, [rsp+280h+Environment]
0x18005e374  lea     r8, [rbp+180h+lpCommandLine]
0x18005e37b  cmp     [rbp+180h+var_D8], 7
0x18005e383  cmova   r8, [rbp+180h+lpCommandLine]; lpCommandLine
0x18005e38b  lea     rcx, [rbp+180h+ProcessInformation]
0x18005e38f  mov     [rsp+280h+lpProcessInformation], rcx; lpProcessInformation
0x18005e394  lea     rcx, [rbp+180h+StartupInfo]
0x18005e398  mov     [rsp+280h+lpStartupInfo], rcx; lpStartupInfo
0x18005e39d  mov     [rsp+280h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18005e3a2  mov     [rsp+280h+lpEnvironment], rax; lpEnvironment
0x18005e3a7  mov     [rsp+280h+dwCreationFlags], 400h; dwCreationFlags
0x18005e3af  mov     [rsp+280h+bInheritHandles], r15d; bInheritHandles
0x18005e3b4  mov     [rsp+280h+lpThreadAttributes], r15; lpThreadAttributes
0x18005e3b9  lea     r9, [rbp+180h+ProcessAttributes]; lpProcessAttributes
0x18005e3bd  mov     rdx, rdi; lpApplicationName
0x18005e3c0  mov     rcx, [rsp+280h+phToken]; hToken
0x18005e3c5  call    cs:__imp_CreateProcessAsUserW
0x18005e3cb  test    eax, eax
0x18005e3cd  jnz     short loc_18005E400
0x18005e3cf  call    cs:__imp_GetLastError
0x18005e3d5  mov     edi, eax
0x18005e3d7  mov     r8d, eax
0x18005e3da  lea     rdx, aProcessCreatio
0x18005e3e1  mov     ecx, ebx; unsigned __int8
0x18005e3e3  call    ?Log@@YAXEPEB_WZZ
0x18005e3e8  test    edi, edi
0x18005e3ea  jle     short loc_18005E3F5
0x18005e3ec  movzx   edi, di
0x18005e3ef  or      edi, 80070000h
0x18005e3f5  call    cs:__imp_RevertToSelf
0x18005e3fb  jmp     loc_18005E35D
0x18005e400  mov     r9d, [rbp+180h+ProcessInformation.dwProcessId]
0x18005e404  mov     r8, rdi
0x18005e407  lea     rdx, aProcessCreated
  ... truncated ...
```
