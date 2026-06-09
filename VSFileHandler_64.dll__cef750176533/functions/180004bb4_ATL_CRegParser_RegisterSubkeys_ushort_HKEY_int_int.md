# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004bb4`
- end: `0x180005394`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2016`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004bb4`
- `0x180005394`

## callees

- `0x180001848`
- `0x180002238`
- `0x180004128`
- `0x18000421c`
- `0x18000483c`
- `0x1800048ec`
- `0x180004a00`
- `0x180004a10`
- `0x180004bb4`
- `0x180007700`
- `0x18000bb9c`
- `0x18001aff0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180005317`
- `ADVAPI32!RegDeleteKeyW` at `0x180005317`
- `ADVAPI32!RegCloseKey` at `0x180004e58`
- `ADVAPI32!RegCloseKey` at `0x180004f5f`
- `ADVAPI32!RegCloseKey` at `0x180004f90`
- `ADVAPI32!RegCloseKey` at `0x180005286`
- `ADVAPI32!RegCloseKey` at `0x180005357`
- `ADVAPI32!RegCloseKey` at `0x180004e58`
- `ADVAPI32!RegCloseKey` at `0x180004f5f`
- `ADVAPI32!RegCloseKey` at `0x180004f90`
- `ADVAPI32!RegCloseKey` at `0x180005286`
- `ADVAPI32!RegCloseKey` at `0x180005357`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800051c4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005266`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800051c4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005266`
- `ADVAPI32!RegCreateKeyExW` at `0x180004f47`
- `ADVAPI32!RegCreateKeyExW` at `0x180004f47`
- `ADVAPI32!RegDeleteValueW` at `0x180004e3f`
- `ADVAPI32!RegDeleteValueW` at `0x180004e3f`
- `KERNEL32!lstrcmpiW` at `0x180004c3a`
- `KERNEL32!lstrcmpiW` at `0x180004c4c`
- `KERNEL32!lstrcmpiW` at `0x180004cc7`
- `KERNEL32!lstrcmpiW` at `0x180004d48`
- `KERNEL32!lstrcmpiW` at `0x180004d74`
- `KERNEL32!lstrcmpiW` at `0x1800051eb`
- `KERNEL32!lstrcmpiW` at `0x180004c3a`
- `KERNEL32!lstrcmpiW` at `0x180004c4c`
- `KERNEL32!lstrcmpiW` at `0x180004cc7`
- `KERNEL32!lstrcmpiW` at `0x180004d48`
- `KERNEL32!lstrcmpiW` at `0x180004d74`
- `KERNEL32!lstrcmpiW` at `0x1800051eb`
- `KERNEL32!GetModuleHandleW` at `0x1800052c1`
- `KERNEL32!GetModuleHandleW` at `0x1800052c1`
- `KERNEL32!GetProcAddress` at `0x1800052d6`
- `KERNEL32!GetProcAddress` at `0x1800052d6`
- `USER32!CharNextW` at `0x180004c9e`
- `USER32!CharNextW` at `0x180004e89`
- `USER32!CharNextW` at `0x180004c9e`
- `USER32!CharNextW` at `0x180004e89`

## string_xrefs

- `0x1800052ba`: `Advapi32.dll`
- `0x1800052cc`: `RegDeleteKeyExW`
- `0x180004c30`: `Delete`
- `0x180004c42`: `ForceRemove`
- `0x180004d3e`: `NoRemove`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  HKEY v5; // r14
  HKEY v8; // r15
  int Token; // ebx
  int v10; // r12d
  int v11; // esi
  LPWSTR v12; // rcx
  WCHAR i; // ax
  LPCWSTR *v14; // rbx
  int v15; // esi
  HRESULT v16; // eax
  unsigned int v17; // eax
  HKEY v18; // rsi
  LSTATUS v19; // eax
  int v20; // eax
  LPWSTR v21; // rcx
  WCHAR j; // ax
  __int64 v23; // r9
  LSTATUS v24; // eax
  unsigned int v25; // ecx
  __int64 v27; // rax
  int v28; // esi
  int v29; // r14d
  errno_t v30; // eax
  __int64 v31; // rax
  LPCWSTR *v32; // rsi
  int v33; // esi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HKEY v36; // rcx
  unsigned __int16 *dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *phkResult; // [rsp+38h] [rbp-C8h]
  HKEY v43; // [rsp+70h] [rbp-90h] BYREF
  HKEY v44[2]; // [rsp+78h] [rbp-88h] BYREF
  ATL::CAtlTransactionManager *v45; // [rsp+88h] [rbp-78h]
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h]
  DWORD dwDisposition; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a3;
  v8 = 0;
  v44[0] = 0;
  v44[1] = 0;
  v45 = 0;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    _mm_lfence();
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *a2 == 125 )
          goto LABEL_58;
        v10 = 1;
        v11 = lstrcmpiW(a2, L"Delete");
        if ( !lstrcmpiW(a2, L"ForceRemove") || !v11 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_58;
          _mm_lfence();
          if ( a4 )
          {
            hKey[1] = 0;
            hKey[0] = 0;
            v47 = 0;
            v12 = a2;
            for ( i = *a2; i; i = *v12 )
            {
              if ( i == 92 )
              {
                if ( v12 )
                  goto LABEL_127;
                break;
              }
              v12 = CharNextW(v12);
            }
            v14 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
            while ( lstrcmpiW(a2, *v14) )
            {
              if ( (__int64)++v14 >= (__int64)L"# Visual Studio 2010\r\n" )
              {
                _mm_lfence();
                hKey[0] = v5;
                LODWORD(hKey[1]) = 0;
                v47 = 0;
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a2);
                break;
              }
            }
            if ( !v11 )
            {
              _mm_lfence();
              Token = ATL::CRegParser::NextToken(this, a2);
              if ( Token < 0 )
                goto LABEL_58;
              _mm_lfence();
              Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
              if ( Token < 0 )
                goto LABEL_58;
              v15 = a4;
              goto LABEL_66;
            }
          }
        }
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v10 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_58;
        }
        if ( lstrcmpiW(a2, L"Val") )
          break;
        Token = ATL::CRegParser::NextToken(this, ValueName);
        if ( Token < 0 )
          goto LABEL_58;
        _mm_lfence();
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_58;
        if ( *a2 != 61 )
        {
LABEL_127:
          Token = -2147352567;
          goto LABEL_58;
        }
        v15 = a4;
        if ( a4 )
        {
          _mm_lfence();
          hKey[0] = v5;
          hKey[1] = 0;
          v47 = 0;
          v16 = ATL::CRegParser::AddValue(this, hKey, ValueName, a2);
          Token = v16;
LABEL_65:
          if ( v16 < 0 )
            goto LABEL_58;
LABEL_66:
          if ( *a2 == 123 )
          {
            v27 = -1;
            do
              ++v27;
            while ( a2[v27] );
            if ( v27 == 1 )
            {
              Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v8, v15, 0);
              if ( Token < 0 )
                goto LABEL_58;
              _mm_lfence();
              v20 = ATL::CRegParser::NextToken(this, a2);
              goto LABEL_36;
            }
          }
        }
        else
        {
          if ( !a5 && v10 )
          {
            hKey[1] = 0;
            hKey[0] = 0;
            v47 = 0;
            v17 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v5, 0, 0x20006u);
            if ( v17 )
            {
              Token = ATL::AtlHresultFromWin32(v17);
              v36 = hKey[0];
              if ( !hKey[0] )
                goto LABEL_58;
              goto LABEL_126;
            }
            v18 = hKey[0];
            v19 = RegDeleteValueW(hKey[0], ValueName);
            if ( (v19 & 0xFFFFFFFD) != 0 )
            {
              Token = ATL::AtlHresultFromWin32(v19);
              if ( !v18 )
                goto LABEL_58;
              v36 = v18;
LABEL_126:
              RegCloseKey(v36);
              goto LABEL_58;
            }
            if ( v18 )
              RegCloseKey(v18);
          }
          _mm_lfence();
          v20 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
LABEL_36:
          Token = v20;
          if ( v20 < 0 )
            goto LABEL_58;
        }
      }
      v21 = a2;
      for ( j = *a2; j; j = *v21 )
      {
        if ( j == 92 )
        {
          if ( v21 )
            goto LABEL_127;
          break;
        }
        v21 = CharNextW(v21);
      }
      v15 = a4;
      if ( a4 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v44, v5, a2, 0x2001Fu)
          && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v44, v5, a2, 0x20019u) )
        {
          v43 = 0;
          if ( v45 )
            v24 = ATL::CAtlTransactionManager::RegCreateKeyExW(
                    v45,
                    v5,
                    a2,
                    v23,
                    dwOptions,
                    samDesired,
                    lpSecurityAttributes,
                    phkResult,
                    &v43,
                    &dwDisposition);
          else
            v24 = RegCreateKeyExW(v5, a2, 0, 0, 0, 0x2001Fu, 0, &v43, &dwDisposition);
          if ( v24 )
          {
            v8 = v44[0];
          }
          else
          {
            v24 = 0;
            if ( v44[0] )
              v24 = RegCloseKey(v44[0]);
            v8 = v43;
            v44[0] = v43;
            LODWORD(v44[1]) = 0;
          }
          if ( v24 )
            goto LABEL_56;
        }
        else
        {
          v8 = v44[0];
        }
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          break;
        if ( *a2 != 61 )
          goto LABEL_66;
        _mm_lfence();
        v16 = ATL::CRegParser::AddValue(this, v44, 0, a2);
        Token = v16;
        v8 = v44[0];
        goto LABEL_65;
      }
      if ( a5 )
      {
        v28 = 2;
      }
      else
      {
        v28 = ATL::CRegKey::Open((ATL::CRegKey *)v44, v5, a2, 0x20019u);
        v8 = v44[0];
      }
      v29 = 1;
      if ( !v28 )
        v29 = a5;
      v30 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
      if ( v30 )
      {
        if ( v30 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v30 == 22 || v30 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v30 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      _mm_lfence();
      Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
      if ( Token < 0 )
        break;
      if ( *a2 == 123 )
      {
        _mm_lfence();
        v31 = -1;
        do
          ++v31;
        while ( a2[v31] );
        if ( v31 == 1 )
        {
          _mm_lfence();
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v8, 0, v29);
          if ( Token < 0 && !v29 )
            break;
          _mm_lfence();
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
      }
      if ( v28 == 2 )
        goto LABEL_94;
      if ( v28 )
      {
        if ( !a5 )
        {
          v25 = v28;
          goto LABEL_57;
        }
        goto LABEL_94;
      }
      if ( a5 )
      {
        LODWORD(v43) = 0;
        if ( !RegQueryInfoKeyW(v8, 0, 0, 0, (LPDWORD)&v43, 0, 0, 0, 0, 0, 0, 0) )
        {
          if ( (_DWORD)v43 )
          {
            v32 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
            while ( lstrcmpiW(Destination, *v32) )
            {
              if ( (__int64)++v32 >= (__int64)L"# Visual Studio 2010\r\n" )
              {
                if ( v10 )
                {
                  ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v44, Destination);
                  v8 = v44[0];
                }
                goto LABEL_94;
              }
            }
            goto LABEL_94;
          }
        }
      }
      LODWORD(v43) = 0;
      v33 = 0;
      if ( !RegQueryInfoKeyW(v8, 0, 0, 0, (LPDWORD)&v43, 0, 0, 0, 0, 0, 0, 0) )
        LOBYTE(v33) = (_DWORD)v43 != 0;
      v24 = 0;
      if ( v8 )
      {
        v24 = RegCloseKey(v8);
        v8 = 0;
        v44[0] = 0;
      }
      LODWORD(v44[1]) = 0;
      if ( v24 )
      {
LABEL_56:
        v25 = v24;
LABEL_57:
        Token = ATL::AtlHresultFromWin32(v25);
        break;
      }
      if ( !v10 || v33 )
      {
LABEL_94:
        v5 = a3;
      }
      else
      {
        if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
        {
          ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
        }
        else
        {
          ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
          if ( ModuleHandleW )
          {
            ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
            `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)ProcAddress;
          }
          else
          {
            ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
          }
          `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
        }
        v5 = a3;
        if ( ProcAddress )
          v24 = ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, _QWORD))ProcAddress)(a3, Destination, 0, 0);
        else
          v24 = RegDeleteKeyW(a3, Destination);
        if ( v24 )
          goto LABEL_56;
      }
    }
  }
LABEL_58:
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180004bb4  push    rbp
0x180004bb6  push    rbx
0x180004bb7  push    rsi
0x180004bb8  push    rdi
0x180004bb9  push    r12
0x180004bbb  push    r13
0x180004bbd  push    r14
0x180004bbf  push    r15
0x180004bc1  lea     rbp, [rsp-21D8h]
0x180004bc9  mov     eax, 22D8h
0x180004bce  call    _alloca_probe
0x180004bd3  sub     rsp, rax
0x180004bd6  mov     rax, cs:__security_cookie
0x180004bdd  xor     rax, rsp
0x180004be0  mov     [rbp+2210h+var_50], rax
0x180004be7  mov     [rsp+2310h+var_22B0], r9d
0x180004bec  mov     r14, r8
0x180004bef  mov     [rsp+2310h+var_22A8], r8
0x180004bf4  mov     rdi, rdx
0x180004bf7  mov     r13, rcx
0x180004bfa  xorps   xmm0, xmm0
0x180004bfd  xor     eax, eax
0x180004bff  movups  xmmword ptr [rsp+2310h+var_2298], xmm0
0x180004c04  mov     r15d, eax
0x180004c07  mov     [rsp+2310h+var_2298], rax
0x180004c0c  mov     dword ptr [rbp+2210h+var_2298+8], eax
0x180004c0f  mov     [rbp+2210h+var_2288], rax
0x180004c13  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004c18  mov     ebx, eax
0x180004c1a  test    eax, eax
0x180004c1c  js      loc_180004F88
0x180004c22  lfence
0x180004c25  jmp     loc_18000516D
0x180004c2a  mov     r12d, 1
0x180004c30  lea     rdx, aDelete; "Delete"
0x180004c37  mov     rcx, rdi; lpString1
0x180004c3a  call    cs:__imp_lstrcmpiW
0x180004c40  mov     esi, eax
0x180004c42  lea     rdx, aForceremove; "ForceRemove"
0x180004c49  mov     rcx, rdi; lpString1
0x180004c4c  call    cs:__imp_lstrcmpiW
0x180004c52  xor     ebx, ebx
0x180004c54  test    eax, eax
0x180004c56  jz      short loc_180004C60
0x180004c58  test    esi, esi
0x180004c5a  jnz     loc_180004D3E
0x180004c60  mov     rdx, rdi; unsigned __int16 *
0x180004c63  mov     rcx, r13; this
0x180004c66  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004c6b  mov     ebx, eax
0x180004c6d  xor     edx, edx
0x180004c6f  test    eax, eax
0x180004c71  js      loc_180004F88
0x180004c77  lfence
0x180004c7a  cmp     [rsp+2310h+var_22B0], edx
0x180004c7e  jz      loc_180004D3C
0x180004c84  mov     [rbp+2210h+hKey+8], rdx
0x180004c88  mov     [rbp+2210h+hKey], rdx
0x180004c8c  mov     [rbp+2210h+var_2270], rdx
0x180004c90  mov     rcx, rdi
0x180004c93  movzx   eax, word ptr [rdi]
0x180004c96  jmp     short loc_180004CAA
0x180004c98  cmp     ax, 5Ch ; '\'
0x180004c9c  jz      short loc_180004CB1
0x180004c9e  call    cs:__imp_CharNextW
0x180004ca4  mov     rcx, rax; lpsz
0x180004ca7  movzx   eax, word ptr [rax]
0x180004caa  test    ax, ax
0x180004cad  jnz     short loc_180004C98
0x180004caf  jmp     short loc_180004CBA
0x180004cb1  test    rcx, rcx
0x180004cb4  jnz     loc_180005362
0x180004cba  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004cc1  mov     rdx, [rbx]; lpString2
0x180004cc4  mov     rcx, rdi; lpString1
0x180004cc7  call    cs:__imp_lstrcmpiW
0x180004ccd  xor     ecx, ecx
0x180004ccf  test    eax, eax
0x180004cd1  jz      short loc_180004CFD
0x180004cd3  add     rbx, 8
0x180004cd7  lea     rax, aVisualStudio20; "# Visual Studio 2010\r\n"
0x180004cde  cmp     rbx, rax
0x180004ce1  jl      short loc_180004CC1
0x180004ce3  lfence
0x180004ce6  mov     [rbp+2210h+hKey], r14
0x180004cea  mov     dword ptr [rbp+2210h+hKey+8], ecx
0x180004ced  mov     [rbp+2210h+var_2270], rcx
0x180004cf1  mov     rdx, rdi; unsigned __int16 *
0x180004cf4  lea     rcx, [rbp+2210h+hKey]; this
0x180004cf8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004cfd  test    esi, esi
0x180004cff  jnz     short loc_180004D3C
0x180004d01  lfence
0x180004d04  mov     rdx, rdi; unsigned __int16 *
0x180004d07  mov     rcx, r13; this
0x180004d0a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004d0f  mov     ebx, eax
0x180004d11  test    eax, eax
0x180004d13  js      loc_180004F88
0x180004d19  lfence
0x180004d1c  mov     rdx, rdi; unsigned __int16 *
0x180004d1f  mov     rcx, r13; this
0x180004d22  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004d27  mov     ebx, eax
0x180004d29  xor     edx, edx
0x180004d2b  test    eax, eax
0x180004d2d  js      loc_180004F88
0x180004d33  mov     esi, [rsp+2310h+var_22B0]
0x180004d37  jmp     loc_180004FFC
0x180004d3c  xor     ebx, ebx
0x180004d3e  lea     rdx, aNoremove; "NoRemove"
0x180004d45  mov     rcx, rdi; lpString1
0x180004d48  call    cs:__imp_lstrcmpiW
0x180004d4e  test    eax, eax
0x180004d50  jnz     short loc_180004D6A
0x180004d52  mov     r12d, ebx
0x180004d55  mov     rdx, rdi; unsigned __int16 *
0x180004d58  mov     rcx, r13; this
0x180004d5b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004d60  mov     ebx, eax
0x180004d62  test    eax, eax
0x180004d64  js      loc_180004F88
0x180004d6a  lea     rdx, aVal; "Val"
0x180004d71  mov     rcx, rdi; lpString1
0x180004d74  call    cs:__imp_lstrcmpiW
0x180004d7a  test    eax, eax
0x180004d7c  jnz     loc_180004E7B
0x180004d82  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004d89  mov     rcx, r13; this
0x180004d8c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004d91  mov     ebx, eax
0x180004d93  test    eax, eax
0x180004d95  js      loc_180004F88
0x180004d9b  lfence
0x180004d9e  mov     rdx, rdi; unsigned __int16 *
0x180004da1  mov     rcx, r13; this
0x180004da4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004da9  mov     ebx, eax
0x180004dab  xor     edx, edx
0x180004dad  test    eax, eax
0x180004daf  js      loc_180004F88
0x180004db5  cmp     word ptr [rdi], 3Dh ; '='
0x180004db9  jnz     loc_180005362
0x180004dbf  mov     esi, [rsp+2310h+var_22B0]
0x180004dc3  test    esi, esi
0x180004dc5  jz      short loc_180004DFB
0x180004dc7  lfence
0x180004dca  xorps   xmm0, xmm0
0x180004dcd  movups  xmmword ptr [rbp+2210h+hKey], xmm0
0x180004dd1  mov     [rbp+2210h+hKey], r14
0x180004dd5  mov     dword ptr [rbp+2210h+hKey+8], edx
0x180004dd8  mov     [rbp+2210h+var_2270], rdx
0x180004ddc  mov     r9, rdi; unsigned __int16 *
0x180004ddf  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004de6  lea     rdx, [rbp+2210h+hKey]; struct ATL::CRegKey *
0x180004dea  mov     rcx, r13; this
0x180004ded  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004df2  mov     ebx, eax
0x180004df4  xor     edx, edx
0x180004df6  jmp     loc_180004FF8
0x180004dfb  cmp     [rbp+2210h+arg_20], edx
0x180004e01  jnz     short loc_180004E5E
0x180004e03  test    r12d, r12d
0x180004e06  jz      short loc_180004E5E
0x180004e08  mov     [rbp+2210h+hKey+8], rdx
0x180004e0c  mov     [rbp+2210h+hKey], rdx
0x180004e10  mov     [rbp+2210h+var_2270], rdx
0x180004e14  mov     r9d, 20006h; unsigned int
0x180004e1a  xor     r8d, r8d; unsigned __int16 *
0x180004e1d  mov     rdx, r14; HKEY
0x180004e20  lea     rcx, [rbp+2210h+hKey]; this
0x180004e24  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004e29  test    eax, eax
0x180004e2b  jnz     loc_180005341
0x180004e31  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180004e38  mov     rsi, [rbp+2210h+hKey]
0x180004e3c  mov     rcx, rsi; hKey
0x180004e3f  call    cs:__imp_RegDeleteValueW
0x180004e45  test    eax, 0FFFFFFFDh
0x180004e4a  jnz     loc_18000532A
0x180004e50  test    rsi, rsi
0x180004e53  jz      short loc_180004E5E
0x180004e55  mov     rcx, rsi; hKey
0x180004e58  call    cs:__imp_RegCloseKey
0x180004e5e  lfence
0x180004e61  mov     rdx, rdi; unsigned __int16 *
0x180004e64  mov     rcx, r13; this
0x180004e67  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004e6c  mov     ebx, eax
0x180004e6e  test    eax, eax
0x180004e70  js      loc_180004F88
0x180004e76  jmp     loc_18000516D
0x180004e7b  mov     rcx, rdi
0x180004e7e  movzx   eax, word ptr [rdi]
0x180004e81  jmp     short loc_180004E95
0x180004e83  cmp     ax, 5Ch ; '\'
0x180004e87  jz      short loc_180004E9C
0x180004e89  call    cs:__imp_CharNextW
0x180004e8f  mov     rcx, rax; lpsz
0x180004e92  movzx   eax, word ptr [rax]
0x180004e95  test    ax, ax
0x180004e98  jnz     short loc_180004E83
0x180004e9a  jmp     short loc_180004EA5
0x180004e9c  test    rcx, rcx
0x180004e9f  jnz     loc_180005362
0x180004ea5  mov     esi, [rsp+2310h+var_22B0]
0x180004ea9  test    esi, esi
0x180004eab  jz      loc_18000504F
0x180004eb1  mov     r15d, 2001Fh
0x180004eb7  mov     r9d, r15d; unsigned int
0x180004eba  mov     r8, rdi; unsigned __int16 *
0x180004ebd  mov     rdx, r14; HKEY
0x180004ec0  lea     rcx, [rsp+2310h+var_2298]; this
0x180004ec5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004eca  xor     ebx, ebx
0x180004ecc  test    eax, eax
0x180004ece  jz      loc_180004FBB
0x180004ed4  lea     r9d, [r15-6]; unsigned int
0x180004ed8  mov     r8, rdi; unsigned __int16 *
0x180004edb  mov     rdx, r14; HKEY
0x180004ede  lea     rcx, [rsp+2310h+var_2298]; this
0x180004ee3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004ee8  test    eax, eax
0x180004eea  jz      loc_180004FBB
0x180004ef0  mov     [rsp+2310h+var_22A0], rbx
0x180004ef5  mov     rcx, [rbp+2210h+var_2288]; this
0x180004ef9  lea     rax, [rbp+2210h+dwDisposition]
0x180004efd  test    rcx, rcx
0x180004f00  jz      short loc_180004F1E
0x180004f02  mov     [rsp+2310h+lpcbMaxValueLen], rax; unsigned int *
0x180004f07  lea     rax, [rsp+2310h+var_22A0]
0x180004f0c  mov     [rsp+2310h+lpdwDisposition], rax; HKEY *
0x180004f11  mov     r8, rdi; unsigned __int16 *
0x180004f14  mov     rdx, r14; HKEY
0x180004f17  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x180004f1c  jmp     short loc_180004F4D
0x180004f1e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004f23  lea     rax, [rsp+2310h+var_22A0]
0x180004f28  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004f2d  mov     [rsp+2310h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180004f32  mov     [rsp+2310h+samDesired], r15d; samDesired
0x180004f37  mov     [rsp+2310h+dwOptions], ebx; dwOptions
0x180004f3b  xor     r9d, r9d; lpClass
0x180004f3e  xor     r8d, r8d; Reserved
0x180004f41  mov     rdx, rdi; lpSubKey
0x180004f44  mov     rcx, r14; hKey
0x180004f47  call    cs:__imp_RegCreateKeyExW
0x180004f4d  xor     edx, edx
0x180004f4f  test    eax, eax
0x180004f51  jnz     short loc_180004F76
0x180004f53  mov     eax, edx
0x180004f55  mov     rcx, [rsp+2310h+var_2298]; hKey
0x180004f5a  test    rcx, rcx
0x180004f5d  jz      short loc_180004F67
0x180004f5f  call    cs:__imp_RegCloseKey
0x180004f65  xor     edx, edx
0x180004f67  mov     r15, [rsp+2310h+var_22A0]
0x180004f6c  mov     [rsp+2310h+var_2298], r15
0x180004f71  mov     dword ptr [rbp+2210h+var_2298+8], edx
0x180004f74  jmp     short loc_180004F7B
0x180004f76  mov     r15, [rsp+2310h+var_2298]
0x180004f7b  test    eax, eax
0x180004f7d  jz      short loc_180004FC0
0x180004f7f  mov     ecx, eax; unsigned int
0x180004f81  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180004f86  mov     ebx, eax
0x180004f88  test    r15, r15
0x180004f8b  jz      short loc_180004F96
0x180004f8d  mov     rcx, r15; hKey
0x180004f90  call    cs:__imp_RegCloseKey
0x180004f96  mov     eax, ebx
0x180004f98  mov     rcx, [rbp+2210h+var_50]
0x180004f9f  xor     rcx, rsp; StackCookie
0x180004fa2  call    __security_check_cookie
0x180004fa7  add     rsp, 22D8h
0x180004fae  pop     r15
0x180004fb0  pop     r14
0x180004fb2  pop     r13
0x180004fb4  pop     r12
0x180004fb6  pop     rdi
0x180004fb7  pop     rsi
0x180004fb8  pop     rbx
0x180004fb9  pop     rbp
0x180004fba  retn
0x180004fbb  mov     r15, [rsp+2310h+var_2298]
0x180004fc0  mov     rdx, rdi; unsigned __int16 *
0x180004fc3  mov     rcx, r13; this
0x180004fc6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004fcb  mov     ebx, eax
0x180004fcd  xor     edx, edx
0x180004fcf  test    eax, eax
0x180004fd1  js      short loc_180004F88
0x180004fd3  cmp     word ptr [rdi], 3Dh ; '='
0x180004fd7  jnz     short loc_180004FFC
0x180004fd9  lfence
0x180004fdc  mov     r9, rdi; unsigned __int16 *
0x180004fdf  xor     r8d, r8d; unsigned __int16 *
0x180004fe2  lea     rdx, [rsp+2310h+var_2298]; struct ATL::CRegKey *
0x180004fe7  mov     rcx, r13; this
0x180004fea  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
  ... truncated ...
```
