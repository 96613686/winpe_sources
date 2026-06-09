# EnumerateUninstalledUpdates(void)

- ea: `0x180047ab0`
- end: `0x180047f31`
- name: `?EnumerateUninstalledUpdates@@YAJXZ`
- size: `1153`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180048408`

## callees

- `0x180007660`
- `0x180007dc0`
- `0x18000856c`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800473a8`
- `0x180047404`
- `0x180047510`
- `0x180047ab0`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180047e8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047d74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047db3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047d74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047db3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047ccf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047ccf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180047d2e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180047d2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047edf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047edf`

## string_xrefs

- `0x180047c0a`: `SOFTWARE\MICROSOFT\WINDOWS\CURRENTVERSION\WINDOWSUPDATE\WINREUNINSTALLLIST`
- `0x180047d64`: `UpdateType`
- `0x180047da3`: `UninstallTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 EnumerateUninstalledUpdates(void)
{
  _QWORD *v0; // rdi
  char *v1; // rsi
  char *v2; // rbx
  _QWORD *v3; // rdi
  char *v4; // rsi
  char *v5; // rbx
  LSTATUS v6; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  LSTATUS v10; // eax
  DWORD v11; // edi
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS ValueW; // eax
  LSTATUS v15; // eax
  bool v16; // sf
  __int64 v17; // r8
  __int64 v18; // rcx
  __int128 *v19; // rcx
  __int64 v20; // r8
  __int128 *v21; // r14
  __int128 *v22; // rcx
  unsigned __int16 *v23; // rbx
  unsigned __int16 *v24; // rsi
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int pvData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxClassLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchClass; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-68h] BYREF
  HKEY *p_hKey; // [rsp+A0h] [rbp-60h]
  char v40; // [rsp+A8h] [rbp-58h]
  _BYTE v41[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v43; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v45; // [rsp+E8h] [rbp-18h]
  __int128 v46; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  WCHAR Name[256]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Class[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  hKey = 0;
  cchName = 0;
  memset_0(Class, 0, 0x208u);
  cchClass = 260;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  pvData = 0;
  pcbData = 4;
  v0 = (_QWORD *)qword_180096890;
  v1 = *(char **)(qword_180096890 + 8);
  while ( !v1[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      &qword_180096890,
      &qword_180096890,
      *((_QWORD *)v1 + 2));
    v2 = v1;
    v1 = *(char **)v1;
    std::wstring::_Tidy_deallocate(v2 + 32);
    operator delete(v2);
  }
  v0[1] = v0;
  *v0 = v0;
  v0[2] = v0;
  qword_180096898 = 0;
  v3 = (_QWORD *)qword_1800968A0;
  v4 = *(char **)(qword_1800968A0 + 8);
  while ( !v4[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      &qword_1800968A0,
      &qword_1800968A0,
      *((_QWORD *)v4 + 2));
    v5 = v4;
    v4 = *(char **)v4;
    std::wstring::_Tidy_deallocate(v5 + 32);
    operator delete(v5);
  }
  v3[1] = v3;
  *v3 = v3;
  v3[2] = v3;
  qword_1800968A8 = 0;
  byte_180095D80 = 0;
  p_hKey = &hKey;
  v40 = 1;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\MICROSOFT\\WINDOWS\\CURRENTVERSION\\WINDOWSUPDATE\\WINREUNINSTALLLIST",
         0,
         0xF003Fu,
         &hKey);
  v7 = v6;
  if ( v6 == 2 )
    goto LABEL_52;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 168;
    goto LABEL_12;
  }
  v10 = RegQueryInfoKeyW(
          hKey,
          Class,
          &cchClass,
          0,
          &cSubKeys,
          &cbMaxSubKeyLen,
          &cbMaxClassLen,
          &cValues,
          &cbMaxValueNameLen,
          &cbMaxValueLen,
          &cbSecurityDescriptor,
          &ftLastWriteTime);
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 182;
    goto LABEL_12;
  }
  if ( !cSubKeys )
  {
LABEL_51:
    byte_180095D80 = 1;
LABEL_52:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v11 = 0;
  while ( 1 )
  {
    cchName = 255;
    v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    v13 = v12 < 0;
    if ( v12 > 0 )
      v13 = 1;
    if ( v13 )
      goto LABEL_50;
    ValueW = RegGetValueW(hKey, Name, L"UpdateType", 0x18u, 0, &pvData, &pcbData);
    v7 = ValueW;
    if ( ValueW > 0 )
      v7 = (unsigned __int16)ValueW | 0x80070000;
    if ( v7 == -2147024894 )
    {
      v15 = RegGetValueW(hKey, Name, L"UninstallTimestamp", 2u, 0, 0, 0);
      v16 = v15 < 0;
      if ( v15 > 0 )
        v16 = 1;
      if ( v16 )
      {
        v7 = -2147418113;
        v8 = 224;
        goto LABEL_12;
      }
      pvData = 0;
      goto LABEL_33;
    }
    if ( v7 < 0 )
      break;
    if ( pvData )
    {
      if ( pvData != 1 )
      {
        v7 = -2147467263;
        v8 = 244;
        goto LABEL_12;
      }
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v20 = -1;
      do
        ++v20;
      while ( Name[v20] );
      std::wstring::_Construct<1,unsigned short const *>(&v43, Name);
      v21 = &v43;
      if ( v45 > 7 )
        v21 = (__int128 *)v43;
      v22 = &v43;
      if ( v45 > 7 )
        v22 = (__int128 *)v43;
      v23 = (unsigned __int16 *)v22 + v44;
      v24 = (unsigned __int16 *)&v43;
      if ( v45 > 7 )
        v24 = (unsigned __int16 *)v43;
      while ( v24 != v23 )
      {
        *(_WORD *)v21 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v24);
        v21 = (__int128 *)((char *)v21 + 2);
        ++v24;
      }
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        v22,
        v42,
        &v43);
      v19 = &v43;
      goto LABEL_49;
    }
LABEL_33:
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v17 = -1;
    do
      ++v17;
    while ( Name[v17] );
    std::wstring::_Construct<1,unsigned short const *>(&v46, Name);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v18,
      v41,
      &v46);
    v19 = &v46;
LABEL_49:
    std::wstring::_Tidy_deallocate(v19);
LABEL_50:
    if ( ++v11 >= cSubKeys )
      goto LABEL_51;
  }
  v8 = 229;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
    (const char *)(unsigned int)v7,
    phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047ab0  push    rbp
0x180047ab2  push    rbx
0x180047ab3  push    rsi
0x180047ab4  push    rdi
0x180047ab5  push    r12
0x180047ab7  push    r14
0x180047ab9  push    r15
0x180047abb  lea     rbp, [rsp-430h]
0x180047ac3  sub     rsp, 530h
0x180047aca  mov     rax, cs:__security_cookie
0x180047ad1  xor     rax, rsp
0x180047ad4  mov     [rbp+460h+var_40], rax
0x180047adb  xor     r15d, r15d
0x180047ade  mov     [rsp+560h+hKey], r15
0x180047ae3  mov     [rsp+560h+cchName], r15d
0x180047ae8  xor     edx, edx; Val
0x180047aea  mov     r8d, 208h; Size
0x180047af0  lea     rcx, [rbp+460h+Class]; void *
0x180047af7  call    memset_0
0x180047afc  mov     [rbp+460h+cchClass], 104h
0x180047b03  mov     [rsp+560h+cSubKeys], r15d
0x180047b08  mov     [rbp+460h+cbMaxSubKeyLen], r15d
0x180047b0c  mov     [rbp+460h+cbMaxClassLen], r15d
0x180047b10  mov     [rbp+460h+cValues], r15d
0x180047b14  mov     [rsp+560h+cbMaxValueNameLen], r15d
0x180047b19  mov     [rsp+560h+cbMaxValueLen], r15d
0x180047b1e  mov     [rsp+560h+cbSecurityDescriptor], r15d
0x180047b23  mov     qword ptr [rbp+460h+ftLastWriteTime.dwLowDateTime], r15
0x180047b27  mov     [rsp+560h+pvData], r15d
0x180047b2c  mov     [rbp+460h+pcbData], 4
0x180047b33  mov     rdi, cs:qword_180096890
0x180047b3a  mov     rsi, [rdi+8]
0x180047b3e  lea     r14d, [r15+40h]
0x180047b42  jmp     short loc_180047B75
0x180047b44  mov     r8, [rsi+10h]
0x180047b48  lea     rdx, qword_180096890
0x180047b4f  lea     rcx, qword_180096890
0x180047b56  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::_Tree_node<std::wstring,void *> *)
0x180047b5b  mov     rbx, rsi
0x180047b5e  mov     rsi, [rsi]
0x180047b61  lea     rcx, [rbx+20h]
0x180047b65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047b6a  mov     rdx, r14
0x180047b6d  mov     rcx, rbx; Block
0x180047b70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047b75  cmp     [rsi+19h], r15b
0x180047b79  jz      short loc_180047B44
0x180047b7b  mov     [rdi+8], rdi
0x180047b7f  mov     [rdi], rdi
0x180047b82  mov     [rdi+10h], rdi
0x180047b86  mov     cs:qword_180096898, r15
0x180047b8d  mov     rdi, cs:qword_1800968A0
0x180047b94  mov     rsi, [rdi+8]
0x180047b98  jmp     short loc_180047BCB
0x180047b9a  mov     r8, [rsi+10h]
0x180047b9e  lea     rdx, qword_1800968A0
0x180047ba5  lea     rcx, qword_1800968A0
0x180047bac  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::_Tree_node<std::wstring,void *> *)
0x180047bb1  mov     rbx, rsi
0x180047bb4  mov     rsi, [rsi]
0x180047bb7  lea     rcx, [rbx+20h]
0x180047bbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047bc0  mov     rdx, r14
0x180047bc3  mov     rcx, rbx; Block
0x180047bc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047bcb  cmp     [rsi+19h], r15b
0x180047bcf  jz      short loc_180047B9A
0x180047bd1  mov     [rdi+8], rdi
0x180047bd5  mov     [rdi], rdi
0x180047bd8  mov     [rdi+10h], rdi
0x180047bdc  mov     cs:qword_1800968A8, r15
0x180047be3  mov     cs:byte_180095D80, r15b
0x180047bea  lea     rax, [rsp+560h+hKey]
0x180047bef  mov     [rbp+460h+var_4C0], rax
0x180047bf3  mov     [rbp+460h+var_4B8], 1
0x180047bf7  lea     rax, [rsp+560h+hKey]
0x180047bfc  mov     [rsp+560h+phkResult], rax; int
0x180047c01  mov     r9d, 0F003Fh; samDesired
0x180047c07  xor     r8d, r8d; ulOptions
0x180047c0a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\MICROSOFT\\WINDOWS\\CURRENTVE"...
0x180047c11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047c18  call    cs:__imp_RegOpenKeyExW
0x180047c1e  mov     ebx, eax
0x180047c20  cmp     eax, 2
0x180047c23  jz      loc_180047ED5
0x180047c29  mov     r12d, 80070000h
0x180047c2f  test    eax, eax
0x180047c31  jle     short loc_180047C39
0x180047c33  movzx   ebx, ax
0x180047c36  or      ebx, r12d
0x180047c39  test    ebx, ebx
0x180047c3b  jns     short loc_180047C70
0x180047c3d  mov     edx, 0A8h; void *
0x180047c42  mov     rcx, [rbp+468h]; this
0x180047c49  mov     r9d, ebx; char *
0x180047c4c  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x180047c53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c58  nop
0x180047c59  mov     rcx, [rsp+560h+hKey]; hKey
0x180047c5e  test    rcx, rcx
0x180047c61  jz      short loc_180047C69
0x180047c63  call    cs:__imp_RegCloseKey
0x180047c69  mov     eax, ebx
0x180047c6b  jmp     loc_180047EE7
0x180047c70  lea     rax, [rbp+460h+ftLastWriteTime]
0x180047c74  mov     [rsp+560h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180047c79  lea     rax, [rsp+560h+cbSecurityDescriptor]
0x180047c7e  mov     [rsp+560h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180047c83  lea     rax, [rsp+560h+cbMaxValueLen]
0x180047c88  mov     [rsp+560h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180047c8d  lea     rax, [rsp+560h+cbMaxValueNameLen]
0x180047c92  mov     [rsp+560h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180047c97  lea     rax, [rbp+460h+cValues]
0x180047c9b  mov     [rsp+560h+lpcValues], rax; lpcValues
0x180047ca0  lea     rax, [rbp+460h+cbMaxClassLen]
0x180047ca4  mov     [rsp+560h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x180047ca9  lea     rax, [rbp+460h+cbMaxSubKeyLen]
0x180047cad  mov     [rsp+560h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180047cb2  lea     rax, [rsp+560h+cSubKeys]
0x180047cb7  mov     [rsp+560h+phkResult], rax; lpcSubKeys
0x180047cbc  xor     r9d, r9d; lpReserved
0x180047cbf  lea     r8, [rbp+460h+cchClass]; lpcchClass
0x180047cc3  lea     rdx, [rbp+460h+Class]; lpClass
0x180047cca  mov     rcx, [rsp+560h+hKey]; hKey
0x180047ccf  call    cs:__imp_RegQueryInfoKeyW
0x180047cd5  mov     ebx, eax
0x180047cd7  test    eax, eax
0x180047cd9  jle     short loc_180047CE1
0x180047cdb  movzx   ebx, ax
0x180047cde  or      ebx, r12d
0x180047ce1  test    ebx, ebx
0x180047ce3  jns     short loc_180047CEF
0x180047ce5  mov     edx, 0B6h
0x180047cea  jmp     loc_180047C42
0x180047cef  mov     eax, [rsp+560h+cSubKeys]
0x180047cf3  test    eax, eax
0x180047cf5  jz      loc_180047ECE
0x180047cfb  mov     edi, r15d
0x180047cfe  mov     [rsp+560h+cchName], 0FFh
0x180047d06  lea     rax, [rbp+460h+ftLastWriteTime]
0x180047d0a  mov     [rsp+560h+lpcValues], rax; lpftLastWriteTime
0x180047d0f  mov     [rsp+560h+lpcbMaxClassLen], r15; lpcchClass
0x180047d14  mov     [rsp+560h+lpcbMaxSubKeyLen], r15; lpClass
0x180047d19  mov     [rsp+560h+phkResult], r15; lpReserved
0x180047d1e  lea     r9, [rsp+560h+cchName]; lpcchName
0x180047d23  lea     r8, [rbp+460h+Name]; lpName
0x180047d27  mov     edx, edi; dwIndex
0x180047d29  mov     rcx, [rsp+560h+hKey]; hKey
0x180047d2e  call    cs:__imp_RegEnumKeyExW
0x180047d34  test    eax, eax
0x180047d36  jle     short loc_180047D40
0x180047d38  movzx   eax, ax
0x180047d3b  or      eax, r12d
0x180047d3e  test    eax, eax
0x180047d40  js      loc_180047EC2
0x180047d46  lea     rax, [rbp+460h+pcbData]
0x180047d4a  mov     [rsp+560h+lpcbMaxClassLen], rax; pcbData
0x180047d4f  lea     rax, [rsp+560h+pvData]
0x180047d54  mov     [rsp+560h+lpcbMaxSubKeyLen], rax; pvData
0x180047d59  mov     [rsp+560h+phkResult], r15; pdwType
0x180047d5e  mov     r9d, 18h; dwFlags
0x180047d64  lea     r8, aUpdatetype; "UpdateType"
0x180047d6b  lea     rdx, [rbp+460h+Name]; lpSubKey
0x180047d6f  mov     rcx, [rsp+560h+hKey]; hkey
0x180047d74  call    cs:__imp_RegGetValueW
0x180047d7a  mov     ebx, eax
0x180047d7c  test    eax, eax
0x180047d7e  jle     short loc_180047D86
0x180047d80  movzx   ebx, ax
0x180047d83  or      ebx, r12d
0x180047d86  cmp     ebx, 80070002h
0x180047d8c  jnz     short loc_180047DD2
0x180047d8e  mov     [rsp+560h+lpcbMaxClassLen], r15; pcbData
0x180047d93  mov     [rsp+560h+lpcbMaxSubKeyLen], r15; pvData
0x180047d98  mov     [rsp+560h+phkResult], r15; pdwType
0x180047d9d  mov     r9d, 2; dwFlags
0x180047da3  lea     r8, aUninstalltimes; "UninstallTimestamp"
0x180047daa  lea     rdx, [rbp+460h+Name]; lpSubKey
0x180047dae  mov     rcx, [rsp+560h+hKey]; hkey
0x180047db3  call    cs:__imp_RegGetValueW
0x180047db9  test    eax, eax
0x180047dbb  jle     short loc_180047DC5
0x180047dbd  movzx   eax, ax
0x180047dc0  or      eax, r12d
0x180047dc3  test    eax, eax
0x180047dc5  js      loc_180047F08
0x180047dcb  mov     [rsp+560h+pvData], r15d
0x180047dd0  jmp     short loc_180047DE2
0x180047dd2  test    ebx, ebx
0x180047dd4  js      loc_180047F26
0x180047dda  mov     eax, [rsp+560h+pvData]
0x180047dde  test    eax, eax
0x180047de0  jnz     short loc_180047E28
0x180047de2  xorps   xmm0, xmm0
0x180047de5  movups  [rbp+460h+var_470], xmm0
0x180047de9  mov     [rbp+460h+var_460], r15
0x180047ded  mov     [rbp+460h+var_458], r15
0x180047df1  lea     rax, [rbp+460h+Name]
0x180047df5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180047df9  inc     r8
0x180047dfc  cmp     [rax+r8*2], r15w
0x180047e01  jnz     short loc_180047DF9
0x180047e03  lea     rdx, [rbp+460h+Name]
0x180047e07  lea     rcx, [rbp+460h+var_470]
0x180047e0b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180047e10  nop
0x180047e11  lea     r8, [rbp+460h+var_470]
0x180047e15  lea     rdx, [rbp+460h+var_4B0]
0x180047e19  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180047e1e  nop
0x180047e1f  lea     rcx, [rbp+460h+var_470]
0x180047e23  jmp     loc_180047EBD
0x180047e28  cmp     eax, 1
0x180047e2b  jnz     loc_180047F17
0x180047e31  xorps   xmm0, xmm0
0x180047e34  movups  [rbp+460h+var_490], xmm0
0x180047e38  mov     [rbp+460h+var_480], r15
0x180047e3c  mov     [rbp+460h+var_478], r15
0x180047e40  lea     rax, [rbp+460h+Name]
0x180047e44  or      r8, 0FFFFFFFFFFFFFFFFh
0x180047e48  inc     r8
0x180047e4b  cmp     [rax+r8*2], r15w
0x180047e50  jnz     short loc_180047E48
0x180047e52  lea     rdx, [rbp+460h+Name]
0x180047e56  lea     rcx, [rbp+460h+var_490]
0x180047e5a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180047e5f  nop
0x180047e60  lea     r14, [rbp+460h+var_490]
0x180047e64  mov     r8, qword ptr [rbp+460h+var_490]
0x180047e68  cmp     [rbp+460h+var_478], 7
0x180047e6d  cmova   r14, r8
0x180047e71  lea     rcx, [rbp+460h+var_490]
0x180047e75  cmova   rcx, r8
0x180047e79  mov     rax, [rbp+460h+var_480]
0x180047e7d  lea     rbx, [rcx+rax*2]
0x180047e81  lea     rsi, [rbp+460h+var_490]
0x180047e85  cmova   rsi, r8
0x180047e89  jmp     short loc_180047EA6
0x180047e8b  movzx   ecx, word ptr [rsi]
0x180047e8e  mov     rax, cs:__imp__o_towlower
0x180047e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e9a  mov     [r14], ax
0x180047e9e  lea     r14, [r14+2]
0x180047ea2  add     rsi, 2
0x180047ea6  cmp     rsi, rbx
0x180047ea9  jnz     short loc_180047E8B
0x180047eab  lea     r8, [rbp+460h+var_490]
0x180047eaf  lea     rdx, [rbp+460h+var_4A0]
0x180047eb3  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x180047eb8  nop
0x180047eb9  lea     rcx, [rbp+460h+var_490]
0x180047ebd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047ec2  inc     edi
0x180047ec4  cmp     edi, [rsp+560h+cSubKeys]
0x180047ec8  jb      loc_180047CFE
0x180047ece  mov     cs:byte_180095D80, 1
0x180047ed5  mov     rcx, [rsp+560h+hKey]; hKey
0x180047eda  test    rcx, rcx
0x180047edd  jz      short loc_180047EE5
0x180047edf  call    cs:__imp_RegCloseKey
0x180047ee5  xor     eax, eax
0x180047ee7  mov     rcx, [rbp+460h+var_40]
0x180047eee  xor     rcx, rsp; StackCookie
0x180047ef1  call    __security_check_cookie
0x180047ef6  add     rsp, 530h
0x180047efd  pop     r15
0x180047eff  pop     r14
0x180047f01  pop     r12
0x180047f03  pop     rdi
0x180047f04  pop     rsi
0x180047f05  pop     rbx
0x180047f06  pop     rbp
0x180047f07  retn
0x180047f08  mov     ebx, 8000FFFFh
0x180047f0d  mov     edx, 0E0h
0x180047f12  jmp     loc_180047C42
0x180047f17  mov     ebx, 80004001h
0x180047f1c  mov     edx, 0F4h
0x180047f21  jmp     loc_180047C42
0x180047f26  mov     edx, 0E5h
0x180047f2b  jmp     loc_180047C42
```
