# RegistryStore::RecurseDeleteKey(ushort const *)

- ea: `0x180081700`
- end: `0x18008194a`
- name: `?RecurseDeleteKey@RegistryStore@@AEAAJPEBG@Z`
- size: `586`
- prototype: `__int64 __fastcall(RegistryStore *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180081700`
- `0x1800819d0`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x180015fa0`
- `0x180016440`
- `0x180020358`
- `0x18002b8c0`
- `0x18002edcc`
- `0x180037780`
- `0x180081700`
- `0x180081990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081779`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081779`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800818af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800818af`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800817e9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800817e9`

## string_xrefs

- `0x1800818c5`: `RegDelete:RegKeyName = %ws`
- `0x1800817a4`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081868`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x1800818d4`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081910`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryStore::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // eax
  const unsigned __int16 *p_lpSubKey; // rdx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v14; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v20; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v22; // [rsp+68h] [rbp-98h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( a2 && *a2 )
  {
    hKey = 0;
    lpSubKey = (LPCWSTR)&hKey;
    v20 = 0;
    v21 = 1;
    v4 = RegOpenKeyExW(*this, a2, 0, 0x20019u, &v20);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&lpSubKey);
    if ( v4 == 2 )
    {
      v5 = 0;
    }
    else
    {
      if ( v4 )
      {
        v6 = (const char *)v4;
        v7 = 898;
LABEL_7:
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
               v6,
               phkResulta);
      }
      else
      {
        while ( 1 )
        {
          cchName = 259;
          v9 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
          if ( v9 == 259 )
            break;
          if ( v9 )
          {
            v6 = (const char *)v9;
            v7 = 912;
            goto LABEL_7;
          }
          std::wstring::wstring(&lpSubKey, a2);
          std::wstring::append(&lpSubKey, L"\\");
          std::wstring::append(&lpSubKey, Name);
          p_lpSubKey = (const unsigned __int16 *)&lpSubKey;
          if ( v22 > 7 )
            p_lpSubKey = lpSubKey;
          v11 = RegistryStore::RecurseDeleteKey((RegistryStore *)this, p_lpSubKey);
          v12 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x396,
              (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
              (const char *)(unsigned int)v11,
              phkResulta);
            std::wstring::_Tidy_deallocate(&lpSubKey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v12;
          }
          std::wstring::_Tidy_deallocate(&lpSubKey);
        }
        v14 = RegDeleteKeyExW(*this, a2, 0, 0);
        if ( !v14 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
        v8 = wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0x39B,
               (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
               (const char *)v14,
               (unsigned int)"RegDelete:RegKeyName = %ws",
               (const char *)a2);
      }
      v5 = v8;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x378,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
      (const char *)0x80070057LL,
      phkResult);
  }
  return v5;
}

```

## disassembly

```asm
0x180081700  mov     [rsp-8+arg_10], rbx
0x180081705  mov     [rsp-8+arg_18], rsi
0x18008170a  push    rbp
0x18008170b  push    rdi
0x18008170c  push    r14
0x18008170e  lea     rbp, [rsp-190h]
0x180081716  sub     rsp, 290h
0x18008171d  mov     rax, cs:__security_cookie
0x180081724  xor     rax, rsp
0x180081727  mov     [rbp+1A0h+var_20], rax
0x18008172e  mov     rbx, rdx
0x180081731  mov     rsi, rcx
0x180081734  xor     r14d, r14d
0x180081737  test    rdx, rdx
0x18008173a  jz      loc_180081901
0x180081740  cmp     [rdx], r14w
0x180081744  jz      loc_180081901
0x18008174a  mov     [rsp+2A0h+hKey], r14
0x18008174f  lea     rax, [rsp+2A0h+hKey]
0x180081754  mov     [rsp+2A0h+lpSubKey], rax
0x180081759  mov     [rsp+2A0h+var_248], r14
0x18008175e  mov     [rsp+2A0h+var_240], 1
0x180081763  lea     rax, [rsp+2A0h+var_248]
0x180081768  mov     [rsp+2A0h+phkResult], rax; unsigned int
0x18008176d  mov     r9d, 20019h; samDesired
0x180081773  xor     r8d, r8d; ulOptions
0x180081776  mov     rcx, [rcx]; hKey
0x180081779  call    cs:__imp_RegOpenKeyExW
0x18008177f  mov     edi, eax
0x180081781  lea     rcx, [rsp+2A0h+lpSubKey]
0x180081786  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008178b  cmp     edi, 2
0x18008178e  jnz     short loc_180081798
0x180081790  mov     ebx, r14d
0x180081793  jmp     loc_1800818E7
0x180081798  test    edi, edi
0x18008179a  jz      short loc_1800817BC
0x18008179c  mov     r9d, edi; char *
0x18008179f  mov     edx, 382h; void *
0x1800817a4  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x1800817ab  mov     rcx, [rbp+1A8h]; this
0x1800817b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800817b7  jmp     loc_1800818E5
0x1800817bc  mov     [rsp+2A0h+cchName], 103h
0x1800817c4  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800817c9  mov     [rsp+2A0h+lpcchClass], r14; lpcchClass
0x1800817ce  mov     [rsp+2A0h+lpClass], r14; lpClass
0x1800817d3  mov     [rsp+2A0h+phkResult], r14; int
0x1800817d8  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800817dd  lea     r8, [rsp+2A0h+Name]; lpName
0x1800817e2  xor     edx, edx; dwIndex
0x1800817e4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800817e9  call    cs:__imp_RegEnumKeyExW
0x1800817ef  cmp     eax, 103h
0x1800817f4  jz      loc_1800818A3
0x1800817fa  test    eax, eax
0x1800817fc  jnz     loc_180081896
0x180081802  mov     rdx, rbx
0x180081805  lea     rcx, [rsp+2A0h+lpSubKey]
0x18008180a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008180f  nop
0x180081810  lea     rdx, S; "\\"
0x180081817  lea     rcx, [rsp+2A0h+lpSubKey]
0x18008181c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180081821  lea     rdx, [rsp+2A0h+Name]
0x180081826  lea     rcx, [rsp+2A0h+lpSubKey]
0x18008182b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180081830  lea     rdx, [rsp+2A0h+lpSubKey]
0x180081835  cmp     [rsp+2A0h+var_238], 7
0x18008183b  cmova   rdx, [rsp+2A0h+lpSubKey]; unsigned __int16 *
0x180081841  mov     rcx, rsi; this
0x180081844  call    ?RecurseDeleteKey@RegistryStore@@AEAAJPEBG@Z; RegistryStore::RecurseDeleteKey(ushort const *)
0x180081849  mov     edi, eax
0x18008184b  test    eax, eax
0x18008184d  js      short loc_18008185E
0x18008184f  lea     rcx, [rsp+2A0h+lpSubKey]
0x180081854  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081859  jmp     loc_1800817BC
0x18008185e  mov     rcx, [rbp+1A8h]; this
0x180081865  mov     r9d, edi; char *
0x180081868  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18008186f  mov     edx, 396h; void *
0x180081874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081879  nop
0x18008187a  lea     rcx, [rsp+2A0h+lpSubKey]
0x18008187f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081884  nop
0x180081885  lea     rcx, [rsp+2A0h+hKey]
0x18008188a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008188f  mov     eax, edi
0x180081891  jmp     loc_180081923
0x180081896  mov     r9d, eax
0x180081899  mov     edx, 390h
0x18008189e  jmp     loc_1800817A4
0x1800818a3  xor     r9d, r9d; Reserved
0x1800818a6  xor     r8d, r8d; samDesired
0x1800818a9  mov     rdx, rbx; lpSubKey
0x1800818ac  mov     rcx, [rsi]; hKey
0x1800818af  call    cs:__imp_RegDeleteKeyExW
0x1800818b5  test    eax, eax
0x1800818b7  jz      short loc_1800818F3
0x1800818b9  mov     rcx, [rbp+1A8h]; this
0x1800818c0  mov     [rsp+2A0h+lpClass], rbx; char *
0x1800818c5  lea     rdx, aRegdeleteRegke; "RegDelete:RegKeyName = %ws"
0x1800818cc  mov     [rsp+2A0h+phkResult], rdx; unsigned int
0x1800818d1  mov     r9d, eax; char *
0x1800818d4  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x1800818db  mov     edx, 39Bh; void *
0x1800818e0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800818e5  mov     ebx, eax
0x1800818e7  lea     rcx, [rsp+2A0h+hKey]
0x1800818ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818f1  jmp     short loc_180081921
0x1800818f3  lea     rcx, [rsp+2A0h+hKey]
0x1800818f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818fd  xor     eax, eax
0x1800818ff  jmp     short loc_180081923
0x180081901  mov     rcx, [rbp+1A8h]; this
0x180081908  mov     ebx, 80070057h
0x18008190d  mov     r9d, ebx; char *
0x180081910  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081917  mov     edx, 378h; void *
0x18008191c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081921  mov     eax, ebx
0x180081923  mov     rcx, [rbp+1A0h+var_20]
0x18008192a  xor     rcx, rsp; StackCookie
0x18008192d  call    __security_check_cookie
0x180081932  lea     r11, [rsp+2A0h+var_10]
0x18008193a  mov     rbx, [r11+30h]
0x18008193e  mov     rsi, [r11+38h]
0x180081942  mov     rsp, r11
0x180081945  pop     r14
0x180081947  pop     rdi
0x180081948  pop     rbp
0x180081949  retn
```
