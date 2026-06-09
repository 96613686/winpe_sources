# WJRegisterKeyNotification

- ea: `0x18002b6fc`
- end: `0x18002ba0e`
- name: `WJRegisterKeyNotification`
- size: `786`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001cdcc`
- `0x18001d81c`

## callees

- `0x18002b6fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b9cf`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b9cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b7b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b7b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b7fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b7fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b90c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b90c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b813`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b870`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002b8f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002b8f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b97a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b9a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b97a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b9a3`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b7e3`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b841`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b897`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002ba03`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b7e3`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b841`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b897`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002ba03`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b77f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b8ca`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b99b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b77f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b8ca`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b99b`

## string_xrefs

- `0x18002b75a`: `AutoJoinSvc/%s: started. Key name: "%s". Reg key: "%s\%s". Task: "%s\%s". bInitialState: %s.`
- `0x18002b7dc`: `AutoJoinSvc/%s: Failed to open %s registry key "%s\%s" with status 0x%08x.`
- `0x18002b82b`: `AutoJoinSvc/%s: Failed to create wait event for %s with status 0x%08x.`
- `0x18002b912`: `AutoJoinSvc/%s: Failed to create thread-pool wait for %s with status 0x%08x.`
- `0x18002b994`: `AutoJoinSvc/%s: Successfully queued a thread to set initial state of the task ("%s\%s")`
- `0x18002b890`: `AutoJoinSvc/%s: Failed to register change notification for %s registry key "%s\%s" with status 0x%08x.`
- `0x18002b9fc`: `AutoJoinSvc/%s: Failed to register change notification for %s registry key "%s\%s" with status 0x%08x.`
- `0x18002b8ae`: `AutoJoinSvc/%s: finished - Return code: 0x%08x. Key name: "%s". Reg key: "%s\%s". Task: "%s\%s". bInitialState: %s.`

## pseudocode

```c
__int64 __fastcall WJRegisterKeyNotification(
        struct _FILETIME a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        HKEY a9,
        HKEY a10,
        HKEY a11,
        PVOID pv)
{
  int v12; // r15d
  __int64 v13; // r12
  const wchar_t *v14; // r13
  HKEY v15; // rbp
  HKEY EventW; // rsi
  HKEY *v18; // rdi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  DWORD LastError; // eax
  const wchar_t *v22; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v25; // rcx
  HKEY v26; // rdx
  HKEY v27; // rax
  LSTATUS v28; // eax
  __int64 v29; // [rsp+28h] [rbp-60h]
  struct _FILETIME pftTimeout; // [rsp+90h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+10h] BYREF

  pftTimeout = a1;
  v12 = a6;
  v13 = a8;
  v14 = L"TRUE";
  v15 = a9;
  EventW = 0;
  hKey = 0;
  if ( !a6 )
    v14 = L"FALSE";
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: started. Key name: \"%s\". Reg key: \"%s\\%s\". Task: \"%s\\%s\". bInitialState: %s.",
    L"WJRegisterKeyNotification",
    a9,
    L"HKEY_LOCAL_MACHINE",
    a3,
    g_szTaskFolder,
    a8,
    v14);
  v18 = (HKEY *)pv;
  *(_QWORD *)pv = 0;
  v18[1] = 0;
  v18[2] = 0;
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x10u, &hKey);
  v20 = v19;
  if ( v19 )
  {
    LODWORD(v29) = v19;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to open %s registry key \"%s\\%s\" with status 0x%08x.",
      L"WJRegisterKeyNotification",
      v15,
      L"HKEY_LOCAL_MACHINE",
      a3,
      v29);
    if ( !v12 )
      goto LABEL_10;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  EventW = (HKEY)CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v22 = L"AutoJoinSvc/%s: Failed to create wait event for %s with status 0x%08x.";
LABEL_9:
    v20 = LastError;
    DsrWriteAutoJoinSvcAdminEvent(v22, L"WJRegisterKeyNotification", v15, LastError);
    goto LABEL_10;
  }
  ThreadpoolWait = CreateThreadpoolWait(WJRegistryKeyChangedCallback, v18, 0);
  v18[2] = (HKEY)ThreadpoolWait;
  v25 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = GetLastError();
    v22 = L"AutoJoinSvc/%s: Failed to create thread-pool wait for %s with status 0x%08x.";
    goto LABEL_9;
  }
  *v18 = hKey;
  v26 = EventW;
  v18[5] = a10;
  v27 = a11;
  v18[1] = EventW;
  EventW = 0;
  v18[6] = v27;
  hKey = 0;
  *((_DWORD *)v18 + 6) = 0;
  *((_DWORD *)v18 + 7) = 268435460;
  v18[4] = v15;
  if ( v12 )
  {
    pftTimeout = 0;
    SetThreadpoolWait(v25, v26, &pftTimeout);
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Successfully queued a thread to set initial state of the task (\"%s\\%s\")",
      L"WJRegisterKeyNotification",
      g_szTaskFolder,
      v13);
  }
  else
  {
    SetThreadpoolWait(v25, v26, 0);
  }
  if ( *v18 )
  {
    v28 = RegNotifyChangeKeyValue(*v18, *((_DWORD *)v18 + 6), *((_DWORD *)v18 + 7), v18[1], 1);
    v20 = v28;
    if ( v28 )
    {
      LODWORD(v29) = v28;
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to register change notification for %s registry key \"%s\\%s\" with status 0x%08x.",
        L"WJRegisterKeyNotification",
        v15,
        L"HKEY_LOCAL_MACHINE",
        a3,
        v29);
    }
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( EventW )
    CloseHandle(EventW);
  if ( v20 )
  {
    LODWORD(v29) = v20;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to register change notification for %s registry key \"%s\\%s\" with status 0x%08x.",
      L"WJRegisterKeyNotification",
      v15,
      L"HKEY_LOCAL_MACHINE",
      a3,
      v29);
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - Return code: 0x%08x. Key name: \"%s\". Reg key: \"%s\\%s\". Task: \"%s\\%s\". bInitialState: %s.",
    L"WJRegisterKeyNotification",
    v20,
    v15,
    L"HKEY_LOCAL_MACHINE",
    a3,
    g_szTaskFolder,
    v13,
    v14);
  return v20;
}

```

## disassembly

```asm
0x18002b6fc  mov     r11, rsp
0x18002b6ff  mov     [r11+18h], rbx
0x18002b703  mov     [r11+10h], rdx
0x18002b707  mov     [r11+8], rcx
0x18002b70b  push    rbp
0x18002b70c  push    rsi
0x18002b70d  push    rdi
0x18002b70e  push    r12
0x18002b710  push    r13
0x18002b712  push    r14
0x18002b714  push    r15
0x18002b716  sub     rsp, 50h
0x18002b71a  mov     r15d, [rsp+88h+arg_28]
0x18002b722  lea     rax, aFalse_0; "FALSE"
0x18002b729  mov     r12, [rsp+88h+arg_38]
0x18002b731  lea     r13, aTrue_0; "TRUE"
0x18002b738  mov     rbp, [rsp+88h+arg_40]
0x18002b740  lea     r9, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002b747  xor     esi, esi
0x18002b749  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b750  mov     r14, r8
0x18002b753  mov     [r11+10h], rsi
0x18002b757  test    r15d, r15d
0x18002b75a  lea     rcx, aAutojoinsvcSSt_0; "AutoJoinSvc/%s: started. Key name: \"%s"...
0x18002b761  cmovz   r13, rax
0x18002b765  lea     rax, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002b76c  mov     [r11-50h], r13
0x18002b770  mov     [r11-58h], r12
0x18002b774  mov     [r11-60h], rax
0x18002b778  mov     [r11-68h], r8
0x18002b77c  mov     r8, rbp
0x18002b77f  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b785  mov     rdi, [rsp+88h+pv]
0x18002b78d  lea     rax, [rsp+88h+hKey]
0x18002b795  lea     r9d, [rsi+10h]; samDesired
0x18002b799  mov     [rsp+88h+phkResult], rax; phkResult
0x18002b79e  xor     r8d, r8d; ulOptions
0x18002b7a1  mov     rdx, r14; lpSubKey
0x18002b7a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b7ab  mov     [rdi], rsi
0x18002b7ae  mov     [rdi+8], rsi
0x18002b7b2  mov     [rdi+10h], rsi
0x18002b7b6  call    cs:__imp_RegOpenKeyExW
0x18002b7bc  mov     ebx, eax
0x18002b7be  test    eax, eax
0x18002b7c0  jz      short loc_18002B809
0x18002b7c2  mov     dword ptr [rsp+88h+var_60], eax
0x18002b7c6  lea     r9, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002b7cd  mov     r8, rbp
0x18002b7d0  mov     [rsp+88h+phkResult], r14
0x18002b7d5  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b7dc  lea     rcx, aAutojoinsvcSFa_9; "AutoJoinSvc/%s: Failed to open %s regis"...
0x18002b7e3  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002b7e9  test    r15d, r15d
0x18002b7ec  jz      short loc_18002B847
0x18002b7ee  mov     rcx, [rsp+88h+hKey]; hKey
0x18002b7f6  test    rcx, rcx
0x18002b7f9  jz      short loc_18002B809
0x18002b7fb  call    cs:__imp_RegCloseKey
0x18002b801  mov     [rsp+88h+hKey], rsi
0x18002b809  xor     r9d, r9d; lpName
0x18002b80c  xor     r8d, r8d; bInitialState
0x18002b80f  xor     edx, edx; bManualReset
0x18002b811  xor     ecx, ecx; lpEventAttributes
0x18002b813  call    cs:__imp_CreateEventW
0x18002b819  mov     rsi, rax
0x18002b81c  test    rax, rax
0x18002b81f  jnz     loc_18002B8EA
0x18002b825  call    cs:__imp_GetLastError
0x18002b82b  lea     rcx, aAutojoinsvcSFa_18; "AutoJoinSvc/%s: Failed to create wait e"...
0x18002b832  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b839  mov     r8, rbp
0x18002b83c  mov     r9d, eax
0x18002b83f  mov     ebx, eax
0x18002b841  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002b847  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002b84e  lea     rdi, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002b855  mov     rcx, [rsp+88h+hKey]; hKey
0x18002b85d  test    rcx, rcx
0x18002b860  jz      short loc_18002B868
0x18002b862  call    cs:__imp_RegCloseKey
0x18002b868  test    rsi, rsi
0x18002b86b  jz      short loc_18002B876
0x18002b86d  mov     rcx, rsi; hObject
0x18002b870  call    cs:__imp_CloseHandle
0x18002b876  test    ebx, ebx
0x18002b878  jz      short loc_18002B89D
0x18002b87a  mov     dword ptr [rsp+88h+var_60], ebx
0x18002b87e  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b885  mov     r9, rdi
0x18002b888  mov     [rsp+88h+phkResult], r14
0x18002b88d  mov     r8, rbp
0x18002b890  lea     rcx, aAutojoinsvcSFa_21; "AutoJoinSvc/%s: Failed to register chan"...
0x18002b897  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002b89d  mov     [rsp+88h+var_48], r13
0x18002b8a2  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b8a9  mov     [rsp+88h+var_50], r12
0x18002b8ae  lea     rcx, aAutojoinsvcSFi_0; "AutoJoinSvc/%s: finished - Return code:"...
0x18002b8b5  mov     [rsp+88h+var_58], r15
0x18002b8ba  mov     r9, rbp
0x18002b8bd  mov     [rsp+88h+var_60], r14
0x18002b8c2  mov     r8d, ebx
0x18002b8c5  mov     [rsp+88h+phkResult], rdi
0x18002b8ca  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b8d0  mov     eax, ebx
0x18002b8d2  mov     rbx, [rsp+88h+arg_10]
0x18002b8da  add     rsp, 50h
0x18002b8de  pop     r15
0x18002b8e0  pop     r14
0x18002b8e2  pop     r13
0x18002b8e4  pop     r12
0x18002b8e6  pop     rdi
0x18002b8e7  pop     rsi
0x18002b8e8  pop     rbp
0x18002b8e9  retn
0x18002b8ea  xor     r8d, r8d; pcbe
0x18002b8ed  lea     rcx, WJRegistryKeyChangedCallback; pfnwa
0x18002b8f4  mov     rdx, rdi; pv
0x18002b8f7  call    cs:__imp_CreateThreadpoolWait
0x18002b8fd  xor     r8d, r8d; pftTimeout
0x18002b900  mov     [rdi+10h], rax
0x18002b904  mov     rcx, rax; pwa
0x18002b907  test    rax, rax
0x18002b90a  jnz     short loc_18002B91E
0x18002b90c  call    cs:__imp_GetLastError
0x18002b912  lea     rcx, aAutojoinsvcSFa_14; "AutoJoinSvc/%s: Failed to create thread"...
0x18002b919  jmp     loc_18002B832
0x18002b91e  mov     rax, [rsp+88h+hKey]
0x18002b926  mov     r9, rsi
0x18002b929  mov     [rdi], rax
0x18002b92c  mov     rdx, rsi; h
0x18002b92f  mov     rax, [rsp+88h+arg_48]
0x18002b937  mov     [rdi+28h], rax
0x18002b93b  mov     rax, [rsp+88h+arg_50]
0x18002b943  mov     [rdi+8], rsi
0x18002b947  mov     rsi, r8
0x18002b94a  mov     [rdi+30h], rax
0x18002b94e  mov     [rsp+88h+hKey], r8
0x18002b956  mov     [rdi+18h], r8d
0x18002b95a  mov     dword ptr [rdi+1Ch], 10000004h
0x18002b961  mov     [rdi+20h], rbp
0x18002b965  test    r15d, r15d
0x18002b968  jz      short loc_18002B9A3
0x18002b96a  mov     qword ptr [rsp+88h+pftTimeout.dwLowDateTime], r8
0x18002b972  lea     r8, [rsp+88h+pftTimeout]; pftTimeout
0x18002b97a  call    cs:__imp_SetThreadpoolWait
0x18002b980  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002b987  mov     r9, r12
0x18002b98a  mov     r8, r15
0x18002b98d  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b994  lea     rcx, aAutojoinsvcSSu; "AutoJoinSvc/%s: Successfully queued a t"...
0x18002b99b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b9a1  jmp     short loc_18002B9B0
0x18002b9a3  call    cs:__imp_SetThreadpoolWait
0x18002b9a9  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002b9b0  mov     rcx, [rdi]; hKey
0x18002b9b3  test    rcx, rcx
0x18002b9b6  jz      loc_18002B84E
0x18002b9bc  mov     r9, [rdi+8]; hEvent
0x18002b9c0  mov     r8d, [rdi+1Ch]; dwNotifyFilter
0x18002b9c4  mov     edx, [rdi+18h]; bWatchSubtree
0x18002b9c7  mov     dword ptr [rsp+88h+phkResult], 1; fAsynchronous
0x18002b9cf  call    cs:__imp_RegNotifyChangeKeyValue
0x18002b9d5  mov     ebx, eax
0x18002b9d7  test    eax, eax
0x18002b9d9  jz      loc_18002B84E
0x18002b9df  mov     dword ptr [rsp+88h+var_60], eax
0x18002b9e3  lea     rdi, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002b9ea  mov     r9, rdi
0x18002b9ed  mov     [rsp+88h+phkResult], r14
0x18002b9f2  mov     r8, rbp
0x18002b9f5  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002b9fc  lea     rcx, aAutojoinsvcSFa_21; "AutoJoinSvc/%s: Failed to register chan"...
0x18002ba03  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002ba09  jmp     loc_18002B855
```
