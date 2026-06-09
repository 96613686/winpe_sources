# MbbIpGetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY * *,ulong *)

- ea: `0x140043eb4`
- end: `0x140044574`
- name: `?MbbIpGetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAPEAU_MBB_IPADDRESS_ENTRY@@PEAK@Z`
- size: `1728`
- prototype: `__int64 __fastcall(void *, unsigned int, struct in_addr **, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x140046d80`

## callees

- `0x140001db8`
- `0x14001c054`
- `0x140042488`
- `0x140043eb4`
- `0x14004457c`
- `0x140045b70`
- `0x140045c64`
- `0x140045d28`
- `0x140045e18`
- `0x140045f0c`
- `0x140046190`
- `0x140046284`
- `0x140047e50`
- `0x140048340`

## import_xrefs

- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400440a9`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x140044415`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400440a9`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x140044415`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044092`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x14004424b`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044340`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044092`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x14004424b`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140044340`
- `ntoskrnl!ExAllocatePool2` at `0x14004418f`
- `ntoskrnl!ExAllocatePool2` at `0x14004418f`
- `NDIS!NdisReadConfiguration` at `0x140043fdd`
- `NDIS!NdisReadConfiguration` at `0x140043fdd`
- `NDIS!NdisCloseConfiguration` at `0x14004453d`
- `NDIS!NdisCloseConfiguration` at `0x14004453d`
- `NDIS!NdisOpenConfigurationEx` at `0x140043f36`
- `NDIS!NdisOpenConfigurationEx` at `0x140043f36`

## pseudocode

```c
__int64 __fastcall MbbIpGetLastIPAddresses(void *a1, unsigned int a2, struct in_addr **a3, _DWORD *a4)
{
  struct in_addr **v4; // rbx
  unsigned int v5; // r12d
  unsigned int v6; // r15d
  unsigned int v7; // r13d
  struct in_addr *v8; // rsi
  NDIS_STATUS v9; // eax
  int v10; // edx
  __int32 v11; // edx
  int v12; // r8d
  unsigned int i; // ebx
  UNICODE_STRING *p_Keyword; // r9
  unsigned int v15; // esi
  int v16; // r9d
  const WCHAR *Buffer; // rcx
  NTSTATUS v18; // eax
  int v19; // r9d
  bool v20; // zf
  __int64 v21; // r13
  struct in_addr *Pool2; // rax
  __int64 v23; // rbx
  __int64 v24; // r12
  __int64 v25; // r13
  NTSTATUS v26; // eax
  int v27; // r9d
  unsigned __int8 *p_s_b1; // rax
  struct in_addr *v29; // r13
  NTSTATUS v30; // eax
  int v31; // r9d
  unsigned __int64 v32; // rax
  __int64 v33; // r13
  struct in_addr *v34; // rsi
  NTSTATUS v35; // eax
  int v36; // r9d
  struct in_addr *v37; // rsi
  _DWORD *v38; // rcx
  int ParameterType; // [rsp+20h] [rbp-A9h]
  LPCWSTR Terminator; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int8 v42[4]; // [rsp+48h] [rbp-81h] BYREF
  int Status; // [rsp+4Ch] [rbp-7Dh] BYREF
  unsigned int v44; // [rsp+50h] [rbp-79h]
  unsigned int v45; // [rsp+54h] [rbp-75h]
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+58h] [rbp-71h] BYREF
  PNDIS_CONFIGURATION_PARAMETER v47; // [rsp+60h] [rbp-69h]
  struct in_addr *v48; // [rsp+68h] [rbp-61h]
  PNDIS_CONFIGURATION_PARAMETER v49; // [rsp+70h] [rbp-59h]
  struct in_addr Addr; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v51; // [rsp+7Ch] [rbp-4Dh]
  PVOID ConfigurationHandle; // [rsp+80h] [rbp-49h] BYREF
  struct in_addr **v53; // [rsp+88h] [rbp-41h]
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+90h] [rbp-39h] BYREF
  _DWORD *v55; // [rsp+A8h] [rbp-21h]
  __int128 v56; // [rsp+B0h] [rbp-19h] BYREF
  UNICODE_STRING Keyword; // [rsp+C0h] [rbp-9h] BYREF
  struct in6_addr v58; // [rsp+D0h] [rbp+7h] BYREF

  v51 = a2;
  ConfigObject.NdisHandle = a1;
  v4 = a3;
  Terminator = 0;
  v5 = a2;
  v53 = a3;
  Addr = 0;
  ConfigurationHandle = 0;
  v6 = 0;
  v48 = 0;
  v7 = 0;
  *(_QWORD *)&ConfigObject.Flags = 0;
  v58 = 0;
  v8 = 0;
  v55 = a4;
  Keyword = 0;
  *(_QWORD *)&ConfigObject.Header.Type = 1573289;
  v56 = 0;
  v9 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = v9;
  if ( !v9 )
  {
    v49 = 0;
    v47 = 0;
    MbbIpAddressTableIdToRegistryValueName(v5, &Keyword, &v56);
    for ( i = 0; i < 2; ++i )
    {
      ParameterValue = 0;
      p_Keyword = (UNICODE_STRING *)&v56;
      if ( !i )
        p_Keyword = &Keyword;
      v15 = 0;
      NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, p_Keyword, NdisParameterString);
      v11 = Status;
      if ( Status )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Ldd(
            WPP_GLOBAL_Control->DeviceExtension,
            Status,
            v12,
            v16,
            ParameterType,
            v5,
            i != 0 ? 6 : 4,
            Status);
      }
      else
      {
        v11 = ParameterValue->ParameterType;
        if ( ParameterValue->ParameterType == NdisParameterString )
        {
          Buffer = ParameterValue->ParameterData.StringData.Buffer;
          Terminator = Buffer;
          while ( 1 )
          {
            v42[0] = 0;
            v18 = i
                ? RtlIpv6StringToAddressW(Buffer, &Terminator, &v58)
                : RtlIpv4StringToAddressW(Buffer, 1u, &Terminator, &Addr);
            v11 = v18;
            if ( v18 )
              break;
            if ( !v5 )
              MbbIpGetPrefixLength((unsigned __int16 *)Terminator, (unsigned __int16 **)&Terminator, v42);
            Buffer = Terminator;
            if ( *Terminator )
              Buffer = ++Terminator;
            ++v15;
          }
          if ( !v15 && *Terminator && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_LdD(
              WPP_GLOBAL_Control->DeviceExtension,
              v18,
              v12,
              v19,
              ParameterType,
              v5,
              i != 0 ? 6 : 4,
              v18);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_dLd(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v12,
            v16,
            ParameterType,
            v11,
            v5,
            i != 0 ? 6 : 4);
        }
      }
      if ( i )
        v47 = ParameterValue;
      else
        v49 = ParameterValue;
      if ( i )
      {
        v7 = v15;
        v15 = v6;
      }
      v6 = v15;
    }
    v45 = v7;
    v20 = v15 + v7 == 0;
    v21 = v15 + v7;
    v44 = v21;
    if ( v20 )
    {
      v8 = v48;
    }
    else
    {
      Pool2 = (struct in_addr *)ExAllocatePool2(256, 24 * v21, 1682129485);
      v48 = Pool2;
      v8 = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            2,
            14,
            (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
            v5);
        }
        Status = -1073741670;
        v6 = 0;
        v7 = 0;
LABEL_84:
        v4 = v53;
        goto LABEL_85;
      }
      memset(Pool2, 0, 24 * v21);
    }
    Status = 0;
    if ( v49 )
      Terminator = v49->ParameterData.StringData.Buffer;
    v23 = 0;
    if ( v6 )
    {
      if ( v5 )
      {
        do
        {
          v49 = (PNDIS_CONFIGURATION_PARAMETER)(3 * v23);
          v29 = &v8[6 * v23 + 2];
          v30 = RtlIpv4StringToAddressW(Terminator, 1u, &Terminator, v29);
          if ( v30 )
          {
            if ( !(_DWORD)v23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_LDd(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 16, ParameterType, v5, v30, v6);
            v29->S_un.S_addr = 0;
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_L_IPV4_(
                WPP_GLOBAL_Control->DeviceExtension,
                v11,
                v12,
                v31,
                ParameterType,
                v5,
                (__int64)v29);
            v12 = (int)Terminator;
            if ( *Terminator )
              ++Terminator;
          }
          v23 = (unsigned int)(v23 + 1);
          v8[2 * (_QWORD)v49].S_un.S_addr = v8[2 * (_QWORD)v49].S_un.S_addr & 0xFFFFFFFC | 2;
        }
        while ( (unsigned int)v23 < v6 );
      }
      else
      {
        v24 = 0;
        do
        {
          v25 = 3 * v24;
          v26 = RtlIpv4StringToAddressW(Terminator, 1u, &Terminator, &v8[6 * v24 + 2]);
          if ( v26 )
          {
            if ( !(_DWORD)v23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_LDd(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 16, ParameterType, 0, v26, v6);
            v8[6 * v24 + 2].S_un.S_addr = 0;
          }
          else
          {
            p_s_b1 = &v8[6 * v24 + 1].S_un.S_un_b.s_b1;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              WPP_RECORDER_SF_L_IPV4_(
                WPP_GLOBAL_Control->DeviceExtension,
                v11,
                v12,
                v27,
                ParameterType,
                0,
                (__int64)&v8[2 * v25 + 2]);
              p_s_b1 = &v8[6 * v24 + 1].S_un.S_un_b.s_b1;
            }
            MbbIpGetPrefixLength((unsigned __int16 *)Terminator, (unsigned __int16 **)&Terminator, p_s_b1);
            v12 = (int)Terminator;
            if ( *Terminator )
              ++Terminator;
          }
          LODWORD(v23) = v23 + 1;
          ++v24;
          v8[2 * v25].S_un.S_addr = v8[2 * v25].S_un.S_addr & 0xFFFFFFFC | 2;
        }
        while ( (unsigned int)v23 < v6 );
        v5 = v51;
      }
      LODWORD(v21) = v44;
    }
    if ( v47 )
      Terminator = v47->ParameterData.StringData.Buffer;
    if ( (unsigned int)v23 < (unsigned int)v21 )
    {
      v32 = (unsigned int)v23;
      v47 = (PNDIS_CONFIGURATION_PARAMETER)(unsigned int)v23;
      do
      {
        v33 = 3 * v32;
        v34 = &v8[6 * v32];
        v35 = RtlIpv6StringToAddressW(Terminator, &Terminator, (struct in6_addr *)&v34[2]);
        if ( v35 )
        {
          if ( (_DWORD)v23 == v6 - 1 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_LDd(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 18, ParameterType, v5, v35, v45);
          *(_OWORD *)&v34[2].S_un.S_un_b.s_b1 = 0;
        }
        else
        {
          v37 = &v48[2 * v33];
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_L_IPV6_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              v12,
              v36,
              ParameterType,
              v5,
              (__int64)&v48[2 * v33 + 2],
              v37[1].S_un.S_addr);
          if ( !v5 )
            MbbIpGetPrefixLength(
              (unsigned __int16 *)Terminator,
              (unsigned __int16 **)&Terminator,
              &v37[1].S_un.S_un_b.s_b1);
          v12 = (int)Terminator;
          if ( *Terminator )
            ++Terminator;
        }
        LODWORD(v23) = v23 + 1;
        v8 = v48;
        v32 = (unsigned __int64)&v47->ParameterType + 1;
        v47 = (PNDIS_CONFIGURATION_PARAMETER)((char *)v47 + 1);
        v48[2 * v33].S_un.S_addr |= 3u;
      }
      while ( (unsigned int)v23 < v44 );
    }
    v7 = v45;
    goto LABEL_84;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_87;
  WPP_RECORDER_SF_Ld(
    WPP_GLOBAL_Control->DeviceExtension,
    v10,
    2,
    10,
    (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
    v5,
    v9);
LABEL_85:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ddL(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 19);
LABEL_87:
  v38 = v55;
  *v4 = v8;
  *v38 = v6 + v7;
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140043eb4  mov     [rsp-8+arg_8], rbx
0x140043eb9  push    rbp
0x140043eba  push    rsi
0x140043ebb  push    rdi
0x140043ebc  push    r12
0x140043ebe  push    r13
0x140043ec0  push    r14
0x140043ec2  push    r15
0x140043ec4  lea     rbp, [rsp-27h]
0x140043ec9  sub     rsp, 0F0h
0x140043ed0  mov     rax, cs:__security_cookie
0x140043ed7  xor     rax, rsp
0x140043eda  mov     [rbp+57h+var_40], rax
0x140043ede  xor     edi, edi
0x140043ee0  mov     [rbp+57h+var_A4], edx
0x140043ee3  xorps   xmm0, xmm0
0x140043ee6  mov     [rbp+57h+ConfigObject.NdisHandle], rcx
0x140043eea  mov     rbx, r8
0x140043eed  mov     [rsp+120h+Terminator], rdi
0x140043ef2  mov     r12d, edx
0x140043ef5  mov     [rbp+57h+var_98], rbx
0x140043ef9  xorps   xmm1, xmm1
0x140043efc  mov     dword ptr [rbp+57h+Addr.S_un], edi
0x140043eff  lea     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140043f03  mov     [rbp+57h+Status], edi
0x140043f06  lea     rcx, [rbp+57h+ConfigObject]; ConfigObject
0x140043f0a  mov     [rbp+57h+ConfigurationHandle], rdi
0x140043f0e  mov     r15d, edi
0x140043f11  mov     [rbp+57h+var_B8], rdi
0x140043f15  mov     r13d, edi
0x140043f18  mov     qword ptr [rbp+57h+ConfigObject.Flags], rdi
0x140043f1c  movups  xmmword ptr [rbp+57h+var_50.u], xmm0
0x140043f20  mov     esi, edi
0x140043f22  mov     [rbp+57h+var_78], r9
0x140043f26  movups  xmmword ptr [rbp+57h+Keyword.Length], xmm0
0x140043f2a  mov     qword ptr [rbp+57h+ConfigObject.Header.Type], 1801A9h
0x140043f32  movups  [rbp+57h+var_70], xmm1
0x140043f36  call    cs:__imp_NdisOpenConfigurationEx
0x140043f3d  nop     dword ptr [rax+rax+00h]
0x140043f42  mov     [rbp+57h+Status], eax
0x140043f45  test    eax, eax
0x140043f47  jz      short loc_140043F8F
0x140043f49  lea     r14, WPP_RECORDER_INITIALIZED
0x140043f50  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140043f57  jz      loc_140044527
0x140043f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f64  lea     r9d, [rdi+0Ah]
0x140043f68  mov     dword ptr [rsp+120h+var_F0], eax
0x140043f6c  lea     r8d, [rdi+2]
0x140043f70  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140043f77  mov     [rsp+120h+var_F8], r12d
0x140043f7c  mov     qword ptr [rsp+120h+ParameterType], rax
0x140043f81  mov     rcx, [rcx+40h]
0x140043f85  call    WPP_RECORDER_SF_Ld
0x140043f8a  jmp     loc_1400444F9
0x140043f8f  lea     r8, [rbp+57h+var_70]
0x140043f93  mov     [rbp+57h+var_B0], rdi
0x140043f97  lea     rdx, [rbp+57h+Keyword]
0x140043f9b  mov     [rbp+57h+var_C0], rdi
0x140043f9f  mov     ecx, r12d
0x140043fa2  call    ?MbbIpAddressTableIdToRegistryValueName@@YAXW4MBB_ADDRESS_TABLE_ID@@PEAU_UNICODE_STRING@@1@Z; MbbIpAddressTableIdToRegistryValueName(MBB_ADDRESS_TABLE_ID,_UNICODE_STRING *,_UNICODE_STRING *)
0x140043fa7  xor     r10d, r10d
0x140043faa  lea     r14, WPP_RECORDER_INITIALIZED
0x140043fb1  mov     ebx, r10d
0x140043fb4  lea     edi, [r10+2]
0x140043fb8  mov     r8, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140043fbc  lea     rax, [rbp+57h+Keyword]
0x140043fc0  test    ebx, ebx
0x140043fc2  mov     [rbp+57h+ParameterValue], r10
0x140043fc6  lea     r9, [rbp+57h+var_70]
0x140043fca  mov     [rsp+120h+ParameterType], edi; ParameterType
0x140043fce  cmovz   r9, rax; Keyword
0x140043fd2  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x140043fd6  lea     rcx, [rbp+57h+Status]; Status
0x140043fda  mov     esi, r10d
0x140043fdd  call    cs:__imp_NdisReadConfiguration
0x140043fe4  nop     dword ptr [rax+rax+00h]
0x140043fe9  mov     edx, [rbp+57h+Status]
0x140043fec  xor     r10d, r10d
0x140043fef  test    edx, edx
0x140043ff1  jz      short loc_14004402D
0x140043ff3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140043ffa  jz      loc_140044134
0x140044000  mov     [rsp+120h+var_E8], edx
0x140044004  mov     eax, ebx
0x140044006  neg     eax
0x140044008  sbb     ecx, ecx
0x14004400a  and     ecx, edi
0x14004400c  add     ecx, 4
0x14004400f  mov     dword ptr [rsp+120h+var_F0], ecx
0x140044013  mov     rcx, cs:WPP_GLOBAL_Control
0x14004401a  mov     [rsp+120h+var_F8], r12d
0x14004401f  mov     rcx, [rcx+40h]
0x140044023  call    WPP_RECORDER_SF_Ldd
0x140044028  jmp     loc_140044131
0x14004402d  mov     rax, [rbp+57h+ParameterValue]
0x140044031  mov     edx, [rax]
0x140044033  cmp     edx, edi
0x140044035  jz      short loc_140044071
0x140044037  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004403e  jz      loc_140044134
0x140044044  mov     eax, ebx
0x140044046  neg     eax
0x140044048  sbb     ecx, ecx
0x14004404a  and     ecx, edi
0x14004404c  add     ecx, 4
0x14004404f  mov     [rsp+120h+var_E8], ecx
0x140044053  mov     rcx, cs:WPP_GLOBAL_Control
0x14004405a  mov     dword ptr [rsp+120h+var_F0], r12d
0x14004405f  mov     [rsp+120h+var_F8], edx
0x140044063  mov     rcx, [rcx+40h]
0x140044067  call    WPP_RECORDER_SF_dLd
0x14004406c  jmp     loc_140044131
0x140044071  mov     rax, [rbp+57h+ParameterValue]
0x140044075  mov     rcx, [rax+10h]; S
0x140044079  mov     [rsp+120h+Terminator], rcx
0x14004407e  mov     [rsp+120h+var_D8], r10b
0x140044083  test    ebx, ebx
0x140044085  jnz     short loc_1400440A0
0x140044087  lea     r9, [rbp+57h+Addr]; Addr
0x14004408b  mov     dl, 1; Strict
0x14004408d  lea     r8, [rsp+120h+Terminator]; Terminator
0x140044092  call    cs:__imp_RtlIpv4StringToAddressW
0x140044099  nop     dword ptr [rax+rax+00h]
0x14004409e  jmp     short loc_1400440B5
0x1400440a0  lea     r8, [rbp+57h+var_50]; Addr
0x1400440a4  lea     rdx, [rsp+120h+Terminator]; Terminator
0x1400440a9  call    cs:__imp_RtlIpv6StringToAddressW
0x1400440b0  nop     dword ptr [rax+rax+00h]
0x1400440b5  xor     r10d, r10d
0x1400440b8  mov     edx, eax
0x1400440ba  test    eax, eax
0x1400440bc  jnz     short loc_1400440F1
0x1400440be  test    r12d, r12d
0x1400440c1  jnz     short loc_1400440DA
0x1400440c3  mov     rcx, [rsp+120h+Terminator]; unsigned __int16 *
0x1400440c8  lea     r8, [rsp+120h+var_D8]; unsigned __int8 *
0x1400440cd  lea     rdx, [rsp+120h+Terminator]; unsigned __int16 **
0x1400440d2  call    ?MbbIpGetPrefixLength@@YAXPEAGPEAPEAGPEAE@Z; MbbIpGetPrefixLength(ushort *,ushort * *,uchar *)
0x1400440d7  xor     r10d, r10d
0x1400440da  mov     rcx, [rsp+120h+Terminator]
0x1400440df  cmp     [rcx], r10w
0x1400440e3  jz      short loc_1400440ED
0x1400440e5  add     rcx, rdi
0x1400440e8  mov     [rsp+120h+Terminator], rcx
0x1400440ed  inc     esi
0x1400440ef  jmp     short loc_14004407E
0x1400440f1  test    esi, esi
0x1400440f3  jnz     short loc_140044134
0x1400440f5  mov     rax, [rsp+120h+Terminator]
0x1400440fa  cmp     [rax], r10w
0x1400440fe  jz      short loc_140044134
0x140044100  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140044107  jz      short loc_140044134
0x140044109  mov     [rsp+120h+var_E8], edx
0x14004410d  mov     eax, ebx
0x14004410f  neg     eax
0x140044111  sbb     ecx, ecx
0x140044113  and     ecx, edi
0x140044115  add     ecx, 4
0x140044118  mov     dword ptr [rsp+120h+var_F0], ecx
0x14004411c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044123  mov     [rsp+120h+var_F8], r12d
0x140044128  mov     rcx, [rcx+40h]
0x14004412c  call    WPP_RECORDER_SF_LdD
0x140044131  xor     r10d, r10d
0x140044134  test    ebx, ebx
0x140044136  jnz     short loc_140044142
0x140044138  mov     rax, [rbp+57h+ParameterValue]
0x14004413c  mov     [rbp+57h+var_B0], rax
0x140044140  jmp     short loc_14004414A
0x140044142  mov     rcx, [rbp+57h+ParameterValue]
0x140044146  mov     [rbp+57h+var_C0], rcx
0x14004414a  test    ebx, ebx
0x14004414c  cmovnz  r13d, esi
0x140044150  cmovnz  esi, r15d
0x140044154  inc     ebx
0x140044156  mov     r15d, esi
0x140044159  cmp     ebx, edi
0x14004415b  jb      loc_140043FB8
0x140044161  mov     [rbp+57h+var_CC], r13d
0x140044165  add     r13d, esi
0x140044168  mov     [rbp+57h+var_D0], r13d
0x14004416c  jz      loc_140044201
0x140044172  lea     rbx, ds:0[r13*2]
0x14004417a  mov     r8d, 6443424Dh
0x140044180  add     rbx, r13
0x140044183  mov     ecx, 100h
0x140044188  shl     rbx, 3
0x14004418c  mov     rdx, rbx
0x14004418f  call    cs:__imp_ExAllocatePool2
0x140044196  nop     dword ptr [rax+rax+00h]
0x14004419b  mov     [rbp+57h+var_B8], rax
0x14004419f  mov     rsi, rax
0x1400441a2  test    rax, rax
0x1400441a5  jnz     short loc_1400441EF
0x1400441a7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400441ae  jz      short loc_1400441DB
0x1400441b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400441b7  lea     r9d, [rax+0Eh]
0x1400441bb  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400441c2  mov     [rsp+120h+var_F8], r12d
0x1400441c7  mov     r8d, edi
0x1400441ca  mov     qword ptr [rsp+120h+ParameterType], rax
0x1400441cf  mov     dl, dil
0x1400441d2  mov     rcx, [rcx+40h]
0x1400441d6  call    WPP_RECORDER_SF_d
0x1400441db  xor     edi, edi
0x1400441dd  mov     [rbp+57h+Status], 0C000009Ah
0x1400441e4  mov     r15d, edi
0x1400441e7  mov     r13d, edi
0x1400441ea  jmp     loc_1400444F5
0x1400441ef  mov     r8, rbx; Size
0x1400441f2  xor     edx, edx; Val
0x1400441f4  mov     rcx, rax; void *
0x1400441f7  call    memset
0x1400441fc  xor     r10d, r10d
0x1400441ff  jmp     short loc_140044205
0x140044201  mov     rsi, [rbp+57h+var_B8]
0x140044205  mov     rax, [rbp+57h+var_B0]
0x140044209  mov     [rbp+57h+Status], r10d
0x14004420d  test    rax, rax
0x140044210  jz      short loc_14004421B
0x140044212  mov     rax, [rax+10h]
0x140044216  mov     [rsp+120h+Terminator], rax
0x14004421b  mov     ebx, r10d
0x14004421e  test    r15d, r15d
0x140044221  jz      loc_1400443DE
0x140044227  test    r12d, r12d
0x14004422a  jnz     loc_140044322
0x140044230  mov     r12, r10
0x140044233  mov     rcx, [rsp+120h+Terminator]; S
0x140044238  lea     r13, [r12+r12*2]
0x14004423c  lea     r9, [r13+1]
0x140044240  mov     dl, 1; Strict
0x140044242  lea     r9, [rsi+r9*8]; Addr
0x140044246  lea     r8, [rsp+120h+Terminator]; Terminator
0x14004424b  call    cs:__imp_RtlIpv4StringToAddressW
0x140044252  nop     dword ptr [rax+rax+00h]
0x140044257  xor     r10d, r10d
0x14004425a  test    eax, eax
0x14004425c  jnz     short loc_1400442C6
0x14004425e  lea     rax, ds:4[r13*8]
0x140044266  add     rax, rsi
0x140044269  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140044270  jz      short loc_14004429F
0x140044272  mov     rcx, cs:WPP_GLOBAL_Control
0x140044279  lea     rax, [r13+1]
0x14004427d  lea     rax, [rsi+rax*8]
0x140044281  mov     [rsp+120h+var_F0], rax
0x140044286  mov     [rsp+120h+var_F8], r10d
0x14004428b  mov     rcx, [rcx+40h]
0x14004428f  call    WPP_RECORDER_SF_L_IPV4_
0x140044294  lea     rax, ds:4[r13*8]
0x14004429c  add     rax, rsi
0x14004429f  mov     rcx, [rsp+120h+Terminator]; unsigned __int16 *
0x1400442a4  lea     rdx, [rsp+120h+Terminator]; unsigned __int16 **
0x1400442a9  mov     r8, rax; unsigned __int8 *
0x1400442ac  call    ?MbbIpGetPrefixLength@@YAXPEAGPEAPEAGPEAE@Z; MbbIpGetPrefixLength(ushort *,ushort * *,uchar *)
0x1400442b1  mov     r8, [rsp+120h+Terminator]
0x1400442b6  xor     r10d, r10d
0x1400442b9  cmp     [r8], r10w
0x1400442bd  jz      short loc_1400442FE
0x1400442bf  add     [rsp+120h+Terminator], rdi
0x1400442c4  jmp     short loc_1400442FE
0x1400442c6  test    ebx, ebx
0x1400442c8  jnz     short loc_1400442F5
0x1400442ca  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400442d1  jz      short loc_1400442F5
0x1400442d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400442da  lea     r9d, [rbx+10h]
0x1400442de  mov     [rsp+120h+var_E8], r15d
0x1400442e3  mov     dword ptr [rsp+120h+var_F0], eax
0x1400442e7  mov     [rsp+120h+var_F8], r10d
0x1400442ec  mov     rcx, [rcx+40h]
0x1400442f0  call    WPP_RECORDER_SF_LDd
0x1400442f5  xor     ecx, ecx
0x1400442f7  lea     rax, [rsi+r13*8]
0x1400442fb  mov     [rax+8], ecx
0x1400442fe  mov     eax, [rsi+r13*8]
0x140044302  inc     ebx
0x140044304  and     eax, 0FFFFFFFEh
0x140044307  inc     r12
0x14004430a  or      eax, edi
0x14004430c  mov     [rsi+r13*8], eax
0x140044310  cmp     ebx, r15d
0x140044313  jb      loc_140044233
0x140044319  mov     r12d, [rbp+57h+var_A4]
0x14004431d  jmp     loc_1400443DA
0x140044322  mov     rcx, [rsp+120h+Terminator]; S
0x140044327  lea     rax, [rbx+rbx*2]
0x14004432b  mov     [rbp+57h+var_B0], rax
0x14004432f  lea     r8, [rsp+120h+Terminator]; Terminator
0x140044334  inc     rax
0x140044337  mov     dl, 1; Strict
0x140044339  lea     r13, [rsi+rax*8]
0x14004433d  mov     r9, r13; Addr
0x140044340  call    cs:__imp_RtlIpv4StringToAddressW
0x140044347  nop     dword ptr [rax+rax+00h]
0x14004434c  xor     r10d, r10d
  ... truncated ...
```
