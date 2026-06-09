# FWIndicatePortInUse

- ea: `0x18000fe30`
- end: `0x1800102be`
- name: `FWIndicatePortInUse`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102d0`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18000fe30`
- `0x18001f3cc`
- `0x180024c3c`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b934`
- `RPCRT4!RpcExceptionFilter` at `0x18005b934`
- `RPCRT4!NdrClientCall3` at `0x18000ffe7`
- `RPCRT4!NdrClientCall3` at `0x18000ffe7`
- `RPCRT4!RpcBindingFree` at `0x180010282`
- `RPCRT4!RpcBindingFree` at `0x180010282`
- `fwbase!FwIOWritePortUseIndications` at `0x180010122`
- `fwbase!FwIOWritePortUseIndications` at `0x180010122`
- `fwbase!FwIOReadPortUseIndications` at `0x1800100b2`
- `fwbase!FwIOReadPortUseIndications` at `0x1800100b2`
- `fwbase!FwCriticalSectionEnter` at `0x18000ff0b`
- `fwbase!FwCriticalSectionEnter` at `0x180010099`
- `fwbase!FwCriticalSectionEnter` at `0x18001020d`
- `fwbase!FwCriticalSectionEnter` at `0x18000ff0b`
- `fwbase!FwCriticalSectionEnter` at `0x180010099`
- `fwbase!FwCriticalSectionEnter` at `0x18001020d`
- `fwbase!FwCriticalSectionLeave` at `0x18000ffb1`
- `fwbase!FwCriticalSectionLeave` at `0x18001025e`
- `fwbase!FwCriticalSectionLeave` at `0x18000ffb1`
- `fwbase!FwCriticalSectionLeave` at `0x18001025e`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18000ff96`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001010c`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001024c`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18000ff96`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001010c`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001024c`
- `fwbase!FwBaseFree` at `0x180010269`
- `fwbase!FwBaseFree` at `0x180010269`
- `fwbase!FwHResultToWindowsError` at `0x180010199`
- `fwbase!FwHResultToWindowsError` at `0x180010199`

## pseudocode

```c
__int64 __fastcall FWIndicatePortInUse(unsigned int a1, unsigned __int16 a2, unsigned int a3)
{
  int v3; // r14d
  int v5; // r12d
  int v6; // r15d
  unsigned int inited; // eax
  unsigned int Pointer; // ebx
  FwPolicy2 *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-A8h]
  int v21; // [rsp+50h] [rbp-78h]
  __int64 v22; // [rsp+78h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp-48h] BYREF
  int v24; // [rsp+88h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+8Ch] [rbp-3Ch] BYREF

  v3 = a2;
  v22 = 0;
  v25 = 0;
  v5 = 0;
  Binding = 0;
  v24 = 1;
  v21 = 0;
  if ( a1 > 8 )
  {
    Pointer = 0;
    v6 = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v13 = 30;
    v14 = 2147942487LL;
    goto LABEL_42;
  }
  v6 = 0;
  inited = Int_FWLocalRpcBindingCreate(&Binding);
  Pointer = inited;
  if ( inited )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 31;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, inited);
LABEL_43:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  if ( a1 )
  {
LABEL_18:
    LODWORD(v18) = a1;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
                              0,
                              0,
                              Binding,
                              v18,
                              v3,
                              a3).Pointer;
    if ( Pointer == 1753 || Pointer == -2144206780 )
    {
      v11 = 1;
      Pointer = 0;
    }
    else
    {
      v11 = 0;
    }
    if ( Pointer )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, Pointer);
        v9 = WPP_GLOBAL_Control;
      }
      v5 = 0;
      goto LABEL_44;
    }
    if ( a1 == 4 && v11 != 1 )
    {
      v5 = 0;
      goto LABEL_43;
    }
    FwCriticalSectionEnter(g_FwPortKeywordLock);
    v5 = 1;
    v12 = FwIOReadPortUseIndications(a1, &v22, &v25);
    v6 = v12;
    if ( v12 >= 0 )
    {
      FWIndicatePortInUse_Helper(v22, (unsigned __int16)v3, a3, &v25, 0);
      v12 = FwIOWritePortUseIndications(a1, v22, v25);
      v6 = v12;
      if ( v12 >= 0 )
        goto LABEL_43;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v13 = 35;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v13 = 34;
    }
    v14 = (unsigned int)v12;
LABEL_42:
    WPP_SF_d(*((_QWORD *)v9 + 2), v13, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, v14);
    goto LABEL_43;
  }
  FwCriticalSectionEnter(g_FwPortKeywordLock);
  v5 = 1;
  inited = FwInitPortCollCache(0);
  Pointer = inited;
  if ( !inited )
  {
    if ( (_WORD)v3 != 135 && (_WORD)v3 != 593 )
    {
      v24 = 0;
      goto LABEL_43;
    }
    FWIndicatePortInUse_Helper(PortCollCache, (unsigned __int16)v3, a3, qword_180097708, &v24);
    v21 = 1;
    if ( !v24 )
      goto LABEL_43;
    FwCriticalSectionLeave(g_FwPortKeywordLock);
    goto LABEL_18;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 32;
    goto LABEL_6;
  }
LABEL_44:
  if ( v6 < 0 )
  {
    Pointer = FwHResultToWindowsError((unsigned int)v6);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 2), 36, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids, Pointer);
    v9 = WPP_GLOBAL_Control;
  }
  if ( Pointer == 5 )
  {
    if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 37, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids);
    Pointer = 0;
  }
  if ( Pointer && v21 == 1 )
  {
    if ( !v5 )
    {
      FwCriticalSectionEnter(g_FwPortKeywordLock);
      v5 = 1;
    }
    FWIndicatePortInUse_Helper(*(&PortCollCache + 2 * (int)a1), a2, a3 != 1, &qword_180097708[2 * (int)a1], &v24);
  }
  if ( v5 == 1 )
    FwCriticalSectionLeave(g_FwPortKeywordLock);
  FwBaseFree(v22);
  if ( Binding )
  {
    v15 = RpcBindingFree(&Binding);
    if ( v15 )
      MicrosoftTelemetryAssertTriggeredArgs(v16, v15);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000fe30  mov     r11, rsp
0x18000fe33  mov     [r11+20h], rbx
0x18000fe37  push    rsi
0x18000fe38  push    r12
0x18000fe3a  push    r13
0x18000fe3c  push    r14
0x18000fe3e  push    r15
0x18000fe40  sub     rsp, 0A0h
0x18000fe47  mov     rax, cs:__security_cookie
0x18000fe4e  xor     rax, rsp
0x18000fe51  mov     [rsp+0C8h+var_38], rax
0x18000fe59  mov     [rsp+0C8h+var_84], r8d
0x18000fe5e  movzx   r14d, dx
0x18000fe62  mov     [rsp+0C8h+var_88], r14w
0x18000fe68  mov     r13d, ecx
0x18000fe6b  mov     [rsp+0C8h+var_68], ecx
0x18000fe6f  mov     [rsp+0C8h+var_80], r14w
0x18000fe75  mov     [rsp+0C8h+var_60], r8d
0x18000fe7a  mov     qword ptr [r11-50h], 0
0x18000fe82  mov     dword ptr [r11-3Ch], 0
0x18000fe8a  xor     r12d, r12d
0x18000fe8d  mov     [r11-48h], r12
0x18000fe91  lea     esi, [r12+1]
0x18000fe96  mov     [r11-40h], esi
0x18000fe9a  mov     [rsp+0C8h+var_78], r12d
0x18000fe9f  cmp     ecx, 8
0x18000fea2  ja      loc_180010153
0x18000fea8  xor     r15d, r15d
0x18000feab  mov     [rsp+0C8h+var_70], r15d
0x18000feb0  lea     rcx, [r11-48h]
0x18000feb4  call    Int_FWLocalRpcBindingCreate
0x18000feb9  mov     ebx, eax
0x18000febb  test    eax, eax
0x18000febd  jz      short loc_18000FEFB
0x18000febf  lea     r14, WPP_GLOBAL_Control
0x18000fec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fecd  cmp     rcx, r14
0x18000fed0  jz      loc_180010191
0x18000fed6  test    [rcx+1Ch], sil
0x18000feda  jz      loc_180010191
0x18000fee0  lea     edx, [rsi+1Eh]
0x18000fee3  mov     r9d, eax
0x18000fee6  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18000feed  mov     rcx, [rcx+10h]
0x18000fef1  call    WPP_SF_d
0x18000fef6  jmp     loc_18001018A
0x18000fefb  test    r13d, r13d
0x18000fefe  jnz     loc_18000FFB8
0x18000ff04  lea     rcx, g_FwPortKeywordLock
0x18000ff0b  call    cs:__imp_FwCriticalSectionEnter
0x18000ff11  mov     r12d, esi
0x18000ff14  xor     ecx, ecx
0x18000ff16  call    ?FwInitPortCollCache@@YAKW4_tag_FW_PORT_COLLECTION_TYPE@@@Z; FwInitPortCollCache(_tag_FW_PORT_COLLECTION_TYPE)
0x18000ff1b  mov     ebx, eax
0x18000ff1d  test    eax, eax
0x18000ff1f  jz      short loc_18000FF48
0x18000ff21  lea     r14, WPP_GLOBAL_Control
0x18000ff28  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff2f  cmp     rcx, r14
0x18000ff32  jz      loc_180010191
0x18000ff38  test    [rcx+1Ch], sil
0x18000ff3c  jz      loc_180010191
0x18000ff42  lea     edx, [r13+20h]
0x18000ff46  jmp     short loc_18000FEE3
0x18000ff48  mov     eax, 87h
0x18000ff4d  cmp     r14w, ax
0x18000ff51  jz      short loc_18000FF72
0x18000ff53  mov     eax, 251h
0x18000ff58  cmp     r14w, ax
0x18000ff5c  jz      short loc_18000FF72
0x18000ff5e  mov     [rsp+0C8h+var_40], r15d
0x18000ff66  lea     r14, WPP_GLOBAL_Control
0x18000ff6d  jmp     loc_18001018A
0x18000ff72  lea     rax, [rsp+0C8h+var_40]
0x18000ff7a  mov     [rsp+0C8h+var_A8], rax
0x18000ff7f  lea     r9, qword_180097708
0x18000ff86  mov     r8d, [rsp+0C8h+var_84]
0x18000ff8b  movzx   edx, r14w
0x18000ff8f  mov     rcx, cs:?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x18000ff96  call    cs:__imp_FWIndicatePortInUse_Helper
0x18000ff9c  mov     [rsp+0C8h+var_78], esi
0x18000ffa0  cmp     [rsp+0C8h+var_40], r15d
0x18000ffa8  jz      short loc_18000FF66
0x18000ffaa  lea     rcx, g_FwPortKeywordLock
0x18000ffb1  call    cs:__imp_FwCriticalSectionLeave
0x18000ffb7  nop
0x18000ffb8  mov     [rsp+0C8h+var_58], 0
0x18000ffc1  mov     ecx, [rsp+0C8h+var_84]
0x18000ffc5  mov     [rsp+0C8h+var_98], ecx
0x18000ffc9  mov     [rsp+0C8h+var_A0], r14d
0x18000ffce  mov     dword ptr [rsp+0C8h+var_A8], r13d
0x18000ffd3  mov     r9, [rsp+0C8h+Binding]
0x18000ffdb  xor     r8d, r8d; pReturnValue
0x18000ffde  xor     edx, edx; nProcNum
0x18000ffe0  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000ffe7  call    cs:__imp_NdrClientCall3
0x18000ffed  mov     rbx, rax
0x18000fff0  mov     [rsp+0C8h+var_58], rax
0x18000fff5  mov     [rsp+0C8h+var_74], eax
0x18000fff9  jmp     short loc_180010024
0x18000fffb  mov     ebx, eax
0x18000fffd  mov     [rsp+0C8h+var_74], eax
0x180010001  mov     esi, 1
0x180010006  mov     r15d, [rsp+0C8h+var_70]
0x18001000b  movzx   r14d, [rsp+0C8h+var_80]
0x180010011  mov     [rsp+0C8h+var_88], r14w
0x180010017  mov     r13d, [rsp+0C8h+var_68]
0x18001001c  mov     eax, [rsp+0C8h+var_60]
0x180010020  mov     [rsp+0C8h+var_84], eax
0x180010024  cmp     ebx, 6D9h
0x18001002a  jz      short loc_180010038
0x18001002c  cmp     ebx, 80320044h
0x180010032  jz      short loc_180010038
0x180010034  xor     eax, eax
0x180010036  jmp     short loc_18001003C
0x180010038  mov     eax, esi
0x18001003a  xor     ebx, ebx
0x18001003c  test    ebx, ebx
0x18001003e  jz      short loc_180010080
0x180010040  lea     r14, WPP_GLOBAL_Control
0x180010047  mov     rcx, cs:WPP_GLOBAL_Control
0x18001004e  cmp     rcx, r14
0x180010051  jz      short loc_180010078
0x180010053  test    [rcx+1Ch], sil
0x180010057  jz      short loc_180010078
0x180010059  mov     edx, 21h ; '!'
0x18001005e  mov     r9d, ebx
0x180010061  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x180010068  mov     rcx, [rcx+10h]
0x18001006c  call    WPP_SF_d
0x180010071  mov     rcx, cs:WPP_GLOBAL_Control
0x180010078  xor     r12d, r12d
0x18001007b  jmp     loc_180010191
0x180010080  cmp     r13d, 4
0x180010084  jnz     short loc_180010092
0x180010086  cmp     eax, esi
0x180010088  jz      short loc_180010092
0x18001008a  xor     r12d, r12d
0x18001008d  jmp     loc_18000FF66
0x180010092  lea     rcx, g_FwPortKeywordLock
0x180010099  call    cs:__imp_FwCriticalSectionEnter
0x18001009f  mov     r12d, esi
0x1800100a2  lea     r8, [rsp+0C8h+var_3C]
0x1800100aa  lea     rdx, [rsp+0C8h+var_50]
0x1800100af  mov     ecx, r13d
0x1800100b2  call    cs:__imp_FwIOReadPortUseIndications
0x1800100b8  mov     r15d, eax
0x1800100bb  test    eax, eax
0x1800100bd  jns     short loc_1800100ED
0x1800100bf  lea     r14, WPP_GLOBAL_Control
0x1800100c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100cd  cmp     rcx, r14
0x1800100d0  jz      loc_180010191
0x1800100d6  test    [rcx+1Ch], sil
0x1800100da  jz      loc_180010191
0x1800100e0  mov     edx, 22h ; '"'
0x1800100e5  mov     r9d, eax
0x1800100e8  jmp     loc_18001017A
0x1800100ed  mov     [rsp+0C8h+var_A8], 0
0x1800100f6  lea     r9, [rsp+0C8h+var_3C]
0x1800100fe  mov     r8d, [rsp+0C8h+var_84]
0x180010103  movzx   edx, r14w
0x180010107  mov     rcx, [rsp+0C8h+var_50]
0x18001010c  call    cs:__imp_FWIndicatePortInUse_Helper
0x180010112  mov     r8d, [rsp+0C8h+var_3C]
0x18001011a  mov     rdx, [rsp+0C8h+var_50]
0x18001011f  mov     ecx, r13d
0x180010122  call    cs:__imp_FwIOWritePortUseIndications
0x180010128  mov     r15d, eax
0x18001012b  test    eax, eax
0x18001012d  jns     loc_18000FF66
0x180010133  lea     r14, WPP_GLOBAL_Control
0x18001013a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010141  cmp     rcx, r14
0x180010144  jz      short loc_180010191
0x180010146  test    [rcx+1Ch], sil
0x18001014a  jz      short loc_180010191
0x18001014c  mov     edx, 23h ; '#'
0x180010151  jmp     short loc_1800100E5
0x180010153  xor     ebx, ebx
0x180010155  mov     r15d, 80070057h
0x18001015b  lea     r14, WPP_GLOBAL_Control
0x180010162  mov     rcx, cs:WPP_GLOBAL_Control
0x180010169  cmp     rcx, r14
0x18001016c  jz      short loc_180010191
0x18001016e  test    [rcx+1Ch], sil
0x180010172  jz      short loc_180010191
0x180010174  lea     edx, [rbx+1Eh]
0x180010177  mov     r9d, r15d
0x18001017a  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x180010181  mov     rcx, [rcx+10h]
0x180010185  call    WPP_SF_d
0x18001018a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010191  test    r15d, r15d
0x180010194  jns     short loc_1800101A8
0x180010196  mov     ecx, r15d
0x180010199  call    cs:__imp_FwHResultToWindowsError
0x18001019f  mov     ebx, eax
0x1800101a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101a8  cmp     rcx, r14
0x1800101ab  jz      short loc_1800101D2
0x1800101ad  test    [rcx+1Ch], sil
0x1800101b1  jz      short loc_1800101D2
0x1800101b3  mov     edx, 24h ; '$'
0x1800101b8  mov     r9d, ebx
0x1800101bb  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800101c2  mov     rcx, [rcx+10h]
0x1800101c6  call    WPP_SF_d
0x1800101cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101d2  cmp     ebx, 5
0x1800101d5  jnz     short loc_1800101F7
0x1800101d7  cmp     rcx, r14
0x1800101da  jz      short loc_1800101F5
0x1800101dc  test    [rcx+1Ch], sil
0x1800101e0  jz      short loc_1800101F5
0x1800101e2  lea     edx, [rbx+20h]
0x1800101e5  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x1800101ec  mov     rcx, [rcx+10h]
0x1800101f0  call    WPP_SF_
0x1800101f5  xor     ebx, ebx
0x1800101f7  test    ebx, ebx
0x1800101f9  jz      short loc_180010252
0x1800101fb  cmp     [rsp+0C8h+var_78], esi
0x1800101ff  jnz     short loc_180010252
0x180010201  test    r12d, r12d
0x180010204  jnz     short loc_180010216
0x180010206  lea     rcx, g_FwPortKeywordLock
0x18001020d  call    cs:__imp_FwCriticalSectionEnter
0x180010213  mov     r12d, esi
0x180010216  movsxd  rcx, r13d
0x180010219  shl     rcx, 4
0x18001021d  lea     r10, ?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x180010224  lea     r9, [r10+8]
0x180010228  add     r9, rcx
0x18001022b  xor     r8d, r8d
0x18001022e  cmp     [rsp+0C8h+var_84], esi
0x180010232  setnz   r8b
0x180010236  lea     rax, [rsp+0C8h+var_40]
0x18001023e  mov     [rsp+0C8h+var_A8], rax
0x180010243  movzx   edx, [rsp+0C8h+var_88]
0x180010248  mov     rcx, [rcx+r10]
0x18001024c  call    cs:__imp_FWIndicatePortInUse_Helper
0x180010252  cmp     r12d, esi
0x180010255  jnz     short loc_180010264
0x180010257  lea     rcx, g_FwPortKeywordLock
0x18001025e  call    cs:__imp_FwCriticalSectionLeave
0x180010264  mov     rcx, [rsp+0C8h+var_50]
0x180010269  call    cs:__imp_FwBaseFree
0x18001026f  cmp     [rsp+0C8h+Binding], 0
0x180010278  jz      short loc_180010293
0x18001027a  lea     rcx, [rsp+0C8h+Binding]; Binding
0x180010282  call    cs:__imp_RpcBindingFree
0x180010288  test    eax, eax
0x18001028a  jz      short loc_180010293
0x18001028c  mov     edx, eax
0x18001028e  call    MicrosoftTelemetryAssertTriggeredArgs
0x180010293  mov     eax, ebx
0x180010295  mov     rcx, [rsp+0C8h+var_38]
0x18001029d  xor     rcx, rsp; StackCookie
0x1800102a0  call    __security_check_cookie
0x1800102a5  mov     rbx, [rsp+0C8h+arg_18]
0x1800102ad  add     rsp, 0A0h
0x1800102b4  pop     r15
0x1800102b6  pop     r14
0x1800102b8  pop     r13
0x1800102ba  pop     r12
0x1800102bc  pop     rsi
0x1800102bd  retn
0x18005b926  push    rbp
0x18005b928  sub     rsp, 40h
0x18005b92c  mov     rbp, rdx
0x18005b92f  mov     rcx, [rcx]
0x18005b932  mov     ecx, [rcx]; ExceptionCode
0x18005b934  call    cs:__imp_RpcExceptionFilter
0x18005b93a  nop
0x18005b93b  add     rsp, 40h
0x18005b93f  pop     rbp
0x18005b940  retn
```
