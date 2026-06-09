# DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)

- ea: `0x180003b4c`
- end: `0x180003d4e`
- name: `?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `514`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000270c`
- `0x180003a30`

## callees

- `0x180003b4c`
- `0x1800051c0`
- `0x180005954`
- `0x180009080`
- `0x18000b8c0`
- `0x180014690`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003c32`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003c32`
- `fwbase!FwBaseFree` at `0x180003bef`
- `fwbase!FwBaseFree` at `0x180003bef`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003c1b`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003c1b`
- `fwbase!IsRuleOldAuthApp` at `0x180003c02`
- `fwbase!IsRuleOldAuthApp` at `0x180003c02`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180003be1`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180003be1`

## pseudocode

```c
__int64 __fastcall DeleteAllMatchingAuthAppRules(unsigned __int16 *a1, __int64 a2, int a3)
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
  v6 = FWEnumFirewallRules((_DWORD)a1, 196608, a3, 0, (__int64)&v19, (__int64)&Src);
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
0x180003b4c  mov     [rsp-38h+arg_18], rbx
0x180003b51  push    rbp
0x180003b52  push    rsi
0x180003b53  push    rdi
0x180003b54  push    r12
0x180003b56  push    r13
0x180003b58  push    r14
0x180003b5a  push    r15
0x180003b5c  mov     rbp, rsp
0x180003b5f  sub     rsp, 50h
0x180003b63  mov     rax, cs:__security_cookie
0x180003b6a  xor     rax, rsp
0x180003b6d  mov     [rbp+var_8], rax
0x180003b71  lea     rax, [rbp+Src]
0x180003b75  mov     [rbp+Src], 0
0x180003b7d  mov     [rsp+50h+var_28], rax
0x180003b82  mov     r13, rdx
0x180003b85  lea     rax, [rbp+var_C]
0x180003b89  mov     [rbp+var_C], 0
0x180003b90  xor     r9d, r9d
0x180003b93  mov     [rsp+50h+var_30], rax
0x180003b98  mov     edx, 30000h
0x180003b9d  mov     r12d, r8d
0x180003ba0  mov     r15, rcx
0x180003ba3  call    FWEnumFirewallRules
0x180003ba8  mov     ebx, eax
0x180003baa  test    eax, eax
0x180003bac  jg      loc_180003D0C
0x180003bb2  test    ebx, ebx
0x180003bb4  js      loc_180003D28
0x180003bba  mov     rdi, [rbp+Src]
0x180003bbe  mov     esi, 1
0x180003bc3  test    rdi, rdi
0x180003bc6  jz      loc_180003CCF
0x180003bcc  mov     rcx, rdi
0x180003bcf  mov     [rbp+var_20], 0
0x180003bd7  mov     [rbp+var_10], 0
0x180003bde  xor     r14d, r14d
0x180003be1  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180003be7  test    eax, eax
0x180003be9  jnz     short loc_180003BFF
0x180003beb  mov     rcx, [rbp+var_20]
0x180003bef  call    cs:__imp_FwBaseFree
0x180003bf5  cmp     r14d, esi
0x180003bf8  jz      short loc_180003C40
0x180003bfa  mov     rdi, [rdi]
0x180003bfd  jmp     short loc_180003BC3
0x180003bff  mov     rcx, rdi
0x180003c02  call    cs:__imp_IsRuleOldAuthApp
0x180003c08  test    eax, eax
0x180003c0a  jz      short loc_180003BEB
0x180003c0c  mov     rcx, [rdi+110h]
0x180003c13  lea     r8, [rbp+var_10]
0x180003c17  lea     rdx, [rbp+var_20]
0x180003c1b  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180003c21  test    eax, eax
0x180003c23  js      short loc_180003BEB
0x180003c25  cmp     [rbp+var_10], r14d
0x180003c29  jz      short loc_180003BEB
0x180003c2b  mov     rdx, [rbp+var_20]
0x180003c2f  mov     rcx, r13
0x180003c32  call    cs:__imp__o__wcsicmp
0x180003c38  test    eax, eax
0x180003c3a  cmovz   r14d, esi
0x180003c3e  jmp     short loc_180003BEB
0x180003c40  mov     eax, r12d
0x180003c43  mov     rcx, r15; __int64
0x180003c46  not     eax
0x180003c48  and     [rdi+28h], eax
0x180003c4b  jnz     short loc_180003C84
0x180003c4d  mov     rdx, [rdi+10h]
0x180003c51  call    FWDeleteFirewallRule
0x180003c56  mov     ebx, eax
0x180003c58  test    eax, eax
0x180003c5a  jg      loc_180003CFE
0x180003c60  test    ebx, ebx
0x180003c62  jns     short loc_180003BFA
0x180003c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c6b  lea     rax, WPP_GLOBAL_Control
0x180003c72  cmp     rcx, rax
0x180003c75  jz      short loc_180003CCF
0x180003c77  test    [rcx+1Ch], sil
0x180003c7b  jz      short loc_180003CCF
0x180003c7d  mov     edx, 0Ch
0x180003c82  jmp     short loc_180003CBC
0x180003c84  mov     rdx, rdi; Src
0x180003c87  call    FWSetFirewallRule
0x180003c8c  mov     ebx, eax
0x180003c8e  test    eax, eax
0x180003c90  jg      loc_180003D1A
0x180003c96  test    ebx, ebx
0x180003c98  jns     loc_180003BFA
0x180003c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ca5  lea     rax, WPP_GLOBAL_Control
0x180003cac  cmp     rcx, rax
0x180003caf  jz      short loc_180003CCF
0x180003cb1  test    [rcx+1Ch], sil
0x180003cb5  jz      short loc_180003CCF
0x180003cb7  mov     edx, 0Bh
0x180003cbc  mov     rcx, [rcx+10h]
0x180003cc0  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x180003cc7  mov     r9d, ebx
0x180003cca  call    WPP_SF_d
0x180003ccf  mov     rcx, [rbp+Src]
0x180003cd3  call    FWFreeFirewallRules
0x180003cd8  mov     eax, ebx
0x180003cda  mov     rcx, [rbp+var_8]
0x180003cde  xor     rcx, rsp; StackCookie
0x180003ce1  call    __security_check_cookie
0x180003ce6  mov     rbx, [rsp+50h+arg_18]
0x180003cee  add     rsp, 50h
0x180003cf2  pop     r15
0x180003cf4  pop     r14
0x180003cf6  pop     r13
0x180003cf8  pop     r12
0x180003cfa  pop     rdi
0x180003cfb  pop     rsi
0x180003cfc  pop     rbp
0x180003cfd  retn
0x180003cfe  movzx   ebx, ax
0x180003d01  or      ebx, 80070000h
0x180003d07  jmp     loc_180003C60
0x180003d0c  movzx   ebx, ax
0x180003d0f  or      ebx, 80070000h
0x180003d15  jmp     loc_180003BB2
0x180003d1a  movzx   ebx, ax
0x180003d1d  or      ebx, 80070000h
0x180003d23  jmp     loc_180003C96
0x180003d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d2f  lea     rax, WPP_GLOBAL_Control
0x180003d36  cmp     rcx, rax
0x180003d39  jz      short loc_180003CCF
0x180003d3b  mov     esi, 1
0x180003d40  test    [rcx+1Ch], sil
0x180003d44  jz      short loc_180003CCF
0x180003d46  lea     edx, [rsi+9]
0x180003d49  jmp     loc_180003CBC
```
