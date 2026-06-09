# BrainSettings::Load(std::filesystem::path,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>)

- ea: `0x180035cb0`
- end: `0x180035fd9`
- name: `?Load@BrainSettings@@CA?AVvalue@json@web@@Vpath@filesystem@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@7@@Z`
- size: `809`
- prototype: `__int64 __fastcall(web::json::value *this, struct std::error_code *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180038884`

## callees

- `0x18000f914`
- `0x180017784`
- `0x1800240ac`
- `0x180024a44`
- `0x180027228`
- `0x1800286d0`
- `0x180029644`
- `0x1800296cc`
- `0x1800298d4`
- `0x18002dd88`
- `0x180035cb0`
- `0x18003d580`
- `0x18003d5e0`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
web::json::value *__fastcall BrainSettings::Load(
        web::json::value *this,
        struct std::error_code *a2,
        struct std::error_code *a3)
{
  struct std::error_code *v3; // rdi
  struct std::error_code *v4; // rsi
  web::json::value *v5; // r14
  bool v6; // cl
  const struct std::filesystem::path *v7; // r9
  bool v8; // al
  const char *v9; // rdx
  __int64 v10; // rax
  _QWORD *v12; // rax
  const wchar_t *v13; // r8
  const char *v14; // rax
  __int64 *v15; // rbp
  wil *v16; // rcx
  int v17; // eax
  const wchar_t *v18; // rbx
  const wchar_t *v19; // r8
  __int64 *v20; // rdx
  __int64 v21; // [rsp+0h] [rbp-1B8h] BYREF
  _BOOL8 v22; // [rsp+30h] [rbp-188h]
  char v23[8]; // [rsp+38h] [rbp-180h] BYREF
  void ***v24; // [rsp+40h] [rbp-178h]
  web::json::value *v25; // [rsp+48h] [rbp-170h]
  struct std::error_code *v26; // [rsp+58h] [rbp-160h]
  struct std::error_code *v27; // [rsp+60h] [rbp-158h]
  int v28; // [rsp+6Ch] [rbp-14Ch]
  _QWORD v29[34]; // [rsp+70h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  v25 = this;
  v26 = a2;
  v27 = a3;
  LOBYTE(v22) = 0;
  *(_QWORD *)v23 = 0;
  v24 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v6 = std::filesystem::exists(a2, (const struct std::filesystem::path *)v23, a3);
  if ( *(_DWORD *)v23 )
  {
    try
    {
      std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v23, v4, v7);
    }
    catch ( ... )
    {
      v20 = &v21;
      v15 = v20;
      v17 = wil::ResultFromCaughtException(v16);
      v18 = (const wchar_t *)v15[11];
      v19 = v18;
      if ( *((_QWORD *)v18 + 3) > 7u )
        v19 = *(const wchar_t **)v18;
      uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(
        "Unable to check if OneSettings JSON file exist:",
        v17,
        v19);
      if ( *((_QWORD *)v18 + 3) > 7u )
        v18 = *(const wchar_t **)v18;
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        (wil::details::in1diag3 *)v15[55],
        (void *)0x4E,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
        "Unable to check if OneSettings JSON file exist: %s",
        (const char *)v18);
      v8 = v22;
      v5 = v25;
      v4 = v26;
      v3 = v27;
      goto LABEL_3;
    }
  }
  v8 = v6;
  LOBYTE(v22) = v6;
LABEL_3:
  if ( v8 )
  {
    memset(v29, 0, sizeof(v29));
    v9 = (const char *)v4;
    if ( *((_QWORD *)v4 + 3) > 7u )
      v9 = *(const char **)v4;
    std::wifstream::wifstream(v29, v9);
    *(_QWORD *)((char *)v29 + *(int *)(v29[0] + 4LL)) = &std::wifstream::`vftable';
    *(int *)((char *)&v28 + *(int *)(v29[0] + 4LL)) = *(_DWORD *)(v29[0] + 4LL) - 176;
    *(_QWORD *)v23 = 0;
    web::json::value::parse(v23, (__int64)v29);
    if ( !*((_BYTE *)v3 + 32) )
    {
      v10 = *(_QWORD *)v23;
      *(_QWORD *)v23 = 0;
      *(_QWORD *)v5 = v10;
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v29[22]);
      v29[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v29[22]);
      std::wstring::_Tidy_deallocate(v4);
      if ( *((_BYTE *)v3 + 32) )
        std::wstring::_Tidy_deallocate(v3);
      return v5;
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, struct std::error_code *))(**(_QWORD **)v23 + 8LL))(
           *(_QWORD *)v23,
           v3) )
    {
      if ( !*((_BYTE *)v3 + 32) )
        std::_Throw_bad_optional_access();
      v12 = (_QWORD *)web::json::value::at(v23, v3);
      (**(void (__fastcall ***)(_QWORD, web::json::value *))*v12)(*v12, v5);
      if ( *(_QWORD *)v23 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v23 + 192LL))(*(_QWORD *)v23, 1);
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v29[22]);
      v29[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v29[22]);
      std::wstring::_Tidy_deallocate(v4);
      if ( *((_BYTE *)v3 + 32) )
        std::wstring::_Tidy_deallocate(v3);
      return v5;
    }
    if ( !*((_BYTE *)v3 + 32) )
      std::_Throw_bad_optional_access();
    v13 = (const wchar_t *)v3;
    if ( *((_QWORD *)v3 + 3) > 7u )
      v13 = *(const wchar_t **)v3;
    uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure("Expected root node not found:", -2147023886, v13);
    v14 = (const char *)v4;
    if ( *((_QWORD *)v4 + 3) > 7u )
      v14 = *(const char **)v4;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x64,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
      (const char *)0x800703F2LL,
      (int)"Expected root node not found: %s",
      v14,
      v22);
    if ( *(_QWORD *)v23 )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v23 + 192LL))(*(_QWORD *)v23, 1);
    std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v29[22]);
    v29[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v29[22]);
  }
  web::json::value::value(v5);
  std::wstring::_Tidy_deallocate(v4);
  if ( *((_BYTE *)v3 + 32) )
    std::wstring::_Tidy_deallocate(v3);
  return v5;
}

```

## disassembly

```asm
0x180035cb0  push    rbx
0x180035cb2  push    rsi
0x180035cb3  push    rdi
0x180035cb4  push    r14
0x180035cb6  push    r15
0x180035cb8  sub     rsp, 190h
0x180035cbf  mov     rax, cs:__security_cookie
0x180035cc6  xor     rax, rsp
0x180035cc9  mov     [rsp+1B8h+var_38], rax
0x180035cd1  mov     rdi, r8
0x180035cd4  mov     rsi, rdx
0x180035cd7  mov     r14, rcx
0x180035cda  mov     [rsp+1B8h+var_170], rcx
0x180035cdf  mov     [rsp+1B8h+var_160], rdx
0x180035ce4  mov     [rsp+1B8h+var_158], r8
0x180035ce9  xor     ebx, ebx
0x180035ceb  mov     byte ptr [rsp+1B8h+var_188], bl
0x180035cef  mov     qword ptr [rsp+1B8h+var_180], rbx
0x180035cf4  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180035cfb  mov     [rsp+1B8h+var_178], rax
0x180035d00  lea     rdx, [rsp+1B8h+var_180]; struct std::filesystem::path *
0x180035d05  mov     rcx, rsi; this
0x180035d08  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180035d0d  mov     cl, al
0x180035d0f  cmp     dword ptr [rsp+1B8h+var_180], ebx
0x180035d13  jnz     loc_180035FB8
0x180035d19  movzx   eax, bl
0x180035d1c  mov     r15d, 1
0x180035d22  test    cl, cl
0x180035d24  cmovnz  eax, r15d
0x180035d28  mov     byte ptr [rsp+1B8h+var_188], al
0x180035d2c  jmp     short loc_180035D47
0x180035d2e  xor     ebx, ebx
0x180035d30  lea     r15d, [rbx+1]
0x180035d34  mov     al, byte ptr [rsp+1B8h+var_188]
0x180035d38  mov     r14, [rsp+1B8h+var_170]
0x180035d3d  mov     rsi, [rsp+1B8h+var_160]
0x180035d42  mov     rdi, [rsp+1B8h+var_158]
0x180035d47  test    al, al
0x180035d49  jz      loc_180035F77
0x180035d4f  xor     edx, edx; Val
0x180035d51  mov     r8d, 110h; Size
0x180035d57  lea     rcx, [rsp+1B8h+var_148]; void *
0x180035d5c  call    memset
0x180035d61  mov     rdx, rsi
0x180035d64  cmp     qword ptr [rsi+18h], 7
0x180035d69  jbe     short loc_180035D6E
0x180035d6b  mov     rdx, [rsi]
0x180035d6e  lea     rcx, [rsp+1B8h+var_148]
0x180035d73  call    ??0?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@QEAA@PEB_WHH@Z; std::wifstream::wifstream(wchar_t const *,int,int)
0x180035d78  mov     rax, [rsp+1B8h+var_148]
0x180035d7d  movsxd  rcx, dword ptr [rax+4]
0x180035d81  lea     rax, ??_7?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wifstream::`vftable'
0x180035d88  mov     [rsp+rcx+1B8h+var_148], rax
0x180035d8d  mov     rax, [rsp+1B8h+var_148]
0x180035d92  movsxd  rcx, dword ptr [rax+4]
0x180035d96  lea     edx, [rcx-0B0h]
0x180035d9c  mov     [rsp+rcx+1B8h+var_14C], edx
0x180035da0  mov     qword ptr [rsp+1B8h+var_180], rbx
0x180035da5  lea     rdx, [rsp+1B8h+var_148]
0x180035daa  lea     rcx, [rsp+1B8h+var_180]
0x180035daf  call    ?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@_WU?$char_traits@_W@std@@@std@@@Z; web::json::value::parse(std::wistream &)
0x180035db4  nop
0x180035db5  cmp     [rdi+20h], bl
0x180035db8  jnz     short loc_180035E0F
0x180035dba  mov     rax, qword ptr [rsp+1B8h+var_180]
0x180035dbf  mov     qword ptr [rsp+1B8h+var_180], rbx
0x180035dc4  mov     [r14], rax
0x180035dc7  lea     rcx, [rsp+1B8h+var_98]
0x180035dcf  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x180035dd4  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180035ddb  mov     [rsp+1B8h+var_98], rax
0x180035de3  lea     rcx, [rsp+1B8h+var_98]; this
0x180035deb  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x180035df0  nop
0x180035df1  mov     rcx, rsi
0x180035df4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035df9  nop
0x180035dfa  cmp     [rdi+20h], bl
0x180035dfd  jz      short loc_180035E07
0x180035dff  mov     rcx, rdi
0x180035e02  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035e07  mov     rax, r14
0x180035e0a  jmp     loc_180035F99
0x180035e0f  mov     rcx, qword ptr [rsp+1B8h+var_180]
0x180035e14  mov     rax, [rcx]
0x180035e17  mov     rdx, rdi
0x180035e1a  mov     rax, [rax+8]
0x180035e1e  call    _guard_dispatch_icall
0x180035e23  test    al, al
0x180035e25  jz      loc_180035EB8
0x180035e2b  cmp     [rdi+20h], bl
0x180035e2e  jz      loc_180035FCD
0x180035e34  mov     rdx, rdi
0x180035e37  lea     rcx, [rsp+1B8h+var_180]
0x180035e3c  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180035e41  mov     rcx, [rax]
0x180035e44  mov     rax, [rcx]
0x180035e47  mov     rdx, r14
0x180035e4a  mov     rax, [rax]
0x180035e4d  call    _guard_dispatch_icall
0x180035e52  nop
0x180035e53  mov     rcx, qword ptr [rsp+1B8h+var_180]
0x180035e58  test    rcx, rcx
0x180035e5b  jz      short loc_180035E70
0x180035e5d  mov     rax, [rcx]
0x180035e60  mov     edx, r15d
0x180035e63  mov     rax, [rax+0C0h]
0x180035e6a  call    _guard_dispatch_icall
0x180035e6f  nop
0x180035e70  lea     rcx, [rsp+1B8h+var_98]
0x180035e78  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x180035e7d  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180035e84  mov     [rsp+1B8h+var_98], rax
0x180035e8c  lea     rcx, [rsp+1B8h+var_98]; this
0x180035e94  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x180035e99  nop
0x180035e9a  mov     rcx, rsi
0x180035e9d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ea2  nop
0x180035ea3  cmp     [rdi+20h], bl
0x180035ea6  jz      short loc_180035EB0
0x180035ea8  mov     rcx, rdi
0x180035eab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035eb0  mov     rax, r14
0x180035eb3  jmp     loc_180035F99
0x180035eb8  cmp     [rdi+20h], bl
0x180035ebb  jz      loc_180035FD2
0x180035ec1  mov     r8, rdi
0x180035ec4  cmp     qword ptr [rdi+18h], 7
0x180035ec9  jbe     short loc_180035ECE
0x180035ecb  mov     r8, [rdi]; wchar_t *
0x180035ece  mov     edx, 800703F2h; int
0x180035ed3  lea     rcx, aExpectedRootNo_0; "Expected root node not found:"
0x180035eda  call    ?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z; uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)
0x180035edf  mov     rax, rsi
0x180035ee2  cmp     qword ptr [rsi+18h], 7
0x180035ee7  jbe     short loc_180035EEC
0x180035ee9  mov     rax, [rsi]
0x180035eec  mov     rcx, [rsp+1B8h]; this
0x180035ef4  mov     [rsp+1B8h+var_190], rax; char *
0x180035ef9  lea     rax, aExpectedRootNo; "Expected root node not found: %s"
0x180035f00  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x180035f05  mov     r9d, 800703F2h; char *
0x180035f0b  lea     r8, aCW1SSrcBrainLi_1; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainSe"...
0x180035f12  mov     edx, 64h ; 'd'; void *
0x180035f17  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035f1c  nop
0x180035f1d  mov     rcx, qword ptr [rsp+1B8h+var_180]
0x180035f22  test    rcx, rcx
0x180035f25  jz      short loc_180035F3A
0x180035f27  mov     rax, [rcx]
0x180035f2a  mov     edx, r15d
0x180035f2d  mov     rax, [rax+0C0h]
0x180035f34  call    _guard_dispatch_icall
0x180035f39  nop
0x180035f3a  lea     rcx, [rsp+1B8h+var_98]
0x180035f42  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x180035f47  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180035f4e  mov     [rsp+1B8h+var_98], rax
0x180035f56  lea     rcx, [rsp+1B8h+var_98]; this
0x180035f5e  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x180035f63  nop
0x180035f64  jmp     short loc_180035F77
0x180035f66  xor     ebx, ebx
0x180035f68  mov     r14, [rsp+1B8h+var_170]
0x180035f6d  mov     rsi, [rsp+1B8h+var_160]
0x180035f72  mov     rdi, [rsp+1B8h+var_158]
0x180035f77  mov     rcx, r14; this
0x180035f7a  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180035f7f  nop
0x180035f80  mov     rcx, rsi
0x180035f83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035f88  nop
0x180035f89  cmp     [rdi+20h], bl
0x180035f8c  jz      short loc_180035F96
0x180035f8e  mov     rcx, rdi
0x180035f91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035f96  mov     rax, r14
0x180035f99  mov     rcx, [rsp+1B8h+var_38]
0x180035fa1  xor     rcx, rsp; StackCookie
0x180035fa4  call    __security_check_cookie
0x180035fa9  add     rsp, 190h
0x180035fb0  pop     r15
0x180035fb2  pop     r14
0x180035fb4  pop     rdi
0x180035fb5  pop     rsi
0x180035fb6  pop     rbx
0x180035fb7  retn
0x180035fb8  mov     r8, rsi; struct std::error_code *
0x180035fbb  lea     rdx, [rsp+1B8h+var_180]; char *
0x180035fc0  lea     rcx, aExists; "exists"
0x180035fc7  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x180035fcd  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180035fd2  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
