# SystemSettings::WorkAccess::CApplicationManagedByMDM::get_Description(HSTRING__ * *)

- ea: `0x180039aa0`
- end: `0x180039bb2`
- name: `?get_Description@CApplicationManagedByMDM@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CApplicationManagedByMDM *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18000eacc`
- `0x180023164`
- `0x1800291ec`
- `0x180029234`
- `0x180029298`
- `0x180029eec`
- `0x180039aa0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b82`

## string_xrefs

- `0x180039b50`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::CApplicationManagedByMDM::get_Description(
        SystemSettings::WorkAccess::CApplicationManagedByMDM *this,
        HSTRING *a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v7; // rax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v10; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  string = 0;
  v4 = std::wstring::wstring(v12, *((_QWORD *)this + 27));
  std::operator+<unsigned short>(v11, "\" ", v4);
  std::wstring::_Tidy_deallocate(v12);
  if ( *((_QWORD *)this + 33) )
  {
    std::wstring::append(v11, L": ");
    std::wstring::append(v11, *((_QWORD *)this + 33));
  }
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v10);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = string;
    string = 0;
    *a2 = v7;
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x836,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
  }
  std::wstring::_Tidy_deallocate(v11);
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x180039aa0  mov     [rsp-8+arg_10], rbx
0x180039aa5  mov     [rsp-8+arg_18], rdi
0x180039aaa  push    rbp
0x180039aab  mov     rbp, rsp
0x180039aae  sub     rsp, 80h
0x180039ab5  mov     rax, cs:__security_cookie
0x180039abc  xor     rax, rsp
0x180039abf  mov     [rbp+var_10], rax
0x180039ac3  mov     rdi, rdx
0x180039ac6  mov     rbx, rcx
0x180039ac9  mov     [rbp+string], 0
0x180039ad1  mov     rdx, [rcx+0D8h]
0x180039ad8  lea     rcx, [rbp+var_30]
0x180039adc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039ae1  nop
0x180039ae2  mov     r8, rax
0x180039ae5  lea     rdx, asc_18005D884; "\" "
0x180039aec  lea     rcx, [rbp+var_50]
0x180039af0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180039af5  nop
0x180039af6  lea     rcx, [rbp+var_30]
0x180039afa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039aff  cmp     qword ptr [rbx+108h], 0
0x180039b07  jz      short loc_180039B29
0x180039b09  lea     rdx, asc_18005DAD4; ": "
0x180039b10  lea     rcx, [rbp+var_50]
0x180039b14  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180039b19  mov     rdx, [rbx+108h]
0x180039b20  lea     rcx, [rbp+var_50]
0x180039b24  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180039b29  lea     rcx, [rbp+var_50]
0x180039b2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039b32  mov     [rbp+var_58], rax
0x180039b36  lea     rdx, [rbp+var_58]
0x180039b3a  lea     rcx, [rbp+string]
0x180039b3e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180039b43  mov     ebx, eax
0x180039b45  test    eax, eax
0x180039b47  jns     short loc_180039B63
0x180039b49  mov     rcx, [rbp+8]; this
0x180039b4d  mov     r9d, eax; char *
0x180039b50  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039b57  mov     edx, 836h; void *
0x180039b5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b61  jmp     short loc_180039B74
0x180039b63  mov     rax, [rbp+string]
0x180039b67  mov     [rbp+string], 0
0x180039b6f  mov     [rdi], rax
0x180039b72  xor     ebx, ebx
0x180039b74  lea     rcx, [rbp+var_50]
0x180039b78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039b7d  nop
0x180039b7e  mov     rcx, [rbp+string]; string
0x180039b82  call    cs:__imp_WindowsDeleteString
0x180039b89  nop     dword ptr [rax+rax+00h]
0x180039b8e  mov     eax, ebx
0x180039b90  mov     rcx, [rbp+var_10]
0x180039b94  xor     rcx, rsp; StackCookie
0x180039b97  call    __security_check_cookie
0x180039b9c  lea     r11, [rsp+80h+var_s0]
0x180039ba4  mov     rbx, [r11+20h]
0x180039ba8  mov     rdi, [r11+28h]
0x180039bac  mov     rsp, r11
0x180039baf  pop     rbp
0x180039bb0  retn
```
