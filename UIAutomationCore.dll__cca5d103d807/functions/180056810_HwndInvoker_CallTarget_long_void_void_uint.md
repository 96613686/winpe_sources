# HwndInvoker::CallTarget(long (*)(void *),void *,uint)

- ea: `0x180056810`
- end: `0x180056ae8`
- name: `?CallTarget@HwndInvoker@@UEAAJP6AJPEAX@Z0I@Z`
- size: `728`
- prototype: `__int64 __fastcall(HwndInvoker *__hidden this, int (*)(void *), void *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180032724`
- `0x180056810`
- `0x180056bf0`
- `0x1801b2924`
- `0x1801b2ef4`
- `0x1801e8344`
- `0x1801e8380`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056a69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056a69`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800569b2`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800569b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056969`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800568b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800568b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056883`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056883`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180056a56`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180056a56`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800568af`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180056a27`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800568af`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180056a27`

## string_xrefs

- `0x180056898`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x1800568dc`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x1800569db`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x180056ab6`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x180056acd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180056a4f`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HwndInvoker::CallTarget(
        HwndInvoker *this,
        __int64 (__fastcall *a2)(void *),
        void *a3,
        unsigned int a4)
{
  HWND v8; // rbx
  int v9; // ebx
  DWORD WindowThreadProcessId; // ebx
  __int64 v11; // rcx
  int v12; // eax
  const char *v13; // r9
  unsigned __int32 v14; // edi
  char *v15; // rax
  RTL_SRWLOCK *v16; // rsi
  volatile void *v17; // rbx
  __int64 v18; // r9
  unsigned int *v19; // rdi
  const char *v20; // r9
  const char *v21; // r9
  __int64 result; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v25; // [rsp+20h] [rbp-38h]
  int v26; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int *CompareAddress; // [rsp+60h] [rbp+8h] BYREF

  try
  {
    v8 = (HWND)*((_QWORD *)this + 2);
    LODWORD(CompareAddress) = 0;
    if ( dword_1803A34B0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 88LL) )
    {
      Init_thread_header(&dword_1803A34B0);
      if ( dword_1803A34B0 == -1 )
      {
        LibraryW = LoadLibraryW(L"user32.dll");
        if ( LibraryW )
          ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xA98);
        else
          ProcAddress = 0;
        qword_1803A34B8 = (__int64 (__fastcall *)(_QWORD))ProcAddress;
        Init_thread_footer(&dword_1803A34B0);
      }
    }
    if ( qword_1803A34B8 )
    {
      v9 = qword_1803A34B8(v8);
      LODWORD(CompareAddress) = v9;
    }
    else
    {
      GetWindowThreadProcessId(v8, (LPDWORD)&CompareAddress);
      v9 = (int)CompareAddress;
    }
    if ( GetCurrentProcessId() != v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
        (const char *)0x80040201LL,
        v25);
    WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 2), 0);
    if ( WindowThreadProcessId == GetCurrentThreadId() )
    {
      v12 = a2(a3);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
          (const char *)(unsigned int)v12,
          v25);
    }
    else
    {
      v14 = _InterlockedIncrement(&g_nextContextChangeInstanceId);
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v11, ProcessIncomingRequest_ContextChange_Start, v14);
      v15 = (char *)operator new(0x30u);
      CompareAddress = (unsigned int *)v15;
      *((_DWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 3) = 0;
      *(_WORD *)(v15 + 41) = 0;
      v15[43] = 0;
      v16 = (RTL_SRWLOCK *)(v15 + 32);
      *((_QWORD *)v15 + 4) = 0;
      v15[40] = 0;
      v17 = v15 + 44;
      *((_DWORD *)v15 + 11) = 0;
      v26 = (int)v15;
      *(_DWORD *)v15 = v14;
      *((_QWORD *)v15 + 1) = a2;
      *((_QWORD *)v15 + 2) = a3;
      v18 = 500;
      if ( a4 )
        v18 = a4;
      PerformOperationOnHwndThread(*((_QWORD *)this + 2), 3, v15, v18);
      AcquireSRWLockExclusive(v16);
      v19 = CompareAddress;
      if ( !*((_BYTE *)CompareAddress + 40) )
      {
        *((_QWORD *)CompareAddress + 2) = 0;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x434,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
          (const char *)0x80131505LL,
          0);
      }
      if ( v16 )
        ReleaseSRWLockExclusive(v16);
      while ( !_InterlockedExchange((volatile __int32 *)v17, 0) )
      {
        LODWORD(CompareAddress) = 0;
        if ( !WaitOnAddress(v17, &CompareAddress, 4u, 0xFFFFFFFF) )
        {
          if ( GetLastError() != 1460 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xDBF,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v20);
          break;
        }
      }
      v21 = (const char *)v19[6];
      if ( (int)v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x43F,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
          v21,
          v26);
      operator delete(v19);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x444,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180056810  mov     [rsp+arg_8], rbx
0x180056815  mov     [rsp+arg_10], rsi
0x18005681a  push    rdi
0x18005681b  push    r12
0x18005681d  push    r13
0x18005681f  push    r14
0x180056821  push    r15
0x180056823  sub     rsp, 30h
0x180056827  mov     r13d, r9d
0x18005682a  mov     r15, r8
0x18005682d  mov     r12, rdx
0x180056830  mov     r14, rcx
0x180056833  xor     esi, esi
0x180056835  mov     rbx, [rcx+10h]
0x180056839  mov     dword ptr [rsp+58h+CompareAddress], esi
0x18005683d  mov     r8d, cs:_tls_index
0x180056844  mov     rax, gs:58h
0x18005684d  mov     ecx, 58h ; 'X'
0x180056852  mov     rax, [rax+r8*8]
0x180056856  mov     eax, [rcx+rax]
0x180056859  cmp     cs:dword_1803A34B0, eax
0x18005685f  jg      loc_180056A36
0x180056865  mov     rax, cs:qword_1803A34B8
0x18005686c  mov     rcx, rbx; hWnd
0x18005686f  test    rax, rax
0x180056872  jz      loc_180056A22
0x180056878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005687d  mov     ebx, eax
0x18005687f  mov     dword ptr [rsp+58h+CompareAddress], eax
0x180056883  call    cs:__imp_GetCurrentProcessId
0x180056889  cmp     eax, ebx
0x18005688b  jz      short loc_1800568A9
0x18005688d  mov     rcx, [rsp+58h]; this
0x180056892  mov     r9d, 80040201h; char *
0x180056898  lea     r8, aOnecoreWindows_124; "onecore\\windows\\accessibletech\\uiaut"...
0x18005689f  mov     edx, 3F6h; void *
0x1800568a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800568a9  xor     edx, edx; lpdwProcessId
0x1800568ab  mov     rcx, [r14+10h]; hWnd
0x1800568af  call    cs:__imp_GetWindowThreadProcessId
0x1800568b5  mov     ebx, eax
0x1800568b7  call    cs:__imp_GetCurrentThreadId
0x1800568bd  cmp     ebx, eax
0x1800568bf  jnz     short loc_1800568ED
0x1800568c1  mov     rcx, r15
0x1800568c4  mov     rax, r12
0x1800568c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568cc  mov     rcx, [rsp+58h]; this
0x1800568d1  test    eax, eax
0x1800568d3  jns     loc_1800569FA
0x1800568d9  mov     r9d, eax; char *
0x1800568dc  lea     r8, aOnecoreWindows_124; "onecore\\windows\\accessibletech\\uiaut"...
0x1800568e3  mov     edx, 3FEh; void *
0x1800568e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800568ed  mov     edi, 1
0x1800568f2  lock xadd cs:?g_nextContextChangeInstanceId@@3JA, edi; long g_nextContextChangeInstanceId
0x1800568fa  inc     edi
0x1800568fc  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180056903  jnz     loc_180056A71
0x180056909  mov     ecx, 30h ; '0'; Size
0x18005690e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056913  mov     [rsp+58h+CompareAddress], rax
0x180056918  mov     [rax+4], esi
0x18005691b  mov     [rax+18h], rsi
0x18005691f  mov     [rax+29h], si
0x180056923  mov     byte ptr [rax+2Bh], 0
0x180056927  lea     rsi, [rax+20h]
0x18005692b  xor     ecx, ecx
0x18005692d  mov     [rsi], rcx
0x180056930  mov     [rax+28h], cl
0x180056933  lea     rbx, [rax+2Ch]
0x180056937  mov     [rbx], ecx
0x180056939  mov     qword ptr [rsp+58h+var_38], rax; int
0x18005693e  mov     [rax], edi
0x180056940  mov     [rax+8], r12
0x180056944  mov     [rax+10h], r15
0x180056948  mov     r9d, 1F4h
0x18005694e  test    r13d, r13d
0x180056951  cmovnz  r9d, r13d
0x180056955  mov     r8, rax
0x180056958  mov     edx, 3
0x18005695d  mov     rcx, [r14+10h]
0x180056961  call    ?PerformOperationOnHwndThread@@YAJPEAUHWND__@@W4HookMessageOperation@@_JK@Z; PerformOperationOnHwndThread(HWND__ *,HookMessageOperation,__int64,ulong)
0x180056966  mov     rcx, rsi; SRWLock
0x180056969  call    cs:__imp_AcquireSRWLockExclusive
0x18005696f  mov     [rsp+58h+var_30], rsi
0x180056974  mov     rdi, [rsp+58h+CompareAddress]
0x180056979  cmp     byte ptr [rdi+28h], 0
0x18005697d  jz      loc_180056AA0
0x180056983  test    rsi, rsi
0x180056986  jnz     loc_180056A14
0x18005698c  nop     dword ptr [rax+00h]
0x180056990  xor     ecx, ecx
0x180056992  mov     eax, ecx
0x180056994  xchg    eax, [rbx]
0x180056996  test    eax, eax
0x180056998  jnz     short loc_1800569CD
0x18005699a  mov     dword ptr [rsp+58h+CompareAddress], ecx
0x18005699e  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800569a4  mov     r8d, 4; AddressSize
0x1800569aa  lea     rdx, [rsp+58h+CompareAddress]; CompareAddress
0x1800569af  mov     rcx, rbx; Address
0x1800569b2  call    cs:__imp_WaitOnAddress
0x1800569b8  test    eax, eax
0x1800569ba  jnz     short loc_180056990
0x1800569bc  call    cs:__imp_GetLastError
0x1800569c2  cmp     eax, 5B4h
0x1800569c7  jnz     loc_180056AC8
0x1800569cd  mov     r9d, [rdi+18h]; char *
0x1800569d1  mov     rcx, [rsp+58h]; this
0x1800569d6  test    r9d, r9d
0x1800569d9  jns     short loc_1800569ED
0x1800569db  lea     r8, aOnecoreWindows_124; "onecore\\windows\\accessibletech\\uiaut"...
0x1800569e2  mov     edx, 43Fh; void *
0x1800569e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800569ed  mov     edx, 30h ; '0'
0x1800569f2  mov     rcx, rdi; Block
0x1800569f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800569fa  xor     eax, eax
0x1800569fc  mov     rbx, [rsp+58h+arg_8]
0x180056a01  mov     rsi, [rsp+58h+arg_10]
0x180056a06  add     rsp, 30h
0x180056a0a  pop     r15
0x180056a0c  pop     r14
0x180056a0e  pop     r13
0x180056a10  pop     r12
0x180056a12  pop     rdi
0x180056a13  retn
0x180056a14  mov     rcx, rsi; SRWLock
0x180056a17  call    cs:__imp_ReleaseSRWLockExclusive
0x180056a1d  jmp     loc_180056990
0x180056a22  lea     rdx, [rsp+58h+CompareAddress]; lpdwProcessId
0x180056a27  call    cs:__imp_GetWindowThreadProcessId
0x180056a2d  mov     ebx, dword ptr [rsp+58h+CompareAddress]
0x180056a31  jmp     loc_180056883
0x180056a36  lea     rcx, dword_1803A34B0
0x180056a3d  call    _Init_thread_header
0x180056a42  cmp     cs:dword_1803A34B0, 0FFFFFFFFh
0x180056a49  jnz     loc_180056865
0x180056a4f  lea     rcx, LibFileName; "user32.dll"
0x180056a56  call    cs:__imp_LoadLibraryW
0x180056a5c  test    rax, rax
0x180056a5f  jz      short loc_180056A85
0x180056a61  mov     edx, 0A98h; lpProcName
0x180056a66  mov     rcx, rax; hModule
0x180056a69  call    cs:__imp_GetProcAddress
0x180056a6f  jmp     short loc_180056A88
0x180056a71  mov     r8d, edi
0x180056a74  lea     rdx, ProcessIncomingRequest_ContextChange_Start
0x180056a7b  call    McTemplateU0q_EventWriteTransfer
0x180056a80  jmp     loc_180056909
0x180056a85  mov     rax, rsi
0x180056a88  mov     cs:qword_1803A34B8, rax
0x180056a8f  lea     rcx, dword_1803A34B0
0x180056a96  call    _Init_thread_footer
0x180056a9b  jmp     loc_180056865
0x180056aa0  xor     eax, eax
0x180056aa2  mov     [rdi+10h], rax
0x180056aa6  mov     qword ptr [rsp+58h+var_38], rax; int
0x180056aab  mov     rcx, [rsp+58h]; this
0x180056ab0  mov     r9d, 80131505h; char *
0x180056ab6  lea     r8, aOnecoreWindows_124; "onecore\\windows\\accessibletech\\uiaut"...
0x180056abd  mov     edx, 434h; void *
0x180056ac2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056ac8  mov     rcx, [rsp+58h]; this
0x180056acd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180056ad4  mov     edx, 0DBFh; void *
0x180056ad9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180056adf  mov     eax, dword ptr [rsp+58h+CompareAddress]
0x180056ae3  jmp     loc_1800569FC
```
