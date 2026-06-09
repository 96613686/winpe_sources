# PolicyManager::IsPinRecoveryEnabled(ushort const *,_NGC_ENABLED_STATE *)

- ea: `0x18000aa14`
- end: `0x18000ad18`
- name: `?IsPinRecoveryEnabled@PolicyManager@@YAJPEBGPEAW4_NGC_ENABLED_STATE@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, const unsigned __int16 *, enum _NGC_ENABLED_STATE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800332d0`

## callees

- `0x180006800`
- `0x18000a8e0`
- `0x18000aa14`
- `0x18000ad20`
- `0x180017f68`
- `0x180023278`
- `0x180024e68`
- `0x18002c640`

## import_xrefs

- `dsreg!DsrFreeJoinInfo` at `0x18000aa88`
- `dsreg!DsrFreeJoinInfo` at `0x18000aa88`
- `dsreg!DsrGetJoinInfo` at `0x18000aa54`
- `dsreg!DsrGetJoinInfo` at `0x18000aa54`

## string_xrefs

- `0x18000aa6d`: `onecore\ds\security\ngc\ctnrsvc\policymgr\policymanager.cpp`
- `0x18000aae4`: `onecore\ds\security\ngc\ctnrsvc\policymgr\policymanager.cpp`
- `0x18000abcd`: `onecore\ds\security\ngc\ctnrsvc\policymgr\policymanager.cpp`
- `0x18000aca5`: `onecore\ds\security\ngc\ctnrsvc\policymgr\policymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::IsPinRecoveryEnabled(
        PolicyManager *this,
        unsigned __int16 *a2,
        enum _NGC_ENABLED_STATE *a3)
{
  int JoinInfo; // eax
  unsigned int v6; // ebx
  int EnabledState; // eax
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  __int128 *p_Src; // rdx
  int v13; // eax
  int v14; // esi
  __int128 *v15; // rdx
  int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-50h] BYREF
  __int128 Src; // [rsp+28h] [rbp-48h] BYREF
  __int128 v19; // [rsp+38h] [rbp-38h]
  __int128 v20; // [rsp+48h] [rbp-28h] BYREF
  __int128 v21; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *(_DWORD *)a2 = 2;
  v17 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v17);
  v6 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\policymgr\\policymanager.cpp",
      (const char *)(unsigned int)JoinInfo,
      v17);
    goto LABEL_3;
  }
  if ( v17 && *(_DWORD *)v17 == 1 )
  {
    EnabledState = PolicyManager::ReadEnabledState(
                     -2147483646,
                     L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                     L"EnablePinRecovery",
                     a2);
    v6 = EnabledState;
    if ( EnabledState < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A8,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\policymgr\\policymanager.cpp",
        (const char *)(unsigned int)EnabledState,
        v17);
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v17);
      return v6;
    }
    if ( *(_DWORD *)a2 != 2 )
    {
LABEL_21:
      v6 = 0;
      goto LABEL_22;
    }
    Src = 0;
    v19 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 43);
    std::wstring::_Append<unsigned short>(&Src);
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*(_QWORD *)(v17 + 32) + 2 * v10) );
    std::wstring::_Append<unsigned short>(&Src);
    std::wstring::_Append<unsigned short>(&Src);
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)this + v11) );
    std::wstring::_Append<unsigned short>(&Src);
    std::wstring::_Append<unsigned short>(&Src);
    p_Src = &Src;
    if ( *((_QWORD *)&v19 + 1) > 7u )
      p_Src = (__int128 *)Src;
    v13 = PolicyManager::ReadEnabledState(-2147483646, p_Src, L"EnablePinRecovery", a2);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\policymgr\\policymanager.cpp",
        (const char *)(unsigned int)v13,
        v17);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&Src);
      v6 = v14;
      goto LABEL_22;
    }
    if ( *(_DWORD *)a2 != 2 )
    {
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&Src);
      goto LABEL_21;
    }
    v20 = 0;
    v21 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v20, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 43);
    std::wstring::_Append<unsigned short>(&v20);
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)(v17 + 32) + 2 * v9) );
    std::wstring::_Append<unsigned short>(&v20);
    std::wstring::_Append<unsigned short>(&v20);
    v15 = &v20;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v15 = (__int128 *)v20;
    v16 = PolicyManager::ReadEnabledState(-2147483646, v15, L"EnablePinRecovery", a2);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C5,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\policymgr\\policymanager.cpp",
        (const char *)(unsigned int)v16,
        v17);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v20);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&Src);
LABEL_3:
      if ( v17 )
        DsrFreeJoinInfo();
      return v6;
    }
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v20);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&Src);
  }
  else
  {
    *(_DWORD *)a2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v17);
  return 0;
}

```

## disassembly

```asm
0x18000aa14  mov     [rsp-28h+arg_10], rbx
0x18000aa19  mov     [rsp-28h+arg_18], rsi
0x18000aa1e  push    rbp
0x18000aa1f  push    rdi
0x18000aa20  push    r13
0x18000aa22  push    r14
0x18000aa24  push    r15
0x18000aa26  mov     rbp, rsp
0x18000aa29  sub     rsp, 70h
0x18000aa2d  mov     rax, cs:__security_cookie
0x18000aa34  xor     rax, rsp
0x18000aa37  mov     [rbp+var_8], rax
0x18000aa3b  mov     rdi, rdx
0x18000aa3e  mov     rsi, rcx
0x18000aa41  mov     dword ptr [rdx], 2
0x18000aa47  xor     r14d, r14d
0x18000aa4a  mov     [rbp+var_50], r14
0x18000aa4e  lea     rdx, [rbp+var_50]
0x18000aa52  xor     ecx, ecx
0x18000aa54  call    cs:__imp_DsrGetJoinInfo
0x18000aa5b  nop     dword ptr [rax+rax+00h]
0x18000aa60  mov     ebx, eax
0x18000aa62  test    eax, eax
0x18000aa64  jns     short loc_18000AA9B
0x18000aa66  mov     rcx, [rbp+28h]; this
0x18000aa6a  mov     r9d, eax; char *
0x18000aa6d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\ctnrsvc\\po"...
0x18000aa74  mov     edx, 28Fh; void *
0x18000aa79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa7e  nop
0x18000aa7f  mov     rcx, [rbp+var_50]
0x18000aa83  test    rcx, rcx
0x18000aa86  jz      short loc_18000AA94
0x18000aa88  call    cs:__imp_DsrFreeJoinInfo
0x18000aa8f  nop     dword ptr [rax+rax+00h]
0x18000aa94  mov     eax, ebx
0x18000aa96  jmp     loc_18000ACF2
0x18000aa9b  mov     rax, [rbp+var_50]
0x18000aa9f  test    rax, rax
0x18000aaa2  jz      loc_18000ACE4
0x18000aaa8  mov     r15d, 1
0x18000aaae  cmp     [rax], r15d
0x18000aab1  jnz     loc_18000ACE4
0x18000aab7  mov     r9, rdi
0x18000aaba  lea     r8, aEnablepinrecov; "EnablePinRecovery"
0x18000aac1  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Passport"...
0x18000aac8  mov     r13, 0FFFFFFFF80000002h
0x18000aacf  mov     rcx, r13
0x18000aad2  call    PolicyManager__ReadEnabledState
0x18000aad7  mov     ebx, eax
0x18000aad9  test    eax, eax
0x18000aadb  jns     short loc_18000AAFA
0x18000aadd  mov     rcx, [rbp+28h]; this
0x18000aae1  mov     r9d, eax; char *
0x18000aae4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\ctnrsvc\\po"...
0x18000aaeb  mov     edx, 2A8h; void *
0x18000aaf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaf5  jmp     loc_18000ABFD
0x18000aafa  cmp     dword ptr [rdi], 2
0x18000aafd  jnz     loc_18000ABFA
0x18000ab03  xorps   xmm0, xmm0
0x18000ab06  movups  [rbp+Src], xmm0
0x18000ab0a  xorps   xmm1, xmm1
0x18000ab0d  movdqu  [rbp+var_38], xmm1
0x18000ab12  mov     r8d, 2Bh ; '+'
0x18000ab18  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x18000ab1f  lea     rcx, [rbp+Src]
0x18000ab23  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ab28  nop
0x18000ab29  mov     r8, r15
0x18000ab2c  lea     rdx, asc_18008F0A4; "\\"
0x18000ab33  lea     rcx, [rbp+Src]; Src
0x18000ab37  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ab3c  mov     rax, [rbp+var_50]
0x18000ab40  mov     rdx, [rax+20h]
0x18000ab44  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ab48  mov     r8, rbx
0x18000ab4b  inc     r8
0x18000ab4e  cmp     [rdx+r8*2], r14w
0x18000ab53  jnz     short loc_18000AB4B
0x18000ab55  lea     rcx, [rbp+Src]; Src
0x18000ab59  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ab5e  mov     r8, r15
0x18000ab61  lea     rdx, asc_18008F0A4; "\\"
0x18000ab68  lea     rcx, [rbp+Src]; Src
0x18000ab6c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ab71  mov     r8, rbx
0x18000ab74  inc     r8
0x18000ab77  cmp     [rsi+r8*2], r14w
0x18000ab7c  jnz     short loc_18000AB74
0x18000ab7e  mov     rdx, rsi
0x18000ab81  lea     rcx, [rbp+Src]; Src
0x18000ab85  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ab8a  mov     r8d, 9
0x18000ab90  lea     rdx, aPolicies; "\\Policies"
0x18000ab97  lea     rcx, [rbp+Src]; Src
0x18000ab9b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000aba0  lea     rdx, [rbp+Src]
0x18000aba4  cmp     qword ptr [rbp+var_38+8], 7
0x18000aba9  cmova   rdx, qword ptr [rbp+Src]
0x18000abae  mov     r9, rdi
0x18000abb1  lea     r8, aEnablepinrecov; "EnablePinRecovery"
0x18000abb8  mov     rcx, r13
0x18000abbb  call    PolicyManager__ReadEnabledState
0x18000abc0  mov     esi, eax
0x18000abc2  test    eax, eax
0x18000abc4  jns     short loc_18000ABEC
0x18000abc6  mov     rcx, [rbp+28h]; this
0x18000abca  mov     r9d, eax; char *
0x18000abcd  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\ctnrsvc\\po"...
0x18000abd4  mov     edx, 2B7h; void *
0x18000abd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abde  nop
0x18000abdf  lea     rcx, [rbp+Src]
0x18000abe3  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000abe8  mov     ebx, esi
0x18000abea  jmp     short loc_18000ABFD
0x18000abec  cmp     dword ptr [rdi], 2
0x18000abef  jz      short loc_18000AC0B
0x18000abf1  lea     rcx, [rbp+Src]
0x18000abf5  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000abfa  mov     ebx, r14d
0x18000abfd  lea     rcx, [rbp+var_50]
0x18000ac01  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18000ac06  jmp     loc_18000AA94
0x18000ac0b  xorps   xmm0, xmm0
0x18000ac0e  movups  [rbp+var_28], xmm0
0x18000ac12  xorps   xmm1, xmm1
0x18000ac15  movdqu  [rbp+var_18], xmm1
0x18000ac1a  mov     r8d, 2Bh ; '+'
0x18000ac20  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x18000ac27  lea     rcx, [rbp+var_28]
0x18000ac2b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ac30  nop
0x18000ac31  mov     r8, r15
0x18000ac34  lea     rdx, asc_18008F0A4; "\\"
0x18000ac3b  lea     rcx, [rbp+var_28]; Src
0x18000ac3f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ac44  mov     rax, [rbp+var_50]
0x18000ac48  mov     rdx, [rax+20h]
0x18000ac4c  inc     rbx
0x18000ac4f  cmp     [rdx+rbx*2], r14w
0x18000ac54  jnz     short loc_18000AC4C
0x18000ac56  mov     r8, rbx
0x18000ac59  lea     rcx, [rbp+var_28]; Src
0x18000ac5d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ac62  mov     r8d, 10h
0x18000ac68  lea     rdx, aDevicePolicies; "\\Device\\Policies"
0x18000ac6f  lea     rcx, [rbp+var_28]; Src
0x18000ac73  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000ac78  lea     rdx, [rbp+var_28]
0x18000ac7c  cmp     qword ptr [rbp+var_18+8], 7
0x18000ac81  cmova   rdx, qword ptr [rbp+var_28]
0x18000ac86  mov     r9, rdi
0x18000ac89  lea     r8, aEnablepinrecov; "EnablePinRecovery"
0x18000ac90  mov     rcx, r13
0x18000ac93  call    PolicyManager__ReadEnabledState
0x18000ac98  mov     ebx, eax
0x18000ac9a  test    eax, eax
0x18000ac9c  jns     short loc_18000ACCF
0x18000ac9e  mov     rcx, [rbp+28h]; this
0x18000aca2  mov     r9d, eax; char *
0x18000aca5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\ctnrsvc\\po"...
0x18000acac  mov     edx, 2C5h; void *
0x18000acb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acb6  nop
0x18000acb7  lea     rcx, [rbp+var_28]
0x18000acbb  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000acc0  nop
0x18000acc1  lea     rcx, [rbp+Src]
0x18000acc5  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000acca  jmp     loc_18000AA7F
0x18000accf  lea     rcx, [rbp+var_28]
0x18000acd3  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000acd8  nop
0x18000acd9  lea     rcx, [rbp+Src]
0x18000acdd  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000ace2  jmp     short loc_18000ACE7
0x18000ace4  mov     [rdi], r14d
0x18000ace7  lea     rcx, [rbp+var_50]
0x18000aceb  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18000acf0  xor     eax, eax
0x18000acf2  mov     rcx, [rbp+var_8]
0x18000acf6  xor     rcx, rsp; StackCookie
0x18000acf9  call    __security_check_cookie
0x18000acfe  lea     r11, [rsp+70h+var_s0]
0x18000ad03  mov     rbx, [r11+40h]
0x18000ad07  mov     rsi, [r11+48h]
0x18000ad0b  mov     rsp, r11
0x18000ad0e  pop     r15
0x18000ad10  pop     r14
0x18000ad12  pop     r13
0x18000ad14  pop     rdi
0x18000ad15  pop     rbp
0x18000ad16  retn
```
