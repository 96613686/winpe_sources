# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x1800087c4`
- end: `0x18000918c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `2504`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000861c`
- `0x1800087c4`

## callees

- `0x180006d60`
- `0x180006d7c`
- `0x1800071a8`
- `0x1800079bc`
- `0x180007b54`
- `0x180008158`
- `0x1800087c4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dbe0`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008af1`
- `KERNEL32!GetProcAddress` at `0x180008bc5`
- `KERNEL32!GetProcAddress` at `0x180008db6`
- `KERNEL32!GetProcAddress` at `0x1800090b2`
- `KERNEL32!GetProcAddress` at `0x180008af1`
- `KERNEL32!GetProcAddress` at `0x180008bc5`
- `KERNEL32!GetProcAddress` at `0x180008db6`
- `KERNEL32!GetProcAddress` at `0x1800090b2`
- `KERNEL32!GetModuleHandleW` at `0x180008adc`
- `KERNEL32!GetModuleHandleW` at `0x180008bb0`
- `KERNEL32!GetModuleHandleW` at `0x180008da1`
- `KERNEL32!GetModuleHandleW` at `0x18000909d`
- `KERNEL32!GetModuleHandleW` at `0x180008adc`
- `KERNEL32!GetModuleHandleW` at `0x180008bb0`
- `KERNEL32!GetModuleHandleW` at `0x180008da1`
- `KERNEL32!GetModuleHandleW` at `0x18000909d`
- `KERNEL32!lstrcmpiW` at `0x180008843`
- `KERNEL32!lstrcmpiW` at `0x180008855`
- `KERNEL32!lstrcmpiW` at `0x1800088d3`
- `KERNEL32!lstrcmpiW` at `0x180008946`
- `KERNEL32!lstrcmpiW` at `0x180008974`
- `KERNEL32!lstrcmpiW` at `0x180008fc6`
- `KERNEL32!lstrcmpiW` at `0x180008843`
- `KERNEL32!lstrcmpiW` at `0x180008855`
- `KERNEL32!lstrcmpiW` at `0x1800088d3`
- `KERNEL32!lstrcmpiW` at `0x180008946`
- `KERNEL32!lstrcmpiW` at `0x180008974`
- `KERNEL32!lstrcmpiW` at `0x180008fc6`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180008e75`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180008e75`
- `USER32!CharNextW` at `0x1800088a7`
- `USER32!CharNextW` at `0x180008a97`
- `USER32!CharNextW` at `0x1800088a7`
- `USER32!CharNextW` at `0x180008a97`
- `ADVAPI32!RegCloseKey` at `0x180008a70`
- `ADVAPI32!RegCloseKey` at `0x180008b7e`
- `ADVAPI32!RegCloseKey` at `0x180008c40`
- `ADVAPI32!RegCloseKey` at `0x180008cd0`
- `ADVAPI32!RegCloseKey` at `0x180008e3a`
- `ADVAPI32!RegCloseKey` at `0x180009068`
- `ADVAPI32!RegCloseKey` at `0x180009120`
- `ADVAPI32!RegCloseKey` at `0x180009140`
- `ADVAPI32!RegCloseKey` at `0x180008a70`
- `ADVAPI32!RegCloseKey` at `0x180008b7e`
- `ADVAPI32!RegCloseKey` at `0x180008c40`
- `ADVAPI32!RegCloseKey` at `0x180008cd0`
- `ADVAPI32!RegCloseKey` at `0x180008e3a`
- `ADVAPI32!RegCloseKey` at `0x180009068`
- `ADVAPI32!RegCloseKey` at `0x180009120`
- `ADVAPI32!RegCloseKey` at `0x180009140`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008fa4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009044`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008fa4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009044`
- `ADVAPI32!RegDeleteKeyW` at `0x1800090f4`
- `ADVAPI32!RegDeleteKeyW` at `0x1800090f4`
- `ADVAPI32!RegCreateKeyExW` at `0x180008cb8`
- `ADVAPI32!RegCreateKeyExW` at `0x180008cb8`
- `ADVAPI32!RegOpenKeyExW` at `0x180008a2c`
- `ADVAPI32!RegOpenKeyExW` at `0x180008b66`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c2b`
- `ADVAPI32!RegOpenKeyExW` at `0x180008e20`
- `ADVAPI32!RegOpenKeyExW` at `0x180008a2c`
- `ADVAPI32!RegOpenKeyExW` at `0x180008b66`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c2b`
- `ADVAPI32!RegOpenKeyExW` at `0x180008e20`
- `ADVAPI32!RegDeleteValueW` at `0x180008a57`
- `ADVAPI32!RegDeleteValueW` at `0x180008a57`

## string_xrefs

- `0x18000884b`: `ForceRemove`
- `0x18000893c`: `NoRemove`
- `0x180008839`: `Delete`
- `0x180008ad5`: `Advapi32.dll`
- `0x180008ba9`: `Advapi32.dll`
- `0x180008d9a`: `Advapi32.dll`
- `0x180009096`: `Advapi32.dll`
- `0x180008ae7`: `RegOpenKeyTransactedW`
- `0x180008bbb`: `RegOpenKeyTransactedW`
- `0x180008dac`: `RegOpenKeyTransactedW`
- `0x1800090a8`: `RegDeleteKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  wchar_t *v5; // rdi
  ATL::CRegParser *v6; // r15
  HKEY v7; // r14
  ATL::CAtlTransactionManager *v8; // r13
  int Token; // eax
  int v10; // ebx
  int v11; // r12d
  int v12; // esi
  LPWSTR v13; // rcx
  LPWSTR v14; // rbx
  WCHAR i; // ax
  LPCWSTR *v16; // rbx
  int v17; // esi
  unsigned int v18; // r9d
  LSTATUS v19; // eax
  HKEY v20; // rsi
  unsigned int v21; // edx
  unsigned int v22; // eax
  LPWSTR v23; // rcx
  LPWSTR v24; // rbx
  WCHAR j; // ax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HKEY v28; // rbx
  LSTATUS v29; // eax
  HMODULE v30; // rax
  FARPROC v31; // rax
  LSTATUS v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // edx
  __int64 v35; // rax
  HMODULE v36; // rax
  FARPROC v37; // rax
  LSTATUS v38; // eax
  unsigned int v39; // esi
  int v40; // r15d
  errno_t v41; // eax
  __int64 v42; // rax
  winrt::impl *v43; // rcx
  LPCWSTR *v44; // rsi
  int v45; // esi
  HMODULE v46; // rax
  FARPROC v47; // rax
  winrt::impl *v48; // rcx
  HKEY *phkResult; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v53; // [rsp+38h] [rbp-C8h]
  HKEY lpdwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+70h] [rbp-90h]
  ATL::CRegParser *v57; // [rsp+78h] [rbp-88h]
  HKEY v58; // [rsp+80h] [rbp-80h] BYREF
  HKEY v59; // [rsp+88h] [rbp-78h] BYREF
  int v60; // [rsp+90h] [rbp-70h]
  ATL::CAtlTransactionManager *v61; // [rsp+98h] [rbp-68h]
  HKEY v62; // [rsp+A0h] [rbp-60h] BYREF
  int v63; // [rsp+A8h] [rbp-58h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  wchar_t Destination[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ValueName[4096]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v56 = a4;
  hKey = a3;
  v5 = a2;
  v6 = this;
  v57 = this;
  v7 = 0;
  v59 = 0;
  v60 = 0;
  v8 = 0;
  v61 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_166;
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_157:
        if ( *v5 == 125 )
          goto LABEL_166;
        v11 = 1;
        v12 = lstrcmpiW(v5, L"Delete");
        if ( lstrcmpiW(v5, L"ForceRemove") )
        {
          if ( v12 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v6, v5);
        if ( v10 < 0 )
          goto LABEL_166;
        if ( !v56 )
          break;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v13 = v5;
        v14 = 0;
        for ( i = *v5; i; i = *v13 )
        {
          if ( i == 92 )
          {
            v14 = v13;
            break;
          }
          v13 = CharNextW(v13);
        }
        if ( v14 )
          goto LABEL_165;
        v16 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
        while ( lstrcmpiW(v5, *v16) )
        {
          if ( (__int64)++v16 >= (__int64)&GUID_b91b32b7_27d5_4622_8deb_05db4dbc2558 )
          {
            v62 = hKey;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v62, v5);
            break;
          }
        }
        if ( v12 )
          break;
        v10 = ATL::CRegParser::NextToken(v6, v5);
        if ( v10 < 0 )
          goto LABEL_166;
        v10 = ATL::CRegParser::SkipAssignment(v6, v5);
        if ( v10 < 0 )
          goto LABEL_166;
        v17 = v56;
LABEL_88:
        if ( *v5 == 123 )
        {
          v35 = -1;
          do
            ++v35;
          while ( v5[v35] );
          if ( v35 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v6, v5, v7, v17, 0);
            if ( v10 < 0 )
              goto LABEL_166;
            a2 = v5;
            this = v6;
            goto LABEL_2;
          }
        }
      }
      if ( !lstrcmpiW(v5, L"NoRemove") )
      {
        v11 = 0;
        v10 = ATL::CRegParser::NextToken(v6, v5);
        if ( v10 < 0 )
          goto LABEL_166;
      }
      if ( !lstrcmpiW(v5, L"Val") )
        break;
      v23 = v5;
      v24 = 0;
      for ( j = *v5; j; j = *v23 )
      {
        if ( j == 92 )
        {
          v24 = v23;
          break;
        }
        v23 = CharNextW(v23);
      }
      if ( v24 )
        goto LABEL_165;
      v17 = v56;
      if ( v56 )
      {
        lpdwDisposition = 0;
        if ( v8 )
        {
          if ( *(_QWORD *)v8 )
          {
            ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
            if ( ModuleHandleW )
            {
              ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
              if ( ProcAddress )
              {
                lpSecurityAttributes = 0;
                *(_QWORD *)samDesired = *(_QWORD *)v8;
                phkResult = &lpdwDisposition;
                v28 = hKey;
                v29 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, __int64))ProcAddress)(hKey, v5, 0, 131103);
                goto LABEL_58;
              }
            }
LABEL_56:
            v29 = 1;
            v28 = hKey;
LABEL_58:
            if ( !v29 )
            {
              v29 = 0;
              if ( v7 )
                v29 = RegCloseKey(v7);
              v7 = lpdwDisposition;
              v59 = lpdwDisposition;
              v60 = 0;
            }
            if ( !v29 )
              goto LABEL_84;
            lpdwDisposition = 0;
            if ( v8 )
            {
              if ( *(_QWORD *)v8 )
              {
                v30 = GetModuleHandleW(L"Advapi32.dll");
                if ( v30 )
                {
                  v31 = GetProcAddress(v30, "RegOpenKeyTransactedW");
                  if ( v31 )
                  {
                    lpSecurityAttributes = 0;
                    *(_QWORD *)samDesired = *(_QWORD *)v8;
                    phkResult = &lpdwDisposition;
                    v32 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, __int64))v31)(v28, v5, 0, 131097);
LABEL_71:
                    if ( !v32 )
                    {
                      v32 = 0;
                      if ( v7 )
                        v32 = RegCloseKey(v7);
                      v7 = lpdwDisposition;
                      v59 = lpdwDisposition;
                      v60 = 0;
                    }
                    if ( v32 )
                    {
                      LODWORD(lpdwDisposition) = 0;
                      v58 = 0;
                      if ( v8 )
                        v33 = ATL::CAtlTransactionManager::RegCreateKeyExW(
                                v8,
                                v28,
                                v5,
                                v18,
                                (wchar_t *)phkResult,
                                samDesired[0],
                                lpSecurityAttributes,
                                v53,
                                &v58,
                                (unsigned int *)&lpdwDisposition);
                      else
                        v33 = RegCreateKeyExW(v28, v5, 0, 0, 0, 0x2001Fu, 0, &v58, (LPDWORD)&lpdwDisposition);
                      if ( !v33 )
                      {
                        v33 = 0;
                        if ( v7 )
                          v33 = RegCloseKey(v7);
                        v7 = v58;
                        v59 = v58;
                        v60 = 0;
                      }
                      if ( v33 )
                        goto LABEL_163;
                    }
LABEL_84:
                    v10 = ATL::CRegParser::NextToken(v6, v5);
                    if ( v10 < 0 )
                      goto LABEL_166;
                    if ( *v5 == 61 )
                    {
                      v10 = ATL::CRegParser::AddValue(v6, (struct ATL::CRegKey *)&v59, 0, v5);
                      v7 = v59;
                      if ( v10 < 0 )
                        goto LABEL_166;
                      v8 = v61;
                    }
                    goto LABEL_88;
                  }
                }
LABEL_69:
                v32 = 1;
                goto LABEL_71;
              }
              if ( !*((_DWORD *)v8 + 2) )
                goto LABEL_69;
            }
            v32 = RegOpenKeyExW(v28, v5, 0, 0x20019u, &lpdwDisposition);
            goto LABEL_71;
          }
          if ( !*((_DWORD *)v8 + 2) )
            goto LABEL_56;
        }
        v28 = hKey;
        v29 = RegOpenKeyExW(hKey, v5, 0, 0x2001Fu, &lpdwDisposition);
        goto LABEL_58;
      }
      if ( !a5 )
      {
        lpdwDisposition = 0;
        if ( v8 )
        {
          if ( *(_QWORD *)v8 )
          {
            v36 = GetModuleHandleW(L"Advapi32.dll");
            if ( v36 )
            {
              v37 = GetProcAddress(v36, "RegOpenKeyTransactedW");
              if ( v37 )
              {
                lpSecurityAttributes = 0;
                *(_QWORD *)samDesired = *(_QWORD *)v8;
                phkResult = &lpdwDisposition;
                v38 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, __int64))v37)(hKey, v5, 0, 131097);
                goto LABEL_103;
              }
            }
LABEL_101:
            v39 = 1;
LABEL_104:
            if ( !v39 )
            {
              v39 = 0;
              if ( v7 )
                v39 = RegCloseKey(v7);
              v7 = lpdwDisposition;
              v59 = lpdwDisposition;
              v60 = 0;
            }
            goto LABEL_110;
          }
          if ( !*((_DWORD *)v8 + 2) )
            goto LABEL_101;
        }
        v38 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &lpdwDisposition);
LABEL_103:
        v39 = v38;
        goto LABEL_104;
      }
      v39 = 2;
LABEL_110:
      v40 = 1;
      if ( !v39 )
        v40 = a5;
      v41 = wcsncpy_s(Destination, 0x104u, v5, 0xFFFFFFFFFFFFFFFFuLL);
      if ( v41 )
      {
        if ( v41 == 12 )
          ATL::BaseAtlThrow(-2147024882);
        if ( v41 == 22 || v41 == 34 )
          ATL::BaseAtlThrow(-2147024809);
        if ( v41 != 80 )
          ATL::BaseAtlThrow(-2147467259);
      }
      v10 = ATL::CRegParser::NextToken(v57, v5);
      if ( v10 < 0 )
        goto LABEL_166;
      v10 = ATL::CRegParser::SkipAssignment(v57, v5);
      if ( v10 < 0 )
        goto LABEL_166;
      if ( *v5 != 123 )
        goto LABEL_127;
      v42 = -1;
      do
        ++v42;
      while ( v5[v42] );
      if ( v42 == 1 )
      {
        v10 = ATL::CRegParser::RegisterSubkeys(v57, v5, v7, 0, v40);
        if ( v10 < 0 && !v40 )
          goto LABEL_166;
        v6 = v57;
        v10 = ATL::CRegParser::NextToken(v57, v5);
        if ( v10 < 0 )
          goto LABEL_166;
      }
      else
      {
LABEL_127:
        v6 = v57;
      }
      if ( v39 != 2 )
      {
        if ( v39 )
        {
          if ( !a5 )
          {
            v43 = (winrt::impl *)v39;
LABEL_164:
            v10 = winrt::impl::hresult_from_win32(v43, v34);
            goto LABEL_166;
          }
        }
        else if ( a5
               && (LODWORD(lpdwDisposition) = 0,
                   !RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&lpdwDisposition, 0, 0, 0, 0, 0, 0, 0))
               && (_DWORD)lpdwDisposition )
        {
          v44 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
          while ( lstrcmpiW(Destination, *v44) )
          {
            if ( (__int64)++v44 >= (__int64)&GUID_b91b32b7_27d5_4622_8deb_05db4dbc2558 )
            {
              if ( v11 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v59, Destination);
                v8 = v61;
                v7 = v59;
              }
              goto LABEL_157;
            }
          }
        }
        else
        {
          LODWORD(lpdwDisposition) = 0;
          v45 = 0;
          if ( !RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&lpdwDisposition, 0, 0, 0, 0, 0, 0, 0) )
            LOBYTE(v45) = (_DWORD)lpdwDisposition != 0;
          v33 = 0;
          if ( v7 )
          {
            v33 = RegCloseKey(v7);
            v7 = 0;
            v59 = 0;
          }
          v60 = 0;
          if ( v33
            || v11
            && !v45
            && (`ATL::CRegKey::DeleteSubKey'::`2'::bInitialized
              ? (v47 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx)
              : (FARPROC)((v46 = GetModuleHandleW(L"Advapi32.dll")) == 0
                        ? (v47 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx)
                        : (FARPROC)(v47 = GetProcAddress(v46, "RegDeleteKeyExW"),
                                    `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v47),
                          `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1),
                !v47
              ? (v33 = RegDeleteKeyW(hKey, Destination))
              : (v33 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, _QWORD))v47)(hKey, Destination, 0, 0)),
                v33) )
          {
LABEL_163:
            v43 = (winrt::impl *)v33;
            goto LABEL_164;
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v6, ValueName);
    if ( v10 < 0 )
      goto LABEL_166;
    v10 = ATL::CRegParser::NextToken(v6, v5);
    if ( v10 < 0 )
      goto LABEL_166;
    if ( *v5 != 61 )
    {
LABEL_165:
      v10 = -2147352567;
      goto LABEL_166;
    }
    v17 = v56;
    if ( v56 )
    {
      v62 = hKey;
      v63 = 0;
      v64 = 0;
      v10 = ATL::CRegParser::AddValue(v6, (struct ATL::CRegKey *)&v62, ValueName, v5);
      if ( v10 < 0 )
        goto LABEL_166;
      goto LABEL_88;
    }
    if ( a5 || !v11 )
    {
LABEL_41:
      Token = ATL::CRegParser::SkipAssignment(v6, v5);
      continue;
    }
    break;
  }
  v58 = 0;
  v19 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &v58);
  v20 = 0;
  if ( !v19 )
    v20 = v58;
  v21 = v19 != 0 ? v19 : 0;
  if ( v21 )
  {
    v48 = (winrt::impl *)v21;
  }
  else
  {
    v22 = RegDeleteValueW(v20, ValueName);
    if ( (v22 & 0xFFFFFFFD) == 0 )
    {
      if ( v20 )
        RegCloseKey(v20);
      goto LABEL_41;
    }
    v48 = (winrt::impl *)v22;
  }
  v10 = winrt::impl::hresult_from_win32(v48, v21);
  if ( v20 )
    RegCloseKey(v20);
LABEL_166:
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800087c4  push    rbp
0x1800087c6  push    rbx
0x1800087c7  push    rsi
0x1800087c8  push    rdi
0x1800087c9  push    r12
0x1800087cb  push    r13
0x1800087cd  push    r14
0x1800087cf  push    r15
0x1800087d1  lea     rbp, [rsp-21E8h]
0x1800087d9  mov     eax, 22E8h
0x1800087de  call    _alloca_probe
0x1800087e3  sub     rsp, rax
0x1800087e6  mov     rax, cs:__security_cookie
0x1800087ed  xor     rax, rsp
0x1800087f0  mov     [rbp+2220h+var_50], rax
0x1800087f7  mov     [rsp+2320h+var_22B0], r9d
0x1800087fc  mov     [rsp+2320h+hKey], r8
0x180008801  mov     rdi, rdx
0x180008804  mov     r15, rcx
0x180008807  mov     [rsp+2320h+var_22A8], rcx
0x18000880c  xor     eax, eax
0x18000880e  mov     r14d, eax
0x180008811  mov     [rbp+2220h+var_2298], rax
0x180008815  mov     [rbp+2220h+var_2290], eax
0x180008818  mov     r13d, eax
0x18000881b  mov     [rbp+2220h+var_2288], rax
0x18000881f  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008824  mov     ebx, eax
0x180008826  test    eax, eax
0x180008828  js      loc_180009138
0x18000882e  jmp     loc_1800090FF
0x180008833  mov     r12d, 1
0x180008839  lea     rdx, aDelete; "Delete"
0x180008840  mov     rcx, rdi; lpString1
0x180008843  call    cs:__imp_lstrcmpiW
0x180008849  mov     esi, eax
0x18000884b  lea     rdx, aForceremove; "ForceRemove"
0x180008852  mov     rcx, rdi; lpString1
0x180008855  call    cs:__imp_lstrcmpiW
0x18000885b  test    eax, eax
0x18000885d  jz      short loc_180008867
0x18000885f  test    esi, esi
0x180008861  jnz     loc_18000893C
0x180008867  mov     rdx, rdi; wchar_t *
0x18000886a  mov     rcx, r15; this
0x18000886d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008872  mov     ebx, eax
0x180008874  xor     r8d, r8d
0x180008877  test    eax, eax
0x180008879  js      loc_180009138
0x18000887f  cmp     [rsp+2320h+var_22B0], r8d
0x180008884  jz      loc_18000893C
0x18000888a  mov     [rbp+2220h+var_2280], r8
0x18000888e  mov     [rbp+2220h+var_2278], r8d
0x180008892  mov     [rbp+2220h+var_2270], r8
0x180008896  mov     rcx, rdi
0x180008899  mov     ebx, r8d
0x18000889c  movzx   eax, word ptr [rdi]
0x18000889f  jmp     short loc_1800088B3
0x1800088a1  cmp     ax, 5Ch ; '\'
0x1800088a5  jz      short loc_1800088BA
0x1800088a7  call    cs:__imp_CharNextW
0x1800088ad  mov     rcx, rax; lpsz
0x1800088b0  movzx   eax, word ptr [rax]
0x1800088b3  test    ax, ax
0x1800088b6  jnz     short loc_1800088A1
0x1800088b8  jmp     short loc_1800088BD
0x1800088ba  mov     rbx, rcx
0x1800088bd  test    rbx, rbx
0x1800088c0  jnz     loc_180009133
0x1800088c6  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEB_WB; wchar_t const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800088cd  mov     rdx, [rbx]; lpString2
0x1800088d0  mov     rcx, rdi; lpString1
0x1800088d3  call    cs:__imp_lstrcmpiW
0x1800088d9  test    eax, eax
0x1800088db  jz      short loc_180008902
0x1800088dd  add     rbx, 8
0x1800088e1  lea     rax, _GUID_b91b32b7_27d5_4622_8deb_05db4dbc2558
0x1800088e8  cmp     rbx, rax
0x1800088eb  jl      short loc_1800088CD
0x1800088ed  mov     rax, [rsp+2320h+hKey]
0x1800088f2  mov     [rbp+2220h+var_2280], rax
0x1800088f6  mov     rdx, rdi; wchar_t *
0x1800088f9  lea     rcx, [rbp+2220h+var_2280]; this
0x1800088fd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180008902  test    esi, esi
0x180008904  jnz     short loc_18000893C
0x180008906  mov     rdx, rdi; wchar_t *
0x180008909  mov     rcx, r15; this
0x18000890c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008911  mov     ebx, eax
0x180008913  test    eax, eax
0x180008915  js      loc_180009138
0x18000891b  mov     rdx, rdi; wchar_t *
0x18000891e  mov     rcx, r15; this
0x180008921  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180008926  mov     ebx, eax
0x180008928  xor     r8d, r8d
0x18000892b  test    eax, eax
0x18000892d  js      loc_180009138
0x180008933  mov     esi, [rsp+2320h+var_22B0]
0x180008937  jmp     loc_180008D2F
0x18000893c  lea     rdx, aNoremove; "NoRemove"
0x180008943  mov     rcx, rdi; lpString1
0x180008946  call    cs:__imp_lstrcmpiW
0x18000894c  xor     ecx, ecx
0x18000894e  test    eax, eax
0x180008950  jnz     short loc_18000896A
0x180008952  mov     r12d, ecx
0x180008955  mov     rdx, rdi; wchar_t *
0x180008958  mov     rcx, r15; this
0x18000895b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008960  mov     ebx, eax
0x180008962  test    eax, eax
0x180008964  js      loc_180009138
0x18000896a  lea     rdx, aVal; "Val"
0x180008971  mov     rcx, rdi; lpString1
0x180008974  call    cs:__imp_lstrcmpiW
0x18000897a  xor     r8d, r8d
0x18000897d  test    eax, eax
0x18000897f  jnz     loc_180008A86
0x180008985  lea     rdx, [rbp+2220h+ValueName]; wchar_t *
0x18000898c  mov     rcx, r15; this
0x18000898f  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180008994  mov     ebx, eax
0x180008996  test    eax, eax
0x180008998  js      loc_180009138
0x18000899e  mov     rdx, rdi; wchar_t *
0x1800089a1  mov     rcx, r15; this
0x1800089a4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800089a9  mov     ebx, eax
0x1800089ab  xor     r8d, r8d
0x1800089ae  test    eax, eax
0x1800089b0  js      loc_180009138
0x1800089b6  cmp     word ptr [rdi], 3Dh ; '='
0x1800089ba  jnz     loc_180009133
0x1800089c0  mov     esi, [rsp+2320h+var_22B0]
0x1800089c4  test    esi, esi
0x1800089c6  jz      short loc_180008A01
0x1800089c8  mov     rax, [rsp+2320h+hKey]
0x1800089cd  mov     [rbp+2220h+var_2280], rax
0x1800089d1  mov     [rbp+2220h+var_2278], r8d
0x1800089d5  mov     [rbp+2220h+var_2270], r8
0x1800089d9  mov     r9, rdi; wchar_t *
0x1800089dc  lea     r8, [rbp+2220h+ValueName]; wchar_t *
0x1800089e3  lea     rdx, [rbp+2220h+var_2280]; struct ATL::CRegKey *
0x1800089e7  mov     rcx, r15; this
0x1800089ea  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x1800089ef  mov     ebx, eax
0x1800089f1  xor     r8d, r8d
0x1800089f4  test    eax, eax
0x1800089f6  js      loc_180009138
0x1800089fc  jmp     loc_180008D2F
0x180008a01  cmp     [rbp+2220h+arg_20], r8d
0x180008a08  jnz     short loc_180008A76
0x180008a0a  test    r12d, r12d
0x180008a0d  jz      short loc_180008A76
0x180008a0f  mov     [rbp+2220h+var_22A0], r8
0x180008a13  lea     rax, [rbp+2220h+var_22A0]
0x180008a17  mov     [rsp+2320h+phkResult], rax; phkResult
0x180008a1c  mov     r9d, 20006h; samDesired
0x180008a22  xor     r8d, r8d; ulOptions
0x180008a25  xor     edx, edx; lpSubKey
0x180008a27  mov     rcx, [rsp+2320h+hKey]; hKey
0x180008a2c  call    cs:__imp_RegOpenKeyExW
0x180008a32  mov     ecx, eax
0x180008a34  xor     r8d, r8d
0x180008a37  mov     esi, r8d
0x180008a3a  test    eax, eax
0x180008a3c  cmovz   rsi, [rbp+2220h+var_22A0]
0x180008a41  neg     eax
0x180008a43  sbb     edx, edx
0x180008a45  and     edx, ecx; unsigned int
0x180008a47  jnz     loc_18000910F
0x180008a4d  lea     rdx, [rbp+2220h+ValueName]; lpValueName
0x180008a54  mov     rcx, rsi; hKey
0x180008a57  call    cs:__imp_RegDeleteValueW
0x180008a5d  test    eax, 0FFFFFFFDh
0x180008a62  jnz     loc_18000910B
0x180008a68  test    rsi, rsi
0x180008a6b  jz      short loc_180008A76
0x180008a6d  mov     rcx, rsi; hKey
0x180008a70  call    cs:__imp_RegCloseKey
0x180008a76  mov     rdx, rdi; wchar_t *
0x180008a79  mov     rcx, r15; this
0x180008a7c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180008a81  jmp     loc_180008824
0x180008a86  mov     rcx, rdi
0x180008a89  mov     rbx, r8
0x180008a8c  movzx   eax, word ptr [rdi]
0x180008a8f  jmp     short loc_180008AA6
0x180008a91  cmp     ax, 5Ch ; '\'
0x180008a95  jz      short loc_180008AAD
0x180008a97  call    cs:__imp_CharNextW
0x180008a9d  mov     rcx, rax; lpsz
0x180008aa0  movzx   eax, word ptr [rax]
0x180008aa3  xor     r8d, r8d
0x180008aa6  test    ax, ax
0x180008aa9  jnz     short loc_180008A91
0x180008aab  jmp     short loc_180008AB0
0x180008aad  mov     rbx, rcx
0x180008ab0  test    rbx, rbx
0x180008ab3  jnz     loc_180009133
0x180008ab9  mov     esi, [rsp+2320h+var_22B0]
0x180008abd  test    esi, esi
0x180008abf  jz      loc_180008D7C
0x180008ac5  mov     [rsp+2320h+var_22C0], r8
0x180008aca  test    r13, r13
0x180008acd  jz      short loc_180008B48
0x180008acf  cmp     [r13+0], r8
0x180008ad3  jz      short loc_180008B36
0x180008ad5  lea     rcx, ModuleName; "Advapi32.dll"
0x180008adc  call    cs:__imp_GetModuleHandleW
0x180008ae2  test    rax, rax
0x180008ae5  jz      short loc_180008B3C
0x180008ae7  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180008aee  mov     rcx, rax; hModule
0x180008af1  call    cs:__imp_GetProcAddress
0x180008af7  mov     r10, rax
0x180008afa  xor     r8d, r8d
0x180008afd  test    rax, rax
0x180008b00  jz      short loc_180008B3C
0x180008b02  mov     [rsp+2320h+lpSecurityAttributes], r8
0x180008b07  mov     rax, [r13+0]
0x180008b0b  mov     qword ptr [rsp+2320h+samDesired], rax
0x180008b10  lea     rax, [rsp+2320h+var_22C0]
0x180008b15  mov     [rsp+2320h+phkResult], rax
0x180008b1a  mov     r9d, 2001Fh
0x180008b20  mov     rdx, rdi
0x180008b23  mov     rbx, [rsp+2320h+hKey]
0x180008b28  mov     rcx, rbx
0x180008b2b  mov     rax, r10
0x180008b2e  call    cs:__guard_dispatch_icall_fptr
0x180008b34  jmp     short loc_180008B6C
0x180008b36  cmp     [r13+8], r8d
0x180008b3a  jnz     short loc_180008B48
0x180008b3c  mov     eax, 1
0x180008b41  mov     rbx, [rsp+2320h+hKey]
0x180008b46  jmp     short loc_180008B6C
0x180008b48  lea     rax, [rsp+2320h+var_22C0]
0x180008b4d  mov     rbx, [rsp+2320h+hKey]
0x180008b52  mov     [rsp+2320h+phkResult], rax; phkResult
0x180008b57  mov     r9d, 2001Fh; samDesired
0x180008b5d  xor     r8d, r8d; ulOptions
0x180008b60  mov     rdx, rdi; lpSubKey
0x180008b63  mov     rcx, rbx; hKey
0x180008b66  call    cs:__imp_RegOpenKeyExW
0x180008b6c  xor     r12d, r12d
0x180008b6f  test    eax, eax
0x180008b71  jnz     short loc_180008B91
0x180008b73  mov     eax, r12d
0x180008b76  test    r14, r14
0x180008b79  jz      short loc_180008B84
0x180008b7b  mov     rcx, r14; hKey
0x180008b7e  call    cs:__imp_RegCloseKey
0x180008b84  mov     r14, [rsp+2320h+var_22C0]
0x180008b89  mov     [rbp+2220h+var_2298], r14
0x180008b8d  mov     [rbp+2220h+var_2290], r12d
0x180008b91  test    eax, eax
0x180008b93  jz      loc_180008CED
0x180008b99  mov     [rsp+2320h+var_22C0], r12
0x180008b9e  test    r13, r13
0x180008ba1  jz      short loc_180008C12
0x180008ba3  cmp     [r13+0], r12
0x180008ba7  jz      short loc_180008C05
0x180008ba9  lea     rcx, ModuleName; "Advapi32.dll"
0x180008bb0  call    cs:__imp_GetModuleHandleW
0x180008bb6  test    rax, rax
0x180008bb9  jz      short loc_180008C0B
0x180008bbb  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180008bc2  mov     rcx, rax; hModule
0x180008bc5  call    cs:__imp_GetProcAddress
0x180008bcb  mov     r10, rax
0x180008bce  test    rax, rax
0x180008bd1  jz      short loc_180008C0B
0x180008bd3  mov     [rsp+2320h+lpSecurityAttributes], r12
0x180008bd8  mov     rax, [r13+0]
0x180008bdc  mov     qword ptr [rsp+2320h+samDesired], rax
0x180008be1  lea     rax, [rsp+2320h+var_22C0]
0x180008be6  mov     [rsp+2320h+phkResult], rax
0x180008beb  mov     r9d, 20019h
0x180008bf1  xor     r8d, r8d
0x180008bf4  mov     rdx, rdi
0x180008bf7  mov     rcx, rbx
0x180008bfa  mov     rax, r10
0x180008bfd  call    cs:__guard_dispatch_icall_fptr
0x180008c03  jmp     short loc_180008C31
0x180008c05  cmp     [r13+8], r12d
0x180008c09  jnz     short loc_180008C12
0x180008c0b  mov     eax, 1
0x180008c10  jmp     short loc_180008C31
0x180008c12  lea     rax, [rsp+2320h+var_22C0]
0x180008c17  mov     [rsp+2320h+phkResult], rax; wchar_t *
0x180008c1c  mov     r9d, 20019h; samDesired
0x180008c22  xor     r8d, r8d; ulOptions
0x180008c25  mov     rdx, rdi; lpSubKey
0x180008c28  mov     rcx, rbx; hKey
0x180008c2b  call    cs:__imp_RegOpenKeyExW
0x180008c31  test    eax, eax
0x180008c33  jnz     short loc_180008C53
  ... truncated ...
```
