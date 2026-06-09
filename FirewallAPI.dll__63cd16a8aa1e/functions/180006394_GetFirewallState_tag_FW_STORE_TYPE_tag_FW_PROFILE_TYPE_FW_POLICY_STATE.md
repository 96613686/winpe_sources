# GetFirewallState(_tag_FW_STORE_TYPE,_tag_FW_PROFILE_TYPE,_FW_POLICY_STATE *)

- ea: `0x180006394`
- end: `0x180006908`
- name: `?GetFirewallState@@YAJW4_tag_FW_STORE_TYPE@@W4_tag_FW_PROFILE_TYPE@@PEAW4_FW_POLICY_STATE@@@Z`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180005fe8`

## callees

- `0x180005954`
- `0x180006394`
- `0x180007130`
- `0x180007470`
- `0x180008b30`
- `0x18000c130`
- `0x18000c560`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180006454`
- `ntdll!EtwEventWrite` at `0x1800064de`
- `ntdll!EtwEventWrite` at `0x180006520`
- `ntdll!EtwEventWrite` at `0x1800065a7`
- `ntdll!EtwEventWrite` at `0x180006454`
- `ntdll!EtwEventWrite` at `0x1800064de`
- `ntdll!EtwEventWrite` at `0x180006520`
- `ntdll!EtwEventWrite` at `0x1800065a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006477`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006543`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006477`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006543`

## pseudocode

```c
__int64 __fastcall GetFirewallState(unsigned int a1, unsigned int a2, int *a3)
{
  signed int v6; // ebx
  unsigned __int8 v7; // si
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edi
  int v13; // edi
  FwPolicy2 *v14; // rcx
  __int64 v15; // rax
  int v16; // edi
  int v17; // edi
  int v18; // eax
  __int64 v20; // rdx
  int v21; // eax
  int v22; // [rsp+40h] [rbp-30h] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h] BYREF
  int v24; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+54h] [rbp-1Ch] BYREF
  int v26; // [rsp+58h] [rbp-18h] BYREF
  int v27; // [rsp+5Ch] [rbp-14h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids);
  v27 = 4;
  v6 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  if ( a1 == 1 || (v7 = 0, a1 == 11) )
    v7 = 1;
  v8 = FWOpenPolicyStore(0x221u, 0, a1, 1u, 0, &v23);
  if ( a1 == 1 && v8 == 2 )
    goto LABEL_36;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    else
      v6 = v8;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v20 = 49;
    goto LABEL_73;
  }
  v12 = v23;
  v24 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v13 = Int_FWGetOrSetConfig(1, v12, 3, a2, 1, (__int64)&v26, (__int64)&v27, (__int64)&v24);
  if ( !v13 )
    goto LABEL_12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
      (unsigned int)v13);
LABEL_12:
    v14 = WPP_GLOBAL_Control;
  }
  v15 = g_Provider;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v14 = WPP_GLOBAL_Control;
    v15 = g_Provider;
  }
  if ( v7 && v13 == 2 )
  {
    v26 = 0;
  }
  else if ( v13 )
  {
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
    else
      v6 = v13;
    if ( v14 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
      goto LABEL_37;
    v20 = 50;
    goto LABEL_73;
  }
  v16 = v23;
  v24 = 0;
  if ( v15 )
  {
    EtwEventWrite(v15, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v14 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v17 = Int_FWGetOrSetConfig(1, v16, 1, a2, 1, (__int64)&v25, (__int64)&v27, (__int64)&v24);
  if ( !v17 )
    goto LABEL_23;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
      (unsigned int)v17);
LABEL_23:
    v14 = WPP_GLOBAL_Control;
  }
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v7 && v17 == 2 )
  {
    v18 = 1;
    v25 = 1;
  }
  else
  {
    if ( v17 )
    {
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      else
        v6 = v17;
      if ( v14 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
        goto LABEL_37;
      v20 = 51;
      goto LABEL_73;
    }
    v18 = v25;
  }
  if ( !v18 )
  {
    if ( v14 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v14 + 2), 52, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, a2);
    v21 = v7 != 0 ? 5 : 2;
LABEL_83:
    *a3 = v21;
    goto LABEL_37;
  }
  if ( v26 )
  {
LABEL_36:
    *a3 = 0;
    goto LABEL_37;
  }
  v24 = 0;
  if ( v7 )
  {
LABEL_34:
    v6 = VerifyInboundDefaultSecureState(v23, &v24, a2);
    if ( v6 >= 0 )
    {
      if ( v24 )
        goto LABEL_36;
      v21 = 2 * v7 + 4;
      goto LABEL_83;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 55;
      goto LABEL_73;
    }
    goto LABEL_37;
  }
  v22 = 0;
  v6 = AreAllInterfacesEnabled(v23, &v22, a2);
  if ( v6 >= 0 )
  {
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, a2);
      *a3 = 3;
      goto LABEL_37;
    }
    goto LABEL_34;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = 53;
LABEL_73:
    WPP_SF_d(*((_QWORD *)v14 + 2), v20, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, (unsigned int)v6);
  }
LABEL_37:
  if ( v23 )
    FWClosePolicyStore(v23, v9, v10, v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006394  mov     [rsp-38h+arg_18], rbx
0x180006399  push    rbp
0x18000639a  push    rsi
0x18000639b  push    rdi
0x18000639c  push    r12
0x18000639e  push    r13
0x1800063a0  push    r14
0x1800063a2  push    r15
0x1800063a4  mov     rbp, rsp
0x1800063a7  sub     rsp, 70h
0x1800063ab  mov     rax, cs:__security_cookie
0x1800063b2  xor     rax, rsp
0x1800063b5  mov     [rbp+var_10], rax
0x1800063b9  mov     r14, r8
0x1800063bc  mov     r15d, edx
0x1800063bf  mov     edi, ecx
0x1800063c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063c8  lea     rax, WPP_GLOBAL_Control
0x1800063cf  cmp     rcx, rax
0x1800063d2  jnz     loc_18000668F
0x1800063d8  xor     r12d, r12d
0x1800063db  mov     [rbp+var_14], 4
0x1800063e2  mov     ebx, r12d
0x1800063e5  mov     [rbp+var_28], r12
0x1800063e9  mov     [rbp+var_1C], r12d
0x1800063ed  mov     [rbp+var_18], r12d
0x1800063f1  lea     r13d, [r12+1]
0x1800063f6  cmp     edi, r13d
0x1800063f9  jnz     loc_18000673D
0x1800063ff  mov     sil, r13b
0x180006402  lea     rax, [rbp+var_28]
0x180006406  mov     ecx, 221h
0x18000640b  mov     [rsp+70h+var_48], rax
0x180006410  mov     r9d, r13d
0x180006413  mov     r8d, edi
0x180006416  mov     [rsp+70h+var_50], r12d
0x18000641b  xor     edx, edx
0x18000641d  call    FWOpenPolicyStore
0x180006422  cmp     edi, r13d
0x180006425  jz      loc_1800067D6
0x18000642b  test    eax, eax
0x18000642d  jnz     loc_18000665D
0x180006433  mov     rcx, cs:g_Provider
0x18000643a  mov     rdi, [rbp+var_28]
0x18000643e  mov     [rbp+var_20], r12d
0x180006442  test    rcx, rcx
0x180006445  jz      short loc_18000645A
0x180006447  xor     r9d, r9d
0x18000644a  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180006451  xor     r8d, r8d
0x180006454  call    cs:__imp_EtwEventWrite
0x18000645a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006461  lea     rax, WPP_GLOBAL_Control
0x180006468  cmp     rcx, rax
0x18000646b  jz      short loc_180006477
0x18000646d  test    byte ptr [rcx+1Ch], 8
0x180006471  jnz     loc_180006801
0x180006477  call    cs:__imp_GetTickCount64
0x18000647d  lea     rax, [rbp+var_20]
0x180006481  mov     r9d, r15d
0x180006484  mov     [rsp+70h+var_38], rax
0x180006489  mov     r8d, 3
0x18000648f  lea     rax, [rbp+var_14]
0x180006493  mov     rdx, rdi
0x180006496  mov     [rsp+70h+var_40], rax
0x18000649b  mov     ecx, r13d
0x18000649e  lea     rax, [rbp+var_18]
0x1800064a2  mov     [rsp+70h+var_48], rax
0x1800064a7  mov     [rsp+70h+var_50], r13d
0x1800064ac  call    Int_FWGetOrSetConfig
0x1800064b1  mov     edi, eax
0x1800064b3  test    eax, eax
0x1800064b5  jnz     loc_1800066B3
0x1800064bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064c2  mov     rax, cs:g_Provider
0x1800064c9  test    rax, rax
0x1800064cc  jz      short loc_1800064F2
0x1800064ce  xor     r9d, r9d
0x1800064d1  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800064d8  xor     r8d, r8d
0x1800064db  mov     rcx, rax
0x1800064de  call    cs:__imp_EtwEventWrite
0x1800064e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064eb  mov     rax, cs:g_Provider
0x1800064f2  test    sil, sil
0x1800064f5  jnz     loc_18000681B
0x1800064fb  test    edi, edi
0x1800064fd  jnz     loc_180006776
0x180006503  mov     rdi, [rbp+var_28]
0x180006507  mov     [rbp+var_20], r12d
0x18000650b  test    rax, rax
0x18000650e  jz      short loc_18000652D
0x180006510  xor     r9d, r9d
0x180006513  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000651a  xor     r8d, r8d
0x18000651d  mov     rcx, rax
0x180006520  call    cs:__imp_EtwEventWrite
0x180006526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000652d  lea     rax, WPP_GLOBAL_Control
0x180006534  cmp     rcx, rax
0x180006537  jz      short loc_180006543
0x180006539  test    byte ptr [rcx+1Ch], 8
0x18000653d  jnz     loc_18000682D
0x180006543  call    cs:__imp_GetTickCount64
0x180006549  lea     rax, [rbp+var_20]
0x18000654d  mov     r9d, r15d
0x180006550  mov     [rsp+70h+var_38], rax
0x180006555  mov     r8d, r13d
0x180006558  lea     rax, [rbp+var_14]
0x18000655c  mov     rdx, rdi
0x18000655f  mov     [rsp+70h+var_40], rax
0x180006564  mov     ecx, r13d
0x180006567  lea     rax, [rbp+var_1C]
0x18000656b  mov     [rsp+70h+var_48], rax
0x180006570  mov     [rsp+70h+var_50], r13d
0x180006575  call    Int_FWGetOrSetConfig
0x18000657a  mov     edi, eax
0x18000657c  test    eax, eax
0x18000657e  jnz     loc_1800066F1
0x180006584  mov     rcx, cs:WPP_GLOBAL_Control
0x18000658b  mov     rax, cs:g_Provider
0x180006592  test    rax, rax
0x180006595  jz      short loc_1800065B4
0x180006597  xor     r9d, r9d
0x18000659a  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800065a1  xor     r8d, r8d
0x1800065a4  mov     rcx, rax
0x1800065a7  call    cs:__imp_EtwEventWrite
0x1800065ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065b4  test    sil, sil
0x1800065b7  jnz     loc_180006847
0x1800065bd  test    edi, edi
0x1800065bf  jnz     loc_1800067A6
0x1800065c5  mov     eax, [rbp+var_1C]
0x1800065c8  test    eax, eax
0x1800065ca  jz      loc_18000685B
0x1800065d0  cmp     [rbp+var_18], r12d
0x1800065d4  jnz     short loc_18000662B
0x1800065d6  mov     [rbp+var_20], r12d
0x1800065da  test    sil, sil
0x1800065dd  jnz     short loc_180006607
0x1800065df  mov     rcx, [rbp+var_28]
0x1800065e3  lea     rdx, [rbp+var_30]
0x1800065e7  mov     r8d, r15d
0x1800065ea  mov     [rbp+var_30], r12d
0x1800065ee  call    ?AreAllInterfacesEnabled@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; AreAllInterfacesEnabled(void *,int *,_tag_FW_PROFILE_TYPE)
0x1800065f3  mov     ebx, eax
0x1800065f5  test    eax, eax
0x1800065f7  js      loc_18000674E
0x1800065fd  cmp     [rbp+var_30], r12d
0x180006601  jz      loc_1800068A5
0x180006607  mov     rcx, [rbp+var_28]
0x18000660b  lea     rdx, [rbp+var_20]
0x18000660f  mov     r8d, r15d
0x180006612  call    ?VerifyInboundDefaultSecureState@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; VerifyInboundDefaultSecureState(void *,int *,_tag_FW_PROFILE_TYPE)
0x180006617  mov     ebx, eax
0x180006619  test    eax, eax
0x18000661b  js      loc_1800068E2
0x180006621  cmp     [rbp+var_20], r12d
0x180006625  jz      loc_180006892
0x18000662b  mov     [r14], r12d
0x18000662e  mov     rcx, [rbp+var_28]
0x180006632  test    rcx, rcx
0x180006635  jnz     short loc_180006688
0x180006637  mov     eax, ebx
0x180006639  mov     rcx, [rbp+var_10]
0x18000663d  xor     rcx, rsp; StackCookie
0x180006640  call    __security_check_cookie
0x180006645  mov     rbx, [rsp+70h+arg_18]
0x18000664d  add     rsp, 70h
0x180006651  pop     r15
0x180006653  pop     r14
0x180006655  pop     r13
0x180006657  pop     r12
0x180006659  pop     rdi
0x18000665a  pop     rsi
0x18000665b  pop     rbp
0x18000665c  retn
0x18000665d  jg      loc_18000672F
0x180006663  mov     ebx, eax
0x180006665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000666c  lea     rax, WPP_GLOBAL_Control
0x180006673  cmp     rcx, rax
0x180006676  jz      short loc_18000662E
0x180006678  test    [rcx+1Ch], r13b
0x18000667c  jz      short loc_18000662E
0x18000667e  mov     edx, 31h ; '1'
0x180006683  jmp     loc_1800067E9
0x180006688  call    FWClosePolicyStore
0x18000668d  jmp     short loc_180006637
0x18000668f  test    byte ptr [rcx+1Ch], 8
0x180006693  jz      loc_1800063D8
0x180006699  mov     rcx, [rcx+10h]
0x18000669d  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x1800066a4  mov     edx, 30h ; '0'
0x1800066a9  call    WPP_SF_
0x1800066ae  jmp     loc_1800063D8
0x1800066b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066ba  lea     rax, WPP_GLOBAL_Control
0x1800066c1  cmp     rcx, rax
0x1800066c4  jz      loc_1800064C2
0x1800066ca  test    [rcx+1Ch], r13b
0x1800066ce  jz      loc_1800064C2
0x1800066d4  mov     rcx, [rcx+10h]
0x1800066d8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800066df  mov     edx, 6Bh ; 'k'
0x1800066e4  mov     r9d, edi
0x1800066e7  call    WPP_SF_d
0x1800066ec  jmp     loc_1800064BB
0x1800066f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066f8  lea     rax, WPP_GLOBAL_Control
0x1800066ff  cmp     rcx, rax
0x180006702  jz      loc_18000658B
0x180006708  test    [rcx+1Ch], r13b
0x18000670c  jz      loc_18000658B
0x180006712  mov     rcx, [rcx+10h]
0x180006716  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000671d  mov     edx, 6Bh ; 'k'
0x180006722  mov     r9d, edi
0x180006725  call    WPP_SF_d
0x18000672a  jmp     loc_180006584
0x18000672f  movzx   ebx, ax
0x180006732  or      ebx, 80070000h
0x180006738  jmp     loc_180006665
0x18000673d  mov     sil, r12b
0x180006740  cmp     edi, 0Bh
0x180006743  jnz     loc_180006402
0x180006749  jmp     loc_1800063FF
0x18000674e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006755  lea     rax, WPP_GLOBAL_Control
0x18000675c  cmp     rcx, rax
0x18000675f  jz      loc_18000662E
0x180006765  test    [rcx+1Ch], r13b
0x180006769  jz      loc_18000662E
0x18000676f  mov     edx, 35h ; '5'
0x180006774  jmp     short loc_1800067E9
0x180006776  jg      short loc_18000679B
0x180006778  mov     ebx, edi
0x18000677a  lea     rax, WPP_GLOBAL_Control
0x180006781  cmp     rcx, rax
0x180006784  jz      loc_18000662E
0x18000678a  test    [rcx+1Ch], r13b
0x18000678e  jz      loc_18000662E
0x180006794  mov     edx, 32h ; '2'
0x180006799  jmp     short loc_1800067E9
0x18000679b  movzx   ebx, di
0x18000679e  or      ebx, 80070000h
0x1800067a4  jmp     short loc_18000677A
0x1800067a6  jg      short loc_1800067CB
0x1800067a8  mov     ebx, edi
0x1800067aa  lea     rax, WPP_GLOBAL_Control
0x1800067b1  cmp     rcx, rax
0x1800067b4  jz      loc_18000662E
0x1800067ba  test    [rcx+1Ch], r13b
0x1800067be  jz      loc_18000662E
0x1800067c4  mov     edx, 33h ; '3'
0x1800067c9  jmp     short loc_1800067E9
0x1800067cb  movzx   ebx, di
0x1800067ce  or      ebx, 80070000h
0x1800067d4  jmp     short loc_1800067AA
0x1800067d6  cmp     eax, 2
0x1800067d9  jz      loc_18000662B
0x1800067df  jmp     loc_18000642B
0x1800067e4  mov     edx, 37h ; '7'
0x1800067e9  mov     rcx, [rcx+10h]
0x1800067ed  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x1800067f4  mov     r9d, ebx
0x1800067f7  call    WPP_SF_d
0x1800067fc  jmp     loc_18000662E
0x180006801  mov     rcx, [rcx+10h]
0x180006805  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000680c  mov     edx, 6Ah ; 'j'
0x180006811  call    WPP_SF_
0x180006816  jmp     loc_180006477
0x18000681b  cmp     edi, 2
0x18000681e  jnz     loc_1800064FB
0x180006824  mov     [rbp+var_18], r12d
0x180006828  jmp     loc_180006503
0x18000682d  mov     rcx, [rcx+10h]
0x180006831  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180006838  mov     edx, 6Ah ; 'j'
0x18000683d  call    WPP_SF_
0x180006842  jmp     loc_180006543
0x180006847  cmp     edi, 2
0x18000684a  jnz     loc_1800065BD
0x180006850  mov     eax, r13d
0x180006853  mov     [rbp+var_1C], eax
0x180006856  jmp     loc_1800065C8
0x18000685b  lea     rax, WPP_GLOBAL_Control
0x180006862  cmp     rcx, rax
0x180006865  jz      short loc_180006885
0x180006867  test    byte ptr [rcx+1Ch], 4
0x18000686b  jz      short loc_180006885
0x18000686d  mov     rcx, [rcx+10h]
0x180006871  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180006878  mov     edx, 34h ; '4'
0x18000687d  mov     r9d, r15d
0x180006880  call    WPP_SF_d
0x180006885  neg     sil
0x180006888  sbb     eax, eax
  ... truncated ...
```
