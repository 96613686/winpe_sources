# FwAdvPolicyAddRule

- ea: `0x18001d320`
- end: `0x18001d577`
- name: `FwAdvPolicyAddRule`
- size: `599`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE_MANIPULATOR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x180004874`
- `0x180005454`
- `0x18001d320`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `fwbase!FwFree` at `0x18001d544`
- `fwbase!FwFree` at `0x18001d54e`
- `fwbase!FwFree` at `0x18001d544`
- `fwbase!FwFree` at `0x18001d54e`
- `fwbase!FwRegCloseKey` at `0x18001d558`
- `fwbase!FwRegCloseKey` at `0x18001d558`
- `fwbase!FwRegCreateKey` at `0x18001d378`
- `fwbase!FwRegCreateKey` at `0x18001d378`
- `fwbase!FwRegSetString` at `0x18001d4c4`
- `fwbase!FwRegSetString` at `0x18001d4c4`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyAddRule(__int64 (__fastcall **a1)(__int64), __int64 a2, __int64 a3, __int64 a4)
{
  int AdvPolicyRule; // eax
  unsigned int v7; // ebx
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // r9
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 *v14; // rax
  int v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h] BYREF

  v18 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  AdvPolicyRule = FwRegCreateKey(*(_QWORD *)(a2 + 40), a3, 15, &v18);
  v7 = AdvPolicyRule;
  if ( AdvPolicyRule >= 0 )
  {
    v10 = (_QWORD *)a1[4](a4);
    AdvPolicyRule = FwAdvPolicyLookForRuleID(v18, *v10, &v16);
    v7 = AdvPolicyRule;
    if ( AdvPolicyRule >= 0 )
    {
      if ( v16 )
      {
        v7 = -2147418113;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v9 = 70;
          v11 = 2147549183LL;
LABEL_29:
          WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v11);
        }
      }
      else
      {
        AdvPolicyRule = ((__int64 (__fastcall *)(__int64, __int64 *))a1[8])(a4, &v19);
        v7 = AdvPolicyRule;
        if ( AdvPolicyRule >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v19);
          v12 = v19;
          v13 = (_QWORD *)a1[4](a4);
          AdvPolicyRule = FwRegSetString(v18, 0, *v13, v12);
          v7 = AdvPolicyRule;
          if ( AdvPolicyRule >= 0 )
          {
            v14 = (__int64 *)a1[4](a4);
            AdvPolicyRule = FwGetAdvPolicyRule(
                              (struct _tag_FW_RULE_MANIPULATOR *)a1,
                              v18,
                              0,
                              *v14,
                              (struct _tag_FW_BLOB_RULE **)&v17);
            v7 = AdvPolicyRule;
            if ( AdvPolicyRule < 0 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v9 = 74;
                goto LABEL_28;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v9 = 73;
              goto LABEL_28;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v9 = 71;
            goto LABEL_28;
          }
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 69;
        goto LABEL_28;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 68;
LABEL_28:
      v11 = (unsigned int)AdvPolicyRule;
      goto LABEL_29;
    }
  }
  FwFree(v17);
  FwFree(v19);
  FwRegCloseKey(v18);
  return v7;
}

```

## disassembly

```asm
0x18001d320  push    rbp
0x18001d322  push    rbx
0x18001d323  push    rsi
0x18001d324  push    rdi
0x18001d325  push    r14
0x18001d327  mov     rbp, rsp
0x18001d32a  sub     rsp, 60h
0x18001d32e  mov     rax, cs:__security_cookie
0x18001d335  xor     rax, rsp
0x18001d338  mov     [rbp+var_10], rax
0x18001d33c  mov     rax, rdx
0x18001d33f  mov     [rbp+var_20], 0
0x18001d347  mov     r10, r8
0x18001d34a  mov     [rbp+var_18], 0
0x18001d352  mov     r14, r9
0x18001d355  mov     [rbp+var_30], 0
0x18001d35c  mov     rsi, rcx
0x18001d35f  mov     [rbp+var_28], 0
0x18001d367  mov     rcx, [rax+28h]
0x18001d36b  lea     r9, [rbp+var_20]
0x18001d36f  mov     r8d, 0Fh
0x18001d375  mov     rdx, r10
0x18001d378  call    cs:__imp_FwRegCreateKey
0x18001d37e  mov     ebx, eax
0x18001d380  test    eax, eax
0x18001d382  jns     short loc_18001D3AF
0x18001d384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d38b  lea     rdi, WPP_GLOBAL_Control
0x18001d392  cmp     rcx, rdi
0x18001d395  jz      loc_18001D540
0x18001d39b  test    byte ptr [rcx+1Ch], 1
0x18001d39f  jz      loc_18001D540
0x18001d3a5  mov     edx, 44h ; 'D'
0x18001d3aa  jmp     loc_18001D52D
0x18001d3af  mov     rax, [rsi+20h]
0x18001d3b3  mov     rcx, r14
0x18001d3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3bb  mov     rcx, [rbp+var_20]
0x18001d3bf  lea     r8, [rbp+var_30]
0x18001d3c3  mov     rdx, [rax]
0x18001d3c6  call    FwAdvPolicyLookForRuleID
0x18001d3cb  mov     ebx, eax
0x18001d3cd  test    eax, eax
0x18001d3cf  jns     short loc_18001D3FC
0x18001d3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d8  lea     rdi, WPP_GLOBAL_Control
0x18001d3df  cmp     rcx, rdi
0x18001d3e2  jz      loc_18001D540
0x18001d3e8  test    byte ptr [rcx+1Ch], 1
0x18001d3ec  jz      loc_18001D540
0x18001d3f2  mov     edx, 45h ; 'E'
0x18001d3f7  jmp     loc_18001D52D
0x18001d3fc  cmp     [rbp+var_30], 0
0x18001d400  jbe     short loc_18001D435
0x18001d402  mov     ebx, 8000FFFFh
0x18001d407  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d40e  lea     rdi, WPP_GLOBAL_Control
0x18001d415  cmp     rcx, rdi
0x18001d418  jz      loc_18001D540
0x18001d41e  test    byte ptr [rcx+1Ch], 1
0x18001d422  jz      loc_18001D540
0x18001d428  mov     edx, 46h ; 'F'
0x18001d42d  mov     r9d, ebx
0x18001d430  jmp     loc_18001D530
0x18001d435  mov     rax, [rsi+40h]
0x18001d439  lea     rdx, [rbp+var_18]
0x18001d43d  mov     rcx, r14
0x18001d440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d445  mov     ebx, eax
0x18001d447  test    eax, eax
0x18001d449  jns     short loc_18001D476
0x18001d44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d452  lea     rdi, WPP_GLOBAL_Control
0x18001d459  cmp     rcx, rdi
0x18001d45c  jz      loc_18001D540
0x18001d462  test    byte ptr [rcx+1Ch], 1
0x18001d466  jz      loc_18001D540
0x18001d46c  mov     edx, 47h ; 'G'
0x18001d471  jmp     loc_18001D52D
0x18001d476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d47d  lea     rdi, WPP_GLOBAL_Control
0x18001d484  cmp     rcx, rdi
0x18001d487  jz      short loc_18001D4A8
0x18001d489  test    byte ptr [rcx+1Ch], 4
0x18001d48d  jz      short loc_18001D4A8
0x18001d48f  mov     r9, [rbp+var_18]
0x18001d493  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d49a  mov     rcx, [rcx+10h]
0x18001d49e  mov     edx, 48h ; 'H'
0x18001d4a3  call    WPP_SF_S
0x18001d4a8  mov     rax, [rsi+20h]
0x18001d4ac  mov     rcx, r14
0x18001d4af  mov     rbx, [rbp+var_18]
0x18001d4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b8  mov     rcx, [rbp+var_20]
0x18001d4bc  mov     r9, rbx
0x18001d4bf  xor     edx, edx
0x18001d4c1  mov     r8, [rax]
0x18001d4c4  call    cs:__imp_FwRegSetString
0x18001d4ca  mov     ebx, eax
0x18001d4cc  test    eax, eax
0x18001d4ce  jns     short loc_18001D4E9
0x18001d4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4d7  cmp     rcx, rdi
0x18001d4da  jz      short loc_18001D540
0x18001d4dc  test    byte ptr [rcx+1Ch], 1
0x18001d4e0  jz      short loc_18001D540
0x18001d4e2  mov     edx, 49h ; 'I'
0x18001d4e7  jmp     short loc_18001D52D
0x18001d4e9  mov     rax, [rsi+20h]
0x18001d4ed  mov     rcx, r14
0x18001d4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4f5  mov     rdx, [rbp+var_20]
0x18001d4f9  lea     rcx, [rbp+var_28]
0x18001d4fd  mov     [rsp+60h+var_40], rcx; __int64
0x18001d502  xor     r8d, r8d
0x18001d505  mov     rcx, rsi; struct _tag_FW_RULE_MANIPULATOR *
0x18001d508  mov     r9, [rax]
0x18001d50b  call    FwGetAdvPolicyRule
0x18001d510  mov     ebx, eax
0x18001d512  test    eax, eax
0x18001d514  jns     short loc_18001D540
0x18001d516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d51d  cmp     rcx, rdi
0x18001d520  jz      short loc_18001D540
0x18001d522  test    byte ptr [rcx+1Ch], 1
0x18001d526  jz      short loc_18001D540
0x18001d528  mov     edx, 4Ah ; 'J'
0x18001d52d  mov     r9d, eax
0x18001d530  mov     rcx, [rcx+10h]
0x18001d534  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d53b  call    WPP_SF_d
0x18001d540  mov     rcx, [rbp+var_28]
0x18001d544  call    cs:__imp_FwFree
0x18001d54a  mov     rcx, [rbp+var_18]
0x18001d54e  call    cs:__imp_FwFree
0x18001d554  mov     rcx, [rbp+var_20]
0x18001d558  call    cs:__imp_FwRegCloseKey
0x18001d55e  mov     eax, ebx
0x18001d560  mov     rcx, [rbp+var_10]
0x18001d564  xor     rcx, rsp; StackCookie
0x18001d567  call    __security_check_cookie
0x18001d56c  add     rsp, 60h
0x18001d570  pop     r14
0x18001d572  pop     rdi
0x18001d573  pop     rsi
0x18001d574  pop     rbx
0x18001d575  pop     rbp
0x18001d576  retn
```
