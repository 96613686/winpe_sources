# _anonymous_namespace_::GetErrorMessageWithResourcePrefix

- ea: `0x1800340c8`
- end: `0x18003436a`
- name: `_anonymous_namespace_::GetErrorMessageWithResourcePrefix`
- size: `674`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033f34`
- `0x180033ff4`

## callees

- `0x18000c840`
- `0x18001ecc4`
- `0x18001ecfc`
- `0x1800234f8`
- `0x1800236e0`
- `0x18002373c`
- `0x18002395c`
- `0x18002487c`
- `0x180024af8`
- `0x18002bc6c`
- `0x18002f220`
- `0x180030b0c`
- `0x1800340c8`
- `0x1800353bc`
- `0x180045c94`
- `0x180045d98`
- `0x1800470b0`
- `0x18004d1ac`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180034243`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180034243`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180034232`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180034232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800341fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800341fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800341e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800342fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800341e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800342fd`

## string_xrefs

- `0x18003419d`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x1800341cb`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x1800342b8`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x1800342e6`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::GetErrorMessageWithResourcePrefix(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  SystemSettings::DataModel *v11; // rax
  HSTRING *v12; // r8
  int ResourceStringById; // eax
  HSTRING v14; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  SystemSettings::DataModel *v22; // rax
  HSTRING *v23; // r8
  int v24; // eax
  HSTRING v25; // rbx
  PCWSTR v26; // rax
  __int64 v27; // rax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v30[3]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v31[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[240]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[16]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v34; // [rsp+150h] [rbp+50h]
  _BYTE v35[32]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v30[0] = a1;
  LODWORD(string) = a2;
  anonymous_namespace_::GetMessageForHresult(v33);
  if ( *(_QWORD *)std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(
                    v6,
                    v30,
                    &string) == qword_18039C608 )
  {
    if ( !v34 )
    {
      std::_Hash<std::_Umap_traits<long,std::wstring,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,std::wstring>>,0>>::find(
        qword_18039C608,
        v30,
        &string);
      v7 = v30[0];
      if ( v30[0] == qword_18039C648 )
      {
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v31);
        v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, L"0x");
        v17 = std::basic_ostream<unsigned short>::operator<<(v16, std::hex);
        std::basic_ostream<unsigned short>::operator<<(v17, a2);
        v18 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                v31,
                v35);
        std::wstring::operator=(v33, v18);
        std::wstring::_Tidy_deallocate(v35);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v31);
      }
      else
      {
        WindowsDeleteString(0);
        string = 0;
        v11 = (SystemSettings::DataModel *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 24, v8, v9, v10);
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(v11, &string, v12);
        if ( ResourceStringById < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x200,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
            (const char *)(unsigned int)ResourceStringById,
            (int)string);
        v14 = string;
        if ( !string )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x201,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
            (const char *)0x8000FFFFLL,
            0);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        std::wstring::assign(v33, StringRawBuffer);
        WindowsDeleteString(v14);
      }
    }
    WindowsDeleteString(0);
    string = 0;
    v22 = (SystemSettings::DataModel *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3, v19, v20, v21);
    v24 = SystemSettings::DataModel::GetResourceStringById(v22, &string, v23);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
        (const char *)(unsigned int)v24,
        (int)string);
    v25 = string;
    if ( !string )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
        (const char *)0x8000FFFFLL,
        0);
    v26 = WindowsGetStringRawBuffer(string, 0);
    v27 = std::wstring::wstring(v35, v26);
    std::operator+<unsigned short>(a1, v27, v33);
    std::wstring::_Tidy_deallocate(v35);
    WindowsDeleteString(v25);
  }
  else
  {
    std::wstring::wstring(a1, v33);
  }
  std::wstring::_Tidy_deallocate(v33);
  return a1;
}

```

## disassembly

```asm
0x1800340c8  push    rbp
0x1800340ca  push    rbx
0x1800340cb  push    rsi
0x1800340cc  push    rdi
0x1800340cd  push    r14
0x1800340cf  lea     rbp, [rsp-90h]
0x1800340d7  sub     rsp, 190h
0x1800340de  mov     rax, cs:__security_cookie
0x1800340e5  xor     rax, rsp
0x1800340e8  mov     [rbp+0B0h+var_30], rax
0x1800340ef  mov     r14, r8
0x1800340f2  mov     esi, edx
0x1800340f4  mov     rdi, rcx
0x1800340f7  mov     [rsp+1B0h+var_188], rcx
0x1800340fc  mov     dword ptr [rsp+1B0h+string], edx
0x180034100  lea     rcx, [rbp+0B0h+var_70]
0x180034104  call    _anonymous_namespace___GetMessageForHresult
0x180034109  nop
0x18003410a  lea     r8, [rsp+1B0h+string]
0x18003410f  lea     rdx, [rsp+1B0h+var_188]
0x180034114  call    ?find@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@2@AEBJ@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(long const &)
0x180034119  mov     rcx, cs:qword_18039C608
0x180034120  cmp     [rax], rcx
0x180034123  jz      short loc_180034136
0x180034125  lea     rdx, [rbp+0B0h+var_70]
0x180034129  mov     rcx, rdi
0x18003412c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180034131  jmp     loc_180034340
0x180034136  cmp     [rbp+0B0h+var_60], 0
0x18003413b  jnz     loc_18003427E
0x180034141  lea     r8, [rsp+1B0h+string]
0x180034146  lea     rdx, [rsp+1B0h+var_188]
0x18003414b  call    ?find@?$_Hash@V?$_Umap_traits@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@2@V?$allocator@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@AEBJ@Z; std::_Hash<std::_Umap_traits<long,std::wstring,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,std::wstring>>,0>>::find(long const &)
0x180034150  mov     rbx, [rsp+1B0h+var_188]
0x180034155  cmp     rbx, cs:qword_18039C648
0x18003415c  jz      loc_18003420C
0x180034162  xor     ecx, ecx; string
0x180034164  call    cs:__imp_WindowsDeleteString
0x18003416b  nop     dword ptr [rax+rax+00h]
0x180034170  mov     [rsp+1B0h+string], 0; int
0x180034179  lea     rcx, [rbx+18h]
0x18003417d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180034182  lea     rdx, [rsp+1B0h+string]; HSTRING *
0x180034187  mov     rcx, rax; this
0x18003418a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18003418f  mov     rcx, [rbp+0B8h]; this
0x180034196  test    eax, eax
0x180034198  jns     short loc_1800341AF
0x18003419a  mov     r9d, eax; char *
0x18003419d  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x1800341a4  mov     edx, 200h; void *
0x1800341a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800341af  mov     rbx, [rsp+1B0h+string]
0x1800341b4  test    rbx, rbx
0x1800341b7  setz    al
0x1800341ba  mov     rcx, [rbp+0B8h]; this
0x1800341c1  test    al, al
0x1800341c3  jz      short loc_1800341DD
0x1800341c5  mov     r9d, 8000FFFFh; char *
0x1800341cb  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x1800341d2  mov     edx, 201h; void *
0x1800341d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800341dd  xor     edx, edx; length
0x1800341df  mov     rcx, rbx; string
0x1800341e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800341e9  nop     dword ptr [rax+rax+00h]
0x1800341ee  mov     rdx, rax
0x1800341f1  lea     rcx, [rbp+0B0h+var_70]
0x1800341f5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800341fa  nop
0x1800341fb  mov     rcx, rbx; string
0x1800341fe  call    cs:__imp_WindowsDeleteString
0x180034205  nop     dword ptr [rax+rax+00h]
0x18003420a  jmp     short loc_18003427E
0x18003420c  lea     rcx, [rsp+1B0h+var_170]
0x180034211  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180034216  nop
0x180034217  lea     rdx, a0x; "0x"
0x18003421e  lea     rcx, [rsp+1B0h+var_160]
0x180034223  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180034228  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18003422f  mov     rcx, rax
0x180034232  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180034239  nop     dword ptr [rax+rax+00h]
0x18003423e  mov     edx, esi
0x180034240  mov     rcx, rax
0x180034243  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18003424a  nop     dword ptr [rax+rax+00h]
0x18003424f  lea     rdx, [rbp+0B0h+var_50]
0x180034253  lea     rcx, [rsp+1B0h+var_170]
0x180034258  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18003425d  mov     rdx, rax
0x180034260  lea     rcx, [rbp+0B0h+var_70]
0x180034264  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034269  lea     rcx, [rbp+0B0h+var_50]
0x18003426d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034272  nop
0x180034273  lea     rcx, [rsp+1B0h+var_170]
0x180034278  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18003427d  nop
0x18003427e  xor     ecx, ecx; string
0x180034280  call    cs:__imp_WindowsDeleteString
0x180034287  nop     dword ptr [rax+rax+00h]
0x18003428c  mov     [rsp+1B0h+string], 0; int
0x180034295  mov     rcx, r14
0x180034298  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003429d  lea     rdx, [rsp+1B0h+string]; HSTRING *
0x1800342a2  mov     rcx, rax; this
0x1800342a5  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800342aa  mov     rcx, [rbp+0B8h]; this
0x1800342b1  test    eax, eax
0x1800342b3  jns     short loc_1800342CA
0x1800342b5  mov     r9d, eax; char *
0x1800342b8  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x1800342bf  mov     edx, 20Eh; void *
0x1800342c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800342ca  mov     rbx, [rsp+1B0h+string]
0x1800342cf  test    rbx, rbx
0x1800342d2  setz    al
0x1800342d5  mov     rcx, [rbp+0B8h]; this
0x1800342dc  test    al, al
0x1800342de  jz      short loc_1800342F8
0x1800342e0  mov     r9d, 8000FFFFh; char *
0x1800342e6  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x1800342ed  mov     edx, 20Fh; void *
0x1800342f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800342f8  xor     edx, edx; length
0x1800342fa  mov     rcx, rbx; string
0x1800342fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180034304  nop     dword ptr [rax+rax+00h]
0x180034309  mov     rdx, rax
0x18003430c  lea     rcx, [rbp+0B0h+var_50]
0x180034310  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034315  nop
0x180034316  lea     r8, [rbp+0B0h+var_70]
0x18003431a  mov     rdx, rax
0x18003431d  mov     rcx, rdi
0x180034320  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180034325  nop
0x180034326  lea     rcx, [rbp+0B0h+var_50]
0x18003432a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003432f  nop
0x180034330  mov     rcx, rbx; string
0x180034333  call    cs:__imp_WindowsDeleteString
0x18003433a  nop     dword ptr [rax+rax+00h]
0x18003433f  nop
0x180034340  lea     rcx, [rbp+0B0h+var_70]
0x180034344  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034349  mov     rax, rdi
0x18003434c  mov     rcx, [rbp+0B0h+var_30]
0x180034353  xor     rcx, rsp; StackCookie
0x180034356  call    __security_check_cookie
0x18003435b  add     rsp, 190h
0x180034362  pop     r14
0x180034364  pop     rdi
0x180034365  pop     rsi
0x180034366  pop     rbx
0x180034367  pop     rbp
0x180034368  retn
```
