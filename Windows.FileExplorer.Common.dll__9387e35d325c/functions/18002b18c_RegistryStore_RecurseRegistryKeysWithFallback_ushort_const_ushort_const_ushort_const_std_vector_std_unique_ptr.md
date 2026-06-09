# RegistryStore::RecurseRegistryKeysWithFallback(ushort const *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>,std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>> &,bool &)

- ea: `0x18002b18c`
- end: `0x18002b611`
- name: `?RecurseRegistryKeysWithFallback@RegistryStore@@AEAAJPEBG00AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z`
- size: `1157`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002b18c`
- `0x18002f75c`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x180015fa0`
- `0x180016440`
- `0x180020358`
- `0x18002b18c`
- `0x18002b618`
- `0x18002b8c0`
- `0x18002b8e4`
- `0x18002edcc`
- `0x180037780`
- `0x18007ddd0`
- `0x18007def4`
- `0x180080534`
- `0x180081040`
- `0x180081d80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b1f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b27b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b1f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b27b`

## string_xrefs

- `0x18002b22d`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b2c3`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b30b`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b348`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002b59e`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RegistryStore::RecurseRegistryKeysWithFallback(
        HKEY *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  int v14; // eax
  int AllRegistryValuesWithFallback; // eax
  int v16; // edi
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 *v21; // rbx
  _QWORD *v22; // rdx
  __int64 **v23; // r9
  LPCWSTR *v24; // r8
  __int64 v25; // rdx
  __int64 **v26; // r8
  __int64 **v27; // r8
  LPCWSTR *v28; // rdx
  __int64 **v29; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  int phkResultb; // [rsp+20h] [rbp-A9h]
  int phkResultc; // [rsp+20h] [rbp-A9h]
  char v37; // [rsp+40h] [rbp-89h] BYREF
  char v38; // [rsp+41h] [rbp-88h] BYREF
  __int64 v39; // [rsp+48h] [rbp-81h] BYREF
  __int128 v40; // [rsp+50h] [rbp-79h] BYREF
  __int64 v41; // [rsp+60h] [rbp-69h] BYREF
  __int64 *v42; // [rsp+68h] [rbp-61h] BYREF
  HKEY v43; // [rsp+70h] [rbp-59h] BYREF
  __int64 v44; // [rsp+78h] [rbp-51h]
  unsigned __int64 v45; // [rsp+80h] [rbp-49h]
  _DWORD lpSubKey[6]; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int64 v47; // [rsp+A0h] [rbp-29h]
  _DWORD Src[6]; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v49; // [rsp+C0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  *a6 = 0;
  v41 = 0;
  v42 = &v41;
  v43 = 0;
  LOBYTE(v44) = 1;
  v10 = RegOpenKeyExW(*a1, a2, 0, 0x20019u, &v43);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v42);
  if ( v10 == 2 )
  {
    v11 = RegistryStore::RecurseRegistryKeys((_DWORD)a1, (_DWORD)a3, a4, a5, (__int64)a6);
LABEL_5:
    v12 = v11;
    goto LABEL_56;
  }
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x260,
            (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
            (const char *)v10,
            phkResult);
    goto LABEL_5;
  }
  v39 = 0;
  v42 = &v39;
  v43 = 0;
  LOBYTE(v44) = 1;
  v13 = RegOpenKeyExW(*a1, a3, 0, 0x20019u, &v43);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v42);
  if ( v13 == 2 )
  {
    v14 = RegistryStore::RecurseRegistryKeys((_DWORD)a1, (_DWORD)a2, a4, a5, (__int64)a6);
LABEL_8:
    v12 = v14;
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
    goto LABEL_56;
  }
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x26C,
            (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
            (const char *)v13,
            phkResulta);
    goto LABEL_8;
  }
  *a6 = 1;
  AllRegistryValuesWithFallback = RegistryStore::GetAllRegistryValuesWithFallback(
                                    (_DWORD)a1,
                                    v41,
                                    v39,
                                    (_DWORD)a2,
                                    (__int64)a3,
                                    a4,
                                    a5);
  v12 = AllRegistryValuesWithFallback;
  v16 = 0;
  if ( AllRegistryValuesWithFallback < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
      (const char *)(unsigned int)AllRegistryValuesWithFallback,
      phkResultb);
    goto LABEL_9;
  }
  v40 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::_Alloc_sentinel_and_proxy(&v40);
  v18 = lambda_fe90a98c913095a05a04163a2206b1c8_::operator()__lambda_12d61112bbe27118e170da8e70443aa3___(v17, v41, &v40);
  v12 = v18;
  if ( v18 < 0 )
  {
    v20 = 664;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
      (const char *)(unsigned int)v18,
      phkResultb);
    std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>(&v40);
    goto LABEL_9;
  }
  v18 = lambda_fe90a98c913095a05a04163a2206b1c8_::operator()__lambda_18be2498ddba8ed1d9000ceb738c6366___(v19, v39, &v40);
  v12 = v18;
  if ( v18 < 0 )
  {
    v20 = 666;
    goto LABEL_16;
  }
  v21 = *(__int64 **)v40;
  while ( !*((_BYTE *)v21 + 25) )
  {
    std::wstring::wstring(Src, a2);
    std::wstring::append(Src, L"\\");
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::wstring(lpSubKey, a3);
    std::wstring::append(lpSubKey, L"\\");
    std::wstring::_Append<unsigned short>(lpSubKey);
    std::wstring::wstring(&v42, a4);
    if ( v44 )
      std::wstring::append(&v42, L"\\");
    std::wstring::_Append<unsigned short>(&v42);
    if ( *((_BYTE *)v21 + 64) )
    {
      v22 = Src;
      if ( *((_BYTE *)v21 + 65) )
      {
        v38 = 0;
        v23 = &v42;
        if ( v45 > 7 )
          LODWORD(v23) = (_DWORD)v42;
        v24 = (LPCWSTR *)lpSubKey;
        if ( v47 > 7 )
          LODWORD(v24) = lpSubKey[0];
        if ( v49 > 7 )
          LODWORD(v22) = Src[0];
        v16 = RegistryStore::RecurseRegistryKeysWithFallback(
                (_DWORD)a1,
                (_DWORD)v22,
                (_DWORD)v24,
                (_DWORD)v23,
                a5,
                (__int64)&v38);
        if ( v16 < 0 )
        {
          v25 = 696;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
            (const char *)(unsigned int)v16,
            phkResultc);
          std::wstring::_Tidy_deallocate(&v42);
          std::wstring::_Tidy_deallocate(lpSubKey);
          std::wstring::_Tidy_deallocate(Src);
          break;
        }
      }
      else
      {
        v37 = 0;
        v26 = &v42;
        if ( v45 > 7 )
          LODWORD(v26) = (_DWORD)v42;
        if ( v49 > 7 )
          LODWORD(v22) = Src[0];
        v16 = RegistryStore::RecurseRegistryKeys((_DWORD)a1, (_DWORD)v22, (_DWORD)v26, a5, (__int64)&v37);
        if ( v16 < 0 )
        {
          v25 = 707;
          goto LABEL_54;
        }
      }
    }
    else
    {
      v37 = 0;
      v27 = &v42;
      if ( v45 > 7 )
        LODWORD(v27) = (_DWORD)v42;
      v28 = (LPCWSTR *)lpSubKey;
      if ( v47 > 7 )
        LODWORD(v28) = lpSubKey[0];
      v16 = RegistryStore::RecurseRegistryKeys((_DWORD)a1, (_DWORD)v28, (_DWORD)v27, a5, (__int64)&v37);
      if ( v16 < 0 )
      {
        v25 = 718;
        goto LABEL_54;
      }
    }
    std::wstring::_Tidy_deallocate(&v42);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(Src);
    v29 = (__int64 **)v21[2];
    v16 = 0;
    if ( *((_BYTE *)v29 + 25) )
    {
      for ( i = (__int64 *)v21[1]; !*((_BYTE *)i + 25) && v21 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v21 = i;
      v21 = i;
    }
    else
    {
      v21 = (__int64 *)v21[2];
      for ( j = *v29; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v21 = j;
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
  v12 = v16;
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
  return v12;
}

```

## disassembly

```asm
0x18002b18c  push    rbp
0x18002b18e  push    rbx
0x18002b18f  push    rsi
0x18002b190  push    rdi
0x18002b191  push    r12
0x18002b193  push    r13
0x18002b195  push    r14
0x18002b197  push    r15
0x18002b199  lea     rbp, [rsp-0Fh]
0x18002b19e  sub     rsp, 0D8h
0x18002b1a5  mov     rax, cs:__security_cookie
0x18002b1ac  xor     rax, rsp
0x18002b1af  mov     [rbp+47h+var_48], rax
0x18002b1b3  mov     r15, r9
0x18002b1b6  mov     r12, r8
0x18002b1b9  mov     r13, rdx
0x18002b1bc  mov     rsi, rcx
0x18002b1bf  mov     r14, [rbp+47h+arg_20]
0x18002b1c3  mov     rdi, [rbp+47h+arg_28]
0x18002b1c7  xor     ecx, ecx
0x18002b1c9  mov     [rdi], cl
0x18002b1cb  mov     [rbp+47h+var_B0], rcx
0x18002b1cf  lea     rax, [rbp+47h+var_B0]
0x18002b1d3  mov     [rbp+47h+var_A8], rax
0x18002b1d7  mov     [rbp+47h+var_A0], rcx
0x18002b1db  mov     byte ptr [rbp+47h+var_98], 1
0x18002b1df  lea     rax, [rbp+47h+var_A0]
0x18002b1e3  mov     [rsp+110h+phkResult], rax; unsigned int
0x18002b1e8  mov     r9d, 20019h; samDesired
0x18002b1ee  xor     r8d, r8d; ulOptions
0x18002b1f1  mov     rcx, [rsi]; hKey
0x18002b1f4  call    cs:__imp_RegOpenKeyExW
0x18002b1fa  mov     ebx, eax
0x18002b1fc  lea     rcx, [rbp+47h+var_A8]
0x18002b200  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002b205  cmp     ebx, 2
0x18002b208  jnz     short loc_18002B222
0x18002b20a  mov     [rsp+110h+phkResult], rdi
0x18002b20f  mov     r9, r14
0x18002b212  mov     r8, r15
0x18002b215  mov     rdx, r12
0x18002b218  mov     rcx, rsi
0x18002b21b  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b220  jmp     short loc_18002B23E
0x18002b222  test    ebx, ebx
0x18002b224  jz      short loc_18002B245
0x18002b226  mov     rcx, [rbp+4Fh]; this
0x18002b22a  mov     r9d, ebx; char *
0x18002b22d  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b234  mov     edx, 260h; void *
0x18002b239  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b23e  mov     ebx, eax
0x18002b240  jmp     loc_18002B5E6
0x18002b245  mov     [rsp+110h+var_C8], 0
0x18002b24e  lea     rax, [rsp+110h+var_C8]
0x18002b253  mov     [rbp+47h+var_A8], rax
0x18002b257  mov     [rbp+47h+var_A0], 0
0x18002b25f  mov     byte ptr [rbp+47h+var_98], 1
0x18002b263  lea     rax, [rbp+47h+var_A0]
0x18002b267  mov     [rsp+110h+phkResult], rax; unsigned int
0x18002b26c  mov     r9d, 20019h; samDesired
0x18002b272  xor     r8d, r8d; ulOptions
0x18002b275  mov     rdx, r12; lpSubKey
0x18002b278  mov     rcx, [rsi]; hKey
0x18002b27b  call    cs:__imp_RegOpenKeyExW
0x18002b281  mov     ebx, eax
0x18002b283  lea     rcx, [rbp+47h+var_A8]
0x18002b287  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002b28c  cmp     ebx, 2
0x18002b28f  jnz     short loc_18002B2B8
0x18002b291  mov     [rsp+110h+phkResult], rdi
0x18002b296  mov     r9, r14
0x18002b299  mov     r8, r15
0x18002b29c  mov     rdx, r13
0x18002b29f  mov     rcx, rsi
0x18002b2a2  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b2a7  mov     ebx, eax
0x18002b2a9  lea     rcx, [rsp+110h+var_C8]
0x18002b2ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b2b3  jmp     loc_18002B5E6
0x18002b2b8  test    ebx, ebx
0x18002b2ba  jz      short loc_18002B2D6
0x18002b2bc  mov     rcx, [rbp+4Fh]; this
0x18002b2c0  mov     r9d, ebx; char *
0x18002b2c3  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b2ca  mov     edx, 26Ch; void *
0x18002b2cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b2d4  jmp     short loc_18002B2A7
0x18002b2d6  mov     byte ptr [rdi], 1
0x18002b2d9  mov     [rsp+110h+var_E0], r14
0x18002b2de  mov     [rsp+110h+var_E8], r15
0x18002b2e3  mov     [rsp+110h+phkResult], r12; int
0x18002b2e8  mov     r9, r13
0x18002b2eb  mov     r8, [rsp+110h+var_C8]
0x18002b2f0  mov     rdx, [rbp+47h+var_B0]
0x18002b2f4  mov     rcx, rsi
0x18002b2f7  call    ?GetAllRegistryValuesWithFallback@RegistryStore@@AEAAJPEAUHKEY__@@0PEBG11AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@@Z; RegistryStore::GetAllRegistryValuesWithFallback(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &)
0x18002b2fc  mov     ebx, eax
0x18002b2fe  xor     edi, edi
0x18002b300  test    eax, eax
0x18002b302  jns     short loc_18002B31E
0x18002b304  mov     rcx, [rbp+4Fh]; this
0x18002b308  mov     r9d, eax; char *
0x18002b30b  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b312  mov     edx, 278h; void *
0x18002b317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b31c  jmp     short loc_18002B2A9
0x18002b31e  xorps   xmm0, xmm0
0x18002b321  movdqu  [rbp+47h+var_C0], xmm0
0x18002b326  lea     rcx, [rbp+47h+var_C0]
0x18002b32a  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002b32f  nop
0x18002b330  lea     r8, [rbp+47h+var_C0]
0x18002b334  mov     rdx, [rbp+47h+var_B0]
0x18002b338  call    _lambda_fe90a98c913095a05a04163a2206b1c8___operator____lambda_12d61112bbe27118e170da8e70443aa3___
0x18002b33d  mov     ebx, eax
0x18002b33f  test    eax, eax
0x18002b341  jns     short loc_18002B36A
0x18002b343  mov     edx, 298h; void *
0x18002b348  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b34f  mov     r9d, eax; char *
0x18002b352  mov     rcx, [rbp+4Fh]; this
0x18002b356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b35b  nop
0x18002b35c  lea     rcx, [rbp+47h+var_C0]
0x18002b360  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>(void)
0x18002b365  jmp     loc_18002B2A9
0x18002b36a  lea     r8, [rbp+47h+var_C0]
0x18002b36e  mov     rdx, [rsp+110h+var_C8]
0x18002b373  call    _lambda_fe90a98c913095a05a04163a2206b1c8___operator____lambda_18be2498ddba8ed1d9000ceb738c6366___
0x18002b378  mov     ebx, eax
0x18002b37a  test    eax, eax
0x18002b37c  jns     short loc_18002B385
0x18002b37e  mov     edx, 29Ah
0x18002b383  jmp     short loc_18002B348
0x18002b385  mov     rbx, qword ptr [rbp+47h+var_C0]
0x18002b389  mov     rbx, [rbx]
0x18002b38c  cmp     [rbx+19h], dil
0x18002b390  jnz     loc_18002B5D0
0x18002b396  lea     rdi, [rbx+20h]
0x18002b39a  mov     rdx, r13
0x18002b39d  lea     rcx, [rbp+47h+Src]
0x18002b3a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b3a6  nop
0x18002b3a7  lea     rdx, S; "\\"
0x18002b3ae  lea     rcx, [rbp+47h+Src]
0x18002b3b2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b3b7  cmp     qword ptr [rbx+38h], 7
0x18002b3bc  jbe     short loc_18002B3C3
0x18002b3be  mov     rdx, [rdi]
0x18002b3c1  jmp     short loc_18002B3C6
0x18002b3c3  mov     rdx, rdi
0x18002b3c6  mov     r8, [rbx+30h]
0x18002b3ca  lea     rcx, [rbp+47h+Src]; Src
0x18002b3ce  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002b3d3  mov     rdx, r12
0x18002b3d6  lea     rcx, [rbp+47h+lpSubKey]
0x18002b3da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b3df  nop
0x18002b3e0  lea     rdx, S; "\\"
0x18002b3e7  lea     rcx, [rbp+47h+lpSubKey]
0x18002b3eb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b3f0  cmp     qword ptr [rdi+18h], 7
0x18002b3f5  jbe     short loc_18002B3FC
0x18002b3f7  mov     rdx, [rdi]
0x18002b3fa  jmp     short loc_18002B3FF
0x18002b3fc  mov     rdx, rdi
0x18002b3ff  mov     r8, [rbx+30h]
0x18002b403  lea     rcx, [rbp+47h+lpSubKey]; Src
0x18002b407  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002b40c  mov     rdx, r15
0x18002b40f  lea     rcx, [rbp+47h+var_A8]
0x18002b413  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b418  nop
0x18002b419  cmp     [rbp+47h+var_98], 0
0x18002b41e  jz      short loc_18002B430
0x18002b420  lea     rdx, S; "\\"
0x18002b427  lea     rcx, [rbp+47h+var_A8]
0x18002b42b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b430  cmp     qword ptr [rdi+18h], 7
0x18002b435  jbe     short loc_18002B43C
0x18002b437  mov     rdx, [rdi]
0x18002b43a  jmp     short loc_18002B43F
0x18002b43c  mov     rdx, rdi
0x18002b43f  mov     r8, [rbx+30h]
0x18002b443  lea     rcx, [rbp+47h+var_A8]; Src
0x18002b447  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002b44c  xor     eax, eax
0x18002b44e  mov     rcx, rsi
0x18002b451  cmp     [rdi+20h], al
0x18002b454  jz      loc_18002B4F3
0x18002b45a  lea     rdx, [rbp+47h+Src]
0x18002b45e  cmp     [rbx+41h], al
0x18002b461  jz      short loc_18002B4B5
0x18002b463  mov     [rsp+110h+var_D0+1], al
0x18002b467  lea     r9, [rbp+47h+var_A8]
0x18002b46b  cmp     [rbp+47h+var_90], 7
0x18002b470  cmova   r9, [rbp+47h+var_A8]
0x18002b475  lea     r8, [rbp+47h+lpSubKey]
0x18002b479  cmp     [rbp+47h+var_70], 7
0x18002b47e  cmova   r8, qword ptr [rbp+47h+lpSubKey]
0x18002b483  cmp     [rbp+47h+var_50], 7
0x18002b488  cmova   rdx, qword ptr [rbp+47h+Src]
0x18002b48d  lea     rax, [rsp+110h+var_D0+1]
0x18002b492  mov     [rsp+110h+var_E8], rax
0x18002b497  mov     [rsp+110h+phkResult], r14
0x18002b49c  call    ?RecurseRegistryKeysWithFallback@RegistryStore@@AEAAJPEBG00AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeysWithFallback(ushort const *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b4a1  mov     edi, eax
0x18002b4a3  test    eax, eax
0x18002b4a5  jns     loc_18002B52B
0x18002b4ab  mov     edx, 2B8h
0x18002b4b0  jmp     loc_18002B59E
0x18002b4b5  mov     [rsp+110h+var_D0], al
0x18002b4b9  lea     r8, [rbp+47h+var_A8]
0x18002b4bd  cmp     [rbp+47h+var_90], 7
0x18002b4c2  cmova   r8, [rbp+47h+var_A8]
0x18002b4c7  cmp     [rbp+47h+var_50], 7
0x18002b4cc  cmova   rdx, qword ptr [rbp+47h+Src]
0x18002b4d1  lea     rax, [rsp+110h+var_D0]
0x18002b4d6  mov     [rsp+110h+phkResult], rax
0x18002b4db  mov     r9, r14
0x18002b4de  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b4e3  mov     edi, eax
0x18002b4e5  test    eax, eax
0x18002b4e7  jns     short loc_18002B52B
0x18002b4e9  mov     edx, 2C3h
0x18002b4ee  jmp     loc_18002B59E
0x18002b4f3  mov     [rsp+110h+var_D0], al
0x18002b4f7  lea     r8, [rbp+47h+var_A8]
0x18002b4fb  cmp     [rbp+47h+var_90], 7
0x18002b500  cmova   r8, [rbp+47h+var_A8]
0x18002b505  lea     rdx, [rbp+47h+lpSubKey]
0x18002b509  cmp     [rbp+47h+var_70], 7
0x18002b50e  cmova   rdx, qword ptr [rbp+47h+lpSubKey]
0x18002b513  lea     rax, [rsp+110h+var_D0]
0x18002b518  mov     [rsp+110h+phkResult], rax; int
0x18002b51d  mov     r9, r14
0x18002b520  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002b525  mov     edi, eax
0x18002b527  test    eax, eax
0x18002b529  js      short loc_18002B599
0x18002b52b  lea     rcx, [rbp+47h+var_A8]
0x18002b52f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b534  nop
0x18002b535  lea     rcx, [rbp+47h+lpSubKey]
0x18002b539  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b53e  nop
0x18002b53f  lea     rcx, [rbp+47h+Src]
0x18002b543  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b548  mov     rcx, [rbx+10h]
0x18002b54c  xor     edi, edi
0x18002b54e  cmp     [rcx+19h], dil
0x18002b552  jz      short loc_18002B575
0x18002b554  mov     rax, [rbx+8]
0x18002b558  jmp     short loc_18002B567
0x18002b55a  cmp     rbx, [rax+10h]
0x18002b55e  jnz     short loc_18002B56D
0x18002b560  mov     rbx, rax
0x18002b563  mov     rax, [rax+8]
0x18002b567  cmp     [rax+19h], dil
0x18002b56b  jz      short loc_18002B55A
0x18002b56d  mov     rbx, rax
0x18002b570  jmp     loc_18002B38C
0x18002b575  mov     rbx, rcx
0x18002b578  mov     rcx, [rcx]
0x18002b57b  cmp     [rcx+19h], dil
0x18002b57f  jnz     loc_18002B38C
0x18002b585  mov     rbx, rcx
0x18002b588  mov     rax, [rcx]
0x18002b58b  mov     rcx, rax
0x18002b58e  cmp     [rax+19h], dil
0x18002b592  jz      short loc_18002B585
0x18002b594  jmp     loc_18002B38C
0x18002b599  mov     edx, 2CEh; void *
0x18002b59e  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18002b5a5  mov     r9d, edi; char *
0x18002b5a8  mov     rcx, [rbp+4Fh]; this
0x18002b5ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b5b1  nop
0x18002b5b2  lea     rcx, [rbp+47h+var_A8]
0x18002b5b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b5bb  nop
0x18002b5bc  lea     rcx, [rbp+47h+lpSubKey]
0x18002b5c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b5c5  nop
0x18002b5c6  lea     rcx, [rbp+47h+Src]
0x18002b5ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b5cf  nop
0x18002b5d0  lea     rcx, [rbp+47h+var_C0]
0x18002b5d4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KeyFoundInLocationEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KeyFoundInLocationEntry>>,0>>(void)
0x18002b5d9  nop
0x18002b5da  lea     rcx, [rsp+110h+var_C8]
0x18002b5df  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b5e4  mov     ebx, edi
0x18002b5e6  lea     rcx, [rbp+47h+var_B0]
0x18002b5ea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b5ef  mov     eax, ebx
0x18002b5f1  mov     rcx, [rbp+47h+var_48]
0x18002b5f5  xor     rcx, rsp; StackCookie
0x18002b5f8  call    __security_check_cookie
  ... truncated ...
```
