# ChangePKHelper::RestartSystem(int)

- ea: `0x18000d7b4`
- end: `0x18000d953`
- name: `?RestartSystem@ChangePKHelper@@SAJH@Z`
- size: `415`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800170b0`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000b884`
- `0x18000d7b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d920`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d7ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d7ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d7ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d936`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d840`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000d840`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000d877`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000d877`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000d8d0`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000d8d0`

## string_xrefs

- `0x18000d839`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall ChangePKHelper::RestartSystem(int a1)
{
  LPWSTR v1; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // edi
  __int64 v6; // rcx
  int v7; // eax
  signed int v8; // eax
  HANDLE ProcessHeap; // rax
  LPWSTR lpMessage; // [rsp+30h] [rbp-38h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-20h] BYREF

  Luid = 0;
  v1 = 0;
  TokenHandle = 0;
  NewState = 0;
  lpMessage = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x200E8u, &TokenHandle)
    || !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid)
    || (NewState.Privileges[0].Luid = Luid,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = 2,
        !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v6 = v5;
    goto LABEL_7;
  }
  v7 = STRAPI_LoadFromResource(0x55u, &lpMessage);
  v5 = v7;
  if ( v7 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
    v1 = lpMessage;
    goto LABEL_20;
  }
  v1 = lpMessage;
  if ( !InitiateSystemShutdownExW(0, lpMessage, a1 == 0 ? 0x1C20 : 0, 1, 1, 3u) )
  {
    v8 = GetLastError();
    if ( v8 != 1115 )
    {
      if ( v8 )
      {
        if ( v8 > 0 )
        {
          v5 = (unsigned __int16)v8 | 0x80070000;
          v8 = v5;
        }
        else
        {
          v5 = v8;
        }
        v6 = (unsigned int)v8;
LABEL_7:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
        goto LABEL_20;
      }
      v5 = 0;
    }
  }
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18000d7b4  push    rbp
0x18000d7b6  push    rbx
0x18000d7b7  push    rsi
0x18000d7b8  push    rdi
0x18000d7b9  mov     rbp, rsp
0x18000d7bc  sub     rsp, 68h
0x18000d7c0  mov     rax, cs:__security_cookie
0x18000d7c7  xor     rax, rsp
0x18000d7ca  mov     [rbp+var_10], rax
0x18000d7ce  xorps   xmm0, xmm0
0x18000d7d1  mov     qword ptr [rbp+Luid.LowPart], 0
0x18000d7d9  xor     ebx, ebx
0x18000d7db  mov     [rbp+TokenHandle], 0
0x18000d7e3  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000d7e7  mov     [rbp+lpMessage], rbx
0x18000d7eb  mov     esi, ecx
0x18000d7ed  call    cs:__imp_GetCurrentProcess
0x18000d7f3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000d7f7  mov     edx, 200E8h; DesiredAccess
0x18000d7fc  mov     rcx, rax; ProcessHandle
0x18000d7ff  call    cs:__imp_OpenProcessToken
0x18000d805  test    eax, eax
0x18000d807  jnz     short loc_18000D833
0x18000d809  call    cs:__imp_GetLastError
0x18000d80f  mov     edi, eax
0x18000d811  test    eax, eax
0x18000d813  jnz     short loc_18000D81C
0x18000d815  mov     edi, 80004005h
0x18000d81a  jmp     short loc_18000D827
0x18000d81c  jle     short loc_18000D827
0x18000d81e  movzx   edi, ax
0x18000d821  or      edi, 80070000h
0x18000d827  mov     ecx, edi
0x18000d829  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000d82e  jmp     loc_18000D905
0x18000d833  lea     r8, [rbp+Luid]; lpLuid
0x18000d837  xor     ecx, ecx; lpSystemName
0x18000d839  lea     rdx, Name; "SeShutdownPrivilege"
0x18000d840  call    cs:__imp_LookupPrivilegeValueW
0x18000d846  test    eax, eax
0x18000d848  jz      short loc_18000D809
0x18000d84a  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18000d84e  lea     r8, [rbp+NewState]; NewState
0x18000d852  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000d856  xor     r9d, r9d; BufferLength
0x18000d859  mov     [rsp+68h+ReturnLength], rbx; ReturnLength
0x18000d85e  xor     edx, edx; DisableAllPrivileges
0x18000d860  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18000d864  mov     [rbp+NewState.PrivilegeCount], 1
0x18000d86b  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000d872  mov     [rsp+68h+PreviousState], rbx; PreviousState
0x18000d877  call    cs:__imp_AdjustTokenPrivileges
0x18000d87d  test    eax, eax
0x18000d87f  jz      short loc_18000D809
0x18000d881  lea     rdx, [rbp+lpMessage]; unsigned __int16 **
0x18000d885  mov     ecx, 55h ; 'U'; unsigned int
0x18000d88a  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x18000d88f  mov     edi, eax
0x18000d891  test    eax, eax
0x18000d893  jns     short loc_18000D8A2
0x18000d895  mov     ecx, eax
0x18000d897  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000d89c  mov     rbx, [rbp+lpMessage]
0x18000d8a0  jmp     short loc_18000D905
0x18000d8a2  mov     rbx, [rbp+lpMessage]
0x18000d8a6  neg     esi
0x18000d8a8  mov     dword ptr [rsp+68h+ReturnLength], 3; dwReason
0x18000d8b0  mov     r9d, 1; bForceAppsClosed
0x18000d8b6  sbb     r8d, r8d
0x18000d8b9  mov     dword ptr [rsp+68h+PreviousState], 1; bRebootAfterShutdown
0x18000d8c1  not     r8d
0x18000d8c4  mov     rdx, rbx; lpMessage
0x18000d8c7  and     r8d, 1C20h; dwTimeout
0x18000d8ce  xor     ecx, ecx; lpMachineName
0x18000d8d0  call    cs:__imp_InitiateSystemShutdownExW
0x18000d8d6  test    eax, eax
0x18000d8d8  jnz     short loc_18000D905
0x18000d8da  call    cs:__imp_GetLastError
0x18000d8e0  cmp     eax, 45Bh
0x18000d8e5  jz      short loc_18000D905
0x18000d8e7  test    eax, eax
0x18000d8e9  jz      short loc_18000D903
0x18000d8eb  jg      short loc_18000D8F1
0x18000d8ed  mov     edi, eax
0x18000d8ef  jmp     short loc_18000D8FC
0x18000d8f1  movzx   edi, ax
0x18000d8f4  or      edi, 80070000h
0x18000d8fa  mov     eax, edi
0x18000d8fc  mov     ecx, eax
0x18000d8fe  jmp     loc_18000D829
0x18000d903  xor     edi, edi
0x18000d905  mov     ecx, edi
0x18000d907  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000d90c  test    rbx, rbx
0x18000d90f  jz      short loc_18000D92D
0x18000d911  call    cs:__imp_GetProcessHeap
0x18000d917  lea     r8, [rbx-4]; lpMem
0x18000d91b  xor     edx, edx; dwFlags
0x18000d91d  mov     rcx, rax; hHeap
0x18000d920  call    cs:__imp_HeapFree
0x18000d926  xor     ecx, ecx
0x18000d928  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000d92d  mov     rcx, [rbp+TokenHandle]; hObject
0x18000d931  test    rcx, rcx
0x18000d934  jz      short loc_18000D93C
0x18000d936  call    cs:__imp_CloseHandle
0x18000d93c  mov     eax, edi
0x18000d93e  mov     rcx, [rbp+var_10]
0x18000d942  xor     rcx, rsp; StackCookie
0x18000d945  call    __security_check_cookie
0x18000d94a  add     rsp, 68h
0x18000d94e  pop     rdi
0x18000d94f  pop     rsi
0x18000d950  pop     rbx
0x18000d951  pop     rbp
0x18000d952  retn
```
