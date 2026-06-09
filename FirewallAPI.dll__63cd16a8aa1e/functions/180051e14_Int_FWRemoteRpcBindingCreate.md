# Int_FWRemoteRpcBindingCreate

- ea: `0x180051e14`
- end: `0x1800520a9`
- name: `Int_FWRemoteRpcBindingCreate`
- size: `661`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6c0`

## callees

- `0x180005954`
- `0x180024c3c`
- `0x1800277b0`
- `0x18003104c`
- `0x180051e14`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180051eb3`
- `RPCRT4!RpcStringBindingComposeW` at `0x180051eb3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180051eeb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180051eeb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180052005`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180052005`
- `RPCRT4!RpcBindingSetOption` at `0x180051f63`
- `RPCRT4!RpcBindingSetOption` at `0x180051f63`
- `RPCRT4!RpcEpResolveBinding` at `0x180051f26`
- `RPCRT4!RpcEpResolveBinding` at `0x180051f26`
- `RPCRT4!RpcStringFreeW` at `0x180052067`
- `RPCRT4!RpcStringFreeW` at `0x180052067`
- `RPCRT4!RpcBindingFree` at `0x180052042`
- `RPCRT4!RpcBindingFree` at `0x180052042`
- `fwbase!FwConstructRemoteMachineSPN` at `0x180051f9a`
- `fwbase!FwConstructRemoteMachineSPN` at `0x180051f9a`
- `fwbase!FwBaseFree` at `0x180052081`
- `fwbase!FwBaseFree` at `0x180052081`

## pseudocode

```c
__int64 __fastcall Int_FWRemoteRpcBindingCreate(RPC_WSTR NetworkAddr, RPC_BINDING_HANDLE *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  FwPolicy2 *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 362, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  String = 0;
  Binding = 0;
  ServerPrincName = 0;
  *a2 = 0;
  SecurityQOS = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", NetworkAddr, 0, 0, &String);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 363;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v4);
    }
  }
  else
  {
    v4 = RpcBindingFromStringBindingW(String, &Binding);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 364;
        goto LABEL_28;
      }
    }
    else
    {
      v4 = RpcEpResolveBinding(Binding, qword_1800774B0);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 365;
          goto LABEL_28;
        }
      }
      else
      {
        v4 = RpcBindingSetOption(Binding, 0xBu, 1u);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 366;
            goto LABEL_28;
          }
        }
        else
        {
          v4 = FwConstructRemoteMachineSPN(NetworkAddr, &ServerPrincName);
          v5 = v4;
          if ( v4 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 367;
              goto LABEL_28;
            }
          }
          else
          {
            SecurityQOS.Version = 1;
            *(_QWORD *)&SecurityQOS.Capabilities = 1;
            SecurityQOS.ImpersonationType = 3;
            v4 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 9u, 0, 0, &SecurityQOS);
            v5 = v4;
            if ( !v4 )
            {
              *a2 = Binding;
              goto LABEL_33;
            }
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 368;
              goto LABEL_28;
            }
          }
        }
      }
    }
  }
  if ( Binding )
  {
    v8 = RpcBindingFree(&Binding);
    if ( v8 )
      MicrosoftTelemetryAssertTriggeredArgs(v9, v8);
  }
LABEL_33:
  if ( String )
  {
    v10 = RpcStringFreeW(&String);
    if ( v10 )
      MicrosoftTelemetryAssertTriggeredArgs(v11, v10);
  }
  if ( ServerPrincName )
    FwBaseFree(ServerPrincName);
  return v5;
}

```

## disassembly

```asm
0x180051e14  mov     [rsp-28h+arg_10], rbx
0x180051e19  push    rbp
0x180051e1a  push    rsi
0x180051e1b  push    rdi
0x180051e1c  push    r12
0x180051e1e  push    r15
0x180051e20  mov     rbp, rsp
0x180051e23  sub     rsp, 70h
0x180051e27  mov     rax, cs:__security_cookie
0x180051e2e  xor     rax, rsp
0x180051e31  mov     [rbp+var_8], rax
0x180051e35  mov     rdi, rdx
0x180051e38  mov     rsi, rcx
0x180051e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e42  lea     r15, WPP_GLOBAL_Control
0x180051e49  lea     r12, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180051e50  cmp     rcx, r15
0x180051e53  jz      short loc_180051E6C
0x180051e55  test    byte ptr [rcx+1Ch], 8
0x180051e59  jz      short loc_180051E6C
0x180051e5b  mov     rcx, [rcx+10h]
0x180051e5f  mov     edx, 16Ah
0x180051e64  mov     r8, r12
0x180051e67  call    WPP_SF_
0x180051e6c  lea     rax, [rbp+String]
0x180051e70  mov     [rbp+String], 0
0x180051e78  xorps   xmm0, xmm0
0x180051e7b  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180051e80  xor     r9d, r9d; Endpoint
0x180051e83  mov     [rsp+70h+Options], 0; Options
0x180051e8c  mov     r8, rsi; NetworkAddr
0x180051e8f  mov     [rbp+Binding], 0
0x180051e97  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180051e9e  mov     [rbp+ServerPrincName], 0
0x180051ea6  xor     ecx, ecx; ObjUuid
0x180051ea8  mov     qword ptr [rdi], 0
0x180051eaf  movups  xmmword ptr [rbp+var_18.Version], xmm0
0x180051eb3  call    cs:__imp_RpcStringBindingComposeW
0x180051eb9  mov     ebx, eax
0x180051ebb  test    eax, eax
0x180051ebd  jz      short loc_180051EE3
0x180051ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180051ec6  cmp     rcx, r15
0x180051ec9  jz      loc_180052037
0x180051ecf  test    byte ptr [rcx+1Ch], 1
0x180051ed3  jz      loc_180052037
0x180051ed9  mov     edx, 16Bh
0x180051ede  jmp     loc_180052028
0x180051ee3  mov     rcx, [rbp+String]; StringBinding
0x180051ee7  lea     rdx, [rbp+Binding]; Binding
0x180051eeb  call    cs:__imp_RpcBindingFromStringBindingW
0x180051ef1  mov     ebx, eax
0x180051ef3  test    eax, eax
0x180051ef5  jz      short loc_180051F1B
0x180051ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180051efe  cmp     rcx, r15
0x180051f01  jz      loc_180052037
0x180051f07  test    byte ptr [rcx+1Ch], 1
0x180051f0b  jz      loc_180052037
0x180051f11  mov     edx, 16Ch
0x180051f16  jmp     loc_180052028
0x180051f1b  mov     rcx, [rbp+Binding]; Binding
0x180051f1f  lea     rdx, qword_1800774B0; IfSpec
0x180051f26  call    cs:__imp_RpcEpResolveBinding
0x180051f2c  mov     ebx, eax
0x180051f2e  test    eax, eax
0x180051f30  jz      short loc_180051F56
0x180051f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f39  cmp     rcx, r15
0x180051f3c  jz      loc_180052037
0x180051f42  test    byte ptr [rcx+1Ch], 1
0x180051f46  jz      loc_180052037
0x180051f4c  mov     edx, 16Dh
0x180051f51  jmp     loc_180052028
0x180051f56  mov     rcx, [rbp+Binding]; hBinding
0x180051f5a  mov     edx, 0Bh; option
0x180051f5f  lea     r8d, [rdx-0Ah]; optionValue
0x180051f63  call    cs:__imp_RpcBindingSetOption
0x180051f69  mov     ebx, eax
0x180051f6b  test    eax, eax
0x180051f6d  jz      short loc_180051F93
0x180051f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f76  cmp     rcx, r15
0x180051f79  jz      loc_180052037
0x180051f7f  test    byte ptr [rcx+1Ch], 1
0x180051f83  jz      loc_180052037
0x180051f89  mov     edx, 16Eh
0x180051f8e  jmp     loc_180052028
0x180051f93  lea     rdx, [rbp+ServerPrincName]
0x180051f97  mov     rcx, rsi
0x180051f9a  call    cs:__imp_FwConstructRemoteMachineSPN
0x180051fa0  mov     ebx, eax
0x180051fa2  test    eax, eax
0x180051fa4  jz      short loc_180051FC3
0x180051fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180051fad  cmp     rcx, r15
0x180051fb0  jz      loc_180052037
0x180051fb6  test    byte ptr [rcx+1Ch], 1
0x180051fba  jz      short loc_180052037
0x180051fbc  mov     edx, 16Fh
0x180051fc1  jmp     short loc_180052028
0x180051fc3  mov     rdx, [rbp+ServerPrincName]; ServerPrincName
0x180051fc7  lea     rax, [rbp+var_18]
0x180051fcb  mov     rcx, [rbp+Binding]; Binding
0x180051fcf  mov     r9d, 9; AuthnSvc
0x180051fd5  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180051fda  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x180051fe2  mov     [rbp+var_18.Version], 1
0x180051fe9  lea     r8d, [r9-3]; AuthnLevel
0x180051fed  mov     qword ptr [rbp+var_18.Capabilities], 1
0x180051ff5  mov     [rbp+var_18.ImpersonationType], 3
0x180051ffc  mov     [rsp+70h+Options], 0; AuthIdentity
0x180052005  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18005200b  mov     ebx, eax
0x18005200d  test    eax, eax
0x18005200f  jz      short loc_180052055
0x180052011  mov     rcx, cs:WPP_GLOBAL_Control
0x180052018  cmp     rcx, r15
0x18005201b  jz      short loc_180052037
0x18005201d  test    byte ptr [rcx+1Ch], 1
0x180052021  jz      short loc_180052037
0x180052023  mov     edx, 170h
0x180052028  mov     rcx, [rcx+10h]
0x18005202c  mov     r9d, eax
0x18005202f  mov     r8, r12
0x180052032  call    WPP_SF_d
0x180052037  cmp     [rbp+Binding], 0
0x18005203c  jz      short loc_18005205C
0x18005203e  lea     rcx, [rbp+Binding]; Binding
0x180052042  call    cs:__imp_RpcBindingFree
0x180052048  test    eax, eax
0x18005204a  jz      short loc_18005205C
0x18005204c  mov     edx, eax
0x18005204e  call    MicrosoftTelemetryAssertTriggeredArgs
0x180052053  jmp     short loc_18005205C
0x180052055  mov     rax, [rbp+Binding]
0x180052059  mov     [rdi], rax
0x18005205c  cmp     [rbp+String], 0
0x180052061  jz      short loc_180052078
0x180052063  lea     rcx, [rbp+String]; String
0x180052067  call    cs:__imp_RpcStringFreeW
0x18005206d  test    eax, eax
0x18005206f  jz      short loc_180052078
0x180052071  mov     edx, eax
0x180052073  call    MicrosoftTelemetryAssertTriggeredArgs
0x180052078  mov     rcx, [rbp+ServerPrincName]
0x18005207c  test    rcx, rcx
0x18005207f  jz      short loc_180052087
0x180052081  call    cs:__imp_FwBaseFree
0x180052087  mov     eax, ebx
0x180052089  mov     rcx, [rbp+var_8]
0x18005208d  xor     rcx, rsp; StackCookie
0x180052090  call    __security_check_cookie
0x180052095  mov     rbx, [rsp+70h+arg_10]
0x18005209d  add     rsp, 70h
0x1800520a1  pop     r15
0x1800520a3  pop     r12
0x1800520a5  pop     rdi
0x1800520a6  pop     rsi
0x1800520a7  pop     rbp
0x1800520a8  retn
```
