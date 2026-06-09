# Appx::Packaging::Sbom::ExtractAuthorFromSbomStream

- ea: `0x1800c6720`
- end: `0x1800c6b5e`
- name: `Appx::Packaging::Sbom::ExtractAuthorFromSbomStream`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c8800`

## callees

- `0x1800133fc`
- `0x1800992a0`
- `0x1800992c4`
- `0x180099e38`
- `0x18009d3d0`
- `0x1800c6720`
- `0x1800c97ec`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c68c6`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c6913`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c693c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c6965`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c68c6`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c6913`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c693c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800c6965`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c698f`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c69c0`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c69ed`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c698f`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c69c0`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800c69ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6afa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c6a53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c6adb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c6a53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c6adb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6aee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6aee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c6a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c6a9e`

## string_xrefs

- `0x1800c6766`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c67db`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c6818`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c6892`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c68f1`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c68d7`: `"metadata" not found in SBOM.json`
- `0x1800c6924`: `"tools" not found in SBOM.json metadata`
- `0x1800c6932`: `"components"`
- `0x1800c694d`: `"components" not found in SBOM.json tools`
- `0x1800c6976`: `"author" not found in SBOM.json components`
- `0x1800c69a6`: `Invalid SBOM.json format: missing colon after author`
- `0x1800c69d1`: `Invalid SBOM.json format: missing opening quote for author value`
- `0x1800c6a01`: `Invalid SBOM.json format: missing closing quote for author value`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Sbom::ExtractAuthorFromSbomStream(__int64 *a1, WCHAR **a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v7; // rsi
  unsigned int v8; // edi
  const char *v9; // rbx
  unsigned __int64 v10; // rdx
  char *v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r9
  char *v16; // rax
  const char *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r9
  signed int v20; // eax
  char *v21; // rax
  char *v22; // rax
  char *v23; // rax
  char *v24; // rax
  char *v25; // rax
  const CHAR *v26; // rbp
  char *v27; // rax
  int v28; // edi
  int v29; // eax
  __int64 v30; // r12
  signed int LastError; // eax
  WCHAR *v32; // rax
  WCHAR *v33; // rsi
  int lpWideCharStr; // [rsp+20h] [rbp-A8h]
  const char *cchWideChar; // [rsp+28h] [rbp-A0h]
  int v36[4]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v37[16]; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( !a1 )
  {
    v4 = 50;
LABEL_3:
    v5 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)v5,
      lpWideCharStr);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v4 = 51;
    goto LABEL_3;
  }
  *a2 = 0;
  memset_0(v37, 0, 0x50u);
  v5 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, __int64))(*a1 + 96))(a1, v37, 1);
  if ( v5 < 0 )
  {
    v4 = 56;
    goto LABEL_4;
  }
  v7 = v38;
  if ( v38 - 1 <= 0x9FFFFF )
  {
    v9 = (const char *)operator new[](v38 + 1, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v9 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)0x8007000ELL,
        lpWideCharStr);
      v11 = 0;
LABEL_52:
      operator delete(v11, v10);
      return v8;
    }
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*a1 + 40))(a1, 0, 0, 0);
    v8 = v12;
    if ( v12 < 0 )
    {
      v13 = 67;
LABEL_17:
      v15 = (unsigned int)v12;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)v15,
        lpWideCharStr);
LABEL_51:
      v11 = (char *)v9;
      goto LABEL_52;
    }
    v14 = *a1;
    v36[0] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, const char *, _QWORD, int *))(v14 + 24))(a1, v9, (unsigned int)v7, v36);
    v8 = v12;
    if ( v12 < 0 )
    {
      v13 = 70;
      goto LABEL_17;
    }
    if ( v36[0] != (_DWORD)v7 )
    {
      v8 = -2147418113;
      v13 = 71;
      v15 = 2147549183LL;
      goto LABEL_18;
    }
    v9[v7] = 0;
    v16 = strstr(v9, "\"metadata\"");
    if ( v16 )
    {
      v21 = strstr(v16, "\"tools\"");
      if ( v21 )
      {
        v22 = strstr(v21, "\"components\"");
        if ( v22 )
        {
          v23 = strstr(v22, "\"author\"");
          if ( v23 )
          {
            v24 = strchr(v23, 58);
            if ( v24 )
            {
              v25 = strchr(v24, 34);
              if ( v25 )
              {
                v26 = v25 + 1;
                v27 = strchr(v25 + 1, 34);
                if ( v27 )
                {
                  v28 = (_DWORD)v27 - (_DWORD)v26;
                  if ( (unsigned __int64)(v27 - v26 - 1) > 0x3FF )
                  {
                    v8 = -2147024809;
                    v13 = 131;
                    v15 = 2147942487LL;
                    goto LABEL_18;
                  }
                  v29 = MultiByteToWideChar(0xFDE9u, 0, v26, v28, 0, 0);
                  v30 = v29;
                  if ( !v29 )
                  {
                    LastError = GetLastError();
                    v8 = LastError;
                    if ( LastError > 0 )
                      v8 = (unsigned __int16)LastError | 0x80070000;
                    if ( (v8 & 0x80000000) == 0 )
                      goto LABEL_51;
                    v15 = v8;
                    v13 = 135;
                    goto LABEL_18;
                  }
                  v32 = (WCHAR *)CoTaskMemAlloc(2LL * v29 + 2);
                  v33 = v32;
                  if ( !v32 )
                  {
                    v8 = -2147024882;
                    v13 = 138;
                    v15 = 2147942414LL;
                    goto LABEL_18;
                  }
                  if ( MultiByteToWideChar(0xFDE9u, 0, v26, v28, v32, v30) )
                  {
                    v33[v30] = 0;
                    v8 = 0;
                    *a2 = v33;
                    goto LABEL_51;
                  }
                  CoTaskMemFree(v33);
                  v20 = GetLastError();
                  if ( v20 > 0 )
                    v20 = (unsigned __int16)v20 | 0x80070000;
LABEL_25:
                  v8 = v20;
                  goto LABEL_51;
                }
                v17 = "Invalid SBOM.json format: missing closing quote for author value";
                v19 = 11;
                v18 = 126;
              }
              else
              {
                v17 = "Invalid SBOM.json format: missing opening quote for author value";
                v19 = 11;
                v18 = 118;
              }
            }
            else
            {
              v19 = 11;
              v17 = "Invalid SBOM.json format: missing colon after author";
              v18 = 111;
            }
LABEL_24:
            v20 = wil::details::in1diag3::Return_Win32Msg(
                    retaddr,
                    (void *)v18,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
                    (const char *)v19,
                    (unsigned int)v17,
                    cchWideChar);
            goto LABEL_25;
          }
          v17 = "\"author\" not found in SBOM.json components";
          v18 = 104;
        }
        else
        {
          v17 = "\"components\" not found in SBOM.json tools";
          v18 = 97;
        }
      }
      else
      {
        v17 = "\"tools\" not found in SBOM.json metadata";
        v18 = 90;
      }
    }
    else
    {
      v17 = "\"metadata\" not found in SBOM.json";
      v18 = 83;
    }
    v19 = 1168;
    goto LABEL_24;
  }
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
    (const char *)0x80070057LL,
    lpWideCharStr);
  return v8;
}

```

## disassembly

```asm
0x1800c6720  mov     [rsp+arg_10], rbx
0x1800c6725  mov     [rsp+arg_18], rbp
0x1800c672a  push    rsi
0x1800c672b  push    rdi
0x1800c672c  push    r12
0x1800c672e  push    r14
0x1800c6730  push    r15
0x1800c6732  sub     rsp, 0A0h
0x1800c6739  mov     rax, cs:__security_cookie
0x1800c6740  xor     rax, rsp
0x1800c6743  mov     [rsp+0C8h+var_38], rax
0x1800c674b  mov     r15, rdx
0x1800c674e  mov     r14, rcx
0x1800c6751  test    rcx, rcx
0x1800c6754  jnz     short loc_1800C677C
0x1800c6756  lea     edx, [rcx+32h]; void *
0x1800c6759  mov     ebx, 80004003h
0x1800c675e  mov     rcx, [rsp+0C8h]; this
0x1800c6766  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c676d  mov     r9d, ebx; char *
0x1800c6770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6775  mov     eax, ebx
0x1800c6777  jmp     loc_1800C6B31
0x1800c677c  test    r15, r15
0x1800c677f  jnz     short loc_1800C6787
0x1800c6781  lea     edx, [r15+33h]
0x1800c6785  jmp     short loc_1800C6759
0x1800c6787  mov     qword ptr [rdx], 0
0x1800c678e  lea     rcx, [rsp+0C8h+var_88]; void *
0x1800c6793  xor     edx, edx; Val
0x1800c6795  lea     r8d, [rdx+50h]; Size
0x1800c6799  call    memset_0
0x1800c679e  mov     rax, [r14]
0x1800c67a1  lea     rdx, [rsp+0C8h+var_88]
0x1800c67a6  mov     r8d, 1
0x1800c67ac  mov     rcx, r14
0x1800c67af  mov     rax, [rax+60h]
0x1800c67b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67b8  mov     ebx, eax
0x1800c67ba  test    eax, eax
0x1800c67bc  jns     short loc_1800C67C5
0x1800c67be  mov     edx, 38h ; '8'
0x1800c67c3  jmp     short loc_1800C675E
0x1800c67c5  mov     esi, [rsp+0C8h+var_78]
0x1800c67c9  lea     eax, [rsi-1]
0x1800c67cc  cmp     eax, 9FFFFFh
0x1800c67d1  jbe     short loc_1800C67F9
0x1800c67d3  mov     rcx, [rsp+0C8h]; this
0x1800c67db  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c67e2  mov     edi, 80070057h
0x1800c67e7  mov     edx, 3Bh ; ';'; void *
0x1800c67ec  mov     r9d, edi; char *
0x1800c67ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c67f4  jmp     loc_1800C6B2F
0x1800c67f9  lea     ecx, [rsi+1]; unsigned __int64
0x1800c67fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c6803  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c6808  mov     rbx, rax
0x1800c680b  test    rax, rax
0x1800c680e  jnz     short loc_1800C6836
0x1800c6810  mov     rcx, [rsp+0C8h]; this
0x1800c6818  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c681f  mov     edi, 8007000Eh
0x1800c6824  lea     edx, [rax+40h]; void *
0x1800c6827  mov     r9d, edi; char *
0x1800c682a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c682f  xor     ecx, ecx
0x1800c6831  jmp     loc_1800C6B2A
0x1800c6836  mov     rax, [r14]
0x1800c6839  xor     edx, edx
0x1800c683b  xor     r9d, r9d
0x1800c683e  xor     r8d, r8d
0x1800c6841  mov     rcx, r14
0x1800c6844  mov     rax, [rax+28h]
0x1800c6848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c684d  mov     edi, eax
0x1800c684f  test    eax, eax
0x1800c6851  jns     short loc_1800C685A
0x1800c6853  mov     edx, 43h ; 'C'
0x1800c6858  jmp     short loc_1800C6887
0x1800c685a  mov     rax, [r14]
0x1800c685d  lea     r9, [rsp+0C8h+var_98]
0x1800c6862  mov     r8d, esi
0x1800c6865  mov     [rsp+0C8h+var_98], 0
0x1800c686d  mov     rdx, rbx
0x1800c6870  mov     rcx, r14
0x1800c6873  mov     rax, [rax+18h]
0x1800c6877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c687c  mov     edi, eax
0x1800c687e  test    eax, eax
0x1800c6880  jns     short loc_1800C68A3
0x1800c6882  mov     edx, 46h ; 'F'; void *
0x1800c6887  mov     r9d, eax; char *
0x1800c688a  mov     rcx, [rsp+0C8h]; this
0x1800c6892  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c6899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c689e  jmp     loc_1800C6B27
0x1800c68a3  cmp     [rsp+0C8h+var_98], esi
0x1800c68a7  jz      short loc_1800C68B8
0x1800c68a9  mov     edi, 8000FFFFh
0x1800c68ae  mov     edx, 47h ; 'G'
0x1800c68b3  mov     r9d, edi
0x1800c68b6  jmp     short loc_1800C688A
0x1800c68b8  lea     rdx, SubStr; "\"metadata\""
0x1800c68bf  mov     byte ptr [rsi+rbx], 0
0x1800c68c3  mov     rcx, rbx; Str
0x1800c68c6  call    cs:__imp_strstr
0x1800c68cd  nop     dword ptr [rax+rax+00h]
0x1800c68d2  test    rax, rax
0x1800c68d5  jnz     short loc_1800C6909
0x1800c68d7  lea     rax, aMetadataNotFou; "\"metadata\" not found in SBOM.json"
0x1800c68de  mov     edx, 53h ; 'S'; void *
0x1800c68e3  mov     r9d, 490h; char *
0x1800c68e9  mov     rcx, [rsp+0C8h]; this
0x1800c68f1  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c68f8  mov     [rsp+0C8h+lpWideCharStr], rax; unsigned int
0x1800c68fd  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800c6902  mov     edi, eax
0x1800c6904  jmp     loc_1800C6B27
0x1800c6909  lea     rdx, aTools; "\"tools\""
0x1800c6910  mov     rcx, rax; Str
0x1800c6913  call    cs:__imp_strstr
0x1800c691a  nop     dword ptr [rax+rax+00h]
0x1800c691f  test    rax, rax
0x1800c6922  jnz     short loc_1800C6932
0x1800c6924  lea     rax, aToolsNotFoundI; "\"tools\" not found in SBOM.json metada"...
0x1800c692b  mov     edx, 5Ah ; 'Z'
0x1800c6930  jmp     short loc_1800C68E3
0x1800c6932  lea     rdx, aComponents; "\"components\""
0x1800c6939  mov     rcx, rax; Str
0x1800c693c  call    cs:__imp_strstr
0x1800c6943  nop     dword ptr [rax+rax+00h]
0x1800c6948  test    rax, rax
0x1800c694b  jnz     short loc_1800C695B
0x1800c694d  lea     rax, aComponentsNotF; "\"components\" not found in SBOM.json t"...
0x1800c6954  mov     edx, 61h ; 'a'
0x1800c6959  jmp     short loc_1800C68E3
0x1800c695b  lea     rdx, aAuthor; "\"author\""
0x1800c6962  mov     rcx, rax; Str
0x1800c6965  call    cs:__imp_strstr
0x1800c696c  nop     dword ptr [rax+rax+00h]
0x1800c6971  test    rax, rax
0x1800c6974  jnz     short loc_1800C6987
0x1800c6976  lea     rax, aAuthorNotFound; "\"author\" not found in SBOM.json compo"...
0x1800c697d  mov     edx, 68h ; 'h'
0x1800c6982  jmp     loc_1800C68E3
0x1800c6987  mov     edx, 3Ah ; ':'; Val
0x1800c698c  mov     rcx, rax; Str
0x1800c698f  call    cs:__imp_strchr
0x1800c6996  nop     dword ptr [rax+rax+00h]
0x1800c699b  test    rax, rax
0x1800c699e  jnz     short loc_1800C69B6
0x1800c69a0  mov     r9d, 0Bh
0x1800c69a6  lea     rax, aInvalidSbomJso; "Invalid SBOM.json format: missing colon"...
0x1800c69ad  lea     edx, [r9+64h]
0x1800c69b1  jmp     loc_1800C68E9
0x1800c69b6  mov     edi, 22h ; '"'
0x1800c69bb  mov     rcx, rax; Str
0x1800c69be  mov     edx, edi; Val
0x1800c69c0  call    cs:__imp_strchr
0x1800c69c7  nop     dword ptr [rax+rax+00h]
0x1800c69cc  test    rax, rax
0x1800c69cf  jnz     short loc_1800C69E4
0x1800c69d1  lea     rax, aInvalidSbomJso_0; "Invalid SBOM.json format: missing openi"...
0x1800c69d8  lea     r9d, [rdi-17h]
0x1800c69dc  lea     edx, [rdi+54h]
0x1800c69df  jmp     loc_1800C68E9
0x1800c69e4  lea     rbp, [rax+1]
0x1800c69e8  mov     edx, edi; Val
0x1800c69ea  mov     rcx, rbp; Str
0x1800c69ed  call    cs:__imp_strchr
0x1800c69f4  nop     dword ptr [rax+rax+00h]
0x1800c69f9  mov     rdi, rax
0x1800c69fc  test    rax, rax
0x1800c69ff  jnz     short loc_1800C6A14
0x1800c6a01  lea     rax, aInvalidSbomJso_1; "Invalid SBOM.json format: missing closi"...
0x1800c6a08  lea     r9d, [rdi+0Bh]
0x1800c6a0c  lea     edx, [rdi+7Eh]
0x1800c6a0f  jmp     loc_1800C68E9
0x1800c6a14  sub     rdi, rbp
0x1800c6a17  lea     rax, [rdi-1]
0x1800c6a1b  cmp     rax, 3FFh
0x1800c6a21  jbe     short loc_1800C6A35
0x1800c6a23  mov     edi, 80070057h
0x1800c6a28  mov     edx, 83h
0x1800c6a2d  mov     r9d, edi
0x1800c6a30  jmp     loc_1800C688A
0x1800c6a35  mov     dword ptr [rsp+0C8h+cchWideChar], 0; cchWideChar
0x1800c6a3d  mov     r9d, edi; cbMultiByte
0x1800c6a40  mov     r8, rbp; lpMultiByteStr
0x1800c6a43  mov     [rsp+0C8h+lpWideCharStr], 0; lpWideCharStr
0x1800c6a4c  xor     edx, edx; dwFlags
0x1800c6a4e  mov     ecx, 0FDE9h; CodePage
0x1800c6a53  call    cs:__imp_MultiByteToWideChar
0x1800c6a5a  nop     dword ptr [rax+rax+00h]
0x1800c6a5f  movsxd  r12, eax
0x1800c6a62  test    eax, eax
0x1800c6a64  jnz     short loc_1800C6A96
0x1800c6a66  call    cs:__imp_GetLastError
0x1800c6a6d  nop     dword ptr [rax+rax+00h]
0x1800c6a72  mov     edi, eax
0x1800c6a74  test    eax, eax
0x1800c6a76  jle     short loc_1800C6A81
0x1800c6a78  movzx   edi, ax
0x1800c6a7b  or      edi, 80070000h
0x1800c6a81  test    edi, edi
0x1800c6a83  jns     loc_1800C6B27
0x1800c6a89  mov     r9d, edi
0x1800c6a8c  mov     edx, 87h
0x1800c6a91  jmp     loc_1800C688A
0x1800c6a96  lea     rcx, ds:2[r12*2]; cb
0x1800c6a9e  call    cs:__imp_CoTaskMemAlloc
0x1800c6aa5  nop     dword ptr [rax+rax+00h]
0x1800c6aaa  mov     rsi, rax
0x1800c6aad  test    rax, rax
0x1800c6ab0  jnz     short loc_1800C6AC4
0x1800c6ab2  mov     edi, 8007000Eh
0x1800c6ab7  mov     edx, 8Ah
0x1800c6abc  mov     r9d, edi
0x1800c6abf  jmp     loc_1800C688A
0x1800c6ac4  mov     dword ptr [rsp+0C8h+cchWideChar], r12d; cchWideChar
0x1800c6ac9  mov     r9d, edi; cbMultiByte
0x1800c6acc  mov     r8, rbp; lpMultiByteStr
0x1800c6acf  mov     [rsp+0C8h+lpWideCharStr], rsi; lpWideCharStr
0x1800c6ad4  xor     edx, edx; dwFlags
0x1800c6ad6  mov     ecx, 0FDE9h; CodePage
0x1800c6adb  call    cs:__imp_MultiByteToWideChar
0x1800c6ae2  nop     dword ptr [rax+rax+00h]
0x1800c6ae7  test    eax, eax
0x1800c6ae9  jnz     short loc_1800C6B1B
0x1800c6aeb  mov     rcx, rsi; pv
0x1800c6aee  call    cs:__imp_CoTaskMemFree
0x1800c6af5  nop     dword ptr [rax+rax+00h]
0x1800c6afa  call    cs:__imp_GetLastError
0x1800c6b01  nop     dword ptr [rax+rax+00h]
0x1800c6b06  test    eax, eax
0x1800c6b08  jle     loc_1800C6902
0x1800c6b0e  movzx   eax, ax
0x1800c6b11  or      eax, 80070000h
0x1800c6b16  jmp     loc_1800C6902
0x1800c6b1b  xor     eax, eax
0x1800c6b1d  mov     [rsi+r12*2], ax
0x1800c6b22  xor     edi, edi
0x1800c6b24  mov     [r15], rsi
0x1800c6b27  mov     rcx, rbx; void *
0x1800c6b2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c6b2f  mov     eax, edi
0x1800c6b31  mov     rcx, [rsp+0C8h+var_38]
0x1800c6b39  xor     rcx, rsp; StackCookie
0x1800c6b3c  call    __security_check_cookie
0x1800c6b41  lea     r11, [rsp+0C8h+var_28]
0x1800c6b49  mov     rbx, [r11+40h]
0x1800c6b4d  mov     rbp, [r11+48h]
0x1800c6b51  mov     rsp, r11
0x1800c6b54  pop     r15
0x1800c6b56  pop     r14
0x1800c6b58  pop     r12
0x1800c6b5a  pop     rdi
0x1800c6b5b  pop     rsi
0x1800c6b5c  retn
```
