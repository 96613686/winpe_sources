# CEfsTokenManager::CheckIsEdpCaller(int *)

- ea: `0x180066888`
- end: `0x180066967`
- name: `?CheckIsEdpCaller@CEfsTokenManager@@SAKPEAH@Z`
- size: `223`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180066d30`

## callees

- `0x180063698`
- `0x180066888`
- `0x1800d94e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800668c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800668c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800668bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800668bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800668a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800668a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066943`
- `ntdll!RtlNtStatusToDosError` at `0x180066909`
- `ntdll!RtlNtStatusToDosError` at `0x180066909`

## pseudocode

```c
__int64 __fastcall CEfsTokenManager::CheckIsEdpCaller(int *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  ULONG v4; // ebx
  void *v5; // rcx
  NTSTATUS EvaluationFlags; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v5 = TokenHandle;
    v9 = 0;
    *a1 = 0;
    EvaluationFlags = SrpGetEvaluationFlags(v5, &v9);
    if ( EvaluationFlags >= 0 )
    {
      v4 = 0;
      if ( (v9 & 1) != 0 )
      {
        *a1 = 1;
        goto LABEL_9;
      }
    }
    else
    {
      v4 = RtlNtStatusToDosError(EvaluationFlags);
    }
    if ( v4 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v4, 29, 231);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 1008 )
      v4 = 0;
    else
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 29, 227);
  }
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180066888  mov     [rsp+arg_10], rbx
0x18006688d  push    rdi
0x18006688e  sub     rsp, 30h
0x180066892  mov     rdi, rcx
0x180066895  mov     [rsp+38h+TokenHandle], 0
0x18006689e  mov     dword ptr [rcx], 0
0x1800668a4  call    cs:__imp_GetCurrentThread
0x1800668aa  mov     edx, 8; DesiredAccess
0x1800668af  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800668b4  mov     rcx, rax; ThreadHandle
0x1800668b7  lea     r8d, [rdx-7]; OpenAsSelf
0x1800668bb  call    cs:__imp_OpenThreadToken
0x1800668c1  test    eax, eax
0x1800668c3  jnz     short loc_1800668E5
0x1800668c5  call    cs:__imp_GetLastError
0x1800668cb  mov     ebx, eax
0x1800668cd  cmp     eax, 3F0h
0x1800668d2  jnz     short loc_1800668D8
0x1800668d4  xor     ebx, ebx
0x1800668d6  jmp     short loc_180066939
0x1800668d8  mov     [rsp+38h+var_18], 1E3h
0x1800668e0  mov     r8d, eax
0x1800668e3  jmp     short loc_180066920
0x1800668e5  mov     rcx, [rsp+38h+TokenHandle]
0x1800668ea  lea     rdx, [rsp+38h+arg_8]
0x1800668ef  mov     [rsp+38h+arg_8], 0
0x1800668f8  mov     dword ptr [rdi], 0
0x1800668fe  call    SrpGetEvaluationFlags
0x180066903  test    eax, eax
0x180066905  jns     short loc_180066956
0x180066907  mov     ecx, eax; Status
0x180066909  call    cs:__imp_RtlNtStatusToDosError
0x18006690f  mov     ebx, eax
0x180066911  test    ebx, ebx
0x180066913  jz      short loc_180066939
0x180066915  mov     [rsp+38h+var_18], 1E7h
0x18006691d  mov     r8d, ebx
0x180066920  mov     rcx, cs:g_hPublisher
0x180066927  lea     rdx, EFS_API_ERROR
0x18006692e  mov     r9d, 1Dh
0x180066934  call    fnEfsLogTrace1
0x180066939  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18006693e  test    rcx, rcx
0x180066941  jz      short loc_180066949
0x180066943  call    cs:__imp_CloseHandle
0x180066949  mov     eax, ebx
0x18006694b  mov     rbx, [rsp+38h+arg_10]
0x180066950  add     rsp, 30h
0x180066954  pop     rdi
0x180066955  retn
0x180066956  xor     ebx, ebx
0x180066958  test    byte ptr [rsp+38h+arg_8], 1
0x18006695d  jz      short loc_180066911
0x18006695f  mov     dword ptr [rdi], 1
0x180066965  jmp     short loc_180066939
```
