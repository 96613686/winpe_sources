# MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::SaveMitigationLogToRegistry(void)

- ea: `0x1800208b0`
- end: `0x180020b15`
- name: `?SaveMitigationLogToRegistry@?$MitigationLog@U_AVAILABLE_MITIGATION_RECORD@@UMitigationResultInternal@@@@IEAAJXZ`
- size: `613`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001f63c`
- `0x180050ec4`
- `0x180051828`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800198b0`
- `0x180019f10`
- `0x18001fb04`
- `0x1800208b0`
- `0x180024550`
- `0x180029eb0`
- `0x18002a488`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020a14`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020a14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020a83`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020a83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800209c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800209c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::SaveMitigationLogToRegistry(
        __int64 a1)
{
  __int64 v2; // r9
  int v3; // eax
  unsigned int v4; // ebx
  int MitigationRegistryPath; // eax
  unsigned int v6; // edi
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  const WCHAR *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  int phkResult; // [rsp+20h] [rbp-39h]
  unsigned int phkResulta; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  __int64 v16; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  hKey = 0;
  v2 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 16) != v2 )
  {
    std::wstring::wstring((__int64)v17);
    MitigationRegistryPath = MitigationRegUtils::GetMitigationRegistryPath(*(_DWORD *)(a1 + 80), (__int64)v17);
    v6 = MitigationRegistryPath;
    if ( MitigationRegistryPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
        (const char *)(unsigned int)MitigationRegistryPath,
        phkResult);
      std::wstring::_Tidy_deallocate(v17);
      v4 = v6;
      goto LABEL_18;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20006u, &hKey);
    if ( v8 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    }
    if ( v8 )
    {
      v10 = 598;
    }
    else
    {
      v8 = RegSetValueExW(
             hKey,
             L"Log",
             0,
             3u,
             *(const BYTE **)(a1 + 16),
             4 * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 2));
      if ( !v8 )
      {
        v16 = -2147483646;
        v11 = MitigationRegUtils::SetMitigationRegDWORD(
                &v16,
                *(unsigned int *)(a1 + 80),
                L"RecordsCount",
                0x2E8BA2E8BA2E8BA3LL * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 2));
        v4 = v11;
        if ( v11 >= 0 )
        {
          std::wstring::_Tidy_deallocate(v17);
          goto LABEL_17;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
          (const char *)(unsigned int)v11,
          0);
LABEL_11:
        std::wstring::_Tidy_deallocate(v17);
        goto LABEL_18;
      }
      v10 = 611;
    }
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
           (const char *)v8,
           phkResulta);
    goto LABEL_11;
  }
  v16 = -2147483646;
  v3 = MitigationRegUtils::SetMitigationRegDWORD(
         &v16,
         *(unsigned int *)(a1 + 80),
         L"RecordsCount",
         0x2E8BA2E8BA2E8BA3LL * ((v2 - *(_QWORD *)(a1 + 16)) >> 2));
  v4 = v3;
  if ( v3 >= 0 )
  {
LABEL_17:
    v4 = 0;
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23C,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
    (const char *)(unsigned int)v3,
    0);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x1800208b0  push    rbp
0x1800208b2  push    rbx
0x1800208b3  push    rsi
0x1800208b4  push    rdi
0x1800208b5  lea     rbp, [rsp-3Fh]
0x1800208ba  sub     rsp, 98h
0x1800208c1  mov     rax, cs:__security_cookie
0x1800208c8  xor     rax, rsp
0x1800208cb  mov     [rbp+57h+var_30], rax
0x1800208cf  mov     rbx, rcx
0x1800208d2  mov     [rbp+57h+hKey], 0
0x1800208da  mov     r9, [rcx+18h]
0x1800208de  cmp     [rcx+10h], r9
0x1800208e2  jnz     short loc_180020948
0x1800208e4  mov     rdi, 0FFFFFFFF80000002h
0x1800208eb  mov     [rbp+57h+var_58], rdi
0x1800208ef  sub     r9, [rcx+10h]
0x1800208f3  sar     r9, 2
0x1800208f7  mov     rsi, 2E8BA2E8BA2E8BA3h
0x180020901  imul    r9, rsi
0x180020905  mov     [rsp+0B0h+phkResult], 0; int
0x18002090e  lea     r8, aRecordscount; "RecordsCount"
0x180020915  mov     edx, [rcx+50h]
0x180020918  lea     rcx, [rbp+57h+var_58]
0x18002091c  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180020921  mov     ebx, eax
0x180020923  test    eax, eax
0x180020925  jns     loc_180020AF0
0x18002092b  mov     rcx, [rbp+5Fh]; this
0x18002092f  mov     r9d, eax; char *
0x180020932  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180020939  mov     edx, 23Ch; void *
0x18002093e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020943  jmp     loc_180020AF2
0x180020948  lea     rcx, [rbp+57h+var_50]
0x18002094c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020951  nop
0x180020952  lea     rdx, [rbp+57h+var_50]
0x180020956  mov     ecx, [rbx+50h]
0x180020959  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x18002095e  mov     edi, eax
0x180020960  test    eax, eax
0x180020962  jns     short loc_18002098D
0x180020964  mov     rcx, [rbp+5Fh]; this
0x180020968  mov     r9d, eax; char *
0x18002096b  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180020972  mov     edx, 241h; void *
0x180020977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002097c  nop
0x18002097d  lea     rcx, [rbp+57h+var_50]
0x180020981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020986  mov     ebx, edi
0x180020988  jmp     loc_180020AF2
0x18002098d  xor     edx, edx
0x18002098f  lea     rcx, [rbp+57h+hKey]
0x180020993  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180020998  lea     rcx, [rbp+57h+var_50]
0x18002099c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800209a1  mov     rdx, rax; lpSubKey
0x1800209a4  lea     rax, [rbp+57h+hKey]
0x1800209a8  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800209ad  mov     esi, 20006h
0x1800209b2  mov     r9d, esi; samDesired
0x1800209b5  xor     r8d, r8d; ulOptions
0x1800209b8  mov     rdi, 0FFFFFFFF80000002h
0x1800209bf  mov     rcx, rdi; hKey
0x1800209c2  call    cs:__imp_RegOpenKeyExW
0x1800209c8  cmp     eax, 2
0x1800209cb  jnz     short loc_180020A1A
0x1800209cd  xor     edx, edx
0x1800209cf  lea     rcx, [rbp+57h+hKey]
0x1800209d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800209d8  lea     rcx, [rbp+57h+var_50]
0x1800209dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800209e1  mov     rdx, rax; lpSubKey
0x1800209e4  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x1800209ed  lea     rax, [rbp+57h+hKey]
0x1800209f1  mov     [rsp+0B0h+var_78], rax; phkResult
0x1800209f6  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800209ff  mov     [rsp+0B0h+samDesired], esi; samDesired
0x180020a03  mov     dword ptr [rsp+0B0h+phkResult], 0; unsigned int
0x180020a0b  xor     r9d, r9d; lpClass
0x180020a0e  xor     r8d, r8d; Reserved
0x180020a11  mov     rcx, rdi; hKey
0x180020a14  call    cs:__imp_RegCreateKeyExW
0x180020a1a  test    eax, eax
0x180020a1c  jz      short loc_180020A46
0x180020a1e  mov     edx, 256h; void *
0x180020a23  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180020a2a  mov     r9d, eax; char *
0x180020a2d  mov     rcx, [rbp+5Fh]; this
0x180020a31  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020a36  mov     ebx, eax
0x180020a38  lea     rcx, [rbp+57h+var_50]
0x180020a3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020a41  jmp     loc_180020AF2
0x180020a46  mov     rdx, [rbx+10h]
0x180020a4a  mov     rax, [rbx+18h]
0x180020a4e  sub     rax, rdx
0x180020a51  sar     rax, 2
0x180020a55  mov     rsi, 2E8BA2E8BA2E8BA3h
0x180020a5f  imul    rax, rsi
0x180020a63  imul    eax, 2Ch ; ','
0x180020a66  mov     [rsp+0B0h+samDesired], eax; cbData
0x180020a6a  mov     [rsp+0B0h+phkResult], rdx; lpData
0x180020a6f  mov     r9d, 3; dwType
0x180020a75  xor     r8d, r8d; Reserved
0x180020a78  lea     rdx, ValueName; "Log"
0x180020a7f  mov     rcx, [rbp+57h+hKey]; hKey
0x180020a83  call    cs:__imp_RegSetValueExW
0x180020a89  test    eax, eax
0x180020a8b  jz      short loc_180020A94
0x180020a8d  mov     edx, 263h
0x180020a92  jmp     short loc_180020A23
0x180020a94  mov     [rbp+57h+var_58], rdi
0x180020a98  mov     r9, [rbx+18h]
0x180020a9c  sub     r9, [rbx+10h]
0x180020aa0  sar     r9, 2
0x180020aa4  imul    r9, rsi
0x180020aa8  mov     [rsp+0B0h+phkResult], 0; int
0x180020ab1  lea     r8, aRecordscount; "RecordsCount"
0x180020ab8  mov     edx, [rbx+50h]
0x180020abb  lea     rcx, [rbp+57h+var_58]
0x180020abf  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180020ac4  mov     ebx, eax
0x180020ac6  test    eax, eax
0x180020ac8  jns     short loc_180020AE7
0x180020aca  mov     rcx, [rbp+5Fh]; this
0x180020ace  mov     r9d, eax; char *
0x180020ad1  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180020ad8  mov     edx, 265h; void *
0x180020add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ae2  jmp     loc_180020A38
0x180020ae7  lea     rcx, [rbp+57h+var_50]
0x180020aeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020af0  xor     ebx, ebx
0x180020af2  lea     rcx, [rbp+57h+hKey]
0x180020af6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020afb  mov     eax, ebx
0x180020afd  mov     rcx, [rbp+57h+var_30]
0x180020b01  xor     rcx, rsp; StackCookie
0x180020b04  call    __security_check_cookie
0x180020b09  add     rsp, 98h
0x180020b10  pop     rdi
0x180020b11  pop     rsi
0x180020b12  pop     rbx
0x180020b13  pop     rbp
0x180020b14  retn
```
