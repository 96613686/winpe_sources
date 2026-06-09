# SystemSettings::WorkAccess::CPolicyManagedByMDM::get_Description(HSTRING__ * *)

- ea: `0x180039bc0`
- end: `0x180039cc1`
- name: `?get_Description@CPolicyManagedByMDM@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CPolicyManagedByMDM *__hidden this, HSTRING *)`
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
- `0x180039bc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c91`

## string_xrefs

- `0x180039c5f`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::CPolicyManagedByMDM::get_Description(
        SystemSettings::WorkAccess::CPolicyManagedByMDM *this,
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
  if ( *((_BYTE *)this + 240) )
    std::wstring::append(v11, L" [Dynamic]");
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
      (void *)0x5E5,
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
0x180039bc0  mov     [rsp-8+arg_10], rbx
0x180039bc5  mov     [rsp-8+arg_18], rdi
0x180039bca  push    rbp
0x180039bcb  mov     rbp, rsp
0x180039bce  sub     rsp, 80h
0x180039bd5  mov     rax, cs:__security_cookie
0x180039bdc  xor     rax, rsp
0x180039bdf  mov     [rbp+var_10], rax
0x180039be3  mov     rdi, rdx
0x180039be6  mov     rbx, rcx
0x180039be9  mov     [rbp+string], 0
0x180039bf1  mov     rdx, [rcx+0D8h]
0x180039bf8  lea     rcx, [rbp+var_30]
0x180039bfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039c01  nop
0x180039c02  mov     r8, rax
0x180039c05  lea     rdx, asc_18005D884; "\" "
0x180039c0c  lea     rcx, [rbp+var_50]
0x180039c10  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180039c15  nop
0x180039c16  lea     rcx, [rbp+var_30]
0x180039c1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c1f  cmp     byte ptr [rbx+0F0h], 0
0x180039c26  jz      short loc_180039C38
0x180039c28  lea     rdx, aDynamic; " [Dynamic]"
0x180039c2f  lea     rcx, [rbp+var_50]
0x180039c33  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180039c38  lea     rcx, [rbp+var_50]
0x180039c3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039c41  mov     [rbp+var_58], rax
0x180039c45  lea     rdx, [rbp+var_58]
0x180039c49  lea     rcx, [rbp+string]
0x180039c4d  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180039c52  mov     ebx, eax
0x180039c54  test    eax, eax
0x180039c56  jns     short loc_180039C72
0x180039c58  mov     rcx, [rbp+8]; this
0x180039c5c  mov     r9d, eax; char *
0x180039c5f  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039c66  mov     edx, 5E5h; void *
0x180039c6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c70  jmp     short loc_180039C83
0x180039c72  mov     rax, [rbp+string]
0x180039c76  mov     [rbp+string], 0
0x180039c7e  mov     [rdi], rax
0x180039c81  xor     ebx, ebx
0x180039c83  lea     rcx, [rbp+var_50]
0x180039c87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c8c  nop
0x180039c8d  mov     rcx, [rbp+string]; string
0x180039c91  call    cs:__imp_WindowsDeleteString
0x180039c98  nop     dword ptr [rax+rax+00h]
0x180039c9d  mov     eax, ebx
0x180039c9f  mov     rcx, [rbp+var_10]
0x180039ca3  xor     rcx, rsp; StackCookie
0x180039ca6  call    __security_check_cookie
0x180039cab  lea     r11, [rsp+80h+var_s0]
0x180039cb3  mov     rbx, [r11+20h]
0x180039cb7  mov     rdi, [r11+28h]
0x180039cbb  mov     rsp, r11
0x180039cbe  pop     rbp
0x180039cbf  retn
```
