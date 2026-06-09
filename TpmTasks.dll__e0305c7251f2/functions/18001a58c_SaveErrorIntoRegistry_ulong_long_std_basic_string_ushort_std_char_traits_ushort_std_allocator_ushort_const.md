# SaveErrorIntoRegistry(ulong,long,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001a58c`
- end: `0x18001a6e5`
- name: `?SaveErrorIntoRegistry@@YAXKJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x180009d98`
- `0x18000e48c`
- `0x180014350`
- `0x18001a58c`
- `0x180023634`
- `0x18002386c`
- `0x1800243e8`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a650`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a69e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a650`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a69e`

## string_xrefs

- `0x18001a5cf`: `Unknown update type %x, cannot save error into registry\n`
- `0x18001a600`: `LastUpdateError`
- `0x18001a615`: `LastUpdateErrorReason`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall SaveErrorIntoRegistry(unsigned int a1, int a2, __int64 a3)
{
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  _WORD *lpData; // rdx
  const WCHAR *v9; // r8
  DWORD cbData; // eax
  __int64 v11; // rax
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  int Data; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v16; // [rsp+50h] [rbp-29h]
  _BYTE v17[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v18[32]; // [rsp+80h] [rbp+7h] BYREF

  hKey = 0;
  GetRegistryPrefixForUpdateType(v15, a1);
  if ( v16 )
  {
    if ( (int)wil::reg::open_unique_key_nothrow(
                v6,
                L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
                &hKey,
                1) >= 0 )
    {
      std::operator+<unsigned short>(v18, v15, L"LastUpdateError");
      std::operator+<unsigned short>(v17, v15, L"LastUpdateErrorReason");
      Data = a2;
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
      RegSetKeyValueW(hKey, 0, v7, 4u, &Data, 4u);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      if ( lpData )
      {
        v11 = -1;
        do
          ++v11;
        while ( lpData[v11] );
        cbData = 2 * v11 + 2;
      }
      else
      {
        cbData = 0;
      }
      RegSetKeyValueW(hKey, 0, v9, 1u, lpData, cbData);
      std::wstring::_Tidy_deallocate(v17);
      std::wstring::_Tidy_deallocate(v18);
    }
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"Unknown update type %x, cannot save error into registry\n", a1);
  }
  std::wstring::_Tidy_deallocate(v15);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18001a58c  push    rbp
0x18001a58e  push    rbx
0x18001a58f  push    rsi
0x18001a590  push    rdi
0x18001a591  push    r14
0x18001a593  lea     rbp, [rsp-37h]
0x18001a598  sub     rsp, 0B0h
0x18001a59f  mov     rax, cs:__security_cookie
0x18001a5a6  xor     rax, rsp
0x18001a5a9  mov     [rbp+57h+var_30], rax
0x18001a5ad  mov     rsi, r8
0x18001a5b0  mov     edi, edx
0x18001a5b2  mov     ebx, ecx
0x18001a5b4  xor     r14d, r14d
0x18001a5b7  mov     [rbp+57h+hKey], r14
0x18001a5bb  mov     edx, ecx
0x18001a5bd  lea     rcx, [rbp+57h+var_90]
0x18001a5c1  call    ?GetRegistryPrefixForUpdateType@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetRegistryPrefixForUpdateType(ulong)
0x18001a5c6  nop
0x18001a5c7  cmp     [rbp+57h+var_80], r14
0x18001a5cb  jnz     short loc_18001A5E0
0x18001a5cd  mov     edx, ebx
0x18001a5cf  lea     rcx, aUnknownUpdateT_0; "Unknown update type %x, cannot save err"...
0x18001a5d6  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18001a5db  jmp     loc_18001A6B8
0x18001a5e0  mov     ebx, 1
0x18001a5e5  mov     r9d, ebx
0x18001a5e8  lea     r8, [rbp+57h+hKey]
0x18001a5ec  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18001a5f3  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001a5f8  test    eax, eax
0x18001a5fa  js      loc_18001A6B8
0x18001a600  lea     r8, aLastupdateerro; "LastUpdateError"
0x18001a607  lea     rdx, [rbp+57h+var_90]
0x18001a60b  lea     rcx, [rbp+57h+var_50]
0x18001a60f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001a614  nop
0x18001a615  lea     r8, aLastupdateerro_0; "LastUpdateErrorReason"
0x18001a61c  lea     rdx, [rbp+57h+var_90]
0x18001a620  lea     rcx, [rbp+57h+var_70]
0x18001a624  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001a629  mov     [rbp+57h+Data], edi
0x18001a62c  lea     rcx, [rbp+57h+var_50]
0x18001a630  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a635  mov     r8, rax; lpValueName
0x18001a638  lea     r9d, [rbx+3]; dwType
0x18001a63c  mov     [rsp+0D0h+cbData], r9d; cbData
0x18001a641  lea     rax, [rbp+57h+Data]
0x18001a645  mov     [rsp+0D0h+lpData], rax; lpData
0x18001a64a  xor     edx, edx; lpSubKey
0x18001a64c  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a650  call    cs:__imp_RegSetKeyValueW
0x18001a656  mov     rcx, rsi
0x18001a659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a65e  mov     rdx, rax
0x18001a661  lea     rcx, [rbp+57h+var_70]
0x18001a665  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a66a  mov     r8, rax; lpValueName
0x18001a66d  test    rdx, rdx
0x18001a670  jnz     short loc_18001A677
0x18001a672  mov     eax, r14d
0x18001a675  jmp     short loc_18001A68C
0x18001a677  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a67b  inc     rax
0x18001a67e  cmp     [rdx+rax*2], r14w
0x18001a683  jnz     short loc_18001A67B
0x18001a685  lea     eax, ds:2[rax*2]
0x18001a68c  mov     [rsp+0D0h+cbData], eax; cbData
0x18001a690  mov     [rsp+0D0h+lpData], rdx; lpData
0x18001a695  mov     r9d, ebx; dwType
0x18001a698  xor     edx, edx; lpSubKey
0x18001a69a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a69e  call    cs:__imp_RegSetKeyValueW
0x18001a6a4  lea     rcx, [rbp+57h+var_70]
0x18001a6a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6ad  nop
0x18001a6ae  lea     rcx, [rbp+57h+var_50]
0x18001a6b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6b7  nop
0x18001a6b8  lea     rcx, [rbp+57h+var_90]
0x18001a6bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6c1  nop
0x18001a6c2  lea     rcx, [rbp+57h+hKey]
0x18001a6c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a6cb  mov     rcx, [rbp+57h+var_30]
0x18001a6cf  xor     rcx, rsp; StackCookie
0x18001a6d2  call    __security_check_cookie
0x18001a6d7  add     rsp, 0B0h
0x18001a6de  pop     r14
0x18001a6e0  pop     rdi
0x18001a6e1  pop     rsi
0x18001a6e2  pop     rbx
0x18001a6e3  pop     rbp
0x18001a6e4  retn
```
