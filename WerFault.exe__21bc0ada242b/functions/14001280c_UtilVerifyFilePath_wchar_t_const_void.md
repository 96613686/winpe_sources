# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x14001280c`
- end: `0x140013016`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `2058`
- prototype: `int(const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014ddc`

## callees

- `0x14000113c`
- `0x1400011dc`
- `0x140002470`
- `0x140002728`
- `0x140005498`
- `0x14000c8a0`
- `0x14000e3c4`
- `0x14000ff08`
- `0x1400118fc`
- `0x14001280c`
- `0x140015b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012c26`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400128fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400128fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400128dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400128dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012943`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140012dd2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140012dd2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140012c16`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140012ce4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140012c16`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x140012ce4`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140012de0`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140012de0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyFilePath(wchar_t *a1, void *a2, __int64 a3, __int64 a4)
{
  const WCHAR *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rbx
  void **v8; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  __int16 *v11; // rdx
  __int64 v12; // r15
  unsigned __int64 v13; // r8
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
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // r8
  LPCWSTR v30; // rcx
  int v31; // eax
  __int64 v32; // rsi
  __int64 v33; // r8
  __int64 v34; // rdx
  void *v35; // r9
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned __int16 v38; // ax
  __int64 v39; // rcx
  unsigned __int16 v40; // cx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v43; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v45; // [rsp+48h] [rbp-B8h]
  _WORD v46[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v47; // [rsp+60h] [rbp-A0h]
  char *v48; // [rsp+68h] [rbp-98h]
  _WORD v49[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v51; // [rsp+88h] [rbp-78h] BYREF
  void *v52; // [rsp+90h] [rbp-70h]
  unsigned __int16 v53; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v54; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v55; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *p_hObject; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  WCHAR szLongPath[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  const WCHAR *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  _WORD *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  LPCWSTR v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  LPCWSTR v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  void *v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+14Ch] [rbp+4Ch]
  HANDLE *v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]

  v5 = a1;
  v47 = v49;
  v48 = (char *)v49;
  v49[0] = 0;
  lpszShortPath = v46;
  v45 = v46;
  v46[0] = 0;
  if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)a1,
      (__int64)word_14006EA7A,
      a3,
      a4,
      (const WCHAR **)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = tlx::replace<tlx::file_handle_traits>(&hObject);
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
      if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
        tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, byte_14006EA49, 0, 0, 2, &v54);
      FinalPathByHandle = 0;
      goto LABEL_109;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_14007A000 <= 2 || (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
      goto LABEL_109;
    LODWORD(hObject) = FinalPathByHandle;
    v11 = (__int16 *)byte_14006EA1B;
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
    goto LABEL_109;
  }
  if ( v47 == v48 || (v14 = 1, *((_WORD *)v48 - 1) != 92) )
    v14 = 0;
  if ( v5[v13 - 1] == 92 && !v14 )
    --v13;
  v15 = 2;
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpszShortPath,
          v5,
          v13) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_14007A000 <= 2 || (qword_14007A010 & 8) == 0 || (qword_14007A018 & 8) != qword_14007A018 )
      goto LABEL_109;
    LODWORD(hObject) = -2147024882;
    v11 = &word_14006E9E6;
LABEL_26:
    p_hObject = &hObject;
    v57 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, v11, 0, 0, 3, &v54);
    goto LABEL_109;
  }
  if ( v14
    && (unsigned int)dword_14007A000 > 4
    && (qword_14007A010 & 8) != 0
    && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v16 = v45 - lpszShortPath;
    if ( (unsigned __int16)v16 > 0x7FFFu )
      v17 = -2;
    else
      v17 = 2 * v16;
    v50 = (__int64)lpszShortPath;
    v51 = v17;
    v18 = (v48 - (_BYTE *)v47) >> 1;
    if ( (unsigned __int16)v18 > 0x7FFFu )
      v19 = -2;
    else
      v19 = 2 * v18;
    hObject = v47;
    v43 = v19;
    v65 = &v51;
    v66 = 2;
    v67 = lpszShortPath;
    v68 = v17;
    v61 = &v43;
    v62 = 2;
    v63 = v47;
    v64 = v19;
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
    v59 = (__int64 *)v20;
    v60 = v22;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, byte_14006E985, 0, 0, 7, szLongPath);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v24 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v25 = GetLastError();
    FinalPathByHandle = v25;
    if ( v25 > 0 )
      FinalPathByHandle = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v57 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &dword_14006E94C, 0, 0, 3, &v54);
    }
    goto LABEL_78;
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
        else
        {
          v28 = 0;
        }
        v26 = (const struct std::nothrow_t *)(unsigned int)-(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                                               (__int64)&lpszShortPath,
                                                               v27,
                                                               v28) == 0);
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
LABEL_78:
    if ( FinalPathByHandle < 0 )
      goto LABEL_109;
    goto LABEL_84;
  }
  v29 = -1;
  do
    ++v29;
  while ( szLongPath[v29] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpszShortPath,
          szLongPath,
          v29) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_109;
  }
  FinalPathByHandle = 0;
LABEL_84:
  v30 = lpszShortPath;
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v31 = 0, lpszShortPath[3] != 92) )
  {
    v31 = 1;
  }
  v32 = (unsigned int)(4 * v31);
  v33 = v32;
  v34 = v45 - lpszShortPath;
  v35 = v47;
  if ( v34 != ((v48 - (_BYTE *)v47) >> 1) - v32
    || CompareStringOrdinal(lpszShortPath, v34, (LPCWCH)v47 + v32, v34, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode(v30, v34, v33, v35) == 3 && (unsigned int)dword_14007A000 > 2 )
    {
      v36 = qword_14007A018;
      if ( (qword_14007A010 & 0x200000000008LL) != 0 && (qword_14007A018 & 0x200000000008LL) == qword_14007A018 )
      {
        LODWORD(hObject) = v32;
        v37 = (v48 - (_BYTE *)v47) >> 1;
        if ( (unsigned __int16)v37 > 0x7FFFu )
          v38 = -2;
        else
          v38 = 2 * v37;
        v52 = v47;
        v53 = v38;
        v39 = v45 - lpszShortPath;
        if ( (unsigned __int16)v39 > 0x7FFFu )
          v40 = -2;
        else
          v40 = 2 * v39;
        v54 = lpszShortPath;
        v55 = v40;
        v50 = 0x1000000;
        v72 = &hObject;
        v73 = 4;
        v67 = &v53;
        v68 = 2;
        v69 = v47;
        v70 = v38;
        v71 = 0;
        v63 = &v55;
        v64 = 2;
        v65 = lpszShortPath;
        v66 = v40;
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
        v61 = v5;
        v62 = v15;
        v59 = &v50;
        v60 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &unk_14006E8D8, 0, 0, 9, szLongPath);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v36);
    FinalPathByHandle = -2147024735;
  }
LABEL_109:
  if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v57 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, byte_14006E8AB, 0, 0, 3, &v54);
  }
  if ( lpszShortPath != v46 )
    operator delete((void *)lpszShortPath, (const struct std::nothrow_t *)&std::nothrow);
  if ( v47 != v49 )
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x14001280c  mov     [rsp-8+arg_10], rbx
0x140012811  push    rbp
0x140012812  push    rsi
0x140012813  push    rdi
0x140012814  push    r12
0x140012816  push    r13
0x140012818  push    r14
0x14001281a  push    r15
0x14001281c  lea     rbp, [rsp-1F0h]
0x140012824  sub     rsp, 2F0h
0x14001282b  mov     rax, cs:__security_cookie
0x140012832  xor     rax, rsp
0x140012835  mov     [rbp+220h+var_40], rax
0x14001283c  mov     rbx, rdx
0x14001283f  mov     r14, rcx
0x140012842  lea     rax, [rsp+320h+var_2B0]
0x140012847  mov     [rsp+320h+var_2C0], rax
0x14001284c  lea     rax, [rsp+320h+var_2B0]
0x140012851  mov     [rsp+320h+var_2B8], rax
0x140012856  xor     r12d, r12d
0x140012859  mov     [rsp+320h+var_2B0], r12w
0x14001285f  lea     rax, [rsp+320h+var_2D0]
0x140012864  mov     [rsp+320h+lpszShortPath], rax
0x140012869  lea     rax, [rsp+320h+var_2D0]
0x14001286e  mov     [rsp+320h+var_2D8], rax
0x140012873  mov     [rsp+320h+var_2D0], r12w
0x140012879  mov     eax, cs:dword_14007A000
0x14001287f  lea     r13d, [r12+8]
0x140012884  cmp     eax, 4
0x140012887  jbe     short loc_1400128C2
0x140012889  mov     rdx, cs:qword_14007A018
0x140012890  mov     rax, cs:qword_14007A010
0x140012897  test    r13b, al
0x14001289a  jz      short loc_1400128C2
0x14001289c  mov     rax, rdx
0x14001289f  and     rax, r13
0x1400128a2  cmp     rax, rdx
0x1400128a5  jnz     short loc_1400128C2
0x1400128a7  mov     [rsp+320h+hObject], rcx
0x1400128ac  lea     rax, [rsp+320h+hObject]
0x1400128b1  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x1400128b6  lea     rdx, word_14006EA7A
0x1400128bd  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1400128c2  lea     rdx, [rsp+320h+var_2C0]
0x1400128c7  mov     rcx, rbx; hFile
0x1400128ca  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400128cf  mov     edi, eax
0x1400128d1  cmp     eax, 80070005h
0x1400128d6  jnz     loc_1400129A8
0x1400128dc  call    cs:__imp_GetCurrentProcess
0x1400128e2  mov     rbx, rax
0x1400128e5  mov     [rsp+320h+hObject], r12
0x1400128ea  lea     rcx, [rsp+320h+hObject]
0x1400128ef  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400128f4  mov     r8, rax; TokenHandle
0x1400128f7  mov     edx, r13d; DesiredAccess
0x1400128fa  mov     rcx, rbx; ProcessHandle
0x1400128fd  call    cs:__imp_OpenProcessToken
0x140012903  test    eax, eax
0x140012905  jnz     short loc_140012928
0x140012907  call    cs:__imp_GetLastError
0x14001290d  mov     ebx, eax
0x14001290f  test    eax, eax
0x140012911  jle     short loc_14001291C
0x140012913  movzx   ebx, ax
0x140012916  or      ebx, 80070000h
0x14001291c  mov     eax, 80004005h
0x140012921  test    ebx, ebx
0x140012923  cmovns  ebx, eax
0x140012926  jmp     short loc_140012934
0x140012928  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x14001292d  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x140012932  mov     ebx, eax
0x140012934  mov     rcx, [rsp+320h+hObject]; hObject
0x140012939  lea     rdx, [rcx+1]
0x14001293d  cmp     rdx, 1
0x140012941  jbe     short loc_140012949
0x140012943  call    cs:__imp_CloseHandle
0x140012949  test    ebx, ebx
0x14001294b  jnz     short loc_1400129AC
0x14001294d  mov     eax, cs:dword_14007A000
0x140012953  cmp     eax, 4
0x140012956  jbe     short loc_1400129A0
0x140012958  mov     rcx, cs:qword_14007A018
0x14001295f  mov     rax, cs:qword_14007A010
0x140012966  test    r13b, al
0x140012969  jz      short loc_1400129A0
0x14001296b  mov     rax, rcx
0x14001296e  and     rax, r13
0x140012971  cmp     rax, rcx
0x140012974  jnz     short loc_1400129A0
0x140012976  lea     rax, [rbp+220h+var_280]
0x14001297a  mov     [rsp+320h+var_2F8], rax
0x14001297f  mov     [rsp+320h+bIgnoreCase], 2
0x140012987  xor     r9d, r9d
0x14001298a  xor     r8d, r8d
0x14001298d  lea     rdx, byte_14006EA49
0x140012994  lea     rcx, dword_14007A000
0x14001299b  call    _tlgWriteTransfer_EventWriteTransfer
0x1400129a0  mov     edi, r12d
0x1400129a3  jmp     loc_140012F4A
0x1400129a8  test    edi, edi
0x1400129aa  jns     short loc_140012A29
0x1400129ac  mov     eax, cs:dword_14007A000
0x1400129b2  mov     ebx, 2
0x1400129b7  cmp     eax, ebx
0x1400129b9  jbe     loc_140012F4A
0x1400129bf  mov     rcx, cs:qword_14007A018
0x1400129c6  mov     rax, cs:qword_14007A010
0x1400129cd  test    r13b, al
0x1400129d0  jz      loc_140012F4A
0x1400129d6  mov     rax, rcx
0x1400129d9  and     rax, r13
0x1400129dc  cmp     rax, rcx
0x1400129df  jnz     loc_140012F4A
0x1400129e5  mov     dword ptr [rsp+320h+hObject], edi
0x1400129e9  lea     rdx, byte_14006EA1B
0x1400129f0  lea     rax, [rsp+320h+hObject]
0x1400129f5  mov     [rbp+220h+var_260], rax
0x1400129f9  lea     rax, [rbp+220h+var_280]
0x1400129fd  xor     r9d, r9d
0x140012a00  mov     [rsp+320h+var_2F8], rax
0x140012a05  xor     r8d, r8d
0x140012a08  mov     [rsp+320h+bIgnoreCase], 3
0x140012a10  mov     [rbp+220h+var_258], 4
0x140012a18  lea     rcx, dword_14007A000
0x140012a1f  call    _tlgWriteTransfer_EventWriteTransfer
0x140012a24  jmp     loc_140012F4A
0x140012a29  or      r15, 0FFFFFFFFFFFFFFFFh
0x140012a2d  mov     r8, r15
0x140012a30  inc     r8
0x140012a33  cmp     [r14+r8*2], r12w
0x140012a38  jnz     short loc_140012A30
0x140012a3a  cmp     r8, 1
0x140012a3e  jnb     short loc_140012A4A
0x140012a40  mov     edi, 80070057h
0x140012a45  jmp     loc_140012F4A
0x140012a4a  mov     ecx, 5Ch ; '\'
0x140012a4f  mov     rax, [rsp+320h+var_2B8]
0x140012a54  cmp     [rsp+320h+var_2C0], rax
0x140012a59  jz      short loc_140012A64
0x140012a5b  cmp     cx, [rax-2]
0x140012a5f  mov     dil, 1
0x140012a62  jz      short loc_140012A67
0x140012a64  mov     dil, r12b
0x140012a67  cmp     [r14+r8*2-2], cx
0x140012a6d  jnz     short loc_140012A77
0x140012a6f  test    dil, dil
0x140012a72  jnz     short loc_140012A77
0x140012a74  dec     r8
0x140012a77  mov     rdx, r14
0x140012a7a  lea     rcx, [rsp+320h+lpszShortPath]
0x140012a7f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140012a84  mov     ebx, 2
0x140012a89  test    al, al
0x140012a8b  jnz     short loc_140012ADA
0x140012a8d  mov     edi, 8007000Eh
0x140012a92  mov     eax, cs:dword_14007A000
0x140012a98  cmp     eax, ebx
0x140012a9a  jbe     loc_140012F4A
0x140012aa0  mov     rcx, cs:qword_14007A018
0x140012aa7  mov     rax, cs:qword_14007A010
0x140012aae  test    r13b, al
0x140012ab1  jz      loc_140012F4A
0x140012ab7  mov     rax, rcx
0x140012aba  and     rax, r13
0x140012abd  cmp     rax, rcx
0x140012ac0  jnz     loc_140012F4A
0x140012ac6  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x140012ace  lea     rdx, word_14006E9E6
0x140012ad5  jmp     loc_1400129F0
0x140012ada  mov     r10d, 7FFFh
0x140012ae0  mov     r9d, 0FFFEh
0x140012ae6  test    dil, dil
0x140012ae9  jz      loc_140012C05
0x140012aef  mov     eax, cs:dword_14007A000
0x140012af5  cmp     eax, 4
0x140012af8  jbe     loc_140012C05
0x140012afe  mov     rcx, cs:qword_14007A018
0x140012b05  mov     rax, cs:qword_14007A010
0x140012b0c  test    r13b, al
0x140012b0f  jz      loc_140012C05
0x140012b15  mov     rax, rcx
0x140012b18  and     rax, r13
0x140012b1b  cmp     rax, rcx
0x140012b1e  jnz     loc_140012C05
0x140012b24  mov     rax, [rsp+320h+var_2D8]
0x140012b29  mov     r8, [rsp+320h+lpszShortPath]
0x140012b2e  sub     rax, r8
0x140012b31  sar     rax, 1
0x140012b34  cmp     ax, r10w
0x140012b38  ja      short loc_140012B3F
0x140012b3a  add     ax, ax
0x140012b3d  jmp     short loc_140012B43
0x140012b3f  movzx   eax, r9w
0x140012b43  mov     [rbp+220h+var_2A0], r8
0x140012b47  mov     [rbp+220h+var_298], ax
0x140012b4b  mov     rcx, [rsp+320h+var_2B8]
0x140012b50  mov     rdx, [rsp+320h+var_2C0]
0x140012b55  sub     rcx, rdx
0x140012b58  sar     rcx, 1
0x140012b5b  cmp     cx, r10w
0x140012b5f  ja      short loc_140012B66
0x140012b61  add     cx, cx
0x140012b64  jmp     short loc_140012B6A
0x140012b66  movzx   ecx, r9w
0x140012b6a  mov     [rsp+320h+hObject], rdx
0x140012b6f  mov     [rsp+320h+var_2E8], cx
0x140012b74  lea     r9, [rbp+220h+var_298]
0x140012b78  mov     [rbp+220h+var_200], r9
0x140012b7c  mov     [rbp+220h+var_1F8], rbx
0x140012b80  mov     [rbp+220h+var_1F0], r8
0x140012b84  movzx   eax, ax
0x140012b87  mov     dword ptr [rbp+220h+var_1E8], eax
0x140012b8a  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x140012b8e  lea     rax, [rsp+320h+var_2E8]
0x140012b93  mov     [rbp+220h+var_220], rax
0x140012b97  mov     [rbp+220h+var_218], rbx
0x140012b9b  mov     [rbp+220h+var_210], rdx
0x140012b9f  movzx   eax, cx
0x140012ba2  mov     dword ptr [rbp+220h+var_208], eax
0x140012ba5  mov     dword ptr [rbp+220h+var_208+4], r12d
0x140012ba9  test    r14, r14
0x140012bac  jz      short loc_140012BC7
0x140012bae  mov     rcx, r14
0x140012bb1  mov     rax, r15
0x140012bb4  inc     rax
0x140012bb7  cmp     [r14+rax*2], r12w
0x140012bbc  jnz     short loc_140012BB4
0x140012bbe  lea     eax, ds:2[rax*2]
0x140012bc5  jmp     short loc_140012BD0
0x140012bc7  lea     rcx, pwzValue
0x140012bce  mov     eax, ebx
0x140012bd0  mov     [rbp+220h+var_230], rcx
0x140012bd4  mov     dword ptr [rbp+220h+var_228], eax
0x140012bd7  mov     dword ptr [rbp+220h+var_228+4], r12d
0x140012bdb  lea     rax, [rbp+220h+szLongPath]
0x140012bdf  mov     [rsp+320h+var_2F8], rax
0x140012be4  mov     [rsp+320h+bIgnoreCase], 7
0x140012bec  xor     r9d, r9d
0x140012bef  xor     r8d, r8d
0x140012bf2  lea     rdx, byte_14006E985
0x140012bf9  lea     rcx, dword_14007A000
0x140012c00  call    _tlgWriteTransfer_EventWriteTransfer
0x140012c05  mov     esi, 105h
0x140012c0a  mov     r8d, esi; cchBuffer
0x140012c0d  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x140012c11  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x140012c16  call    cs:__imp_GetLongPathNameW
0x140012c1c  mov     edi, eax
0x140012c1e  test    eax, eax
0x140012c20  jnz     loc_140012CB3
0x140012c26  call    cs:__imp_GetLastError
0x140012c2c  mov     edi, eax
0x140012c2e  test    eax, eax
0x140012c30  jle     short loc_140012C3B
0x140012c32  movzx   edi, ax
0x140012c35  or      edi, 80070000h
0x140012c3b  mov     eax, cs:dword_14007A000
0x140012c41  cmp     eax, ebx
0x140012c43  jbe     loc_140012D33
0x140012c49  mov     rcx, cs:qword_14007A018
0x140012c50  mov     rax, cs:qword_14007A010
0x140012c57  test    r13b, al
0x140012c5a  jz      loc_140012D33
0x140012c60  mov     rax, rcx
0x140012c63  and     rax, r13
0x140012c66  cmp     rax, rcx
0x140012c69  jnz     loc_140012D33
0x140012c6f  mov     dword ptr [rsp+320h+hObject], edi
0x140012c73  lea     rax, [rsp+320h+hObject]
0x140012c78  mov     [rbp+220h+var_260], rax
0x140012c7c  mov     [rbp+220h+var_258], 4
0x140012c84  lea     rax, [rbp+220h+var_280]
0x140012c88  mov     [rsp+320h+var_2F8], rax
0x140012c8d  mov     [rsp+320h+bIgnoreCase], 3
0x140012c95  xor     r9d, r9d
0x140012c98  xor     r8d, r8d
0x140012c9b  lea     rdx, dword_14006E94C
0x140012ca2  lea     rcx, dword_14007A000
0x140012ca9  call    _tlgWriteTransfer_EventWriteTransfer
0x140012cae  jmp     loc_140012D33
0x140012cb3  cmp     edi, esi
0x140012cb5  jbe     loc_140012D3D
0x140012cbb  mov     rdx, rdi
0x140012cbe  lea     rcx, [rsp+320h+hObject]
0x140012cc3  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140012cc8  mov     rsi, [rsp+320h+hObject]
0x140012ccd  test    rsi, rsi
0x140012cd0  jnz     short loc_140012CD9
0x140012cd2  mov     edi, 8007000Eh
0x140012cd7  jmp     short loc_140012D26
0x140012cd9  mov     r8d, edi; cchBuffer
0x140012cdc  mov     rdx, rsi; lpszLongPath
0x140012cdf  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x140012ce4  call    cs:__imp_GetLongPathNameW
0x140012cea  cmp     edi, eax
0x140012cec  ja      short loc_140012CF5
0x140012cee  mov     edi, 8000FFFFh
0x140012cf3  jmp     short loc_140012D26
  ... truncated ...
```
