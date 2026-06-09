# CEcsWebRequest::ResolveSyncUri(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool *)

- ea: `0x18007da44`
- end: `0x18007e05f`
- name: `?ResolveSyncUri@CEcsWebRequest@@CAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z`
- size: `1563`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18007a7e8`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x180015150`
- `0x1800151c0`
- `0x18001db58`
- `0x18001db74`
- `0x18001db80`
- `0x180028490`
- `0x180028830`
- `0x180028984`
- `0x1800603a0`
- `0x1800612fc`
- `0x180063c08`
- `0x180063c48`
- `0x180067658`
- `0x18006770c`
- `0x18007812c`
- `0x18007da44`
- `0x18007e4c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007dd63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007dd63`
- `KERNEL32!GetLastError` at `0x18007dbff`
- `KERNEL32!GetLastError` at `0x18007de7f`
- `KERNEL32!GetLastError` at `0x18007dbff`
- `KERNEL32!GetLastError` at `0x18007de7f`
- `WINHTTP!WinHttpCreateUrl` at `0x18007de71`
- `WINHTTP!WinHttpCreateUrl` at `0x18007df1f`
- `WINHTTP!WinHttpCreateUrl` at `0x18007de71`
- `WINHTTP!WinHttpCreateUrl` at `0x18007df1f`
- `WINHTTP!WinHttpCrackUrl` at `0x18007dbf5`
- `WINHTTP!WinHttpCrackUrl` at `0x18007dbf5`

## string_xrefs

- `0x18007dae0`: `CEcsWebRequest::ResolveSyncUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CEcsWebRequest::ResolveSyncUri(_WORD *a1, __int64 a2, char *a3)
{
  _BYTE *v6; // rax
  unsigned __int64 v7; // rdi
  char v8; // cl
  const WCHAR *v9; // rax
  __int64 v10; // r8
  signed int LastError; // eax
  char v12; // si
  char v13; // r14
  wchar_t **v14; // r8
  __int64 i; // rbx
  __int64 v16; // r12
  __int64 v17; // rax
  int v18; // eax
  DWORD v19; // edx
  WCHAR *v20; // r8
  signed int v21; // eax
  int v22; // eax
  WCHAR *v23; // r8
  LPWSTR v24; // rdx
  __int64 pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  int LastFailureAsHRESULT; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+2Ch] [rbp-D4h]
  char v28; // [rsp+30h] [rbp-D0h]
  const char *v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  DWORD pdwUrlLength; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v32[32]; // [rsp+50h] [rbp-B0h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[16]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v35; // [rsp+F0h] [rbp-10h]
  _BYTE v36[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+120h] [rbp+20h] BYREF
  LPWSTR pwszUrl; // [rsp+128h] [rbp+28h]
  _BYTE v40[512]; // [rsp+130h] [rbp+30h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 85, &WPP_a38f3d36aa553766ad33a752e2b88333_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  if ( (v6[68] & 8) == 0 || (v8 = 1, v6[65] < 6u) )
    v8 = 0;
  LastFailureAsHRESULT = 0;
  v27 = 2004;
  v28 = v8;
  v29 = "CEcsWebRequest::ResolveSyncUri";
  v30 = 0;
  std::wstring::_Eos(a2, 0);
  if ( a3 )
    *a3 = 0;
  std::wstring::wstring((__int64)v34);
  std::vector<std::wstring>::vector<std::wstring>(v32);
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  pdwUrlLength = 0;
  v38 = 256;
  pwszUrl = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( !a1 || !*a1 )
  {
    LastFailureAsHRESULT = -2134372351;
    HIWORD(v27) = 2034;
    LODWORD(pExceptionObject) = -2134372351;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v27) = 2034;
  std::wstring::wstring((__int64)v36, (__int64)a1);
  CEcsStringUtil::StringTrim(v36);
  if ( !v37 )
  {
    LastFailureAsHRESULT = -2134372351;
    HIWORD(v27) = 2042;
    LODWORD(pExceptionObject) = -2134372351;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v27) = 2042;
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwExtraInfoLength = 1;
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
  if ( !WinHttpCrackUrl(v9, 0, 0x4000u, &UrlComponents) )
  {
    LastError = GetLastError();
    if ( (unsigned int)(LastError - 12005) > 1 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastFailureAsHRESULT = LastError;
      HIWORD(v27) = 2058;
      LODWORD(pExceptionObject) = LastError;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = -2134372351;
    HIWORD(v27) = 2055;
    LODWORD(pExceptionObject) = -2134372351;
    throw (long *)&pExceptionObject;
  }
  if ( UrlComponents.dwExtraInfoLength )
  {
    LastFailureAsHRESULT = -2134372351;
    HIWORD(v27) = 2061;
    LODWORD(pExceptionObject) = -2134372351;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v27) = 2061;
  LastFailureAsHRESULT = 0;
  if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER && !CEcsWebRequest::AllowUnsecureClientConnection() )
  {
    LastFailureAsHRESULT = -2134372350;
    HIWORD(v27) = 2065;
    LODWORD(pExceptionObject) = -2134372350;
    throw (long *)&pExceptionObject;
  }
  v12 = 0;
  LastFailureAsHRESULT = 0;
  LOWORD(v27) = 2065;
  if ( UrlComponents.dwUrlPathLength > 1 )
  {
    v13 = 0;
    CEcsStringUtil::DelimitedStringToVector<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
      UrlComponents.lpszUrlPath + 2,
      &UrlComponents.lpszUrlPath[2 * UrlComponents.dwUrlPathLength],
      v10,
      v32);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::end(
      v32,
      &pExceptionObject);
    v14 = &off_180147500;
    for ( i = pExceptionObject;
          i != *(_QWORD *)std::vector<PrepareBatchResponseEntry>::end(v32, &pExceptionObject, v14);
          i += 32 )
    {
      if ( *(_QWORD *)(i + 16) )
      {
        while ( v7 < 6 )
        {
          v16 = 2 * v7;
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
          v18 = _o__wcsicmp(v17);
          v14 = &off_180147500;
          if ( !v18 )
          {
            v13 = 1;
            v7 = 0;
            if ( v12 || (v12 = 0, *((_BYTE *)&off_180147500 + 8 * v16 + 8)) )
              v12 = 1;
            LastFailureAsHRESULT = 0;
            LOWORD(v27) = 2102;
            goto LABEL_37;
          }
          ++v7;
        }
        v7 = 0;
        if ( v13 )
        {
          LastFailureAsHRESULT = -2134372351;
          HIWORD(v27) = 2102;
          LODWORD(pExceptionObject) = -2134372351;
          throw (long *)&pExceptionObject;
        }
        std::wstring::push_back(v34, 47);
        std::wstring::append(v34, i);
        v14 = &off_180147500;
      }
LABEL_37:
      ;
    }
  }
  std::wstring::append(v34, L"/sync/");
  if ( v35 > 0x7FFF )
  {
    LastFailureAsHRESULT = -2134372351;
    HIWORD(v27) = 2123;
    LODWORD(pExceptionObject) = -2134372351;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v27) = 2123;
  UrlComponents.lpszUrlPath = (LPSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
  UrlComponents.dwUrlPathLength = v19;
  pdwUrlLength = v38;
  v20 = (WCHAR *)v40;
  if ( pwszUrl )
    v20 = pwszUrl;
  if ( !WinHttpCreateUrl(&UrlComponents, 0, v20, &pdwUrlLength) )
  {
    v21 = GetLastError();
    if ( v21 != 122 )
    {
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      LastFailureAsHRESULT = v21;
      HIWORD(v27) = 2137;
      LODWORD(pExceptionObject) = v21;
      throw (long *)&pExceptionObject;
    }
    v22 = CEcsPreallocArray<unsigned short,256>::Alloc(&v38, pdwUrlLength);
    LastFailureAsHRESULT = v22;
    if ( v22 < 0 )
    {
      HIWORD(v27) = 2142;
      LODWORD(pExceptionObject) = v22;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v27) = 2142;
    LastFailureAsHRESULT = v22;
    v23 = (WCHAR *)v40;
    if ( pwszUrl )
      v23 = pwszUrl;
    if ( !WinHttpCreateUrl(&UrlComponents, 0, v23, &pdwUrlLength) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v27) = 2144;
      LODWORD(pExceptionObject) = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v27) = 2144;
  }
  v24 = (LPWSTR)v40;
  if ( pwszUrl )
    v24 = pwszUrl;
  std::wstring::assign(v34, v24, pdwUrlLength);
  std::wstring::swap(a2, v34);
  if ( a3 )
    *a3 = v12;
  std::wstring::~wstring((__int64)v36);
  CEcsPreallocArray<unsigned short,256>::Clear(&v38);
  std::vector<std::wstring>::_Tidy(v32);
  std::wstring::~wstring((__int64)v34);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x18007da44  mov     [rsp-8+arg_18], rbx
0x18007da49  push    rbp
0x18007da4a  push    rsi
0x18007da4b  push    rdi
0x18007da4c  push    r12
0x18007da4e  push    r13
0x18007da50  push    r14
0x18007da52  push    r15
0x18007da54  lea     rbp, [rsp-240h]
0x18007da5c  sub     rsp, 340h
0x18007da63  mov     rax, cs:__security_cookie
0x18007da6a  xor     rax, rsp
0x18007da6d  mov     [rbp+270h+var_40], rax
0x18007da74  mov     r15, r8
0x18007da77  mov     r13, rdx
0x18007da7a  mov     rbx, rcx
0x18007da7d  lea     rcx, WPP_GLOBAL_Control
0x18007da84  mov     rax, cs:WPP_GLOBAL_Control
0x18007da8b  cmp     rax, rcx
0x18007da8e  jz      short loc_18007DAB8
0x18007da90  test    byte ptr [rax+44h], 8
0x18007da94  jz      short loc_18007DAB8
0x18007da96  cmp     byte ptr [rax+41h], 6
0x18007da9a  jb      short loc_18007DAB8
0x18007da9c  mov     edx, 55h ; 'U'
0x18007daa1  lea     r8, WPP_a38f3d36aa553766ad33a752e2b88333_Traceguids
0x18007daa8  mov     rcx, [rax+38h]
0x18007daac  call    WPP_SF_
0x18007dab1  mov     rax, cs:WPP_GLOBAL_Control
0x18007dab8  xor     edi, edi
0x18007daba  lea     r14d, [rdi+1]
0x18007dabe  test    byte ptr [rax+44h], 8
0x18007dac2  jz      short loc_18007DACD
0x18007dac4  cmp     byte ptr [rax+41h], 6
0x18007dac8  mov     cl, r14b
0x18007dacb  jnb     short loc_18007DAD0
0x18007dacd  mov     cl, dil
0x18007dad0  mov     [rsp+370h+var_348], edi
0x18007dad4  mov     [rsp+370h+var_344], 7D4h
0x18007dadc  mov     [rsp+370h+var_340], cl
0x18007dae0  lea     rax, aCecswebrequest_20; "CEcsWebRequest::ResolveSyncUri"
0x18007dae7  mov     [rsp+370h+var_338], rax
0x18007daec  mov     [rsp+370h+var_330], rdi
0x18007daf1  xor     edx, edx
0x18007daf3  mov     rcx, r13
0x18007daf6  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18007dafb  test    r15, r15
0x18007dafe  jz      short loc_18007DB03
0x18007db00  mov     [r15], dil
0x18007db03  lea     rcx, [rbp+270h+var_290]
0x18007db07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007db0c  nop
0x18007db0d  lea     rcx, [rsp+370h+var_320]
0x18007db12  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18007db17  nop
0x18007db18  mov     esi, 68h ; 'h'
0x18007db1d  mov     r8d, esi; Size
0x18007db20  xor     edx, edx; Val
0x18007db22  lea     rcx, [rsp+370h+UrlComponents]; void *
0x18007db27  call    memset_0
0x18007db2c  mov     [rsp+370h+pdwUrlLength], edi
0x18007db30  mov     [rbp+270h+var_250], 100h
0x18007db38  mov     [rbp+270h+pwszUrl], rdi
0x18007db3c  xor     edx, edx; Val
0x18007db3e  mov     r8d, 200h; Size
0x18007db44  lea     rcx, [rbp+270h+var_240]; void *
0x18007db48  call    memset_0
0x18007db4d  nop
0x18007db4e  mov     eax, [rsp+370h+var_348]
0x18007db52  mov     [rsp+370h+var_348], eax
0x18007db56  test    rbx, rbx
0x18007db59  jz      loc_18007E036
0x18007db5f  cmp     [rbx], di
0x18007db62  jz      loc_18007E036
0x18007db68  mov     [rsp+370h+var_348], edi
0x18007db6c  mov     ecx, 7F2h
0x18007db71  mov     word ptr [rsp+370h+var_344], cx
0x18007db76  mov     rdx, rbx
0x18007db79  lea     rcx, [rbp+270h+var_270]
0x18007db7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007db82  nop
0x18007db83  lea     rcx, [rbp+270h+var_270]
0x18007db87  call    ?StringTrim@CEcsStringUtil@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CEcsStringUtil::StringTrim(std::wstring &)
0x18007db8c  mov     eax, [rsp+370h+var_348]
0x18007db90  mov     [rsp+370h+var_348], eax
0x18007db94  mov     ecx, 7FAh
0x18007db99  cmp     [rbp+270h+var_260], rdi
0x18007db9d  jnz     short loc_18007DBC3
0x18007db9f  mov     eax, 80C81001h
0x18007dba4  mov     [rsp+370h+var_348], eax
0x18007dba8  mov     word ptr [rsp+370h+var_344+2], cx
0x18007dbad  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007dbb1  lea     rdx, _TI1J; pThrowInfo
0x18007dbb8  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007dbbd  call    _CxxThrowException_0
0x18007dbc3  mov     [rsp+370h+var_348], edi
0x18007dbc7  mov     word ptr [rsp+370h+var_344], cx
0x18007dbcc  mov     [rsp+370h+UrlComponents.dwStructSize], esi
0x18007dbd0  mov     [rbp+270h+UrlComponents.dwHostNameLength], r14d
0x18007dbd4  mov     [rbp+270h+UrlComponents.dwUrlPathLength], r14d
0x18007dbd8  mov     [rbp+270h+UrlComponents.dwExtraInfoLength], r14d
0x18007dbdc  lea     rcx, [rbp+270h+var_270]
0x18007dbe0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dbe5  mov     rcx, rax; pwszUrl
0x18007dbe8  lea     r9, [rsp+370h+UrlComponents]; lpUrlComponents
0x18007dbed  xor     edx, edx; dwUrlLength
0x18007dbef  mov     r8d, 4000h; dwFlags
0x18007dbf5  call    cs:__imp_WinHttpCrackUrl
0x18007dbfb  test    eax, eax
0x18007dbfd  jnz     short loc_18007DC79
0x18007dbff  call    cs:__imp_GetLastError
0x18007dc05  lea     ecx, [rax-2EE5h]
0x18007dc0b  cmp     ecx, r14d
0x18007dc0e  jbe     short loc_18007DC48
0x18007dc10  mov     ecx, [rsp+370h+var_348]
0x18007dc14  mov     [rsp+370h+var_348], ecx
0x18007dc18  test    eax, eax
0x18007dc1a  jle     short loc_18007DC24
0x18007dc1c  movzx   eax, ax
0x18007dc1f  or      eax, 80070000h
0x18007dc24  mov     [rsp+370h+var_348], eax
0x18007dc28  mov     ecx, 80Ah
0x18007dc2d  mov     word ptr [rsp+370h+var_344+2], cx
0x18007dc32  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007dc36  lea     rdx, _TI1J; pThrowInfo
0x18007dc3d  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007dc42  call    _CxxThrowException_0
0x18007dc48  mov     eax, [rsp+370h+var_348]
0x18007dc4c  mov     [rsp+370h+var_348], eax
0x18007dc50  mov     eax, 80C81001h
0x18007dc55  mov     [rsp+370h+var_348], eax
0x18007dc59  mov     ecx, 807h
0x18007dc5e  mov     word ptr [rsp+370h+var_344+2], cx
0x18007dc63  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007dc67  lea     rdx, _TI1J; pThrowInfo
0x18007dc6e  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007dc73  call    _CxxThrowException_0
0x18007dc79  mov     eax, [rsp+370h+var_348]
0x18007dc7d  mov     [rsp+370h+var_348], eax
0x18007dc81  mov     ecx, 80Dh
0x18007dc86  cmp     [rbp+270h+UrlComponents.dwExtraInfoLength], edi
0x18007dc89  jnz     loc_18007E012
0x18007dc8f  mov     [rsp+370h+var_348], edi
0x18007dc93  mov     word ptr [rsp+370h+var_344], cx
0x18007dc98  mov     [rsp+370h+var_348], edi
0x18007dc9c  cmp     [rbp+270h+UrlComponents.nScheme], 2
0x18007dca0  jz      short loc_18007DCD4
0x18007dca2  call    ?AllowUnsecureClientConnection@CEcsWebRequest@@CA_NXZ; CEcsWebRequest::AllowUnsecureClientConnection(void)
0x18007dca7  test    al, al
0x18007dca9  jnz     short loc_18007DCD4
0x18007dcab  mov     ecx, 80C81002h
0x18007dcb0  mov     [rsp+370h+var_348], ecx
0x18007dcb4  mov     eax, 811h
0x18007dcb9  mov     word ptr [rsp+370h+var_344+2], ax
0x18007dcbe  mov     dword ptr [rsp+370h+pExceptionObject], ecx
0x18007dcc2  lea     rdx, _TI1J; pThrowInfo
0x18007dcc9  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007dcce  call    _CxxThrowException_0
0x18007dcd4  mov     sil, dil
0x18007dcd7  mov     [rsp+370h+var_348], edi
0x18007dcdb  mov     eax, 811h
0x18007dce0  mov     word ptr [rsp+370h+var_344], ax
0x18007dce5  cmp     [rbp+270h+UrlComponents.dwUrlPathLength], r14d
0x18007dce9  jbe     loc_18007DE08
0x18007dcef  mov     r14b, dil
0x18007dcf2  mov     eax, [rbp+270h+UrlComponents.dwUrlPathLength]
0x18007dcf5  mov     rcx, [rbp+270h+UrlComponents.lpszUrlPath]
0x18007dcf9  lea     rdx, [rcx+rax*2]
0x18007dcfd  add     rcx, 2
0x18007dd01  lea     r9, [rsp+370h+var_320]
0x18007dd06  call    ??$DelimitedStringToVector@GU?$char_traits@G@std@@V?$allocator@G@2@@CEcsStringUtil@@SAXPEBG0GAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CEcsStringUtil::DelimitedStringToVector<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *,ushort const *,ushort,std::vector<std::wstring> &)
0x18007dd0b  lea     rdx, [rsp+370h+pExceptionObject]
0x18007dd10  lea     rcx, [rsp+370h+var_320]
0x18007dd15  call    ?end@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::end(void)
0x18007dd1a  lea     r8, off_180147500; "sync"
0x18007dd21  mov     rbx, [rsp+370h+pExceptionObject]
0x18007dd26  lea     rdx, [rsp+370h+pExceptionObject]
0x18007dd2b  lea     rcx, [rsp+370h+var_320]
0x18007dd30  call    ?end@?$vector@UPrepareBatchResponseEntry@@V?$allocator@UPrepareBatchResponseEntry@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPrepareBatchResponseEntry@@@std@@@std@@@2@XZ; std::vector<PrepareBatchResponseEntry>::end(void)
0x18007dd35  cmp     rbx, [rax]
0x18007dd38  jz      loc_18007DE08
0x18007dd3e  cmp     [rbx+10h], rdi
0x18007dd42  jz      loc_18007DDCE
0x18007dd48  cmp     rdi, 6
0x18007dd4c  jnb     short loc_18007DDA8
0x18007dd4e  mov     r12, rdi
0x18007dd51  add     r12, r12
0x18007dd54  mov     rcx, rbx
0x18007dd57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dd5c  mov     rdx, [r8+r12*8]
0x18007dd60  mov     rcx, rax
0x18007dd63  call    cs:__imp__o__wcsicmp
0x18007dd69  lea     r8, off_180147500; "sync"
0x18007dd70  test    eax, eax
0x18007dd72  jz      short loc_18007DD79
0x18007dd74  inc     rdi
0x18007dd77  jmp     short loc_18007DD48
0x18007dd79  mov     r14b, 1
0x18007dd7c  xor     edi, edi
0x18007dd7e  test    sil, sil
0x18007dd81  jnz     short loc_18007DD8D
0x18007dd83  cmp     [r8+r12*8+8], dil
0x18007dd88  mov     sil, dil
0x18007dd8b  jz      short loc_18007DD90
0x18007dd8d  mov     sil, r14b
0x18007dd90  mov     eax, [rsp+370h+var_348]
0x18007dd94  mov     [rsp+370h+var_348], eax
0x18007dd98  mov     [rsp+370h+var_348], edi
0x18007dd9c  mov     eax, 836h
0x18007dda1  mov     word ptr [rsp+370h+var_344], ax
0x18007dda6  jmp     short loc_18007DDCE
0x18007dda8  xor     edi, edi
0x18007ddaa  test    r14b, r14b
0x18007ddad  jnz     short loc_18007DDD7
0x18007ddaf  lea     edx, [rdi+2Fh]
0x18007ddb2  lea     rcx, [rbp+270h+var_290]
0x18007ddb6  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18007ddbb  mov     rdx, rbx
0x18007ddbe  lea     rcx, [rbp+270h+var_290]
0x18007ddc2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18007ddc7  lea     r8, off_180147500; "sync"
0x18007ddce  add     rbx, 20h ; ' '
0x18007ddd2  jmp     loc_18007DD26
0x18007ddd7  mov     eax, [rsp+370h+var_348]
0x18007dddb  mov     [rsp+370h+var_348], eax
0x18007dddf  mov     eax, 80C81001h
0x18007dde4  mov     [rsp+370h+var_348], eax
0x18007dde8  mov     ecx, 836h
0x18007dded  mov     word ptr [rsp+370h+var_344+2], cx
0x18007ddf2  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007ddf6  lea     rdx, _TI1J; pThrowInfo
0x18007ddfd  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007de02  call    _CxxThrowException_0
0x18007de08  lea     rdx, aSync; "/sync/"
0x18007de0f  lea     rcx, [rbp+270h+var_290]
0x18007de13  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007de18  mov     eax, [rsp+370h+var_348]
0x18007de1c  mov     [rsp+370h+var_348], eax
0x18007de20  mov     rdx, [rbp+270h+var_280]
0x18007de24  mov     ecx, 84Bh
0x18007de29  cmp     rdx, 7FFFh
0x18007de30  ja      loc_18007DFEE
0x18007de36  mov     [rsp+370h+var_348], edi
0x18007de3a  mov     word ptr [rsp+370h+var_344], cx
0x18007de3f  lea     rcx, [rbp+270h+var_290]
0x18007de43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007de48  mov     [rbp+270h+UrlComponents.lpszUrlPath], rax
0x18007de4c  mov     [rbp+270h+UrlComponents.dwUrlPathLength], edx
0x18007de4f  mov     eax, dword ptr [rbp+270h+var_250]
0x18007de52  mov     [rsp+370h+pdwUrlLength], eax
0x18007de56  lea     r8, [rbp+270h+var_240]
0x18007de5a  mov     rax, [rbp+270h+pwszUrl]
0x18007de5e  test    rax, rax
0x18007de61  cmovnz  r8, rax; pwszUrl
0x18007de65  lea     r9, [rsp+370h+pdwUrlLength]; pdwUrlLength
0x18007de6a  xor     edx, edx; dwFlags
0x18007de6c  lea     rcx, [rsp+370h+UrlComponents]; lpUrlComponents
0x18007de71  call    cs:__imp_WinHttpCreateUrl
0x18007de77  test    eax, eax
0x18007de79  jnz     loc_18007DF60
0x18007de7f  call    cs:__imp_GetLastError
0x18007de85  cmp     eax, 7Ah ; 'z'
0x18007de88  jz      short loc_18007DEC2
0x18007de8a  mov     ecx, [rsp+370h+var_348]
0x18007de8e  mov     [rsp+370h+var_348], ecx
0x18007de92  test    eax, eax
0x18007de94  jle     short loc_18007DE9E
0x18007de96  movzx   eax, ax
0x18007de99  or      eax, 80070000h
0x18007de9e  mov     [rsp+370h+var_348], eax
0x18007dea2  mov     ecx, 859h
0x18007dea7  mov     word ptr [rsp+370h+var_344+2], cx
0x18007deac  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007deb0  lea     rdx, _TI1J; pThrowInfo
0x18007deb7  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007debc  call    _CxxThrowException_0
0x18007dec2  mov     edx, [rsp+370h+pdwUrlLength]
0x18007dec6  lea     rcx, [rbp+270h+var_250]
0x18007deca  call    ?Alloc@?$CEcsPreallocArray@G$0BAA@@@QEAAJ_K@Z; CEcsPreallocArray<ushort,256>::Alloc(unsigned __int64)
0x18007decf  mov     [rsp+370h+var_348], eax
0x18007ded3  mov     [rsp+370h+var_348], eax
0x18007ded7  mov     ecx, 85Eh
0x18007dedc  test    eax, eax
0x18007dede  jns     short loc_18007DEFB
0x18007dee0  mov     word ptr [rsp+370h+var_344+2], cx
0x18007dee5  mov     dword ptr [rsp+370h+pExceptionObject], eax
0x18007dee9  lea     rdx, _TI1J; pThrowInfo
0x18007def0  lea     rcx, [rsp+370h+pExceptionObject]; pExceptionObject
0x18007def5  call    _CxxThrowException_0
0x18007defb  mov     word ptr [rsp+370h+var_344], cx
0x18007df00  mov     [rsp+370h+var_348], eax
0x18007df04  lea     r8, [rbp+270h+var_240]
0x18007df08  mov     rax, [rbp+270h+pwszUrl]
0x18007df0c  test    rax, rax
0x18007df0f  cmovnz  r8, rax; pwszUrl
0x18007df13  lea     r9, [rsp+370h+pdwUrlLength]; pdwUrlLength
0x18007df18  xor     edx, edx; dwFlags
0x18007df1a  lea     rcx, [rsp+370h+UrlComponents]; lpUrlComponents
0x18007df1f  call    cs:__imp_WinHttpCreateUrl
0x18007df25  test    eax, eax
  ... truncated ...
```
