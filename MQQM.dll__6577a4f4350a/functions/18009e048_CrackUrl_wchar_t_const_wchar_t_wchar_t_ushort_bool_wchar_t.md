# CrackUrl(wchar_t const *,wchar_t * *,wchar_t * *,ushort *,bool *,wchar_t * *)

- ea: `0x18009e048`
- end: `0x18009e453`
- name: `?CrackUrl@@YAXPEB_WPEAPEA_W1PEAGPEA_N1@Z`
- size: `1035`
- prototype: `void __usercall(LPCWSTR pwszUrl@<rcx>, wchar_t **@<rdx>, wchar_t **@<r8>, unsigned __int16 *@<r9>, bool *, wchar_t **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009e45c`
- `0x1800c7f5c`

## callees

- `0x180004d91`
- `0x18000ba64`
- `0x18000f7e4`
- `0x18002c61c`
- `0x18009bd1c`
- `0x18009e048`
- `0x1800d6e56`

## import_xrefs

- `msvcrt!free` at `0x18009e31a`
- `msvcrt!free` at `0x18009e3ca`
- `msvcrt!free` at `0x18009e3ec`
- `msvcrt!free` at `0x18009e3f6`
- `msvcrt!free` at `0x18009e400`
- `msvcrt!free` at `0x18009e31a`
- `msvcrt!free` at `0x18009e3ca`
- `msvcrt!free` at `0x18009e3ec`
- `msvcrt!free` at `0x18009e3f6`
- `msvcrt!free` at `0x18009e400`
- `msvcrt!_wcsnicmp` at `0x18009e345`
- `msvcrt!_wcsnicmp` at `0x18009e345`
- `KERNEL32!GetLastError` at `0x18009e0e8`
- `KERNEL32!GetLastError` at `0x18009e1bc`
- `KERNEL32!GetLastError` at `0x18009e238`
- `KERNEL32!GetLastError` at `0x18009e2c8`
- `KERNEL32!GetLastError` at `0x18009e0e8`
- `KERNEL32!GetLastError` at `0x18009e1bc`
- `KERNEL32!GetLastError` at `0x18009e238`
- `KERNEL32!GetLastError` at `0x18009e2c8`
- `WINHTTP!WinHttpCrackUrl` at `0x18009e0d6`
- `WINHTTP!WinHttpCrackUrl` at `0x18009e1b2`
- `WINHTTP!WinHttpCrackUrl` at `0x18009e0d6`
- `WINHTTP!WinHttpCrackUrl` at `0x18009e1b2`
- `WINHTTP!WinHttpCreateUrl` at `0x18009e22e`
- `WINHTTP!WinHttpCreateUrl` at `0x18009e2be`
- `WINHTTP!WinHttpCreateUrl` at `0x18009e22e`
- `WINHTTP!WinHttpCreateUrl` at `0x18009e2be`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CrackUrl(LPCWSTR pwszUrl, CHAR **a2, wchar_t **a3, unsigned __int16 *a4, bool *a5, wchar_t **a6)
{
  CHAR *v9; // rbx
  CHAR *v10; // rsi
  CHAR *v11; // r15
  signed int LastError; // eax
  int v13; // ebx
  signed int v14; // ecx
  signed int v15; // eax
  int v16; // ebx
  signed int v17; // ecx
  WCHAR *v18; // rdi
  signed int v19; // eax
  int v20; // edi
  signed int v21; // ecx
  signed int v22; // eax
  int v23; // ebx
  signed int v24; // ecx
  __int64 v25; // rax
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  _WORD v28[2]; // [rsp+20h] [rbp-B9h] BYREF
  DWORD pdwUrlLength; // [rsp+24h] [rbp-B5h] BYREF
  CHAR *v30; // [rsp+28h] [rbp-B1h]
  CHAR *v31; // [rsp+30h] [rbp-A9h]
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-A1h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+60h] [rbp-79h] BYREF
  CHAR *v34; // [rsp+D0h] [rbp-9h]
  WCHAR *v35; // [rsp+D8h] [rbp-1h]

  v28[0] = 0;
  v9 = 0;
  v31 = 0;
  v10 = 0;
  v34 = 0;
  v11 = 0;
  v30 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszScheme = (LPSTR)v28;
  UrlComponents.dwSchemeLength = 1;
  UrlComponents.lpszHostName = (LPSTR)v28;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.lpszUrlPath = (LPSTR)v28;
  UrlComponents.dwUrlPathLength = 1;
  if ( !WinHttpCrackUrl(pwszUrl, 0, 0x80000000, &UrlComponents) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      if ( v14 < 0 )
        LogMsgHR(v14, (wchar_t *)L"tm", 0x6Eu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v13);
      throw (bad_win32_error *)pExceptionObject;
    }
    v9 = (CHAR *)MmAllocate(saturated_mul(UrlComponents.dwUrlPathLength, 2u));
    v31 = v9;
    v10 = (CHAR *)MmAllocate(saturated_mul(UrlComponents.dwSchemeLength, 2u));
    v34 = v10;
    v11 = (CHAR *)MmAllocate(saturated_mul(UrlComponents.dwHostNameLength, 2u));
    v30 = v11;
    UrlComponents.lpszScheme = v10;
    UrlComponents.lpszHostName = v11;
    UrlComponents.lpszUrlPath = v9;
    if ( !WinHttpCrackUrl(pwszUrl, 0, 0x80000000, &UrlComponents) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v17 = (unsigned __int16)v15 | 0x80070000;
      else
        v17 = v15;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"tm", 0x78u);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v16);
      throw (bad_win32_error *)pExceptionObject;
    }
  }
  if ( a6 )
  {
    v18 = 0;
    v35 = 0;
    pdwUrlLength = 0;
    if ( !WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength) )
    {
      v19 = GetLastError();
      v20 = v19;
      if ( v19 != 122 )
      {
        if ( v19 > 0 )
          v21 = (unsigned __int16)v19 | 0x80070000;
        else
          v21 = v19;
        if ( v21 < 0 )
          LogMsgHR(v21, (wchar_t *)L"tm", 0x82u);
        bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v20);
        throw (bad_win32_error *)pExceptionObject;
      }
      v18 = (WCHAR *)MmAllocate(saturated_mul(pdwUrlLength, 2u));
      v35 = v18;
    }
    if ( !WinHttpCreateUrl(&UrlComponents, 0, v18, &pdwUrlLength) )
    {
      v22 = GetLastError();
      v23 = v22;
      if ( v22 > 0 )
        v24 = (unsigned __int16)v22 | 0x80070000;
      else
        v24 = v22;
      if ( v24 < 0 )
        LogMsgHR(v24, (wchar_t *)L"tm", 0x8Cu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v23);
      throw (bad_win32_error *)pExceptionObject;
    }
    *a6 = v18;
    free(0);
  }
  if ( !UrlComponents.dwSchemeLength || !UrlComponents.lpszScheme )
  {
    LogMsgHR(-2147012891, (wchar_t *)L"tm", 0x96u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, 12005);
    throw (bad_win32_error *)pExceptionObject;
  }
  *a5 = _wcsnicmp((const wchar_t *)UrlComponents.lpszScheme, L"https", 5u) == 0;
  *(_WORD *)&v11[2 * UrlComponents.dwHostNameLength] = 0;
  if ( UrlComponents.dwHostNameLength )
  {
    if ( *(_WORD *)UrlComponents.lpszHostName == 91 )
    {
      v25 = UrlComponents.dwHostNameLength - 1;
      if ( *(_WORD *)&UrlComponents.lpszHostName[2 * v25] == 93 )
      {
        *(_WORD *)&UrlComponents.lpszHostName[2 * (unsigned int)v25] = 0;
        StringCchCopyNW(
          (wchar_t *)UrlComponents.lpszHostName,
          UrlComponents.dwHostNameLength,
          (const wchar_t *)UrlComponents.lpszHostName + 1,
          UrlComponents.dwHostNameLength - 1);
      }
    }
  }
  v30 = 0;
  *a2 = v11;
  *a4 = UrlComponents.nPort;
  if ( UrlComponents.dwUrlPathLength )
  {
    *(_WORD *)&v9[2 * UrlComponents.dwUrlPathLength] = 0;
    v27 = (wchar_t *)v9;
    v9 = 0;
    v31 = 0;
    *a3 = v27;
  }
  else
  {
    v26 = (wchar_t *)MmAllocate(4u);
    *(_DWORD *)v26 = 47;
    *a3 = v26;
    free(0);
  }
  free(0);
  free(v10);
  free(v9);
}

```

## disassembly

```asm
0x18009e048  mov     [rsp-8+arg_8], rdx
0x18009e04d  push    rbp
0x18009e04e  push    rbx
0x18009e04f  push    rsi
0x18009e050  push    rdi
0x18009e051  push    r12
0x18009e053  push    r13
0x18009e055  push    r14
0x18009e057  push    r15
0x18009e059  lea     rbp, [rsp-0Fh]
0x18009e05e  sub     rsp, 0E8h
0x18009e065  mov     r13, r9
0x18009e068  mov     r12, r8
0x18009e06b  mov     rdi, rcx
0x18009e06e  xor     eax, eax
0x18009e070  mov     [rsp+120h+var_100], ax
0x18009e075  xor     ebx, ebx
0x18009e077  mov     [rsp+120h+var_F0], rbx
0x18009e07c  xor     esi, esi
0x18009e07e  mov     [rbp+47h+var_50], rsi
0x18009e082  xor     r15d, r15d
0x18009e085  mov     [rsp+120h+var_F8], r15
0x18009e08a  lea     r14d, [rax+68h]
0x18009e08e  mov     r8d, r14d; Size
0x18009e091  xor     edx, edx; Val
0x18009e093  lea     rcx, [rbp+47h+UrlComponents]; void *
0x18009e097  call    memset_0
0x18009e09c  mov     [rbp+47h+UrlComponents.dwStructSize], r14d
0x18009e0a0  lea     rax, [rsp+120h+var_100]
0x18009e0a5  mov     [rbp+47h+UrlComponents.lpszScheme], rax
0x18009e0a9  lea     ecx, [rbx+1]
0x18009e0ac  mov     [rbp+47h+UrlComponents.dwSchemeLength], ecx
0x18009e0af  lea     rax, [rsp+120h+var_100]
0x18009e0b4  mov     [rbp+47h+UrlComponents.lpszHostName], rax
0x18009e0b8  mov     [rbp+47h+UrlComponents.dwHostNameLength], ecx
0x18009e0bb  lea     rax, [rsp+120h+var_100]
0x18009e0c0  mov     [rbp+47h+UrlComponents.lpszUrlPath], rax
0x18009e0c4  mov     [rbp+47h+UrlComponents.dwUrlPathLength], ecx
0x18009e0c7  lea     r9, [rbp+47h+UrlComponents]; lpUrlComponents
0x18009e0cb  xor     edx, edx; dwUrlLength
0x18009e0cd  mov     r8d, 80000000h; dwFlags
0x18009e0d3  mov     rcx, rdi; pwszUrl
0x18009e0d6  call    cs:__imp_WinHttpCrackUrl
0x18009e0dc  lea     r14d, [rbx+2]
0x18009e0e0  test    eax, eax
0x18009e0e2  jnz     loc_18009E209
0x18009e0e8  call    cs:__imp_GetLastError
0x18009e0ee  mov     ebx, eax
0x18009e0f0  cmp     eax, 7Ah ; 'z'
0x18009e0f3  jz      short loc_18009E13A
0x18009e0f5  test    eax, eax
0x18009e0f7  jg      short loc_18009E0FD
0x18009e0f9  mov     ecx, eax
0x18009e0fb  jmp     short loc_18009E106
0x18009e0fd  movzx   ecx, bx
0x18009e100  or      ecx, 80070000h; int
0x18009e106  test    ecx, ecx
0x18009e108  jns     short loc_18009E11C
0x18009e10a  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x18009e110  lea     rdx, aTm; "tm"
0x18009e117  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009e11c  mov     edx, ebx; unsigned int
0x18009e11e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009e123  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18009e128  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18009e12f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009e134  call    _CxxThrowException_0
0x18009e13a  mov     ecx, [rbp+47h+UrlComponents.dwUrlPathLength]
0x18009e13d  mov     rax, r14
0x18009e140  mul     rcx
0x18009e143  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18009e14a  cmovb   rax, r15
0x18009e14e  mov     rcx, rax; unsigned __int64
0x18009e151  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009e156  mov     rbx, rax
0x18009e159  mov     [rsp+120h+var_F0], rax
0x18009e15e  mov     ecx, [rbp+47h+UrlComponents.dwSchemeLength]
0x18009e161  mov     rax, r14
0x18009e164  mul     rcx
0x18009e167  cmovb   rax, r15
0x18009e16b  mov     rcx, rax; unsigned __int64
0x18009e16e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009e173  mov     rsi, rax
0x18009e176  mov     [rbp+47h+var_50], rax
0x18009e17a  mov     ecx, [rbp+47h+UrlComponents.dwHostNameLength]
0x18009e17d  mov     rax, r14
0x18009e180  mul     rcx
0x18009e183  cmovb   rax, r15
0x18009e187  mov     rcx, rax; unsigned __int64
0x18009e18a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009e18f  mov     r15, rax
0x18009e192  mov     [rsp+120h+var_F8], rax
0x18009e197  mov     [rbp+47h+UrlComponents.lpszScheme], rsi
0x18009e19b  mov     [rbp+47h+UrlComponents.lpszHostName], rax
0x18009e19f  mov     [rbp+47h+UrlComponents.lpszUrlPath], rbx
0x18009e1a3  lea     r9, [rbp+47h+UrlComponents]; lpUrlComponents
0x18009e1a7  xor     edx, edx; dwUrlLength
0x18009e1a9  mov     r8d, 80000000h; dwFlags
0x18009e1af  mov     rcx, rdi; pwszUrl
0x18009e1b2  call    cs:__imp_WinHttpCrackUrl
0x18009e1b8  test    eax, eax
0x18009e1ba  jnz     short loc_18009E209
0x18009e1bc  call    cs:__imp_GetLastError
0x18009e1c2  mov     ebx, eax
0x18009e1c4  test    eax, eax
0x18009e1c6  jg      short loc_18009E1CC
0x18009e1c8  mov     ecx, eax
0x18009e1ca  jmp     short loc_18009E1D5
0x18009e1cc  movzx   ecx, bx
0x18009e1cf  or      ecx, 80070000h; int
0x18009e1d5  test    ecx, ecx
0x18009e1d7  jns     short loc_18009E1EB
0x18009e1d9  mov     r8d, 78h ; 'x'; unsigned __int16
0x18009e1df  lea     rdx, aTm; "tm"
0x18009e1e6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009e1eb  mov     edx, ebx; unsigned int
0x18009e1ed  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009e1f2  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18009e1f7  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18009e1fe  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009e203  call    _CxxThrowException_0
0x18009e209  mov     r14, [rbp+47h+arg_28]
0x18009e20d  test    r14, r14
0x18009e210  jz      loc_18009E321
0x18009e216  xor     edi, edi
0x18009e218  mov     [rbp+47h+var_48], rdi
0x18009e21c  mov     [rsp+120h+pdwUrlLength], edi
0x18009e220  lea     r9, [rsp+120h+pdwUrlLength]; pdwUrlLength
0x18009e225  xor     r8d, r8d; pwszUrl
0x18009e228  xor     edx, edx; dwFlags
0x18009e22a  lea     rcx, [rbp+47h+UrlComponents]; lpUrlComponents
0x18009e22e  call    cs:__imp_WinHttpCreateUrl
0x18009e234  test    eax, eax
0x18009e236  jnz     short loc_18009E2B0
0x18009e238  call    cs:__imp_GetLastError
0x18009e23e  mov     edi, eax
0x18009e240  cmp     eax, 7Ah ; 'z'
0x18009e243  jz      short loc_18009E28A
0x18009e245  test    eax, eax
0x18009e247  jg      short loc_18009E24D
0x18009e249  mov     ecx, eax
0x18009e24b  jmp     short loc_18009E256
0x18009e24d  movzx   ecx, di
0x18009e250  or      ecx, 80070000h; int
0x18009e256  test    ecx, ecx
0x18009e258  jns     short loc_18009E26C
0x18009e25a  mov     r8d, 82h; unsigned __int16
0x18009e260  lea     rdx, aTm; "tm"
0x18009e267  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009e26c  mov     edx, edi; unsigned int
0x18009e26e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009e273  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18009e278  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18009e27f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009e284  call    _CxxThrowException_0
0x18009e28a  mov     ecx, [rsp+120h+pdwUrlLength]
0x18009e28e  mov     eax, 2
0x18009e293  mul     rcx
0x18009e296  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e29d  cmovb   rax, rcx
0x18009e2a1  mov     rcx, rax; unsigned __int64
0x18009e2a4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009e2a9  mov     rdi, rax
0x18009e2ac  mov     [rbp+47h+var_48], rax
0x18009e2b0  lea     r9, [rsp+120h+pdwUrlLength]; pdwUrlLength
0x18009e2b5  mov     r8, rdi; pwszUrl
0x18009e2b8  xor     edx, edx; dwFlags
0x18009e2ba  lea     rcx, [rbp+47h+UrlComponents]; lpUrlComponents
0x18009e2be  call    cs:__imp_WinHttpCreateUrl
0x18009e2c4  test    eax, eax
0x18009e2c6  jnz     short loc_18009E315
0x18009e2c8  call    cs:__imp_GetLastError
0x18009e2ce  mov     ebx, eax
0x18009e2d0  test    eax, eax
0x18009e2d2  jg      short loc_18009E2D8
0x18009e2d4  mov     ecx, eax
0x18009e2d6  jmp     short loc_18009E2E1
0x18009e2d8  movzx   ecx, bx
0x18009e2db  or      ecx, 80070000h; int
0x18009e2e1  test    ecx, ecx
0x18009e2e3  jns     short loc_18009E2F7
0x18009e2e5  mov     r8d, 8Ch; unsigned __int16
0x18009e2eb  lea     rdx, aTm; "tm"
0x18009e2f2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009e2f7  mov     edx, ebx; unsigned int
0x18009e2f9  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009e2fe  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18009e303  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18009e30a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009e30f  call    _CxxThrowException_0
0x18009e315  mov     [r14], rdi
0x18009e318  xor     ecx, ecx; Block
0x18009e31a  call    cs:__imp_free
0x18009e320  nop
0x18009e321  cmp     [rbp+47h+UrlComponents.dwSchemeLength], 0
0x18009e325  jbe     loc_18009E41B
0x18009e32b  mov     rcx, [rbp+47h+UrlComponents.lpszScheme]; String1
0x18009e32f  test    rcx, rcx
0x18009e332  jz      loc_18009E41B
0x18009e338  mov     r8d, 5; MaxCount
0x18009e33e  lea     rdx, aHttps_1; "https"
0x18009e345  call    cs:__imp__wcsnicmp
0x18009e34b  test    eax, eax
0x18009e34d  setz    cl
0x18009e350  mov     rax, [rbp+47h+arg_20]
0x18009e354  mov     [rax], cl
0x18009e356  mov     ecx, [rbp+47h+UrlComponents.dwHostNameLength]
0x18009e359  xor     eax, eax
0x18009e35b  mov     [r15+rcx*2], ax
0x18009e360  mov     eax, [rbp+47h+UrlComponents.dwHostNameLength]
0x18009e363  test    eax, eax
0x18009e365  jz      short loc_18009E396
0x18009e367  mov     rcx, [rbp+47h+UrlComponents.lpszHostName]
0x18009e36b  cmp     word ptr [rcx], 5Bh ; '['
0x18009e36f  jnz     short loc_18009E396
0x18009e371  dec     eax
0x18009e373  mov     edx, eax
0x18009e375  cmp     word ptr [rcx+rax*2], 5Dh ; ']'
0x18009e37a  jnz     short loc_18009E396
0x18009e37c  xor     eax, eax
0x18009e37e  mov     [rcx+rdx*2], ax
0x18009e382  mov     edx, [rbp+47h+UrlComponents.dwHostNameLength]; unsigned __int64
0x18009e385  lea     r9d, [rdx-1]; unsigned __int64
0x18009e389  mov     rcx, [rbp+47h+UrlComponents.lpszHostName]; wchar_t *
0x18009e38d  lea     r8, [rcx+2]; wchar_t *
0x18009e391  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18009e396  mov     [rsp+120h+var_F8], 0
0x18009e39f  mov     rax, [rbp+47h+arg_8]
0x18009e3a3  mov     [rax], r15
0x18009e3a6  movzx   eax, [rbp+47h+UrlComponents.nPort]
0x18009e3aa  mov     [r13+0], ax
0x18009e3af  mov     eax, [rbp+47h+UrlComponents.dwUrlPathLength]
0x18009e3b2  test    eax, eax
0x18009e3b4  jnz     short loc_18009E3D3
0x18009e3b6  lea     ecx, [rax+4]; unsigned __int64
0x18009e3b9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009e3be  mov     dword ptr [rax], 2Fh ; '/'
0x18009e3c4  mov     [r12], rax
0x18009e3c8  xor     ecx, ecx; Block
0x18009e3ca  call    cs:__imp_free
0x18009e3d0  nop
0x18009e3d1  jmp     short loc_18009E3EA
0x18009e3d3  mov     rcx, rax
0x18009e3d6  xor     eax, eax
0x18009e3d8  mov     [rbx+rcx*2], ax
0x18009e3dc  mov     rax, rbx
0x18009e3df  xor     ebx, ebx
0x18009e3e1  mov     [rsp+120h+var_F0], rbx
0x18009e3e6  mov     [r12], rax
0x18009e3ea  xor     ecx, ecx; Block
0x18009e3ec  call    cs:__imp_free
0x18009e3f2  nop
0x18009e3f3  mov     rcx, rsi; Block
0x18009e3f6  call    cs:__imp_free
0x18009e3fc  nop
0x18009e3fd  mov     rcx, rbx; Block
0x18009e400  call    cs:__imp_free
0x18009e406  nop
0x18009e407  add     rsp, 0E8h
0x18009e40e  pop     r15
0x18009e410  pop     r14
0x18009e412  pop     r13
0x18009e414  pop     r12
0x18009e416  pop     rdi
0x18009e417  pop     rsi
0x18009e418  pop     rbx
0x18009e419  pop     rbp
0x18009e41a  retn
0x18009e41b  mov     r8d, 96h; unsigned __int16
0x18009e421  lea     rdx, aTm; "tm"
0x18009e428  mov     ecx, 80072EE5h; int
0x18009e42d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009e432  mov     edx, 2EE5h; unsigned int
0x18009e437  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009e43c  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18009e441  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18009e448  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009e44d  call    _CxxThrowException_0
```
