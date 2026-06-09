# PrintCore::PrintSupportDebugHelper::AddPsaBrokerProcessId(uint)

- ea: `0x18000b500`
- end: `0x18000b5d1`
- name: `?AddPsaBrokerProcessId@PrintSupportDebugHelper@PrintCore@@SAXI@Z`
- size: `209`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b4d8`

## callees

- `0x180003ca0`
- `0x180008698`
- `0x18000a014`
- `0x18000b500`
- `0x18000bc48`
- `0x1800127a4`
- `0x180012820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000b57c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000b57c`

## string_xrefs

- `0x18000b570`: `BrokerProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PrintCore::PrintSupportDebugHelper::AddPsaBrokerProcessId(int a1)
{
  HKEY v2; // rbx
  int v3; // eax
  int lpData; // [rsp+20h] [rbp-58h]
  __int64 Data; // [rsp+30h] [rbp-48h] BYREF
  HKEY v6; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  std::wstring::wstring((__int64)v7, (__int64)L"Printers\\PsaDebuggingData");
  Data = -2147483647;
  v2 = (HKEY)PrintCore::RegHelpers::CreateOrOpenKey(&Data, v7);
  v6 = v2;
  std::wstring::_Tidy_deallocate(v7);
  LODWORD(Data) = a1;
  v3 = RegSetKeyValueW(v2, 0, L"BrokerProcessId", 4u, &Data, 4u);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PrintSupportDebugHelper.h",
      (const char *)(unsigned int)v3,
      lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x18000b500  mov     [rsp+arg_8], rbx
0x18000b505  push    rdi
0x18000b506  sub     rsp, 70h
0x18000b50a  mov     rax, cs:__security_cookie
0x18000b511  xor     rax, rsp
0x18000b514  mov     [rsp+78h+var_18], rax
0x18000b519  mov     edi, ecx
0x18000b51b  lea     rdx, aPrintersPsadeb; "Printers\\PsaDebuggingData"
0x18000b522  lea     rcx, [rsp+78h+var_38]
0x18000b527  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000b52c  nop
0x18000b52d  mov     [rsp+78h+Data], 0FFFFFFFF80000001h
0x18000b536  lea     rdx, [rsp+78h+var_38]
0x18000b53b  lea     rcx, [rsp+78h+Data]
0x18000b540  call    ?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x18000b545  mov     rbx, rax
0x18000b548  mov     [rsp+78h+var_40], rax
0x18000b54d  lea     rcx, [rsp+78h+var_38]
0x18000b552  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b557  mov     dword ptr [rsp+78h+Data], edi
0x18000b55b  mov     r9d, 4; dwType
0x18000b561  mov     [rsp+78h+cbData], r9d; cbData
0x18000b566  lea     rax, [rsp+78h+Data]
0x18000b56b  mov     [rsp+78h+lpData], rax; int
0x18000b570  lea     r8, ValueName; "BrokerProcessId"
0x18000b577  xor     edx, edx; lpSubKey
0x18000b579  mov     rcx, rbx; hKey
0x18000b57c  call    cs:__imp_RegSetKeyValueW
0x18000b582  test    eax, eax
0x18000b584  jle     short loc_18000B58E
0x18000b586  movzx   eax, ax
0x18000b589  or      eax, 80070000h
0x18000b58e  mov     rcx, [rsp+78h]; this
0x18000b593  test    eax, eax
0x18000b595  js      short loc_18000B5BC
0x18000b597  lea     rcx, [rsp+78h+var_40]
0x18000b59c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b5a1  mov     rcx, [rsp+78h+var_18]
0x18000b5a6  xor     rcx, rsp; StackCookie
0x18000b5a9  call    __security_check_cookie
0x18000b5ae  mov     rbx, [rsp+78h+arg_8]
0x18000b5b6  add     rsp, 70h
0x18000b5ba  pop     rdi
0x18000b5bb  retn
0x18000b5bc  mov     r9d, eax; char *
0x18000b5bf  lea     r8, aOnecoreuapPrin_22; "onecoreuap\\printscan\\print\\workflow"...
0x18000b5c6  mov     edx, 56h ; 'V'; void *
0x18000b5cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
