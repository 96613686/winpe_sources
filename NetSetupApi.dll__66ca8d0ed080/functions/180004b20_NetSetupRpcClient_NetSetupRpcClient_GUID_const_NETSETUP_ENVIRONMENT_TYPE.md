# NetSetupRpcClient::NetSetupRpcClient(_GUID const &,_NETSETUP_ENVIRONMENT_TYPE)

- ea: `0x180004b20`
- end: `0x180004d3a`
- name: `??0NetSetupRpcClient@@QEAA@AEBU_GUID@@W4_NETSETUP_ENVIRONMENT_TYPE@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003b90`
- `0x18000dda4`

## callees

- `0x180004b20`
- `0x180004d40`
- `0x180006608`
- `0x18000895c`
- `0x18000d18c`
- `0x1800119f0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180004c0a`
- `RPCRT4!RpcBindingCreateW` at `0x180004c0a`
- `RPCRT4!RpcBindingBind` at `0x180004c2b`
- `RPCRT4!RpcBindingBind` at `0x180004c2b`

## pseudocode

```c
__int64 __fastcall NetSetupRpcClient::NetSetupRpcClient(__int64 a1, _OWORD *a2, int a3)
{
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  _QWORD v8[4]; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+118h] [rbp+10h] BYREF
  int v11; // [rsp+120h] [rbp+18h]
  __int64 v12; // [rsp+124h] [rbp+1Ch]
  __int64 v13; // [rsp+12Ch] [rbp+24h]
  int v14; // [rsp+134h] [rbp+2Ch]
  __int64 v15; // [rsp+138h] [rbp+30h]
  __int64 v16; // [rsp+140h] [rbp+38h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+148h] [rbp+40h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+170h] [rbp+68h] BYREF

  v8[2] = -2;
  v8[3] = a1;
  *(_QWORD *)a1 = &NetSetupRpcClient::`vftable';
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)(a1 + 32) = *a2;
  memset(&Template.ProtocolSequence + 1, 0, 44);
  *(_QWORD *)&Security.Version = 1;
  Security.AuthIdentity = 0;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  *(_QWORD *)&Template.Version = 1;
  Template.ProtocolSequence = 3;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v10;
  v10 = 4;
  v11 = 1;
  v12 = 2;
  v15 = 0;
  v5 = RpcBindingCreateW(&Template, &Security, 0, (RPC_BINDING_HANDLE *)(a1 + 16));
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6dac5f645e313f70d35f2be1a71ce853_Traceguids, v5);
    HResultException::HResultException((HResultException *)pExceptionObject, v5 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 8) = 1;
  v6 = RpcBindingBind(0, *(RPC_BINDING_HANDLE *)(a1 + 16), qword_180019DC0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6dac5f645e313f70d35f2be1a71ce853_Traceguids, v6);
    HResultException::HResultException((HResultException *)pExceptionObject, v6 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 8) = 2;
  LODWORD(v8[0]) = a3;
  v8[1] = a1;
  NetSetupExecuteInRpc__lambda_a248543b255889d98cee257f8f54a92e_(v8);
  *(_DWORD *)(a1 + 8) = 3;
  return a1;
}

```

## disassembly

```asm
0x180004b20  mov     rax, rsp
0x180004b23  push    rbp
0x180004b24  push    rdi
0x180004b25  push    r14
0x180004b27  lea     rbp, [rax-0C8h]
0x180004b2e  sub     rsp, 1B0h
0x180004b35  mov     [rsp+1C0h+var_190], 0FFFFFFFFFFFFFFFEh
0x180004b3e  mov     [rax+10h], rbx
0x180004b42  mov     [rax+18h], rsi
0x180004b46  mov     rax, cs:__security_cookie
0x180004b4d  xor     rax, rsp
0x180004b50  mov     [rbp+0C0h+var_20], rax
0x180004b57  mov     esi, r8d
0x180004b5a  mov     rdi, rcx
0x180004b5d  mov     qword ptr [rsp+1C0h+var_188], rcx
0x180004b62  lea     rax, ??_7NetSetupRpcClient@@6B@; const NetSetupRpcClient::`vftable'
0x180004b69  mov     [rcx], rax
0x180004b6c  xor     ecx, ecx
0x180004b6e  mov     [rdi+8], ecx
0x180004b71  mov     [rdi+10h], rcx
0x180004b75  mov     [rdi+18h], rcx
0x180004b79  movups  xmm0, xmmword ptr [rdx]
0x180004b7c  movups  xmmword ptr [rdi+20h], xmm0
0x180004b80  mov     qword ptr [rbp+0C0h+Template+0Ch], rcx
0x180004b84  mov     dword ptr [rbp+0C0h+Template.NetworkAddress+4], ecx
0x180004b87  xorps   xmm0, xmm0
0x180004b8a  movdqu  xmmword ptr [rbp+0C0h+Template.u1], xmm0
0x180004b92  mov     qword ptr [rbp+0C0h+Template.ObjectUuid.Data4], rcx
0x180004b99  mov     qword ptr [rbp+0C0h+Security.Version], 1
0x180004ba1  mov     [rbp+0C0h+Security.AuthIdentity], rcx
0x180004ba5  mov     [rbp+0C0h+var_9C], rcx
0x180004ba9  mov     [rbp+0C0h+var_94], ecx
0x180004bac  mov     [rbp+0C0h+var_88], rcx
0x180004bb0  mov     qword ptr [rbp+0C0h+Template.Version], 1
0x180004bb8  mov     [rbp+0C0h+Template.ProtocolSequence], 3
0x180004bbf  mov     [rbp+0C0h+Template.StringEndpoint], rcx
0x180004bc6  mov     [rbp+0C0h+Security.ServerPrincName], rcx
0x180004bca  mov     [rbp+0C0h+Security.AuthnLevel], 6
0x180004bd1  mov     [rbp+0C0h+Security.AuthnSvc], 14h
0x180004bd8  lea     rax, [rbp+0C0h+var_B0]
0x180004bdc  mov     [rbp+0C0h+Security.SecurityQos], rax
0x180004be0  mov     [rbp+0C0h+var_B0], 4
0x180004be8  mov     [rbp+0C0h+var_A8], 1
0x180004bef  mov     [rbp+0C0h+var_A4], 2
0x180004bf7  mov     [rbp+0C0h+var_90], rcx
0x180004bfb  lea     r9, [rdi+10h]; Binding
0x180004bff  xor     r8d, r8d; Options
0x180004c02  lea     rdx, [rbp+0C0h+Security]; Security
0x180004c06  lea     rcx, [rbp+0C0h+Template]; Template
0x180004c0a  call    cs:__imp_RpcBindingCreateW
0x180004c10  mov     r14d, eax
0x180004c13  test    eax, eax
0x180004c15  jnz     short loc_180004C8E
0x180004c17  mov     dword ptr [rdi+8], 1
0x180004c1e  lea     r8, qword_180019DC0; IfSpec
0x180004c25  mov     rdx, [rdi+10h]; Binding
0x180004c29  xor     ecx, ecx; pAsync
0x180004c2b  call    cs:__imp_RpcBindingBind
0x180004c31  mov     ebx, eax
0x180004c33  test    eax, eax
0x180004c35  jnz     loc_180004CE5
0x180004c3b  mov     dword ptr [rdi+8], 2
0x180004c42  mov     dword ptr [rsp+1C0h+var_1A0], esi
0x180004c46  mov     ecx, dword ptr [rsp+1C0h+var_1A0+4]
0x180004c4a  mov     dword ptr [rsp+1C0h+var_1A0+4], ecx
0x180004c4e  mov     [rsp+1C0h+var_198], rdi
0x180004c53  lea     rcx, [rsp+1C0h+var_1A0]
0x180004c58  call    NetSetupExecuteInRpc__lambda_a248543b255889d98cee257f8f54a92e___; NetSetupExecuteInRpc__lambda_a248543b255889d98cee257f8f54a92e_
0x180004c5d  mov     dword ptr [rdi+8], 3
0x180004c64  mov     rax, rdi
0x180004c67  mov     rcx, [rbp+0C0h+var_20]
0x180004c6e  xor     rcx, rsp; StackCookie
0x180004c71  call    __security_check_cookie
0x180004c76  lea     r11, [rsp+1C0h+var_10]
0x180004c7e  mov     rbx, [r11+28h]
0x180004c82  mov     rsi, [r11+30h]
0x180004c86  mov     rsp, r11
0x180004c89  pop     r14
0x180004c8b  pop     rdi
0x180004c8c  pop     rbp
0x180004c8d  retn
0x180004c8e  lea     rax, WPP_GLOBAL_Control
0x180004c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c9c  cmp     rcx, rax
0x180004c9f  jz      short loc_180004CBF
0x180004ca1  cmp     byte ptr [rcx+19h], 2
0x180004ca5  jb      short loc_180004CBF
0x180004ca7  mov     edx, 13h
0x180004cac  mov     r9d, r14d
0x180004caf  lea     r8, WPP_6dac5f645e313f70d35f2be1a71ce853_Traceguids
0x180004cb6  mov     rcx, [rcx+10h]
0x180004cba  call    WPP_SF_d
0x180004cbf  or      r14d, 80010000h
0x180004cc6  mov     edx, r14d; int
0x180004cc9  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x180004cce  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180004cd3  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180004cda  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180004cdf  call    _CxxThrowException_0
0x180004ce5  lea     rax, WPP_GLOBAL_Control
0x180004cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf3  cmp     rcx, rax
0x180004cf6  jz      short loc_180004D16
0x180004cf8  cmp     byte ptr [rcx+19h], 2
0x180004cfc  jb      short loc_180004D16
0x180004cfe  mov     edx, 14h
0x180004d03  mov     r9d, ebx
0x180004d06  lea     r8, WPP_6dac5f645e313f70d35f2be1a71ce853_Traceguids
0x180004d0d  mov     rcx, [rcx+10h]
0x180004d11  call    WPP_SF_d
0x180004d16  or      ebx, 80010000h
0x180004d1c  mov     edx, ebx; int
0x180004d1e  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x180004d23  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180004d28  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180004d2f  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180004d34  call    _CxxThrowException_0
```
