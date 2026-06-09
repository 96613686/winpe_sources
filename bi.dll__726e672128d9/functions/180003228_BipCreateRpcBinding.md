# BipCreateRpcBinding

- ea: `0x180003228`
- end: `0x180003400`
- name: `BipCreateRpcBinding`
- size: `472`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800018e0`
- `0x1800019f0`
- `0x180001c40`
- `0x180001cd0`
- `0x180001dd0`
- `0x180001f10`
- `0x180001fa0`
- `0x180002040`
- `0x180002170`
- `0x180002290`
- `0x180002320`
- `0x1800023c0`
- `0x180002450`
- `0x1800024f0`
- `0x180002590`
- `0x180002630`
- `0x180002740`
- `0x180002870`
- `0x180002940`
- `0x1800029e0`
- `0x180002a70`
- `0x180002b10`
- `0x180002bb0`
- `0x180002c60`
- `0x180002d10`
- `0x180002db0`
- `0x180002e70`
- `0x180002f60`
- `0x180003020`
- `0x1800030c0`
- `0x180003160`

## callees

- `0x180003228`
- `0x1800034e0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x1800032ee`
- `RPCRT4!RpcBindingCreateW` at `0x1800032ee`
- `RPCRT4!RpcBindingBind` at `0x180003309`
- `RPCRT4!RpcBindingBind` at `0x1800033a6`
- `RPCRT4!RpcBindingBind` at `0x180003309`
- `RPCRT4!RpcBindingBind` at `0x1800033a6`
- `RPCRT4!RpcBindingFree` at `0x1800033c9`
- `RPCRT4!RpcBindingFree` at `0x1800033c9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800033b2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800033b2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180003326`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180003326`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180003386`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000338f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180003386`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000338f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000334b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000334b`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180003370`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180003370`

## string_xrefs

- `0x180003341`: `BrokerInfrastructure`

## pseudocode

```c
__int64 __fastcall BipCreateRpcBinding(RPC_BINDING_HANDLE *a1)
{
  RPC_STATUS v2; // eax
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rsi
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-79h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-71h] BYREF
  _DWORD v11[4]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v12; // [rsp+60h] [rbp-39h]
  _DWORD *v13; // [rsp+70h] [rbp-29h]
  _DWORD v14[4]; // [rsp+78h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+88h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp-1h] BYREF

  v14[0] = 257;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v14[1] = 83886080;
  v14[2] = 18;
  memset(&Template, 0, sizeof(Template));
  Template.Version = 1;
  Options.Version = 1;
  Options.Flags = 1;
  Template.ProtocolSequence = 3;
  v11[0] = 3;
  v11[3] = 3;
  v13 = v14;
  v11[1] = 1;
  v11[2] = 1;
  Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v11;
  Binding = 0;
  *(_QWORD *)&Options.ComTimeout = 5;
  Security.AuthnLevel = 6;
  v12 = 0;
  Security.AuthnSvc = 20;
  v2 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v2 )
    goto LABEL_11;
  v2 = RpcBindingBind(0, Binding, &unk_180005380);
  if ( v2 != 1753 )
  {
LABEL_10:
    if ( !v2 )
    {
      v5 = 0;
      *a1 = Binding;
      return (unsigned int)v5;
    }
LABEL_11:
    v5 = I_RpcMapWin32Status(v2);
    if ( v5 >= 0 )
      return (unsigned int)v5;
    goto LABEL_12;
  }
  v3 = OpenSCManagerW(0, 0, 4u);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, L"BrokerInfrastructure", 4u);
    v7 = v6;
    if ( v6 )
    {
      v5 = (unsigned int)WaitServiceState(v6, 8, 120000) != 4 ? 0xC0000001 : 0;
      CloseServiceHandle(v7);
    }
    else
    {
      v5 = -1073741823;
    }
    CloseServiceHandle(v4);
    if ( v5 < 0 )
      goto LABEL_12;
    v2 = RpcBindingBind(0, Binding, &unk_180005380);
    goto LABEL_10;
  }
  v5 = -1073741823;
LABEL_12:
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003228  mov     [rsp-8+arg_8], rbx
0x18000322d  mov     [rsp-8+arg_10], rsi
0x180003232  push    rbp
0x180003233  push    rdi
0x180003234  push    r14
0x180003236  lea     rbp, [rsp-47h]
0x18000323b  sub     rsp, 0E0h
0x180003242  mov     rax, cs:__security_cookie
0x180003249  xor     rax, rsp
0x18000324c  mov     [rbp+57h+var_20], rax
0x180003250  xor     eax, eax
0x180003252  mov     [rbp+57h+var_78], 101h
0x180003259  xorps   xmm0, xmm0
0x18000325c  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180003260  mov     qword ptr [rbp+57h+Security+4], rax
0x180003264  lea     r9, [rbp+57h+Binding]; Binding
0x180003268  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], eax
0x18000326b  lea     r8, [rbp+57h+Options]; Options
0x18000326f  mov     [rbp+57h+Security.AuthIdentity], rax
0x180003273  lea     rdx, [rbp+57h+Security]; Security
0x180003277  mov     r14, rcx
0x18000327a  mov     [rbp+57h+var_74], 5000000h
0x180003281  mov     ecx, 1
0x180003286  mov     [rbp+57h+var_70], 12h
0x18000328d  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180003291  mov     [rbp+57h+Template.Version], ecx
0x180003294  mov     [rbp+57h+Options.Version], ecx
0x180003297  lea     eax, [rcx+2]
0x18000329a  mov     [rbp+57h+Options.Flags], ecx
0x18000329d  mov     [rbp+57h+Template.ProtocolSequence], eax
0x1800032a0  mov     [rbp+57h+var_A0], eax
0x1800032a3  mov     [rbp+57h+var_94], eax
0x1800032a6  lea     rax, [rbp+57h+var_78]
0x1800032aa  mov     [rbp+57h+var_80], rax
0x1800032ae  lea     rax, [rbp+57h+var_A0]
0x1800032b2  mov     [rbp+57h+var_9C], ecx
0x1800032b5  mov     [rbp+57h+var_98], ecx
0x1800032b8  mov     [rbp+57h+Security.Version], ecx
0x1800032bb  lea     rcx, [rbp+57h+Template]; Template
0x1800032bf  mov     [rbp+57h+Security.SecurityQos], rax
0x1800032c3  mov     [rbp+57h+Binding], 0
0x1800032cb  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x1800032cf  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x1800032d7  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x1800032db  mov     [rbp+57h+Security.AuthnLevel], 6
0x1800032e2  movdqu  [rbp+57h+var_90], xmm0
0x1800032e7  mov     [rbp+57h+Security.AuthnSvc], 14h
0x1800032ee  call    cs:__imp_RpcBindingCreateW
0x1800032f4  test    eax, eax
0x1800032f6  jnz     loc_1800033B0
0x1800032fc  mov     rdx, [rbp+57h+Binding]; Binding
0x180003300  lea     r8, unk_180005380; IfSpec
0x180003307  xor     ecx, ecx; pAsync
0x180003309  call    cs:__imp_RpcBindingBind
0x18000330f  cmp     eax, 6D9h
0x180003314  jnz     loc_1800033AC
0x18000331a  mov     ebx, 4
0x18000331f  xor     edx, edx; lpDatabaseName
0x180003321  mov     r8d, ebx; dwDesiredAccess
0x180003324  xor     ecx, ecx; lpMachineName
0x180003326  call    cs:__imp_OpenSCManagerW
0x18000332c  mov     rdi, rax
0x18000332f  test    rax, rax
0x180003332  jnz     short loc_18000333E
0x180003334  mov     ebx, 0C0000001h
0x180003339  jmp     loc_1800033BE
0x18000333e  mov     r8d, ebx; dwDesiredAccess
0x180003341  lea     rdx, ServiceName; "BrokerInfrastructure"
0x180003348  mov     rcx, rdi; hSCManager
0x18000334b  call    cs:__imp_OpenServiceW
0x180003351  mov     rsi, rax
0x180003354  test    rax, rax
0x180003357  jnz     short loc_180003360
0x180003359  mov     ebx, 0C0000001h
0x18000335e  jmp     short loc_18000338C
0x180003360  xor     r9d, r9d
0x180003363  mov     r8d, 1D4C0h
0x180003369  mov     rcx, rsi
0x18000336c  lea     edx, [r9+8]
0x180003370  call    cs:__imp_WaitServiceState
0x180003376  sub     eax, ebx
0x180003378  mov     rcx, rsi; hSCObject
0x18000337b  neg     eax
0x18000337d  mov     ebx, 0C0000001h
0x180003382  sbb     eax, eax
0x180003384  and     ebx, eax
0x180003386  call    cs:__imp_CloseServiceHandle
0x18000338c  mov     rcx, rdi; hSCObject
0x18000338f  call    cs:__imp_CloseServiceHandle
0x180003395  test    ebx, ebx
0x180003397  js      short loc_1800033BE
0x180003399  mov     rdx, [rbp+57h+Binding]; Binding
0x18000339d  lea     r8, unk_180005380; IfSpec
0x1800033a4  xor     ecx, ecx; pAsync
0x1800033a6  call    cs:__imp_RpcBindingBind
0x1800033ac  test    eax, eax
0x1800033ae  jz      short loc_1800033D1
0x1800033b0  mov     ecx, eax; Status
0x1800033b2  call    cs:__imp_I_RpcMapWin32Status
0x1800033b8  mov     ebx, eax
0x1800033ba  test    eax, eax
0x1800033bc  jns     short loc_1800033DA
0x1800033be  cmp     [rbp+57h+Binding], 0
0x1800033c3  jz      short loc_1800033DA
0x1800033c5  lea     rcx, [rbp+57h+Binding]; Binding
0x1800033c9  call    cs:__imp_RpcBindingFree
0x1800033cf  jmp     short loc_1800033DA
0x1800033d1  mov     rax, [rbp+57h+Binding]
0x1800033d5  xor     ebx, ebx
0x1800033d7  mov     [r14], rax
0x1800033da  mov     eax, ebx
0x1800033dc  mov     rcx, [rbp+57h+var_20]
0x1800033e0  xor     rcx, rsp; StackCookie
0x1800033e3  call    __security_check_cookie
0x1800033e8  lea     r11, [rsp+0F0h+var_10]
0x1800033f0  mov     rbx, [r11+28h]
0x1800033f4  mov     rsi, [r11+30h]
0x1800033f8  mov     rsp, r11
0x1800033fb  pop     r14
0x1800033fd  pop     rdi
0x1800033fe  pop     rbp
0x1800033ff  retn
```
