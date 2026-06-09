# RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>,std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>> &,bool &)

- ea: `0x18002b618`
- end: `0x18002b8b7`
- name: `?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z`
- size: `671`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002b18c`
- `0x18002b618`
- `0x18002f75c`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x180015fa0`
- `0x180016440`
- `0x180020358`
- `0x18002b618`
- `0x18002b8c0`
- `0x18002edcc`
- `0x180037780`
- `0x180080e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b690`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b690`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002b747`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002b747`

## string_xrefs

- `0x18002b6f3`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b829`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b867`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryStore::RecurseRegistryKeys(HKEY *a1, const WCHAR *a2, __int64 a3, int a4, _BYTE *a5)
{
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  int AllRegistryValues; // eax
  DWORD i; // ebx
  unsigned int v15; // eax
  HKEY **p_p_hKey; // r8
  _QWORD *v17; // rdx
  int v18; // eax
  unsigned int v19; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY *p_hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  unsigned __int64 v29; // [rsp+70h] [rbp-90h]
  _QWORD v30[5]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  *a5 = 0;
  hKey = 0;
  p_hKey = &hKey;
  v27 = 0;
  LOBYTE(v28) = 1;
  v9 = RegOpenKeyExW(*a1, a2, 0, 0x20019u, &v27);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v9 == 2 )
  {
    v10 = 0;
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v10;
  }
  *a5 = 1;
  if ( v9 )
  {
    v11 = (const char *)v9;
    v12 = 537;
LABEL_20:
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v12,
            (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
            v11,
            phkResult);
    goto LABEL_21;
  }
  AllRegistryValues = RegistryStore::GetAllRegistryValues(a1, hKey, a2, a3);
  v10 = AllRegistryValues;
  if ( AllRegistryValues < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
      (const char *)(unsigned int)AllRegistryValues,
      a4);
    goto LABEL_21;
  }
  for ( i = 0; ; ++i )
  {
    cchName = 259;
    v15 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v15 == 259 )
      break;
    if ( v15 )
    {
      v11 = (const char *)v15;
      v12 = 561;
      goto LABEL_20;
    }
    std::wstring::wstring(v30, a2);
    std::wstring::append(v30, L"\\");
    std::wstring::append(v30, Name);
    std::wstring::wstring(&p_hKey, a3);
    if ( v28 )
      std::wstring::append(&p_hKey, L"\\");
    std::wstring::append(&p_hKey, Name);
    LOBYTE(v23) = 0;
    p_p_hKey = &p_hKey;
    if ( v29 > 7 )
      LODWORD(p_p_hKey) = (_DWORD)p_hKey;
    v17 = v30;
    if ( v30[3] > 7u )
      LODWORD(v17) = v30[0];
    v18 = RegistryStore::RecurseRegistryKeys((_DWORD)a1, (_DWORD)v17, (_DWORD)p_p_hKey, a4, (__int64)&v23);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
        (const char *)(unsigned int)v18,
        phkResulta);
      std::wstring::_Tidy_deallocate(&p_hKey);
      std::wstring::_Tidy_deallocate(v30);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v19;
    }
    std::wstring::_Tidy_deallocate(&p_hKey);
    std::wstring::_Tidy_deallocate(v30);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18002b618  push    rbp
0x18002b61a  push    rbx
0x18002b61b  push    rsi
0x18002b61c  push    rdi
0x18002b61d  push    r12
0x18002b61f  push    r14
0x18002b621  push    r15
0x18002b623  lea     rbp, [rsp-1C0h]
0x18002b62b  sub     rsp, 2C0h
0x18002b632  mov     rax, cs:__security_cookie
0x18002b639  xor     rax, rsp
0x18002b63c  mov     [rbp+1F0h+var_40], rax
0x18002b643  mov     r12, r9
0x18002b646  mov     r14, r8
0x18002b649  mov     rsi, rdx
0x18002b64c  mov     r15, rcx
0x18002b64f  mov     rdi, [rbp+1F0h+arg_20]
0x18002b656  mov     byte ptr [rdi], 0
0x18002b659  mov     [rsp+2F0h+hKey], 0
0x18002b662  lea     rax, [rsp+2F0h+hKey]
0x18002b667  mov     [rsp+2F0h+var_298], rax
0x18002b66c  mov     [rsp+2F0h+var_290], 0
0x18002b675  mov     byte ptr [rsp+2F0h+var_288], 1
0x18002b67a  lea     rax, [rsp+2F0h+var_290]
0x18002b67f  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18002b684  mov     r9d, 20019h; samDesired
0x18002b68a  xor     r8d, r8d; ulOptions
0x18002b68d  mov     rcx, [rcx]; hKey
0x18002b690  call    cs:__imp_RegOpenKeyExW
0x18002b696  mov     ebx, eax
0x18002b698  lea     rcx, [rsp+2F0h+var_298]
0x18002b69d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002b6a2  cmp     ebx, 2
0x18002b6a5  jnz     short loc_18002B6AE
0x18002b6a7  xor     ebx, ebx
0x18002b6a9  jmp     loc_18002B87C
0x18002b6ae  mov     byte ptr [rdi], 1
0x18002b6b1  test    ebx, ebx
0x18002b6b3  jz      short loc_18002B6C2
0x18002b6b5  mov     r9d, ebx
0x18002b6b8  mov     edx, 219h
0x18002b6bd  jmp     loc_18002B867
0x18002b6c2  mov     [rsp+2F0h+lpClass], 0
0x18002b6cb  mov     [rsp+2F0h+phkResult], r12; int
0x18002b6d0  mov     r9, r14
0x18002b6d3  mov     r8, rsi
0x18002b6d6  mov     rdx, [rsp+2F0h+hKey]
0x18002b6db  mov     rcx, r15
0x18002b6de  call    ?GetAllRegistryValues@RegistryStore@@AEAAJPEAUHKEY__@@PEBG1AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@PEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; RegistryStore::GetAllRegistryValues(HKEY__ *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,std::set<std::wstring> *)
0x18002b6e3  mov     ebx, eax
0x18002b6e5  test    eax, eax
0x18002b6e7  jns     short loc_18002B709
0x18002b6e9  mov     rcx, [rbp+1F8h]; this
0x18002b6f0  mov     r9d, eax; char *
0x18002b6f3  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b6fa  mov     edx, 221h; void *
0x18002b6ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b704  jmp     loc_18002B87C
0x18002b709  xor     ebx, ebx
0x18002b70b  mov     [rsp+2F0h+cchName], 103h
0x18002b713  mov     [rsp+2F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002b71c  mov     [rsp+2F0h+lpcchClass], 0; lpcchClass
0x18002b725  mov     [rsp+2F0h+lpClass], 0; lpClass
0x18002b72e  mov     [rsp+2F0h+phkResult], 0; unsigned int
0x18002b737  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x18002b73c  lea     r8, [rbp+1F0h+Name]; lpName
0x18002b740  mov     edx, ebx; dwIndex
0x18002b742  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18002b747  call    cs:__imp_RegEnumKeyExW
0x18002b74d  cmp     eax, 103h
0x18002b752  jz      loc_18002B88A
0x18002b758  test    eax, eax
0x18002b75a  jnz     loc_18002B85F
0x18002b760  mov     rdx, rsi
0x18002b763  lea     rcx, [rsp+2F0h+var_278]
0x18002b768  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b76d  nop
0x18002b76e  lea     rdx, S; "\\"
0x18002b775  lea     rcx, [rsp+2F0h+var_278]
0x18002b77a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b77f  lea     rdx, [rbp+1F0h+Name]
0x18002b783  lea     rcx, [rsp+2F0h+var_278]
0x18002b788  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b78d  mov     rdx, r14
0x18002b790  lea     rcx, [rsp+2F0h+var_298]
0x18002b795  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b79a  nop
0x18002b79b  cmp     [rsp+2F0h+var_288], 0
0x18002b7a1  jz      short loc_18002B7B4
0x18002b7a3  lea     rdx, S; "\\"
0x18002b7aa  lea     rcx, [rsp+2F0h+var_298]
0x18002b7af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b7b4  lea     rdx, [rbp+1F0h+Name]
0x18002b7b8  lea     rcx, [rsp+2F0h+var_298]
0x18002b7bd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b7c2  mov     byte ptr [rsp+2F0h+var_2B0], 0
0x18002b7c7  lea     r8, [rsp+2F0h+var_298]
0x18002b7cc  cmp     [rsp+2F0h+var_280], 7
0x18002b7d2  cmova   r8, [rsp+2F0h+var_298]
0x18002b7d8  lea     rdx, [rsp+2F0h+var_278]
0x18002b7dd  cmp     [rbp+1F0h+var_260], 7
0x18002b7e2  cmova   rdx, [rsp+2F0h+var_278]
0x18002b7e8  lea     rax, [rsp+2F0h+var_2B0]
0x18002b7ed  mov     [rsp+2F0h+phkResult], rax; int
0x18002b7f2  mov     r9, r12
0x18002b7f5  mov     rcx, r15
0x18002b7f8  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b7fd  mov     edi, eax
0x18002b7ff  test    eax, eax
0x18002b801  js      short loc_18002B81F
0x18002b803  inc     ebx
0x18002b805  lea     rcx, [rsp+2F0h+var_298]
0x18002b80a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b80f  nop
0x18002b810  lea     rcx, [rsp+2F0h+var_278]
0x18002b815  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b81a  jmp     loc_18002B70B
0x18002b81f  mov     rcx, [rbp+1F8h]; this
0x18002b826  mov     r9d, edi; char *
0x18002b829  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b830  mov     edx, 246h; void *
0x18002b835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b83a  nop
0x18002b83b  lea     rcx, [rsp+2F0h+var_298]
0x18002b840  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b845  nop
0x18002b846  lea     rcx, [rsp+2F0h+var_278]
0x18002b84b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b850  nop
0x18002b851  lea     rcx, [rsp+2F0h+hKey]
0x18002b856  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b85b  mov     eax, edi
0x18002b85d  jmp     short loc_18002B896
0x18002b85f  mov     r9d, eax; char *
0x18002b862  mov     edx, 231h; void *
0x18002b867  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b86e  mov     rcx, [rbp+1F8h]; this
0x18002b875  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b87a  mov     ebx, eax
0x18002b87c  lea     rcx, [rsp+2F0h+hKey]
0x18002b881  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b886  mov     eax, ebx
0x18002b888  jmp     short loc_18002B896
0x18002b88a  lea     rcx, [rsp+2F0h+hKey]
0x18002b88f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b894  xor     eax, eax
0x18002b896  mov     rcx, [rbp+1F0h+var_40]
0x18002b89d  xor     rcx, rsp; StackCookie
0x18002b8a0  call    __security_check_cookie
0x18002b8a5  add     rsp, 2C0h
0x18002b8ac  pop     r15
0x18002b8ae  pop     r14
0x18002b8b0  pop     r12
0x18002b8b2  pop     rdi
0x18002b8b3  pop     rsi
0x18002b8b4  pop     rbx
0x18002b8b5  pop     rbp
0x18002b8b6  retn
```
