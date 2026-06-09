# CodeIntegrity::Management::GetTokenInformation(ushort const *)

- ea: `0x180013660`
- end: `0x1800137cb`
- name: `?GetTokenInformation@Management@CodeIntegrity@@YA?AV?$unique_ptr@$$CBVAuthorizationToken@Management@CodeIntegrity@@U?$default_delete@$$CBVAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@PEBG@Z`
- size: `363`
- prototype: `BOOL __stdcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, LPVOID TokenInformation, DWORD TokenInformationLength, PDWORD ReturnLength)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800093d0`

## callees

- `0x180002a90`
- `0x180002ab4`
- `0x180005494`
- `0x180008474`
- `0x18000eab0`
- `0x18000ef38`
- `0x180010534`
- `0x18001097c`
- `0x1800109d8`
- `0x180013660`
- `0x180015518`
- `0x1800159fc`
- `0x180015a54`
- `0x1800185a8`
- `0x180018774`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall CodeIntegrity::Management::GetTokenInformation(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        LPVOID TokenInformation,
        DWORD TokenInformationLength,
        PDWORD ReturnLength)
{
  __int64 v5; // rdi
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdx
  __int64 AuthorizationToken; // rdi
  unsigned int v18; // r8d
  const char *v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25[2]; // [rsp+20h] [rbp-158h] BYREF
  _BYTE v26[32]; // [rsp+30h] [rbp-148h] BYREF
  _BYTE v27[32]; // [rsp+50h] [rbp-128h] BYREF
  void *v28[30]; // [rsp+70h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v5 = *(_QWORD *)&TokenInformationClass;
  *(_QWORD *)v25 = TokenHandle;
  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
    (__int64 *)qword_180039710,
    (__int64 *)v25,
    (__int64)qword_180039720);
  try
  {
    if ( *(_QWORD *)v25 == *(_QWORD *)qword_180039710 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x270, v7, v8, v25[0]);
    v9 = (__int64 *)(*(_QWORD *)v25 + 64LL);
    std::operator+<unsigned short>(v27, qword_180039720);
    v10 = std::_WChar_traits<unsigned short>::length(v5);
    v12 = std::wstring::_Append<unsigned short>(v11, v5, v10);
    std::wstring::wstring(v26, v12);
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(
      v9,
      v25,
      (__int64)v26);
    std::wstring::_Tidy_deallocate((__int64)v26);
    std::wstring::_Tidy_deallocate((__int64)v27);
    if ( *(_QWORD *)v25 == *v9 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x276, v13, v14, v25[0]);
    v15 = *(_QWORD *)v25 + 120LL;
    std::wstring::wstring((__int64)v26, v5);
    AuthorizationToken = CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
                           (__int64)v28,
                           v16,
                           (__int64)v26,
                           v15);
    *(_QWORD *)v25 = operator new(0xE8u);
    v20 = AuthorizationToken;
    v21 = *(_QWORD *)v25;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x281, v18, v19);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x282, v23, v24);
  }
  if ( *(_QWORD *)v25 == *(_QWORD *)qword_180039710 )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x270, v7, v8, v25[0]);
  v9 = (__int64 *)(*(_QWORD *)v25 + 64LL);
  std::operator+<unsigned short>(v27, qword_180039720);
  v10 = std::_WChar_traits<unsigned short>::length(v5);
}

```

## disassembly

```asm
0x180013660  mov     [rsp+arg_10], rbx
0x180013665  mov     [rsp+arg_18], rsi
0x18001366a  push    rdi
0x18001366b  sub     rsp, 170h
0x180013672  mov     rax, cs:__security_cookie
0x180013679  xor     rax, rsp
0x18001367c  mov     [rsp+178h+var_18], rax
0x180013684  mov     rdi, rdx
0x180013687  mov     rbx, rcx
0x18001368a  mov     qword ptr [rsp+178h+var_158], rcx; unsigned int
0x18001368f  lea     r8, qword_180039720
0x180013696  lea     rdx, [rsp+178h+var_158]
0x18001369b  mov     rcx, cs:qword_180039710
0x1800136a2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x1800136a7  mov     rax, qword ptr [rsp+178h+var_158]
0x1800136ac  mov     rcx, cs:qword_180039710
0x1800136b3  cmp     rax, [rcx]
0x1800136b6  jnz     short loc_1800136CA
0x1800136b8  mov     rcx, [rsp+178h]; this
0x1800136c0  mov     edx, 270h; void *
0x1800136c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800136ca  lea     rsi, [rax+40h]
0x1800136ce  lea     rdx, qword_180039720
0x1800136d5  lea     rcx, [rsp+178h+var_128]
0x1800136da  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800136df  mov     r9, rax
0x1800136e2  mov     rcx, rdi
0x1800136e5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800136ea  mov     r8, rax
0x1800136ed  mov     rdx, rdi
0x1800136f0  mov     rcx, r9
0x1800136f3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800136f8  mov     rdx, rax
0x1800136fb  lea     rcx, [rsp+178h+var_148]
0x180013700  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180013705  lea     r8, [rsp+178h+var_148]
0x18001370a  lea     rdx, [rsp+178h+var_158]
0x18001370f  mov     rcx, rsi
0x180013712  call    ??$find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@$0A@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(std::wstring const &)
0x180013717  lea     rcx, [rsp+178h+var_148]
0x18001371c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013721  nop
0x180013722  lea     rcx, [rsp+178h+var_128]
0x180013727  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001372c  mov     rax, qword ptr [rsp+178h+var_158]
0x180013731  cmp     rax, [rsi]
0x180013734  jnz     short loc_180013748
0x180013736  mov     rcx, [rsp+178h]; this
0x18001373e  mov     edx, 276h; void *
0x180013743  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013748  lea     rsi, [rax+78h]
0x18001374c  mov     rdx, rdi
0x18001374f  lea     rcx, [rsp+178h+var_148]
0x180013754  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013759  nop
0x18001375a  mov     r9, rsi
0x18001375d  lea     r8, [rsp+178h+var_148]
0x180013762  lea     rcx, [rsp+178h+var_108]
0x180013767  call    ?CreateAuthorizationToken@AuthorizationToken@Management@CodeIntegrity@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@5@@Z; CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(std::wstring const &,std::wstring const &,std::vector<uchar> const &)
0x18001376c  mov     rdi, rax
0x18001376f  mov     ecx, 0E8h; Size
0x180013774  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013779  mov     qword ptr [rsp+178h+var_158], rax
0x18001377e  mov     rdx, rdi
0x180013781  mov     rcx, rax
0x180013784  call    ??0AuthorizationToken@Management@CodeIntegrity@@QEAA@$$QEAV012@@Z; CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(CodeIntegrity::Management::AuthorizationToken &&)
0x180013789  nop
0x18001378a  mov     [rbx], rax
0x18001378d  lea     rcx, [rsp+178h+var_108]; this
0x180013792  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x180013797  nop
0x180013798  lea     rcx, [rsp+178h+var_148]
0x18001379d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800137a2  mov     rax, rbx
0x1800137a5  mov     rcx, [rsp+178h+var_18]
0x1800137ad  xor     rcx, rsp; StackCookie
0x1800137b0  call    __security_check_cookie
0x1800137b5  lea     r11, [rsp+178h+var_8]
0x1800137bd  mov     rbx, [r11+20h]
0x1800137c1  mov     rsi, [r11+28h]
0x1800137c5  mov     rsp, r11
0x1800137c8  pop     rdi
0x1800137c9  retn
```
