# UnregisterServer(HINSTANCE__ *,_GUID const *,_GUID const *,ushort const *,ushort const *)

- ea: `0x14005faf8`
- end: `0x14006049b`
- name: `?UnregisterServer@@YAJPEAUHINSTANCE__@@PEBU_GUID@@1PEBG2@Z`
- size: `2467`
- prototype: `int(HINSTANCE, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140045fa0`

## callees

- `0x14002e718`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005faf8`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14005fbb4`
- `KERNEL32!GetModuleFileNameW` at `0x14005fbb4`
- `KERNEL32!GetLastError` at `0x14005fbc5`
- `KERNEL32!GetLastError` at `0x14005ff1a`
- `KERNEL32!GetLastError` at `0x14005ffaa`
- `KERNEL32!GetLastError` at `0x140060035`
- `KERNEL32!GetLastError` at `0x140060210`
- `KERNEL32!GetLastError` at `0x1400603d9`
- `KERNEL32!GetLastError` at `0x14005fbc5`
- `KERNEL32!GetLastError` at `0x14005ff1a`
- `KERNEL32!GetLastError` at `0x14005ffaa`
- `KERNEL32!GetLastError` at `0x140060035`
- `KERNEL32!GetLastError` at `0x140060210`
- `KERNEL32!GetLastError` at `0x1400603d9`
- `KERNEL32!IsDebuggerPresent` at `0x14005fc22`
- `KERNEL32!IsDebuggerPresent` at `0x14005fccd`
- `KERNEL32!IsDebuggerPresent` at `0x14005fd5c`
- `KERNEL32!IsDebuggerPresent` at `0x14005fe41`
- `KERNEL32!IsDebuggerPresent` at `0x14005fed1`
- `KERNEL32!IsDebuggerPresent` at `0x14005ff67`
- `KERNEL32!IsDebuggerPresent` at `0x14005fff7`
- `KERNEL32!IsDebuggerPresent` at `0x140060082`
- `KERNEL32!IsDebuggerPresent` at `0x140060148`
- `KERNEL32!IsDebuggerPresent` at `0x1400601c7`
- `KERNEL32!IsDebuggerPresent` at `0x14006025d`
- `KERNEL32!IsDebuggerPresent` at `0x14006030e`
- `KERNEL32!IsDebuggerPresent` at `0x14006038c`
- `KERNEL32!IsDebuggerPresent` at `0x140060426`
- `KERNEL32!IsDebuggerPresent` at `0x14005fc22`
- `KERNEL32!IsDebuggerPresent` at `0x14005fccd`
- `KERNEL32!IsDebuggerPresent` at `0x14005fd5c`
- `KERNEL32!IsDebuggerPresent` at `0x14005fe41`
- `KERNEL32!IsDebuggerPresent` at `0x14005fed1`
- `KERNEL32!IsDebuggerPresent` at `0x14005ff67`
- `KERNEL32!IsDebuggerPresent` at `0x14005fff7`
- `KERNEL32!IsDebuggerPresent` at `0x140060082`
- `KERNEL32!IsDebuggerPresent` at `0x140060148`
- `KERNEL32!IsDebuggerPresent` at `0x1400601c7`
- `KERNEL32!IsDebuggerPresent` at `0x14006025d`
- `KERNEL32!IsDebuggerPresent` at `0x14006030e`
- `KERNEL32!IsDebuggerPresent` at `0x14006038c`
- `KERNEL32!IsDebuggerPresent` at `0x140060426`
- `msvcrt!wcsrchr` at `0x14005fc78`
- `msvcrt!wcsrchr` at `0x14005fc78`
- `ole32!StringFromGUID2` at `0x14005fd81`
- `ole32!StringFromGUID2` at `0x14005fd9b`
- `ole32!StringFromGUID2` at `0x14005fd81`
- `ole32!StringFromGUID2` at `0x14005fd9b`
- `SHLWAPI!SHDeleteKeyW` at `0x14005ff0d`
- `SHLWAPI!SHDeleteKeyW` at `0x14005ff9b`
- `SHLWAPI!SHDeleteKeyW` at `0x14006002b`
- `SHLWAPI!SHDeleteKeyW` at `0x140060203`
- `SHLWAPI!SHDeleteKeyW` at `0x1400603c8`
- `SHLWAPI!SHDeleteKeyW` at `0x14005ff0d`
- `SHLWAPI!SHDeleteKeyW` at `0x14005ff9b`
- `SHLWAPI!SHDeleteKeyW` at `0x14006002b`
- `SHLWAPI!SHDeleteKeyW` at `0x140060203`
- `SHLWAPI!SHDeleteKeyW` at `0x1400603c8`

## string_xrefs

- `0x14005fbe9`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005fcb2`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005fd41`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005fe1e`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005feae`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005ff44`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005ffd4`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14006005f`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x140060125`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x1400601a4`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14006023a`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x1400602eb`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x140060369`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x140060403`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005fc8d`: `pszServiceExeName != 0`
- `0x14005fcd5`: `pszServiceExeName != 0`
- `0x14005fd1c`: `pszServiceExeName[0] != 0`
- `0x14005fd64`: `pszServiceExeName[0] != 0`
- `0x14005fdbb`: `CLSID\`

## pseudocode

```c
__int64 __fastcall UnregisterServer(
        HINSTANCE a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  wchar_t *v11; // rax
  unsigned int v12; // r12d
  bool v13; // zf
  const unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  WCHAR *v20; // r8
  WCHAR *v21; // rcx
  int v22; // eax
  signed int v23; // eax
  __int64 v24; // r8
  signed int v25; // eax
  signed int v26; // eax
  const wchar_t *v27; // rsi
  const wchar_t *v28; // rcx
  WCHAR *v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rax
  WCHAR *v32; // rcx
  int v33; // eax
  signed int v34; // eax
  __int64 v35; // rdx
  WCHAR *v36; // r8
  WCHAR *v37; // rcx
  int v38; // eax
  signed int v39; // eax
  const unsigned __int16 *v41; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v42; // [rsp+30h] [rbp-D0h]
  int v43; // [rsp+38h] [rbp-C8h]
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR v45[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszSubKey[128]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v47[128]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR v48[128]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR Filename[512]; // [rsp+3E0h] [rbp+2E0h] BYREF

  memset_0(Filename, 0, sizeof(Filename));
  memset_0(sz, 0, sizeof(sz));
  memset_0(v45, 0, sizeof(v45));
  memset_0(pszSubKey, 0, sizeof(pszSubKey));
  memset_0(v48, 0, sizeof(v48));
  memset_0(v47, 0, sizeof(v47));
  if ( !GetModuleFileNameW(0, Filename, 0x200u) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
      v9 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0xF0u,
      L"UnregisterServer",
      L"CBRAEx",
      L"dwResult != 0",
      v9);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        240,
        L"UnregisterServer",
        L"CBRAEx",
        L"dwResult != 0",
        v9);
      return v9;
    }
    v43 = v9;
    v10 = 240;
    v42 = L"dwResult != 0";
    v41 = L"CBRAEx";
    goto LABEL_8;
  }
  v11 = wcsrchr(Filename, 0x5Cu);
  if ( !v11 )
  {
    v12 = 244;
    v9 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0xF4u,
      L"UnregisterServer",
      L"CBRA",
      L"pszServiceExeName != 0",
      -2147467259);
    v13 = !IsDebuggerPresent();
    v14 = L"pszServiceExeName != 0";
LABEL_12:
    if ( v13 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        v12,
        L"UnregisterServer",
        L"CBRA",
        v14,
        -2147467259);
      return v9;
    }
    v43 = -2147467259;
    v10 = v12;
    v42 = v14;
    v41 = L"CBRA";
    goto LABEL_8;
  }
  v15 = v11 + 1;
  if ( !v11[1] )
  {
    v12 = 248;
    v9 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0xF8u,
      L"UnregisterServer",
      L"CBRA",
      L"pszServiceExeName[0] != 0",
      -2147467259);
    v13 = !IsDebuggerPresent();
    v14 = L"pszServiceExeName[0] != 0";
    goto LABEL_12;
  }
  v9 = StringFromGUID2(a2, sz, 40);
  if ( (v9 & 0x80000000) == 0 )
  {
    v9 = StringFromGUID2(a3, v45, 40);
    if ( (v9 & 0x80000000) == 0 )
    {
      v16 = 2147483646;
      v17 = 128;
      v18 = 2147483646;
      v19 = L"CLSID\\";
      v20 = pszSubKey;
      do
      {
        if ( !v18 )
          break;
        if ( !*v19 )
          break;
        *v20++ = *v19++;
        --v18;
        --v17;
      }
      while ( v17 );
      v21 = v20 - 1;
      v9 = v17 == 0 ? 0x8007007A : 0;
      if ( v17 )
        v21 = v20;
      *v21 = 0;
      if ( !v17 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x105u,
          L"UnregisterServer",
          L"CHRA",
          L"hr",
          -2147024774);
        if ( !IsDebuggerPresent() )
        {
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            261,
            L"UnregisterServer",
            L"CHRA",
            L"hr",
            v9);
          return v9;
        }
        v10 = 261;
        goto LABEL_28;
      }
      v22 = StringCchCatW(pszSubKey, 0x80u, sz);
      v9 = v22;
      if ( v22 < 0 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x107u,
          L"UnregisterServer",
          L"CHRA",
          L"hr",
          v22);
        if ( !IsDebuggerPresent() )
        {
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            263,
            L"UnregisterServer",
            L"CHRA",
            L"hr",
            v9);
          return v9;
        }
        v10 = 263;
        goto LABEL_28;
      }
      if ( (SHDeleteKeyW(HKEY_CLASSES_ROOT, pszSubKey) & 0xFFFFFFFD) != 0 )
      {
        v23 = GetLastError();
        v9 = v23;
        if ( v23 > 0 )
          v9 = (unsigned __int16)v23 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x10Fu,
          L"UnregisterServer",
          L"CBRAEx",
          L"lResult == 0L || lResult == 2L",
          v9);
        if ( IsDebuggerPresent() )
        {
          v43 = v9;
          v10 = 271;
          v42 = L"lResult == 0L || lResult == 2L";
          v41 = L"CBRAEx";
          goto LABEL_8;
        }
        v24 = 271;
      }
      else if ( (SHDeleteKeyW(HKEY_CLASSES_ROOT, a4) & 0xFFFFFFFD) != 0 )
      {
        v25 = GetLastError();
        v9 = v25;
        if ( v25 > 0 )
          v9 = (unsigned __int16)v25 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x113u,
          L"UnregisterServer",
          L"CBRAEx",
          L"lResult == 0L || lResult == 2L",
          v9);
        if ( IsDebuggerPresent() )
        {
          v43 = v9;
          v10 = 275;
          v42 = L"lResult == 0L || lResult == 2L";
          v41 = L"CBRAEx";
          goto LABEL_8;
        }
        v24 = 275;
      }
      else
      {
        if ( (SHDeleteKeyW(HKEY_CLASSES_ROOT, a5) & 0xFFFFFFFD) == 0 )
        {
          v27 = L"AppID\\";
          v28 = L"AppID\\";
          v29 = v47;
          v30 = 128;
          v31 = 2147483646;
          do
          {
            if ( !v31 )
              break;
            if ( !*v28 )
              break;
            *v29++ = *v28++;
            --v31;
            --v30;
          }
          while ( v30 );
          v32 = v29 - 1;
          v9 = v30 == 0 ? 0x8007007A : 0;
          if ( v30 )
            v32 = v29;
          *v32 = 0;
          if ( v30 )
          {
            v33 = StringCchCatW(v47, 0x80u, v45);
            v9 = v33;
            if ( v33 >= 0 )
            {
              if ( (SHDeleteKeyW(HKEY_CLASSES_ROOT, v47) & 0xFFFFFFFD) != 0 )
              {
                v34 = GetLastError();
                v9 = v34;
                if ( v34 > 0 )
                  v9 = (unsigned __int16)v34 | 0x80070000;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                  0x125u,
                  L"UnregisterServer",
                  L"CBRAEx",
                  L"lResult == 0L || lResult == 2L",
                  v9);
                if ( IsDebuggerPresent() )
                {
                  v43 = v9;
                  v10 = 293;
                  v42 = L"lResult == 0L || lResult == 2L";
                  v41 = L"CBRAEx";
                  goto LABEL_8;
                }
                v24 = 293;
                goto LABEL_92;
              }
              v35 = 128;
              v36 = v48;
              do
              {
                if ( !v16 )
                  break;
                if ( !*v27 )
                  break;
                *v36++ = *v27++;
                --v16;
                --v35;
              }
              while ( v35 );
              v37 = v36 - 1;
              v9 = v35 == 0 ? 0x8007007A : 0;
              if ( v35 )
                v37 = v36;
              *v37 = 0;
              if ( v35 )
              {
                v38 = StringCchCatW(v48, 0x80u, v15);
                v9 = v38;
                if ( v38 >= 0 )
                {
                  if ( (SHDeleteKeyW(HKEY_CLASSES_ROOT, v48) & 0xFFFFFFFD) == 0 )
                    return v9;
                  v39 = GetLastError();
                  v9 = v39;
                  if ( v39 > 0 )
                    v9 = (unsigned __int16)v39 | 0x80070000;
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                    0x12Fu,
                    L"UnregisterServer",
                    L"CBRAEx",
                    L"lResult == 0L || lResult == 2L",
                    v9);
                  if ( IsDebuggerPresent() )
                  {
                    v43 = v9;
                    v10 = 303;
                    v42 = L"lResult == 0L || lResult == 2L";
                    v41 = L"CBRAEx";
                    goto LABEL_8;
                  }
                  v24 = 303;
                  goto LABEL_92;
                }
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                  0x12Bu,
                  L"UnregisterServer",
                  L"CHRA",
                  L"hr",
                  v38);
                if ( !IsDebuggerPresent() )
                {
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                    299,
                    L"UnregisterServer",
                    L"CHRA",
                    L"hr",
                    v9);
                  return v9;
                }
                v10 = 299;
              }
              else
              {
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                  0x129u,
                  L"UnregisterServer",
                  L"CHRA",
                  L"hr",
                  -2147024774);
                if ( !IsDebuggerPresent() )
                {
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                    297,
                    L"UnregisterServer",
                    L"CHRA",
                    L"hr",
                    v9);
                  return v9;
                }
                v10 = 297;
              }
            }
            else
            {
              LOGASSERTHR(
                L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                0x121u,
                L"UnregisterServer",
                L"CHRA",
                L"hr",
                v33);
              if ( !IsDebuggerPresent() )
              {
                DEBUGMSGBOX(
                  L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                  L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                  289,
                  L"UnregisterServer",
                  L"CHRA",
                  L"hr",
                  v9);
                return v9;
              }
              v10 = 289;
            }
          }
          else
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
              0x11Fu,
              L"UnregisterServer",
              L"CHRA",
              L"hr",
              -2147024774);
            if ( !IsDebuggerPresent() )
            {
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                287,
                L"UnregisterServer",
                L"CHRA",
                L"hr",
                v9);
              return v9;
            }
            v10 = 287;
          }
LABEL_28:
          v43 = v9;
          v42 = L"hr";
          v41 = L"CHRA";
LABEL_8:
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            v10,
            L"UnregisterServer",
            v41,
            v42,
            v43);
          return v9;
        }
        v26 = GetLastError();
        v9 = v26;
        if ( v26 > 0 )
          v9 = (unsigned __int16)v26 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x117u,
          L"UnregisterServer",
          L"CBRAEx",
          L"lResult == 0L || lResult == 2L",
          v9);
        if ( IsDebuggerPresent() )
        {
          v43 = v9;
          v10 = 279;
          v42 = L"lResult == 0L || lResult == 2L";
          v41 = L"CBRAEx";
          goto LABEL_8;
        }
        v24 = 279;
      }
LABEL_92:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        v24,
        L"UnregisterServer",
        L"CBRAEx",
        L"lResult == 0L || lResult == 2L",
        v9);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14005faf8  mov     [rsp-8+arg_0], rbx
0x14005fafd  push    rbp
0x14005fafe  push    rsi
0x14005faff  push    rdi
0x14005fb00  push    r12
0x14005fb02  push    r13
0x14005fb04  push    r14
0x14005fb06  push    r15
0x14005fb08  lea     rbp, [rsp-6F0h]
0x14005fb10  sub     rsp, 7F0h
0x14005fb17  mov     rax, cs:__security_cookie
0x14005fb1e  xor     rax, rsp
0x14005fb21  mov     [rbp+720h+var_40], rax
0x14005fb28  mov     r15, [rbp+720h+arg_20]
0x14005fb2f  lea     rcx, [rbp+720h+Filename]; void *
0x14005fb36  mov     rdi, r8
0x14005fb39  mov     rbx, rdx
0x14005fb3c  xor     edx, edx; Val
0x14005fb3e  mov     r8d, 400h; Size
0x14005fb44  mov     rsi, r9
0x14005fb47  call    memset_0
0x14005fb4c  mov     r14d, 50h ; 'P'
0x14005fb52  lea     rcx, [rsp+820h+sz]; void *
0x14005fb57  mov     r8d, r14d; Size
0x14005fb5a  xor     edx, edx; Val
0x14005fb5c  call    memset_0
0x14005fb61  mov     r8d, r14d; Size
0x14005fb64  lea     rcx, [rbp+720h+var_790]; void *
0x14005fb68  xor     edx, edx; Val
0x14005fb6a  call    memset_0
0x14005fb6f  mov     r14d, 100h
0x14005fb75  lea     rcx, [rbp+720h+pszSubKey]; void *
0x14005fb79  mov     r8d, r14d; Size
0x14005fb7c  xor     edx, edx; Val
0x14005fb7e  call    memset_0
0x14005fb83  mov     r8d, r14d; Size
0x14005fb86  lea     rcx, [rbp+720h+var_540]; void *
0x14005fb8d  xor     edx, edx; Val
0x14005fb8f  call    memset_0
0x14005fb94  mov     r8d, r14d; Size
0x14005fb97  lea     rcx, [rbp+720h+var_640]; void *
0x14005fb9e  xor     edx, edx; Val
0x14005fba0  call    memset_0
0x14005fba5  mov     r8d, 200h; nSize
0x14005fbab  lea     rdx, [rbp+720h+Filename]; lpFilename
0x14005fbb2  xor     ecx, ecx; hModule
0x14005fbb4  call    cs:__imp_GetModuleFileNameW
0x14005fbba  xor     r13d, r13d
0x14005fbbd  test    eax, eax
0x14005fbbf  jnz     loc_14005FC6C
0x14005fbc5  call    cs:__imp_GetLastError
0x14005fbcb  mov     ebx, eax
0x14005fbcd  test    eax, eax
0x14005fbcf  jle     short loc_14005FBDA
0x14005fbd1  movzx   ebx, ax
0x14005fbd4  or      ebx, 80070000h
0x14005fbda  mov     r14d, 80004005h
0x14005fbe0  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005fbe7  test    ebx, ebx
0x14005fbe9  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fbf0  mov     r15d, 0F0h
0x14005fbf6  lea     r12, aDwresult0; "dwResult != 0"
0x14005fbfd  cmovns  ebx, r14d
0x14005fc01  mov     r8, rsi; unsigned __int16 *
0x14005fc04  lea     r14, aCbraex; "CBRAEx"
0x14005fc0b  mov     [rsp+820h+var_7F8], ebx; int
0x14005fc0f  mov     r9, r14; unsigned __int16 *
0x14005fc12  mov     [rsp+820h+var_800], r12; unsigned __int16 *
0x14005fc17  mov     edx, r15d; unsigned int
0x14005fc1a  mov     rcx, rdi; unsigned __int16 *
0x14005fc1d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fc22  call    cs:__imp_IsDebuggerPresent
0x14005fc28  test    eax, eax
0x14005fc2a  jz      short loc_14005FC5B
0x14005fc2c  mov     [rsp+820h+var_7E8], ebx
0x14005fc30  mov     r9d, r15d
0x14005fc33  mov     [rsp+820h+var_7F0], r12
0x14005fc38  mov     qword ptr [rsp+820h+var_7F8], r14
0x14005fc3d  mov     ecx, 2; unsigned __int8
0x14005fc42  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005fc49  mov     [rsp+820h+var_800], rsi
0x14005fc4e  mov     r8, rdi
0x14005fc51  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005fc56  jmp     loc_14006046F
0x14005fc5b  mov     dword ptr [rsp+820h+var_7F0], ebx
0x14005fc5f  mov     r8d, r15d
0x14005fc62  mov     qword ptr [rsp+820h+var_7F8], r12
0x14005fc67  jmp     loc_140060458
0x14005fc6c  mov     edx, 5Ch ; '\'; Ch
0x14005fc71  lea     rcx, [rbp+720h+Filename]; Str
0x14005fc78  call    cs:__imp_wcsrchr
0x14005fc7e  test    rax, rax
0x14005fc81  jnz     loc_14005FD0C
0x14005fc87  mov     r14d, 80004005h
0x14005fc8d  lea     rax, aPszserviceexen_0; "pszServiceExeName != 0"
0x14005fc94  lea     r15, aCbra; "CBRA"
0x14005fc9b  mov     [rsp+820h+var_7F8], r14d; int
0x14005fca0  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005fca7  mov     [rsp+820h+var_800], rax; unsigned __int16 *
0x14005fcac  mov     r12d, 0F4h
0x14005fcb2  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fcb9  mov     r9, r15; unsigned __int16 *
0x14005fcbc  mov     r8, rsi; unsigned __int16 *
0x14005fcbf  mov     edx, r12d; unsigned int
0x14005fcc2  mov     rcx, rdi; unsigned __int16 *
0x14005fcc5  mov     ebx, r14d
0x14005fcc8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fccd  call    cs:__imp_IsDebuggerPresent
0x14005fcd3  test    eax, eax
0x14005fcd5  lea     rax, aPszserviceexen_0; "pszServiceExeName != 0"
0x14005fcdc  jz      short loc_14005FCF5
0x14005fcde  mov     [rsp+820h+var_7E8], r14d
0x14005fce3  mov     r9d, r12d
0x14005fce6  mov     [rsp+820h+var_7F0], rax
0x14005fceb  mov     qword ptr [rsp+820h+var_7F8], r15
0x14005fcf0  jmp     loc_14005FC3D
0x14005fcf5  mov     dword ptr [rsp+820h+var_7F0], r14d
0x14005fcfa  mov     r8d, r12d
0x14005fcfd  mov     qword ptr [rsp+820h+var_7F8], rax
0x14005fd02  mov     [rsp+820h+var_800], r15
0x14005fd07  jmp     loc_14006045D
0x14005fd0c  lea     r14, [rax+2]
0x14005fd10  cmp     [r14], r13w
0x14005fd14  jnz     short loc_14005FD70
0x14005fd16  mov     r14d, 80004005h
0x14005fd1c  lea     rax, aPszserviceexen; "pszServiceExeName[0] != 0"
0x14005fd23  lea     r15, aCbra; "CBRA"
0x14005fd2a  mov     [rsp+820h+var_7F8], r14d; int
0x14005fd2f  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005fd36  mov     [rsp+820h+var_800], rax; unsigned __int16 *
0x14005fd3b  mov     r12d, 0F8h
0x14005fd41  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fd48  mov     r9, r15; unsigned __int16 *
0x14005fd4b  mov     r8, rsi; unsigned __int16 *
0x14005fd4e  mov     edx, r12d; unsigned int
0x14005fd51  mov     rcx, rdi; unsigned __int16 *
0x14005fd54  mov     ebx, r14d
0x14005fd57  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fd5c  call    cs:__imp_IsDebuggerPresent
0x14005fd62  test    eax, eax
0x14005fd64  lea     rax, aPszserviceexen; "pszServiceExeName[0] != 0"
0x14005fd6b  jmp     loc_14005FCDC
0x14005fd70  mov     r12d, 28h ; '('
0x14005fd76  lea     rdx, [rsp+820h+sz]; lpsz
0x14005fd7b  mov     r8d, r12d; cchMax
0x14005fd7e  mov     rcx, rbx; rguid
0x14005fd81  call    cs:__imp_StringFromGUID2
0x14005fd87  mov     ebx, eax
0x14005fd89  test    eax, eax
0x14005fd8b  js      loc_14006046F
0x14005fd91  mov     r8d, r12d; cchMax
0x14005fd94  lea     rdx, [rbp+720h+var_790]; lpsz
0x14005fd98  mov     rcx, rdi; rguid
0x14005fd9b  call    cs:__imp_StringFromGUID2
0x14005fda1  mov     ebx, eax
0x14005fda3  test    eax, eax
0x14005fda5  js      loc_14006046F
0x14005fdab  mov     edi, 7FFFFFFEh
0x14005fdb0  lea     edx, [r12+58h]
0x14005fdb5  mov     eax, edi
0x14005fdb7  lea     r12d, [rdx-7Eh]
0x14005fdbb  lea     rcx, aClsid; "CLSID\\"
0x14005fdc2  lea     r8, [rbp+720h+pszSubKey]
0x14005fdc6  test    rax, rax
0x14005fdc9  jz      short loc_14005FDE8
0x14005fdcb  movzx   r9d, word ptr [rcx]
0x14005fdcf  test    r9w, r9w
0x14005fdd3  jz      short loc_14005FDE8
0x14005fdd5  mov     [r8], r9w
0x14005fdd9  add     rcx, r12
0x14005fddc  add     r8, r12
0x14005fddf  dec     rax
0x14005fde2  sub     rdx, 1
0x14005fde6  jnz     short loc_14005FDC6
0x14005fde8  mov     rax, rdx
0x14005fdeb  lea     rcx, [r8-2]
0x14005fdef  neg     rax
0x14005fdf2  sbb     ebx, ebx
0x14005fdf4  not     ebx
0x14005fdf6  and     ebx, 8007007Ah
0x14005fdfc  test    rdx, rdx
0x14005fdff  cmovnz  rcx, r8
0x14005fe03  mov     [rcx], r13w
0x14005fe07  jnz     short loc_14005FE80
0x14005fe09  lea     r15, aChra; "CHRA"
0x14005fe10  mov     [rsp+820h+var_7F8], ebx; int
0x14005fe14  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005fe1b  mov     r9, r15; unsigned __int16 *
0x14005fe1e  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fe25  mov     r8, rsi; unsigned __int16 *
0x14005fe28  lea     r14, aHr; "hr"
0x14005fe2f  mov     rcx, rdi; unsigned __int16 *
0x14005fe32  mov     edx, 105h; unsigned int
0x14005fe37  mov     [rsp+820h+var_800], r14; unsigned __int16 *
0x14005fe3c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fe41  call    cs:__imp_IsDebuggerPresent
0x14005fe47  test    eax, eax
0x14005fe49  jz      short loc_14005FE67
0x14005fe4b  mov     r9d, 105h
0x14005fe51  mov     [rsp+820h+var_7E8], ebx
0x14005fe55  mov     [rsp+820h+var_7F0], r14
0x14005fe5a  mov     qword ptr [rsp+820h+var_7F8], r15
0x14005fe5f  mov     ecx, r12d
0x14005fe62  jmp     loc_14005FC42
0x14005fe67  mov     dword ptr [rsp+820h+var_7F0], ebx
0x14005fe6b  mov     r8d, 105h
0x14005fe71  mov     qword ptr [rsp+820h+var_7F8], r14
0x14005fe76  mov     [rsp+820h+var_800], r15
0x14005fe7b  jmp     loc_14006045D
0x14005fe80  lea     r8, [rsp+820h+sz]; unsigned __int16 *
0x14005fe85  mov     edx, 80h; unsigned __int64
0x14005fe8a  lea     rcx, [rbp+720h+pszSubKey]; unsigned __int16 *
0x14005fe8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005fe93  mov     ebx, eax
0x14005fe95  test    eax, eax
0x14005fe97  jns     short loc_14005FEFF
0x14005fe99  mov     [rsp+820h+var_7F8], eax; int
0x14005fe9d  lea     r15, aChra; "CHRA"
0x14005fea4  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005feab  mov     r9, r15; unsigned __int16 *
0x14005feae  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005feb5  mov     r8, rsi; unsigned __int16 *
0x14005feb8  lea     r14, aHr; "hr"
0x14005febf  mov     rcx, rdi; unsigned __int16 *
0x14005fec2  mov     edx, 107h; unsigned int
0x14005fec7  mov     [rsp+820h+var_800], r14; unsigned __int16 *
0x14005fecc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fed1  call    cs:__imp_IsDebuggerPresent
0x14005fed7  test    eax, eax
0x14005fed9  jz      short loc_14005FEE6
0x14005fedb  mov     r9d, 107h
0x14005fee1  jmp     loc_14005FE51
0x14005fee6  mov     dword ptr [rsp+820h+var_7F0], ebx
0x14005feea  mov     r8d, 107h
0x14005fef0  mov     qword ptr [rsp+820h+var_7F8], r14
0x14005fef5  mov     [rsp+820h+var_800], r15
0x14005fefa  jmp     loc_14006045D
0x14005feff  mov     rbx, 0FFFFFFFF80000000h
0x14005ff06  lea     rdx, [rbp+720h+pszSubKey]; pszSubKey
0x14005ff0a  mov     rcx, rbx; hkey
0x14005ff0d  call    cs:__imp_SHDeleteKeyW
0x14005ff13  test    eax, 0FFFFFFFDh
0x14005ff18  jz      short loc_14005FF95
0x14005ff1a  call    cs:__imp_GetLastError
0x14005ff20  mov     ebx, eax
0x14005ff22  test    eax, eax
0x14005ff24  jle     short loc_14005FF2F
0x14005ff26  movzx   ebx, ax
0x14005ff29  or      ebx, 80070000h
0x14005ff2f  lea     r14, aCbraex; "CBRAEx"
0x14005ff36  mov     [rsp+820h+var_7F8], ebx; int
0x14005ff3a  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005ff41  mov     r9, r14; unsigned __int16 *
0x14005ff44  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005ff4b  mov     r8, rsi; unsigned __int16 *
0x14005ff4e  lea     r15, aLresult0lLresu; "lResult == 0L || lResult == 2L"
0x14005ff55  mov     rcx, rdi; unsigned __int16 *
0x14005ff58  mov     edx, 10Fh; unsigned int
0x14005ff5d  mov     [rsp+820h+var_800], r15; unsigned __int16 *
0x14005ff62  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005ff67  call    cs:__imp_IsDebuggerPresent
0x14005ff6d  test    eax, eax
0x14005ff6f  jz      short loc_14005FF8A
0x14005ff71  mov     [rsp+820h+var_7E8], ebx
0x14005ff75  mov     r9d, 10Fh
0x14005ff7b  mov     [rsp+820h+var_7F0], r15
0x14005ff80  mov     qword ptr [rsp+820h+var_7F8], r14
0x14005ff85  jmp     loc_14005FE5F
0x14005ff8a  mov     r8d, 10Fh
0x14005ff90  jmp     loc_14006044F
0x14005ff95  mov     rdx, rsi; pszSubKey
0x14005ff98  mov     rcx, rbx; hkey
0x14005ff9b  call    cs:__imp_SHDeleteKeyW
0x14005ffa1  mov     esi, 0FFFFFFFDh
0x14005ffa6  test    esi, eax
0x14005ffa8  jz      short loc_140060025
0x14005ffaa  call    cs:__imp_GetLastError
0x14005ffb0  mov     ebx, eax
0x14005ffb2  test    eax, eax
0x14005ffb4  jle     short loc_14005FFBF
0x14005ffb6  movzx   ebx, ax
0x14005ffb9  or      ebx, 80070000h
0x14005ffbf  lea     r14, aCbraex; "CBRAEx"
0x14005ffc6  mov     [rsp+820h+var_7F8], ebx; int
0x14005ffca  lea     rsi, aUnregisterserv; "UnregisterServer"
0x14005ffd1  mov     r9, r14; unsigned __int16 *
0x14005ffd4  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005ffdb  mov     r8, rsi; unsigned __int16 *
0x14005ffde  lea     r15, aLresult0lLresu; "lResult == 0L || lResult == 2L"
0x14005ffe5  mov     rcx, rdi; unsigned __int16 *
0x14005ffe8  mov     edx, 113h; unsigned int
0x14005ffed  mov     [rsp+820h+var_800], r15; unsigned __int16 *
0x14005fff2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fff7  call    cs:__imp_IsDebuggerPresent
0x14005fffd  test    eax, eax
0x14005ffff  jz      short loc_14006001A
0x140060001  mov     [rsp+820h+var_7E8], ebx
0x140060005  mov     r9d, 113h
0x14006000b  mov     [rsp+820h+var_7F0], r15
0x140060010  mov     qword ptr [rsp+820h+var_7F8], r14
  ... truncated ...
```
