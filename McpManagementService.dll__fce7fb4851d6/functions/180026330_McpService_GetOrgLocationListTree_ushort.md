# McpService::GetOrgLocationListTree(ushort * *)

- ea: `0x180026330`
- end: `0x180026486`
- name: `?GetOrgLocationListTree@McpService@@UEAAJPEAPEAG@Z`
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
- `0x180016184`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x180026330`

## string_xrefs

- `0x180026361`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x1800263a8`: `McpService::GetOrgLocationListTree`
- `0x180026407`: `McpService::GetOrgLocationListTree`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetOrgLocationListTree(McpService *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // r8
  int OrgLocationListTree; // eax
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
    OrgLocationListTree = CloudPrint::CloudPrintHelper::GetOrgLocationListTree(
                            *(CloudPrint::CloudPrintHelper **)(v5 + 24),
                            (__int64)v16);
    v7 = OrgLocationListTree;
    if ( OrgLocationListTree >= 0 )
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
          "McpService::GetOrgLocationListTree",
          L"Failed to init orgLocationListTreeStr string. hr=%#x",
          (unsigned int)v9);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = v10;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetOrgLocationListTree",
        L"Failed to GetOrgLocationListTree. hr=%#x",
        (unsigned int)OrgLocationListTree);
      std::wstring::_Tidy_deallocate((__int64)v16);
      result = v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
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
                               (void *)0xFB,
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
0x180026330  mov     [rsp+arg_10], rbx
0x180026335  push    rdi
0x180026336  sub     rsp, 70h
0x18002633a  mov     rax, cs:__security_cookie
0x180026341  xor     rax, rsp
0x180026344  mov     [rsp+78h+var_18], rax
0x180026349  mov     rbx, rdx
0x18002634c  mov     r8, rcx
0x18002634f  test    rdx, rdx
0x180026352  jnz     short loc_180026379
0x180026354  mov     rcx, [rsp+78h]; this
0x180026359  mov     ebx, 80004003h
0x18002635e  mov     r9d, ebx; char *
0x180026361  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180026368  mov     edx, 0E4h; void *
0x18002636d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026372  mov     eax, ebx
0x180026374  jmp     loc_18002646A
0x180026379  mov     qword ptr [rdx], 0
0x180026380  lea     rcx, [rsp+78h+var_38]
0x180026385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002638a  lea     rdx, [rsp+78h+var_38]
0x18002638f  mov     rcx, [r8+18h]; this
0x180026393  call    ?GetOrgLocationListTree@CloudPrintHelper@CloudPrint@@QEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetOrgLocationListTree(std::wstring *)
0x180026398  mov     edi, eax
0x18002639a  test    eax, eax
0x18002639c  jns     short loc_1800263C5
0x18002639e  mov     r8d, eax
0x1800263a1  lea     rdx, aFailedToGetorg; "Failed to GetOrgLocationListTree. hr=%#"...
0x1800263a8  lea     rcx, aMcpserviceGeto; "McpService::GetOrgLocationListTree"
0x1800263af  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800263b4  lea     rcx, [rsp+78h+var_38]
0x1800263b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800263be  mov     eax, edi
0x1800263c0  jmp     loc_18002646A
0x1800263c5  mov     [rsp+78h+var_50], 0
0x1800263ce  mov     [rsp+78h+var_48], 0
0x1800263d7  mov     [rsp+78h+var_40], 0
0x1800263e0  lea     rcx, [rsp+78h+var_38]
0x1800263e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800263ea  mov     rdx, rax
0x1800263ed  lea     rcx, [rsp+78h+var_50]
0x1800263f2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800263f7  mov     edi, eax
0x1800263f9  test    eax, eax
0x1800263fb  jns     short loc_18002642B
0x1800263fd  mov     r8d, eax
0x180026400  lea     rdx, aFailedToInitOr; "Failed to init orgLocationListTreeStr s"...
0x180026407  lea     rcx, aMcpserviceGeto; "McpService::GetOrgLocationListTree"
0x18002640e  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026413  lea     rcx, [rsp+78h+var_50]
0x180026418  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002641d  lea     rcx, [rsp+78h+var_38]
0x180026422  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026427  mov     eax, edi
0x180026429  jmp     short loc_18002646A
0x18002642b  mov     rax, [rsp+78h+var_50]
0x180026430  mov     [rsp+78h+var_50], 0
0x180026439  mov     [rsp+78h+var_40], 0
0x180026442  mov     [rsp+78h+var_48], 0
0x18002644b  mov     [rbx], rax
0x18002644e  lea     rcx, [rsp+78h+var_50]
0x180026453  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180026458  lea     rcx, [rsp+78h+var_38]
0x18002645d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026462  xor     eax, eax
0x180026464  jmp     short loc_18002646A
0x180026466  mov     eax, [rsp+78h+var_58]
0x18002646a  mov     rcx, [rsp+78h+var_18]
0x18002646f  xor     rcx, rsp; StackCookie
0x180026472  call    __security_check_cookie
0x180026477  mov     rbx, [rsp+78h+arg_10]
0x18002647f  add     rsp, 70h
0x180026483  pop     rdi
0x180026484  retn
```
