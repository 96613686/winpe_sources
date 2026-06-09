# FwAuthSuiteFieldParserCertCriteria(ushort const *,_tag_FW_AUTH_SUITE *)

- ea: `0x180035c40`
- end: `0x180035f6f`
- name: `?FwAuthSuiteFieldParserCertCriteria@@YAJPEBGPEAU_tag_FW_AUTH_SUITE@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_AUTH_SUITE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042c4`
- `0x18000ef00`
- `0x18001a56c`
- `0x18001f650`
- `0x180035a88`
- `0x180035c40`

## import_xrefs

- `fwbase!FwFree` at `0x180035e9d`
- `fwbase!FwFree` at `0x180035e9d`
- `fwbase!FwAlloc` at `0x180035d87`
- `fwbase!FwAlloc` at `0x180035d87`
- `fwbase!FwStringCopy` at `0x180035cd0`
- `fwbase!FwStringCopy` at `0x180035cd0`
- `fwbase!FwFreeCertCriteria` at `0x180035eaa`
- `fwbase!FwFreeCertCriteria` at `0x180035eaa`

## pseudocode

```c
__int64 __fastcall FwAuthSuiteFieldParserCertCriteria(const unsigned __int16 *a1, struct _tag_FW_AUTH_SUITE *a2)
{
  unsigned __int16 *v3; // r12
  struct _tag_FW_CERT_CRITERIA *v4; // r14
  unsigned int v5; // edi
  __int64 v6; // r9
  int v7; // ebx
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 v10; // si
  struct _tag_FW_RULE_PARSER *SmallestCompatibleParserForSchemaVersion; // r15
  unsigned __int16 *v13; // rax
  __int64 i; // rcx
  int v15; // eax
  __int64 v16; // r9
  LPCOLESTR v17; // rcx
  __int64 v18; // rdx
  int v19; // [rsp+30h] [rbp-20h]
  unsigned int v20; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v21; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v22; // [rsp+40h] [rbp-10h] BYREF

  v21 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  v22 = 0;
  v5 = 0;
  v19 = 0;
  if ( !a1 )
  {
    v6 = 2147549183LL;
    v7 = -2147418113;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_36;
    v9 = 15;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids, v6);
    goto LABEL_36;
  }
  v7 = FwStringCopy(a1, &v22);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_36;
    v9 = 16;
LABEL_10:
    v6 = (unsigned int)v7;
    goto LABEL_5;
  }
  v3 = v22;
  v7 = FwAdvPolicyRuleDecodeVersion(v22, &v21, &v20, (const unsigned __int16 **)&v22);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_36;
    v9 = 17;
    goto LABEL_10;
  }
  v10 = (unsigned __int8)v20 | ((unsigned __int8)v21 << 8);
  SmallestCompatibleParserForSchemaVersion = FwFindSmallestCompatibleParserForSchemaVersion(
                                               v10,
                                               1u,
                                               &g_CertCriteriaParsers);
  if ( !SmallestCompatibleParserForSchemaVersion )
    return 2147942487LL;
  v13 = (unsigned __int16 *)FwAlloc(48);
  v4 = (struct _tag_FW_CERT_CRITERIA *)v13;
  if ( !v13 )
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids, 2147942414LL);
    goto LABEL_36;
  }
  *v13 = v10;
  for ( i = 0; ; i = v5 )
  {
    while ( 1 )
    {
      if ( !v22[v5] )
      {
        *((_QWORD *)a2 + 2) = v4;
        if ( v5 != (_DWORD)i )
        {
          v16 = 2147549183LL;
          v7 = -2147418113;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v18 = 22;
            goto LABEL_34;
          }
        }
        goto LABEL_35;
      }
      if ( v22[v5] == 124 )
        break;
      ++v5;
    }
    if ( v5 == (_DWORD)i )
    {
      v16 = 2147549183LL;
      v7 = -2147418113;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v18 = 19;
        goto LABEL_34;
      }
      goto LABEL_35;
    }
    v22[v5] = 0;
    v20 = 0;
    v15 = FwAdvPolicyParseCriteriaFields(&v22[i], v4, &v20, SmallestCompatibleParserForSchemaVersion, v10);
    v16 = (unsigned int)v15;
    if ( v15 != -2147467263 )
      break;
    if ( v10 <= 0x221u )
    {
      v7 = -2147024809;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v18 = 20;
        v16 = 2147942487LL;
LABEL_34:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids, v16);
        goto LABEL_35;
      }
      goto LABEL_35;
    }
    v19 = 1;
LABEL_29:
    ++v5;
  }
  v7 = v15;
  if ( v15 >= 0 )
    goto LABEL_29;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v18 = 21;
    goto LABEL_34;
  }
LABEL_35:
  v5 = v19;
LABEL_36:
  FwFree(v3);
  if ( v7 < 0 )
    FwFreeCertCriteria(v4);
  if ( v5 )
    return (unsigned int)-2147467263;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035c40  mov     [rsp-38h+arg_10], rbx
0x180035c45  push    rbp
0x180035c46  push    rsi
0x180035c47  push    rdi
0x180035c48  push    r12
0x180035c4a  push    r13
0x180035c4c  push    r14
0x180035c4e  push    r15
0x180035c50  mov     rbp, rsp
0x180035c53  sub     rsp, 50h
0x180035c57  mov     rax, cs:__security_cookie
0x180035c5e  xor     rax, rsp
0x180035c61  mov     [rbp+var_8], rax
0x180035c65  xor     eax, eax
0x180035c67  mov     r13, rdx
0x180035c6a  mov     [rbp+var_18], eax
0x180035c6d  mov     r12d, eax
0x180035c70  mov     [rbp+var_1C], eax
0x180035c73  mov     r14d, eax
0x180035c76  mov     [rbp+var_10], rax
0x180035c7a  mov     edi, eax
0x180035c7c  mov     [rbp+var_20], eax
0x180035c7f  mov     esi, 80004001h
0x180035c84  test    rcx, rcx
0x180035c87  jnz     short loc_180035CCC
0x180035c89  mov     r9d, 8000FFFFh
0x180035c8f  mov     ebx, r9d
0x180035c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c99  lea     rax, WPP_GLOBAL_Control
0x180035ca0  cmp     rcx, rax
0x180035ca3  jz      loc_180035E9A
0x180035ca9  test    byte ptr [rcx+1Ch], 1
0x180035cad  jz      loc_180035E9A
0x180035cb3  lea     edx, [r14+0Fh]
0x180035cb7  mov     rcx, [rcx+10h]
0x180035cbb  lea     r8, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids
0x180035cc2  call    WPP_SF_d
0x180035cc7  jmp     loc_180035E9A
0x180035ccc  lea     rdx, [rbp+var_10]
0x180035cd0  call    cs:__imp_FwStringCopy
0x180035cd6  mov     ebx, eax
0x180035cd8  test    eax, eax
0x180035cda  jns     short loc_180035D07
0x180035cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ce3  lea     rax, WPP_GLOBAL_Control
0x180035cea  cmp     rcx, rax
0x180035ced  jz      loc_180035E9A
0x180035cf3  test    byte ptr [rcx+1Ch], 1
0x180035cf7  jz      loc_180035E9A
0x180035cfd  mov     edx, 10h
0x180035d02  mov     r9d, ebx
0x180035d05  jmp     short loc_180035CB7
0x180035d07  mov     r12, [rbp+var_10]
0x180035d0b  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180035d0f  mov     rcx, r12; unsigned __int16 *
0x180035d12  lea     r8, [rbp+var_1C]; unsigned int *
0x180035d16  lea     rdx, [rbp+var_18]; unsigned int *
0x180035d1a  call    ?FwAdvPolicyRuleDecodeVersion@@YAJPEBGPEAK1PEAPEBG@Z; FwAdvPolicyRuleDecodeVersion(ushort const *,ulong *,ulong *,ushort const * *)
0x180035d1f  mov     ebx, eax
0x180035d21  test    eax, eax
0x180035d23  jns     short loc_180035D4D
0x180035d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d2c  lea     rax, WPP_GLOBAL_Control
0x180035d33  cmp     rcx, rax
0x180035d36  jz      loc_180035E9A
0x180035d3c  test    byte ptr [rcx+1Ch], 1
0x180035d40  jz      loc_180035E9A
0x180035d46  mov     edx, 11h
0x180035d4b  jmp     short loc_180035D02
0x180035d4d  movzx   eax, byte ptr [rbp+var_1C]
0x180035d51  lea     r8, ?g_CertCriteriaParsers@@3PAPEAU_tag_FW_RULE_PARSER@@A; struct _tag_FW_RULE_PARSER **
0x180035d58  movzx   esi, byte ptr [rbp+var_18]
0x180035d5c  mov     edx, 1; unsigned int
0x180035d61  shl     si, 8
0x180035d65  or      si, ax
0x180035d68  movzx   ecx, si; unsigned __int16
0x180035d6b  call    ?FwFindSmallestCompatibleParserForSchemaVersion@@YAPEAU_tag_FW_RULE_PARSER@@GKPEAPEAU1@@Z; FwFindSmallestCompatibleParserForSchemaVersion(ushort,ulong,_tag_FW_RULE_PARSER * *)
0x180035d70  mov     r15, rax
0x180035d73  test    rax, rax
0x180035d76  jnz     short loc_180035D82
0x180035d78  mov     eax, 80070057h
0x180035d7d  jmp     loc_180035EB7
0x180035d82  mov     ecx, 30h ; '0'
0x180035d87  call    cs:__imp_FwAlloc
0x180035d8d  xor     r9d, r9d
0x180035d90  mov     r14, rax
0x180035d93  test    rax, rax
0x180035d96  jnz     short loc_180035DDA
0x180035d98  mov     ebx, 8007000Eh
0x180035d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035da4  lea     rax, WPP_GLOBAL_Control
0x180035dab  cmp     rcx, rax
0x180035dae  jz      loc_180035E95
0x180035db4  test    byte ptr [rcx+1Ch], 1
0x180035db8  jz      loc_180035E95
0x180035dbe  mov     rcx, [rcx+10h]
0x180035dc2  lea     edx, [r14+12h]
0x180035dc6  mov     r9d, ebx
0x180035dc9  lea     r8, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids
0x180035dd0  call    WPP_SF_d
0x180035dd5  jmp     loc_180035E95
0x180035dda  mov     [rax], si
0x180035ddd  mov     ecx, r9d
0x180035de0  mov     r8, [rbp+var_10]
0x180035de4  mov     edx, edi
0x180035de6  cmp     [r8+rdx*2], r9w
0x180035deb  jz      loc_180035F2F
0x180035df1  cmp     word ptr [r8+rdx*2], 7Ch ; '|'
0x180035df7  jnz     short loc_180035E58
0x180035df9  cmp     edi, ecx
0x180035dfb  jz      loc_180035EFB
0x180035e01  mov     [r8+rdx*2], r9w
0x180035e06  lea     r8, [rbp+var_1C]; unsigned int *
0x180035e0a  mov     rax, [rbp+var_10]
0x180035e0e  mov     rdx, r14; struct _tag_FW_CERT_CRITERIA *
0x180035e11  mov     [rbp+var_1C], r9d
0x180035e15  mov     r9, r15; struct _tag_FW_RULE_PARSER *
0x180035e18  mov     [rsp+50h+var_30], si; unsigned __int16
0x180035e1d  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x180035e21  call    ?FwAdvPolicyParseCriteriaFields@@YAJPEBGPEAU_tag_FW_CERT_CRITERIA@@PEAKPEAU_tag_FW_RULE_PARSER@@G@Z; FwAdvPolicyParseCriteriaFields(ushort const *,_tag_FW_CERT_CRITERIA *,ulong *,_tag_FW_RULE_PARSER *,ushort)
0x180035e26  mov     r9d, eax
0x180035e29  cmp     eax, 80004001h
0x180035e2e  jnz     short loc_180035E43
0x180035e30  mov     eax, 221h
0x180035e35  cmp     si, ax
0x180035e38  jbe     short loc_180035E5C
0x180035e3a  mov     [rbp+var_20], 1
0x180035e41  jmp     short loc_180035E4F
0x180035e43  mov     ebx, r9d
0x180035e46  test    r9d, r9d
0x180035e49  js      loc_180035EDB
0x180035e4f  inc     edi
0x180035e51  mov     ecx, edi
0x180035e53  xor     r9d, r9d
0x180035e56  jmp     short loc_180035DE0
0x180035e58  inc     edi
0x180035e5a  jmp     short loc_180035DE0
0x180035e5c  mov     ebx, 80070057h
0x180035e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e68  lea     rax, WPP_GLOBAL_Control
0x180035e6f  cmp     rcx, rax
0x180035e72  jz      short loc_180035E92
0x180035e74  test    byte ptr [rcx+1Ch], 1
0x180035e78  jz      short loc_180035E92
0x180035e7a  mov     edx, 14h
0x180035e7f  mov     r9d, ebx
0x180035e82  mov     rcx, [rcx+10h]
0x180035e86  lea     r8, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids
0x180035e8d  call    WPP_SF_d
0x180035e92  mov     edi, [rbp+var_20]
0x180035e95  mov     esi, 80004001h
0x180035e9a  mov     rcx, r12
0x180035e9d  call    cs:__imp_FwFree
0x180035ea3  test    ebx, ebx
0x180035ea5  jns     short loc_180035EB0
0x180035ea7  mov     rcx, r14
0x180035eaa  call    cs:__imp_FwFreeCertCriteria
0x180035eb0  test    edi, edi
0x180035eb2  cmovnz  ebx, esi
0x180035eb5  mov     eax, ebx
0x180035eb7  mov     rcx, [rbp+var_8]
0x180035ebb  xor     rcx, rsp; StackCookie
0x180035ebe  call    __security_check_cookie
0x180035ec3  mov     rbx, [rsp+50h+arg_10]
0x180035ecb  add     rsp, 50h
0x180035ecf  pop     r15
0x180035ed1  pop     r14
0x180035ed3  pop     r13
0x180035ed5  pop     r12
0x180035ed7  pop     rdi
0x180035ed8  pop     rsi
0x180035ed9  pop     rbp
0x180035eda  retn
0x180035edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ee2  lea     rax, WPP_GLOBAL_Control
0x180035ee9  cmp     rcx, rax
0x180035eec  jz      short loc_180035E92
0x180035eee  test    byte ptr [rcx+1Ch], 1
0x180035ef2  jz      short loc_180035E92
0x180035ef4  mov     edx, 15h
0x180035ef9  jmp     short loc_180035E82
0x180035efb  mov     r9d, 8000FFFFh
0x180035f01  mov     ebx, r9d
0x180035f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f0b  lea     rax, WPP_GLOBAL_Control
0x180035f12  cmp     rcx, rax
0x180035f15  jz      loc_180035E92
0x180035f1b  test    byte ptr [rcx+1Ch], 1
0x180035f1f  jz      loc_180035E92
0x180035f25  mov     edx, 13h
0x180035f2a  jmp     loc_180035E82
0x180035f2f  mov     [r13+10h], r14
0x180035f33  cmp     edi, ecx
0x180035f35  jz      loc_180035E92
0x180035f3b  mov     r9d, 8000FFFFh
0x180035f41  mov     ebx, r9d
0x180035f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f4b  lea     rax, WPP_GLOBAL_Control
0x180035f52  cmp     rcx, rax
0x180035f55  jz      loc_180035E92
0x180035f5b  test    byte ptr [rcx+1Ch], 1
0x180035f5f  jz      loc_180035E92
0x180035f65  mov     edx, 16h
0x180035f6a  jmp     loc_180035E82
```
