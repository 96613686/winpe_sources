# Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x1800322f0`
- end: `0x1800327bb`
- name: `?Enumerate@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1PEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800327c4`

## callees

- `0x180002a60`
- `0x18000421c`
- `0x18000526c`
- `0x1800058fc`
- `0x1800096ec`
- `0x180023164`
- `0x1800291ec`
- `0x180029234`
- `0x180029298`
- `0x18002bb80`
- `0x18002bc20`
- `0x18002bf00`
- `0x18002d464`
- `0x18002ec84`
- `0x18002ed1c`
- `0x1800322f0`
- `0x1800349f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180032445`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180032445`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003239f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003239f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003236b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003236b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003253c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003253c`

## string_xrefs

- `0x1800323d2`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180032460`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180032557`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180032724`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x18003276e`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Enumerate(HKEY *a1, const WCHAR *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v4; // r14
  __int64 v5; // r12
  _QWORD *v8; // r15
  unsigned int v9; // edi
  LSTATUS v10; // eax
  signed int v11; // ebx
  unsigned int v12; // eax
  unsigned __int64 v13; // rax
  BYTE *v14; // rbx
  DWORD i; // esi
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int phkResult; // [rsp+20h] [rbp-118h]
  unsigned int phkResulta; // [rsp+20h] [rbp-118h]
  unsigned int phkResultb; // [rsp+20h] [rbp-118h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-D0h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-C8h] BYREF
  DWORD v27; // [rsp+74h] [rbp-C4h]
  LPWSTR lpValueName; // [rsp+78h] [rbp-C0h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+84h] [rbp-B4h] BYREF
  BYTE *v31; // [rsp+88h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+90h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+94h] [rbp-A4h] BYREF
  __int64 v34; // [rsp+98h] [rbp-A0h]
  _QWORD *v35; // [rsp+A0h] [rbp-98h]
  __int64 v36; // [rsp+B0h] [rbp-88h] BYREF
  _BYTE v37[16]; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-70h]
  _BYTE v39[16]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v40; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v34 = a3;
  v8 = a4;
  v35 = a4;
  v9 = 0;
  hKey = 0;
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(a1, *a4);
  *(_QWORD *)*v8 = *v8;
  *(_QWORD *)(*v8 + 8LL) = *v8;
  v8[1] = 0;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&lpValueName);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&lpValueName);
  }
  hKey = 0;
  v10 = RegOpenKeyExW(*a1, a2, 0, 0x20019u, &hKey);
  v11 = v10;
  if ( v10 == 2 )
    goto LABEL_28;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)(unsigned int)v11,
      phkResult);
LABEL_27:
    v9 = v11;
    goto LABEL_28;
  }
  Type = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v12 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x146,
           (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
           (const char *)v12,
           phkResulta);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  v13 = 2LL * ++cbMaxValueNameLen;
  if ( !is_mul_ok(cbMaxValueNameLen, 2u) )
    v13 = -1;
  lpValueName = (LPWSTR)operator new[](v13, (const struct std::nothrow_t *)std::nothrow);
  if ( lpValueName )
  {
    v14 = (BYTE *)operator new[](cbMaxValueLen + 2, (const struct std::nothrow_t *)std::nothrow);
    v31 = v14;
    if ( !v14 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v31);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
      goto LABEL_27;
    }
    for ( i = 0; ; ++i )
    {
      v27 = i;
      if ( i >= cValues )
        break;
      cchValueName = cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      v16 = RegEnumValueW(hKey, i, lpValueName, &cchValueName, 0, &Type, v14, &cbData);
      if ( v16 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x15D,
               (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
               (const char *)v16,
               phkResultb);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v31);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
        goto LABEL_28;
      }
      if ( Type == 1 )
      {
        if ( v5 )
        {
          try
          {
            std::wstring::wstring(v39, v14);
            std::wstring::wstring(v37, L"/");
            std::wstring::append(v37, v5);
            std::wstring::append(v37, L"/");
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
            v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
            std::search_std::_String_iterator_std::_String_val_std::_Simple_types_unsigned_short______std::_String_iterator_std::_String_val_std::_Simple_types_unsigned_short_______lambda_92ccef5a2a2a293d1ca1c69c9fcbe43c___(
              (unsigned int)&v36,
              v17,
              v17 + 2 * v40,
              v18,
              v18 + 2 * v38);
            v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
            if ( v36 != v19 + 2 * v40 )
              std::list<std::wstring>::_Emplace<std::wstring const &>(v8, *v4, v39);
            std::wstring::_Tidy_deallocate(v37);
            std::wstring::_Tidy_deallocate(v39);
          }
          catch ( ... )
          {
            v8 = v35;
            v4 = v35;
            v5 = v34;
            i = v27;
            v14 = v31;
            continue;
          }
        }
        else
        {
          try
          {
            std::wstring::wstring(v37, v14);
            std::list<std::wstring>::_Emplace<std::wstring>(v8, *v4, v37);
            std::wstring::_Tidy_deallocate(v37);
          }
          catch ( ... )
          {
            v8 = v35;
            v4 = v35;
            v5 = v34;
            i = v27;
            v14 = v31;
            continue;
          }
        }
      }
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v31);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800322f0  push    rbx
0x1800322f2  push    rsi
0x1800322f3  push    rdi
0x1800322f4  push    r12
0x1800322f6  push    r13
0x1800322f8  push    r14
0x1800322fa  push    r15
0x1800322fc  sub     rsp, 100h
0x180032303  mov     rax, cs:__security_cookie
0x18003230a  xor     rax, rsp
0x18003230d  mov     [rsp+138h+var_40], rax
0x180032315  mov     r14, r9
0x180032318  mov     r12, r8
0x18003231b  mov     r13, rdx
0x18003231e  mov     rsi, rcx
0x180032321  mov     [rsp+138h+var_A0], r8
0x180032329  mov     r15, r9
0x18003232c  mov     [rsp+138h+var_98], r9
0x180032334  xor     edi, edi
0x180032336  mov     [rsp+138h+hKey], rdi
0x18003233b  mov     rdx, [r9]
0x18003233e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180032343  mov     rax, [r15]
0x180032346  mov     [rax], rax
0x180032349  mov     rax, [r15]
0x18003234c  mov     [rax+8], rax
0x180032350  mov     [r15+8], rdi
0x180032354  mov     rbx, [rsp+138h+hKey]
0x180032359  test    rbx, rbx
0x18003235c  jz      short loc_180032381
0x18003235e  lea     rcx, [rsp+138h+lpValueName]; this
0x180032363  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032368  mov     rcx, rbx; hKey
0x18003236b  call    cs:__imp_RegCloseKey
0x180032372  nop     dword ptr [rax+rax+00h]
0x180032377  lea     rcx, [rsp+138h+lpValueName]; this
0x18003237c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180032381  mov     [rsp+138h+hKey], rdi
0x180032386  lea     rax, [rsp+138h+hKey]
0x18003238b  mov     [rsp+138h+phkResult], rax; int
0x180032390  mov     r9d, 20019h; samDesired
0x180032396  xor     r8d, r8d; ulOptions
0x180032399  mov     rdx, r13; lpSubKey
0x18003239c  mov     rcx, [rsi]; hKey
0x18003239f  call    cs:__imp_RegOpenKeyExW
0x1800323a6  nop     dword ptr [rax+rax+00h]
0x1800323ab  mov     ebx, eax
0x1800323ad  cmp     eax, 2
0x1800323b0  jz      loc_180032750
0x1800323b6  test    eax, eax
0x1800323b8  jle     short loc_1800323C3
0x1800323ba  movzx   ebx, ax
0x1800323bd  or      ebx, 80070000h
0x1800323c3  test    ebx, ebx
0x1800323c5  jns     short loc_1800323E8
0x1800323c7  mov     rcx, [rsp+138h]; this
0x1800323cf  mov     r9d, ebx; char *
0x1800323d2  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x1800323d9  mov     edx, 133h; void *
0x1800323de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323e3  jmp     loc_18003274E
0x1800323e8  mov     [rsp+138h+Type], edi
0x1800323ef  mov     [rsp+138h+cValues], edi
0x1800323f6  mov     [rsp+138h+cbMaxValueNameLen], edi
0x1800323fa  mov     [rsp+138h+cbMaxValueLen], edi
0x1800323fe  mov     [rsp+138h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180032403  mov     [rsp+138h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180032408  lea     rax, [rsp+138h+cbMaxValueLen]
0x18003240d  mov     [rsp+138h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180032412  lea     rax, [rsp+138h+cbMaxValueNameLen]
0x180032417  mov     [rsp+138h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003241c  lea     rax, [rsp+138h+cValues]
0x180032424  mov     [rsp+138h+lpcValues], rax; lpcValues
0x180032429  mov     [rsp+138h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18003242e  mov     [rsp+138h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180032433  mov     [rsp+138h+phkResult], rdi; int
0x180032438  xor     r9d, r9d; lpReserved
0x18003243b  xor     r8d, r8d; lpcchClass
0x18003243e  xor     edx, edx; lpClass
0x180032440  mov     rcx, [rsp+138h+hKey]; hKey
0x180032445  call    cs:__imp_RegQueryInfoKeyW
0x18003244c  nop     dword ptr [rax+rax+00h]
0x180032451  test    eax, eax
0x180032453  jz      short loc_180032478
0x180032455  mov     rcx, [rsp+138h]; this
0x18003245d  mov     r9d, eax; char *
0x180032460  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032467  mov     edx, 146h; void *
0x18003246c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032471  mov     edi, eax
0x180032473  jmp     loc_180032750
0x180032478  mov     eax, [rsp+138h+cbMaxValueNameLen]
0x18003247c  inc     eax
0x18003247e  mov     [rsp+138h+cbMaxValueNameLen], eax
0x180032482  mov     ecx, eax
0x180032484  mov     eax, 2
0x180032489  mul     rcx
0x18003248c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032493  cmovb   rax, rcx
0x180032497  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003249e  mov     rcx, rax; unsigned __int64
0x1800324a1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800324a6  mov     [rsp+138h+lpValueName], rax
0x1800324ab  test    rax, rax
0x1800324ae  jz      loc_18003275E
0x1800324b4  mov     ecx, [rsp+138h+cbMaxValueLen]
0x1800324b8  add     ecx, 2; unsigned __int64
0x1800324bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800324c2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800324c7  mov     rbx, rax
0x1800324ca  mov     [rsp+138h+var_B0], rax
0x1800324d2  test    rax, rax
0x1800324d5  jz      loc_180032714
0x1800324db  mov     esi, edi
0x1800324dd  mov     [rsp+138h+var_C4], esi
0x1800324e1  cmp     esi, [rsp+138h+cValues]
0x1800324e8  jnb     loc_1800326EA
0x1800324ee  mov     eax, [rsp+138h+cbMaxValueNameLen]
0x1800324f2  mov     [rsp+138h+cchValueName], eax
0x1800324f9  mov     eax, [rsp+138h+cbMaxValueLen]
0x1800324fd  mov     [rsp+138h+cbData], eax
0x180032504  lea     rax, [rsp+138h+cbData]
0x18003250c  mov     [rsp+138h+lpcValues], rax; lpcbData
0x180032511  mov     [rsp+138h+lpcbMaxClassLen], rbx; lpData
0x180032516  lea     rax, [rsp+138h+Type]
0x18003251e  mov     [rsp+138h+lpcbMaxSubKeyLen], rax; lpType
0x180032523  mov     [rsp+138h+phkResult], rdi; unsigned int
0x180032528  lea     r9, [rsp+138h+cchValueName]; lpcchValueName
0x180032530  mov     r8, [rsp+138h+lpValueName]; lpValueName
0x180032535  mov     edx, esi; dwIndex
0x180032537  mov     rcx, [rsp+138h+hKey]; hKey
0x18003253c  call    cs:__imp_RegEnumValueW
0x180032543  nop     dword ptr [rax+rax+00h]
0x180032548  test    eax, eax
0x18003254a  jz      short loc_180032587
0x18003254c  mov     rcx, [rsp+138h]; this
0x180032554  mov     r9d, eax; char *
0x180032557  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x18003255e  mov     edx, 15Dh; void *
0x180032563  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032568  mov     edi, eax
0x18003256a  lea     rcx, [rsp+138h+var_B0]
0x180032572  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180032577  nop
0x180032578  lea     rcx, [rsp+138h+lpValueName]
0x18003257d  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180032582  jmp     loc_180032750
0x180032587  cmp     [rsp+138h+Type], 1
0x18003258f  jnz     loc_1800326E3
0x180032595  test    r12, r12
0x180032598  jnz     short loc_1800325D6
0x18003259a  mov     rdx, rbx
0x18003259d  lea     rcx, [rsp+138h+var_80]
0x1800325a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800325aa  nop
0x1800325ab  lea     r8, [rsp+138h+var_80]
0x1800325b3  mov     rdx, [r14]
0x1800325b6  mov     rcx, r15
0x1800325b9  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x1800325be  nop
0x1800325bf  lea     rcx, [rsp+138h+var_80]
0x1800325c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800325cc  jmp     loc_1800326C0
0x1800325d1  jmp     loc_1800326C2
0x1800325d6  mov     rdx, rbx
0x1800325d9  lea     rcx, [rsp+138h+var_60]
0x1800325e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800325e6  nop
0x1800325e7  lea     rdx, asc_18005A070; "/"
0x1800325ee  lea     rcx, [rsp+138h+var_80]
0x1800325f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800325fb  nop
0x1800325fc  mov     rdx, r12
0x1800325ff  lea     rcx, [rsp+138h+var_80]
0x180032607  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003260c  lea     rdx, asc_18005A070; "/"
0x180032613  lea     rcx, [rsp+138h+var_80]
0x18003261b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180032620  lea     rcx, [rsp+138h+var_80]
0x180032628  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003262d  mov     r9, rax
0x180032630  lea     rcx, [rsp+138h+var_60]
0x180032638  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003263d  mov     rdx, rax
0x180032640  mov     rax, [rsp+138h+var_70]
0x180032648  lea     rcx, [r9+rax*2]
0x18003264c  mov     rax, [rsp+138h+var_50]
0x180032654  lea     r8, [rdx+rax*2]
0x180032658  mov     [rsp+138h+phkResult], rcx
0x18003265d  lea     rcx, [rsp+138h+var_88]
0x180032665  call    std__search_std___String_iterator_std___String_val_std___Simple_types_unsigned_short______std___String_iterator_std___String_val_std___Simple_types_unsigned_short_______lambda_92ccef5a2a2a293d1ca1c69c9fcbe43c___
0x18003266a  lea     rcx, [rsp+138h+var_60]
0x180032672  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032677  mov     rdx, rax
0x18003267a  mov     rax, [rsp+138h+var_50]
0x180032682  lea     rcx, [rdx+rax*2]
0x180032686  cmp     [rsp+138h+var_88], rcx
0x18003268e  jz      short loc_1800326A4
0x180032690  lea     r8, [rsp+138h+var_60]
0x180032698  mov     rdx, [r14]
0x18003269b  mov     rcx, r15
0x18003269e  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring const &>(std::_List_node<std::wstring,void *> * const,std::wstring const &)
0x1800326a3  nop
0x1800326a4  lea     rcx, [rsp+138h+var_80]
0x1800326ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800326b1  nop
0x1800326b2  lea     rcx, [rsp+138h+var_60]
0x1800326ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800326bf  nop
0x1800326c0  jmp     short loc_1800326E3
0x1800326c2  mov     r15, [rsp+138h+var_98]
0x1800326ca  mov     r14, r15
0x1800326cd  mov     r12, [rsp+138h+var_A0]
0x1800326d5  mov     esi, [rsp+138h+var_C4]
0x1800326d9  mov     rbx, [rsp+138h+var_B0]
0x1800326e1  xor     edi, edi
0x1800326e3  inc     esi
0x1800326e5  jmp     loc_1800324DD
0x1800326ea  lea     rcx, [rsp+138h+var_B0]
0x1800326f2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800326f7  nop
0x1800326f8  lea     rcx, [rsp+138h+lpValueName]
0x1800326fd  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180032702  nop
0x180032703  lea     rcx, [rsp+138h+hKey]
0x180032708  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003270d  xor     eax, eax
0x18003270f  jmp     loc_180032797
0x180032714  mov     rcx, [rsp+138h]; this
0x18003271c  mov     ebx, 8007000Eh
0x180032721  mov     r9d, ebx; char *
0x180032724  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x18003272b  mov     edx, 14Eh; void *
0x180032730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032735  nop
0x180032736  lea     rcx, [rsp+138h+var_B0]
0x18003273e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180032743  nop
0x180032744  lea     rcx, [rsp+138h+lpValueName]
0x180032749  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003274e  mov     edi, ebx
0x180032750  lea     rcx, [rsp+138h+hKey]
0x180032755  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003275a  mov     eax, edi
0x18003275c  jmp     short loc_180032797
0x18003275e  mov     rcx, [rsp+138h]; this
0x180032766  mov     ebx, 8007000Eh
0x18003276b  mov     r9d, ebx; char *
0x18003276e  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032775  mov     edx, 14Ah; void *
0x18003277a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003277f  nop
0x180032780  lea     rcx, [rsp+138h+lpValueName]
0x180032785  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003278a  nop
0x18003278b  lea     rcx, [rsp+138h+hKey]
0x180032790  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180032795  mov     eax, ebx
0x180032797  mov     rcx, [rsp+138h+var_40]
0x18003279f  xor     rcx, rsp; StackCookie
0x1800327a2  call    __security_check_cookie
0x1800327a7  add     rsp, 100h
0x1800327ae  pop     r15
0x1800327b0  pop     r14
0x1800327b2  pop     r13
0x1800327b4  pop     r12
0x1800327b6  pop     rdi
0x1800327b7  pop     rsi
0x1800327b8  pop     rbx
0x1800327b9  retn
```
