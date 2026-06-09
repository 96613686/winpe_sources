# UbpmpTaskHostChannelInterfaceSecurityCb

- ea: `0x180029590`
- end: `0x180029816`
- name: `UbpmpTaskHostChannelInterfaceSecurityCb`
- size: `646`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180029590`
- `0x1800351ec`
- `0x18003ecfc`
- `0x18003f5b4`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800296c7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800296c7`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002971d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002971d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002967e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002967e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029630`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029630`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002964a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002964a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002979f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002979f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029737`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800295db`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800295db`
- `RPCRT4!RpcImpersonateClient` at `0x18002961a`
- `RPCRT4!RpcImpersonateClient` at `0x18002961a`
- `RPCRT4!RpcRevertToSelf` at `0x18002965e`
- `RPCRT4!RpcRevertToSelf` at `0x1800297ad`
- `RPCRT4!RpcRevertToSelf` at `0x18002965e`
- `RPCRT4!RpcRevertToSelf` at `0x1800297ad`

## pseudocode

```c
__int64 __fastcall UbpmpTaskHostChannelInterfaceSecurityCb(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // eax
  __int64 v4; // r8
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  void *v7; // r15
  int v8; // r14d
  __int64 v9; // r8
  _UNKNOWN **v10; // rsi
  _UNKNOWN **v11; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  DWORD v16; // eax
  WINBOOL IsMember; // [rsp+30h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-71h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v20[36]; // [rsp+44h] [rbp-65h] BYREF
  int v21; // [rsp+68h] [rbp-41h]
  int v22; // [rsp+6Ch] [rbp-3Dh]
  int v23; // [rsp+70h] [rbp-39h]
  int v24; // [rsp+78h] [rbp-31h]

  memset_0(v20, 0, 0x74u);
  TokenHandle = 0;
  RpcCallAttributes = 3;
  v3 = RpcServerInqCallAttributesW(Context, &RpcCallAttributes);
  LastError = v3;
  if ( v3 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v14 = 129;
    v15 = v3;
LABEL_26:
    WPP_SF_D(v13[2], v14, v4, v15);
    goto LABEL_19;
  }
  if ( v24 != 3 || v23 || v21 != 6 || v22 != 10 )
  {
LABEL_22:
    LastError = 5;
    goto LABEL_19;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_19;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    RpcRevertToSelf();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v14 = 130;
    v15 = LastError;
    goto LABEL_26;
  }
  RpcRevertToSelf();
  v7 = TokenHandle;
  IsMember = 0;
  v8 = 1168;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  v10 = (_UNKNOWN **)g_leTaskHostContextListHead;
  while ( v10 != &g_leTaskHostContextListHead )
  {
    v11 = v10 - 1;
    v10 = (_UNKNOWN **)*v10;
    if ( ((_BYTE)v11[13] & 0x84) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, v9, v11, *((unsigned __int8 *)v11 + 104));
    }
    else
    {
      if ( !CheckTokenMembership(v7, v11[22], &IsMember) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v16);
        }
        break;
      }
      if ( IsMember == 1 )
      {
        v8 = 0;
        break;
      }
    }
  }
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  if ( v8 )
    goto LABEL_22;
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180029590  push    rbp
0x180029592  push    rbx
0x180029593  push    rsi
0x180029594  push    rdi
0x180029595  push    r14
0x180029597  push    r15
0x180029599  lea     rbp, [rsp-2Fh]
0x18002959e  sub     rsp, 0D8h
0x1800295a5  mov     rax, cs:__security_cookie
0x1800295ac  xor     rax, rsp
0x1800295af  mov     [rbp+57h+var_40], rax
0x1800295b3  mov     rbx, rdx
0x1800295b6  lea     rcx, [rbp+57h+var_BC]; void *
0x1800295ba  xor     edx, edx; Val
0x1800295bc  lea     r8d, [rdx+74h]; Size
0x1800295c0  call    memset_0
0x1800295c5  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800295c9  mov     [rbp+57h+TokenHandle], 0
0x1800295d1  mov     rcx, rbx; ClientBinding
0x1800295d4  mov     [rbp+57h+RpcCallAttributes], 3
0x1800295db  call    cs:__imp_RpcServerInqCallAttributesW
0x1800295e2  nop     dword ptr [rax+rax+00h]
0x1800295e7  mov     ebx, eax
0x1800295e9  test    eax, eax
0x1800295eb  jnz     loc_180029769
0x1800295f1  cmp     [rbp+57h+var_88], 3
0x1800295f5  jnz     loc_180029762
0x1800295fb  cmp     [rbp+57h+var_90], eax
0x1800295fe  jnz     loc_180029762
0x180029604  cmp     [rbp+57h+var_98], 6
0x180029608  jnz     loc_180029762
0x18002960e  cmp     [rbp+57h+var_94], 0Ah
0x180029612  jnz     loc_180029762
0x180029618  xor     ecx, ecx; BindingHandle
0x18002961a  call    cs:__imp_RpcImpersonateClient
0x180029621  nop     dword ptr [rax+rax+00h]
0x180029626  mov     ebx, eax
0x180029628  test    eax, eax
0x18002962a  jnz     loc_18002972E
0x180029630  call    cs:__imp_GetCurrentThread
0x180029637  nop     dword ptr [rax+rax+00h]
0x18002963c  mov     rcx, rax; ThreadHandle
0x18002963f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180029643  lea     edx, [rbx+8]; DesiredAccess
0x180029646  lea     r8d, [rbx+1]; OpenAsSelf
0x18002964a  call    cs:__imp_OpenThreadToken
0x180029651  nop     dword ptr [rax+rax+00h]
0x180029656  test    eax, eax
0x180029658  jz      loc_18002979F
0x18002965e  call    cs:__imp_RpcRevertToSelf
0x180029665  nop     dword ptr [rax+rax+00h]
0x18002966a  mov     r15, [rbp+57h+TokenHandle]
0x18002966e  lea     rcx, g_TaskHostContextListLock
0x180029675  mov     [rbp+57h+IsMember], ebx
0x180029678  mov     r14d, 490h
0x18002967e  call    cs:__imp_RtlAcquireSRWLockShared
0x180029685  nop     dword ptr [rax+rax+00h]
0x18002968a  mov     rsi, cs:g_leTaskHostContextListHead
0x180029691  lea     rdi, WPP_GLOBAL_Control
0x180029698  mov     rcx, cs:WPP_GLOBAL_Control
0x18002969f  lea     rax, g_leTaskHostContextListHead
0x1800296a6  cmp     rsi, rax
0x1800296a9  jz      short loc_180029716
0x1800296ab  lea     r9, [rsi-8]
0x1800296af  mov     rsi, [rsi]
0x1800296b2  test    byte ptr [r9+68h], 84h
0x1800296b7  jnz     short loc_1800296E2
0x1800296b9  mov     rdx, [r9+0B0h]; SidToCheck
0x1800296c0  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800296c4  mov     rcx, r15; TokenHandle
0x1800296c7  call    cs:__imp_CheckTokenMembership
0x1800296ce  nop     dword ptr [rax+rax+00h]
0x1800296d3  test    eax, eax
0x1800296d5  jz      short loc_180029706
0x1800296d7  cmp     [rbp+57h+IsMember], 1
0x1800296db  jnz     short loc_180029698
0x1800296dd  xor     r14d, r14d
0x1800296e0  jmp     short loc_180029716
0x1800296e2  cmp     rcx, rdi
0x1800296e5  jz      short loc_18002969F
0x1800296e7  test    byte ptr [rcx+1Ch], 2
0x1800296eb  jz      short loc_18002969F
0x1800296ed  movzx   eax, byte ptr [r9+68h]
0x1800296f2  mov     edx, 59h ; 'Y'
0x1800296f7  mov     rcx, [rcx+10h]
0x1800296fb  mov     [rsp+100h+var_E0], eax
0x1800296ff  call    WPP_SF_qd
0x180029704  jmp     short loc_180029698
0x180029706  mov     rax, cs:WPP_GLOBAL_Control
0x18002970d  cmp     rax, rdi
0x180029710  jnz     loc_1800297DC
0x180029716  lea     rcx, g_TaskHostContextListLock
0x18002971d  call    cs:__imp_RtlReleaseSRWLockShared
0x180029724  nop     dword ptr [rax+rax+00h]
0x180029729  test    r14d, r14d
0x18002972c  jnz     short loc_180029762
0x18002972e  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180029732  test    rcx, rcx
0x180029735  jz      short loc_180029743
0x180029737  call    cs:__imp_CloseHandle
0x18002973e  nop     dword ptr [rax+rax+00h]
0x180029743  mov     eax, ebx
0x180029745  mov     rcx, [rbp+57h+var_40]
0x180029749  xor     rcx, rsp; StackCookie
0x18002974c  call    __security_check_cookie
0x180029751  add     rsp, 0D8h
0x180029758  pop     r15
0x18002975a  pop     r14
0x18002975c  pop     rdi
0x18002975d  pop     rsi
0x18002975e  pop     rbx
0x18002975f  pop     rbp
0x180029760  retn
0x180029762  mov     ebx, 5
0x180029767  jmp     short loc_18002972E
0x180029769  mov     rcx, cs:WPP_GLOBAL_Control
0x180029770  lea     rdi, WPP_GLOBAL_Control
0x180029777  cmp     rcx, rdi
0x18002977a  jz      short loc_18002972E
0x18002977c  test    byte ptr [rcx+1Ch], 1
0x180029780  jz      short loc_18002972E
0x180029782  mov     edx, 81h
0x180029787  mov     r9d, eax
0x18002978a  jmp     short loc_180029794
0x18002978c  mov     edx, 82h
0x180029791  mov     r9d, ebx
0x180029794  mov     rcx, [rcx+10h]
0x180029798  call    WPP_SF_D
0x18002979d  jmp     short loc_18002972E
0x18002979f  call    cs:__imp_GetLastError
0x1800297a6  nop     dword ptr [rax+rax+00h]
0x1800297ab  mov     ebx, eax
0x1800297ad  call    cs:__imp_RpcRevertToSelf
0x1800297b4  nop     dword ptr [rax+rax+00h]
0x1800297b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297c0  lea     rdi, WPP_GLOBAL_Control
0x1800297c7  cmp     rcx, rdi
0x1800297ca  jz      loc_18002972E
0x1800297d0  test    byte ptr [rcx+1Ch], 1
0x1800297d4  jz      loc_18002972E
0x1800297da  jmp     short loc_18002978C
0x1800297dc  test    byte ptr [rax+1Ch], 1
0x1800297e0  jz      loc_180029716
0x1800297e6  call    cs:__imp_GetLastError
0x1800297ed  nop     dword ptr [rax+rax+00h]
0x1800297f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297f9  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180029800  mov     edx, 5Ah ; 'Z'
0x180029805  mov     r9d, eax
0x180029808  mov     rcx, [rcx+10h]
0x18002980c  call    WPP_SF_d
0x180029811  jmp     loc_180029716
```
