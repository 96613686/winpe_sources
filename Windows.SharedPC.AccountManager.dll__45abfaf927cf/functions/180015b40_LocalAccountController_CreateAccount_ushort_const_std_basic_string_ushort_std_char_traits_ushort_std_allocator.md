# LocalAccountController::CreateAccount(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180015b40`
- end: `0x180015ca8`
- name: `?CreateAccount@LocalAccountController@@UEAAJPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000cd50`
- `0x1800126ac`
- `0x180013dcc`
- `0x1800150d4`
- `0x1800159bc`
- `0x180015b40`
- `0x180015cf8`
- `0x180016924`
- `0x180016ab4`
- `0x180017214`
- `0x180019874`

## string_xrefs

- `0x180015be5`: `CreatedLocalAccounts\%s`
- `0x180015c05`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
__int64 __fastcall LocalAccountController::CreateAccount(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  const unsigned __int16 *v6; // rdx
  LocalAccountController *v7; // rcx
  __int64 *v8; // rax
  const unsigned __int16 *v9; // rdx
  LocalAccountController *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  HKEY v14[2]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v15[5]; // [rsp+30h] [rbp-88h] BYREF
  char v16; // [rsp+58h] [rbp-60h]
  _BYTE v17[32]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v18[32]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  LocalAccountController::GetNextUserName(a1, v17);
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  LocalAccountController::CreateUser(v7, v6, a2);
  v8 = (__int64 *)_lambda_580024a2357b1cfd8c7a6c9d21b0d049_::_lambda_580024a2357b1cfd8c7a6c9d21b0d049_(v14, a1, v17);
  v15[3] = *v8;
  v15[4] = v8[1];
  v16 = 1;
  v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  LocalAccountController::AddUserToBuiltInUsersGroup(v10, v9);
  memset(v15, 0, 24);
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          v15,
          L"CreatedLocalAccounts\\%s",
          v11);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x96,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v12,
      (int)v14[0]);
  std::wstring::wstring((__int64)v18, v15[0]);
  v14[0] = (HKEY)GetSharedPCKey(v18, 983103);
  std::wstring::_Tidy_deallocate((__int64)v18);
  std::wstring::operator=(a3, v17);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v14);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v15);
  std::wstring::_Tidy_deallocate((__int64)v17);
  return 0;
}

```

## disassembly

```asm
0x180015b40  mov     [rsp+arg_0], rbx
0x180015b45  mov     [rsp+arg_18], rsi
0x180015b4a  push    rdi
0x180015b4b  sub     rsp, 0B0h
0x180015b52  mov     rax, cs:__security_cookie
0x180015b59  xor     rax, rsp
0x180015b5c  mov     [rsp+0B8h+var_18], rax
0x180015b64  mov     rdi, r8
0x180015b67  mov     rbx, rdx
0x180015b6a  mov     rsi, rcx
0x180015b6d  lea     rdx, [rsp+0B8h+var_58]
0x180015b72  call    ?GetNextUserName@LocalAccountController@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; LocalAccountController::GetNextUserName(void)
0x180015b77  nop
0x180015b78  lea     rcx, [rsp+0B8h+var_58]
0x180015b7d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015b82  mov     rdx, rax; unsigned __int16 *
0x180015b85  mov     r8, rbx; unsigned __int16 *
0x180015b88  call    ?CreateUser@LocalAccountController@@AEAAXPEBG0@Z; LocalAccountController::CreateUser(ushort const *,ushort const *)
0x180015b8d  lea     r8, [rsp+0B8h+var_58]
0x180015b92  mov     rdx, rsi
0x180015b95  lea     rcx, [rsp+0B8h+var_98]
0x180015b9a  call    ??0_lambda_580024a2357b1cfd8c7a6c9d21b0d049_@@QEAA@PEAVLocalAccountController@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; _lambda_580024a2357b1cfd8c7a6c9d21b0d049_::_lambda_580024a2357b1cfd8c7a6c9d21b0d049_(LocalAccountController *,std::wstring &)
0x180015b9f  mov     rcx, [rax]
0x180015ba2  mov     [rsp+0B8h+var_70], rcx
0x180015ba7  mov     rax, [rax+8]
0x180015bab  mov     [rsp+0B8h+var_68], rax
0x180015bb0  mov     [rsp+0B8h+var_60], 1
0x180015bb5  lea     rcx, [rsp+0B8h+var_58]
0x180015bba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015bbf  mov     rdx, rax; unsigned __int16 *
0x180015bc2  call    ?AddUserToBuiltInUsersGroup@LocalAccountController@@AEAAXPEBG@Z; LocalAccountController::AddUserToBuiltInUsersGroup(ushort const *)
0x180015bc7  xor     ebx, ebx
0x180015bc9  mov     [rsp+0B8h+var_88], rbx
0x180015bce  mov     [rsp+0B8h+var_80], rbx
0x180015bd3  mov     [rsp+0B8h+var_78], rbx
0x180015bd8  lea     rcx, [rsp+0B8h+var_58]
0x180015bdd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015be2  mov     r8, rax
0x180015be5  lea     rdx, aCreatedlocalac_0; "CreatedLocalAccounts\\%s"
0x180015bec  lea     rcx, [rsp+0B8h+var_88]
0x180015bf1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180015bf6  mov     rcx, [rsp+0B8h]; this
0x180015bfe  test    eax, eax
0x180015c00  jns     short loc_180015C16
0x180015c02  mov     r9d, eax; char *
0x180015c05  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015c0c  mov     edx, 96h; void *
0x180015c11  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015c16  mov     rdx, [rsp+0B8h+var_88]
0x180015c1b  lea     rcx, [rsp+0B8h+var_38]
0x180015c23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015c28  nop
0x180015c29  mov     edx, 0F003Fh
0x180015c2e  lea     rcx, [rsp+0B8h+var_38]
0x180015c36  call    ?GetSharedPCKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCKey(std::wstring const &,ulong)
0x180015c3b  mov     [rsp+0B8h+var_98], rax
0x180015c40  lea     rcx, [rsp+0B8h+var_38]
0x180015c48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015c4d  lea     rdx, [rsp+0B8h+var_58]
0x180015c52  mov     rcx, rdi
0x180015c55  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015c5a  lea     rcx, [rsp+0B8h+var_98]
0x180015c5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015c64  nop
0x180015c65  lea     rcx, [rsp+0B8h+var_88]
0x180015c6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180015c6f  nop
0x180015c70  lea     rcx, [rsp+0B8h+var_58]
0x180015c75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015c7a  xor     eax, eax
0x180015c7c  jmp     short loc_180015C82
0x180015c7e  mov     eax, dword ptr [rsp+0B8h+var_98]
0x180015c82  mov     rcx, [rsp+0B8h+var_18]
0x180015c8a  xor     rcx, rsp; StackCookie
0x180015c8d  call    __security_check_cookie
0x180015c92  lea     r11, [rsp+0B8h+var_8]
0x180015c9a  mov     rbx, [r11+10h]
0x180015c9e  mov     rsi, [r11+28h]
0x180015ca2  mov     rsp, r11
0x180015ca5  pop     rdi
0x180015ca6  retn
```
