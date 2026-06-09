# WwanUpdateIPStack

- ea: `0x140046d80`
- end: `0x14004732e`
- name: `WwanUpdateIPStack`
- size: `1454`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x140006d90`

## callees

- `0x140001cf8`
- `0x140001ea4`
- `0x1400429a0`
- `0x140042bf4`
- `0x140042e30`
- `0x1400432ec`
- `0x140043eb4`
- `0x140045688`
- `0x1400469e8`
- `0x140046d80`
- `0x140047e50`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140046f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004702d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047301`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004702d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047301`
- `NETIO!InitializeIpInterfaceEntry` at `0x140047061`
- `NETIO!InitializeIpInterfaceEntry` at `0x140047109`
- `NETIO!InitializeIpInterfaceEntry` at `0x140047061`
- `NETIO!InitializeIpInterfaceEntry` at `0x140047109`
- `NETIO!SetIpInterfaceEntry` at `0x140047089`
- `NETIO!SetIpInterfaceEntry` at `0x140047131`
- `NETIO!SetIpInterfaceEntry` at `0x140047089`
- `NETIO!SetIpInterfaceEntry` at `0x140047131`

## pseudocode

```c
__int64 __fastcall WwanUpdateIPStack(
        void *a1,
        __int64 a2,
        union _NET_LUID_LH a3,
        struct _GUID *a4,
        NET_IFINDEX a5,
        char a6)
{
  struct _GUID v6; // xmm0
  unsigned int IPAddresses; // edi
  __int64 v8; // rbx
  int v10; // edx
  PVOID v11; // rsi
  int Value; // edx
  int v13; // edx
  PVOID v14; // rsi
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // r8d
  PVOID v21; // rsi
  PVOID v22; // r14
  int v23; // edx
  union _NET_LUID_LH *Source1; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+40h] [rbp-C0h]
  union _NET_LUID_LH v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID P; // [rsp+68h] [rbp-98h] BYREF
  PVOID v33; // [rsp+70h] [rbp-90h] BYREF
  PVOID v34; // [rsp+78h] [rbp-88h] BYREF
  PVOID v35; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v36; // [rsp+90h] [rbp-70h] BYREF
  _MIB_IPINTERFACE_ROW Row; // [rsp+A0h] [rbp-60h] BYREF

  v6 = *a4;
  IPAddresses = 0;
  v27.Value = a3.Value;
  v33 = 0;
  v8 = a2;
  v29 = 0;
  v35 = 0;
  v31 = 0;
  P = 0;
  v28 = 0;
  v34 = 0;
  v30 = 0;
  v36 = v6;
  if ( a6 )
  {
    if ( !*(_QWORD *)(a2 + 48) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        2,
        13,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids);
    }
    if ( (unsigned int)MbbIpGetLastIPAddresses(a1, 2u, (struct in_addr **)&P, &v28)
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_i(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        2,
        14,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
        v27.Value);
    }
    v11 = P;
    MbbIpEvaluateReportedDnsServers(
      *(struct _MBB_IPADDRESS_ENTRY **)(v8 + 48),
      *(_DWORD *)(v8 + 56),
      (struct _MBB_IPADDRESS_ENTRY *)P,
      v28,
      Source1,
      &v36);
    IPAddresses = MbbIpSetLastIPAddresses(a1, 2u, *(_QWORD *)(v8 + 48), *(_DWORD *)(v8 + 56));
    if ( IPAddresses && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Value = v27.Value;
      LOBYTE(Value) = 2;
      WPP_RECORDER_SF_i(
        WPP_GLOBAL_Control->DeviceExtension,
        Value,
        2,
        15,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
        v27.Value);
    }
    if ( v11 )
      ExFreePoolWithTag(v11, 0);
  }
  if ( *(_QWORD *)(v8 + 16) )
  {
    IPAddresses = MbbIpGetLastIPAddresses(a1, 0, (struct in_addr **)&v33, &v29);
    if ( IPAddresses && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_i(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        2,
        16,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
        v27.Value);
    }
    v14 = v33;
    MbbIpEvaluateReportedIp(
      *(struct _MBB_IPADDRESS_ENTRY **)(v8 + 16),
      *(_DWORD *)(v8 + 24),
      (struct _MBB_IPADDRESS_ENTRY *)v33,
      v29,
      &v27,
      a5);
    if ( a6 )
    {
      IPAddresses = MbbIpSetLastIPAddresses(a1, 0, *(_QWORD *)(v8 + 16), *(_DWORD *)(v8 + 24));
      if ( IPAddresses )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_i(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            2,
            17,
            (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
            v27.Value);
        }
      }
    }
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
  }
  if ( (*(_DWORD *)v8 & 8) != 0 )
  {
    if ( a6 )
    {
      memset(&Row, 0, sizeof(Row));
      InitializeIpInterfaceEntry(&Row);
      Row.InterfaceLuid = v27;
      Row.NlMtu = *(_DWORD *)(v8 + 8);
      Row.Family = 2;
      if ( SetIpInterfaceEntry(&Row) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_i(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            2,
            18,
            (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
            v27.Value);
        }
      }
    }
  }
  if ( (*(_DWORD *)(v8 + 4) & 8) != 0 )
  {
    if ( a6 )
    {
      memset(&Row, 0, sizeof(Row));
      InitializeIpInterfaceEntry(&Row);
      Row.InterfaceLuid = v27;
      Row.Family = 23;
      Row.NlMtu = *(_DWORD *)(v8 + 12);
      if ( SetIpInterfaceEntry(&Row) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = 2;
          WPP_RECORDER_SF_i(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            2,
            19,
            (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
            v27.Value);
        }
      }
    }
  }
  if ( *(_QWORD *)(v8 + 32) )
  {
    if ( (unsigned int)MbbIpGetLastIPAddresses(a1, 1u, (struct in_addr **)&v35, &v31)
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_i(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        2,
        20,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
        v27.Value);
    }
    IPAddresses = MbbIpGetDhcpDefaultGatewayAddressTable((struct _MBB_IPADDRESS_ENTRY **)&v34, &v30, &v36);
    if ( IPAddresses && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_id(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        v20,
        21,
        (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
        v27.Value,
        IPAddresses);
    v21 = v34;
    v22 = v35;
    MbbIpEvaluateReportedRoutes(
      *(struct _MBB_IPADDRESS_ENTRY **)(v8 + 32),
      *(_DWORD *)(v8 + 40),
      (struct _MBB_IPADDRESS_ENTRY *)v35,
      v31,
      (struct _MBB_IPADDRESS_ENTRY *)v34,
      v30,
      &v27,
      a5,
      v26);
    if ( a6 )
    {
      IPAddresses = MbbIpSetLastIPAddresses(a1, 1u, *(_QWORD *)(v8 + 32), *(_DWORD *)(v8 + 40));
      if ( IPAddresses )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_i(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            2,
            22,
            (__int64)&WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids,
            v27.Value);
        }
      }
    }
    if ( v22 )
      ExFreePoolWithTag(v22, 0);
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
  }
  return IPAddresses;
}

```

## disassembly

```asm
0x140046d80  push    rbp
0x140046d82  push    rbx
0x140046d83  push    rsi
0x140046d84  push    rdi
0x140046d85  push    r12
0x140046d87  push    r14
0x140046d89  push    r15
0x140046d8b  lea     rbp, [rsp-60h]
0x140046d90  sub     rsp, 160h
0x140046d97  mov     rax, cs:__security_cookie
0x140046d9e  xor     rax, rsp
0x140046da1  mov     [rbp+90h+var_40], rax
0x140046da5  movups  xmm0, xmmword ptr [r9]
0x140046da9  mov     r12b, [rbp+90h+arg_28]
0x140046db0  lea     rsi, WPP_RECORDER_INITIALIZED
0x140046db7  xor     edi, edi
0x140046db9  mov     qword ptr [rsp+190h+var_140], r8
0x140046dbe  mov     [rsp+190h+var_120], 0
0x140046dc7  mov     rbx, rdx
0x140046dca  mov     [rsp+190h+var_134], 0
0x140046dd2  mov     r15, rcx
0x140046dd5  mov     [rbp+90h+var_110], 0
0x140046ddd  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140046de4  mov     [rsp+190h+var_12C], 0
0x140046dec  lea     r14d, [rdi+2]
0x140046df0  mov     [rsp+190h+P], 0
0x140046df9  mov     [rsp+190h+var_138], 0
0x140046e01  mov     [rsp+190h+var_118], rdi
0x140046e06  mov     [rsp+190h+var_130], edi
0x140046e0a  movdqu  xmmword ptr [rbp+90h+var_100.Data1], xmm0
0x140046e0f  test    r12b, r12b
0x140046e12  jz      loc_140046F33
0x140046e18  cmp     [rdx+30h], rdi
0x140046e1c  jnz     short loc_140046E45
0x140046e1e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140046e25  jz      short loc_140046E45
0x140046e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e2e  lea     r9d, [rdi+0Dh]
0x140046e32  mov     r8d, r14d
0x140046e35  mov     [rsp+190h+Source1], rax
0x140046e3a  mov     dl, 4
0x140046e3c  mov     rcx, [rcx+40h]
0x140046e40  call    WPP_RECORDER_SF_
0x140046e45  lea     r9, [rsp+190h+var_138]
0x140046e4a  mov     edx, r14d
0x140046e4d  lea     r8, [rsp+190h+P]
0x140046e52  mov     rcx, r15
0x140046e55  call    ?MbbIpGetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAPEAU_MBB_IPADDRESS_ENTRY@@PEAK@Z; MbbIpGetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY * *,ulong *)
0x140046e5a  test    eax, eax
0x140046e5c  jz      short loc_140046E99
0x140046e5e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140046e65  jz      short loc_140046E99
0x140046e67  mov     rax, qword ptr [rsp+190h+var_140]
0x140046e6c  mov     r9d, 0Eh
0x140046e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e79  mov     r8d, r14d
0x140046e7c  mov     [rsp+190h+var_168], rax
0x140046e81  mov     dl, r14b
0x140046e84  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140046e8b  mov     [rsp+190h+Source1], rax; union _NET_LUID_LH *
0x140046e90  mov     rcx, [rcx+40h]
0x140046e94  call    WPP_RECORDER_SF_i
0x140046e99  mov     rsi, [rsp+190h+P]
0x140046e9e  lea     rax, [rbp+90h+var_100]
0x140046ea2  mov     r9d, [rsp+190h+var_138]; unsigned int
0x140046ea7  mov     r8, rsi; struct _MBB_IPADDRESS_ENTRY *
0x140046eaa  mov     edx, [rbx+38h]; unsigned int
0x140046ead  mov     rcx, [rbx+30h]; struct _MBB_IPADDRESS_ENTRY *
0x140046eb1  mov     [rsp+190h+var_168], rax; struct _GUID *
0x140046eb6  call    ?MbbIpEvaluateReportedDnsServers@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0KPEAT_NET_LUID_LH@@PEAU_GUID@@@Z; MbbIpEvaluateReportedDnsServers(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,_GUID *)
0x140046ebb  mov     r9d, [rbx+38h]
0x140046ebf  mov     edx, r14d
0x140046ec2  mov     r8, [rbx+30h]
0x140046ec6  mov     rcx, r15
0x140046ec9  call    ?MbbIpSetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAU_MBB_IPADDRESS_ENTRY@@K@Z; MbbIpSetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY *,ulong)
0x140046ece  mov     edi, eax
0x140046ed0  test    eax, eax
0x140046ed2  jz      short loc_140046F16
0x140046ed4  lea     rax, WPP_RECORDER_INITIALIZED
0x140046edb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140046ee2  jz      short loc_140046F16
0x140046ee4  mov     rdx, qword ptr [rsp+190h+var_140]
0x140046ee9  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140046ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x140046ef7  mov     r9d, 0Fh
0x140046efd  mov     [rsp+190h+var_168], rdx
0x140046f02  mov     r8d, r14d
0x140046f05  mov     dl, r14b
0x140046f08  mov     [rsp+190h+Source1], rax
0x140046f0d  mov     rcx, [rcx+40h]
0x140046f11  call    WPP_RECORDER_SF_i
0x140046f16  test    rsi, rsi
0x140046f19  jz      short loc_140046F2C
0x140046f1b  xor     edx, edx; Tag
0x140046f1d  mov     rcx, rsi; P
0x140046f20  call    cs:__imp_ExFreePoolWithTag
0x140046f27  nop     dword ptr [rax+rax+00h]
0x140046f2c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140046f33  cmp     qword ptr [rbx+10h], 0
0x140046f38  mov     r14d, [rbp+90h+arg_20]
0x140046f3f  jz      loc_140047039
0x140046f45  lea     r9, [rsp+190h+var_134]
0x140046f4a  xor     edx, edx
0x140046f4c  lea     r8, [rsp+190h+var_120]
0x140046f51  mov     rcx, r15
0x140046f54  call    ?MbbIpGetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAPEAU_MBB_IPADDRESS_ENTRY@@PEAK@Z; MbbIpGetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY * *,ulong *)
0x140046f59  mov     edi, eax
0x140046f5b  test    eax, eax
0x140046f5d  jz      short loc_140046F9B
0x140046f5f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140046f66  jz      short loc_140046F9B
0x140046f68  mov     rax, qword ptr [rsp+190h+var_140]
0x140046f6d  mov     r9d, 10h
0x140046f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140046f7a  mov     [rsp+190h+var_168], rax
0x140046f7f  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140046f86  mov     [rsp+190h+Source1], rax
0x140046f8b  lea     r8d, [r9-0Eh]
0x140046f8f  mov     rcx, [rcx+40h]
0x140046f93  mov     dl, r8b
0x140046f96  call    WPP_RECORDER_SF_i
0x140046f9b  mov     rsi, [rsp+190h+var_120]
0x140046fa0  lea     rax, [rsp+190h+var_140]
0x140046fa5  mov     r9d, [rsp+190h+var_134]; unsigned int
0x140046faa  mov     r8, rsi; struct _MBB_IPADDRESS_ENTRY *
0x140046fad  mov     edx, [rbx+18h]; unsigned int
0x140046fb0  mov     rcx, [rbx+10h]; struct _MBB_IPADDRESS_ENTRY *
0x140046fb4  mov     dword ptr [rsp+190h+var_168], r14d; unsigned int
0x140046fb9  mov     [rsp+190h+Source1], rax; Source1
0x140046fbe  call    ?MbbIpEvaluateReportedIp@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0KPEAT_NET_LUID_LH@@K@Z; MbbIpEvaluateReportedIp(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)
0x140046fc3  test    r12b, r12b
0x140046fc6  jz      short loc_140047023
0x140046fc8  mov     r9d, [rbx+18h]
0x140046fcc  xor     edx, edx
0x140046fce  mov     r8, [rbx+10h]
0x140046fd2  mov     rcx, r15
0x140046fd5  call    ?MbbIpSetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAU_MBB_IPADDRESS_ENTRY@@K@Z; MbbIpSetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY *,ulong)
0x140046fda  mov     edi, eax
0x140046fdc  test    eax, eax
0x140046fde  jz      short loc_140047023
0x140046fe0  lea     rax, WPP_RECORDER_INITIALIZED
0x140046fe7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140046fee  jz      short loc_140047023
0x140046ff0  mov     rax, qword ptr [rsp+190h+var_140]
0x140046ff5  mov     r9d, 11h
0x140046ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140047002  mov     [rsp+190h+var_168], rax
0x140047007  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x14004700e  mov     [rsp+190h+Source1], rax
0x140047013  lea     r8d, [r9-0Fh]
0x140047017  mov     rcx, [rcx+40h]
0x14004701b  mov     dl, r8b
0x14004701e  call    WPP_RECORDER_SF_i
0x140047023  test    rsi, rsi
0x140047026  jz      short loc_140047039
0x140047028  xor     edx, edx; Tag
0x14004702a  mov     rcx, rsi; P
0x14004702d  call    cs:__imp_ExFreePoolWithTag
0x140047034  nop     dword ptr [rax+rax+00h]
0x140047039  mov     eax, [rbx]
0x14004703b  test    al, 8
0x14004703d  jz      loc_1400470DB
0x140047043  test    r12b, r12b
0x140047046  jz      loc_1400470DB
0x14004704c  xor     edx, edx; Val
0x14004704e  lea     rcx, [rbp+90h+Row]; void *
0x140047052  mov     r8d, 0A8h; Size
0x140047058  call    memset
0x14004705d  lea     rcx, [rbp+90h+Row]; Row
0x140047061  call    cs:__imp_InitializeIpInterfaceEntry
0x140047068  nop     dword ptr [rax+rax+00h]
0x14004706d  mov     rax, qword ptr [rsp+190h+var_140]
0x140047072  lea     rcx, [rbp+90h+Row]; Row
0x140047076  mov     qword ptr [rbp+90h+Row.InterfaceLuid], rax
0x14004707a  mov     esi, 2
0x14004707f  mov     eax, [rbx+8]
0x140047082  mov     [rbp+90h+Row.NlMtu], eax
0x140047085  mov     [rbp+90h+Row.Family], si
0x140047089  call    cs:__imp_SetIpInterfaceEntry
0x140047090  nop     dword ptr [rax+rax+00h]
0x140047095  test    eax, eax
0x140047097  jz      short loc_1400470E0
0x140047099  lea     rax, WPP_RECORDER_INITIALIZED
0x1400470a0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400470a7  jz      short loc_1400470E0
0x1400470a9  mov     rax, qword ptr [rsp+190h+var_140]
0x1400470ae  lea     r9d, [rsi+10h]
0x1400470b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400470b9  mov     r8d, esi
0x1400470bc  mov     [rsp+190h+var_168], rax
0x1400470c1  mov     dl, sil
0x1400470c4  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x1400470cb  mov     [rsp+190h+Source1], rax
0x1400470d0  mov     rcx, [rcx+40h]
0x1400470d4  call    WPP_RECORDER_SF_i
0x1400470d9  jmp     short loc_1400470E0
0x1400470db  mov     esi, 2
0x1400470e0  mov     eax, [rbx+4]
0x1400470e3  test    al, 8
0x1400470e5  jz      loc_140047183
0x1400470eb  test    r12b, r12b
0x1400470ee  jz      loc_140047183
0x1400470f4  xor     edx, edx; Val
0x1400470f6  lea     rcx, [rbp+90h+Row]; void *
0x1400470fa  mov     r8d, 0A8h; Size
0x140047100  call    memset
0x140047105  lea     rcx, [rbp+90h+Row]; Row
0x140047109  call    cs:__imp_InitializeIpInterfaceEntry
0x140047110  nop     dword ptr [rax+rax+00h]
0x140047115  mov     rax, qword ptr [rsp+190h+var_140]
0x14004711a  lea     rcx, [rbp+90h+Row]; Row
0x14004711e  mov     qword ptr [rbp+90h+Row.InterfaceLuid], rax
0x140047122  mov     eax, 17h
0x140047127  mov     [rbp+90h+Row.Family], ax
0x14004712b  mov     eax, [rbx+0Ch]
0x14004712e  mov     [rbp+90h+Row.NlMtu], eax
0x140047131  call    cs:__imp_SetIpInterfaceEntry
0x140047138  nop     dword ptr [rax+rax+00h]
0x14004713d  test    eax, eax
0x14004713f  jz      short loc_140047183
0x140047141  lea     rax, WPP_RECORDER_INITIALIZED
0x140047148  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004714f  jz      short loc_140047183
0x140047151  mov     rax, qword ptr [rsp+190h+var_140]
0x140047156  mov     r9d, 13h
0x14004715c  mov     rcx, cs:WPP_GLOBAL_Control
0x140047163  mov     r8d, esi
0x140047166  mov     [rsp+190h+var_168], rax
0x14004716b  mov     dl, sil
0x14004716e  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140047175  mov     [rsp+190h+Source1], rax
0x14004717a  mov     rcx, [rcx+40h]
0x14004717e  call    WPP_RECORDER_SF_i
0x140047183  cmp     qword ptr [rbx+20h], 0
0x140047188  jz      loc_14004730D
0x14004718e  lea     r9, [rsp+190h+var_12C]
0x140047193  mov     edx, 1
0x140047198  lea     r8, [rbp+90h+var_110]
0x14004719c  mov     rcx, r15
0x14004719f  call    ?MbbIpGetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAPEAU_MBB_IPADDRESS_ENTRY@@PEAK@Z; MbbIpGetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY * *,ulong *)
0x1400471a4  test    eax, eax
0x1400471a6  jz      short loc_1400471EA
0x1400471a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400471af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400471b6  jz      short loc_1400471EA
0x1400471b8  mov     rax, qword ptr [rsp+190h+var_140]
0x1400471bd  mov     r9d, 14h
0x1400471c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400471ca  mov     r8d, esi
0x1400471cd  mov     [rsp+190h+var_168], rax
0x1400471d2  mov     dl, sil
0x1400471d5  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x1400471dc  mov     [rsp+190h+Source1], rax
0x1400471e1  mov     rcx, [rcx+40h]
0x1400471e5  call    WPP_RECORDER_SF_i
0x1400471ea  lea     r8, [rbp+90h+var_100]; struct _GUID *
0x1400471ee  lea     rdx, [rsp+190h+var_130]; unsigned int *
0x1400471f3  lea     rcx, [rsp+190h+var_118]; struct _MBB_IPADDRESS_ENTRY **
0x1400471f8  call    ?MbbIpGetDhcpDefaultGatewayAddressTable@@YAHPEAPEAU_MBB_IPADDRESS_ENTRY@@PEAKPEAU_GUID@@@Z; MbbIpGetDhcpDefaultGatewayAddressTable(_MBB_IPADDRESS_ENTRY * *,ulong *,_GUID *)
0x1400471fd  mov     edi, eax
0x1400471ff  test    eax, eax
0x140047201  jz      short loc_140047243
0x140047203  lea     rax, WPP_RECORDER_INITIALIZED
0x14004720a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047211  jz      short loc_140047243
0x140047213  mov     rax, qword ptr [rsp+190h+var_140]
0x140047218  mov     r9d, 15h
0x14004721e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047225  mov     dword ptr [rsp+190h+var_160], edi
0x140047229  mov     [rsp+190h+var_168], rax
0x14004722e  lea     rax, WPP_d533bf8b792a3d7f7174350879f31a6c_Traceguids
0x140047235  mov     [rsp+190h+Source1], rax
0x14004723a  mov     rcx, [rcx+40h]
0x14004723e  call    WPP_RECORDER_SF_id
0x140047243  mov     rsi, [rsp+190h+var_118]
0x140047248  lea     rax, [rsp+190h+var_140]
0x14004724d  mov     r9d, [rsp+190h+var_12C]; unsigned int
0x140047252  mov     edx, [rbx+28h]; unsigned int
0x140047255  mov     rcx, [rbx+20h]; struct _MBB_IPADDRESS_ENTRY *
0x140047259  mov     [rsp+190h+var_158], r14d; unsigned int
0x14004725e  mov     r14, [rbp+90h+var_110]
0x140047262  mov     [rsp+190h+var_160], rax; Source1
0x140047267  mov     r8, r14; struct _MBB_IPADDRESS_ENTRY *
0x14004726a  mov     eax, [rsp+190h+var_130]
0x14004726e  mov     dword ptr [rsp+190h+var_168], eax; unsigned int
0x140047272  mov     [rsp+190h+Source1], rsi; struct _MBB_IPADDRESS_ENTRY *
0x140047277  call    ?MbbIpEvaluateReportedRoutes@@YAXPEAU_MBB_IPADDRESS_ENTRY@@K0K0KPEAT_NET_LUID_LH@@KE@Z; MbbIpEvaluateReportedRoutes(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong,uchar)
0x14004727c  test    r12b, r12b
0x14004727f  jz      short loc_1400472E1
0x140047281  mov     r9d, [rbx+28h]
0x140047285  mov     edx, 1
0x14004728a  mov     r8, [rbx+20h]
0x14004728e  mov     rcx, r15
0x140047291  call    ?MbbIpSetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAU_MBB_IPADDRESS_ENTRY@@K@Z; MbbIpSetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY *,ulong)
0x140047296  mov     edi, eax
0x140047298  test    eax, eax
0x14004729a  jz      short loc_1400472E1
0x14004729c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400472a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400472aa  jz      short loc_1400472E1
  ... truncated ...
```
