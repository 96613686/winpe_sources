# McpService::GetOAuthClientId(ushort * *)

- ea: `0x1800261d0`
- end: `0x180026326`
- name: `?GetOAuthClientId@McpService@@UEAAJPEAPEAG@Z`
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
- `0x1800160d0`
- `0x180022000`
- `0x1800248bc`
- `0x1800248f8`
- `0x1800261d0`

## string_xrefs

- `0x180026201`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180026248`: `McpService::GetOAuthClientId`
- `0x1800262a7`: `McpService::GetOAuthClientId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall McpService::GetOAuthClientId(McpService *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // r8
  int OAuthClientId; // eax
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
    OAuthClientId = CloudPrint::CloudPrintHelper::GetOAuthClientId(*(_QWORD *)(v5 + 24), v16);
    v7 = OAuthClientId;
    if ( OAuthClientId >= 0 )
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
          "McpService::GetOAuthClientId",
          L"Failed to init oauthClientIdStr string. hr=%#x",
          (unsigned int)v9);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v13);
        std::wstring::_Tidy_deallocate((__int64)v16);
        result = v10;
      }
    }
    else
    {
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpService::GetOAuthClientId",
        L"Failed to GetOAuthClientId. hr=%#x",
        (unsigned int)OAuthClientId);
      std::wstring::_Tidy_deallocate((__int64)v16);
      result = v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
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
                               (void *)0x90,
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
0x1800261d0  mov     [rsp+arg_10], rbx
0x1800261d5  push    rdi
0x1800261d6  sub     rsp, 70h
0x1800261da  mov     rax, cs:__security_cookie
0x1800261e1  xor     rax, rsp
0x1800261e4  mov     [rsp+78h+var_18], rax
0x1800261e9  mov     rbx, rdx
0x1800261ec  mov     r8, rcx
0x1800261ef  test    rdx, rdx
0x1800261f2  jnz     short loc_180026219
0x1800261f4  mov     rcx, [rsp+78h]; this
0x1800261f9  mov     ebx, 80004003h
0x1800261fe  mov     r9d, ebx; char *
0x180026201  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180026208  mov     edx, 79h ; 'y'; void *
0x18002620d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026212  mov     eax, ebx
0x180026214  jmp     loc_18002630A
0x180026219  mov     qword ptr [rdx], 0
0x180026220  lea     rcx, [rsp+78h+var_38]
0x180026225  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002622a  lea     rdx, [rsp+78h+var_38]
0x18002622f  mov     rcx, [r8+18h]
0x180026233  call    ?GetOAuthClientId@CloudPrintHelper@CloudPrint@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::GetOAuthClientId(std::wstring *)
0x180026238  mov     edi, eax
0x18002623a  test    eax, eax
0x18002623c  jns     short loc_180026265
0x18002623e  mov     r8d, eax
0x180026241  lea     rdx, aFailedToGetoau_0; "Failed to GetOAuthClientId. hr=%#x"
0x180026248  lea     rcx, aMcpserviceGeto_0; "McpService::GetOAuthClientId"
0x18002624f  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026254  lea     rcx, [rsp+78h+var_38]
0x180026259  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002625e  mov     eax, edi
0x180026260  jmp     loc_18002630A
0x180026265  mov     [rsp+78h+var_50], 0
0x18002626e  mov     [rsp+78h+var_48], 0
0x180026277  mov     [rsp+78h+var_40], 0
0x180026280  lea     rcx, [rsp+78h+var_38]
0x180026285  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002628a  mov     rdx, rax
0x18002628d  lea     rcx, [rsp+78h+var_50]
0x180026292  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180026297  mov     edi, eax
0x180026299  test    eax, eax
0x18002629b  jns     short loc_1800262CB
0x18002629d  mov     r8d, eax
0x1800262a0  lea     rdx, aFailedToInitOa_0; "Failed to init oauthClientIdStr string."...
0x1800262a7  lea     rcx, aMcpserviceGeto_0; "McpService::GetOAuthClientId"
0x1800262ae  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800262b3  lea     rcx, [rsp+78h+var_50]
0x1800262b8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800262bd  lea     rcx, [rsp+78h+var_38]
0x1800262c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800262c7  mov     eax, edi
0x1800262c9  jmp     short loc_18002630A
0x1800262cb  mov     rax, [rsp+78h+var_50]
0x1800262d0  mov     [rsp+78h+var_50], 0
0x1800262d9  mov     [rsp+78h+var_40], 0
0x1800262e2  mov     [rsp+78h+var_48], 0
0x1800262eb  mov     [rbx], rax
0x1800262ee  lea     rcx, [rsp+78h+var_50]
0x1800262f3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800262f8  lea     rcx, [rsp+78h+var_38]
0x1800262fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026302  xor     eax, eax
0x180026304  jmp     short loc_18002630A
0x180026306  mov     eax, [rsp+78h+var_58]
0x18002630a  mov     rcx, [rsp+78h+var_18]
0x18002630f  xor     rcx, rsp; StackCookie
0x180026312  call    __security_check_cookie
0x180026317  mov     rbx, [rsp+78h+arg_10]
0x18002631f  add     rsp, 70h
0x180026323  pop     rdi
0x180026324  retn
```
