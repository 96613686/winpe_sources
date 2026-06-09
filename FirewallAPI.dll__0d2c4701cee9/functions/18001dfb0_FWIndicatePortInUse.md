# FWIndicatePortInUse

- ea: `0x18001dfb0`
- end: `0x18001e493`
- name: `FWIndicatePortInUse`
- size: `1251`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001da20`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x18001dfb0`
- `0x18002094c`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fc5c`
- `RPCRT4!RpcExceptionFilter` at `0x18005fc5c`
- `RPCRT4!NdrClientCall3` at `0x18001e179`
- `RPCRT4!NdrClientCall3` at `0x18001e179`
- `RPCRT4!RpcBindingFree` at `0x18001e450`
- `RPCRT4!RpcBindingFree` at `0x18001e450`
- `fwbase!FwIOWritePortUseIndications` at `0x18001e2cc`
- `fwbase!FwIOWritePortUseIndications` at `0x18001e2cc`
- `fwbase!FwIOReadPortUseIndications` at `0x18001e250`
- `fwbase!FwIOReadPortUseIndications` at `0x18001e250`
- `fwbase!FwCriticalSectionEnter` at `0x18001e08b`
- `fwbase!FwCriticalSectionEnter` at `0x18001e231`
- `fwbase!FwCriticalSectionEnter` at `0x18001e3c3`
- `fwbase!FwCriticalSectionEnter` at `0x18001e08b`
- `fwbase!FwCriticalSectionEnter` at `0x18001e231`
- `fwbase!FwCriticalSectionEnter` at `0x18001e3c3`
- `fwbase!FwCriticalSectionLeave` at `0x18001e13d`
- `fwbase!FwCriticalSectionLeave` at `0x18001e420`
- `fwbase!FwCriticalSectionLeave` at `0x18001e13d`
- `fwbase!FwCriticalSectionLeave` at `0x18001e420`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e11c`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e2b0`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e408`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e11c`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e2b0`
- `fwbase!FWIndicatePortInUse_Helper` at `0x18001e408`
- `fwbase!FwBaseFree` at `0x18001e431`
- `fwbase!FwBaseFree` at `0x18001e431`
- `fwbase!FwHResultToWindowsError` at `0x18001e349`
- `fwbase!FwHResultToWindowsError` at `0x18001e349`

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
    FWIndicatePortInUse_Helper(PortCollCache, (unsigned __int16)v3, a3, qword_18009B688, &v24);
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
    FWIndicatePortInUse_Helper(*(&PortCollCache + 2 * (int)a1), a2, a3 != 1, &qword_18009B688[2 * (int)a1], &v24);
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
0x18001dfb0  mov     r11, rsp
0x18001dfb3  mov     [r11+20h], rbx
0x18001dfb7  push    rsi
0x18001dfb8  push    r12
0x18001dfba  push    r13
0x18001dfbc  push    r14
0x18001dfbe  push    r15
0x18001dfc0  sub     rsp, 0A0h
0x18001dfc7  mov     rax, cs:__security_cookie
0x18001dfce  xor     rax, rsp
0x18001dfd1  mov     [rsp+0C8h+var_38], rax
0x18001dfd9  mov     [rsp+0C8h+var_84], r8d
0x18001dfde  movzx   r14d, dx
0x18001dfe2  mov     [rsp+0C8h+var_88], r14w
0x18001dfe8  mov     r13d, ecx
0x18001dfeb  mov     [rsp+0C8h+var_68], ecx
0x18001dfef  mov     [rsp+0C8h+var_80], r14w
0x18001dff5  mov     [rsp+0C8h+var_60], r8d
0x18001dffa  mov     qword ptr [r11-50h], 0
0x18001e002  mov     dword ptr [r11-3Ch], 0
0x18001e00a  xor     r12d, r12d
0x18001e00d  mov     [r11-48h], r12
0x18001e011  lea     esi, [r12+1]
0x18001e016  mov     [r11-40h], esi
0x18001e01a  mov     [rsp+0C8h+var_78], r12d
0x18001e01f  cmp     ecx, 8
0x18001e022  ja      loc_18001E303
0x18001e028  xor     r15d, r15d
0x18001e02b  mov     [rsp+0C8h+var_70], r15d
0x18001e030  lea     rcx, [r11-48h]
0x18001e034  call    Int_FWLocalRpcBindingCreate
0x18001e039  mov     ebx, eax
0x18001e03b  test    eax, eax
0x18001e03d  jz      short loc_18001E07B
0x18001e03f  lea     r14, WPP_GLOBAL_Control
0x18001e046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e04d  cmp     rcx, r14
0x18001e050  jz      loc_18001E341
0x18001e056  test    [rcx+1Ch], sil
0x18001e05a  jz      loc_18001E341
0x18001e060  lea     edx, [rsi+1Eh]
0x18001e063  mov     r9d, eax
0x18001e066  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001e06d  mov     rcx, [rcx+10h]
0x18001e071  call    WPP_SF_d
0x18001e076  jmp     loc_18001E33A
0x18001e07b  test    r13d, r13d
0x18001e07e  jnz     loc_18001E14A
0x18001e084  lea     rcx, g_FwPortKeywordLock
0x18001e08b  call    cs:__imp_FwCriticalSectionEnter
0x18001e092  nop     dword ptr [rax+rax+00h]
0x18001e097  mov     r12d, esi
0x18001e09a  xor     ecx, ecx
0x18001e09c  call    ?FwInitPortCollCache@@YAKW4_tag_FW_PORT_COLLECTION_TYPE@@@Z; FwInitPortCollCache(_tag_FW_PORT_COLLECTION_TYPE)
0x18001e0a1  mov     ebx, eax
0x18001e0a3  test    eax, eax
0x18001e0a5  jz      short loc_18001E0CE
0x18001e0a7  lea     r14, WPP_GLOBAL_Control
0x18001e0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0b5  cmp     rcx, r14
0x18001e0b8  jz      loc_18001E341
0x18001e0be  test    [rcx+1Ch], sil
0x18001e0c2  jz      loc_18001E341
0x18001e0c8  lea     edx, [r13+20h]
0x18001e0cc  jmp     short loc_18001E063
0x18001e0ce  mov     eax, 87h
0x18001e0d3  cmp     r14w, ax
0x18001e0d7  jz      short loc_18001E0F8
0x18001e0d9  mov     eax, 251h
0x18001e0de  cmp     r14w, ax
0x18001e0e2  jz      short loc_18001E0F8
0x18001e0e4  mov     [rsp+0C8h+var_40], r15d
0x18001e0ec  lea     r14, WPP_GLOBAL_Control
0x18001e0f3  jmp     loc_18001E33A
0x18001e0f8  lea     rax, [rsp+0C8h+var_40]
0x18001e100  mov     [rsp+0C8h+var_A8], rax
0x18001e105  lea     r9, qword_18009B688
0x18001e10c  mov     r8d, [rsp+0C8h+var_84]
0x18001e111  movzx   edx, r14w
0x18001e115  mov     rcx, cs:?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x18001e11c  call    cs:__imp_FWIndicatePortInUse_Helper
0x18001e123  nop     dword ptr [rax+rax+00h]
0x18001e128  mov     [rsp+0C8h+var_78], esi
0x18001e12c  cmp     [rsp+0C8h+var_40], r15d
0x18001e134  jz      short loc_18001E0EC
0x18001e136  lea     rcx, g_FwPortKeywordLock
0x18001e13d  call    cs:__imp_FwCriticalSectionLeave
0x18001e144  nop     dword ptr [rax+rax+00h]
0x18001e149  nop
0x18001e14a  mov     [rsp+0C8h+var_58], 0
0x18001e153  mov     ecx, [rsp+0C8h+var_84]
0x18001e157  mov     [rsp+0C8h+var_98], ecx
0x18001e15b  mov     [rsp+0C8h+var_A0], r14d
0x18001e160  mov     dword ptr [rsp+0C8h+var_A8], r13d
0x18001e165  mov     r9, [rsp+0C8h+Binding]
0x18001e16d  xor     r8d, r8d; pReturnValue
0x18001e170  xor     edx, edx; nProcNum
0x18001e172  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001e179  call    cs:__imp_NdrClientCall3
0x18001e180  nop     dword ptr [rax+rax+00h]
0x18001e185  mov     rbx, rax
0x18001e188  mov     [rsp+0C8h+var_58], rax
0x18001e18d  mov     [rsp+0C8h+var_74], eax
0x18001e191  jmp     short loc_18001E1BC
0x18001e193  mov     ebx, eax
0x18001e195  mov     [rsp+0C8h+var_74], eax
0x18001e199  mov     esi, 1
0x18001e19e  mov     r15d, [rsp+0C8h+var_70]
0x18001e1a3  movzx   r14d, [rsp+0C8h+var_80]
0x18001e1a9  mov     [rsp+0C8h+var_88], r14w
0x18001e1af  mov     r13d, [rsp+0C8h+var_68]
0x18001e1b4  mov     eax, [rsp+0C8h+var_60]
0x18001e1b8  mov     [rsp+0C8h+var_84], eax
0x18001e1bc  cmp     ebx, 6D9h
0x18001e1c2  jz      short loc_18001E1D0
0x18001e1c4  cmp     ebx, 80320044h
0x18001e1ca  jz      short loc_18001E1D0
0x18001e1cc  xor     eax, eax
0x18001e1ce  jmp     short loc_18001E1D4
0x18001e1d0  mov     eax, esi
0x18001e1d2  xor     ebx, ebx
0x18001e1d4  test    ebx, ebx
0x18001e1d6  jz      short loc_18001E218
0x18001e1d8  lea     r14, WPP_GLOBAL_Control
0x18001e1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1e6  cmp     rcx, r14
0x18001e1e9  jz      short loc_18001E210
0x18001e1eb  test    [rcx+1Ch], sil
0x18001e1ef  jz      short loc_18001E210
0x18001e1f1  mov     edx, 21h ; '!'
0x18001e1f6  mov     r9d, ebx
0x18001e1f9  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001e200  mov     rcx, [rcx+10h]
0x18001e204  call    WPP_SF_d
0x18001e209  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e210  xor     r12d, r12d
0x18001e213  jmp     loc_18001E341
0x18001e218  cmp     r13d, 4
0x18001e21c  jnz     short loc_18001E22A
0x18001e21e  cmp     eax, esi
0x18001e220  jz      short loc_18001E22A
0x18001e222  xor     r12d, r12d
0x18001e225  jmp     loc_18001E0EC
0x18001e22a  lea     rcx, g_FwPortKeywordLock
0x18001e231  call    cs:__imp_FwCriticalSectionEnter
0x18001e238  nop     dword ptr [rax+rax+00h]
0x18001e23d  mov     r12d, esi
0x18001e240  lea     r8, [rsp+0C8h+var_3C]
0x18001e248  lea     rdx, [rsp+0C8h+var_50]
0x18001e24d  mov     ecx, r13d
0x18001e250  call    cs:__imp_FwIOReadPortUseIndications
0x18001e257  nop     dword ptr [rax+rax+00h]
0x18001e25c  mov     r15d, eax
0x18001e25f  test    eax, eax
0x18001e261  jns     short loc_18001E291
0x18001e263  lea     r14, WPP_GLOBAL_Control
0x18001e26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e271  cmp     rcx, r14
0x18001e274  jz      loc_18001E341
0x18001e27a  test    [rcx+1Ch], sil
0x18001e27e  jz      loc_18001E341
0x18001e284  mov     edx, 22h ; '"'
0x18001e289  mov     r9d, eax
0x18001e28c  jmp     loc_18001E32A
0x18001e291  mov     [rsp+0C8h+var_A8], 0
0x18001e29a  lea     r9, [rsp+0C8h+var_3C]
0x18001e2a2  mov     r8d, [rsp+0C8h+var_84]
0x18001e2a7  movzx   edx, r14w
0x18001e2ab  mov     rcx, [rsp+0C8h+var_50]
0x18001e2b0  call    cs:__imp_FWIndicatePortInUse_Helper
0x18001e2b7  nop     dword ptr [rax+rax+00h]
0x18001e2bc  mov     r8d, [rsp+0C8h+var_3C]
0x18001e2c4  mov     rdx, [rsp+0C8h+var_50]
0x18001e2c9  mov     ecx, r13d
0x18001e2cc  call    cs:__imp_FwIOWritePortUseIndications
0x18001e2d3  nop     dword ptr [rax+rax+00h]
0x18001e2d8  mov     r15d, eax
0x18001e2db  test    eax, eax
0x18001e2dd  jns     loc_18001E0EC
0x18001e2e3  lea     r14, WPP_GLOBAL_Control
0x18001e2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2f1  cmp     rcx, r14
0x18001e2f4  jz      short loc_18001E341
0x18001e2f6  test    [rcx+1Ch], sil
0x18001e2fa  jz      short loc_18001E341
0x18001e2fc  mov     edx, 23h ; '#'
0x18001e301  jmp     short loc_18001E289
0x18001e303  xor     ebx, ebx
0x18001e305  mov     r15d, 80070057h
0x18001e30b  lea     r14, WPP_GLOBAL_Control
0x18001e312  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e319  cmp     rcx, r14
0x18001e31c  jz      short loc_18001E341
0x18001e31e  test    [rcx+1Ch], sil
0x18001e322  jz      short loc_18001E341
0x18001e324  lea     edx, [rbx+1Eh]
0x18001e327  mov     r9d, r15d
0x18001e32a  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001e331  mov     rcx, [rcx+10h]
0x18001e335  call    WPP_SF_d
0x18001e33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e341  test    r15d, r15d
0x18001e344  jns     short loc_18001E35E
0x18001e346  mov     ecx, r15d
0x18001e349  call    cs:__imp_FwHResultToWindowsError
0x18001e350  nop     dword ptr [rax+rax+00h]
0x18001e355  mov     ebx, eax
0x18001e357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e35e  cmp     rcx, r14
0x18001e361  jz      short loc_18001E388
0x18001e363  test    [rcx+1Ch], sil
0x18001e367  jz      short loc_18001E388
0x18001e369  mov     edx, 24h ; '$'
0x18001e36e  mov     r9d, ebx
0x18001e371  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001e378  mov     rcx, [rcx+10h]
0x18001e37c  call    WPP_SF_d
0x18001e381  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e388  cmp     ebx, 5
0x18001e38b  jnz     short loc_18001E3AD
0x18001e38d  cmp     rcx, r14
0x18001e390  jz      short loc_18001E3AB
0x18001e392  test    [rcx+1Ch], sil
0x18001e396  jz      short loc_18001E3AB
0x18001e398  lea     edx, [rbx+20h]
0x18001e39b  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001e3a2  mov     rcx, [rcx+10h]
0x18001e3a6  call    WPP_SF_
0x18001e3ab  xor     ebx, ebx
0x18001e3ad  test    ebx, ebx
0x18001e3af  jz      short loc_18001E414
0x18001e3b1  cmp     [rsp+0C8h+var_78], esi
0x18001e3b5  jnz     short loc_18001E414
0x18001e3b7  test    r12d, r12d
0x18001e3ba  jnz     short loc_18001E3D2
0x18001e3bc  lea     rcx, g_FwPortKeywordLock
0x18001e3c3  call    cs:__imp_FwCriticalSectionEnter
0x18001e3ca  nop     dword ptr [rax+rax+00h]
0x18001e3cf  mov     r12d, esi
0x18001e3d2  movsxd  rcx, r13d
0x18001e3d5  shl     rcx, 4
0x18001e3d9  lea     r10, ?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x18001e3e0  lea     r9, [r10+8]
0x18001e3e4  add     r9, rcx
0x18001e3e7  xor     r8d, r8d
0x18001e3ea  cmp     [rsp+0C8h+var_84], esi
0x18001e3ee  setnz   r8b
0x18001e3f2  lea     rax, [rsp+0C8h+var_40]
0x18001e3fa  mov     [rsp+0C8h+var_A8], rax
0x18001e3ff  movzx   edx, [rsp+0C8h+var_88]
0x18001e404  mov     rcx, [rcx+r10]
0x18001e408  call    cs:__imp_FWIndicatePortInUse_Helper
0x18001e40f  nop     dword ptr [rax+rax+00h]
0x18001e414  cmp     r12d, esi
0x18001e417  jnz     short loc_18001E42C
0x18001e419  lea     rcx, g_FwPortKeywordLock
0x18001e420  call    cs:__imp_FwCriticalSectionLeave
0x18001e427  nop     dword ptr [rax+rax+00h]
0x18001e42c  mov     rcx, [rsp+0C8h+var_50]
0x18001e431  call    cs:__imp_FwBaseFree
0x18001e438  nop     dword ptr [rax+rax+00h]
0x18001e43d  cmp     [rsp+0C8h+Binding], 0
0x18001e446  jz      short loc_18001E467
0x18001e448  lea     rcx, [rsp+0C8h+Binding]; Binding
0x18001e450  call    cs:__imp_RpcBindingFree
0x18001e457  nop     dword ptr [rax+rax+00h]
0x18001e45c  test    eax, eax
0x18001e45e  jz      short loc_18001E467
0x18001e460  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18001e462  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001e467  mov     eax, ebx
0x18001e469  mov     rcx, [rsp+0C8h+var_38]
0x18001e471  xor     rcx, rsp; StackCookie
0x18001e474  call    __security_check_cookie
0x18001e479  mov     rbx, [rsp+0C8h+arg_18]
0x18001e481  add     rsp, 0A0h
0x18001e488  pop     r15
0x18001e48a  pop     r14
0x18001e48c  pop     r13
0x18001e48e  pop     r12
0x18001e490  pop     rsi
0x18001e491  retn
0x18005fc4e  push    rbp
0x18005fc50  sub     rsp, 40h
0x18005fc54  mov     rbp, rdx
0x18005fc57  mov     rcx, [rcx]
0x18005fc5a  mov     ecx, [rcx]; ExceptionCode
0x18005fc5c  call    cs:__imp_RpcExceptionFilter
0x18005fc63  nop     dword ptr [rax+rax+00h]
0x18005fc68  nop
0x18005fc69  add     rsp, 40h
0x18005fc6d  pop     rbp
0x18005fc6e  retn
```
