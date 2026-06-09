# FwIcmpSettings::CacheIcmpSettings(void *)

- ea: `0x180003580`
- end: `0x1800038e9`
- name: `?CacheIcmpSettings@FwIcmpSettings@@AEAAJPEAX@Z`
- size: `873`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180003454`

## callees

- `0x180003580`
- `0x180005954`
- `0x180009080`
- `0x180009fb0`
- `0x18001e664`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180003665`
- `ntdll!EtwEventWrite` at `0x180003712`
- `ntdll!EtwEventWrite` at `0x180003665`
- `ntdll!EtwEventWrite` at `0x180003712`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003688`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003688`
- `fwbase!FwReportReturnError` at `0x180003877`
- `fwbase!FwReportReturnError` at `0x180003890`
- `fwbase!FwReportReturnError` at `0x180003877`
- `fwbase!FwReportReturnError` at `0x180003890`

## string_xrefs

- `0x180003870`: `FwIcmpSettings::CacheIcmpSettings`
- `0x180003889`: `FwIcmpSettings::CacheIcmpSettings`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v4);
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
0x180003580  mov     [rsp-8+arg_10], rbx
0x180003585  mov     [rsp-8+arg_18], rsi
0x18000358a  push    rbp
0x18000358b  push    rdi
0x18000358c  push    r14
0x18000358e  lea     rbp, [rsp-10h]
0x180003593  sub     rsp, 110h
0x18000359a  mov     rax, cs:__security_cookie
0x1800035a1  xor     rax, rsp
0x1800035a4  mov     [rbp+20h+var_18], rax
0x1800035a8  xor     edi, edi
0x1800035aa  mov     [rsp+120h+var_B8], 221h
0x1800035b2  mov     eax, 3Ah ; ':'
0x1800035b7  mov     [rsp+120h+var_C0], rdi
0x1800035bc  mov     [rbp+20h+var_88], ax
0x1800035c0  mov     rsi, rcx
0x1800035c3  mov     ecx, 1
0x1800035c8  mov     [rbp+20h+var_A0], edi
0x1800035cb  lea     rax, [rbp+20h+var_98]
0x1800035cf  mov     [rbp+20h+var_58], cx
0x1800035d3  mov     [rbp+20h+var_30], rax
0x1800035d7  mov     rbx, rdx
0x1800035da  lea     rax, [rbp+20h+var_68]
0x1800035de  mov     [rbp+20h+var_50], rcx
0x1800035e2  mov     [rbp+20h+var_80], rcx
0x1800035e6  mov     rcx, cs:g_Provider
0x1800035ed  mov     [rbp+20h+var_20], rax
0x1800035f1  lea     rax, [rbp+20h+var_38]
0x1800035f5  mov     [rsp+120h+var_B0], rax
0x1800035fa  mov     [rsp+120h+var_A8], 10000h
0x180003603  mov     [rbp+20h+var_68], 5
0x18000360b  mov     [rbp+20h+var_98], 5
0x180003613  mov     [rbp+20h+var_60], 2
0x18000361a  mov     [rbp+20h+var_90], 2
0x180003621  mov     [rbp+20h+var_48], 3
0x180003628  mov     [rbp+20h+var_78], 3
0x18000362f  mov     [rbp+20h+var_40], 30000h
0x180003636  mov     [rbp+20h+var_70], 30000h
0x18000363d  mov     [rbp+20h+var_38], 2
0x180003644  mov     [rbp+20h+var_28], 2
0x18000364b  mov     [rsp+120h+var_B4], 2
0x180003653  test    rcx, rcx
0x180003656  jz      short loc_18000366B
0x180003658  xor     r9d, r9d
0x18000365b  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180003662  xor     r8d, r8d
0x180003665  call    cs:__imp_EtwEventWrite
0x18000366b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003672  lea     r14, WPP_GLOBAL_Control
0x180003679  cmp     rcx, r14
0x18000367c  jz      short loc_180003688
0x18000367e  test    byte ptr [rcx+1Ch], 8
0x180003682  jnz     loc_180003898
0x180003688  call    cs:__imp_GetTickCount64
0x18000368e  mov     [rsp+120h+var_C8], edi
0x180003692  lea     rax, [rsp+120h+var_C0]
0x180003697  mov     [rsp+120h+var_D0], rax
0x18000369c  lea     r9, RRPC_FWQueryFirewallRules
0x1800036a3  lea     rax, [rbp+20h+var_A0]
0x1800036a7  xor     ecx, ecx
0x1800036a9  mov     [rsp+120h+var_D8], rax
0x1800036ae  lea     r8, RPC_FWQueryFirewallRules
0x1800036b5  mov     [rsp+120h+var_E0], 0Fh
0x1800036bc  lea     rax, [rsp+120h+var_B8]
0x1800036c1  mov     [rsp+120h+var_E8], rax
0x1800036c6  lea     rdx, FWVerifyFirewallRuleQuery
0x1800036cd  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800036d4  mov     [rsp+120h+var_F0], rbx
0x1800036d9  mov     [rsp+120h+var_F8], rax
0x1800036de  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800036e5  mov     [rsp+120h+var_100], rax
0x1800036ea  call    Int_FWQueryObject
0x1800036ef  mov     edi, eax
0x1800036f1  test    eax, eax
0x1800036f3  jnz     loc_1800038B2
0x1800036f9  mov     rcx, cs:g_Provider
0x180003700  test    rcx, rcx
0x180003703  jz      short loc_180003718
0x180003705  xor     r9d, r9d
0x180003708  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000370f  xor     r8d, r8d
0x180003712  call    cs:__imp_EtwEventWrite
0x180003718  test    edi, edi
0x18000371a  jg      loc_18000383E
0x180003720  js      loc_18000386E
0x180003726  mov     rbx, [rsp+120h+var_C0]
0x18000372b  test    rbx, rbx
0x18000372e  jz      loc_18000380C
0x180003734  mov     r14d, 100h
0x18000373a  nop     word ptr [rax+rax+00h]
0x180003740  cmp     dword ptr [rbx+68h], 0
0x180003744  jnz     loc_1800037FB
0x18000374a  cmp     dword ptr [rbx+6Ch], 0
0x18000374e  jnz     loc_1800037FB
0x180003754  cmp     dword ptr [rbx+70h], 0
0x180003758  jnz     loc_1800037FB
0x18000375e  cmp     dword ptr [rbx+90h], 0
0x180003765  jnz     loc_1800037FB
0x18000376b  cmp     dword ptr [rbx+80h], 0
0x180003772  jnz     loc_1800037FB
0x180003778  cmp     dword ptr [rbx+0A0h], 0
0x18000377f  jnz     short loc_1800037FB
0x180003781  cmp     dword ptr [rbx+0F8h], 0
0x180003788  jnz     short loc_1800037FB
0x18000378a  cmp     dword ptr [rbx+108h], 0
0x180003791  jnz     short loc_1800037FB
0x180003793  cmp     dword ptr [rbx+0B0h], 0
0x18000379a  jnz     short loc_1800037FB
0x18000379c  cmp     dword ptr [rbx+0B4h], 0
0x1800037a3  jnz     short loc_1800037FB
0x1800037a5  cmp     dword ptr [rbx+0B8h], 0
0x1800037ac  jnz     short loc_1800037FB
0x1800037ae  cmp     dword ptr [rbx+0D8h], 0
0x1800037b5  jnz     short loc_1800037FB
0x1800037b7  cmp     dword ptr [rbx+0C8h], 0
0x1800037be  jnz     short loc_1800037FB
0x1800037c0  cmp     dword ptr [rbx+0E8h], 0
0x1800037c7  jnz     short loc_1800037FB
0x1800037c9  mov     eax, [rbx+120h]
0x1800037cf  sub     eax, 2
0x1800037d2  cmp     eax, 1
0x1800037d5  ja      short loc_1800037FB
0x1800037d7  cmp     qword ptr [rbx+110h], 0
0x1800037df  jnz     short loc_1800037FB
0x1800037e1  cmp     qword ptr [rbx+118h], 0
0x1800037e9  jnz     short loc_1800037FB
0x1800037eb  movzx   eax, word ptr [rbx+30h]
0x1800037ef  cmp     ax, 1
0x1800037f3  jz      short loc_18000384E
0x1800037f5  cmp     ax, 3Ah ; ':'
0x1800037f9  jz      short loc_18000384E
0x1800037fb  mov     rbx, [rbx]
0x1800037fe  test    rbx, rbx
0x180003801  jnz     loc_180003740
0x180003807  mov     rbx, [rsp+120h+var_C0]
0x18000380c  mov     rcx, rbx
0x18000380f  call    FWFreeFirewallRules
0x180003814  test    edi, edi
0x180003816  js      short loc_180003887
0x180003818  mov     eax, edi
0x18000381a  mov     rcx, [rbp+20h+var_18]
0x18000381e  xor     rcx, rsp; StackCookie
0x180003821  call    __security_check_cookie
0x180003826  lea     r11, [rsp+120h+var_10]
0x18000382e  mov     rbx, [r11+30h]
0x180003832  mov     rsi, [r11+38h]
0x180003836  mov     rsp, r11
0x180003839  pop     r14
0x18000383b  pop     rdi
0x18000383c  pop     rbp
0x18000383d  retn
0x18000383e  movzx   edi, di
0x180003841  or      edi, 80070000h
0x180003847  test    edi, edi
0x180003849  jmp     loc_180003720
0x18000384e  cmp     dword ptr [rbx+38h], 1
0x180003852  jnz     short loc_1800037FB
0x180003854  mov     rax, [rbx+40h]
0x180003858  cmp     [rax+2], r14w
0x18000385d  jnz     short loc_1800037FB
0x18000385f  mov     rdx, rbx; struct _tag_FW_RULE *
0x180003862  mov     rcx, rsi; this
0x180003865  call    ?GetIcmpSettingsFromRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@@Z; FwIcmpSettings::GetIcmpSettingsFromRule(_tag_FW_RULE *)
0x18000386a  mov     edi, eax
0x18000386c  jmp     short loc_1800037FB
0x18000386e  mov     edx, edi
0x180003870  lea     rcx, aFwicmpsettings_7; "FwIcmpSettings::CacheIcmpSettings"
0x180003877  call    cs:__imp_FwReportReturnError
0x18000387d  mov     rcx, [rsp+120h+var_C0]
0x180003882  call    FWFreeFirewallRules
0x180003887  mov     edx, edi
0x180003889  lea     rcx, aFwicmpsettings_7; "FwIcmpSettings::CacheIcmpSettings"
0x180003890  call    cs:__imp_FwReportReturnError
0x180003896  jmp     short loc_18000381A
0x180003898  mov     rcx, [rcx+10h]
0x18000389c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800038a3  mov     edx, 0B7h
0x1800038a8  call    WPP_SF_
0x1800038ad  jmp     loc_180003688
0x1800038b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038b9  cmp     rcx, r14
0x1800038bc  jz      loc_1800036F9
0x1800038c2  test    byte ptr [rcx+1Ch], 1
0x1800038c6  jz      loc_1800036F9
0x1800038cc  mov     rcx, [rcx+10h]
0x1800038d0  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800038d7  mov     edx, 0B8h
0x1800038dc  mov     r9d, edi
0x1800038df  call    WPP_SF_d
0x1800038e4  jmp     loc_1800036F9
```
