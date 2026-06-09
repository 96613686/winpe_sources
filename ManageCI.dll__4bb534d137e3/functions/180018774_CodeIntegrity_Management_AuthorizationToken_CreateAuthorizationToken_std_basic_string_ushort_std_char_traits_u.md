# CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180018774`
- end: `0x18001882e`
- name: `?CreateAuthorizationToken@AuthorizationToken@Management@CodeIntegrity@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@5@@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013660`

## callees

- `0x180002a90`
- `0x180005494`
- `0x180010cdc`
- `0x180016780`
- `0x1800185a8`
- `0x180018774`
- `0x1800188c0`
- `0x180018b50`

## pseudocode

```c
__int64 __fastcall CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v6[17]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v7[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v8[3]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v9[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v10; // [rsp+F0h] [rbp-10h]
  char v11; // [rsp+100h] [rbp+0h]

  CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(
    (CodeIntegrity::Management::detail::SbcpTokenView *)v6,
    (__int64)qword_180039720,
    a3,
    a4);
  v6[0] = &CodeIntegrity::Management::AuthorizationToken::`vftable';
  std::vector<_GUID>::vector<_GUID>(v7);
  std::vector<_GUID>::vector<_GUID>(v8);
  std::vector<_GUID>::vector<_GUID>(v9);
  v10 = 0;
  v11 = 2;
  if ( v6[2] )
    CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData((CodeIntegrity::Management::AuthorizationToken *)v6);
  CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad((CodeIntegrity::Management::AuthorizationToken *)v6);
  CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(a1, (__int64)v6);
  CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(v6);
  return a1;
}

```

## disassembly

```asm
0x180018774  mov     [rsp-8+arg_8], rbx
0x180018779  push    rbp
0x18001877a  lea     rbp, [rsp-20h]
0x18001877f  sub     rsp, 120h
0x180018786  mov     rax, cs:__security_cookie
0x18001878d  xor     rax, rsp
0x180018790  mov     [rbp+20h+var_10], rax
0x180018794  mov     rbx, rcx
0x180018797  lea     rdx, qword_180039720
0x18001879e  lea     rcx, [rsp+120h+var_100]; this
0x1800187a3  call    ??0SbcpTokenView@detail@Management@CodeIntegrity@@IEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@5@@Z; CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(std::wstring const &,std::wstring const &,std::vector<uchar> const &)
0x1800187a8  lea     rax, ??_7AuthorizationToken@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::AuthorizationToken::`vftable'
0x1800187af  mov     [rsp+120h+var_100], rax
0x1800187b4  lea     rcx, [rbp+20h+var_78]
0x1800187b8  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800187bd  lea     rcx, [rbp+20h+var_60]
0x1800187c1  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800187c6  lea     rcx, [rbp+20h+var_48]
0x1800187ca  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800187cf  xorps   xmm0, xmm0
0x1800187d2  movdqa  [rbp+20h+var_30], xmm0
0x1800187d7  mov     [rbp+20h+var_20], 2
0x1800187db  cmp     [rsp+120h+var_F0], 0
0x1800187e1  jz      short loc_1800187ED
0x1800187e3  lea     rcx, [rsp+120h+var_100]; this
0x1800187e8  call    ?ValidateSpecificData@AuthorizationToken@Management@CodeIntegrity@@EEAAXXZ; CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData(void)
0x1800187ed  lea     rcx, [rsp+120h+var_100]; this
0x1800187f2  call    ?ReportTokenLoad@AuthorizationToken@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad(void)
0x1800187f7  lea     rdx, [rsp+120h+var_100]
0x1800187fc  mov     rcx, rbx
0x1800187ff  call    ??0AuthorizationToken@Management@CodeIntegrity@@QEAA@$$QEAV012@@Z; CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(CodeIntegrity::Management::AuthorizationToken &&)
0x180018804  lea     rcx, [rsp+120h+var_100]; this
0x180018809  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x18001880e  mov     rax, rbx
0x180018811  mov     rcx, [rbp+20h+var_10]
0x180018815  xor     rcx, rsp; StackCookie
0x180018818  call    __security_check_cookie
0x18001881d  mov     rbx, [rsp+120h+arg_8]
0x180018825  add     rsp, 120h
0x18001882c  pop     rbp
0x18001882d  retn
```
