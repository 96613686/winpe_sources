# McpService::GetAadTenantId(ushort * *)

- ea: `0x180025ba0`
- end: `0x180025cf6`
- name: `?GetAadTenantId@McpService@@UEAAJPEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(McpService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180003a60`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x180013598`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x180025ba0`

## string_xrefs

- `0x180025bd1`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180025c18`: `McpService::GetAadTenantId`
- `0x180025c77`: `McpService::GetAadTenantId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetAadTenantId(McpService *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // r8
  int AadTenantId; // eax
  unsigned int v7; // edi
  _WORD *v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rax
  int v12; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v13; // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+38h] [rbp-40h]
  _BYTE v16[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    std::wstring::wstring((__int64)v16);
    AadTenantId = CloudPrint::CloudPrintHelper::GetAadTenantId(*(_QWORD *)(v5 + 24), v16);
    v7 = AadTenantId;
    if ( AadTenantId >= 0 )
    {
      v13 = 0;
      v14 = 0;
      v15 = 0;
      v8 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&v13, v8);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v11 = v13;
        v13 = 0;
        v15 = 0;
        v14 = 0;
        *a2 = v11;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = 0;
      }
      else
      {
        McpManagementTelemetry::WriteDbgTraceWarning(
          "McpService::GetAadTenantId",
          L"Failed to init aadTenantIdStr string. hr=%#x",
          (unsigned int)v9);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = v10;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetAadTenantId",
        L"Failed to GetAadTenantId. hr=%#x",
        (unsigned int)AadTenantId);
      std::wstring::_Tidy_deallocate((__int64)v16);
      result = v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      v12);
    result = 2147500035LL;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xAB,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                               v3);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180025ba0  mov     [rsp+arg_10], rbx
0x180025ba5  push    rdi
0x180025ba6  sub     rsp, 70h
0x180025baa  mov     rax, cs:__security_cookie
0x180025bb1  xor     rax, rsp
0x180025bb4  mov     [rsp+78h+var_18], rax
0x180025bb9  mov     rbx, rdx
0x180025bbc  mov     r8, rcx
0x180025bbf  test    rdx, rdx
0x180025bc2  jnz     short loc_180025BE9
0x180025bc4  mov     rcx, [rsp+78h]; this
0x180025bc9  mov     ebx, 80004003h
0x180025bce  mov     r9d, ebx; char *
0x180025bd1  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025bd8  mov     edx, 94h; void *
0x180025bdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025be2  mov     eax, ebx
0x180025be4  jmp     loc_180025CDA
0x180025be9  mov     qword ptr [rdx], 0
0x180025bf0  lea     rcx, [rsp+78h+var_38]
0x180025bf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180025bfa  lea     rdx, [rsp+78h+var_38]
0x180025bff  mov     rcx, [r8+18h]
0x180025c03  call    ?GetAadTenantId@CloudPrintHelper@CloudPrint@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetAadTenantId(std::wstring *)
0x180025c08  mov     edi, eax
0x180025c0a  test    eax, eax
0x180025c0c  jns     short loc_180025C35
0x180025c0e  mov     r8d, eax
0x180025c11  lea     rdx, aFailedToGetaad; "Failed to GetAadTenantId. hr=%#x"
0x180025c18  lea     rcx, aMcpserviceGeta; "McpService::GetAadTenantId"
0x180025c1f  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025c24  lea     rcx, [rsp+78h+var_38]
0x180025c29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025c2e  mov     eax, edi
0x180025c30  jmp     loc_180025CDA
0x180025c35  mov     [rsp+78h+var_50], 0
0x180025c3e  mov     [rsp+78h+var_48], 0
0x180025c47  mov     [rsp+78h+var_40], 0
0x180025c50  lea     rcx, [rsp+78h+var_38]
0x180025c55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180025c5a  mov     rdx, rax
0x180025c5d  lea     rcx, [rsp+78h+var_50]
0x180025c62  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180025c67  mov     edi, eax
0x180025c69  test    eax, eax
0x180025c6b  jns     short loc_180025C9B
0x180025c6d  mov     r8d, eax
0x180025c70  lea     rdx, aFailedToInitAa; "Failed to init aadTenantIdStr string. h"...
0x180025c77  lea     rcx, aMcpserviceGeta; "McpService::GetAadTenantId"
0x180025c7e  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025c83  lea     rcx, [rsp+78h+var_50]
0x180025c88  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025c8d  lea     rcx, [rsp+78h+var_38]
0x180025c92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025c97  mov     eax, edi
0x180025c99  jmp     short loc_180025CDA
0x180025c9b  mov     rax, [rsp+78h+var_50]
0x180025ca0  mov     [rsp+78h+var_50], 0
0x180025ca9  mov     [rsp+78h+var_40], 0
0x180025cb2  mov     [rsp+78h+var_48], 0
0x180025cbb  mov     [rbx], rax
0x180025cbe  lea     rcx, [rsp+78h+var_50]
0x180025cc3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025cc8  lea     rcx, [rsp+78h+var_38]
0x180025ccd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025cd2  xor     eax, eax
0x180025cd4  jmp     short loc_180025CDA
0x180025cd6  mov     eax, [rsp+78h+var_58]
0x180025cda  mov     rcx, [rsp+78h+var_18]
0x180025cdf  xor     rcx, rsp; StackCookie
0x180025ce2  call    __security_check_cookie
0x180025ce7  mov     rbx, [rsp+78h+arg_10]
0x180025cef  add     rsp, 70h
0x180025cf3  pop     rdi
0x180025cf4  retn
```
