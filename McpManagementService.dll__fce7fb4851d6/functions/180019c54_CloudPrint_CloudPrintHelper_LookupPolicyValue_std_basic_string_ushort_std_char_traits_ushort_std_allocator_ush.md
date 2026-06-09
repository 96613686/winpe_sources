# CloudPrint::CloudPrintHelper::LookupPolicyValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180019c54`
- end: `0x180019d13`
- name: `?LookupPolicyValue@CloudPrintHelper@CloudPrint@@KAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z`
- size: `191`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180018f08`

## callees

- `0x1800067a4`
- `0x18000e164`
- `0x18000e5e8`
- `0x1800126a8`
- `0x180019c54`
- `0x18001c298`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyString` at `0x180019c80`
- `policymanager!PolicyManager_GetPolicyString` at `0x180019c80`

## string_xrefs

- `0x180019ce2`: `Failed to read policy string %s with %#x`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::LookupPolicyValue(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  int PolicyString; // eax
  unsigned int v6; // esi
  __int64 v7; // rcx
  const char *v8; // r9
  __int64 result; // rax
  __int64 v10; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _WORD *v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  PolicyString = PolicyManager_GetPolicyString(L"EnterpriseCloudPrint", v4, &v12);
  try
  {
    v6 = PolicyString;
    if ( PolicyString < 0 )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::LookupPolicyValue",
        L"Failed to read policy string %s with %#x",
        v10,
        v6);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
      result = v6;
    }
    else if ( v12 && *v12 )
    {
      if ( a2 )
      {
        std::_WChar_traits<unsigned short>::length(v12);
        std::wstring::_Assign<unsigned short>(a2, v7);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
      result = 0;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
      result = 1;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x755,
                           (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180019c54  push    rbx
0x180019c56  push    rsi
0x180019c57  push    rdi
0x180019c58  push    r14
0x180019c5a  sub     rsp, 28h
0x180019c5e  mov     rbx, rdx
0x180019c61  mov     rdi, rcx
0x180019c64  xor     r14d, r14d
0x180019c67  mov     [rsp+48h+arg_0], r14
0x180019c6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019c71  lea     r8, [rsp+48h+arg_0]
0x180019c76  mov     rdx, rax
0x180019c79  lea     rcx, aEnterpriseclou; "EnterpriseCloudPrint"
0x180019c80  call    cs:__imp_PolicyManager_GetPolicyString
0x180019c86  mov     esi, eax
0x180019c88  test    eax, eax
0x180019c8a  js      short loc_180019CD4
0x180019c8c  mov     rcx, [rsp+48h+arg_0]
0x180019c91  test    rcx, rcx
0x180019c94  jz      short loc_180019CC3
0x180019c96  cmp     [rcx], r14w
0x180019c9a  jz      short loc_180019CC3
0x180019c9c  test    rbx, rbx
0x180019c9f  jz      short loc_180019CB5
0x180019ca1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019ca6  mov     r8, rax
0x180019ca9  mov     rdx, rcx
0x180019cac  mov     rcx, rbx
0x180019caf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019cb4  nop
0x180019cb5  lea     rcx, [rsp+48h+arg_0]
0x180019cba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019cbf  xor     eax, eax
0x180019cc1  jmp     short loc_180019D08
0x180019cc3  lea     rcx, [rsp+48h+arg_0]
0x180019cc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019ccd  mov     eax, 1
0x180019cd2  jmp     short loc_180019D08
0x180019cd4  mov     rcx, rdi
0x180019cd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019cdc  mov     r9d, esi
0x180019cdf  mov     r8, rax
0x180019ce2  lea     rdx, aFailedToReadPo; "Failed to read policy string %s with %#"...
0x180019ce9  lea     rcx, aCloudprintClou_17; "CloudPrint::CloudPrintHelper::LookupPol"...
0x180019cf0  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180019cf5  nop
0x180019cf6  lea     rcx, [rsp+48h+arg_0]
0x180019cfb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019d00  mov     eax, esi
0x180019d02  jmp     short loc_180019D08
0x180019d04  mov     eax, dword ptr [rsp+48h+arg_0]
0x180019d08  add     rsp, 28h
0x180019d0c  pop     r14
0x180019d0e  pop     rdi
0x180019d0f  pop     rsi
0x180019d10  pop     rbx
0x180019d11  retn
```
