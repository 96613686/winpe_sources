# GetFirewallState(_tag_FW_STORE_TYPE,_tag_FW_PROFILE_TYPE,_FW_POLICY_STATE *)

- ea: `0x180006874`
- end: `0x180006e0d`
- name: `?GetFirewallState@@YAJW4_tag_FW_STORE_TYPE@@W4_tag_FW_PROFILE_TYPE@@PEAW4_FW_POLICY_STATE@@@Z`
- size: `1433`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800064cc`

## callees

- `0x180005e0c`
- `0x180006874`
- `0x1800076a0`
- `0x180007a00`
- `0x180009210`
- `0x18000cc80`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180006934`
- `ntdll!EtwEventWrite` at `0x1800069ca`
- `ntdll!EtwEventWrite` at `0x180006a12`
- `ntdll!EtwEventWrite` at `0x180006aa5`
- `ntdll!EtwEventWrite` at `0x180006934`
- `ntdll!EtwEventWrite` at `0x1800069ca`
- `ntdll!EtwEventWrite` at `0x180006a12`
- `ntdll!EtwEventWrite` at `0x180006aa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000695d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000695d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a3b`

## pseudocode

```c
__int64 __fastcall GetFirewallState(int a1, unsigned int a2, int *a3)
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
  v8 = FWOpenPolicyStore(545, 0, a1, 1, 0, (__int64)&v23);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v13 = Int_FWGetOrSetConfig(1, v12, 3, a2, 1, (__int64)&v26, (__int64)&v27, (__int64)&v24);
  if ( !v13 )
    goto LABEL_12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
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
    WPP_SF_(*((_QWORD *)v14 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v17 = Int_FWGetOrSetConfig(1, v16, 1, a2, 1, (__int64)&v25, (__int64)&v27, (__int64)&v24);
  if ( !v17 )
    goto LABEL_23;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
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
0x180006874  mov     [rsp-38h+arg_18], rbx
0x180006879  push    rbp
0x18000687a  push    rsi
0x18000687b  push    rdi
0x18000687c  push    r12
0x18000687e  push    r13
0x180006880  push    r14
0x180006882  push    r15
0x180006884  mov     rbp, rsp
0x180006887  sub     rsp, 70h
0x18000688b  mov     rax, cs:__security_cookie
0x180006892  xor     rax, rsp
0x180006895  mov     [rbp+var_10], rax
0x180006899  mov     r14, r8
0x18000689c  mov     r15d, edx
0x18000689f  mov     edi, ecx
0x1800068a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068a8  lea     rax, WPP_GLOBAL_Control
0x1800068af  cmp     rcx, rax
0x1800068b2  jnz     loc_180006B94
0x1800068b8  xor     r12d, r12d
0x1800068bb  mov     [rbp+var_14], 4
0x1800068c2  mov     ebx, r12d
0x1800068c5  mov     [rbp+var_28], r12
0x1800068c9  mov     [rbp+var_1C], r12d
0x1800068cd  mov     [rbp+var_18], r12d
0x1800068d1  lea     r13d, [r12+1]
0x1800068d6  cmp     edi, r13d
0x1800068d9  jnz     loc_180006C42
0x1800068df  mov     sil, r13b
0x1800068e2  lea     rax, [rbp+var_28]
0x1800068e6  mov     ecx, 221h
0x1800068eb  mov     [rsp+70h+var_48], rax
0x1800068f0  mov     r9d, r13d
0x1800068f3  mov     r8d, edi
0x1800068f6  mov     [rsp+70h+var_50], r12d
0x1800068fb  xor     edx, edx
0x1800068fd  call    FWOpenPolicyStore
0x180006902  cmp     edi, r13d
0x180006905  jz      loc_180006CDB
0x18000690b  test    eax, eax
0x18000690d  jnz     loc_180006B62
0x180006913  mov     rcx, cs:g_Provider
0x18000691a  mov     rdi, [rbp+var_28]
0x18000691e  mov     [rbp+var_20], r12d
0x180006922  test    rcx, rcx
0x180006925  jz      short loc_180006940
0x180006927  xor     r9d, r9d
0x18000692a  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180006931  xor     r8d, r8d
0x180006934  call    cs:__imp_EtwEventWrite
0x18000693b  nop     dword ptr [rax+rax+00h]
0x180006940  mov     rcx, cs:WPP_GLOBAL_Control
0x180006947  lea     rax, WPP_GLOBAL_Control
0x18000694e  cmp     rcx, rax
0x180006951  jz      short loc_18000695D
0x180006953  test    byte ptr [rcx+1Ch], 8
0x180006957  jnz     loc_180006D06
0x18000695d  call    cs:__imp_GetTickCount64
0x180006964  nop     dword ptr [rax+rax+00h]
0x180006969  lea     rax, [rbp+var_20]
0x18000696d  mov     r9d, r15d
0x180006970  mov     [rsp+70h+var_38], rax
0x180006975  mov     r8d, 3
0x18000697b  lea     rax, [rbp+var_14]
0x18000697f  mov     rdx, rdi
0x180006982  mov     [rsp+70h+var_40], rax
0x180006987  mov     ecx, r13d
0x18000698a  lea     rax, [rbp+var_18]
0x18000698e  mov     [rsp+70h+var_48], rax
0x180006993  mov     [rsp+70h+var_50], r13d
0x180006998  call    Int_FWGetOrSetConfig
0x18000699d  mov     edi, eax
0x18000699f  test    eax, eax
0x1800069a1  jnz     loc_180006BB8
0x1800069a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ae  mov     rax, cs:g_Provider
0x1800069b5  test    rax, rax
0x1800069b8  jz      short loc_1800069E4
0x1800069ba  xor     r9d, r9d
0x1800069bd  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800069c4  xor     r8d, r8d
0x1800069c7  mov     rcx, rax
0x1800069ca  call    cs:__imp_EtwEventWrite
0x1800069d1  nop     dword ptr [rax+rax+00h]
0x1800069d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069dd  mov     rax, cs:g_Provider
0x1800069e4  test    sil, sil
0x1800069e7  jnz     loc_180006D20
0x1800069ed  test    edi, edi
0x1800069ef  jnz     loc_180006C7B
0x1800069f5  mov     rdi, [rbp+var_28]
0x1800069f9  mov     [rbp+var_20], r12d
0x1800069fd  test    rax, rax
0x180006a00  jz      short loc_180006A25
0x180006a02  xor     r9d, r9d
0x180006a05  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180006a0c  xor     r8d, r8d
0x180006a0f  mov     rcx, rax
0x180006a12  call    cs:__imp_EtwEventWrite
0x180006a19  nop     dword ptr [rax+rax+00h]
0x180006a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a25  lea     rax, WPP_GLOBAL_Control
0x180006a2c  cmp     rcx, rax
0x180006a2f  jz      short loc_180006A3B
0x180006a31  test    byte ptr [rcx+1Ch], 8
0x180006a35  jnz     loc_180006D32
0x180006a3b  call    cs:__imp_GetTickCount64
0x180006a42  nop     dword ptr [rax+rax+00h]
0x180006a47  lea     rax, [rbp+var_20]
0x180006a4b  mov     r9d, r15d
0x180006a4e  mov     [rsp+70h+var_38], rax
0x180006a53  mov     r8d, r13d
0x180006a56  lea     rax, [rbp+var_14]
0x180006a5a  mov     rdx, rdi
0x180006a5d  mov     [rsp+70h+var_40], rax
0x180006a62  mov     ecx, r13d
0x180006a65  lea     rax, [rbp+var_1C]
0x180006a69  mov     [rsp+70h+var_48], rax
0x180006a6e  mov     [rsp+70h+var_50], r13d
0x180006a73  call    Int_FWGetOrSetConfig
0x180006a78  mov     edi, eax
0x180006a7a  test    eax, eax
0x180006a7c  jnz     loc_180006BF6
0x180006a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a89  mov     rax, cs:g_Provider
0x180006a90  test    rax, rax
0x180006a93  jz      short loc_180006AB8
0x180006a95  xor     r9d, r9d
0x180006a98  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180006a9f  xor     r8d, r8d
0x180006aa2  mov     rcx, rax
0x180006aa5  call    cs:__imp_EtwEventWrite
0x180006aac  nop     dword ptr [rax+rax+00h]
0x180006ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ab8  test    sil, sil
0x180006abb  jnz     loc_180006D4C
0x180006ac1  test    edi, edi
0x180006ac3  jnz     loc_180006CAB
0x180006ac9  mov     eax, [rbp+var_1C]
0x180006acc  test    eax, eax
0x180006ace  jz      loc_180006D60
0x180006ad4  cmp     [rbp+var_18], r12d
0x180006ad8  jnz     short loc_180006B2F
0x180006ada  mov     [rbp+var_20], r12d
0x180006ade  test    sil, sil
0x180006ae1  jnz     short loc_180006B0B
0x180006ae3  mov     rcx, [rbp+var_28]
0x180006ae7  lea     rdx, [rbp+var_30]
0x180006aeb  mov     r8d, r15d
0x180006aee  mov     [rbp+var_30], r12d
0x180006af2  call    ?AreAllInterfacesEnabled@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; AreAllInterfacesEnabled(void *,int *,_tag_FW_PROFILE_TYPE)
0x180006af7  mov     ebx, eax
0x180006af9  test    eax, eax
0x180006afb  js      loc_180006C53
0x180006b01  cmp     [rbp+var_30], r12d
0x180006b05  jz      loc_180006DAA
0x180006b0b  mov     rcx, [rbp+var_28]
0x180006b0f  lea     rdx, [rbp+var_20]
0x180006b13  mov     r8d, r15d
0x180006b16  call    ?VerifyInboundDefaultSecureState@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; VerifyInboundDefaultSecureState(void *,int *,_tag_FW_PROFILE_TYPE)
0x180006b1b  mov     ebx, eax
0x180006b1d  test    eax, eax
0x180006b1f  js      loc_180006DE7
0x180006b25  cmp     [rbp+var_20], r12d
0x180006b29  jz      loc_180006D97
0x180006b2f  mov     [r14], r12d
0x180006b32  mov     rcx, [rbp+var_28]
0x180006b36  test    rcx, rcx
0x180006b39  jnz     short loc_180006B8D
0x180006b3b  mov     eax, ebx
0x180006b3d  mov     rcx, [rbp+var_10]
0x180006b41  xor     rcx, rsp; StackCookie
0x180006b44  call    __security_check_cookie
0x180006b49  mov     rbx, [rsp+70h+arg_18]
0x180006b51  add     rsp, 70h
0x180006b55  pop     r15
0x180006b57  pop     r14
0x180006b59  pop     r13
0x180006b5b  pop     r12
0x180006b5d  pop     rdi
0x180006b5e  pop     rsi
0x180006b5f  pop     rbp
0x180006b60  retn
0x180006b62  jg      loc_180006C34
0x180006b68  mov     ebx, eax
0x180006b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b71  lea     rax, WPP_GLOBAL_Control
0x180006b78  cmp     rcx, rax
0x180006b7b  jz      short loc_180006B32
0x180006b7d  test    [rcx+1Ch], r13b
0x180006b81  jz      short loc_180006B32
0x180006b83  mov     edx, 31h ; '1'
0x180006b88  jmp     loc_180006CEE
0x180006b8d  call    FWClosePolicyStore
0x180006b92  jmp     short loc_180006B3B
0x180006b94  test    byte ptr [rcx+1Ch], 8
0x180006b98  jz      loc_1800068B8
0x180006b9e  mov     rcx, [rcx+10h]
0x180006ba2  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180006ba9  mov     edx, 30h ; '0'
0x180006bae  call    WPP_SF_
0x180006bb3  jmp     loc_1800068B8
0x180006bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bbf  lea     rax, WPP_GLOBAL_Control
0x180006bc6  cmp     rcx, rax
0x180006bc9  jz      loc_1800069AE
0x180006bcf  test    [rcx+1Ch], r13b
0x180006bd3  jz      loc_1800069AE
0x180006bd9  mov     rcx, [rcx+10h]
0x180006bdd  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180006be4  mov     edx, 6Ah ; 'j'
0x180006be9  mov     r9d, edi
0x180006bec  call    WPP_SF_d
0x180006bf1  jmp     loc_1800069A7
0x180006bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bfd  lea     rax, WPP_GLOBAL_Control
0x180006c04  cmp     rcx, rax
0x180006c07  jz      loc_180006A89
0x180006c0d  test    [rcx+1Ch], r13b
0x180006c11  jz      loc_180006A89
0x180006c17  mov     rcx, [rcx+10h]
0x180006c1b  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180006c22  mov     edx, 6Ah ; 'j'
0x180006c27  mov     r9d, edi
0x180006c2a  call    WPP_SF_d
0x180006c2f  jmp     loc_180006A82
0x180006c34  movzx   ebx, ax
0x180006c37  or      ebx, 80070000h
0x180006c3d  jmp     loc_180006B6A
0x180006c42  mov     sil, r12b
0x180006c45  cmp     edi, 0Bh
0x180006c48  jnz     loc_1800068E2
0x180006c4e  jmp     loc_1800068DF
0x180006c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c5a  lea     rax, WPP_GLOBAL_Control
0x180006c61  cmp     rcx, rax
0x180006c64  jz      loc_180006B32
0x180006c6a  test    [rcx+1Ch], r13b
0x180006c6e  jz      loc_180006B32
0x180006c74  mov     edx, 35h ; '5'
0x180006c79  jmp     short loc_180006CEE
0x180006c7b  jg      short loc_180006CA0
0x180006c7d  mov     ebx, edi
0x180006c7f  lea     rax, WPP_GLOBAL_Control
0x180006c86  cmp     rcx, rax
0x180006c89  jz      loc_180006B32
0x180006c8f  test    [rcx+1Ch], r13b
0x180006c93  jz      loc_180006B32
0x180006c99  mov     edx, 32h ; '2'
0x180006c9e  jmp     short loc_180006CEE
0x180006ca0  movzx   ebx, di
0x180006ca3  or      ebx, 80070000h
0x180006ca9  jmp     short loc_180006C7F
0x180006cab  jg      short loc_180006CD0
0x180006cad  mov     ebx, edi
0x180006caf  lea     rax, WPP_GLOBAL_Control
0x180006cb6  cmp     rcx, rax
0x180006cb9  jz      loc_180006B32
0x180006cbf  test    [rcx+1Ch], r13b
0x180006cc3  jz      loc_180006B32
0x180006cc9  mov     edx, 33h ; '3'
0x180006cce  jmp     short loc_180006CEE
0x180006cd0  movzx   ebx, di
0x180006cd3  or      ebx, 80070000h
0x180006cd9  jmp     short loc_180006CAF
0x180006cdb  cmp     eax, 2
0x180006cde  jz      loc_180006B2F
0x180006ce4  jmp     loc_18000690B
0x180006ce9  mov     edx, 37h ; '7'
0x180006cee  mov     rcx, [rcx+10h]
0x180006cf2  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180006cf9  mov     r9d, ebx
0x180006cfc  call    WPP_SF_d
0x180006d01  jmp     loc_180006B32
0x180006d06  mov     rcx, [rcx+10h]
0x180006d0a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180006d11  mov     edx, 69h ; 'i'
0x180006d16  call    WPP_SF_
0x180006d1b  jmp     loc_18000695D
0x180006d20  cmp     edi, 2
0x180006d23  jnz     loc_1800069ED
0x180006d29  mov     [rbp+var_18], r12d
0x180006d2d  jmp     loc_1800069F5
0x180006d32  mov     rcx, [rcx+10h]
0x180006d36  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180006d3d  mov     edx, 69h ; 'i'
0x180006d42  call    WPP_SF_
0x180006d47  jmp     loc_180006A3B
0x180006d4c  cmp     edi, 2
0x180006d4f  jnz     loc_180006AC1
0x180006d55  mov     eax, r13d
0x180006d58  mov     [rbp+var_1C], eax
0x180006d5b  jmp     loc_180006ACC
0x180006d60  lea     rax, WPP_GLOBAL_Control
0x180006d67  cmp     rcx, rax
0x180006d6a  jz      short loc_180006D8A
0x180006d6c  test    byte ptr [rcx+1Ch], 4
0x180006d70  jz      short loc_180006D8A
0x180006d72  mov     rcx, [rcx+10h]
  ... truncated ...
```
