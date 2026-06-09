# CabUtils::GetFileFromCab(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x1800c1ed4`
- end: `0x1800c21f3`
- name: `?GetFileFromCab@CabUtils@@SAJPEBG00PEAPEAX@Z`
- size: `799`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9514`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x1800254ac`
- `0x1800876cc`
- `0x1800a61b0`
- `0x1800c1ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c1f3f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c1f3f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c2078`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c218f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c2078`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c218f`
- `Cabinet!__imp_FDICreate` at `0x1800c20fa`
- `Cabinet!__imp_FDICreate` at `0x1800c20fa`
- `Cabinet!__imp_FDICopy` at `0x1800c213b`
- `Cabinet!__imp_FDICopy` at `0x1800c213b`
- `Cabinet!__imp_FDIDestroy` at `0x1800c215f`
- `Cabinet!__imp_FDIDestroy` at `0x1800c21a8`
- `Cabinet!__imp_FDIDestroy` at `0x1800c215f`
- `Cabinet!__imp_FDIDestroy` at `0x1800c21a8`

## string_xrefs

- `0x1800c1fda`: `PrivilegedActions.cab`
- `0x1800c1f5e`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c1fae`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c1ff3`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c2031`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c208c`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c214a`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CabUtils::GetFileFromCab(
        LPCWCH lpWideCharStr,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  int v7; // eax
  unsigned int LastError; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rdx
  wchar_t *v12; // rcx
  int DirectoryDeepNoThrow; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  HANDLE FileA; // rbx
  const char *v18; // r9
  __int64 v19; // rdx
  HFDI v20; // rdi
  const char *v21; // r9
  __int64 v22; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  LPSTR pszCabPath; // [rsp+50h] [rbp-19h] BYREF
  LPCSTR lpFileName; // [rsp+58h] [rbp-11h] BYREF
  LPSTR pszCabinet; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *Str[3]; // [rsp+68h] [rbp-1h] BYREF
  ERF perf; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  memset(Str, 0, sizeof(Str));
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(Str, a3, -1);
  LastError = v7;
  if ( v7 >= 0 )
  {
    v12 = wcsrchr(Str[0], 0x5Cu);
    if ( !v12 )
    {
      LastError = -2147024809;
      v9 = 2147942487LL;
      v10 = 404;
      goto LABEL_5;
    }
    *v12 = 0;
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Str[0], v11);
    LastError = DirectoryDeepNoThrow;
    if ( DirectoryDeepNoThrow < 0 )
    {
      v9 = (unsigned int)DirectoryDeepNoThrow;
      v10 = 406;
      goto LABEL_5;
    }
    pszCabPath = 0;
    v14 = FSCommonUtils::ConvertWcharToANSI(lpWideCharStr, &pszCabPath);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
        (const char *)(unsigned int)v14,
        dwCreationDisposition);
LABEL_10:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabPath);
      goto LABEL_28;
    }
    pszCabinet = 0;
    v15 = FSCommonUtils::ConvertWcharToANSI(L"PrivilegedActions.cab", &pszCabinet);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
LABEL_13:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabinet);
      goto LABEL_10;
    }
    lpFileName = 0;
    v16 = FSCommonUtils::ConvertWcharToANSI(a3, (char **)&lpFileName);
    LastError = v16;
    if ( v16 >= 0 )
    {
      FileA = CreateFileA(lpFileName, 0x120116u, 1u, 0, 2u, 0x100u, 0);
      if ( FileA == (HANDLE)-1LL )
      {
        v19 = 426;
      }
      else
      {
        *(_QWORD *)&perf.erfOper = 0;
        perf.fError = 0;
        v20 = FDICreate(fdi_alloc, fdi_free, fdi_open, fdi_read, fdi_write, fdi_close, fdi_seek, -1, &perf);
        if ( v20 != (HFDI)-1LL )
        {
          if ( FDICopy(v20, pszCabinet, pszCabPath, 0, fdi_notify, 0, FileA) )
          {
            *a4 = CreateFileA(lpFileName, 0x120089u, 1u, 0, 3u, 0x100u, 0);
            if ( a4 != (void **)-1LL )
            {
              FDIDestroy(v20);
              CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpFileName);
              CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabinet);
              CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabPath);
              LastError = 0;
              goto LABEL_28;
            }
            v22 = 457;
          }
          else
          {
            v22 = 446;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v22,
                        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
                        v21);
          FDIDestroy(v20);
          goto LABEL_16;
        }
        v19 = 438;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v19,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
                    v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
        (const char *)(unsigned int)v16,
        dwCreationDisposition);
    }
LABEL_16:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpFileName);
    goto LABEL_13;
  }
  v9 = (unsigned int)v7;
  v10 = 402;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
    (const char *)v9,
    dwCreationDisposition);
LABEL_28:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x1800c1ed4  push    rbp
0x1800c1ed6  push    rbx
0x1800c1ed7  push    rsi
0x1800c1ed8  push    rdi
0x1800c1ed9  push    r14
0x1800c1edb  lea     rbp, [rsp-37h]
0x1800c1ee0  sub     rsp, 0A0h
0x1800c1ee7  mov     rax, cs:__security_cookie
0x1800c1eee  xor     rax, rsp
0x1800c1ef1  mov     [rbp+57h+var_30], rax
0x1800c1ef5  mov     r14, r9
0x1800c1ef8  mov     rdi, r8
0x1800c1efb  mov     rsi, rcx
0x1800c1efe  mov     [rbp+57h+Str], 0
0x1800c1f06  mov     [rbp+57h+var_50], 0
0x1800c1f0e  mov     [rbp+57h+var_48], 0
0x1800c1f16  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c1f1a  mov     rdx, rdi
0x1800c1f1d  lea     rcx, [rbp+57h+Str]
0x1800c1f21  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800c1f26  mov     ebx, eax
0x1800c1f28  test    eax, eax
0x1800c1f2a  jns     short loc_1800C1F36
0x1800c1f2c  mov     r9d, eax
0x1800c1f2f  mov     edx, 192h
0x1800c1f34  jmp     short loc_1800C1F5A
0x1800c1f36  mov     edx, 5Ch ; '\'; Ch
0x1800c1f3b  mov     rcx, [rbp+57h+Str]; Str
0x1800c1f3f  call    cs:__imp_wcsrchr
0x1800c1f45  mov     rcx, rax
0x1800c1f48  test    rax, rax
0x1800c1f4b  jnz     short loc_1800C1F6F
0x1800c1f4d  mov     ebx, 80070057h
0x1800c1f52  mov     r9d, ebx; char *
0x1800c1f55  mov     edx, 194h; void *
0x1800c1f5a  mov     rcx, [rbp+5Fh]; this
0x1800c1f5e  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c1f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1f6a  jmp     loc_1800C21CE
0x1800c1f6f  xor     eax, eax
0x1800c1f71  mov     [rcx], ax
0x1800c1f74  mov     rcx, [rbp+57h+Str]; this
0x1800c1f78  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800c1f7d  mov     ebx, eax
0x1800c1f7f  test    eax, eax
0x1800c1f81  jns     short loc_1800C1F8D
0x1800c1f83  mov     r9d, eax
0x1800c1f86  mov     edx, 196h
0x1800c1f8b  jmp     short loc_1800C1F5A
0x1800c1f8d  mov     [rbp+57h+pszCabPath], 0
0x1800c1f95  lea     rdx, [rbp+57h+pszCabPath]; char **
0x1800c1f99  mov     rcx, rsi; lpWideCharStr
0x1800c1f9c  call    ?ConvertWcharToANSI@FSCommonUtils@@SAJPEBGPEAPEAD@Z; FSCommonUtils::ConvertWcharToANSI(ushort const *,char * *)
0x1800c1fa1  mov     ebx, eax
0x1800c1fa3  test    eax, eax
0x1800c1fa5  jns     short loc_1800C1FCE
0x1800c1fa7  mov     rcx, [rbp+5Fh]; this
0x1800c1fab  mov     r9d, eax; char *
0x1800c1fae  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c1fb5  mov     edx, 19Bh; void *
0x1800c1fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1fbf  nop
0x1800c1fc0  lea     rcx, [rbp+57h+pszCabPath]
0x1800c1fc4  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c1fc9  jmp     loc_1800C21CE
0x1800c1fce  mov     [rbp+57h+pszCabinet], 0
0x1800c1fd6  lea     rdx, [rbp+57h+pszCabinet]; char **
0x1800c1fda  lea     rcx, WideCharStr; "PrivilegedActions.cab"
0x1800c1fe1  call    ?ConvertWcharToANSI@FSCommonUtils@@SAJPEBGPEAPEAD@Z; FSCommonUtils::ConvertWcharToANSI(ushort const *,char * *)
0x1800c1fe6  mov     ebx, eax
0x1800c1fe8  test    eax, eax
0x1800c1fea  jns     short loc_1800C2010
0x1800c1fec  mov     rcx, [rbp+5Fh]; this
0x1800c1ff0  mov     r9d, eax; char *
0x1800c1ff3  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c1ffa  mov     edx, 19Dh; void *
0x1800c1fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2004  nop
0x1800c2005  lea     rcx, [rbp+57h+pszCabinet]
0x1800c2009  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c200e  jmp     short loc_1800C1FC0
0x1800c2010  mov     [rbp+57h+lpFileName], 0
0x1800c2018  lea     rdx, [rbp+57h+lpFileName]; char **
0x1800c201c  mov     rcx, rdi; lpWideCharStr
0x1800c201f  call    ?ConvertWcharToANSI@FSCommonUtils@@SAJPEBGPEAPEAD@Z; FSCommonUtils::ConvertWcharToANSI(ushort const *,char * *)
0x1800c2024  mov     ebx, eax
0x1800c2026  test    eax, eax
0x1800c2028  jns     short loc_1800C204E
0x1800c202a  mov     rcx, [rbp+5Fh]; this
0x1800c202e  mov     r9d, eax; char *
0x1800c2031  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2038  mov     edx, 19Fh; void *
0x1800c203d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2042  nop
0x1800c2043  lea     rcx, [rbp+57h+lpFileName]
0x1800c2047  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c204c  jmp     short loc_1800C2005
0x1800c204e  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800c2057  mov     esi, 100h
0x1800c205c  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1800c2060  mov     [rsp+0C0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c2068  xor     r9d, r9d; lpSecurityAttributes
0x1800c206b  mov     edx, 120116h; dwDesiredAccess
0x1800c2070  lea     r8d, [r9+1]; dwShareMode
0x1800c2074  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800c2078  call    cs:__imp_CreateFileA
0x1800c207e  mov     rbx, rax
0x1800c2081  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c2085  jnz     short loc_1800C20A0
0x1800c2087  mov     edx, 1AAh; void *
0x1800c208c  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2093  mov     rcx, [rbp+5Fh]; this
0x1800c2097  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c209c  mov     ebx, eax
0x1800c209e  jmp     short loc_1800C2043
0x1800c20a0  xor     eax, eax
0x1800c20a2  mov     qword ptr [rbp+57h+var_40.erfOper], rax
0x1800c20a6  mov     [rbp+57h+var_40.fError], eax
0x1800c20a9  lea     rax, [rbp+57h+var_40]
0x1800c20ad  mov     [rsp+0C0h+perf], rax; perf
0x1800c20b2  mov     [rsp+0C0h+cpuType], 0FFFFFFFFh; cpuType
0x1800c20ba  lea     rax, ?fdi_seek@@YAJ_JJH@Z; fdi_seek(__int64,long,int)
0x1800c20c1  mov     [rsp+0C0h+hTemplateFile], rax; pfnseek
0x1800c20c6  lea     rax, ?fdi_close@@YAH_J@Z; fdi_close(__int64)
0x1800c20cd  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; pfnclose
0x1800c20d2  lea     rax, ?fdi_write@@YAI_JPEAXI@Z; fdi_write(__int64,void *,uint)
0x1800c20d9  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; pfnwrite
0x1800c20de  lea     r9, ?fdi_read@@YAI_JPEAXI@Z; pfnread
0x1800c20e5  lea     r8, ?fdi_open@@YA_JPEADHH@Z; pfnopen
0x1800c20ec  lea     rdx, ?fdi_free@@YAXPEAX@Z; pfnfree
0x1800c20f3  lea     rcx, ?fdi_alloc@@YAPEAXK@Z; pfnalloc
0x1800c20fa  call    cs:__imp_FDICreate
0x1800c2100  mov     rdi, rax
0x1800c2103  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c2107  jnz     short loc_1800C2113
0x1800c2109  mov     edx, 1B6h
0x1800c210e  jmp     loc_1800C208C
0x1800c2113  mov     [rsp+0C0h+hTemplateFile], rbx; pvUser
0x1800c2118  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 0; pfnfdid
0x1800c2121  lea     rax, ?fdi_notify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; fdi_notify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1800c2128  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; pfnfdin
0x1800c212d  xor     r9d, r9d; flags
0x1800c2130  mov     r8, [rbp+57h+pszCabPath]; pszCabPath
0x1800c2134  mov     rdx, [rbp+57h+pszCabinet]; pszCabinet
0x1800c2138  mov     rcx, rdi; hfdi
0x1800c213b  call    cs:__imp_FDICopy
0x1800c2141  test    eax, eax
0x1800c2143  jnz     short loc_1800C216A
0x1800c2145  mov     edx, 1BEh; void *
0x1800c214a  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2151  mov     rcx, [rbp+5Fh]; this
0x1800c2155  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c215a  mov     ebx, eax
0x1800c215c  mov     rcx, rdi; hfdi
0x1800c215f  call    cs:__imp_FDIDestroy
0x1800c2165  jmp     loc_1800C2043
0x1800c216a  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800c2173  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1800c2177  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c217f  xor     r9d, r9d; lpSecurityAttributes
0x1800c2182  mov     edx, 120089h; dwDesiredAccess
0x1800c2187  lea     r8d, [r9+1]; dwShareMode
0x1800c218b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800c218f  call    cs:__imp_CreateFileA
0x1800c2195  mov     [r14], rax
0x1800c2198  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800c219c  jnz     short loc_1800C21A5
0x1800c219e  mov     edx, 1C9h
0x1800c21a3  jmp     short loc_1800C214A
0x1800c21a5  mov     rcx, rdi; hfdi
0x1800c21a8  call    cs:__imp_FDIDestroy
0x1800c21ae  nop
0x1800c21af  lea     rcx, [rbp+57h+lpFileName]
0x1800c21b3  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c21b8  nop
0x1800c21b9  lea     rcx, [rbp+57h+pszCabinet]
0x1800c21bd  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c21c2  nop
0x1800c21c3  lea     rcx, [rbp+57h+pszCabPath]
0x1800c21c7  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c21cc  xor     ebx, ebx
0x1800c21ce  lea     rcx, [rbp+57h+Str]
0x1800c21d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c21d7  mov     eax, ebx
0x1800c21d9  mov     rcx, [rbp+57h+var_30]
0x1800c21dd  xor     rcx, rsp; StackCookie
0x1800c21e0  call    __security_check_cookie
0x1800c21e5  add     rsp, 0A0h
0x1800c21ec  pop     r14
0x1800c21ee  pop     rdi
0x1800c21ef  pop     rsi
0x1800c21f0  pop     rbx
0x1800c21f1  pop     rbp
0x1800c21f2  retn
```
