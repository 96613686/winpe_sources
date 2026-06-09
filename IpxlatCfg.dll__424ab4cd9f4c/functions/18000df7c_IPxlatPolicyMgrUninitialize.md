# IPxlatPolicyMgrUninitialize

- ea: `0x18000df7c`
- end: `0x18000e17a`
- name: `IPxlatPolicyMgrUninitialize`
- size: `510`
- prototype: `void()`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000b250`
- `0x18000f4f8`

## callees

- `0x180002110`
- `0x18000d040`
- `0x18000df7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e00a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e08e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e00a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e08e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e02a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e02a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e123`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e123`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000dfca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e04e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000dfca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e04e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000dfc1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e045`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000dfc1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000e045`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dfb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e03a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dfb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e03a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0ff`

## pseudocode

```c
void IPxlatPolicyMgrUninitialize()
{
  PHKEY v0; // rdx
  PHKEY v1; // rsi
  struct _TP_WAIT *v2; // rdi
  DWORD LastError; // ebx
  _QWORD *v4; // rdi
  HKEY v5; // rsi
  DWORD v6; // ebx
  _QWORD *v7; // rsi
  struct _TP_WAIT *v8; // rdi
  DWORD v9; // ebx
  _QWORD *v10; // rsi
  HKEY v11; // rdi
  DWORD v12; // ebx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  PHKEY v14; // rbx
  PHKEY v15; // rsi
  HKEY v16; // rbp
  DWORD v17; // ebx
  _QWORD *v18; // rsi
  HKEY v19; // rbp
  DWORD v20; // ebx

  v0 = phkResult;
  if ( phkResult )
  {
    v1 = phkResult + 2;
    v2 = (struct _TP_WAIT *)phkResult[2];
    if ( v2 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v2, 0, 0);
      WaitForThreadpoolWaitCallbacks(v2, 1);
      CloseThreadpoolWait(v2);
      SetLastError(LastError);
      v0 = phkResult;
    }
    v4 = v0 + 1;
    *v1 = 0;
    v5 = v0[1];
    if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v6 = GetLastError();
      CloseHandle(v5);
      SetLastError(v6);
      v0 = phkResult;
    }
    v7 = v0 + 7;
    *v4 = 0;
    v8 = (struct _TP_WAIT *)v0[7];
    if ( v8 )
    {
      v9 = GetLastError();
      SetThreadpoolWait(v8, 0, 0);
      WaitForThreadpoolWaitCallbacks(v8, 1);
      CloseThreadpoolWait(v8);
      SetLastError(v9);
      v0 = phkResult;
    }
    *v7 = 0;
    v10 = v0 + 6;
    v11 = v0[6];
    if ( (unsigned __int64)v11 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v12 = GetLastError();
      CloseHandle(v11);
      SetLastError(v12);
      v0 = phkResult;
    }
    v13 = (struct _RTL_CRITICAL_SECTION *)(v0 + 10);
    *v10 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)v0 + 2);
    v14 = phkResult;
    v15 = phkResult;
    v16 = *phkResult;
    if ( *phkResult )
    {
      v17 = GetLastError();
      RegCloseKey(v16);
      SetLastError(v17);
      v14 = phkResult;
    }
    *v15 = 0;
    v18 = v14 + 5;
    v19 = v14[5];
    if ( v19 )
    {
      v20 = GetLastError();
      RegCloseKey(v19);
      SetLastError(v20);
      v14 = phkResult;
    }
    *v18 = 0;
    if ( v13 )
    {
      LeaveCriticalSection(v13);
      v14 = phkResult;
    }
    v14[15] = 0;
    *((_OWORD *)v14 + 8) = 0;
    *((_OWORD *)v14 + 9) = 0;
    if ( v14 )
    {
      IPxlatPolicyMgrGlobals::~IPxlatPolicyMgrGlobals((IPxlatPolicyMgrGlobals *)v14);
      operator delete(v14);
    }
    phkResult = 0;
  }
}

```

## disassembly

```asm
0x18000df7c  push    rbx
0x18000df7e  push    rbp
0x18000df7f  push    rsi
0x18000df80  push    rdi
0x18000df81  sub     rsp, 28h
0x18000df85  mov     rdx, cs:phkResult
0x18000df8c  test    rdx, rdx
0x18000df8f  jz      loc_18000E171
0x18000df95  lea     rsi, [rdx+10h]
0x18000df99  mov     ebp, 1
0x18000df9e  mov     rdi, [rsi]
0x18000dfa1  test    rdi, rdi
0x18000dfa4  jz      short loc_18000DFDF
0x18000dfa6  call    cs:__imp_GetLastError
0x18000dfac  xor     r8d, r8d; pftTimeout
0x18000dfaf  xor     edx, edx; h
0x18000dfb1  mov     rcx, rdi; pwa
0x18000dfb4  mov     ebx, eax
0x18000dfb6  call    cs:__imp_SetThreadpoolWait
0x18000dfbc  mov     edx, ebp; fCancelPendingCallbacks
0x18000dfbe  mov     rcx, rdi; pwa
0x18000dfc1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000dfc7  mov     rcx, rdi; pwa
0x18000dfca  call    cs:__imp_CloseThreadpoolWait
0x18000dfd0  mov     ecx, ebx; dwErrCode
0x18000dfd2  call    cs:__imp_SetLastError
0x18000dfd8  mov     rdx, cs:phkResult
0x18000dfdf  lea     rdi, [rdx+8]
0x18000dfe3  mov     qword ptr [rsi], 0
0x18000dfea  mov     rsi, [rdi]
0x18000dfed  lea     rax, [rsi-1]
0x18000dff1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dff5  ja      short loc_18000E017
0x18000dff7  call    cs:__imp_GetLastError
0x18000dffd  mov     rcx, rsi; hObject
0x18000e000  mov     ebx, eax
0x18000e002  call    cs:__imp_CloseHandle
0x18000e008  mov     ecx, ebx; dwErrCode
0x18000e00a  call    cs:__imp_SetLastError
0x18000e010  mov     rdx, cs:phkResult
0x18000e017  lea     rsi, [rdx+38h]
0x18000e01b  mov     qword ptr [rdi], 0
0x18000e022  mov     rdi, [rsi]
0x18000e025  test    rdi, rdi
0x18000e028  jz      short loc_18000E063
0x18000e02a  call    cs:__imp_GetLastError
0x18000e030  xor     r8d, r8d; pftTimeout
0x18000e033  xor     edx, edx; h
0x18000e035  mov     rcx, rdi; pwa
0x18000e038  mov     ebx, eax
0x18000e03a  call    cs:__imp_SetThreadpoolWait
0x18000e040  mov     edx, ebp; fCancelPendingCallbacks
0x18000e042  mov     rcx, rdi; pwa
0x18000e045  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000e04b  mov     rcx, rdi; pwa
0x18000e04e  call    cs:__imp_CloseThreadpoolWait
0x18000e054  mov     ecx, ebx; dwErrCode
0x18000e056  call    cs:__imp_SetLastError
0x18000e05c  mov     rdx, cs:phkResult
0x18000e063  mov     qword ptr [rsi], 0
0x18000e06a  lea     rsi, [rdx+30h]
0x18000e06e  mov     rdi, [rsi]
0x18000e071  lea     rax, [rdi-1]
0x18000e075  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e079  ja      short loc_18000E09B
0x18000e07b  call    cs:__imp_GetLastError
0x18000e081  mov     rcx, rdi; hObject
0x18000e084  mov     ebx, eax
0x18000e086  call    cs:__imp_CloseHandle
0x18000e08c  mov     ecx, ebx; dwErrCode
0x18000e08e  call    cs:__imp_SetLastError
0x18000e094  mov     rdx, cs:phkResult
0x18000e09b  lea     rdi, [rdx+50h]
0x18000e09f  mov     qword ptr [rsi], 0
0x18000e0a6  mov     rcx, rdi; lpCriticalSection
0x18000e0a9  call    cs:__imp_EnterCriticalSection
0x18000e0af  mov     rbx, cs:phkResult
0x18000e0b6  mov     rsi, rbx
0x18000e0b9  mov     rbp, [rbx]
0x18000e0bc  test    rbp, rbp
0x18000e0bf  jz      short loc_18000E0E1
0x18000e0c1  call    cs:__imp_GetLastError
0x18000e0c7  mov     rcx, rbp; hKey
0x18000e0ca  mov     ebx, eax
0x18000e0cc  call    cs:__imp_RegCloseKey
0x18000e0d2  mov     ecx, ebx; dwErrCode
0x18000e0d4  call    cs:__imp_SetLastError
0x18000e0da  mov     rbx, cs:phkResult
0x18000e0e1  mov     qword ptr [rsi], 0
0x18000e0e8  lea     rsi, [rbx+28h]
0x18000e0ec  mov     rbp, [rsi]
0x18000e0ef  test    rbp, rbp
0x18000e0f2  jz      short loc_18000E114
0x18000e0f4  call    cs:__imp_GetLastError
0x18000e0fa  mov     rcx, rbp; hKey
0x18000e0fd  mov     ebx, eax
0x18000e0ff  call    cs:__imp_RegCloseKey
0x18000e105  mov     ecx, ebx; dwErrCode
0x18000e107  call    cs:__imp_SetLastError
0x18000e10d  mov     rbx, cs:phkResult
0x18000e114  mov     qword ptr [rsi], 0
0x18000e11b  test    rdi, rdi
0x18000e11e  jz      short loc_18000E130
0x18000e120  mov     rcx, rdi; lpCriticalSection
0x18000e123  call    cs:__imp_LeaveCriticalSection
0x18000e129  mov     rbx, cs:phkResult
0x18000e130  mov     qword ptr [rbx+78h], 0
0x18000e138  xorps   xmm0, xmm0
0x18000e13b  xorps   xmm1, xmm1
0x18000e13e  movups  xmmword ptr [rbx+80h], xmm0
0x18000e145  movups  xmmword ptr [rbx+90h], xmm1
0x18000e14c  test    rbx, rbx
0x18000e14f  jz      short loc_18000E166
0x18000e151  mov     rcx, rbx; this
0x18000e154  call    ??1IPxlatPolicyMgrGlobals@@QEAA@XZ; IPxlatPolicyMgrGlobals::~IPxlatPolicyMgrGlobals(void)
0x18000e159  mov     edx, 0A0h; unsigned __int64
0x18000e15e  mov     rcx, rbx; void *
0x18000e161  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e166  mov     cs:phkResult, 0
0x18000e171  add     rsp, 28h
0x18000e175  pop     rdi
0x18000e176  pop     rsi
0x18000e177  pop     rbp
0x18000e178  pop     rbx
0x18000e179  retn
```
