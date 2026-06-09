# GetSharedPCTargetPath(void)

- ea: `0x180016d5c`
- end: `0x180016eb1`
- name: `?GetSharedPCTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016ab4`
- `0x180016c08`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x180013dcc`
- `0x1800151fc`
- `0x180016d5c`
- `0x1800198f4`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016ddc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016e40`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016ddc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016e40`

## string_xrefs

- `0x180016d88`: `SharedPCConfiguration`
- `0x180016def`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180016e51`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetSharedPCTargetPath(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v10[4]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v10[1] = HIDWORD(a1);
  std::wstring::wstring((__int64)v13, (__int64)L"SharedPCConfiguration");
  std::wstring::wstring((__int64)v12, (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedPC");
  v10[0] = 0;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( (unsigned int)GetPersistedRegistryLocationW(v2, v3, 0, 0) != 234 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)0x8000FFFFLL,
      (int)v10);
  std::vector<unsigned short>::vector<unsigned short>(&v11, v10[0]);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(v4, v5, v6, v7);
  if ( PersistedRegistryLocationW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x38,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)PersistedRegistryLocationW,
      0);
  std::wstring::wstring(a1, v11);
  std::vector<unsigned short>::_Tidy(&v11);
  std::wstring::_Tidy_deallocate((__int64)v12);
  std::wstring::_Tidy_deallocate((__int64)v13);
  return a1;
}

```

## disassembly

```asm
0x180016d5c  mov     [rsp-8+arg_8], rbx
0x180016d61  mov     [rsp-8+arg_10], rdi
0x180016d66  push    rbp
0x180016d67  lea     rbp, [rsp-57h]
0x180016d6c  sub     rsp, 0A0h
0x180016d73  mov     rax, cs:__security_cookie
0x180016d7a  xor     rax, rsp
0x180016d7d  mov     [rbp+57h+var_8], rax
0x180016d81  mov     rbx, rcx
0x180016d84  mov     qword ptr [rbp+57h+var_70], rcx
0x180016d88  lea     rdx, aSharedpcconfig; "SharedPCConfiguration"
0x180016d8f  lea     rcx, [rbp+57h+var_28]
0x180016d93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016d98  nop
0x180016d99  lea     rdx, String1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016da0  lea     rcx, [rbp+57h+var_48]
0x180016da4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016da9  nop
0x180016daa  mov     [rbp+57h+var_70], 0
0x180016db1  mov     rdi, [rbp+5Fh]
0x180016db5  lea     rcx, [rbp+57h+var_48]
0x180016db9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016dbe  mov     rdx, rax
0x180016dc1  lea     rcx, [rbp+57h+var_28]
0x180016dc5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016dca  mov     rcx, rax
0x180016dcd  lea     rax, [rbp+57h+var_70]
0x180016dd1  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180016dd6  xor     r9d, r9d
0x180016dd9  xor     r8d, r8d
0x180016ddc  call    cs:__imp_GetPersistedRegistryLocationW
0x180016de2  cmp     eax, 0EAh
0x180016de7  jz      short loc_180016E04
0x180016de9  mov     r9d, 8000FFFFh; char *
0x180016def  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016df6  mov     edx, 35h ; '5'; void *
0x180016dfb  mov     rcx, rdi; this
0x180016dfe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016e04  mov     edx, [rbp+57h+var_70]
0x180016e07  lea     rcx, [rbp+57h+var_60]
0x180016e0b  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180016e10  nop
0x180016e11  mov     r8, [rbp+57h+var_60]
0x180016e15  mov     r9, [rbp+57h+var_58]
0x180016e19  sub     r9, r8
0x180016e1c  sar     r9, 1
0x180016e1f  lea     rcx, [rbp+57h+var_48]
0x180016e23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016e28  mov     rdx, rax
0x180016e2b  lea     rcx, [rbp+57h+var_28]
0x180016e2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016e34  mov     rcx, rax
0x180016e37  mov     qword ptr [rsp+0A0h+var_80], 0; unsigned int
0x180016e40  call    cs:__imp_GetPersistedRegistryLocationW
0x180016e46  mov     rcx, [rbp+5Fh]; this
0x180016e4a  test    eax, eax
0x180016e4c  jz      short loc_180016E63
0x180016e4e  mov     r9d, eax; char *
0x180016e51  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016e58  mov     edx, 38h ; '8'; void *
0x180016e5d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016e63  mov     rdx, [rbp+57h+var_60]
0x180016e67  mov     rcx, rbx
0x180016e6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016e6f  nop
0x180016e70  lea     rcx, [rbp+57h+var_60]
0x180016e74  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180016e79  nop
0x180016e7a  lea     rcx, [rbp+57h+var_48]
0x180016e7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016e83  nop
0x180016e84  lea     rcx, [rbp+57h+var_28]
0x180016e88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016e8d  mov     rax, rbx
0x180016e90  mov     rcx, [rbp+57h+var_8]
0x180016e94  xor     rcx, rsp; StackCookie
0x180016e97  call    __security_check_cookie
0x180016e9c  lea     r11, [rsp+0A0h+var_s0]
0x180016ea4  mov     rbx, [r11+18h]
0x180016ea8  mov     rdi, [r11+20h]
0x180016eac  mov     rsp, r11
0x180016eaf  pop     rbp
0x180016eb0  retn
```
