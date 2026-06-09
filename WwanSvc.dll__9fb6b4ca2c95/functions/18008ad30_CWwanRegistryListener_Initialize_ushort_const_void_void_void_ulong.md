# CWwanRegistryListener::Initialize(ushort const *,void (*)(void *),void *,ulong)

- ea: `0x18008ad30`
- end: `0x18008af28`
- name: `?Initialize@CWwanRegistryListener@@QEAAKPEBGP6AXPEAX@Z1K@Z`
- size: `504`
- prototype: `unsigned int __fastcall(PVOID pv, LPCWSTR lpSubKey, void (*)(void *), void *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057124`
- `0x180066ac4`

## callees

- `0x18000a2dc`
- `0x180012300`
- `0x180014f1c`
- `0x18005ab34`
- `0x18008abe4`
- `0x18008ad24`
- `0x18008ad30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ad69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aeeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ad69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aeeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aef6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008ae3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008ae3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008aed8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008aed8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18008aea7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18008aea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008aded`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008aded`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18008ae78`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18008ae78`

## string_xrefs

- `0x18008ad74`: `already initialized`
- `0x18008ad44`: `CWwanRegistryListener::Initialize`
- `0x18008ae1e`: `the main regkey path %s can't be opened (error %u)`
- `0x18008adfd`: ` reg path %s does not exist. MDM roam policy will not function at this boot`
- `0x18008ae4d`: `Failed to CreateEvent`
- `0x18008aeb6`: `Failed to CreateThreadpoolWait`

## pseudocode

```c
__int64 __fastcall CWwanRegistryListener::Initialize(char *pv, LPCWSTR lpSubKey, void (*a3)(void *), void *a4)
{
  __int64 v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  HANDLE EventW; // rax
  unsigned int v12; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-58h]
  _BYTE v15[72]; // [rsp+30h] [rbp-48h] BYREF
  void *v16; // [rsp+98h] [rbp+20h] BYREF

  v16 = a4;
  WwanLog::Info("CWwanRegistryListener::Initialize", 0, L" Initializing ");
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 8));
  if ( *(_DWORD *)pv )
  {
    WwanLog::Error("CWwanRegistryListener::Initialize", 0, L"already initialized");
    LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 8));
    return 5023;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 8));
  *((_QWORD *)pv + 10) = a3;
  *((_QWORD *)pv + 11) = 0;
  *((_DWORD *)pv + 14) = 268435461;
  v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v16, pv);
  wil::scope_exit__NlaplgCommit_::_2_::_lambda_1___(v15, v8);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, (PHKEY)pv + 6);
  v10 = v9;
  if ( v9 == 2 )
  {
    WwanLog::Info(
      "CWwanRegistryListener::Initialize",
      0,
      L" reg path %s does not exist. MDM roam policy will not function at this boot",
      lpSubKey);
LABEL_14:
    v10 = 0;
    goto LABEL_15;
  }
  if ( v9 )
  {
    LODWORD(phkResult) = v9;
    WwanLog::Error(
      "CWwanRegistryListener::Initialize",
      0,
      L"the main regkey path %s can't be opened (error %u)",
      lpSubKey,
      phkResult);
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)pv + 8) = EventW;
    if ( !EventW )
    {
      WwanLog::Error("CWwanRegistryListener::Initialize", 0, L"Failed to CreateEvent");
      goto LABEL_14;
    }
    v12 = RegNotifyChangeKeyValue(*((HKEY *)pv + 6), 1, *((_DWORD *)pv + 14), EventW, 1);
    v10 = v12;
    if ( v12 )
    {
      WwanLog::Error("CWwanRegistryListener::Initialize", 0, L"Failed to RegNotifyChangeKeyValue %u", v12);
    }
    else
    {
      ThreadpoolWait = CreateThreadpoolWait(CWwanRegistryListener::_RegistryListenerChangeOSCb, pv, 0);
      *((_QWORD *)pv + 9) = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)pv + 8), 0);
        wil::details::ScopeExitFn__CWwanRegistryListener::Initialize_::_2_::_lambda_1___::Dismiss(v15);
        EnterCriticalSection((LPCRITICAL_SECTION)(pv + 8));
        *(_DWORD *)pv = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 8));
        WwanLog::Info("CWwanRegistryListener::Initialize", 0, L" Successfully Initialized");
        goto LABEL_14;
      }
      WwanLog::Error("CWwanRegistryListener::Initialize", 0, L"Failed to CreateThreadpoolWait");
      v10 = 5023;
    }
  }
LABEL_15:
  wil::details::ScopeExitFn__CWwanRegistryListener::Initialize_::_2_::_lambda_1___::_ScopeExitFn__CWwanRegistryListener::Initialize_::_2_::_lambda_1___(v15);
  return v10;
}

```

## disassembly

```asm
0x18008ad30  mov     [rsp+arg_18], r9
0x18008ad35  push    rbx
0x18008ad36  push    rbp
0x18008ad37  push    rsi
0x18008ad38  push    rdi
0x18008ad39  push    r14
0x18008ad3b  push    r15
0x18008ad3d  sub     rsp, 48h
0x18008ad41  mov     rbx, r8
0x18008ad44  lea     r15, aCwwanregistryl_1; "CWwanRegistryListener::Initialize"
0x18008ad4b  mov     rbp, rdx
0x18008ad4e  lea     r8, aInitializing; " Initializing "
0x18008ad55  mov     rdi, rcx
0x18008ad58  xor     edx, edx; struct _GUID *
0x18008ad5a  mov     rcx, r15; char *
0x18008ad5d  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008ad62  lea     rsi, [rdi+8]
0x18008ad66  mov     rcx, rsi; lpCriticalSection
0x18008ad69  call    cs:__imp_EnterCriticalSection
0x18008ad6f  cmp     dword ptr [rdi], 0
0x18008ad72  jz      short loc_18008AD98
0x18008ad74  lea     r8, aAlreadyInitial; "already initialized"
0x18008ad7b  xor     edx, edx; struct _GUID *
0x18008ad7d  mov     rcx, r15; char *
0x18008ad80  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008ad85  mov     rcx, rsi; lpCriticalSection
0x18008ad88  call    cs:__imp_LeaveCriticalSection
0x18008ad8e  mov     eax, 139Fh
0x18008ad93  jmp     loc_18008AF1B
0x18008ad98  mov     rcx, rsi; lpCriticalSection
0x18008ad9b  call    cs:__imp_LeaveCriticalSection
0x18008ada1  mov     rdx, rdi
0x18008ada4  mov     [rdi+50h], rbx
0x18008ada8  lea     rcx, [rsp+78h+arg_18]
0x18008adb0  mov     qword ptr [rdi+58h], 0
0x18008adb8  mov     dword ptr [rdi+38h], 10000005h
0x18008adbf  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18008adc4  mov     rdx, rax
0x18008adc7  lea     rcx, [rsp+78h+var_48]
0x18008adcc  call    wil__scope_exit__NlaplgCommit____2____lambda_1___
0x18008add1  lea     r14, [rdi+30h]
0x18008add5  mov     r9d, 20019h; samDesired
0x18008addb  xor     r8d, r8d; ulOptions
0x18008adde  mov     [rsp+78h+phkResult], r14; phkResult
0x18008ade3  mov     rdx, rbp; lpSubKey
0x18008ade6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008aded  call    cs:__imp_RegOpenKeyExW
0x18008adf3  mov     ebx, eax
0x18008adf5  cmp     eax, 2
0x18008adf8  jnz     short loc_18008AE13
0x18008adfa  mov     r9, rbp
0x18008adfd  lea     r8, aRegPathSDoesNo; " reg path %s does not exist. MDM roam p"...
0x18008ae04  xor     edx, edx; struct _GUID *
0x18008ae06  mov     rcx, r15; char *
0x18008ae09  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008ae0e  jmp     loc_18008AF0D
0x18008ae13  test    eax, eax
0x18008ae15  jz      short loc_18008AE34
0x18008ae17  mov     r9, rbp
0x18008ae1a  mov     dword ptr [rsp+78h+phkResult], eax
0x18008ae1e  lea     r8, aTheMainRegkeyP; "the main regkey path %s can't be opened"...
0x18008ae25  xor     edx, edx; struct _GUID *
0x18008ae27  mov     rcx, r15; char *
0x18008ae2a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008ae2f  jmp     loc_18008AF0F
0x18008ae34  xor     r9d, r9d; lpName
0x18008ae37  xor     r8d, r8d; bInitialState
0x18008ae3a  xor     edx, edx; bManualReset
0x18008ae3c  xor     ecx, ecx; lpEventAttributes
0x18008ae3e  call    cs:__imp_CreateEventW
0x18008ae44  mov     [rdi+40h], rax
0x18008ae48  test    rax, rax
0x18008ae4b  jnz     short loc_18008AE63
0x18008ae4d  lea     r8, aFailedToCreate_5; "Failed to CreateEvent"
0x18008ae54  xor     edx, edx; struct _GUID *
0x18008ae56  mov     rcx, r15; char *
0x18008ae59  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008ae5e  jmp     loc_18008AF0D
0x18008ae63  mov     r8d, [rdi+38h]; dwNotifyFilter
0x18008ae67  mov     ebp, 1
0x18008ae6c  mov     rcx, [r14]; hKey
0x18008ae6f  mov     edx, ebp; bWatchSubtree
0x18008ae71  mov     r9, rax; hEvent
0x18008ae74  mov     dword ptr [rsp+78h+phkResult], ebp; fAsynchronous
0x18008ae78  call    cs:__imp_RegNotifyChangeKeyValue
0x18008ae7e  mov     ebx, eax
0x18008ae80  test    eax, eax
0x18008ae82  jz      short loc_18008AE9A
0x18008ae84  mov     r9d, eax
0x18008ae87  lea     r8, aFailedToRegnot; "Failed to RegNotifyChangeKeyValue %u"
0x18008ae8e  xor     edx, edx; struct _GUID *
0x18008ae90  mov     rcx, r15; char *
0x18008ae93  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008ae98  jmp     short loc_18008AF0F
0x18008ae9a  xor     r8d, r8d; pcbe
0x18008ae9d  lea     rcx, ?_RegistryListenerChangeOSCb@CWwanRegistryListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18008aea4  mov     rdx, rdi; pv
0x18008aea7  call    cs:__imp_CreateThreadpoolWait
0x18008aead  mov     [rdi+48h], rax
0x18008aeb1  test    rax, rax
0x18008aeb4  jnz     short loc_18008AECE
0x18008aeb6  lea     r8, aFailedToCreate_3; "Failed to CreateThreadpoolWait"
0x18008aebd  xor     edx, edx; struct _GUID *
0x18008aebf  mov     rcx, r15; char *
0x18008aec2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008aec7  mov     ebx, 139Fh
0x18008aecc  jmp     short loc_18008AF0F
0x18008aece  mov     rdx, [rdi+40h]; h
0x18008aed2  xor     r8d, r8d; pftTimeout
0x18008aed5  mov     rcx, rax; pwa
0x18008aed8  call    cs:__imp_SetThreadpoolWait
0x18008aede  lea     rcx, [rsp+78h+var_48]
0x18008aee3  call    wil__details__ScopeExitFn__CWwanRegistryListener__Initialize____2____lambda_1_____Dismiss
0x18008aee8  mov     rcx, rsi; lpCriticalSection
0x18008aeeb  call    cs:__imp_EnterCriticalSection
0x18008aef1  mov     rcx, rsi; lpCriticalSection
0x18008aef4  mov     [rdi], ebp
0x18008aef6  call    cs:__imp_LeaveCriticalSection
0x18008aefc  lea     r8, aSuccessfullyIn; " Successfully Initialized"
0x18008af03  xor     edx, edx; struct _GUID *
0x18008af05  mov     rcx, r15; char *
0x18008af08  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008af0d  xor     ebx, ebx
0x18008af0f  lea     rcx, [rsp+78h+var_48]
0x18008af14  call    wil__details__ScopeExitFn__CWwanRegistryListener__Initialize____2____lambda_1______ScopeExitFn__CWwanRegistryListener__Initialize____2____lambda_1___
0x18008af19  mov     eax, ebx
0x18008af1b  add     rsp, 48h
0x18008af1f  pop     r15
0x18008af21  pop     r14
0x18008af23  pop     rdi
0x18008af24  pop     rsi
0x18008af25  pop     rbp
0x18008af26  pop     rbx
0x18008af27  retn
```
