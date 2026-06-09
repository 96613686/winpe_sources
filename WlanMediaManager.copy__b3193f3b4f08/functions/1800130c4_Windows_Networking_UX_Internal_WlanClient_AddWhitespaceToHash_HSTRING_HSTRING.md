# Windows::Networking::UX::Internal::WlanClient::AddWhitespaceToHash(HSTRING__ *,HSTRING__ * *)

- ea: `0x1800130c4`
- end: `0x1800131af`
- name: `?AddWhitespaceToHash@WlanClient@Internal@UX@Networking@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU6@@Z`
- size: `235`
- prototype: `int(Windows::Networking::UX::Internal::WlanClient *__hidden this, HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017068`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x180011140`
- `0x1800118d0`
- `0x180011f84`
- `0x1800130c4`
- `0x18001b838`
- `0x18001c044`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800130ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800130ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001312f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001312f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::AddWhitespaceToHash(
        Windows::Networking::UX::Internal::WlanClient *this,
        HSTRING a2,
        HSTRING *a3)
{
  PCWSTR StringRawBuffer; // rbx
  const WCHAR *v5; // rax
  HRESULT String; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-78h]
  _BYTE v10[40]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[16]; // [rsp+60h] [rbp-38h] BYREF
  UINT32 length; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v10,
    L"(.{2})");
  std::regex_replace<std::regex_traits<unsigned short>,unsigned short>(v11, StringRawBuffer, v10);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  String = WindowsCreateString(v5, length, a3);
  v7 = String;
  if ( String >= 0 )
  {
    std::wstring::_Tidy_deallocate(v11);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x424,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
      (const char *)(unsigned int)String,
      v9);
    std::wstring::_Tidy_deallocate(v11);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v10);
    return v7;
  }
}

```

## disassembly

```asm
0x1800130c4  mov     [rsp+arg_0], rbx
0x1800130c9  push    rdi
0x1800130ca  sub     rsp, 90h
0x1800130d1  mov     rax, cs:__security_cookie
0x1800130d8  xor     rax, rsp
0x1800130db  mov     [rsp+98h+var_18], rax
0x1800130e3  mov     rdi, r8
0x1800130e6  mov     rax, rdx
0x1800130e9  xor     edx, edx; length
0x1800130eb  mov     rcx, rax; string
0x1800130ee  call    cs:__imp_WindowsGetStringRawBuffer
0x1800130f4  mov     rbx, rax
0x1800130f7  lea     rdx, a2; "(.{2})"
0x1800130fe  lea     rcx, [rsp+98h+var_60]
0x180013103  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180013108  nop
0x180013109  lea     r8, [rsp+98h+var_60]
0x18001310e  mov     rdx, rbx
0x180013111  lea     rcx, [rsp+98h+var_38]
0x180013116  call    ??$regex_replace@V?$regex_traits@G@std@@G@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV?$basic_regex@GV?$regex_traits@G@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<ushort>,ushort>(ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,ushort const *,std::regex_constants::match_flag_type)
0x18001311b  lea     rcx, [rsp+98h+var_38]
0x180013120  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013125  mov     rcx, rax; sourceString
0x180013128  mov     r8, rdi; string
0x18001312b  mov     edx, [rsp+98h+length]; length
0x18001312f  call    cs:__imp_WindowsCreateString
0x180013135  mov     ebx, eax
0x180013137  test    eax, eax
0x180013139  jns     short loc_180013170
0x18001313b  mov     rcx, [rsp+98h]; this
0x180013143  mov     r9d, eax; char *
0x180013146  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18001314d  mov     edx, 424h; void *
0x180013152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013157  lea     rcx, [rsp+98h+var_38]
0x18001315c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013161  nop
0x180013162  lea     rcx, [rsp+98h+var_60]
0x180013167  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18001316c  mov     eax, ebx
0x18001316e  jmp     short loc_18001318D
0x180013170  lea     rcx, [rsp+98h+var_38]
0x180013175  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001317a  nop
0x18001317b  lea     rcx, [rsp+98h+var_60]
0x180013180  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180013185  xor     eax, eax
0x180013187  jmp     short loc_18001318D
0x180013189  mov     eax, [rsp+98h+var_68]
0x18001318d  mov     rcx, [rsp+98h+var_18]
0x180013195  xor     rcx, rsp; StackCookie
0x180013198  call    __security_check_cookie
0x18001319d  mov     rbx, [rsp+98h+arg_0]
0x1800131a5  add     rsp, 90h
0x1800131ac  pop     rdi
0x1800131ad  retn
```
