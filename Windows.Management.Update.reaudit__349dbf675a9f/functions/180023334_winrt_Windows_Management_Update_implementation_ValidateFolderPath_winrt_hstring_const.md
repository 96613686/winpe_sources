# winrt::Windows::Management::Update::implementation::ValidateFolderPath(winrt::hstring const &)

- ea: `0x180023334`
- end: `0x180023558`
- name: `?ValidateFolderPath@implementation@Update@Management@Windows@winrt@@YAXAEBUhstring@5@@Z`
- size: `548`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation *__hidden this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180023118`

## callees

- `0x180002880`
- `0x1800035f0`
- `0x180011ffc`
- `0x180015ac0`
- `0x1800188d4`
- `0x180018f10`
- `0x18001da30`
- `0x180023334`
- `0x180023728`
- `0x180023a40`
- `0x180023a98`
- `0x180024160`

## string_xrefs

- `0x1800234a3`: `Folder path cannot be empty`
- `0x1800234e0`: `Specified folder path does not exist`
- `0x180023527`: `Specified path is not a directory`
- `0x180023451`: `Specified directory is empty`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::ValidateFolderPath(
        winrt::Windows::Management::Update::implementation *this,
        const struct winrt::hstring *a2)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  int *any_status; // rax
  const struct std::filesystem::path *v5; // r9
  int v6; // ecx
  bool v7; // al
  int *v8; // rax
  const struct std::filesystem::path *v9; // rdx
  const struct winrt::impl::slim_source_location *v10; // rbx
  const struct winrt::impl::slim_source_location *v11; // rbx
  const struct winrt::impl::slim_source_location *v12; // rbx
  const struct winrt::impl::slim_source_location *v13; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-39h] BYREF
  void ***pExceptionObject_8; // [rsp+28h] [rbp-31h]
  __int64 v16; // [rsp+40h] [rbp-19h]
  int v17[6]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v19; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v20; // [rsp+98h] [rbp+3Fh]
  __int64 v21; // [rsp+A0h] [rbp+47h]

  if ( !*(_QWORD *)this )
  {
    v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Folder path cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      v11);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v2 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(v2 + 2 * v3) );
  v19 = 0;
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v19, v2, v3);
  any_status = std::filesystem::_Get_any_status(v17, (__int64)&v19);
  v16 = *(_QWORD *)any_status;
  v6 = any_status[2];
  pExceptionObject = v6;
  pExceptionObject_8 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( (_DWORD)v16 )
  {
    v7 = (_DWORD)v16 != 1;
  }
  else
  {
    v7 = 0;
    if ( v6 )
      std::filesystem::_Throw_fs_error(
        (std::filesystem *)"exists",
        (const char *)&pExceptionObject,
        (const struct std::error_code *)&v19,
        v5);
  }
  if ( !v7 )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Specified folder path does not exist");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      v12);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v8 = std::filesystem::_Get_any_status(v17, (__int64)&v19);
  v16 = *(_QWORD *)v8;
  v9 = (const struct std::filesystem::path *)(unsigned int)v8[2];
  if ( (_DWORD)v9 && (((_DWORD)v16 - 1) & 0xFFFFFFF7) != 0 )
    std::filesystem::_Throw_fs_error((unsigned int)v16, v9, &v19);
  if ( (_DWORD)v16 != 3 )
  {
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Specified path is not a directory");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      v13);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  if ( std::filesystem::is_empty((std::filesystem *)&v19, v9) )
  {
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Specified directory is empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      v10);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  std::wstring::_Tidy_deallocate(&v19);
}

```

## disassembly

```asm
0x180023334  mov     [rsp-8+arg_0], rbx
0x180023339  push    rbp
0x18002333a  lea     rbp, [rsp-57h]
0x18002333f  sub     rsp, 0B0h
0x180023346  mov     rax, cs:__security_cookie
0x18002334d  xor     rax, rsp
0x180023350  mov     [rbp+57h+var_8], rax
0x180023354  xor     ebx, ebx
0x180023356  mov     rax, [rcx]
0x180023359  test    rax, rax
0x18002335c  jz      loc_180023497
0x180023362  mov     rdx, [rax+10h]
0x180023366  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002336a  inc     r8
0x18002336d  cmp     [rdx+r8*2], bx
0x180023372  jnz     short loc_18002336A
0x180023374  xorps   xmm0, xmm0
0x180023377  movups  [rbp+57h+var_28], xmm0
0x18002337b  mov     [rbp+57h+var_18], rbx
0x18002337f  mov     [rbp+57h+var_10], rbx
0x180023383  lea     rcx, [rbp+57h+var_28]
0x180023387  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002338c  nop
0x18002338d  lea     rdx, [rbp+57h+var_28]
0x180023391  lea     rcx, [rbp+57h+var_60]
0x180023395  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x18002339a  movsd   xmm0, qword ptr [rax]
0x18002339e  movsd   [rbp+57h+var_70], xmm0
0x1800233a3  mov     ecx, [rax+8]
0x1800233a6  mov     dword ptr [rbp+57h+pExceptionObject], ecx
0x1800233a9  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800233b0  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x1800233b4  movaps  xmm0, [rbp+57h+pExceptionObject]
0x1800233b8  movdqa  [rbp+57h+pExceptionObject], xmm0
0x1800233bd  mov     eax, dword ptr [rbp+57h+var_70]
0x1800233c0  test    eax, eax
0x1800233c2  jz      short loc_18002343D
0x1800233c4  cmp     eax, 1
0x1800233c7  setnz   al
0x1800233ca  test    al, al
0x1800233cc  jz      loc_1800234D4
0x1800233d2  lea     rdx, [rbp+57h+var_28]
0x1800233d6  lea     rcx, [rbp+57h+var_60]
0x1800233da  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x1800233df  movsd   xmm0, qword ptr [rax]
0x1800233e3  movsd   [rbp+57h+var_70], xmm0
0x1800233e8  mov     edx, [rax+8]; struct std::filesystem::path *
0x1800233eb  mov     ecx, dword ptr [rbp+57h+var_70]
0x1800233ee  test    edx, edx
0x1800233f0  jz      short loc_180023400
0x1800233f2  lea     eax, [rcx-1]
0x1800233f5  test    eax, 0FFFFFFF7h
0x1800233fa  jnz     loc_180023511
0x180023400  cmp     ecx, 3
0x180023403  jnz     loc_18002351B
0x180023409  lea     rcx, [rbp+57h+var_28]; this
0x18002340d  call    ?is_empty@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::is_empty(std::filesystem::path const &)
0x180023412  test    al, al
0x180023414  jnz     short loc_180023445
0x180023416  lea     rcx, [rbp+57h+var_28]
0x18002341a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002341f  mov     rcx, [rbp+57h+var_8]
0x180023423  xor     rcx, rsp; StackCookie
0x180023426  call    __security_check_cookie
0x18002342b  mov     rbx, [rsp+0B0h+arg_0]
0x180023433  add     rsp, 0B0h
0x18002343a  pop     rbp
0x18002343b  retn
0x18002343d  mov     al, bl
0x18002343f  test    ecx, ecx
0x180023441  jnz     short loc_180023482
0x180023443  jmp     short loc_1800233CA
0x180023445  lea     rcx, [rbp+57h+var_60]
0x180023449  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002344e  mov     rbx, rax
0x180023451  lea     rdx, aSpecifiedDirec; "Specified directory is empty"
0x180023458  lea     rcx, [rbp+57h+var_48]; this
0x18002345c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023461  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180023464  lea     rdx, [rbp+57h+var_48]; struct winrt::param::hstring *
0x180023468  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002346c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180023471  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180023478  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002347c  call    _CxxThrowException_0
0x180023482  lea     r8, [rbp+57h+var_28]; struct std::error_code *
0x180023486  lea     rdx, [rbp+57h+pExceptionObject]; char *
0x18002348a  lea     rcx, aExists; "exists"
0x180023491  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x180023497  lea     rcx, [rbp+57h+var_60]
0x18002349b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800234a0  mov     rbx, rax
0x1800234a3  lea     rdx, aFolderPathCann; "Folder path cannot be empty"
0x1800234aa  lea     rcx, [rbp+57h+var_48]; this
0x1800234ae  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800234b3  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800234b6  lea     rdx, [rbp+57h+var_48]; struct winrt::param::hstring *
0x1800234ba  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800234be  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800234c3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800234ca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800234ce  call    _CxxThrowException_0
0x1800234d4  lea     rcx, [rbp+57h+var_60]
0x1800234d8  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800234dd  mov     rbx, rax
0x1800234e0  lea     rdx, aSpecifiedFolde; "Specified folder path does not exist"
0x1800234e7  lea     rcx, [rbp+57h+var_48]; this
0x1800234eb  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800234f0  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800234f3  lea     rdx, [rbp+57h+var_48]; struct winrt::param::hstring *
0x1800234f7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800234fb  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180023500  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180023507  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002350b  call    _CxxThrowException_0
0x180023511  lea     r8, [rbp+57h+var_28]
0x180023515  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x18002351b  lea     rcx, [rbp+57h+var_60]
0x18002351f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180023524  mov     rbx, rax
0x180023527  lea     rdx, aSpecifiedPathI; "Specified path is not a directory"
0x18002352e  lea     rcx, [rbp+57h+var_48]; this
0x180023532  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023537  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x18002353a  lea     rdx, [rbp+57h+var_48]; struct winrt::param::hstring *
0x18002353e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180023542  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180023547  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18002354e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023552  call    _CxxThrowException_0
```
