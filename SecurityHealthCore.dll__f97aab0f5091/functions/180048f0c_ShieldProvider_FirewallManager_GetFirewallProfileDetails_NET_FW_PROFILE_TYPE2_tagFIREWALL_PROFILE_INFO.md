# ShieldProvider::FirewallManager::GetFirewallProfileDetails(NET_FW_PROFILE_TYPE2_,tagFIREWALL_PROFILE_INFO * *)

- ea: `0x180048f0c`
- end: `0x1800492a0`
- name: `?GetFirewallProfileDetails@FirewallManager@ShieldProvider@@QEAAJW4NET_FW_PROFILE_TYPE2_@@PEAPEAUtagFIREWALL_PROFILE_INFO@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(ShieldProvider::FirewallManager *__hidden this, enum NET_FW_PROFILE_TYPE2_, struct tagFIREWALL_PROFILE_INFO **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045ce0`

## callees

- `0x18000a7ec`
- `0x18000d7fc`
- `0x180048f0c`
- `0x1800492a8`
- `0x18004970c`
- `0x18004af04`
- `0x18004b014`
- `0x18004b200`
- `0x1800ceb24`
- `0x1800d53bc`
- `0x1800e17e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180048fec`
- `ole32!CoTaskMemFree` at `0x18004925a`
- `ole32!CoTaskMemFree` at `0x180048fec`
- `ole32!CoTaskMemFree` at `0x18004925a`

## string_xrefs

- `0x180048f4b`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\networkprotectionshield\firewallmanager.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::FirewallManager::GetFirewallProfileDetails(
        ShieldProvider::FirewallManager *this,
        enum NET_FW_PROFILE_TYPE2_ a2,
        struct tagFIREWALL_PROFILE_INFO **a3)
{
  int IsProviderReady; // eax
  unsigned __int64 v7; // r8
  bool v8; // r9
  int IsFirewallEnabled; // ebx
  enum NLM_NETWORK_CATEGORY v11; // edi
  ShieldProvider::FirewallManager *v12; // rcx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  struct tagFIREWALL_PROFILE_INFO *v16; // rbx
  int NetworkDetails; // eax
  __int64 v18; // rcx
  unsigned int v19; // esi
  PVOID *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rcx
  ShieldProvider *v24; // rcx
  __int64 v25; // rcx
  int IsGroupPolicyEnforced; // eax
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-30h]
  int v29; // [rsp+30h] [rbp-20h] BYREF
  int v30; // [rsp+34h] [rbp-1Ch] BYREF
  int v31; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v34; // [rsp+98h] [rbp+48h] BYREF

  v29 = 0;
  v34 = 0;
  IsProviderReady = ShieldProvider::FirewallManager::IsProviderReady(this);
  IsFirewallEnabled = IsProviderReady;
  if ( IsProviderReady < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\networkprotectionshield"
                    "\\firewallmanager.cpp",
      (const char *)(unsigned int)IsProviderReady,
      v28);
    return (unsigned int)IsFirewallEnabled;
  }
  *a3 = 0;
  v11 = NLM_NETWORK_CATEGORY_DOMAIN_AUTHENTICATED;
  switch ( a2 )
  {
    case NET_FW_PROFILE2_DOMAIN:
LABEL_9:
      LOBYTE(v7) = 1;
      pv[0] = 0;
      IsFirewallEnabled = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)pv, (void **)0x38, v7, v8);
      if ( IsFirewallEnabled < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_14;
        v14 = 43;
LABEL_13:
        WPP_SF_d(v13[2], v14, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, (unsigned int)IsFirewallEnabled);
LABEL_14:
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        return (unsigned int)IsFirewallEnabled;
      }
      v30 = 0;
      v31 = 0;
      IsFirewallEnabled = ShieldProvider::FirewallManager::IsFirewallEnabled(v12, a2, &v30, &v31);
      if ( IsFirewallEnabled < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_14;
        v14 = 44;
        goto LABEL_13;
      }
      v16 = (struct tagFIREWALL_PROFILE_INFO *)pv[0];
      *(_DWORD *)pv[0] = v30;
      *((_DWORD *)v16 + 6) = v31;
      v34 = 0;
      v29 = 4;
      NetworkDetails = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, int *))ShieldProvider::FirewallManager::GetFwConfig)(
                         v15,
                         5,
                         10,
                         (unsigned int)a2,
                         &v34,
                         &v29);
      v19 = NetworkDetails;
      if ( NetworkDetails < 0 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v21 = 45;
        goto LABEL_24;
      }
      *((_DWORD *)v16 + 1) = v34 == 1;
      v34 = 0;
      v29 = 4;
      NetworkDetails = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, int *))ShieldProvider::FirewallManager::GetFwConfig)(
                         v18,
                         5,
                         3,
                         (unsigned int)a2,
                         &v34,
                         &v29);
      v19 = NetworkDetails;
      if ( NetworkDetails < 0 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v21 = 46;
        goto LABEL_24;
      }
      *((_DWORD *)v16 + 3) = v34 == 1;
      v34 = 0;
      v29 = 4;
      NetworkDetails = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, int *))ShieldProvider::FirewallManager::GetFwConfig)(
                         v23,
                         5,
                         17,
                         (unsigned int)a2,
                         &v34,
                         &v29);
      v19 = NetworkDetails;
      if ( NetworkDetails < 0 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v21 = 47;
        goto LABEL_24;
      }
      *((_DWORD *)v16 + 2) = v34 == 0;
      NetworkDetails = ShieldProvider::FirewallManager::GetNetworkDetails(this, v11, v16);
      v19 = NetworkDetails;
      if ( NetworkDetails < 0 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v21 = 48;
LABEL_24:
        v22 = (unsigned int)NetworkDetails;
LABEL_48:
        WPP_SF_d(v20[2], v21, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, v22);
        goto LABEL_49;
      }
      if ( ShieldProvider::IsOSWcos(v24) )
      {
        *((_DWORD *)v16 + 7) = 0;
      }
      else
      {
        if ( v16 == (struct tagFIREWALL_PROFILE_INFO *)-20LL )
        {
          v19 = -2147024809;
          goto LABEL_44;
        }
        IsGroupPolicyEnforced = FwIsGroupPolicyEnforced(v25, (unsigned int)a2);
        v19 = IsGroupPolicyEnforced;
        if ( IsGroupPolicyEnforced < 0 )
        {
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_49:
            CoTaskMemFree(v16);
            return v19;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_45;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
            (unsigned int)IsGroupPolicyEnforced);
LABEL_44:
          v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
          if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 )
            goto LABEL_49;
          v21 = 49;
          v22 = v19;
          goto LABEL_48;
        }
        *((_DWORD *)v16 + 7) = ShieldProvider::FirewallManager::IsSettingControlledByPolicy(v27, 10, (unsigned int)a2);
      }
      *a3 = v16;
      return v19;
    case NET_FW_PROFILE2_PRIVATE:
      v11 = NLM_NETWORK_CATEGORY_PRIVATE;
      goto LABEL_9;
    case NET_FW_PROFILE2_PUBLIC:
      v11 = NLM_NETWORK_CATEGORY_PUBLIC;
      goto LABEL_9;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180048f0c  mov     [rsp-28h+arg_0], rbx
0x180048f11  mov     [rsp-28h+arg_8], rsi
0x180048f16  push    rbp
0x180048f17  push    rdi
0x180048f18  push    r12
0x180048f1a  push    r14
0x180048f1c  push    r15
0x180048f1e  mov     rbp, rsp
0x180048f21  sub     rsp, 50h
0x180048f25  mov     r15, r8
0x180048f28  mov     [rbp+var_20], 0
0x180048f2f  mov     r14d, edx
0x180048f32  mov     [rbp+arg_18], 0
0x180048f39  mov     r12, rcx
0x180048f3c  call    ?IsProviderReady@FirewallManager@ShieldProvider@@AEAAJXZ; ShieldProvider::FirewallManager::IsProviderReady(void)
0x180048f41  mov     ebx, eax
0x180048f43  test    eax, eax
0x180048f45  jns     short loc_180048F66
0x180048f47  mov     rcx, [rbp+28h]; this
0x180048f4b  lea     r8, aOnecoreAmcoreA_12; "onecore\\amcore\\antimalware\\source\\s"...
0x180048f52  mov     r9d, eax; char *
0x180048f55  mov     edx, 376h; void *
0x180048f5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f5f  mov     eax, ebx
0x180048f61  jmp     loc_180049287
0x180048f66  mov     esi, 1
0x180048f6b  mov     qword ptr [r15], 0
0x180048f72  lea     edi, [rsi+1]
0x180048f75  cmp     r14d, esi
0x180048f78  jz      short loc_180048F8F
0x180048f7a  cmp     r14d, edi
0x180048f7d  jnz     short loc_180048F83
0x180048f7f  mov     edi, esi
0x180048f81  jmp     short loc_180048F8F
0x180048f83  cmp     r14d, 4
0x180048f87  jnz     loc_180049282
0x180048f8d  xor     edi, edi
0x180048f8f  mov     r8b, sil; unsigned __int64
0x180048f92  mov     [rbp+pv], 0
0x180048f9a  mov     edx, 38h ; '8'; void **
0x180048f9f  lea     rcx, [rbp+pv]; this
0x180048fa3  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x180048fa8  mov     ebx, eax
0x180048faa  test    eax, eax
0x180048fac  jns     short loc_180048FF7
0x180048fae  mov     rcx, cs:WPP_GLOBAL_Control
0x180048fb5  lea     rdi, WPP_GLOBAL_Control
0x180048fbc  cmp     rcx, rdi
0x180048fbf  jz      short loc_180048FDF
0x180048fc1  test    [rcx+1Ch], sil
0x180048fc5  jz      short loc_180048FDF
0x180048fc7  mov     edx, 2Bh ; '+'
0x180048fcc  mov     rcx, [rcx+10h]
0x180048fd0  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180048fd7  mov     r9d, ebx
0x180048fda  call    WPP_SF_d
0x180048fdf  mov     rcx, [rbp+pv]; pv
0x180048fe3  test    rcx, rcx
0x180048fe6  jz      loc_180048F5F
0x180048fec  call    cs:__imp_CoTaskMemFree
0x180048ff2  jmp     loc_180048F5F
0x180048ff7  lea     r9, [rbp+var_18]; int *
0x180048ffb  mov     [rbp+var_1C], 0
0x180049002  lea     r8, [rbp+var_1C]; int *
0x180049006  mov     [rbp+var_18], 0
0x18004900d  mov     edx, r14d; enum NET_FW_PROFILE_TYPE2_
0x180049010  call    ?IsFirewallEnabled@FirewallManager@ShieldProvider@@AEAAJW4NET_FW_PROFILE_TYPE2_@@PEAH1@Z; ShieldProvider::FirewallManager::IsFirewallEnabled(NET_FW_PROFILE_TYPE2_,int *,int *)
0x180049015  mov     ebx, eax
0x180049017  test    eax, eax
0x180049019  jns     short loc_18004903B
0x18004901b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049022  lea     rdi, WPP_GLOBAL_Control
0x180049029  cmp     rcx, rdi
0x18004902c  jz      short loc_180048FDF
0x18004902e  test    [rcx+1Ch], sil
0x180049032  jz      short loc_180048FDF
0x180049034  mov     edx, 2Ch ; ','
0x180049039  jmp     short loc_180048FCC
0x18004903b  mov     eax, [rbp+var_1C]
0x18004903e  mov     edx, 5
0x180049043  mov     rbx, [rbp+pv]
0x180049047  mov     r9d, r14d
0x18004904a  lea     r8d, [rdx+5]
0x18004904e  mov     [rbx], eax
0x180049050  mov     eax, [rbp+var_18]
0x180049053  mov     [rbx+18h], eax
0x180049056  lea     rax, [rbp+var_20]
0x18004905a  mov     [rsp+50h+var_28], rax
0x18004905f  lea     rax, [rbp+arg_18]
0x180049063  mov     [rsp+50h+var_30], rax
0x180049068  mov     [rbp+arg_18], 0
0x18004906f  mov     [rbp+var_20], 4
0x180049076  call    ?GetFwConfig@FirewallManager@ShieldProvider@@AEAAJW4_tag_FW_STORE_TYPE@@W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@PEAXPEAK@Z; ShieldProvider::FirewallManager::GetFwConfig(_tag_FW_STORE_TYPE,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,void *,ulong *)
0x18004907b  mov     esi, eax
0x18004907d  test    eax, eax
0x18004907f  jns     short loc_1800490AF
0x180049081  mov     rcx, cs:WPP_GLOBAL_Control
0x180049088  lea     rdi, WPP_GLOBAL_Control
0x18004908f  cmp     rcx, rdi
0x180049092  jz      loc_180049257
0x180049098  test    byte ptr [rcx+1Ch], 1
0x18004909c  jz      loc_180049257
0x1800490a2  mov     edx, 2Dh ; '-'
0x1800490a7  mov     r9d, eax
0x1800490aa  jmp     loc_180049247
0x1800490af  xor     eax, eax
0x1800490b1  mov     edx, 5
0x1800490b6  cmp     [rbp+arg_18], 1
0x1800490ba  mov     r9d, r14d
0x1800490bd  setz    al
0x1800490c0  mov     [rbx+4], eax
0x1800490c3  lea     r8d, [rdx-2]
0x1800490c7  lea     rax, [rbp+var_20]
0x1800490cb  mov     [rbp+arg_18], 0
0x1800490d2  mov     [rsp+50h+var_28], rax
0x1800490d7  lea     rax, [rbp+arg_18]
0x1800490db  mov     [rsp+50h+var_30], rax
0x1800490e0  mov     [rbp+var_20], 4
0x1800490e7  call    ?GetFwConfig@FirewallManager@ShieldProvider@@AEAAJW4_tag_FW_STORE_TYPE@@W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@PEAXPEAK@Z; ShieldProvider::FirewallManager::GetFwConfig(_tag_FW_STORE_TYPE,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,void *,ulong *)
0x1800490ec  mov     esi, eax
0x1800490ee  test    eax, eax
0x1800490f0  jns     short loc_18004911A
0x1800490f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800490f9  lea     rdi, WPP_GLOBAL_Control
0x180049100  cmp     rcx, rdi
0x180049103  jz      loc_180049257
0x180049109  test    byte ptr [rcx+1Ch], 1
0x18004910d  jz      loc_180049257
0x180049113  mov     edx, 2Eh ; '.'
0x180049118  jmp     short loc_1800490A7
0x18004911a  xor     eax, eax
0x18004911c  mov     edx, 5
0x180049121  cmp     [rbp+arg_18], 1
0x180049125  mov     r9d, r14d
0x180049128  setz    al
0x18004912b  mov     [rbx+0Ch], eax
0x18004912e  lea     r8d, [rdx+0Ch]
0x180049132  lea     rax, [rbp+var_20]
0x180049136  mov     [rbp+arg_18], 0
0x18004913d  mov     [rsp+50h+var_28], rax
0x180049142  lea     rax, [rbp+arg_18]
0x180049146  mov     [rsp+50h+var_30], rax
0x18004914b  mov     [rbp+var_20], 4
0x180049152  call    ?GetFwConfig@FirewallManager@ShieldProvider@@AEAAJW4_tag_FW_STORE_TYPE@@W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@PEAXPEAK@Z; ShieldProvider::FirewallManager::GetFwConfig(_tag_FW_STORE_TYPE,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,void *,ulong *)
0x180049157  mov     esi, eax
0x180049159  test    eax, eax
0x18004915b  jns     short loc_180049188
0x18004915d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049164  lea     rdi, WPP_GLOBAL_Control
0x18004916b  cmp     rcx, rdi
0x18004916e  jz      loc_180049257
0x180049174  test    byte ptr [rcx+1Ch], 1
0x180049178  jz      loc_180049257
0x18004917e  mov     edx, 2Fh ; '/'
0x180049183  jmp     loc_1800490A7
0x180049188  xor     eax, eax
0x18004918a  mov     r8, rbx; struct tagFIREWALL_PROFILE_INFO *
0x18004918d  cmp     [rbp+arg_18], eax
0x180049190  mov     edx, edi; enum NLM_NETWORK_CATEGORY
0x180049192  mov     rcx, r12; this
0x180049195  setz    al
0x180049198  mov     [rbx+8], eax
0x18004919b  call    ?GetNetworkDetails@FirewallManager@ShieldProvider@@AEAAJW4NLM_NETWORK_CATEGORY@@PEAUtagFIREWALL_PROFILE_INFO@@@Z; ShieldProvider::FirewallManager::GetNetworkDetails(NLM_NETWORK_CATEGORY,tagFIREWALL_PROFILE_INFO *)
0x1800491a0  mov     esi, eax
0x1800491a2  test    eax, eax
0x1800491a4  jns     short loc_1800491D1
0x1800491a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800491ad  lea     rdi, WPP_GLOBAL_Control
0x1800491b4  cmp     rcx, rdi
0x1800491b7  jz      loc_180049257
0x1800491bd  test    byte ptr [rcx+1Ch], 1
0x1800491c1  jz      loc_180049257
0x1800491c7  mov     edx, 30h ; '0'
0x1800491cc  jmp     loc_1800490A7
0x1800491d1  call    ?IsOSWcos@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcos(void)
0x1800491d6  test    al, al
0x1800491d8  jnz     loc_180049276
0x1800491de  lea     r8, [rbx+14h]
0x1800491e2  lea     rdi, WPP_GLOBAL_Control
0x1800491e9  test    r8, r8
0x1800491ec  jnz     short loc_1800491F5
0x1800491ee  mov     esi, 80070057h
0x1800491f3  jmp     short loc_18004922D
0x1800491f5  mov     edx, r14d
0x1800491f8  call    FwIsGroupPolicyEnforced
0x1800491fd  mov     esi, eax
0x1800491ff  test    eax, eax
0x180049201  jns     short loc_180049264
0x180049203  mov     rcx, cs:WPP_GLOBAL_Control
0x18004920a  cmp     rcx, rdi
0x18004920d  jz      short loc_180049257
0x18004920f  test    byte ptr [rcx+1Ch], 1
0x180049213  jz      short loc_180049234
0x180049215  mov     rcx, [rcx+10h]
0x180049219  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049220  mov     edx, 3Ch ; '<'
0x180049225  mov     r9d, eax
0x180049228  call    WPP_SF_d
0x18004922d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049234  cmp     rcx, rdi
0x180049237  jz      short loc_180049257
0x180049239  test    byte ptr [rcx+1Ch], 1
0x18004923d  jz      short loc_180049257
0x18004923f  mov     edx, 31h ; '1'
0x180049244  mov     r9d, esi
0x180049247  mov     rcx, [rcx+10h]
0x18004924b  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x180049252  call    WPP_SF_d
0x180049257  mov     rcx, rbx; pv
0x18004925a  call    cs:__imp_CoTaskMemFree
0x180049260  mov     eax, esi
0x180049262  jmp     short loc_180049287
0x180049264  mov     r8d, r14d
0x180049267  mov     edx, 0Ah
0x18004926c  call    ?IsSettingControlledByPolicy@FirewallManager@ShieldProvider@@AEAAHW4_tag_FW_PROFILE_CONFIG@@W4NET_FW_PROFILE_TYPE2_@@@Z; ShieldProvider::FirewallManager::IsSettingControlledByPolicy(_tag_FW_PROFILE_CONFIG,NET_FW_PROFILE_TYPE2_)
0x180049271  mov     [rbx+1Ch], eax
0x180049274  jmp     short loc_18004927D
0x180049276  mov     dword ptr [rbx+1Ch], 0
0x18004927d  mov     [r15], rbx
0x180049280  jmp     short loc_180049260
0x180049282  mov     eax, 80070057h
0x180049287  lea     r11, [rsp+50h+var_s0]
0x18004928c  mov     rbx, [r11+30h]
0x180049290  mov     rsi, [r11+38h]
0x180049294  mov     rsp, r11
0x180049297  pop     r15
0x180049299  pop     r14
0x18004929b  pop     r12
0x18004929d  pop     rdi
0x18004929e  pop     rbp
0x18004929f  retn
```
