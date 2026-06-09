# McpService::GetCloudPrintDiscoveryEndpoint(ushort * *)

- ea: `0x180025d00`
- end: `0x180025e56`
- name: `?GetCloudPrintDiscoveryEndpoint@McpService@@UEAAJPEAPEAG@Z`
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
- `0x180014504`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x180025d00`

## string_xrefs

- `0x180025d78`: `McpService::GetCloudPrintDiscoveryEndpoint`
- `0x180025dd7`: `McpService::GetCloudPrintDiscoveryEndpoint`
- `0x180025d31`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetCloudPrintDiscoveryEndpoint(McpService *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // r8
  int CloudPrintDiscoveryEndpoint; // eax
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
    CloudPrintDiscoveryEndpoint = CloudPrint::CloudPrintHelper::GetCloudPrintDiscoveryEndpoint(
                                    *(_QWORD *)(v5 + 24),
                                    v16);
    v7 = CloudPrintDiscoveryEndpoint;
    if ( CloudPrintDiscoveryEndpoint >= 0 )
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
          "McpService::GetCloudPrintDiscoveryEndpoint",
          L"Failed to init discoveryEndpointStr string. hr=%#x",
          (unsigned int)v9);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = v10;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetCloudPrintDiscoveryEndpoint",
        L"Failed to GetCloudPrintDiscoveryEndpoint. hr=%#x",
        (unsigned int)CloudPrintDiscoveryEndpoint);
      std::wstring::_Tidy_deallocate((__int64)v16);
      result = v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
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
                               (void *)0x5A,
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
0x180025d00  mov     [rsp+arg_10], rbx
0x180025d05  push    rdi
0x180025d06  sub     rsp, 70h
0x180025d0a  mov     rax, cs:__security_cookie
0x180025d11  xor     rax, rsp
0x180025d14  mov     [rsp+78h+var_18], rax
0x180025d19  mov     rbx, rdx
0x180025d1c  mov     r8, rcx
0x180025d1f  test    rdx, rdx
0x180025d22  jnz     short loc_180025D49
0x180025d24  mov     rcx, [rsp+78h]; this
0x180025d29  mov     ebx, 80004003h
0x180025d2e  mov     r9d, ebx; char *
0x180025d31  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025d38  mov     edx, 43h ; 'C'; void *
0x180025d3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d42  mov     eax, ebx
0x180025d44  jmp     loc_180025E3A
0x180025d49  mov     qword ptr [rdx], 0
0x180025d50  lea     rcx, [rsp+78h+var_38]
0x180025d55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180025d5a  lea     rdx, [rsp+78h+var_38]
0x180025d5f  mov     rcx, [r8+18h]
0x180025d63  call    ?GetCloudPrintDiscoveryEndpoint@CloudPrintHelper@CloudPrint@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetCloudPrintDiscoveryEndpoint(std::wstring *)
0x180025d68  mov     edi, eax
0x180025d6a  test    eax, eax
0x180025d6c  jns     short loc_180025D95
0x180025d6e  mov     r8d, eax
0x180025d71  lea     rdx, aFailedToGetclo; "Failed to GetCloudPrintDiscoveryEndpoin"...
0x180025d78  lea     rcx, aMcpserviceGetc; "McpService::GetCloudPrintDiscoveryEndpo"...
0x180025d7f  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025d84  lea     rcx, [rsp+78h+var_38]
0x180025d89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025d8e  mov     eax, edi
0x180025d90  jmp     loc_180025E3A
0x180025d95  mov     [rsp+78h+var_50], 0
0x180025d9e  mov     [rsp+78h+var_48], 0
0x180025da7  mov     [rsp+78h+var_40], 0
0x180025db0  lea     rcx, [rsp+78h+var_38]
0x180025db5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180025dba  mov     rdx, rax
0x180025dbd  lea     rcx, [rsp+78h+var_50]
0x180025dc2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180025dc7  mov     edi, eax
0x180025dc9  test    eax, eax
0x180025dcb  jns     short loc_180025DFB
0x180025dcd  mov     r8d, eax
0x180025dd0  lea     rdx, aFailedToInitDi; "Failed to init discoveryEndpointStr str"...
0x180025dd7  lea     rcx, aMcpserviceGetc; "McpService::GetCloudPrintDiscoveryEndpo"...
0x180025dde  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025de3  lea     rcx, [rsp+78h+var_50]
0x180025de8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025ded  lea     rcx, [rsp+78h+var_38]
0x180025df2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025df7  mov     eax, edi
0x180025df9  jmp     short loc_180025E3A
0x180025dfb  mov     rax, [rsp+78h+var_50]
0x180025e00  mov     [rsp+78h+var_50], 0
0x180025e09  mov     [rsp+78h+var_40], 0
0x180025e12  mov     [rsp+78h+var_48], 0
0x180025e1b  mov     [rbx], rax
0x180025e1e  lea     rcx, [rsp+78h+var_50]
0x180025e23  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025e28  lea     rcx, [rsp+78h+var_38]
0x180025e2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025e32  xor     eax, eax
0x180025e34  jmp     short loc_180025E3A
0x180025e36  mov     eax, [rsp+78h+var_58]
0x180025e3a  mov     rcx, [rsp+78h+var_18]
0x180025e3f  xor     rcx, rsp; StackCookie
0x180025e42  call    __security_check_cookie
0x180025e47  mov     rbx, [rsp+78h+arg_10]
0x180025e4f  add     rsp, 70h
0x180025e53  pop     rdi
0x180025e54  retn
```
