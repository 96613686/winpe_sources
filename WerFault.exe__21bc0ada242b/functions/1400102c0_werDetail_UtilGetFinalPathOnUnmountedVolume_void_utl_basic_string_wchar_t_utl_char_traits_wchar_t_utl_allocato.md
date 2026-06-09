# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1400102c0`
- end: `0x1400108cd`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1549`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14000ff08`

## callees

- `0x14000113c`
- `0x1400011dc`
- `0x14000126c`
- `0x14000134c`
- `0x140002470`
- `0x140002728`
- `0x14000c8a0`
- `0x14000e6dc`
- `0x1400102c0`
- `0x140012210`
- `0x140014104`
- `0x1400141b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400104ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400107d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400104ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400107d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001089e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001089e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400105d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400105d7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010337`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010588`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010337`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010588`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400104d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400104d7`

## string_xrefs

- `0x14001041e`: `StorePath`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  char *FileW; // rbx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r8
  signed int LastError; // edi
  char *v10; // rdx
  const WCHAR *v11; // rcx
  signed int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  char *v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  DWORD hTemplateFile; // [rsp+30h] [rbp-D0h]
  const WCHAR *v24; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v27; // [rsp+58h] [rbp-A8h]
  _WORD v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v30; // [rsp+78h] [rbp-88h]
  _WORD v31[8]; // [rsp+80h] [rbp-80h] BYREF
  char v32[32]; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR **v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v28;
  v28[0] = 0;
  v27 = v28;
  v31[0] = 0;
  lpString1 = v31;
  v30 = v31;
  FileW = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_69:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14007A000 <= 2 || (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
        goto LABEL_77;
      v10 = &byte_14006EE67;
LABEL_75:
      LODWORD(v24) = LastError;
      goto LABEL_76;
    }
LABEL_68:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_69;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_68;
  }
  if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v24 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14007A018,
      (__int64)byte_14006EE25,
      v5,
      v6,
      &v24);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpString1,
          szFilePath,
          v8) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      LODWORD(v24) = -2147024882;
      v10 = byte_14006EDE9;
LABEL_76:
      v34 = 4;
      v33 = &v24;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, v10, 0, 0, 3, v32);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                L"StorePath",
                (__int64)&lpFileName,
                0,
                hTemplateFile);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_14007A000 <= 2 || (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
      goto LABEL_77;
    v10 = (char *)&word_14006EDA6;
    goto LABEL_75;
  }
  v11 = lpFileName;
  if ( lpFileName == v27 || *(v27 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &lpFileName,
                             92) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v11 = lpFileName;
  }
  FileW = (char *)CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v12 = GetLastError();
    LastError = v12;
    if ( v12 > 0 )
      LastError = (unsigned __int16)v12 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_14007A000 <= 2 )
      goto LABEL_77;
    v15 = qword_14007A018;
    if ( (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
      goto LABEL_77;
    v16 = &byte_14006ED57;
    goto LABEL_33;
  }
  v17 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14007A000 <= 2 )
        goto LABEL_77;
      v15 = qword_14007A018;
      if ( (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
        goto LABEL_77;
      v16 = (char *)&unk_14006ED08;
LABEL_33:
      v25 = lpFileName;
      LODWORD(v24) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)v16,
        v13,
        v14,
        &v25,
        (__int64)&v24);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v17 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v30 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      v25 = lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14007A018,
        (__int64)word_14006ECC2,
        v13,
        v14,
        &v25);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v18,
                            v7,
                            lpFileName,
                            v27 - lpFileName) )
    {
      if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
      {
        v25 = lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v19,
          (__int64)&byte_14006EC3F,
          v20,
          v21,
          &v25);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, (__int64)&lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
      {
        LODWORD(v24) = -2147024882;
        v10 = (char *)&dword_14006EC84;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      v25 = szFilePath;
      v24 = lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_14007A018,
        (__int64)byte_14006EBEB,
        v13,
        v14,
        &v24,
        &v25);
    }
  }
LABEL_77:
  if ( lpString1 != v31 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v28 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400102c0  mov     [rsp-8+arg_10], rbx
0x1400102c5  push    rbp
0x1400102c6  push    rdi
0x1400102c7  push    r12
0x1400102c9  push    r13
0x1400102cb  push    r14
0x1400102cd  lea     rbp, [rsp-1E0h]
0x1400102d5  sub     rsp, 2E0h
0x1400102dc  mov     rax, cs:__security_cookie
0x1400102e3  xor     rax, rsp
0x1400102e6  mov     [rbp+200h+var_30], rax
0x1400102ed  xor     r13d, r13d
0x1400102f0  lea     rax, [rsp+300h+var_2A0]
0x1400102f5  mov     [rsp+300h+lpFileName], rax
0x1400102fa  mov     r12, rdx
0x1400102fd  lea     rax, [rsp+300h+var_2A0]
0x140010302  mov     [rsp+300h+var_2A0], r13w
0x140010308  mov     [rsp+300h+var_2A8], rax
0x14001030d  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x140010311  lea     rax, [rbp+200h+var_280]
0x140010315  mov     [rbp+200h+var_280], r13w
0x14001031a  mov     [rsp+300h+lpString1], rax
0x14001031f  lea     r9d, [r13+2]; dwFlags
0x140010323  lea     rax, [rbp+200h+var_280]
0x140010327  mov     edi, 104h
0x14001032c  mov     r8d, edi; cchFilePath
0x14001032f  mov     [rsp+300h+var_288], rax
0x140010334  mov     ebx, r13d
0x140010337  call    cs:__imp_GetFinalPathNameByHandleW
0x14001033d  test    eax, eax
0x14001033f  jz      loc_1400107D6
0x140010345  cmp     eax, edi
0x140010347  jnb     loc_1400107CF
0x14001034d  mov     eax, cs:dword_14007A000
0x140010353  cmp     eax, 4
0x140010356  jbe     short loc_140010394
0x140010358  mov     rcx, cs:qword_14007A018
0x14001035f  mov     rax, cs:qword_14007A010
0x140010366  test    al, 8
0x140010368  jz      short loc_140010394
0x14001036a  mov     rax, rcx
0x14001036d  and     eax, 8
0x140010370  cmp     rax, rcx
0x140010373  jnz     short loc_140010394
0x140010375  lea     rax, [rbp+200h+szFilePath]
0x140010379  mov     [rsp+300h+var_2C0], rax
0x14001037e  lea     rdx, byte_14006EE25
0x140010385  lea     rax, [rsp+300h+var_2C0]
0x14001038a  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14001038f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140010394  or      r14, 0FFFFFFFFFFFFFFFFh
0x140010398  lea     rax, [rbp+200h+szFilePath]
0x14001039c  mov     r8, r14
0x14001039f  inc     r8
0x1400103a2  cmp     [rax+r8*2], r13w
0x1400103a7  jnz     short loc_14001039F
0x1400103a9  lea     rdx, [rbp+200h+szFilePath]
0x1400103ad  lea     rcx, [rsp+300h+lpString1]
0x1400103b2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400103b7  test    al, al
0x1400103b9  jnz     short loc_140010408
0x1400103bb  mov     eax, cs:dword_14007A000
0x1400103c1  mov     edi, 8007000Eh
0x1400103c6  cmp     eax, 2
0x1400103c9  jbe     loc_14001085C
0x1400103cf  mov     rcx, cs:qword_14007A018
0x1400103d6  mov     rax, cs:qword_14007A010
0x1400103dd  test    al, 8
0x1400103df  jz      loc_14001085C
0x1400103e5  mov     rax, rcx
0x1400103e8  and     eax, 8
0x1400103eb  cmp     rax, rcx
0x1400103ee  jnz     loc_14001085C
0x1400103f4  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x1400103fc  lea     rdx, byte_14006EDE9
0x140010403  jmp     loc_140010828
0x140010408  lea     rax, [rsp+300h+lpFileName]
0x14001040d  mov     byte ptr [rsp+300h+dwFlagsAndAttributes], r13b; char
0x140010412  lea     r9, pwzValue
0x140010419  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x14001041e  lea     r8, aStorepath; "StorePath"
0x140010425  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001042c  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x140010433  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140010438  mov     edi, eax
0x14001043a  test    eax, eax
0x14001043c  jns     short loc_14001047F
0x14001043e  mov     ecx, cs:dword_14007A000
0x140010444  cmp     ecx, 2
0x140010447  jbe     loc_14001085C
0x14001044d  mov     rax, cs:qword_14007A018
0x140010454  mov     rcx, cs:qword_14007A010
0x14001045b  test    cl, 8
0x14001045e  jz      loc_14001085C
0x140010464  mov     rcx, rax
0x140010467  and     ecx, 8
0x14001046a  cmp     rcx, rax
0x14001046d  jnz     loc_14001085C
0x140010473  lea     rdx, word_14006EDA6
0x14001047a  jmp     loc_140010824
0x14001047f  mov     rcx, [rsp+300h+lpFileName]
0x140010484  mov     edx, 5Ch ; '\'
0x140010489  mov     rax, [rsp+300h+var_2A8]
0x14001048e  cmp     rcx, rax
0x140010491  jz      short loc_140010499
0x140010493  cmp     dx, [rax-2]
0x140010497  jz      short loc_1400104B6
0x140010499  lea     rcx, [rsp+300h+lpFileName]
0x14001049e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400104a3  test    al, al
0x1400104a5  jnz     short loc_1400104B1
0x1400104a7  mov     edi, 8007000Eh
0x1400104ac  jmp     loc_14001085C
0x1400104b1  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x1400104b6  xor     r9d, r9d; lpSecurityAttributes
0x1400104b9  mov     qword ptr [rsp+300h+hTemplateFile], r13; hTemplateFile
0x1400104be  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1400104c6  mov     edx, 80h; dwDesiredAccess
0x1400104cb  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x1400104d3  lea     r8d, [r9+1]; dwShareMode
0x1400104d7  call    cs:__imp_CreateFileW
0x1400104dd  mov     rbx, rax
0x1400104e0  inc     rax
0x1400104e3  cmp     rax, 1
0x1400104e7  ja      loc_140010573
0x1400104ed  call    cs:__imp_GetLastError
0x1400104f3  mov     edi, eax
0x1400104f5  test    eax, eax
0x1400104f7  jle     short loc_140010502
0x1400104f9  movzx   edi, ax
0x1400104fc  or      edi, 80070000h
0x140010502  test    edi, edi
0x140010504  mov     eax, 80004005h
0x140010509  cmovns  edi, eax
0x14001050c  mov     eax, cs:dword_14007A000
0x140010512  cmp     eax, 2
0x140010515  jbe     loc_14001085C
0x14001051b  mov     rcx, cs:qword_14007A018
0x140010522  mov     rax, cs:qword_14007A010
0x140010529  test    al, 8
0x14001052b  jz      loc_14001085C
0x140010531  mov     rax, rcx
0x140010534  and     eax, 8
0x140010537  cmp     rax, rcx
0x14001053a  jnz     loc_14001085C
0x140010540  lea     rdx, byte_14006ED57
0x140010547  mov     rax, [rsp+300h+lpFileName]
0x14001054c  mov     [rsp+300h+var_2B8], rax
0x140010551  lea     rax, [rsp+300h+var_2C0]
0x140010556  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x14001055b  lea     rax, [rsp+300h+var_2B8]
0x140010560  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010565  mov     dword ptr [rsp+300h+var_2C0], edi
0x140010569  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14001056e  jmp     loc_14001085C
0x140010573  mov     edi, 104h
0x140010578  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x14001057c  mov     r8d, edi; cchFilePath
0x14001057f  mov     r9d, 2; dwFlags
0x140010585  mov     rcx, rbx; hFile
0x140010588  call    cs:__imp_GetFinalPathNameByHandleW
0x14001058e  test    eax, eax
0x140010590  jz      loc_140010770
0x140010596  cmp     eax, edi
0x140010598  jnb     loc_140010769
0x14001059e  lea     rax, [rbp+200h+szFilePath]
0x1400105a2  inc     r14
0x1400105a5  cmp     [rax+r14*2], r13w
0x1400105aa  jnz     short loc_1400105A2
0x1400105ac  mov     rax, [rsp+300h+var_288]
0x1400105b1  mov     rcx, [rsp+300h+lpString1]; lpString1
0x1400105b6  sub     rax, rcx
0x1400105b9  sar     rax, 1
0x1400105bc  cmp     rax, r14
0x1400105bf  jb      loc_1400106F8
0x1400105c5  mov     r9d, r14d; cchCount2
0x1400105c8  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x1400105d0  lea     r8, [rbp+200h+szFilePath]; lpString2
0x1400105d4  mov     edx, r14d; cchCount1
0x1400105d7  call    cs:__imp_CompareStringOrdinal
0x1400105dd  cmp     eax, 2
0x1400105e0  jnz     loc_1400106F8
0x1400105e6  mov     eax, cs:dword_14007A000
0x1400105ec  cmp     eax, 4
0x1400105ef  jbe     short loc_14001062E
0x1400105f1  mov     rcx, cs:qword_14007A018
0x1400105f8  mov     rax, cs:qword_14007A010
0x1400105ff  test    al, 8
0x140010601  jz      short loc_14001062E
0x140010603  mov     rax, rcx
0x140010606  and     eax, 8
0x140010609  cmp     rax, rcx
0x14001060c  jnz     short loc_14001062E
0x14001060e  mov     rax, [rsp+300h+lpString1]
0x140010613  lea     rdx, word_14006ECC2
0x14001061a  mov     [rsp+300h+var_2B8], rax
0x14001061f  lea     rax, [rsp+300h+var_2B8]
0x140010624  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010629  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14001062e  mov     rax, [rsp+300h+var_2A8]
0x140010633  lea     rcx, [rsp+300h+lpString1]
0x140010638  mov     r9, [rsp+300h+lpFileName]
0x14001063d  mov     r8, r14
0x140010640  sub     rax, r9
0x140010643  sar     rax, 1
0x140010646  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14001064b  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x140010650  test    al, al
0x140010652  mov     eax, cs:dword_14007A000
0x140010658  jnz     short loc_1400106A1
0x14001065a  mov     edi, 8007000Eh
0x14001065f  cmp     eax, 2
0x140010662  jbe     loc_14001085C
0x140010668  mov     rcx, cs:qword_14007A018
0x14001066f  mov     rax, cs:qword_14007A010
0x140010676  test    al, 8
0x140010678  jz      loc_14001085C
0x14001067e  mov     rax, rcx
0x140010681  and     eax, 8
0x140010684  cmp     rax, rcx
0x140010687  jnz     loc_14001085C
0x14001068d  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x140010695  lea     rdx, dword_14006EC84
0x14001069c  jmp     loc_140010828
0x1400106a1  cmp     eax, 4
0x1400106a4  jbe     short loc_1400106E3
0x1400106a6  mov     rdx, cs:qword_14007A018
0x1400106ad  mov     rax, cs:qword_14007A010
0x1400106b4  test    al, 8
0x1400106b6  jz      short loc_1400106E3
0x1400106b8  mov     rax, rdx
0x1400106bb  and     eax, 8
0x1400106be  cmp     rax, rdx
0x1400106c1  jnz     short loc_1400106E3
0x1400106c3  mov     rax, [rsp+300h+lpString1]
0x1400106c8  lea     rdx, byte_14006EC3F
0x1400106cf  mov     [rsp+300h+var_2B8], rax
0x1400106d4  lea     rax, [rsp+300h+var_2B8]
0x1400106d9  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1400106de  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1400106e3  lea     rdx, [rsp+300h+lpString1]
0x1400106e8  mov     rcx, r12
0x1400106eb  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1400106f0  mov     edi, r13d
0x1400106f3  jmp     loc_14001085C
0x1400106f8  mov     eax, cs:dword_14007A000
0x1400106fe  mov     edi, 800700A1h
0x140010703  cmp     eax, 2
0x140010706  jbe     loc_14001085C
0x14001070c  mov     rcx, cs:qword_14007A018
0x140010713  mov     rax, cs:qword_14007A010
0x14001071a  test    al, 8
0x14001071c  jz      loc_14001085C
0x140010722  mov     rax, rcx
0x140010725  and     eax, 8
0x140010728  cmp     rax, rcx
0x14001072b  jnz     loc_14001085C
0x140010731  lea     rax, [rbp+200h+szFilePath]
0x140010735  mov     [rsp+300h+var_2B8], rax
0x14001073a  lea     rdx, byte_14006EBEB
0x140010741  mov     rax, [rsp+300h+lpString1]
0x140010746  mov     [rsp+300h+var_2C0], rax
0x14001074b  lea     rax, [rsp+300h+var_2B8]
0x140010750  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x140010755  lea     rax, [rsp+300h+var_2C0]
0x14001075a  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14001075f  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x140010764  jmp     loc_14001085C
0x140010769  mov     edi, 6Fh ; 'o'
0x14001076e  jmp     short loc_14001077C
0x140010770  call    cs:__imp_GetLastError
0x140010776  mov     edi, eax
0x140010778  test    eax, eax
0x14001077a  jle     short loc_140010785
0x14001077c  movzx   edi, di
0x14001077f  or      edi, 80070000h
0x140010785  test    edi, edi
0x140010787  mov     eax, 80004005h
0x14001078c  cmovns  edi, eax
0x14001078f  mov     eax, cs:dword_14007A000
0x140010795  cmp     eax, 2
0x140010798  jbe     loc_14001085C
0x14001079e  mov     rcx, cs:qword_14007A018
0x1400107a5  mov     rax, cs:qword_14007A010
0x1400107ac  test    al, 8
0x1400107ae  jz      loc_14001085C
0x1400107b4  mov     rax, rcx
0x1400107b7  and     eax, 8
0x1400107ba  cmp     rax, rcx
0x1400107bd  jnz     loc_14001085C
0x1400107c3  lea     rdx, unk_14006ED08
0x1400107ca  jmp     loc_140010547
0x1400107cf  mov     edi, 6Fh ; 'o'
0x1400107d4  jmp     short loc_1400107E2
0x1400107d6  call    cs:__imp_GetLastError
0x1400107dc  mov     edi, eax
0x1400107de  test    eax, eax
0x1400107e0  jle     short loc_1400107EB
0x1400107e2  movzx   edi, di
0x1400107e5  or      edi, 80070000h
  ... truncated ...
```
