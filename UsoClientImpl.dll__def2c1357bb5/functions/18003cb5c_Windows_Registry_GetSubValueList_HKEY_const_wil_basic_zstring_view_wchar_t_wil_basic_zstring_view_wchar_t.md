# Windows::Registry::GetSubValueList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003cb5c`
- end: `0x18003d0b8`
- name: `?GetSubValueList@Registry@Windows@@QEAA?AV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x180023400`

## callees

- `0x180009380`
- `0x18002ed04`
- `0x1800338a4`
- `0x180033b00`
- `0x180034a30`
- `0x180034a70`
- `0x18003679c`
- `0x18003b68c`
- `0x18003b8e0`
- `0x18003ba50`
- `0x18003c020`
- `0x18003cb5c`
- `0x18003de3c`
- `0x180056500`
- `0x180056524`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d039`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003cc90`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003cc90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cc3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cc3d`

## string_xrefs

- `0x18003d079`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003d08e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003d0a6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall Windows::Registry::GetSubValueList(__int64 a1, __int64 *a2, __int64 a3, __int128 *a4, _OWORD *a5)
{
  __int128 *v5; // rbx
  _OWORD *v8; // rdi
  _QWORD *v9; // rax
  HKEY *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  DWORD v13; // r12d
  unsigned int v14; // eax
  __int64 v15; // r8
  int v16; // r8d
  wchar_t **v17; // rax
  __int64 inserted; // rdi
  __int64 v19; // rbx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rdx
  size_t v22; // rsi
  size_t v23; // r14
  size_t v24; // r8
  int v25; // eax
  char v26; // al
  const wchar_t *v27; // rdx
  size_t v28; // rbx
  const wchar_t *v29; // rcx
  size_t v30; // rsi
  size_t v31; // r8
  int v32; // eax
  char v33; // al
  __int64 v34; // rdi
  _DWORD *v35; // rsi
  _QWORD *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h] BYREF
  __int128 *v45; // [rsp+70h] [rbp-90h]
  _OWORD *v46; // [rsp+78h] [rbp-88h]
  __int64 *v47; // [rsp+80h] [rbp-80h]
  __int128 v48; // [rsp+90h] [rbp-70h] BYREF
  int v49[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v51; // [rsp+C0h] [rbp-40h]
  wchar_t *S2[2]; // [rsp+D0h] [rbp-30h] BYREF
  size_t N; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v54; // [rsp+E8h] [rbp-18h]
  DWORD cchValueName; // [rsp+F0h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+F8h] [rbp-8h] BYREF
  char *v57; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v58[4]; // [rsp+108h] [rbp+8h] BYREF
  char v59; // [rsp+128h] [rbp+28h]
  char v60; // [rsp+130h] [rbp+30h]
  LPCWSTR lpSubKey[5]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR ValueName[256]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v5 = a4;
  v45 = a4;
  v47 = a2;
  v8 = a5;
  v46 = a5;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  v9 = operator new(0x68u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *a2 = (__int64)v9;
  v44 = *a5;
  v43 = *v5;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v43, &v44);
  hKey = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator&(&hKey);
  v11 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v11 = lpSubKey[0];
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, v10);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v12,
      phkResult);
  v13 = 0;
  memset(ValueName, 0, sizeof(ValueName));
  while ( 1 )
  {
    cchValueName = 256;
    v14 = RegEnumValueW(hKey, v13, ValueName, &cchValueName, 0, 0, 0, 0);
    if ( v14 == 259 )
      break;
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x205,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v14,
        phkResulta);
    *(_OWORD *)S2 = 0;
    N = 0;
    v54 = 0;
    v15 = -1;
    do
      ++v15;
    while ( ValueName[v15] );
    std::wstring::_Construct<1,wchar_t const *>(S2);
    v17 = S2;
    if ( v54 > 7 )
      v17 = (wchar_t **)S2[0];
    *(_QWORD *)&v44 = v17;
    *((_QWORD *)&v44 + 1) = N;
    v48 = v44;
    *(_OWORD *)v49 = *v8;
    v50 = *v5;
    Windows::Registry::GetValue(a1, (unsigned int)&v57, v16, (unsigned int)&v50, (__int64)v49, (__int64)&v48);
    if ( (int)v57 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)(unsigned int)v57,
        phkResultb);
    inserted = *a2;
    v19 = *(_QWORD *)(*a2 + 8);
    v50 = (unsigned __int64)v19;
    while ( !*(_BYTE *)(v19 + 25) )
    {
      *(_QWORD *)&v50 = v19;
      v20 = (const wchar_t *)(v19 + 32);
      v21 = (const wchar_t *)S2;
      if ( v54 > 7 )
        v21 = S2[0];
      v22 = *(_QWORD *)(v19 + 48);
      if ( *(_QWORD *)(v19 + 56) > 7u )
        v20 = *(const wchar_t **)v20;
      v23 = N;
      v24 = *(_QWORD *)(v19 + 48);
      if ( N < v22 )
        v24 = N;
      v25 = wmemcmp(v20, v21, v24);
      if ( v25 )
      {
        if ( v25 >= 0 )
          goto LABEL_25;
      }
      else if ( v22 >= v23 )
      {
        if ( v22 <= v23 )
          goto LABEL_28;
LABEL_25:
        v26 = 1;
        goto LABEL_26;
      }
      v26 = -1;
LABEL_26:
      if ( v26 >= 0 )
      {
LABEL_28:
        DWORD2(v50) = 1;
        inserted = v19;
        v19 = *(_QWORD *)v19;
      }
      else
      {
        DWORD2(v50) = 0;
        v19 = *(_QWORD *)(v19 + 16);
      }
    }
    if ( *(_BYTE *)(inserted + 25) )
      goto LABEL_45;
    v27 = (const wchar_t *)(inserted + 32);
    v28 = *(_QWORD *)(inserted + 48);
    if ( *(_QWORD *)(inserted + 56) > 7u )
      v27 = *(const wchar_t **)v27;
    v29 = (const wchar_t *)S2;
    if ( v54 > 7 )
      v29 = S2[0];
    v30 = N;
    v31 = N;
    if ( v28 < N )
      v31 = *(_QWORD *)(inserted + 48);
    v32 = wmemcmp(v29, v27, v31);
    if ( v32 )
    {
      if ( v32 < 0 )
      {
LABEL_41:
        v33 = -1;
        goto LABEL_44;
      }
LABEL_43:
      v33 = 1;
LABEL_44:
      if ( v33 < 0 )
      {
LABEL_45:
        if ( a2[1] == 0x276276276276276LL )
          std::_Throw_tree_length_error();
        v34 = *a2;
        v43 = (unsigned __int64)a2;
        v35 = operator new(0x68u);
        *((_QWORD *)&v43 + 1) = v35;
        std::wstring::wstring(v35 + 8, S2);
        v35[16] = 0;
        *((_BYTE *)v35 + 96) = 0;
        *(_QWORD *)v35 = v34;
        *((_QWORD *)v35 + 1) = v34;
        *((_QWORD *)v35 + 2) = v34;
        *((_WORD *)v35 + 12) = 0;
        *((_QWORD *)&v43 + 1) = 0;
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(
                     a2,
                     &v50,
                     v35);
      }
    }
    else
    {
      if ( v30 < v28 )
        goto LABEL_41;
      if ( v30 > v28 )
        goto LABEL_43;
    }
    v36 = (_QWORD *)(inserted + 64);
    if ( v59 == -1 )
    {
      if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
        std::wstring::~wstring((void *)(inserted + 64));
      *(_BYTE *)(inserted + 96) = -1;
    }
    else if ( v59 )
    {
      if ( v59 == 1 )
      {
        if ( *(_BYTE *)(inserted + 96) == 1 )
        {
          *v36 = v58[0];
        }
        else
        {
          if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
            std::wstring::~wstring((void *)(inserted + 64));
          *(_BYTE *)(inserted + 96) = -1;
          *v36 = v58[0];
          *(_BYTE *)(inserted + 96) = 1;
        }
      }
      else if ( *(_BYTE *)(inserted + 96) == 2 )
      {
        std::wstring::operator=((void *)(inserted + 64));
      }
      else
      {
        std::wstring::wstring(&v50, v58);
        if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
          std::wstring::~wstring((void *)(inserted + 64));
        *(_BYTE *)(inserted + 96) = -1;
        *(_OWORD *)v36 = v50;
        *(_OWORD *)(inserted + 80) = v51;
        *(_QWORD *)&v51 = 0;
        *((_QWORD *)&v51 + 1) = 7;
        LOWORD(v50) = 0;
        std::wstring::~wstring(&v50);
        *(_BYTE *)(inserted + 96) = 2;
      }
    }
    else
    {
      v37 = *(char *)(inserted + 96);
      if ( (_BYTE)v37 )
      {
        v38 = v37 + 1;
        if ( v38 && (unsigned __int64)(v38 - 1) >= 2 )
          std::wstring::~wstring((void *)(inserted + 64));
        *(_BYTE *)(inserted + 96) = -1;
        *(_DWORD *)v36 = v58[0];
        *(_BYTE *)(inserted + 96) = 0;
      }
      else
      {
        *(_DWORD *)v36 = v58[0];
      }
    }
    if ( v60 && v59 != -1 && v59 && v59 != 1 )
      std::wstring::~wstring(v58);
    std::wstring::~wstring(S2);
    ++v13;
    memset(ValueName, 0, sizeof(ValueName));
    v5 = v45;
    v8 = v46;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x18003cb5c  mov     [rsp-8+arg_0], rbx
0x18003cb61  push    rbp
0x18003cb62  push    rsi
0x18003cb63  push    rdi
0x18003cb64  push    r12
0x18003cb66  push    r13
0x18003cb68  push    r14
0x18003cb6a  push    r15
0x18003cb6c  lea     rbp, [rsp-270h]
0x18003cb74  sub     rsp, 370h
0x18003cb7b  mov     rax, cs:__security_cookie
0x18003cb82  xor     rax, rsp
0x18003cb85  mov     [rbp+2A0h+var_40], rax
0x18003cb8c  mov     rbx, r9
0x18003cb8f  mov     [rsp+3A0h+var_330], rbx
0x18003cb94  mov     r15, rdx
0x18003cb97  mov     r13, rcx
0x18003cb9a  mov     [rbp+2A0h+var_320], rdx
0x18003cb9e  mov     rdi, [rbp+2A0h+arg_20]
0x18003cba5  mov     [rsp+3A0h+var_328], rdi
0x18003cbaa  xor     r14d, r14d
0x18003cbad  mov     [rsp+3A0h+var_360], r14d
0x18003cbb2  xorps   xmm0, xmm0
0x18003cbb5  movups  xmmword ptr [rdx], xmm0
0x18003cbb8  mov     [rdx], r14
0x18003cbbb  mov     [rdx+8], r14
0x18003cbbf  lea     ecx, [r14+68h]; Size
0x18003cbc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cbc8  mov     [rax], rax
0x18003cbcb  mov     [rax+8], rax
0x18003cbcf  mov     [rax+10h], rax
0x18003cbd3  mov     word ptr [rax+18h], 101h
0x18003cbd9  mov     [r15], rax
0x18003cbdc  mov     [rsp+3A0h+var_360], 1
0x18003cbe4  movaps  xmm0, xmmword ptr [rdi]
0x18003cbe7  movdqa  [rsp+3A0h+var_340], xmm0
0x18003cbed  movaps  xmm1, xmmword ptr [rbx]
0x18003cbf0  movdqa  [rsp+3A0h+var_350], xmm1
0x18003cbf6  lea     r9, [rsp+3A0h+var_340]
0x18003cbfb  lea     r8, [rsp+3A0h+var_350]
0x18003cc00  lea     rdx, [rbp+2A0h+lpSubKey]
0x18003cc04  mov     rcx, r13
0x18003cc07  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003cc0c  nop
0x18003cc0d  mov     [rbp+2A0h+hKey], r14
0x18003cc11  lea     rcx, [rbp+2A0h+hKey]
0x18003cc15  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator&(void)
0x18003cc1a  lea     rdx, [rbp+2A0h+lpSubKey]
0x18003cc1e  cmp     [rbp+2A0h+var_250], 7
0x18003cc23  cmova   rdx, [rbp+2A0h+lpSubKey]; lpSubKey
0x18003cc28  mov     [rsp+3A0h+phkResult], rax; unsigned int
0x18003cc2d  mov     r9d, 20019h; samDesired
0x18003cc33  xor     r8d, r8d; ulOptions
0x18003cc36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cc3d  call    cs:__imp_RegOpenKeyExW
0x18003cc43  mov     rcx, [rbp+2A8h]; this
0x18003cc4a  test    eax, eax
0x18003cc4c  jnz     loc_18003D08B
0x18003cc52  mov     r12d, r14d
0x18003cc55  xor     edx, edx; Val
0x18003cc57  mov     r8d, 200h; Size
0x18003cc5d  lea     rcx, [rbp+2A0h+ValueName]; void *
0x18003cc61  call    memset
0x18003cc66  mov     [rbp+2A0h+cchValueName], 100h
0x18003cc6d  mov     [rsp+3A0h+lpcbData], r14; lpcbData
0x18003cc72  mov     [rsp+3A0h+lpData], r14; lpData
0x18003cc77  mov     [rsp+3A0h+lpType], r14; lpType
0x18003cc7c  mov     [rsp+3A0h+phkResult], r14; unsigned int
0x18003cc81  lea     r9, [rbp+2A0h+cchValueName]; lpcchValueName
0x18003cc85  lea     r8, [rbp+2A0h+ValueName]; lpValueName
0x18003cc89  mov     edx, r12d; dwIndex
0x18003cc8c  mov     rcx, [rbp+2A0h+hKey]; hKey
0x18003cc90  call    cs:__imp_RegEnumValueW
0x18003cc96  cmp     eax, 103h
0x18003cc9b  jz      loc_18003D030
0x18003cca1  mov     rcx, [rbp+2A8h]; this
0x18003cca8  test    eax, eax
0x18003ccaa  jnz     loc_18003D076
0x18003ccb0  xorps   xmm0, xmm0
0x18003ccb3  movups  xmmword ptr [rbp+2A0h+S2], xmm0
0x18003ccb7  mov     [rbp+2A0h+N], r14
0x18003ccbb  mov     [rbp+2A0h+var_2B8], r14
0x18003ccbf  lea     rax, [rbp+2A0h+ValueName]
0x18003ccc3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ccc7  inc     r8
0x18003ccca  cmp     [rax+r8*2], r14w
0x18003cccf  jnz     short loc_18003CCC7
0x18003ccd1  lea     rdx, [rbp+2A0h+ValueName]
0x18003ccd5  lea     rcx, [rbp+2A0h+S2]
0x18003ccd9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003ccde  nop
0x18003ccdf  lea     rax, [rbp+2A0h+S2]
0x18003cce3  cmp     [rbp+2A0h+var_2B8], 7
0x18003cce8  cmova   rax, [rbp+2A0h+S2]
0x18003cced  mov     qword ptr [rsp+3A0h+var_340], rax
0x18003ccf2  mov     rax, [rbp+2A0h+N]
0x18003ccf6  mov     qword ptr [rsp+3A0h+var_340+8], rax
0x18003ccfb  movaps  xmm0, [rsp+3A0h+var_340]
0x18003cd00  movdqa  [rbp+2A0h+var_310], xmm0
0x18003cd05  movaps  xmm1, xmmword ptr [rdi]
0x18003cd08  movdqa  xmmword ptr [rbp+2A0h+var_300], xmm1
0x18003cd0d  movaps  xmm0, xmmword ptr [rbx]
0x18003cd10  movdqa  [rbp+2A0h+var_2F0], xmm0
0x18003cd15  lea     rax, [rbp+2A0h+var_310]
0x18003cd19  mov     [rsp+3A0h+lpType], rax
0x18003cd1e  lea     rax, [rbp+2A0h+var_300]
0x18003cd22  mov     [rsp+3A0h+phkResult], rax; int
0x18003cd27  lea     r9, [rbp+2A0h+var_2F0]
0x18003cd2b  lea     rdx, [rbp+2A0h+var_2A0]
0x18003cd2f  mov     rcx, r13
0x18003cd32  call    ?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z; Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003cd37  nop
0x18003cd38  mov     rcx, [rbp+2A8h]; this
0x18003cd3f  mov     r9d, dword ptr [rbp+2A0h+var_2A0]; char *
0x18003cd43  test    r9d, r9d
0x18003cd46  js      loc_18003D0A6
0x18003cd4c  mov     rdi, [r15]
0x18003cd4f  mov     rbx, [rdi+8]
0x18003cd53  mov     qword ptr [rbp+2A0h+var_2F0], rbx
0x18003cd57  mov     qword ptr [rbp+2A0h+var_2F0+8], 0
0x18003cd5f  jmp     short loc_18003CDD6
0x18003cd61  mov     qword ptr [rbp+2A0h+var_2F0], rbx
0x18003cd65  lea     rcx, [rbx+20h]
0x18003cd69  lea     rdx, [rbp+2A0h+S2]
0x18003cd6d  cmp     [rbp+2A0h+var_2B8], 7
0x18003cd72  cmova   rdx, [rbp+2A0h+S2]; S2
0x18003cd77  mov     rsi, [rcx+10h]
0x18003cd7b  cmp     qword ptr [rcx+18h], 7
0x18003cd80  jbe     short loc_18003CD85
0x18003cd82  mov     rcx, [rcx]; S1
0x18003cd85  mov     r14, [rbp+2A0h+N]
0x18003cd89  mov     r8, rsi
0x18003cd8c  cmp     r14, rsi
0x18003cd8f  cmovb   r8, r14; N
0x18003cd93  call    wmemcmp
0x18003cd98  test    eax, eax
0x18003cd9a  jz      short loc_18003CDA5
0x18003cd9c  xor     r14d, r14d
0x18003cd9f  test    eax, eax
0x18003cda1  jns     short loc_18003CDB6
0x18003cda3  jmp     short loc_18003CDAD
0x18003cda5  cmp     rsi, r14
0x18003cda8  jnb     short loc_18003CDB1
0x18003cdaa  xor     r14d, r14d
0x18003cdad  mov     al, 0FFh
0x18003cdaf  jmp     short loc_18003CDB8
0x18003cdb1  jbe     short loc_18003CDC6
0x18003cdb3  xor     r14d, r14d
0x18003cdb6  mov     al, 1
0x18003cdb8  test    al, al
0x18003cdba  jns     short loc_18003CDC9
0x18003cdbc  mov     dword ptr [rbp+2A0h+var_2F0+8], r14d
0x18003cdc0  mov     rbx, [rbx+10h]
0x18003cdc4  jmp     short loc_18003CDD6
0x18003cdc6  xor     r14d, r14d
0x18003cdc9  mov     dword ptr [rbp+2A0h+var_2F0+8], 1
0x18003cdd0  mov     rdi, rbx
0x18003cdd3  mov     rbx, [rbx]
0x18003cdd6  cmp     [rbx+19h], r14b
0x18003cdda  jz      short loc_18003CD61
0x18003cddc  cmp     [rdi+19h], r14b
0x18003cde0  jnz     short loc_18003CE2E
0x18003cde2  lea     rdx, [rdi+20h]
0x18003cde6  mov     rbx, [rdx+10h]
0x18003cdea  cmp     qword ptr [rdx+18h], 7
0x18003cdef  jbe     short loc_18003CDF4
0x18003cdf1  mov     rdx, [rdx]; S2
0x18003cdf4  lea     rcx, [rbp+2A0h+S2]
0x18003cdf8  cmp     [rbp+2A0h+var_2B8], 7
0x18003cdfd  cmova   rcx, [rbp+2A0h+S2]; S1
0x18003ce02  mov     rsi, [rbp+2A0h+N]
0x18003ce06  mov     r8, rsi
0x18003ce09  cmp     rbx, rsi
0x18003ce0c  cmovb   r8, rbx; N
0x18003ce10  call    wmemcmp
0x18003ce15  test    eax, eax
0x18003ce17  jz      short loc_18003CE1D
0x18003ce19  jns     short loc_18003CE28
0x18003ce1b  jmp     short loc_18003CE22
0x18003ce1d  cmp     rsi, rbx
0x18003ce20  jnb     short loc_18003CE26
0x18003ce22  mov     al, 0FFh
0x18003ce24  jmp     short loc_18003CE2A
0x18003ce26  jbe     short loc_18003CEA7
0x18003ce28  mov     al, 1
0x18003ce2a  test    al, al
0x18003ce2c  jns     short loc_18003CEA7
0x18003ce2e  mov     rax, 276276276276276h
0x18003ce38  cmp     [r15+8], rax
0x18003ce3c  jz      loc_18003D0A0
0x18003ce42  mov     rdi, [r15]
0x18003ce45  mov     qword ptr [rsp+3A0h+var_350], r15
0x18003ce4a  mov     qword ptr [rsp+3A0h+var_350+8], r14
0x18003ce4f  mov     ecx, 68h ; 'h'; Size
0x18003ce54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ce59  mov     rsi, rax
0x18003ce5c  mov     qword ptr [rsp+3A0h+var_350+8], rax
0x18003ce61  lea     rdx, [rbp+2A0h+S2]
0x18003ce65  lea     rcx, [rax+20h]
0x18003ce69  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ce6e  mov     [rsi+40h], r14d
0x18003ce72  mov     [rsi+60h], r14b
0x18003ce76  mov     [rsi], rdi
0x18003ce79  mov     [rsi+8], rdi
0x18003ce7d  mov     [rsi+10h], rdi
0x18003ce81  mov     word ptr [rsi+18h], 0
0x18003ce87  mov     qword ptr [rsp+3A0h+var_350+8], r14
0x18003ce8c  movups  xmm0, [rbp+2A0h+var_2F0]
0x18003ce90  movdqu  [rbp+2A0h+var_2F0], xmm0
0x18003ce95  mov     r8, rsi
0x18003ce98  lea     rdx, [rbp+2A0h+var_2F0]
0x18003ce9c  mov     rcx, r15
0x18003ce9f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@U12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@U12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@U12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<winrt::hstring const,winrt::hstring>,void *> *>,std::_Tree_node<std::pair<winrt::hstring const,winrt::hstring>,void *> * const)
0x18003cea4  mov     rdi, rax
0x18003cea7  lea     rbx, [rdi+40h]
0x18003ceab  movsx   rax, [rbp+2A0h+var_278]
0x18003ceb0  add     rax, 1
0x18003ceb4  jz      loc_18003CFBA
0x18003ceba  sub     rax, 1
0x18003cebe  jz      loc_18003CF81
0x18003cec4  cmp     rax, 1
0x18003cec8  jz      short loc_18003CF3F
0x18003ceca  lea     rdx, [rbp+2A0h+var_298]
0x18003cece  cmp     byte ptr [rbx+20h], 2
0x18003ced2  jnz     short loc_18003CEE1
0x18003ced4  mov     rcx, rbx; void *
0x18003ced7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003cedc  jmp     loc_18003CFDD
0x18003cee1  lea     rcx, [rbp+2A0h+var_2F0]
0x18003cee5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ceea  movsx   rax, byte ptr [rbx+20h]
0x18003ceef  add     rax, 1
0x18003cef3  jz      short loc_18003CF09
0x18003cef5  sub     rax, 1
0x18003cef9  jz      short loc_18003CF09
0x18003cefb  cmp     rax, 1
0x18003ceff  jz      short loc_18003CF09
0x18003cf01  mov     rcx, rbx; void *
0x18003cf04  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cf09  mov     byte ptr [rbx+20h], 0FFh
0x18003cf0d  movups  xmm0, [rbp+2A0h+var_2F0]
0x18003cf11  movups  xmmword ptr [rbx], xmm0
0x18003cf14  movups  xmm1, [rbp+2A0h+var_2E0]
0x18003cf18  movups  xmmword ptr [rbx+10h], xmm1
0x18003cf1c  mov     qword ptr [rbp+2A0h+var_2E0], r14
0x18003cf20  mov     qword ptr [rbp+2A0h+var_2E0+8], 7
0x18003cf28  mov     word ptr [rbp+2A0h+var_2F0], r14w
0x18003cf2d  lea     rcx, [rbp+2A0h+var_2F0]; void *
0x18003cf31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cf36  mov     byte ptr [rbx+20h], 2
0x18003cf3a  jmp     loc_18003CFDD
0x18003cf3f  cmp     byte ptr [rbx+20h], 1
0x18003cf43  jnz     short loc_18003CF51
0x18003cf45  mov     rax, [rbp+2A0h+var_298]
0x18003cf49  mov     [rbx], rax
0x18003cf4c  jmp     loc_18003CFDD
0x18003cf51  movsx   rax, byte ptr [rbx+20h]
0x18003cf56  add     rax, 1
0x18003cf5a  jz      short loc_18003CF70
0x18003cf5c  sub     rax, 1
0x18003cf60  jz      short loc_18003CF70
0x18003cf62  cmp     rax, 1
0x18003cf66  jz      short loc_18003CF70
0x18003cf68  mov     rcx, rbx; void *
0x18003cf6b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cf70  mov     byte ptr [rbx+20h], 0FFh
0x18003cf74  mov     rax, [rbp+2A0h+var_298]
0x18003cf78  mov     [rbx], rax
0x18003cf7b  mov     byte ptr [rbx+20h], 1
0x18003cf7f  jmp     short loc_18003CFDD
0x18003cf81  movsx   rax, byte ptr [rbx+20h]
0x18003cf86  test    al, al
0x18003cf88  jnz     short loc_18003CF91
0x18003cf8a  mov     eax, dword ptr [rbp+2A0h+var_298]
0x18003cf8d  mov     [rbx], eax
0x18003cf8f  jmp     short loc_18003CFDD
0x18003cf91  add     rax, 1
0x18003cf95  jz      short loc_18003CFAB
0x18003cf97  sub     rax, 1
0x18003cf9b  jz      short loc_18003CFAB
0x18003cf9d  cmp     rax, 1
0x18003cfa1  jz      short loc_18003CFAB
0x18003cfa3  mov     rcx, rbx; void *
0x18003cfa6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cfab  mov     byte ptr [rbx+20h], 0FFh
0x18003cfaf  mov     eax, dword ptr [rbp+2A0h+var_298]
0x18003cfb2  mov     [rbx], eax
0x18003cfb4  mov     [rbx+20h], r14b
0x18003cfb8  jmp     short loc_18003CFDD
0x18003cfba  movsx   rax, byte ptr [rbx+20h]
0x18003cfbf  add     rax, 1
0x18003cfc3  jz      short loc_18003CFD9
0x18003cfc5  sub     rax, 1
0x18003cfc9  jz      short loc_18003CFD9
0x18003cfcb  cmp     rax, 1
0x18003cfcf  jz      short loc_18003CFD9
0x18003cfd1  mov     rcx, rbx; void *
0x18003cfd4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cfd9  mov     byte ptr [rbx+20h], 0FFh
0x18003cfdd  cmp     [rbp+2A0h+var_270], r14b
  ... truncated ...
```
