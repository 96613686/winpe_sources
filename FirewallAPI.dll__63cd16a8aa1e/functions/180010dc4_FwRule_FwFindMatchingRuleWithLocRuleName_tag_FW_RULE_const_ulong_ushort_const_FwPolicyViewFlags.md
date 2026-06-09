# FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)

- ea: `0x180010dc4`
- end: `0x180010f65`
- name: `?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003f80`
- `0x180004300`

## callees

- `0x180010dc4`
- `0x180010f70`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010e7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010e7e`
- `fwbase!FwBaseFree` at `0x180010e93`
- `fwbase!FwBaseFree` at `0x180010edf`
- `fwbase!FwBaseFree` at `0x180010ee9`
- `fwbase!FwBaseFree` at `0x180010e93`
- `fwbase!FwBaseFree` at `0x180010edf`
- `fwbase!FwBaseFree` at `0x180010ee9`
- `fwbase!FwLoadIndirectString` at `0x180010e29`
- `fwbase!FwLoadIndirectString` at `0x180010e6c`
- `fwbase!FwLoadIndirectString` at `0x180010e29`
- `fwbase!FwLoadIndirectString` at `0x180010e6c`
- `fwbase!FwReportReturnError` at `0x180010ec5`
- `fwbase!FwReportReturnError` at `0x180010ed5`
- `fwbase!FwReportReturnError` at `0x180010f37`
- `fwbase!FwReportReturnError` at `0x180010ec5`
- `fwbase!FwReportReturnError` at `0x180010ed5`
- `fwbase!FwReportReturnError` at `0x180010f37`
- `fwbase!FwStringCopy` at `0x180010eaf`
- `fwbase!FwStringCopy` at `0x180010f1e`
- `fwbase!FwStringCopy` at `0x180010eaf`
- `fwbase!FwStringCopy` at `0x180010f1e`

## pseudocode

```c
_QWORD *__fastcall FwRule::FwFindMatchingRuleWithLocRuleName(_QWORD *a1, unsigned int a2, _WORD *a3, unsigned int a4)
{
  _QWORD *v8; // rdi
  bool v9; // zf
  unsigned int i; // esi
  _WORD *v11; // r14
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rdx
  int v16; // eax
  unsigned int v17; // esi
  __int64 v18; // [rsp+20h] [rbp-20h] BYREF
  __int64 v19; // [rsp+28h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v8 = 0;
  v9 = *a3 == 64;
  v19 = 0;
  v18 = 0;
  if ( v9 && (int)FwLoadIndirectString(a3, &v19) >= 0 || (v16 = FwStringCopy(a3, &v19), v17 = v16, v16 >= 0) )
  {
    for ( i = 0; i < a2 && !v8; ++i )
    {
      if ( (unsigned int)FwRule::FwIsValidRule(a1, a4) )
      {
        v11 = (_WORD *)a1[3];
        if ( *v11 != 64 || (int)FwLoadIndirectString(a1[3], &v18) < 0 )
        {
          v12 = FwStringCopy(v11, &v18);
          v13 = v12;
          if ( v12 < 0 )
          {
            FwReportReturnError("FwTryResolveString", (unsigned int)v12);
            v14 = v13;
            goto LABEL_16;
          }
        }
        v8 = a1;
        if ( (unsigned int)_o__wcsicmp(v19, v18) )
          v8 = 0;
        FwBaseFree(v18);
        v18 = 0;
      }
      a1 = (_QWORD *)*a1;
    }
  }
  else
  {
    FwReportReturnError("FwTryResolveString", (unsigned int)v16);
    v14 = v17;
LABEL_16:
    FwReportReturnError("FwRule::FwFindMatchingRuleWithLocRuleName", v14);
  }
  FwBaseFree(v19);
  FwBaseFree(v18);
  return v8;
}

```

## disassembly

```asm
0x180010dc4  mov     [rsp-28h+arg_8], rbx
0x180010dc9  mov     [rsp-28h+arg_18], rsi
0x180010dce  push    rbp
0x180010dcf  push    rdi
0x180010dd0  push    r12
0x180010dd2  push    r14
0x180010dd4  push    r15
0x180010dd6  mov     rbp, rsp
0x180010dd9  sub     rsp, 40h
0x180010ddd  mov     rax, cs:__security_cookie
0x180010de4  xor     rax, rsp
0x180010de7  mov     [rbp+var_10], rax
0x180010deb  mov     r12d, r9d
0x180010dee  mov     rsi, r8
0x180010df1  mov     r15d, edx
0x180010df4  mov     rbx, rcx
0x180010df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dfe  lea     rax, WPP_GLOBAL_Control
0x180010e05  cmp     rcx, rax
0x180010e08  jnz     loc_180010F41
0x180010e0e  xor     edi, edi
0x180010e10  cmp     word ptr [rsi], 40h ; '@'
0x180010e14  mov     [rbp+var_18], rdi
0x180010e18  mov     [rbp+var_20], rdi
0x180010e1c  jnz     loc_180010F17
0x180010e22  lea     rdx, [rbp+var_18]
0x180010e26  mov     rcx, rsi
0x180010e29  call    cs:__imp_FwLoadIndirectString
0x180010e2f  test    eax, eax
0x180010e31  js      loc_180010F17
0x180010e37  xor     esi, esi
0x180010e39  cmp     esi, r15d
0x180010e3c  jnb     loc_180010EDB
0x180010e42  test    rdi, rdi
0x180010e45  jnz     loc_180010EDB
0x180010e4b  mov     edx, r12d
0x180010e4e  mov     rcx, rbx
0x180010e51  call    ?FwIsValidRule@FwRule@@SAHQEAU_tag_FW_RULE@@W4FwPolicyViewFlags@@@Z; FwRule::FwIsValidRule(_tag_FW_RULE * const,FwPolicyViewFlags)
0x180010e56  test    eax, eax
0x180010e58  jz      short loc_180010EA1
0x180010e5a  mov     r14, [rbx+18h]
0x180010e5e  cmp     word ptr [r14], 40h ; '@'
0x180010e63  jnz     short loc_180010EA8
0x180010e65  lea     rdx, [rbp+var_20]
0x180010e69  mov     rcx, r14
0x180010e6c  call    cs:__imp_FwLoadIndirectString
0x180010e72  test    eax, eax
0x180010e74  js      short loc_180010EA8
0x180010e76  mov     rdx, [rbp+var_20]
0x180010e7a  mov     rcx, [rbp+var_18]
0x180010e7e  call    cs:__imp__o__wcsicmp
0x180010e84  xor     ecx, ecx
0x180010e86  mov     rdi, rbx
0x180010e89  test    eax, eax
0x180010e8b  cmovnz  rdi, rcx
0x180010e8f  mov     rcx, [rbp+var_20]
0x180010e93  call    cs:__imp_FwBaseFree
0x180010e99  mov     [rbp+var_20], 0
0x180010ea1  mov     rbx, [rbx]
0x180010ea4  inc     esi
0x180010ea6  jmp     short loc_180010E39
0x180010ea8  lea     rdx, [rbp+var_20]
0x180010eac  mov     rcx, r14
0x180010eaf  call    cs:__imp_FwStringCopy
0x180010eb5  mov     r14d, eax
0x180010eb8  test    eax, eax
0x180010eba  jns     short loc_180010E76
0x180010ebc  mov     edx, eax
0x180010ebe  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x180010ec5  call    cs:__imp_FwReportReturnError
0x180010ecb  mov     edx, r14d
0x180010ece  lea     rcx, aFwruleFwfindma; "FwRule::FwFindMatchingRuleWithLocRuleNa"...
0x180010ed5  call    cs:__imp_FwReportReturnError
0x180010edb  mov     rcx, [rbp+var_18]
0x180010edf  call    cs:__imp_FwBaseFree
0x180010ee5  mov     rcx, [rbp+var_20]
0x180010ee9  call    cs:__imp_FwBaseFree
0x180010eef  mov     rax, rdi
0x180010ef2  mov     rcx, [rbp+var_10]
0x180010ef6  xor     rcx, rsp; StackCookie
0x180010ef9  call    __security_check_cookie
0x180010efe  lea     r11, [rsp+40h+var_s0]
0x180010f03  mov     rbx, [r11+38h]
0x180010f07  mov     rsi, [r11+48h]
0x180010f0b  mov     rsp, r11
0x180010f0e  pop     r15
0x180010f10  pop     r14
0x180010f12  pop     r12
0x180010f14  pop     rdi
0x180010f15  pop     rbp
0x180010f16  retn
0x180010f17  lea     rdx, [rbp+var_18]
0x180010f1b  mov     rcx, rsi
0x180010f1e  call    cs:__imp_FwStringCopy
0x180010f24  mov     esi, eax
0x180010f26  test    eax, eax
0x180010f28  jns     loc_180010E37
0x180010f2e  mov     edx, eax
0x180010f30  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x180010f37  call    cs:__imp_FwReportReturnError
0x180010f3d  mov     edx, esi
0x180010f3f  jmp     short loc_180010ECE
0x180010f41  test    byte ptr [rcx+1Ch], 8
0x180010f45  jz      loc_180010E0E
0x180010f4b  mov     rcx, [rcx+10h]
0x180010f4f  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180010f56  mov     edx, 62h ; 'b'
0x180010f5b  call    WPP_SF_
0x180010f60  jmp     loc_180010E0E
```
