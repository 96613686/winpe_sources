# _SleepStudy::IndicateClientRequestBegin_::_3_::_lambda_1_::operator()

- ea: `0x180043bb0`
- end: `0x1800447da`
- name: `_SleepStudy::IndicateClientRequestBegin_::_3_::_lambda_1_::operator()`
- size: `3114`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180043ba0`

## callees

- `0x18001c11c`
- `0x18001c19c`
- `0x18002e560`
- `0x18003ed4c`
- `0x180041044`
- `0x180041a20`
- `0x180043bb0`
- `0x180046c50`
- `0x18004a6b8`
- `0x180067b5c`
- `0x18007424c`
- `0x180074264`
- `0x180084f50`
- `0x18008534c`
- `0x180085bac`
- `0x1800a1564`
- `0x1800a97a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800443f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800443f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004464a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004464a`
- `ntdll!EtwEventWriteTransfer` at `0x180043d75`
- `ntdll!EtwEventWriteTransfer` at `0x1800445e3`
- `ntdll!EtwEventWriteTransfer` at `0x18004477e`
- `ntdll!EtwEventWriteTransfer` at `0x180043d75`
- `ntdll!EtwEventWriteTransfer` at `0x1800445e3`
- `ntdll!EtwEventWriteTransfer` at `0x18004477e`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044199`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044641`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044664`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044199`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044641`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180044664`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800441a8`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180044400`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180044433`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800441a8`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180044400`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180044433`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x1800445f1`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x1800445f1`

## string_xrefs

- `0x18004479a`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`
- `0x1800447c7`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SleepStudy::IndicateClientRequestBegin_::_3_::_lambda_1_::operator()(
        _QWORD *a1,
        unsigned __int64 a2)
{
  _BYTE *v2; // r8
  __int64 result; // rax
  __int64 v4; // rax
  __int64 v5; // rcx
  __int128 v6; // xmm1
  _QWORD *v7; // rbx
  SleepStudy::Singleton *v8; // rsi
  unsigned int v9; // r10d
  _DWORD *v10; // rdi
  unsigned __int64 v11; // rcx
  unsigned int *v12; // rsi
  _DWORD *v13; // rsi
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  char *v18; // rbx
  int v19; // eax
  unsigned __int16 v20; // r12
  char v21; // al
  char *v22; // rcx
  __int64 v23; // r15
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // r13
  _QWORD *v29; // r14
  void *v30; // rax
  char *v31; // r10
  char *v32; // rdx
  _QWORD *v33; // r8
  char *v34; // rcx
  __int64 v35; // r10
  __int64 v36; // r11
  __int64 v37; // rbx
  __int64 i; // r15
  __int64 v39; // rcx
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rax
  char *v42; // r14
  _QWORD *v43; // r13
  const void *v44; // rax
  unsigned __int64 *v45; // r8
  unsigned __int64 v46; // r9
  size_t v47; // r10
  unsigned __int64 v48; // r11
  const void *v49; // r12
  size_t v50; // r14
  unsigned __int64 v51; // r15
  size_t v52; // rax
  void *v53; // rax
  _QWORD *v54; // r13
  size_t v55; // rcx
  __int64 v56; // rax
  int *v57; // r14
  _QWORD *blocker; // rax
  _QWORD *v59; // r15
  __int64 v60; // r13
  __int64 v61; // r12
  DWORD LastError; // r14d
  const struct std::nothrow_t *v63; // rdx
  void *v64; // rcx
  const struct std::nothrow_t *v65; // rdx
  void *v66; // rcx
  int active; // eax
  __int64 v68; // r15
  __int64 v69; // r12
  DWORD v70; // r14d
  int SourceString; // [rsp+20h] [rbp-178h]
  int v72; // [rsp+38h] [rbp-160h] BYREF
  int v73; // [rsp+3Ch] [rbp-15Ch] BYREF
  __int64 v74; // [rsp+40h] [rbp-158h] BYREF
  _BYTE *v75; // [rsp+48h] [rbp-150h]
  int v76; // [rsp+50h] [rbp-148h]
  unsigned __int64 v77; // [rsp+58h] [rbp-140h] BYREF
  int v78; // [rsp+60h] [rbp-138h]
  __int128 v79; // [rsp+68h] [rbp-130h] BYREF
  size_t v80; // [rsp+78h] [rbp-120h]
  unsigned __int64 v81; // [rsp+80h] [rbp-118h]
  __int64 v82; // [rsp+88h] [rbp-110h]
  _QWORD v83[3]; // [rsp+90h] [rbp-108h] BYREF
  unsigned __int64 v84; // [rsp+A8h] [rbp-F0h]
  char v85; // [rsp+B0h] [rbp-E8h] BYREF
  unsigned __int16 v86[4]; // [rsp+B8h] [rbp-E0h] BYREF
  int *v87; // [rsp+C0h] [rbp-D8h]
  int v88; // [rsp+C8h] [rbp-D0h]
  int v89; // [rsp+CCh] [rbp-CCh]
  char *v90; // [rsp+D0h] [rbp-C8h]
  int v91; // [rsp+D8h] [rbp-C0h]
  int v92; // [rsp+DCh] [rbp-BCh]
  __int64 *v93; // [rsp+E0h] [rbp-B8h]
  __int64 v94; // [rsp+E8h] [rbp-B0h]
  int *v95; // [rsp+F0h] [rbp-A8h]
  __int64 v96; // [rsp+F8h] [rbp-A0h]
  unsigned __int64 *v97; // [rsp+100h] [rbp-98h]
  __int64 v98; // [rsp+108h] [rbp-90h]
  __int64 *v99; // [rsp+110h] [rbp-88h]
  __int64 v100; // [rsp+118h] [rbp-80h]
  int v101[2]; // [rsp+120h] [rbp-78h] BYREF
  __int64 v102; // [rsp+128h] [rbp-70h]
  _BYTE v103[24]; // [rsp+130h] [rbp-68h] BYREF
  _DWORD v104[2]; // [rsp+150h] [rbp-48h] BYREF
  __int64 v105; // [rsp+158h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v2 = a1;
  v75 = a1;
  v76 = 0;
  result = (unsigned int)dword_18013A120;
  if ( (unsigned int)dword_18013A120 <= 4 )
  {
    v7 = a1 + 2;
  }
  else
  {
    v4 = *a1;
    v5 = 0;
    *(_OWORD *)&v103[8] = 0;
    if ( *(_BYTE *)(v4 + 56) )
    {
      v6 = *(_OWORD *)(v4 + 32);
      *(_QWORD *)&v103[16] = *(_QWORD *)(v4 + 48);
      v5 = v6;
    }
    v74 = v5;
    v7 = v2 + 16;
    if ( v2[32] )
      *(_OWORD *)v103 = *(_OWORD *)v7;
    else
      *(_OWORD *)v103 = 0;
    v73 = *((_DWORD *)v2 + 3);
    v72 = *((_DWORD *)v2 + 2);
    v99 = &v74;
    v100 = 8;
    v97 = (unsigned __int64 *)v103;
    v98 = 16;
    v95 = &v73;
    v96 = 4;
    v93 = (__int64 *)&v72;
    v94 = 4;
    v101[0] = 184549376;
    v101[1] = 4;
    v102 = 0;
    v87 = off_18013A128;
    v88 = *(unsigned __int16 *)off_18013A128;
    v89 = 2;
    v90 = byte_180119A05;
    v91 = 120;
    v92 = 1;
    *(_DWORD *)v86 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    SourceString = 6;
    result = EtwEventWriteTransfer(RegHandle, v101, 0, 0);
    v2 = v75;
  }
  try
  {
    v8 = *(SleepStudy::Singleton **)v2;
    if ( !v2[32] )
    {
      v10 = (_DWORD *)*((_QWORD *)v8 + 9);
      v13 = (_DWORD *)*((_QWORD *)v8 + 10);
      goto LABEL_30;
    }
    if ( !*((_BYTE *)v7 + 16) )
      std::_Throw_bad_optional_access();
    result = SleepStudy::Singleton::InterfaceIndexFromGuid(*(SleepStudy::Singleton **)v2, (const struct _GUID *)v7);
    v9 = result;
    v2 = v75;
    v10 = *(_DWORD **)(*(_QWORD *)v75 + 72LL);
    a2 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(*(_QWORD *)v75 + 80LL) - (_QWORD)v10) >> 4);
    if ( (__int64)a2 <= 0 )
    {
LABEL_17:
      v13 = v10;
      goto LABEL_30;
    }
    while ( 1 )
    {
      v11 = a2 >> 1;
      v12 = &v10[12 * (a2 >> 1)];
      if ( *v12 >= v9 )
      {
        if ( *v12 <= v9 )
        {
          v14 = a2 >> 1;
          if ( v11 )
          {
            do
            {
              v15 = v14 >> 1;
              if ( v10[12 * (v14 >> 1)] >= v9 )
              {
                v14 >>= 1;
              }
              else
              {
                v10 += 12 * (v14 >> 1) + 12;
                result = -1LL - v15;
                v14 += -1LL - v15;
              }
            }
            while ( (__int64)v14 > 0 );
          }
          a2 = a2 - v11 - 1;
          v13 = v12 + 12;
          while ( (__int64)a2 > 0 )
          {
            v16 = a2 >> 1;
            if ( v9 >= v13[12 * (a2 >> 1)] )
            {
              v13 += 12 * (a2 >> 1) + 12;
              result = -1LL - v16;
              a2 += -1LL - v16;
            }
            else
            {
              a2 >>= 1;
            }
          }
          v2 = v75;
LABEL_30:
          while ( 2 )
          {
            v17 = 0x7FFFFFFFFFFFFFFFLL;
            if ( v10 == v13 )
              return result;
            result = *((_QWORD *)v10 + 4);
            v18 = (char *)*((_QWORD *)v10 + 3);
            if ( v18 == (char *)result )
              goto LABEL_35;
            do
            {
              if ( *(_DWORD *)v18 == *((_DWORD *)v2 + 2) )
                break;
              v18 += 48;
            }
            while ( v18 != (char *)result );
            if ( v18 == (char *)result )
            {
LABEL_35:
              LOWORD(v73) = GUID_WCM_CS_BLOCKER_GEN.Data2;
              LODWORD(v74) = *(_DWORD *)&GUID_WCM_CS_BLOCKER_GEN.Data4[1];
              LOWORD(v72) = *(_WORD *)&GUID_WCM_CS_BLOCKER_GEN.Data4[5];
              v86[0] = 0;
              v19 = ULongToUShort(*v10, v86);
              if ( v19 < 0 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0x132,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
                  (const char *)(unsigned int)v19,
                  SourceString);
              v20 = v86[0];
              v2 = v75;
              v21 = v75[8];
              LOBYTE(v86[0]) = v21;
              a2 = *((unsigned int *)v75 + 2);
              v78 = *((_DWORD *)v75 + 2);
              v18 = (char *)*((_QWORD *)v10 + 4);
              v22 = (char *)*((_QWORD *)v10 + 5);
              if ( v18 == v22 )
              {
                v23 = *((_QWORD *)v10 + 3);
                v24 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)&v18[-v23] >> 4);
                if ( v24 == 0x555555555555555LL )
                  std::vector<_WCM_SELECTABLE_CONNECTION_DETAIL>::_Xlength();
                v25 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)&v22[-v23] >> 4);
                if ( v25 > 0x555555555555555LL - (v25 >> 1) )
LABEL_126:
                  std::_Throw_bad_array_new_length();
                v77 = v24 + 1;
                v26 = v25 + (v25 >> 1);
                v27 = v24 + 1;
                if ( v26 >= v24 + 1 )
                  v27 = v26;
                if ( v27 > 0x555555555555555LL )
                  std::_Throw_bad_array_new_length();
                v28 = 48 * v27;
                if ( 48 * v27 )
                {
                  if ( v28 < 0x1000 )
                  {
                    v29 = operator new(48 * v27);
                  }
                  else
                  {
                    if ( v28 + 39 < v28 )
                      goto LABEL_126;
                    v30 = operator new(v28 + 39);
                    if ( !v30 )
LABEL_111:
                      __fastfail(5u);
                    v29 = (_QWORD *)(((unsigned __int64)v30 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                    *(v29 - 1) = v30;
                  }
                }
                else
                {
                  v29 = 0;
                }
                v82 = (__int64)&v18[-v23] / 48;
                v31 = (char *)&v29[6 * v82];
                *(_DWORD *)v31 = v78;
                *((_DWORD *)v31 + 1) = GUID_WCM_CS_BLOCKER_GEN.Data1;
                *((_WORD *)v31 + 4) = v73;
                *((_WORD *)v31 + 5) = v20;
                v31[12] = v86[0];
                *(_DWORD *)(v31 + 13) = v74;
                *(_WORD *)(v31 + 17) = v72;
                v31[19] = GUID_WCM_CS_BLOCKER_GEN.Data4[7];
                *((_DWORD *)v31 + 5) = 0;
                *((_QWORD *)v31 + 3) = 0;
                *((_QWORD *)v31 + 4) = 0;
                *((_QWORD *)v31 + 5) = 0;
                v32 = (char *)*((_QWORD *)v10 + 4);
                v33 = v29;
                v34 = (char *)*((_QWORD *)v10 + 3);
                if ( v18 != v32 )
                {
                  std::_Uninitialized_move<SleepStudy::BlockerNode *>(v34, v18, v29);
                  v33 = (_QWORD *)(v35 + 48);
                  v32 = (char *)*((_QWORD *)v10 + 4);
                  v34 = v18;
                }
                std::_Uninitialized_move<SleepStudy::BlockerNode *>(v34, v32, v33);
                v37 = *((_QWORD *)v10 + 3);
                if ( v37 )
                {
                  for ( i = *((_QWORD *)v10 + 4); v37 != i; v37 += 48 )
                  {
                    if ( *(_QWORD *)(v37 + 32) )
                      ((void (*)(void))SleepstudyHelperBlockerActiveDereference)();
                    if ( *(_QWORD *)(v37 + 24) )
                      ((void (*)(void))SleepstudyHelperDestroyBlocker)();
                  }
                  v39 = *((_QWORD *)v10 + 3);
                  v40 = (const struct std::nothrow_t *)(16 * ((*((_QWORD *)v10 + 5) - v39) >> 4));
                  if ( (unsigned __int64)v40 < 0x1000 )
                  {
                    v41 = (void *)*((_QWORD *)v10 + 3);
                  }
                  else
                  {
                    v41 = *(void **)(v39 - 8);
                    if ( (unsigned __int64)(v39 - (_QWORD)v41 - 8) > 0x1F )
                      goto LABEL_111;
                    v40 = (const struct std::nothrow_t *)((char *)v40 + 39);
                  }
                  operator delete(v41, v40);
                  v36 = v82;
                }
                *((_QWORD *)v10 + 3) = v29;
                *((_QWORD *)v10 + 4) = &v29[6 * v77];
                result = (__int64)&v29[v28 / 8];
                *((_QWORD *)v10 + 5) = &v29[v28 / 8];
                v18 = (char *)&v29[6 * v36];
                v2 = v75;
              }
              else
              {
                *(_DWORD *)v18 = a2;
                *((_DWORD *)v18 + 1) = GUID_WCM_CS_BLOCKER_GEN.Data1;
                *((_WORD *)v18 + 4) = GUID_WCM_CS_BLOCKER_GEN.Data2;
                *((_WORD *)v18 + 5) = v20;
                v18[12] = v21;
                *(_DWORD *)(v18 + 13) = *(_DWORD *)&GUID_WCM_CS_BLOCKER_GEN.Data4[1];
                *(_WORD *)(v18 + 17) = v72;
                v18[19] = GUID_WCM_CS_BLOCKER_GEN.Data4[7];
                result = 0;
                *((_DWORD *)v18 + 5) = 0;
                *((_QWORD *)v18 + 3) = 0;
                *((_QWORD *)v18 + 4) = 0;
                *((_QWORD *)v18 + 5) = 0;
                *((_QWORD *)v10 + 4) += 48LL;
              }
              v17 = 0x7FFFFFFFFFFFFFFFLL;
            }
            ++*((_QWORD *)v18 + 5);
            if ( *((_BYTE *)v10 + 20) )
            {
              v42 = v18 + 32;
              if ( !*((_QWORD *)v18 + 4) )
              {
                v43 = v18 + 24;
                if ( !*((_QWORD *)v18 + 3) )
                {
                  v44 = (const void *)PdcManager::EnumToString(*((unsigned int *)v2 + 2));
                  v49 = v44;
                  v79 = 0;
                  v80 = 0;
                  v81 = 0;
                  v50 = -1;
                  do
                    ++v50;
                  while ( *((_BYTE *)v44 + v50) );
                  if ( v50 > v46 )
                    std::_Xlen_string();
                  v51 = *v45;
                  v77 = *v45;
                  if ( v50 <= 0xF )
                  {
                    v80 = v50;
                    v81 = 15;
                    memcpy_0(&v79, v44, v50);
                    *((_BYTE *)&v79 + v50) = 0;
                    goto LABEL_87;
                  }
                  v51 = v50 | 0xF;
                  if ( (v50 | 0xF) > v46 )
                  {
                    v51 = v46;
                    v52 = v47;
                    goto LABEL_76;
                  }
                  if ( v51 < 0x16 )
                    v51 = v48;
                  v55 = v51 + 1;
                  if ( v51 == -1 )
                  {
                    v54 = 0;
                  }
                  else if ( v55 < 0x1000 )
                  {
                    v54 = operator new(v55);
                  }
                  else
                  {
                    v52 = v51 + 40;
                    if ( v51 + 40 < v51 + 1 )
                      std::_Throw_bad_array_new_length();
LABEL_76:
                    v53 = operator new(v52);
                    if ( !v53 )
                      goto LABEL_111;
                    v54 = (_QWORD *)(((unsigned __int64)v53 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                    *(v54 - 1) = v53;
                  }
                  *(_QWORD *)&v79 = v54;
                  v80 = v50;
                  v81 = v51;
                  memcpy_0(v54, v49, v50);
                  *((_BYTE *)v54 + v50) = 0;
                  v43 = v18 + 24;
                  LODWORD(v51) = v77;
LABEL_87:
                  v56 = ctl::ctString::convert_to_wstring(v83, &v79);
                  if ( *(_QWORD *)(v56 + 24) > 7u )
                    v56 = *(_QWORD *)v56;
                  v57 = (int *)(v18 + 4);
                  blocker = (_QWORD *)SleepStudy::library_t::make_blocker(
                                        (int)v51 + 64,
                                        (int)v101,
                                        (int)v10 + 4,
                                        (int)v18 + 4,
                                        (PCWSTR)v56);
                  v59 = blocker;
                  if ( v43 != blocker )
                  {
                    v60 = *blocker;
                    v61 = *((_QWORD *)v18 + 3);
                    if ( v61 )
                    {
                      LastError = GetLastError();
                      SleepstudyHelperDestroyBlocker(v61);
                      SetLastError(LastError);
                      v57 = (int *)(v18 + 4);
                    }
                    *((_QWORD *)v18 + 3) = v60;
                    *v59 = 0;
                    v43 = v18 + 24;
                  }
                  if ( *(_QWORD *)v101 )
                    SleepstudyHelperDestroyBlocker(*(_QWORD *)v101);
                  if ( v84 > 7 )
                  {
                    v63 = (const struct std::nothrow_t *)(2 * v84 + 2);
                    v64 = (void *)v83[0];
                    if ( (unsigned __int64)v63 >= 0x1000 )
                    {
                      if ( (unsigned __int64)(v83[0] - *(_QWORD *)(v83[0] - 8LL) - 8LL) > 0x1F )
                        __fastfail(5u);
                      v63 = (const struct std::nothrow_t *)(2 * v84 + 41);
                      v64 = *(void **)(v83[0] - 8LL);
                    }
                    operator delete(v64, v63);
                  }
                  v83[2] = 0;
                  v84 = 7;
                  LOWORD(v83[0]) = 0;
                  a2 = v81;
                  if ( v81 > 0xF )
                  {
                    v65 = (const struct std::nothrow_t *)(v81 + 1);
                    v66 = (void *)v79;
                    if ( v81 + 1 >= 0x1000 )
                    {
                      if ( (unsigned __int64)(v79 - *(_QWORD *)(v79 - 8) - 8) > 0x1F )
                        goto LABEL_111;
                      v65 = (const struct std::nothrow_t *)(v81 + 40);
                      v66 = *(void **)(v79 - 8);
                    }
                    operator delete(v66, v65);
                  }
                  v80 = 0;
                  v81 = 15;
                  LOBYTE(v79) = 0;
                  if ( (unsigned int)dword_18013A120 > 4 )
                  {
                    LODWORD(v74) = *(_DWORD *)v18;
                    v95 = v57;
                    v96 = 16;
                    v93 = &v74;
                    v94 = 4;
                    v104[0] = 184549376;
                    v104[1] = 4;
                    v105 = 0;
                    v87 = off_18013A128;
                    v88 = *(unsigned __int16 *)off_18013A128;
                    v89 = 2;
                    v90 = (char *)&dword_180119AFC;
                    v91 = 93;
                    v92 = 1;
                    SourceString = 4;
                    EtwEventWriteTransfer(RegHandle, v104, 0, 0);
                  }
                  v42 = v18 + 32;
                }
                active = SleepstudyHelperBlockerActiveReference(*v43, a2, v2, v17);
                if ( active < 0 )
                  wil::details::in1diag3::_Throw_NtStatus(
                    retaddr,
                    (void *)0x38,
                    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
                    (const char *)(unsigned int)active,
                    SourceString);
                v68 = *v43;
                v76 |= 1u;
                if ( v42 == &v85 )
                {
                  if ( v68 )
                    SleepstudyHelperBlockerActiveDereference(v68);
                }
                else
                {
                  v69 = *(_QWORD *)v42;
                  if ( *(_QWORD *)v42 )
                  {
                    v70 = GetLastError();
                    SleepstudyHelperBlockerActiveDereference(v69);
                    SetLastError(v70);
                    v42 = v18 + 32;
                  }
                  *(_QWORD *)v42 = v68;
                }
                result = (unsigned int)dword_18013A120;
                if ( (unsigned int)dword_18013A120 > 4 )
                {
                  v77 = *((_QWORD *)v18 + 5);
                  LODWORD(v74) = *(_DWORD *)v18;
                  v97 = &v77;
                  v98 = 8;
                  v95 = (int *)(v18 + 4);
                  v96 = 16;
                  v93 = &v74;
                  v94 = 4;
                  *(_OWORD *)v103 = 0x40B000000uLL;
                  v87 = off_18013A128;
                  v88 = *(unsigned __int16 *)off_18013A128;
                  v89 = 2;
                  v90 = byte_180119A89;
                  v91 = 103;
                  v92 = 1;
                  SourceString = 5;
                  result = EtwEventWriteTransfer(RegHandle, v103, 0, 0);
                }
              }
            }
            v10 += 12;
            v2 = v75;
            continue;
          }
        }
        a2 >>= 1;
      }
      else
      {
        v10 = v12 + 12;
        result = -1LL - v11;
        a2 += -1LL - v11;
      }
      if ( (__int64)a2 <= 0 )
        goto LABEL_17;
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x3CB,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
             (const char *)0x7FFFFFFFFFFFFFFFLL);
  }
  return result;
}

```

## disassembly

```asm
0x180043bb0  mov     r11, rsp
0x180043bb3  mov     [r11+10h], rbx
0x180043bb7  mov     [r11+18h], rsi
0x180043bbb  push    rdi
0x180043bbc  push    r12
0x180043bbe  push    r13
0x180043bc0  push    r14
0x180043bc2  push    r15
0x180043bc4  sub     rsp, 170h
0x180043bcb  mov     rax, cs:__security_cookie
0x180043bd2  xor     rax, rsp
0x180043bd5  mov     [rsp+198h+var_38], rax
0x180043bdd  mov     r8, rcx
0x180043be0  mov     [rsp+198h+var_150], rcx
0x180043be5  xor     r12d, r12d
0x180043be8  mov     [rsp+198h+var_148], r12d
0x180043bed  mov     eax, cs:dword_18013A120
0x180043bf3  cmp     eax, 4
0x180043bf6  jbe     loc_180043D82
0x180043bfc  mov     rax, [rcx]
0x180043bff  mov     ecx, r12d
0x180043c02  xorps   xmm0, xmm0
0x180043c05  movups  xmmword ptr [r11-60h], xmm0
0x180043c0a  cmp     [rax+38h], r12b
0x180043c0e  jz      short loc_180043C24
0x180043c10  movups  xmm1, xmmword ptr [rax+20h]
0x180043c14  movsd   xmm0, qword ptr [rax+30h]
0x180043c19  movsd   qword ptr [r11-58h], xmm0
0x180043c1f  movq    rcx, xmm1
0x180043c24  mov     [rsp+198h+var_158], rcx
0x180043c29  lea     rbx, [r8+10h]
0x180043c2d  xorps   xmm0, xmm0
0x180043c30  cmp     byte ptr [rbx+10h], 0
0x180043c34  jz      short loc_180043C43
0x180043c36  movups  xmm0, xmmword ptr [rbx]
0x180043c39  movaps  [rsp+198h+var_68], xmm0
0x180043c41  jmp     short loc_180043C4C
0x180043c43  movdqa  [rsp+198h+var_68], xmm0
0x180043c4c  mov     eax, [r8+0Ch]
0x180043c50  mov     [rsp+198h+var_15C], eax
0x180043c54  mov     eax, [r8+8]
0x180043c58  mov     [rsp+198h+var_160], eax
0x180043c5c  lea     rax, [rsp+198h+var_158]
0x180043c61  mov     [rsp+198h+var_88], rax
0x180043c69  mov     [rsp+198h+var_80], 8
0x180043c75  lea     rax, [rsp+198h+var_68]
0x180043c7d  mov     [rsp+198h+var_98], rax
0x180043c85  mov     [rsp+198h+var_90], 10h
0x180043c91  lea     rax, [rsp+198h+var_15C]
0x180043c96  mov     [rsp+198h+var_A8], rax
0x180043c9e  mov     [rsp+198h+var_A0], 4
0x180043caa  lea     rax, [rsp+198h+var_160]
0x180043caf  mov     [rsp+198h+var_B8], rax
0x180043cb7  mov     [rsp+198h+var_B0], 4
0x180043cc3  mov     [rsp+198h+var_78], 0B000000h
0x180043cce  movzx   eax, cs:word_1801199FB
0x180043cd5  mov     [rsp+198h+var_78+4], eax
0x180043cdc  mov     [rsp+198h+var_70], r12
0x180043ce4  mov     rax, cs:off_18013A128
0x180043ceb  mov     [rsp+198h+var_D8], rax
0x180043cf3  movzx   eax, word ptr [rax]
0x180043cf6  mov     [rsp+198h+var_D0], eax
0x180043cfd  mov     [rsp+198h+var_CC], 2
0x180043d08  lea     rax, byte_180119A05
0x180043d0f  mov     [rsp+198h+var_C8], rax
0x180043d17  mov     [rsp+198h+var_C0], 78h ; 'x'
0x180043d22  mov     [rsp+198h+var_BC], 1
0x180043d2d  lea     rax, _TraceLoggingMetadataEnd
0x180043d34  lea     rdi, _TraceLoggingMetadata
0x180043d3b  sub     eax, edi
0x180043d3d  mov     dword ptr [rsp+198h+var_E0], eax
0x180043d44  mov     eax, dword ptr [rsp+198h+var_E0]
0x180043d4b  lea     rax, [rsp+198h+var_D8]
0x180043d53  mov     [rsp+198h+var_170], rax
0x180043d58  mov     dword ptr [rsp+198h+SourceString], 6
0x180043d60  xor     r9d, r9d
0x180043d63  xor     r8d, r8d
0x180043d66  lea     rdx, [rsp+198h+var_78]
0x180043d6e  mov     rcx, cs:RegHandle
0x180043d75  call    cs:__imp_EtwEventWriteTransfer
0x180043d7b  mov     r8, [rsp+198h+var_150]
0x180043d80  jmp     short loc_180043D86
0x180043d82  lea     rbx, [rcx+10h]
0x180043d86  mov     rsi, [r8]
0x180043d89  cmp     byte ptr [r8+20h], 0
0x180043d8e  jz      loc_180043EA9
0x180043d94  cmp     byte ptr [rbx+10h], 0
0x180043d98  jz      loc_180044792
0x180043d9e  mov     rdx, rbx; struct _GUID *
0x180043da1  mov     rcx, rsi; this
0x180043da4  call    ?InterfaceIndexFromGuid@Singleton@SleepStudy@@AEAA@AEBU_GUID@@@Z; SleepStudy::Singleton::InterfaceIndexFromGuid(_GUID const &)
0x180043da9  mov     r10d, eax
0x180043dac  mov     r8, [rsp+198h+var_150]
0x180043db1  mov     rcx, [r8]
0x180043db4  mov     rdi, [rcx+48h]
0x180043db8  mov     rdx, [rcx+50h]
0x180043dbc  sub     rdx, rdi
0x180043dbf  sar     rdx, 4
0x180043dc3  mov     r9, 0AAAAAAAAAAAAAAABh
0x180043dcd  imul    rdx, r9
0x180043dd1  test    rdx, rdx
0x180043dd4  jle     short loc_180043E13
0x180043dd6  nop     word ptr [rax+rax+00000000h]
0x180043de0  mov     rcx, rdx
0x180043de3  shr     rcx, 1
0x180043de6  lea     rsi, [rcx+rcx*2]
0x180043dea  shl     rsi, 4
0x180043dee  add     rsi, rdi
0x180043df1  cmp     [rsi], r10d
0x180043df4  jnb     short loc_180043E09
0x180043df6  lea     rdi, [rsi+30h]
0x180043dfa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180043e01  sub     rax, rcx
0x180043e04  add     rdx, rax
0x180043e07  jmp     short loc_180043E0E
0x180043e09  jbe     short loc_180043E1B
0x180043e0b  mov     rdx, rcx
0x180043e0e  test    rdx, rdx
0x180043e11  jg      short loc_180043DE0
0x180043e13  mov     rsi, rdi
0x180043e16  jmp     loc_180043EB1
0x180043e1b  mov     r9, rcx
0x180043e1e  test    rcx, rcx
0x180043e21  jz      short loc_180043E55
0x180043e23  mov     r8, r9
0x180043e26  shr     r8, 1
0x180043e29  lea     r11, [r8+r8*2]
0x180043e2d  add     r11, r11
0x180043e30  cmp     [rdi+r11*8], r10d
0x180043e34  jnb     short loc_180043E4D
0x180043e36  lea     rdi, [rdi+r11*8]
0x180043e3a  add     rdi, 30h ; '0'
0x180043e3e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180043e45  sub     rax, r8
0x180043e48  add     r9, rax
0x180043e4b  jmp     short loc_180043E50
0x180043e4d  mov     r9, r8
0x180043e50  test    r9, r9
0x180043e53  jg      short loc_180043E23
0x180043e55  sub     rdx, rcx
0x180043e58  dec     rdx
0x180043e5b  add     rsi, 30h ; '0'
0x180043e5f  test    rdx, rdx
0x180043e62  jle     short loc_180043EA2
0x180043e64  nop     dword ptr [rax+00h]
0x180043e68  nop     dword ptr [rax+rax+00000000h]
0x180043e70  mov     rcx, rdx
0x180043e73  shr     rcx, 1
0x180043e76  lea     r8, [rcx+rcx*2]
0x180043e7a  add     r8, r8
0x180043e7d  cmp     r10d, [rsi+r8*8]
0x180043e81  jnb     short loc_180043E88
0x180043e83  mov     rdx, rcx
0x180043e86  jmp     short loc_180043E9D
0x180043e88  lea     rsi, [rsi+r8*8]
0x180043e8c  add     rsi, 30h ; '0'
0x180043e90  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180043e97  sub     rax, rcx
0x180043e9a  add     rdx, rax
0x180043e9d  test    rdx, rdx
0x180043ea0  jg      short loc_180043E70
0x180043ea2  mov     r8, [rsp+198h+var_150]
0x180043ea7  jmp     short loc_180043EB1
0x180043ea9  mov     rdi, [rsi+48h]
0x180043ead  mov     rsi, [rsi+50h]
0x180043eb1  mov     r11d, 16h
0x180043eb7  mov     r10, 8000000000000027h
0x180043ec1  mov     r9, 7FFFFFFFFFFFFFFFh
0x180043ecb  cmp     rdi, rsi
0x180043ece  jnz     short loc_180043EFD
0x180043ed0  mov     rcx, [rsp+198h+var_38]
0x180043ed8  xor     rcx, rsp; StackCookie
0x180043edb  call    __security_check_cookie
0x180043ee0  lea     r11, [rsp+198h+var_28]
0x180043ee8  mov     rbx, [r11+38h]
0x180043eec  mov     rsi, [r11+40h]
0x180043ef0  mov     rsp, r11
0x180043ef3  pop     r15
0x180043ef5  pop     r14
0x180043ef7  pop     r13
0x180043ef9  pop     r12
0x180043efb  pop     rdi
0x180043efc  retn
0x180043efd  mov     ecx, [r8+8]
0x180043f01  mov     rax, [rdi+20h]
0x180043f05  mov     rbx, [rdi+18h]
0x180043f09  cmp     rbx, rax
0x180043f0c  jz      short loc_180043F26
0x180043f0e  xchg    ax, ax
0x180043f10  cmp     [rbx], ecx
0x180043f12  jz      short loc_180043F1D
0x180043f14  add     rbx, 30h ; '0'
0x180043f18  cmp     rbx, rax
0x180043f1b  jnz     short loc_180043F10
0x180043f1d  cmp     rbx, rax
0x180043f20  jnz     loc_18004425D
0x180043f26  mov     r14d, cs:GUID_WCM_CS_BLOCKER_GEN.Data1
0x180043f2d  mov     [rsp+198h+var_164], r14d
0x180043f32  movzx   r15d, cs:GUID_WCM_CS_BLOCKER_GEN.Data2
0x180043f3a  mov     word ptr [rsp+198h+var_15C], r15w
0x180043f40  mov     r13d, dword ptr cs:GUID_WCM_CS_BLOCKER_GEN.Data4+1
0x180043f47  mov     dword ptr [rsp+198h+var_158], r13d
0x180043f4c  movzx   eax, word ptr cs:GUID_WCM_CS_BLOCKER_GEN.Data4+5
0x180043f53  mov     word ptr [rsp+198h+var_160], ax
0x180043f58  movzx   eax, cs:GUID_WCM_CS_BLOCKER_GEN.Data4+7
0x180043f5f  mov     [rsp+198h+var_168], al
0x180043f63  mov     [rsp+198h+var_E0], r12w
0x180043f6c  lea     rdx, [rsp+198h+var_E0]; unsigned __int16 *
0x180043f74  mov     ecx, [rdi]; unsigned int
0x180043f76  call    ?ULongToUShort@@YAJKPEAG@Z; ULongToUShort(ulong,ushort *)
0x180043f7b  mov     rcx, [rsp+198h]; this
0x180043f83  test    eax, eax
0x180043f85  js      loc_180044797
0x180043f8b  movzx   r12d, [rsp+198h+var_E0]
0x180043f94  mov     r8, [rsp+198h+var_150]
0x180043f99  movzx   eax, byte ptr [r8+8]
0x180043f9e  mov     byte ptr [rsp+198h+var_E0], al
0x180043fa5  mov     edx, [r8+8]
0x180043fa9  mov     [rsp+198h+var_138], edx
0x180043fad  mov     rbx, [rdi+20h]
0x180043fb1  mov     rcx, [rdi+28h]
0x180043fb5  cmp     rbx, rcx
0x180043fb8  jz      short loc_180044000
0x180043fba  mov     [rbx], edx
0x180043fbc  mov     [rbx+4], r14d
0x180043fc0  mov     [rbx+8], r15w
0x180043fc5  mov     [rbx+0Ah], r12w
0x180043fca  mov     [rbx+0Ch], al
0x180043fcd  mov     [rbx+0Dh], r13d
0x180043fd1  movzx   eax, word ptr [rsp+198h+var_160]
0x180043fd6  mov     [rbx+11h], ax
0x180043fda  movzx   eax, [rsp+198h+var_168]
0x180043fdf  mov     [rbx+13h], al
0x180043fe2  xor     eax, eax
0x180043fe4  mov     [rbx+14h], eax
0x180043fe7  xor     r12d, r12d
0x180043fea  mov     [rbx+18h], r12
0x180043fee  mov     [rbx+20h], r12
0x180043ff2  mov     [rbx+28h], r12
0x180043ff6  add     qword ptr [rdi+20h], 30h ; '0'
0x180043ffb  jmp     loc_180044243
0x180044000  mov     r15, [rdi+18h]
0x180044004  mov     rdx, rbx
0x180044007  sub     rdx, r15
0x18004400a  sar     rdx, 4
0x18004400e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180044018  imul    rdx, rax
0x18004401c  mov     r9, 555555555555555h
0x180044026  cmp     rdx, r9
0x180044029  jz      loc_1800447AB
0x18004402f  sub     rcx, r15
0x180044032  sar     rcx, 4
0x180044036  imul    rcx, rax
0x18004403a  mov     r8, rcx
0x18004403d  shr     r8, 1
0x180044040  mov     rax, r9
0x180044043  sub     rax, r8
0x180044046  cmp     rcx, rax
0x180044049  ja      loc_1800447BA
0x18004404f  inc     rdx
0x180044052  mov     [rsp+198h+var_140], rdx
0x180044057  lea     rax, [rcx+r8]
0x18004405b  mov     rcx, rdx
0x18004405e  cmp     rax, rdx
0x180044061  cmovnb  rcx, rax
0x180044065  cmp     rcx, r9
0x180044068  ja      loc_1800447B0
0x18004406e  lea     r13, [rcx+rcx*2]
0x180044072  shl     r13, 4
0x180044076  test    r13, r13
0x180044079  jnz     short loc_180044080
0x18004407b  xor     r14d, r14d
0x18004407e  jmp     short loc_1800440BD
0x180044080  cmp     r13, 1000h
0x180044087  jb      short loc_1800440B2
0x180044089  lea     rcx, [r13+27h]; Size
0x18004408d  cmp     rcx, r13
0x180044090  jbe     loc_1800447BA
0x180044096  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004409b  test    rax, rax
0x18004409e  jz      loc_180044610
0x1800440a4  lea     r14, [rax+27h]
0x1800440a8  and     r14, 0FFFFFFFFFFFFFFE0h
0x1800440ac  mov     [r14-8], rax
0x1800440b0  jmp     short loc_1800440BD
0x1800440b2  mov     rcx, r13; Size
0x1800440b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800440ba  mov     r14, rax
0x1800440bd  mov     rcx, rbx
0x1800440c0  sub     rcx, r15
0x1800440c3  mov     rax, 2AAAAAAAAAAAAAABh
0x1800440cd  imul    rcx
0x1800440d0  mov     r11, rdx
0x1800440d3  sar     r11, 3
0x1800440d7  mov     rcx, r11
0x1800440da  shr     rcx, 3Fh
0x1800440de  add     r11, rcx
0x1800440e1  mov     [rsp+198h+var_110], r11
0x1800440e9  lea     r10, [r11+r11*2]
0x1800440ed  shl     r10, 4
  ... truncated ...
```
