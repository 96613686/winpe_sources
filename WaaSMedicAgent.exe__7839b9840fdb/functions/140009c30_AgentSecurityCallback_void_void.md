# AgentSecurityCallback(void *,void *)

- ea: `0x140009c30`
- end: `0x140009e59`
- name: `?AgentSecurityCallback@@YAJPEAX0@Z`
- size: `553`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002a30`
- `0x140009c30`
- `0x14000b470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009db6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009cef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009cef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009cf9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140009d0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140009d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009e35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009e35`
- `RPCRT4!RpcRevertToSelf` at `0x140009ddc`
- `RPCRT4!RpcRevertToSelf` at `0x140009ddc`
- `RPCRT4!RpcImpersonateClient` at `0x140009cb6`
- `RPCRT4!RpcImpersonateClient` at `0x140009cb6`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x140009c7e`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x140009c7e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140009dac`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140009dac`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140009d7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140009d7b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140009e03`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140009e03`

## string_xrefs

- `0x140009c88`: `Agent: I_RpcBindingInqTransportType failed. RPC status code 0x%08x`
- `0x140009ca2`: `Agent: Did not find expected transport type. Found %u`
- `0x140009cc5`: `Agent: RpcImpersonateClient failed. RPC status code 0x%08x`
- `0x140009d2e`: `Agent: OpenThreadToken failed. hr=0x%08x`
- `0x140009d97`: `Agent: AllocateAndInitializeSid failed. hr=0x%08x`
- `0x140009dc8`: `Agent: CheckTokenMembership failed. hr=0x%08x`
- `0x140009de6`: `Agent: RpcRevertToSelf failed. RPC status code 0x%08x`
- `0x140009e12`: `Agent: IsCallerLocalSystem determined caller is local system.`
- `0x140009e09`: `Agent: IsCallerLocalSystem determined caller is not local system.`

## pseudocode

```c
__int64 __fastcall AgentSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // edi
  HANDLE v5; // rsi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  const unsigned __int16 *v11; // rdx
  unsigned int Type; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp-5h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-1h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+7h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  hObject = 0;
  IsMember = 0;
  Type = 0;
  if ( I_RpcBindingInqTransportType(Context, &Type) )
  {
    v3 = L"Agent: I_RpcBindingInqTransportType failed. RPC status code 0x%08x";
    goto LABEL_26;
  }
  if ( Type != 4 )
  {
    v3 = L"Agent: Did not find expected transport type. Found %u";
    goto LABEL_26;
  }
  v4 = RpcImpersonateClient(Context);
  if ( v4 )
  {
    v3 = L"Agent: RpcImpersonateClient failed. RPC status code 0x%08x";
    goto LABEL_26;
  }
  v5 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &hObject) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( CheckTokenMembership(hObject, SidToCheck, &IsMember) )
      {
        if ( !IsMember )
          v4 = 5;
        goto LABEL_24;
      }
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      LogLevelW(2u, L"Agent: CheckTokenMembership failed. hr=0x%08x", (unsigned int)v10);
    }
    else
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      LogLevelW(2u, L"Agent: AllocateAndInitializeSid failed. hr=0x%08x", (unsigned int)v9);
    }
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    LogLevelW(2u, L"Agent: OpenThreadToken failed. hr=0x%08x", (unsigned int)v8);
  }
  v4 = 5;
LABEL_24:
  if ( !RpcRevertToSelf() )
    goto LABEL_27;
  v3 = L"Agent: RpcRevertToSelf failed. RPC status code 0x%08x";
LABEL_26:
  LogLevelW(2u, v3);
  v4 = 5;
LABEL_27:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  v11 = L"Agent: IsCallerLocalSystem determined caller is local system.";
  if ( v4 )
    v11 = L"Agent: IsCallerLocalSystem determined caller is not local system.";
  LogLevelW(4u, v11);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x140009c30  push    rbp
0x140009c32  push    rbx
0x140009c33  push    rsi
0x140009c34  push    rdi
0x140009c35  push    r14
0x140009c37  push    r15
0x140009c39  lea     rbp, [rsp-2Fh]
0x140009c3e  sub     rsp, 98h
0x140009c45  mov     rax, cs:__security_cookie
0x140009c4c  xor     rax, rsp
0x140009c4f  mov     [rbp+57h+var_40], rax
0x140009c53  xor     r14d, r14d
0x140009c56  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140009c5c  mov     rbx, rdx
0x140009c5f  mov     [rbp+57h+SidToCheck], r14
0x140009c63  lea     rdx, [rbp+57h+Type]; Type
0x140009c67  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x140009c6b  mov     rcx, rbx; Binding
0x140009c6e  mov     [rbp+57h+hObject], r14
0x140009c72  lea     r15d, [r14+5]
0x140009c76  mov     [rbp+57h+IsMember], r14d
0x140009c7a  mov     [rbp+57h+Type], r14d
0x140009c7e  call    cs:__imp_I_RpcBindingInqTransportType
0x140009c84  test    eax, eax
0x140009c86  jz      short loc_140009C98
0x140009c88  lea     rdx, aAgentIRpcbindi; "Agent: I_RpcBindingInqTransportType fai"...
0x140009c8f  lea     ecx, [r14+2]
0x140009c93  jmp     loc_140009DEF
0x140009c98  mov     r8d, [rbp+57h+Type]
0x140009c9c  cmp     r8d, 4
0x140009ca0  jz      short loc_140009CB3
0x140009ca2  lea     rdx, aAgentDidNotFin; "Agent: Did not find expected transport "...
0x140009ca9  mov     ecx, 2
0x140009cae  jmp     loc_140009DF2
0x140009cb3  mov     rcx, rbx; BindingHandle
0x140009cb6  call    cs:__imp_RpcImpersonateClient
0x140009cbc  mov     edi, eax
0x140009cbe  test    eax, eax
0x140009cc0  jz      short loc_140009CCE
0x140009cc2  mov     r8d, eax
0x140009cc5  lea     rdx, aAgentRpcimpers; "Agent: RpcImpersonateClient failed. RPC"...
0x140009ccc  jmp     short loc_140009CA9
0x140009cce  mov     rsi, [rbp+57h+hObject]
0x140009cd2  lea     rax, [rsi-1]
0x140009cd6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140009cda  ja      short loc_140009CF5
0x140009cdc  call    cs:__imp_GetLastError
0x140009ce2  mov     rcx, rsi; hObject
0x140009ce5  mov     ebx, eax
0x140009ce7  call    cs:__imp_CloseHandle
0x140009ced  mov     ecx, ebx; dwErrCode
0x140009cef  call    cs:__imp_SetLastError
0x140009cf5  mov     [rbp+57h+hObject], r14
0x140009cf9  call    cs:__imp_GetCurrentThread
0x140009cff  xor     r8d, r8d; OpenAsSelf
0x140009d02  lea     r9, [rbp+57h+hObject]; TokenHandle
0x140009d06  mov     rcx, rax; ThreadHandle
0x140009d09  lea     edx, [r8+8]; DesiredAccess
0x140009d0d  call    cs:__imp_OpenThreadToken
0x140009d13  mov     ebx, 2
0x140009d18  test    eax, eax
0x140009d1a  jnz     short loc_140009D47
0x140009d1c  call    cs:__imp_GetLastError
0x140009d22  test    eax, eax
0x140009d24  jle     short loc_140009D2E
0x140009d26  movzx   eax, ax
0x140009d29  or      eax, 80070000h
0x140009d2e  lea     rdx, aAgentOpenthrea; "Agent: OpenThreadToken failed. hr=0x%08"...
0x140009d35  mov     r8d, eax
0x140009d38  mov     ecx, ebx; unsigned __int8
0x140009d3a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140009d3f  mov     edi, r15d
0x140009d42  jmp     loc_140009DDC
0x140009d47  lea     rax, [rbp+57h+SidToCheck]
0x140009d4b  xor     r9d, r9d; nSubAuthority1
0x140009d4e  mov     [rsp+0C0h+pSid], rax; pSid
0x140009d53  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140009d57  mov     [rsp+0C0h+nSubAuthority7], r14d; nSubAuthority7
0x140009d5c  mov     dl, 1; nSubAuthorityCount
0x140009d5e  mov     [rsp+0C0h+nSubAuthority6], r14d; nSubAuthority6
0x140009d63  mov     [rsp+0C0h+nSubAuthority5], r14d; nSubAuthority5
0x140009d68  lea     r8d, [r9+12h]; nSubAuthority0
0x140009d6c  mov     [rsp+0C0h+nSubAuthority4], r14d; nSubAuthority4
0x140009d71  mov     [rsp+0C0h+nSubAuthority3], r14d; nSubAuthority3
0x140009d76  mov     [rsp+0C0h+nSubAuthority2], r14d; nSubAuthority2
0x140009d7b  call    cs:__imp_AllocateAndInitializeSid
0x140009d81  test    eax, eax
0x140009d83  jnz     short loc_140009DA0
0x140009d85  call    cs:__imp_GetLastError
0x140009d8b  test    eax, eax
0x140009d8d  jle     short loc_140009D97
0x140009d8f  movzx   eax, ax
0x140009d92  or      eax, 80070000h
0x140009d97  lea     rdx, aAgentAllocatea; "Agent: AllocateAndInitializeSid failed."...
0x140009d9e  jmp     short loc_140009D35
0x140009da0  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140009da4  lea     r8, [rbp+57h+IsMember]; IsMember
0x140009da8  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x140009dac  call    cs:__imp_CheckTokenMembership
0x140009db2  test    eax, eax
0x140009db4  jnz     short loc_140009DD4
0x140009db6  call    cs:__imp_GetLastError
0x140009dbc  test    eax, eax
0x140009dbe  jle     short loc_140009DC8
0x140009dc0  movzx   eax, ax
0x140009dc3  or      eax, 80070000h
0x140009dc8  lea     rdx, aAgentChecktoke; "Agent: CheckTokenMembership failed. hr="...
0x140009dcf  jmp     loc_140009D35
0x140009dd4  cmp     [rbp+57h+IsMember], r14d
0x140009dd8  cmovz   edi, r15d
0x140009ddc  call    cs:__imp_RpcRevertToSelf
0x140009de2  test    eax, eax
0x140009de4  jz      short loc_140009DFA
0x140009de6  lea     rdx, aAgentRpcrevert; "Agent: RpcRevertToSelf failed. RPC stat"...
0x140009ded  mov     ecx, ebx; unsigned __int8
0x140009def  mov     r8d, eax
0x140009df2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140009df7  mov     edi, r15d
0x140009dfa  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140009dfe  test    rcx, rcx
0x140009e01  jz      short loc_140009E09
0x140009e03  call    cs:__imp_FreeSid
0x140009e09  lea     rax, aAgentIscallerl_0; "Agent: IsCallerLocalSystem determined c"...
0x140009e10  test    edi, edi
0x140009e12  lea     rdx, aAgentIscallerl; "Agent: IsCallerLocalSystem determined c"...
0x140009e19  mov     ecx, 4; unsigned __int8
0x140009e1e  cmovnz  rdx, rax; unsigned __int16 *
0x140009e22  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140009e27  mov     rcx, [rbp+57h+hObject]; hObject
0x140009e2b  lea     rdx, [rcx-1]
0x140009e2f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140009e33  ja      short loc_140009E3B
0x140009e35  call    cs:__imp_CloseHandle
0x140009e3b  mov     eax, edi
0x140009e3d  mov     rcx, [rbp+57h+var_40]
0x140009e41  xor     rcx, rsp; StackCookie
0x140009e44  call    __security_check_cookie
0x140009e49  add     rsp, 98h
0x140009e50  pop     r15
0x140009e52  pop     r14
0x140009e54  pop     rdi
0x140009e55  pop     rsi
0x140009e56  pop     rbx
0x140009e57  pop     rbp
0x140009e58  retn
```
