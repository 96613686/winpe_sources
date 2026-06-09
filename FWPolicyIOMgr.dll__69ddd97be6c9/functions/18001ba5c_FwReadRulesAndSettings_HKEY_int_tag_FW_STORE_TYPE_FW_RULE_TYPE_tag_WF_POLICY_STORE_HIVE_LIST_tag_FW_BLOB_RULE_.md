# FwReadRulesAndSettings(HKEY__ *,int,_tag_FW_STORE_TYPE,FW_RULE_TYPE,_tag_WF_POLICY_STORE_HIVE_LIST *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)

- ea: `0x18001ba5c`
- end: `0x18001c130`
- name: `?FwReadRulesAndSettings@@YAJPEAUHKEY__@@HW4_tag_FW_STORE_TYPE@@W4FW_RULE_TYPE@@PEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z`
- size: `1748`
- prototype: `__int64 __fastcall(HKEY, int, unsigned int, unsigned int, __int64, struct _tag_FW_RULE **, _DWORD *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a290`
- `0x18002b1cc`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18000f420`
- `0x18001a628`
- `0x18001a718`
- `0x18001aecc`
- `0x18001ba5c`
- `0x18001e4b0`
- `0x18001f650`
- `0x18002ad4c`
- `0x180031964`
- `0x180032050`
- `0x18003993c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c101`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c101`
- `fwbase!FwGetIcmpSettings` at `0x18001bd50`
- `fwbase!FwGetIcmpSettings` at `0x18001bd50`
- `fwbase!FwGetServiceTypes` at `0x18001bc89`
- `fwbase!FwGetServiceTypes` at `0x18001bc89`
- `fwbase!FwGetServices` at `0x18001bca0`
- `fwbase!FwGetServices` at `0x18001bca0`
- `fwbase!FwIcfAuthBypassServicesDestroy` at `0x18001bce6`
- `fwbase!FwIcfAuthBypassServicesDestroy` at `0x18001c0d9`
- `fwbase!FwIcfAuthBypassServicesDestroy` at `0x18001bce6`
- `fwbase!FwIcfAuthBypassServicesDestroy` at `0x18001c0d9`
- `fwbase!FwGetRemoteAdminSettings` at `0x18001bbe9`
- `fwbase!FwGetRemoteAdminSettings` at `0x18001bbe9`
- `fwbase!FwIcfAuthBypassSubNetsDestroy` at `0x18001bc3e`
- `fwbase!FwIcfAuthBypassSubNetsDestroy` at `0x18001c0e3`
- `fwbase!FwIcfAuthBypassSubNetsDestroy` at `0x18001bc3e`
- `fwbase!FwIcfAuthBypassSubNetsDestroy` at `0x18001c0e3`

## pseudocode

```c
__int64 __fastcall FwReadRulesAndSettings(
        HKEY a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        struct _tag_FW_RULE **a6,
        _DWORD *a7,
        unsigned int a8,
        unsigned int a9)
{
  unsigned int v9; // r14d
  HKEY v10; // r11
  int v11; // r8d
  unsigned int v12; // eax
  int v13; // ebx
  __int64 v14; // r10
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edx
  int ProfileHandleForLegacyEnum; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // edx
  HKEY v23; // r14
  __int64 v24; // rdx
  int v25; // edx
  __int64 v26; // rdx
  __int64 v27; // rdx
  LPCOLESTR v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v34; // [rsp+44h] [rbp-BCh]
  HKEY v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h]
  HKEY v38; // [rsp+68h] [rbp-98h]
  __int128 v39; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+80h] [rbp-80h]
  __int128 v41; // [rsp+90h] [rbp-70h]
  unsigned int v42[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v44[3]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[40]; // [rsp+F0h] [rbp-10h] BYREF
  HKEY hKey[2]; // [rsp+118h] [rbp+18h] BYREF

  v9 = a4;
  v10 = a1;
  v37 = a3;
  v11 = a2;
  v38 = a1;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v10 = v38;
    v11 = a2;
  }
  v12 = 0;
  v13 = 0;
  *(_OWORD *)hKey = 0;
  memset(v44, 0, sizeof(v44));
  v43 = 0;
  v34 = 0;
  if ( !*(_DWORD *)a5 )
  {
LABEL_85:
    SetRulesOrigin(v37, *a6, v9);
    goto LABEL_86;
  }
  while ( 1 )
  {
    v14 = *(_QWORD *)(a5 + 8);
    v42[0] = 0;
    v15 = 2LL * v12;
    memset(v45, 0, sizeof(v45));
    v36[0] = 0;
    v16 = *(unsigned int *)(v14 + 16LL * v12 + 8);
    switch ( (_DWORD)v16 )
    {
      case 0:
        goto LABEL_45;
      case 1:
        v31 = *(_DWORD *)(v14 + 16LL * v12 + 12);
        if ( (v31 & a9) == 0 )
          goto LABEL_27;
        ProfileHandleForLegacyEnum = FwEnumGlobalOpenPorts(
                                       v10,
                                       *(const unsigned __int16 **)(v14 + 8 * v15),
                                       v42,
                                       a6,
                                       a8,
                                       v11,
                                       v31);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_51;
          v29 = 81;
          goto LABEL_49;
        }
        goto LABEL_44;
      case 2:
        v30 = *(_DWORD *)(v14 + 16LL * v12 + 12);
        if ( (v30 & a9) == 0 )
          goto LABEL_27;
        ProfileHandleForLegacyEnum = FwEnumAuthApps(
                                       v10,
                                       *(const unsigned __int16 **)(v14 + 8 * v15),
                                       v42,
                                       a6,
                                       a8,
                                       v11,
                                       v30);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v29 = 82;
            goto LABEL_49;
          }
          goto LABEL_51;
        }
        goto LABEL_44;
    }
    if ( (_DWORD)v16 != 3 )
      break;
    v25 = *(_DWORD *)(v14 + 16LL * v12 + 12);
    if ( (v25 & a9) != 0 )
    {
      ProfileHandleForLegacyEnum = FwGetProfileHandleForLegacyEnum(
                                     v10,
                                     v25,
                                     *(const unsigned __int16 **)(v14 + 16LL * v12),
                                     hKey,
                                     v36);
      v13 = ProfileHandleForLegacyEnum;
      if ( ProfileHandleForLegacyEnum < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_86;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_51;
        v29 = 83;
        goto LABEL_49;
      }
      if ( v36[0] )
      {
        ProfileHandleForLegacyEnum = FwGetIcmpSettings(v36[0], v45);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_51;
          v29 = 84;
          goto LABEL_49;
        }
        v26 = *(_QWORD *)(a5 + 8);
        v39 = *(_OWORD *)v45;
        v27 = *(unsigned int *)(v26 + 8 * v15 + 12);
        *(_QWORD *)&v41 = *(_QWORD *)&v45[32];
        v40 = *(_OWORD *)&v45[16];
        ProfileHandleForLegacyEnum = FwConvertIcmpSettingsToRules(&v39, v27, a6, v42);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v29 = 85;
            goto LABEL_49;
          }
          goto LABEL_51;
        }
        goto LABEL_44;
      }
    }
LABEL_27:
    v12 = v34 + 1;
    v34 = v12;
    if ( v12 >= *(_DWORD *)a5 )
    {
      if ( v13 >= 0 )
        goto LABEL_85;
      goto LABEL_50;
    }
    v10 = v38;
    v11 = a2;
  }
  if ( (_DWORD)v16 == 4 )
  {
    v22 = *(_DWORD *)(v14 + 16LL * v12 + 12);
    if ( (v22 & a9) != 0 )
    {
      ProfileHandleForLegacyEnum = FwGetProfileHandleForLegacyEnum(
                                     v10,
                                     v22,
                                     *(const unsigned __int16 **)(v14 + 16LL * v12),
                                     hKey,
                                     v36);
      v13 = ProfileHandleForLegacyEnum;
      if ( ProfileHandleForLegacyEnum < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_86;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_51;
        v29 = 86;
        goto LABEL_49;
      }
      v23 = v36[0];
      if ( v36[0] )
      {
        ProfileHandleForLegacyEnum = FwGetServiceTypes(&v43);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_51;
          v29 = 87;
          goto LABEL_49;
        }
        ProfileHandleForLegacyEnum = FwGetServices(v23, &v43);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_51;
          v29 = 88;
          goto LABEL_49;
        }
        v24 = *(_QWORD *)(a5 + 8);
        *(_OWORD *)v36 = v43;
        ProfileHandleForLegacyEnum = FwConvertServiceSettingsToRules(
                                       (unsigned int *)v36,
                                       *(_DWORD *)(v24 + 8 * v15 + 12),
                                       a6,
                                       v42);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            goto LABEL_86;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_51;
          v29 = 89;
          goto LABEL_49;
        }
        *a7 += v42[0];
        FwIcfAuthBypassServicesDestroy(&v43);
      }
      v9 = a4;
    }
    goto LABEL_27;
  }
  if ( (_DWORD)v16 == 5 )
  {
    v18 = *(_DWORD *)(v14 + 16LL * v12 + 12);
    if ( (v18 & a9) == 0 )
      goto LABEL_27;
    ProfileHandleForLegacyEnum = FwGetProfileHandleForLegacyEnum(
                                   v10,
                                   v18,
                                   *(const unsigned __int16 **)(v14 + 16LL * v12),
                                   hKey,
                                   v36);
    v13 = ProfileHandleForLegacyEnum;
    if ( ProfileHandleForLegacyEnum < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        goto LABEL_86;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_51;
      v29 = 90;
      goto LABEL_49;
    }
    if ( v36[0] )
    {
      ProfileHandleForLegacyEnum = FwGetRemoteAdminSettings(v36[0], v44);
      v13 = ProfileHandleForLegacyEnum;
      if ( ProfileHandleForLegacyEnum < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_86;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_51;
        v29 = 91;
      }
      else
      {
        v20 = *(_QWORD *)(a5 + 8);
        v39 = v44[0];
        v21 = *(unsigned int *)(v20 + 8 * v15 + 12);
        v40 = v44[1];
        v41 = v44[2];
        ProfileHandleForLegacyEnum = FwConvertRemoteAdminSettingsToRules(&v39, v21, a6, v42);
        v13 = ProfileHandleForLegacyEnum;
        if ( ProfileHandleForLegacyEnum >= 0 )
        {
          *a7 += v42[0];
          FwIcfAuthBypassSubNetsDestroy((char *)v44 + 8);
          goto LABEL_27;
        }
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_86;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_51;
        v29 = 92;
      }
LABEL_49:
      WPP_SF_d(
        *((_QWORD *)v28 + 2),
        v29,
        WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        (unsigned int)ProfileHandleForLegacyEnum);
LABEL_50:
      v28 = WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    goto LABEL_27;
  }
  v17 = (unsigned int)(v16 - 8);
  if ( (unsigned int)v17 >= 2 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(v17, v16);
    v13 = -2147024809;
    goto LABEL_27;
  }
LABEL_45:
  ProfileHandleForLegacyEnum = FwEnumAdvPolicyRules(*(&g_RuleManipulators + (int)v9), a6, a8, a9);
  v13 = ProfileHandleForLegacyEnum;
  if ( ProfileHandleForLegacyEnum >= 0 )
  {
LABEL_44:
    *a7 += v42[0];
    goto LABEL_27;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
    goto LABEL_86;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v29 = 80;
    goto LABEL_49;
  }
LABEL_51:
  if ( v28 != (LPCOLESTR)&WPP_GLOBAL_Control && (v28[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v28 + 2), 93, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v13);
LABEL_86:
  FwIcfAuthBypassServicesDestroy(&v43);
  FwIcfAuthBypassSubNetsDestroy((char *)v44 + 8);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( hKey[1] )
    RegCloseKey(hKey[1]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ba5c  mov     [rsp-8+arg_10], rbx
0x18001ba61  push    rbp
0x18001ba62  push    rsi
0x18001ba63  push    rdi
0x18001ba64  push    r12
0x18001ba66  push    r13
0x18001ba68  push    r14
0x18001ba6a  push    r15
0x18001ba6c  lea     rbp, [rsp-30h]
0x18001ba71  sub     rsp, 130h
0x18001ba78  mov     rax, cs:__security_cookie
0x18001ba7f  xor     rax, rsp
0x18001ba82  mov     [rbp+60h+var_38], rax
0x18001ba86  mov     r13, [rbp+60h+arg_20]
0x18001ba8d  mov     r14d, r9d
0x18001ba90  mov     r12, [rbp+60h+arg_28]
0x18001ba97  mov     r11, rcx
0x18001ba9a  mov     rsi, [rbp+60h+arg_30]
0x18001baa1  mov     [rsp+160h+var_100], r8d
0x18001baa6  mov     r8d, edx
0x18001baa9  mov     [rsp+160h+var_120], r9d
0x18001baae  mov     [rsp+160h+var_118], edx
0x18001bab2  mov     [rsp+160h+var_F8], rcx
0x18001bab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001babe  lea     rax, WPP_GLOBAL_Control
0x18001bac5  cmp     rcx, rax
0x18001bac8  jz      short loc_18001BAEF
0x18001baca  test    byte ptr [rcx+1Ch], 8
0x18001bace  jz      short loc_18001BAEF
0x18001bad0  mov     rcx, [rcx+10h]
0x18001bad4  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001badb  mov     edx, 4Fh ; 'O'
0x18001bae0  call    WPP_SF_
0x18001bae5  mov     r11, [rsp+160h+var_F8]
0x18001baea  mov     r8d, [rsp+160h+var_118]
0x18001baef  xorps   xmm0, xmm0
0x18001baf2  xor     eax, eax
0x18001baf4  xor     ebx, ebx
0x18001baf6  mov     [rbp+60h+var_78], rax
0x18001bafa  movdqu  xmmword ptr [rbp+60h+hKey], xmm0
0x18001baff  mov     qword ptr [rbp+60h+var_A0], rbx
0x18001bb03  movups  [rbp+60h+var_B0], xmm0
0x18001bb07  mov     [rsp+160h+var_11C], eax
0x18001bb0b  movups  [rbp+60h+var_A0+8], xmm0
0x18001bb0f  movups  [rbp+60h+var_88], xmm0
0x18001bb13  cmp     [r13+0], eax
0x18001bb17  jbe     loc_18001C0C5
0x18001bb1d  mov     r15d, [rbp+60h+arg_40]
0x18001bb24  mov     r10, [r13+8]
0x18001bb28  xor     ecx, ecx
0x18001bb2a  xorps   xmm0, xmm0
0x18001bb2d  mov     [rbp+60h+var_4C], ecx
0x18001bb30  mov     [rbp+60h+var_C0], ecx
0x18001bb33  mov     edi, eax
0x18001bb35  add     rdi, rdi
0x18001bb38  mov     dword ptr [rbp+60h+var_70], 0
0x18001bb3f  movups  [rbp+60h+var_70+4], xmm0
0x18001bb43  mov     [rsp+160h+var_110], rcx
0x18001bb48  movups  [rbp+60h+var_5C], xmm0
0x18001bb4c  mov     edx, [r10+rdi*8+8]
0x18001bb51  mov     ecx, edx
0x18001bb53  test    edx, edx
0x18001bb55  jz      loc_18001BE76
0x18001bb5b  sub     ecx, 1
0x18001bb5e  jz      loc_18001BE2E
0x18001bb64  sub     ecx, 1
0x18001bb67  jz      loc_18001BDC9
0x18001bb6d  sub     ecx, 1
0x18001bb70  jz      loc_18001BD14
0x18001bb76  sub     ecx, 1
0x18001bb79  jz      loc_18001BC49
0x18001bb7f  sub     ecx, 1
0x18001bb82  jz      short loc_18001BBA5
0x18001bb84  sub     ecx, 3
0x18001bb87  jz      loc_18001BE76
0x18001bb8d  cmp     ecx, 1
0x18001bb90  jz      loc_18001BE76
0x18001bb96  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001bb9b  mov     ebx, 80070057h
0x18001bba0  jmp     loc_18001BCF1
0x18001bba5  mov     edx, [r10+rdi*8+0Ch]; unsigned int
0x18001bbaa  test    r15d, edx
0x18001bbad  jz      loc_18001BCF1
0x18001bbb3  mov     r8, [r10+rdi*8]; unsigned __int16 *
0x18001bbb7  lea     rax, [rsp+160h+var_110]
0x18001bbbc  lea     r9, [rbp+60h+hKey]; HKEY *
0x18001bbc0  mov     [rsp+160h+var_140], rax; HKEY *
0x18001bbc5  mov     rcx, r11; HKEY
0x18001bbc8  call    ?FwGetProfileHandleForLegacyEnum@@YAJPEAUHKEY__@@KPEBGPEAPEAU1@2@Z; FwGetProfileHandleForLegacyEnum(HKEY__ *,ulong,ushort const *,HKEY__ * *,HKEY__ * *)
0x18001bbcd  mov     ebx, eax
0x18001bbcf  test    eax, eax
0x18001bbd1  js      loc_18001BF65
0x18001bbd7  mov     rcx, [rsp+160h+var_110]
0x18001bbdc  test    rcx, rcx
0x18001bbdf  jz      loc_18001BCF1
0x18001bbe5  lea     rdx, [rbp+60h+var_A0]
0x18001bbe9  call    cs:__imp_FwGetRemoteAdminSettings
0x18001bbef  mov     ebx, eax
0x18001bbf1  test    eax, eax
0x18001bbf3  js      loc_18001BF3E
0x18001bbf9  movups  xmm0, [rbp+60h+var_A0]
0x18001bbfd  mov     rdx, [r13+8]
0x18001bc01  lea     r9, [rbp+60h+var_C0]
0x18001bc05  movups  xmm1, xmmword ptr [rbp-30h]
0x18001bc09  lea     rcx, [rsp+160h+var_F0]
0x18001bc0e  mov     r8, r12
0x18001bc11  movaps  [rsp+160h+var_F0], xmm0
0x18001bc16  movups  xmm0, [rbp+60h+var_88+8]
0x18001bc1a  mov     edx, [rdx+rdi*8+0Ch]
0x18001bc1e  movaps  [rbp+60h+var_E0], xmm1
0x18001bc22  movaps  [rbp+60h+var_D0], xmm0
0x18001bc26  call    ?FwConvertRemoteAdminSettingsToRules@@YAJUICF_AUTHBYPASS_REMOTE_ADMIN_SETTINGS_@@KPEAPEAU_tag_FW_RULE@@PEAK@Z; FwConvertRemoteAdminSettingsToRules(ICF_AUTHBYPASS_REMOTE_ADMIN_SETTINGS_,ulong,_tag_FW_RULE * *,ulong *)
0x18001bc2b  mov     ebx, eax
0x18001bc2d  test    eax, eax
0x18001bc2f  js      loc_18001BF1A
0x18001bc35  mov     eax, [rbp+60h+var_C0]
0x18001bc38  lea     rcx, [rbp+60h+var_A0+8]
0x18001bc3c  add     [rsi], eax
0x18001bc3e  call    cs:__imp_FwIcfAuthBypassSubNetsDestroy
0x18001bc44  jmp     loc_18001BCF1
0x18001bc49  mov     edx, [r10+rdi*8+0Ch]; unsigned int
0x18001bc4e  test    r15d, edx
0x18001bc51  jz      loc_18001BCF1
0x18001bc57  mov     r8, [r10+rdi*8]; unsigned __int16 *
0x18001bc5b  lea     rax, [rsp+160h+var_110]
0x18001bc60  lea     r9, [rbp+60h+hKey]; HKEY *
0x18001bc64  mov     [rsp+160h+var_140], rax; HKEY *
0x18001bc69  mov     rcx, r11; HKEY
0x18001bc6c  call    ?FwGetProfileHandleForLegacyEnum@@YAJPEAUHKEY__@@KPEBGPEAPEAU1@2@Z; FwGetProfileHandleForLegacyEnum(HKEY__ *,ulong,ushort const *,HKEY__ * *,HKEY__ * *)
0x18001bc71  mov     ebx, eax
0x18001bc73  test    eax, eax
0x18001bc75  js      loc_18001C011
0x18001bc7b  mov     r14, [rsp+160h+var_110]
0x18001bc80  test    r14, r14
0x18001bc83  jz      short loc_18001BCEC
0x18001bc85  lea     rcx, [rbp+60h+var_B0]
0x18001bc89  call    cs:__imp_FwGetServiceTypes
0x18001bc8f  mov     ebx, eax
0x18001bc91  test    eax, eax
0x18001bc93  js      loc_18001BFE6
0x18001bc99  lea     rdx, [rbp+60h+var_B0]
0x18001bc9d  mov     rcx, r14
0x18001bca0  call    cs:__imp_FwGetServices
0x18001bca6  mov     ebx, eax
0x18001bca8  test    eax, eax
0x18001bcaa  js      loc_18001BFBB
0x18001bcb0  mov     rdx, [r13+8]
0x18001bcb4  lea     r9, [rbp+60h+var_C0]
0x18001bcb8  movaps  xmm0, [rbp+60h+var_B0]
0x18001bcbc  lea     rcx, [rsp+160h+var_110]
0x18001bcc1  mov     r8, r12
0x18001bcc4  movdqa  xmmword ptr [rsp+160h+var_110], xmm0
0x18001bcca  mov     edx, [rdx+rdi*8+0Ch]
0x18001bcce  call    ?FwConvertServiceSettingsToRules@@YAJUICF_AUTHBYPASS_SERVICES_@@KPEAPEAU_tag_FW_RULE@@PEAK@Z; FwConvertServiceSettingsToRules(ICF_AUTHBYPASS_SERVICES_,ulong,_tag_FW_RULE * *,ulong *)
0x18001bcd3  mov     ebx, eax
0x18001bcd5  test    eax, eax
0x18001bcd7  js      loc_18001BF90
0x18001bcdd  mov     eax, [rbp+60h+var_C0]
0x18001bce0  lea     rcx, [rbp+60h+var_B0]
0x18001bce4  add     [rsi], eax
0x18001bce6  call    cs:__imp_FwIcfAuthBypassServicesDestroy
0x18001bcec  mov     r14d, [rsp+160h+var_120]
0x18001bcf1  mov     eax, [rsp+160h+var_11C]
0x18001bcf5  inc     eax
0x18001bcf7  mov     [rsp+160h+var_11C], eax
0x18001bcfb  cmp     eax, [r13+0]
0x18001bcff  jnb     loc_18001C0B5
0x18001bd05  mov     r11, [rsp+160h+var_F8]
0x18001bd0a  mov     r8d, [rsp+160h+var_118]
0x18001bd0f  jmp     loc_18001BB24
0x18001bd14  mov     edx, [r10+rdi*8+0Ch]; unsigned int
0x18001bd19  test    r15d, edx
0x18001bd1c  jz      short loc_18001BCF1
0x18001bd1e  mov     r8, [r10+rdi*8]; unsigned __int16 *
0x18001bd22  lea     rax, [rsp+160h+var_110]
0x18001bd27  lea     r9, [rbp+60h+hKey]; HKEY *
0x18001bd2b  mov     [rsp+160h+var_140], rax; HKEY *
0x18001bd30  mov     rcx, r11; HKEY
0x18001bd33  call    ?FwGetProfileHandleForLegacyEnum@@YAJPEAUHKEY__@@KPEBGPEAPEAU1@2@Z; FwGetProfileHandleForLegacyEnum(HKEY__ *,ulong,ushort const *,HKEY__ * *,HKEY__ * *)
0x18001bd38  mov     ebx, eax
0x18001bd3a  test    eax, eax
0x18001bd3c  js      loc_18001C067
0x18001bd42  mov     rcx, [rsp+160h+var_110]
0x18001bd47  test    rcx, rcx
0x18001bd4a  jz      short loc_18001BCF1
0x18001bd4c  lea     rdx, [rbp+60h+var_70]
0x18001bd50  call    cs:__imp_FwGetIcmpSettings
0x18001bd56  mov     ebx, eax
0x18001bd58  test    eax, eax
0x18001bd5a  js      loc_18001C03C
0x18001bd60  movups  xmm0, [rbp+60h+var_70]
0x18001bd64  mov     rdx, [r13+8]
0x18001bd68  lea     r9, [rbp+60h+var_C0]
0x18001bd6c  movups  xmm1, xmmword ptr [rbp+0]
0x18001bd70  lea     rcx, [rsp+160h+var_F0]
0x18001bd75  mov     r8, r12
0x18001bd78  movaps  [rsp+160h+var_F0], xmm0
0x18001bd7d  movsd   xmm0, qword ptr [rbp+60h+var_5C+0Ch]
0x18001bd82  mov     edx, [rdx+rdi*8+0Ch]
0x18001bd86  movsd   qword ptr [rbp+60h+var_D0], xmm0
0x18001bd8b  movaps  [rbp+60h+var_E0], xmm1
0x18001bd8f  call    ?FwConvertIcmpSettingsToRules@@YAJUICF_ICMP_SETTINGS_@@KPEAPEAU_tag_FW_RULE@@PEAK@Z; FwConvertIcmpSettingsToRules(ICF_ICMP_SETTINGS_,ulong,_tag_FW_RULE * *,ulong *)
0x18001bd94  mov     ebx, eax
0x18001bd96  test    eax, eax
0x18001bd98  jns     loc_18001BE6C
0x18001bd9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bda5  lea     rdi, WPP_GLOBAL_Control
0x18001bdac  cmp     rcx, rdi
0x18001bdaf  jz      loc_18001C0D5
0x18001bdb5  test    byte ptr [rcx+1Ch], 1
0x18001bdb9  jz      loc_18001BEEA
0x18001bdbf  mov     edx, 55h ; 'U'
0x18001bdc4  jmp     loc_18001BED0
0x18001bdc9  mov     eax, [r10+rdi*8+0Ch]
0x18001bdce  test    r15d, eax
0x18001bdd1  jz      loc_18001BCF1
0x18001bdd7  mov     rdx, [r10+rdi*8]; unsigned __int16 *
0x18001bddb  mov     r9, r12; struct _tag_FW_RULE **
0x18001bdde  mov     [rsp+160h+var_130], eax; unsigned int
0x18001bde2  mov     rcx, r11; HKEY
0x18001bde5  mov     eax, [rbp+60h+arg_38]
0x18001bdeb  mov     [rsp+160h+var_138], r8d; int
0x18001bdf0  lea     r8, [rbp+60h+var_C0]; unsigned int *
0x18001bdf4  mov     dword ptr [rsp+160h+var_140], eax; unsigned int
0x18001bdf8  call    ?FwEnumAuthApps@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAU_tag_FW_RULE@@KHK@Z; FwEnumAuthApps(HKEY__ *,ushort const *,ulong *,_tag_FW_RULE * *,ulong,int,ulong)
0x18001bdfd  mov     ebx, eax
0x18001bdff  test    eax, eax
0x18001be01  jns     short loc_18001BE6C
0x18001be03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be0a  lea     rdi, WPP_GLOBAL_Control
0x18001be11  cmp     rcx, rdi
0x18001be14  jz      loc_18001C0D5
0x18001be1a  test    byte ptr [rcx+1Ch], 1
0x18001be1e  jz      loc_18001BEEA
0x18001be24  mov     edx, 52h ; 'R'
0x18001be29  jmp     loc_18001BED0
0x18001be2e  mov     eax, [r10+rdi*8+0Ch]
0x18001be33  test    r15d, eax
0x18001be36  jz      loc_18001BCF1
0x18001be3c  mov     rdx, [r10+rdi*8]; unsigned __int16 *
0x18001be40  mov     r9, r12; struct _tag_FW_RULE **
0x18001be43  mov     [rsp+160h+var_130], eax; unsigned int
0x18001be47  mov     rcx, r11; HKEY
0x18001be4a  mov     eax, [rbp+60h+arg_38]
0x18001be50  mov     [rsp+160h+var_138], r8d; int
0x18001be55  lea     r8, [rbp+60h+var_C0]; unsigned int *
0x18001be59  mov     dword ptr [rsp+160h+var_140], eax; unsigned int
0x18001be5d  call    ?FwEnumGlobalOpenPorts@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAU_tag_FW_RULE@@KHK@Z; FwEnumGlobalOpenPorts(HKEY__ *,ushort const *,ulong *,_tag_FW_RULE * *,ulong,int,ulong)
0x18001be62  mov     ebx, eax
0x18001be64  test    eax, eax
0x18001be66  js      loc_18001C08E
0x18001be6c  mov     eax, [rbp+60h+var_C0]
0x18001be6f  add     [rsi], eax
0x18001be71  jmp     loc_18001BCF1
0x18001be76  mov     eax, [rbp+60h+arg_38]
0x18001be7c  lea     rbx, ?g_RuleManipulators@@3PAPEAU_tag_FW_RULE_MANIPULATOR@@A; _tag_FW_RULE_MANIPULATOR * near * g_RuleManipulators
0x18001be83  mov     r8, [r10+rdi*8]
0x18001be87  lea     r9, [rbp+60h+var_C0]
0x18001be8b  mov     [rsp+160h+var_130], r15d; unsigned int
0x18001be90  mov     rdx, r11
0x18001be93  mov     [rsp+160h+var_138], eax; unsigned int
0x18001be97  movsxd  rcx, r14d
0x18001be9a  mov     [rsp+160h+var_140], r12; struct _tag_FW_BLOB_RULE **
0x18001be9f  mov     rcx, [rbx+rcx*8]; struct _tag_FW_RULE_MANIPULATOR *
0x18001bea3  call    FwEnumAdvPolicyRules
0x18001bea8  mov     ebx, eax
0x18001beaa  test    eax, eax
0x18001beac  jns     short loc_18001BE6C
0x18001beae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beb5  lea     rdi, WPP_GLOBAL_Control
0x18001bebc  cmp     rcx, rdi
0x18001bebf  jz      loc_18001C0D5
0x18001bec5  test    byte ptr [rcx+1Ch], 1
0x18001bec9  jz      short loc_18001BEEA
0x18001becb  mov     edx, 50h ; 'P'
0x18001bed0  mov     rcx, [rcx+10h]
0x18001bed4  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001bedb  mov     r9d, eax
0x18001bede  call    WPP_SF_d
0x18001bee3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beea  cmp     rcx, rdi
0x18001beed  jz      loc_18001C0D5
0x18001bef3  test    byte ptr [rcx+1Ch], 1
0x18001bef7  jz      loc_18001C0D5
0x18001befd  mov     rcx, [rcx+10h]
0x18001bf01  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001bf08  mov     edx, 5Dh ; ']'
0x18001bf0d  mov     r9d, ebx
0x18001bf10  call    WPP_SF_d
0x18001bf15  jmp     loc_18001C0D5
0x18001bf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf21  lea     rdi, WPP_GLOBAL_Control
0x18001bf28  cmp     rcx, rdi
0x18001bf2b  jz      loc_18001C0D5
0x18001bf31  test    byte ptr [rcx+1Ch], 1
0x18001bf35  jz      short loc_18001BEEA
0x18001bf37  mov     edx, 5Ch ; '\'
0x18001bf3c  jmp     short loc_18001BED0
0x18001bf3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf45  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
