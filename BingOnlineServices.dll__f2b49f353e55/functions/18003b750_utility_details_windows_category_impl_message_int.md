# utility::details::windows_category_impl::message(int)

- ea: `0x18003b750`
- end: `0x18003b886`
- name: `?message@windows_category_impl@details@utility@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x180009778`
- `0x18000e5a8`
- `0x18000f68c`
- `0x18000fe9c`
- `0x18001679c`
- `0x18003a808`
- `0x18003abe4`
- `0x18003b750`
- `0x18003c020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18003b815`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18003b815`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003b78c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003b78c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b7eb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b7eb`

## string_xrefs

- `0x18003b785`: `winhttp.dll`

## pseudocode

```c
__int64 __fastcall utility::details::windows_category_impl::message(__int64 a1, __int64 a2, signed int a3)
{
  DWORD v5; // esi
  HMODULE ModuleHandleA; // rbp
  WCHAR *lpBuffer; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _BYTE v11[8]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v12[232]; // [rsp+48h] [rbp-130h] BYREF
  _BYTE v13[32]; // [rsp+130h] [rbp-48h] BYREF

  if ( a3 < 12000 )
  {
    v5 = 4096;
    ModuleHandleA = 0;
  }
  else
  {
    v5 = 2048;
    ModuleHandleA = GetModuleHandleA("winhttp.dll");
  }
  std::wstring::wstring(v13);
  std::wstring::resize(v13, 4096);
  lpBuffer = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  if ( FormatMessageW(v5, ModuleHandleA, a3, 0, lpBuffer, 0x1000u, 0) )
  {
    utility::conversions::to_utf8string(a2, v13);
  }
  else
  {
    std::ostringstream::ostringstream(v11);
    v8 = std::operator<<<std::char_traits<char>>(v11, "Unable to get an error message for error code: ");
    v9 = std::ostream::operator<<(v8, (unsigned int)a3);
    std::operator<<<std::char_traits<char>>(v9, ".");
    std::stringbuf::str(v12, a2);
    std::ostringstream::`vbase destructor'(v11);
  }
  std::wstring::_Tidy_deallocate(v13);
  return a2;
}

```

## disassembly

```asm
0x18003b750  mov     [rsp+arg_0], rbx
0x18003b755  push    rbp
0x18003b756  push    rsi
0x18003b757  push    rdi
0x18003b758  sub     rsp, 160h
0x18003b75f  mov     rax, cs:__security_cookie
0x18003b766  xor     rax, rsp
0x18003b769  mov     [rsp+178h+var_28], rax
0x18003b771  mov     edi, r8d
0x18003b774  mov     rbx, rdx
0x18003b777  cmp     r8d, 2EE0h
0x18003b77e  jl      short loc_18003B797
0x18003b780  mov     esi, 800h
0x18003b785  lea     rcx, aWinhttpDll_0; "winhttp.dll"
0x18003b78c  call    cs:__imp_GetModuleHandleA
0x18003b792  mov     rbp, rax
0x18003b795  jmp     short loc_18003B79E
0x18003b797  mov     esi, 1000h
0x18003b79c  xor     ebp, ebp
0x18003b79e  lea     rcx, [rsp+178h+var_48]
0x18003b7a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b7ab  mov     edx, 1000h
0x18003b7b0  lea     rcx, [rsp+178h+var_48]
0x18003b7b8  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003b7bd  lea     rcx, [rsp+178h+var_48]
0x18003b7c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003b7ca  mov     [rsp+178h+Arguments], 0; Arguments
0x18003b7d3  mov     [rsp+178h+nSize], 1000h; nSize
0x18003b7db  mov     [rsp+178h+lpBuffer], rax; lpBuffer
0x18003b7e0  xor     r9d, r9d; dwLanguageId
0x18003b7e3  mov     r8d, edi; dwMessageId
0x18003b7e6  mov     rdx, rbp; lpSource
0x18003b7e9  mov     ecx, esi; dwFlags
0x18003b7eb  call    cs:__imp_FormatMessageW
0x18003b7f1  test    eax, eax
0x18003b7f3  jnz     short loc_18003B843
0x18003b7f5  lea     rcx, [rsp+178h+var_138]
0x18003b7fa  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003b7ff  lea     rdx, aUnableToGetAnE; "Unable to get an error message for erro"...
0x18003b806  lea     rcx, [rsp+178h+var_138]
0x18003b80b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003b810  mov     edx, edi
0x18003b812  mov     rcx, rax
0x18003b815  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x18003b81b  mov     rcx, rax
0x18003b81e  lea     rdx, asc_180069538; "."
0x18003b825  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003b82a  mov     rdx, rbx
0x18003b82d  lea     rcx, [rsp+178h+var_130]
0x18003b832  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18003b837  lea     rcx, [rsp+178h+var_138]
0x18003b83c  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x18003b841  jmp     short loc_18003B853
0x18003b843  lea     rdx, [rsp+178h+var_48]
0x18003b84b  mov     rcx, rbx
0x18003b84e  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x18003b853  lea     rcx, [rsp+178h+var_48]
0x18003b85b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b860  mov     rax, rbx
0x18003b863  mov     rcx, [rsp+178h+var_28]
0x18003b86b  xor     rcx, rsp; StackCookie
0x18003b86e  call    __security_check_cookie
0x18003b873  mov     rbx, [rsp+178h+arg_0]
0x18003b87b  add     rsp, 160h
0x18003b882  pop     rdi
0x18003b883  pop     rsi
0x18003b884  pop     rbp
0x18003b885  retn
```
