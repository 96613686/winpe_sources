# EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002a6ec`
- end: `0x18002a835`
- name: `?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f834`
- `0x18002a908`

## callees

- `0x18000cfe8`
- `0x18001d1fc`
- `0x18002a6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a7ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a7ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a801`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a722`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a796`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a722`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002a796`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
        __int64 a1,
        __int64 a2,
        HLOCAL *a3)
{
  int PersistedRegistryLocationW; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  HLOCAL v7; // rdi
  int v9; // eax
  HLOCAL v10; // rbp
  DWORD LastError; // ebx
  HLOCAL hMem[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v14; // [rsp+78h] [rbp+10h] BYREF
  int v15; // [rsp+7Ch] [rbp+14h]

  v15 = HIDWORD(a2);
  v14 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"EnterpriseModernAppManagementAppIDs",
                                 L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
                                 0,
                                 0);
  v6 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      hMem,
      0,
      (unsigned int)v14,
      v5);
    v7 = hMem[0];
    if ( !hMem[0] )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x781,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)0x8007000ELL,
        (int)&v14);
      return v6;
    }
    v9 = GetPersistedRegistryLocationW(
           L"EnterpriseModernAppManagementAppIDs",
           L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
           hMem[0],
           (unsigned int)v14);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x783,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)v9,
        (int)&v14);
      LocalFree(v7);
      return v6;
    }
    if ( a3 != hMem )
    {
      v10 = *a3;
      if ( *a3 )
      {
        LastError = GetLastError();
        LocalFree(v10);
        SetLastError(LastError);
      }
      *a3 = v7;
      v7 = 0;
    }
    if ( v7 )
      LocalFree(v7);
  }
  else if ( PersistedRegistryLocationW < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v14);
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a6ec  mov     qword ptr [rsp+arg_8], rdx
0x18002a6f1  push    rbx
0x18002a6f2  push    rbp
0x18002a6f3  push    rsi
0x18002a6f4  push    rdi
0x18002a6f5  sub     rsp, 48h
0x18002a6f9  mov     rsi, r8
0x18002a6fc  mov     [rsp+68h+arg_8], 0
0x18002a704  lea     rax, [rsp+68h+arg_8]
0x18002a709  mov     qword ptr [rsp+68h+var_48], rax; int
0x18002a70e  xor     r9d, r9d
0x18002a711  xor     r8d, r8d
0x18002a714  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002a71b  lea     rcx, ?c_AppIDsRegistryPathStateSeparationName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseModernAppManagementAppIDs"
0x18002a722  call    cs:__imp_GetPersistedRegistryLocationW
0x18002a728  mov     ebx, eax
0x18002a72a  cmp     eax, 0EAh
0x18002a72f  jnz     loc_18002A813
0x18002a735  mov     r8d, [rsp+68h+arg_8]
0x18002a73a  xor     edx, edx
0x18002a73c  lea     rcx, [rsp+68h+hMem]
0x18002a741  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a746  mov     rdi, [rsp+68h+hMem]
0x18002a74b  test    rdi, rdi
0x18002a74e  jnz     short loc_18002A776
0x18002a750  mov     rcx, [rsp+68h]; this
0x18002a755  mov     ebx, 8007000Eh
0x18002a75a  mov     r9d, ebx; char *
0x18002a75d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a764  mov     edx, 781h; void *
0x18002a769  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a76e  nop
0x18002a76f  mov     eax, ebx
0x18002a771  jmp     loc_18002A80A
0x18002a776  lea     rax, [rsp+68h+arg_8]
0x18002a77b  mov     qword ptr [rsp+68h+var_48], rax; int
0x18002a780  mov     r9d, [rsp+68h+arg_8]
0x18002a785  mov     r8, rdi
0x18002a788  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002a78f  lea     rcx, ?c_AppIDsRegistryPathStateSeparationName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseModernAppManagementAppIDs"
0x18002a796  call    cs:__imp_GetPersistedRegistryLocationW
0x18002a79c  mov     ebx, eax
0x18002a79e  test    eax, eax
0x18002a7a0  jns     short loc_18002A7C8
0x18002a7a2  mov     rcx, [rsp+68h]; this
0x18002a7a7  mov     r9d, eax; char *
0x18002a7aa  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a7b1  mov     edx, 783h; void *
0x18002a7b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7bb  nop
0x18002a7bc  mov     rcx, rdi; hMem
0x18002a7bf  call    cs:__imp_LocalFree
0x18002a7c5  nop
0x18002a7c6  jmp     short loc_18002A76F
0x18002a7c8  lea     rax, [rsp+68h+hMem]
0x18002a7cd  cmp     rsi, rax
0x18002a7d0  jz      short loc_18002A7F9
0x18002a7d2  mov     rbp, [rsi]
0x18002a7d5  test    rbp, rbp
0x18002a7d8  jz      short loc_18002A7F4
0x18002a7da  call    cs:__imp_GetLastError
0x18002a7e0  mov     ebx, eax
0x18002a7e2  mov     rcx, rbp; hMem
0x18002a7e5  call    cs:__imp_LocalFree
0x18002a7eb  mov     ecx, ebx; dwErrCode
0x18002a7ed  call    cs:__imp_SetLastError
0x18002a7f3  nop
0x18002a7f4  mov     [rsi], rdi
0x18002a7f7  xor     edi, edi
0x18002a7f9  test    rdi, rdi
0x18002a7fc  jz      short loc_18002A808
0x18002a7fe  mov     rcx, rdi; hMem
0x18002a801  call    cs:__imp_LocalFree
0x18002a807  nop
0x18002a808  xor     eax, eax
0x18002a80a  add     rsp, 48h
0x18002a80e  pop     rdi
0x18002a80f  pop     rsi
0x18002a810  pop     rbp
0x18002a811  pop     rbx
0x18002a812  retn
0x18002a813  test    ebx, ebx
0x18002a815  jns     short loc_18002A808
0x18002a817  mov     rcx, [rsp+68h]; this
0x18002a81c  mov     r9d, ebx; char *
0x18002a81f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a826  mov     edx, 788h; void *
0x18002a82b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a830  jmp     loc_18002A76F
```
