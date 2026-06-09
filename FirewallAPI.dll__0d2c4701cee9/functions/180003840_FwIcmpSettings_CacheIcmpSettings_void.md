# FwIcmpSettings::CacheIcmpSettings(void *)

- ea: `0x180003840`
- end: `0x180003bc9`
- name: `?CacheIcmpSettings@FwIcmpSettings@@AEAAJPEAX@Z`
- size: `905`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180003704`

## callees

- `0x180003840`
- `0x180005e0c`
- `0x180009780`
- `0x18000a530`
- `0x18001f770`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180003925`
- `ntdll!EtwEventWrite` at `0x1800039de`
- `ntdll!EtwEventWrite` at `0x180003925`
- `ntdll!EtwEventWrite` at `0x1800039de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000394e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000394e`
- `fwbase!FwReportReturnError` at `0x180003b48`
- `fwbase!FwReportReturnError` at `0x180003b67`
- `fwbase!FwReportReturnError` at `0x180003b48`
- `fwbase!FwReportReturnError` at `0x180003b67`

## string_xrefs

- `0x180003b41`: `FwIcmpSettings::CacheIcmpSettings`
- `0x180003b60`: `FwIcmpSettings::CacheIcmpSettings`

## pseudocode

```c
__int64 __fastcall FwIcmpSettings::CacheIcmpSettings(FwIcmpSettings *this, __int64 a2)
{
  unsigned int v4; // eax
  signed int IcmpSettingsFromRule; // edi
  bool v6; // sf
  struct _tag_FW_RULE *v7; // rbx
  __int16 v8; // ax
  struct _tag_FW_RULE *v10; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v11[2]; // [rsp+68h] [rbp-98h] BYREF
  int *v12; // [rsp+70h] [rbp-90h]
  __int64 v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+80h] [rbp-80h] BYREF
  __int64 v15; // [rsp+88h] [rbp-78h] BYREF
  int v16; // [rsp+90h] [rbp-70h]
  __int16 v17; // [rsp+98h] [rbp-68h]
  __int64 v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h] BYREF
  int v22; // [rsp+C0h] [rbp-40h]
  __int16 v23; // [rsp+C8h] [rbp-38h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v28; // [rsp+F0h] [rbp-10h]
  int v29; // [rsp+F8h] [rbp-8h]
  __int64 *v30; // [rsp+100h] [rbp+0h]

  v11[0] = 545;
  v10 = 0;
  v17 = 58;
  v14 = 0;
  v23 = 1;
  v28 = &v15;
  v24 = 1;
  v18 = 1;
  v30 = &v21;
  v12 = &v27;
  v13 = 0x10000;
  v21 = 5;
  v15 = 5;
  v22 = 2;
  v16 = 2;
  v25 = 3;
  v19 = 3;
  v26 = 196608;
  v20 = 196608;
  v27 = 2;
  v29 = 2;
  v11[1] = 2;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v4 = Int_FWQueryObject(
         0,
         (unsigned int)FWVerifyFirewallRuleQuery,
         (unsigned int)RPC_FWQueryFirewallRules,
         (unsigned int)RRPC_FWQueryFirewallRules,
         (__int64)Int_RPC_FWEnumFirewallRules2_0,
         (__int64)Int_RRPC_FWEnumFirewallRules2_0,
         a2,
         (__int64)v11,
         15,
         (__int64)&v14,
         (__int64)&v10,
         0);
  IcmpSettingsFromRule = v4;
  if ( v4 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v6 = IcmpSettingsFromRule < 0;
  if ( IcmpSettingsFromRule > 0 )
  {
    IcmpSettingsFromRule = (unsigned __int16)IcmpSettingsFromRule | 0x80070000;
    v6 = IcmpSettingsFromRule < 0;
  }
  if ( v6 )
  {
    FwReportReturnError("FwIcmpSettings::CacheIcmpSettings", (unsigned int)IcmpSettingsFromRule);
    FWFreeFirewallRules(v10);
  }
  else
  {
    v7 = v10;
    if ( v10 )
    {
      do
      {
        if ( !*((_DWORD *)v7 + 26)
          && !*((_DWORD *)v7 + 27)
          && !*((_DWORD *)v7 + 28)
          && !*((_DWORD *)v7 + 36)
          && !*((_DWORD *)v7 + 32)
          && !*((_DWORD *)v7 + 40)
          && !*((_DWORD *)v7 + 62)
          && !*((_DWORD *)v7 + 66)
          && !*((_DWORD *)v7 + 44)
          && !*((_DWORD *)v7 + 45)
          && !*((_DWORD *)v7 + 46)
          && !*((_DWORD *)v7 + 54)
          && !*((_DWORD *)v7 + 50)
          && !*((_DWORD *)v7 + 58)
          && (unsigned int)(*((_DWORD *)v7 + 72) - 2) <= 1
          && !*((_QWORD *)v7 + 34)
          && !*((_QWORD *)v7 + 35) )
        {
          v8 = *((_WORD *)v7 + 24);
          if ( (v8 == 1 || v8 == 58) && *((_DWORD *)v7 + 14) == 1 && *(_WORD *)(*((_QWORD *)v7 + 8) + 2LL) == 256 )
            IcmpSettingsFromRule = FwIcmpSettings::GetIcmpSettingsFromRule(this, v7);
        }
        v7 = *(struct _tag_FW_RULE **)v7;
      }
      while ( v7 );
      v7 = v10;
    }
    FWFreeFirewallRules(v7);
    if ( IcmpSettingsFromRule >= 0 )
      return (unsigned int)IcmpSettingsFromRule;
  }
  return FwReportReturnError("FwIcmpSettings::CacheIcmpSettings", (unsigned int)IcmpSettingsFromRule);
}

```

## disassembly

```asm
0x180003840  mov     [rsp-8+arg_10], rbx
0x180003845  mov     [rsp-8+arg_18], rsi
0x18000384a  push    rbp
0x18000384b  push    rdi
0x18000384c  push    r14
0x18000384e  lea     rbp, [rsp-10h]
0x180003853  sub     rsp, 110h
0x18000385a  mov     rax, cs:__security_cookie
0x180003861  xor     rax, rsp
0x180003864  mov     [rbp+20h+var_18], rax
0x180003868  xor     edi, edi
0x18000386a  mov     [rsp+120h+var_B8], 221h
0x180003872  mov     eax, 3Ah ; ':'
0x180003877  mov     [rsp+120h+var_C0], rdi
0x18000387c  mov     [rbp+20h+var_88], ax
0x180003880  mov     rsi, rcx
0x180003883  mov     ecx, 1
0x180003888  mov     [rbp+20h+var_A0], edi
0x18000388b  lea     rax, [rbp+20h+var_98]
0x18000388f  mov     [rbp+20h+var_58], cx
0x180003893  mov     [rbp+20h+var_30], rax
0x180003897  mov     rbx, rdx
0x18000389a  lea     rax, [rbp+20h+var_68]
0x18000389e  mov     [rbp+20h+var_50], rcx
0x1800038a2  mov     [rbp+20h+var_80], rcx
0x1800038a6  mov     rcx, cs:g_Provider
0x1800038ad  mov     [rbp+20h+var_20], rax
0x1800038b1  lea     rax, [rbp+20h+var_38]
0x1800038b5  mov     [rsp+120h+var_B0], rax
0x1800038ba  mov     [rsp+120h+var_A8], 10000h
0x1800038c3  mov     [rbp+20h+var_68], 5
0x1800038cb  mov     [rbp+20h+var_98], 5
0x1800038d3  mov     [rbp+20h+var_60], 2
0x1800038da  mov     [rbp+20h+var_90], 2
0x1800038e1  mov     [rbp+20h+var_48], 3
0x1800038e8  mov     [rbp+20h+var_78], 3
0x1800038ef  mov     [rbp+20h+var_40], 30000h
0x1800038f6  mov     [rbp+20h+var_70], 30000h
0x1800038fd  mov     [rbp+20h+var_38], 2
0x180003904  mov     [rbp+20h+var_28], 2
0x18000390b  mov     [rsp+120h+var_B4], 2
0x180003913  test    rcx, rcx
0x180003916  jz      short loc_180003931
0x180003918  xor     r9d, r9d
0x18000391b  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180003922  xor     r8d, r8d
0x180003925  call    cs:__imp_EtwEventWrite
0x18000392c  nop     dword ptr [rax+rax+00h]
0x180003931  mov     rcx, cs:WPP_GLOBAL_Control
0x180003938  lea     r14, WPP_GLOBAL_Control
0x18000393f  cmp     rcx, r14
0x180003942  jz      short loc_18000394E
0x180003944  test    byte ptr [rcx+1Ch], 8
0x180003948  jnz     loc_180003B78
0x18000394e  call    cs:__imp_GetTickCount64
0x180003955  nop     dword ptr [rax+rax+00h]
0x18000395a  mov     [rsp+120h+var_C8], edi
0x18000395e  lea     rax, [rsp+120h+var_C0]
0x180003963  mov     [rsp+120h+var_D0], rax
0x180003968  lea     r9, RRPC_FWQueryFirewallRules
0x18000396f  lea     rax, [rbp+20h+var_A0]
0x180003973  xor     ecx, ecx
0x180003975  mov     [rsp+120h+var_D8], rax
0x18000397a  lea     r8, RPC_FWQueryFirewallRules
0x180003981  mov     [rsp+120h+var_E0], 0Fh
0x180003988  lea     rax, [rsp+120h+var_B8]
0x18000398d  mov     [rsp+120h+var_E8], rax
0x180003992  lea     rdx, FWVerifyFirewallRuleQuery
0x180003999  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800039a0  mov     [rsp+120h+var_F0], rbx
0x1800039a5  mov     [rsp+120h+var_F8], rax
0x1800039aa  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800039b1  mov     [rsp+120h+var_100], rax
0x1800039b6  call    Int_FWQueryObject
0x1800039bb  mov     edi, eax
0x1800039bd  test    eax, eax
0x1800039bf  jnz     loc_180003B92
0x1800039c5  mov     rcx, cs:g_Provider
0x1800039cc  test    rcx, rcx
0x1800039cf  jz      short loc_1800039EA
0x1800039d1  xor     r9d, r9d
0x1800039d4  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x1800039db  xor     r8d, r8d
0x1800039de  call    cs:__imp_EtwEventWrite
0x1800039e5  nop     dword ptr [rax+rax+00h]
0x1800039ea  test    edi, edi
0x1800039ec  jg      loc_180003B0F
0x1800039f2  js      loc_180003B3F
0x1800039f8  mov     rbx, [rsp+120h+var_C0]
0x1800039fd  test    rbx, rbx
0x180003a00  jz      loc_180003ADC
0x180003a06  mov     r14d, 100h
0x180003a0c  nop     dword ptr [rax+00h]
0x180003a10  cmp     dword ptr [rbx+68h], 0
0x180003a14  jnz     loc_180003ACB
0x180003a1a  cmp     dword ptr [rbx+6Ch], 0
0x180003a1e  jnz     loc_180003ACB
0x180003a24  cmp     dword ptr [rbx+70h], 0
0x180003a28  jnz     loc_180003ACB
0x180003a2e  cmp     dword ptr [rbx+90h], 0
0x180003a35  jnz     loc_180003ACB
0x180003a3b  cmp     dword ptr [rbx+80h], 0
0x180003a42  jnz     loc_180003ACB
0x180003a48  cmp     dword ptr [rbx+0A0h], 0
0x180003a4f  jnz     short loc_180003ACB
0x180003a51  cmp     dword ptr [rbx+0F8h], 0
0x180003a58  jnz     short loc_180003ACB
0x180003a5a  cmp     dword ptr [rbx+108h], 0
0x180003a61  jnz     short loc_180003ACB
0x180003a63  cmp     dword ptr [rbx+0B0h], 0
0x180003a6a  jnz     short loc_180003ACB
0x180003a6c  cmp     dword ptr [rbx+0B4h], 0
0x180003a73  jnz     short loc_180003ACB
0x180003a75  cmp     dword ptr [rbx+0B8h], 0
0x180003a7c  jnz     short loc_180003ACB
0x180003a7e  cmp     dword ptr [rbx+0D8h], 0
0x180003a85  jnz     short loc_180003ACB
0x180003a87  cmp     dword ptr [rbx+0C8h], 0
0x180003a8e  jnz     short loc_180003ACB
0x180003a90  cmp     dword ptr [rbx+0E8h], 0
0x180003a97  jnz     short loc_180003ACB
0x180003a99  mov     eax, [rbx+120h]
0x180003a9f  sub     eax, 2
0x180003aa2  cmp     eax, 1
0x180003aa5  ja      short loc_180003ACB
0x180003aa7  cmp     qword ptr [rbx+110h], 0
0x180003aaf  jnz     short loc_180003ACB
0x180003ab1  cmp     qword ptr [rbx+118h], 0
0x180003ab9  jnz     short loc_180003ACB
0x180003abb  movzx   eax, word ptr [rbx+30h]
0x180003abf  cmp     ax, 1
0x180003ac3  jz      short loc_180003B1F
0x180003ac5  cmp     ax, 3Ah ; ':'
0x180003ac9  jz      short loc_180003B1F
0x180003acb  mov     rbx, [rbx]
0x180003ace  test    rbx, rbx
0x180003ad1  jnz     loc_180003A10
0x180003ad7  mov     rbx, [rsp+120h+var_C0]
0x180003adc  mov     rcx, rbx
0x180003adf  call    FWFreeFirewallRules
0x180003ae4  test    edi, edi
0x180003ae6  js      short loc_180003B5E
0x180003ae8  mov     eax, edi
0x180003aea  mov     rcx, [rbp+20h+var_18]
0x180003aee  xor     rcx, rsp; StackCookie
0x180003af1  call    __security_check_cookie
0x180003af6  lea     r11, [rsp+120h+var_10]
0x180003afe  mov     rbx, [r11+30h]
0x180003b02  mov     rsi, [r11+38h]
0x180003b06  mov     rsp, r11
0x180003b09  pop     r14
0x180003b0b  pop     rdi
0x180003b0c  pop     rbp
0x180003b0d  retn
0x180003b0f  movzx   edi, di
0x180003b12  or      edi, 80070000h
0x180003b18  test    edi, edi
0x180003b1a  jmp     loc_1800039F2
0x180003b1f  cmp     dword ptr [rbx+38h], 1
0x180003b23  jnz     short loc_180003ACB
0x180003b25  mov     rax, [rbx+40h]
0x180003b29  cmp     [rax+2], r14w
0x180003b2e  jnz     short loc_180003ACB
0x180003b30  mov     rdx, rbx; struct _tag_FW_RULE *
0x180003b33  mov     rcx, rsi; this
0x180003b36  call    ?GetIcmpSettingsFromRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@@Z; FwIcmpSettings::GetIcmpSettingsFromRule(_tag_FW_RULE *)
0x180003b3b  mov     edi, eax
0x180003b3d  jmp     short loc_180003ACB
0x180003b3f  mov     edx, edi
0x180003b41  lea     rcx, aFwicmpsettings_7; "FwIcmpSettings::CacheIcmpSettings"
0x180003b48  call    cs:__imp_FwReportReturnError
0x180003b4f  nop     dword ptr [rax+rax+00h]
0x180003b54  mov     rcx, [rsp+120h+var_C0]
0x180003b59  call    FWFreeFirewallRules
0x180003b5e  mov     edx, edi
0x180003b60  lea     rcx, aFwicmpsettings_7; "FwIcmpSettings::CacheIcmpSettings"
0x180003b67  call    cs:__imp_FwReportReturnError
0x180003b6e  nop     dword ptr [rax+rax+00h]
0x180003b73  jmp     loc_180003AEA
0x180003b78  mov     rcx, [rcx+10h]
0x180003b7c  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180003b83  mov     edx, 0B6h
0x180003b88  call    WPP_SF_
0x180003b8d  jmp     loc_18000394E
0x180003b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b99  cmp     rcx, r14
0x180003b9c  jz      loc_1800039C5
0x180003ba2  test    byte ptr [rcx+1Ch], 1
0x180003ba6  jz      loc_1800039C5
0x180003bac  mov     rcx, [rcx+10h]
0x180003bb0  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180003bb7  mov     edx, 0B7h
0x180003bbc  mov     r9d, edi
0x180003bbf  call    WPP_SF_d
0x180003bc4  jmp     loc_1800039C5
```
