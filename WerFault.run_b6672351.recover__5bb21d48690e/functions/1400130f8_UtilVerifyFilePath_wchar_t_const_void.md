# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x1400130f8`
- end: `0x140013939`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `2113`
- prototype: `int(const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400158e8`

## callees

- `0x140001150`
- `0x1400011f4`
- `0x140002490`
- `0x140002748`
- `0x140005550`
- `0x14000ca20`
- `0x14000e658`
- `0x140010594`
- `0x1400120b8`
- `0x1400130f8`
- `0x1400166ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400131ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013530`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400131ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400131ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400131c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400131c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013241`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400136e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400136e8`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14001351a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1400135f4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14001351a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1400135f4`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x1400136fc`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x1400136fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyFilePath(wchar_t *a1, void *a2, int a3, int a4)
{
  const WCHAR *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rbx
  void **v8; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  __int16 *v11; // rdx
  __int64 v12; // r15
  __int64 v13; // r8
  char v14; // di
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  unsigned __int16 v19; // cx
  const WCHAR *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD LongPathNameW; // eax
  DWORD v24; // edi
  signed int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  _WORD *v27; // rsi
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  unsigned __int16 v38; // ax
  __int64 v39; // rcx
  unsigned __int16 v40; // cx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v44; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v46; // [rsp+48h] [rbp-B8h]
  _WORD v47[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v48; // [rsp+60h] [rbp-A0h]
  char *v49; // [rsp+68h] [rbp-98h]
  _WORD v50[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v52; // [rsp+88h] [rbp-78h] BYREF
  void *v53; // [rsp+90h] [rbp-70h]
  unsigned __int16 v54; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v55; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v56; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *p_hObject; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  WCHAR szLongPath[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  const WCHAR *v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  _WORD *v64; // [rsp+110h] [rbp+10h]
  __int64 v65; // [rsp+118h] [rbp+18h]
  LPCWSTR v66; // [rsp+120h] [rbp+20h]
  __int64 v67; // [rsp+128h] [rbp+28h]
  LPCWSTR v68; // [rsp+130h] [rbp+30h]
  __int64 v69; // [rsp+138h] [rbp+38h]
  void *v70; // [rsp+140h] [rbp+40h]
  int v71; // [rsp+148h] [rbp+48h]
  int v72; // [rsp+14Ch] [rbp+4Ch]
  HANDLE *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]

  v5 = a1;
  v48 = v50;
  v49 = (char *)v50;
  v50[0] = 0;
  lpszShortPath = v47;
  v46 = v47;
  v47[0] = 0;
  if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)a1,
      (unsigned int)word_140072A12,
      a3,
      a4,
      (__int64)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( OpenProcessToken(CurrentProcess, 8u, v8) )
    {
      IsLowRightsToken = UtilIsLowRightsToken(hObject);
    }
    else
    {
      LastError = GetLastError();
      IsLowRightsToken = LastError;
      if ( LastError > 0 )
        IsLowRightsToken = (unsigned __int16)LastError | 0x80070000;
      if ( IsLowRightsToken >= 0 )
        IsLowRightsToken = -2147467259;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    if ( !IsLowRightsToken )
    {
      if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        bIgnoreCase[0] = 2;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, byte_1400729E1, 0, 0, *(_QWORD *)bIgnoreCase, &v55);
      }
      FinalPathByHandle = 0;
      goto LABEL_104;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_14007E000 <= 2 || (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
      goto LABEL_104;
    LODWORD(hObject) = FinalPathByHandle;
    v11 = (__int16 *)byte_1400729B3;
    goto LABEL_26;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v5[v13] );
  if ( !v13 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_104;
  }
  if ( v48 == v49 || (v14 = 1, *((_WORD *)v49 - 1) != 92) )
    v14 = 0;
  v15 = 2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           v5) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_14007E000 <= 2 || (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
      goto LABEL_104;
    LODWORD(hObject) = -2147024882;
    v11 = &word_14007297E;
LABEL_26:
    p_hObject = &hObject;
    bIgnoreCase[0] = 3;
    v58 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, v11, 0, 0, *(_QWORD *)bIgnoreCase, &v55);
    goto LABEL_104;
  }
  if ( v14
    && (unsigned int)dword_14007E000 > 4
    && (qword_14007E010 & 8) != 0
    && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v16 = v46 - lpszShortPath;
    if ( (unsigned __int16)v16 > 0x7FFFu )
      v17 = -2;
    else
      v17 = 2 * v16;
    v51 = (__int64)lpszShortPath;
    v52 = v17;
    v18 = (v49 - (_BYTE *)v48) >> 1;
    if ( (unsigned __int16)v18 > 0x7FFFu )
      v19 = -2;
    else
      v19 = 2 * v18;
    hObject = v48;
    v44 = v19;
    v66 = &v52;
    v67 = 2;
    v68 = lpszShortPath;
    v69 = v17;
    v62 = &v44;
    v63 = 2;
    v64 = v48;
    v65 = v19;
    if ( v5 )
    {
      v20 = v5;
      v21 = -1;
      do
        ++v21;
      while ( v5[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v20 = &pwzValue;
      v22 = 2;
    }
    v60 = (__int64 *)v20;
    v61 = v22;
    bIgnoreCase[0] = 7;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, byte_14007291D, 0, 0, *(_QWORD *)bIgnoreCase, szLongPath);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v24 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v25 = GetLastError();
    FinalPathByHandle = v25;
    if ( v25 > 0 )
      FinalPathByHandle = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v58 = 4;
      bIgnoreCase[0] = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &dword_1400728E4, 0, 0, *(_QWORD *)bIgnoreCase, &v55);
    }
    goto LABEL_73;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&hObject, LongPathNameW);
    v27 = hObject;
    if ( hObject )
    {
      if ( v24 > GetLongPathNameW(lpszShortPath, (LPWSTR)hObject, v24) )
      {
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        v26 = (const struct std::nothrow_t *)(unsigned int)-((unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                                                                &lpszShortPath,
                                                                                v27) == 0);
        FinalPathByHandle = (unsigned int)v26 & 0x8007000E;
      }
      else
      {
        FinalPathByHandle = -2147418113;
      }
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    if ( v27 )
      operator delete(v27, v26);
LABEL_73:
    if ( FinalPathByHandle < 0 )
      goto LABEL_104;
    goto LABEL_79;
  }
  v29 = -1;
  do
    ++v29;
  while ( szLongPath[v29] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_104;
  }
  FinalPathByHandle = 0;
LABEL_79:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v30 = 0, lpszShortPath[3] != 92) )
  {
    v30 = 1;
  }
  v31 = (unsigned int)(4 * v30);
  v32 = v46 - lpszShortPath;
  if ( v32 != ((v49 - (_BYTE *)v48) >> 1) - v31
    || CompareStringOrdinal(lpszShortPath, v32, (LPCWCH)v48 + v31, v32, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 && (unsigned int)dword_14007E000 > 2 )
    {
      v34 = qword_14007E018;
      v33 = 0x200000000008LL;
      if ( (qword_14007E010 & 0x200000000008LL) != 0 && (qword_14007E018 & 0x200000000008LL) == qword_14007E018 )
      {
        LODWORD(hObject) = v31;
        v37 = (v49 - (_BYTE *)v48) >> 1;
        if ( (unsigned __int16)v37 > 0x7FFFu )
          v38 = -2;
        else
          v38 = 2 * v37;
        v53 = v48;
        v54 = v38;
        v39 = v46 - lpszShortPath;
        if ( (unsigned __int16)v39 > 0x7FFFu )
          v40 = -2;
        else
          v40 = 2 * v39;
        v55 = lpszShortPath;
        v56 = v40;
        v51 = 0x1000000;
        v73 = &hObject;
        v74 = 4;
        v68 = &v54;
        v69 = 2;
        v70 = v48;
        v71 = v38;
        v72 = 0;
        v64 = &v56;
        v65 = 2;
        v66 = lpszShortPath;
        v67 = v40;
        if ( v5 )
        {
          do
            ++v12;
          while ( v5[v12] );
          v15 = 2 * v12 + 2;
        }
        else
        {
          v5 = &pwzValue;
        }
        v62 = v5;
        v63 = v15;
        v60 = &v51;
        v61 = 8;
        bIgnoreCase[0] = 9;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &unk_140072870, 0, 0, *(_QWORD *)bIgnoreCase, szLongPath);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35, v36);
    FinalPathByHandle = -2147024735;
  }
LABEL_104:
  if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v58 = 4;
    bIgnoreCase[0] = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, byte_140072843, 0, 0, *(_QWORD *)bIgnoreCase, &v55);
  }
  if ( lpszShortPath != v47 )
    operator delete((void *)lpszShortPath, (const struct std::nothrow_t *)&std::nothrow);
  if ( v48 != v50 )
    operator delete(v48, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x1400130f8  mov     [rsp-8+arg_10], rbx
0x1400130fd  push    rbp
0x1400130fe  push    rsi
0x1400130ff  push    rdi
0x140013100  push    r12
0x140013102  push    r13
0x140013104  push    r14
0x140013106  push    r15
0x140013108  lea     rbp, [rsp-1F0h]
0x140013110  sub     rsp, 2F0h
0x140013117  mov     rax, cs:__security_cookie
0x14001311e  xor     rax, rsp
0x140013121  mov     [rbp+220h+var_40], rax
0x140013128  mov     rbx, rdx
0x14001312b  mov     r14, rcx
0x14001312e  lea     rax, [rsp+320h+var_2B0]
0x140013133  mov     [rsp+320h+var_2C0], rax
0x140013138  lea     rax, [rsp+320h+var_2B0]
0x14001313d  mov     [rsp+320h+var_2B8], rax
0x140013142  xor     r12d, r12d
0x140013145  mov     [rsp+320h+var_2B0], r12w
0x14001314b  lea     rax, [rsp+320h+var_2D0]
0x140013150  mov     [rsp+320h+lpszShortPath], rax
0x140013155  lea     rax, [rsp+320h+var_2D0]
0x14001315a  mov     [rsp+320h+var_2D8], rax
0x14001315f  mov     [rsp+320h+var_2D0], r12w
0x140013165  mov     eax, cs:dword_14007E000
0x14001316b  lea     r13d, [r12+8]
0x140013170  cmp     eax, 4
0x140013173  jbe     short loc_1400131AE
0x140013175  mov     rdx, cs:qword_14007E018
0x14001317c  mov     rax, cs:qword_14007E010
0x140013183  test    r13b, al
0x140013186  jz      short loc_1400131AE
0x140013188  mov     rax, rdx
0x14001318b  and     rax, r13
0x14001318e  cmp     rax, rdx
0x140013191  jnz     short loc_1400131AE
0x140013193  mov     [rsp+320h+hObject], rcx
0x140013198  lea     rax, [rsp+320h+hObject]
0x14001319d  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x1400131a2  lea     rdx, word_140072A12
0x1400131a9  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1400131ae  lea     rdx, [rsp+320h+var_2C0]
0x1400131b3  mov     rcx, rbx; hFile
0x1400131b6  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400131bb  mov     edi, eax
0x1400131bd  cmp     eax, 80070005h
0x1400131c2  jnz     loc_1400132AC
0x1400131c8  call    cs:__imp_GetCurrentProcess
0x1400131cf  nop     dword ptr [rax+rax+00h]
0x1400131d4  mov     rbx, rax
0x1400131d7  mov     [rsp+320h+hObject], r12
0x1400131dc  lea     rcx, [rsp+320h+hObject]
0x1400131e1  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400131e6  mov     r8, rax; TokenHandle
0x1400131e9  mov     edx, r13d; DesiredAccess
0x1400131ec  mov     rcx, rbx; ProcessHandle
0x1400131ef  call    cs:__imp_OpenProcessToken
0x1400131f6  nop     dword ptr [rax+rax+00h]
0x1400131fb  test    eax, eax
0x1400131fd  jnz     short loc_140013226
0x1400131ff  call    cs:__imp_GetLastError
0x140013206  nop     dword ptr [rax+rax+00h]
0x14001320b  mov     ebx, eax
0x14001320d  test    eax, eax
0x14001320f  jle     short loc_14001321A
0x140013211  movzx   ebx, ax
0x140013214  or      ebx, 80070000h
0x14001321a  mov     eax, 80004005h
0x14001321f  test    ebx, ebx
0x140013221  cmovns  ebx, eax
0x140013224  jmp     short loc_140013232
0x140013226  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x14001322b  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x140013230  mov     ebx, eax
0x140013232  mov     rcx, [rsp+320h+hObject]; hObject
0x140013237  lea     rdx, [rcx+1]
0x14001323b  cmp     rdx, 1
0x14001323f  jbe     short loc_14001324D
0x140013241  call    cs:__imp_CloseHandle
0x140013248  nop     dword ptr [rax+rax+00h]
0x14001324d  test    ebx, ebx
0x14001324f  jnz     short loc_1400132B0
0x140013251  mov     eax, cs:dword_14007E000
0x140013257  cmp     eax, 4
0x14001325a  jbe     short loc_1400132A4
0x14001325c  mov     rcx, cs:qword_14007E018
0x140013263  mov     rax, cs:qword_14007E010
0x14001326a  test    r13b, al
0x14001326d  jz      short loc_1400132A4
0x14001326f  mov     rax, rcx
0x140013272  and     rax, r13
0x140013275  cmp     rax, rcx
0x140013278  jnz     short loc_1400132A4
0x14001327a  lea     rax, [rbp+220h+var_280]
0x14001327e  mov     [rsp+320h+var_2F8], rax
0x140013283  mov     [rsp+320h+bIgnoreCase], 2
0x14001328b  xor     r9d, r9d
0x14001328e  xor     r8d, r8d
0x140013291  lea     rdx, byte_1400729E1
0x140013298  lea     rcx, dword_14007E000
0x14001329f  call    _tlgWriteTransfer_EventWriteTransfer
0x1400132a4  mov     edi, r12d
0x1400132a7  jmp     loc_14001386C
0x1400132ac  test    edi, edi
0x1400132ae  jns     short loc_14001332D
0x1400132b0  mov     eax, cs:dword_14007E000
0x1400132b6  mov     ebx, 2
0x1400132bb  cmp     eax, ebx
0x1400132bd  jbe     loc_14001386C
0x1400132c3  mov     rcx, cs:qword_14007E018
0x1400132ca  mov     rax, cs:qword_14007E010
0x1400132d1  test    r13b, al
0x1400132d4  jz      loc_14001386C
0x1400132da  mov     rax, rcx
0x1400132dd  and     rax, r13
0x1400132e0  cmp     rax, rcx
0x1400132e3  jnz     loc_14001386C
0x1400132e9  mov     dword ptr [rsp+320h+hObject], edi
0x1400132ed  lea     rdx, byte_1400729B3
0x1400132f4  lea     rax, [rsp+320h+hObject]
0x1400132f9  mov     [rbp+220h+var_260], rax
0x1400132fd  lea     rax, [rbp+220h+var_280]
0x140013301  xor     r9d, r9d
0x140013304  mov     [rsp+320h+var_2F8], rax
0x140013309  xor     r8d, r8d
0x14001330c  mov     [rsp+320h+bIgnoreCase], 3
0x140013314  mov     [rbp+220h+var_258], 4
0x14001331c  lea     rcx, dword_14007E000
0x140013323  call    _tlgWriteTransfer_EventWriteTransfer
0x140013328  jmp     loc_14001386C
0x14001332d  or      r15, 0FFFFFFFFFFFFFFFFh
0x140013331  mov     r8, r15
0x140013334  inc     r8
0x140013337  cmp     [r14+r8*2], r12w
0x14001333c  jnz     short loc_140013334
0x14001333e  cmp     r8, 1
0x140013342  jnb     short loc_14001334E
0x140013344  mov     edi, 80070057h
0x140013349  jmp     loc_14001386C
0x14001334e  mov     ecx, 5Ch ; '\'
0x140013353  mov     rax, [rsp+320h+var_2B8]
0x140013358  cmp     [rsp+320h+var_2C0], rax
0x14001335d  jz      short loc_140013368
0x14001335f  cmp     cx, [rax-2]
0x140013363  mov     dil, 1
0x140013366  jz      short loc_14001336B
0x140013368  mov     dil, r12b
0x14001336b  cmp     [r14+r8*2-2], cx
0x140013371  jnz     short loc_14001337B
0x140013373  test    dil, dil
0x140013376  jnz     short loc_14001337B
0x140013378  dec     r8
0x14001337b  mov     rdx, r14
0x14001337e  lea     rcx, [rsp+320h+lpszShortPath]
0x140013383  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140013388  mov     ebx, 2
0x14001338d  test    al, al
0x14001338f  jnz     short loc_1400133DE
0x140013391  mov     edi, 8007000Eh
0x140013396  mov     eax, cs:dword_14007E000
0x14001339c  cmp     eax, ebx
0x14001339e  jbe     loc_14001386C
0x1400133a4  mov     rcx, cs:qword_14007E018
0x1400133ab  mov     rax, cs:qword_14007E010
0x1400133b2  test    r13b, al
0x1400133b5  jz      loc_14001386C
0x1400133bb  mov     rax, rcx
0x1400133be  and     rax, r13
0x1400133c1  cmp     rax, rcx
0x1400133c4  jnz     loc_14001386C
0x1400133ca  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x1400133d2  lea     rdx, word_14007297E
0x1400133d9  jmp     loc_1400132F4
0x1400133de  mov     r10d, 7FFFh
0x1400133e4  mov     r9d, 0FFFEh
0x1400133ea  test    dil, dil
0x1400133ed  jz      loc_140013509
0x1400133f3  mov     eax, cs:dword_14007E000
0x1400133f9  cmp     eax, 4
0x1400133fc  jbe     loc_140013509
0x140013402  mov     rcx, cs:qword_14007E018
0x140013409  mov     rax, cs:qword_14007E010
0x140013410  test    r13b, al
0x140013413  jz      loc_140013509
0x140013419  mov     rax, rcx
0x14001341c  and     rax, r13
0x14001341f  cmp     rax, rcx
0x140013422  jnz     loc_140013509
0x140013428  mov     rax, [rsp+320h+var_2D8]
0x14001342d  mov     r8, [rsp+320h+lpszShortPath]
0x140013432  sub     rax, r8
0x140013435  sar     rax, 1
0x140013438  cmp     ax, r10w
0x14001343c  ja      short loc_140013443
0x14001343e  add     ax, ax
0x140013441  jmp     short loc_140013447
0x140013443  movzx   eax, r9w
0x140013447  mov     [rbp+220h+var_2A0], r8
0x14001344b  mov     [rbp+220h+var_298], ax
0x14001344f  mov     rcx, [rsp+320h+var_2B8]
0x140013454  mov     rdx, [rsp+320h+var_2C0]
0x140013459  sub     rcx, rdx
0x14001345c  sar     rcx, 1
0x14001345f  cmp     cx, r10w
0x140013463  ja      short loc_14001346A
0x140013465  add     cx, cx
0x140013468  jmp     short loc_14001346E
0x14001346a  movzx   ecx, r9w
0x14001346e  mov     [rsp+320h+hObject], rdx
0x140013473  mov     [rsp+320h+var_2E8], cx
0x140013478  lea     r9, [rbp+220h+var_298]
0x14001347c  mov     [rbp+220h+var_200], r9
0x140013480  mov     [rbp+220h+var_1F8], rbx
0x140013484  mov     [rbp+220h+var_1F0], r8
0x140013488  movzx   eax, ax
0x14001348b  mov     dword ptr [rbp+220h+var_1E8], eax
0x14001348e  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x140013492  lea     rax, [rsp+320h+var_2E8]
0x140013497  mov     [rbp+220h+var_220], rax
0x14001349b  mov     [rbp+220h+var_218], rbx
0x14001349f  mov     [rbp+220h+var_210], rdx
0x1400134a3  movzx   eax, cx
0x1400134a6  mov     dword ptr [rbp+220h+var_208], eax
0x1400134a9  mov     dword ptr [rbp+220h+var_208+4], r12d
0x1400134ad  test    r14, r14
0x1400134b0  jz      short loc_1400134CB
0x1400134b2  mov     rcx, r14
0x1400134b5  mov     rax, r15
0x1400134b8  inc     rax
0x1400134bb  cmp     [r14+rax*2], r12w
0x1400134c0  jnz     short loc_1400134B8
0x1400134c2  lea     eax, ds:2[rax*2]
0x1400134c9  jmp     short loc_1400134D4
0x1400134cb  lea     rcx, pwzValue
0x1400134d2  mov     eax, ebx
0x1400134d4  mov     [rbp+220h+var_230], rcx
0x1400134d8  mov     dword ptr [rbp+220h+var_228], eax
0x1400134db  mov     dword ptr [rbp+220h+var_228+4], r12d
0x1400134df  lea     rax, [rbp+220h+szLongPath]
0x1400134e3  mov     [rsp+320h+var_2F8], rax
0x1400134e8  mov     [rsp+320h+bIgnoreCase], 7
0x1400134f0  xor     r9d, r9d
0x1400134f3  xor     r8d, r8d
0x1400134f6  lea     rdx, byte_14007291D
0x1400134fd  lea     rcx, dword_14007E000
0x140013504  call    _tlgWriteTransfer_EventWriteTransfer
0x140013509  mov     esi, 105h
0x14001350e  mov     r8d, esi; cchBuffer
0x140013511  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x140013515  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x14001351a  call    cs:__imp_GetLongPathNameW
0x140013521  nop     dword ptr [rax+rax+00h]
0x140013526  mov     edi, eax
0x140013528  test    eax, eax
0x14001352a  jnz     loc_1400135C3
0x140013530  call    cs:__imp_GetLastError
0x140013537  nop     dword ptr [rax+rax+00h]
0x14001353c  mov     edi, eax
0x14001353e  test    eax, eax
0x140013540  jle     short loc_14001354B
0x140013542  movzx   edi, ax
0x140013545  or      edi, 80070000h
0x14001354b  mov     eax, cs:dword_14007E000
0x140013551  cmp     eax, ebx
0x140013553  jbe     loc_140013649
0x140013559  mov     rcx, cs:qword_14007E018
0x140013560  mov     rax, cs:qword_14007E010
0x140013567  test    r13b, al
0x14001356a  jz      loc_140013649
0x140013570  mov     rax, rcx
0x140013573  and     rax, r13
0x140013576  cmp     rax, rcx
0x140013579  jnz     loc_140013649
0x14001357f  mov     dword ptr [rsp+320h+hObject], edi
0x140013583  lea     rax, [rsp+320h+hObject]
0x140013588  mov     [rbp+220h+var_260], rax
0x14001358c  mov     [rbp+220h+var_258], 4
0x140013594  lea     rax, [rbp+220h+var_280]
0x140013598  mov     [rsp+320h+var_2F8], rax
0x14001359d  mov     [rsp+320h+bIgnoreCase], 3
0x1400135a5  xor     r9d, r9d
0x1400135a8  xor     r8d, r8d
0x1400135ab  lea     rdx, dword_1400728E4
0x1400135b2  lea     rcx, dword_14007E000
0x1400135b9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400135be  jmp     loc_140013649
0x1400135c3  cmp     edi, esi
0x1400135c5  jbe     loc_140013653
0x1400135cb  mov     rdx, rdi
0x1400135ce  lea     rcx, [rsp+320h+hObject]
0x1400135d3  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1400135d8  mov     rsi, [rsp+320h+hObject]
0x1400135dd  test    rsi, rsi
0x1400135e0  jnz     short loc_1400135E9
0x1400135e2  mov     edi, 8007000Eh
0x1400135e7  jmp     short loc_14001363C
0x1400135e9  mov     r8d, edi; cchBuffer
0x1400135ec  mov     rdx, rsi; lpszLongPath
  ... truncated ...
```
