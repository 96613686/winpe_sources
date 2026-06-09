# Windows::AI::IsolationEnvironment::IsolationEnvironment::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *)

- ea: `0x180049024`
- end: `0x180049607`
- name: `?CreateWorkerProcess@IsolationEnvironment@1AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus@123@@Z`
- size: `1507`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *this, const wchar_t *, wchar_t *, void **, unsigned int *, enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180049e70`

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
- `0x180049024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049504`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800494fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800494fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495b8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004931b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004931b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004952a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004954e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004952a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004954e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004940d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004940d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004945f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004945f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800493de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049581`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800493de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049581`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004938e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004938e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800490f9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800490f9`
- `USERENV!CreateEnvironmentBlock` at `0x1800492ad`
- `USERENV!CreateEnvironmentBlock` at `0x1800492ad`
- `USERENV!DestroyEnvironmentBlock` at `0x1800493f2`
- `USERENV!DestroyEnvironmentBlock` at `0x180049595`
- `USERENV!DestroyEnvironmentBlock` at `0x1800493f2`
- `USERENV!DestroyEnvironmentBlock` at `0x180049595`

## string_xrefs

- `0x1800495e3`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x1800495f5`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049117`: `WTSQueryUserToken failed for user %s (session %u): %#x`
- `0x1800493b9`: `SetEntriesInAcl failed for user %s: %#x`
- `0x1800492c5`: `CreateEnvironmentBlock failed for user %s: %#x`
- `0x180049477`: `ImpersonateLoggedOnUser failed for user %s: %#x`
- `0x18004953c`: `Process created: %s (pid %u)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::CreateWorkerProcess(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        const wchar_t *a2,
        wchar_t *a3,
        void **a4,
        unsigned int *a5,
        enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *a6)
{
  const wchar_t *v10; // rsi
  __int64 LastError; // rdi
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // rax
  WCHAR *v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // r8
  const char *v22; // r9
  struct _PROCESS_INFORMATION *v23; // rdx
  WCHAR *v24; // r8
  struct _PROCESS_INFORMATION *v25; // rdx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  void *phToken; // [rsp+60h] [rbp-A0h] BYREF
  ULONG SessionId; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Environment; // [rsp+70h] [rbp-90h] BYREF
  PACL NewAcl; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  char v32; // [rsp+89h] [rbp-77h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v34; // [rsp+A8h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v38; // [rsp+118h] [rbp+18h]
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp+20h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+190h] [rbp+90h] BYREF
  __int128 Src; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v42; // [rsp+1C0h] [rbp+C0h]
  _OWORD v43[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v44[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v45[2]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v34 = a5;
  v10 = (const wchar_t *)(*((_QWORD *)this + 6) + 144LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 6) + 168LL) > 7u )
    v10 = *(const wchar_t **)v10;
  Log(4u, L"Creating process in user %s session: %s %s", v10, a2, a3);
  *(_DWORD *)a6 = 1;
  *a4 = 0;
  *a5 = 0;
  SessionId = 0;
  if ( !FindSessionForUser(v10, &SessionId) )
  {
    Log(2u, L"Did not find a session for user %s", v10);
    *(_DWORD *)a6 = 5;
    return 2147549183LL;
  }
  phToken = 0;
  if ( !WTSQueryUserToken(SessionId, &phToken) )
  {
    LODWORD(LastError) = GetLastError();
    LODWORD(lpThreadAttributes) = LastError;
    Log(2u, L"WTSQueryUserToken failed for user %s (session %u): %#x", v10, SessionId, lpThreadAttributes);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  memset(v44, 0, sizeof(v44));
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  std::wstring::_Construct<1,wchar_t const *>(v44, a3);
  memset(v43, 0, sizeof(v43));
  do
    ++v13;
  while ( a2[v13] );
  std::wstring::_Construct<1,wchar_t const *>(v43, a2);
  v15 = std::wstring::_Insert<wchar_t>(v43);
  Src = 0;
  v42 = 0;
  Src = *(_OWORD *)v15;
  v42 = *(_OWORD *)(v15 + 16);
  *(_QWORD *)(v15 + 24) = 7;
  *(_WORD *)v15 = 0;
  *(_QWORD *)(v15 + 16) = 0;
  v16 = std::wstring::append(&Src, L"\" ");
  v45[0] = *(_OWORD *)v16;
  v45[1] = *(_OWORD *)(v16 + 16);
  *(_WORD *)v16 = 0;
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  std::operator+<wchar_t>(lpCommandLine, v45, v44);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v44);
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, phToken, 0) )
  {
    LastError = GetLastError();
    Log(2u, L"CreateEnvironmentBlock failed for user %s: %#x", v10, LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    std::wstring::~wstring(lpCommandLine);
LABEL_8:
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    return (unsigned int)LastError;
  }
  *(_QWORD *)&Src = &Environment;
  BYTE8(Src) = 1;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v38 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      v17);
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)(&pListOfExplicitEntries.Trustee.TrusteeType + 1) = 0;
  HIDWORD(pListOfExplicitEntries.Trustee.ptstrName) = 0;
  pListOfExplicitEntries.grfAccessPermissions = 1052672;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
  v18 = *((_QWORD *)this + 8);
  v19 = (WCHAR *)(*(_QWORD *)(v18 + 40) + 16LL);
  if ( *(_QWORD *)(*(_QWORD *)(v18 + 40) + 40LL) > 7u )
    v19 = *(WCHAR **)v19;
  pListOfExplicitEntries.Trustee.ptstrName = v19;
  NewAcl = 0;
  v31 = 0;
  if ( !SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
  {
    LODWORD(LastError) = GetLastError();
    v20 = *((_QWORD *)this + 8);
    v21 = (_QWORD *)(*(_QWORD *)(v20 + 40) + 48LL);
    if ( *(_QWORD *)(*(_QWORD *)(v20 + 40) + 72LL) > 7u )
      v21 = (_QWORD *)*v21;
    Log(2u, L"SetEntriesInAcl failed for user %s: %#x", v21, (unsigned int)LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      v22);
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  *(_QWORD *)&ProcessAttributes.bInheritHandle = 0;
  ProcessAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !ImpersonateLoggedOnUser(phToken) )
  {
    LastError = GetLastError();
    Log(2u, L"ImpersonateLoggedOnUser failed for user %s: %#x", v10, LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v23);
LABEL_27:
    if ( NewAcl )
    {
      LocalFree(NewAcl);
      NewAcl = 0;
      v31 = 0;
    }
    DestroyEnvironmentBlock(Environment);
    goto LABEL_18;
  }
  v32 = 1;
  v24 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v24 = lpCommandLine[0];
  if ( !CreateProcessAsUserW(
          phToken,
          a2,
          v24,
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
  *v34 = ProcessInformation.dwProcessId;
  *(_DWORD *)a6 = 0;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v25);
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
    v31 = 0;
  }
  DestroyEnvironmentBlock(Environment);
  std::wstring::~wstring(lpCommandLine);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  return 0;
}

```

## disassembly

```asm
0x180049024  push    rbp
0x180049026  push    rbx
0x180049027  push    rsi
0x180049028  push    rdi
0x180049029  push    r12
0x18004902b  push    r13
0x18004902d  push    r14
0x18004902f  push    r15
0x180049031  lea     rbp, [rsp-148h]
0x180049039  sub     rsp, 248h
0x180049040  mov     rax, cs:__security_cookie
0x180049047  xor     rax, rsp
0x18004904a  mov     [rbp+180h+var_50], rax
0x180049051  mov     r13, r9
0x180049054  mov     r14, r8
0x180049057  mov     rdi, rdx
0x18004905a  mov     r15, rcx
0x18004905d  mov     rbx, [rbp+180h+arg_20]
0x180049064  mov     [rbp+180h+var_1D8], rbx
0x180049068  mov     r12, [rbp+180h+arg_28]
0x18004906f  mov     rsi, [rcx+30h]
0x180049073  add     rsi, 90h
0x18004907a  cmp     qword ptr [rsi+18h], 7
0x18004907f  jbe     short loc_180049084
0x180049081  mov     rsi, [rsi]
0x180049084  mov     [rsp+280h+lpThreadAttributes], r14
0x180049089  mov     r9, rdi
0x18004908c  mov     r8, rsi
0x18004908f  lea     rdx, aCreatingProces
0x180049096  mov     ecx, 4; unsigned __int8
0x18004909b  call    ?Log@@YAXEPEB_WZZ
0x1800490a0  mov     dword ptr [r12], 1
0x1800490a8  xor     eax, eax
0x1800490aa  mov     [r13+0], rax
0x1800490ae  mov     [rbx], eax
0x1800490b0  xor     ebx, ebx
0x1800490b2  mov     [rsp+280h+SessionId], ebx
0x1800490b6  lea     rdx, [rsp+280h+SessionId]; unsigned int *
0x1800490bb  mov     rcx, rsi; wchar_t *
0x1800490be  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z
0x1800490c3  test    al, al
0x1800490c5  jnz     short loc_1800490EB
0x1800490c7  mov     r8, rsi
0x1800490ca  lea     rdx, aDidNotFindASes
0x1800490d1  lea     ecx, [rbx+2]; unsigned __int8
0x1800490d4  call    ?Log@@YAXEPEB_WZZ
0x1800490d9  mov     dword ptr [r12], 5
0x1800490e1  mov     eax, 8000FFFFh
0x1800490e6  jmp     loc_1800495C0
0x1800490eb  mov     [rsp+280h+phToken], rbx
0x1800490f0  lea     rdx, [rsp+280h+phToken]; phToken
0x1800490f5  mov     ecx, [rsp+280h+SessionId]; SessionId
0x1800490f9  call    cs:__imp_WTSQueryUserToken
0x1800490ff  test    eax, eax
0x180049101  jnz     short loc_180049151
0x180049103  call    cs:__imp_GetLastError
0x180049109  mov     edi, eax
0x18004910b  mov     dword ptr [rsp+280h+lpThreadAttributes], eax
0x18004910f  mov     r9d, [rsp+280h+SessionId]
0x180049114  mov     r8, rsi
0x180049117  lea     rdx, aWtsqueryuserto_0
0x18004911e  mov     ecx, 2; unsigned __int8
0x180049123  call    ?Log@@YAXEPEB_WZZ
0x180049128  test    edi, edi
0x18004912a  jle     short loc_180049135
0x18004912c  movzx   edi, di
0x18004912f  or      edi, 80070000h
0x180049135  mov     rcx, [rsp+280h+phToken]; hObject
0x18004913a  lea     rdx, [rcx-1]
0x18004913e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180049142  ja      short loc_18004914A
0x180049144  call    cs:__imp_CloseHandle
0x18004914a  mov     eax, edi
0x18004914c  jmp     loc_1800495C0
0x180049151  xorps   xmm0, xmm0
0x180049154  movups  [rbp+180h+var_90], xmm0
0x18004915b  xorps   xmm1, xmm1
0x18004915e  movdqu  [rbp+180h+var_80], xmm1
0x180049166  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004916a  mov     r8, rbx
0x18004916d  xor     eax, eax
0x18004916f  inc     r8
0x180049172  cmp     [r14+r8*2], ax
0x180049177  jnz     short loc_18004916F
0x180049179  mov     rdx, r14
0x18004917c  lea     rcx, [rbp+180h+var_90]
0x180049183  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z
0x180049188  nop
0x180049189  xorps   xmm0, xmm0
0x18004918c  movups  [rbp+180h+var_B0], xmm0
0x180049193  xorps   xmm1, xmm1
0x180049196  movdqu  [rbp+180h+var_A0], xmm1
0x18004919e  xor     r14d, r14d
0x1800491a1  inc     rbx
0x1800491a4  cmp     [rdi+rbx*2], r14w
0x1800491a9  jnz     short loc_1800491A1
0x1800491ab  mov     r8, rbx
0x1800491ae  mov     rdx, rdi
0x1800491b1  lea     rcx, [rbp+180h+var_B0]
0x1800491b8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z
0x1800491bd  nop
0x1800491be  mov     ebx, 1
0x1800491c3  mov     r9d, ebx
0x1800491c6  lea     r8, asc_1800A1348
0x1800491cd  xor     edx, edx
0x1800491cf  lea     rcx, [rbp+180h+var_B0]; Src
0x1800491d6  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z
0x1800491db  xorps   xmm0, xmm0
0x1800491de  movups  [rbp+180h+Src], xmm0
0x1800491e5  xorps   xmm1, xmm1
0x1800491e8  movdqu  [rbp+180h+var_C0], xmm1
0x1800491f0  movups  xmm0, xmmword ptr [rax]
0x1800491f3  movups  [rbp+180h+Src], xmm0
0x1800491fa  movups  xmm1, xmmword ptr [rax+10h]
0x1800491fe  movups  [rbp+180h+var_C0], xmm1
0x180049205  mov     qword ptr [rax+18h], 7
0x18004920d  mov     [rax], r14w
0x180049211  mov     [rax+10h], r14
0x180049215  lea     rdx, asc_1800A134C
0x18004921c  lea     rcx, [rbp+180h+Src]; Src
0x180049223  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z
0x180049228  movups  xmm0, xmmword ptr [rax]
0x18004922b  movups  [rbp+180h+var_70], xmm0
0x180049232  movups  xmm1, xmmword ptr [rax+10h]
0x180049236  movups  [rbp+180h+var_60], xmm1
0x18004923d  mov     [rax], r14w
0x180049241  mov     [rax+10h], r14
0x180049245  mov     qword ptr [rax+18h], 7
0x18004924d  lea     r8, [rbp+180h+var_90]
0x180049254  lea     rdx, [rbp+180h+var_70]
0x18004925b  lea     rcx, [rbp+180h+lpCommandLine]
0x180049262  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z
0x180049267  nop
0x180049268  lea     rcx, [rbp+180h+var_70]
0x18004926f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x180049274  nop
0x180049275  lea     rcx, [rbp+180h+Src]
0x18004927c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x180049281  nop
0x180049282  lea     rcx, [rbp+180h+var_B0]
0x180049289  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18004928e  nop
0x18004928f  lea     rcx, [rbp+180h+var_90]
0x180049296  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x18004929b  mov     [rsp+280h+Environment], r14
0x1800492a0  xor     r8d, r8d; bInherit
0x1800492a3  mov     rdx, [rsp+280h+phToken]; hToken
0x1800492a8  lea     rcx, [rsp+280h+Environment]; lpEnvironment
0x1800492ad  call    cs:__imp_CreateEnvironmentBlock
0x1800492b3  test    eax, eax
0x1800492b5  jnz     short loc_1800492F2
0x1800492b7  call    cs:__imp_GetLastError
0x1800492bd  mov     edi, eax
0x1800492bf  mov     r9d, eax
0x1800492c2  mov     r8, rsi
0x1800492c5  lea     rdx, aCreateenvironm_0
0x1800492cc  lea     ecx, [rbx+1]; unsigned __int8
0x1800492cf  call    ?Log@@YAXEPEB_WZZ
0x1800492d4  test    edi, edi
0x1800492d6  jle     short loc_1800492E1
0x1800492d8  movzx   edi, di
0x1800492db  or      edi, 80070000h
0x1800492e1  lea     rcx, [rbp+180h+lpCommandLine]
0x1800492e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ
0x1800492ed  jmp     loc_180049135
0x1800492f2  lea     rax, [rsp+280h+Environment]
0x1800492f7  mov     qword ptr [rbp+180h+Src], rax
0x1800492fe  mov     byte ptr [rbp+180h+Src+8], bl
0x180049304  xorps   xmm0, xmm0
0x180049307  xor     eax, eax
0x180049309  movups  [rbp+180h+pSecurityDescriptor], xmm0
0x18004930d  movups  [rbp+180h+var_178], xmm0
0x180049311  mov     [rbp+180h+var_168], rax
0x180049315  mov     edx, ebx; dwRevision
0x180049317  lea     rcx, [rbp+180h+pSecurityDescriptor]; pSecurityDescriptor
0x18004931b  call    cs:__imp_InitializeSecurityDescriptor
0x180049321  mov     rcx, [rbp+188h]; this
0x180049328  test    eax, eax
0x18004932a  jz      loc_1800495F5
0x180049330  xorps   xmm0, xmm0
0x180049333  movdqu  xmmword ptr [rbp+180h+pListOfExplicitEntries+0Ch], xmm0
0x180049338  mov     qword ptr [rbp+180h+pListOfExplicitEntries.Trustee+14h], r14
0x18004933c  mov     dword ptr [rbp+180h+pListOfExplicitEntries.Trustee.ptstrName+4], r14d
0x180049340  mov     [rbp+180h+pListOfExplicitEntries.grfAccessPermissions], 101000h
0x180049347  mov     ebx, 2
0x18004934c  mov     qword ptr [rbp+180h+pListOfExplicitEntries.grfAccessMode], rbx
0x180049350  mov     [rbp+180h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180049354  mov     [rbp+180h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18004935b  mov     rax, [r15+40h]
0x18004935f  mov     rcx, [rax+28h]
0x180049363  add     rcx, 10h
0x180049367  cmp     qword ptr [rcx+18h], 7
0x18004936c  jbe     short loc_180049371
0x18004936e  mov     rcx, [rcx]
0x180049371  mov     [rbp+180h+pListOfExplicitEntries.Trustee.ptstrName], rcx
0x180049375  mov     [rsp+280h+NewAcl], r14
0x18004937a  mov     [rbp+180h+var_200], r14
0x18004937e  lea     r9, [rsp+280h+NewAcl]; NewAcl
0x180049383  xor     r8d, r8d; OldAcl
0x180049386  lea     rdx, [rbp+180h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004938a  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x18004938e  call    cs:__imp_SetEntriesInAclW
0x180049394  test    eax, eax
0x180049396  jnz     short loc_1800493FD
0x180049398  call    cs:__imp_GetLastError
0x18004939e  mov     edi, eax
0x1800493a0  mov     rax, [r15+40h]
0x1800493a4  mov     r8, [rax+28h]
0x1800493a8  add     r8, 30h ; '0'
0x1800493ac  cmp     qword ptr [r8+18h], 7
0x1800493b1  jbe     short loc_1800493B6
0x1800493b3  mov     r8, [r8]
0x1800493b6  mov     r9d, edi
0x1800493b9  lea     rdx, aSetentriesinac
0x1800493c0  mov     ecx, ebx; unsigned __int8
0x1800493c2  call    ?Log@@YAXEPEB_WZZ
0x1800493c7  test    edi, edi
0x1800493c9  jle     short loc_1800493D4
0x1800493cb  movzx   edi, di
0x1800493ce  or      edi, 80070000h
0x1800493d4  mov     rcx, [rsp+280h+NewAcl]; hMem
0x1800493d9  test    rcx, rcx
0x1800493dc  jz      short loc_1800493ED
0x1800493de  call    cs:__imp_LocalFree
0x1800493e4  mov     [rsp+280h+NewAcl], r14
0x1800493e9  mov     [rbp+180h+var_200], r14
0x1800493ed  mov     rcx, [rsp+280h+Environment]; lpEnvironment
0x1800493f2  call    cs:__imp_DestroyEnvironmentBlock
0x1800493f8  jmp     loc_1800492E1
0x1800493fd  xor     r9d, r9d; bDaclDefaulted
0x180049400  mov     r8, [rsp+280h+NewAcl]; pDacl
0x180049405  lea     edx, [r9+1]; bDaclPresent
0x180049409  lea     rcx, [rbp+180h+pSecurityDescriptor]; pSecurityDescriptor
0x18004940d  call    cs:__imp_SetSecurityDescriptorDacl
0x180049413  mov     rcx, [rbp+188h]; this
0x18004941a  test    eax, eax
0x18004941c  jz      loc_1800495E3
0x180049422  mov     qword ptr [rbp+180h+ProcessAttributes.nLength], 18h
0x18004942a  mov     qword ptr [rbp+180h+ProcessAttributes.bInheritHandle], r14
0x18004942e  lea     rax, [rbp+180h+pSecurityDescriptor]
0x180049432  mov     [rbp+180h+ProcessAttributes.lpSecurityDescriptor], rax
0x180049436  mov     qword ptr [rbp+180h+StartupInfo.cb], 68h ; 'h'
0x18004943e  xor     edx, edx; Val
0x180049440  lea     r8d, [rdx+60h]; Size
0x180049444  lea     rcx, [rbp+180h+StartupInfo.lpReserved]; void *
0x180049448  call    memset_0
0x18004944d  xorps   xmm0, xmm0
0x180049450  xor     eax, eax
0x180049452  movups  xmmword ptr [rbp+180h+ProcessInformation.hProcess], xmm0
0x180049456  mov     qword ptr [rbp+180h+ProcessInformation.dwProcessId], rax
0x18004945a  mov     rcx, [rsp+280h+phToken]; hToken
0x18004945f  call    cs:__imp_ImpersonateLoggedOnUser
0x180049465  test    eax, eax
0x180049467  jnz     short loc_1800494A0
0x180049469  call    cs:__imp_GetLastError
0x18004946f  mov     edi, eax
0x180049471  mov     r9d, eax
0x180049474  mov     r8, rsi
0x180049477  lea     rdx, aImpersonatelog
0x18004947e  mov     ecx, ebx; unsigned __int8
0x180049480  call    ?Log@@YAXEPEB_WZZ
0x180049485  test    edi, edi
0x180049487  jle     short loc_180049492
0x180049489  movzx   edi, di
0x18004948c  or      edi, 80070000h
0x180049492  lea     rcx, [rbp+180h+ProcessInformation]; this
0x180049496  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z
0x18004949b  jmp     loc_1800493D4
0x1800494a0  mov     [rbp+180h+var_1F7], 1
0x1800494a4  mov     rax, [rsp+280h+Environment]
0x1800494a9  lea     r8, [rbp+180h+lpCommandLine]
0x1800494b0  cmp     [rbp+180h+var_D8], 7
0x1800494b8  cmova   r8, [rbp+180h+lpCommandLine]; lpCommandLine
0x1800494c0  lea     rcx, [rbp+180h+ProcessInformation]
0x1800494c4  mov     [rsp+280h+lpProcessInformation], rcx; lpProcessInformation
0x1800494c9  lea     rcx, [rbp+180h+StartupInfo]
0x1800494cd  mov     [rsp+280h+lpStartupInfo], rcx; lpStartupInfo
0x1800494d2  mov     [rsp+280h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800494d7  mov     [rsp+280h+lpEnvironment], rax; lpEnvironment
0x1800494dc  mov     [rsp+280h+dwCreationFlags], 400h; dwCreationFlags
0x1800494e4  mov     [rsp+280h+bInheritHandles], r14d; bInheritHandles
0x1800494e9  mov     [rsp+280h+lpThreadAttributes], r14; lpThreadAttributes
0x1800494ee  lea     r9, [rbp+180h+ProcessAttributes]; lpProcessAttributes
0x1800494f2  mov     rdx, rdi; lpApplicationName
0x1800494f5  mov     rcx, [rsp+280h+phToken]; hToken
0x1800494fa  call    cs:__imp_CreateProcessAsUserW
0x180049500  test    eax, eax
0x180049502  jnz     short loc_180049535
0x180049504  call    cs:__imp_GetLastError
0x18004950a  mov     edi, eax
0x18004950c  mov     r8d, eax
0x18004950f  lea     rdx, aProcessCreatio
0x180049516  mov     ecx, ebx; unsigned __int8
0x180049518  call    ?Log@@YAXEPEB_WZZ
0x18004951d  test    edi, edi
0x18004951f  jle     short loc_18004952A
0x180049521  movzx   edi, di
0x180049524  or      edi, 80070000h
0x18004952a  call    cs:__imp_RevertToSelf
0x180049530  jmp     loc_180049492
  ... truncated ...
```
