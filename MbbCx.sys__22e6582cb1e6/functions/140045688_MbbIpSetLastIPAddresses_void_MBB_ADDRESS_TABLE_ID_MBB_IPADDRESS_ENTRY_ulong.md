# MbbIpSetLastIPAddresses(void *,MBB_ADDRESS_TABLE_ID,_MBB_IPADDRESS_ENTRY *,ulong)

- ea: `0x140045688`
- end: `0x140045b03`
- name: `?MbbIpSetLastIPAddresses@@YAHPEAXW4MBB_ADDRESS_TABLE_ID@@PEAU_MBB_IPADDRESS_ENTRY@@K@Z`
- size: `1147`
- prototype: `__int64 __fastcall(void *, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140046d80`

## callees

- `0x140001db8`
- `0x140042488`
- `0x140045688`
- `0x140045b0c`
- `0x140046284`

## import_xrefs

- `ntoskrnl!RtlIpv4AddressToStringW` at `0x1400458d9`
- `ntoskrnl!RtlIpv4AddressToStringW` at `0x140045967`
- `ntoskrnl!RtlIpv4AddressToStringW` at `0x1400458d9`
- `ntoskrnl!RtlIpv4AddressToStringW` at `0x140045967`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x140045908`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x140045985`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x140045908`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x140045985`
- `ntoskrnl!ExAllocatePool2` at `0x1400457b8`
- `ntoskrnl!ExAllocatePool2` at `0x140045831`
- `ntoskrnl!ExAllocatePool2` at `0x1400457b8`
- `ntoskrnl!ExAllocatePool2` at `0x140045831`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045aca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045aca`
- `NDIS!NdisCloseConfiguration` at `0x140045adf`
- `NDIS!NdisCloseConfiguration` at `0x140045adf`
- `NDIS!NdisWriteConfiguration` at `0x140045a13`
- `NDIS!NdisWriteConfiguration` at `0x140045a4e`
- `NDIS!NdisWriteConfiguration` at `0x140045a13`
- `NDIS!NdisWriteConfiguration` at `0x140045a4e`
- `NDIS!NdisOpenConfigurationEx` at `0x1400456f8`
- `NDIS!NdisOpenConfigurationEx` at `0x1400456f8`

## pseudocode

```c
__int64 __fastcall MbbIpSetLastIPAddresses(void *a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // edi
  NDIS_STATUS v7; // eax
  int v8; // r14d
  int v9; // esi
  unsigned int i; // r8d
  int v11; // eax
  int v12; // edx
  __int64 Pool2; // rax
  int v14; // edx
  wchar_t *v15; // r12
  int v16; // r9d
  WCHAR *v17; // r13
  WCHAR *v18; // rcx
  __int64 v19; // r14
  __int64 v20; // rdi
  __int64 v21; // r8
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rax
  unsigned int v25; // edi
  __int64 v26; // r15
  __int64 v27; // r8
  PWSTR v28; // rax
  wchar_t *v29; // rax
  int v30; // r8d
  unsigned int v32; // [rsp+4Ch] [rbp-85h]
  WCHAR *v33; // [rsp+50h] [rbp-81h]
  PVOID ConfigurationHandle; // [rsp+58h] [rbp-79h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-71h]
  unsigned int v36; // [rsp+64h] [rbp-6Dh]
  PWSTR S; // [rsp+68h] [rbp-69h]
  wchar_t *v38; // [rsp+70h] [rbp-61h]
  struct _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+78h] [rbp-59h] BYREF
  struct _NDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+90h] [rbp-41h] BYREF
  struct _NDIS_CONFIGURATION_PARAMETER v41; // [rsp+A8h] [rbp-29h] BYREF
  UNICODE_STRING Keyword; // [rsp+C0h] [rbp-11h] BYREF
  UNICODE_STRING v43; // [rsp+D0h] [rbp-1h] BYREF
  int Status; // [rsp+138h] [rbp+67h] BYREF
  unsigned int v45; // [rsp+140h] [rbp+6Fh]
  __int64 v46; // [rsp+148h] [rbp+77h]
  unsigned int v47; // [rsp+150h] [rbp+7Fh]

  v47 = a4;
  v46 = a3;
  v45 = a2;
  ConfigObject.NdisHandle = a1;
  Status = 0;
  ConfigurationHandle = 0;
  *(_QWORD *)&ConfigObject.Flags = 0;
  v4 = a2;
  *(_QWORD *)&ConfigObject.Header.Type = 1573289;
  Keyword = 0;
  v43 = 0;
  memset(&ParameterValue, 0, sizeof(ParameterValue));
  memset(&v41, 0, sizeof(v41));
  v7 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = v7;
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        20,
        (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
        v7);
    goto LABEL_41;
  }
  v8 = 0;
  v9 = 0;
  for ( i = 0; i < a4; v8 = v11 )
  {
    if ( (*(_DWORD *)(a3 + 24LL * i) & 1) != 0 )
      ++v9;
    v11 = v8 + 1;
    if ( (*(_DWORD *)(a3 + 24LL * i) & 1) != 0 )
      v11 = v8;
    ++i;
  }
  v35 = v8 * (v4 != 0 ? 32 : 40) + 2;
  S = (PWSTR)ExAllocatePool2(256, v35, 1682129485);
  if ( !S )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        2,
        21,
        (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
        v4);
    }
    goto LABEL_41;
  }
  v36 = v9 * (v4 != 0 ? 92 : 100) + 2;
  Pool2 = ExAllocatePool2(256, v36, 1682129485);
  v38 = (wchar_t *)Pool2;
  v15 = (wchar_t *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_39;
    v16 = 22;
    goto LABEL_16;
  }
  v17 = S;
  v18 = (WCHAR *)Pool2;
  v33 = (WCHAR *)Pool2;
  if ( a4 )
  {
    v19 = v46;
    v32 = 0;
    if ( v4 )
    {
      v25 = v47;
      v26 = 0;
      do
      {
        v27 = v19 + 24 * v26;
        if ( (*(_DWORD *)v27 & 1) != 0 )
        {
          v28 = RtlIpv6AddressToStringW((const struct in6_addr *)(v27 + 8), v18);
          v18 = v28 + 1;
          v33 = v28 + 1;
        }
        else
        {
          v28 = RtlIpv4AddressToStringW((const struct in_addr *)(v27 + 8), v17);
          v18 = v33;
          v17 = v28 + 1;
        }
        v26 = (unsigned int)(v26 + 1);
        *v28 = 32;
      }
      while ( (unsigned int)v26 < v25 );
    }
    else
    {
      v20 = 0;
      do
      {
        v21 = v19 + 24 * v20;
        if ( (*(_DWORD *)v21 & 1) != 0 )
        {
          v24 = RtlIpv6AddressToStringW((const struct in6_addr *)(v21 + 8), v18);
          v23 = MbbIpSetPrefixLength(v24, *(_BYTE *)(v19 + 24 * v20 + 4));
          v18 = v23 + 1;
          v33 = v23 + 1;
        }
        else
        {
          v22 = RtlIpv4AddressToStringW((const struct in_addr *)(v21 + 8), v17);
          v23 = MbbIpSetPrefixLength(v22, *(_BYTE *)(v19 + 24 * v20 + 4));
          v18 = v33;
          v17 = v23 + 1;
        }
        ++v20;
        *v23 = 32;
        ++v32;
      }
      while ( v32 < a4 );
    }
    v15 = v38;
    v4 = v45;
  }
  *v17 = 0;
  v29 = S;
  *v18 = 0;
  ParameterValue.ParameterData.StringData.Buffer = v29;
  ParameterValue.ParameterData.StringData.MaximumLength = v35;
  ParameterValue.ParameterData.StringData.Length = v35 - 2;
  v41.ParameterData.StringData.MaximumLength = v36;
  v41.ParameterData.StringData.Length = v36 - 2;
  ParameterValue.ParameterType = NdisParameterString;
  v41.ParameterType = NdisParameterString;
  v41.ParameterData.StringData.Buffer = v15;
  MbbIpAddressTableIdToRegistryValueName(v4, &Keyword, &v43);
  NdisWriteConfiguration(&Status, ConfigurationHandle, &Keyword, &ParameterValue);
  if ( Status )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 23;
LABEL_16:
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        2,
        v16,
        (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
        v4);
    }
  }
  else
  {
    NdisWriteConfiguration(&Status, ConfigurationHandle, &v43, &v41);
    if ( !Status )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_ddL(WPP_GLOBAL_Control->DeviceExtension, v14, v30, 25);
      goto LABEL_39;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 24;
      goto LABEL_16;
    }
  }
LABEL_39:
  ExFreePoolWithTag(S, 0);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
LABEL_41:
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140045688  mov     rax, rsp
0x14004568b  mov     [rax+20h], r9d
0x14004568f  mov     [rax+18h], r8
0x140045693  mov     [rax+10h], edx
0x140045696  push    rbp
0x140045697  push    rbx
0x140045698  push    rsi
0x140045699  push    rdi
0x14004569a  push    r12
0x14004569c  push    r13
0x14004569e  push    r14
0x1400456a0  push    r15
0x1400456a2  lea     rbp, [rax-5Fh]
0x1400456a6  sub     rsp, 0E8h
0x1400456ad  xor     r13d, r13d
0x1400456b0  mov     [rbp+57h+ConfigObject.NdisHandle], rcx
0x1400456b4  xorps   xmm0, xmm0
0x1400456b7  mov     [rbp+57h+Status], r13d
0x1400456bb  xorps   xmm1, xmm1
0x1400456be  mov     [rbp+57h+ConfigurationHandle], r13
0x1400456c2  xor     eax, eax
0x1400456c4  mov     qword ptr [rbp+57h+ConfigObject.Flags], r13
0x1400456c8  mov     edi, edx
0x1400456ca  mov     qword ptr [rbp+57h+ParameterValue.ParameterData+8], rax
0x1400456ce  lea     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400456d2  mov     qword ptr [rbp+57h+var_80.ParameterData+8], rax
0x1400456d6  lea     rcx, [rbp+57h+ConfigObject]; ConfigObject
0x1400456da  mov     qword ptr [rbp+57h+ConfigObject.Header.Type], 1801A9h
0x1400456e2  movups  xmmword ptr [rbp+57h+Keyword.Length], xmm0
0x1400456e6  mov     r15d, r9d
0x1400456e9  mov     rbx, r8
0x1400456ec  movups  xmmword ptr [rbp+57h+var_58.Length], xmm1
0x1400456f0  movups  xmmword ptr [rbp+57h+ParameterValue.ParameterType], xmm0
0x1400456f4  movups  xmmword ptr [rbp+57h+var_80.ParameterType], xmm1
0x1400456f8  call    cs:__imp_NdisOpenConfigurationEx
0x1400456ff  nop     dword ptr [rax+rax+00h]
0x140045704  mov     [rbp+57h+Status], eax
0x140045707  test    eax, eax
0x140045709  jz      short loc_140045750
0x14004570b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140045712  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045719  jz      loc_140045AD6
0x14004571f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045726  lea     r9d, [r13+14h]
0x14004572a  mov     [rsp+120h+var_F8], eax
0x14004572e  lea     edx, [r13+2]
0x140045732  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140045739  lea     r8d, [r13+1]
0x14004573d  mov     qword ptr [rsp+120h+var_100], rax
0x140045742  mov     rcx, [rcx+40h]
0x140045746  call    WPP_RECORDER_SF_d
0x14004574b  jmp     loc_140045AD6
0x140045750  mov     dword ptr [rsp+120h+var_E0], r13d
0x140045755  mov     r14d, r13d
0x140045758  mov     esi, r13d
0x14004575b  mov     r8d, r13d
0x14004575e  test    r15d, r15d
0x140045761  jz      short loc_14004578E
0x140045763  mov     eax, r8d
0x140045766  lea     rcx, [rax+rax*2]
0x14004576a  test    dword ptr [rbx+rcx*8], 1
0x140045771  lea     eax, [rsi+1]
0x140045774  cmovnz  esi, eax
0x140045777  lea     eax, [r14+1]
0x14004577b  cmovnz  eax, r14d
0x14004577f  inc     r8d
0x140045782  mov     r14d, eax
0x140045785  cmp     r8d, r15d
0x140045788  jb      short loc_140045763
0x14004578a  mov     dword ptr [rsp+120h+var_E0], eax
0x14004578e  mov     eax, edi
0x140045790  mov     ebx, 0FFFFFFF8h
0x140045795  neg     eax
0x140045797  mov     r12d, 6443424Dh
0x14004579d  mov     r8d, r12d
0x1400457a0  sbb     ecx, ecx
0x1400457a2  and     ecx, ebx
0x1400457a4  lea     eax, [rcx+28h]
0x1400457a7  mov     ecx, 100h
0x1400457ac  imul    eax, r14d
0x1400457b0  add     eax, 2
0x1400457b3  mov     edx, eax
0x1400457b5  mov     [rbp+57h+var_C8], eax
0x1400457b8  call    cs:__imp_ExAllocatePool2
0x1400457bf  nop     dword ptr [rax+rax+00h]
0x1400457c4  mov     [rbp+57h+S], rax
0x1400457c8  test    rax, rax
0x1400457cb  jnz     short loc_140045813
0x1400457cd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400457d4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400457db  jz      loc_140045AD6
0x1400457e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457e8  lea     r9d, [rax+15h]
0x1400457ec  lea     ebx, [r9-13h]
0x1400457f0  mov     [rsp+120h+var_F8], edi
0x1400457f4  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400457fb  mov     r8d, ebx
0x1400457fe  mov     dl, bl
0x140045800  mov     qword ptr [rsp+120h+var_100], rax
0x140045805  mov     rcx, [rcx+40h]
0x140045809  call    WPP_RECORDER_SF_d
0x14004580e  jmp     loc_140045AD6
0x140045813  mov     eax, edi
0x140045815  mov     r8d, r12d
0x140045818  neg     eax
0x14004581a  mov     ecx, 100h
0x14004581f  sbb     edx, edx
0x140045821  and     edx, ebx
0x140045823  lea     eax, [rdx+64h]
0x140045826  imul    eax, esi
0x140045829  add     eax, 2
0x14004582c  mov     edx, eax
0x14004582e  mov     [rbp+57h+var_C4], eax
0x140045831  call    cs:__imp_ExAllocatePool2
0x140045838  nop     dword ptr [rax+rax+00h]
0x14004583d  mov     [rbp+57h+var_B8], rax
0x140045841  mov     r12, rax
0x140045844  test    rax, rax
0x140045847  jnz     short loc_14004588E
0x140045849  lea     rcx, WPP_RECORDER_INITIALIZED
0x140045850  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045857  jz      loc_140045AAE
0x14004585d  lea     r9d, [rax+16h]
0x140045861  lea     ebx, [rax+2]
0x140045864  mov     rcx, cs:WPP_GLOBAL_Control
0x14004586b  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140045872  mov     [rsp+120h+var_F8], edi
0x140045876  mov     r8d, ebx
0x140045879  mov     dl, bl
0x14004587b  mov     qword ptr [rsp+120h+var_100], rax
0x140045880  mov     rcx, [rcx+40h]
0x140045884  call    WPP_RECORDER_SF_d
0x140045889  jmp     loc_140045AAE
0x14004588e  mov     r13, [rbp+57h+S]
0x140045892  mov     rcx, rax
0x140045895  mov     [rsp+48h], rax
0x14004589a  mov     ebx, 2
0x14004589f  test    r15d, r15d
0x1400458a2  jz      loc_1400459B2
0x1400458a8  mov     r14, [rbp+57h+arg_10]
0x1400458ac  lea     r12d, [rbx+1Eh]
0x1400458b0  mov     dword ptr [rsp+120h+var_E0+4], 0
0x1400458b8  test    edi, edi
0x1400458ba  jnz     loc_14004594A
0x1400458c0  xor     edi, edi
0x1400458c2  lea     rax, [rdi+rdi*2]
0x1400458c6  lea     r8, [r14+rax*8]
0x1400458ca  mov     eax, [r14+rax*8]
0x1400458ce  test    al, 1
0x1400458d0  jnz     short loc_140045901
0x1400458d2  mov     rdx, r13; S
0x1400458d5  lea     rcx, [r8+8]; Addr
0x1400458d9  call    cs:__imp_RtlIpv4AddressToStringW
0x1400458e0  nop     dword ptr [rax+rax+00h]
0x1400458e5  lea     rdx, [rdi+rdi*2]
0x1400458e9  mov     rcx, rax; unsigned __int16 *
0x1400458ec  mov     dl, [r14+rdx*8+4]; unsigned __int8
0x1400458f1  call    ?MbbIpSetPrefixLength@@YAPEAGPEAGE@Z; MbbIpSetPrefixLength(ushort *,uchar)
0x1400458f6  mov     rcx, [rsp+48h]
0x1400458fb  lea     r13, [rbx+rax]
0x1400458ff  jmp     short loc_14004592E
0x140045901  mov     rdx, rcx; S
0x140045904  lea     rcx, [r8+8]; Addr
0x140045908  call    cs:__imp_RtlIpv6AddressToStringW
0x14004590f  nop     dword ptr [rax+rax+00h]
0x140045914  lea     rdx, [rdi+rdi*2]
0x140045918  mov     rcx, rax; unsigned __int16 *
0x14004591b  mov     dl, [r14+rdx*8+4]; unsigned __int8
0x140045920  call    ?MbbIpSetPrefixLength@@YAPEAGPEAGE@Z; MbbIpSetPrefixLength(ushort *,uchar)
0x140045925  lea     rcx, [rbx+rax]
0x140045929  mov     [rsp+48h], rcx
0x14004592e  mov     edx, dword ptr [rsp+120h+var_E0+4]
0x140045932  inc     rdi
0x140045935  inc     edx
0x140045937  mov     [rax], r12w
0x14004593b  mov     dword ptr [rsp+120h+var_E0+4], edx
0x14004593f  cmp     edx, r15d
0x140045942  jb      loc_1400458C2
0x140045948  jmp     short loc_1400459A6
0x14004594a  mov     edi, [rbp+57h+arg_18]
0x14004594d  xor     r15d, r15d
0x140045950  lea     rax, [r15+r15*2]
0x140045954  lea     r8, [r14+rax*8]
0x140045958  mov     eax, [r14+rax*8]
0x14004595c  test    al, 1
0x14004595e  jnz     short loc_14004597E
0x140045960  mov     rdx, r13; S
0x140045963  lea     rcx, [r8+8]; Addr
0x140045967  call    cs:__imp_RtlIpv4AddressToStringW
0x14004596e  nop     dword ptr [rax+rax+00h]
0x140045973  mov     rcx, [rsp+48h]
0x140045978  lea     r13, [rbx+rax]
0x14004597c  jmp     short loc_14004599A
0x14004597e  mov     rdx, rcx; S
0x140045981  lea     rcx, [r8+8]; Addr
0x140045985  call    cs:__imp_RtlIpv6AddressToStringW
0x14004598c  nop     dword ptr [rax+rax+00h]
0x140045991  lea     rcx, [rbx+rax]
0x140045995  mov     [rsp+48h], rcx
0x14004599a  inc     r15d
0x14004599d  mov     [rax], r12w
0x1400459a1  cmp     r15d, edi
0x1400459a4  jb      short loc_140045950
0x1400459a6  mov     r12, [rbp+57h+var_B8]
0x1400459aa  mov     r14d, dword ptr [rsp+120h+var_E0]
0x1400459af  mov     edi, [rbp+57h+arg_8]
0x1400459b2  xor     eax, eax
0x1400459b4  lea     r8, [rbp+57h+var_58]
0x1400459b8  mov     [r13+0], ax
0x1400459bd  lea     rdx, [rbp+57h+Keyword]
0x1400459c1  mov     rax, [rbp+57h+S]
0x1400459c5  xor     r13d, r13d
0x1400459c8  mov     [rcx], r13w
0x1400459cc  mov     ecx, [rbp+57h+var_C8]
0x1400459cf  mov     qword ptr [rbp+57h+ParameterValue.ParameterData+8], rax
0x1400459d3  movzx   eax, cx
0x1400459d6  sub     ax, bx
0x1400459d9  mov     word ptr [rbp+57h+ParameterValue.ParameterData+2], cx
0x1400459dd  mov     ecx, [rbp+57h+var_C4]
0x1400459e0  mov     word ptr [rbp+57h+ParameterValue.ParameterData], ax
0x1400459e4  movzx   eax, cx
0x1400459e7  sub     ax, bx
0x1400459ea  mov     word ptr [rbp+57h+var_80.ParameterData+2], cx
0x1400459ee  mov     ecx, edi
0x1400459f0  mov     word ptr [rbp+57h+var_80.ParameterData], ax
0x1400459f4  mov     [rbp+57h+ParameterValue.ParameterType], ebx
0x1400459f7  mov     [rbp+57h+var_80.ParameterType], ebx
0x1400459fa  mov     qword ptr [rbp+57h+var_80.ParameterData+8], r12
0x1400459fe  call    ?MbbIpAddressTableIdToRegistryValueName@@YAXW4MBB_ADDRESS_TABLE_ID@@PEAU_UNICODE_STRING@@1@Z; MbbIpAddressTableIdToRegistryValueName(MBB_ADDRESS_TABLE_ID,_UNICODE_STRING *,_UNICODE_STRING *)
0x140045a03  mov     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140045a07  lea     r9, [rbp+57h+ParameterValue]; ParameterValue
0x140045a0b  lea     r8, [rbp+57h+Keyword]; Keyword
0x140045a0f  lea     rcx, [rbp+57h+Status]; Status
0x140045a13  call    cs:__imp_NdisWriteConfiguration
0x140045a1a  nop     dword ptr [rax+rax+00h]
0x140045a1f  cmp     [rbp+57h+Status], r13d
0x140045a23  jz      short loc_140045A3E
0x140045a25  lea     rcx, WPP_RECORDER_INITIALIZED
0x140045a2c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045a33  jz      short loc_140045AAE
0x140045a35  lea     r9d, [r13+17h]
0x140045a39  jmp     loc_140045864
0x140045a3e  mov     rdx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140045a42  lea     r9, [rbp+57h+var_80]; ParameterValue
0x140045a46  lea     r8, [rbp+57h+var_58]; Keyword
0x140045a4a  lea     rcx, [rbp+57h+Status]; Status
0x140045a4e  call    cs:__imp_NdisWriteConfiguration
0x140045a55  nop     dword ptr [rax+rax+00h]
0x140045a5a  cmp     [rbp+57h+Status], r13d
0x140045a5e  jz      short loc_140045A7B
0x140045a60  lea     rcx, WPP_RECORDER_INITIALIZED
0x140045a67  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045a6e  jz      short loc_140045AAE
0x140045a70  mov     r9d, 18h
0x140045a76  jmp     loc_140045864
0x140045a7b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140045a82  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045a89  jz      short loc_140045AAE
0x140045a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045a92  mov     r9d, 19h
0x140045a98  mov     [rsp+120h+var_E8], edi
0x140045a9c  mov     [rsp+120h+var_F0], esi
0x140045aa0  mov     [rsp+120h+var_F8], r14d
0x140045aa5  mov     rcx, [rcx+40h]
0x140045aa9  call    WPP_RECORDER_SF_ddL
0x140045aae  mov     rcx, [rbp+57h+S]; P
0x140045ab2  xor     edx, edx; Tag
0x140045ab4  call    cs:__imp_ExFreePoolWithTag
0x140045abb  nop     dword ptr [rax+rax+00h]
0x140045ac0  test    r12, r12
0x140045ac3  jz      short loc_140045AD6
0x140045ac5  xor     edx, edx; Tag
0x140045ac7  mov     rcx, r12; P
0x140045aca  call    cs:__imp_ExFreePoolWithTag
0x140045ad1  nop     dword ptr [rax+rax+00h]
0x140045ad6  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x140045ada  test    rcx, rcx
0x140045add  jz      short loc_140045AEB
0x140045adf  call    cs:__imp_NdisCloseConfiguration
0x140045ae6  nop     dword ptr [rax+rax+00h]
0x140045aeb  mov     eax, [rbp+57h+Status]
0x140045aee  add     rsp, 0E8h
0x140045af5  pop     r15
0x140045af7  pop     r14
0x140045af9  pop     r13
0x140045afb  pop     r12
0x140045afd  pop     rdi
0x140045afe  pop     rsi
0x140045aff  pop     rbx
0x140045b00  pop     rbp
0x140045b01  retn
```
