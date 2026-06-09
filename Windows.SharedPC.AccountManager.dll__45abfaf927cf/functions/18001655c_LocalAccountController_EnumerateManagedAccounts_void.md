# LocalAccountController::EnumerateManagedAccounts(void)

- ea: `0x18001655c`
- end: `0x1800166af`
- name: `?EnumerateManagedAccounts@LocalAccountController@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `339`
- prototype: `HKEY __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800167f0`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000f454`
- `0x1800146b0`
- `0x1800148d0`
- `0x18001655c`
- `0x180016ab4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001660d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001660d`

## string_xrefs

- `0x18001659e`: `CreatedLocalAccounts`
- `0x180016674`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
HKEY __fastcall LocalAccountController::EnumerateManagedAccounts(HKEY a1)
{
  HKEY SharedPCKey; // rbx
  DWORD i; // esi
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY v9[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[40]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v9[1] = a1;
  std::vector<SessionUserInfo>::vector<SessionUserInfo>(a1);
  std::wstring::wstring((__int64)v11, (__int64)L"CreatedLocalAccounts");
  SharedPCKey = (HKEY)GetSharedPCKey(v11, 8);
  v9[0] = SharedPCKey;
  std::wstring::_Tidy_deallocate((__int64)v11);
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    v4 = RegEnumKeyExW(SharedPCKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v4 )
      break;
    std::wstring::wstring((__int64)v10, (__int64)Name);
    v5 = *((_QWORD *)a1 + 1);
    if ( v5 == *((_QWORD *)a1 + 2) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, *((_QWORD *)a1 + 1), v10);
    }
    else
    {
      std::_Construct_in_place<std::wstring,std::wstring>(v5, v10);
      *((_QWORD *)a1 + 1) += 32LL;
    }
    std::wstring::_Tidy_deallocate((__int64)v10);
  }
  if ( v4 != 259 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x72,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v4,
      lpReserved);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v9);
  return a1;
}

```

## disassembly

```asm
0x18001655c  push    rbp
0x18001655e  push    rbx
0x18001655f  push    rsi
0x180016560  push    rdi
0x180016561  lea     rbp, [rsp-1C8h]
0x180016569  sub     rsp, 2C8h
0x180016570  mov     rax, cs:__security_cookie
0x180016577  xor     rax, rsp
0x18001657a  mov     [rbp+1E0h+var_30], rax
0x180016581  mov     rdi, rcx
0x180016584  mov     [rsp+2E0h+var_290], rcx
0x180016589  mov     [rsp+2E0h+var_2A0], 0
0x180016591  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x180016596  mov     [rsp+2E0h+var_2A0], 1
0x18001659e  lea     rdx, aCreatedlocalac; "CreatedLocalAccounts"
0x1800165a5  lea     rcx, [rsp+2E0h+var_268]
0x1800165aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800165af  nop
0x1800165b0  mov     edx, 8
0x1800165b5  lea     rcx, [rsp+2E0h+var_268]
0x1800165ba  call    ?GetSharedPCKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCKey(std::wstring const &,ulong)
0x1800165bf  mov     rbx, rax
0x1800165c2  mov     [rsp+2E0h+var_298], rax
0x1800165c7  lea     rcx, [rsp+2E0h+var_268]
0x1800165cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800165d1  xor     esi, esi
0x1800165d3  mov     [rsp+2E0h+cchName], 104h
0x1800165db  mov     [rsp+2E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800165e4  mov     [rsp+2E0h+lpcchClass], 0; lpcchClass
0x1800165ed  mov     [rsp+2E0h+lpClass], 0; lpClass
0x1800165f6  mov     [rsp+2E0h+lpReserved], 0; unsigned int
0x1800165ff  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180016604  lea     r8, [rbp+1E0h+Name]; lpName
0x180016608  mov     edx, esi; dwIndex
0x18001660a  mov     rcx, rbx; hKey
0x18001660d  call    cs:__imp_RegEnumKeyExW
0x180016613  test    eax, eax
0x180016615  jnz     short loc_180016663
0x180016617  lea     rdx, [rbp+1E0h+Name]
0x18001661b  lea     rcx, [rsp+2E0h+var_288]
0x180016620  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016625  nop
0x180016626  mov     rcx, [rdi+8]
0x18001662a  cmp     rcx, [rdi+10h]
0x18001662e  jz      short loc_180016641
0x180016630  lea     rdx, [rsp+2E0h+var_288]
0x180016635  call    ??$_Construct_in_place@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@@Z; std::_Construct_in_place<std::wstring,std::wstring>(std::wstring &,std::wstring &&)
0x18001663a  add     qword ptr [rdi+8], 20h ; ' '
0x18001663f  jmp     short loc_180016652
0x180016641  lea     r8, [rsp+2E0h+var_288]
0x180016646  mov     rdx, rcx
0x180016649  mov     rcx, rdi
0x18001664c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180016651  nop
0x180016652  lea     rcx, [rsp+2E0h+var_288]
0x180016657  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001665c  inc     esi
0x18001665e  jmp     loc_1800165D3
0x180016663  cmp     eax, 103h
0x180016668  jz      short loc_180016686
0x18001666a  mov     rcx, [rbp+1E8h]; this
0x180016671  mov     r9d, eax; char *
0x180016674  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001667b  mov     edx, 72h ; 'r'; void *
0x180016680  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016686  lea     rcx, [rsp+2E0h+var_298]
0x18001668b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016690  mov     rax, rdi
0x180016693  mov     rcx, [rbp+1E0h+var_30]
0x18001669a  xor     rcx, rsp; StackCookie
0x18001669d  call    __security_check_cookie
0x1800166a2  add     rsp, 2C8h
0x1800166a9  pop     rdi
0x1800166aa  pop     rsi
0x1800166ab  pop     rbx
0x1800166ac  pop     rbp
0x1800166ad  retn
```
