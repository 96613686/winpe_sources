# CReaderDriver::SyncIoControl(ulong,void *,ulong,void *,ulong,ulong *,int)

- ea: `0x180012aa0`
- end: `0x180013645`
- name: `?SyncIoControl@CReaderDriver@@IEAAKKPEAXK0KPEAKH@Z`
- size: `2981`
- prototype: `__int64 __fastcall(CReaderDriver *this, unsigned int, char *, DWORD, void *, DWORD nOutBufferSize, unsigned int *lpBytesReturned, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180012a30`

## callees

- `0x1800023d0`
- `0x18000c870`
- `0x180012aa0`
- `0x18001364c`
- `0x1800143c0`
- `0x180019bc4`
- `0x180027708`
- `0x1800277fc`
- `0x180029b78`
- `0x180029dd4`
- `0x1800326d0`

## import_xrefs

- `msvcrt!_ultow` at `0x180013310`
- `msvcrt!_ultow` at `0x180013310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001309b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001309b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fd7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001308d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001308d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d03`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180013505`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180013505`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012e4a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012e4a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012f2d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012f2d`
- `ADVAPI32!ReportEventW` at `0x1800135cd`
- `ADVAPI32!ReportEventW` at `0x1800135cd`
- `ADVAPI32!RegisterEventSourceW` at `0x180013589`
- `ADVAPI32!RegisterEventSourceW` at `0x180013589`

## string_xrefs

- `0x180013472`: `SET_PROTOCOL`

## pseudocode

```c
__int64 __fastcall CReaderDriver::SyncIoControl(
        CReaderDriver *this,
        unsigned int a2,
        char *a3,
        DWORD a4,
        void *a5,
        DWORD nOutBufferSize,
        unsigned int *lpBytesReturned,
        int a8)
{
  unsigned int v10; // esi
  CReaderDriver *v11; // r12
  wchar_t *v12; // r14
  __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rcx
  unsigned __int16 *v16; // r9
  wchar_t v17; // dx
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  HANDLE *v21; // rdi
  char *v22; // rcx
  DWORD v23; // ebx
  const wchar_t *v24; // rsi
  const WCHAR *v25; // r15
  int v26; // eax
  WORD i; // di
  HANDLE v28; // rax
  __int64 v29; // rax
  const wchar_t *v30; // r8
  wchar_t v31; // dx
  __int64 v32; // rax
  const wchar_t *v33; // r8
  __int64 v34; // rcx
  unsigned __int16 *v35; // rdx
  wchar_t v36; // r9
  unsigned __int16 *v37; // rax
  char *v38; // rax
  DWORD v39; // eax
  struct _OVERLAPPED *v40; // r14
  DWORD LastError; // eax
  int v43; // r12d
  CReaderDriver *v44; // rax
  const unsigned __int16 *v45; // r9
  HANDLE v46; // rax
  unsigned __int64 v47; // r15
  HANDLE ProcessHeap; // rax
  const wchar_t *v49; // rcx
  wchar_t *v50; // rbx
  size_t v51; // r8
  size_t v52; // rdx
  size_t *v53; // r8
  DWORD v54; // edi
  unsigned __int64 v55; // rsi
  HANDLE v56; // rax
  wchar_t v57; // r9
  const wchar_t *v58; // r8
  unsigned __int16 *v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rcx
  wchar_t v62; // r9
  const wchar_t *v63; // r8
  __int64 v64; // rax
  wchar_t v65; // r9
  const wchar_t *v66; // r8
  __int64 v67; // rax
  wchar_t v68; // r9
  const wchar_t *v69; // r8
  __int64 v70; // rax
  unsigned __int16 v71; // r9
  const unsigned __int16 *v72; // r8
  __int64 v73; // rax
  wchar_t v74; // r9
  const wchar_t *v75; // r8
  __int64 v76; // rax
  wchar_t v77; // r9
  const wchar_t *v78; // r8
  __int64 v79; // rax
  wchar_t v80; // r9
  const wchar_t *v81; // r8
  __int64 v82; // rax
  wchar_t v83; // r9
  const wchar_t *v84; // r8
  __int64 v85; // rax
  wchar_t v86; // r9
  const wchar_t *v87; // r8
  __int64 v88; // rax
  wchar_t v89; // r9
  unsigned __int16 *v90; // rax
  const wchar_t *v91; // r8
  unsigned __int16 *v92; // rdx
  __int64 v93; // rax
  __int64 v94; // rcx
  const unsigned __int16 *v95; // rbx
  const unsigned __int16 *v96; // r12
  DWORD v97; // eax
  const WCHAR *v98; // rax
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-168h]
  const unsigned __int16 *lpOutBuffera; // [rsp+20h] [rbp-168h]
  DWORD v101; // [rsp+50h] [rbp-138h]
  wchar_t *lpMem; // [rsp+60h] [rbp-128h]
  char *v106; // [rsp+70h] [rbp-118h]
  struct _OVERLAPPED *lpInBuffera; // [rsp+90h] [rbp-F8h]
  int v109; // [rsp+C0h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp-C0h]
  char v111; // [rsp+D0h] [rbp-B8h] BYREF
  _QWORD pszSrc[4]; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 v113; // [rsp+108h] [rbp-80h]
  unsigned __int16 v114[2]; // [rsp+110h] [rbp-78h] BYREF
  __int16 v115; // [rsp+114h] [rbp-74h]
  unsigned __int16 v116[2]; // [rsp+118h] [rbp-70h] BYREF
  wchar_t Buffer[18]; // [rsp+11Ch] [rbp-6Ch] BYREF

  v10 = a2;
  v11 = this;
  v12 = 0;
  lpMem = 0;
  v106 = a3;
  v101 = a4;
  if ( a2 == 3211320 )
  {
    v13 = 2147483646;
    v14 = L"GET_STATE";
    v15 = 20;
    v16 = v116;
    do
    {
      if ( !v13 )
        break;
      v17 = *v14;
      if ( !*v14 )
        break;
      ++v14;
      *v16++ = v17;
      --v13;
      --v15;
    }
    while ( v15 );
  }
  else
  {
    if ( a2 != 3211268 )
    {
      switch ( a2 )
      {
        case 0x310008u:
          v60 = 2147483646;
          v58 = L"GET_ATTRIBUTE";
          v61 = 20;
          v59 = v116;
          do
          {
            if ( !v60 )
              break;
            v57 = *v58;
            if ( !*v58 )
              break;
            ++v58;
            *v59++ = v57;
            --v60;
            --v61;
          }
          while ( v61 );
          goto LABEL_79;
        case 0x31000Cu:
          v64 = 2147483646;
          v63 = L"SET_ATTRIBUTE";
          v61 = 20;
          v59 = v116;
          while ( v64 )
          {
            v62 = *v63;
            if ( !*v63 )
              break;
            ++v63;
            *v59++ = v62;
            --v64;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x310010u:
          v67 = 2147483646;
          v66 = L"CONFISCATE";
          v61 = 20;
          v59 = v116;
          while ( v67 )
          {
            v65 = *v66;
            if ( !*v66 )
              break;
            ++v66;
            *v59++ = v65;
            --v67;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x310014u:
          v32 = 2147483646;
          v33 = L"TRANSMIT";
          v34 = 20;
          v35 = v116;
          do
          {
            if ( !v32 )
              break;
            v36 = *v33;
            if ( !*v33 )
              break;
            ++v33;
            *v35++ = v36;
            --v32;
            --v34;
          }
          while ( v34 );
          v37 = v35 - 1;
          if ( v34 )
            v37 = v35;
          *v37 = 0;
          v38 = a3 + 8;
          if ( a4 < 8 )
            v38 = a3;
          v106 = v38;
          v39 = a4 - 8;
          if ( a4 < 8 )
            v39 = a4;
          v101 = v39;
          goto LABEL_9;
        case 0x310018u:
          v70 = 2147483646;
          v69 = L"EJECT";
          v61 = 20;
          v59 = v116;
          while ( v70 )
          {
            v68 = *v69;
            if ( !*v69 )
              break;
            ++v69;
            *v59++ = v68;
            --v70;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x31001Cu:
          v73 = 2147483646;
          v72 = L"SWALLOW";
          v61 = 20;
          v59 = v116;
          while ( v73 )
          {
            v71 = *v72;
            if ( !*v72 )
              break;
            ++v72;
            *v59++ = v71;
            --v73;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x310028u:
          v76 = 2147483646;
          v75 = L"IS_PRESENT";
          v61 = 20;
          v59 = v116;
          while ( v76 )
          {
            v74 = *v75;
            if ( !*v75 )
              break;
            ++v75;
            *v59++ = v74;
            --v76;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x31002Cu:
          v79 = 2147483646;
          v78 = L"IS_ABSENT";
          v61 = 20;
          v59 = v116;
          while ( v79 )
          {
            v77 = *v78;
            if ( !*v78 )
              break;
            ++v78;
            *v59++ = v77;
            --v79;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x310030u:
          v82 = 2147483646;
          v81 = L"SET_PROTOCOL";
          v61 = 20;
          v59 = v116;
          while ( v82 )
          {
            v80 = *v81;
            if ( !*v81 )
              break;
            ++v81;
            *v59++ = v80;
            --v82;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x31003Cu:
          v85 = 2147483646;
          v84 = L"GET_LAST_ERROR";
          v61 = 20;
          v59 = v116;
          while ( v85 )
          {
            v83 = *v84;
            if ( !*v84 )
              break;
            ++v84;
            *v59++ = v83;
            --v85;
            if ( !--v61 )
            {
              v18 = v59 - 1;
              goto LABEL_8;
            }
          }
          goto LABEL_79;
        case 0x310040u:
          v88 = 2147483646;
          v87 = L"GET_PERF_CNTR";
          v61 = 20;
          v59 = v116;
          break;
        default:
          v93 = 2147483646;
          v91 = L"0x";
          v94 = 20;
          v92 = v116;
          do
          {
            if ( !v93 )
              break;
            v89 = *v91;
            if ( !*v91 )
              break;
            ++v91;
            *v92++ = v89;
            --v93;
            --v94;
          }
          while ( v94 );
          v90 = v92 - 1;
          if ( v94 )
            v90 = v92;
          *v90 = 0;
          _ultow(v10, Buffer, 16);
          goto LABEL_9;
      }
      while ( v88 )
      {
        v86 = *v87;
        if ( !*v87 )
          break;
        ++v87;
        *v59++ = v86;
        --v88;
        if ( !--v61 )
        {
          v18 = v59 - 1;
          goto LABEL_8;
        }
      }
LABEL_79:
      v18 = v59 - 1;
      if ( v61 )
        v18 = v59;
      goto LABEL_8;
    }
    v29 = 2147483646;
    v30 = L"POWER";
    v15 = 20;
    v16 = v116;
    do
    {
      if ( !v29 )
        break;
      v31 = *v30;
      if ( !*v30 )
        break;
      ++v30;
      *v16++ = v31;
      --v29;
      --v15;
    }
    while ( v15 );
  }
  v18 = v16 - 1;
  if ( v15 )
    v18 = v16;
LABEL_8:
  *v18 = 0;
LABEL_9:
  wcscpy((wchar_t *)pszSrc, L"XX XX XX XX");
  *(_DWORD *)v114 = 0;
  v115 = 0;
  v19 = 0x7FFFFFFF;
  v20 = pszSrc;
  while ( *(_WORD *)v20 )
  {
    v20 = (_QWORD *)((char *)v20 + 2);
    if ( !--v19 )
      goto LABEL_12;
  }
  v47 = 0x7FFFFFFF - v19;
  ProcessHeap = GetProcessHeap();
  v50 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2 * v47 + 2);
  if ( v50 )
  {
    if ( StringValidateDestW(v49, v47 + 1, v51) < 0 )
    {
      if ( v52 )
        *v50 = 0;
    }
    else
    {
      v54 = 0;
      if ( StringCopyWorkerW(v50, v52, v53, (STRSAFE_PCNZWCH)pszSrc, (size_t)lpOutBuffer) < 0 )
      {
        v12 = 0;
      }
      else
      {
        while ( 1 )
        {
          if ( v54 >= v101 || (v55 = (unsigned int)((_DWORD)v12 + 1), v55 >= v47) )
          {
            v50[v47] = 0;
            v12 = v50;
            lpMem = v50;
            v10 = a2;
            goto LABEL_12;
          }
          if ( (int)StringCchPrintfW(v114, 3u, L"%02x", (unsigned __int8)v106[v54]) < 0 )
            break;
          v50[(unsigned int)v12] = v114[0];
          v50[v55] = v114[1];
          ++v54;
          LODWORD(v12) = (_DWORD)v12 + 3;
        }
        v12 = 0;
        v10 = a2;
      }
    }
    v56 = GetProcessHeap();
    HeapFree(v56, 0, v50);
  }
LABEL_12:
  v21 = (HANDLE *)((char *)v11 + 832);
  v22 = (char *)*((_QWORD *)v11 + 104);
  if ( (unsigned __int64)(v22 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v23 = 1617;
    v24 = L"XX XX XX XX";
    v25 = &Data;
    goto LABEL_14;
  }
  v23 = 0;
  v40 = (struct _OVERLAPPED *)((char *)v11 + 856);
  if ( DeviceIoControl(v22, v10, a3, a4, a5, nOutBufferSize, lpBytesReturned, (LPOVERLAPPED)((char *)v11 + 856)) )
    goto LABEL_46;
  LastError = GetLastError();
  v24 = L"XX XX XX XX";
  v25 = &Data;
  if ( LastError != 997 )
  {
    v23 = LastError;
    goto LABEL_60;
  }
  lpInBuffera = (struct _OVERLAPPED *)((char *)v11 + 856);
  v43 = 0;
  v44 = this;
  do
  {
    *(_DWORD *)v114 = WaitForAnyObject(0x3A98u, g_hCalaisShutdown, *((_QWORD *)v44 + 110), 0);
    if ( *(_DWORD *)v114 == 1 )
    {
      if ( !CancelIoEx(*v21, v40) )
      {
        v95 = L"XX XX XX XX";
        if ( lpMem )
          v95 = lpMem;
        v96 = &Data;
        if ( *((_DWORD *)this + 7) )
          v96 = (const unsigned __int16 *)*((_QWORD *)this + 2);
        v97 = GetLastError();
        CalaisWarningAlwaysEvent((const unsigned __int8 *)v116, 0x26Cu, v97, v96, v116, v95);
      }
      WaitForAnObject(*((void **)this + 110), 0xFFFFFFFF);
    }
    else if ( *(_DWORD *)v114 != 2 )
    {
      CalaisError((const unsigned __int8 *)(unsigned int)(*(_DWORD *)v114 - 1), 0x26Au, 0, v45, lpOutBuffera);
      goto LABEL_58;
    }
    if ( GetOverlappedResult(*v21, lpInBuffera, lpBytesReturned, 1) )
      v23 = 0;
    else
      v23 = GetLastError();
    if ( *(_DWORD *)v114 == 1 )
      v23 = -2146435048;
    v43 = 1;
LABEL_58:
    v44 = this;
  }
  while ( !v43 );
  v11 = this;
LABEL_60:
  if ( v23 && v23 != -2146435048 )
  {
    v12 = lpMem;
LABEL_14:
    if ( a8 )
    {
      v26 = v23;
      if ( a2 == 3211268 && v23 == 1785 )
        v26 = -2146434970;
      if ( v12 )
        v24 = v12;
      if ( *((_DWORD *)v11 + 7) )
        v25 = (const WCHAR *)*((_QWORD *)v11 + 2);
      memset(pszSrc, 0, sizeof(pszSrc));
      v113 = 0;
      hMem = 0;
      v109 = v26;
      pszSrc[0] = CErrorString::Value((CErrorString *)&v109);
      pszSrc[1] = v25;
      pszSrc[2] = v116;
      pszSrc[3] = v24;
      v113 = 0;
      for ( i = 0; pszSrc[i]; ++i )
        ;
      v28 = hEventLog;
      if ( dword_18004BF50 )
      {
        if ( !hEventLog )
        {
          v98 = CalaisString(2u);
          v28 = RegisterEventSourceW(0, v98);
          hEventLog = v28;
          goto LABEL_23;
        }
      }
      else
      {
LABEL_23:
        if ( !v28 )
          goto LABEL_24;
      }
      ReportEventW(v28, 1u, 0, 0x262u, 0, i, 0, (LPCWSTR *)pszSrc, 0);
LABEL_24:
      if ( hMem != &v111 && hMem )
        LocalFree(hMem);
    }
  }
LABEL_46:
  if ( lpMem )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, lpMem);
  }
  return v23;
}

```

## disassembly

```asm
0x180012aa0  push    rbx
0x180012aa2  push    rsi
0x180012aa3  push    rdi
0x180012aa4  push    r12
0x180012aa6  push    r13
0x180012aa8  push    r14
0x180012aaa  push    r15
0x180012aac  sub     rsp, 150h
0x180012ab3  mov     rax, cs:__security_cookie
0x180012aba  xor     rax, rsp
0x180012abd  mov     [rsp+188h+var_48], rax
0x180012ac5  mov     r10d, r9d
0x180012ac8  mov     [rsp+188h+nInBufferSize], r9d
0x180012acd  mov     r11, r8
0x180012ad0  mov     [rsp+188h+lpInBuffer], r8
0x180012ad8  mov     esi, edx
0x180012ada  mov     [rsp+188h+var_134], edx
0x180012ade  mov     r12, rcx
0x180012ae1  mov     [rsp+188h+var_120], rcx
0x180012ae6  mov     [rsp+188h+var_E8], rcx
0x180012aee  mov     [rsp+188h+var_D0], rcx
0x180012af6  mov     [rsp+188h+var_108], edx
0x180012afd  mov     rax, [rsp+188h+arg_20]
0x180012b05  mov     [rsp+188h+var_110], rax
0x180012b0a  mov     rax, [rsp+188h+arg_30]
0x180012b12  mov     [rsp+188h+lpNumberOfBytesTransferred], rax
0x180012b1a  xor     r13d, r13d
0x180012b1d  mov     r14d, r13d
0x180012b20  mov     [rsp+188h+lpMem], r13
0x180012b25  mov     [rsp+188h+var_118], r8
0x180012b2a  mov     [rsp+188h+var_138], r9d
0x180012b2f  cmp     edx, 310038h
0x180012b35  jnz     loc_180012D0E
0x180012b3b  mov     eax, 7FFFFFFEh
0x180012b40  lea     r8, aGetState; "GET_STATE"
0x180012b47  mov     ecx, 14h
0x180012b4c  lea     r9, [rsp+188h+var_70]
0x180012b54  test    rax, rax
0x180012b57  jz      short loc_180012B77
0x180012b59  movzx   edx, word ptr [r8]
0x180012b5d  test    dx, dx
0x180012b60  jz      short loc_180012B77
0x180012b62  add     r8, 2
0x180012b66  mov     [r9], dx
0x180012b6a  add     r9, 2
0x180012b6e  dec     rax
0x180012b71  sub     rcx, 1
0x180012b75  jnz     short loc_180012B54
0x180012b77  lea     rax, [r9-2]
0x180012b7b  test    rcx, rcx
0x180012b7e  cmovnz  rax, r9
0x180012b82  mov     [rax], r13w
0x180012b86  movups  xmm0, xmmword ptr cs:aXxXxXxXx; "XX XX XX XX"
0x180012b8d  movups  xmmword ptr [rsp+188h+pszSrc], xmm0
0x180012b95  movsd   xmm1, qword ptr cs:aXxXxXxXx+10h; " XX"
0x180012b9d  movsd   qword ptr [rsp+188h+var_90], xmm1
0x180012ba6  xor     eax, eax
0x180012ba8  mov     dword ptr [rsp+188h+var_78], eax
0x180012baf  mov     [rsp+188h+var_74], ax
0x180012bb7  mov     r15d, 7FFFFFFFh
0x180012bbd  mov     ecx, r15d
0x180012bc0  lea     rax, [rsp+188h+pszSrc]
0x180012bc8  nop     dword ptr [rax+rax+00000000h]
0x180012bd0  cmp     [rax], r13w
0x180012bd4  jz      loc_180012FC1
0x180012bda  add     rax, 2
0x180012bde  sub     rcx, 1
0x180012be2  jnz     short loc_180012BD0
0x180012be4  lea     rdi, [r12+340h]
0x180012bec  mov     rcx, [rdi]; hDevice
0x180012bef  lea     rax, [rcx-1]
0x180012bf3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012bf7  jbe     loc_180012E05
0x180012bfd  mov     ebx, 651h
0x180012c02  lea     rsi, aXxXxXxXx; "XX XX XX XX"
0x180012c09  lea     r15, Data
0x180012c10  cmp     [rsp+188h+arg_38], 0
0x180012c18  jz      loc_180012E54
0x180012c1e  mov     eax, ebx
0x180012c20  cmp     [rsp+188h+var_134], 310004h
0x180012c28  jz      loc_180013562
0x180012c2e  test    r14, r14
0x180012c31  cmovnz  rsi, r14
0x180012c35  cmp     dword ptr [r12+1Ch], 0
0x180012c3b  ja      loc_180012D60
0x180012c41  xorps   xmm0, xmm0
0x180012c44  xor     ecx, ecx
0x180012c46  movups  xmmword ptr [rsp+188h+pszSrc], xmm0
0x180012c4e  movups  [rsp+188h+var_90], xmm0
0x180012c56  mov     [rsp+188h+var_80], rcx
0x180012c5e  mov     [rsp+188h+hMem], r13
0x180012c66  mov     [rsp+188h+var_C8], eax
0x180012c6d  lea     rcx, [rsp+188h+var_C8]; this
0x180012c75  call    ?Value@CErrorString@@QEAAPEBGXZ; CErrorString::Value(void)
0x180012c7a  mov     qword ptr [rsp+188h+pszSrc], rax
0x180012c82  mov     qword ptr [rsp+188h+pszSrc+8], r15
0x180012c8a  lea     rcx, [rsp+188h+var_70]
0x180012c92  mov     qword ptr [rsp+188h+var_90], rcx
0x180012c9a  mov     qword ptr [rsp+188h+var_90+8], rsi
0x180012ca2  mov     [rsp+188h+var_80], r13
0x180012caa  movzx   edi, r13w
0x180012cae  test    rax, rax
0x180012cb1  jz      short loc_180012CC4
0x180012cb3  inc     di
0x180012cb6  movzx   eax, di
0x180012cb9  cmp     qword ptr [rsp+rax*8+188h+pszSrc], 0
0x180012cc2  jnz     short loc_180012CB3
0x180012cc4  mov     rax, cs:hEventLog
0x180012ccb  cmp     cs:dword_18004BF50, 0
0x180012cd2  jnz     loc_180013575
0x180012cd8  test    rax, rax
0x180012cdb  jnz     loc_18001359B
0x180012ce1  lea     rax, [rsp+188h+var_B8]
0x180012ce9  mov     rcx, [rsp+188h+hMem]; hMem
0x180012cf1  cmp     rcx, rax
0x180012cf4  jz      loc_180012E54
0x180012cfa  test    rcx, rcx
0x180012cfd  jz      loc_180012E54
0x180012d03  call    cs:__imp_LocalFree
0x180012d09  jmp     loc_180012E54
0x180012d0e  cmp     esi, 310004h
0x180012d14  jnz     short loc_180012D6A
0x180012d16  mov     eax, 7FFFFFFEh
0x180012d1b  lea     r8, aPower; "POWER"
0x180012d22  mov     ecx, 14h
0x180012d27  lea     r9, [rsp+188h+var_70]
0x180012d2f  nop
0x180012d30  test    rax, rax
0x180012d33  jz      loc_180012B77
0x180012d39  movzx   edx, word ptr [r8]
0x180012d3d  test    dx, dx
0x180012d40  jz      loc_180012B77
0x180012d46  add     r8, 2
0x180012d4a  mov     [r9], dx
0x180012d4e  add     r9, 2
0x180012d52  dec     rax
0x180012d55  sub     rcx, 1
0x180012d59  jnz     short loc_180012D30
0x180012d5b  jmp     loc_180012B77
0x180012d60  mov     r15, [r12+10h]
0x180012d65  jmp     loc_180012C41
0x180012d6a  lea     eax, [rdx-310008h]; switch 57 cases
0x180012d70  cmp     eax, 38h
0x180012d73  ja      def_180012D92; jumptable 0000000180012D92 default case, cases 3211273-3211275,3211277-3211279,3211281-3211283,3211285-3211287,3211289-3211291,3211293-3211303,3211305-3211307,3211309-3211311,3211313-3211323,3211325-3211327
0x180012d79  lea     rdx, cs:180000000h
0x180012d80  movzx   eax, ds:(byte_18001360C - 180000000h)[rdx+rax]
0x180012d88  mov     ecx, ds:(jpt_180012D92 - 180000000h)[rdx+rax*4]
0x180012d8f  add     rcx, rdx
0x180012d92  jmp     rcx; switch jump
0x180012d94  mov     eax, 7FFFFFFEh; jumptable 0000000180012D92 case 3211284
0x180012d99  lea     r8, aTransmit; "TRANSMIT"
0x180012da0  mov     ecx, 14h
0x180012da5  lea     rdx, [rsp+188h+var_70]
0x180012dad  nop     dword ptr [rax]
0x180012db0  test    rax, rax
0x180012db3  jz      short loc_180012DD4
0x180012db5  movzx   r9d, word ptr [r8]
0x180012db9  test    r9w, r9w
0x180012dbd  jz      short loc_180012DD4
0x180012dbf  add     r8, 2
0x180012dc3  mov     [rdx], r9w
0x180012dc7  add     rdx, 2
0x180012dcb  dec     rax
0x180012dce  sub     rcx, 1
0x180012dd2  jnz     short loc_180012DB0
0x180012dd4  lea     rax, [rdx-2]
0x180012dd8  test    rcx, rcx
0x180012ddb  cmovnz  rax, rdx
0x180012ddf  mov     [rax], r13w
0x180012de3  lea     rax, [r11+8]
0x180012de7  cmp     r10d, 8
0x180012deb  cmovb   rax, r11
0x180012def  mov     [rsp+188h+var_118], rax
0x180012df4  lea     eax, [r10-8]
0x180012df8  cmovb   eax, r10d
0x180012dfc  mov     [rsp+188h+var_138], eax
0x180012e00  jmp     loc_180012B86
0x180012e05  mov     ebx, r13d
0x180012e08  mov     [rsp+188h+var_138], ebx
0x180012e0c  lea     r14, [r12+358h]
0x180012e14  mov     [rsp+188h+lpOverlapped], r14; lpOverlapped
0x180012e19  mov     rax, [rsp+188h+lpNumberOfBytesTransferred]
0x180012e21  mov     [rsp+188h+lpBytesReturned], rax; lpBytesReturned
0x180012e26  mov     eax, [rsp+188h+arg_28]
0x180012e2d  mov     [rsp+188h+nOutBufferSize], eax; nOutBufferSize
0x180012e31  mov     rax, [rsp+188h+var_110]
0x180012e36  mov     [rsp+188h+lpOutBuffer], rax; unsigned __int16 *
0x180012e3b  mov     r9d, [rsp+188h+nInBufferSize]; nInBufferSize
0x180012e40  mov     r8, [rsp+188h+lpInBuffer]; lpInBuffer
0x180012e48  mov     edx, esi; dwIoControlCode
0x180012e4a  call    cs:__imp_DeviceIoControl
0x180012e50  test    eax, eax
0x180012e52  jz      short loc_180012E87
0x180012e54  mov     rdi, [rsp+188h+lpMem]
0x180012e59  test    rdi, rdi
0x180012e5c  jnz     loc_180012F8F
0x180012e62  mov     eax, ebx
0x180012e64  mov     rcx, [rsp+188h+var_48]
0x180012e6c  xor     rcx, rsp; StackCookie
0x180012e6f  call    __security_check_cookie
0x180012e74  add     rsp, 150h
0x180012e7b  pop     r15
0x180012e7d  pop     r14
0x180012e7f  pop     r13
0x180012e81  pop     r12
0x180012e83  pop     rdi
0x180012e84  pop     rsi
0x180012e85  pop     rbx
0x180012e86  retn
0x180012e87  call    cs:__imp_GetLastError
0x180012e8d  lea     rsi, aXxXxXxXx; "XX XX XX XX"
0x180012e94  lea     r15, Data
0x180012e9b  cmp     eax, 3E5h
0x180012ea0  jnz     loc_180012FA8
0x180012ea6  mov     [rsp+188h+var_D8], rdi
0x180012eae  mov     [rsp+188h+var_E0], r14
0x180012eb6  mov     [rsp+188h+lpInBuffer], r14
0x180012ebe  mov     r12d, r13d
0x180012ec1  mov     [rsp+188h+nInBufferSize], r13d
0x180012ec6  mov     dword ptr [rsp+188h+var_110], r13d
0x180012ecb  mov     dword ptr [rsp+188h+var_118], 0Ah
0x180012ed3  mov     r13d, 80100018h
0x180012ed9  mov     rax, [rsp+188h+var_120]
0x180012ede  xor     r9d, r9d
0x180012ee1  mov     r8, [rax+370h]
0x180012ee8  mov     rdx, cs:?g_hCalaisShutdown@@3PEAXEA; void * g_hCalaisShutdown
0x180012eef  mov     ecx, 3A98h; dwMilliseconds
0x180012ef4  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x180012ef9  mov     dword ptr [rsp+188h+var_78], eax
0x180012f00  mov     ecx, eax
0x180012f02  sub     ecx, 1; unsigned __int8 *
0x180012f05  jz      loc_1800134FF
0x180012f0b  cmp     ecx, 1
0x180012f0e  jnz     loc_180012FB2
0x180012f14  mov     r9d, 1; bWait
0x180012f1a  mov     r8, [rsp+188h+lpNumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180012f22  mov     rdx, [rsp+188h+lpInBuffer]; lpOverlapped
0x180012f2a  mov     rcx, [rdi]; hFile
0x180012f2d  call    cs:__imp_GetOverlappedResult
0x180012f33  test    eax, eax
0x180012f35  jnz     short loc_180012F8B
0x180012f37  call    cs:__imp_GetLastError
0x180012f3d  mov     ebx, eax
0x180012f3f  cmp     dword ptr [rsp+188h+var_78], 1
0x180012f47  cmovz   ebx, r13d
0x180012f4b  mov     [rsp+188h+var_138], ebx
0x180012f4f  mov     r12d, 1
0x180012f55  mov     [rsp+188h+nInBufferSize], r12d
0x180012f5a  mov     rax, [rsp+188h+var_120]
0x180012f5f  test    r12d, r12d
0x180012f62  jz      loc_180012EDE
0x180012f68  mov     r12, [rsp+188h+var_120]
0x180012f6d  test    ebx, ebx
0x180012f6f  jz      loc_180012E54
0x180012f75  cmp     ebx, r13d
0x180012f78  jz      loc_180012E54
0x180012f7e  xor     r13d, r13d
0x180012f81  mov     r14, [rsp+188h+lpMem]
0x180012f86  jmp     loc_180012C10
0x180012f8b  xor     ebx, ebx
0x180012f8d  jmp     short loc_180012F3F
0x180012f8f  call    cs:__imp_GetProcessHeap
0x180012f95  mov     r8, rdi; lpMem
0x180012f98  xor     edx, edx; dwFlags
0x180012f9a  mov     rcx, rax; hHeap
0x180012f9d  call    cs:__imp_HeapFree
0x180012fa3  jmp     loc_180012E62
0x180012fa8  mov     ebx, eax
0x180012faa  mov     r13d, 80100018h
0x180012fb0  jmp     short loc_180012F6D
0x180012fb2  xor     r8d, r8d; unsigned __int16 *
0x180012fb5  mov     edx, 26Ah; unsigned int
0x180012fba  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180012fbf  jmp     short loc_180012F5A
0x180012fc1  sub     r15, rcx
0x180012fc4  call    cs:__imp_GetProcessHeap
0x180012fca  lea     r8, ds:2[r15*2]; dwBytes
0x180012fd2  xor     edx, edx; dwFlags
0x180012fd4  mov     rcx, rax; hHeap
0x180012fd7  call    cs:__imp_HeapAlloc
0x180012fdd  mov     rbx, rax
0x180012fe0  test    rax, rax
0x180012fe3  jz      loc_180012BE4
0x180012fe9  lea     rdx, [r15+1]; cchDest
0x180012fed  call    StringValidateDestW
0x180012ff2  test    eax, eax
0x180012ff4  js      loc_1800134E5
0x180012ffa  mov     edi, r13d
0x180012ffd  lea     r9, [rsp+188h+pszSrc]; pszSrc
0x180013005  mov     rcx, rbx; pszDest
0x180013008  call    StringCopyWorkerW
0x18001300d  test    eax, eax
0x18001300f  js      loc_1800134F7
0x180013015  cmp     edi, [rsp+188h+var_138]
0x180013019  jb      short loc_180013031
0x18001301b  mov     [rbx+r15*2], r13w
0x180013020  mov     r14, rbx
0x180013023  mov     [rsp+188h+lpMem], rbx
0x180013028  mov     esi, [rsp+188h+var_134]
0x18001302c  jmp     loc_180012BE4
  ... truncated ...
```
