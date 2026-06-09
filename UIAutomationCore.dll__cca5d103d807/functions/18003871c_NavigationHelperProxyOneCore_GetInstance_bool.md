# NavigationHelperProxyOneCore::GetInstance(bool)

- ea: `0x18003871c`
- end: `0x180038a81`
- name: `?GetInstance@NavigationHelperProxyOneCore@@CA?AV?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@_N@Z`
- size: `869`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800386b8`
- `0x18003b180`

## callees

- `0x18000b214`
- `0x1800226b0`
- `0x18002f580`
- `0x180032724`
- `0x18003871c`
- `0x180038a88`
- `0x180038c30`
- `0x180038cd8`
- `0x18003b150`
- `0x18005b0cc`
- `0x180080cc0`
- `0x180105f30`
- `0x180134444`
- `0x1801345a0`
- `0x1801345f0`
- `0x180134664`
- `0x1801390c4`
- `0x180178398`
- `0x1801e8320`
- `0x1801e8380`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038861`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800387df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800387df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800387ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800387ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800388b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800388b5`

## string_xrefs

- `0x18003877f`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x1800388d8`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x1800389a1`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x180038a54`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
NavigationHelperProxyOneCore **__fastcall NavigationHelperProxyOneCore::GetInstance(
        NavigationHelperProxyOneCore **a1,
        char a2)
{
  signed int v4; // ebx
  int v5; // ebx
  _QWORD **v6; // rcx
  _QWORD *v7; // rax
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  NavigationHelperProxyOneCore *v10; // rbx
  NavigationHelperProxyOneCore *v11; // rcx
  NavigationHelperProxyOneCore *v12; // rbx
  unsigned int v14; // ebx
  DWORD CurrentProcessId; // eax
  int ProcessIntegrityLevel; // eax
  wil *v17; // rcx
  bool *v18; // r8
  struct wil::WNF_CHANGE_STAMP_STRUCT *v19; // r9
  int is_published_nothrow; // eax
  NavigationHelperProxyOneCore *v21; // rax
  NavigationHelperProxyOneCore *v22; // rbx
  int v23; // eax
  _WNF_STATE_NAME v24; // [rsp+20h] [rbp-99h] BYREF
  NavigationHelperProxyOneCore *v25; // [rsp+28h] [rbp-91h] BYREF
  int v26; // [rsp+30h] [rbp-89h]
  NavigationHelperProxyOneCore **v27; // [rsp+38h] [rbp-81h]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+40h] [rbp-79h]
  NavigationHelperProxyOneCore *v29; // [rsp+48h] [rbp-71h]
  _BYTE v30[16]; // [rsp+50h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-59h]
  char v32; // [rsp+68h] [rbp-51h]
  _QWORD v33[3]; // [rsp+70h] [rbp-49h] BYREF
  int v34; // [rsp+88h] [rbp-31h]
  _BYTE v35[80]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v27 = a1;
  v26 = 0;
  UiaInitializeCoreUiTraceLoggingProvider::WatchCurrentThread(v30);
  if ( byte_1803A1834 )
  {
    v4 = (int)dword_1803A1830;
    goto LABEL_3;
  }
  v14 = 0;
  LODWORD(v25) = 0;
  if ( BasicUiaUtils::IsDesktop() )
  {
    CurrentProcessId = GetCurrentProcessId();
    ProcessIntegrityLevel = UiaUtils::GetProcessIntegrityLevel(CurrentProcessId, (unsigned int *)&v25);
    v4 = ProcessIntegrityLevel;
    if ( ProcessIntegrityLevel < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
        (const char *)(unsigned int)ProcessIntegrityLevel,
        v24.Data[0]);
      goto LABEL_3;
    }
    v14 = (unsigned int)v25;
  }
  if ( BasicUiaUtils::IsWinPE() || BasicUiaUtils::IsHoloLens() )
    goto LABEL_37;
  LOBYTE(v24.Data[0]) = 0;
  is_published_nothrow = wil::wnf_is_published_nothrow(v17, &v24, v18, v19);
  if ( is_published_nothrow < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)is_published_nothrow,
      v24.Data[0]);
  if ( LOBYTE(v24.Data[0]) )
  {
LABEL_37:
    if ( BasicUiaUtils::IsDesktop() && v14 <= 0x1000 )
      v4 = -2147024891;
    else
      v4 = BasicUiaUtils::IsWinPE() ? 0x80070032 : 0;
    LODWORD(dword_1803A1830) = v4;
    byte_1803A1834 = 1;
    word_1803A1835 = *(_WORD *)((char *)&v25 + 5);
    byte_1803A1837 = HIBYTE(v25);
  }
  else
  {
    v4 = -2147467259;
  }
LABEL_3:
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
      (const char *)(unsigned int)v4,
      v24.Data[0]);
  v5 = v34;
  if ( v34 )
  {
    if ( v5 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    v34 = 0;
    v6 = (_QWORD **)v33[0];
    while ( 1 )
    {
      v7 = *v6;
      if ( !*v6 )
        break;
      if ( v7 == v33 )
      {
        *v6 = (_QWORD *)v33[2];
        break;
      }
      v6 = (_QWORD **)(v7 + 2);
      v33[0] = v7 + 2;
    }
    v33[0] = 0;
  }
  if ( v32 )
  {
    v8 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  *a1 = 0;
  v26 = 1;
  v28 = &NavigationHelperProxyOneCore::s_instanceLock;
  EnterCriticalSection(&NavigationHelperProxyOneCore::s_instanceLock);
  v10 = NavigationHelperProxyOneCore::s_instance;
  if ( NavigationHelperProxyOneCore::s_instance )
  {
    if ( *a1 != NavigationHelperProxyOneCore::s_instance )
    {
      if ( NavigationHelperProxyOneCore::s_instance )
        (*(void (__fastcall **)(char *))(*((_QWORD *)NavigationHelperProxyOneCore::s_instance + 2) + 8LL))((char *)NavigationHelperProxyOneCore::s_instance + 16);
      v11 = *a1;
      *a1 = v10;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v11 + 2) + 16LL))((__int64)v11 + 16);
    }
  }
  else if ( a2 )
  {
    v25 = 0;
    DebugStartIgnoringLeaks(v35);
    v29 = (NavigationHelperProxyOneCore *)operator new(0x2E8u);
    v21 = NavigationHelperProxyOneCore::NavigationHelperProxyOneCore(v29);
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::Attach(&v25, v21);
    wil::details::lambda_call<std::function<void (void)>>::~lambda_call<std::function<void (void)>>(v35);
    v22 = v25;
    v23 = NavigationHelperProxyOneCore::Initialize(v25);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
        (const char *)(unsigned int)v23,
        v24.Data[0]);
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalAddRef(&v25);
    NavigationHelperProxyOneCore::s_instance = v22;
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(a1);
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalAddRef(&v25);
    *a1 = v22;
    Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(&v25);
  }
  LeaveCriticalSection(&NavigationHelperProxyOneCore::s_instanceLock);
  v12 = *a1;
  if ( *a1 )
  {
    NavigationHelperProxyOneCore::EnsureCrossMachineEventSinksRegisteredIfNeeded(*a1);
    NavigationHelperProxyOneCore::EnsureEndpointStateNotifierSinkRegisteredIfNeeded(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18003871c  mov     [rsp-8+arg_8], rbx
0x180038721  mov     [rsp-8+arg_10], rsi
0x180038726  push    rbp
0x180038727  push    rdi
0x180038728  push    r15
0x18003872a  lea     rbp, [rsp-47h]
0x18003872f  sub     rsp, 100h
0x180038736  mov     rax, cs:__security_cookie
0x18003873d  xor     rax, rsp
0x180038740  mov     [rbp+57h+var_20], rax
0x180038744  mov     sil, dl
0x180038747  mov     rdi, rcx
0x18003874a  mov     [rsp+110h+var_D8], rcx
0x18003874f  mov     [rsp+110h+var_E0], 0
0x180038757  lea     rcx, [rbp+57h+var_C0]
0x18003875b  call    ?WatchCurrentThread@UiaInitializeCoreUiTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UiaInitializeCoreUiTraceLoggingProvider::WatchCurrentThread(char const *)
0x180038760  nop
0x180038761  cmp     cs:byte_1803A1834, 0
0x180038768  jz      loc_1800388A6
0x18003876e  mov     ebx, cs:dword_1803A1830
0x180038774  mov     rcx, [rbp+5Fh]; this
0x180038778  test    ebx, ebx
0x18003877a  jns     short loc_180038791
0x18003877c  mov     r9d, ebx; char *
0x18003877f  lea     r8, aOnecoreWindows_155; "onecore\\windows\\accessibletech\\uiaut"...
0x180038786  mov     edx, 236h; void *
0x18003878b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038791  mov     ebx, [rbp+57h+var_88]
0x180038794  test    ebx, ebx
0x180038796  jz      short loc_1800387D5
0x180038798  call    cs:__imp_GetCurrentThreadId
0x18003879e  cmp     ebx, eax
0x1800387a0  jnz     loc_180038A40
0x1800387a6  mov     [rbp+57h+var_88], 0
0x1800387ad  mov     rcx, [rbp+57h+var_A0]
0x1800387b1  mov     rax, [rcx]
0x1800387b4  test    rax, rax
0x1800387b7  jz      short loc_1800387CD
0x1800387b9  lea     rdx, [rbp+57h+var_A0]
0x1800387bd  cmp     rax, rdx
0x1800387c0  jnz     loc_180038A65
0x1800387c6  mov     rax, [rbp+57h+var_90]
0x1800387ca  mov     [rcx], rax
0x1800387cd  mov     [rbp+57h+var_A0], 0
0x1800387d5  cmp     [rbp+57h+var_A8], 0
0x1800387d9  jz      short loc_1800387F3
0x1800387db  mov     rbx, [rbp+57h+lpMem]
0x1800387df  call    cs:__imp_GetProcessHeap
0x1800387e5  mov     r8, rbx; lpMem
0x1800387e8  xor     edx, edx; dwFlags
0x1800387ea  mov     rcx, rax; hHeap
0x1800387ed  call    cs:__imp_HeapFree
0x1800387f3  mov     qword ptr [rdi], 0
0x1800387fa  mov     [rsp+110h+var_E0], 1
0x180038802  lea     r15, ?s_instanceLock@NavigationHelperProxyOneCore@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NavigationHelperProxyOneCore::s_instanceLock
0x180038809  mov     [rbp+57h+var_D0], r15
0x18003880d  mov     rcx, r15; lpCriticalSection
0x180038810  call    cs:__imp_EnterCriticalSection
0x180038816  nop
0x180038817  mov     rbx, cs:?s_instance@NavigationHelperProxyOneCore@@0PEAV1@EA; NavigationHelperProxyOneCore * NavigationHelperProxyOneCore::s_instance
0x18003881e  test    rbx, rbx
0x180038821  jz      loc_180038A72
0x180038827  cmp     [rdi], rbx
0x18003882a  jz      short loc_18003885E
0x18003882c  test    rbx, rbx
0x18003882f  jz      short loc_180038842
0x180038831  lea     rcx, [rbx+10h]
0x180038835  mov     rax, [rcx]
0x180038838  mov     rax, [rax+8]
0x18003883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038841  nop
0x180038842  mov     rcx, [rdi]
0x180038845  mov     [rdi], rbx
0x180038848  test    rcx, rcx
0x18003884b  jz      short loc_18003885E
0x18003884d  add     rcx, 10h
0x180038851  mov     rax, [rcx]
0x180038854  mov     rax, [rax+10h]
0x180038858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003885d  nop
0x18003885e  mov     rcx, r15; lpCriticalSection
0x180038861  call    cs:__imp_LeaveCriticalSection
0x180038867  mov     rbx, [rdi]
0x18003886a  test    rbx, rbx
0x18003886d  jz      short loc_18003887F
0x18003886f  mov     rcx, rbx; this
0x180038872  call    ?EnsureCrossMachineEventSinksRegisteredIfNeeded@NavigationHelperProxyOneCore@@AEAAXXZ; NavigationHelperProxyOneCore::EnsureCrossMachineEventSinksRegisteredIfNeeded(void)
0x180038877  mov     rcx, rbx; this
0x18003887a  call    ?EnsureEndpointStateNotifierSinkRegisteredIfNeeded@NavigationHelperProxyOneCore@@AEAAXXZ; NavigationHelperProxyOneCore::EnsureEndpointStateNotifierSinkRegisteredIfNeeded(void)
0x18003887f  mov     rax, rdi
0x180038882  mov     rcx, [rbp+57h+var_20]
0x180038886  xor     rcx, rsp; StackCookie
0x180038889  call    __security_check_cookie
0x18003888e  lea     r11, [rsp+110h+var_10]
0x180038896  mov     rbx, [r11+28h]
0x18003889a  mov     rsi, [r11+30h]
0x18003889e  mov     rsp, r11
0x1800388a1  pop     r15
0x1800388a3  pop     rdi
0x1800388a4  pop     rbp
0x1800388a5  retn
0x1800388a6  xor     ebx, ebx
0x1800388a8  mov     dword ptr [rsp+110h+var_E8], ebx
0x1800388ac  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x1800388b1  test    al, al
0x1800388b3  jz      short loc_1800388EE
0x1800388b5  call    cs:__imp_GetCurrentProcessId
0x1800388bb  mov     ecx, eax; unsigned int
0x1800388bd  lea     rdx, [rsp+110h+var_E8]; unsigned int *
0x1800388c2  call    ?GetProcessIntegrityLevel@UiaUtils@@SAJIPEAK@Z; UiaUtils::GetProcessIntegrityLevel(uint,ulong *)
0x1800388c7  mov     ebx, eax
0x1800388c9  test    eax, eax
0x1800388cb  jns     loc_1800389E8
0x1800388d1  mov     rcx, [rbp+5Fh]; this
0x1800388d5  mov     r9d, eax; char *
0x1800388d8  lea     r8, aOnecoreWindows_155; "onecore\\windows\\accessibletech\\uiaut"...
0x1800388df  mov     edx, 1FBh; void *
0x1800388e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800388e9  jmp     loc_180038774
0x1800388ee  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x1800388f3  test    al, al
0x1800388f5  jnz     loc_1800389F1
0x1800388fb  call    ?IsHoloLens@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsHoloLens(void)
0x180038900  test    al, al
0x180038902  jnz     loc_1800389F1
0x180038908  mov     byte ptr [rsp+110h+var_F0.Data], al; int
0x18003890c  lea     rdx, [rsp+110h+var_F0]; struct _WNF_STATE_NAME *
0x180038911  call    ?wnf_is_published_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_is_published_nothrow(_WNF_STATE_NAME const &,bool *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180038916  mov     rcx, [rbp+5Fh]; this
0x18003891a  test    eax, eax
0x18003891c  jns     short loc_180038933
0x18003891e  mov     r9d, eax; char *
0x180038921  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180038928  mov     edx, 342h; void *
0x18003892d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038933  cmp     byte ptr [rsp+110h+var_F0.Data], 0
0x180038938  jnz     loc_1800389F1
0x18003893e  mov     ebx, 80004005h
0x180038943  jmp     loc_180038774
0x180038948  mov     [rsp+110h+var_E8], 0
0x180038951  lea     rcx, [rbp+57h+var_70]
0x180038955  call    ?DebugStartIgnoringLeaks@@YA?AV?$lambda_call@V?$function@$$A6AXXZ@std@@@details@wil@@_N@Z; DebugStartIgnoringLeaks(bool)
0x18003895a  nop
0x18003895b  mov     ecx, 2E8h; Size
0x180038960  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038965  mov     [rbp+57h+var_C8], rax
0x180038969  mov     rcx, rax; this
0x18003896c  call    ??0NavigationHelperProxyOneCore@@AEAA@XZ; NavigationHelperProxyOneCore::NavigationHelperProxyOneCore(void)
0x180038971  nop
0x180038972  mov     rdx, rax
0x180038975  lea     rcx, [rsp+110h+var_E8]
0x18003897a  call    ?Attach@?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@QEAAXPEAVNavigationHelperProxyOneCore@@@Z; Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::Attach(NavigationHelperProxyOneCore *)
0x18003897f  nop
0x180038980  lea     rcx, [rbp+57h+var_70]
0x180038984  call    ??1?$lambda_call@V?$function@$$A6AXXZ@std@@@details@wil@@QEAA@XZ; wil::details::lambda_call<std::function<void (void)>>::~lambda_call<std::function<void (void)>>(void)
0x180038989  mov     rbx, [rsp+110h+var_E8]
0x18003898e  mov     rcx, rbx; this
0x180038991  call    ?Initialize@NavigationHelperProxyOneCore@@AEAAJXZ; NavigationHelperProxyOneCore::Initialize(void)
0x180038996  mov     rcx, [rbp+5Fh]; this
0x18003899a  test    eax, eax
0x18003899c  jns     short loc_1800389B3
0x18003899e  mov     r9d, eax; char *
0x1800389a1  lea     r8, aOnecoreWindows_155; "onecore\\windows\\accessibletech\\uiaut"...
0x1800389a8  mov     edx, 254h; void *
0x1800389ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800389b3  lea     rcx, [rsp+110h+var_E8]
0x1800389b8  call    ?InternalAddRef@?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalAddRef(void)
0x1800389bd  mov     cs:?s_instance@NavigationHelperProxyOneCore@@0PEAV1@EA, rbx; NavigationHelperProxyOneCore * NavigationHelperProxyOneCore::s_instance
0x1800389c4  mov     rcx, rdi
0x1800389c7  call    ?InternalRelease@?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(void)
0x1800389cc  lea     rcx, [rsp+110h+var_E8]
0x1800389d1  call    ?InternalAddRef@?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalAddRef(void)
0x1800389d6  mov     [rdi], rbx
0x1800389d9  lea     rcx, [rsp+110h+var_E8]
0x1800389de  call    ?InternalRelease@?$ComPtr@VNavigationHelperProxyOneCore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(void)
0x1800389e3  jmp     loc_18003885E
0x1800389e8  mov     ebx, dword ptr [rsp+110h+var_E8]
0x1800389ec  jmp     loc_1800388EE
0x1800389f1  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x1800389f6  test    al, al
0x1800389f8  jz      short loc_180038A09
0x1800389fa  cmp     ebx, 1000h
0x180038a00  ja      short loc_180038A09
0x180038a02  mov     ebx, 80070005h
0x180038a07  jmp     short loc_180038A18
0x180038a09  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x180038a0e  neg     al
0x180038a10  sbb     ebx, ebx
0x180038a12  and     ebx, 80070032h
0x180038a18  mov     cs:dword_1803A1830, ebx
0x180038a1e  mov     cs:byte_1803A1834, 1
0x180038a25  movzx   eax, word ptr [rsp+110h+var_E8+5]
0x180038a2a  mov     cs:word_1803A1835, ax
0x180038a31  mov     al, byte ptr [rsp+110h+var_E8+7]
0x180038a35  mov     cs:byte_1803A1837, al
0x180038a3b  jmp     loc_180038774
0x180038a40  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180038a47  test    rax, rax
0x180038a4a  jz      loc_1800387A6
0x180038a50  mov     rdx, [rbp+5Fh]
0x180038a54  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180038a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a60  jmp     loc_1800387A6
0x180038a65  lea     rcx, [rax+10h]
0x180038a69  mov     [rbp+57h+var_A0], rcx
0x180038a6d  jmp     loc_1800387B1
0x180038a72  test    sil, sil
0x180038a75  jz      loc_18003885E
0x180038a7b  jmp     loc_180038948
```
