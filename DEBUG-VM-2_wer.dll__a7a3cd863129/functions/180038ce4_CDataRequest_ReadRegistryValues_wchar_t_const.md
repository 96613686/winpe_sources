# CDataRequest::ReadRegistryValues(wchar_t const *)

- ea: `0x180038ce4`
- end: `0x180038f72`
- name: `?ReadRegistryValues@CDataRequest@@IEAAXPEB_W@Z`
- size: `654`
- prototype: `void __fastcall(CDataRequest *__hidden this, LPCWSTR lpSubKey)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007964c`
- `0x180083cac`
- `0x180084e24`
- `0x180084ee0`
- `0x18008abb0`

## callees

- `0x180004bb4`
- `0x18001c5ec`
- `0x18001c650`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x180038ce4`
- `0x180038f78`
- `0x18008a894`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038e6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038e6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038d48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038d48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180038dee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180038dee`

## pseudocode

```c
void __fastcall CDataRequest::ReadRegistryValues(CDataRequest *this, LPCWSTR lpSubKey)
{
  HKEY *phkResult; // rax
  __int64 unique_for; // rax
  LPWSTR v6; // rbx
  __int64 v7; // rax
  LPBYTE v8; // rdi
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  DWORD i; // r14d
  DWORD cValues; // [rsp+60h] [rbp+7h] BYREF
  DWORD Type; // [rsp+64h] [rbp+Bh] BYREF
  HKEY hKey; // [rsp+68h] [rbp+Fh] BYREF
  LPBYTE lpData; // [rsp+70h] [rbp+17h] BYREF
  LPWSTR lpValueName; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v17[16]; // [rsp+80h] [rbp+27h] BYREF
  DWORD cchValueName; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+7Fh] BYREF

  hKey = 0;
  cValues = 0;
  lpValueName = 0;
  lpData = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, phkResult) )
  {
    unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(v17, 260);
    utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpValueName, unique_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v17);
    v6 = lpValueName;
    if ( lpValueName )
    {
      v7 = utl::make_unique_for_overwrite<wchar_t [0],0>(v17, 2048);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpData, v7);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v17);
      v8 = lpData;
      if ( lpData )
      {
        if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 18;
LABEL_26:
            WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids);
          }
        }
        else
        {
          for ( i = 0; i < cValues; ++i )
          {
            cchValueName = 260;
            cbData = 4096;
            if ( !RegEnumValueW(hKey, i, v6, &cchValueName, 0, &Type, v8, &cbData) )
            {
              if ( Type == 1 && cchValueName <= 0x104 && cbData <= 0x1000 )
              {
                if ( *v6 )
                {
                  v6[259] = 0;
                  *((_WORD *)v8 + 2047) = 0;
                  CDataRequest::AddRequest(this, v6, (const wchar_t *)v8);
                }
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids);
              }
            }
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 17;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 16;
        goto LABEL_26;
      }
    }
  }
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpData);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpValueName);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
}

```

## disassembly

```asm
0x180038ce4  mov     [rsp-8+arg_0], rbx
0x180038ce9  mov     [rsp-8+arg_8], rsi
0x180038cee  push    rbp
0x180038cef  push    rdi
0x180038cf0  push    r12
0x180038cf2  push    r14
0x180038cf4  push    r15
0x180038cf6  lea     rbp, [rsp-37h]
0x180038cfb  sub     rsp, 90h
0x180038d02  xor     r12d, r12d
0x180038d05  mov     r15, rcx
0x180038d08  lea     rcx, [rbp+57h+hKey]
0x180038d0c  mov     [rbp+57h+hKey], r12
0x180038d10  mov     [rbp+57h+cValues], r12d
0x180038d14  mov     rbx, rdx
0x180038d17  mov     [rbp+57h+lpValueName], r12
0x180038d1b  mov     [rbp+57h+lpData], r12
0x180038d1f  mov     [rbp+57h+cchValueName], r12d
0x180038d23  mov     [rbp+57h+cbData], r12d
0x180038d27  mov     [rbp+57h+Type], r12d
0x180038d2b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180038d30  mov     r9d, 20119h; samDesired
0x180038d36  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180038d3b  xor     r8d, r8d; ulOptions
0x180038d3e  mov     rdx, rbx; lpSubKey
0x180038d41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038d48  call    cs:__imp_RegOpenKeyExW
0x180038d4e  test    eax, eax
0x180038d50  jnz     loc_180038F3B
0x180038d56  mov     edx, 104h
0x180038d5b  lea     rcx, [rbp+57h+var_30]
0x180038d5f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180038d64  mov     rdx, rax
0x180038d67  lea     rcx, [rbp+57h+lpValueName]
0x180038d6b  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180038d70  lea     rcx, [rbp+57h+var_30]; void *
0x180038d74  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180038d79  mov     rbx, [rbp+57h+lpValueName]
0x180038d7d  test    rbx, rbx
0x180038d80  jz      loc_180038F0D
0x180038d86  mov     edx, 800h
0x180038d8b  lea     rcx, [rbp+57h+var_30]
0x180038d8f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180038d94  mov     rdx, rax
0x180038d97  lea     rcx, [rbp+57h+lpData]
0x180038d9b  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180038da0  lea     rcx, [rbp+57h+var_30]; void *
0x180038da4  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180038da9  mov     rdi, [rbp+57h+lpData]
0x180038dad  test    rdi, rdi
0x180038db0  jz      loc_180038EED
0x180038db6  mov     rcx, [rbp+57h+hKey]; hKey
0x180038dba  lea     rax, [rbp+57h+cValues]
0x180038dbe  mov     [rsp+0B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180038dc3  xor     r9d, r9d; lpReserved
0x180038dc6  mov     [rsp+0B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180038dcb  xor     r8d, r8d; lpcchClass
0x180038dce  mov     [rsp+0B0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180038dd3  xor     edx, edx; lpClass
0x180038dd5  mov     [rsp+0B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180038dda  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x180038ddf  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180038de4  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180038de9  mov     [rsp+0B0h+phkResult], r12; lpcSubKeys
0x180038dee  call    cs:__imp_RegQueryInfoKeyW
0x180038df4  test    eax, eax
0x180038df6  jz      short loc_180038E23
0x180038df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dff  lea     rsi, WPP_GLOBAL_Control
0x180038e06  cmp     rcx, rsi
0x180038e09  jz      loc_180038F3B
0x180038e0f  test    byte ptr [rcx+1Ch], 1
0x180038e13  jz      loc_180038F3B
0x180038e19  lea     edx, [r12+12h]
0x180038e1e  jmp     loc_180038F2B
0x180038e23  mov     r14d, r12d
0x180038e26  cmp     [rbp+57h+cValues], r12d
0x180038e2a  jbe     loc_180038F3B
0x180038e30  lea     rsi, WPP_GLOBAL_Control
0x180038e37  mov     rcx, [rbp+57h+hKey]; hKey
0x180038e3b  lea     rax, [rbp+57h+cbData]
0x180038e3f  mov     [rsp+0B0h+lpcValues], rax; lpcbData
0x180038e44  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180038e48  lea     rax, [rbp+57h+Type]
0x180038e4c  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpData
0x180038e51  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpType
0x180038e56  mov     r8, rbx; lpValueName
0x180038e59  mov     edx, r14d; dwIndex
0x180038e5c  mov     [rsp+0B0h+phkResult], r12; lpReserved
0x180038e61  mov     [rbp+57h+cchValueName], 104h
0x180038e68  mov     [rbp+57h+cbData], 1000h
0x180038e6f  call    cs:__imp_RegEnumValueW
0x180038e75  test    eax, eax
0x180038e77  jnz     short loc_180038EDE
0x180038e79  cmp     [rbp+57h+Type], 1
0x180038e7d  jnz     short loc_180038EB7
0x180038e7f  cmp     [rbp+57h+cchValueName], 104h
0x180038e86  ja      short loc_180038EB7
0x180038e88  cmp     [rbp+57h+cbData], 1000h
0x180038e8f  ja      short loc_180038EB7
0x180038e91  cmp     [rbx], r12w
0x180038e95  jz      short loc_180038EDE
0x180038e97  mov     [rbx+206h], r12w
0x180038e9f  mov     r8, rdi; wchar_t *
0x180038ea2  mov     rdx, rbx; wchar_t *
0x180038ea5  mov     [rdi+0FFEh], r12w
0x180038ead  mov     rcx, r15; this
0x180038eb0  call    ?AddRequest@CDataRequest@@QEAAJPEB_W0@Z; CDataRequest::AddRequest(wchar_t const *,wchar_t const *)
0x180038eb5  jmp     short loc_180038EDE
0x180038eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ebe  cmp     rcx, rsi
0x180038ec1  jz      short loc_180038EDE
0x180038ec3  test    byte ptr [rcx+1Ch], 1
0x180038ec7  jz      short loc_180038EDE
0x180038ec9  mov     rcx, [rcx+10h]
0x180038ecd  lea     r8, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids
0x180038ed4  mov     edx, 13h
0x180038ed9  call    WPP_SF_
0x180038ede  inc     r14d
0x180038ee1  cmp     r14d, [rbp+57h+cValues]
0x180038ee5  jb      loc_180038E37
0x180038eeb  jmp     short loc_180038F3B
0x180038eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ef4  lea     rsi, WPP_GLOBAL_Control
0x180038efb  cmp     rcx, rsi
0x180038efe  jz      short loc_180038F3B
0x180038f00  test    byte ptr [rcx+1Ch], 1
0x180038f04  jz      short loc_180038F3B
0x180038f06  mov     edx, 11h
0x180038f0b  jmp     short loc_180038F2B
0x180038f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f14  lea     rsi, WPP_GLOBAL_Control
0x180038f1b  cmp     rcx, rsi
0x180038f1e  jz      short loc_180038F3B
0x180038f20  test    byte ptr [rcx+1Ch], 1
0x180038f24  jz      short loc_180038F3B
0x180038f26  mov     edx, 10h
0x180038f2b  mov     rcx, [rcx+10h]
0x180038f2f  lea     r8, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids
0x180038f36  call    WPP_SF_
0x180038f3b  lea     rcx, [rbp+57h+lpData]; void *
0x180038f3f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180038f44  lea     rcx, [rbp+57h+lpValueName]; void *
0x180038f48  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180038f4d  lea     rcx, [rbp+57h+hKey]
0x180038f51  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180038f56  lea     r11, [rsp+0B0h+var_20]
0x180038f5e  mov     rbx, [r11+30h]
0x180038f62  mov     rsi, [r11+38h]
0x180038f66  mov     rsp, r11
0x180038f69  pop     r15
0x180038f6b  pop     r14
0x180038f6d  pop     r12
0x180038f6f  pop     rdi
0x180038f70  pop     rbp
0x180038f71  retn
```
