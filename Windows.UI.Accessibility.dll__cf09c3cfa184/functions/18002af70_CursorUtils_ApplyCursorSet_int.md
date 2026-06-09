# CursorUtils::ApplyCursorSet(int)

- ea: `0x18002af70`
- end: `0x18002b1d9`
- name: `?ApplyCursorSet@CursorUtils@@CAXH@Z`
- size: `617`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b1e0`

## callees

- `0x180003980`
- `0x18000ea34`
- `0x180010dec`
- `0x1800126e4`
- `0x1800166d4`
- `0x180028fc0`
- `0x18002a130`
- `0x18002a96c`
- `0x18002aeb8`
- `0x18002af70`
- `0x18002b67c`
- `0x18002c4f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002afc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aff7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002afc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aff7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b102`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b102`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002b149`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002b165`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002b149`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002b165`

## string_xrefs

- `0x18002b19a`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002b1b2`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002b1c4`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002afb5`: `Software\Microsoft\Accessibility\CursorCustomizedStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CursorUtils::ApplyCursorSet(int a1)
{
  void *v1; // rdi
  unsigned int v2; // eax
  unsigned __int64 v3; // rdx
  LPCWSTR *v4; // rbx
  __int64 v5; // rdx
  unsigned __int16 *v6; // rax
  int v7; // r8d
  int v8; // edx
  __int64 v9; // rax
  _WORD *v10; // rdx
  DWORD cbData; // eax
  __int64 v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-49h]
  HKEY v16; // [rsp+30h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-31h] BYREF
  HKEY v18; // [rsp+40h] [rbp-29h] BYREF
  char *v19; // [rsp+48h] [rbp-21h] BYREF
  HKEY v20; // [rsp+50h] [rbp-19h] BYREF
  char v21[32]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v22[3]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v23; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v1 = (void *)a1;
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility\\CursorCustomizedStatus", 0, 0x20019u, &v18);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, 0xF003Fu, &hKey);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)v2,
      phkResult);
  v4 = (LPCWSTR *)off_180037670;
  do
  {
    if ( v18 )
    {
      v19 = 0;
      v16 = hKey;
      if ( (int)wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
                  &v16,
                  v3,
                  *v4,
                  &v19) >= 0 )
      {
        v16 = 0;
        v20 = v18;
        if ( (int)wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
                    &v20,
                    v5,
                    *v4,
                    &v16) >= 0 )
        {
          v6 = (unsigned __int16 *)v19;
          do
          {
            v7 = *(unsigned __int16 *)((char *)v6 + (char *)v16 - v19);
            v8 = *v6 - v7;
            if ( v8 )
              break;
            ++v6;
          }
          while ( v7 );
          if ( !v8 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
            goto LABEL_20;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    }
    v9 = std::wstring::wstring(v21, v4[2]);
    anonymous_namespace_::GetCursorOutputPath(v22, v9);
    v10 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    if ( v10 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      cbData = 2 * v12 + 2;
    }
    else
    {
      cbData = 0;
    }
    RegSetKeyValueW(hKey, 0, *v4, 2u, v10, cbData);
    v3 = v23;
    if ( v23 > 7 )
      std::_Deallocate<16>(v22[0], 2 * v23 + 2);
LABEL_20:
    v4 += 4;
  }
  while ( v4 != (LPCWSTR *)&load_config_used );
  if ( !SystemParametersInfoW(0x57u, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v13);
  if ( !SystemParametersInfoW(0x2029u, 0, v1, 3u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
}

```

## disassembly

```asm
0x18002af70  push    rbp
0x18002af72  push    rbx
0x18002af73  push    rsi
0x18002af74  push    rdi
0x18002af75  lea     rbp, [rsp-3Fh]
0x18002af7a  sub     rsp, 0A8h
0x18002af81  mov     rax, cs:__security_cookie
0x18002af88  xor     rax, rsp
0x18002af8b  mov     [rbp+57h+var_28], rax
0x18002af8f  movsxd  rdi, ecx
0x18002af92  xor     esi, esi
0x18002af94  mov     [rbp+57h+var_80], rsi
0x18002af98  xor     edx, edx
0x18002af9a  lea     rcx, [rbp+57h+var_80]
0x18002af9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002afa3  lea     rax, [rbp+57h+var_80]
0x18002afa7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002afac  mov     r9d, 20019h; samDesired
0x18002afb2  xor     r8d, r8d; ulOptions
0x18002afb5  lea     rdx, SubKey; "Software\\Microsoft\\Accessibility\\Cur"...
0x18002afbc  mov     rbx, 0FFFFFFFF80000001h
0x18002afc3  mov     rcx, rbx; hKey
0x18002afc6  call    cs:__imp_RegOpenKeyExW
0x18002afcc  mov     [rbp+57h+hKey], rsi
0x18002afd0  xor     edx, edx
0x18002afd2  lea     rcx, [rbp+57h+hKey]
0x18002afd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002afdb  lea     rax, [rbp+57h+hKey]
0x18002afdf  mov     [rsp+0C0h+phkResult], rax; unsigned int
0x18002afe4  mov     r9d, 0F003Fh; samDesired
0x18002afea  xor     r8d, r8d; ulOptions
0x18002afed  lea     rdx, aControlPanelCu; "Control Panel\\Cursors"
0x18002aff4  mov     rcx, rbx; hKey
0x18002aff7  call    cs:__imp_RegOpenKeyExW
0x18002affd  mov     rcx, [rbp+5Fh]; this
0x18002b001  test    eax, eax
0x18002b003  jnz     loc_18002B1AF
0x18002b009  lea     rbx, off_180037670; "Appstarting"
0x18002b010  cmp     [rbp+57h+var_80], rsi
0x18002b014  jz      loc_18002B0A8
0x18002b01a  mov     [rbp+57h+var_78], rsi
0x18002b01e  mov     rax, [rbp+57h+hKey]
0x18002b022  mov     [rbp+57h+var_90], rax
0x18002b026  lea     r9, [rbp+57h+var_78]
0x18002b02a  mov     r8, [rbx]
0x18002b02d  lea     rcx, [rbp+57h+var_90]
0x18002b031  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002b036  test    eax, eax
0x18002b038  js      short loc_18002B09F
0x18002b03a  mov     [rbp+57h+var_90], rsi
0x18002b03e  mov     rax, [rbp+57h+var_80]
0x18002b042  mov     [rbp+57h+var_70], rax
0x18002b046  lea     r9, [rbp+57h+var_90]
0x18002b04a  mov     r8, [rbx]
0x18002b04d  lea     rcx, [rbp+57h+var_70]
0x18002b051  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002b056  test    eax, eax
0x18002b058  js      short loc_18002B096
0x18002b05a  mov     rax, [rbp+57h+var_78]
0x18002b05e  mov     rcx, [rbp+57h+var_90]
0x18002b062  sub     rcx, rax
0x18002b065  movzx   edx, word ptr [rax]
0x18002b068  movzx   r8d, word ptr [rax+rcx]
0x18002b06d  sub     edx, r8d
0x18002b070  jnz     short loc_18002B07B
0x18002b072  add     rax, 2
0x18002b076  test    r8d, r8d
0x18002b079  jnz     short loc_18002B065
0x18002b07b  test    edx, edx
0x18002b07d  jnz     short loc_18002B096
0x18002b07f  lea     rcx, [rbp+57h+var_90]
0x18002b083  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b088  lea     rcx, [rbp+57h+var_78]
0x18002b08c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b091  jmp     loc_18002B123
0x18002b096  lea     rcx, [rbp+57h+var_90]
0x18002b09a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b09f  lea     rcx, [rbp+57h+var_78]
0x18002b0a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b0a8  mov     rdx, [rbx+10h]
0x18002b0ac  lea     rcx, [rbp+57h+var_68]
0x18002b0b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b0b5  mov     rdx, rax
0x18002b0b8  lea     rcx, [rbp+57h+var_48]
0x18002b0bc  call    _anonymous_namespace___GetCursorOutputPath
0x18002b0c1  lea     rcx, [rbp+57h+var_48]
0x18002b0c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b0ca  mov     rdx, rax
0x18002b0cd  test    rax, rax
0x18002b0d0  jnz     short loc_18002B0D6
0x18002b0d2  mov     eax, esi
0x18002b0d4  jmp     short loc_18002B0EA
0x18002b0d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b0da  inc     rax
0x18002b0dd  cmp     [rdx+rax*2], si
0x18002b0e1  jnz     short loc_18002B0DA
0x18002b0e3  lea     eax, ds:2[rax*2]
0x18002b0ea  mov     [rsp+0C0h+cbData], eax; cbData
0x18002b0ee  mov     [rsp+0C0h+phkResult], rdx; lpData
0x18002b0f3  mov     r9d, 2; dwType
0x18002b0f9  mov     r8, [rbx]; lpValueName
0x18002b0fc  xor     edx, edx; lpSubKey
0x18002b0fe  mov     rcx, [rbp+57h+hKey]; hKey
0x18002b102  call    cs:__imp_RegSetKeyValueW
0x18002b108  mov     rdx, [rbp+57h+var_30]
0x18002b10c  cmp     rdx, 7
0x18002b110  jbe     short loc_18002B123
0x18002b112  lea     rdx, ds:2[rdx*2]
0x18002b11a  mov     rcx, [rbp+57h+var_48]
0x18002b11e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b123  add     rbx, 20h ; ' '
0x18002b127  lea     rax, _load_config_used
0x18002b12e  cmp     rbx, rax
0x18002b131  jnz     loc_18002B010
0x18002b137  mov     rbx, [rbp+5Fh]
0x18002b13b  mov     r9d, 2; fWinIni
0x18002b141  xor     r8d, r8d; pvParam
0x18002b144  xor     edx, edx; uiParam
0x18002b146  lea     ecx, [rdx+57h]; uiAction
0x18002b149  call    cs:__imp_SystemParametersInfoW
0x18002b14f  test    eax, eax
0x18002b151  jz      short loc_18002B1C4
0x18002b153  mov     rbx, [rbp+5Fh]
0x18002b157  mov     r8, rdi; pvParam
0x18002b15a  xor     edx, edx; uiParam
0x18002b15c  mov     ecx, 2029h; uiAction
0x18002b161  lea     r9d, [rdx+3]; fWinIni
0x18002b165  call    cs:__imp_SystemParametersInfoW
0x18002b16b  test    eax, eax
0x18002b16d  jz      short loc_18002B19A
0x18002b16f  lea     rcx, [rbp+57h+hKey]
0x18002b173  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b178  nop
0x18002b179  lea     rcx, [rbp+57h+var_80]
0x18002b17d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b182  mov     rcx, [rbp+57h+var_28]
0x18002b186  xor     rcx, rsp; StackCookie
0x18002b189  call    __security_check_cookie
0x18002b18e  add     rsp, 0A8h
0x18002b195  pop     rdi
0x18002b196  pop     rsi
0x18002b197  pop     rbx
0x18002b198  pop     rbp
0x18002b199  retn
0x18002b19a  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b1a1  mov     edx, 269h; void *
0x18002b1a6  mov     rcx, rbx; this
0x18002b1a9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b1af  mov     r9d, eax; char *
0x18002b1b2  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b1b9  mov     edx, 244h; void *
0x18002b1be  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002b1c4  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b1cb  mov     edx, 268h; void *
0x18002b1d0  mov     rcx, rbx; this
0x18002b1d3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
