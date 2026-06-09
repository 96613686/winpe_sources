# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180056d40`
- end: `0x180056e48`
- name: `?ReadPolicyStringArray@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800553e8`

## callees

- `0x180029408`
- `0x18002f280`
- `0x18003ce34`
- `0x180056d40`
- `0x180058ac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056d9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056df5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056d9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056df5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
        __int64 a1,
        HKEY *a2,
        HKEY *a3,
        HKEY *a4,
        __int64 a5)
{
  const WCHAR *v9; // rax
  __int64 v10; // rax
  HKEY v11; // rdx
  const WCHAR *v12; // rax
  HKEY phkResult; // [rsp+88h] [rbp+20h] BYREF

  phkResult = 0;
  if ( !*a4
    || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkResult,
          0),
        v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5),
        RegOpenKeyExW(*a4, v9, 0, 0x20119u, &phkResult)) )
  {
    if ( !*a3
      || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &phkResult,
            0),
          v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5),
          RegOpenKeyExW(*a3, v12, 0, 0x20119u, &phkResult)) )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
      v11 = *a2;
    }
    else
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
      v11 = *a3;
    }
  }
  else
  {
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    v11 = *a4;
  }
  Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(a1, v11, v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return a1;
}

```

## disassembly

```asm
0x180056d40  mov     rax, rsp
0x180056d43  push    rbx
0x180056d44  push    rsi
0x180056d45  push    r14
0x180056d47  push    r15
0x180056d49  sub     rsp, 48h
0x180056d4d  mov     r14, r9
0x180056d50  mov     rsi, r8
0x180056d53  mov     r15, rdx
0x180056d56  mov     rbx, rcx
0x180056d59  mov     qword ptr [rax+20h], 0
0x180056d61  cmp     qword ptr [r9], 0
0x180056d65  jz      short loc_180056DB7
0x180056d67  xor     edx, edx
0x180056d69  lea     rcx, [rax+20h]
0x180056d6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180056d72  mov     rcx, [rsp+68h+arg_20]
0x180056d7a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056d7f  lea     rcx, [rsp+68h+arg_18]
0x180056d87  mov     [rsp+68h+phkResult], rcx; phkResult
0x180056d8c  mov     r9d, 20119h; samDesired
0x180056d92  xor     r8d, r8d; ulOptions
0x180056d95  mov     rdx, rax; lpSubKey
0x180056d98  mov     rcx, [r14]; hKey
0x180056d9b  call    cs:__imp_RegOpenKeyExW
0x180056da1  test    eax, eax
0x180056da3  jnz     short loc_180056DB7
0x180056da5  mov     rcx, [rsp+68h+arg_20]
0x180056dad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056db2  mov     rdx, [r14]
0x180056db5  jmp     short loc_180056E21
0x180056db7  cmp     qword ptr [rsi], 0
0x180056dbb  jz      short loc_180056E11
0x180056dbd  xor     edx, edx
0x180056dbf  lea     rcx, [rsp+68h+arg_18]
0x180056dc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180056dcc  mov     rcx, [rsp+68h+arg_20]
0x180056dd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056dd9  lea     rcx, [rsp+68h+arg_18]
0x180056de1  mov     [rsp+68h+phkResult], rcx; phkResult
0x180056de6  mov     r9d, 20119h; samDesired
0x180056dec  xor     r8d, r8d; ulOptions
0x180056def  mov     rdx, rax; lpSubKey
0x180056df2  mov     rcx, [rsi]; hKey
0x180056df5  call    cs:__imp_RegOpenKeyExW
0x180056dfb  test    eax, eax
0x180056dfd  jnz     short loc_180056E11
0x180056dff  mov     rcx, [rsp+68h+arg_20]
0x180056e07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056e0c  mov     rdx, [rsi]
0x180056e0f  jmp     short loc_180056E21
0x180056e11  mov     rcx, [rsp+68h+arg_20]
0x180056e19  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056e1e  mov     rdx, [r15]
0x180056e21  mov     r8, rax
0x180056e24  mov     rcx, rbx
0x180056e27  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x180056e2c  nop
0x180056e2d  lea     rcx, [rsp+68h+arg_18]
0x180056e35  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180056e3a  mov     rax, rbx
0x180056e3d  add     rsp, 48h
0x180056e41  pop     r15
0x180056e43  pop     r14
0x180056e45  pop     rsi
0x180056e46  pop     rbx
0x180056e47  retn
```
