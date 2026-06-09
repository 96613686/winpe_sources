# FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)

- ea: `0x1800392c0`
- end: `0x1800394a3`
- name: `?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z`
- size: `483`
- prototype: `int(FwOpenPort *__hidden this, const struct _tag_FW_RULE *, struct _tag_FW_RULE *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180001e58`
- `0x180039960`
- `0x180039b50`
- `0x180039ce0`
- `0x180039eb0`
- `0x18003a060`
- `0x18003a240`

## callees

- `0x180003520`
- `0x18000b34c`
- `0x180014368`
- `0x1800277b0`
- `0x18002e484`
- `0x18003063c`
- `0x18003104c`
- `0x1800392c0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x1800393cc`
- `fwbase!FwBaseFree` at `0x1800393cc`
- `fwbase!FwReportReturnError` at `0x180039354`
- `fwbase!FwReportReturnError` at `0x180039363`
- `fwbase!FwReportReturnError` at `0x180039402`
- `fwbase!FwReportReturnError` at `0x18003947e`
- `fwbase!FwReportReturnError` at `0x180039354`
- `fwbase!FwReportReturnError` at `0x180039363`
- `fwbase!FwReportReturnError` at `0x180039402`
- `fwbase!FwReportReturnError` at `0x18003947e`
- `fwbase!FwStringCopy` at `0x1800393de`
- `fwbase!FwStringCopy` at `0x1800393de`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003940c`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003945a`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003940c`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003945a`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800392fb`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800392fb`

## string_xrefs

- `0x180039301`: `FwOpenPort::SetRule`
- `0x18003934d`: `FwOpenPort::ValidateOpenPortRule`
- `0x18003935c`: `FwOpenPort::ValidateOpenPortRule`

## pseudocode

```c
__int64 __fastcall FwOpenPort::SetRule(FwOpenPort *this, const struct _tag_FW_RULE *a2, struct _tag_FW_RULE *a3)
{
  int v5; // eax
  int v6; // ebx
  _WORD *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct _tag_FW_RULE *v10; // rcx
  unsigned int v11; // r8d
  struct _tag_FW_RULE *v12; // rdi
  struct _tag_FW_RULE *v14; // [rsp+20h] [rbp-20h] BYREF
  void *v15; // [rsp+28h] [rbp-18h] BYREF

  v14 = 0;
  v15 = 0;
  v5 = FwCopyRule(a2, &v14);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_20;
  if ( !*((_DWORD *)this + 21) )
    goto LABEL_26;
  if ( *((_WORD *)v14 + 24) != 6 && *((_WORD *)v14 + 24) != 17 )
    goto LABEL_8;
  v7 = (_WORD *)*((_QWORD *)v14 + 3);
  if ( !v7 )
  {
    v8 = -2147467261;
    v9 = 2147500035LL;
    goto LABEL_9;
  }
  if ( !*v7 )
  {
LABEL_8:
    v9 = 2147942487LL;
    v8 = -2147024809;
LABEL_9:
    FwReportReturnError("FwOpenPort::ValidateOpenPortRule", v9);
    v5 = FwReportReturnError("FwOpenPort::ValidateOpenPortRule", v8);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_20;
  }
  v5 = OpenLocalPolicyStore(2, &v15);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v10 = v14;
    v11 = *((_DWORD *)this + 16);
    v12 = v14;
    if ( a3 )
      v12 = a3;
    if ( (~v11 & *((_DWORD *)v12 + 10)) != 0 )
    {
      v5 = FwSplitRule(v15, v12, v11);
      v6 = v5;
      if ( v5 < 0 )
        goto LABEL_20;
      *((_DWORD *)v14 + 10) = *((_DWORD *)v12 + 10);
      v10 = v14;
    }
    if ( !a3 )
      goto LABEL_19;
    FwBaseFree(*((_QWORD *)v10 + 2));
    v5 = FwStringCopy(*((_QWORD *)a3 + 2), (char *)v14 + 16);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v10 = v14;
LABEL_19:
      v5 = SaveRule(v10, v15);
      v6 = v5;
      if ( v5 < 0 )
        goto LABEL_20;
LABEL_26:
      FwFreeWFRule(*((_QWORD *)this + 9));
      *((_QWORD *)this + 9) = v14;
      v14 = 0;
      goto LABEL_27;
    }
  }
LABEL_20:
  FwReportReturnError("FwOpenPort::SetRule", (unsigned int)v5);
  FwFreeWFRule(v14);
  if ( v6 == -2147024891 && (unsigned int)AccessDeniedShouldBeSuppressed() )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4cabb5b60cea3199fbe674e9f4ad4a38_Traceguids);
    v6 = 0;
  }
LABEL_27:
  CloseLocalPolicyStore(v15);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::SetRule", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800392c0  push    rbp
0x1800392c2  push    rbx
0x1800392c3  push    rsi
0x1800392c4  push    rdi
0x1800392c5  push    r12
0x1800392c7  push    r14
0x1800392c9  push    r15
0x1800392cb  mov     rbp, rsp
0x1800392ce  sub     rsp, 40h
0x1800392d2  mov     rax, cs:__security_cookie
0x1800392d9  xor     rax, rsp
0x1800392dc  mov     [rbp+var_10], rax
0x1800392e0  mov     rax, rdx
0x1800392e3  mov     rsi, rcx
0x1800392e6  xor     r15d, r15d
0x1800392e9  lea     rdx, [rbp+var_20]
0x1800392ed  mov     rcx, rax
0x1800392f0  mov     [rbp+var_20], r15
0x1800392f4  mov     r14, r8
0x1800392f7  mov     [rbp+var_18], r15
0x1800392fb  call    cs:__imp_FwCopyRule
0x180039301  lea     r12, aFwopenportSetr; "FwOpenPort::SetRule"
0x180039308  mov     ebx, eax
0x18003930a  test    eax, eax
0x18003930c  js      loc_1800393FD
0x180039312  cmp     [rsi+54h], r15d
0x180039316  jz      loc_180039456
0x18003931c  mov     rax, [rbp+var_20]
0x180039320  cmp     word ptr [rax+30h], 6
0x180039325  jz      short loc_18003932E
0x180039327  cmp     word ptr [rax+30h], 11h
0x18003932c  jnz     short loc_180039346
0x18003932e  mov     rax, [rax+18h]
0x180039332  test    rax, rax
0x180039335  jnz     short loc_180039340
0x180039337  mov     ebx, 80004003h
0x18003933c  mov     edx, ebx
0x18003933e  jmp     short loc_18003934D
0x180039340  cmp     [rax], r15w
0x180039344  jnz     short loc_180039373
0x180039346  mov     edx, 80070057h
0x18003934b  mov     ebx, edx
0x18003934d  lea     rcx, aFwopenportVali; "FwOpenPort::ValidateOpenPortRule"
0x180039354  call    cs:__imp_FwReportReturnError
0x18003935a  mov     edx, ebx
0x18003935c  lea     rcx, aFwopenportVali; "FwOpenPort::ValidateOpenPortRule"
0x180039363  call    cs:__imp_FwReportReturnError
0x180039369  mov     ebx, eax
0x18003936b  test    eax, eax
0x18003936d  js      loc_1800393FD
0x180039373  lea     rdx, [rbp+var_18]
0x180039377  mov     ecx, 2
0x18003937c  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x180039381  mov     ebx, eax
0x180039383  test    eax, eax
0x180039385  js      short loc_1800393FD
0x180039387  mov     rcx, [rbp+var_20]
0x18003938b  test    r14, r14
0x18003938e  mov     r8d, [rsi+40h]; unsigned int
0x180039392  mov     rdi, rcx
0x180039395  cmovnz  rdi, r14
0x180039399  mov     eax, r8d
0x18003939c  not     eax
0x18003939e  test    [rdi+28h], eax
0x1800393a1  jz      short loc_1800393C3
0x1800393a3  mov     rcx, [rbp+var_18]; void *
0x1800393a7  mov     rdx, rdi; struct _tag_FW_RULE *
0x1800393aa  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x1800393af  mov     ebx, eax
0x1800393b1  test    eax, eax
0x1800393b3  js      short loc_1800393FD
0x1800393b5  mov     rax, [rbp+var_20]
0x1800393b9  mov     edx, [rdi+28h]
0x1800393bc  mov     [rax+28h], edx
0x1800393bf  mov     rcx, [rbp+var_20]
0x1800393c3  test    r14, r14
0x1800393c6  jz      short loc_1800393EE
0x1800393c8  mov     rcx, [rcx+10h]
0x1800393cc  call    cs:__imp_FwBaseFree
0x1800393d2  mov     rdx, [rbp+var_20]
0x1800393d6  mov     rcx, [r14+10h]
0x1800393da  add     rdx, 10h
0x1800393de  call    cs:__imp_FwStringCopy
0x1800393e4  mov     ebx, eax
0x1800393e6  test    eax, eax
0x1800393e8  js      short loc_1800393FD
0x1800393ea  mov     rcx, [rbp+var_20]; struct _tag_FW_RULE *
0x1800393ee  mov     rdx, [rbp+var_18]; void *
0x1800393f2  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x1800393f7  mov     ebx, eax
0x1800393f9  test    eax, eax
0x1800393fb  jns     short loc_180039456
0x1800393fd  mov     edx, eax
0x1800393ff  mov     rcx, r12
0x180039402  call    cs:__imp_FwReportReturnError
0x180039408  mov     rcx, [rbp+var_20]
0x18003940c  call    cs:__imp_FwFreeWFRule
0x180039412  cmp     ebx, 80070005h
0x180039418  jnz     short loc_18003946C
0x18003941a  call    ?AccessDeniedShouldBeSuppressed@@YAHXZ; AccessDeniedShouldBeSuppressed(void)
0x18003941f  test    eax, eax
0x180039421  jz      short loc_18003946C
0x180039423  mov     rcx, cs:WPP_GLOBAL_Control
0x18003942a  lea     rax, WPP_GLOBAL_Control
0x180039431  cmp     rcx, rax
0x180039434  jz      short loc_180039451
0x180039436  test    byte ptr [rcx+1Ch], 2
0x18003943a  jz      short loc_180039451
0x18003943c  mov     rcx, [rcx+10h]
0x180039440  lea     r8, WPP_4cabb5b60cea3199fbe674e9f4ad4a38_Traceguids
0x180039447  mov     edx, 0Ah
0x18003944c  call    WPP_SF_
0x180039451  mov     ebx, r15d
0x180039454  jmp     short loc_18003946C
0x180039456  mov     rcx, [rsi+48h]
0x18003945a  call    cs:__imp_FwFreeWFRule
0x180039460  mov     rax, [rbp+var_20]
0x180039464  mov     [rsi+48h], rax
0x180039468  mov     [rbp+var_20], r15
0x18003946c  mov     rcx, [rbp+var_18]; void *
0x180039470  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180039475  test    ebx, ebx
0x180039477  jns     short loc_180039486
0x180039479  mov     edx, ebx
0x18003947b  mov     rcx, r12
0x18003947e  call    cs:__imp_FwReportReturnError
0x180039484  mov     ebx, eax
0x180039486  mov     eax, ebx
0x180039488  mov     rcx, [rbp+var_10]
0x18003948c  xor     rcx, rsp; StackCookie
0x18003948f  call    __security_check_cookie
0x180039494  add     rsp, 40h
0x180039498  pop     r15
0x18003949a  pop     r14
0x18003949c  pop     r12
0x18003949e  pop     rdi
0x18003949f  pop     rsi
0x1800394a0  pop     rbx
0x1800394a1  pop     rbp
0x1800394a2  retn
```
