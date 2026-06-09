# MitigationLog<_MITIGATION_ACTION_LOG_RECORD,MitigationHistoryResultInternal>::SaveMitigationLogToRegistry(void)

- ea: `0x180053594`
- end: `0x1800537fc`
- name: `?SaveMitigationLogToRegistry@?$MitigationLog@U_MITIGATION_ACTION_LOG_RECORD@@UMitigationHistoryResultInternal@@@@IEAAJXZ`
- size: `616`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180052830`
- `0x18005298c`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800198b0`
- `0x180019f10`
- `0x18001fb04`
- `0x180024550`
- `0x180029eb0`
- `0x18002a488`
- `0x180053594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800536f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800536f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005376a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005376a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800536a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800536a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationLog<_MITIGATION_ACTION_LOG_RECORD,MitigationHistoryResultInternal>::SaveMitigationLogToRegistry(
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
             16 * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 4));
      if ( !v8 )
      {
        v16 = -2147483646;
        v11 = MitigationRegUtils::SetMitigationRegDWORD(
                &v16,
                *(unsigned int *)(a1 + 80),
                L"RecordsCount",
                0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 4));
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
         0xAAAAAAAAAAAAAAABuLL * ((v2 - *(_QWORD *)(a1 + 16)) >> 4));
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
0x180053594  push    rbp
0x180053596  push    rbx
0x180053597  push    rsi
0x180053598  push    rdi
0x180053599  lea     rbp, [rsp-3Fh]
0x18005359e  sub     rsp, 98h
0x1800535a5  mov     rax, cs:__security_cookie
0x1800535ac  xor     rax, rsp
0x1800535af  mov     [rbp+57h+var_30], rax
0x1800535b3  mov     rbx, rcx
0x1800535b6  mov     [rbp+57h+hKey], 0
0x1800535be  mov     r9, [rcx+18h]
0x1800535c2  cmp     [rcx+10h], r9
0x1800535c6  jnz     short loc_18005362C
0x1800535c8  mov     rdi, 0FFFFFFFF80000002h
0x1800535cf  mov     [rbp+57h+var_58], rdi
0x1800535d3  sub     r9, [rcx+10h]
0x1800535d7  sar     r9, 4
0x1800535db  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800535e5  imul    r9, rsi
0x1800535e9  mov     [rsp+0B0h+phkResult], 0; int
0x1800535f2  lea     r8, aRecordscount; "RecordsCount"
0x1800535f9  mov     edx, [rcx+50h]
0x1800535fc  lea     rcx, [rbp+57h+var_58]
0x180053600  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180053605  mov     ebx, eax
0x180053607  test    eax, eax
0x180053609  jns     loc_1800537D7
0x18005360f  mov     rcx, [rbp+5Fh]; this
0x180053613  mov     r9d, eax; char *
0x180053616  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005361d  mov     edx, 23Ch; void *
0x180053622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053627  jmp     loc_1800537D9
0x18005362c  lea     rcx, [rbp+57h+var_50]
0x180053630  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180053635  nop
0x180053636  lea     rdx, [rbp+57h+var_50]
0x18005363a  mov     ecx, [rbx+50h]
0x18005363d  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x180053642  mov     edi, eax
0x180053644  test    eax, eax
0x180053646  jns     short loc_180053671
0x180053648  mov     rcx, [rbp+5Fh]; this
0x18005364c  mov     r9d, eax; char *
0x18005364f  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053656  mov     edx, 241h; void *
0x18005365b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053660  nop
0x180053661  lea     rcx, [rbp+57h+var_50]
0x180053665  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005366a  mov     ebx, edi
0x18005366c  jmp     loc_1800537D9
0x180053671  xor     edx, edx
0x180053673  lea     rcx, [rbp+57h+hKey]
0x180053677  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005367c  lea     rcx, [rbp+57h+var_50]
0x180053680  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053685  mov     rdx, rax; lpSubKey
0x180053688  lea     rax, [rbp+57h+hKey]
0x18005368c  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180053691  mov     esi, 20006h
0x180053696  mov     r9d, esi; samDesired
0x180053699  xor     r8d, r8d; ulOptions
0x18005369c  mov     rdi, 0FFFFFFFF80000002h
0x1800536a3  mov     rcx, rdi; hKey
0x1800536a6  call    cs:__imp_RegOpenKeyExW
0x1800536ac  cmp     eax, 2
0x1800536af  jnz     short loc_1800536FE
0x1800536b1  xor     edx, edx
0x1800536b3  lea     rcx, [rbp+57h+hKey]
0x1800536b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800536bc  lea     rcx, [rbp+57h+var_50]
0x1800536c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800536c5  mov     rdx, rax; lpSubKey
0x1800536c8  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x1800536d1  lea     rax, [rbp+57h+hKey]
0x1800536d5  mov     [rsp+0B0h+var_78], rax; phkResult
0x1800536da  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800536e3  mov     [rsp+0B0h+samDesired], esi; samDesired
0x1800536e7  mov     dword ptr [rsp+0B0h+phkResult], 0; unsigned int
0x1800536ef  xor     r9d, r9d; lpClass
0x1800536f2  xor     r8d, r8d; Reserved
0x1800536f5  mov     rcx, rdi; hKey
0x1800536f8  call    cs:__imp_RegCreateKeyExW
0x1800536fe  test    eax, eax
0x180053700  jz      short loc_18005372A
0x180053702  mov     edx, 256h; void *
0x180053707  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005370e  mov     r9d, eax; char *
0x180053711  mov     rcx, [rbp+5Fh]; this
0x180053715  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005371a  mov     ebx, eax
0x18005371c  lea     rcx, [rbp+57h+var_50]
0x180053720  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053725  jmp     loc_1800537D9
0x18005372a  mov     rdx, [rbx+10h]
0x18005372e  mov     rax, [rbx+18h]
0x180053732  sub     rax, rdx
0x180053735  sar     rax, 4
0x180053739  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180053743  imul    rax, rsi
0x180053747  lea     eax, [rax+rax*2]
0x18005374a  shl     eax, 4
0x18005374d  mov     [rsp+0B0h+samDesired], eax; cbData
0x180053751  mov     [rsp+0B0h+phkResult], rdx; lpData
0x180053756  mov     r9d, 3; dwType
0x18005375c  xor     r8d, r8d; Reserved
0x18005375f  lea     rdx, ValueName; "Log"
0x180053766  mov     rcx, [rbp+57h+hKey]; hKey
0x18005376a  call    cs:__imp_RegSetValueExW
0x180053770  test    eax, eax
0x180053772  jz      short loc_18005377B
0x180053774  mov     edx, 263h
0x180053779  jmp     short loc_180053707
0x18005377b  mov     [rbp+57h+var_58], rdi
0x18005377f  mov     r9, [rbx+18h]
0x180053783  sub     r9, [rbx+10h]
0x180053787  sar     r9, 4
0x18005378b  imul    r9, rsi
0x18005378f  mov     [rsp+0B0h+phkResult], 0; int
0x180053798  lea     r8, aRecordscount; "RecordsCount"
0x18005379f  mov     edx, [rbx+50h]
0x1800537a2  lea     rcx, [rbp+57h+var_58]
0x1800537a6  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x1800537ab  mov     ebx, eax
0x1800537ad  test    eax, eax
0x1800537af  jns     short loc_1800537CE
0x1800537b1  mov     rcx, [rbp+5Fh]; this
0x1800537b5  mov     r9d, eax; char *
0x1800537b8  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800537bf  mov     edx, 265h; void *
0x1800537c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800537c9  jmp     loc_18005371C
0x1800537ce  lea     rcx, [rbp+57h+var_50]
0x1800537d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800537d7  xor     ebx, ebx
0x1800537d9  lea     rcx, [rbp+57h+hKey]
0x1800537dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800537e2  mov     eax, ebx
0x1800537e4  mov     rcx, [rbp+57h+var_30]
0x1800537e8  xor     rcx, rsp; StackCookie
0x1800537eb  call    __security_check_cookie
0x1800537f0  add     rsp, 98h
0x1800537f7  pop     rdi
0x1800537f8  pop     rsi
0x1800537f9  pop     rbx
0x1800537fa  pop     rbp
0x1800537fb  retn
```
