# winrt::Windows::Management::Update::implementation::ValidateFolderPath(winrt::hstring const &)

- ea: `0x1800220ac`
- end: `0x1800222be`
- name: `?ValidateFolderPath@implementation@Update@Management@Windows@winrt@@YAXAEBUhstring@5@@Z`
- size: `530`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation *__hidden this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180021e90`

## callees

- `0x1800028f0`
- `0x18000340c`
- `0x180011464`
- `0x180014eb4`
- `0x180017bec`
- `0x180018238`
- `0x18001c81c`
- `0x1800220ac`
- `0x180022478`
- `0x180022794`
- `0x1800227ec`
- `0x180022dc4`

## string_xrefs

- `0x180022246`: `Folder path cannot be empty`
- `0x180022283`: `Specified folder path does not exist`
- `0x1800221f4`: `Specified path is not a directory`
- `0x1800221b7`: `Specified directory is empty`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::ValidateFolderPath(
        winrt::Windows::Management::Update::implementation *this,
        const struct winrt::hstring *a2)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  _DWORD *any_status; // rcx
  const struct std::filesystem::path *v5; // r9
  __int64 v6; // rdx
  bool v7; // al
  unsigned int *v8; // rax
  __int64 v9; // rcx
  const struct std::filesystem::path *v10; // rdx
  __int64 v11; // rdx
  const struct winrt::impl::slim_source_location *v12; // rbx
  const struct winrt::impl::slim_source_location *v13; // rbx
  const struct winrt::impl::slim_source_location *v14; // rbx
  const struct winrt::impl::slim_source_location *v15; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-29h] BYREF
  void ***v17; // [rsp+28h] [rbp-21h]
  _BYTE v18[24]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp+7h] BYREF
  __int128 v20; // [rsp+70h] [rbp+27h] BYREF
  __int64 v21; // [rsp+80h] [rbp+37h]
  __int64 v22; // [rsp+88h] [rbp+3Fh]

  if ( !*(_QWORD *)this )
  {
    v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, a2);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, L"Folder path cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v19,
      v14);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v2 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(v2 + 2 * v3) );
  v20 = 0;
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v20, v2, v3);
  any_status = (_DWORD *)std::filesystem::_Get_any_status(v18, &v20);
  v6 = (unsigned int)any_status[2];
  pExceptionObject = any_status[2];
  v17 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( *any_status )
  {
    v7 = *any_status != 1;
  }
  else
  {
    v7 = 0;
    if ( (_DWORD)v6 )
      std::filesystem::_Throw_fs_error(
        (std::filesystem *)"exists",
        (const char *)&pExceptionObject,
        (const struct std::error_code *)&v20,
        v5);
  }
  if ( !v7 )
  {
    v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, v6);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, L"Specified folder path does not exist");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v19,
      v15);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v8 = (unsigned int *)std::filesystem::_Get_any_status(v18, &v20);
  v9 = *v8;
  v10 = (const struct std::filesystem::path *)v8[2];
  if ( (_DWORD)v10 )
  {
    if ( (((_DWORD)v9 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error(v9, v10, &v20);
LABEL_16:
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, v10);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, L"Specified path is not a directory");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v19,
      v13);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  if ( (_DWORD)v9 != 3 )
    goto LABEL_16;
  if ( std::filesystem::is_empty((std::filesystem *)&v20, v10) )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18, v11);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, L"Specified directory is empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v19,
      v12);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  std::wstring::_Tidy_deallocate(&v20);
}

```

## disassembly

```asm
0x1800220ac  mov     [rsp-8+arg_0], rbx
0x1800220b1  push    rbp
0x1800220b2  lea     rbp, [rsp-57h]
0x1800220b7  sub     rsp, 0A0h
0x1800220be  mov     rax, cs:__security_cookie
0x1800220c5  xor     rax, rsp
0x1800220c8  mov     [rbp+57h+var_10], rax
0x1800220cc  xor     ebx, ebx
0x1800220ce  mov     rax, [rcx]
0x1800220d1  test    rax, rax
0x1800220d4  jz      loc_18002223A
0x1800220da  mov     rdx, [rax+10h]
0x1800220de  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800220e2  inc     r8
0x1800220e5  cmp     [rdx+r8*2], bx
0x1800220ea  jnz     short loc_1800220E2
0x1800220ec  xorps   xmm0, xmm0
0x1800220ef  movups  [rbp+57h+var_30], xmm0
0x1800220f3  mov     [rbp+57h+var_20], rbx
0x1800220f7  mov     [rbp+57h+var_18], rbx
0x1800220fb  lea     rcx, [rbp+57h+var_30]
0x1800220ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022104  nop
0x180022105  lea     rdx, [rbp+57h+var_30]
0x180022109  lea     rcx, [rbp+57h+var_68]
0x18002210d  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x180022112  mov     rcx, rax
0x180022115  mov     edx, [rax+8]
0x180022118  mov     [rbp+57h+pExceptionObject], edx
0x18002211b  mov     eax, [rbp+57h+var_7C]
0x18002211e  mov     [rbp+57h+var_7C], eax
0x180022121  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180022128  mov     [rbp+57h+var_78], rax
0x18002212c  cmp     [rcx], ebx
0x18002212e  jz      short loc_180022167
0x180022130  cmp     dword ptr [rcx], 1
0x180022133  setnz   al
0x180022136  test    al, al
0x180022138  jz      loc_180022277
0x18002213e  lea     rdx, [rbp+57h+var_30]
0x180022142  lea     rcx, [rbp+57h+var_68]
0x180022146  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x18002214b  mov     ecx, [rax]
0x18002214d  mov     edx, [rax+8]; struct std::filesystem::path *
0x180022150  test    edx, edx
0x180022152  jz      short loc_180022173
0x180022154  lea     eax, [rcx-1]
0x180022157  test    eax, 0FFFFFFF7h
0x18002215c  jz      loc_1800221E8
0x180022162  jmp     loc_1800222B4
0x180022167  mov     al, bl
0x180022169  test    edx, edx
0x18002216b  jnz     loc_180022225
0x180022171  jmp     short loc_180022136
0x180022173  cmp     ecx, 3
0x180022176  jnz     short loc_1800221E8
0x180022178  lea     rcx, [rbp+57h+var_30]; this
0x18002217c  call    ?is_empty@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::is_empty(std::filesystem::path const &)
0x180022181  test    al, al
0x180022183  jnz     short loc_1800221AB
0x180022185  lea     rcx, [rbp+57h+var_30]
0x180022189  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002218e  mov     rcx, [rbp+57h+var_10]
0x180022192  xor     rcx, rsp; StackCookie
0x180022195  call    __security_check_cookie
0x18002219a  mov     rbx, [rsp+0A0h+arg_0]
0x1800221a2  add     rsp, 0A0h
0x1800221a9  pop     rbp
0x1800221aa  retn
0x1800221ab  lea     rcx, [rbp+57h+var_68]
0x1800221af  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800221b4  mov     rbx, rax
0x1800221b7  lea     rdx, aSpecifiedDirec; "Specified directory is empty"
0x1800221be  lea     rcx, [rbp+57h+var_50]; this
0x1800221c2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800221c7  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800221ca  lea     rdx, [rbp+57h+var_50]; struct winrt::param::hstring *
0x1800221ce  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800221d2  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800221d7  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800221de  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800221e2  call    _CxxThrowException_0
0x1800221e8  lea     rcx, [rbp+57h+var_68]
0x1800221ec  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800221f1  mov     rbx, rax
0x1800221f4  lea     rdx, aSpecifiedPathI; "Specified path is not a directory"
0x1800221fb  lea     rcx, [rbp+57h+var_50]; this
0x1800221ff  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022204  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180022207  lea     rdx, [rbp+57h+var_50]; struct winrt::param::hstring *
0x18002220b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002220f  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180022214  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18002221b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002221f  call    _CxxThrowException_0
0x180022225  lea     r8, [rbp+57h+var_30]; struct std::error_code *
0x180022229  lea     rdx, [rbp+57h+pExceptionObject]; char *
0x18002222d  lea     rcx, aExists; "exists"
0x180022234  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x18002223a  lea     rcx, [rbp+57h+var_68]
0x18002223e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180022243  mov     rbx, rax
0x180022246  lea     rdx, aFolderPathCann; "Folder path cannot be empty"
0x18002224d  lea     rcx, [rbp+57h+var_50]; this
0x180022251  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022256  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180022259  lea     rdx, [rbp+57h+var_50]; struct winrt::param::hstring *
0x18002225d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180022261  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180022266  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18002226d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180022271  call    _CxxThrowException_0
0x180022277  lea     rcx, [rbp+57h+var_68]
0x18002227b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180022280  mov     rbx, rax
0x180022283  lea     rdx, aSpecifiedFolde; "Specified folder path does not exist"
0x18002228a  lea     rcx, [rbp+57h+var_50]; this
0x18002228e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022293  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180022296  lea     rdx, [rbp+57h+var_50]; struct winrt::param::hstring *
0x18002229a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002229e  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800222a3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800222aa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800222ae  call    _CxxThrowException_0
0x1800222b4  lea     r8, [rbp+57h+var_30]
0x1800222b8  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```
