# CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar const *,unsigned __int64)

- ea: `0x180018834`
- end: `0x1800188b8`
- name: `?CreateAuthorizationToken@AuthorizationToken@Management@CodeIntegrity@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBE_K@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800103c8`
- `0x180011f20`
- `0x18001c714`

## callees

- `0x180002a90`
- `0x180005494`
- `0x1800184d8`
- `0x1800185a8`
- `0x180018834`
- `0x1800188c0`
- `0x180018b50`

## pseudocode

```c
__int64 __fastcall CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  void *v7[30]; // [rsp+30h] [rbp-108h] BYREF

  CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(
    (CodeIntegrity::Management::detail::SbcpTokenView *)v7,
    a2,
    a3,
    a4,
    a5);
  if ( v7[2] )
    CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData((CodeIntegrity::Management::AuthorizationToken *)v7);
  CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad((CodeIntegrity::Management::AuthorizationToken *)v7);
  CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(a1, (__int64)v7);
  CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(v7);
  return a1;
}

```

## disassembly

```asm
0x180018834  push    rbx
0x180018836  sub     rsp, 130h
0x18001883d  mov     rax, cs:__security_cookie
0x180018844  xor     rax, rsp
0x180018847  mov     [rsp+138h+var_18], rax
0x18001884f  mov     rbx, rcx
0x180018852  mov     rax, [rsp+138h+arg_20]
0x18001885a  mov     [rsp+138h+var_118], rax; __int64
0x18001885f  lea     rcx, [rsp+138h+var_108]; this
0x180018864  call    ??0AuthorizationToken@Management@CodeIntegrity@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBE_K@Z; CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(std::wstring const &,std::wstring const &,uchar const *,unsigned __int64)
0x180018869  cmp     [rsp+138h+var_F8], 0
0x18001886f  jz      short loc_18001887B
0x180018871  lea     rcx, [rsp+138h+var_108]; this
0x180018876  call    ?ValidateSpecificData@AuthorizationToken@Management@CodeIntegrity@@EEAAXXZ; CodeIntegrity::Management::AuthorizationToken::ValidateSpecificData(void)
0x18001887b  lea     rcx, [rsp+138h+var_108]; this
0x180018880  call    ?ReportTokenLoad@AuthorizationToken@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::AuthorizationToken::ReportTokenLoad(void)
0x180018885  lea     rdx, [rsp+138h+var_108]
0x18001888a  mov     rcx, rbx
0x18001888d  call    ??0AuthorizationToken@Management@CodeIntegrity@@QEAA@$$QEAV012@@Z; CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(CodeIntegrity::Management::AuthorizationToken &&)
0x180018892  lea     rcx, [rsp+138h+var_108]; this
0x180018897  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x18001889c  mov     rax, rbx
0x18001889f  mov     rcx, [rsp+138h+var_18]
0x1800188a7  xor     rcx, rsp; StackCookie
0x1800188aa  call    __security_check_cookie
0x1800188af  add     rsp, 130h
0x1800188b6  pop     rbx
0x1800188b7  retn
```
