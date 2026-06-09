# McpService::GetEndpointResourceId(_McpEndpoint,ushort * *)

- ea: `0x180025e60`
- end: `0x180025fb6`
- name: `?GetEndpointResourceId@McpService@@UEAAJW4_McpEndpoint@@PEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180003a60`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x180014c54`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x180025e60`

## string_xrefs

- `0x180025e91`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180025ed8`: `McpService::GetEndpointResourceId`
- `0x180025f37`: `McpService::GetEndpointResourceId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetEndpointResourceId(__int64 a1, __int64 a2, _QWORD *a3)
{
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // r9
  __int64 v7; // rdx
  int EndpointResourceId; // eax
  unsigned int v9; // edi
  _WORD *v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+28h] [rbp-50h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+38h] [rbp-40h]
  _BYTE v18[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    std::wstring::wstring((__int64)v18);
    EndpointResourceId = CloudPrint::CloudPrintHelper::GetEndpointResourceId(*(_QWORD *)(v6 + 24), v7, v18);
    v9 = EndpointResourceId;
    if ( EndpointResourceId >= 0 )
    {
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v10 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&v15, v10);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v13 = v15;
        v15 = 0;
        v17 = 0;
        v16 = 0;
        *a3 = v13;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
        std::wstring::_Tidy_deallocate((__int64)v18);
        result = 0;
      }
      else
      {
        McpManagementTelemetry::WriteDbgTraceWarning(
          "McpService::GetEndpointResourceId",
          L"Failed to init endpointResourceIdStr string. hr=%#x",
          (unsigned int)v11);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
        std::wstring::_Tidy_deallocate((__int64)v18);
        result = v12;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetEndpointResourceId",
        L"Failed to GetEndpointResourceId. hr=%#x",
        (unsigned int)EndpointResourceId);
      std::wstring::_Tidy_deallocate((__int64)v18);
      result = v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      v14);
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
                               (void *)0xC6,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                               v4);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180025e60  mov     [rsp+arg_18], rbx
0x180025e65  push    rdi
0x180025e66  sub     rsp, 70h
0x180025e6a  mov     rax, cs:__security_cookie
0x180025e71  xor     rax, rsp
0x180025e74  mov     [rsp+78h+var_18], rax
0x180025e79  mov     rbx, r8
0x180025e7c  mov     r9, rcx
0x180025e7f  test    rbx, rbx
0x180025e82  jnz     short loc_180025EA9
0x180025e84  mov     rcx, [rsp+78h]; this
0x180025e89  mov     ebx, 80004003h
0x180025e8e  mov     r9d, ebx; char *
0x180025e91  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025e98  mov     edx, 0AFh; void *
0x180025e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ea2  mov     eax, ebx
0x180025ea4  jmp     loc_180025F9A
0x180025ea9  mov     qword ptr [r8], 0
0x180025eb0  lea     rcx, [rsp+78h+var_38]
0x180025eb5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180025eba  lea     r8, [rsp+78h+var_38]
0x180025ebf  mov     rcx, [r9+18h]
0x180025ec3  call    ?GetEndpointResourceId@CloudPrintHelper@CloudPrint@@QEBAJW4CloudPrintEndpoint@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetEndpointResourceId(CloudPrint::CloudPrintEndpoint,std::wstring *)
0x180025ec8  mov     edi, eax
0x180025eca  test    eax, eax
0x180025ecc  jns     short loc_180025EF5
0x180025ece  mov     r8d, eax
0x180025ed1  lea     rdx, aFailedToGetend; "Failed to GetEndpointResourceId. hr=%#x"
0x180025ed8  lea     rcx, aMcpserviceGete; "McpService::GetEndpointResourceId"
0x180025edf  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025ee4  lea     rcx, [rsp+78h+var_38]
0x180025ee9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025eee  mov     eax, edi
0x180025ef0  jmp     loc_180025F9A
0x180025ef5  mov     [rsp+78h+var_50], 0
0x180025efe  mov     [rsp+78h+var_48], 0
0x180025f07  mov     [rsp+78h+var_40], 0
0x180025f10  lea     rcx, [rsp+78h+var_38]
0x180025f15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180025f1a  mov     rdx, rax
0x180025f1d  lea     rcx, [rsp+78h+var_50]
0x180025f22  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180025f27  mov     edi, eax
0x180025f29  test    eax, eax
0x180025f2b  jns     short loc_180025F5B
0x180025f2d  mov     r8d, eax
0x180025f30  lea     rdx, aFailedToInitEn; "Failed to init endpointResourceIdStr st"...
0x180025f37  lea     rcx, aMcpserviceGete; "McpService::GetEndpointResourceId"
0x180025f3e  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180025f43  lea     rcx, [rsp+78h+var_50]
0x180025f48  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025f4d  lea     rcx, [rsp+78h+var_38]
0x180025f52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025f57  mov     eax, edi
0x180025f59  jmp     short loc_180025F9A
0x180025f5b  mov     rax, [rsp+78h+var_50]
0x180025f60  mov     [rsp+78h+var_50], 0
0x180025f69  mov     [rsp+78h+var_40], 0
0x180025f72  mov     [rsp+78h+var_48], 0
0x180025f7b  mov     [rbx], rax
0x180025f7e  lea     rcx, [rsp+78h+var_50]
0x180025f83  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025f88  lea     rcx, [rsp+78h+var_38]
0x180025f8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025f92  xor     eax, eax
0x180025f94  jmp     short loc_180025F9A
0x180025f96  mov     eax, [rsp+78h+var_58]
0x180025f9a  mov     rcx, [rsp+78h+var_18]
0x180025f9f  xor     rcx, rsp; StackCookie
0x180025fa2  call    __security_check_cookie
0x180025fa7  mov     rbx, [rsp+78h+arg_18]
0x180025faf  add     rsp, 70h
0x180025fb3  pop     rdi
0x180025fb4  retn
```
