# FWOpenPolicyStore

- ea: `0x18000c560`
- end: `0x18000cd87`
- name: `FWOpenPolicyStore`
- size: `2087`
- prototype: `__int64 __fastcall(unsigned __int16, __int64, unsigned int, unsigned int, unsigned int, _QWORD *)`
- caller_count: `44`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001e58`
- `0x1800021f0`
- `0x18000270c`
- `0x180002e3c`
- `0x180003194`
- `0x180003454`
- `0x180003a30`
- `0x18000470c`
- `0x180005a50`
- `0x180006394`
- `0x1800069b0`
- `0x180006b40`
- `0x18000a980`
- `0x18000b050`
- `0x18000b34c`
- `0x18000b390`
- `0x18000bcd0`
- `0x18000bea0`
- `0x180011120`
- `0x180013f78`
- `0x180018ef0`
- `0x18001a744`
- `0x18001dd10`
- `0x180020370`
- `0x180023d88`
- `0x180025744`
- `0x180026de8`
- `0x180026f50`
- `0x18002e484`
- `0x180030ab8`
- `0x180032ac0`
- `0x180032de0`
- `0x180032f90`
- `0x1800332c0`
- `0x180033630`
- `0x180042740`
- `0x180046370`
- `0x180047734`
- `0x18004ae10`
- `0x18004c230`
- `0x18004cb70`
- `0x18004f6e0`
- `0x180050f10`
- `0x1800587a0`

## callees

- `0x180005954`
- `0x18000c560`
- `0x18000d850`
- `0x18000e6c0`
- `0x18000ebe0`
- `0x180017e70`
- `0x1800277b0`
- `0x18003104c`
- `0x180036fcc`
- `0x18004a8f0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b85e`
- `RPCRT4!RpcExceptionFilter` at `0x18005b87a`
- `RPCRT4!RpcExceptionFilter` at `0x18005b85e`
- `RPCRT4!RpcExceptionFilter` at `0x18005b87a`
- `RPCRT4!NdrClientCall3` at `0x18000ca82`
- `RPCRT4!NdrClientCall3` at `0x18000cb89`
- `RPCRT4!NdrClientCall3` at `0x18000ca82`
- `RPCRT4!NdrClientCall3` at `0x18000cb89`
- `ntdll!EtwEventWrite` at `0x18000c5cb`
- `ntdll!EtwEventWrite` at `0x18000cd5c`
- `ntdll!EtwEventWrite` at `0x18000c5cb`
- `ntdll!EtwEventWrite` at `0x18000cd5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c631`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c631`
- `fwbase!FwBaseAlloc` at `0x18000c7ff`
- `fwbase!FwBaseAlloc` at `0x18000c7ff`
- `fwbase!FwBaseFree` at `0x18000cd16`
- `fwbase!FwBaseFree` at `0x18000cd16`

## pseudocode

```c
__int64 __fastcall FWOpenPolicyStore(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        _QWORD *a6)
{
  _OWORD *v9; // rsi
  unsigned int started; // eax
  FwPolicy2 *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned __int16 v14; // r15
  unsigned __int64 v15; // rax
  _OWORD *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int Pointer; // eax
  unsigned int v24; // eax
  __int64 v26; // [rsp+20h] [rbp-B8h]
  __int64 v27; // [rsp+28h] [rbp-B0h]
  __int64 v28; // [rsp+30h] [rbp-A8h]
  unsigned int v29; // [rsp+58h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-50h] BYREF
  int v32; // [rsp+8Ch] [rbp-4Ch] BYREF

  v29 = a4;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_OpenPolicyStore, 0, 0);
    LOBYTE(a4) = v29;
  }
  v9 = 0;
  v32 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Sddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
      a2,
      a3,
      a4,
      a5);
  GetTickCount64();
  started = Int_FwStartFirewallService();
  if ( !started )
    goto LABEL_10;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, started);
LABEL_10:
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    v12 = 87;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v13 = 18;
LABEL_112:
      v18 = v12;
      goto LABEL_113;
    }
    goto LABEL_115;
  }
  v14 = 512;
  if ( (unsigned __int16)(a1 - 512) > 0x21u )
  {
    v12 = 1306;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v13 = 19;
      goto LABEL_112;
    }
    goto LABEL_115;
  }
  if ( a3 - 1 > 0xB )
  {
    v12 = 87;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v13 = 20;
      goto LABEL_112;
    }
    goto LABEL_115;
  }
  if ( v29 - 1 > 1 )
  {
    v12 = 87;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v13 = 21;
      goto LABEL_112;
    }
    goto LABEL_115;
  }
  if ( a5 < 0x20 )
  {
    if ( a3 == 1 && v29 != 1 )
    {
      v12 = 5;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v13 = 23;
        goto LABEL_112;
      }
      goto LABEL_115;
    }
    if ( a3 == 3 && v29 != 1 )
    {
      v12 = 5;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v13 = 24;
        goto LABEL_112;
      }
      goto LABEL_115;
    }
    if ( a3 != 5 && (a5 & 1) != 0 )
    {
      v12 = 87;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v13 = 25;
        goto LABEL_112;
      }
      goto LABEL_115;
    }
    if ( a3 != 6 )
    {
      if ( a2 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(a2 + 2 * v15) );
        if ( v15 > 0xFF )
        {
          v12 = 87;
          if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
          {
            v13 = 26;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
      }
    }
    if ( (a5 & 0xE) != 0 && a3 != 6 )
    {
      v12 = 87;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v13 = 27;
        goto LABEL_112;
      }
      goto LABEL_115;
    }
    *a6 = 0;
    v16 = (_OWORD *)FwBaseAlloc(80);
    v9 = v16;
    if ( !v16 )
    {
      v12 = 14;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 28;
        goto LABEL_112;
      }
      goto LABEL_115;
    }
    *v16 = 0;
    v16[1] = 0;
    v16[2] = 0;
    v16[3] = 0;
    v16[4] = 0;
    v17 = Int_FWCreateConnectionHandle(a1, a2, a3, v29, a5, v16);
    v12 = v17;
    if ( v17 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_115;
      v13 = 29;
      v18 = v17;
      goto LABEL_113;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::GetImpl'::`2'::impl) )
    {
      if ( a1 > 0x200u && *((_DWORD *)v9 + 1) <= 1u && (a5 != 16 || a2) )
      {
        v32 = 4;
        v19 = FWGetGlobalConfig(512, a2, 5, 11, 0, (__int64)&v31, (__int64)&v32);
        v12 = v19;
        if ( v19 == 1783 || v19 == 87 )
        {
          v12 = 0;
          v31 = 512;
        }
        else
        {
          v14 = v31;
        }
        if ( v12 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 30;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        if ( a1 > v14 )
          a1 = v14;
      }
    }
    else if ( a1 > 0x200u && *((_DWORD *)v9 + 1) <= 1u )
    {
      v32 = 4;
      v20 = FWGetGlobalConfig(512, a2, 5, 11, 0, (__int64)&v31, (__int64)&v32);
      v12 = v20;
      if ( v20 == 1783 || v20 == 87 )
      {
        v12 = 0;
        v31 = 512;
      }
      else
      {
        v14 = v31;
      }
      if ( v12 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 31;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( a1 > v14 )
        a1 = v14;
    }
    *((_WORD *)v9 + 1) = a1;
    v21 = *((_DWORD *)v9 + 1);
    if ( v21 )
    {
      if ( v21 == 1 )
      {
        LODWORD(v28) = v29;
        LODWORD(v27) = a3;
        LODWORD(v26) = a1;
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&RemoteFW_ProxyInfo,
                                  0,
                                  0,
                                  *((_QWORD *)v9 + 4),
                                  v26,
                                  v27,
                                  v28,
                                  a5,
                                  (char *)v9 + 40).Pointer;
        v12 = Pointer;
        if ( Pointer )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Pointer);
            v11 = WPP_GLOBAL_Control;
          }
          goto LABEL_115;
        }
        v32 = 4;
        v24 = FWGetGlobalConfig(a1, a2, 5, 1, 0, (__int64)(v9 + 3), (__int64)&v32);
        v12 = v24;
        if ( v24 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_115;
          v13 = 36;
          v18 = v24;
LABEL_113:
          WPP_SF_d(*((_QWORD *)v11 + 2), v13, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v18);
          goto LABEL_114;
        }
      }
    }
    else
    {
      LODWORD(v28) = v29;
      LODWORD(v27) = a3;
      LODWORD(v26) = a1;
      v22 = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&FW_ProxyInfo,
                            0,
                            0,
                            *((_QWORD *)v9 + 4),
                            v26,
                            v27,
                            v28,
                            a5,
                            (char *)v9 + 40).Pointer;
      v12 = v22;
      if ( v22 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v22);
          v11 = WPP_GLOBAL_Control;
        }
        goto LABEL_115;
      }
      *((_DWORD *)v9 + 12) = 545;
    }
    *a6 = v9;
LABEL_114:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_115;
  }
  v12 = 87;
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
  {
    v13 = 22;
    goto LABEL_112;
  }
LABEL_115:
  if ( v12 )
  {
    Int_FWClientHandleCleanup(v9);
    FwBaseFree(v9);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v11 + 2), 37, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_OpenPolicyStore, 0, 0);
  return v12;
}

```

## disassembly

```asm
0x18000c560  push    rbx
0x18000c562  push    rsi
0x18000c563  push    rdi
0x18000c564  push    r12
0x18000c566  push    r13
0x18000c568  push    r14
0x18000c56a  push    r15
0x18000c56c  sub     rsp, 0A0h
0x18000c573  mov     rax, cs:__security_cookie
0x18000c57a  xor     rax, rsp
0x18000c57d  mov     [rsp+0D8h+var_48], rax
0x18000c585  mov     [rsp+0D8h+var_80], r9d
0x18000c58a  mov     ebx, r8d
0x18000c58d  mov     [rsp+0D8h+var_78], ebx
0x18000c591  mov     r12, rdx
0x18000c594  movzx   r14d, cx
0x18000c598  mov     [rsp+0D8h+var_88], cx
0x18000c59d  mov     [rsp+0D8h+var_58], rdx
0x18000c5a5  mov     r15, [rsp+0D8h+arg_28]
0x18000c5ad  mov     [rsp+0D8h+var_68], r15
0x18000c5b2  mov     rcx, cs:g_Provider
0x18000c5b9  test    rcx, rcx
0x18000c5bc  jz      short loc_18000C5D6
0x18000c5be  xor     r9d, r9d
0x18000c5c1  xor     r8d, r8d
0x18000c5c4  lea     rdx, MPS_CLNT_API_Enter_OpenPolicyStore
0x18000c5cb  call    cs:__imp_EtwEventWrite
0x18000c5d1  mov     r9d, [rsp+0D8h+var_80]
0x18000c5d6  xor     r13d, r13d
0x18000c5d9  mov     esi, r13d
0x18000c5dc  mov     [rsp+0D8h+var_4C], r13d
0x18000c5e4  mov     [rsp+0D8h+var_50], r13d
0x18000c5ec  lea     rdi, WPP_GLOBAL_Control
0x18000c5f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5fa  cmp     rcx, rdi
0x18000c5fd  jz      short loc_18000C631
0x18000c5ff  test    byte ptr [rcx+1Ch], 8
0x18000c603  jz      short loc_18000C631
0x18000c605  mov     edx, 10h
0x18000c60a  mov     eax, [rsp+0D8h+arg_20]
0x18000c611  mov     dword ptr [rsp+0D8h+var_A8], eax
0x18000c615  mov     dword ptr [rsp+0D8h+var_B0], r9d
0x18000c61a  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000c61e  mov     r9, r12
0x18000c621  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c628  mov     rcx, [rcx+10h]
0x18000c62c  call    WPP_SF_Sddd
0x18000c631  call    cs:__imp_GetTickCount64
0x18000c637  call    Int_FwStartFirewallService
0x18000c63c  test    eax, eax
0x18000c63e  jz      short loc_18000C66A
0x18000c640  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c647  cmp     rcx, rdi
0x18000c64a  jz      short loc_18000C671
0x18000c64c  test    byte ptr [rcx+1Ch], 1
0x18000c650  jz      short loc_18000C671
0x18000c652  mov     edx, 11h
0x18000c657  mov     r9d, eax
0x18000c65a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000c661  mov     rcx, [rcx+10h]
0x18000c665  call    WPP_SF_d
0x18000c66a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c671  test    r15, r15
0x18000c674  jnz     short loc_18000C698
0x18000c676  mov     ebx, 57h ; 'W'
0x18000c67b  cmp     rcx, rdi
0x18000c67e  jz      loc_18000CD07
0x18000c684  test    byte ptr [rcx+1Ch], 1
0x18000c688  jz      loc_18000CD07
0x18000c68e  mov     edx, 12h
0x18000c693  jmp     loc_18000CCED
0x18000c698  mov     r15d, 200h
0x18000c69e  movzx   eax, r14w
0x18000c6a2  sub     ax, r15w
0x18000c6a6  cmp     ax, 21h ; '!'
0x18000c6aa  ja      loc_18000CCD8
0x18000c6b0  lea     eax, [rbx-1]
0x18000c6b3  cmp     eax, 0Bh
0x18000c6b6  ja      loc_18000CCC1
0x18000c6bc  mov     r8d, [rsp+0D8h+var_80]
0x18000c6c1  lea     eax, [r8-1]
0x18000c6c5  cmp     eax, 1
0x18000c6c8  ja      loc_18000CCAA
0x18000c6ce  mov     edx, [rsp+0D8h+arg_20]
0x18000c6d5  cmp     edx, 20h ; ' '
0x18000c6d8  jb      short loc_18000C6FC
0x18000c6da  mov     ebx, 57h ; 'W'
0x18000c6df  cmp     rcx, rdi
0x18000c6e2  jz      loc_18000CD07
0x18000c6e8  test    byte ptr [rcx+1Ch], 1
0x18000c6ec  jz      loc_18000CD07
0x18000c6f2  mov     edx, 16h
0x18000c6f7  jmp     loc_18000CCED
0x18000c6fc  cmp     ebx, 1
0x18000c6ff  jnz     short loc_18000C728
0x18000c701  cmp     r8d, ebx
0x18000c704  jz      short loc_18000C728
0x18000c706  mov     ebx, 5
0x18000c70b  cmp     rcx, rdi
0x18000c70e  jz      loc_18000CD07
0x18000c714  test    byte ptr [rcx+1Ch], 1
0x18000c718  jz      loc_18000CD07
0x18000c71e  mov     edx, 17h
0x18000c723  jmp     loc_18000CCED
0x18000c728  cmp     ebx, 3
0x18000c72b  jnz     short loc_18000C755
0x18000c72d  cmp     r8d, 1
0x18000c731  jz      short loc_18000C755
0x18000c733  mov     ebx, 5
0x18000c738  cmp     rcx, rdi
0x18000c73b  jz      loc_18000CD07
0x18000c741  test    byte ptr [rcx+1Ch], 1
0x18000c745  jz      loc_18000CD07
0x18000c74b  mov     edx, 18h
0x18000c750  jmp     loc_18000CCED
0x18000c755  cmp     ebx, 5
0x18000c758  jz      short loc_18000C781
0x18000c75a  test    dl, 1
0x18000c75d  jz      short loc_18000C781
0x18000c75f  mov     ebx, 57h ; 'W'
0x18000c764  cmp     rcx, rdi
0x18000c767  jz      loc_18000CD07
0x18000c76d  test    byte ptr [rcx+1Ch], 1
0x18000c771  jz      loc_18000CD07
0x18000c777  mov     edx, 19h
0x18000c77c  jmp     loc_18000CCED
0x18000c781  cmp     ebx, 6
0x18000c784  jz      short loc_18000C7C6
0x18000c786  test    r12, r12
0x18000c789  jz      short loc_18000C7C6
0x18000c78b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c792  inc     rax
0x18000c795  cmp     [r12+rax*2], si
0x18000c79a  jnz     short loc_18000C792
0x18000c79c  cmp     rax, 0FFh
0x18000c7a2  jbe     short loc_18000C7C6
0x18000c7a4  mov     ebx, 57h ; 'W'
0x18000c7a9  cmp     rcx, rdi
0x18000c7ac  jz      loc_18000CD07
0x18000c7b2  test    byte ptr [rcx+1Ch], 1
0x18000c7b6  jz      loc_18000CD07
0x18000c7bc  mov     edx, 1Ah
0x18000c7c1  jmp     loc_18000CCED
0x18000c7c6  test    dl, 0Eh
0x18000c7c9  jz      short loc_18000C7F2
0x18000c7cb  cmp     ebx, 6
0x18000c7ce  jz      short loc_18000C7F2
0x18000c7d0  mov     ebx, 57h ; 'W'
0x18000c7d5  cmp     rcx, rdi
0x18000c7d8  jz      loc_18000CD07
0x18000c7de  test    byte ptr [rcx+1Ch], 1
0x18000c7e2  jz      loc_18000CD07
0x18000c7e8  mov     edx, 1Bh
0x18000c7ed  jmp     loc_18000CCED
0x18000c7f2  mov     rax, [rsp+0D8h+var_68]
0x18000c7f7  mov     [rax], r13
0x18000c7fa  mov     ecx, 50h ; 'P'
0x18000c7ff  call    cs:__imp_FwBaseAlloc
0x18000c805  mov     rsi, rax
0x18000c808  mov     [rsp+0D8h+var_70], rax
0x18000c80d  test    rax, rax
0x18000c810  jnz     short loc_18000C83B
0x18000c812  mov     ebx, 0Eh
0x18000c817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c81e  cmp     rcx, rdi
0x18000c821  jz      loc_18000CD07
0x18000c827  test    byte ptr [rcx+1Ch], 1
0x18000c82b  jz      loc_18000CD07
0x18000c831  mov     edx, 1Ch
0x18000c836  jmp     loc_18000CCED
0x18000c83b  xorps   xmm0, xmm0
0x18000c83e  movups  xmmword ptr [rax], xmm0
0x18000c841  movups  xmmword ptr [rax+10h], xmm0
0x18000c845  movups  xmmword ptr [rax+20h], xmm0
0x18000c849  movups  xmmword ptr [rax+30h], xmm0
0x18000c84d  movups  xmmword ptr [rax+40h], xmm0
0x18000c851  mov     [rsp+0D8h+var_B0], rsi
0x18000c856  mov     eax, [rsp+0D8h+arg_20]
0x18000c85d  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000c861  mov     r9d, [rsp+0D8h+var_80]
0x18000c866  mov     r8d, ebx
0x18000c869  mov     rdx, r12
0x18000c86c  movzx   ecx, r14w
0x18000c870  call    Int_FWCreateConnectionHandle
0x18000c875  mov     ebx, eax
0x18000c877  test    eax, eax
0x18000c879  jz      short loc_18000C8A2
0x18000c87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c882  cmp     rcx, rdi
0x18000c885  jz      loc_18000CD07
0x18000c88b  test    byte ptr [rcx+1Ch], 1
0x18000c88f  jz      loc_18000CD07
0x18000c895  mov     edx, 1Dh
0x18000c89a  mov     r9d, eax
0x18000c89d  jmp     loc_18000CCF0
0x18000c8a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation> `wil::Feature<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::GetImpl(void)'::`2'::impl
0x18000c8a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::__private_IsEnabled(void)
0x18000c8ae  test    al, al
0x18000c8b0  jz      loc_18000C982
0x18000c8b6  cmp     r14w, r15w
0x18000c8ba  jbe     loc_18000CA31
0x18000c8c0  cmp     dword ptr [rsi+4], 1
0x18000c8c4  ja      loc_18000CA31
0x18000c8ca  cmp     [rsp+0D8h+arg_20], 10h
0x18000c8d2  jnz     short loc_18000C8DD
0x18000c8d4  test    r12, r12
0x18000c8d7  jz      loc_18000CA31
0x18000c8dd  mov     [rsp+0D8h+var_4C], 4
0x18000c8e8  mov     ecx, r15d
0x18000c8eb  lea     rax, [rsp+0D8h+var_4C]
0x18000c8f3  mov     [rsp+0D8h+var_A8], rax
0x18000c8f8  lea     rax, [rsp+0D8h+var_50]
0x18000c900  mov     [rsp+0D8h+var_B0], rax
0x18000c905  mov     dword ptr [rsp+0D8h+var_B8], r13d
0x18000c90a  mov     r9d, 0Bh
0x18000c910  mov     r8d, 5
0x18000c916  mov     rdx, r12
0x18000c919  call    FWGetGlobalConfig
0x18000c91e  mov     ebx, eax
0x18000c920  cmp     eax, 6F7h
0x18000c925  jz      short loc_18000C936
0x18000c927  cmp     eax, 57h ; 'W'
0x18000c92a  jz      short loc_18000C936
0x18000c92c  mov     r15d, [rsp+0D8h+var_50]
0x18000c934  jmp     short loc_18000C941
0x18000c936  mov     ebx, r13d
0x18000c939  mov     [rsp+0D8h+var_50], r15d
0x18000c941  test    ebx, ebx
0x18000c943  jz      short loc_18000C969
0x18000c945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c94c  cmp     rcx, rdi
0x18000c94f  jz      loc_18000CD07
0x18000c955  test    byte ptr [rcx+1Ch], 1
0x18000c959  jz      loc_18000CD07
0x18000c95f  mov     edx, 1Eh
0x18000c964  jmp     loc_18000CCED
0x18000c969  cmp     r14w, r15w
0x18000c96d  jbe     loc_18000CA31
0x18000c973  movzx   r14d, r15w
0x18000c977  mov     [rsp+0D8h+var_88], r15w
0x18000c97d  jmp     loc_18000CA31
0x18000c982  cmp     r14w, r15w
0x18000c986  jbe     loc_18000CA31
0x18000c98c  cmp     dword ptr [rsi+4], 1
0x18000c990  ja      loc_18000CA31
0x18000c996  mov     [rsp+0D8h+var_4C], 4
0x18000c9a1  mov     ecx, r15d
0x18000c9a4  lea     rax, [rsp+0D8h+var_4C]
0x18000c9ac  mov     [rsp+0D8h+var_A8], rax
0x18000c9b1  lea     rax, [rsp+0D8h+var_50]
0x18000c9b9  mov     [rsp+0D8h+var_B0], rax
0x18000c9be  mov     dword ptr [rsp+0D8h+var_B8], r13d
0x18000c9c3  mov     r9d, 0Bh
0x18000c9c9  mov     r8d, 5
0x18000c9cf  mov     rdx, r12
0x18000c9d2  call    FWGetGlobalConfig
0x18000c9d7  mov     ebx, eax
0x18000c9d9  cmp     eax, 6F7h
0x18000c9de  jz      short loc_18000C9EF
0x18000c9e0  cmp     eax, 57h ; 'W'
0x18000c9e3  jz      short loc_18000C9EF
0x18000c9e5  mov     r15d, [rsp+0D8h+var_50]
0x18000c9ed  jmp     short loc_18000C9FA
0x18000c9ef  mov     ebx, r13d
0x18000c9f2  mov     [rsp+0D8h+var_50], r15d
0x18000c9fa  test    ebx, ebx
0x18000c9fc  jz      short loc_18000CA22
0x18000c9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca05  cmp     rcx, rdi
0x18000ca08  jz      loc_18000CD07
0x18000ca0e  test    byte ptr [rcx+1Ch], 1
0x18000ca12  jz      loc_18000CD07
0x18000ca18  mov     edx, 1Fh
0x18000ca1d  jmp     loc_18000CCED
0x18000ca22  cmp     r14w, r15w
0x18000ca26  cmova   r14w, r15w
0x18000ca2b  mov     [rsp+0D8h+var_88], r14w
0x18000ca31  mov     [rsi+2], r14w
0x18000ca36  mov     eax, [rsi+4]
0x18000ca39  test    eax, eax
0x18000ca3b  jnz     loc_18000CB43
0x18000ca41  mov     [rsp+0D8h+var_60], r13
0x18000ca46  lea     rax, [rsi+28h]
0x18000ca4a  movzx   ecx, r14w
0x18000ca4e  mov     [rsp+0D8h+var_98], rax
0x18000ca53  mov     eax, [rsp+0D8h+arg_20]
0x18000ca5a  mov     [rsp+0D8h+var_A0], eax
0x18000ca5e  mov     eax, [rsp+0D8h+var_80]
0x18000ca62  mov     dword ptr [rsp+0D8h+var_A8], eax
0x18000ca66  mov     eax, [rsp+0D8h+var_78]
0x18000ca6a  mov     dword ptr [rsp+0D8h+var_B0], eax
0x18000ca6e  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x18000ca72  mov     r9, [rsi+20h]
0x18000ca76  xor     r8d, r8d; pReturnValue
0x18000ca79  xor     edx, edx; nProcNum
0x18000ca7b  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000ca82  call    cs:__imp_NdrClientCall3
0x18000ca88  mov     rbx, rax
0x18000ca8b  mov     [rsp+0D8h+var_60], rax
0x18000ca90  mov     [rsp+0D8h+var_7C], eax
  ... truncated ...
```
