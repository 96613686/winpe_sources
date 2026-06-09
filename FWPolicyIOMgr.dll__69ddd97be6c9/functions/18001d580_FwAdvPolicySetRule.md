# FwAdvPolicySetRule

- ea: `0x18001d580`
- end: `0x18001d84f`
- name: `FwAdvPolicySetRule`
- size: `719`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE_MANIPULATOR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x180004874`
- `0x180005454`
- `0x18001d580`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `fwbase!FwFree` at `0x18001d826`
- `fwbase!FwFree` at `0x18001d826`
- `fwbase!FwRegOpenKey` at `0x18001d5e8`
- `fwbase!FwRegOpenKey` at `0x18001d5e8`
- `fwbase!FwRegCloseKey` at `0x18001d830`
- `fwbase!FwRegCloseKey` at `0x18001d830`
- `fwbase!FwRegSetString` at `0x18001d7a6`
- `fwbase!FwRegSetString` at `0x18001d7a6`

## pseudocode

```c
__int64 __fastcall FwAdvPolicySetRule(__int64 (__fastcall **a1)(__int64), __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  int AdvPolicyRule; // eax
  unsigned int v8; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  _QWORD *v12; // rax
  __int64 v13; // rbx
  _QWORD *v14; // rax
  __int64 *v15; // rax
  unsigned int v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+50h] [rbp-10h] BYREF

  v19 = 0;
  v20 = 0;
  v17 = 0;
  v21 = 0;
  v6 = *(_QWORD *)(a2 + 40);
  v18 = 0;
  AdvPolicyRule = FwRegOpenKey(v6, a3, 15, &v19, &v21);
  v8 = AdvPolicyRule;
  if ( AdvPolicyRule < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 75;
LABEL_36:
      v11 = (unsigned int)AdvPolicyRule;
      goto LABEL_37;
    }
    goto LABEL_38;
  }
  if ( !v21 )
  {
    v11 = 2147942402LL;
    v8 = -2147024894;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_38;
    v10 = 76;
    goto LABEL_37;
  }
  v12 = (_QWORD *)a1[4](a4);
  AdvPolicyRule = FwAdvPolicyLookForRuleID(v19, *v12, &v17);
  v8 = AdvPolicyRule;
  if ( AdvPolicyRule >= 0 )
  {
    if ( v17 <= 1 )
    {
      if ( v17 )
      {
        AdvPolicyRule = ((__int64 (__fastcall *)(__int64, __int64 *))a1[8])(a4, &v20);
        v8 = AdvPolicyRule;
        if ( AdvPolicyRule >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v20);
          v13 = v20;
          v14 = (_QWORD *)a1[4](a4);
          AdvPolicyRule = FwRegSetString(v19, 0, *v14, v13);
          v8 = AdvPolicyRule;
          if ( AdvPolicyRule >= 0 )
          {
            v15 = (__int64 *)a1[4](a4);
            AdvPolicyRule = FwGetAdvPolicyRule(
                              (struct _tag_FW_RULE_MANIPULATOR *)a1,
                              v19,
                              0,
                              *v15,
                              (struct _tag_FW_BLOB_RULE **)&v18);
            v8 = AdvPolicyRule;
            if ( AdvPolicyRule < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v10 = 83;
                goto LABEL_36;
              }
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v10 = 82;
              goto LABEL_36;
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 80;
            goto LABEL_36;
          }
        }
        goto LABEL_38;
      }
      v11 = 2147942402LL;
      v8 = -2147024894;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_38;
      v10 = 79;
    }
    else
    {
      v8 = -2147418113;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_38;
      v10 = 78;
      v11 = 2147549183LL;
    }
LABEL_37:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v11);
    goto LABEL_38;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v10 = 77;
    goto LABEL_36;
  }
LABEL_38:
  FwFree(v20);
  FwRegCloseKey(v19);
  return v8;
}

```

## disassembly

```asm
0x18001d580  push    rbp
0x18001d582  push    rbx
0x18001d583  push    rsi
0x18001d584  push    rdi
0x18001d585  push    r14
0x18001d587  mov     rbp, rsp
0x18001d58a  sub     rsp, 60h
0x18001d58e  mov     rax, cs:__security_cookie
0x18001d595  xor     rax, rsp
0x18001d598  mov     [rbp+var_8], rax
0x18001d59c  mov     rax, rdx
0x18001d59f  mov     [rbp+var_20], 0
0x18001d5a7  mov     rsi, rcx
0x18001d5aa  mov     [rbp+var_18], 0
0x18001d5b2  mov     r10, r8
0x18001d5b5  mov     [rbp+var_30], 0
0x18001d5bc  lea     rcx, [rbp+var_10]
0x18001d5c0  mov     [rbp+var_10], 0
0x18001d5c7  mov     r14, r9
0x18001d5ca  mov     [rsp+60h+var_40], rcx
0x18001d5cf  mov     rcx, [rax+28h]
0x18001d5d3  lea     r9, [rbp+var_20]
0x18001d5d7  mov     r8d, 0Fh
0x18001d5dd  mov     [rbp+var_28], 0
0x18001d5e5  mov     rdx, r10
0x18001d5e8  call    cs:__imp_FwRegOpenKey
0x18001d5ee  mov     ebx, eax
0x18001d5f0  test    eax, eax
0x18001d5f2  jns     short loc_18001D61F
0x18001d5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5fb  lea     rdi, WPP_GLOBAL_Control
0x18001d602  cmp     rcx, rdi
0x18001d605  jz      loc_18001D822
0x18001d60b  test    byte ptr [rcx+1Ch], 1
0x18001d60f  jz      loc_18001D822
0x18001d615  mov     edx, 4Bh ; 'K'
0x18001d61a  jmp     loc_18001D80F
0x18001d61f  cmp     [rbp+var_10], 0
0x18001d623  jnz     short loc_18001D659
0x18001d625  mov     r9d, 80070002h
0x18001d62b  mov     ebx, r9d
0x18001d62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d635  lea     rdi, WPP_GLOBAL_Control
0x18001d63c  cmp     rcx, rdi
0x18001d63f  jz      loc_18001D822
0x18001d645  test    byte ptr [rcx+1Ch], 1
0x18001d649  jz      loc_18001D822
0x18001d64f  mov     edx, 4Ch ; 'L'
0x18001d654  jmp     loc_18001D812
0x18001d659  mov     rax, [rsi+20h]
0x18001d65d  mov     rcx, r14
0x18001d660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d665  mov     rcx, [rbp+var_20]
0x18001d669  lea     r8, [rbp+var_30]
0x18001d66d  mov     rdx, [rax]
0x18001d670  call    FwAdvPolicyLookForRuleID
0x18001d675  mov     ebx, eax
0x18001d677  test    eax, eax
0x18001d679  jns     short loc_18001D6A6
0x18001d67b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d682  lea     rdi, WPP_GLOBAL_Control
0x18001d689  cmp     rcx, rdi
0x18001d68c  jz      loc_18001D822
0x18001d692  test    byte ptr [rcx+1Ch], 1
0x18001d696  jz      loc_18001D822
0x18001d69c  mov     edx, 4Dh ; 'M'
0x18001d6a1  jmp     loc_18001D80F
0x18001d6a6  mov     eax, [rbp+var_30]
0x18001d6a9  cmp     eax, 1
0x18001d6ac  jbe     short loc_18001D6E1
0x18001d6ae  mov     ebx, 8000FFFFh
0x18001d6b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6ba  lea     rdi, WPP_GLOBAL_Control
0x18001d6c1  cmp     rcx, rdi
0x18001d6c4  jz      loc_18001D822
0x18001d6ca  test    byte ptr [rcx+1Ch], 1
0x18001d6ce  jz      loc_18001D822
0x18001d6d4  mov     edx, 4Eh ; 'N'
0x18001d6d9  mov     r9d, ebx
0x18001d6dc  jmp     loc_18001D812
0x18001d6e1  test    eax, eax
0x18001d6e3  jnz     short loc_18001D717
0x18001d6e5  mov     r9d, 80070002h
0x18001d6eb  mov     ebx, r9d
0x18001d6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6f5  lea     rdi, WPP_GLOBAL_Control
0x18001d6fc  cmp     rcx, rdi
0x18001d6ff  jz      loc_18001D822
0x18001d705  test    byte ptr [rcx+1Ch], 1
0x18001d709  jz      loc_18001D822
0x18001d70f  lea     edx, [rax+4Fh]
0x18001d712  jmp     loc_18001D812
0x18001d717  mov     rax, [rsi+40h]
0x18001d71b  lea     rdx, [rbp+var_18]
0x18001d71f  mov     rcx, r14
0x18001d722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d727  mov     ebx, eax
0x18001d729  test    eax, eax
0x18001d72b  jns     short loc_18001D758
0x18001d72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d734  lea     rdi, WPP_GLOBAL_Control
0x18001d73b  cmp     rcx, rdi
0x18001d73e  jz      loc_18001D822
0x18001d744  test    byte ptr [rcx+1Ch], 1
0x18001d748  jz      loc_18001D822
0x18001d74e  mov     edx, 50h ; 'P'
0x18001d753  jmp     loc_18001D80F
0x18001d758  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d75f  lea     rdi, WPP_GLOBAL_Control
0x18001d766  cmp     rcx, rdi
0x18001d769  jz      short loc_18001D78A
0x18001d76b  test    byte ptr [rcx+1Ch], 4
0x18001d76f  jz      short loc_18001D78A
0x18001d771  mov     r9, [rbp+var_18]
0x18001d775  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d77c  mov     rcx, [rcx+10h]
0x18001d780  mov     edx, 51h ; 'Q'
0x18001d785  call    WPP_SF_S
0x18001d78a  mov     rax, [rsi+20h]
0x18001d78e  mov     rcx, r14
0x18001d791  mov     rbx, [rbp+var_18]
0x18001d795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d79a  mov     rcx, [rbp+var_20]
0x18001d79e  mov     r9, rbx
0x18001d7a1  xor     edx, edx
0x18001d7a3  mov     r8, [rax]
0x18001d7a6  call    cs:__imp_FwRegSetString
0x18001d7ac  mov     ebx, eax
0x18001d7ae  test    eax, eax
0x18001d7b0  jns     short loc_18001D7CB
0x18001d7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7b9  cmp     rcx, rdi
0x18001d7bc  jz      short loc_18001D822
0x18001d7be  test    byte ptr [rcx+1Ch], 1
0x18001d7c2  jz      short loc_18001D822
0x18001d7c4  mov     edx, 52h ; 'R'
0x18001d7c9  jmp     short loc_18001D80F
0x18001d7cb  mov     rax, [rsi+20h]
0x18001d7cf  mov     rcx, r14
0x18001d7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d7  mov     rdx, [rbp+var_20]
0x18001d7db  lea     rcx, [rbp+var_28]
0x18001d7df  mov     [rsp+60h+var_40], rcx; __int64
0x18001d7e4  xor     r8d, r8d
0x18001d7e7  mov     rcx, rsi; struct _tag_FW_RULE_MANIPULATOR *
0x18001d7ea  mov     r9, [rax]
0x18001d7ed  call    FwGetAdvPolicyRule
0x18001d7f2  mov     ebx, eax
0x18001d7f4  test    eax, eax
0x18001d7f6  jns     short loc_18001D822
0x18001d7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7ff  cmp     rcx, rdi
0x18001d802  jz      short loc_18001D822
0x18001d804  test    byte ptr [rcx+1Ch], 1
0x18001d808  jz      short loc_18001D822
0x18001d80a  mov     edx, 53h ; 'S'
0x18001d80f  mov     r9d, eax
0x18001d812  mov     rcx, [rcx+10h]
0x18001d816  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d81d  call    WPP_SF_d
0x18001d822  mov     rcx, [rbp+var_18]
0x18001d826  call    cs:__imp_FwFree
0x18001d82c  mov     rcx, [rbp+var_20]
0x18001d830  call    cs:__imp_FwRegCloseKey
0x18001d836  mov     eax, ebx
0x18001d838  mov     rcx, [rbp+var_8]
0x18001d83c  xor     rcx, rsp; StackCookie
0x18001d83f  call    __security_check_cookie
0x18001d844  add     rsp, 60h
0x18001d848  pop     r14
0x18001d84a  pop     rdi
0x18001d84b  pop     rsi
0x18001d84c  pop     rbx
0x18001d84d  pop     rbp
0x18001d84e  retn
```
