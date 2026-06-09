# I_s_OpenVault

- ea: `0x18006c09c`
- end: `0x18006c316`
- name: `I_s_OpenVault`
- size: `634`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006a378`
- `0x18006a7c4`
- `0x18006b150`

## callees

- `0x180010a94`
- `0x180028d18`
- `0x180034cf8`
- `0x180046d90`
- `0x18005cee0`
- `0x18005f788`
- `0x18006c09c`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x18006c165`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x18006c165`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x18006c2d0`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x18006c2d0`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18006c176`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18006c176`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18006c10b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18006c10b`

## string_xrefs

- `0x18006c1e4`: `onecore\ds\security\ngc\kspsvc\svc\localaccount.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_s_OpenVault(_QWORD *a1)
{
  unsigned int ItemType; // ebx
  __int64 v4; // rdx
  char *v5; // rdx
  unsigned int v6; // [rsp+20h] [rbp-E0h]
  unsigned int v7; // [rsp+30h] [rbp-D0h] BYREF
  void **v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v10[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+60h] [rbp-A0h]
  __int128 v12; // [rsp+70h] [rbp-90h]
  __int128 v13; // [rsp+80h] [rbp-80h]
  _OWORD v14[4]; // [rsp+90h] [rbp-70h] BYREF
  int v15; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v16; // [rsp+D4h] [rbp-2Ch]
  int v17; // [rsp+DCh] [rbp-24h]
  int v18; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v19; // [rsp+E4h] [rbp-1Ch]
  int v20; // [rsp+ECh] [rbp-14h]
  int v21; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v22; // [rsp+F4h] [rbp-Ch]
  int v23; // [rsp+FCh] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  *a1 = 0;
  if ( !(unsigned __int8)IsVaultOpenVaultPresent() )
    return 2147942450LL;
  v8 = &Microsoft::WRL::Wrappers::HandleT<VaultHandleTraits>::`vftable';
  v9 = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v8);
  ItemType = VaultOpenVault(Vault_DefaultVault_ID, 0x10000000, &v9);
  if ( ItemType )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v4 = 68;
LABEL_15:
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\localaccount.cpp",
        (const char *)ItemType,
        v6);
      goto LABEL_19;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_19;
    v5 = byte_1800FE91B;
    goto LABEL_18;
  }
  v10[0] = 0;
  ItemType = VaultGetItemType(v9, &c_guidNgcLocalAccountVaultSchema, 0, v10);
  if ( ItemType )
  {
    if ( ItemType == 1168 )
    {
      v15 = 1;
      v16 = 7;
      v17 = 0;
      v18 = 2;
      v19 = 8;
      v20 = 0;
      v21 = 3;
      v22 = 8;
      v23 = 0;
      v13 = 0u;
      *(_QWORD *)&v11 = L"NGC Local Accoount Logon Vault Resource Schema";
      *((_QWORD *)&v11 + 1) = &v15;
      *(_QWORD *)&v12 = &v18;
      *((_QWORD *)&v12 + 1) = &v21;
      v14[0] = c_guidNgcLocalAccountVaultSchema;
      v14[1] = v11;
      v14[2] = v12;
      v14[3] = 0u;
      ItemType = VaultCreateItemType(v9, v14, 0);
      if ( !ItemType )
        goto LABEL_10;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v4 = 137;
        goto LABEL_15;
      }
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v5 = (char *)&unk_1800FE8C8;
        goto LABEL_18;
      }
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v4 = 101;
        goto LABEL_15;
      }
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v5 = byte_1800FE8F3;
LABEL_18:
        v7 = ItemType;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)v5,
          0,
          0,
          (__int64)&v7);
      }
    }
LABEL_19:
    if ( (int)ItemType > 0 )
      ItemType = (unsigned __int16)ItemType | 0x80070000;
    goto LABEL_11;
  }
  VaultFree(v10[0]);
LABEL_10:
  ItemType = 0;
  *a1 = v9;
  v9 = 0;
LABEL_11:
  v8 = &Microsoft::WRL::Wrappers::HandleT<VaultHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v8);
  return ItemType;
}

```

## disassembly

```asm
0x18006c09c  mov     [rsp-8+arg_8], rbx
0x18006c0a1  mov     [rsp-8+arg_10], rsi
0x18006c0a6  push    rbp
0x18006c0a7  push    rdi
0x18006c0a8  push    r14
0x18006c0aa  lea     rbp, [rsp-10h]
0x18006c0af  sub     rsp, 110h
0x18006c0b6  mov     rax, cs:__security_cookie
0x18006c0bd  xor     rax, rsp
0x18006c0c0  mov     [rbp+20h+var_20], rax
0x18006c0c4  mov     rdi, rcx
0x18006c0c7  xor     esi, esi
0x18006c0c9  mov     [rcx], rsi
0x18006c0cc  call    IsVaultOpenVaultPresent
0x18006c0d1  test    al, al
0x18006c0d3  jnz     short loc_18006C0DF
0x18006c0d5  mov     eax, 80070032h
0x18006c0da  jmp     loc_18006C19C
0x18006c0df  lea     r14, ??_7?$HandleT@UVaultHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<VaultHandleTraits>::`vftable'
0x18006c0e6  mov     [rsp+120h+var_E8], r14
0x18006c0eb  mov     [rsp+120h+var_E0], rsi
0x18006c0f0  lea     rcx, [rsp+120h+var_E8]
0x18006c0f5  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18006c0fa  lea     r8, [rsp+120h+var_E0]
0x18006c0ff  mov     edx, 10000000h
0x18006c104  lea     rcx, Vault_DefaultVault_ID
0x18006c10b  call    cs:__imp_VaultOpenVault
0x18006c111  mov     ebx, eax
0x18006c113  test    eax, eax
0x18006c115  jz      short loc_18006C14C
0x18006c117  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006c11e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006c123  test    al, al
0x18006c125  jz      short loc_18006C131
0x18006c127  mov     edx, 44h ; 'D'
0x18006c12c  jmp     loc_18006C1DD
0x18006c131  mov     eax, cs:dword_180122070
0x18006c137  cmp     eax, 2
0x18006c13a  jbe     loc_18006C224
0x18006c140  lea     rdx, byte_1800FE91B
0x18006c147  jmp     loc_18006C204
0x18006c14c  mov     [rsp+120h+var_D8], rsi
0x18006c151  lea     r9, [rsp+120h+var_D8]
0x18006c156  xor     r8d, r8d
0x18006c159  lea     rdx, c_guidNgcLocalAccountVaultSchema
0x18006c160  mov     rcx, [rsp+120h+var_E0]
0x18006c165  call    cs:__imp_VaultGetItemType
0x18006c16b  mov     ebx, eax
0x18006c16d  test    eax, eax
0x18006c16f  jnz     short loc_18006C1C0
0x18006c171  mov     rcx, [rsp+120h+var_D8]
0x18006c176  call    cs:__imp_VaultFree
0x18006c17c  mov     rax, [rsp+120h+var_E0]
0x18006c181  mov     ebx, esi
0x18006c183  mov     [rdi], rax
0x18006c186  mov     [rsp+120h+var_E0], rsi
0x18006c18b  mov     [rsp+120h+var_E8], r14
0x18006c190  lea     rcx, [rsp+120h+var_E8]
0x18006c195  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18006c19a  mov     eax, ebx
0x18006c19c  mov     rcx, [rbp+20h+var_20]
0x18006c1a0  xor     rcx, rsp; StackCookie
0x18006c1a3  call    __security_check_cookie
0x18006c1a8  lea     r11, [rsp+120h+var_10]
0x18006c1b0  mov     rbx, [r11+28h]
0x18006c1b4  mov     rsi, [r11+30h]
0x18006c1b8  mov     rsp, r11
0x18006c1bb  pop     r14
0x18006c1bd  pop     rdi
0x18006c1be  pop     rbp
0x18006c1bf  retn
0x18006c1c0  cmp     ebx, 490h
0x18006c1c6  jz      short loc_18006C23A
0x18006c1c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006c1cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006c1d4  test    al, al
0x18006c1d6  jz      short loc_18006C1F2
0x18006c1d8  mov     edx, 65h ; 'e'; void *
0x18006c1dd  mov     rcx, [rbp+28h]; this
0x18006c1e1  mov     r9d, ebx; char *
0x18006c1e4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006c1eb  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006c1f0  jmp     short loc_18006C224
0x18006c1f2  mov     eax, cs:dword_180122070
0x18006c1f8  cmp     eax, 2
0x18006c1fb  jbe     short loc_18006C224
0x18006c1fd  lea     rdx, byte_1800FE8F3
0x18006c204  lea     rax, [rsp+120h+var_F0]
0x18006c209  xor     r9d, r9d
0x18006c20c  mov     qword ptr [rsp+120h+var_100], rax
0x18006c211  xor     r8d, r8d
0x18006c214  mov     [rsp+120h+var_F0], ebx
0x18006c218  lea     rcx, dword_180122070
0x18006c21f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006c224  test    ebx, ebx
0x18006c226  jle     loc_18006C18B
0x18006c22c  movzx   ebx, bx
0x18006c22f  or      ebx, 80070000h
0x18006c235  jmp     loc_18006C18B
0x18006c23a  mov     [rbp+20h+var_50], 1
0x18006c241  mov     [rbp+20h+var_4C], 7
0x18006c249  mov     [rbp+20h+var_44], esi
0x18006c24c  mov     [rbp+20h+var_40], 2
0x18006c253  mov     [rbp+20h+var_3C], 8
0x18006c25b  mov     [rbp+20h+var_34], esi
0x18006c25e  mov     [rbp+20h+var_30], 3
0x18006c265  mov     [rbp+20h+var_2C], 8
0x18006c26d  mov     [rbp+20h+var_24], esi
0x18006c270  mov     qword ptr [rbp+20h+var_A0], rsi
0x18006c274  movups  xmm0, cs:c_guidNgcLocalAccountVaultSchema
0x18006c27b  lea     rax, aNgcLocalAccoou_1; "NGC Local Accoount Logon Vault Resource"...
0x18006c282  mov     qword ptr [rsp+120h+var_C0], rax
0x18006c287  lea     rax, [rbp+20h+var_50]
0x18006c28b  mov     qword ptr [rsp+120h+var_C0+8], rax
0x18006c290  lea     rax, [rbp+20h+var_40]
0x18006c294  mov     qword ptr [rsp+120h+var_B0], rax
0x18006c299  lea     rax, [rbp+20h+var_30]
0x18006c29d  mov     qword ptr [rsp+120h+var_B0+8], rax
0x18006c2a2  mov     qword ptr [rbp+20h+var_A0+8], rsi
0x18006c2a6  movaps  [rbp+20h+var_90], xmm0
0x18006c2aa  movaps  xmm0, [rsp+120h+var_C0]
0x18006c2af  movaps  [rbp+20h+var_80], xmm0
0x18006c2b3  movaps  xmm1, [rsp+120h+var_B0]
0x18006c2b8  movaps  [rbp+20h+var_70], xmm1
0x18006c2bc  movaps  xmm0, [rbp+20h+var_A0]
0x18006c2c0  movaps  [rbp+20h+var_60], xmm0
0x18006c2c4  xor     r8d, r8d
0x18006c2c7  lea     rdx, [rbp+20h+var_90]
0x18006c2cb  mov     rcx, [rsp+120h+var_E0]
0x18006c2d0  call    cs:__imp_VaultCreateItemType
0x18006c2d6  mov     ebx, eax
0x18006c2d8  test    eax, eax
0x18006c2da  jz      loc_18006C17C
0x18006c2e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006c2e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006c2ec  test    al, al
0x18006c2ee  jz      short loc_18006C2FA
0x18006c2f0  mov     edx, 89h
0x18006c2f5  jmp     loc_18006C1DD
0x18006c2fa  mov     eax, cs:dword_180122070
0x18006c300  cmp     eax, 2
0x18006c303  jbe     loc_18006C224
0x18006c309  lea     rdx, unk_1800FE8C8
0x18006c310  jmp     loc_18006C204
```
