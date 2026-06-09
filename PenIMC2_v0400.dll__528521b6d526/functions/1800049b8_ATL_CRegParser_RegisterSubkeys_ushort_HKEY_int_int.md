# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800049b8`
- end: `0x180005453`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2715`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800049b8`
- `0x180005454`

## callees

- `0x180003d7c`
- `0x180003ea0`
- `0x180004484`
- `0x1800044a8`
- `0x180004550`
- `0x1800047ec`
- `0x1800047fc`
- `0x1800049b8`
- `0x18000cdb0`
- `0x18000e430`
- `0x18000e4a0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180005381`
- `ADVAPI32!RegDeleteKeyW` at `0x180005381`
- `ADVAPI32!RegCloseKey` at `0x180004cb6`
- `ADVAPI32!RegCloseKey` at `0x180004dbf`
- `ADVAPI32!RegCloseKey` at `0x180004e90`
- `ADVAPI32!RegCloseKey` at `0x180004f2a`
- `ADVAPI32!RegCloseKey` at `0x1800050a7`
- `ADVAPI32!RegCloseKey` at `0x1800052d4`
- `ADVAPI32!RegCloseKey` at `0x1800053c2`
- `ADVAPI32!RegCloseKey` at `0x1800053fd`
- `ADVAPI32!RegCloseKey` at `0x180004cb6`
- `ADVAPI32!RegCloseKey` at `0x180004dbf`
- `ADVAPI32!RegCloseKey` at `0x180004e90`
- `ADVAPI32!RegCloseKey` at `0x180004f2a`
- `ADVAPI32!RegCloseKey` at `0x1800050a7`
- `ADVAPI32!RegCloseKey` at `0x1800052d4`
- `ADVAPI32!RegCloseKey` at `0x1800053c2`
- `ADVAPI32!RegCloseKey` at `0x1800053fd`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005211`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800052b4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005211`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800052b4`
- `ADVAPI32!RegOpenKeyExW` at `0x180004c72`
- `ADVAPI32!RegOpenKeyExW` at `0x180004da9`
- `ADVAPI32!RegOpenKeyExW` at `0x180004e7c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000508f`
- `ADVAPI32!RegOpenKeyExW` at `0x180004c72`
- `ADVAPI32!RegOpenKeyExW` at `0x180004da9`
- `ADVAPI32!RegOpenKeyExW` at `0x180004e7c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000508f`
- `ADVAPI32!RegCreateKeyExW` at `0x180004f10`
- `ADVAPI32!RegCreateKeyExW` at `0x180004f10`
- `ADVAPI32!RegDeleteValueW` at `0x180004c9b`
- `ADVAPI32!RegDeleteValueW` at `0x180004c9b`
- `KERNEL32!GetProcAddress` at `0x180004d3d`
- `KERNEL32!GetProcAddress` at `0x180004e12`
- `KERNEL32!GetProcAddress` at `0x180005023`
- `KERNEL32!GetProcAddress` at `0x18000533f`
- `KERNEL32!GetProcAddress` at `0x180004d3d`
- `KERNEL32!GetProcAddress` at `0x180004e12`
- `KERNEL32!GetProcAddress` at `0x180005023`
- `KERNEL32!GetProcAddress` at `0x18000533f`
- `KERNEL32!GetModuleHandleW` at `0x180004d22`
- `KERNEL32!GetModuleHandleW` at `0x180004df9`
- `KERNEL32!GetModuleHandleW` at `0x180005006`
- `KERNEL32!GetModuleHandleW` at `0x18000532a`
- `KERNEL32!GetModuleHandleW` at `0x180004d22`
- `KERNEL32!GetModuleHandleW` at `0x180004df9`
- `KERNEL32!GetModuleHandleW` at `0x180005006`
- `KERNEL32!GetModuleHandleW` at `0x18000532a`
- `KERNEL32!lstrcmpiW` at `0x180004a3e`
- `KERNEL32!lstrcmpiW` at `0x180004a58`
- `KERNEL32!lstrcmpiW` at `0x180004acf`
- `KERNEL32!lstrcmpiW` at `0x180004b65`
- `KERNEL32!lstrcmpiW` at `0x180004b93`
- `KERNEL32!lstrcmpiW` at `0x180005231`
- `KERNEL32!lstrcmpiW` at `0x180004a3e`
- `KERNEL32!lstrcmpiW` at `0x180004a58`
- `KERNEL32!lstrcmpiW` at `0x180004acf`
- `KERNEL32!lstrcmpiW` at `0x180004b65`
- `KERNEL32!lstrcmpiW` at `0x180004b93`
- `KERNEL32!lstrcmpiW` at `0x180005231`
- `ucrtbase_clr0400!wcsncpy_s` at `0x1800050e9`
- `ucrtbase_clr0400!wcsncpy_s` at `0x1800050e9`
- `USER32!CharNextW` at `0x180004aa4`
- `USER32!CharNextW` at `0x180004ce1`
- `USER32!CharNextW` at `0x180004aa4`
- `USER32!CharNextW` at `0x180004ce1`

## string_xrefs

- `0x180004a34`: `Delete`
- `0x180004a4e`: `ForceRemove`
- `0x180004b5b`: `NoRemove`
- `0x180004add`: `RegOpenKeyTransactedW`
- `0x180004d33`: `RegOpenKeyTransactedW`
- `0x180004e08`: `RegOpenKeyTransactedW`
- `0x180005019`: `RegOpenKeyTransactedW`
- `0x180005245`: `RegOpenKeyTransactedW`
- `0x180004d1b`: `Advapi32.dll`
- `0x180004df2`: `Advapi32.dll`
- `0x180004fff`: `Advapi32.dll`
- `0x180005323`: `Advapi32.dll`
- `0x180005335`: `RegDeleteKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  unsigned __int16 *v5; // rdi
  ATL::CRegParser *v6; // r15
  HKEY v7; // r14
  ATL::CAtlTransactionManager *v8; // r13
  int Token; // eax
  int v10; // edx
  int v11; // ebx
  int v12; // r12d
  BOOL v13; // esi
  const WCHAR *v14; // rcx
  WCHAR v15; // ax
  LPCWSTR *v16; // rbx
  int v17; // esi
  int v18; // eax
  unsigned int v19; // r9d
  LSTATUS v20; // eax
  HKEY v21; // rsi
  LSTATUS v22; // eax
  const WCHAR *v23; // rcx
  WCHAR v24; // ax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  HMODULE v29; // rax
  FARPROC v30; // rax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  __int64 v34; // rax
  HMODULE v35; // rax
  LSTATUS v36; // esi
  FARPROC v37; // rax
  LSTATUS v38; // eax
  int v39; // r15d
  errno_t v40; // eax
  __int64 v41; // rax
  unsigned int v42; // ecx
  LPCWSTR *v43; // rsi
  int v44; // eax
  LSTATUS InfoKeyW; // eax
  int v46; // esi
  HKEY v47; // rcx
  HMODULE v48; // rax
  FARPROC v49; // rax
  LSTATUS v50; // eax
  HKEY *phkResult; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v55; // [rsp+38h] [rbp-C8h]
  HKEY v56; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  int v58; // [rsp+70h] [rbp-90h]
  HKEY v59; // [rsp+78h] [rbp-88h] BYREF
  int v60; // [rsp+80h] [rbp-80h]
  ATL::CAtlTransactionManager *v61; // [rsp+88h] [rbp-78h]
  ATL::CRegParser *v62; // [rsp+90h] [rbp-70h]
  HKEY v63; // [rsp+98h] [rbp-68h] BYREF
  int v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  DWORD dwDisposition; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v67; // [rsp+B8h] [rbp-48h] BYREF
  int v68; // [rsp+C0h] [rbp-40h]
  __int64 v69; // [rsp+C8h] [rbp-38h]
  HKEY v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  HKEY v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  wchar_t Destination[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR ValueName[4096]; // [rsp+310h] [rbp+210h] BYREF

  v58 = a4;
  hKey = a3;
  v5 = a2;
  v6 = this;
  v62 = this;
  v7 = 0;
  v59 = 0;
  v60 = 0;
  v8 = 0;
  v61 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = 0;
    v11 = Token;
    if ( Token < 0 )
      goto LABEL_163;
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_4:
        if ( *v5 == 125 )
          goto LABEL_163;
        v12 = 1;
        v13 = lstrcmpiW(v5, L"Delete") == 0;
        if ( lstrcmpiW(v5, L"ForceRemove") )
        {
          if ( !v13 )
            break;
        }
        v11 = ATL::CRegParser::NextToken(v6, v5);
        v10 = 0;
        if ( v11 < 0 )
          goto LABEL_163;
        if ( !v58 )
          break;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v14 = v5;
        v15 = *v5;
        while ( v15 )
        {
          if ( v15 == 92 )
          {
            if ( v14 )
            {
              v64 = 0;
              goto LABEL_154;
            }
            break;
          }
          v14 = CharNextW(v14);
          v15 = *v14;
          v10 = 0;
        }
        v16 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
        while ( lstrcmpiW(v5, *v16) )
        {
          if ( (__int64)++v16 >= (__int64)"RegOpenKeyTransactedW" )
          {
            v63 = hKey;
            v64 = 0;
            v65 = 0;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v63, v5);
            v63 = 0;
            v64 = 0;
            v65 = 0;
            break;
          }
        }
        if ( !v13 )
        {
          v64 = 0;
          break;
        }
        v11 = ATL::CRegParser::NextToken(v6, v5);
        v10 = 0;
        if ( v11 < 0 )
        {
          v64 = 0;
          goto LABEL_163;
        }
        v11 = ATL::CRegParser::SkipAssignment(v6, v5);
        v10 = 0;
        v64 = 0;
        if ( v11 < 0 )
          goto LABEL_163;
        v17 = v58;
LABEL_83:
        if ( *v5 == 123 )
        {
          v34 = -1;
          do
            ++v34;
          while ( v5[v34] );
          if ( v34 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(v6, v5, v7, v17, 0);
            v10 = 0;
            if ( v11 < 0 )
              goto LABEL_163;
            a2 = v5;
            this = v6;
            goto LABEL_2;
          }
        }
      }
      if ( !lstrcmpiW(v5, L"NoRemove") )
      {
        v12 = 0;
        v11 = ATL::CRegParser::NextToken(v6, v5);
        v10 = 0;
        if ( v11 < 0 )
          goto LABEL_163;
      }
      v18 = lstrcmpiW(v5, L"Val");
      v10 = 0;
      if ( !v18 )
        break;
      v23 = v5;
      v24 = *v5;
      while ( v24 )
      {
        if ( v24 == 92 )
        {
          if ( v23 )
            goto LABEL_154;
          break;
        }
        v23 = CharNextW(v23);
        v24 = *v23;
        v10 = 0;
      }
      v17 = v58;
      if ( v58 )
      {
        v56 = 0;
        if ( v8 )
        {
          if ( *(_QWORD *)v8 )
          {
            ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
            if ( !ModuleHandleW )
              goto LABEL_60;
            ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
            if ( ProcAddress )
            {
              lpSecurityAttributes = 0;
              *(_QWORD *)samDesired = *(_QWORD *)v8;
              phkResult = &v56;
              v27 = ((__int64 (__fastcall *)(HKEY, unsigned __int16 *, _QWORD, __int64))ProcAddress)(
                      hKey,
                      v5,
                      0,
                      131103);
LABEL_56:
              if ( !v27 )
              {
                v28 = 0;
                if ( v7 )
                {
                  v28 = RegCloseKey(v7);
                  v59 = 0;
                }
                v7 = v56;
                v59 = v56;
                v60 = 0;
                if ( !v28 )
                  goto LABEL_79;
              }
LABEL_60:
              v56 = 0;
              if ( v8 )
              {
                if ( *(_QWORD *)v8 )
                {
                  v29 = GetModuleHandleW(L"Advapi32.dll");
                  if ( !v29 )
                    goto LABEL_72;
                  v30 = GetProcAddress(v29, "RegOpenKeyTransactedW");
                  if ( v30 )
                  {
                    lpSecurityAttributes = 0;
                    *(_QWORD *)samDesired = *(_QWORD *)v8;
                    phkResult = &v56;
                    v31 = ((__int64 (__fastcall *)(HKEY, unsigned __int16 *, _QWORD, __int64))v30)(hKey, v5, 0, 131097);
LABEL_68:
                    if ( v31 )
                      goto LABEL_72;
                    v32 = 0;
                    if ( v7 )
                    {
                      v32 = RegCloseKey(v7);
                      v59 = 0;
                    }
                    v7 = v56;
                    v59 = v56;
                    v60 = 0;
                    if ( v32 )
                    {
LABEL_72:
                      v56 = 0;
                      if ( v8 )
                        v33 = ATL::CAtlTransactionManager::RegCreateKeyExW(
                                v8,
                                hKey,
                                v5,
                                v19,
                                (unsigned __int16 *)phkResult,
                                samDesired[0],
                                lpSecurityAttributes,
                                v55,
                                &v56,
                                &dwDisposition);
                      else
                        v33 = RegCreateKeyExW(hKey, v5, 0, 0, 0, 0x2001Fu, 0, &v56, &dwDisposition);
                      if ( v33 )
                        goto LABEL_161;
                      v33 = 0;
                      if ( v7 )
                      {
                        v33 = RegCloseKey(v7);
                        v59 = 0;
                      }
                      v7 = v56;
                      v59 = v56;
                      v60 = 0;
                      if ( v33 )
                        goto LABEL_161;
                    }
LABEL_79:
                    v11 = ATL::CRegParser::NextToken(v6, v5);
                    v10 = 0;
                    if ( v11 < 0 )
                      goto LABEL_163;
                    if ( *v5 == 61 )
                    {
                      v11 = ATL::CRegParser::AddValue(v6, (struct ATL::CRegKey *)&v59, 0, v5);
                      v10 = 0;
                      v7 = v59;
                      if ( v11 < 0 )
                        goto LABEL_163;
                      v8 = v61;
                    }
                    goto LABEL_83;
                  }
LABEL_66:
                  v31 = 1;
                  goto LABEL_68;
                }
                if ( !*((_DWORD *)v8 + 2) )
                  goto LABEL_66;
              }
              v31 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &v56);
              goto LABEL_68;
            }
LABEL_54:
            v27 = 1;
            goto LABEL_56;
          }
          if ( !*((_DWORD *)v8 + 2) )
            goto LABEL_54;
        }
        v27 = RegOpenKeyExW(hKey, v5, 0, 0x2001Fu, &v56);
        goto LABEL_56;
      }
      if ( a5 )
      {
        v36 = 2;
      }
      else
      {
        v56 = 0;
        if ( !v8 )
          goto LABEL_98;
        if ( !*(_QWORD *)v8 )
        {
          if ( !*((_DWORD *)v8 + 2) )
          {
LABEL_97:
            v36 = 1;
            goto LABEL_100;
          }
LABEL_98:
          v38 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &v56);
LABEL_99:
          v36 = v38;
LABEL_100:
          if ( !v36 )
          {
            v36 = 0;
            if ( v7 )
            {
              v36 = RegCloseKey(v7);
              v59 = 0;
            }
            v7 = v56;
            v59 = v56;
            v60 = 0;
          }
          goto LABEL_105;
        }
        v35 = GetModuleHandleW(L"Advapi32.dll");
        if ( v35 )
        {
          v37 = GetProcAddress(v35, "RegOpenKeyTransactedW");
          if ( !v37 )
            goto LABEL_97;
          lpSecurityAttributes = 0;
          *(_QWORD *)samDesired = *(_QWORD *)v8;
          phkResult = &v56;
          v38 = ((__int64 (__fastcall *)(HKEY, unsigned __int16 *, _QWORD, __int64))v37)(hKey, v5, 0, 131097);
          goto LABEL_99;
        }
        v36 = a5 + 1;
      }
LABEL_105:
      v39 = 1;
      if ( !v36 )
        v39 = a5;
      v40 = wcsncpy_s(Destination, 0x104u, v5, 0xFFFFFFFFFFFFFFFFuLL);
      if ( v40 )
      {
        if ( v40 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v40 == 22 || v40 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v40 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v11 = ATL::CRegParser::NextToken(v62, v5);
      v10 = 0;
      if ( v11 < 0 )
        goto LABEL_163;
      v11 = ATL::CRegParser::SkipAssignment(v62, v5);
      v10 = 0;
      if ( v11 < 0 )
        goto LABEL_163;
      if ( *v5 != 123 )
        goto LABEL_122;
      v41 = -1;
      do
        ++v41;
      while ( v5[v41] );
      if ( v41 == 1 )
      {
        v11 = ATL::CRegParser::RegisterSubkeys(v62, v5, v7, 0, v39);
        v10 = 0;
        if ( v11 < 0 && !v39 )
          goto LABEL_163;
        v6 = v62;
        v11 = ATL::CRegParser::NextToken(v62, v5);
        v10 = 0;
        if ( v11 < 0 )
          goto LABEL_163;
      }
      else
      {
LABEL_122:
        v6 = v62;
      }
      if ( v36 != 2 )
      {
        if ( v36 )
        {
          if ( !a5 )
          {
            v42 = v36;
LABEL_162:
            v11 = ATL::AtlHresultFromWin32(v42);
            goto LABEL_163;
          }
        }
        else if ( a5
               && (LODWORD(v56) = 0, !RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&v56, 0, 0, 0, 0, 0, 0, 0))
               && (_DWORD)v56 )
        {
          v43 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
          while ( 1 )
          {
            v44 = lstrcmpiW(Destination, *v43);
            v10 = 0;
            if ( !v44 )
              break;
            if ( (__int64)++v43 >= (__int64)"RegOpenKeyTransactedW" )
            {
              if ( v12 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v59, Destination);
                v8 = v61;
                v7 = v59;
                v10 = 0;
              }
              goto LABEL_4;
            }
          }
        }
        else
        {
          LODWORD(v56) = 0;
          InfoKeyW = RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&v56, 0, 0, 0, 0, 0, 0, 0);
          v10 = 0;
          v46 = 0;
          if ( !InfoKeyW )
            LOBYTE(v46) = (_DWORD)v56 != 0;
          v33 = 0;
          if ( v7 )
          {
            v33 = RegCloseKey(v7);
            v10 = 0;
            v7 = 0;
            v59 = 0;
          }
          v60 = 0;
          if ( v33 )
          {
LABEL_161:
            v42 = v33;
            goto LABEL_162;
          }
          if ( v12 && !v46 )
          {
            v47 = hKey;
            v73 = hKey;
            v74 = 0;
            v75 = 0;
            if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
            {
              v49 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
            }
            else
            {
              v48 = GetModuleHandleW(L"Advapi32.dll");
              if ( v48 )
              {
                v49 = GetProcAddress(v48, "RegDeleteKeyExW");
                `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v49;
              }
              else
              {
                v49 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
              }
              `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
              v47 = hKey;
            }
            if ( v49 )
              v50 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, _QWORD))v49)(v47, Destination, 0, 0);
            else
              v50 = RegDeleteKeyW(v47, Destination);
            v10 = 0;
            v73 = 0;
            v74 = 0;
            v75 = 0;
            if ( v50 )
            {
              v11 = ATL::AtlHresultFromWin32(v50);
              v74 = v10;
              goto LABEL_163;
            }
            v74 = 0;
          }
        }
      }
    }
    v11 = ATL::CRegParser::NextToken(v6, ValueName);
    v10 = 0;
    if ( v11 < 0 )
      goto LABEL_163;
    v11 = ATL::CRegParser::NextToken(v6, v5);
    v10 = 0;
    if ( v11 < 0 )
      goto LABEL_163;
    if ( *v5 != 61 )
    {
LABEL_154:
      v11 = -2147352567;
      goto LABEL_163;
    }
    v17 = v58;
    if ( v58 )
    {
      v67 = hKey;
      v68 = 0;
      v69 = 0;
      v11 = ATL::CRegParser::AddValue(v6, (struct ATL::CRegKey *)&v67, ValueName, v5);
      v10 = 0;
      v67 = 0;
      v69 = 0;
      v68 = 0;
      if ( v11 < 0 )
        goto LABEL_163;
      goto LABEL_83;
    }
    if ( a5 || !v12 )
    {
LABEL_40:
      Token = ATL::CRegParser::SkipAssignment(v6, v5);
      continue;
    }
    break;
  }
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v56 = 0;
  v20 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &v56);
  if ( v20 )
  {
    v11 = ATL::AtlHresultFromWin32(v20);
  }
  else
  {
    v21 = v56;
    v70 = v56;
    v71 = 0;
    v22 = RegDeleteValueW(v56, ValueName);
    if ( (v22 & 0xFFFFFFFD) == 0 )
    {
      if ( v21 )
      {
        RegCloseKey(v21);
        v70 = 0;
      }
      v71 = 0;
      goto LABEL_40;
    }
    v11 = ATL::AtlHresultFromWin32(v22);
    v10 = 0;
    if ( v21 )
    {
      RegCloseKey(v21);
      v10 = 0;
      v70 = 0;
    }
  }
  v71 = v10;
LABEL_163:
  if ( v7 )
  {
    RegCloseKey(v7);
    v10 = 0;
    v59 = 0;
  }
  v60 = v10;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800049b8  push    rbp
0x1800049ba  push    rbx
0x1800049bb  push    rsi
0x1800049bc  push    rdi
0x1800049bd  push    r12
0x1800049bf  push    r13
0x1800049c1  push    r14
0x1800049c3  push    r15
0x1800049c5  lea     rbp, [rsp-2228h]
0x1800049cd  mov     eax, 2328h
0x1800049d2  call    _alloca_probe
0x1800049d7  sub     rsp, rax
0x1800049da  mov     rax, cs:__security_cookie
0x1800049e1  xor     rax, rsp
0x1800049e4  mov     [rbp+2260h+var_50], rax
0x1800049eb  mov     [rsp+2360h+var_22F0], r9d
0x1800049f0  mov     [rsp+2360h+hKey], r8
0x1800049f5  mov     rdi, rdx
0x1800049f8  mov     r15, rcx
0x1800049fb  mov     [rbp+2260h+var_22D0], rcx
0x1800049ff  xor     eax, eax
0x180004a01  mov     r14d, eax
0x180004a04  mov     [rsp+2360h+var_22E8], rax
0x180004a09  mov     [rbp+2260h+var_22E0], eax
0x180004a0c  mov     r13d, eax
0x180004a0f  mov     [rbp+2260h+var_22D8], rax
0x180004a13  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a18  xor     edx, edx
0x180004a1a  test    eax, eax
0x180004a1c  mov     ebx, eax
0x180004a1e  js      loc_1800053F5
0x180004a24  cmp     word ptr [rdi], 7Dh ; '}'
0x180004a28  jz      loc_1800053F5
0x180004a2e  mov     r12d, 1
0x180004a34  lea     rdx, aDelete; "Delete"
0x180004a3b  mov     rcx, rdi; lpString1
0x180004a3e  call    cs:__imp_lstrcmpiW
0x180004a44  xor     ebx, ebx
0x180004a46  mov     esi, ebx
0x180004a48  test    eax, eax
0x180004a4a  setz    sil
0x180004a4e  lea     rdx, aForceremove; "ForceRemove"
0x180004a55  mov     rcx, rdi; lpString1
0x180004a58  call    cs:__imp_lstrcmpiW
0x180004a5e  test    eax, eax
0x180004a60  jz      short loc_180004A6A
0x180004a62  test    esi, esi
0x180004a64  jz      loc_180004B5B
0x180004a6a  mov     rdx, rdi; unsigned __int16 *
0x180004a6d  mov     rcx, r15; this
0x180004a70  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a75  mov     ebx, eax
0x180004a77  xor     edx, edx
0x180004a79  test    eax, eax
0x180004a7b  js      loc_1800053F5
0x180004a81  cmp     [rsp+2360h+var_22F0], edx
0x180004a85  jz      loc_180004B59
0x180004a8b  mov     [rbp+2260h+var_22C8], rdx
0x180004a8f  mov     [rbp+2260h+var_22C0], edx
0x180004a92  mov     [rbp+2260h+var_22B8], rdx
0x180004a96  mov     rcx, rdi
0x180004a99  movzx   eax, word ptr [rdi]
0x180004a9c  jmp     short loc_180004AB2
0x180004a9e  cmp     ax, 5Ch ; '\'
0x180004aa2  jz      short loc_180004AB9
0x180004aa4  call    cs:__imp_CharNextW
0x180004aaa  mov     rcx, rax; lpsz
0x180004aad  movzx   eax, word ptr [rax]
0x180004ab0  xor     edx, edx
0x180004ab2  test    ax, ax
0x180004ab5  jnz     short loc_180004A9E
0x180004ab7  jmp     short loc_180004AC2
0x180004ab9  test    rcx, rcx
0x180004abc  jnz     loc_1800053A0
0x180004ac2  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004ac9  mov     rdx, [rbx]; lpString2
0x180004acc  mov     rcx, rdi; lpString1
0x180004acf  call    cs:__imp_lstrcmpiW
0x180004ad5  test    eax, eax
0x180004ad7  jz      short loc_180004B14
0x180004ad9  add     rbx, 8
0x180004add  lea     rax, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180004ae4  cmp     rbx, rax
0x180004ae7  jl      short loc_180004AC9
0x180004ae9  mov     rax, [rsp+2360h+hKey]
0x180004aee  mov     [rbp+2260h+var_22C8], rax
0x180004af2  xor     ebx, ebx
0x180004af4  mov     [rbp+2260h+var_22C0], ebx
0x180004af7  mov     [rbp+2260h+var_22B8], rbx
0x180004afb  mov     rdx, rdi; unsigned __int16 *
0x180004afe  lea     rcx, [rbp+2260h+var_22C8]; this
0x180004b02  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b07  mov     [rbp+2260h+var_22C8], rbx
0x180004b0b  mov     [rbp+2260h+var_22C0], ebx
0x180004b0e  mov     [rbp+2260h+var_22B8], rbx
0x180004b12  jmp     short loc_180004B16
0x180004b14  xor     ebx, ebx
0x180004b16  test    esi, esi
0x180004b18  jz      short loc_180004B54
0x180004b1a  mov     rdx, rdi; unsigned __int16 *
0x180004b1d  mov     rcx, r15; this
0x180004b20  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b25  mov     ebx, eax
0x180004b27  xor     edx, edx
0x180004b29  test    eax, eax
0x180004b2b  js      loc_1800053AA
0x180004b31  mov     rdx, rdi; unsigned __int16 *
0x180004b34  mov     rcx, r15; this
0x180004b37  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004b3c  mov     ebx, eax
0x180004b3e  xor     edx, edx
0x180004b40  mov     [rbp+2260h+var_22C0], edx
0x180004b43  test    eax, eax
0x180004b45  js      loc_1800053F5
0x180004b4b  mov     esi, [rsp+2360h+var_22F0]
0x180004b4f  jmp     loc_180004F94
0x180004b54  mov     [rbp+2260h+var_22C0], ebx
0x180004b57  jmp     short loc_180004B5B
0x180004b59  xor     ebx, ebx
0x180004b5b  lea     rdx, aNoremove; "NoRemove"
0x180004b62  mov     rcx, rdi; lpString1
0x180004b65  call    cs:__imp_lstrcmpiW
0x180004b6b  test    eax, eax
0x180004b6d  jnz     short loc_180004B89
0x180004b6f  mov     r12d, ebx
0x180004b72  mov     rdx, rdi; unsigned __int16 *
0x180004b75  mov     rcx, r15; this
0x180004b78  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b7d  mov     ebx, eax
0x180004b7f  xor     edx, edx
0x180004b81  test    eax, eax
0x180004b83  js      loc_1800053F5
0x180004b89  lea     rdx, aVal; "Val"
0x180004b90  mov     rcx, rdi; lpString1
0x180004b93  call    cs:__imp_lstrcmpiW
0x180004b99  xor     edx, edx
0x180004b9b  test    eax, eax
0x180004b9d  jnz     loc_180004CD3
0x180004ba3  lea     rdx, [rbp+2260h+ValueName]; unsigned __int16 *
0x180004baa  mov     rcx, r15; this
0x180004bad  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bb2  mov     ebx, eax
0x180004bb4  xor     edx, edx
0x180004bb6  test    eax, eax
0x180004bb8  js      loc_1800053F5
0x180004bbe  mov     rdx, rdi; unsigned __int16 *
0x180004bc1  mov     rcx, r15; this
0x180004bc4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bc9  mov     ebx, eax
0x180004bcb  xor     edx, edx
0x180004bcd  test    eax, eax
0x180004bcf  js      loc_1800053F5
0x180004bd5  cmp     word ptr [rdi], 3Dh ; '='
0x180004bd9  jnz     loc_1800053A3
0x180004bdf  mov     esi, [rsp+2360h+var_22F0]
0x180004be3  test    esi, esi
0x180004be5  jz      short loc_180004C37
0x180004be7  mov     [rbp+2260h+var_22A8], rdx
0x180004beb  mov     [rbp+2260h+var_22A0], edx
0x180004bee  mov     [rbp+2260h+var_2298], rdx
0x180004bf2  mov     rax, [rsp+2360h+hKey]
0x180004bf7  mov     [rbp+2260h+var_22A8], rax
0x180004bfb  mov     [rbp+2260h+var_22A0], edx
0x180004bfe  mov     [rbp+2260h+var_2298], rdx
0x180004c02  mov     r9, rdi; unsigned __int16 *
0x180004c05  lea     r8, [rbp+2260h+ValueName]; unsigned __int16 *
0x180004c0c  lea     rdx, [rbp+2260h+var_22A8]; struct ATL::CRegKey *
0x180004c10  mov     rcx, r15; this
0x180004c13  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004c18  mov     ebx, eax
0x180004c1a  xor     edx, edx
0x180004c1c  mov     [rbp+2260h+var_22A8], rdx
0x180004c20  mov     [rbp+2260h+var_22A0], edx
0x180004c23  mov     [rbp+2260h+var_2298], rdx
0x180004c27  mov     [rbp+2260h+var_22A0], edx
0x180004c2a  test    eax, eax
0x180004c2c  js      loc_1800053F5
0x180004c32  jmp     loc_180004F94
0x180004c37  cmp     [rbp+2260h+arg_20], edx
0x180004c3d  jnz     loc_180004CC3
0x180004c43  test    r12d, r12d
0x180004c46  jz      short loc_180004CC3
0x180004c48  mov     [rbp+2260h+var_2290], rdx
0x180004c4c  mov     [rbp+2260h+var_2288], edx
0x180004c4f  mov     [rbp+2260h+var_2280], rdx
0x180004c53  mov     [rsp+2360h+var_2300], rdx
0x180004c58  lea     rax, [rsp+2360h+var_2300]
0x180004c5d  mov     [rsp+2360h+phkResult], rax; phkResult
0x180004c62  mov     r9d, 20006h; samDesired
0x180004c68  xor     r8d, r8d; ulOptions
0x180004c6b  xor     edx, edx; lpSubKey
0x180004c6d  mov     rcx, [rsp+2360h+hKey]; hKey
0x180004c72  call    cs:__imp_RegOpenKeyExW
0x180004c78  xor     edx, edx
0x180004c7a  test    eax, eax
0x180004c7c  jnz     loc_1800053D0
0x180004c82  mov     [rbp+2260h+var_2288], edx
0x180004c85  mov     rsi, [rsp+2360h+var_2300]
0x180004c8a  mov     [rbp+2260h+var_2290], rsi
0x180004c8e  mov     [rbp+2260h+var_2288], edx
0x180004c91  lea     rdx, [rbp+2260h+ValueName]; lpValueName
0x180004c98  mov     rcx, rsi; hKey
0x180004c9b  call    cs:__imp_RegDeleteValueW
0x180004ca1  test    eax, 0FFFFFFFDh
0x180004ca6  jnz     loc_1800053AF
0x180004cac  xor     ebx, ebx
0x180004cae  test    rsi, rsi
0x180004cb1  jz      short loc_180004CC0
0x180004cb3  mov     rcx, rsi; hKey
0x180004cb6  call    cs:__imp_RegCloseKey
0x180004cbc  mov     [rbp+2260h+var_2290], rbx
0x180004cc0  mov     [rbp+2260h+var_2288], ebx
0x180004cc3  mov     rdx, rdi; unsigned __int16 *
0x180004cc6  mov     rcx, r15; this
0x180004cc9  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004cce  jmp     loc_180004A18
0x180004cd3  mov     rcx, rdi
0x180004cd6  movzx   eax, word ptr [rdi]
0x180004cd9  jmp     short loc_180004CEF
0x180004cdb  cmp     ax, 5Ch ; '\'
0x180004cdf  jz      short loc_180004CF6
0x180004ce1  call    cs:__imp_CharNextW
0x180004ce7  mov     rcx, rax; lpsz
0x180004cea  movzx   eax, word ptr [rax]
0x180004ced  xor     edx, edx
0x180004cef  test    ax, ax
0x180004cf2  jnz     short loc_180004CDB
0x180004cf4  jmp     short loc_180004CFF
0x180004cf6  test    rcx, rcx
0x180004cf9  jnz     loc_1800053A3
0x180004cff  mov     esi, [rsp+2360h+var_22F0]
0x180004d03  test    esi, esi
0x180004d05  jz      loc_180004FE1
0x180004d0b  mov     [rsp+2360h+var_2300], rdx
0x180004d10  test    r13, r13
0x180004d13  jz      short loc_180004D8E
0x180004d15  cmp     [r13+0], rdx
0x180004d19  jz      short loc_180004D81
0x180004d1b  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180004d22  call    cs:__imp_GetModuleHandleW
0x180004d28  xor     ebx, ebx
0x180004d2a  test    rax, rax
0x180004d2d  jz      loc_180004DE2
0x180004d33  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180004d3a  mov     rcx, rax; hModule
0x180004d3d  call    cs:__imp_GetProcAddress
0x180004d43  mov     r10, rax
0x180004d46  xor     edx, edx
0x180004d48  test    rax, rax
0x180004d4b  jz      short loc_180004D87
0x180004d4d  mov     [rsp+2360h+lpSecurityAttributes], rdx
0x180004d52  mov     rax, [r13+0]
0x180004d56  mov     qword ptr [rsp+2360h+samDesired], rax
0x180004d5b  lea     rax, [rsp+2360h+var_2300]
0x180004d60  mov     [rsp+2360h+phkResult], rax
0x180004d65  mov     r9d, 2001Fh
0x180004d6b  xor     r8d, r8d
0x180004d6e  mov     rdx, rdi
0x180004d71  mov     rcx, [rsp+2360h+hKey]
0x180004d76  mov     rax, r10
0x180004d79  call    cs:__guard_dispatch_icall_fptr
0x180004d7f  jmp     short loc_180004DAF
0x180004d81  cmp     [r13+8], edx
0x180004d85  jnz     short loc_180004D8E
0x180004d87  mov     eax, 1
0x180004d8c  jmp     short loc_180004DAF
0x180004d8e  lea     rax, [rsp+2360h+var_2300]
0x180004d93  mov     [rsp+2360h+phkResult], rax; phkResult
0x180004d98  mov     r9d, 2001Fh; samDesired
0x180004d9e  xor     r8d, r8d; ulOptions
0x180004da1  mov     rdx, rdi; lpSubKey
0x180004da4  mov     rcx, [rsp+2360h+hKey]; hKey
0x180004da9  call    cs:__imp_RegOpenKeyExW
0x180004daf  xor     ebx, ebx
0x180004db1  test    eax, eax
0x180004db3  jnz     short loc_180004DE2
0x180004db5  mov     eax, ebx
0x180004db7  test    r14, r14
0x180004dba  jz      short loc_180004DCA
0x180004dbc  mov     rcx, r14; hKey
0x180004dbf  call    cs:__imp_RegCloseKey
0x180004dc5  mov     [rsp+2360h+var_22E8], rbx
0x180004dca  mov     [rbp+2260h+var_22E0], ebx
0x180004dcd  mov     r14, [rsp+2360h+var_2300]
0x180004dd2  mov     [rsp+2360h+var_22E8], r14
0x180004dd7  mov     [rbp+2260h+var_22E0], ebx
0x180004dda  test    eax, eax
0x180004ddc  jz      loc_180004F4F
0x180004de2  mov     [rsp+2360h+var_2300], rbx
0x180004de7  test    r13, r13
0x180004dea  jz      short loc_180004E61
0x180004dec  cmp     [r13+0], rbx
0x180004df0  jz      short loc_180004E54
0x180004df2  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180004df9  call    cs:__imp_GetModuleHandleW
0x180004dff  test    rax, rax
0x180004e02  jz      loc_180004EB3
0x180004e08  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180004e0f  mov     rcx, rax; hModule
0x180004e12  call    cs:__imp_GetProcAddress
  ... truncated ...
```
