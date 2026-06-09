# UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)

- ea: `0x18001abd8`
- end: `0x18001b188`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z`
- size: `1456`
- prototype: `__int64 __fastcall(const wchar_t *, int, const wchar_t *, const wchar_t *, int)`
- caller_count: `8`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800077d4`
- `0x18001a60c`
- `0x18001abd8`
- `0x18004d478`
- `0x180066250`
- `0x1800757a8`
- `0x180075ffc`
- `0x18008b3dc`

## callees

- `0x180002acc`
- `0x180002b1c`
- `0x18000716c`
- `0x18000cc74`
- `0x18000dad0`
- `0x180019808`
- `0x18001abd8`
- `0x18001dfac`
- `0x180023e8c`
- `0x1800303dc`
- `0x180050db0`
- `0x1800517cc`
- `0x180063d74`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aeba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aeff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aeba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0ec`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001af5a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001b15e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001af5a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001b15e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001af40`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001af40`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001ae18`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001ae18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ac8a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ac8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilRecursiveRemoveDirectory(const wchar_t *a1, int a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  LPCWCH *p_lpString2; // rax
  __int16 *v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  HANDLE FirstFileW; // r15
  __int64 v28; // r9
  __int64 v29; // rdx
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  const wchar_t *v32; // rbx
  __int64 v33; // r9
  const wchar_t *v34; // rdx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  DWORD v44; // eax
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpString2; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 cFileName; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v50; // [rsp+68h] [rbp-98h]
  _WORD v51[8]; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  lpString2 = a4;
  v7 = -1;
  lpFileName = v51;
  v50 = v51;
  v8 = 0;
  v51[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_1800D8000 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v9,
          &word_1800C6996);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpFileName);
    return 2147942487LL;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_67;
    lpString2 = a1;
    p_lpString2 = &lpString2;
    v17 = (__int16 *)&byte_1800C69C7;
    goto LABEL_66;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v8 = -2147024809;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      v45 = -2147024809;
      lpString2 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)byte_1800C6A13,
        v19,
        v20,
        (__int64)&lpString2,
        (__int64)&v45);
    }
    goto LABEL_67;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v8 = -2147024809;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      lpString2 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v21,
        (unsigned int)&word_1800C6A5E,
        v22,
        v23,
        (__int64)&lpString2);
    }
    goto LABEL_67;
  }
  if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpFileName, L"%ls\\*", a1) < 0 )
  {
    v8 = -2147024809;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      v45 = -2147024809;
      lpString2 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v24,
        (unsigned int)&byte_1800C6A9F,
        v25,
        v26,
        (__int64)&lpString2,
        (__int64)&v45);
    }
    goto LABEL_67;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  v7 = (__int64)FirstFileW;
  cFileName = (__int64)FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v44 = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(v44);
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_67;
    cFileName = (__int64)lpFileName;
    p_lpString2 = (LPCWCH *)&cFileName;
    v17 = &word_1800C6AE6;
LABEL_66:
    v45 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v13,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)p_lpString2,
      (__int64)&v45);
    goto LABEL_67;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_43;
    }
    v8 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           &lpFileName,
           L"%ls\\%ls",
           a1,
           FindFileData.cFileName);
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v45 = v8;
        cFileName = (__int64)FindFileData.cFileName;
        v47 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v41,
          (unsigned int)&word_1800C6B2E,
          v42,
          v43,
          (__int64)&v47,
          (__int64)&cFileName,
          (__int64)&v45);
      }
      goto LABEL_67;
    }
    v8 = 0;
    if ( !a3 )
      break;
    v28 = -1;
    do
      ++v28;
    while ( a3[v28] );
    v29 = (__int64)v50;
    v30 = lpFileName;
    v31 = v50 - lpFileName;
    if ( v31 != v28 )
      goto LABEL_34;
    if ( CompareStringOrdinal(lpFileName, v31, a3, v28, 1) != 2 )
      break;
LABEL_43:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v7 = -1;
      cFileName = -1;
      FindClose(FirstFileW);
      if ( a2
        && (int)_werDetail::PreparePathForDeletion(a1, v34) < 0
        && (unsigned int)dword_1800D8000 > 3
        && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v45 = v36;
        v47 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v35,
          (unsigned int)&byte_1800C6C0F,
          v36,
          v37,
          (__int64)&v47,
          (__int64)&v45);
      }
      UtilDeleteFilePath(a1);
      goto LABEL_67;
    }
  }
  v29 = (__int64)v50;
  v30 = lpFileName;
LABEL_34:
  v32 = lpString2;
  if ( lpString2 )
  {
    v33 = -1;
    do
      ++v33;
    while ( lpString2[v33] );
    v29 = (v29 - (__int64)v30) >> 1;
    if ( v29 == v33 )
    {
      if ( CompareStringOrdinal(v30, v29, lpString2, v33, 1) == 2 )
      {
LABEL_42:
        v8 = 0;
        goto LABEL_43;
      }
      v30 = lpFileName;
    }
  }
  if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
  {
    v8 = 0;
    if ( a2 )
    {
      if ( (int)_werDetail::PreparePathForDeletion(v30, (const wchar_t *)v29) < 0
        && (unsigned int)dword_1800D8000 > 3
        && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v45 = v39;
        v47 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)&unk_1800C6BC8,
          v39,
          v40,
          (__int64)&v47,
          (__int64)&v45);
      }
      v30 = lpFileName;
    }
    UtilDeleteFilePath(v30);
    goto LABEL_43;
  }
  v8 = UtilRecursiveRemoveDirectory(v30, a2, a3, v32, 0);
  if ( v8 >= 0 )
    goto LABEL_42;
  if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    v47 = lpFileName;
    p_lpString2 = &v47;
    v17 = (__int16 *)&unk_1800C6B80;
    goto LABEL_66;
  }
LABEL_67:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpFileName);
  if ( v7 != -1 )
    FindClose((HANDLE)v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001abd8  push    rbp
0x18001abda  push    rbx
0x18001abdb  push    rsi
0x18001abdc  push    r12
0x18001abde  push    r13
0x18001abe0  push    r14
0x18001abe2  push    r15
0x18001abe4  lea     rbp, [rsp-1E0h]
0x18001abec  sub     rsp, 2E0h
0x18001abf3  mov     rax, cs:__security_cookie
0x18001abfa  xor     rax, rsp
0x18001abfd  mov     [rbp+210h+var_40], rax
0x18001ac04  mov     [rsp+310h+lpString2], r9
0x18001ac09  mov     r12, r8
0x18001ac0c  mov     r13d, edx
0x18001ac0f  mov     rsi, rcx
0x18001ac12  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001ac16  lea     rax, [rsp+310h+var_2A0]
0x18001ac1b  mov     [rsp+310h+lpFileName], rax
0x18001ac20  lea     rax, [rsp+310h+var_2A0]
0x18001ac25  mov     [rsp+310h+var_2A8], rax
0x18001ac2a  xor     ebx, ebx
0x18001ac2c  mov     [rsp+310h+var_2A0], bx
0x18001ac31  xor     edx, edx; Val
0x18001ac33  mov     r8d, 250h; Size
0x18001ac39  lea     rcx, [rbp+210h+FindFileData]; void *
0x18001ac3d  call    memset_0
0x18001ac42  test    rsi, rsi
0x18001ac45  jnz     short loc_18001AC87
0x18001ac47  mov     eax, cs:dword_1800D8000
0x18001ac4d  cmp     eax, 2
0x18001ac50  jbe     short loc_18001AC72
0x18001ac52  lea     edx, [rbx+8]
0x18001ac55  lea     rcx, dword_1800D8000
0x18001ac5c  call    _tlgKeywordOn
0x18001ac61  test    al, al
0x18001ac63  jz      short loc_18001AC72
0x18001ac65  lea     rdx, word_1800C6996
0x18001ac6c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001ac71  nop
0x18001ac72  lea     rcx, [rsp+310h+lpFileName]; void *
0x18001ac77  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001ac7c  nop
0x18001ac7d  mov     eax, 80070057h
0x18001ac82  jmp     loc_18001B166
0x18001ac87  mov     rcx, rsi; lpFileName
0x18001ac8a  call    cs:__imp_GetFileAttributesW
0x18001ac90  cmp     eax, 0FFFFFFFFh
0x18001ac93  jnz     short loc_18001ACEC
0x18001ac95  call    cs:__imp_GetLastError
0x18001ac9b  mov     ecx, eax; unsigned int
0x18001ac9d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001aca2  mov     ebx, eax
0x18001aca4  mov     eax, cs:dword_1800D8000
0x18001acaa  cmp     eax, 2
0x18001acad  jbe     loc_18001B14A
0x18001acb3  mov     edx, 8
0x18001acb8  lea     rcx, dword_1800D8000
0x18001acbf  call    _tlgKeywordOn
0x18001acc4  test    al, al
0x18001acc6  jz      loc_18001B14A
0x18001accc  mov     [rsp+310h+lpString2], rsi
0x18001acd1  lea     rax, [rsp+310h+var_2D0]
0x18001acd6  mov     [rsp+310h+var_2E8], rax
0x18001acdb  lea     rax, [rsp+310h+lpString2]
0x18001ace0  lea     rdx, byte_1800C69C7
0x18001ace7  jmp     loc_18001B13B
0x18001acec  test    al, 10h
0x18001acee  jnz     short loc_18001AD4A
0x18001acf0  mov     ebx, 80070057h
0x18001acf5  mov     eax, cs:dword_1800D8000
0x18001acfb  cmp     eax, 2
0x18001acfe  jbe     loc_18001B14A
0x18001ad04  mov     edx, 8
0x18001ad09  lea     rcx, dword_1800D8000
0x18001ad10  call    _tlgKeywordOn
0x18001ad15  test    al, al
0x18001ad17  jz      loc_18001B14A
0x18001ad1d  mov     [rsp+310h+var_2D0], 80070057h
0x18001ad25  mov     [rsp+310h+lpString2], rsi
0x18001ad2a  lea     rax, [rsp+310h+var_2D0]
0x18001ad2f  mov     [rsp+310h+var_2E8], rax
0x18001ad34  lea     rax, [rsp+310h+lpString2]
0x18001ad39  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x18001ad3e  lea     rdx, byte_1800C6A13
0x18001ad45  jmp     loc_18001B144
0x18001ad4a  bt      eax, 0Ah
0x18001ad4e  jnb     short loc_18001AD9D
0x18001ad50  mov     ebx, 80070057h
0x18001ad55  mov     eax, cs:dword_1800D8000
0x18001ad5b  cmp     eax, 2
0x18001ad5e  jbe     loc_18001B14A
0x18001ad64  mov     edx, 8
0x18001ad69  lea     rcx, dword_1800D8000
0x18001ad70  call    _tlgKeywordOn
0x18001ad75  test    al, al
0x18001ad77  jz      loc_18001B14A
0x18001ad7d  mov     [rsp+310h+lpString2], rsi
0x18001ad82  lea     rax, [rsp+310h+lpString2]
0x18001ad87  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x18001ad8c  lea     rdx, word_1800C6A5E
0x18001ad93  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001ad98  jmp     loc_18001B14A
0x18001ad9d  mov     r8, rsi
0x18001ada0  lea     rdx, aLs; "%ls\\*"
0x18001ada7  lea     rcx, [rsp+310h+lpFileName]
0x18001adac  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001adb1  test    eax, eax
0x18001adb3  jns     short loc_18001AE0F
0x18001adb5  mov     ebx, 80070057h
0x18001adba  mov     eax, cs:dword_1800D8000
0x18001adc0  cmp     eax, 2
0x18001adc3  jbe     loc_18001B14A
0x18001adc9  mov     edx, 8
0x18001adce  lea     rcx, dword_1800D8000
0x18001add5  call    _tlgKeywordOn
0x18001adda  test    al, al
0x18001addc  jz      loc_18001B14A
0x18001ade2  mov     [rsp+310h+var_2D0], 80070057h
0x18001adea  mov     [rsp+310h+lpString2], rsi
0x18001adef  lea     rax, [rsp+310h+var_2D0]
0x18001adf4  mov     [rsp+310h+var_2E8], rax
0x18001adf9  lea     rax, [rsp+310h+lpString2]
0x18001adfe  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x18001ae03  lea     rdx, byte_1800C6A9F
0x18001ae0a  jmp     loc_18001B144
0x18001ae0f  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001ae13  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x18001ae18  call    cs:__imp_FindFirstFileW
0x18001ae1e  mov     r15, rax
0x18001ae21  mov     r14, rax
0x18001ae24  mov     [rsp+310h+var_2B8], rax
0x18001ae29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ae2d  jz      loc_18001B0EC
0x18001ae33  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x18001ae37  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18001ae3c  jnz     short loc_18001AE5E
0x18001ae3e  test    ax, ax
0x18001ae41  jz      loc_18001AF39
0x18001ae47  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18001ae4c  jnz     short loc_18001AE5E
0x18001ae4e  cmp     ax, 2Eh ; '.'
0x18001ae52  jnz     short loc_18001AE5E
0x18001ae54  cmp     [rbp+210h+FindFileData.cFileName+4], bx
0x18001ae58  jz      loc_18001AF39
0x18001ae5e  lea     r9, [rbp+210h+FindFileData.cFileName]
0x18001ae62  mov     r8, rsi
0x18001ae65  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18001ae6c  lea     rcx, [rsp+310h+lpFileName]
0x18001ae71  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001ae76  mov     ebx, eax
0x18001ae78  test    eax, eax
0x18001ae7a  js      loc_18001B086
0x18001ae80  xor     ebx, ebx
0x18001ae82  test    r12, r12
0x18001ae85  jz      short loc_18001AEC5
0x18001ae87  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001ae8b  inc     r9; cchCount2
0x18001ae8e  cmp     [r12+r9*2], bx
0x18001ae93  jnz     short loc_18001AE8B
0x18001ae95  mov     rdx, [rsp+310h+var_2A8]
0x18001ae9a  mov     rax, rdx
0x18001ae9d  mov     rcx, [rsp+310h+lpFileName]; lpString1
0x18001aea2  sub     rax, rcx
0x18001aea5  sar     rax, 1
0x18001aea8  cmp     rax, r9
0x18001aeab  jnz     short loc_18001AECF
0x18001aead  mov     edx, eax; cchCount1
0x18001aeaf  mov     [rsp+310h+bIgnoreCase], 1; bIgnoreCase
0x18001aeb7  mov     r8, r12; lpString2
0x18001aeba  call    cs:__imp_CompareStringOrdinal
0x18001aec0  cmp     eax, 2
0x18001aec3  jz      short loc_18001AF39
0x18001aec5  mov     rdx, [rsp+310h+var_2A8]
0x18001aeca  mov     rcx, [rsp+310h+lpFileName]; lpString1
0x18001aecf  mov     rbx, [rsp+310h+lpString2]
0x18001aed4  xor     eax, eax
0x18001aed6  test    rbx, rbx
0x18001aed9  jz      short loc_18001AF11
0x18001aedb  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001aedf  inc     r9; cchCount2
0x18001aee2  cmp     [rbx+r9*2], ax
0x18001aee7  jnz     short loc_18001AEDF
0x18001aee9  sub     rdx, rcx
0x18001aeec  sar     rdx, 1; cchCount1
0x18001aeef  cmp     rdx, r9
0x18001aef2  jnz     short loc_18001AF11
0x18001aef4  mov     [rsp+310h+bIgnoreCase], 1; bIgnoreCase
0x18001aefc  mov     r8, rbx; lpString2
0x18001aeff  call    cs:__imp_CompareStringOrdinal
0x18001af05  cmp     eax, 2
0x18001af08  jz      short loc_18001AF37
0x18001af0a  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x18001af0f  xor     eax, eax
0x18001af11  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x18001af15  jz      loc_18001AFCA
0x18001af1b  mov     [rsp+310h+bIgnoreCase], eax; int
0x18001af1f  mov     r9, rbx; wchar_t *
0x18001af22  mov     r8, r12; wchar_t *
0x18001af25  mov     edx, r13d; int
0x18001af28  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x18001af2d  mov     ebx, eax
0x18001af2f  test    eax, eax
0x18001af31  js      loc_18001B039
0x18001af37  xor     ebx, ebx
0x18001af39  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001af3d  mov     rcx, r15; hFindFile
0x18001af40  call    cs:__imp_FindNextFileW
0x18001af46  test    eax, eax
0x18001af48  jnz     loc_18001AE33
0x18001af4e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001af52  mov     [rsp+310h+var_2B8], r14
0x18001af57  mov     rcx, r15; hFindFile
0x18001af5a  call    cs:__imp_FindClose
0x18001af60  test    r13d, r13d
0x18001af63  jz      short loc_18001AFBD
0x18001af65  mov     rcx, rsi; lpFileName
0x18001af68  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x18001af6d  mov     r8d, eax
0x18001af70  test    eax, eax
0x18001af72  jns     short loc_18001AFBD
0x18001af74  mov     ecx, cs:dword_1800D8000
0x18001af7a  cmp     ecx, 3
0x18001af7d  jbe     short loc_18001AFBD
0x18001af7f  lea     edx, [r14+9]
0x18001af83  lea     rcx, dword_1800D8000
0x18001af8a  call    _tlgKeywordOn
0x18001af8f  test    al, al
0x18001af91  jz      short loc_18001AFBD
0x18001af93  mov     [rsp+310h+var_2D0], r8d
0x18001af98  mov     [rsp+310h+var_2C0], rsi
0x18001af9d  lea     rax, [rsp+310h+var_2D0]
0x18001afa2  mov     [rsp+310h+var_2E8], rax
0x18001afa7  lea     rax, [rsp+310h+var_2C0]
0x18001afac  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x18001afb1  lea     rdx, byte_1800C6C0F
0x18001afb8  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001afbd  mov     rcx, rsi; wchar_t *
0x18001afc0  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18001afc5  jmp     loc_18001B14A
0x18001afca  xor     ebx, ebx
0x18001afcc  test    r13d, r13d
0x18001afcf  jz      short loc_18001B02F
0x18001afd1  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x18001afd6  mov     r8d, eax
0x18001afd9  test    eax, eax
0x18001afdb  jns     short loc_18001B02A
0x18001afdd  mov     ecx, cs:dword_1800D8000
0x18001afe3  cmp     ecx, 3
0x18001afe6  jbe     short loc_18001B02A
0x18001afe8  lea     edx, [rbx+8]
0x18001afeb  lea     rcx, dword_1800D8000
0x18001aff2  call    _tlgKeywordOn
0x18001aff7  test    al, al
0x18001aff9  jz      short loc_18001B02A
0x18001affb  mov     [rsp+310h+var_2D0], r8d
0x18001b000  mov     rax, [rsp+310h+lpFileName]
0x18001b005  mov     [rsp+310h+var_2C0], rax
0x18001b00a  lea     rax, [rsp+310h+var_2D0]
0x18001b00f  mov     [rsp+310h+var_2E8], rax
0x18001b014  lea     rax, [rsp+310h+var_2C0]
0x18001b019  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x18001b01e  lea     rdx, unk_1800C6BC8
0x18001b025  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001b02a  mov     rcx, [rsp+310h+lpFileName]; wchar_t *
0x18001b02f  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18001b034  jmp     loc_18001AF39
0x18001b039  mov     eax, cs:dword_1800D8000
0x18001b03f  cmp     eax, 2
0x18001b042  jbe     loc_18001B14A
0x18001b048  mov     edx, 8
0x18001b04d  lea     rcx, dword_1800D8000
0x18001b054  call    _tlgKeywordOn
0x18001b059  test    al, al
0x18001b05b  jz      loc_18001B14A
0x18001b061  mov     rax, [rsp+310h+lpFileName]
0x18001b066  mov     [rsp+310h+var_2C0], rax
0x18001b06b  lea     rax, [rsp+310h+var_2D0]
0x18001b070  mov     [rsp+310h+var_2E8], rax
0x18001b075  lea     rax, [rsp+310h+var_2C0]
0x18001b07a  lea     rdx, unk_1800C6B80
0x18001b081  jmp     loc_18001B13B
0x18001b086  mov     eax, cs:dword_1800D8000
0x18001b08c  cmp     eax, 2
0x18001b08f  jbe     loc_18001B14A
0x18001b095  mov     edx, 8
0x18001b09a  lea     rcx, dword_1800D8000
0x18001b0a1  call    _tlgKeywordOn
0x18001b0a6  test    al, al
0x18001b0a8  jz      loc_18001B14A
0x18001b0ae  mov     [rsp+310h+var_2D0], ebx
0x18001b0b2  lea     rax, [rbp+210h+FindFileData.cFileName]
0x18001b0b6  mov     [rsp+310h+var_2B8], rax
0x18001b0bb  mov     [rsp+310h+var_2C0], rsi
0x18001b0c0  lea     rax, [rsp+310h+var_2D0]
0x18001b0c5  mov     [rsp+310h+var_2E0], rax
0x18001b0ca  lea     rax, [rsp+310h+var_2B8]
0x18001b0cf  mov     [rsp+310h+var_2E8], rax
0x18001b0d4  lea     rax, [rsp+310h+var_2C0]
0x18001b0d9  mov     qword ptr [rsp+310h+bIgnoreCase], rax
  ... truncated ...
```
