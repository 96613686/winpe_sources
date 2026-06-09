# _Windows::UsoDatabase::BackupOnlineDatabase_::_3_::_lambda_1_::operator()

- ea: `0x14018e82c`
- end: `0x14018ea9c`
- name: `_Windows::UsoDatabase::BackupOnlineDatabase_::_3_::_lambda_1_::operator()`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14018e380`

## callees

- `0x140040184`
- `0x1400407f8`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x140057920`
- `0x1401192c4`
- `0x14018c578`
- `0x14018d304`
- `0x14018e82c`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_backup_step` at `0x14018e9e9`
- `winsqlite3!sqlite3_backup_step` at `0x14018e9e9`
- `winsqlite3!sqlite3_errcode` at `0x14018e9fc`
- `winsqlite3!sqlite3_errcode` at `0x14018e9fc`
- `winsqlite3!sqlite3_backup_finish` at `0x14018e9f2`
- `winsqlite3!sqlite3_backup_finish` at `0x14018e9f2`
- `winsqlite3!sqlite3_open16` at `0x14018e908`
- `winsqlite3!sqlite3_open16` at `0x14018e908`
- `winsqlite3!sqlite3_backup_init` at `0x14018e9d5`
- `winsqlite3!sqlite3_backup_init` at `0x14018e9d5`
- `winsqlite3!sqlite3_db_config` at `0x14018e93d`
- `winsqlite3!sqlite3_db_config` at `0x14018e9a4`
- `winsqlite3!sqlite3_db_config` at `0x14018e93d`
- `winsqlite3!sqlite3_db_config` at `0x14018e9a4`

## string_xrefs

- `0x14018ea74`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018ea8a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::UsoDatabase::BackupOnlineDatabase_::_3_::_lambda_1_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  char *traits_1_unsigned_char; // rax
  const char *v4; // r9
  __int64 v5; // rax
  _QWORD *v6; // rcx
  int v7; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  char *v11; // rax
  const char *v12; // r9
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rdx
  const wchar_t *v20; // [rsp+20h] [rbp-60h] BYREF
  __int64 v21; // [rsp+28h] [rbp-58h]
  _BYTE v22[32]; // [rsp+30h] [rbp-50h] BYREF
  struct sqlite3 *v23; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  std::wstring::wstring(v24, *(_QWORD *)a1 + 8LL);
  v20 = L".bak";
  v21 = 4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v22, &v20);
  std::filesystem::path::replace_extension((std::filesystem::path *)v24, (const struct std::filesystem::path *)v22);
  std::wstring::~wstring(v22, v2);
  traits_1_unsigned_char = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                                     "VACUUM",
                                     byte_14041AF53,
                                     0);
  if ( traits_1_unsigned_char == byte_14041AF53 || (v5 = traits_1_unsigned_char - "VACUUM", v5 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v4);
  v20 = (const wchar_t *)"VACUUM";
  v21 = v5;
  Windows::SqlExec(*(_QWORD *)a1 + 40LL, &v20);
  v23 = 0;
  v6 = v24;
  if ( v24[3] > 7u )
    v6 = (_QWORD *)v24[0];
  v7 = sqlite3_open16(v6, &v23);
  v8 = (unsigned __int16)v7 | 0x87AF0000;
  if ( v7 <= 0 )
    v8 = v7;
  if ( v8 < 0 )
  {
    v9 = 498;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    goto LABEL_27;
  }
  v10 = sqlite3_db_config(v23, 1009, 1);
  v8 = (unsigned __int16)v10 | 0x87AF0000;
  if ( v10 <= 0 )
    v8 = v10;
  if ( v8 < 0 )
  {
    v9 = 501;
    goto LABEL_25;
  }
  v11 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                  "VACUUM",
                  byte_14041AF53,
                  0);
  if ( v11 == byte_14041AF53 || (v13 = v11 - "VACUUM", v13 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v12);
  v20 = (const wchar_t *)"VACUUM";
  v21 = v13;
  Windows::SqlExec(&v23, &v20);
  v14 = sqlite3_db_config(v23, 1009, 0);
  v8 = (unsigned __int16)v14 | 0x87AF0000;
  if ( v14 <= 0 )
    v8 = v14;
  if ( v8 < 0 )
  {
    v9 = 503;
    goto LABEL_25;
  }
  v15 = sqlite3_backup_init(v23, "main", *(_QWORD *)(*(_QWORD *)a1 + 40LL), "main");
  v16 = v15;
  if ( v15 )
  {
    sqlite3_backup_step(v15, 0xFFFFFFFFLL);
    sqlite3_backup_finish(v16);
  }
  v17 = sqlite3_errcode(v23);
  v8 = (unsigned __int16)v17 | 0x87AF0000;
  if ( v17 <= 0 )
    v8 = v17;
  if ( v8 < 0 )
  {
    v9 = 511;
    goto LABEL_25;
  }
  v8 = 0;
LABEL_27:
  if ( v23 )
    Windows::SqliteDatabaseClose(v23);
  std::wstring::~wstring(v24, v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14018e82c  mov     [rsp-18h+arg_8], rbx
0x14018e831  mov     [rsp-18h+arg_10], rsi
0x14018e836  mov     [rsp-18h+arg_18], rdi
0x14018e83b  push    rbp
0x14018e83c  push    r14
0x14018e83e  push    r15
0x14018e840  mov     rbp, rsp
0x14018e843  sub     rsp, 80h
0x14018e84a  mov     rax, cs:__security_cookie
0x14018e851  xor     rax, rsp
0x14018e854  mov     [rbp+var_8], rax
0x14018e858  mov     rdi, rcx
0x14018e85b  mov     rdx, [rcx]
0x14018e85e  add     rdx, 8
0x14018e862  lea     rcx, [rbp+var_28]
0x14018e866  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14018e86b  nop
0x14018e86c  lea     rax, aBak; ".bak"
0x14018e873  mov     [rbp+var_60], rax
0x14018e877  mov     [rbp+var_58], 4
0x14018e87f  lea     rdx, [rbp+var_60]
0x14018e883  lea     rcx, [rbp+var_50]
0x14018e887  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14018e88c  nop
0x14018e88d  lea     rdx, [rbp+var_50]; struct std::filesystem::path *
0x14018e891  lea     rcx, [rbp+var_28]; this
0x14018e895  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@AEBV123@@Z; std::filesystem::path::replace_extension(std::filesystem::path const &)
0x14018e89a  nop
0x14018e89b  lea     rcx, [rbp+var_50]
0x14018e89f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018e8a4  xor     r8d, r8d
0x14018e8a7  lea     r14, byte_14041AF53
0x14018e8ae  mov     rdx, r14
0x14018e8b1  lea     rsi, aVacuum; "VACUUM"
0x14018e8b8  mov     rcx, rsi
0x14018e8bb  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018e8c0  cmp     rax, r14
0x14018e8c3  jz      loc_14018EA86
0x14018e8c9  sub     rax, rsi
0x14018e8cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018e8d0  jz      loc_14018EA86
0x14018e8d6  mov     [rbp+var_60], rsi
0x14018e8da  mov     [rbp+var_58], rax
0x14018e8de  mov     rcx, [rdi]
0x14018e8e1  add     rcx, 28h ; '('
0x14018e8e5  lea     rdx, [rbp+var_60]
0x14018e8e9  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018e8ee  mov     [rbp+var_30], 0
0x14018e8f6  lea     rcx, [rbp+var_28]
0x14018e8fa  cmp     [rbp+var_10], 7
0x14018e8ff  cmova   rcx, [rbp+var_28]
0x14018e904  lea     rdx, [rbp+var_30]
0x14018e908  call    cs:__imp_sqlite3_open16
0x14018e90e  movzx   ebx, ax
0x14018e911  mov     r15d, 87AF0000h
0x14018e917  or      ebx, r15d
0x14018e91a  test    eax, eax
0x14018e91c  cmovle  ebx, eax
0x14018e91f  test    ebx, ebx
0x14018e921  jns     short loc_14018E92D
0x14018e923  mov     edx, 1F2h
0x14018e928  jmp     loc_14018EA16
0x14018e92d  xor     r9d, r9d
0x14018e930  mov     edx, 3F1h
0x14018e935  lea     r8d, [r9+1]
0x14018e939  mov     rcx, [rbp+var_30]
0x14018e93d  call    cs:__imp_sqlite3_db_config
0x14018e943  movzx   ebx, ax
0x14018e946  or      ebx, r15d
0x14018e949  test    eax, eax
0x14018e94b  cmovle  ebx, eax
0x14018e94e  test    ebx, ebx
0x14018e950  jns     short loc_14018E95C
0x14018e952  mov     edx, 1F5h
0x14018e957  jmp     loc_14018EA16
0x14018e95c  xor     r8d, r8d
0x14018e95f  mov     rdx, r14
0x14018e962  mov     rcx, rsi
0x14018e965  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018e96a  cmp     rax, r14
0x14018e96d  jz      loc_14018EA70
0x14018e973  sub     rax, rsi
0x14018e976  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018e97a  jz      loc_14018EA70
0x14018e980  mov     [rbp+var_60], rsi
0x14018e984  mov     [rbp+var_58], rax
0x14018e988  lea     rdx, [rbp+var_60]
0x14018e98c  lea     rcx, [rbp+var_30]
0x14018e990  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018e995  xor     r9d, r9d
0x14018e998  xor     r8d, r8d
0x14018e99b  mov     edx, 3F1h
0x14018e9a0  mov     rcx, [rbp+var_30]
0x14018e9a4  call    cs:__imp_sqlite3_db_config
0x14018e9aa  movzx   ebx, ax
0x14018e9ad  or      ebx, r15d
0x14018e9b0  test    eax, eax
0x14018e9b2  cmovle  ebx, eax
0x14018e9b5  test    ebx, ebx
0x14018e9b7  jns     short loc_14018E9C0
0x14018e9b9  mov     edx, 1F7h
0x14018e9be  jmp     short loc_14018EA16
0x14018e9c0  mov     r8, [rdi]
0x14018e9c3  lea     rdx, aMain; "main"
0x14018e9ca  mov     r9, rdx
0x14018e9cd  mov     r8, [r8+28h]
0x14018e9d1  mov     rcx, [rbp+var_30]
0x14018e9d5  call    cs:__imp_sqlite3_backup_init
0x14018e9db  mov     rbx, rax
0x14018e9de  test    rax, rax
0x14018e9e1  jz      short loc_14018E9F8
0x14018e9e3  or      edx, 0FFFFFFFFh
0x14018e9e6  mov     rcx, rax
0x14018e9e9  call    cs:__imp_sqlite3_backup_step
0x14018e9ef  mov     rcx, rbx
0x14018e9f2  call    cs:__imp_sqlite3_backup_finish
0x14018e9f8  mov     rcx, [rbp+var_30]
0x14018e9fc  call    cs:__imp_sqlite3_errcode
0x14018ea02  movzx   ebx, ax
0x14018ea05  or      ebx, r15d
0x14018ea08  test    eax, eax
0x14018ea0a  cmovle  ebx, eax
0x14018ea0d  test    ebx, ebx
0x14018ea0f  jns     short loc_14018EA2B
0x14018ea11  mov     edx, 1FFh; void *
0x14018ea16  mov     rcx, [rbp+18h]; this
0x14018ea1a  mov     r9d, ebx; char *
0x14018ea1d  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018ea24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018ea29  jmp     short loc_14018EA2D
0x14018ea2b  xor     ebx, ebx
0x14018ea2d  mov     rcx, [rbp+var_30]; struct sqlite3 *
0x14018ea31  test    rcx, rcx
0x14018ea34  jz      short loc_14018EA3C
0x14018ea36  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018ea3b  nop
0x14018ea3c  lea     rcx, [rbp+var_28]
0x14018ea40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018ea45  mov     eax, ebx
0x14018ea47  mov     rcx, [rbp+var_8]
0x14018ea4b  xor     rcx, rsp; StackCookie
0x14018ea4e  call    __security_check_cookie
0x14018ea53  lea     r11, [rsp+80h+var_s0]
0x14018ea5b  mov     rbx, [r11+28h]
0x14018ea5f  mov     rsi, [r11+30h]
0x14018ea63  mov     rdi, [r11+38h]
0x14018ea67  mov     rsp, r11
0x14018ea6a  pop     r15
0x14018ea6c  pop     r14
0x14018ea6e  pop     rbp
0x14018ea6f  retn
0x14018ea70  mov     rcx, [rbp+18h]; this
0x14018ea74  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018ea7b  mov     edx, 0C9h; void *
0x14018ea80  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14018ea86  mov     rcx, [rbp+18h]; this
0x14018ea8a  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018ea91  mov     edx, 0C9h; void *
0x14018ea96  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
