# IPxlatPolicyMgrUnregisterChangeNotifications

- ea: `0x18000e180`
- end: `0x18000e2eb`
- name: `IPxlatPolicyMgrUnregisterChangeNotifications`
- size: `363`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b280`

## callees

- `0x18000e180`
- `0x18000e43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e214`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e24c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e29b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e214`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e24c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e29b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e26c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e26c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e20c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e293`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e20c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e293`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e203`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e28a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e203`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e28a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e1f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e27c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e1f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e27c`
- `USERENV!UnregisterGPNotification` at `0x18000e1a7`
- `USERENV!UnregisterGPNotification` at `0x18000e1a7`

## pseudocode

```c
__int64 IPxlatPolicyMgrUnregisterChangeNotifications()
{
  DWORD LastError; // esi
  PHKEY v2; // rdi
  PHKEY v3; // r14
  struct _TP_WAIT *v4; // rbp
  DWORD v5; // ebx
  _QWORD *v6; // r14
  HKEY v7; // rbp
  DWORD v8; // ebx
  _QWORD *v9; // r14
  struct _TP_WAIT *v10; // rbp
  DWORD v11; // ebx
  HKEY v12; // rbp
  DWORD v13; // ebx

  if ( !phkResult )
    return 5023;
  LastError = 0;
  if ( !UnregisterGPNotification(phkResult[1]) )
  {
    LastError = GetLastError();
    IPxlatPolicyMgrLogger::LogError(
      (IPxlatPolicyMgrLogger *)(phkResult + 15),
      LastError,
      L"Failed to unregister group policy notifications");
  }
  v2 = phkResult;
  v3 = phkResult + 2;
  v4 = (struct _TP_WAIT *)phkResult[2];
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
    SetLastError(v5);
    v2 = phkResult;
  }
  *v3 = 0;
  v6 = v2 + 1;
  v7 = v2[1];
  if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = GetLastError();
    CloseHandle(v7);
    SetLastError(v8);
    v2 = phkResult;
  }
  *v6 = 0;
  v9 = v2 + 7;
  v10 = (struct _TP_WAIT *)v2[7];
  if ( v10 )
  {
    v11 = GetLastError();
    SetThreadpoolWait(v10, 0, 0);
    WaitForThreadpoolWaitCallbacks(v10, 1);
    CloseThreadpoolWait(v10);
    SetLastError(v11);
    v2 = phkResult;
  }
  *v9 = 0;
  v12 = v2[6];
  if ( (unsigned __int64)v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v13 = GetLastError();
    CloseHandle(v12);
    SetLastError(v13);
  }
  v2[6] = 0;
  return LastError;
}

```

## disassembly

```asm
0x18000e180  push    rbx
0x18000e182  push    rbp
0x18000e183  push    rsi
0x18000e184  push    rdi
0x18000e185  push    r14
0x18000e187  sub     rsp, 20h
0x18000e18b  mov     rcx, cs:phkResult
0x18000e192  test    rcx, rcx
0x18000e195  jnz     short loc_18000E1A1
0x18000e197  mov     eax, 139Fh
0x18000e19c  jmp     loc_18000E2E0
0x18000e1a1  mov     rcx, [rcx+8]; hEvent
0x18000e1a5  xor     esi, esi
0x18000e1a7  call    cs:__imp_UnregisterGPNotification
0x18000e1ad  test    eax, eax
0x18000e1af  jnz     short loc_18000E1D2
0x18000e1b1  call    cs:__imp_GetLastError
0x18000e1b7  mov     rcx, cs:phkResult
0x18000e1be  lea     r8, aFailedToUnregi; "Failed to unregister group policy notif"...
0x18000e1c5  add     rcx, 78h ; 'x'; this
0x18000e1c9  mov     edx, eax; unsigned int
0x18000e1cb  mov     esi, eax
0x18000e1cd  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000e1d2  mov     rdi, cs:phkResult
0x18000e1d9  lea     r14, [rdi+10h]
0x18000e1dd  mov     rbp, [r14]
0x18000e1e0  test    rbp, rbp
0x18000e1e3  jz      short loc_18000E221
0x18000e1e5  call    cs:__imp_GetLastError
0x18000e1eb  xor     r8d, r8d; pftTimeout
0x18000e1ee  xor     edx, edx; h
0x18000e1f0  mov     rcx, rbp; pwa
0x18000e1f3  mov     ebx, eax
0x18000e1f5  call    cs:__imp_SetThreadpoolWait
0x18000e1fb  mov     edx, 1; fCancelPendingCallbacks
0x18000e200  mov     rcx, rbp; pwa
0x18000e203  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000e209  mov     rcx, rbp; pwa
0x18000e20c  call    cs:__imp_CloseThreadpoolWait
0x18000e212  mov     ecx, ebx; dwErrCode
0x18000e214  call    cs:__imp_SetLastError
0x18000e21a  mov     rdi, cs:phkResult
0x18000e221  mov     qword ptr [r14], 0
0x18000e228  lea     r14, [rdi+8]
0x18000e22c  mov     rbp, [r14]
0x18000e22f  lea     rax, [rbp-1]
0x18000e233  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e237  ja      short loc_18000E259
0x18000e239  call    cs:__imp_GetLastError
0x18000e23f  mov     rcx, rbp; hObject
0x18000e242  mov     ebx, eax
0x18000e244  call    cs:__imp_CloseHandle
0x18000e24a  mov     ecx, ebx; dwErrCode
0x18000e24c  call    cs:__imp_SetLastError
0x18000e252  mov     rdi, cs:phkResult
0x18000e259  mov     qword ptr [r14], 0
0x18000e260  lea     r14, [rdi+38h]
0x18000e264  mov     rbp, [r14]
0x18000e267  test    rbp, rbp
0x18000e26a  jz      short loc_18000E2A8
0x18000e26c  call    cs:__imp_GetLastError
0x18000e272  xor     r8d, r8d; pftTimeout
0x18000e275  xor     edx, edx; h
0x18000e277  mov     rcx, rbp; pwa
0x18000e27a  mov     ebx, eax
0x18000e27c  call    cs:__imp_SetThreadpoolWait
0x18000e282  mov     edx, 1; fCancelPendingCallbacks
0x18000e287  mov     rcx, rbp; pwa
0x18000e28a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000e290  mov     rcx, rbp; pwa
0x18000e293  call    cs:__imp_CloseThreadpoolWait
0x18000e299  mov     ecx, ebx; dwErrCode
0x18000e29b  call    cs:__imp_SetLastError
0x18000e2a1  mov     rdi, cs:phkResult
0x18000e2a8  mov     qword ptr [r14], 0
0x18000e2af  mov     rbp, [rdi+30h]
0x18000e2b3  lea     rax, [rbp-1]
0x18000e2b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e2bb  ja      short loc_18000E2D6
0x18000e2bd  call    cs:__imp_GetLastError
0x18000e2c3  mov     rcx, rbp; hObject
0x18000e2c6  mov     ebx, eax
0x18000e2c8  call    cs:__imp_CloseHandle
0x18000e2ce  mov     ecx, ebx; dwErrCode
0x18000e2d0  call    cs:__imp_SetLastError
0x18000e2d6  mov     qword ptr [rdi+30h], 0
0x18000e2de  mov     eax, esi
0x18000e2e0  add     rsp, 20h
0x18000e2e4  pop     r14
0x18000e2e6  pop     rdi
0x18000e2e7  pop     rsi
0x18000e2e8  pop     rbp
0x18000e2e9  pop     rbx
0x18000e2ea  retn
```
