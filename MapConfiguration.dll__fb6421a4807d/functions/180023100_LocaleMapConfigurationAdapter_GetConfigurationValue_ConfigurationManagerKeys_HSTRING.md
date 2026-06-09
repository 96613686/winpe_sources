# LocaleMapConfigurationAdapter::GetConfigurationValue(ConfigurationManagerKeys,HSTRING__ * *)

- ea: `0x180023100`
- end: `0x1800231b6`
- name: `?GetConfigurationValue@LocaleMapConfigurationAdapter@@UEAAJW4ConfigurationManagerKeys@@PEAPEAUHSTRING__@@@Z`
- size: `182`
- prototype: `int __high(enum ConfigurationManagerKeys, HSTRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x180023100`
- `0x18002337c`
- `0x180024500`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023183`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocaleMapConfigurationAdapter::GetConfigurationValue(__int64 a1, __int64 a2, HSTRING *a3)
{
  __int64 v4; // r9
  __int64 v5; // rdx
  HRESULT v6; // ebx
  const unsigned __int16 *v7; // rax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[16]; // [rsp+28h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-20h]

  std::wstring::wstring((__int64)v10);
  string = 0;
  if ( (unsigned __int8)MapControl::LocaleMapConfiguration::getValueString(*(_QWORD *)(v4 + 32), v5, v10) )
  {
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
    v6 = Microsoft::WRL::Wrappers::HString::Set(&string, v7, v11);
    if ( v6 >= 0 )
      v6 = WindowsDuplicateString(string, a3);
  }
  else
  {
    v6 = -2147467259;
  }
  WindowsDeleteString(string);
  string = 0;
  std::wstring::_Tidy_deallocate(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023100  mov     [rsp+arg_8], rbx
0x180023105  push    rdi
0x180023106  sub     rsp, 50h
0x18002310a  mov     rax, cs:__security_cookie
0x180023111  xor     rax, rsp
0x180023114  mov     [rsp+58h+var_10], rax
0x180023119  mov     rdi, r8
0x18002311c  mov     r9, rcx
0x18002311f  lea     rcx, [rsp+58h+var_30]
0x180023124  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023129  nop
0x18002312a  mov     [rsp+58h+string], 0
0x180023133  lea     r8, [rsp+58h+var_30]
0x180023138  mov     rcx, [r9+20h]
0x18002313c  call    ?getValueString@LocaleMapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::LocaleMapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x180023141  test    al, al
0x180023143  jnz     short loc_18002314C
0x180023145  mov     ebx, 80004005h
0x18002314a  jmp     short loc_18002317E
0x18002314c  lea     rcx, [rsp+58h+var_30]
0x180023151  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023156  mov     rdx, rax; unsigned __int16 *
0x180023159  mov     r8d, [rsp+58h+var_20]; unsigned int
0x18002315e  lea     rcx, [rsp+58h+string]; this
0x180023163  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180023168  mov     ebx, eax
0x18002316a  test    eax, eax
0x18002316c  js      short loc_18002317E
0x18002316e  mov     rdx, rdi; newString
0x180023171  mov     rcx, [rsp+58h+string]; string
0x180023176  call    cs:__imp_WindowsDuplicateString
0x18002317c  mov     ebx, eax
0x18002317e  mov     rcx, [rsp+58h+string]; string
0x180023183  call    cs:__imp_WindowsDeleteString
0x180023189  mov     [rsp+58h+string], 0
0x180023192  lea     rcx, [rsp+58h+var_30]
0x180023197  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002319c  mov     eax, ebx
0x18002319e  mov     rcx, [rsp+58h+var_10]
0x1800231a3  xor     rcx, rsp; StackCookie
0x1800231a6  call    __security_check_cookie
0x1800231ab  mov     rbx, [rsp+58h+arg_8]
0x1800231b0  add     rsp, 50h
0x1800231b4  pop     rdi
0x1800231b5  retn
```
