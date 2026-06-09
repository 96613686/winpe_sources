# ReadNetSetupPropertiesFromDriver

- ea: `0x180021350`
- end: `0x18002149c`
- name: `ReadNetSetupPropertiesFromDriver`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x180021350`
- `0x1800214a4`
- `0x1800269c8`
- `0x1800285cc`
- `0x180028784`
- `0x18002d964`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall ReadNetSetupPropertiesFromDriver(__int64 a1, HKEY *a2, __int64 a3)
{
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r10
  HKEY *v10; // [rsp+30h] [rbp-49h] BYREF
  HKEY *v11; // [rsp+38h] [rbp-41h] BYREF
  int v12; // [rsp+40h] [rbp-39h]
  _BYTE v13[8]; // [rsp+48h] [rbp-31h] BYREF
  int v14; // [rsp+50h] [rbp-29h]
  HKEY v15; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v17[8]; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v18[4]; // [rsp+88h] [rbp+Fh] BYREF
  char v19; // [rsp+A8h] [rbp+2Fh]

  RegistryKey::TryOpenSubKey(a2, (RegistryKey *)&v15, L"NetSetupProperties", 1u, 0);
  if ( v15 )
  {
    v10 = &v15;
    v11 = &v15;
    v5 = 0;
    v12 = 0;
    RegistryValueEnumerator::end((RegistryKey **)&v10, (__int64)v13);
    while ( 1 )
    {
      if ( v5 == v14 )
        return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
      RegistryValueIterator::operator*((__int64)&v11, (__int64)v16);
      NetSetup2::details::TransactionBase::TryReflectOnProperty(a1, v17, v16);
      if ( v19 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_S(*(_QWORD *)(v8 + 16), 48, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v7);
LABEL_9:
        if ( v19 )
          std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v18);
      }
      std::wstring::_Tidy_deallocate((__int64)v16);
      v12 = ++v5;
    }
    v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    ReadNetSetupPropertyFromDriver(&v15, v6, v17, a3);
    goto LABEL_9;
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x180021350  mov     [rsp-8+arg_18], rbx
0x180021355  push    rbp
0x180021356  push    rsi
0x180021357  push    rdi
0x180021358  lea     rbp, [rsp-47h]
0x18002135d  sub     rsp, 0C0h
0x180021364  mov     rax, cs:__security_cookie
0x18002136b  xor     rax, rsp
0x18002136e  mov     [rbp+57h+var_20], rax
0x180021372  mov     rsi, r8
0x180021375  mov     rax, rdx
0x180021378  mov     rdi, rcx
0x18002137b  mov     [rsp+0D0h+var_B0], 0
0x180021384  mov     r9d, 1
0x18002138a  lea     r8, aNetsetupproper; "NetSetupProperties"
0x180021391  lea     rdx, [rbp+57h+var_78]
0x180021395  mov     rcx, rax
0x180021398  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18002139d  nop
0x18002139e  cmp     [rbp+57h+var_78], 0
0x1800213a3  jz      loc_180021474
0x1800213a9  lea     rax, [rbp+57h+var_78]
0x1800213ad  mov     [rbp+57h+var_A0], rax
0x1800213b1  lea     rax, [rbp+57h+var_78]
0x1800213b5  mov     [rbp+57h+var_98], rax
0x1800213b9  xor     ebx, ebx
0x1800213bb  mov     [rbp+57h+var_90], ebx
0x1800213be  lea     rdx, [rbp+57h+var_88]
0x1800213c2  lea     rcx, [rbp+57h+var_A0]
0x1800213c6  call    ?end@RegistryValueEnumerator@@QEBA?AVRegistryValueIterator@@XZ; RegistryValueEnumerator::end(void)
0x1800213cb  cmp     ebx, [rbp+57h+var_80]
0x1800213ce  jz      loc_180021474
0x1800213d4  lea     rdx, [rbp+57h+var_70]
0x1800213d8  lea     rcx, [rbp+57h+var_98]
0x1800213dc  call    ??DRegistryValueIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RegistryValueIterator::operator*(void)
0x1800213e1  nop
0x1800213e2  lea     r8, [rbp+57h+var_70]
0x1800213e6  lea     rdx, [rbp+57h+var_50]
0x1800213ea  mov     rcx, rdi
0x1800213ed  call    ?TryReflectOnProperty@TransactionBase@details@NetSetup2@@QEAA?AV?$Optional@VReflectedProperty@NetSetup2@@@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetup2::details::TransactionBase::TryReflectOnProperty(std::wstring const &)
0x1800213f2  cmp     [rbp+57h+var_28], 0
0x1800213f6  jz      short loc_180021416
0x1800213f8  lea     rcx, [rbp+57h+var_70]
0x1800213fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021401  mov     rdx, rax
0x180021404  mov     r9, rsi
0x180021407  lea     r8, [rbp+57h+var_50]
0x18002140b  lea     rcx, [rbp+57h+var_78]
0x18002140f  call    ReadNetSetupPropertyFromDriver
0x180021414  jmp     short loc_180021451
0x180021416  lea     rax, WPP_GLOBAL_Control
0x18002141d  mov     r10, cs:WPP_GLOBAL_Control
0x180021424  cmp     r10, rax
0x180021427  jz      short loc_180021461
0x180021429  cmp     byte ptr [r10+19h], 3
0x18002142e  jb      short loc_180021461
0x180021430  lea     rcx, [rbp+57h+var_70]
0x180021434  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021439  mov     r9, rax
0x18002143c  mov     edx, 30h ; '0'
0x180021441  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180021448  mov     rcx, [r10+10h]
0x18002144c  call    WPP_SF_S
0x180021451  cmp     [rbp+57h+var_28], 0
0x180021455  jz      short loc_180021461
0x180021457  lea     rcx, [rbp+57h+var_48]
0x18002145b  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x180021460  nop
0x180021461  lea     rcx, [rbp+57h+var_70]
0x180021465  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002146a  inc     ebx
0x18002146c  mov     [rbp+57h+var_90], ebx
0x18002146f  jmp     loc_1800213CB
0x180021474  lea     rcx, [rbp+57h+var_78]
0x180021478  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002147d  mov     rcx, [rbp+57h+var_20]
0x180021481  xor     rcx, rsp; StackCookie
0x180021484  call    __security_check_cookie
0x180021489  mov     rbx, [rsp+0D0h+arg_18]
0x180021491  add     rsp, 0C0h
0x180021498  pop     rdi
0x180021499  pop     rsi
0x18002149a  pop     rbp
0x18002149b  retn
```
