# EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002c98c`
- end: `0x18002cb00`
- name: `?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020e2c`
- `0x18002cbe0`

## callees

- `0x18000d3dc`
- `0x18001e358`
- `0x18002c98c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002caab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002caab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ca9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cac5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002c9c2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002ca3c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002c9c2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002ca3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
        __int64 a1,
        __int64 a2,
        HLOCAL *a3)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rdi
  int v8; // eax
  HLOCAL v9; // rbp
  DWORD LastError; // ebx
  HLOCAL hMem[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v13; // [rsp+78h] [rbp+10h] BYREF
  int v14; // [rsp+7Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  v13 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"EnterpriseModernAppManagementAppIDs",
                                 L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
                                 0,
                                 0);
  v5 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      hMem,
      0,
      (unsigned int)v13);
    v6 = hMem[0];
    if ( !hMem[0] )
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x781,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)0x8007000ELL,
        (int)&v13);
      return v5;
    }
    v8 = GetPersistedRegistryLocationW(
           L"EnterpriseModernAppManagementAppIDs",
           L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
           hMem[0],
           (unsigned int)v13);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x783,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)v8,
        (int)&v13);
      LocalFree(v6);
      return v5;
    }
    if ( a3 != hMem )
    {
      v9 = *a3;
      if ( *a3 )
      {
        LastError = GetLastError();
        LocalFree(v9);
        SetLastError(LastError);
      }
      *a3 = v6;
      v6 = 0;
    }
    if ( v6 )
      LocalFree(v6);
  }
  else if ( PersistedRegistryLocationW < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v13);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c98c  mov     qword ptr [rsp+arg_8], rdx
0x18002c991  push    rbx
0x18002c992  push    rbp
0x18002c993  push    rsi
0x18002c994  push    rdi
0x18002c995  sub     rsp, 48h
0x18002c999  mov     rsi, r8
0x18002c99c  mov     [rsp+68h+arg_8], 0
0x18002c9a4  lea     rax, [rsp+68h+arg_8]
0x18002c9a9  mov     qword ptr [rsp+68h+var_48], rax; int
0x18002c9ae  xor     r9d, r9d
0x18002c9b1  xor     r8d, r8d
0x18002c9b4  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002c9bb  lea     rcx, ?c_AppIDsRegistryPathStateSeparationName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseModernAppManagementAppIDs"
0x18002c9c2  call    cs:__imp_GetPersistedRegistryLocationW
0x18002c9c9  nop     dword ptr [rax+rax+00h]
0x18002c9ce  mov     ebx, eax
0x18002c9d0  cmp     eax, 0EAh
0x18002c9d5  jnz     loc_18002CADE
0x18002c9db  mov     r8d, [rsp+68h+arg_8]
0x18002c9e0  xor     edx, edx
0x18002c9e2  lea     rcx, [rsp+68h+hMem]
0x18002c9e7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002c9ec  mov     rdi, [rsp+68h+hMem]
0x18002c9f1  test    rdi, rdi
0x18002c9f4  jnz     short loc_18002CA1C
0x18002c9f6  mov     rcx, [rsp+68h]; this
0x18002c9fb  mov     ebx, 8007000Eh
0x18002ca00  mov     r9d, ebx; char *
0x18002ca03  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002ca0a  mov     edx, 781h; void *
0x18002ca0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca14  nop
0x18002ca15  mov     eax, ebx
0x18002ca17  jmp     loc_18002CAD4
0x18002ca1c  lea     rax, [rsp+68h+arg_8]
0x18002ca21  mov     qword ptr [rsp+68h+var_48], rax; int
0x18002ca26  mov     r9d, [rsp+68h+arg_8]
0x18002ca2b  mov     r8, rdi
0x18002ca2e  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002ca35  lea     rcx, ?c_AppIDsRegistryPathStateSeparationName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseModernAppManagementAppIDs"
0x18002ca3c  call    cs:__imp_GetPersistedRegistryLocationW
0x18002ca43  nop     dword ptr [rax+rax+00h]
0x18002ca48  mov     ebx, eax
0x18002ca4a  test    eax, eax
0x18002ca4c  jns     short loc_18002CA7A
0x18002ca4e  mov     rcx, [rsp+68h]; this
0x18002ca53  mov     r9d, eax; char *
0x18002ca56  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002ca5d  mov     edx, 783h; void *
0x18002ca62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca67  nop
0x18002ca68  mov     rcx, rdi; hMem
0x18002ca6b  call    cs:__imp_LocalFree
0x18002ca72  nop     dword ptr [rax+rax+00h]
0x18002ca77  nop
0x18002ca78  jmp     short loc_18002CA15
0x18002ca7a  lea     rax, [rsp+68h+hMem]
0x18002ca7f  cmp     rsi, rax
0x18002ca82  jz      short loc_18002CABD
0x18002ca84  mov     rbp, [rsi]
0x18002ca87  test    rbp, rbp
0x18002ca8a  jz      short loc_18002CAB8
0x18002ca8c  call    cs:__imp_GetLastError
0x18002ca93  nop     dword ptr [rax+rax+00h]
0x18002ca98  mov     ebx, eax
0x18002ca9a  mov     rcx, rbp; hMem
0x18002ca9d  call    cs:__imp_LocalFree
0x18002caa4  nop     dword ptr [rax+rax+00h]
0x18002caa9  mov     ecx, ebx; dwErrCode
0x18002caab  call    cs:__imp_SetLastError
0x18002cab2  nop     dword ptr [rax+rax+00h]
0x18002cab7  nop
0x18002cab8  mov     [rsi], rdi
0x18002cabb  xor     edi, edi
0x18002cabd  test    rdi, rdi
0x18002cac0  jz      short loc_18002CAD2
0x18002cac2  mov     rcx, rdi; hMem
0x18002cac5  call    cs:__imp_LocalFree
0x18002cacc  nop     dword ptr [rax+rax+00h]
0x18002cad1  nop
0x18002cad2  xor     eax, eax
0x18002cad4  add     rsp, 48h
0x18002cad8  pop     rdi
0x18002cad9  pop     rsi
0x18002cada  pop     rbp
0x18002cadb  pop     rbx
0x18002cadc  retn
0x18002cade  test    ebx, ebx
0x18002cae0  jns     short loc_18002CAD2
0x18002cae2  mov     rcx, [rsp+68h]; this
0x18002cae7  mov     r9d, ebx; char *
0x18002caea  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002caf1  mov     edx, 788h; void *
0x18002caf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cafb  jmp     loc_18002CA15
```
