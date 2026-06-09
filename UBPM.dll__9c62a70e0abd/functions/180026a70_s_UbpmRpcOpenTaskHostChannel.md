# s_UbpmRpcOpenTaskHostChannel

- ea: `0x180026a70`
- end: `0x180026e74`
- name: `s_UbpmRpcOpenTaskHostChannel`
- size: `1028`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180026a70`
- `0x1800351ec`
- `0x18003ee1c`
- `0x18003ee78`
- `0x18003f5b4`
- `0x180041010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026be0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026be0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026b5a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026b5a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026c52`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026c52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b66`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180026ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180026ad0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026b21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026c15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ca7`
- `RPCRT4!RpcImpersonateClient` at `0x180026ae9`
- `RPCRT4!RpcImpersonateClient` at `0x180026ae9`
- `RPCRT4!RpcRevertToSelf` at `0x180026b35`
- `RPCRT4!RpcRevertToSelf` at `0x180026b35`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcOpenTaskHostChannel(__int64 a1, int a2, void ***a3)
{
  DWORD v5; // eax
  DWORD v6; // ebx
  DWORD ProcessId; // r14d
  HANDLE CurrentThread; // rax
  __int64 v9; // r8
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  void *v12; // r12
  void **v13; // rbx
  PVOID *v14; // rcx
  int v15; // eax
  void **v16; // rdi
  __int64 v17; // rdx
  DWORD v19; // eax
  DWORD LastError; // eax
  signed __int32 v21[8]; // [rsp+0h] [rbp-78h] BYREF
  HANDLE Process[2]; // [rsp+30h] [rbp-48h] BYREF
  WINBOOL IsMember; // [rsp+90h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+20h] BYREF

  TokenHandle = 0;
  Process[0] = 0;
  if ( a3 )
    *a3 = 0;
  v5 = ((__int64 (__fastcall *)(_QWORD, __int64, HANDLE *))s_pfnI_RpcOpenClientProcess)(0, 4096, Process);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v5);
    goto LABEL_25;
  }
  ProcessId = GetProcessId(Process[0]);
  if ( !ProcessId )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    goto LABEL_25;
  }
  v6 = RpcImpersonateClient(0);
  if ( v6 )
    goto LABEL_25;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    v6 = GetLastError();
  RpcRevertToSelf();
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v9, ProcessId, v6);
    goto LABEL_25;
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  CurrentThreadId = GetCurrentThreadId();
  v12 = TokenHandle;
  v13 = (void **)g_leTaskHostContextListHead;
  dword_180050018 = CurrentThreadId;
  IsMember = 0;
LABEL_10:
  while ( 2 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    do
    {
      while ( 1 )
      {
        if ( v13 == (void **)&g_leTaskHostContextListHead )
        {
          v6 = 1168;
LABEL_39:
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
            WPP_SF_Ld(v14[2], 21, v11, ProcessId, 1168);
          goto LABEL_24;
        }
        v15 = *((unsigned __int8 *)v13 + 96);
        v16 = v13 - 1;
        v13 = (void **)*v13;
        if ( (v15 & 0x84) == 0 )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, v11, v16, v15);
          goto LABEL_10;
        }
      }
    }
    while ( *((_DWORD *)v16 + 8) != ProcessId || a2 && (v15 & 9) != 1 );
    if ( !CheckTokenMembership(v12, v16[22], &IsMember) )
    {
      v6 = 1168;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_24;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v19);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_39;
    }
    if ( IsMember != 1 )
      continue;
    break;
  }
  _InterlockedIncrement64((volatile signed __int64 *)v16 + 12);
  if ( a2 )
  {
    *((_BYTE *)v16 + 104) |= 2u;
    _InterlockedOr(v21, 0);
    SetEvent(v16[6]);
  }
  if ( a3 )
    *a3 = v16;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Lqi(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v11, ProcessId, v16, v16[12]);
LABEL_24:
  dword_180050018 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
LABEL_25:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Process[0] )
    CloseHandle(Process[0]);
  return v6;
}

```

## disassembly

```asm
0x180026a70  mov     rax, rsp
0x180026a73  push    rbx
0x180026a74  sub     rsp, 70h
0x180026a78  mov     [rax-10h], rsi
0x180026a7c  mov     rsi, r8
0x180026a7f  mov     [rax-18h], rdi
0x180026a83  xor     edi, edi
0x180026a85  mov     [rax-38h], r15
0x180026a89  mov     r15d, edx
0x180026a8c  mov     [rax+20h], rdi
0x180026a90  mov     [rax-48h], rdi
0x180026a94  test    r8, r8
0x180026a97  jz      short loc_180026A9C
0x180026a99  mov     [r8], rdi
0x180026a9c  mov     rax, cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x180026aa3  lea     r8, [rsp+78h+Process]
0x180026aa8  mov     edx, 1000h
0x180026aad  mov     [rsp+78h+arg_0], rbp
0x180026ab5  xor     ecx, ecx
0x180026ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026abc  mov     ebx, eax
0x180026abe  test    eax, eax
0x180026ac0  jnz     loc_180026DB8
0x180026ac6  mov     rcx, [rsp+78h+Process]; Process
0x180026acb  mov     [rsp+78h+var_30], r14
0x180026ad0  call    cs:__imp_GetProcessId
0x180026ad7  nop     dword ptr [rax+rax+00h]
0x180026adc  mov     r14d, eax
0x180026adf  test    eax, eax
0x180026ae1  jz      loc_180026DF6
0x180026ae7  xor     ecx, ecx; BindingHandle
0x180026ae9  call    cs:__imp_RpcImpersonateClient
0x180026af0  nop     dword ptr [rax+rax+00h]
0x180026af5  mov     ebx, eax
0x180026af7  test    eax, eax
0x180026af9  jnz     loc_180026C68
0x180026aff  call    cs:__imp_GetCurrentThread
0x180026b06  nop     dword ptr [rax+rax+00h]
0x180026b0b  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180026b13  mov     edx, 8; DesiredAccess
0x180026b18  mov     rcx, rax; ThreadHandle
0x180026b1b  mov     r8d, 1; OpenAsSelf
0x180026b21  call    cs:__imp_OpenThreadToken
0x180026b28  nop     dword ptr [rax+rax+00h]
0x180026b2d  test    eax, eax
0x180026b2f  jz      loc_180026E42
0x180026b35  call    cs:__imp_RpcRevertToSelf
0x180026b3c  nop     dword ptr [rax+rax+00h]
0x180026b41  test    ebx, ebx
0x180026b43  jnz     loc_180026D7D
0x180026b49  mov     [rsp+78h+var_20], r12
0x180026b4e  lea     rcx, g_TaskHostContextListLock
0x180026b55  mov     [rsp+78h+var_28], r13
0x180026b5a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180026b61  nop     dword ptr [rax+rax+00h]
0x180026b66  call    cs:__imp_GetCurrentThreadId
0x180026b6d  nop     dword ptr [rax+rax+00h]
0x180026b72  mov     r12, [rsp+78h+TokenHandle]
0x180026b7a  lea     rbp, WPP_GLOBAL_Control
0x180026b81  mov     rbx, cs:g_leTaskHostContextListHead
0x180026b88  lea     r13, g_leTaskHostContextListHead
0x180026b8f  mov     cs:dword_180050018, eax
0x180026b95  mov     [rsp+78h+IsMember], edi
0x180026b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ba3  cmp     rbx, r13
0x180026ba6  jz      loc_180026CE9
0x180026bac  movzx   eax, byte ptr [rbx+60h]
0x180026bb0  lea     rdi, [rbx-8]
0x180026bb4  mov     rbx, [rbx]
0x180026bb7  test    al, 84h
0x180026bb9  jnz     loc_180026CBC
0x180026bbf  cmp     [rdi+20h], r14d
0x180026bc3  jnz     short loc_180026BA3
0x180026bc5  test    r15d, r15d
0x180026bc8  jnz     loc_180026CF2
0x180026bce  mov     rdx, [rdi+0B0h]; SidToCheck
0x180026bd5  lea     r8, [rsp+78h+IsMember]; IsMember
0x180026bdd  mov     rcx, r12; TokenHandle
0x180026be0  call    cs:__imp_CheckTokenMembership
0x180026be7  nop     dword ptr [rax+rax+00h]
0x180026bec  test    eax, eax
0x180026bee  jz      loc_180026D01
0x180026bf4  cmp     [rsp+78h+IsMember], 1
0x180026bfc  jnz     short loc_180026B9C
0x180026bfe  lock inc qword ptr [rdi+60h]
0x180026c03  test    r15d, r15d
0x180026c06  jz      short loc_180026C21
0x180026c08  or      byte ptr [rdi+68h], 2
0x180026c0c  lock or [rsp+78h+var_78], 0
0x180026c11  mov     rcx, [rdi+30h]; hEvent
0x180026c15  call    cs:__imp_SetEvent
0x180026c1c  nop     dword ptr [rax+rax+00h]
0x180026c21  test    rsi, rsi
0x180026c24  jz      short loc_180026C29
0x180026c26  mov     [rsi], rdi
0x180026c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c30  xor     ebx, ebx
0x180026c32  cmp     rcx, rbp
0x180026c35  jz      short loc_180026C41
0x180026c37  test    byte ptr [rcx+1Ch], 80h
0x180026c3b  jnz     loc_180026E55
0x180026c41  lea     rcx, g_TaskHostContextListLock
0x180026c48  mov     cs:dword_180050018, 0
0x180026c52  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180026c59  nop     dword ptr [rax+rax+00h]
0x180026c5e  mov     r13, [rsp+78h+var_28]
0x180026c63  mov     r12, [rsp+78h+var_20]
0x180026c68  mov     r14, [rsp+78h+var_30]
0x180026c6d  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180026c75  mov     r15, [rsp+78h+var_38]
0x180026c7a  mov     rdi, [rsp+78h+var_18]
0x180026c7f  mov     rsi, [rsp+78h+var_10]
0x180026c84  mov     rbp, [rsp+78h+arg_0]
0x180026c8c  test    rcx, rcx
0x180026c8f  jz      short loc_180026C9D
0x180026c91  call    cs:__imp_CloseHandle
0x180026c98  nop     dword ptr [rax+rax+00h]
0x180026c9d  mov     rcx, [rsp+78h+Process]; hObject
0x180026ca2  test    rcx, rcx
0x180026ca5  jz      short loc_180026CB3
0x180026ca7  call    cs:__imp_CloseHandle
0x180026cae  nop     dword ptr [rax+rax+00h]
0x180026cb3  mov     eax, ebx
0x180026cb5  add     rsp, 70h
0x180026cb9  pop     rbx
0x180026cba  retn
0x180026cbc  cmp     rcx, rbp
0x180026cbf  jz      loc_180026BA3
0x180026cc5  test    byte ptr [rcx+1Ch], 2
0x180026cc9  jz      loc_180026BA3
0x180026ccf  mov     rcx, [rcx+10h]
0x180026cd3  mov     edx, 59h ; 'Y'
0x180026cd8  mov     r9, rdi
0x180026cdb  mov     dword ptr [rsp+78h+var_58], eax
0x180026cdf  call    WPP_SF_qd
0x180026ce4  jmp     loc_180026B9C
0x180026ce9  mov     ebx, 490h
0x180026cee  mov     edi, ebx
0x180026cf0  jmp     short loc_180026D50
0x180026cf2  and     al, 9
0x180026cf4  cmp     al, 1
0x180026cf6  jnz     loc_180026BA3
0x180026cfc  jmp     loc_180026BCE
0x180026d01  mov     ebx, 490h
0x180026d06  mov     edi, ebx
0x180026d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d0f  cmp     rcx, rbp
0x180026d12  jz      loc_180026C41
0x180026d18  test    byte ptr [rcx+1Ch], 1
0x180026d1c  jz      short loc_180026D50
0x180026d1e  call    cs:__imp_GetLastError
0x180026d25  nop     dword ptr [rax+rax+00h]
0x180026d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d31  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180026d38  mov     edx, 5Ah ; 'Z'
0x180026d3d  mov     r9d, eax
0x180026d40  mov     rcx, [rcx+10h]
0x180026d44  call    WPP_SF_d
0x180026d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d50  cmp     rcx, rbp
0x180026d53  jz      loc_180026C41
0x180026d59  test    byte ptr [rcx+1Ch], 1
0x180026d5d  jz      loc_180026C41
0x180026d63  mov     rcx, [rcx+10h]
0x180026d67  mov     edx, 15h
0x180026d6c  mov     r9d, r14d
0x180026d6f  mov     dword ptr [rsp+78h+var_58], edi
0x180026d73  call    WPP_SF_Ld
0x180026d78  jmp     loc_180026C41
0x180026d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d84  lea     rbp, WPP_GLOBAL_Control
0x180026d8b  cmp     rcx, rbp
0x180026d8e  jz      loc_180026C68
0x180026d94  test    byte ptr [rcx+1Ch], 1
0x180026d98  jz      loc_180026C68
0x180026d9e  mov     rcx, [rcx+10h]
0x180026da2  mov     edx, 14h
0x180026da7  mov     r9d, r14d
0x180026daa  mov     dword ptr [rsp+78h+var_58], ebx
0x180026dae  call    WPP_SF_Ld
0x180026db3  jmp     loc_180026C68
0x180026db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dbf  lea     rbp, WPP_GLOBAL_Control
0x180026dc6  cmp     rcx, rbp
0x180026dc9  jz      loc_180026C6D
0x180026dcf  test    byte ptr [rcx+1Ch], 1
0x180026dd3  jz      loc_180026C6D
0x180026dd9  mov     rcx, [rcx+10h]
0x180026ddd  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180026de4  mov     edx, 12h
0x180026de9  mov     r9d, eax
0x180026dec  call    WPP_SF_d
0x180026df1  jmp     loc_180026C6D
0x180026df6  call    cs:__imp_GetLastError
0x180026dfd  nop     dword ptr [rax+rax+00h]
0x180026e02  mov     ebx, eax
0x180026e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e0b  lea     rbp, WPP_GLOBAL_Control
0x180026e12  cmp     rcx, rbp
0x180026e15  jz      loc_180026C68
0x180026e1b  test    byte ptr [rcx+1Ch], 1
0x180026e1f  jz      loc_180026C68
0x180026e25  mov     rcx, [rcx+10h]
0x180026e29  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180026e30  mov     edx, 13h
0x180026e35  mov     r9d, eax
0x180026e38  call    WPP_SF_d
0x180026e3d  jmp     loc_180026C68
0x180026e42  call    cs:__imp_GetLastError
0x180026e49  nop     dword ptr [rax+rax+00h]
0x180026e4e  mov     ebx, eax
0x180026e50  jmp     loc_180026B35
0x180026e55  mov     rax, [rdi+60h]
0x180026e59  mov     r9d, r14d
0x180026e5c  mov     rcx, [rcx+10h]
0x180026e60  mov     [rsp+78h+var_50], rax
0x180026e65  mov     [rsp+78h+var_58], rdi
0x180026e6a  call    WPP_SF_Lqi
0x180026e6f  jmp     loc_180026C41
```
