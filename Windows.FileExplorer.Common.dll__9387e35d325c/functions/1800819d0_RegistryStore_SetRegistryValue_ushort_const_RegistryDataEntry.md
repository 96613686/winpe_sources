# RegistryStore::SetRegistryValue(ushort const *,RegistryDataEntry *)

- ea: `0x1800819d0`
- end: `0x180081d7a`
- name: `?SetRegistryValue@RegistryStore@@QEAAJPEBGPEAURegistryDataEntry@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(RegistryStore *__hidden this, const unsigned __int16 *, struct RegistryDataEntry *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800809e0`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x180015fa0`
- `0x180016440`
- `0x180020358`
- `0x18002b8c0`
- `0x18002edcc`
- `0x18002fed4`
- `0x18002ff94`
- `0x180030718`
- `0x180037780`
- `0x180080668`
- `0x180080700`
- `0x180081700`
- `0x180081950`
- `0x1800819d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081b57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081b57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180081b7e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180081b7e`
- `ntdll!RtlInitUnicodeString` at `0x180081cc0`
- `ntdll!RtlInitUnicodeString` at `0x180081cc0`
- `ntdll!NtSetValueKey` at `0x180081cdd`
- `ntdll!NtSetValueKey` at `0x180081cdd`

## string_xrefs

- `0x180081c42`: `RecusevelyCreateAndOpenKey for %ws`
- `0x180081d11`: `RegSet:RegKeyName = %ws RegValueName = %ws`
- `0x180081a13`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081b05`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081b93`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081c51`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081d20`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegistryStore::SetRegistryValue(
        RegistryStore *this,
        const unsigned __int16 *a2,
        struct RegistryDataEntry *a3)
{
  unsigned int v6; // ebx
  __int64 PathWithUserSid; // rax
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  const char *v16; // r9
  __int64 v17; // rdx
  ULONG v18; // r14d
  LPCWSTR *v19; // rdx
  int v20; // edi
  LPCWSTR *v21; // rdx
  unsigned int v22; // eax
  char *v23; // rdi
  ULONG DataSize; // esi
  const WCHAR *v25; // rdx
  NTSTATUS v26; // eax
  LPCWSTR *v27; // r8
  LPCWSTR *v28; // rdx
  int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-71h] BYREF
  HKEY v34[2]; // [rsp+50h] [rbp-69h] BYREF
  char v35; // [rsp+60h] [rbp-59h]
  LPCWSTR lpSubKey[3]; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp-39h]
  LPCWSTR lpValueName[3]; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v39; // [rsp+A0h] [rbp-19h]
  HANDLE *p_KeyHandle; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-9h] BYREF
  char v42; // [rsp+B8h] [rbp-1h]
  _BYTE v43[32]; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( a3 )
  {
    std::wstring::wstring(&p_KeyHandle, (char *)a3 + *((_QWORD *)a3 + 1) + 42);
    RegistryStore::GetPathWithUserSid(this, lpValueName, &p_KeyHandle);
    std::wstring::_Tidy_deallocate(&p_KeyHandle);
    std::wstring::wstring(lpSubKey, a2);
    if ( *((_WORD *)a3 + 21) )
    {
      std::wstring::append(lpSubKey, L"\\");
      std::wstring::append(lpSubKey, (char *)a3 + 42);
    }
    PathWithUserSid = RegistryStore::GetPathWithUserSid(this, v43, lpSubKey);
    std::wstring::operator=(lpSubKey, PathWithUserSid);
    std::wstring::_Tidy_deallocate(v43);
    if ( *((_BYTE *)a3 + 40) )
    {
      v8 = (const unsigned __int16 *)lpSubKey;
      if ( v37 > 7 )
        v8 = lpSubKey[0];
      v9 = RegistryStore::RecurseDeleteKey(this, v8);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = (unsigned int)v9;
        v11 = 952;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
          (const char *)v10,
          phkResult);
LABEL_48:
        std::wstring::_Tidy_deallocate(lpSubKey);
        std::wstring::_Tidy_deallocate(lpValueName);
        return v6;
      }
LABEL_47:
      v6 = 0;
      goto LABEL_48;
    }
    if ( *((_DWORD *)a3 + 6) == 1 || *((_DWORD *)a3 + 6) == 2 )
    {
      KeyHandle = 0;
      p_KeyHandle = &KeyHandle;
      v41 = 0;
      v18 = 1;
      v42 = 1;
      v19 = lpSubKey;
      if ( v37 > 7 )
        v19 = (LPCWSTR *)lpSubKey[0];
      std::wstring::wstring(v43, v19);
      v20 = RegistryStore::RecusevelyCreateAndOpenKey(this, v43, &v41);
      std::wstring::_Tidy_deallocate(v43);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_KeyHandle);
      if ( v20 >= 0 )
      {
        if ( *((_BYTE *)a3 + 41) )
        {
          v23 = (char *)this + 56;
          if ( *((_QWORD *)this + 10) > 7u )
            v23 = *(char **)v23;
          DataSize = 2 * *((_DWORD *)this + 18) + 2;
        }
        else
        {
          v23 = (char *)a3 + *((_QWORD *)a3 + 1) + *((_QWORD *)a3 + 2) + 42;
          DataSize = *((_DWORD *)a3 + 8);
          v18 = *(_DWORD *)a3;
        }
        *(_OWORD *)v34 = 0;
        v25 = (const WCHAR *)lpValueName;
        if ( v39 > 7 )
          v25 = lpValueName[0];
        RtlInitUnicodeString((PUNICODE_STRING)v34, v25);
        v26 = NtSetValueKey(KeyHandle, (PUNICODE_STRING)v34, 0, v18, v23, DataSize);
        if ( v26 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
          goto LABEL_47;
        }
        v27 = lpValueName;
        if ( v39 > 7 )
          v27 = (LPCWSTR *)lpValueName[0];
        v28 = lpSubKey;
        if ( v37 > 7 )
          v28 = (LPCWSTR *)lpSubKey[0];
        v22 = wil::details::in1diag3::Return_NtStatusMsg(
                retaddr,
                (void *)0x3FC,
                (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
                (const char *)(unsigned int)v26,
                (int)"RegSet:RegKeyName = %ws RegValueName = %ws",
                (const char *)v28,
                v27);
      }
      else
      {
        v21 = lpSubKey;
        if ( v37 > 7 )
          v21 = (LPCWSTR *)lpSubKey[0];
        v22 = wil::details::in1diag3::Return_NtStatusMsg(
                retaddr,
                (void *)0x3E3,
                (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
                (const char *)(unsigned int)v20,
                (int)"RecusevelyCreateAndOpenKey for %ws",
                (const char *)v21);
      }
      v6 = v22;
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
      goto LABEL_48;
    }
    if ( *((_DWORD *)a3 + 6) != 3 )
    {
      v6 = -2147024883;
      v10 = 2147942413LL;
      v11 = 1026;
      goto LABEL_14;
    }
    hKey = 0;
    v34[0] = (HKEY)&hKey;
    v34[1] = 0;
    v35 = 1;
    v12 = (const WCHAR *)lpSubKey;
    if ( v37 > 7 )
      v12 = lpSubKey[0];
    v13 = RegOpenKeyExW(*(HKEY *)this, v12, 0, 0x20007u, &v34[1]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v34);
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        v16 = (const char *)v13;
        v17 = 978;
        goto LABEL_22;
      }
    }
    else
    {
      v14 = (const WCHAR *)lpValueName;
      if ( v39 > 7 )
        v14 = lpValueName[0];
      v15 = RegDeleteValueW(hKey, v14);
      if ( (v15 & 0xFFFFFFFD) != 0 )
      {
        v16 = (const char *)v15;
        v17 = 972;
LABEL_22:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v17,
               (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
               v16,
               phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_48;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_47;
  }
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3AB,
    (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
    (const char *)0x80070057LL,
    phkResult);
  return v6;
}

```

## disassembly

```asm
0x1800819d0  mov     [rsp-8+arg_18], rbx
0x1800819d5  push    rbp
0x1800819d6  push    rsi
0x1800819d7  push    rdi
0x1800819d8  push    r14
0x1800819da  push    r15
0x1800819dc  lea     rbp, [rsp-37h]
0x1800819e1  sub     rsp, 0F0h
0x1800819e8  mov     rax, cs:__security_cookie
0x1800819ef  xor     rax, rsp
0x1800819f2  mov     [rbp+57h+var_28], rax
0x1800819f6  mov     rbx, r8
0x1800819f9  mov     rdi, rdx
0x1800819fc  mov     rsi, rcx
0x1800819ff  xor     r15d, r15d
0x180081a02  test    r8, r8
0x180081a05  jnz     short loc_180081A29
0x180081a07  mov     rcx, [rbp+5Fh]; this
0x180081a0b  mov     ebx, 80070057h
0x180081a10  mov     r9d, ebx; char *
0x180081a13  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081a1a  mov     edx, 3ABh; void *
0x180081a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081a24  jmp     loc_180081D55
0x180081a29  mov     rdx, [r8+8]
0x180081a2d  add     rdx, 2Ah ; '*'
0x180081a31  add     rdx, rbx
0x180081a34  lea     rcx, [rbp+57h+var_68]
0x180081a38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081a3d  nop
0x180081a3e  lea     r8, [rbp+57h+var_68]
0x180081a42  lea     rdx, [rbp+57h+lpValueName]
0x180081a46  mov     rcx, rsi
0x180081a49  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x180081a4e  nop
0x180081a4f  lea     rcx, [rbp+57h+var_68]
0x180081a53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081a58  mov     rdx, rdi
0x180081a5b  lea     rcx, [rbp+57h+lpSubKey]
0x180081a5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081a64  nop
0x180081a65  cmp     [rbx+2Ah], r15w
0x180081a6a  jz      short loc_180081A89
0x180081a6c  lea     rdx, S; "\\"
0x180081a73  lea     rcx, [rbp+57h+lpSubKey]
0x180081a77  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180081a7c  lea     rdx, [rbx+2Ah]
0x180081a80  lea     rcx, [rbp+57h+lpSubKey]
0x180081a84  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180081a89  lea     r8, [rbp+57h+lpSubKey]
0x180081a8d  lea     rdx, [rbp+57h+var_48]
0x180081a91  mov     rcx, rsi
0x180081a94  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x180081a99  mov     rdx, rax
0x180081a9c  lea     rcx, [rbp+57h+lpSubKey]
0x180081aa0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180081aa5  lea     rcx, [rbp+57h+var_48]
0x180081aa9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081aae  cmp     [rbx+28h], r15b
0x180081ab2  jz      short loc_180081ADE
0x180081ab4  lea     rdx, [rbp+57h+lpSubKey]
0x180081ab8  cmp     [rbp+57h+var_90], 7
0x180081abd  cmova   rdx, [rbp+57h+lpSubKey]; unsigned __int16 *
0x180081ac2  mov     rcx, rsi; this
0x180081ac5  call    ?RecurseDeleteKey@RegistryStore@@AEAAJPEBG@Z; RegistryStore::RecurseDeleteKey(ushort const *)
0x180081aca  mov     ebx, eax
0x180081acc  test    eax, eax
0x180081ace  jns     loc_180081D3F
0x180081ad4  mov     r9d, eax
0x180081ad7  mov     edx, 3B8h
0x180081adc  jmp     short loc_180081B05
0x180081ade  mov     ecx, [rbx+18h]
0x180081ae1  sub     ecx, 1
0x180081ae4  jz      loc_180081BD0
0x180081aea  sub     ecx, 1
0x180081aed  jz      loc_180081BD0
0x180081af3  cmp     ecx, 1
0x180081af6  jz      short loc_180081B1A
0x180081af8  mov     ebx, 8007000Dh
0x180081afd  mov     r9d, ebx; char *
0x180081b00  mov     edx, 402h; void *
0x180081b05  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081b0c  mov     rcx, [rbp+5Fh]; this
0x180081b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081b15  jmp     loc_180081D42
0x180081b1a  mov     [rbp+57h+hKey], r15
0x180081b1e  lea     rax, [rbp+57h+hKey]
0x180081b22  mov     [rbp+57h+var_C0], rax
0x180081b26  mov     [rbp+57h+var_C0+8], r15
0x180081b2a  mov     r14d, 1
0x180081b30  mov     [rbp+57h+var_B0], r14b
0x180081b34  lea     rdx, [rbp+57h+lpSubKey]
0x180081b38  cmp     [rbp+57h+var_90], 7
0x180081b3d  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180081b42  lea     rax, [rbp+57h+var_C0+8]
0x180081b46  mov     [rsp+110h+phkResult], rax; unsigned int
0x180081b4b  mov     r9d, 20007h; samDesired
0x180081b51  xor     r8d, r8d; ulOptions
0x180081b54  mov     rcx, [rsi]; hKey
0x180081b57  call    cs:__imp_RegOpenKeyExW
0x180081b5d  mov     ebx, eax
0x180081b5f  lea     rcx, [rbp+57h+var_C0]
0x180081b63  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180081b68  test    ebx, ebx
0x180081b6a  jnz     short loc_180081BB3
0x180081b6c  lea     rdx, [rbp+57h+lpValueName]
0x180081b70  cmp     [rbp+57h+var_70], 7
0x180081b75  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x180081b7a  mov     rcx, [rbp+57h+hKey]; hKey
0x180081b7e  call    cs:__imp_RegDeleteValueW
0x180081b84  test    eax, 0FFFFFFFDh
0x180081b89  jz      short loc_180081BC2
0x180081b8b  mov     r9d, eax; char *
0x180081b8e  mov     edx, 3CCh; void *
0x180081b93  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081b9a  mov     rcx, [rbp+5Fh]; this
0x180081b9e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180081ba3  mov     ebx, eax
0x180081ba5  lea     rcx, [rbp+57h+hKey]
0x180081ba9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081bae  jmp     loc_180081D42
0x180081bb3  cmp     ebx, 2
0x180081bb6  jz      short loc_180081BC2
0x180081bb8  mov     r9d, ebx
0x180081bbb  mov     edx, 3D2h
0x180081bc0  jmp     short loc_180081B93
0x180081bc2  lea     rcx, [rbp+57h+hKey]
0x180081bc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081bcb  jmp     loc_180081D3F
0x180081bd0  mov     [rbp+57h+KeyHandle], r15
0x180081bd4  lea     rax, [rbp+57h+KeyHandle]
0x180081bd8  mov     [rbp+57h+var_68], rax
0x180081bdc  mov     [rbp+57h+var_60], r15
0x180081be0  mov     r14d, 1
0x180081be6  mov     [rbp+57h+var_58], r14b
0x180081bea  lea     rdx, [rbp+57h+lpSubKey]
0x180081bee  cmp     [rbp+57h+var_90], 7
0x180081bf3  cmova   rdx, [rbp+57h+lpSubKey]
0x180081bf8  lea     rcx, [rbp+57h+var_48]
0x180081bfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081c01  nop
0x180081c02  lea     r8, [rbp+57h+var_60]
0x180081c06  lea     rdx, [rbp+57h+var_48]
0x180081c0a  mov     rcx, rsi
0x180081c0d  call    ?RecusevelyCreateAndOpenKey@RegistryStore@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAX@Z; RegistryStore::RecusevelyCreateAndOpenKey(std::wstring const &,void * *)
0x180081c12  mov     edi, eax
0x180081c14  lea     rcx, [rbp+57h+var_48]
0x180081c18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081c1d  nop
0x180081c1e  lea     rcx, [rbp+57h+var_68]
0x180081c22  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180081c27  test    edi, edi
0x180081c29  jns     short loc_180081C72
0x180081c2b  lea     rdx, [rbp+57h+lpSubKey]
0x180081c2f  cmp     [rbp+57h+var_90], 7
0x180081c34  cmova   rdx, [rbp+57h+lpSubKey]
0x180081c39  mov     rcx, [rbp+5Fh]; this
0x180081c3d  mov     qword ptr [rsp+110h+DataSize], rdx; char *
0x180081c42  lea     rax, aRecusevelycrea; "RecusevelyCreateAndOpenKey for %ws"
0x180081c49  mov     [rsp+110h+phkResult], rax; int
0x180081c4e  mov     r9d, edi; char *
0x180081c51  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081c58  mov     edx, 3E3h; void *
0x180081c5d  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180081c62  mov     ebx, eax
0x180081c64  lea     rcx, [rbp+57h+KeyHandle]
0x180081c68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180081c6d  jmp     loc_180081D42
0x180081c72  cmp     [rbx+29h], r15b
0x180081c76  jz      short loc_180081C92
0x180081c78  lea     rdi, [rsi+38h]
0x180081c7c  cmp     qword ptr [rdi+18h], 7
0x180081c81  jbe     short loc_180081C86
0x180081c83  mov     rdi, [rdi]
0x180081c86  mov     eax, [rsi+48h]
0x180081c89  lea     esi, ds:2[rax*2]
0x180081c90  jmp     short loc_180081CA7
0x180081c92  mov     rdi, [rbx+10h]
0x180081c96  add     rdi, 2Ah ; '*'
0x180081c9a  add     rdi, [rbx+8]
0x180081c9e  add     rdi, rbx
0x180081ca1  mov     esi, [rbx+20h]
0x180081ca4  mov     r14d, [rbx]
0x180081ca7  xorps   xmm0, xmm0
0x180081caa  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x180081cae  lea     rdx, [rbp+57h+lpValueName]
0x180081cb2  cmp     [rbp+57h+var_70], 7
0x180081cb7  cmova   rdx, [rbp+57h+lpValueName]; SourceString
0x180081cbc  lea     rcx, [rbp+57h+var_C0]; DestinationString
0x180081cc0  call    cs:__imp_RtlInitUnicodeString
0x180081cc6  mov     [rsp+110h+DataSize], esi; DataSize
0x180081cca  mov     [rsp+110h+phkResult], rdi; Data
0x180081ccf  mov     r9d, r14d; Type
0x180081cd2  xor     r8d, r8d; TitleIndex
0x180081cd5  lea     rdx, [rbp+57h+var_C0]; ValueName
0x180081cd9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180081cdd  call    cs:__imp_NtSetValueKey
0x180081ce3  test    eax, eax
0x180081ce5  jns     short loc_180081D36
0x180081ce7  lea     r8, [rbp+57h+lpValueName]
0x180081ceb  cmp     [rbp+57h+var_70], 7
0x180081cf0  cmova   r8, [rbp+57h+lpValueName]
0x180081cf5  lea     rdx, [rbp+57h+lpSubKey]
0x180081cf9  cmp     [rbp+57h+var_90], 7
0x180081cfe  cmova   rdx, [rbp+57h+lpSubKey]
0x180081d03  mov     rcx, [rbp+5Fh]; this
0x180081d07  mov     [rsp+110h+var_E0], r8
0x180081d0c  mov     qword ptr [rsp+110h+DataSize], rdx; char *
0x180081d11  lea     rdx, aRegsetRegkeyna; "RegSet:RegKeyName = %ws RegValueName = "...
0x180081d18  mov     [rsp+110h+phkResult], rdx; int
0x180081d1d  mov     r9d, eax; char *
0x180081d20  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081d27  mov     edx, 3FCh; void *
0x180081d2c  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180081d31  jmp     loc_180081C62
0x180081d36  lea     rcx, [rbp+57h+KeyHandle]
0x180081d3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180081d3f  mov     ebx, r15d
0x180081d42  lea     rcx, [rbp+57h+lpSubKey]
0x180081d46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081d4b  nop
0x180081d4c  lea     rcx, [rbp+57h+lpValueName]
0x180081d50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081d55  mov     eax, ebx
0x180081d57  mov     rcx, [rbp+57h+var_28]
0x180081d5b  xor     rcx, rsp; StackCookie
0x180081d5e  call    __security_check_cookie
0x180081d63  mov     rbx, [rsp+110h+arg_18]
0x180081d6b  add     rsp, 0F0h
0x180081d72  pop     r15
0x180081d74  pop     r14
0x180081d76  pop     rdi
0x180081d77  pop     rsi
0x180081d78  pop     rbp
0x180081d79  retn
```
