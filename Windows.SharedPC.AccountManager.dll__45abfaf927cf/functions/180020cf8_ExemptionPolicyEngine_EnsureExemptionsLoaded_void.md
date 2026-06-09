# ExemptionPolicyEngine::EnsureExemptionsLoaded(void)

- ea: `0x180020cf8`
- end: `0x180020dec`
- name: `?EnsureExemptionsLoaded@ExemptionPolicyEngine@@AEAAXXZ`
- size: `244`
- prototype: `void __fastcall(ExemptionPolicyEngine *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020e10`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000cd50`
- `0x18001238c`
- `0x180013dcc`
- `0x18001bcfc`
- `0x18001d01c`
- `0x18001deac`
- `0x180020cf8`
- `0x180022560`
- `0x1800227e4`

## string_xrefs

- `0x180020da8`: `Loaded exemption from the registry: User SID: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall ExemptionPolicyEngine::EnsureExemptionsLoaded(ExemptionPolicyEngine *this)
{
  HKEY SharedPCRegistryKeyIfExists; // rbx
  __int64 KeySubkeyNames; // rax
  _QWORD **v4; // rdi
  _QWORD *i; // rbx
  __int64 v6; // rax
  HKEY v7; // [rsp+20h] [rbp-29h] BYREF
  HKEY v8; // [rsp+28h] [rbp-21h] BYREF
  _BYTE v9[32]; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v10[8]; // [rsp+50h] [rbp+7h] BYREF

  if ( !*((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 1;
    std::wstring::wstring((__int64)v9, (__int64)L"Exemptions");
    SharedPCRegistryKeyIfExists = (HKEY)GetSharedPCRegistryKeyIfExists(v9);
    v8 = SharedPCRegistryKeyIfExists;
    std::wstring::_Tidy_deallocate((__int64)v9);
    if ( SharedPCRegistryKeyIfExists )
    {
      v7 = SharedPCRegistryKeyIfExists;
      KeySubkeyNames = GetKeySubkeyNames(v10, &v7);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
        (__int64)this + 80,
        KeySubkeyNames);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v10);
      v4 = (_QWORD **)*((_QWORD *)this + 11);
      for ( i = *v4; i != v4; i = (_QWORD *)*i )
      {
        std::wstring::wstring(v10, i + 2);
        v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        PolicyTelemetry::TraceLoggingInfo("Loaded exemption from the registry: User SID: %ws", v6);
        std::wstring::_Tidy_deallocate((__int64)v10);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180020cf8  mov     [rsp-8+arg_8], rbx
0x180020cfd  mov     [rsp-8+arg_10], rdi
0x180020d02  push    rbp
0x180020d03  lea     rbp, [rsp-57h]
0x180020d08  sub     rsp, 0A0h
0x180020d0f  mov     rax, cs:__security_cookie
0x180020d16  xor     rax, rsp
0x180020d19  mov     [rbp+57h+var_10], rax
0x180020d1d  mov     rdi, rcx
0x180020d20  cmp     byte ptr [rcx+48h], 0
0x180020d24  jnz     loc_180020DCB
0x180020d2a  mov     byte ptr [rcx+48h], 1
0x180020d2e  lea     rdx, aExemptions; "Exemptions"
0x180020d35  lea     rcx, [rbp+57h+var_70]
0x180020d39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020d3e  nop
0x180020d3f  lea     rcx, [rbp+57h+var_70]
0x180020d43  call    ?GetSharedPCRegistryKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCRegistryKeyIfExists(std::wstring const &,ulong)
0x180020d48  mov     rbx, rax
0x180020d4b  mov     [rbp+57h+var_78], rax
0x180020d4f  lea     rcx, [rbp+57h+var_70]
0x180020d53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020d58  test    rbx, rbx
0x180020d5b  jz      short loc_180020DC2
0x180020d5d  mov     [rbp+57h+var_80], rbx
0x180020d61  lea     rdx, [rbp+57h+var_80]
0x180020d65  lea     rcx, [rbp+57h+var_50]
0x180020d69  call    ?GetKeySubkeyNames@@YA?AV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z; GetKeySubkeyNames(HKEY__ * const &)
0x180020d6e  lea     rcx, [rdi+50h]
0x180020d72  mov     rdx, rax
0x180020d75  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x180020d7a  lea     rcx, [rbp+57h+var_50]
0x180020d7e  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180020d83  mov     rdi, [rdi+58h]
0x180020d87  mov     rbx, [rdi]
0x180020d8a  cmp     rbx, rdi
0x180020d8d  jz      short loc_180020DC2
0x180020d8f  lea     rdx, [rbx+10h]
0x180020d93  lea     rcx, [rbp+57h+var_50]
0x180020d97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020d9c  lea     rcx, [rbp+57h+var_50]
0x180020da0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020da5  mov     rdx, rax
0x180020da8  lea     rcx, aLoadedExemptio; "Loaded exemption from the registry: Use"...
0x180020daf  call    ?TraceLoggingInfo@PolicyTelemetry@@SAXPEBDZZ; PolicyTelemetry::TraceLoggingInfo(char const *,...)
0x180020db4  lea     rcx, [rbp+57h+var_50]
0x180020db8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020dbd  mov     rbx, [rbx]
0x180020dc0  jmp     short loc_180020D8A
0x180020dc2  lea     rcx, [rbp+57h+var_78]
0x180020dc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020dcb  mov     rcx, [rbp+57h+var_10]
0x180020dcf  xor     rcx, rsp; StackCookie
0x180020dd2  call    __security_check_cookie
0x180020dd7  lea     r11, [rsp+0A0h+var_s0]
0x180020ddf  mov     rbx, [r11+18h]
0x180020de3  mov     rdi, [r11+20h]
0x180020de7  mov     rsp, r11
0x180020dea  pop     rbp
0x180020deb  retn
```
