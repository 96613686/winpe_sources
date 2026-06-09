# mfsensorgroup_utils::CreateRegKeyAndStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,HKEY__ * *)

- ea: `0x180065d74`
- end: `0x180065f90`
- name: `?CreateRegKeyAndStringValue@mfsensorgroup_utils@@YAJPEAUHKEY__@@PEBG11PEAPEAU2@@Z`
- size: `540`
- prototype: `__int64 __fastcall(HKEY hKey, const WCHAR *lpSubKey, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180065f98`

## callees

- `0x180005fa0`
- `0x18000d1f0`
- `0x180028d5c`
- `0x180028e5c`
- `0x180065d74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065f25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065f25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065ed5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065ed5`

## pseudocode

```c
__int64 __fastcall mfsensorgroup_utils::CreateRegKeyAndStringValue(
        HKEY hKey,
        const WCHAR *lpSubKey,
        LPCWSTR lpValueName,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v9; // eax
  signed int v10; // ebx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rdi
  __int64 v13; // rdx
  int v14; // r15d
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  unsigned __int64 v18; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+90h] [rbp+8h] BYREF

  hKeya = 0;
  v18 = 0;
  if ( !hKey )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( g_wppLevels )
    {
      v11 = 16;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v9);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  if ( lpSubKey )
  {
    if ( !a4 )
    {
      v9 = -2147024809;
      v10 = -2147024809;
      if ( g_wppLevels )
      {
        v11 = 18;
        goto LABEL_4;
      }
      goto LABEL_33;
    }
    v12 = a5;
    if ( !a5 )
    {
      v10 = -2147467261;
      if ( !g_wppLevels )
        goto LABEL_33;
      v13 = (unsigned int)((_DWORD)a5 + 19);
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v10);
      goto LABEL_33;
    }
    *(_QWORD *)a5 = 0;
    v9 = StringCchLengthW(a4, 0x7FFFFFFFu, &v18);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( g_wppLevels )
      {
        v11 = 20;
        goto LABEL_4;
      }
      goto LABEL_33;
    }
    v14 = v18 + 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeya,
      0);
    v15 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKeya, 0);
    v10 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_33;
        v13 = 21;
        goto LABEL_15;
      }
    }
    v16 = RegSetValueExW(hKeya, lpValueName, 0, 1u, (const BYTE *)a4, 2 * v14);
    v10 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_33;
        v13 = 22;
        goto LABEL_15;
      }
    }
    else
    {
      v10 = 0;
    }
    *(_QWORD *)v12 = hKeya;
    hKeya = 0;
    goto LABEL_33;
  }
  v9 = -2147024809;
  v10 = -2147024809;
  if ( g_wppLevels )
  {
    v11 = 17;
    goto LABEL_4;
  }
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180065d74  mov     rax, rsp
0x180065d77  mov     [rax+10h], rbx
0x180065d7b  mov     [rax+18h], rbp
0x180065d7f  push    rsi
0x180065d80  push    rdi
0x180065d81  push    r12
0x180065d83  push    r14
0x180065d85  push    r15
0x180065d87  sub     rsp, 60h
0x180065d8b  mov     qword ptr [rax+8], 0
0x180065d93  mov     rsi, r9
0x180065d96  mov     qword ptr [rax-38h], 0
0x180065d9e  mov     r12, r8
0x180065da1  mov     rbp, rdx
0x180065da4  mov     r14, rcx
0x180065da7  test    rcx, rcx
0x180065daa  jnz     short loc_180065DE6
0x180065dac  mov     eax, 80070057h
0x180065db1  mov     ebx, eax
0x180065db3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065dba  jb      loc_180065F68
0x180065dc0  lea     edx, [rcx+10h]
0x180065dc3  mov     [rsp+88h+dwOptions], eax
0x180065dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180065dce  lea     r8, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids
0x180065dd5  xor     r9d, r9d
0x180065dd8  mov     rcx, [rcx+10h]
0x180065ddc  call    WPP_SF_qD
0x180065de1  jmp     loc_180065F68
0x180065de6  test    rbp, rbp
0x180065de9  jnz     short loc_180065E04
0x180065deb  mov     eax, 80070057h
0x180065df0  mov     ebx, eax
0x180065df2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065df9  jb      loc_180065F68
0x180065dff  lea     edx, [rbp+11h]
0x180065e02  jmp     short loc_180065DC3
0x180065e04  test    rsi, rsi
0x180065e07  jnz     short loc_180065E22
0x180065e09  mov     eax, 80070057h
0x180065e0e  mov     ebx, eax
0x180065e10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065e17  jb      loc_180065F68
0x180065e1d  lea     edx, [rsi+12h]
0x180065e20  jmp     short loc_180065DC3
0x180065e22  mov     rdi, [rsp+88h+arg_20]
0x180065e2a  test    rdi, rdi
0x180065e2d  jnz     short loc_180065E4D
0x180065e2f  mov     ebx, 80004003h
0x180065e34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065e3b  jb      loc_180065F68
0x180065e41  lea     edx, [rdi+13h]
0x180065e44  mov     [rsp+88h+dwOptions], ebx
0x180065e48  jmp     loc_180065DC7
0x180065e4d  lea     r8, [rsp+88h+var_38]; unsigned __int64 *
0x180065e52  mov     qword ptr [rdi], 0
0x180065e59  mov     edx, 7FFFFFFFh; unsigned __int64
0x180065e5e  mov     rcx, rsi; unsigned __int16 *
0x180065e61  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180065e66  mov     ebx, eax
0x180065e68  test    eax, eax
0x180065e6a  jns     short loc_180065E83
0x180065e6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065e73  jb      loc_180065F68
0x180065e79  mov     edx, 14h
0x180065e7e  jmp     loc_180065DC3
0x180065e83  mov     r15, [rsp+88h+var_38]
0x180065e88  lea     rcx, [rsp+88h+hKey]
0x180065e90  xor     edx, edx
0x180065e92  inc     r15
0x180065e95  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180065e9a  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180065ea3  lea     rax, [rsp+88h+hKey]
0x180065eab  mov     [rsp+88h+phkResult], rax; phkResult
0x180065eb0  xor     r9d, r9d; lpClass
0x180065eb3  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180065ebc  xor     r8d, r8d; Reserved
0x180065ebf  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x180065ec7  mov     rdx, rbp; lpSubKey
0x180065eca  mov     rcx, r14; hKey
0x180065ecd  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180065ed5  call    cs:__imp_RegCreateKeyExW
0x180065edb  mov     ebx, eax
0x180065edd  mov     ebp, 80070000h
0x180065ee2  test    eax, eax
0x180065ee4  jz      short loc_180065F04
0x180065ee6  jle     short loc_180065EED
0x180065ee8  movzx   ebx, ax
0x180065eeb  or      ebx, ebp
0x180065eed  test    ebx, ebx
0x180065eef  jns     short loc_180065F04
0x180065ef1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065ef8  jb      short loc_180065F68
0x180065efa  mov     edx, 15h
0x180065eff  jmp     loc_180065E44
0x180065f04  mov     rcx, [rsp+88h+hKey]; hKey
0x180065f0c  lea     eax, [r15+r15]
0x180065f10  mov     [rsp+88h+samDesired], eax; cbData
0x180065f14  mov     r9d, 1; dwType
0x180065f1a  xor     r8d, r8d; Reserved
0x180065f1d  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x180065f22  mov     rdx, r12; lpValueName
0x180065f25  call    cs:__imp_RegSetValueExW
0x180065f2b  mov     ebx, eax
0x180065f2d  test    eax, eax
0x180065f2f  jz      short loc_180065F4F
0x180065f31  jle     short loc_180065F38
0x180065f33  movzx   ebx, ax
0x180065f36  or      ebx, ebp
0x180065f38  test    ebx, ebx
0x180065f3a  jns     short loc_180065F51
0x180065f3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065f43  jb      short loc_180065F68
0x180065f45  mov     edx, 16h
0x180065f4a  jmp     loc_180065E44
0x180065f4f  xor     ebx, ebx
0x180065f51  mov     rax, [rsp+88h+hKey]
0x180065f59  mov     [rdi], rax
0x180065f5c  mov     [rsp+88h+hKey], 0
0x180065f68  lea     rcx, [rsp+88h+hKey]
0x180065f70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180065f75  lea     r11, [rsp+88h+var_28]
0x180065f7a  mov     eax, ebx
0x180065f7c  mov     rbx, [r11+38h]
0x180065f80  mov     rbp, [r11+40h]
0x180065f84  mov     rsp, r11
0x180065f87  pop     r15
0x180065f89  pop     r14
0x180065f8b  pop     r12
0x180065f8d  pop     rdi
0x180065f8e  pop     rsi
0x180065f8f  retn
```
