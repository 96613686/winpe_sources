# FwMigrateLegacySettingsImpl(_tag_FW_PROFILE_TYPE)

- ea: `0x18002bc34`
- end: `0x18002bf66`
- name: `?FwMigrateLegacySettingsImpl@@YAJW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18002fc40`

## callees

- `0x180002ef0`
- `0x180003b94`
- `0x1800042c4`
- `0x180004320`
- `0x180008360`
- `0x18001a290`
- `0x18001c140`
- `0x18001f650`
- `0x18002b030`
- `0x18002b1cc`
- `0x18002bc34`
- `0x180031008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bdb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bde0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be0b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bdb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bde0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002be0b`
- `fwbase!IsRuleOldAuthApp` at `0x18002be36`
- `fwbase!IsRuleOldAuthApp` at `0x18002be36`
- `fwbase!FwReportReturnError` at `0x18002bcd3`
- `fwbase!FwReportReturnError` at `0x18002bf3c`
- `fwbase!FwReportReturnError` at `0x18002bcd3`
- `fwbase!FwReportReturnError` at `0x18002bf3c`

## string_xrefs

- `0x18002bdb1`: `@FirewallAPI.dll,-28752`
- `0x18002bdd9`: `@FirewallAPI.dll,-28502`
- `0x18002be04`: `@FirewallAPI.dll,-33002`
- `0x18002bd85`: `@FirewallAPI.dll,-23006`

## pseudocode

```c
__int64 __fastcall FwMigrateLegacySettingsImpl(unsigned int a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  char *v4; // rdi
  int v5; // eax
  int v6; // ecx
  int v7; // edx
  int v8; // r13d
  int v9; // r12d
  __int64 v10; // rcx
  _BYTE *v11; // rsi
  BOOL v12; // r14d
  int v13; // eax
  int v14; // eax
  BOOL v16; // [rsp+40h] [rbp-29h]
  BOOL v17; // [rsp+44h] [rbp-25h]
  BOOL v18; // [rsp+48h] [rbp-21h]
  struct _tag_WF_POLICY_STORE *v19; // [rsp+50h] [rbp-19h] BYREF
  void *v20; // [rsp+58h] [rbp-11h]
  void *v21; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v22; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v23; // [rsp+6Ch] [rbp+3h]

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v19 = 0;
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v2 = FwOpenPolicyStore(2, 2, 0, (__int64 *)&v19);
  v3 = v2;
  if ( v2 < 0
    || (v2 = FwEnumRules(v19, 196608, a1, 0), v3 = v2, v2 < 0)
    || (v2 = FwEnumLegacyLocalPolicyRules(a1, &v21, &v22), v3 = v2, v2 < 0) )
  {
    FwReportReturnError("FwMigrateLegacySettingsImpl", (unsigned int)v2);
  }
  else
  {
    v4 = (char *)v21;
    v5 = 0;
    v6 = 0;
    v16 = 0;
    v7 = 0;
    v17 = 0;
    v8 = 0;
    v18 = 0;
    v9 = 0;
    if ( v22 )
    {
      while ( 1 )
      {
        if ( *((_WORD *)v4 + 4) == 256 )
          *((_WORD *)v4 + 4) = 545;
        v10 = *((_QWORD *)v4 + 39);
        if ( !v10 )
          break;
        v11 = v4 + 292;
        v12 = *((_DWORD *)v4 + 72) == 3 && (*v11 & 1) != 0;
        if ( !(unsigned int)_o__wcsicmp(v10, L"@FirewallAPI.dll,-23006") )
        {
          v11 = v4 + 292;
          if ( (v4[292] & 2) == 0 )
          {
            v8 = v12;
            goto LABEL_35;
          }
        }
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)v4 + 39), L"@FirewallAPI.dll,-28752") && (*v11 & 2) == 0 )
        {
          v5 = v12;
          v16 = v12;
          goto LABEL_36;
        }
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)v4 + 39), L"@FirewallAPI.dll,-28502") && (*v11 & 2) == 0 )
        {
          v5 = v16;
          v6 = v12;
          v17 = v12;
          goto LABEL_37;
        }
        if ( (unsigned int)_o__wcsicmp(*((_QWORD *)v4 + 39), L"@FirewallAPI.dll,-33002") || (*v11 & 2) != 0 )
          break;
        v5 = v16;
        v7 = v12;
        v6 = v17;
        v18 = v12;
LABEL_38:
        v4 = *(char **)v4;
        if ( ++v9 >= v22 )
          goto LABEL_39;
      }
      *((_DWORD *)v4 + 10) = a1;
      if ( (unsigned int)IsRuleOldAuthApp(v4) && a1 == 2 )
        *((_DWORD *)v4 + 10) |= 4u;
      v13 = FwAddRule(v19);
      v3 = v13;
      if ( v13 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          358,
          (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          *((_QWORD *)v4 + 3),
          v13);
LABEL_35:
      v5 = v16;
LABEL_36:
      v6 = v17;
LABEL_37:
      v7 = v18;
      goto LABEL_38;
    }
LABEL_39:
    FwEnableBuiltInSvcGroup(v19, a1, (__int64)v20, v23, v8, v5, v6, v7);
  }
  FwFreeRules(v20);
  FwFreeRules(v21);
  if ( v19 )
  {
    v14 = FwClosePolicyStore(v19);
    v3 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          359,
          WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          (unsigned int)v14);
      return (unsigned int)FwReportReturnError("FwMigrateLegacySettingsImpl", v3);
    }
  }
  else if ( (v3 & 0x80000000) != 0 )
  {
    return (unsigned int)FwReportReturnError("FwMigrateLegacySettingsImpl", v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18002bc34  push    rbp
0x18002bc36  push    rbx
0x18002bc37  push    rsi
0x18002bc38  push    rdi
0x18002bc39  push    r12
0x18002bc3b  push    r13
0x18002bc3d  push    r14
0x18002bc3f  push    r15
0x18002bc41  lea     rbp, [rsp-1Fh]
0x18002bc46  sub     rsp, 88h
0x18002bc4d  mov     rax, cs:__security_cookie
0x18002bc54  xor     rax, rsp
0x18002bc57  mov     [rbp+57h+var_50], rax
0x18002bc5b  mov     r15d, ecx
0x18002bc5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc65  lea     rsi, WPP_GLOBAL_Control
0x18002bc6c  cmp     rcx, rsi
0x18002bc6f  jz      short loc_18002BC8C
0x18002bc71  test    byte ptr [rcx+1Ch], 8
0x18002bc75  jz      short loc_18002BC8C
0x18002bc77  mov     rcx, [rcx+10h]
0x18002bc7b  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002bc82  mov     edx, 165h
0x18002bc87  call    WPP_SF_
0x18002bc8c  xor     r8d, r8d
0x18002bc8f  mov     [rbp+57h+var_70], 0
0x18002bc97  lea     r9, [rbp+57h+var_70]
0x18002bc9b  mov     [rbp+57h+var_68], 0
0x18002bca3  mov     [rbp+57h+var_54], 0
0x18002bcaa  mov     [rbp+57h+var_60], 0
0x18002bcb2  lea     edx, [r8+2]
0x18002bcb6  mov     [rbp+57h+var_58], 0
0x18002bcbd  mov     ecx, edx
0x18002bcbf  call    FwOpenPolicyStore
0x18002bcc4  mov     ebx, eax
0x18002bcc6  test    eax, eax
0x18002bcc8  jns     short loc_18002BCDE
0x18002bcca  mov     edx, eax
0x18002bccc  lea     rcx, aFwmigratelegac_1; "FwMigrateLegacySettingsImpl"
0x18002bcd3  call    cs:__imp_FwReportReturnError
0x18002bcd9  jmp     loc_18002BED9
0x18002bcde  mov     rcx, [rbp+57h+var_70]; struct _tag_WF_POLICY_STORE *
0x18002bce2  lea     r9, [rbp+57h+var_54]
0x18002bce6  mov     [rsp+0C0h+var_90], 0; int
0x18002bcee  lea     r8, [rbp+57h+var_68]
0x18002bcf2  mov     [rsp+0C0h+var_98], r15d; int
0x18002bcf7  xor     edx, edx
0x18002bcf9  mov     [rsp+0C0h+var_A0], 30000h; int
0x18002bd01  call    FwEnumRules
0x18002bd06  mov     ebx, eax
0x18002bd08  test    eax, eax
0x18002bd0a  js      short loc_18002BCCA
0x18002bd0c  lea     r8, [rbp+57h+var_58]
0x18002bd10  mov     ecx, r15d
0x18002bd13  lea     rdx, [rbp+57h+var_60]
0x18002bd17  call    ?FwEnumLegacyLocalPolicyRules@@YAJW4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z; FwEnumLegacyLocalPolicyRules(_tag_FW_PROFILE_TYPE,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)
0x18002bd1c  mov     ebx, eax
0x18002bd1e  test    eax, eax
0x18002bd20  js      short loc_18002BCCA
0x18002bd22  mov     rdi, [rbp+57h+var_60]
0x18002bd26  xor     eax, eax
0x18002bd28  xor     ecx, ecx
0x18002bd2a  mov     [rbp+57h+var_80], eax
0x18002bd2d  xor     edx, edx
0x18002bd2f  mov     [rbp+57h+var_7C], ecx
0x18002bd32  xor     r13d, r13d
0x18002bd35  mov     [rbp+57h+var_78], edx
0x18002bd38  xor     r12d, r12d
0x18002bd3b  cmp     [rbp+57h+var_58], eax
0x18002bd3e  jbe     loc_18002BEB4
0x18002bd44  mov     eax, 100h
0x18002bd49  cmp     [rdi+8], ax
0x18002bd4d  jnz     short loc_18002BD55
0x18002bd4f  mov     word ptr [rdi+8], 221h
0x18002bd55  mov     rcx, [rdi+138h]
0x18002bd5c  test    rcx, rcx
0x18002bd5f  jz      loc_18002BE2F
0x18002bd65  cmp     dword ptr [rdi+120h], 3
0x18002bd6c  lea     rsi, [rdi+124h]
0x18002bd73  jnz     short loc_18002BD82
0x18002bd75  test    byte ptr [rsi], 1
0x18002bd78  jz      short loc_18002BD82
0x18002bd7a  mov     r14d, 1
0x18002bd80  jmp     short loc_18002BD85
0x18002bd82  xor     r14d, r14d
0x18002bd85  lea     rdx, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x18002bd8c  call    cs:__imp__o__wcsicmp
0x18002bd92  test    eax, eax
0x18002bd94  jnz     short loc_18002BDAA
0x18002bd96  lea     rsi, [rdi+124h]
0x18002bd9d  test    byte ptr [rsi], 2
0x18002bda0  jnz     short loc_18002BDAA
0x18002bda2  mov     r13d, r14d
0x18002bda5  jmp     loc_18002BE8D
0x18002bdaa  mov     rcx, [rdi+138h]
0x18002bdb1  lea     rdx, aFirewallapiDll_2; "@FirewallAPI.dll,-28752"
0x18002bdb8  call    cs:__imp__o__wcsicmp
0x18002bdbe  test    eax, eax
0x18002bdc0  jnz     short loc_18002BDD2
0x18002bdc2  test    byte ptr [rsi], 2
0x18002bdc5  jnz     short loc_18002BDD2
0x18002bdc7  mov     eax, r14d
0x18002bdca  mov     [rbp+57h+var_80], eax
0x18002bdcd  jmp     loc_18002BE90
0x18002bdd2  mov     rcx, [rdi+138h]
0x18002bdd9  lea     rdx, aFirewallapiDll_4; "@FirewallAPI.dll,-28502"
0x18002bde0  call    cs:__imp__o__wcsicmp
0x18002bde6  test    eax, eax
0x18002bde8  jnz     short loc_18002BDFD
0x18002bdea  test    byte ptr [rsi], 2
0x18002bded  jnz     short loc_18002BDFD
0x18002bdef  mov     eax, [rbp+57h+var_80]
0x18002bdf2  mov     ecx, r14d
0x18002bdf5  mov     [rbp+57h+var_7C], ecx
0x18002bdf8  jmp     loc_18002BE93
0x18002bdfd  mov     rcx, [rdi+138h]
0x18002be04  lea     rdx, aFirewallapiDll; "@FirewallAPI.dll,-33002"
0x18002be0b  call    cs:__imp__o__wcsicmp
0x18002be11  test    eax, eax
0x18002be13  jnz     short loc_18002BE28
0x18002be15  test    byte ptr [rsi], 2
0x18002be18  jnz     short loc_18002BE28
0x18002be1a  mov     eax, [rbp+57h+var_80]
0x18002be1d  mov     edx, r14d
0x18002be20  mov     ecx, [rbp+57h+var_7C]
0x18002be23  mov     [rbp+57h+var_78], edx
0x18002be26  jmp     short loc_18002BE96
0x18002be28  lea     rsi, WPP_GLOBAL_Control
0x18002be2f  mov     rcx, rdi
0x18002be32  mov     [rdi+28h], r15d
0x18002be36  call    cs:__imp_IsRuleOldAuthApp
0x18002be3c  test    eax, eax
0x18002be3e  jz      short loc_18002BE4A
0x18002be40  cmp     r15d, 2
0x18002be44  jnz     short loc_18002BE4A
0x18002be46  or      dword ptr [rdi+28h], 4
0x18002be4a  mov     rcx, [rbp+57h+var_70]; struct _tag_WF_POLICY_STORE *
0x18002be4e  mov     r8, rdi
0x18002be51  xor     edx, edx
0x18002be53  call    FwAddRule
0x18002be58  mov     ebx, eax
0x18002be5a  test    eax, eax
0x18002be5c  jns     short loc_18002BE8D
0x18002be5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be65  cmp     rcx, rsi
0x18002be68  jz      short loc_18002BE8D
0x18002be6a  test    byte ptr [rcx+1Ch], 1
0x18002be6e  jz      short loc_18002BE8D
0x18002be70  mov     r9, [rdi+18h]
0x18002be74  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002be7b  mov     rcx, [rcx+10h]
0x18002be7f  mov     edx, 166h
0x18002be84  mov     [rsp+0C0h+var_A0], eax
0x18002be88  call    WPP_SF_Sd
0x18002be8d  mov     eax, [rbp+57h+var_80]
0x18002be90  mov     ecx, [rbp+57h+var_7C]
0x18002be93  mov     edx, [rbp+57h+var_78]
0x18002be96  mov     rdi, [rdi]
0x18002be99  lea     rsi, WPP_GLOBAL_Control
0x18002bea0  inc     r12d
0x18002bea3  cmp     r12d, [rbp+57h+var_58]
0x18002bea7  jb      loc_18002BD44
0x18002bead  lea     rsi, WPP_GLOBAL_Control
0x18002beb4  mov     r9d, [rbp+57h+var_54]
0x18002beb8  mov     r8, [rbp+57h+var_68]
0x18002bebc  mov     [rsp+0C0h+var_88], edx
0x18002bec0  mov     edx, r15d
0x18002bec3  mov     [rsp+0C0h+var_90], ecx
0x18002bec7  mov     rcx, [rbp+57h+var_70]
0x18002becb  mov     [rsp+0C0h+var_98], eax
0x18002becf  mov     [rsp+0C0h+var_A0], r13d
0x18002bed4  call    ?FwEnableBuiltInSvcGroup@@YAXPEAXW4_tag_FW_PROFILE_TYPE@@PEAU_tag_FW_RULE@@KHHHH@Z; FwEnableBuiltInSvcGroup(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE *,ulong,int,int,int,int)
0x18002bed9  mov     rcx, [rbp+57h+var_68]; void *
0x18002bedd  xor     edx, edx
0x18002bedf  call    FwFreeRules
0x18002bee4  mov     rcx, [rbp+57h+var_60]; void *
0x18002bee8  xor     edx, edx
0x18002beea  call    FwFreeRules
0x18002beef  mov     rcx, [rbp+57h+var_70]; struct _tag_WF_POLICY_STORE *
0x18002bef3  test    rcx, rcx
0x18002bef6  jz      short loc_18002BF2F
0x18002bef8  call    FwClosePolicyStore
0x18002befd  mov     ebx, eax
0x18002beff  test    eax, eax
0x18002bf01  jns     short loc_18002BF44
0x18002bf03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf0a  cmp     rcx, rsi
0x18002bf0d  jz      short loc_18002BF33
0x18002bf0f  test    byte ptr [rcx+1Ch], 1
0x18002bf13  jz      short loc_18002BF33
0x18002bf15  mov     rcx, [rcx+10h]
0x18002bf19  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002bf20  mov     edx, 167h
0x18002bf25  mov     r9d, eax
0x18002bf28  call    WPP_SF_d
0x18002bf2d  jmp     short loc_18002BF33
0x18002bf2f  test    ebx, ebx
0x18002bf31  jns     short loc_18002BF44
0x18002bf33  mov     edx, ebx
0x18002bf35  lea     rcx, aFwmigratelegac_1; "FwMigrateLegacySettingsImpl"
0x18002bf3c  call    cs:__imp_FwReportReturnError
0x18002bf42  mov     ebx, eax
0x18002bf44  mov     eax, ebx
0x18002bf46  mov     rcx, [rbp+57h+var_50]
0x18002bf4a  xor     rcx, rsp; StackCookie
0x18002bf4d  call    __security_check_cookie
0x18002bf52  add     rsp, 88h
0x18002bf59  pop     r15
0x18002bf5b  pop     r14
0x18002bf5d  pop     r13
0x18002bf5f  pop     r12
0x18002bf61  pop     rdi
0x18002bf62  pop     rsi
0x18002bf63  pop     rbx
0x18002bf64  pop     rbp
0x18002bf65  retn
```
