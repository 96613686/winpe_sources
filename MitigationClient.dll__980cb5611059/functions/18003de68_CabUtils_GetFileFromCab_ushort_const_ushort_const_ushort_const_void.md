# CabUtils::GetFileFromCab(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18003de68`
- end: `0x18003e187`
- name: `?GetFileFromCab@CabUtils@@SAJPEBG00PEAPEAX@Z`
- size: `799`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x18003cab8`

## callees

- `0x18000a6e0`
- `0x18001206c`
- `0x18001208c`
- `0x18002407c`
- `0x1800240b8`
- `0x1800271bc`
- `0x18003c1d8`
- `0x18003db9c`
- `0x18003de68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003ded3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003ded3`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e00c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e123`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e00c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e123`
- `Cabinet!__imp_FDICreate` at `0x18003e08e`
- `Cabinet!__imp_FDICreate` at `0x18003e08e`
- `Cabinet!__imp_FDICopy` at `0x18003e0cf`
- `Cabinet!__imp_FDICopy` at `0x18003e0cf`
- `Cabinet!__imp_FDIDestroy` at `0x18003e0f3`
- `Cabinet!__imp_FDIDestroy` at `0x18003e13c`
- `Cabinet!__imp_FDIDestroy` at `0x18003e0f3`
- `Cabinet!__imp_FDIDestroy` at `0x18003e13c`

## string_xrefs

- `0x18003df6e`: `PrivilegedActions.cab`
- `0x18003def2`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003df42`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003df87`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003dfc5`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e020`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e0de`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
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
      v10 = 405;
      goto LABEL_5;
    }
    *v12 = 0;
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Str[0], v11);
    LastError = DirectoryDeepNoThrow;
    if ( DirectoryDeepNoThrow < 0 )
    {
      v9 = (unsigned int)DirectoryDeepNoThrow;
      v10 = 407;
      goto LABEL_5;
    }
    pszCabPath = 0;
    v14 = CabUtils::ConvertWcharToANSI(lpWideCharStr, &pszCabPath);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)v14,
        dwCreationDisposition);
LABEL_10:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabPath);
      goto LABEL_28;
    }
    pszCabinet = 0;
    v15 = CabUtils::ConvertWcharToANSI(L"PrivilegedActions.cab", &pszCabinet);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
LABEL_13:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszCabinet);
      goto LABEL_10;
    }
    lpFileName = 0;
    v16 = CabUtils::ConvertWcharToANSI(a3, (char **)&lpFileName);
    LastError = v16;
    if ( v16 >= 0 )
    {
      FileA = CreateFileA(lpFileName, 0x120116u, 1u, 0, 2u, 0x100u, 0);
      if ( FileA == (HANDLE)-1LL )
      {
        v19 = 427;
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
            v22 = 459;
          }
          else
          {
            v22 = 447;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v22,
                        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                        v21);
          FDIDestroy(v20);
          goto LABEL_16;
        }
        v19 = 439;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v19,
                    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                    v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)v16,
        dwCreationDisposition);
    }
LABEL_16:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpFileName);
    goto LABEL_13;
  }
  v9 = (unsigned int)v7;
  v10 = 403;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
    (const char *)v9,
    dwCreationDisposition);
LABEL_28:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x18003de68  push    rbp
0x18003de6a  push    rbx
0x18003de6b  push    rsi
0x18003de6c  push    rdi
0x18003de6d  push    r14
0x18003de6f  lea     rbp, [rsp-37h]
0x18003de74  sub     rsp, 0A0h
0x18003de7b  mov     rax, cs:__security_cookie
0x18003de82  xor     rax, rsp
0x18003de85  mov     [rbp+57h+var_30], rax
0x18003de89  mov     r14, r9
0x18003de8c  mov     rdi, r8
0x18003de8f  mov     rsi, rcx
0x18003de92  mov     [rbp+57h+Str], 0
0x18003de9a  mov     [rbp+57h+var_50], 0
0x18003dea2  mov     [rbp+57h+var_48], 0
0x18003deaa  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003deae  mov     rdx, rdi
0x18003deb1  lea     rcx, [rbp+57h+Str]
0x18003deb5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003deba  mov     ebx, eax
0x18003debc  test    eax, eax
0x18003debe  jns     short loc_18003DECA
0x18003dec0  mov     r9d, eax
0x18003dec3  mov     edx, 193h
0x18003dec8  jmp     short loc_18003DEEE
0x18003deca  mov     edx, 5Ch ; '\'; Ch
0x18003decf  mov     rcx, [rbp+57h+Str]; Str
0x18003ded3  call    cs:__imp_wcsrchr
0x18003ded9  mov     rcx, rax
0x18003dedc  test    rax, rax
0x18003dedf  jnz     short loc_18003DF03
0x18003dee1  mov     ebx, 80070057h
0x18003dee6  mov     r9d, ebx; char *
0x18003dee9  mov     edx, 195h; void *
0x18003deee  mov     rcx, [rbp+5Fh]; this
0x18003def2  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003def9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003defe  jmp     loc_18003E162
0x18003df03  xor     eax, eax
0x18003df05  mov     [rcx], ax
0x18003df08  mov     rcx, [rbp+57h+Str]; this
0x18003df0c  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003df11  mov     ebx, eax
0x18003df13  test    eax, eax
0x18003df15  jns     short loc_18003DF21
0x18003df17  mov     r9d, eax
0x18003df1a  mov     edx, 197h
0x18003df1f  jmp     short loc_18003DEEE
0x18003df21  mov     [rbp+57h+pszCabPath], 0
0x18003df29  lea     rdx, [rbp+57h+pszCabPath]; char **
0x18003df2d  mov     rcx, rsi; lpWideCharStr
0x18003df30  call    ?ConvertWcharToANSI@CabUtils@@CAJPEBGPEAPEAD@Z; CabUtils::ConvertWcharToANSI(ushort const *,char * *)
0x18003df35  mov     ebx, eax
0x18003df37  test    eax, eax
0x18003df39  jns     short loc_18003DF62
0x18003df3b  mov     rcx, [rbp+5Fh]; this
0x18003df3f  mov     r9d, eax; char *
0x18003df42  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003df49  mov     edx, 19Ch; void *
0x18003df4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003df53  nop
0x18003df54  lea     rcx, [rbp+57h+pszCabPath]
0x18003df58  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003df5d  jmp     loc_18003E162
0x18003df62  mov     [rbp+57h+pszCabinet], 0
0x18003df6a  lea     rdx, [rbp+57h+pszCabinet]; char **
0x18003df6e  lea     rcx, WideCharStr; "PrivilegedActions.cab"
0x18003df75  call    ?ConvertWcharToANSI@CabUtils@@CAJPEBGPEAPEAD@Z; CabUtils::ConvertWcharToANSI(ushort const *,char * *)
0x18003df7a  mov     ebx, eax
0x18003df7c  test    eax, eax
0x18003df7e  jns     short loc_18003DFA4
0x18003df80  mov     rcx, [rbp+5Fh]; this
0x18003df84  mov     r9d, eax; char *
0x18003df87  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003df8e  mov     edx, 19Eh; void *
0x18003df93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003df98  nop
0x18003df99  lea     rcx, [rbp+57h+pszCabinet]
0x18003df9d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003dfa2  jmp     short loc_18003DF54
0x18003dfa4  mov     [rbp+57h+lpFileName], 0
0x18003dfac  lea     rdx, [rbp+57h+lpFileName]; char **
0x18003dfb0  mov     rcx, rdi; lpWideCharStr
0x18003dfb3  call    ?ConvertWcharToANSI@CabUtils@@CAJPEBGPEAPEAD@Z; CabUtils::ConvertWcharToANSI(ushort const *,char * *)
0x18003dfb8  mov     ebx, eax
0x18003dfba  test    eax, eax
0x18003dfbc  jns     short loc_18003DFE2
0x18003dfbe  mov     rcx, [rbp+5Fh]; this
0x18003dfc2  mov     r9d, eax; char *
0x18003dfc5  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003dfcc  mov     edx, 1A0h; void *
0x18003dfd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dfd6  nop
0x18003dfd7  lea     rcx, [rbp+57h+lpFileName]
0x18003dfdb  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003dfe0  jmp     short loc_18003DF99
0x18003dfe2  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18003dfeb  mov     esi, 100h
0x18003dff0  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003dff4  mov     [rsp+0C0h+dwCreationDisposition], 2; dwCreationDisposition
0x18003dffc  xor     r9d, r9d; lpSecurityAttributes
0x18003dfff  mov     edx, 120116h; dwDesiredAccess
0x18003e004  lea     r8d, [r9+1]; dwShareMode
0x18003e008  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003e00c  call    cs:__imp_CreateFileA
0x18003e012  mov     rbx, rax
0x18003e015  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e019  jnz     short loc_18003E034
0x18003e01b  mov     edx, 1ABh; void *
0x18003e020  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e027  mov     rcx, [rbp+5Fh]; this
0x18003e02b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e030  mov     ebx, eax
0x18003e032  jmp     short loc_18003DFD7
0x18003e034  xor     eax, eax
0x18003e036  mov     qword ptr [rbp+57h+var_40.erfOper], rax
0x18003e03a  mov     [rbp+57h+var_40.fError], eax
0x18003e03d  lea     rax, [rbp+57h+var_40]
0x18003e041  mov     [rsp+0C0h+perf], rax; perf
0x18003e046  mov     [rsp+0C0h+cpuType], 0FFFFFFFFh; cpuType
0x18003e04e  lea     rax, ?fdi_seek@@YAJ_JJH@Z; fdi_seek(__int64,long,int)
0x18003e055  mov     [rsp+0C0h+hTemplateFile], rax; pfnseek
0x18003e05a  lea     rax, ?fdi_close@@YAH_J@Z; fdi_close(__int64)
0x18003e061  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; pfnclose
0x18003e066  lea     rax, ?fdi_write@@YAI_JPEAXI@Z; fdi_write(__int64,void *,uint)
0x18003e06d  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; pfnwrite
0x18003e072  lea     r9, ?fdi_read@@YAI_JPEAXI@Z; pfnread
0x18003e079  lea     r8, ?fdi_open@@YA_JPEADHH@Z; pfnopen
0x18003e080  lea     rdx, ?fdi_free@@YAXPEAX@Z; pfnfree
0x18003e087  lea     rcx, ?fdi_alloc@@YAPEAXK@Z; pfnalloc
0x18003e08e  call    cs:__imp_FDICreate
0x18003e094  mov     rdi, rax
0x18003e097  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e09b  jnz     short loc_18003E0A7
0x18003e09d  mov     edx, 1B7h
0x18003e0a2  jmp     loc_18003E020
0x18003e0a7  mov     [rsp+0C0h+hTemplateFile], rbx; pvUser
0x18003e0ac  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], 0; pfnfdid
0x18003e0b5  lea     rax, ?fdi_notify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; fdi_notify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18003e0bc  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; pfnfdin
0x18003e0c1  xor     r9d, r9d; flags
0x18003e0c4  mov     r8, [rbp+57h+pszCabPath]; pszCabPath
0x18003e0c8  mov     rdx, [rbp+57h+pszCabinet]; pszCabinet
0x18003e0cc  mov     rcx, rdi; hfdi
0x18003e0cf  call    cs:__imp_FDICopy
0x18003e0d5  test    eax, eax
0x18003e0d7  jnz     short loc_18003E0FE
0x18003e0d9  mov     edx, 1BFh; void *
0x18003e0de  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e0e5  mov     rcx, [rbp+5Fh]; this
0x18003e0e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e0ee  mov     ebx, eax
0x18003e0f0  mov     rcx, rdi; hfdi
0x18003e0f3  call    cs:__imp_FDIDestroy
0x18003e0f9  jmp     loc_18003DFD7
0x18003e0fe  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18003e107  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003e10b  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003e113  xor     r9d, r9d; lpSecurityAttributes
0x18003e116  mov     edx, 120089h; dwDesiredAccess
0x18003e11b  lea     r8d, [r9+1]; dwShareMode
0x18003e11f  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003e123  call    cs:__imp_CreateFileA
0x18003e129  mov     [r14], rax
0x18003e12c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003e130  jnz     short loc_18003E139
0x18003e132  mov     edx, 1CBh
0x18003e137  jmp     short loc_18003E0DE
0x18003e139  mov     rcx, rdi; hfdi
0x18003e13c  call    cs:__imp_FDIDestroy
0x18003e142  nop
0x18003e143  lea     rcx, [rbp+57h+lpFileName]
0x18003e147  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003e14c  nop
0x18003e14d  lea     rcx, [rbp+57h+pszCabinet]
0x18003e151  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003e156  nop
0x18003e157  lea     rcx, [rbp+57h+pszCabPath]
0x18003e15b  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18003e160  xor     ebx, ebx
0x18003e162  lea     rcx, [rbp+57h+Str]
0x18003e166  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e16b  mov     eax, ebx
0x18003e16d  mov     rcx, [rbp+57h+var_30]
0x18003e171  xor     rcx, rsp; StackCookie
0x18003e174  call    __security_check_cookie
0x18003e179  add     rsp, 0A0h
0x18003e180  pop     r14
0x18003e182  pop     rdi
0x18003e183  pop     rsi
0x18003e184  pop     rbx
0x18003e185  pop     rbp
0x18003e186  retn
```
