# _anonymous_namespace_::GetSubKeyNames

- ea: `0x180135484`
- end: `0x180135613`
- name: `_anonymous_namespace_::GetSubKeyNames`
- size: `399`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180133ec4`
- `0x180135ac4`
- `0x180135ef4`
- `0x180136034`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800e7c08`
- `0x1800ef5d8`
- `0x180104108`
- `0x1801058cc`
- `0x180105c40`
- `0x180132f88`
- `0x180135484`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180135533`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180135533`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180135592`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180135592`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801354d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801354d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetSubKeyNames(HKEY *a1, const WCHAR *a2, __int64 a3)
{
  HKEY v4; // rsi
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  DWORD i; // ebx
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v13; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[40]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v13 = 0;
  v4 = *a1;
  if ( a2 )
  {
    v13 = 0;
    v5 = RegOpenKeyExW(v4, a2, 0, 0x20019u, &v13);
    if ( v5 )
    {
      v6 = 31;
LABEL_7:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
             (const char *)v5,
             phkResult);
      goto LABEL_17;
    }
    v4 = v13;
  }
  cSubKeys = 0;
  std::vector<std::wstring>::clear(a3);
  v5 = RegQueryInfoKeyW(v4, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v5 )
  {
    v6 = 56;
    goto LABEL_7;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 260;
    v5 = RegEnumKeyExW(v4, i, Name, &cchName, 0, 0, 0, 0);
    if ( v5 )
    {
      v6 = 60;
      goto LABEL_7;
    }
    std::wstring::wstring(v15, Name);
    v9 = *(_QWORD *)(a3 + 8);
    if ( v9 == *(_QWORD *)(a3 + 16) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a3, v9, v15);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(a3, v15);
    std::wstring::_Tidy_deallocate(v15);
  }
  v7 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
  return v7;
}

```

## disassembly

```asm
0x180135484  push    rbp
0x180135486  push    rbx
0x180135487  push    rsi
0x180135488  push    rdi
0x180135489  push    r14
0x18013548b  lea     rbp, [rsp-1C0h]
0x180135493  sub     rsp, 2C0h
0x18013549a  mov     rax, cs:__security_cookie
0x1801354a1  xor     rax, rsp
0x1801354a4  mov     [rbp+1E0h+var_30], rax
0x1801354ab  mov     rdi, r8
0x1801354ae  xor     r14d, r14d
0x1801354b1  mov     [rsp+2E0h+var_278], r14
0x1801354b6  mov     rsi, [rcx]
0x1801354b9  test    rdx, rdx
0x1801354bc  jz      short loc_1801354EE
0x1801354be  mov     [rsp+2E0h+var_278], r14
0x1801354c3  lea     rax, [rsp+2E0h+var_278]
0x1801354c8  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1801354cd  mov     r9d, 20019h; samDesired
0x1801354d3  xor     r8d, r8d; ulOptions
0x1801354d6  mov     rcx, rsi; hKey
0x1801354d9  call    cs:__imp_RegOpenKeyExW
0x1801354df  test    eax, eax
0x1801354e1  jz      short loc_1801354E9
0x1801354e3  lea     edx, [r14+1Fh]
0x1801354e7  jmp     short loc_180135542
0x1801354e9  mov     rsi, [rsp+2E0h+var_278]
0x1801354ee  mov     [rsp+2E0h+cSubKeys], r14d
0x1801354f3  mov     rcx, rdi
0x1801354f6  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x1801354fb  mov     [rsp+2E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180135500  mov     [rsp+2E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180135505  mov     [rsp+2E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18013550a  mov     [rsp+2E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18013550f  mov     [rsp+2E0h+lpcValues], r14; lpcValues
0x180135514  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180135519  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18013551e  lea     rax, [rsp+2E0h+cSubKeys]
0x180135523  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x180135528  xor     r9d, r9d; lpReserved
0x18013552b  xor     r8d, r8d; lpcchClass
0x18013552e  xor     edx, edx; lpClass
0x180135530  mov     rcx, rsi; hKey
0x180135533  call    cs:__imp_RegQueryInfoKeyW
0x180135539  test    eax, eax
0x18013553b  jz      short loc_18013555F
0x18013553d  mov     edx, 38h ; '8'; void *
0x180135542  mov     rcx, [rbp+1E8h]; this
0x180135549  mov     r9d, eax; char *
0x18013554c  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135553  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135558  mov     ebx, eax
0x18013555a  jmp     loc_1801355EA
0x18013555f  mov     ebx, r14d
0x180135562  cmp     ebx, [rsp+2E0h+cSubKeys]
0x180135566  jnb     short loc_1801355E7
0x180135568  mov     [rsp+2E0h+cchName], 104h
0x180135570  mov     [rsp+2E0h+lpcValues], r14; lpftLastWriteTime
0x180135575  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpcchClass
0x18013557a  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r14; lpClass
0x18013557f  mov     [rsp+2E0h+phkResult], r14; lpReserved
0x180135584  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180135589  lea     r8, [rbp+1E0h+Name]; lpName
0x18013558d  mov     edx, ebx; dwIndex
0x18013558f  mov     rcx, rsi; hKey
0x180135592  call    cs:__imp_RegEnumKeyExW
0x180135598  test    eax, eax
0x18013559a  jnz     short loc_1801355DD
0x18013559c  lea     rdx, [rbp+1E0h+Name]
0x1801355a0  lea     rcx, [rsp+2E0h+var_268]
0x1801355a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801355aa  nop
0x1801355ab  mov     rdx, [rdi+8]
0x1801355af  mov     rcx, rdi
0x1801355b2  cmp     rdx, [rdi+10h]
0x1801355b6  jz      short loc_1801355C4
0x1801355b8  lea     rdx, [rsp+2E0h+var_268]
0x1801355bd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801355c2  jmp     short loc_1801355CF
0x1801355c4  lea     r8, [rsp+2E0h+var_268]
0x1801355c9  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801355ce  nop
0x1801355cf  lea     rcx, [rsp+2E0h+var_268]
0x1801355d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801355d9  inc     ebx
0x1801355db  jmp     short loc_180135562
0x1801355dd  mov     edx, 3Ch ; '<'
0x1801355e2  jmp     loc_180135542
0x1801355e7  mov     ebx, r14d
0x1801355ea  lea     rcx, [rsp+2E0h+var_278]
0x1801355ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801355f4  mov     eax, ebx
0x1801355f6  mov     rcx, [rbp+1E0h+var_30]
0x1801355fd  xor     rcx, rsp; StackCookie
0x180135600  call    __security_check_cookie
0x180135605  add     rsp, 2C0h
0x18013560c  pop     r14
0x18013560e  pop     rdi
0x18013560f  pop     rsi
0x180135610  pop     rbx
0x180135611  pop     rbp
0x180135612  retn
```
