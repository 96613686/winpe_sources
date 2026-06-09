# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x1800072cc`
- end: `0x18000779d`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `1233`
- prototype: `int(const wchar_t *, void *)`
- caller_count: `9`
- callee_count: `19`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180005380`
- `0x18000718c`
- `0x180008568`
- `0x18001bbc4`
- `0x18001dfac`
- `0x180035ce0`
- `0x18003ef14`
- `0x18004ee3c`
- `0x18006493c`

## callees

- `0x180002acc`
- `0x180002c14`
- `0x180002d9c`
- `0x180003024`
- `0x1800072cc`
- `0x18000bfbc`
- `0x18000c390`
- `0x18000dad0`
- `0x180019808`
- `0x18001c650`
- `0x180023dc4`
- `0x18002d010`
- `0x1800303dc`
- `0x1800306e4`
- `0x180038f78`
- `0x18003bf14`
- `0x18004ac4c`
- `0x180050db0`
- `0x18006528c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000738d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000738d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007654`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007534`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180007528`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800075b0`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180007528`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800075b0`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x180007663`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x180007663`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyFilePath(WCHAR *a1, void *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int FinalPathByHandle; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rdx
  __int64 v14; // r8
  char v15; // al
  __int64 v16; // r8
  char v17; // bl
  __int64 v18; // rax
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // r9
  DWORD LongPathNameW; // eax
  DWORD v23; // edi
  signed int LastError; // eax
  const wchar_t *v25; // rdx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  LPWSTR v29; // rbx
  __int64 v30; // rdi
  const WCHAR *v31; // r10
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  int v37; // r8d
  __int64 v38; // r9
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  LPWSTR lpszLongPath; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v45; // [rsp+60h] [rbp-A0h]
  _WORD v46[8]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v47; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v48; // [rsp+80h] [rbp-80h]
  _WORD v49[8]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v50[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v51[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v52[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v53[24]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR szLongPath[264]; // [rsp+E0h] [rbp-20h] BYREF

  v47 = v49;
  v48 = v49;
  v49[0] = 0;
  lpszShortPath = v46;
  v45 = v46;
  v46[0] = 0;
  if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)&word_1800C6C9E,
      v5,
      v6,
      (__int64)&lpszLongPath);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !(unsigned int)UtilIsLowRightsProcess(CurrentProcess) )
    {
      if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v9,
          &unk_1800C6CD8);
      FinalPathByHandle = 0;
      goto LABEL_55;
    }
    goto LABEL_11;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_11:
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_55;
    LODWORD(lpszLongPath) = FinalPathByHandle;
    v13 = byte_1800C6D09;
    goto LABEL_14;
  }
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  if ( !v14 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_55;
  }
  v15 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(&v47);
  v17 = v15;
  if ( a1[v16 - 1] == 92 && !v15 )
    --v16;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           a1,
                           v16) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_55;
    LODWORD(lpszLongPath) = -2147024882;
    v13 = &byte_1800C6D37;
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v10,
      (_DWORD)v13,
      v11,
      v12,
      (__int64)&lpszLongPath);
    goto LABEL_55;
  }
  if ( v17 && (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    _tlgWrapBinary<wchar_t,2>(v51, lpszShortPath, (unsigned __int16)(v45 - lpszShortPath));
    v18 = _tlgWrapBinary<wchar_t,2>(v50, v47, (unsigned __int16)(v48 - v47));
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
      v19,
      (unsigned int)&dword_1800C6D6C,
      v20,
      v21,
      (__int64)&lpszLongPath,
      v18,
      v21);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v23 = LongPathNameW;
  if ( !LongPathNameW )
  {
    LastError = GetLastError();
    FinalPathByHandle = LastError;
    if ( LastError > 0 )
      FinalPathByHandle = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      LODWORD(lpszLongPath) = FinalPathByHandle;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)byte_1800C6DCD,
        v27,
        v28,
        (__int64)&lpszLongPath);
    }
LABEL_43:
    if ( FinalPathByHandle < 0 )
      goto LABEL_55;
    goto LABEL_47;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&lpszLongPath, LongPathNameW);
    v29 = lpszLongPath;
    if ( lpszLongPath )
    {
      if ( v23 > GetLongPathNameW(lpszShortPath, lpszLongPath, v23) )
        FinalPathByHandle = (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                               &lpszShortPath,
                                               v29) == 0
                          ? 0x8007000E
                          : 0;
      else
        FinalPathByHandle = -2147418113;
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpszLongPath);
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_55;
  }
  FinalPathByHandle = 0;
LABEL_47:
  v30 = (unsigned int)_werDetail::HasExtendedLengthPathPrefix((_werDetail *)lpszShortPath, v25) == 0 ? 4 : 0;
  v32 = v45 - v31;
  if ( v32 != v48 - v47 - v30 || CompareStringOrdinal(v31, v32, &v47[v30], v32, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3
      && (unsigned int)dword_1800D8000 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 0x200000000008LL) )
    {
      LODWORD(lpszLongPath) = v30;
      _tlgWrapBinary<wchar_t,2>(v52, v47, (unsigned __int16)(v48 - v47));
      v36 = _tlgWrapBinary<wchar_t,2>(v53, lpszShortPath, (unsigned __int16)(v45 - lpszShortPath));
      v50[0] = a1;
      v51[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
        (unsigned int)&lpszLongPath,
        (unsigned int)&word_1800C6E06,
        v37,
        v38,
        (__int64)v51,
        (__int64)v50,
        v36,
        v38,
        (__int64)&lpszLongPath);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35);
    FinalPathByHandle = -2147024735;
  }
LABEL_55:
  if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    LODWORD(lpszLongPath) = FinalPathByHandle;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v39,
      (unsigned int)word_1800C6E7A,
      v40,
      v41,
      (__int64)&lpszLongPath);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpszShortPath);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v47);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x1800072cc  mov     [rsp-8+arg_10], rbx
0x1800072d1  mov     [rsp-8+arg_18], rsi
0x1800072d6  push    rbp
0x1800072d7  push    rdi
0x1800072d8  push    r12
0x1800072da  push    r14
0x1800072dc  push    r15
0x1800072de  lea     rbp, [rsp-200h]
0x1800072e6  sub     rsp, 300h
0x1800072ed  mov     rax, cs:__security_cookie
0x1800072f4  xor     rax, rsp
0x1800072f7  mov     [rbp+220h+var_30], rax
0x1800072fe  mov     rbx, rdx
0x180007301  mov     rsi, rcx
0x180007304  lea     rax, [rbp+220h+var_298]
0x180007308  mov     [rsp+320h+var_2A8], rax
0x18000730d  lea     rax, [rbp+220h+var_298]
0x180007311  mov     [rbp+220h+var_2A0], rax
0x180007315  xor     r14d, r14d
0x180007318  mov     [rbp+220h+var_298], r14w
0x18000731d  lea     rax, [rsp+320h+var_2B8]
0x180007322  mov     [rsp+320h+lpszShortPath], rax
0x180007327  lea     rax, [rsp+320h+var_2B8]
0x18000732c  mov     [rsp+320h+var_2C0], rax
0x180007331  mov     [rsp+320h+var_2B8], r14w
0x180007337  mov     eax, cs:dword_1800D8000
0x18000733d  lea     r12d, [r14+8]
0x180007341  lea     r15, dword_1800D8000
0x180007348  cmp     eax, 4
0x18000734b  jbe     short loc_180007377
0x18000734d  mov     edx, r12d
0x180007350  mov     rcx, r15
0x180007353  call    _tlgKeywordOn
0x180007358  test    al, al
0x18000735a  jz      short loc_180007377
0x18000735c  mov     [rsp+320h+lpszLongPath], rsi
0x180007361  lea     rax, [rsp+320h+lpszLongPath]
0x180007366  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18000736b  lea     rdx, word_1800C6C9E
0x180007372  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180007377  lea     rdx, [rsp+320h+var_2A8]
0x18000737c  mov     rcx, rbx; hFile
0x18000737f  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180007384  mov     ebx, eax
0x180007386  cmp     eax, 80070005h
0x18000738b  jnz     short loc_1800073CD
0x18000738d  call    cs:__imp_GetCurrentProcess
0x180007393  mov     rcx, rax; ProcessHandle
0x180007396  call    ?UtilIsLowRightsProcess@@YAJPEAX@Z; UtilIsLowRightsProcess(void *)
0x18000739b  test    eax, eax
0x18000739d  jnz     short loc_1800073D1
0x18000739f  mov     eax, cs:dword_1800D8000
0x1800073a5  cmp     eax, 4
0x1800073a8  jbe     short loc_1800073C5
0x1800073aa  mov     rdx, r12
0x1800073ad  mov     rcx, r15
0x1800073b0  call    _tlgKeywordOn
0x1800073b5  test    al, al
0x1800073b7  jz      short loc_1800073C5
0x1800073b9  lea     rdx, unk_1800C6CD8
0x1800073c0  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800073c5  mov     ebx, r14d
0x1800073c8  jmp     loc_180007726
0x1800073cd  test    ebx, ebx
0x1800073cf  jns     short loc_180007412
0x1800073d1  mov     eax, cs:dword_1800D8000
0x1800073d7  cmp     eax, 2
0x1800073da  jbe     loc_180007726
0x1800073e0  mov     rdx, r12
0x1800073e3  mov     rcx, r15
0x1800073e6  call    _tlgKeywordOn
0x1800073eb  test    al, al
0x1800073ed  jz      loc_180007726
0x1800073f3  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x1800073f7  lea     rdx, byte_1800C6D09
0x1800073fe  lea     rax, [rsp+320h+lpszLongPath]
0x180007403  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180007408  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000740d  jmp     loc_180007726
0x180007412  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007416  inc     r8
0x180007419  cmp     [rsi+r8*2], r14w
0x18000741e  jnz     short loc_180007416
0x180007420  cmp     r8, 1
0x180007424  jnb     short loc_180007430
0x180007426  mov     ebx, 80070057h
0x18000742b  jmp     loc_180007726
0x180007430  lea     rcx, [rsp+320h+var_2A8]
0x180007435  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x18000743a  mov     bl, al
0x18000743c  cmp     word ptr [rsi+r8*2-2], 5Ch ; '\'
0x180007443  jnz     short loc_18000744C
0x180007445  test    al, al
0x180007447  jnz     short loc_18000744C
0x180007449  dec     r8
0x18000744c  mov     rdx, rsi
0x18000744f  lea     rcx, [rsp+320h+lpszShortPath]
0x180007454  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180007459  test    al, al
0x18000745b  jnz     short loc_180007498
0x18000745d  mov     ebx, 8007000Eh
0x180007462  mov     eax, cs:dword_1800D8000
0x180007468  cmp     eax, 2
0x18000746b  jbe     loc_180007726
0x180007471  mov     rdx, r12
0x180007474  mov     rcx, r15
0x180007477  call    _tlgKeywordOn
0x18000747c  test    al, al
0x18000747e  jz      loc_180007726
0x180007484  mov     dword ptr [rsp+320h+lpszLongPath], 8007000Eh
0x18000748c  lea     rdx, byte_1800C6D37
0x180007493  jmp     loc_1800073FE
0x180007498  test    bl, bl
0x18000749a  jz      short loc_180007517
0x18000749c  mov     eax, cs:dword_1800D8000
0x1800074a2  cmp     eax, 4
0x1800074a5  jbe     short loc_180007517
0x1800074a7  mov     rdx, r12
0x1800074aa  mov     rcx, r15
0x1800074ad  call    _tlgKeywordOn
0x1800074b2  test    al, al
0x1800074b4  jz      short loc_180007517
0x1800074b6  mov     rax, [rsp+320h+var_2C0]
0x1800074bb  mov     rdx, [rsp+320h+lpszShortPath]
0x1800074c0  sub     rax, rdx
0x1800074c3  sar     rax, 1
0x1800074c6  movzx   r8d, ax
0x1800074ca  lea     rcx, [rbp+220h+var_278]
0x1800074ce  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800074d3  mov     r9, rax
0x1800074d6  mov     rcx, [rbp+220h+var_2A0]
0x1800074da  mov     rdx, [rsp+320h+var_2A8]
0x1800074df  sub     rcx, rdx
0x1800074e2  sar     rcx, 1
0x1800074e5  movzx   r8d, cx
0x1800074e9  lea     rcx, [rbp+220h+var_288]
0x1800074ed  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800074f2  mov     [rsp+320h+lpszLongPath], rsi
0x1800074f7  mov     [rsp+320h+var_2F0], r9
0x1800074fc  mov     [rsp+320h+var_2F8], rax
0x180007501  lea     rax, [rsp+320h+lpszLongPath]
0x180007506  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18000750b  lea     rdx, dword_1800C6D6C
0x180007512  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x180007517  mov     ebx, 105h
0x18000751c  mov     r8d, ebx; cchBuffer
0x18000751f  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x180007523  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x180007528  call    cs:__imp_GetLongPathNameW
0x18000752e  mov     edi, eax
0x180007530  test    eax, eax
0x180007532  jnz     short loc_180007583
0x180007534  call    cs:__imp_GetLastError
0x18000753a  mov     ebx, eax
0x18000753c  test    eax, eax
0x18000753e  jle     short loc_180007549
0x180007540  movzx   ebx, ax
0x180007543  or      ebx, 80070000h
0x180007549  mov     eax, cs:dword_1800D8000
0x18000754f  cmp     eax, 2
0x180007552  jbe     loc_1800075E5
0x180007558  mov     rdx, r12
0x18000755b  mov     rcx, r15
0x18000755e  call    _tlgKeywordOn
0x180007563  test    al, al
0x180007565  jz      short loc_1800075E5
0x180007567  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x18000756b  lea     rax, [rsp+320h+lpszLongPath]
0x180007570  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180007575  lea     rdx, byte_1800C6DCD
0x18000757c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180007581  jmp     short loc_1800075E5
0x180007583  cmp     edi, ebx
0x180007585  jbe     short loc_1800075EF
0x180007587  mov     rdx, rdi
0x18000758a  lea     rcx, [rsp+320h+lpszLongPath]
0x18000758f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180007594  mov     rbx, [rsp+320h+lpszLongPath]
0x180007599  test    rbx, rbx
0x18000759c  jnz     short loc_1800075A5
0x18000759e  mov     ebx, 8007000Eh
0x1800075a3  jmp     short loc_1800075DB
0x1800075a5  mov     r8d, edi; cchBuffer
0x1800075a8  mov     rdx, rbx; lpszLongPath
0x1800075ab  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x1800075b0  call    cs:__imp_GetLongPathNameW
0x1800075b6  cmp     edi, eax
0x1800075b8  ja      short loc_1800075C1
0x1800075ba  mov     ebx, 8000FFFFh
0x1800075bf  jmp     short loc_1800075DB
0x1800075c1  mov     rdx, rbx
0x1800075c4  lea     rcx, [rsp+320h+lpszShortPath]
0x1800075c9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800075ce  neg     al
0x1800075d0  sbb     ecx, ecx
0x1800075d2  not     ecx
0x1800075d4  mov     ebx, 8007000Eh
0x1800075d9  and     ebx, ecx
0x1800075db  lea     rcx, [rsp+320h+lpszLongPath]; void *
0x1800075e0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800075e5  test    ebx, ebx
0x1800075e7  js      loc_180007726
0x1800075ed  jmp     short loc_180007608
0x1800075ef  lea     rdx, [rbp+220h+szLongPath]
0x1800075f3  lea     rcx, [rsp+320h+lpszShortPath]
0x1800075f8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800075fd  test    al, al
0x1800075ff  jz      loc_180007721
0x180007605  mov     ebx, r14d
0x180007608  mov     r10, [rsp+320h+lpszShortPath]
0x18000760d  mov     rcx, r10; this
0x180007610  call    ?HasExtendedLengthPathPrefix@_werDetail@@YAHPEB_W@Z; _werDetail::HasExtendedLengthPathPrefix(wchar_t const *)
0x180007615  neg     eax
0x180007617  sbb     ecx, ecx
0x180007619  not     ecx
0x18000761b  and     ecx, 4
0x18000761e  mov     edi, ecx
0x180007620  mov     rdx, [rsp+320h+var_2C0]
0x180007625  sub     rdx, r10
0x180007628  sar     rdx, 1; cchCount1
0x18000762b  mov     rax, [rbp+220h+var_2A0]
0x18000762f  mov     rcx, [rsp+320h+var_2A8]
0x180007634  sub     rax, rcx
0x180007637  sar     rax, 1
0x18000763a  sub     rax, rdi
0x18000763d  cmp     rdx, rax
0x180007640  jnz     short loc_180007663
0x180007642  lea     r8, [rcx+rdi*2]; lpString2
0x180007646  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x18000764e  mov     r9d, edx; cchCount2
0x180007651  mov     rcx, r10; lpString1
0x180007654  call    cs:__imp_CompareStringOrdinal
0x18000765a  cmp     eax, 2
0x18000765d  jz      loc_180007726
0x180007663  call    cs:__imp_TelGetWerTelemetryMode
0x180007669  cmp     eax, 3
0x18000766c  jnz     loc_180007715
0x180007672  mov     eax, cs:dword_1800D8000
0x180007678  cmp     eax, 2
0x18000767b  jbe     loc_180007715
0x180007681  mov     rdx, 200000000008h
0x18000768b  mov     rcx, r15
0x18000768e  call    _tlgKeywordOn
0x180007693  test    al, al
0x180007695  jz      short loc_180007715
0x180007697  mov     dword ptr [rsp+320h+lpszLongPath], edi
0x18000769b  mov     rax, [rbp+220h+var_2A0]
0x18000769f  mov     rdx, [rsp+320h+var_2A8]
0x1800076a4  sub     rax, rdx
0x1800076a7  sar     rax, 1
0x1800076aa  movzx   r8d, ax
0x1800076ae  lea     rcx, [rbp+220h+var_268]
0x1800076b2  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800076b7  mov     r9, rax
0x1800076ba  mov     rcx, [rsp+320h+var_2C0]
0x1800076bf  mov     rdx, [rsp+320h+lpszShortPath]
0x1800076c4  sub     rcx, rdx
0x1800076c7  sar     rcx, 1
0x1800076ca  movzx   r8d, cx
0x1800076ce  lea     rcx, [rbp+220h+var_258]
0x1800076d2  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1800076d7  mov     [rbp+220h+var_288], rsi
0x1800076db  mov     [rbp+220h+var_278], 1000000h
0x1800076e3  lea     rcx, [rsp+320h+lpszLongPath]
0x1800076e8  mov     [rsp+320h+var_2E0], rcx
0x1800076ed  mov     [rsp+320h+var_2E8], r9
0x1800076f2  mov     [rsp+320h+var_2F0], rax
0x1800076f7  lea     rax, [rbp+220h+var_288]
0x1800076fb  mov     [rsp+320h+var_2F8], rax
0x180007700  lea     rax, [rbp+220h+var_278]
0x180007704  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180007709  lea     rdx, word_1800C6E06
0x180007710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperArray@$00@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperArray@$00@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x180007715  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000771a  mov     ebx, 800700A1h
0x18000771f  jmp     short loc_180007726
0x180007721  mov     ebx, 8007000Eh
0x180007726  mov     eax, cs:dword_1800D8000
0x18000772c  cmp     eax, 4
0x18000772f  jbe     short loc_18000775B
0x180007731  mov     rdx, r12
0x180007734  mov     rcx, r15
0x180007737  call    _tlgKeywordOn
0x18000773c  test    al, al
0x18000773e  jz      short loc_18000775B
0x180007740  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x180007744  lea     rax, [rsp+320h+lpszLongPath]
0x180007749  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18000774e  lea     rdx, word_1800C6E7A
0x180007755  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000775a  nop
0x18000775b  lea     rcx, [rsp+320h+lpszShortPath]; void *
0x180007760  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007765  nop
0x180007766  lea     rcx, [rsp+320h+var_2A8]; void *
0x18000776b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007770  mov     eax, ebx
0x180007772  mov     rcx, [rbp+220h+var_30]
0x180007779  xor     rcx, rsp; StackCookie
0x18000777c  call    __security_check_cookie
  ... truncated ...
```
