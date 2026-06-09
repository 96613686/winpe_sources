# _LoadRegKeyvalueExtensions

- ea: `0x180009a10`
- end: `0x180009f6e`
- name: `_LoadRegKeyvalueExtensions`
- size: `1374`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b300`
- `0x180015384`

## callees

- `0x1800070d0`
- `0x180009a10`
- `0x18000b1a0`
- `0x18000fc70`
- `0x180014ce0`
- `0x18001860d`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009ec9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009ec9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009de2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009de2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ed5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ed5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009eec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009eaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009d93`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f47`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009aff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009aff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009c35`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009c35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ab7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ab7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009be2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009da8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009da8`

## string_xrefs

- `0x180009b35`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180009e59`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180009aa9`: `SOFTWARE\Microsoft\Cryptography\CryptXML\KeyValue`
- `0x180009dbd`: `CryptXmlEncodeKeyValue`
- `0x180009dd7`: `CryptXmlCreateKey`

## pseudocode

```c
void LoadRegKeyvalueExtensions()
{
  _QWORD *v0; // rbx
  int v1; // r15d
  DWORD i; // esi
  __int64 v3; // rcx
  __int64 v4; // rdx
  const char *v5; // rax
  void *v6; // rax
  DWORD v7; // edx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // r13
  unsigned int v12; // edi
  DWORD v13; // r14d
  __int64 v14; // rsi
  BYTE *v15; // rax
  DWORD v16; // ecx
  int v17; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v20; // rcx
  HANDLE ProcessHeap; // rax
  int v22; // edx
  const char *v23; // rax
  HMODULE v24; // rcx
  HANDLE v25; // rax
  DWORD cchName; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cValues[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-90h] BYREF
  DWORD Type; // [rsp+80h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-84h] BYREF
  DWORD v32; // [rsp+88h] [rbp-80h]
  HKEY hKey; // [rsp+90h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+98h] [rbp-70h] BYREF

  hKey = 0;
  phkResult = 0;
  cValues[0] = 0;
  cbMaxValueLen = 0;
  cchName = 0;
  if ( !dword_180022FC4 )
  {
    v0 = 0;
    EnterCriticalSection(&g_csCryptXmlCriticalSection);
    if ( !dword_180022FC4
      && !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Cryptography\\CryptXML\\KeyValue",
            0,
            0x20019u,
            &hKey) )
    {
      v1 = 0;
      for ( i = 0; ; ++i )
      {
        v32 = i;
        cchName = 259;
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          goto LABEL_9;
        v3 = v1 & 0xFFFFFFF8;
        v4 = (unsigned int)(v3 + 8);
        if ( dword_180022FE0 )
        {
          if ( v1 + 1 >= (unsigned int)v4 )
          {
            v6 = (void *)CryptXmlRealloc(lpMem, v4, 8LL * (unsigned int)(v3 + 16));
            if ( !v6 )
            {
              v23 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v23, 829);
              dword_180022FC4 = 1;
              LeaveCriticalSection(&g_csCryptXmlCriticalSection);
              goto LABEL_42;
            }
            lpMem = v6;
          }
        }
        else
        {
          lpMem = (LPVOID)CryptXmlAlloc(v3, 8 * v4);
          if ( !lpMem )
          {
            v5 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v5, 810);
LABEL_9:
            dword_180022FC4 = 1;
            LeaveCriticalSection(&g_csCryptXmlCriticalSection);
            goto LABEL_42;
          }
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        v0 = 0;
        if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult)
          || RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, cValues, 0, &cbMaxValueLen, 0, 0) )
        {
          break;
        }
        v7 = cbMaxValueLen;
        if ( cbMaxValueLen < 4 )
        {
          v7 = 4;
          cbMaxValueLen = 4;
        }
        v8 = cchName + 1;
        v9 = cValues[0] * v7 + 2 * (v8 + 83);
        if ( v9 <= 0xFFFFFF )
        {
          v10 = (_QWORD *)CryptXmlAlloc(v8, (unsigned int)v9);
          v0 = v10;
          if ( !v10 )
            break;
          *v10 = v10 + 6;
          v11 = (__int64)v10 + 2 * cchName + 50;
          memcpy_0(v10 + 6, Name, 2LL * cchName);
          v12 = 0;
          v13 = cValues[0] * cbMaxValueLen + 6;
          while ( v12 < 2 )
          {
            Type = 0;
            v14 = 3LL * v12;
            if ( *((_DWORD *)&off_180022658 + 2 * v14 + 2) == 4 )
            {
              v15 = (BYTE *)v0 + LODWORD((&off_180022658)[v14 + 1]);
              v16 = 4;
            }
            else
            {
              *(_QWORD *)((char *)v0 + LODWORD((&off_180022658)[v14 + 1])) = v11;
              v15 = (BYTE *)v11;
              v16 = v13;
            }
            cbData = v16;
            if ( RegQueryValueExW(phkResult, (&off_180022658)[v14], 0, &Type, v15, &cbData)
              || (v17 = *((_DWORD *)&off_180022658 + 2 * v14 + 2), v17 != Type) )
            {
              if ( !*((_DWORD *)&off_180022658 + 2 * v14 + 3) )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 8u, v0);
                v0 = 0;
                break;
              }
            }
            else if ( v17 != 4 )
            {
              v11 += cbData;
              v13 -= cbData;
              if ( CompareStringW(0, 1u, (&off_180022658)[v14], -1, L"DLL", -1) == 2 )
              {
                LibraryW = LoadLibraryW((LPCWSTR)v0[1]);
                v0[2] = LibraryW;
                if ( LibraryW )
                {
                  ProcAddress = GetProcAddress(LibraryW, "CryptXmlEncodeKeyValue");
                  v20 = (HMODULE)v0[2];
                  v0[4] = ProcAddress;
                  v0[5] = GetProcAddress(v20, "CryptXmlCreateKey");
                }
              }
            }
            ++v12;
          }
          v22 = dword_180022FE0;
          i = v32;
          *((_QWORD *)lpMem + (unsigned int)dword_180022FE0) = v0;
          dword_180022FE0 = v22 + 1;
          ++v1;
        }
      }
    }
    dword_180022FC4 = 1;
    LeaveCriticalSection(&g_csCryptXmlCriticalSection);
    if ( v0 )
    {
      v24 = (HMODULE)v0[2];
      if ( v24 )
        FreeLibrary(v24);
      v25 = GetProcessHeap();
      HeapFree(v25, 8u, v0);
    }
LABEL_42:
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180009a10  mov     r11, rsp
0x180009a13  push    rbp
0x180009a14  push    r12
0x180009a16  lea     rbp, [r11-1D8h]
0x180009a1d  sub     rsp, 2C8h
0x180009a24  mov     rax, cs:__security_cookie
0x180009a2b  xor     rax, rsp
0x180009a2e  mov     [rbp+1D0h+var_30], rax
0x180009a35  xor     r12d, r12d
0x180009a38  cmp     cs:dword_180022FC4, r12d
0x180009a3f  mov     [rbp+1D0h+hKey], r12
0x180009a43  mov     [rsp+2D0h+var_260], r12
0x180009a48  mov     [rsp+2D0h+cValues], r12d
0x180009a4d  mov     [rsp+2D0h+cbMaxValueLen], r12d
0x180009a52  mov     [rsp+2D0h+cchName], r12d
0x180009a57  jnz     loc_180009F53
0x180009a5d  mov     [r11+8], rbx
0x180009a61  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x180009a68  mov     [r11+10h], rsi
0x180009a6c  mov     ebx, r12d
0x180009a6f  mov     [r11+18h], rdi
0x180009a73  mov     [r11-18h], r13
0x180009a77  mov     [r11-20h], r14
0x180009a7b  mov     [r11-28h], r15
0x180009a7f  call    cs:__imp_EnterCriticalSection
0x180009a86  nop     dword ptr [rax+rax+00h]
0x180009a8b  cmp     cs:dword_180022FC4, ebx
0x180009a91  jnz     loc_180009E9E
0x180009a97  lea     rax, [rbp+1D0h+hKey]
0x180009a9b  mov     r9d, 20019h; samDesired
0x180009aa1  xor     r8d, r8d; ulOptions
0x180009aa4  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180009aa9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Cryptography\\Cryp"...
0x180009ab0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009ab7  call    cs:__imp_RegOpenKeyExW
0x180009abe  nop     dword ptr [rax+rax+00h]
0x180009ac3  test    eax, eax
0x180009ac5  jnz     loc_180009E9E
0x180009acb  mov     r15d, r12d
0x180009ace  mov     esi, r12d
0x180009ad1  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180009ad5  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180009ada  mov     [rsp+2D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180009adf  lea     r8, [rbp+1D0h+Name]; lpName
0x180009ae3  mov     [rsp+2D0h+lpcchClass], r12; lpcchClass
0x180009ae8  mov     edx, esi; dwIndex
0x180009aea  mov     [rsp+2D0h+lpClass], r12; lpClass
0x180009aef  mov     [rsp+2D0h+phkResult], r12; lpReserved
0x180009af4  mov     [rbp+1D0h+var_250], esi
0x180009af7  mov     [rsp+2D0h+cchName], 103h
0x180009aff  call    cs:__imp_RegEnumKeyExW
0x180009b06  nop     dword ptr [rax+rax+00h]
0x180009b0b  test    eax, eax
0x180009b0d  jnz     short loc_180009B5B
0x180009b0f  mov     ecx, r15d
0x180009b12  and     ecx, 0FFFFFFF8h
0x180009b15  cmp     cs:dword_180022FE0, eax
0x180009b1b  lea     edx, [rcx+8]
0x180009b1e  jnz     short loc_180009B7D
0x180009b20  shl     rdx, 3
0x180009b24  call    CryptXmlAlloc
0x180009b29  mov     cs:lpMem, rax
0x180009b30  test    rax, rax
0x180009b33  jnz     short loc_180009BA9
0x180009b35  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009b3c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009b41  mov     r8, rax
0x180009b44  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180009b4b  mov     edx, 8007000Eh
0x180009b50  mov     r9d, 32Ah
0x180009b56  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009b5b  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x180009b62  mov     cs:dword_180022FC4, 1
0x180009b6c  call    cs:__imp_LeaveCriticalSection
0x180009b73  nop     dword ptr [rax+rax+00h]
0x180009b78  jmp     loc_180009EF8
0x180009b7d  lea     eax, [r15+1]
0x180009b81  cmp     eax, edx
0x180009b83  jb      short loc_180009BA9
0x180009b85  lea     r8d, [rcx+10h]
0x180009b89  mov     rcx, cs:lpMem
0x180009b90  shl     r8, 3
0x180009b94  call    CryptXmlRealloc
0x180009b99  test    rax, rax
0x180009b9c  jz      loc_180009E59
0x180009ba2  mov     cs:lpMem, rax
0x180009ba9  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180009bae  test    rcx, rcx
0x180009bb1  jz      short loc_180009BC4
0x180009bb3  call    cs:__imp_RegCloseKey
0x180009bba  nop     dword ptr [rax+rax+00h]
0x180009bbf  mov     [rsp+2D0h+var_260], r12
0x180009bc4  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180009bc8  lea     rax, [rsp+2D0h+var_260]
0x180009bcd  mov     r9d, 20019h; samDesired
0x180009bd3  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180009bd8  xor     r8d, r8d; ulOptions
0x180009bdb  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x180009bdf  mov     rbx, r12
0x180009be2  call    cs:__imp_RegOpenKeyExW
0x180009be9  nop     dword ptr [rax+rax+00h]
0x180009bee  test    eax, eax
0x180009bf0  jnz     loc_180009E9E
0x180009bf6  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180009bfb  lea     rax, [rsp+2D0h+cbMaxValueLen]
0x180009c00  mov     [rsp+2D0h+var_278], r12; lpftLastWriteTime
0x180009c05  xor     r9d, r9d; lpReserved
0x180009c08  mov     [rsp+2D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180009c0d  xor     r8d, r8d; lpcchClass
0x180009c10  mov     [rsp+2D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180009c15  xor     edx, edx; lpClass
0x180009c17  mov     [rsp+2D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180009c1c  lea     rax, [rsp+2D0h+cValues]
0x180009c21  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpcValues
0x180009c26  mov     [rsp+2D0h+lpcchClass], r12; lpcbMaxClassLen
0x180009c2b  mov     [rsp+2D0h+lpClass], r12; lpcbMaxSubKeyLen
0x180009c30  mov     [rsp+2D0h+phkResult], r12; lpcSubKeys
0x180009c35  call    cs:__imp_RegQueryInfoKeyW
0x180009c3c  nop     dword ptr [rax+rax+00h]
0x180009c41  test    eax, eax
0x180009c43  jnz     loc_180009E9E
0x180009c49  mov     edx, [rsp+2D0h+cbMaxValueLen]
0x180009c4d  cmp     edx, 4
0x180009c50  jnb     short loc_180009C5B
0x180009c52  mov     edx, 4
0x180009c57  mov     [rsp+2D0h+cbMaxValueLen], edx
0x180009c5b  imul    edx, [rsp+2D0h+cValues]
0x180009c60  mov     ecx, [rsp+2D0h+cchName]
0x180009c64  inc     ecx
0x180009c66  mov     eax, edx
0x180009c68  lea     rdx, [rcx+53h]
0x180009c6c  lea     rdx, [rax+rdx*2]
0x180009c70  cmp     rdx, 0FFFFFFh
0x180009c77  ja      loc_180009E52
0x180009c7d  mov     edx, edx
0x180009c7f  call    CryptXmlAlloc
0x180009c84  mov     rbx, rax
0x180009c87  test    rax, rax
0x180009c8a  jz      loc_180009E9E
0x180009c90  lea     r9, [rax+30h]
0x180009c94  mov     [rax], r9
0x180009c97  mov     rcx, r9; void *
0x180009c9a  mov     edx, [rsp+2D0h+cchName]
0x180009c9e  mov     r8d, edx
0x180009ca1  add     r8, r8; Size
0x180009ca4  lea     eax, [rdx+1]
0x180009ca7  lea     rdx, [rbp+1D0h+Name]; Src
0x180009cab  lea     r13, [r9+rax*2]
0x180009caf  call    memcpy_0
0x180009cb4  mov     r14d, [rsp+2D0h+cbMaxValueLen]
0x180009cb9  lea     rdx, off_180022658; "DLL"
0x180009cc0  imul    r14d, [rsp+2D0h+cValues]
0x180009cc6  mov     edi, r12d
0x180009cc9  add     r14d, 6
0x180009ccd  cmp     edi, 2
0x180009cd0  jnb     loc_180009E33
0x180009cd6  mov     eax, edi
0x180009cd8  mov     [rsp+2D0h+Type], r12d
0x180009cdd  lea     rcx, [rax+rax*2]
0x180009ce1  lea     rsi, ds:0[rcx*8]
0x180009ce9  mov     ecx, [rsi+rdx+10h]
0x180009ced  add     rcx, rbx
0x180009cf0  cmp     dword ptr [rsi+rdx+8], 4
0x180009cf5  jnz     short loc_180009D01
0x180009cf7  mov     rax, rcx
0x180009cfa  mov     ecx, 4
0x180009cff  jmp     short loc_180009D0A
0x180009d01  mov     [rcx], r13
0x180009d04  mov     rax, r13
0x180009d07  mov     ecx, r14d
0x180009d0a  mov     [rsp+2D0h+cbData], ecx
0x180009d0e  lea     r12, [rsi+rdx]
0x180009d12  mov     rdx, [rsi+rdx]; lpValueName
0x180009d16  lea     rcx, [rsp+2D0h+cbData]
0x180009d1b  mov     [rsp+2D0h+lpClass], rcx; lpcbData
0x180009d20  lea     r9, [rsp+2D0h+Type]; lpType
0x180009d25  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180009d2a  xor     r8d, r8d; lpReserved
0x180009d2d  mov     [rsp+2D0h+phkResult], rax; lpData
0x180009d32  call    cs:__imp_RegQueryValueExW
0x180009d39  nop     dword ptr [rax+rax+00h]
0x180009d3e  lea     rdx, off_180022658; "DLL"
0x180009d45  test    eax, eax
0x180009d47  jnz     loc_180009E03
0x180009d4d  mov     eax, [rsi+rdx+8]
0x180009d51  cmp     eax, [rsp+2D0h+Type]
0x180009d55  jnz     loc_180009E03
0x180009d5b  cmp     eax, 4
0x180009d5e  jz      loc_180009DF9
0x180009d64  mov     ecx, [rsp+2D0h+cbData]
0x180009d68  lea     rax, aDll; "DLL"
0x180009d6f  mov     r8, [r12]; lpString1
0x180009d73  add     r13, rcx
0x180009d76  sub     r14d, ecx
0x180009d79  mov     dword ptr [rsp+2D0h+lpClass], 0FFFFFFFFh; cchCount2
0x180009d81  xor     ecx, ecx; Locale
0x180009d83  mov     [rsp+2D0h+phkResult], rax; lpString2
0x180009d88  mov     r9d, 0FFFFFFFFh; cchCount1
0x180009d8e  mov     edx, 1; dwCmpFlags
0x180009d93  call    cs:__imp_CompareStringW
0x180009d9a  nop     dword ptr [rax+rax+00h]
0x180009d9f  cmp     eax, 2
0x180009da2  jnz     short loc_180009DF2
0x180009da4  mov     rcx, [rbx+8]; lpLibFileName
0x180009da8  call    cs:__imp_LoadLibraryW
0x180009daf  nop     dword ptr [rax+rax+00h]
0x180009db4  mov     [rbx+10h], rax
0x180009db8  test    rax, rax
0x180009dbb  jz      short loc_180009DF2
0x180009dbd  lea     rdx, ProcName; "CryptXmlEncodeKeyValue"
0x180009dc4  mov     rcx, rax; hModule
0x180009dc7  call    cs:__imp_GetProcAddress
0x180009dce  nop     dword ptr [rax+rax+00h]
0x180009dd3  mov     rcx, [rbx+10h]; hModule
0x180009dd7  lea     rdx, aCryptxmlcreate_0; "CryptXmlCreateKey"
0x180009dde  mov     [rbx+20h], rax
0x180009de2  call    cs:__imp_GetProcAddress
0x180009de9  nop     dword ptr [rax+rax+00h]
0x180009dee  mov     [rbx+28h], rax
0x180009df2  lea     rdx, off_180022658; "DLL"
0x180009df9  inc     edi
0x180009dfb  xor     r12d, r12d
0x180009dfe  jmp     loc_180009CCD
0x180009e03  cmp     dword ptr [rsi+rdx+0Ch], 0
0x180009e08  jnz     short loc_180009DF9
0x180009e0a  call    cs:__imp_GetProcessHeap
0x180009e11  nop     dword ptr [rax+rax+00h]
0x180009e16  mov     r8, rbx; lpMem
0x180009e19  mov     edx, 8; dwFlags
0x180009e1e  mov     rcx, rax; hHeap
0x180009e21  call    cs:__imp_HeapFree
0x180009e28  nop     dword ptr [rax+rax+00h]
0x180009e2d  xor     r12d, r12d
0x180009e30  mov     ebx, r12d
0x180009e33  mov     edx, cs:dword_180022FE0
0x180009e39  mov     rax, cs:lpMem
0x180009e40  mov     esi, [rbp+1D0h+var_250]
0x180009e43  mov     [rax+rdx*8], rbx
0x180009e47  inc     edx
0x180009e49  mov     cs:dword_180022FE0, edx
0x180009e4f  inc     r15d
0x180009e52  inc     esi
0x180009e54  jmp     loc_180009AD1
0x180009e59  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009e60  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009e65  mov     r8, rax
0x180009e68  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180009e6f  mov     edx, 8007000Eh
0x180009e74  mov     r9d, 33Dh
0x180009e7a  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009e7f  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x180009e86  mov     cs:dword_180022FC4, 1
0x180009e90  call    cs:__imp_LeaveCriticalSection
0x180009e97  nop     dword ptr [rax+rax+00h]
0x180009e9c  jmp     short loc_180009EF8
0x180009e9e  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x180009ea5  mov     cs:dword_180022FC4, 1
0x180009eaf  call    cs:__imp_LeaveCriticalSection
0x180009eb6  nop     dword ptr [rax+rax+00h]
0x180009ebb  test    rbx, rbx
0x180009ebe  jz      short loc_180009EF8
0x180009ec0  mov     rcx, [rbx+10h]; hLibModule
0x180009ec4  test    rcx, rcx
0x180009ec7  jz      short loc_180009ED5
0x180009ec9  call    cs:__imp_FreeLibrary
0x180009ed0  nop     dword ptr [rax+rax+00h]
0x180009ed5  call    cs:__imp_GetProcessHeap
0x180009edc  nop     dword ptr [rax+rax+00h]
0x180009ee1  mov     r8, rbx; lpMem
0x180009ee4  mov     edx, 8; dwFlags
0x180009ee9  mov     rcx, rax; hHeap
0x180009eec  call    cs:__imp_HeapFree
0x180009ef3  nop     dword ptr [rax+rax+00h]
0x180009ef8  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180009efd  mov     r15, [rsp+2D0h+var_20]
0x180009f05  mov     r14, [rsp+2D0h+var_18]
0x180009f0d  mov     r13, [rsp+2C0h]
0x180009f15  mov     rdi, [rsp+2D0h+arg_10]
0x180009f1d  mov     rsi, [rsp+2D0h+arg_8]
0x180009f25  mov     rbx, [rsp+2D0h+arg_0]
0x180009f2d  test    rcx, rcx
0x180009f30  jz      short loc_180009F3E
0x180009f32  call    cs:__imp_RegCloseKey
0x180009f39  nop     dword ptr [rax+rax+00h]
0x180009f3e  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180009f42  test    rcx, rcx
0x180009f45  jz      short loc_180009F53
0x180009f47  call    cs:__imp_RegCloseKey
0x180009f4e  nop     dword ptr [rax+rax+00h]
0x180009f53  mov     rcx, [rbp+1D0h+var_30]
0x180009f5a  xor     rcx, rsp; StackCookie
0x180009f5d  call    __security_check_cookie
0x180009f62  add     rsp, 2C8h
0x180009f69  pop     r12
0x180009f6b  pop     rbp
0x180009f6c  retn
```
