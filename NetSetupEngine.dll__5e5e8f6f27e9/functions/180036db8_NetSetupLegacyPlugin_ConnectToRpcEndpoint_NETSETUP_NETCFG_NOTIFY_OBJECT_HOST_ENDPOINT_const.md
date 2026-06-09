# NetSetupLegacyPlugin::ConnectToRpcEndpoint(_NETSETUP_NETCFG_NOTIFY_OBJECT_HOST_ENDPOINT const &)

- ea: `0x180036db8`
- end: `0x1800370d8`
- name: `?ConnectToRpcEndpoint@NetSetupLegacyPlugin@@AEAAXAEBU_NETSETUP_NETCFG_NOTIFY_OBJECT_HOST_ENDPOINT@@@Z`
- size: `800`
- prototype: `void __fastcall(RPC_BINDING_HANDLE *Binding, const struct _NETSETUP_NETCFG_NOTIFY_OBJECT_HOST_ENDPOINT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003690c`

## callees

- `0x180036db8`
- `0x1800370e0`
- `0x18005097c`
- `0x18005b034`
- `0x18005b134`
- `0x18005c848`
- `0x180065035`
- `0x1800810d0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180036ea4`
- `RPCRT4!RpcBindingCreateW` at `0x180036ea4`
- `RPCRT4!RpcBindingSetOption` at `0x180036f88`
- `RPCRT4!RpcBindingSetOption` at `0x180036f88`
- `RPCRT4!RpcBindingBind` at `0x180036f15`
- `RPCRT4!RpcBindingBind` at `0x180036f15`

## pseudocode

```c
void __fastcall NetSetupLegacyPlugin::ConnectToRpcEndpoint(
        RPC_BINDING_HANDLE *Binding,
        const struct _NETSETUP_NETCFG_NOTIFY_OBJECT_HOST_ENDPOINT *a2)
{
  __int64 v2; // r8
  unsigned int v5; // eax
  unsigned int v6; // edi
  RPC_BINDING_HANDLE v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // edi
  RPC_BINDING_HANDLE v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  int v14; // edi
  bool v15; // zf
  _QWORD v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v18[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v19; // [rsp+120h] [rbp+20h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+130h] [rbp+30h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v22[64]; // [rsp+190h] [rbp+90h] BYREF

  v2 = *(unsigned int *)a2;
  memset(&Template, 0, sizeof(Template));
  memset(&Security, 0, sizeof(Security));
  memset(v18, 0, sizeof(v18));
  v19 = 0;
  swprintf_s<32>(v22, L"NetCfgNotify-%08x", v2);
  Template.ProtocolSequence = 3;
  *(_QWORD *)&Template.Version = 1;
  Template.StringEndpoint = (unsigned __int16 *)v22;
  Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v18;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  *(_QWORD *)&v18[0] = 4;
  DWORD2(v18[0]) = 1;
  *(_QWORD *)((char *)v18 + 12) = 2;
  *(_QWORD *)&v19 = 0;
  DWORD2(v19) = 0;
  v5 = RpcBindingCreateW(&Template, &Security, 0, Binding);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids, v5);
    HResultException::HResultException((HResultException *)pExceptionObject, v6 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  v7 = *Binding;
  *((_DWORD *)Binding + 8) = 1;
  v8 = RpcBindingBind(0, v7, qword_180090310);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids, v8);
    HResultException::HResultException((HResultException *)pExceptionObject, v9 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  v10 = *Binding;
  *((_DWORD *)Binding + 8) = 2;
  v11 = RpcBindingSetOption(v10, 0xDu, 1u);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids, v11);
    HResultException::HResultException((HResultException *)pExceptionObject, v12 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  v16[0] = Binding;
  v16[1] = a2;
  v13 = NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_ad95adbec8f9c7e255192ae81e671132___(Binding, v16);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids,
        (unsigned int)v13);
    HResultException::HResultException((HResultException *)pExceptionObject, v14);
    throw (HResultException *)pExceptionObject;
  }
  v15 = *((_DWORD *)Binding + 9) == 0;
  *((_DWORD *)Binding + 8) = 3;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147418097);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180036db8  mov     [rsp-8+arg_10], rbx
0x180036dbd  mov     [rsp-8+arg_18], rsi
0x180036dc2  push    rbp
0x180036dc3  push    rdi
0x180036dc4  push    r12
0x180036dc6  lea     rbp, [rsp-0E0h]
0x180036dce  sub     rsp, 1E0h
0x180036dd5  mov     rax, cs:__security_cookie
0x180036ddc  xor     rax, rsp
0x180036ddf  mov     [rbp+0F0h+var_20], rax
0x180036de6  mov     r8d, [rdx]
0x180036de9  xorps   xmm0, xmm0
0x180036dec  xorps   xmm1, xmm1
0x180036def  xor     eax, eax
0x180036df1  mov     rsi, rdx
0x180036df4  mov     qword ptr [rbp+0F0h+Template.ObjectUuid.Data4], rax
0x180036dfb  mov     rbx, rcx
0x180036dfe  mov     [rbp+0F0h+Security.SecurityQos], rax
0x180036e02  lea     rdx, aNetcfgnotify08; "NetCfgNotify-%08x"
0x180036e09  lea     rcx, [rbp+0F0h+var_60]
0x180036e10  movups  xmmword ptr [rbp+0F0h+Template.Version], xmm0
0x180036e14  movups  xmmword ptr [rbp+0F0h+Template.NetworkAddress], xmm0
0x180036e18  movups  xmmword ptr [rbp+0F0h+Template.u1], xmm0
0x180036e1c  movups  xmmword ptr [rbp+0F0h+Security.Version], xmm0
0x180036e20  movups  xmmword ptr [rbp+0F0h+Security.AuthnLevel], xmm0
0x180036e24  movups  [rbp+0F0h+var_F0], xmm1
0x180036e28  movups  [rbp+0F0h+var_E0], xmm1
0x180036e2c  movups  [rbp+0F0h+var_D0], xmm1
0x180036e30  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@_WPEB_WZZ; swprintf_s<32>(wchar_t (&)[32],wchar_t const *,...)
0x180036e35  mov     r12d, 1
0x180036e3b  mov     [rbp+0F0h+Template.ProtocolSequence], 3
0x180036e42  lea     rax, [rbp+0F0h+var_60]
0x180036e49  mov     qword ptr [rbp+0F0h+Template.Version], r12
0x180036e4d  mov     [rbp+0F0h+Template.StringEndpoint], rax
0x180036e51  lea     rdx, [rbp+0F0h+Security]; Security
0x180036e55  lea     rax, [rbp+0F0h+var_F0]
0x180036e59  mov     [rbp+0F0h+Security.Version], r12d
0x180036e5d  mov     r9, rbx; Binding
0x180036e60  mov     [rbp+0F0h+Security.SecurityQos], rax
0x180036e64  xor     r8d, r8d; Options
0x180036e67  mov     [rbp+0F0h+Security.ServerPrincName], 0
0x180036e6f  lea     rcx, [rbp+0F0h+Template]; Template
0x180036e73  mov     [rbp+0F0h+Security.AuthnLevel], 6
0x180036e7a  mov     [rbp+0F0h+Security.AuthnSvc], 14h
0x180036e81  mov     qword ptr [rbp+0F0h+var_F0], 4
0x180036e89  mov     dword ptr [rbp+0F0h+var_F0+8], r12d
0x180036e8d  mov     qword ptr [rbp+0F0h+var_F0+0Ch], 2
0x180036e95  mov     qword ptr [rbp+0F0h+var_D0], 0
0x180036e9d  mov     dword ptr [rbp+0F0h+var_D0+8], 0
0x180036ea4  call    cs:__imp_RpcBindingCreateW
0x180036eaa  mov     edi, eax
0x180036eac  test    eax, eax
0x180036eae  jz      short loc_180036F05
0x180036eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036eb7  lea     rdx, WPP_GLOBAL_Control
0x180036ebe  cmp     rcx, rdx
0x180036ec1  jz      short loc_180036EE1
0x180036ec3  cmp     byte ptr [rcx+19h], 2
0x180036ec7  jb      short loc_180036EE1
0x180036ec9  mov     rcx, [rcx+10h]
0x180036ecd  lea     edx, [r12+17h]
0x180036ed2  mov     r9d, eax
0x180036ed5  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x180036edc  call    WPP_SF_d
0x180036ee1  or      edi, 80010000h
0x180036ee7  lea     rcx, [rsp+1F0h+pExceptionObject]; this
0x180036eec  mov     edx, edi; int
0x180036eee  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180036ef3  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180036efa  lea     rcx, [rsp+1F0h+pExceptionObject]; pExceptionObject
0x180036eff  call    _CxxThrowException_0
0x180036f05  mov     rdx, [rbx]; Binding
0x180036f08  lea     r8, qword_180090310; IfSpec
0x180036f0f  xor     ecx, ecx; pAsync
0x180036f11  mov     [rbx+20h], r12d
0x180036f15  call    cs:__imp_RpcBindingBind
0x180036f1b  mov     edi, eax
0x180036f1d  test    eax, eax
0x180036f1f  jz      short loc_180036F76
0x180036f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f28  lea     rdx, WPP_GLOBAL_Control
0x180036f2f  cmp     rcx, rdx
0x180036f32  jz      short loc_180036F52
0x180036f34  cmp     byte ptr [rcx+19h], 2
0x180036f38  jb      short loc_180036F52
0x180036f3a  mov     rcx, [rcx+10h]
0x180036f3e  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x180036f45  mov     edx, 19h
0x180036f4a  mov     r9d, eax
0x180036f4d  call    WPP_SF_d
0x180036f52  or      edi, 80010000h
0x180036f58  lea     rcx, [rsp+1F0h+pExceptionObject]; this
0x180036f5d  mov     edx, edi; int
0x180036f5f  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180036f64  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180036f6b  lea     rcx, [rsp+1F0h+pExceptionObject]; pExceptionObject
0x180036f70  call    _CxxThrowException_0
0x180036f76  mov     rcx, [rbx]; hBinding
0x180036f79  mov     r8, r12; optionValue
0x180036f7c  mov     edx, 0Dh; option
0x180036f81  mov     dword ptr [rbx+20h], 2
0x180036f88  call    cs:__imp_RpcBindingSetOption
0x180036f8e  mov     edi, eax
0x180036f90  test    eax, eax
0x180036f92  jz      short loc_180036FE9
0x180036f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f9b  lea     rdx, WPP_GLOBAL_Control
0x180036fa2  cmp     rcx, rdx
0x180036fa5  jz      short loc_180036FC5
0x180036fa7  cmp     byte ptr [rcx+19h], 2
0x180036fab  jb      short loc_180036FC5
0x180036fad  mov     rcx, [rcx+10h]
0x180036fb1  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x180036fb8  mov     edx, 1Ah
0x180036fbd  mov     r9d, eax
0x180036fc0  call    WPP_SF_d
0x180036fc5  or      edi, 80010000h
0x180036fcb  lea     rcx, [rsp+1F0h+pExceptionObject]; this
0x180036fd0  mov     edx, edi; int
0x180036fd2  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180036fd7  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180036fde  lea     rcx, [rsp+1F0h+pExceptionObject]; pExceptionObject
0x180036fe3  call    _CxxThrowException_0
0x180036fe9  lea     rdx, [rsp+1F0h+var_1D0]
0x180036fee  mov     [rsp+1F0h+var_1D0], rbx
0x180036ff3  mov     rcx, rbx
0x180036ff6  mov     [rsp+1F0h+var_1C8], rsi
0x180036ffb  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_ad95adbec8f9c7e255192ae81e671132___
0x180037000  mov     edi, eax
0x180037002  test    eax, eax
0x180037004  jns     short loc_180037055
0x180037006  mov     rcx, cs:WPP_GLOBAL_Control
0x18003700d  lea     rdx, WPP_GLOBAL_Control
0x180037014  cmp     rcx, rdx
0x180037017  jz      short loc_180037037
0x180037019  cmp     byte ptr [rcx+19h], 2
0x18003701d  jb      short loc_180037037
0x18003701f  mov     rcx, [rcx+10h]
0x180037023  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x18003702a  mov     edx, 1Bh
0x18003702f  mov     r9d, eax
0x180037032  call    WPP_SF_d
0x180037037  mov     edx, edi; int
0x180037039  lea     rcx, [rsp+1F0h+pExceptionObject]; this
0x18003703e  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180037043  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18003704a  lea     rcx, [rsp+1F0h+pExceptionObject]; pExceptionObject
0x18003704f  call    _CxxThrowException_0
0x180037055  cmp     dword ptr [rbx+24h], 0
0x180037059  mov     dword ptr [rbx+20h], 3
0x180037060  jnz     short loc_1800370B1
0x180037062  mov     rcx, cs:WPP_GLOBAL_Control
0x180037069  lea     rdx, WPP_GLOBAL_Control
0x180037070  cmp     rcx, rdx
0x180037073  jz      short loc_180037090
0x180037075  cmp     byte ptr [rcx+19h], 2
0x180037079  jb      short loc_180037090
0x18003707b  mov     rcx, [rcx+10h]
0x18003707f  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x180037086  mov     edx, 1Ch
0x18003708b  call    WPP_SF_
0x180037090  mov     edx, 8001000Fh; int
0x180037095  lea     rcx, [rsp+1F0h+pExceptionObject]; this
0x18003709a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18003709f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800370a6  lea     rcx, [rsp+1F0h+pExceptionObject]; pExceptionObject
0x1800370ab  call    _CxxThrowException_0
0x1800370b1  mov     rcx, [rbp+0F0h+var_20]
0x1800370b8  xor     rcx, rsp; StackCookie
0x1800370bb  call    __security_check_cookie
0x1800370c0  lea     r11, [rsp+1F0h+var_10]
0x1800370c8  mov     rbx, [r11+30h]
0x1800370cc  mov     rsi, [r11+38h]
0x1800370d0  mov     rsp, r11
0x1800370d3  pop     r12
0x1800370d5  pop     rdi
0x1800370d6  pop     rbp
0x1800370d7  retn
```
