# FilterAlreadyAppliedUpdates(ulong *,ulong,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,long,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,long>>> &)

- ea: `0x180010d04`
- end: `0x180010f1f`
- name: `?FilterAlreadyAppliedUpdates@@YAXPEAKKAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x1800095cc`
- `0x18000ce04`
- `0x18000d524`
- `0x180010d04`
- `0x18001a42c`
- `0x18002386c`
- `0x180038130`
- `0x1800383c4`
- `0x18003c0b8`

## string_xrefs

- `0x180010d59`: `IsDBUpdateRequired_1P`
- `0x180010d8f`: `1P DB update not needed`
- `0x180010dbe`: `IsDBUpdateRequired_3POROM_Before`
- `0x180010df3`: `3P OROM DB update not needed`
- `0x180010e22`: `IsDBUpdateRequired_3PUEFI_Before`
- `0x180010e57`: `3P UEFI DB update not needed`
- `0x180010ea4`: `IsKEKUpdateRequired`
- `0x180010ed6`: `KEK update not needed`
- `0x180010eeb`: `BootMgr update is not needed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FilterAlreadyAppliedUpdates(int *a1, int a2, __int64 a3)
{
  int v6; // edi
  int v7; // esi
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // [rsp+20h] [rbp-50h] BYREF
  int v12[3]; // [rsp+24h] [rbp-4Ch] BYREF
  __int128 v13; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v6 = *a1;
  v7 = 1;
  v11 = 1;
  v13 = *(_OWORD *)byte_18005F3B0;
  v8 = IsDBUpdateRequired(&v11, &v13);
  std::wstring::wstring((__int64)v14, (__int64)L"IsDBUpdateRequired_1P");
  v15 = v8;
  std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
    a3,
    &v13,
    v14);
  std::wstring::_Tidy_deallocate(v14);
  if ( !v11 )
  {
    v6 &= ~0x40u;
    SBServicingLogMessage((wchar_t *)L"1P DB update not needed");
  }
  v12[0] = 1;
  v13 = *(_OWORD *)byte_18005F3C0;
  v11 = IsDBUpdateRequired(v12, &v13);
  std::pair<std::wstring const,long>::pair<std::wstring const,long>(v14, L"IsDBUpdateRequired_3POROM_Before", &v11);
  std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
    a3,
    &v13,
    v14);
  std::wstring::_Tidy_deallocate(v14);
  if ( !v12[0] )
  {
    v6 &= ~0x800u;
    SBServicingLogMessage((wchar_t *)L"3P OROM DB update not needed");
  }
  v12[0] = 1;
  v13 = *(_OWORD *)byte_18005F3A0;
  v11 = IsDBUpdateRequired(v12, &v13);
  std::pair<std::wstring const,long>::pair<std::wstring const,long>(v14, L"IsDBUpdateRequired_3PUEFI_Before", &v11);
  std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
    a3,
    &v13,
    v14);
  std::wstring::_Tidy_deallocate(v14);
  if ( !v12[0] )
  {
    v6 &= ~0x1000u;
    SBServicingLogMessage((wchar_t *)L"3P UEFI DB update not needed");
  }
  v12[0] = 0;
  v9 = IsKEKUpdatePresent(v12);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( v12[0] )
      v7 = 0;
    v10 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9D,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbservicing.cpp",
      (const char *)(unsigned int)v9,
      v11);
  }
  v11 = v10;
  std::pair<std::wstring const,long>::pair<std::wstring const,long>(v14, L"IsKEKUpdateRequired", &v11);
  std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
    a3,
    &v13,
    v14);
  std::wstring::_Tidy_deallocate(v14);
  if ( !v7 )
  {
    v6 &= ~4u;
    SBServicingLogMessage((wchar_t *)L"KEK update not needed");
  }
  if ( a2 )
  {
    v6 &= ~0x100u;
    SBServicingLogMessage((wchar_t *)L"BootMgr update is not needed");
  }
  *a1 = v6;
}

```

## disassembly

```asm
0x180010d04  mov     [rsp-28h+arg_8], rbx
0x180010d09  mov     [rsp-28h+arg_18], rsi
0x180010d0e  push    rbp
0x180010d0f  push    rdi
0x180010d10  push    r12
0x180010d12  push    r14
0x180010d14  push    r15
0x180010d16  mov     rbp, rsp
0x180010d19  sub     rsp, 70h
0x180010d1d  mov     rax, cs:__security_cookie
0x180010d24  xor     rax, rsp
0x180010d27  mov     [rbp+var_8], rax
0x180010d2b  mov     r14, r8
0x180010d2e  mov     r12d, edx
0x180010d31  mov     r15, rcx
0x180010d34  mov     edi, [rcx]
0x180010d36  mov     esi, 1
0x180010d3b  mov     [rbp+var_50], esi
0x180010d3e  movups  xmm0, xmmword ptr cs:byte_18005F3B0
0x180010d45  movdqu  [rbp+var_40], xmm0
0x180010d4a  lea     rdx, [rbp+var_40]
0x180010d4e  lea     rcx, [rbp+var_50]
0x180010d52  call    ?IsDBUpdateRequired@@YAJPEAHUSB_HASH@@@Z; IsDBUpdateRequired(int *,SB_HASH)
0x180010d57  mov     ebx, eax
0x180010d59  lea     rdx, aIsdbupdaterequ_2; "IsDBUpdateRequired_1P"
0x180010d60  lea     rcx, [rbp+var_30]
0x180010d64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010d69  mov     [rbp+var_10], ebx
0x180010d6c  lea     r8, [rbp+var_30]
0x180010d70  lea     rdx, [rbp+var_40]
0x180010d74  mov     rcx, r14
0x180010d77  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x180010d7c  nop
0x180010d7d  lea     rcx, [rbp+var_30]
0x180010d81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010d86  cmp     [rbp+var_50], 0
0x180010d8a  jnz     short loc_180010D9B
0x180010d8c  and     edi, 0FFFFFFBFh
0x180010d8f  lea     rcx, a1pDbUpdateNotN; "1P DB update not needed"
0x180010d96  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180010d9b  mov     [rbp+var_4C], esi
0x180010d9e  movups  xmm0, xmmword ptr cs:byte_18005F3C0
0x180010da5  movdqu  [rbp+var_40], xmm0
0x180010daa  lea     rdx, [rbp+var_40]
0x180010dae  lea     rcx, [rbp+var_4C]
0x180010db2  call    ?IsDBUpdateRequired@@YAJPEAHUSB_HASH@@@Z; IsDBUpdateRequired(int *,SB_HASH)
0x180010db7  mov     [rbp+var_50], eax
0x180010dba  lea     r8, [rbp+var_50]
0x180010dbe  lea     rdx, aIsdbupdaterequ_3; "IsDBUpdateRequired_3POROM_Before"
0x180010dc5  lea     rcx, [rbp+var_30]
0x180010dc9  call    ??$?0AEAY0BE@$$CBGAEAJ$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@QEAA@AEAY0BE@$$CBGAEAJ@Z; std::pair<std::wstring const,long>::pair<std::wstring const,long>(ushort const (&)[20],long &)
0x180010dce  nop
0x180010dcf  lea     r8, [rbp+var_30]
0x180010dd3  lea     rdx, [rbp+var_40]
0x180010dd7  mov     rcx, r14
0x180010dda  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x180010ddf  nop
0x180010de0  lea     rcx, [rbp+var_30]
0x180010de4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010de9  cmp     [rbp+var_4C], 0
0x180010ded  jnz     short loc_180010DFF
0x180010def  btr     edi, 0Bh
0x180010df3  lea     rcx, a3pOromDbUpdate; "3P OROM DB update not needed"
0x180010dfa  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180010dff  mov     [rbp+var_4C], esi
0x180010e02  movups  xmm0, xmmword ptr cs:byte_18005F3A0
0x180010e09  movdqu  [rbp+var_40], xmm0
0x180010e0e  lea     rdx, [rbp+var_40]
0x180010e12  lea     rcx, [rbp+var_4C]
0x180010e16  call    ?IsDBUpdateRequired@@YAJPEAHUSB_HASH@@@Z; IsDBUpdateRequired(int *,SB_HASH)
0x180010e1b  mov     [rbp+var_50], eax
0x180010e1e  lea     r8, [rbp+var_50]
0x180010e22  lea     rdx, aIsdbupdaterequ_0; "IsDBUpdateRequired_3PUEFI_Before"
0x180010e29  lea     rcx, [rbp+var_30]
0x180010e2d  call    ??$?0AEAY0BE@$$CBGAEAJ$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@QEAA@AEAY0BE@$$CBGAEAJ@Z; std::pair<std::wstring const,long>::pair<std::wstring const,long>(ushort const (&)[20],long &)
0x180010e32  nop
0x180010e33  lea     r8, [rbp+var_30]
0x180010e37  lea     rdx, [rbp+var_40]
0x180010e3b  mov     rcx, r14
0x180010e3e  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x180010e43  nop
0x180010e44  lea     rcx, [rbp+var_30]
0x180010e48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010e4d  cmp     [rbp+var_4C], 0
0x180010e51  jnz     short loc_180010E63
0x180010e53  btr     edi, 0Ch
0x180010e57  lea     rcx, a3pUefiDbUpdate; "3P UEFI DB update not needed"
0x180010e5e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180010e63  mov     [rbp+var_4C], 0
0x180010e6a  lea     rcx, [rbp+var_4C]; int *
0x180010e6e  call    ?IsKEKUpdatePresent@@YAJPEAH@Z; IsKEKUpdatePresent(int *)
0x180010e73  mov     ebx, eax
0x180010e75  test    eax, eax
0x180010e77  jns     short loc_180010E93
0x180010e79  mov     rcx, [rbp+28h]; this
0x180010e7d  mov     r9d, eax; char *
0x180010e80  lea     r8, aOnecoreBaseSec; "onecore\\base\\secureboot\\servicing\\l"...
0x180010e87  mov     edx, 0B9Dh; void *
0x180010e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e91  jmp     short loc_180010E9D
0x180010e93  xor     eax, eax
0x180010e95  cmp     [rbp+var_4C], eax
0x180010e98  cmovnz  esi, eax
0x180010e9b  xor     ebx, ebx
0x180010e9d  mov     [rbp+var_50], ebx
0x180010ea0  lea     r8, [rbp+var_50]
0x180010ea4  lea     rdx, aIskekupdatereq; "IsKEKUpdateRequired"
0x180010eab  lea     rcx, [rbp+var_30]
0x180010eaf  call    ??$?0AEAY0BE@$$CBGAEAJ$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@QEAA@AEAY0BE@$$CBGAEAJ@Z; std::pair<std::wstring const,long>::pair<std::wstring const,long>(ushort const (&)[20],long &)
0x180010eb4  nop
0x180010eb5  lea     r8, [rbp+var_30]
0x180010eb9  lea     rdx, [rbp+var_40]
0x180010ebd  mov     rcx, r14
0x180010ec0  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x180010ec5  nop
0x180010ec6  lea     rcx, [rbp+var_30]
0x180010eca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010ecf  test    esi, esi
0x180010ed1  jnz     short loc_180010EE2
0x180010ed3  and     edi, 0FFFFFFFBh
0x180010ed6  lea     rcx, aKekUpdateNotNe; "KEK update not needed"
0x180010edd  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180010ee2  test    r12d, r12d
0x180010ee5  jz      short loc_180010EF7
0x180010ee7  btr     edi, 8
0x180010eeb  lea     rcx, aBootmgrUpdateI; "BootMgr update is not needed"
0x180010ef2  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180010ef7  mov     [r15], edi
0x180010efa  mov     rcx, [rbp+var_8]
0x180010efe  xor     rcx, rsp; StackCookie
0x180010f01  call    __security_check_cookie
0x180010f06  lea     r11, [rsp+70h+var_s0]
0x180010f0b  mov     rbx, [r11+38h]
0x180010f0f  mov     rsi, [r11+48h]
0x180010f13  mov     rsp, r11
0x180010f16  pop     r15
0x180010f18  pop     r14
0x180010f1a  pop     r12
0x180010f1c  pop     rdi
0x180010f1d  pop     rbp
0x180010f1e  retn
```
