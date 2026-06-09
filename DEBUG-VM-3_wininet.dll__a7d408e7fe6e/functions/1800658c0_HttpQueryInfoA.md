# HttpQueryInfoA

- ea: `0x1800658c0`
- end: `0x180066254`
- name: `HttpQueryInfoA`
- size: `2452`
- prototype: `BOOL __stdcall(HINTERNET hRequest, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpdwBufferLength, LPDWORD lpdwIndex)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180128f30`
- `0x18018138c`
- `0x180181f3c`

## callees

- `0x180060d30`
- `0x180060f00`
- `0x1800641c0`
- `0x180064560`
- `0x1800658c0`
- `0x180066750`
- `0x1800d2e04`
- `0x1800f9050`
- `0x18011fcc8`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e490c`
- `0x1801e75a4`
- `0x1801e7750`
- `0x1801ecb7c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180065ed5`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180065ef2`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180065ed5`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180065ef2`
- `api-ms-win-crt-private-l1-1-0!_o_iscntrl` at `0x180065ee1`
- `api-ms-win-crt-private-l1-1-0!_o_iscntrl` at `0x180065ee1`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180065efe`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180065efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006599c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065df4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065e06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006599c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065df4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065e06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180065c74`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180065e6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180065c74`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180065e6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180065caf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180065caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066033`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180065988`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180065988`
- `ntdll!EtwEventActivityIdControl` at `0x180065a63`
- `ntdll!EtwEventActivityIdControl` at `0x180065a9a`
- `ntdll!EtwEventActivityIdControl` at `0x180065dd8`
- `ntdll!EtwEventActivityIdControl` at `0x180065a63`
- `ntdll!EtwEventActivityIdControl` at `0x180065a9a`
- `ntdll!EtwEventActivityIdControl` at `0x180065dd8`
- `ntdll!RtlGetLastNtStatus` at `0x180065c85`
- `ntdll!RtlGetLastNtStatus` at `0x180065e80`
- `ntdll!RtlGetLastNtStatus` at `0x180065c85`
- `ntdll!RtlGetLastNtStatus` at `0x180065e80`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall HttpQueryInfoA(
        HINTERNET hRequest,
        DWORD dwInfoLevel,
        LPVOID lpBuffer,
        LPDWORD lpdwBufferLength,
        LPDWORD lpdwIndex)
{
  DWORD LastError; // eax
  DWORD v9; // edi
  LPVOID Value; // rbx
  DWORD IsValid; // edi
  HTTP_REQUEST_HANDLE_OBJECT *v12; // rbx
  __int128 *v13; // rax
  __int64 v14; // rdx
  char *v15; // rbx
  __int64 v16; // rcx
  int v17; // edi
  __int128 *v18; // rax
  __int64 v19; // rcx
  __int128 *v20; // rax
  int v21; // eax
  bool v22; // sf
  int v23; // eax
  bool v24; // sf
  __int64 v25; // r11
  unsigned int *v26; // rsi
  __int64 v27; // rdx
  char v28; // r8
  char v29; // cl
  LPDWORD v30; // r14
  __int64 v31; // rcx
  HTTP_REQUEST_HANDLE_OBJECT *v32; // rdi
  __int64 v33; // rbx
  signed __int32 v34; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v37; // r15d
  HTTP_REQUEST_HANDLE_OBJECT *v38; // rbx
  unsigned int v39; // esi
  __int64 v40; // r8
  __int64 v41; // r9
  signed __int32 v42; // eax
  bool v43; // zf
  int v44; // eax
  BOOL v45; // r14d
  DWORD v46; // eax
  DWORD v47; // esi
  int v48; // eax
  bool v49; // sf
  __int64 v51; // rbx
  __int64 v52; // r13
  int v53; // ebx
  unsigned int v54; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v56; // eax
  const char *v57; // rax
  __int64 v58; // rdx
  int v59; // ecx
  int v60; // r8d
  char v61; // r9
  __int64 v62; // r10
  int v63; // [rsp+20h] [rbp-E0h]
  int v64; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+30h] [rbp-D0h]
  _OWORD v67[6]; // [rsp+70h] [rbp-90h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v68; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v69; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v70; // [rsp+F0h] [rbp-10h] BYREF
  int v71; // [rsp+100h] [rbp+0h] BYREF
  __int128 v72; // [rsp+108h] [rbp+8h] BYREF
  int v73; // [rsp+118h] [rbp+18h]
  __int128 v74; // [rsp+120h] [rbp+20h] BYREF
  _UNKNOWN *retaddr; // [rsp+188h] [rbp+88h]

  if ( (xmmword_180266B60 & 4) != 0 )
  {
    v57 = InternetMapHttpOption(dwInfoLevel & 0x3FFFFFF);
    WPP_SF_qsDqsqdqd(
      v59,
      v58,
      v60,
      (_DWORD)hRequest,
      (__int64)v57,
      dwInfoLevel,
      (__int64)lpBuffer,
      v58,
      v62,
      v60,
      (__int64)lpdwIndex,
      v61);
  }
  v71 = 0;
  v68 = 0;
  v73 = 0;
  v72 = 0;
  memset(v67, 0, sizeof(v67));
  InternetSaveThreadInfo(v67, *(_QWORD *)&dwInfoLevel, lpBuffer, lpdwBufferLength);
  if ( !GlobalDataInitialized )
  {
    IsValid = 12172;
    goto LABEL_47;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( qword_180269EA8 && LastError && LastError != 997 && LastError != 12150 && LastError != 12028 && LastError != 122 )
  {
    v33 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v33 + qword_180269EA8));
    *(_DWORD *)(v33 + qword_180269EA8 + 8) = v9;
    *(_DWORD *)(v33 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  Value = TlsGetValue(InternetTlsIndex);
  if ( !Value )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 22, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
    }
    Value = (LPVOID)InternetCreateThreadInfo(1);
    if ( !Value && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      WPP_SF_(1037, 23, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
      SetLastError(v9);
      goto LABEL_108;
    }
  }
  SetLastError(v9);
  if ( !Value )
  {
LABEL_108:
    IsValid = 12004;
    goto LABEL_47;
  }
  IsValid = MapHandleToAddress(hRequest, &v68, 0);
  if ( IsValid || (v12 = v68, (IsValid = HANDLE_OBJECT::IsValid(v68, 1902465608)) != 0) )
  {
LABEL_54:
    if ( IsValid == 12150 || IsValid == 122 )
      goto LABEL_55;
LABEL_47:
    if ( (xmmword_180266B50 & 2) != 0 )
      WPP_SF_d(513, 11, &WPP_93aa1e82e024382eec5a2d0e0dbba38b_Traceguids, IsValid);
    goto LABEL_55;
  }
  (*(void (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = &v72;
  v14 = 16;
  v15 = (char *)v68 + 164;
  v16 = 16;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (__int128 *)((char *)v13 + 1);
    --v16;
  }
  while ( v16 );
  v17 = 0;
  v18 = &v72;
  v73 = 0;
  v19 = 16;
  v69 = 0;
  v74 = 0;
  do
  {
    *(_BYTE *)v18 = 0;
    v18 = (__int128 *)((char *)v18 + 1);
    --v19;
  }
  while ( v19 );
  v70 = 0;
  v20 = &v74;
  do
  {
    *(_BYTE *)v20 = 0;
    v20 = (__int128 *)((char *)v20 + 1);
    --v14;
  }
  while ( v14 );
  v21 = EtwEventActivityIdControl(1, &v70);
  v22 = v21 < 0;
  if ( v21 > 0 )
    v22 = 1;
  if ( v22 )
    DWORD1(v70) = 128;
  else
    v74 = v70;
  if ( !v15 )
  {
    v34 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    TickCount = GetTickCount();
    CurrentProcessId = GetCurrentProcessId();
    *(_QWORD *)&v69 = __PAIR64__(v34, (unsigned int)retaddr);
    v17 = 0;
    *((_QWORD *)&v69 + 1) = __PAIR64__(CurrentProcessId, TickCount);
    v15 = (char *)&v69;
  }
  DWORD1(v70) = 0;
  v23 = EtwEventActivityIdControl(2, v15);
  v24 = v23 < 0;
  if ( v23 > 0 )
    v24 = 1;
  if ( v24 )
    DWORD1(v70) = 144;
  v25 = dwInfoLevel & 0x3FFFFFF;
  v73 = 1;
  v72 = v74;
  if ( (unsigned int)v25 > 0x5F && (_DWORD)v25 != 0xFFFF )
    goto LABEL_88;
  v26 = lpdwBufferLength;
  if ( !lpdwBufferLength )
    goto LABEL_88;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  if ( (dwInfoLevel & 0x28000000) != 0x28000000 )
    v27 = ((dwInfoLevel & 0x48000000) != 1207959552) & (unsigned __int8)((dwInfoLevel & 0x60000000) != 1610612736);
  LOBYTE(v27) = ((dwInfoLevel & 0x24000000) != 603979776) & v27;
  if ( (dwInfoLevel & 0xC000000) != 0xC000000 )
    v28 = v27;
  if ( (dwInfoLevel & 0x84000000) != 0x84000000 )
    v29 = ((dwInfoLevel & 0x44000000) != 1140850688) & v28;
  if ( !v29 )
    goto LABEL_88;
  v30 = (LPDWORD)&v71;
  if ( lpdwIndex )
    v30 = lpdwIndex;
  if ( *v30 && ((dwInfoLevel & 0x4000000) != 0 || (unsigned int)(v25 - 18) <= 4) )
  {
    IsValid = 12150;
LABEL_55:
    v37 = 0;
    goto LABEL_56;
  }
  if ( (_DWORD)v25 == 0xFFFF )
  {
    if ( lpBuffer )
    {
      v52 = 0x400000000002401LL;
      while ( 1 )
      {
        v31 = (unsigned int)*((char *)lpBuffer + v17);
        if ( *((_BYTE *)lpBuffer + v17) <= 0x3Au )
        {
          if ( _bittest64(&v52, v31) )
            break;
        }
        v53 = *((char *)lpBuffer + v17);
        if ( __isascii(v31) && iscntrl(v53) )
          goto LABEL_88;
        v54 = *((char *)lpBuffer + v17);
        if ( __isascii(v54) )
        {
          if ( (unsigned int)_o_isspace(v54) )
            goto LABEL_88;
        }
        ++v17;
      }
      v26 = lpdwBufferLength;
      goto LABEL_42;
    }
LABEL_88:
    IsValid = 87;
    goto LABEL_47;
  }
  v31 = 3 * v25;
  if ( (dwInfoLevel & ~*((_DWORD *)&unk_1801EF92C + 6 * v25) & 0xF8000000) != 0 )
  {
    IsValid = 12154;
    goto LABEL_47;
  }
  if ( !lpBuffer )
    *lpdwBufferLength = 0;
LABEL_42:
  v32 = v68;
  if ( (dwInfoLevel & 0x80000000) != 0 )
  {
    if ( !(unsigned int)HTTP_REQUEST_HANDLE_OBJECT::CheckState(v68, 0x400u) )
    {
LABEL_46:
      IsValid = 12019;
      goto LABEL_47;
    }
  }
  else
  {
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      v65 = (*((_DWORD *)v68 + 318) >> 9) & 1;
      v64 = 512;
      v63 = 512;
      WPP_SF_lDll(v31, v27);
    }
    if ( (*((_DWORD *)v32 + 318) & 0x200) == 0 )
      goto LABEL_46;
  }
  IsValid = HTTP_REQUEST_HANDLE_OBJECT::QueryInfo(v32, dwInfoLevel, lpBuffer, v26, v30);
  if ( IsValid )
    goto LABEL_54;
  if ( (xmmword_180266B60 & 4) == 0 )
    goto LABEL_111;
  WPP_SF_d(1026, 12, &WPP_93aa1e82e024382eec5a2d0e0dbba38b_Traceguids, *v26);
  if ( (xmmword_180266B60 & 4) == 0 )
    goto LABEL_111;
  v69 = (unsigned __int64)lpBuffer;
  if ( lpBuffer )
  {
    v56 = *v26;
    if ( *v26 > 0xFFFF )
    {
      WORD4(v69) = -1;
      goto LABEL_117;
    }
  }
  else
  {
    LOWORD(v56) = 0;
  }
  WORD4(v69) = v56;
LABEL_117:
  v74 = v69;
  WPP_SF__COUNTEDSTRING_(1026, 13, &WPP_93aa1e82e024382eec5a2d0e0dbba38b_Traceguids, &v74);
LABEL_111:
  v37 = 1;
LABEL_56:
  v38 = v68;
  if ( v68 )
  {
    if ( (BYTE2(xmmword_180266B60) & 2) != 0 )
      WPP_SF_q(1041, 30, &WPP_dddf2698fa6139794d752a52a3642573_Traceguids, v68);
    v39 = HANDLE_OBJECT::IsValid(v38, 1684826455);
    if ( !v39 )
    {
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
        WPP_SF_q(1032, 24, &WPP_a85fccec657a30c16cbc767298893445_Traceguids, *((_QWORD *)v38 + 16));
      v41 = *((_QWORD *)v38 + 16);
      v42 = _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 35, 0xFFFFFFFF);
      v43 = v42 == 1;
      v44 = v42 - 1;
      v45 = v43;
      if ( (BYTE2(xmmword_180266B60) & 0x20) != 0 )
      {
        v64 = v44;
        WPP_SF_qqD(1045, 25, (unsigned int)&WPP_a85fccec657a30c16cbc767298893445_Traceguids, v41, (__int64)v38);
      }
      if ( v45 )
        (*(void (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64, __int64, int, int, int))(*(_QWORD *)v38 + 8LL))(
          v38,
          1,
          v40,
          v41,
          v63,
          v64,
          v65);
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
        WPP_SF_d(1032, 26, &WPP_a85fccec657a30c16cbc767298893445_Traceguids, v45);
      if ( !v45 )
        v39 = 12036;
    }
    if ( (BYTE2(xmmword_180266B60) & 2) != 0 )
      WPP_SF_d(1041, 31, &WPP_dddf2698fa6139794d752a52a3642573_Traceguids, v39);
  }
  if ( (xmmword_180266B60 & 4) != 0 )
    WPP_SF_d(1026, 14, &WPP_93aa1e82e024382eec5a2d0e0dbba38b_Traceguids, v37);
  v46 = GetLastError();
  v47 = v46;
  if ( qword_180269EA8 && v46 && v46 != 997 && v46 != 12150 && v46 != 12028 && v46 != 122 )
  {
    v51 = 16LL * (unsigned __int8)_InterlockedIncrement(&dword_180269EA4);
    GetSystemTimeAsFileTime((LPFILETIME)(v51 + qword_180269EA8));
    *(_DWORD *)(v51 + qword_180269EA8 + 8) = v47;
    *(_DWORD *)(v51 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  if ( v73 )
  {
    DWORD1(v70) = 0;
    v48 = EtwEventActivityIdControl(2, &v72);
    v49 = v48 < 0;
    if ( v48 > 0 )
      v49 = 1;
    if ( v49 )
      DWORD1(v70) = 144;
  }
  SetLastError(v47);
  InternetRestoreThreadInfo(v67);
  SetLastError(IsValid);
  return v37;
}

```

## disassembly

```asm
0x1800658c0  mov     r11, rsp
0x1800658c3  push    rbp
0x1800658c4  push    rsi
0x1800658c5  push    rdi
0x1800658c6  push    r15
0x1800658c8  lea     rbp, [rsp-68h]
0x1800658cd  sub     rsp, 168h
0x1800658d4  mov     rax, cs:__security_cookie
0x1800658db  xor     rax, rsp
0x1800658de  mov     [rbp+80h+var_50], rax
0x1800658e2  mov     [r11-28h], rbx
0x1800658e6  mov     r10, r9
0x1800658e9  mov     [r11-30h], r12
0x1800658ed  mov     r15, r8
0x1800658f0  mov     [r11-38h], r13
0x1800658f4  mov     r12d, edx
0x1800658f7  mov     r13, [rbp+80h+lpdwIndex]
0x1800658fe  mov     rsi, rcx
0x180065901  mov     [rsp+180h+var_120], r9
0x180065906  xor     edi, edi
0x180065908  test    byte ptr cs:xmmword_180266B60, 4
0x18006590f  jnz     loc_1800660F5
0x180065915  xorps   xmm1, xmm1
0x180065918  mov     [rsp+180h+var_38], r14
0x180065920  xorps   xmm0, xmm0
0x180065923  mov     [rbp+80h+var_80], edi
0x180065926  xor     eax, eax
0x180065928  mov     [rbp+80h+var_B0], rdi
0x18006592c  lea     rcx, [rsp+180h+var_110]
0x180065931  mov     [rbp+80h+var_68], eax
0x180065934  movups  [rbp+80h+var_78], xmm0
0x180065938  movups  [rsp+180h+var_110], xmm1
0x18006593d  movups  [rbp+80h+var_100], xmm1
0x180065941  movups  [rbp+80h+var_F0], xmm1
0x180065945  movups  [rbp+80h+var_E0], xmm1
0x180065949  movups  [rbp+80h+var_D0], xmm1
0x18006594d  movups  [rbp+80h+var_C0], xmm1
0x180065951  call    InternetSaveThreadInfo
0x180065956  cmp     cs:GlobalDataInitialized, edi
0x18006595c  jz      loc_180065F2A
0x180065962  call    cs:__imp_GetLastError
0x180065968  cmp     cs:qword_180269EA8, 0
0x180065970  mov     r14d, 1
0x180065976  mov     edi, eax
0x180065978  jz      short loc_180065982
0x18006597a  test    eax, eax
0x18006597c  jnz     loc_180065C29
0x180065982  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x180065988  call    cs:__imp_TlsGetValue
0x18006598e  mov     rbx, rax
0x180065991  test    rax, rax
0x180065994  jz      loc_180065F61
0x18006599a  mov     ecx, edi; dwErrCode
0x18006599c  call    cs:__imp_SetLastError
0x1800659a2  test    rbx, rbx
0x1800659a5  jz      loc_180065FAD
0x1800659ab  xor     r8d, r8d
0x1800659ae  lea     rdx, [rbp+80h+var_B0]
0x1800659b2  mov     rcx, rsi
0x1800659b5  call    MapHandleToAddress
0x1800659ba  mov     edi, eax
0x1800659bc  test    eax, eax
0x1800659be  jnz     loc_180065CD4
0x1800659c4  mov     rbx, [rbp+80h+var_B0]
0x1800659c8  mov     edx, 71655248h
0x1800659cd  mov     rcx, rbx
0x1800659d0  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800659d5  mov     edi, eax
0x1800659d7  test    eax, eax
0x1800659d9  jnz     loc_180065CD4
0x1800659df  mov     rax, [rbx]
0x1800659e2  mov     rcx, rbx
0x1800659e5  mov     rax, [rax+10h]
0x1800659e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800659ee  mov     rbx, [rbp+80h+var_B0]
0x1800659f2  lea     rax, [rbp+80h+var_78]
0x1800659f6  mov     edx, 10h
0x1800659fb  add     rbx, 0A4h
0x180065a02  mov     ecx, edx
0x180065a04  mov     byte ptr [rax], 0
0x180065a07  lea     rax, [rax+1]
0x180065a0b  sub     rcx, r14
0x180065a0e  jnz     short loc_180065A04
0x180065a10  xor     edi, edi
0x180065a12  lea     rax, [rbp+80h+var_78]
0x180065a16  xorps   xmm0, xmm0
0x180065a19  mov     [rbp+80h+var_68], edi
0x180065a1c  xorps   xmm1, xmm1
0x180065a1f  mov     rcx, rdx
0x180065a22  movups  [rbp+80h+var_A0], xmm0
0x180065a26  movups  [rbp+80h+var_60], xmm1
0x180065a2a  nop     word ptr [rax+rax+00h]
0x180065a30  mov     [rax], dil
0x180065a33  lea     rax, [rax+1]
0x180065a37  sub     rcx, r14
0x180065a3a  jnz     short loc_180065A30
0x180065a3c  xorps   xmm0, xmm0
0x180065a3f  mov     dword ptr [rbp+80h+var_90+4], edi
0x180065a42  movups  xmmword ptr [rbp-10h], xmm0
0x180065a46  lea     rax, [rbp+80h+var_60]
0x180065a4a  nop     word ptr [rax+rax+00h]
0x180065a50  mov     [rax], dil
0x180065a53  lea     rax, [rax+1]
0x180065a57  sub     rdx, r14
0x180065a5a  jnz     short loc_180065A50
0x180065a5c  lea     rdx, [rbp+80h+var_90]
0x180065a60  mov     ecx, r14d
0x180065a63  call    cs:__imp_EtwEventActivityIdControl
0x180065a69  test    eax, eax
0x180065a6b  jle     short loc_180065A77
0x180065a6d  movzx   eax, ax
0x180065a70  or      eax, 80070000h
0x180065a75  test    eax, eax
0x180065a77  js      loc_180066167
0x180065a7d  movaps  xmm0, [rbp+80h+var_90]
0x180065a81  movdqa  [rbp+80h+var_60], xmm0
0x180065a86  test    rbx, rbx
0x180065a89  jz      loc_180065C9B
0x180065a8f  mov     rdx, rbx
0x180065a92  mov     dword ptr [rbp+80h+var_90+4], edi
0x180065a95  mov     ecx, 2
0x180065a9a  call    cs:__imp_EtwEventActivityIdControl
0x180065aa0  test    eax, eax
0x180065aa2  jle     short loc_180065AAE
0x180065aa4  movzx   eax, ax
0x180065aa7  or      eax, 80070000h
0x180065aac  test    eax, eax
0x180065aae  js      loc_180066173
0x180065ab4  movaps  xmm0, [rbp+80h+var_60]
0x180065ab8  mov     r11d, r12d
0x180065abb  and     r11d, 3FFFFFFh
0x180065ac2  mov     [rbp+80h+var_68], r14d
0x180065ac6  mov     ebx, 0FFFFh
0x180065acb  movups  [rbp+80h+var_78], xmm0
0x180065acf  cmp     r11d, 5Fh ; '_'
0x180065ad3  ja      loc_180065E96
0x180065ad9  mov     rsi, [rsp+180h+var_120]
0x180065ade  test    rsi, rsi
0x180065ae1  jz      loc_180065E9F
0x180065ae7  mov     r10d, r12d
0x180065aea  mov     r9d, r12d
0x180065aed  and     r10d, 84000000h
0x180065af4  and     r9d, 0C000000h
0x180065afb  mov     r8d, r12d
0x180065afe  mov     eax, r12d
0x180065b01  and     eax, 60000000h
0x180065b06  and     r8d, 28000000h
0x180065b0d  cmp     eax, 60000000h
0x180065b12  mov     edx, edi
0x180065b14  mov     eax, r12d
0x180065b17  setnz   cl
0x180065b1a  and     eax, 48000000h
0x180065b1f  cmp     eax, 48000000h
0x180065b24  setnz   al
0x180065b27  and     cl, al
0x180065b29  cmp     r8d, 28000000h
0x180065b30  movzx   eax, cl
0x180065b33  mov     r8d, edi
0x180065b36  mov     ecx, edi
0x180065b38  cmovnz  edx, eax
0x180065b3b  mov     eax, r12d
0x180065b3e  and     eax, 24000000h
0x180065b43  cmp     eax, 24000000h
0x180065b48  setnz   al
0x180065b4b  and     dl, al
0x180065b4d  cmp     r9d, 0C000000h
0x180065b54  movzx   eax, dl
0x180065b57  cmovnz  r8d, eax
0x180065b5b  mov     eax, r12d
0x180065b5e  and     eax, 44000000h
0x180065b63  cmp     eax, 44000000h
0x180065b68  setnz   al
0x180065b6b  and     r8b, al
0x180065b6e  cmp     r10d, 84000000h
0x180065b75  movzx   eax, r8b
0x180065b79  cmovnz  ecx, eax
0x180065b7c  test    cl, cl
0x180065b7e  jz      loc_180065E9F
0x180065b84  test    r13, r13
0x180065b87  lea     r14, [rbp+80h+var_80]
0x180065b8b  cmovnz  r14, r13
0x180065b8f  cmp     dword ptr [r14], 0
0x180065b93  jnz     loc_180065F43
0x180065b99  cmp     r11d, ebx
0x180065b9c  jz      loc_180065EA9
0x180065ba2  lea     rcx, [r11+r11*2]
0x180065ba6  lea     rax, unk_1801EF92C
0x180065bad  mov     eax, [rax+rcx*8]
0x180065bb0  not     eax
0x180065bb2  and     eax, r12d
0x180065bb5  test    eax, 0F8000000h
0x180065bba  jnz     loc_18006617F
0x180065bc0  test    r15, r15
0x180065bc3  jz      loc_180065F0C
0x180065bc9  mov     rdi, [rbp+80h+var_B0]
0x180065bcd  test    r12d, r12d
0x180065bd0  js      loc_180066189
0x180065bd6  test    byte ptr cs:xmmword_180266B60, 2
0x180065bdd  jnz     loc_1800661A3
0x180065be3  test    dword ptr [rdi+4F8h], 200h
0x180065bed  jnz     loc_180065FF3
0x180065bf3  mov     edi, 2EF3h
0x180065bf8  mov     r12d, 1
0x180065bfe  test    byte ptr cs:xmmword_180266B50, 2
0x180065c05  jz      loc_180065CE6
0x180065c0b  mov     edx, 0Bh
0x180065c10  lea     r8, WPP_93aa1e82e024382eec5a2d0e0dbba38b_Traceguids
0x180065c17  mov     ecx, 201h
0x180065c1c  mov     r9d, edi
0x180065c1f  call    WPP_SF_d
0x180065c24  jmp     loc_180065CE6
0x180065c29  cmp     edi, 3E5h
0x180065c2f  jz      loc_180065982
0x180065c35  cmp     edi, 2F76h
0x180065c3b  jz      loc_180065982
0x180065c41  cmp     edi, 2EFCh
0x180065c47  jz      loc_180065982
0x180065c4d  cmp     edi, 7Ah ; 'z'
0x180065c50  jz      loc_180065982
0x180065c56  mov     eax, r14d
0x180065c59  lock xadd cs:dword_180269EA4, eax
0x180065c61  mov     rcx, cs:qword_180269EA8
0x180065c68  inc     eax
0x180065c6a  movzx   ebx, al
0x180065c6d  shl     rbx, 4
0x180065c71  add     rcx, rbx; lpSystemTimeAsFileTime
0x180065c74  call    cs:__imp_GetSystemTimeAsFileTime
0x180065c7a  mov     rax, cs:qword_180269EA8
0x180065c81  mov     [rbx+rax+8], edi
0x180065c85  call    cs:__imp_RtlGetLastNtStatus
0x180065c8b  mov     rcx, cs:qword_180269EA8
0x180065c92  mov     [rbx+rcx+0Ch], eax
0x180065c96  jmp     loc_180065982
0x180065c9b  mov     rdi, [rbp+88h]
0x180065ca2  mov     esi, r14d
0x180065ca5  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180065cad  inc     esi
0x180065caf  call    cs:__imp_GetTickCount
0x180065cb5  mov     ebx, eax
0x180065cb7  call    cs:__imp_GetCurrentProcessId
0x180065cbd  mov     dword ptr [rbp+80h+var_A0], edi
0x180065cc0  xor     edi, edi
0x180065cc2  mov     dword ptr [rbp+80h+var_A0+8], ebx
0x180065cc5  lea     rbx, [rbp+80h+var_A0]
0x180065cc9  mov     dword ptr [rbp+80h+var_A0+0Ch], eax
0x180065ccc  mov     dword ptr [rbp+80h+var_A0+4], esi
0x180065ccf  jmp     loc_180065A8F
0x180065cd4  cmp     edi, 2F76h
0x180065cda  jnz     loc_18006609D
0x180065ce0  mov     r12d, 1
0x180065ce6  xor     r15d, r15d
0x180065ce9  mov     rbx, [rbp+80h+var_B0]
0x180065ced  mov     r13, [rsp+180h+var_30]
0x180065cf5  test    rbx, rbx
0x180065cf8  jz      loc_180065D87
0x180065cfe  test    byte ptr cs:xmmword_180266B60+2, 2
0x180065d05  jnz     loc_180065FD5
0x180065d0b  mov     edx, 646C6957h
0x180065d10  mov     rcx, rbx
0x180065d13  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180065d18  mov     esi, eax
0x180065d1a  test    eax, eax
0x180065d1c  jnz     short loc_180065D7A
0x180065d1e  test    byte ptr cs:xmmword_180266B60+1, 1
0x180065d25  jnz     loc_180066057
0x180065d2b  mov     r9, [rbx+80h]
0x180065d32  mov     eax, 0FFFFFFFFh
0x180065d37  lock xadd [rbx+8Ch], eax
0x180065d3f  add     eax, 0FFFFFFFFh
0x180065d42  mov     r14d, 0
0x180065d48  setz    r14b
0x180065d4c  test    byte ptr cs:xmmword_180266B60+2, 20h
0x180065d53  jnz     loc_180066079
0x180065d59  test    r14d, r14d
0x180065d5c  jnz     loc_180065F13
0x180065d62  test    byte ptr cs:xmmword_180266B60+1, 1
0x180065d69  jnz     loc_18006620C
0x180065d6f  test    r14d, r14d
0x180065d72  mov     eax, 2F04h
0x180065d77  cmovz   esi, eax
0x180065d7a  test    byte ptr cs:xmmword_180266B60+2, 2
0x180065d81  jnz     loc_180065FB7
0x180065d87  test    byte ptr cs:xmmword_180266B60, 4
0x180065d8e  mov     r14, [rsp+180h+var_38]
0x180065d96  jnz     loc_18006622A
0x180065d9c  call    cs:__imp_GetLastError
0x180065da2  cmp     cs:qword_180269EA8, 0
0x180065daa  mov     esi, eax
0x180065dac  jz      short loc_180065DB2
0x180065dae  test    eax, eax
0x180065db0  jnz     short loc_180065E28
0x180065db2  cmp     [rbp+80h+var_68], 0
0x180065db6  mov     r12, [rsp+180h+var_28]
0x180065dbe  mov     rbx, [rsp+180h+var_20]
0x180065dc6  jz      short loc_180065DF2
0x180065dc8  lea     rdx, [rbp+80h+var_78]
0x180065dcc  mov     dword ptr [rbp+80h+var_90+4], 0
0x180065dd3  mov     ecx, 2
0x180065dd8  call    cs:__imp_EtwEventActivityIdControl
0x180065dde  test    eax, eax
  ... truncated ...
```
