# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002bd90`
- end: `0x18002be98`
- name: `?ReadPolicyStringArray@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002a438`

## callees

- `0x18001b444`
- `0x180021550`
- `0x180023b38`
- `0x18002bd90`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bdeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bdeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be45`

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
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  const WCHAR *v12; // rax
  __int64 v13; // rax
  HKEY v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  const WCHAR *v18; // rax
  HKEY phkResult; // [rsp+88h] [rbp+20h] BYREF

  phkResult = 0;
  if ( !*a4
    || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkResult,
          0),
        v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, v9, v10, v11),
        RegOpenKeyExW(*a4, v12, 0, 0x20119u, &phkResult)) )
  {
    if ( !*a3
      || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &phkResult,
            0),
          v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, v15, v16, v17),
          RegOpenKeyExW(*a3, v18, 0, 0x20119u, &phkResult)) )
    {
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, a2, a3, a4);
      v14 = *a2;
    }
    else
    {
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, a2, a3, a4);
      v14 = *a3;
    }
  }
  else
  {
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, a2, a3, a4);
    v14 = *a4;
  }
  Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(a1, v14, v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return a1;
}

```

## disassembly

```asm
0x18002bd90  mov     rax, rsp
0x18002bd93  push    rbx
0x18002bd94  push    rsi
0x18002bd95  push    r14
0x18002bd97  push    r15
0x18002bd99  sub     rsp, 48h
0x18002bd9d  mov     r14, r9
0x18002bda0  mov     rsi, r8
0x18002bda3  mov     r15, rdx
0x18002bda6  mov     rbx, rcx
0x18002bda9  mov     qword ptr [rax+20h], 0
0x18002bdb1  cmp     qword ptr [r9], 0
0x18002bdb5  jz      short loc_18002BE07
0x18002bdb7  xor     edx, edx
0x18002bdb9  lea     rcx, [rax+20h]
0x18002bdbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002bdc2  mov     rcx, [rsp+68h+arg_20]
0x18002bdca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002bdcf  lea     rcx, [rsp+68h+arg_18]
0x18002bdd7  mov     [rsp+68h+phkResult], rcx; phkResult
0x18002bddc  mov     r9d, 20119h; samDesired
0x18002bde2  xor     r8d, r8d; ulOptions
0x18002bde5  mov     rdx, rax; lpSubKey
0x18002bde8  mov     rcx, [r14]; hKey
0x18002bdeb  call    cs:__imp_RegOpenKeyExW
0x18002bdf1  test    eax, eax
0x18002bdf3  jnz     short loc_18002BE07
0x18002bdf5  mov     rcx, [rsp+68h+arg_20]
0x18002bdfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002be02  mov     rdx, [r14]
0x18002be05  jmp     short loc_18002BE71
0x18002be07  cmp     qword ptr [rsi], 0
0x18002be0b  jz      short loc_18002BE61
0x18002be0d  xor     edx, edx
0x18002be0f  lea     rcx, [rsp+68h+arg_18]
0x18002be17  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002be1c  mov     rcx, [rsp+68h+arg_20]
0x18002be24  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002be29  lea     rcx, [rsp+68h+arg_18]
0x18002be31  mov     [rsp+68h+phkResult], rcx; phkResult
0x18002be36  mov     r9d, 20119h; samDesired
0x18002be3c  xor     r8d, r8d; ulOptions
0x18002be3f  mov     rdx, rax; lpSubKey
0x18002be42  mov     rcx, [rsi]; hKey
0x18002be45  call    cs:__imp_RegOpenKeyExW
0x18002be4b  test    eax, eax
0x18002be4d  jnz     short loc_18002BE61
0x18002be4f  mov     rcx, [rsp+68h+arg_20]
0x18002be57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002be5c  mov     rdx, [rsi]
0x18002be5f  jmp     short loc_18002BE71
0x18002be61  mov     rcx, [rsp+68h+arg_20]
0x18002be69  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002be6e  mov     rdx, [r15]
0x18002be71  mov     r8, rax
0x18002be74  mov     rcx, rbx
0x18002be77  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x18002be7c  nop
0x18002be7d  lea     rcx, [rsp+68h+arg_18]
0x18002be85  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002be8a  mov     rax, rbx
0x18002be8d  add     rsp, 48h
0x18002be91  pop     r15
0x18002be93  pop     r14
0x18002be95  pop     rsi
0x18002be96  pop     rbx
0x18002be97  retn
```
