# McpService::GetOAuthAuthority(ushort * *)

- ea: `0x180026070`
- end: `0x1800261c6`
- name: `?GetOAuthAuthority@McpService@@UEAAJPEAPEAG@Z`
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
- `0x18001601c`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x180026070`

## string_xrefs

- `0x1800260a1`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x1800260e8`: `McpService::GetOAuthAuthority`
- `0x180026147`: `McpService::GetOAuthAuthority`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetOAuthAuthority(McpService *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // r8
  int OAuthAuthority; // eax
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
    OAuthAuthority = CloudPrint::CloudPrintHelper::GetOAuthAuthority(*(_QWORD *)(v5 + 24), v16);
    v7 = OAuthAuthority;
    if ( OAuthAuthority >= 0 )
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
          "McpService::GetOAuthAuthority",
          L"Failed to init oauthAuthorityStr string. hr=%#x",
          (unsigned int)v9);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = v10;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetOAuthAuthority",
        L"Failed to GetOAuthAuthority. hr=%#x",
        (unsigned int)OAuthAuthority);
      std::wstring::_Tidy_deallocate((__int64)v16);
      result = v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
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
                               (void *)0x75,
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
0x180026070  mov     [rsp+arg_10], rbx
0x180026075  push    rdi
0x180026076  sub     rsp, 70h
0x18002607a  mov     rax, cs:__security_cookie
0x180026081  xor     rax, rsp
0x180026084  mov     [rsp+78h+var_18], rax
0x180026089  mov     rbx, rdx
0x18002608c  mov     r8, rcx
0x18002608f  test    rdx, rdx
0x180026092  jnz     short loc_1800260B9
0x180026094  mov     rcx, [rsp+78h]; this
0x180026099  mov     ebx, 80004003h
0x18002609e  mov     r9d, ebx; char *
0x1800260a1  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800260a8  mov     edx, 5Eh ; '^'; void *
0x1800260ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800260b2  mov     eax, ebx
0x1800260b4  jmp     loc_1800261AA
0x1800260b9  mov     qword ptr [rdx], 0
0x1800260c0  lea     rcx, [rsp+78h+var_38]
0x1800260c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800260ca  lea     rdx, [rsp+78h+var_38]
0x1800260cf  mov     rcx, [r8+18h]
0x1800260d3  call    ?GetOAuthAuthority@CloudPrintHelper@CloudPrint@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetOAuthAuthority(std::wstring *)
0x1800260d8  mov     edi, eax
0x1800260da  test    eax, eax
0x1800260dc  jns     short loc_180026105
0x1800260de  mov     r8d, eax
0x1800260e1  lea     rdx, aFailedToGetoau; "Failed to GetOAuthAuthority. hr=%#x"
0x1800260e8  lea     rcx, aMcpserviceGeto_1; "McpService::GetOAuthAuthority"
0x1800260ef  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800260f4  lea     rcx, [rsp+78h+var_38]
0x1800260f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800260fe  mov     eax, edi
0x180026100  jmp     loc_1800261AA
0x180026105  mov     [rsp+78h+var_50], 0
0x18002610e  mov     [rsp+78h+var_48], 0
0x180026117  mov     [rsp+78h+var_40], 0
0x180026120  lea     rcx, [rsp+78h+var_38]
0x180026125  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002612a  mov     rdx, rax
0x18002612d  lea     rcx, [rsp+78h+var_50]
0x180026132  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180026137  mov     edi, eax
0x180026139  test    eax, eax
0x18002613b  jns     short loc_18002616B
0x18002613d  mov     r8d, eax
0x180026140  lea     rdx, aFailedToInitOa; "Failed to init oauthAuthorityStr string"...
0x180026147  lea     rcx, aMcpserviceGeto_1; "McpService::GetOAuthAuthority"
0x18002614e  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026153  lea     rcx, [rsp+78h+var_50]
0x180026158  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002615d  lea     rcx, [rsp+78h+var_38]
0x180026162  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026167  mov     eax, edi
0x180026169  jmp     short loc_1800261AA
0x18002616b  mov     rax, [rsp+78h+var_50]
0x180026170  mov     [rsp+78h+var_50], 0
0x180026179  mov     [rsp+78h+var_40], 0
0x180026182  mov     [rsp+78h+var_48], 0
0x18002618b  mov     [rbx], rax
0x18002618e  lea     rcx, [rsp+78h+var_50]
0x180026193  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180026198  lea     rcx, [rsp+78h+var_38]
0x18002619d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261a2  xor     eax, eax
0x1800261a4  jmp     short loc_1800261AA
0x1800261a6  mov     eax, [rsp+78h+var_58]
0x1800261aa  mov     rcx, [rsp+78h+var_18]
0x1800261af  xor     rcx, rsp; StackCookie
0x1800261b2  call    __security_check_cookie
0x1800261b7  mov     rbx, [rsp+78h+arg_10]
0x1800261bf  add     rsp, 70h
0x1800261c3  pop     rdi
0x1800261c4  retn
```
