# CRegistryHelper::LoadPropertiesFromRegistry(CPropertyCache *,_WFC_REG_ENTRY *,ulong)

- ea: `0x14007a4c8`
- end: `0x14007a864`
- name: `?LoadPropertiesFromRegistry@CRegistryHelper@@QEAAHPEAVCPropertyCache@@PEAU_WFC_REG_ENTRY@@K@Z`
- size: `924`
- prototype: `__int64 __fastcall(CRegistryHelper *__hidden this, CPropertyCache *, struct _WFC_REG_ENTRY *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x140077e34`

## callees

- `0x14000d3e0`
- `0x1400100f8`
- `0x1400101c8`
- `0x140010390`
- `0x140012214`
- `0x140034ec4`
- `0x14005a090`
- `0x140069a90`
- `0x14007a4c8`
- `0x14007a86c`
- `0x14008234c`
- `0x1400a4778`
- `0x1400da4f0`

## import_xrefs

- `NDIS!NdisReadConfiguration` at `0x14007a5b0`
- `NDIS!NdisReadConfiguration` at `0x14007a5b0`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::LoadPropertiesFromRegistry(
        CRegistryHelper *this,
        CPropertyCache *a2,
        struct _WFC_REG_ENTRY *a3)
{
  int v5; // eax
  int v6; // edx
  unsigned int i; // esi
  void *v8; // r8
  struct _WFC_REG_ENTRY near **v9; // rbx
  _BYTE *v10; // rdi
  int v11; // edx
  ULONG IntegerData; // r8d
  bool v13; // cc
  int v14; // edx
  __int64 result; // rax
  int v16; // ecx
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  int v21; // r9d
  __int64 v22; // [rsp+28h] [rbp-51h]
  char v23; // [rsp+28h] [rbp-51h]
  char v24; // [rsp+30h] [rbp-49h]
  int Status; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-25h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int8 v28; // [rsp+60h] [rbp-19h] BYREF
  __int128 v29; // [rsp+61h] [rbp-18h]
  __int128 v30; // [rsp+71h] [rbp-8h]
  _BYTE v31[19]; // [rsp+81h] [rbp+8h] BYREF

  v26 = 52;
  Status = 0;
  ParameterValue = 0;
  memset(v31, 0, sizeof(v31));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = CRegistryHelper::Open(this);
    Status = v5;
    if ( v5 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          11,
          (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
          v5);
      }
      Status = 0;
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x2B )
    {
      v17 = CRegistryHelper::ReadAdapterRegistryBinaries(this, L"StaLastConnectedAP", &v26, &v28);
      Status = v17;
      if ( v17 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return 0;
        LODWORD(v22) = v17;
        v21 = 18;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 4;
          WPP_RECORDER_SF__MAC_Ddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v19,
            16,
            (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
            (__int64)&v28,
            SBYTE7(v29),
            SBYTE11(v29),
            SHIBYTE(v29));
        }
        v20 = CPropertyCache::SetPropertyBuffer(a2, 0x43u, v26, &v28);
        Status = v20;
        if ( !v20 || *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return 0;
        LODWORD(v22) = v20;
        v21 = 17;
      }
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        1,
        v21,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        v22);
      return 0;
    }
    v8 = (void *)*((_QWORD *)this + 1);
    v9 = &g_AdapterRegTable + 5 * i;
    v10 = v9 + 2;
    if ( v8 )
    {
      NdisReadConfiguration(
        &Status,
        &ParameterValue,
        v8,
        (PNDIS_STRING)(&g_AdapterRegTable + 5 * i),
        (NDIS_PARAMETER_TYPE)(unsigned __int8)*v10);
      v11 = Status;
    }
    else
    {
      v11 = -1073741823;
      Status = -1073741823;
    }
    if ( v11 || (LODWORD(v8) = (_DWORD)ParameterValue, !ParameterValue) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v24 = v11;
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_dDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          (_DWORD)v8,
          13,
          (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
          *((_DWORD *)v9 + 6),
          v24,
          *((_DWORD *)v9 + 7));
      }
      v13 = *v10 <= 1u;
      Status = 0;
      if ( !v13 )
        continue;
      goto LABEL_23;
    }
    if ( *v10 > 1u )
      continue;
    IntegerData = ParameterValue->ParameterData.IntegerData;
    if ( IntegerData < *((_DWORD *)v9 + 8) || IntegerData > *((_DWORD *)v9 + 9) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          IntegerData,
          12,
          (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
          IntegerData,
          *((_DWORD *)v9 + 6),
          *((_DWORD *)v9 + 7));
      }
LABEL_23:
      IntegerData = *((_DWORD *)v9 + 7);
    }
    v14 = *((_DWORD *)v9 + 5);
    if ( v14 != 1 )
      break;
    result = CPropertyCache::SetPropertyULong(a2, *((_DWORD *)v9 + 6), IntegerData);
LABEL_30:
    Status = result;
    v16 = result;
    if ( (_DWORD)result )
      goto LABEL_35;
  }
  if ( *((_DWORD *)v9 + 5) == 2 )
  {
    result = CPropertyCache::SetPropertyBoolean(a2, *((_DWORD *)v9 + 6), IntegerData != 0);
    goto LABEL_30;
  }
  if ( *((_DWORD *)v9 + 5) == 3 )
  {
    result = CPropertyCache::SetPropertyUchar(a2, *((_DWORD *)v9 + 6), IntegerData);
    goto LABEL_30;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v23 = v14;
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      IntegerData,
      14,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      v23,
      *((_DWORD *)v9 + 6));
  }
  v16 = -1073676267;
  result = 3221291029LL;
  Status = -1073676267;
LABEL_35:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v22) = v16;
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      1,
      15,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      v22);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x14007a4c8  mov     [rsp-8+arg_10], rbx
0x14007a4cd  push    rbp
0x14007a4ce  push    rsi
0x14007a4cf  push    rdi
0x14007a4d0  push    r12
0x14007a4d2  push    r13
0x14007a4d4  push    r14
0x14007a4d6  push    r15
0x14007a4d8  lea     rbp, [rsp-27h]
0x14007a4dd  sub     rsp, 0A0h
0x14007a4e4  mov     rax, cs:__security_cookie
0x14007a4eb  xor     rax, rsp
0x14007a4ee  mov     [rbp+57h+var_38], rax
0x14007a4f2  xor     r12d, r12d
0x14007a4f5  mov     [rbp+57h+var_7C], 34h ; '4'
0x14007a4fc  xorps   xmm0, xmm0
0x14007a4ff  mov     [rbp+57h+Status], r12d
0x14007a503  xor     eax, eax
0x14007a505  mov     [rbp+57h+ParameterValue], r12
0x14007a509  lea     r13, WPP_RECORDER_INITIALIZED
0x14007a510  mov     r15, rdx
0x14007a513  lea     rbx, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a51a  mov     r14, rcx
0x14007a51d  movups  xmmword ptr [rbp+57h+var_4F], xmm0
0x14007a521  mov     dword ptr [rbp+57h+var_4F+0Fh], eax
0x14007a524  mov     [rbp+57h+var_70], r12b
0x14007a528  movups  [rbp+57h+var_6F], xmm0
0x14007a52c  movups  [rbp+57h+var_5F], xmm0
0x14007a530  cmp     [rcx+8], r12
0x14007a534  jnz     short loc_14007A574
0x14007a536  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x14007a53b  mov     [rbp+57h+Status], eax
0x14007a53e  test    eax, eax
0x14007a540  jz      short loc_14007A574
0x14007a542  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a549  jz      short loc_14007A570
0x14007a54b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a552  lea     r9d, [r12+0Bh]
0x14007a557  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14007a55b  lea     r8d, [r12+1]
0x14007a560  mov     dl, 2
0x14007a562  mov     qword ptr [rsp+0D0h+ParameterType], rbx
0x14007a567  mov     rcx, [rcx+40h]
0x14007a56b  call    WPP_RECORDER_SF_D
0x14007a570  mov     [rbp+57h+Status], r12d
0x14007a574  mov     esi, r12d
0x14007a577  cmp     esi, 2Bh ; '+'
0x14007a57a  jnb     loc_14007A765
0x14007a580  mov     r8, [r14+8]; ConfigurationHandle
0x14007a584  mov     eax, esi
0x14007a586  lea     rcx, [rax+rax*4]
0x14007a58a  lea     rax, ?g_AdapterRegTable@@3PAU_WFC_REG_ENTRY@@A; " \""
0x14007a591  lea     rbx, [rax+rcx*8]
0x14007a595  lea     rdi, [rbx+10h]
0x14007a599  test    r8, r8
0x14007a59c  jz      short loc_14007A5C1
0x14007a59e  movzx   eax, byte ptr [rdi]
0x14007a5a1  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14007a5a5  mov     r9, rbx; Keyword
0x14007a5a8  mov     [rsp+0D0h+ParameterType], eax; ParameterType
0x14007a5ac  lea     rcx, [rbp+57h+Status]; Status
0x14007a5b0  call    cs:__imp_NdisReadConfiguration
0x14007a5b7  nop     dword ptr [rax+rax+00h]
0x14007a5bc  mov     edx, [rbp+57h+Status]
0x14007a5bf  jmp     short loc_14007A5C9
0x14007a5c1  mov     edx, 0C0000001h
0x14007a5c6  mov     [rbp+57h+Status], edx
0x14007a5c9  test    edx, edx
0x14007a5cb  jnz     short loc_14007A639
0x14007a5cd  mov     r8, [rbp+57h+ParameterValue]
0x14007a5d1  test    r8, r8
0x14007a5d4  jz      short loc_14007A639
0x14007a5d6  cmp     byte ptr [rdi], 1
0x14007a5d9  ja      loc_14007A6DB
0x14007a5df  mov     r8d, [r8+8]
0x14007a5e3  cmp     r8d, [rbx+20h]
0x14007a5e7  jb      short loc_14007A5F3
0x14007a5e9  cmp     r8d, [rbx+24h]
0x14007a5ed  jbe     loc_14007A692
0x14007a5f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a5fa  jz      loc_14007A68E
0x14007a600  mov     eax, [rbx+1Ch]
0x14007a603  mov     r9d, 0Ch
0x14007a609  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a610  mov     dl, 2
0x14007a612  mov     [rsp+0D0h+var_98], eax
0x14007a616  mov     eax, [rbx+18h]
0x14007a619  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14007a61d  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a624  mov     rcx, [rcx+40h]
0x14007a628  mov     dword ptr [rsp+0D0h+var_A8], r8d
0x14007a62d  mov     qword ptr [rsp+0D0h+ParameterType], rax
0x14007a632  call    WPP_RECORDER_SF_ddd
0x14007a637  jmp     short loc_14007A68E
0x14007a639  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a640  jz      short loc_14007A685
0x14007a642  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a649  cmp     byte ptr [rcx+29h], 5
0x14007a64d  jnb     short loc_14007A656
0x14007a64f  cmp     [rcx+48h], r12w
0x14007a654  jz      short loc_14007A685
0x14007a656  mov     eax, [rbx+1Ch]
0x14007a659  mov     r9d, 0Dh
0x14007a65f  mov     rcx, [rcx+40h]
0x14007a663  mov     [rsp+0D0h+var_98], eax
0x14007a667  mov     eax, [rbx+18h]
0x14007a66a  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14007a66e  mov     dl, 5
0x14007a670  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14007a674  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a67b  mov     qword ptr [rsp+0D0h+ParameterType], rax
0x14007a680  call    WPP_RECORDER_SF_dDD
0x14007a685  cmp     byte ptr [rdi], 1
0x14007a688  mov     [rbp+57h+Status], r12d
0x14007a68c  ja      short loc_14007A6DB
0x14007a68e  mov     r8d, [rbx+1Ch]; unsigned int
0x14007a692  mov     edx, [rbx+14h]
0x14007a695  mov     ecx, edx
0x14007a697  sub     ecx, 1
0x14007a69a  jz      short loc_14007A6C7
0x14007a69c  sub     ecx, 1
0x14007a69f  jz      short loc_14007A6B3
0x14007a6a1  cmp     ecx, 1
0x14007a6a4  jnz     short loc_14007A6E2
0x14007a6a6  mov     edx, [rbx+18h]; unsigned int
0x14007a6a9  mov     rcx, r15; this
0x14007a6ac  call    ?SetPropertyUchar@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyUchar(ulong,uchar)
0x14007a6b1  jmp     short loc_14007A6D2
0x14007a6b3  mov     edx, [rbx+18h]; unsigned int
0x14007a6b6  test    r8d, r8d
0x14007a6b9  mov     rcx, r15; this
0x14007a6bc  setnz   r8b; unsigned __int8
0x14007a6c0  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14007a6c5  jmp     short loc_14007A6D2
0x14007a6c7  mov     edx, [rbx+18h]; unsigned int
0x14007a6ca  mov     rcx, r15; this
0x14007a6cd  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14007a6d2  mov     [rbp+57h+Status], eax
0x14007a6d5  mov     ecx, eax
0x14007a6d7  test    eax, eax
0x14007a6d9  jnz     short loc_14007A724
0x14007a6db  inc     esi
0x14007a6dd  jmp     loc_14007A577
0x14007a6e2  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a6e9  jz      short loc_14007A71A
0x14007a6eb  mov     eax, [rbx+18h]
0x14007a6ee  mov     r9d, 0Eh
0x14007a6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6fb  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14007a6ff  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a706  mov     dword ptr [rsp+0D0h+var_A8], edx
0x14007a70a  mov     dl, 2
0x14007a70c  mov     qword ptr [rsp+0D0h+ParameterType], rax
0x14007a711  mov     rcx, [rcx+40h]
0x14007a715  call    WPP_RECORDER_SF_Ld
0x14007a71a  mov     ecx, 0C0010015h
0x14007a71f  mov     eax, ecx
0x14007a721  mov     [rbp+57h+Status], ecx
0x14007a724  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a72b  jz      loc_14007A83C
0x14007a731  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x14007a735  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a73c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a743  mov     r9d, 0Fh
0x14007a749  mov     dl, 2
0x14007a74b  mov     qword ptr [rsp+0D0h+ParameterType], rax
0x14007a750  mov     rcx, [rcx+40h]
0x14007a754  lea     r8d, [r9-0Eh]
0x14007a758  call    WPP_RECORDER_SF_D
0x14007a75d  mov     eax, [rbp+57h+Status]
0x14007a760  jmp     loc_14007A83C
0x14007a765  lea     r9, [rbp+57h+var_70]; unsigned __int8 *
0x14007a769  mov     rcx, r14; this
0x14007a76c  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x14007a770  lea     rdx, aStalastconnect; "StaLastConnectedAP"
0x14007a777  call    ?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z; CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)
0x14007a77c  mov     [rbp+57h+Status], eax
0x14007a77f  test    eax, eax
0x14007a781  jnz     short loc_14007A802
0x14007a783  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a78a  lea     rbx, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a791  jz      short loc_14007A7CC
0x14007a793  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a79a  lea     r9d, [rax+10h]
0x14007a79e  mov     eax, dword ptr [rbp+57h+var_6F+0Fh]
0x14007a7a1  mov     dl, 4
0x14007a7a3  mov     [rsp+0D0h+var_90], eax
0x14007a7a7  mov     eax, dword ptr [rbp+57h+var_6F+0Bh]
0x14007a7aa  mov     rcx, [rcx+40h]
0x14007a7ae  mov     [rsp+0D0h+var_98], eax
0x14007a7b2  mov     eax, dword ptr [rbp+57h+var_6F+7]
0x14007a7b5  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14007a7b9  lea     rax, [rbp+57h+var_70]
0x14007a7bd  mov     [rsp+0D0h+var_A8], rax
0x14007a7c2  mov     qword ptr [rsp+0D0h+ParameterType], rbx
0x14007a7c7  call    WPP_RECORDER_SF__MAC_Ddd
0x14007a7cc  mov     r8d, [rbp+57h+var_7C]; unsigned int
0x14007a7d0  lea     r9, [rbp+57h+var_70]; unsigned __int8 *
0x14007a7d4  mov     edx, 43h ; 'C'; unsigned int
0x14007a7d9  mov     rcx, r15; this
0x14007a7dc  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x14007a7e1  mov     [rbp+57h+Status], eax
0x14007a7e4  test    eax, eax
0x14007a7e6  jz      short loc_14007A839
0x14007a7e8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a7ef  jz      short loc_14007A839
0x14007a7f1  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14007a7f5  mov     r9d, 11h
0x14007a7fb  mov     qword ptr [rsp+0D0h+ParameterType], rbx
0x14007a800  jmp     short loc_14007A821
0x14007a802  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007a809  jz      short loc_14007A839
0x14007a80b  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14007a80f  mov     r9d, 12h
0x14007a815  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a81c  mov     qword ptr [rsp+0D0h+ParameterType], rax
0x14007a821  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a828  mov     r8d, 1
0x14007a82e  mov     dl, 2
0x14007a830  mov     rcx, [rcx+40h]
0x14007a834  call    WPP_RECORDER_SF_D
0x14007a839  mov     eax, r12d
0x14007a83c  mov     rcx, [rbp+57h+var_38]
0x14007a840  xor     rcx, rsp; StackCookie
0x14007a843  call    __security_check_cookie
0x14007a848  mov     rbx, [rsp+0D0h+arg_10]
0x14007a850  add     rsp, 0A0h
0x14007a857  pop     r15
0x14007a859  pop     r14
0x14007a85b  pop     r13
0x14007a85d  pop     r12
0x14007a85f  pop     rdi
0x14007a860  pop     rsi
0x14007a861  pop     rbp
0x14007a862  retn
```
