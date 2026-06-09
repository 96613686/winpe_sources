# RegisterPolicyChangeNotification

- ea: `0x18000d550`
- end: `0x18000d756`
- name: `RegisterPolicyChangeNotification`
- size: `518`
- prototype: `__int64 __fastcall(HKEY, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b1e0`

## callees

- `0x18000d550`
- `0x18000e43c`
- `0x18000e478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d706`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d576`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d576`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d620`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d620`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d617`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d6c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d617`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d6c0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d5e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d5e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d609`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d72a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d609`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d72a`
- `USERENV!RegisterGPNotification` at `0x18000d658`
- `USERENV!RegisterGPNotification` at `0x18000d658`

## string_xrefs

- `0x18000d5c6`: `Failed to create policy change event`
- `0x18000d646`: `Failed to create policy change threadpool`

## pseudocode

```c
__int64 __fastcall RegisterPolicyChangeNotification(HKEY a1, HKEY a2)
{
  PHKEY v2; // rsi
  HKEY EventW; // rax
  HKEY v6; // rdi
  HKEY v7; // rbp
  DWORD LastError; // ebx
  PHKEY v9; // rdi
  DWORD v10; // eax
  const unsigned __int16 *v11; // r8
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v13; // rsi
  PTP_WAIT v14; // rbp
  DWORD v15; // ebx
  PHKEY v16; // rcx
  DWORD v17; // edi
  PHKEY v18; // rsi
  PHKEY v19; // r14
  struct _TP_WAIT *v20; // rbp
  DWORD v21; // ebx
  HKEY v22; // rbp
  DWORD v23; // ebx

  v2 = phkResult;
  EventW = (HKEY)CreateEventW(0, 1, 0, 0);
  v6 = v2[1];
  v7 = EventW;
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v6);
    SetLastError(LastError);
  }
  v9 = phkResult;
  v2[1] = v7;
  if ( (((unsigned __int64)v9[1] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v9[4] = a2;
    v9[3] = a1;
    ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)PolicyChangeCallback, v9 + 3, 0);
    v13 = (struct _TP_WAIT *)v9[2];
    v14 = ThreadpoolWait;
    if ( v13 )
    {
      v15 = GetLastError();
      SetThreadpoolWait(v13, 0, 0);
      WaitForThreadpoolWaitCallbacks(v13, 1);
      CloseThreadpoolWait(v13);
      SetLastError(v15);
    }
    v16 = phkResult;
    v9[2] = (HKEY)v14;
    if ( v16[2] )
    {
      if ( RegisterGPNotification(v16[1], 1) )
      {
        v17 = 0;
        SetThreadpoolWait((PTP_WAIT)phkResult[2], phkResult[1], 0);
        IPxlatPolicyMgrLogger::LogInfo(
          (IPxlatPolicyMgrLogger *)(phkResult + 15),
          L"Registered for group policy change notifications");
        return v17;
      }
      v10 = GetLastError();
      v11 = L"Failed to register for group policy notifications";
    }
    else
    {
      v10 = GetLastError();
      v11 = L"Failed to create policy change threadpool";
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = L"Failed to create policy change event";
  }
  v17 = v10;
  IPxlatPolicyMgrLogger::LogError((IPxlatPolicyMgrLogger *)(phkResult + 15), v10, v11);
  if ( v17 )
  {
    v18 = phkResult;
    v19 = phkResult + 2;
    v20 = (struct _TP_WAIT *)phkResult[2];
    if ( v20 )
    {
      v21 = GetLastError();
      SetThreadpoolWait(v20, 0, 0);
      WaitForThreadpoolWaitCallbacks(v20, 1);
      CloseThreadpoolWait(v20);
      SetLastError(v21);
      v18 = phkResult;
    }
    *v19 = 0;
    v22 = v18[1];
    if ( (unsigned __int64)v22 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v23 = GetLastError();
      CloseHandle(v22);
      SetLastError(v23);
    }
    v18[1] = 0;
  }
  return v17;
}

```

## disassembly

```asm
0x18000d550  push    rbx
0x18000d552  push    rbp
0x18000d553  push    rsi
0x18000d554  push    rdi
0x18000d555  push    r14
0x18000d557  push    r15
0x18000d559  sub     rsp, 28h
0x18000d55d  mov     rsi, cs:phkResult
0x18000d564  xor     r9d, r9d; lpName
0x18000d567  mov     r14, rdx
0x18000d56a  mov     r15, rcx
0x18000d56d  xor     r8d, r8d; bInitialState
0x18000d570  xor     ecx, ecx; lpEventAttributes
0x18000d572  lea     edx, [r9+1]; bManualReset
0x18000d576  call    cs:__imp_CreateEventW
0x18000d57c  mov     rdi, [rsi+8]
0x18000d580  mov     rbp, rax
0x18000d583  lea     r8, [rdi-1]
0x18000d587  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x18000d58b  ja      short loc_18000D5A6
0x18000d58d  call    cs:__imp_GetLastError
0x18000d593  mov     rcx, rdi; hObject
0x18000d596  mov     ebx, eax
0x18000d598  call    cs:__imp_CloseHandle
0x18000d59e  mov     ecx, ebx; dwErrCode
0x18000d5a0  call    cs:__imp_SetLastError
0x18000d5a6  mov     rdi, cs:phkResult
0x18000d5ad  mov     [rsi+8], rbp
0x18000d5b1  mov     rax, [rdi+8]
0x18000d5b5  inc     rax
0x18000d5b8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d5be  jnz     short loc_18000D5D2
0x18000d5c0  call    cs:__imp_GetLastError
0x18000d5c6  lea     r8, aFailedToCreate; "Failed to create policy change event"
0x18000d5cd  jmp     loc_18000D673
0x18000d5d2  lea     rdx, [rdi+18h]; pv
0x18000d5d6  mov     [rdi+20h], r14
0x18000d5da  xor     r8d, r8d; pcbe
0x18000d5dd  mov     [rdx], r15
0x18000d5e0  lea     rcx, PolicyChangeCallback; pfnwa
0x18000d5e7  call    cs:__imp_CreateThreadpoolWait
0x18000d5ed  mov     rsi, [rdi+10h]
0x18000d5f1  mov     rbp, rax
0x18000d5f4  test    rsi, rsi
0x18000d5f7  jz      short loc_18000D62E
0x18000d5f9  call    cs:__imp_GetLastError
0x18000d5ff  xor     r8d, r8d; pftTimeout
0x18000d602  xor     edx, edx; h
0x18000d604  mov     rcx, rsi; pwa
0x18000d607  mov     ebx, eax
0x18000d609  call    cs:__imp_SetThreadpoolWait
0x18000d60f  mov     edx, 1; fCancelPendingCallbacks
0x18000d614  mov     rcx, rsi; pwa
0x18000d617  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d61d  mov     rcx, rsi; pwa
0x18000d620  call    cs:__imp_CloseThreadpoolWait
0x18000d626  mov     ecx, ebx; dwErrCode
0x18000d628  call    cs:__imp_SetLastError
0x18000d62e  mov     rcx, cs:phkResult
0x18000d635  mov     [rdi+10h], rbp
0x18000d639  cmp     qword ptr [rcx+10h], 0
0x18000d63e  jnz     short loc_18000D64F
0x18000d640  call    cs:__imp_GetLastError
0x18000d646  lea     r8, aFailedToCreate_0; "Failed to create policy change threadpo"...
0x18000d64d  jmp     short loc_18000D673
0x18000d64f  mov     rcx, [rcx+8]; hEvent
0x18000d653  mov     edx, 1; bMachine
0x18000d658  call    cs:__imp_RegisterGPNotification
0x18000d65e  test    eax, eax
0x18000d660  jnz     loc_18000D716
0x18000d666  call    cs:__imp_GetLastError
0x18000d66c  lea     r8, aFailedToRegist_0; "Failed to register for group policy not"...
0x18000d673  mov     rcx, cs:phkResult
0x18000d67a  mov     edi, eax
0x18000d67c  add     rcx, 78h ; 'x'; this
0x18000d680  mov     edx, eax; unsigned int
0x18000d682  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000d687  test    edi, edi
0x18000d689  jz      loc_18000D747
0x18000d68f  mov     rsi, cs:phkResult
0x18000d696  lea     r14, [rsi+10h]
0x18000d69a  mov     rbp, [r14]
0x18000d69d  test    rbp, rbp
0x18000d6a0  jz      short loc_18000D6DE
0x18000d6a2  call    cs:__imp_GetLastError
0x18000d6a8  xor     r8d, r8d; pftTimeout
0x18000d6ab  xor     edx, edx; h
0x18000d6ad  mov     rcx, rbp; pwa
0x18000d6b0  mov     ebx, eax
0x18000d6b2  call    cs:__imp_SetThreadpoolWait
0x18000d6b8  mov     edx, 1; fCancelPendingCallbacks
0x18000d6bd  mov     rcx, rbp; pwa
0x18000d6c0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d6c6  mov     rcx, rbp; pwa
0x18000d6c9  call    cs:__imp_CloseThreadpoolWait
0x18000d6cf  mov     ecx, ebx; dwErrCode
0x18000d6d1  call    cs:__imp_SetLastError
0x18000d6d7  mov     rsi, cs:phkResult
0x18000d6de  mov     qword ptr [r14], 0
0x18000d6e5  mov     rbp, [rsi+8]
0x18000d6e9  lea     rax, [rbp-1]
0x18000d6ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d6f1  ja      short loc_18000D70C
0x18000d6f3  call    cs:__imp_GetLastError
0x18000d6f9  mov     rcx, rbp; hObject
0x18000d6fc  mov     ebx, eax
0x18000d6fe  call    cs:__imp_CloseHandle
0x18000d704  mov     ecx, ebx; dwErrCode
0x18000d706  call    cs:__imp_SetLastError
0x18000d70c  mov     qword ptr [rsi+8], 0
0x18000d714  jmp     short loc_18000D747
0x18000d716  mov     rcx, cs:phkResult
0x18000d71d  xor     r8d, r8d; pftTimeout
0x18000d720  xor     edi, edi
0x18000d722  mov     rdx, [rcx+8]; h
0x18000d726  mov     rcx, [rcx+10h]; pwa
0x18000d72a  call    cs:__imp_SetThreadpoolWait
0x18000d730  mov     rcx, cs:phkResult
0x18000d737  lea     rdx, aRegisteredForG; "Registered for group policy change noti"...
0x18000d73e  add     rcx, 78h ; 'x'; this
0x18000d742  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000d747  mov     eax, edi
0x18000d749  add     rsp, 28h
0x18000d74d  pop     r15
0x18000d74f  pop     r14
0x18000d751  pop     rdi
0x18000d752  pop     rsi
0x18000d753  pop     rbp
0x18000d754  pop     rbx
0x18000d755  retn
```
