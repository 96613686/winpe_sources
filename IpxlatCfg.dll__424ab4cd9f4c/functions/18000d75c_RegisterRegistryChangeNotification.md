# RegisterRegistryChangeNotification

- ea: `0x18000d75c`
- end: `0x18000da1a`
- name: `RegisterRegistryChangeNotification`
- size: `702`
- prototype: `__int64 __fastcall(HKEY, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b1e0`

## callees

- `0x18000d75c`
- `0x18000e43c`
- `0x18000e478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d81d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d81d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d9b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d9b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d7f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d7f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d93f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d93f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d77f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d77f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d89a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d97f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d89a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d97f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d891`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d976`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d891`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d976`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d861`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d861`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d883`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d968`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d9ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d883`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d968`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d9ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d7b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d7b9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000d90e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000d90e`

## string_xrefs

- `0x18000d7ab`: `System\CurrentControlSet\Services\IpxlatCfgSvc`
- `0x18000d7d2`: `Failed to open IPxlatCfgSvc registry root key`
- `0x18000d843`: `Failed to create registry change event`
- `0x18000d8c0`: `Failed to create registry change threadpool`
- `0x18000d925`: `Failed to register for registry change notification`
- `0x18000d9f9`: `Registered for registry change notifications`

## pseudocode

```c
__int64 __fastcall RegisterRegistryChangeNotification(HKEY a1, HKEY a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  PHKEY v5; // rsi
  PHKEY phkResult; // rax
  int v7; // eax
  bool v8; // sf
  DWORD v9; // esi
  HKEY EventW; // rax
  HKEY v11; // rbp
  HKEY v12; // r14
  DWORD LastError; // ebx
  PHKEY v14; // rsi
  DWORD v15; // eax
  const unsigned __int16 *v16; // r8
  PHKEY v17; // rdx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v19; // rbp
  PTP_WAIT v20; // r14
  DWORD v21; // ebx
  PHKEY v22; // rcx
  LSTATUS v23; // eax
  PHKEY v24; // rdi
  PHKEY v25; // r14
  struct _TP_WAIT *v26; // rbp
  DWORD v27; // ebx
  HKEY v28; // rbp
  DWORD v29; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)(::phkResult + 10);
  EnterCriticalSection((LPCRITICAL_SECTION)::phkResult + 2);
  v5 = ::phkResult;
  phkResult = ::phkResult + 5;
  if ( !::phkResult[5] )
  {
    *phkResult = 0;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc", 0, 0x20019u, phkResult);
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
    {
      v9 = (unsigned __int16)v7;
      IPxlatPolicyMgrLogger::LogError(
        (IPxlatPolicyMgrLogger *)(::phkResult + 15),
        (unsigned __int16)v7,
        L"Failed to open IPxlatCfgSvc registry root key");
      goto LABEL_16;
    }
    v5 = ::phkResult;
  }
  EventW = (HKEY)CreateEventW(0, 1, 0, 0);
  v11 = v5[6];
  v12 = EventW;
  if ( (unsigned __int64)v11 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v11);
    SetLastError(LastError);
  }
  v5[6] = v12;
  v14 = ::phkResult;
  if ( (((unsigned __int64)::phkResult[6] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v15 = GetLastError();
    v16 = L"Failed to create registry change event";
LABEL_15:
    v9 = v15;
    IPxlatPolicyMgrLogger::LogError((IPxlatPolicyMgrLogger *)(::phkResult + 15), v15, v16);
LABEL_16:
    if ( v3 )
      LeaveCriticalSection(v3);
    if ( v9 )
    {
LABEL_23:
      v24 = ::phkResult;
      v25 = ::phkResult + 7;
      v26 = (struct _TP_WAIT *)::phkResult[7];
      if ( v26 )
      {
        v27 = GetLastError();
        SetThreadpoolWait(v26, 0, 0);
        WaitForThreadpoolWaitCallbacks(v26, 1);
        CloseThreadpoolWait(v26);
        SetLastError(v27);
        v24 = ::phkResult;
      }
      *v25 = 0;
      v28 = v24[6];
      if ( (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v29 = GetLastError();
        CloseHandle(v28);
        SetLastError(v29);
      }
      v24[6] = 0;
      return v9;
    }
    return v9;
  }
  v17 = ::phkResult + 8;
  ::phkResult[9] = a2;
  v14[8] = a1;
  ThreadpoolWait = CreateThreadpoolWait(RegistryChangeCallback, v17, 0);
  v19 = (struct _TP_WAIT *)v14[7];
  v20 = ThreadpoolWait;
  if ( v19 )
  {
    v21 = GetLastError();
    SetThreadpoolWait(v19, 0, 0);
    WaitForThreadpoolWaitCallbacks(v19, 1);
    CloseThreadpoolWait(v19);
    SetLastError(v21);
  }
  v22 = ::phkResult;
  v14[7] = (HKEY)v20;
  if ( !v22[7] )
  {
    v15 = GetLastError();
    v16 = L"Failed to create registry change threadpool";
    goto LABEL_15;
  }
  v23 = RegNotifyChangeKeyValue(v22[5], 1, 0x10000007u, v22[6], 1);
  v9 = v23;
  if ( v23 )
  {
    IPxlatPolicyMgrLogger::LogError(
      (IPxlatPolicyMgrLogger *)(::phkResult + 15),
      v23,
      L"Failed to register for registry change notification");
    if ( v3 )
      LeaveCriticalSection(v3);
    goto LABEL_23;
  }
  if ( v3 )
    LeaveCriticalSection(v3);
  SetThreadpoolWait((PTP_WAIT)::phkResult[7], ::phkResult[6], 0);
  IPxlatPolicyMgrLogger::LogInfo(
    (IPxlatPolicyMgrLogger *)(::phkResult + 15),
    L"Registered for registry change notifications");
  return v9;
}

```

## disassembly

```asm
0x18000d75c  push    rbx
0x18000d75e  push    rbp
0x18000d75f  push    rsi
0x18000d760  push    rdi
0x18000d761  push    r12
0x18000d763  push    r14
0x18000d765  push    r15
0x18000d767  sub     rsp, 30h
0x18000d76b  mov     rdi, cs:phkResult
0x18000d772  mov     r12, rcx
0x18000d775  add     rdi, 50h ; 'P'
0x18000d779  mov     r15, rdx
0x18000d77c  mov     rcx, rdi; lpCriticalSection
0x18000d77f  call    cs:__imp_EnterCriticalSection
0x18000d785  mov     rsi, cs:phkResult
0x18000d78c  lea     rax, [rsi+28h]
0x18000d790  cmp     qword ptr [rax], 0
0x18000d794  jnz     short loc_18000D7E7
0x18000d796  mov     r9d, 20019h; samDesired
0x18000d79c  mov     qword ptr [rax], 0
0x18000d7a3  xor     r8d, r8d; ulOptions
0x18000d7a6  mov     [rsp+68h+phkResult], rax; phkResult
0x18000d7ab  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ip"...
0x18000d7b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d7b9  call    cs:__imp_RegOpenKeyExW
0x18000d7bf  test    eax, eax
0x18000d7c1  jle     short loc_18000D7CD
0x18000d7c3  movzx   eax, ax
0x18000d7c6  or      eax, 80070000h
0x18000d7cb  test    eax, eax
0x18000d7cd  jns     short loc_18000D7E0
0x18000d7cf  movzx   esi, ax
0x18000d7d2  lea     r8, aFailedToOpenIp; "Failed to open IPxlatCfgSvc registry ro"...
0x18000d7d9  mov     edx, esi
0x18000d7db  jmp     loc_18000D8CB
0x18000d7e0  mov     rsi, cs:phkResult
0x18000d7e7  xor     r9d, r9d; lpName
0x18000d7ea  xor     r8d, r8d; bInitialState
0x18000d7ed  xor     ecx, ecx; lpEventAttributes
0x18000d7ef  lea     edx, [r9+1]; bManualReset
0x18000d7f3  call    cs:__imp_CreateEventW
0x18000d7f9  mov     rbp, [rsi+30h]
0x18000d7fd  mov     r14, rax
0x18000d800  lea     rdx, [rbp-1]
0x18000d804  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000d808  ja      short loc_18000D823
0x18000d80a  call    cs:__imp_GetLastError
0x18000d810  mov     rcx, rbp; hObject
0x18000d813  mov     ebx, eax
0x18000d815  call    cs:__imp_CloseHandle
0x18000d81b  mov     ecx, ebx; dwErrCode
0x18000d81d  call    cs:__imp_SetLastError
0x18000d823  mov     [rsi+30h], r14
0x18000d827  mov     rsi, cs:phkResult
0x18000d82e  mov     rax, [rsi+30h]
0x18000d832  inc     rax
0x18000d835  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d83b  jnz     short loc_18000D84C
0x18000d83d  call    cs:__imp_GetLastError
0x18000d843  lea     r8, aFailedToCreate_1; "Failed to create registry change event"
0x18000d84a  jmp     short loc_18000D8C7
0x18000d84c  lea     rdx, [rsi+40h]; pv
0x18000d850  mov     [rsi+48h], r15
0x18000d854  xor     r8d, r8d; pcbe
0x18000d857  mov     [rdx], r12
0x18000d85a  lea     rcx, RegistryChangeCallback; pfnwa
0x18000d861  call    cs:__imp_CreateThreadpoolWait
0x18000d867  mov     rbp, [rsi+38h]
0x18000d86b  mov     r14, rax
0x18000d86e  test    rbp, rbp
0x18000d871  jz      short loc_18000D8A8
0x18000d873  call    cs:__imp_GetLastError
0x18000d879  xor     r8d, r8d; pftTimeout
0x18000d87c  xor     edx, edx; h
0x18000d87e  mov     rcx, rbp; pwa
0x18000d881  mov     ebx, eax
0x18000d883  call    cs:__imp_SetThreadpoolWait
0x18000d889  mov     edx, 1; fCancelPendingCallbacks
0x18000d88e  mov     rcx, rbp; pwa
0x18000d891  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d897  mov     rcx, rbp; pwa
0x18000d89a  call    cs:__imp_CloseThreadpoolWait
0x18000d8a0  mov     ecx, ebx; dwErrCode
0x18000d8a2  call    cs:__imp_SetLastError
0x18000d8a8  mov     rcx, cs:phkResult
0x18000d8af  mov     [rsi+38h], r14
0x18000d8b3  cmp     qword ptr [rcx+38h], 0
0x18000d8b8  jnz     short loc_18000D8F3
0x18000d8ba  call    cs:__imp_GetLastError
0x18000d8c0  lea     r8, aFailedToCreate_2; "Failed to create registry change thread"...
0x18000d8c7  mov     edx, eax; unsigned int
0x18000d8c9  mov     esi, eax
0x18000d8cb  mov     rcx, cs:phkResult
0x18000d8d2  add     rcx, 78h ; 'x'; this
0x18000d8d6  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000d8db  test    rdi, rdi
0x18000d8de  jz      short loc_18000D8E9
0x18000d8e0  mov     rcx, rdi; lpCriticalSection
0x18000d8e3  call    cs:__imp_LeaveCriticalSection
0x18000d8e9  test    esi, esi
0x18000d8eb  jz      loc_18000DA09
0x18000d8f1  jmp     short loc_18000D945
0x18000d8f3  mov     r9, [rcx+30h]; hEvent
0x18000d8f7  mov     edx, 1; bWatchSubtree
0x18000d8fc  mov     rcx, [rcx+28h]; hKey
0x18000d900  mov     r8d, 10000007h; dwNotifyFilter
0x18000d906  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x18000d90e  call    cs:__imp_RegNotifyChangeKeyValue
0x18000d914  mov     esi, eax
0x18000d916  test    eax, eax
0x18000d918  jz      loc_18000D9CC
0x18000d91e  mov     rcx, cs:phkResult
0x18000d925  lea     r8, aFailedToRegist; "Failed to register for registry change "...
0x18000d92c  add     rcx, 78h ; 'x'; this
0x18000d930  mov     edx, eax; unsigned int
0x18000d932  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000d937  test    rdi, rdi
0x18000d93a  jz      short loc_18000D945
0x18000d93c  mov     rcx, rdi; lpCriticalSection
0x18000d93f  call    cs:__imp_LeaveCriticalSection
0x18000d945  mov     rdi, cs:phkResult
0x18000d94c  lea     r14, [rdi+38h]
0x18000d950  mov     rbp, [r14]
0x18000d953  test    rbp, rbp
0x18000d956  jz      short loc_18000D994
0x18000d958  call    cs:__imp_GetLastError
0x18000d95e  xor     r8d, r8d; pftTimeout
0x18000d961  xor     edx, edx; h
0x18000d963  mov     rcx, rbp; pwa
0x18000d966  mov     ebx, eax
0x18000d968  call    cs:__imp_SetThreadpoolWait
0x18000d96e  mov     edx, 1; fCancelPendingCallbacks
0x18000d973  mov     rcx, rbp; pwa
0x18000d976  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d97c  mov     rcx, rbp; pwa
0x18000d97f  call    cs:__imp_CloseThreadpoolWait
0x18000d985  mov     ecx, ebx; dwErrCode
0x18000d987  call    cs:__imp_SetLastError
0x18000d98d  mov     rdi, cs:phkResult
0x18000d994  mov     qword ptr [r14], 0
0x18000d99b  mov     rbp, [rdi+30h]
0x18000d99f  lea     rax, [rbp-1]
0x18000d9a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d9a7  ja      short loc_18000D9C2
0x18000d9a9  call    cs:__imp_GetLastError
0x18000d9af  mov     rcx, rbp; hObject
0x18000d9b2  mov     ebx, eax
0x18000d9b4  call    cs:__imp_CloseHandle
0x18000d9ba  mov     ecx, ebx; dwErrCode
0x18000d9bc  call    cs:__imp_SetLastError
0x18000d9c2  mov     qword ptr [rdi+30h], 0
0x18000d9ca  jmp     short loc_18000DA09
0x18000d9cc  test    rdi, rdi
0x18000d9cf  jz      short loc_18000D9DA
0x18000d9d1  mov     rcx, rdi; lpCriticalSection
0x18000d9d4  call    cs:__imp_LeaveCriticalSection
0x18000d9da  mov     rcx, cs:phkResult
0x18000d9e1  xor     r8d, r8d; pftTimeout
0x18000d9e4  mov     rdx, [rcx+30h]; h
0x18000d9e8  mov     rcx, [rcx+38h]; pwa
0x18000d9ec  call    cs:__imp_SetThreadpoolWait
0x18000d9f2  mov     rcx, cs:phkResult
0x18000d9f9  lea     rdx, aRegisteredForR; "Registered for registry change notifica"...
0x18000da00  add     rcx, 78h ; 'x'; this
0x18000da04  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000da09  mov     eax, esi
0x18000da0b  add     rsp, 30h
0x18000da0f  pop     r15
0x18000da11  pop     r14
0x18000da13  pop     r12
0x18000da15  pop     rdi
0x18000da16  pop     rsi
0x18000da17  pop     rbp
0x18000da18  pop     rbx
0x18000da19  retn
```
