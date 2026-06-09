# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *)

- ea: `0x180054804`
- end: `0x180054b9a`
- name: `?CreateWorkerProcess@IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus_Exp@2345@@Z`
- size: `918`
- prototype: `int(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *__hidden this, const wchar_t *, wchar_t *, void **, unsigned int *, enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180054d30`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x1800185c0`
- `0x1800350b4`
- `0x18003c638`
- `0x1800486b8`
- `0x180048fbc`
- `0x180054804`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ac8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180054abe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180054abe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005493b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054b6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005493b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005488c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800548ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005490a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005488c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800548ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005490a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800548de`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800548de`

## string_xrefs

- `0x18005491a`: `WTSQueryUserToken failed for user %s (session %u): %#x`
- `0x180054b26`: `Process created: %s (pid %u)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::CreateWorkerProcess(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *this,
        const wchar_t *a2,
        wchar_t *a3,
        void **a4,
        unsigned int *a5,
        enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *a6)
{
  const wchar_t *StringRawBuffer; // rax
  PCWSTR v12; // rax
  signed int v13; // eax
  unsigned int v14; // edi
  ULONG v15; // ebx
  PCWSTR v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  WCHAR *v21; // r8
  __int64 LastError; // rbx
  struct _PROCESS_INFORMATION *v23; // rdx
  struct _PROCESS_INFORMATION *v24; // rdx
  ULONG SessionId; // [rsp+60h] [rbp-A0h] BYREF
  void *phToken; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  __int128 Src; // [rsp+100h] [rbp+0h] BYREF
  __int128 v30; // [rsp+110h] [rbp+10h]
  LPWSTR lpCommandLine[4]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v32[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v33[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v34[2]; // [rsp+180h] [rbp+80h] BYREF

  Log(4u, L"(v1) Creating process in session: %s %s", a2, a3);
  *(_DWORD *)a6 = 0;
  *a4 = 0;
  *a5 = 0;
  if ( !*((_QWORD *)this + 15) )
    return 2147947423LL;
  SessionId = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 21), 0);
  if ( FindSessionForUser(StringRawBuffer, &SessionId) )
  {
    phToken = 0;
    if ( WTSQueryUserToken(SessionId, &phToken) )
    {
      memset(v33, 0, sizeof(v33));
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( a3[v18] );
      std::wstring::_Construct<1,wchar_t const *>((char **)v33, a3, v18);
      memset(v32, 0, sizeof(v32));
      do
        ++v17;
      while ( a2[v17] );
      std::wstring::_Construct<1,wchar_t const *>((char **)v32, a2, v17);
      v19 = std::wstring::_Insert<wchar_t>(v32);
      Src = 0;
      v30 = 0;
      Src = *(_OWORD *)v19;
      v30 = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      *(_QWORD *)(v19 + 16) = 0;
      v20 = std::wstring::append(&Src, L"\" ");
      v34[0] = *(_OWORD *)v20;
      v34[1] = *(_OWORD *)(v20 + 16);
      *(_WORD *)v20 = 0;
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 7;
      std::operator+<wchar_t>(lpCommandLine, v34, v33);
      std::wstring::~wstring((char **)v34);
      std::wstring::~wstring((char **)&Src);
      std::wstring::~wstring((char **)v32);
      std::wstring::~wstring((char **)v33);
      *(_QWORD *)&StartupInfo.cb = 104;
      memset_0(&StartupInfo.lpReserved, 0, 0x60u);
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      v21 = (WCHAR *)lpCommandLine;
      if ( lpCommandLine[3] > (LPWSTR)7 )
        v21 = lpCommandLine[0];
      if ( CreateProcessAsUserW(phToken, a2, v21, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        Log(4u, L"Process created: %s (pid %u)", a2, ProcessInformation.dwProcessId);
        *a4 = ProcessInformation.hProcess;
        ProcessInformation.hProcess = 0;
        *a5 = ProcessInformation.dwProcessId;
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
        std::wstring::~wstring((char **)lpCommandLine);
        if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phToken);
        return 0;
      }
      else
      {
        LastError = GetLastError();
        Log(2u, L"Process creation failed: %#x", LastError);
        if ( (int)LastError > 0 )
          LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v23);
        std::wstring::~wstring((char **)lpCommandLine);
        if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phToken);
        return (unsigned int)LastError;
      }
    }
    else
    {
      v13 = GetLastError();
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      v15 = SessionId;
      v16 = WindowsGetStringRawBuffer(*((HSTRING *)this + 21), 0);
      Log(2u, L"WTSQueryUserToken failed for user %s (session %u): %#x", v16, v15, v14);
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      return v14;
    }
  }
  else
  {
    v12 = WindowsGetStringRawBuffer(*((HSTRING *)this + 21), 0);
    Log(2u, L"Did not find a session for user %s", v12);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180054804  push    rbp
0x180054806  push    rbx
0x180054807  push    rsi
0x180054808  push    rdi
0x180054809  push    r12
0x18005480b  push    r13
0x18005480d  push    r14
0x18005480f  push    r15
0x180054811  lea     rbp, [rsp-0B8h]
0x180054819  sub     rsp, 1B8h
0x180054820  mov     rax, cs:__security_cookie
0x180054827  xor     rax, rsp
0x18005482a  mov     [rbp+0F0h+var_50], rax
0x180054831  mov     r15, r9
0x180054834  mov     r14, r8
0x180054837  mov     rdi, rdx
0x18005483a  mov     rsi, rcx
0x18005483d  mov     r12, [rbp+0F0h+arg_20]
0x180054844  mov     rbx, [rbp+0F0h+arg_28]
0x18005484b  xor     r13d, r13d
0x18005484e  mov     r9, r8
0x180054851  mov     r8, rdx
0x180054854  lea     rdx, aV1CreatingProc; "(v1) Creating process in session: %s %s"
0x18005485b  lea     ecx, [r13+4]; unsigned __int8
0x18005485f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180054864  mov     [rbx], r13d
0x180054867  mov     [r15], r13
0x18005486a  mov     [r12], r13d
0x18005486e  cmp     [rsi+78h], r13
0x180054872  jnz     short loc_18005487E
0x180054874  mov     eax, 8007139Fh
0x180054879  jmp     loc_180054B77
0x18005487e  mov     [rsp+1F0h+SessionId], r13d
0x180054883  xor     edx, edx; length
0x180054885  mov     rcx, [rsi+0A8h]; string
0x18005488c  call    cs:__imp_WindowsGetStringRawBuffer
0x180054892  lea     rdx, [rsp+1F0h+SessionId]; unsigned int *
0x180054897  mov     rcx, rax; wchar_t *
0x18005489a  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z; FindSessionForUser(wchar_t const *,ulong *)
0x18005489f  test    al, al
0x1800548a1  jnz     short loc_1800548D0
0x1800548a3  xor     edx, edx; length
0x1800548a5  mov     rcx, [rsi+0A8h]; string
0x1800548ac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800548b2  mov     r8, rax
0x1800548b5  lea     rdx, aDidNotFindASes; "Did not find a session for user %s"
0x1800548bc  mov     ecx, 2; unsigned __int8
0x1800548c1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800548c6  mov     eax, 8000FFFFh
0x1800548cb  jmp     loc_180054B77
0x1800548d0  mov     [rsp+1F0h+phToken], r13
0x1800548d5  lea     rdx, [rsp+1F0h+phToken]; phToken
0x1800548da  mov     ecx, [rsp+1F0h+SessionId]; SessionId
0x1800548de  call    cs:__imp_WTSQueryUserToken
0x1800548e4  test    eax, eax
0x1800548e6  jnz     short loc_180054948
0x1800548e8  call    cs:__imp_GetLastError
0x1800548ee  mov     edi, eax
0x1800548f0  test    eax, eax
0x1800548f2  jle     short loc_1800548FD
0x1800548f4  movzx   edi, ax
0x1800548f7  or      edi, 80070000h
0x1800548fd  mov     ebx, [rsp+1F0h+SessionId]
0x180054901  xor     edx, edx; length
0x180054903  mov     rcx, [rsi+0A8h]; string
0x18005490a  call    cs:__imp_WindowsGetStringRawBuffer
0x180054910  mov     dword ptr [rsp+1F0h+lpThreadAttributes], edi
0x180054914  mov     r9d, ebx
0x180054917  mov     r8, rax
0x18005491a  lea     rdx, aWtsqueryuserto_0; "WTSQueryUserToken failed for user %s (s"...
0x180054921  mov     ecx, 2; unsigned __int8
0x180054926  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005492b  nop
0x18005492c  mov     rcx, [rsp+1F0h+phToken]; hObject
0x180054931  lea     rdx, [rcx-1]
0x180054935  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180054939  ja      short loc_180054941
0x18005493b  call    cs:__imp_CloseHandle
0x180054941  mov     eax, edi
0x180054943  jmp     loc_180054B77
0x180054948  xorps   xmm0, xmm0
0x18005494b  movups  [rbp+0F0h+var_90], xmm0
0x18005494f  xorps   xmm1, xmm1
0x180054952  movdqu  [rbp+0F0h+var_80], xmm1
0x180054957  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005495b  mov     r8, rbx
0x18005495e  inc     r8
0x180054961  cmp     [r14+r8*2], r13w
0x180054966  jnz     short loc_18005495E
0x180054968  mov     rdx, r14
0x18005496b  lea     rcx, [rbp+0F0h+var_90]
0x18005496f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180054974  nop
0x180054975  xorps   xmm0, xmm0
0x180054978  movups  [rbp+0F0h+var_B0], xmm0
0x18005497c  xorps   xmm1, xmm1
0x18005497f  movdqu  [rbp+0F0h+var_A0], xmm1
0x180054984  inc     rbx
0x180054987  cmp     [rdi+rbx*2], r13w
0x18005498c  jnz     short loc_180054984
0x18005498e  mov     r8, rbx
0x180054991  mov     rdx, rdi
0x180054994  lea     rcx, [rbp+0F0h+var_B0]
0x180054998  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005499d  nop
0x18005499e  mov     r9d, 1
0x1800549a4  lea     r8, asc_1800A1348; "\""
0x1800549ab  xor     edx, edx
0x1800549ad  lea     rcx, [rbp+0F0h+var_B0]; Src
0x1800549b1  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800549b6  xorps   xmm0, xmm0
0x1800549b9  movups  [rbp+0F0h+Src], xmm0
0x1800549bd  xorps   xmm1, xmm1
0x1800549c0  movdqu  [rbp+0F0h+var_E0], xmm1
0x1800549c5  movups  xmm0, xmmword ptr [rax]
0x1800549c8  movups  [rbp+0F0h+Src], xmm0
0x1800549cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800549d0  movups  [rbp+0F0h+var_E0], xmm1
0x1800549d4  mov     ebx, 7
0x1800549d9  mov     [rax+18h], rbx
0x1800549dd  mov     [rax], r13w
0x1800549e1  mov     [rax+10h], r13
0x1800549e5  lea     rdx, asc_1800A134C; "\" "
0x1800549ec  lea     rcx, [rbp+0F0h+Src]; Src
0x1800549f0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800549f5  movups  xmm0, xmmword ptr [rax]
0x1800549f8  movups  [rbp+0F0h+var_70], xmm0
0x1800549ff  movups  xmm1, xmmword ptr [rax+10h]
0x180054a03  movups  [rbp+0F0h+var_60], xmm1
0x180054a0a  mov     [rax], r13w
0x180054a0e  mov     [rax+10h], r13
0x180054a12  mov     [rax+18h], rbx
0x180054a16  lea     r8, [rbp+0F0h+var_90]
0x180054a1a  lea     rdx, [rbp+0F0h+var_70]
0x180054a21  lea     rcx, [rbp+0F0h+lpCommandLine]
0x180054a25  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x180054a2a  nop
0x180054a2b  lea     rcx, [rbp+0F0h+var_70]
0x180054a32  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054a37  nop
0x180054a38  lea     rcx, [rbp+0F0h+Src]
0x180054a3c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054a41  nop
0x180054a42  lea     rcx, [rbp+0F0h+var_B0]
0x180054a46  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054a4b  nop
0x180054a4c  lea     rcx, [rbp+0F0h+var_90]
0x180054a50  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054a55  mov     qword ptr [rbp+0F0h+StartupInfo.cb], 68h ; 'h'
0x180054a5d  xor     edx, edx; Val
0x180054a5f  lea     r8d, [rbx+59h]; Size
0x180054a63  lea     rcx, [rbp+0F0h+StartupInfo.lpReserved]; void *
0x180054a67  call    memset_0
0x180054a6c  xorps   xmm0, xmm0
0x180054a6f  xor     eax, eax
0x180054a71  movups  xmmword ptr [rsp+1F0h+ProcessInformation.hProcess], xmm0
0x180054a76  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x180054a7a  lea     r8, [rbp+0F0h+lpCommandLine]
0x180054a7e  cmp     [rbp+0F0h+var_B8], rbx
0x180054a82  cmova   r8, [rbp+0F0h+lpCommandLine]; lpCommandLine
0x180054a87  lea     rax, [rsp+1F0h+ProcessInformation]
0x180054a8c  mov     [rsp+1F0h+lpProcessInformation], rax; lpProcessInformation
0x180054a91  lea     rax, [rbp+0F0h+StartupInfo]
0x180054a95  mov     [rsp+1F0h+lpStartupInfo], rax; lpStartupInfo
0x180054a9a  mov     [rsp+1F0h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180054a9f  mov     [rsp+1F0h+lpEnvironment], r13; lpEnvironment
0x180054aa4  mov     [rsp+1F0h+dwCreationFlags], r13d; dwCreationFlags
0x180054aa9  mov     [rsp+1F0h+bInheritHandles], r13d; bInheritHandles
0x180054aae  mov     [rsp+1F0h+lpThreadAttributes], r13; lpThreadAttributes
0x180054ab3  xor     r9d, r9d; lpProcessAttributes
0x180054ab6  mov     rdx, rdi; lpApplicationName
0x180054ab9  mov     rcx, [rsp+1F0h+phToken]; hToken
0x180054abe  call    cs:__imp_CreateProcessAsUserW
0x180054ac4  test    eax, eax
0x180054ac6  jnz     short loc_180054B1F
0x180054ac8  call    cs:__imp_GetLastError
0x180054ace  mov     ebx, eax
0x180054ad0  mov     r8d, eax
0x180054ad3  lea     rdx, aProcessCreatio; "Process creation failed: %#x"
0x180054ada  mov     ecx, 2; unsigned __int8
0x180054adf  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180054ae4  test    ebx, ebx
0x180054ae6  jle     short loc_180054AF1
0x180054ae8  movzx   ebx, bx
0x180054aeb  or      ebx, 80070000h
0x180054af1  lea     rcx, [rsp+1F0h+ProcessInformation]; this
0x180054af6  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180054afb  nop
0x180054afc  lea     rcx, [rbp+0F0h+lpCommandLine]
0x180054b00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054b05  nop
0x180054b06  mov     rcx, [rsp+1F0h+phToken]; hObject
0x180054b0b  lea     rdx, [rcx-1]
0x180054b0f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180054b13  ja      short loc_180054B1B
0x180054b15  call    cs:__imp_CloseHandle
0x180054b1b  mov     eax, ebx
0x180054b1d  jmp     short loc_180054B77
0x180054b1f  mov     r9d, [rbp+0F0h+ProcessInformation.dwProcessId]
0x180054b23  mov     r8, rdi
0x180054b26  lea     rdx, aProcessCreated; "Process created: %s (pid %u)"
0x180054b2d  mov     ecx, 4; unsigned __int8
0x180054b32  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180054b37  mov     rax, [rsp+1F0h+ProcessInformation.hProcess]
0x180054b3c  mov     [r15], rax
0x180054b3f  mov     [rsp+1F0h+ProcessInformation.hProcess], r13
0x180054b44  mov     eax, [rbp+0F0h+ProcessInformation.dwProcessId]
0x180054b47  mov     [r12], eax
0x180054b4b  lea     rcx, [rsp+1F0h+ProcessInformation]; this
0x180054b50  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180054b55  nop
0x180054b56  lea     rcx, [rbp+0F0h+lpCommandLine]
0x180054b5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054b5f  nop
0x180054b60  mov     rcx, [rsp+1F0h+phToken]; hObject
0x180054b65  lea     rax, [rcx-1]
0x180054b69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180054b6d  ja      short loc_180054B75
0x180054b6f  call    cs:__imp_CloseHandle
0x180054b75  xor     eax, eax
0x180054b77  mov     rcx, [rbp+0F0h+var_50]
0x180054b7e  xor     rcx, rsp; StackCookie
0x180054b81  call    __security_check_cookie
0x180054b86  add     rsp, 1B8h
0x180054b8d  pop     r15
0x180054b8f  pop     r14
0x180054b91  pop     r13
0x180054b93  pop     r12
0x180054b95  pop     rdi
0x180054b96  pop     rsi
0x180054b97  pop     rbx
0x180054b98  pop     rbp
0x180054b99  retn
```
