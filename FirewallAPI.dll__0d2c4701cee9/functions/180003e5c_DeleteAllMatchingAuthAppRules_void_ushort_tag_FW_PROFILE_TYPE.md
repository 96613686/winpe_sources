# DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)

- ea: `0x180003e5c`
- end: `0x18000407d`
- name: `?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000283c`
- `0x180003d20`

## callees

- `0x180003e5c`
- `0x180005630`
- `0x180005e0c`
- `0x180009780`
- `0x18000c3f0`
- `0x180014720`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003f5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003f5a`
- `fwbase!FwBaseFree` at `0x180003f05`
- `fwbase!FwBaseFree` at `0x180003f05`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003f3d`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003f3d`
- `fwbase!IsRuleOldAuthApp` at `0x180003f1e`
- `fwbase!IsRuleOldAuthApp` at `0x180003f1e`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180003ef1`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180003ef1`

## pseudocode

```c
__int64 __fastcall DeleteAllMatchingAuthAppRules(__int64 a1, __int64 a2, int a3)
{
  int v6; // eax
  signed int v7; // ebx
  _QWORD *i; // rdi
  BOOL v9; // r14d
  bool v10; // zf
  int v11; // eax
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  void *Src; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+44h] [rbp-Ch] BYREF

  Src = 0;
  v19 = 0;
  v6 = FWEnumFirewallRules(a1, 196608, a3, 0, (__int64)&v19, (__int64)&Src);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 10;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, (unsigned int)v7);
    }
  }
  else
  {
    for ( i = Src; i; i = (_QWORD *)*i )
    {
      v16 = 0;
      v18 = 0;
      v9 = 0;
      if ( (unsigned int)IsRuleOpenPortOrAuthApp(i)
        && (unsigned int)IsRuleOldAuthApp(i)
        && (int)FwGetExpandedCanonicalLongPathName(i[34], &v16, &v18) >= 0
        && v18 )
      {
        v9 = _o__wcsicmp(a2, v16) == 0;
      }
      FwBaseFree(v16);
      if ( v9 )
      {
        v10 = (~a3 & (_DWORD)i[5]) == 0;
        *((_DWORD *)i + 10) &= ~a3;
        if ( v10 )
        {
          v11 = FWDeleteFirewallRule(a1, i[2]);
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          if ( v7 < 0 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 12;
              goto LABEL_26;
            }
            break;
          }
        }
        else
        {
          v14 = FWSetFirewallRule(a1, i);
          v7 = v14;
          if ( v14 > 0 )
            v7 = (unsigned __int16)v14 | 0x80070000;
          if ( v7 < 0 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 11;
              goto LABEL_26;
            }
            break;
          }
        }
      }
    }
  }
  FWFreeFirewallRules(Src);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003e5c  mov     [rsp-38h+arg_18], rbx
0x180003e61  push    rbp
0x180003e62  push    rsi
0x180003e63  push    rdi
0x180003e64  push    r12
0x180003e66  push    r13
0x180003e68  push    r14
0x180003e6a  push    r15
0x180003e6c  mov     rbp, rsp
0x180003e6f  sub     rsp, 50h
0x180003e73  mov     rax, cs:__security_cookie
0x180003e7a  xor     rax, rsp
0x180003e7d  mov     [rbp+var_8], rax
0x180003e81  lea     rax, [rbp+Src]
0x180003e85  mov     [rbp+Src], 0
0x180003e8d  mov     [rsp+50h+var_28], rax
0x180003e92  mov     r13, rdx
0x180003e95  lea     rax, [rbp+var_C]
0x180003e99  mov     [rbp+var_C], 0
0x180003ea0  xor     r9d, r9d
0x180003ea3  mov     [rsp+50h+var_30], rax
0x180003ea8  mov     edx, 30000h
0x180003ead  mov     r12d, r8d
0x180003eb0  mov     r15, rcx
0x180003eb3  call    FWEnumFirewallRules
0x180003eb8  mov     ebx, eax
0x180003eba  test    eax, eax
0x180003ebc  jg      loc_18000403B
0x180003ec2  test    ebx, ebx
0x180003ec4  js      loc_180004057
0x180003eca  mov     rdi, [rbp+Src]
0x180003ece  mov     esi, 1
0x180003ed3  test    rdi, rdi
0x180003ed6  jz      loc_180003FFD
0x180003edc  mov     rcx, rdi
0x180003edf  mov     [rbp+var_20], 0
0x180003ee7  mov     [rbp+var_10], 0
0x180003eee  xor     r14d, r14d
0x180003ef1  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180003ef8  nop     dword ptr [rax+rax+00h]
0x180003efd  test    eax, eax
0x180003eff  jnz     short loc_180003F1B
0x180003f01  mov     rcx, [rbp+var_20]
0x180003f05  call    cs:__imp_FwBaseFree
0x180003f0c  nop     dword ptr [rax+rax+00h]
0x180003f11  cmp     r14d, esi
0x180003f14  jz      short loc_180003F6E
0x180003f16  mov     rdi, [rdi]
0x180003f19  jmp     short loc_180003ED3
0x180003f1b  mov     rcx, rdi
0x180003f1e  call    cs:__imp_IsRuleOldAuthApp
0x180003f25  nop     dword ptr [rax+rax+00h]
0x180003f2a  test    eax, eax
0x180003f2c  jz      short loc_180003F01
0x180003f2e  mov     rcx, [rdi+110h]
0x180003f35  lea     r8, [rbp+var_10]
0x180003f39  lea     rdx, [rbp+var_20]
0x180003f3d  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180003f44  nop     dword ptr [rax+rax+00h]
0x180003f49  test    eax, eax
0x180003f4b  js      short loc_180003F01
0x180003f4d  cmp     [rbp+var_10], r14d
0x180003f51  jz      short loc_180003F01
0x180003f53  mov     rdx, [rbp+var_20]
0x180003f57  mov     rcx, r13
0x180003f5a  call    cs:__imp__o__wcsicmp
0x180003f61  nop     dword ptr [rax+rax+00h]
0x180003f66  test    eax, eax
0x180003f68  cmovz   r14d, esi
0x180003f6c  jmp     short loc_180003F01
0x180003f6e  mov     eax, r12d
0x180003f71  mov     rcx, r15; __int64
0x180003f74  not     eax
0x180003f76  and     [rdi+28h], eax
0x180003f79  jnz     short loc_180003FB2
0x180003f7b  mov     rdx, [rdi+10h]
0x180003f7f  call    FWDeleteFirewallRule
0x180003f84  mov     ebx, eax
0x180003f86  test    eax, eax
0x180003f88  jg      loc_18000402D
0x180003f8e  test    ebx, ebx
0x180003f90  jns     short loc_180003F16
0x180003f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f99  lea     rax, WPP_GLOBAL_Control
0x180003fa0  cmp     rcx, rax
0x180003fa3  jz      short loc_180003FFD
0x180003fa5  test    [rcx+1Ch], sil
0x180003fa9  jz      short loc_180003FFD
0x180003fab  mov     edx, 0Ch
0x180003fb0  jmp     short loc_180003FEA
0x180003fb2  mov     rdx, rdi; Src
0x180003fb5  call    FWSetFirewallRule
0x180003fba  mov     ebx, eax
0x180003fbc  test    eax, eax
0x180003fbe  jg      loc_180004049
0x180003fc4  test    ebx, ebx
0x180003fc6  jns     loc_180003F16
0x180003fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd3  lea     rax, WPP_GLOBAL_Control
0x180003fda  cmp     rcx, rax
0x180003fdd  jz      short loc_180003FFD
0x180003fdf  test    [rcx+1Ch], sil
0x180003fe3  jz      short loc_180003FFD
0x180003fe5  mov     edx, 0Bh
0x180003fea  mov     rcx, [rcx+10h]
0x180003fee  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x180003ff5  mov     r9d, ebx
0x180003ff8  call    WPP_SF_d
0x180003ffd  mov     rcx, [rbp+Src]
0x180004001  call    FWFreeFirewallRules
0x180004006  mov     eax, ebx
0x180004008  mov     rcx, [rbp+var_8]
0x18000400c  xor     rcx, rsp; StackCookie
0x18000400f  call    __security_check_cookie
0x180004014  mov     rbx, [rsp+50h+arg_18]
0x18000401c  add     rsp, 50h
0x180004020  pop     r15
0x180004022  pop     r14
0x180004024  pop     r13
0x180004026  pop     r12
0x180004028  pop     rdi
0x180004029  pop     rsi
0x18000402a  pop     rbp
0x18000402b  retn
0x18000402d  movzx   ebx, ax
0x180004030  or      ebx, 80070000h
0x180004036  jmp     loc_180003F8E
0x18000403b  movzx   ebx, ax
0x18000403e  or      ebx, 80070000h
0x180004044  jmp     loc_180003EC2
0x180004049  movzx   ebx, ax
0x18000404c  or      ebx, 80070000h
0x180004052  jmp     loc_180003FC4
0x180004057  mov     rcx, cs:WPP_GLOBAL_Control
0x18000405e  lea     rax, WPP_GLOBAL_Control
0x180004065  cmp     rcx, rax
0x180004068  jz      short loc_180003FFD
0x18000406a  mov     esi, 1
0x18000406f  test    [rcx+1Ch], sil
0x180004073  jz      short loc_180003FFD
0x180004075  lea     edx, [rsi+9]
0x180004078  jmp     loc_180003FEA
```
