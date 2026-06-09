# WaasMedic::CSandboxRpcWrapper::ConnectToSandbox(void)

- ea: `0x18001e780`
- end: `0x18001e834`
- name: `?ConnectToSandbox@CSandboxRpcWrapper@WaasMedic@@QEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(WaasMedic::CSandboxRpcWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018d3c`

## callees

- `0x18001e780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e798`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7b2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001e7f1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001e7f1`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001e7dd`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001e7dd`
- `RPCRT4!RpcStringFreeW` at `0x18001e7aa`
- `RPCRT4!RpcStringFreeW` at `0x18001e7aa`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18001e819`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18001e819`

## pseudocode

```c
RPC_STATUS __fastcall WaasMedic::CSandboxRpcWrapper::ConnectToSandbox(WaasMedic::CSandboxRpcWrapper *this)
{
  RPC_WSTR *StringBinding; // rdi
  unsigned __int16 *v3; // rsi
  DWORD LastError; // eax
  DWORD v5; // ebx
  RPC_STATUS result; // eax
  bool v7; // cc
  RPC_WSTR String; // [rsp+60h] [rbp+8h] BYREF

  StringBinding = (RPC_WSTR *)((char *)this + 24);
  v3 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    LastError = GetLastError();
    String = v3;
    v5 = LastError;
    RpcStringFreeW(&String);
    SetLastError(v5);
  }
  *StringBinding = 0;
  result = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, *((RPC_WSTR *)this + 1), 0, StringBinding);
  v7 = result <= 0;
  if ( !result )
  {
    result = RpcBindingFromStringBindingW(*StringBinding, &agent_v1_0_c_ifspec);
    v7 = result <= 0;
    if ( !result )
    {
      result = RpcBindingSetAuthInfoW(agent_v1_0_c_ifspec, 0, 6u, 0xFFFFFFFF, 0, 0);
      v7 = result <= 0;
    }
  }
  if ( !v7 )
    return (unsigned __int16)result | 0x80010000;
  return result;
}

```

## disassembly

```asm
0x18001e780  push    rbx
0x18001e782  push    rbp
0x18001e783  push    rsi
0x18001e784  push    rdi
0x18001e785  sub     rsp, 38h
0x18001e789  lea     rdi, [rcx+18h]
0x18001e78d  mov     rbp, rcx
0x18001e790  mov     rsi, [rdi]
0x18001e793  test    rsi, rsi
0x18001e796  jz      short loc_18001E7B8
0x18001e798  call    cs:__imp_GetLastError
0x18001e79e  lea     rcx, [rsp+58h+String]; String
0x18001e7a3  mov     [rsp+58h+String], rsi
0x18001e7a8  mov     ebx, eax
0x18001e7aa  call    cs:__imp_RpcStringFreeW
0x18001e7b0  mov     ecx, ebx; dwErrCode
0x18001e7b2  call    cs:__imp_SetLastError
0x18001e7b8  mov     qword ptr [rdi], 0
0x18001e7bf  lea     rdx, ProtSeq; "ncalrpc"
0x18001e7c6  mov     r9, [rbp+8]; Endpoint
0x18001e7ca  xor     r8d, r8d; NetworkAddr
0x18001e7cd  mov     [rsp+58h+StringBinding], rdi; StringBinding
0x18001e7d2  xor     ecx, ecx; ObjUuid
0x18001e7d4  mov     [rsp+58h+Options], 0; Options
0x18001e7dd  call    cs:__imp_RpcStringBindingComposeW
0x18001e7e3  test    eax, eax
0x18001e7e5  jnz     short loc_18001E821
0x18001e7e7  mov     rcx, [rdi]; StringBinding
0x18001e7ea  lea     rdx, agent_v1_0_c_ifspec; Binding
0x18001e7f1  call    cs:__imp_RpcBindingFromStringBindingW
0x18001e7f7  test    eax, eax
0x18001e7f9  jnz     short loc_18001E821
0x18001e7fb  mov     rcx, cs:agent_v1_0_c_ifspec; Binding
0x18001e802  lea     r8d, [rax+6]; AuthnLevel
0x18001e806  mov     dword ptr [rsp+58h+StringBinding], eax; AuthzSvc
0x18001e80a  or      r9d, 0FFFFFFFFh; AuthnSvc
0x18001e80e  xor     edx, edx; ServerPrincName
0x18001e810  mov     [rsp+58h+Options], 0; AuthIdentity
0x18001e819  call    cs:__imp_RpcBindingSetAuthInfoW
0x18001e81f  test    eax, eax
0x18001e821  jle     short loc_18001E82B
0x18001e823  movzx   eax, ax
0x18001e826  or      eax, 80010000h
0x18001e82b  add     rsp, 38h
0x18001e82f  pop     rdi
0x18001e830  pop     rsi
0x18001e831  pop     rbp
0x18001e832  pop     rbx
0x18001e833  retn
```
