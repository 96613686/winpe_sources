# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18001fcb0`
- end: `0x180020170`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800229c0`
- `0x180022b60`

## callees

- `0x1800018f0`
- `0x18001fcb0`
- `0x180020178`
- `0x180020698`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001fe62`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001fe9e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001ffd0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002000c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001fe62`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001fe9e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001ffd0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002000c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001fe1e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001ff94`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001fe1e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001ff94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fd57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fd57`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001fe06`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001fe06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800200c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800200f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020104`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800200c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800200f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020104`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020059`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020059`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ff4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800200b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ff4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800200b9`

## string_xrefs

- `0x18001fe0c`: `CLSID\`
- `0x18001ff82`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a2;
  ppv = 0;
  v28 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_66:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_66;
      StringFromGUID2(rguid, sz, 64);
      v12 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = _o_wcscat_s(SubKey, 128, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      if ( v14 )
      {
        if ( v14 == 12 )
          goto LABEL_69;
        if ( v14 == 22 || v14 == 34 )
          goto LABEL_71;
        if ( v14 != 80 )
          goto LABEL_70;
      }
      v15 = HKEY_CLASSES_ROOT;
      v27[0] = 0xFFFFFFFF80000000uLL;
      v27[1] = 0;
      v27[2] = 0;
      cSubKeys = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = _o_wcscat_s(SubKey, 128, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, SubKey, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
            v15 = (HKEY)v27[0];
          }
        }
        if ( v15 )
          RegCloseKey(v15);
        goto LABEL_66;
      }
      if ( v20 != 12 )
      {
        if ( v20 != 22 && v20 != 34 )
        {
          if ( v20 == 80 )
            goto LABEL_58;
LABEL_70:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_71:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_69:
      ATL::AtlThrowImpl(-2147024882);
    }
    v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v28);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v28);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x18001fcb0  mov     [rsp-8+arg_10], rbx
0x18001fcb5  mov     [rsp-8+arg_18], rsi
0x18001fcba  push    rbp
0x18001fcbb  push    rdi
0x18001fcbc  push    r12
0x18001fcbe  push    r14
0x18001fcc0  push    r15
0x18001fcc2  lea     rbp, [rsp-140h]
0x18001fcca  sub     rsp, 240h
0x18001fcd1  mov     rax, cs:__security_cookie
0x18001fcd8  xor     rax, rsp
0x18001fcdb  mov     [rbp+160h+var_30], rax
0x18001fce2  mov     r14d, r8d
0x18001fce5  mov     rdi, rdx
0x18001fce8  mov     rbx, rcx
0x18001fceb  xor     r15d, r15d
0x18001fcee  mov     [rsp+260h+var_1F8], r15
0x18001fcf3  xorps   xmm0, xmm0
0x18001fcf6  movups  [rbp+160h+var_1C8], xmm0
0x18001fcfa  test    rdx, rdx
0x18001fcfd  jnz     short loc_18001FD04
0x18001fcff  jmp     loc_180020122
0x18001fd04  mov     eax, cs:GUID_NULL.Data1
0x18001fd0a  cmp     [rcx], eax
0x18001fd0c  jnz     short loc_18001FD34
0x18001fd0e  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18001fd14  cmp     [rcx+4], eax
0x18001fd17  jnz     short loc_18001FD34
0x18001fd19  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18001fd1f  cmp     [rcx+8], eax
0x18001fd22  jnz     short loc_18001FD34
0x18001fd24  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18001fd2a  cmp     [rcx+0Ch], eax
0x18001fd2d  jnz     short loc_18001FD34
0x18001fd2f  jmp     loc_180020122
0x18001fd34  lea     rax, [rsp+260h+var_1F8]
0x18001fd39  mov     [rsp+260h+ppv], rax; ppv
0x18001fd3e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18001fd45  mov     r12d, 1
0x18001fd4b  mov     r8d, r12d; dwClsContext
0x18001fd4e  xor     edx, edx; pUnkOuter
0x18001fd50  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18001fd57  call    cs:__imp_CoCreateInstance
0x18001fd5d  test    eax, eax
0x18001fd5f  jns     loc_18001FDE5
0x18001fd65  jmp     loc_18002010B
0x18001fd6a  mov     rax, [rdi+8]
0x18001fd6e  movups  xmm0, xmmword ptr [rax]
0x18001fd71  movdqu  [rbp+160h+var_1C8], xmm0
0x18001fd76  lea     r9, [rbp+160h+var_1C8]
0x18001fd7a  mov     r8d, r12d
0x18001fd7d  mov     rdx, rbx
0x18001fd80  test    r14d, r14d
0x18001fd83  jz      short loc_18001FDC5
0x18001fd85  cmp     ecx, r12d
0x18001fd88  mov     rcx, [rsp+260h+var_1F8]
0x18001fd8d  mov     rax, [rcx]
0x18001fd90  jnz     short loc_18001FD98
0x18001fd92  mov     rax, [rax+28h]
0x18001fd96  jmp     short loc_18001FD9C
0x18001fd98  mov     rax, [rax+38h]
0x18001fd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fda1  mov     esi, eax
0x18001fda3  test    eax, eax
0x18001fda5  jns     short loc_18001FDE1
0x18001fda7  mov     rcx, [rsp+260h+var_1F8]
0x18001fdac  test    rcx, rcx
0x18001fdaf  jz      short loc_18001FDBE
0x18001fdb1  mov     rax, [rcx]
0x18001fdb4  mov     rax, [rax+10h]
0x18001fdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdbd  nop
0x18001fdbe  mov     eax, esi
0x18001fdc0  jmp     loc_180020124
0x18001fdc5  cmp     ecx, r12d
0x18001fdc8  mov     rcx, [rsp+260h+var_1F8]
0x18001fdcd  mov     rax, [rcx]
0x18001fdd0  jnz     short loc_18001FDD8
0x18001fdd2  mov     rax, [rax+30h]
0x18001fdd6  jmp     short loc_18001FDDC
0x18001fdd8  mov     rax, [rax+40h]
0x18001fddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fde1  add     rdi, 10h
0x18001fde5  mov     ecx, [rdi]
0x18001fde7  test    ecx, ecx
0x18001fde9  jnz     loc_18001FD6A
0x18001fdef  test    r14d, r14d
0x18001fdf2  jnz     loc_18002010B
0x18001fdf8  lea     r8d, [rcx+40h]; cchMax
0x18001fdfc  lea     rdx, [rbp+160h+sz]; lpsz
0x18001fe03  mov     rcx, rbx; rguid
0x18001fe06  call    cs:__imp_StringFromGUID2
0x18001fe0c  lea     r8, aClsid; "CLSID\\"
0x18001fe13  mov     ebx, 80h
0x18001fe18  mov     edx, ebx
0x18001fe1a  lea     rcx, [rbp+160h+SubKey]
0x18001fe1e  call    cs:__imp__o_wcscpy_s
0x18001fe24  lea     r14d, [rbx-74h]
0x18001fe28  lea     r12d, [rbx-30h]
0x18001fe2c  test    eax, eax
0x18001fe2e  jz      short loc_18001FE54
0x18001fe30  cmp     eax, r14d
0x18001fe33  jz      loc_18002014F
0x18001fe39  cmp     eax, 16h
0x18001fe3c  jz      loc_180020165
0x18001fe42  cmp     eax, 22h ; '"'
0x18001fe45  jz      loc_180020165
0x18001fe4b  cmp     eax, r12d
0x18001fe4e  jnz     loc_18002015A
0x18001fe54  lea     r8, [rbp+160h+sz]
0x18001fe5b  mov     rdx, rbx
0x18001fe5e  lea     rcx, [rbp+160h+SubKey]
0x18001fe62  call    cs:__imp__o_wcscat_s
0x18001fe68  test    eax, eax
0x18001fe6a  jz      short loc_18001FE90
0x18001fe6c  cmp     eax, r14d
0x18001fe6f  jz      loc_18002014F
0x18001fe75  cmp     eax, 16h
0x18001fe78  jz      loc_180020165
0x18001fe7e  cmp     eax, 22h ; '"'
0x18001fe81  jz      loc_180020165
0x18001fe87  cmp     eax, r12d
0x18001fe8a  jnz     loc_18002015A
0x18001fe90  lea     r8, aRequiredCatego; "\\Required Categories"
0x18001fe97  mov     rdx, rbx
0x18001fe9a  lea     rcx, [rbp+160h+SubKey]
0x18001fe9e  call    cs:__imp__o_wcscat_s
0x18001fea4  test    eax, eax
0x18001fea6  jz      short loc_18001FECC
0x18001fea8  cmp     eax, r14d
0x18001feab  jz      loc_18002014F
0x18001feb1  cmp     eax, 16h
0x18001feb4  jz      loc_180020165
0x18001feba  cmp     eax, 22h ; '"'
0x18001febd  jz      loc_180020165
0x18001fec3  cmp     eax, r12d
0x18001fec6  jnz     loc_18002015A
0x18001fecc  mov     rdi, 0FFFFFFFF80000000h
0x18001fed3  mov     [rbp+160h+var_1E0], rdi
0x18001fed7  mov     [rbp+160h+var_1D8], r15
0x18001fedb  mov     [rbp+160h+var_1D0], r15
0x18001fedf  mov     rbx, r15
0x18001fee2  mov     [rsp+260h+cSubKeys], r15d
0x18001fee7  mov     [rsp+260h+phkResult], r15
0x18001feec  lea     rax, [rsp+260h+phkResult]
0x18001fef1  mov     [rsp+260h+ppv], rax; phkResult
0x18001fef6  mov     r9d, 20019h; samDesired
0x18001fefc  xor     r8d, r8d; ulOptions
0x18001feff  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18001ff03  mov     rcx, rdi; hKey
0x18001ff06  call    cs:__imp_RegOpenKeyExW
0x18001ff0c  test    eax, eax
0x18001ff0e  jnz     short loc_18001FF82
0x18001ff10  mov     rbx, [rsp+260h+phkResult]
0x18001ff15  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001ff1a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001ff1f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001ff24  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001ff29  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18001ff2e  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001ff33  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001ff38  lea     rax, [rsp+260h+cSubKeys]
0x18001ff3d  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18001ff42  xor     r9d, r9d; lpReserved
0x18001ff45  xor     r8d, r8d; lpcchClass
0x18001ff48  xor     edx, edx; lpClass
0x18001ff4a  mov     rcx, rbx; hKey
0x18001ff4d  call    cs:__imp_RegQueryInfoKeyW
0x18001ff53  mov     esi, eax
0x18001ff55  test    rbx, rbx
0x18001ff58  jz      short loc_18001FF66
0x18001ff5a  mov     rcx, rbx; hKey
0x18001ff5d  call    cs:__imp_RegCloseKey
0x18001ff63  mov     rbx, r15
0x18001ff66  test    esi, esi
0x18001ff68  jnz     short loc_18001FF82
0x18001ff6a  cmp     [rsp+260h+cSubKeys], r15d
0x18001ff6f  jnz     short loc_18001FF82
0x18001ff71  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18001ff75  lea     rcx, [rbp+160h+var_1E0]; this
0x18001ff79  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001ff7e  mov     rdi, [rbp+160h+var_1E0]
0x18001ff82  lea     r8, aClsid; "CLSID\\"
0x18001ff89  mov     esi, 80h
0x18001ff8e  mov     edx, esi
0x18001ff90  lea     rcx, [rbp+160h+SubKey]
0x18001ff94  call    cs:__imp__o_wcscpy_s
0x18001ff9a  test    eax, eax
0x18001ff9c  jz      short loc_18001FFC2
0x18001ff9e  cmp     eax, r14d
0x18001ffa1  jz      loc_18002014F
0x18001ffa7  cmp     eax, 16h
0x18001ffaa  jz      loc_180020165
0x18001ffb0  cmp     eax, 22h ; '"'
0x18001ffb3  jz      loc_180020165
0x18001ffb9  cmp     eax, r12d
0x18001ffbc  jnz     loc_18002015A
0x18001ffc2  lea     r8, [rbp+160h+sz]
0x18001ffc9  mov     rdx, rsi
0x18001ffcc  lea     rcx, [rbp+160h+SubKey]
0x18001ffd0  call    cs:__imp__o_wcscat_s
0x18001ffd6  test    eax, eax
0x18001ffd8  jz      short loc_18001FFFE
0x18001ffda  cmp     eax, r14d
0x18001ffdd  jz      loc_18002014F
0x18001ffe3  cmp     eax, 16h
0x18001ffe6  jz      loc_180020165
0x18001ffec  cmp     eax, 22h ; '"'
0x18001ffef  jz      loc_180020165
0x18001fff5  cmp     eax, r12d
0x18001fff8  jnz     loc_18002015A
0x18001fffe  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180020005  mov     rdx, rsi
0x180020008  lea     rcx, [rbp+160h+SubKey]
0x18002000c  call    cs:__imp__o_wcscat_s
0x180020012  test    eax, eax
0x180020014  jz      short loc_18002003A
0x180020016  cmp     eax, r14d
0x180020019  jz      loc_18002014F
0x18002001f  cmp     eax, 16h
0x180020022  jz      loc_180020165
0x180020028  cmp     eax, 22h ; '"'
0x18002002b  jz      loc_180020165
0x180020031  cmp     eax, r12d
0x180020034  jnz     loc_18002015A
0x18002003a  mov     [rsp+260h+hKey], r15
0x18002003f  lea     rax, [rsp+260h+hKey]
0x180020044  mov     [rsp+260h+ppv], rax; phkResult
0x180020049  mov     r9d, 20019h; samDesired
0x18002004f  xor     r8d, r8d; ulOptions
0x180020052  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180020056  mov     rcx, rdi; hKey
0x180020059  call    cs:__imp_RegOpenKeyExW
0x18002005f  test    eax, eax
0x180020061  jnz     loc_1800200EE
0x180020067  mov     eax, r15d
0x18002006a  test    rbx, rbx
0x18002006d  jz      short loc_180020078
0x18002006f  mov     rcx, rbx; hKey
0x180020072  call    cs:__imp_RegCloseKey
0x180020078  mov     rbx, [rsp+260h+hKey]
0x18002007d  test    eax, eax
0x18002007f  jnz     short loc_1800200EE
0x180020081  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180020086  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002008b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180020090  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180020095  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18002009a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002009f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800200a4  lea     rax, [rsp+260h+cSubKeys]
0x1800200a9  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800200ae  xor     r9d, r9d; lpReserved
0x1800200b1  xor     r8d, r8d; lpcchClass
0x1800200b4  xor     edx, edx; lpClass
0x1800200b6  mov     rcx, rbx; hKey
0x1800200b9  call    cs:__imp_RegQueryInfoKeyW
0x1800200bf  mov     esi, eax
0x1800200c1  test    rbx, rbx
0x1800200c4  jz      short loc_1800200D2
0x1800200c6  mov     rcx, rbx; hKey
0x1800200c9  call    cs:__imp_RegCloseKey
0x1800200cf  mov     rbx, r15
0x1800200d2  test    esi, esi
0x1800200d4  jnz     short loc_1800200FC
0x1800200d6  cmp     [rsp+260h+cSubKeys], r15d
0x1800200db  jnz     short loc_1800200EE
0x1800200dd  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800200e1  lea     rcx, [rbp+160h+var_1E0]; this
0x1800200e5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800200ea  mov     rdi, [rbp+160h+var_1E0]
0x1800200ee  test    rbx, rbx
0x1800200f1  jz      short loc_1800200FC
0x1800200f3  mov     rcx, rbx; hKey
0x1800200f6  call    cs:__imp_RegCloseKey
0x1800200fc  test    rdi, rdi
0x1800200ff  jz      short loc_18002010B
0x180020101  mov     rcx, rdi; hKey
0x180020104  call    cs:__imp_RegCloseKey
0x18002010a  nop
0x18002010b  mov     rcx, [rsp+260h+var_1F8]
0x180020110  test    rcx, rcx
0x180020113  jz      short loc_180020122
0x180020115  mov     rax, [rcx]
0x180020118  mov     rax, [rax+10h]
0x18002011c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020121  nop
0x180020122  xor     eax, eax
0x180020124  mov     rcx, [rbp+160h+var_30]
0x18002012b  xor     rcx, rsp; StackCookie
0x18002012e  call    __security_check_cookie
0x180020133  lea     r11, [rsp+260h+var_20]
0x18002013b  mov     rbx, [r11+40h]
0x18002013f  mov     rsi, [r11+48h]
0x180020143  mov     rsp, r11
0x180020146  pop     r15
0x180020148  pop     r14
0x18002014a  pop     r12
0x18002014c  pop     rdi
0x18002014d  pop     rbp
  ... truncated ...
```
