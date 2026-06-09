# CUserModeHangReport::PrepareSnapshotDumper(void)

- ea: `0x1400251c0`
- end: `0x140025777`
- name: `?PrepareSnapshotDumper@CUserModeHangReport@@AEAAJXZ`
- size: `1463`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140026360`
- `0x1400268e0`

## callees

- `0x1400030f8`
- `0x1400121e8`
- `0x140012994`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x14001ffa4`
- `0x14002430c`
- `0x1400251c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002546e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400254b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002546e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400254b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002540a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140025436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002551d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002540a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140025436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002551d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140025419`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140025419`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140025448`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14002552f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140025448`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14002552f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400253fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140025580`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140025689`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400253fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140025580`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140025689`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002565f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002565f`
- `wer!WerpInitializeImageCache` at `0x1400252fe`
- `wer!WerpInitializeImageCache` at `0x1400252fe`
- `wer!WerpAuxmdFree` at `0x14002564c`
- `wer!WerpAuxmdFree` at `0x14002564c`
- `wer!WerpUnmapProcessViews` at `0x1400255af`
- `wer!WerpUnmapProcessViews` at `0x1400255af`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x140025639`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x140025639`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140025370`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140025370`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x1400253c8`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x1400253c8`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::PrepareSnapshotDumper(CUserModeHangReport *this)
{
  struct HPSS__ *SnapshotForProcess; // r15
  __int64 result; // rax
  int IsNamedEventSet; // eax
  unsigned int v5; // edx
  int v6; // eax
  signed int v7; // esi
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r14d
  HANDLE v12; // rax
  DWORD v13; // eax
  DWORD LastError; // eax
  CUserModeHangReport *v15; // rcx
  __int64 v16; // rdx
  HANDLE v17; // rax
  DWORD v18; // eax
  void *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  bool v31; // [rsp+28h] [rbp-71h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-69h] BYREF
  LARGE_INTEGER v33; // [rsp+38h] [rbp-61h] BYREF
  _OWORD v34[11]; // [rsp+40h] [rbp-59h] BYREF
  void *v35; // [rsp+100h] [rbp+67h] BYREF
  __int64 v36; // [rsp+108h] [rbp+6Fh] BYREF

  SnapshotForProcess = CHangReport::FindSnapshotForProcess(this, **((_DWORD **)this + 2988));
  v35 = 0;
  result = *((unsigned int *)this + 9246);
  v36 = 0;
  if ( (int)result >= 1 )
  {
    if ( !SnapshotForProcess )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
      }
      result = 2147943568LL;
LABEL_7:
      *((_DWORD *)this + 9246) = result;
      return result;
    }
    if ( UtilRegGetDWORD(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
           L"FailSnapshotDumper",
           0,
           0,
           v31) )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
      }
      result = 2147943525LL;
      goto LABEL_7;
    }
    if ( !*((_DWORD *)this + 10544) )
    {
      if ( (unsigned int)UtilIsNamedEventSet(L"BD") != 1
        || (unsigned int)UtilIsNamedEventSet(L"DF") != 1
        || (IsNamedEventSet = UtilIsNamedEventSet(L"JL"), v5 = 0x8000000, IsNamedEventSet != 1) )
      {
        v5 = 0x2000000;
      }
      v6 = WerpInitializeImageCache((CUserModeHangReport *)((char *)this + 41368), v5);
      v7 = v6;
      *((_DWORD *)this + 10544) = v6 >= 0;
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
            (unsigned int)v6);
        }
LABEL_22:
        *((_DWORD *)this + 9246) = v7;
        return (unsigned int)v7;
      }
    }
    v35 = 0;
    v7 = PssQuerySnapshot(SnapshotForProcess, 1, &v35, 8);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 115;
LABEL_27:
        WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, (unsigned int)v7);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    v7 = PssWalkMarkerCreate(0, &v36);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 116;
        goto LABEL_27;
      }
LABEL_28:
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_22;
    }
    QueryPerformanceCounter(&PerformanceCount);
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority == 0x7FFFFFFF )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, LastError);
      }
    }
    else
    {
      v12 = GetCurrentThread();
      if ( !SetThreadPriority(v12, -1) )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v13 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v13);
        }
        ThreadPriority = 0x7FFFFFFF;
      }
    }
    v7 = CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(this, v35);
    if ( v7 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_62;
      }
      v16 = 119;
LABEL_61:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, (unsigned int)v7);
LABEL_62:
      v20 = v36;
      *((_DWORD *)this + 9246) = v7;
      PssWalkMarkerFree(v20);
      WerpAuxmdFree((char *)this + 37176);
      DeleteFileW((LPCWSTR)this + 20820);
      return (unsigned int)v7;
    }
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v17 = GetCurrentThread();
      if ( !SetThreadPriority(v17, ThreadPriority)
        && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v18);
      }
    }
    QueryPerformanceCounter(&v33);
    v19 = v35;
    *((_QWORD *)this + 5270) = v33.QuadPart - PerformanceCount.QuadPart;
    v7 = WerpUnmapProcessViews((char *)this + 37144, v19, 3);
    if ( v7 >= 0 )
    {
      if ( !*((_DWORD *)this + 9293) )
      {
        QueryPerformanceCounter(&PerformanceCount);
        *((_QWORD *)this + 5271) = PerformanceCount.QuadPart - v33.QuadPart;
        memset_0(v34, 0, 0x90u);
        v21 = *((_QWORD *)this + 4643);
        v22 = v34[0];
        *((_DWORD *)this + 9246) = 0;
        v23 = v34[1];
        *((_OWORD *)this + 2312) = v22;
        v24 = v34[2];
        *((_OWORD *)this + 2313) = v23;
        v25 = v34[3];
        *((_OWORD *)this + 2314) = v24;
        v26 = v34[4];
        *((_OWORD *)this + 2315) = v25;
        v27 = v34[5];
        *((_OWORD *)this + 2316) = v26;
        v28 = v34[6];
        *((_OWORD *)this + 2317) = v27;
        v29 = v34[7];
        *((_OWORD *)this + 2318) = v28;
        v30 = v34[8];
        *((_OWORD *)this + 2319) = v29;
        *((_OWORD *)this + 2320) = v30;
        *((_QWORD *)this + 4625) = v21;
        *((_DWORD *)this + 9252) = *((_DWORD *)this + 9288);
        *((_QWORD *)this + 4627) = (char *)this + 37176;
        *((_QWORD *)this + 4629) = (char *)this + 41368;
        *((_QWORD *)this + 4631) = v36;
        result = 0;
        *((_DWORD *)this + 9248) = 3;
        *((_QWORD *)this + 4630) = SnapshotForProcess;
        return result;
      }
      v7 = -2147023672;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
        goto LABEL_62;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_58;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
    }
    v15 = WPP_GLOBAL_Control;
LABEL_58:
    if ( v15 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
      goto LABEL_62;
    v16 = 122;
    goto LABEL_61;
  }
  return result;
}

```

## disassembly

```asm
0x1400251c0  mov     [rsp-8+arg_10], rbx
0x1400251c5  push    rbp
0x1400251c6  push    rsi
0x1400251c7  push    rdi
0x1400251c8  push    r14
0x1400251ca  push    r15
0x1400251cc  lea     rbp, [rsp-37h]
0x1400251d1  sub     rsp, 0D0h
0x1400251d8  mov     rdx, [rcx+5D60h]
0x1400251df  mov     rbx, rcx
0x1400251e2  mov     edx, [rdx]; unsigned int
0x1400251e4  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x1400251e9  mov     r15, rax
0x1400251ec  mov     [rbp+57h+arg_0], 0
0x1400251f4  mov     eax, [rbx+9078h]
0x1400251fa  mov     edi, 1
0x1400251ff  mov     [rbp+57h+arg_8], 0
0x140025207  cmp     eax, edi
0x140025209  jl      loc_14002566D
0x14002520f  test    r15, r15
0x140025212  jnz     short loc_140025251
0x140025214  mov     rcx, cs:WPP_GLOBAL_Control
0x14002521b  lea     rdi, WPP_GLOBAL_Control
0x140025222  cmp     rcx, rdi
0x140025225  jz      short loc_140025241
0x140025227  test    byte ptr [rcx+1Ch], 2
0x14002522b  jz      short loc_140025241
0x14002522d  mov     rcx, [rcx+10h]
0x140025231  lea     edx, [r15+70h]
0x140025235  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x14002523c  call    WPP_SF_
0x140025241  mov     eax, 80070490h
0x140025246  mov     [rbx+9078h], eax
0x14002524c  jmp     loc_14002566D
0x140025251  xor     r9d, r9d; unsigned int
0x140025254  mov     [rsp+0F0h+var_D0], 0; bool *
0x14002525d  lea     r8, aFailsnapshotdu; "FailSnapshotDumper"
0x140025264  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002526b  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x140025272  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140025277  test    eax, eax
0x140025279  jz      short loc_1400252B0
0x14002527b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025282  lea     rdi, WPP_GLOBAL_Control
0x140025289  cmp     rcx, rdi
0x14002528c  jz      short loc_1400252A9
0x14002528e  test    byte ptr [rcx+1Ch], 4
0x140025292  jz      short loc_1400252A9
0x140025294  mov     rcx, [rcx+10h]
0x140025298  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x14002529f  mov     edx, 71h ; 'q'
0x1400252a4  call    WPP_SF_
0x1400252a9  mov     eax, 80070465h
0x1400252ae  jmp     short loc_140025246
0x1400252b0  cmp     dword ptr [rbx+0A4C0h], 0
0x1400252b7  jnz     loc_140025359
0x1400252bd  lea     rcx, aBd; "BD"
0x1400252c4  call    UtilIsNamedEventSet
0x1400252c9  cmp     eax, edi
0x1400252cb  jnz     short loc_1400252F2
0x1400252cd  lea     rcx, aDf_0; "DF"
0x1400252d4  call    UtilIsNamedEventSet
0x1400252d9  cmp     eax, edi
0x1400252db  jnz     short loc_1400252F2
0x1400252dd  lea     rcx, aJl; "JL"
0x1400252e4  call    UtilIsNamedEventSet
0x1400252e9  mov     edx, 8000000h
0x1400252ee  cmp     eax, edi
0x1400252f0  jz      short loc_1400252F7
0x1400252f2  mov     edx, 2000000h
0x1400252f7  lea     rcx, [rbx+0A198h]
0x1400252fe  call    cs:__imp_?WerpInitializeImageCache@@YAJPEAUWERP_IMAGE_CACHE@@K@Z; WerpInitializeImageCache(WERP_IMAGE_CACHE *,ulong)
0x140025305  nop     dword ptr [rax+rax+00h]
0x14002530a  mov     ecx, eax
0x14002530c  mov     esi, eax
0x14002530e  not     ecx
0x140025310  shr     ecx, 1Fh
0x140025313  mov     [rbx+0A4C0h], ecx
0x140025319  test    eax, eax
0x14002531b  jns     short loc_140025359
0x14002531d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025324  lea     rdi, WPP_GLOBAL_Control
0x14002532b  cmp     rcx, rdi
0x14002532e  jz      short loc_14002534E
0x140025330  test    byte ptr [rcx+1Ch], 2
0x140025334  jz      short loc_14002534E
0x140025336  mov     rcx, [rcx+10h]
0x14002533a  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140025341  mov     edx, 72h ; 'r'
0x140025346  mov     r9d, eax
0x140025349  call    WPP_SF_d
0x14002534e  mov     [rbx+9078h], esi
0x140025354  jmp     loc_14002566B
0x140025359  mov     r9d, 8
0x14002535f  mov     [rbp+57h+arg_0], 0
0x140025367  lea     r8, [rbp+57h+arg_0]
0x14002536b  mov     edx, edi
0x14002536d  mov     rcx, r15
0x140025370  call    cs:__imp_PssQuerySnapshot
0x140025377  nop     dword ptr [rax+rax+00h]
0x14002537c  mov     esi, eax
0x14002537e  test    eax, eax
0x140025380  jz      short loc_1400253C2
0x140025382  mov     rcx, cs:WPP_GLOBAL_Control
0x140025389  lea     rdi, WPP_GLOBAL_Control
0x140025390  cmp     rcx, rdi
0x140025393  jz      short loc_1400253B3
0x140025395  test    byte ptr [rcx+1Ch], 2
0x140025399  jz      short loc_1400253B3
0x14002539b  mov     edx, 73h ; 's'
0x1400253a0  mov     rcx, [rcx+10h]
0x1400253a4  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400253ab  mov     r9d, esi
0x1400253ae  call    WPP_SF_d
0x1400253b3  test    esi, esi
0x1400253b5  jle     short loc_14002534E
0x1400253b7  movzx   esi, si
0x1400253ba  or      esi, 80070000h
0x1400253c0  jmp     short loc_14002534E
0x1400253c2  lea     rdx, [rbp+57h+arg_8]
0x1400253c6  xor     ecx, ecx
0x1400253c8  call    cs:__imp_PssWalkMarkerCreate
0x1400253cf  nop     dword ptr [rax+rax+00h]
0x1400253d4  mov     esi, eax
0x1400253d6  test    eax, eax
0x1400253d8  jz      short loc_1400253FA
0x1400253da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253e1  lea     rdi, WPP_GLOBAL_Control
0x1400253e8  cmp     rcx, rdi
0x1400253eb  jz      short loc_1400253B3
0x1400253ed  test    byte ptr [rcx+1Ch], 2
0x1400253f1  jz      short loc_1400253B3
0x1400253f3  mov     edx, 74h ; 't'
0x1400253f8  jmp     short loc_1400253A0
0x1400253fa  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1400253fe  call    cs:__imp_QueryPerformanceCounter
0x140025405  nop     dword ptr [rax+rax+00h]
0x14002540a  call    cs:__imp_GetCurrentThread
0x140025411  nop     dword ptr [rax+rax+00h]
0x140025416  mov     rcx, rax; hThread
0x140025419  call    cs:__imp_GetThreadPriority
0x140025420  nop     dword ptr [rax+rax+00h]
0x140025425  lea     rdi, WPP_GLOBAL_Control
0x14002542c  mov     r14d, eax
0x14002542f  cmp     eax, 7FFFFFFFh
0x140025434  jz      short loc_1400254A1
0x140025436  call    cs:__imp_GetCurrentThread
0x14002543d  nop     dword ptr [rax+rax+00h]
0x140025442  mov     rcx, rax; hThread
0x140025445  or      edx, 0FFFFFFFFh; nPriority
0x140025448  call    cs:__imp_SetThreadPriority
0x14002544f  nop     dword ptr [rax+rax+00h]
0x140025454  test    eax, eax
0x140025456  jnz     loc_1400254DE
0x14002545c  mov     rax, cs:WPP_GLOBAL_Control
0x140025463  cmp     rax, rdi
0x140025466  jz      short loc_140025499
0x140025468  test    byte ptr [rax+1Ch], 2
0x14002546c  jz      short loc_140025499
0x14002546e  call    cs:__imp_GetLastError
0x140025475  nop     dword ptr [rax+rax+00h]
0x14002547a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025481  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140025488  mov     edx, 75h ; 'u'
0x14002548d  mov     r9d, eax
0x140025490  mov     rcx, [rcx+10h]
0x140025494  call    WPP_SF_d
0x140025499  mov     r14d, 7FFFFFFFh
0x14002549f  jmp     short loc_1400254DE
0x1400254a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400254a8  cmp     rax, rdi
0x1400254ab  jz      short loc_1400254DE
0x1400254ad  test    byte ptr [rax+1Ch], 2
0x1400254b1  jz      short loc_1400254DE
0x1400254b3  call    cs:__imp_GetLastError
0x1400254ba  nop     dword ptr [rax+rax+00h]
0x1400254bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254c6  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400254cd  mov     edx, 76h ; 'v'
0x1400254d2  mov     r9d, eax
0x1400254d5  mov     rcx, [rcx+10h]
0x1400254d9  call    WPP_SF_d
0x1400254de  mov     rdx, [rbp+57h+arg_0]; void *
0x1400254e2  mov     rcx, rbx; this
0x1400254e5  call    ?DumpProcessDataSegsRegisteredBlocks@CUserModeHangReport@@AEAAJPEAX@Z; CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(void *)
0x1400254ea  mov     esi, eax
0x1400254ec  test    eax, eax
0x1400254ee  jns     short loc_140025514
0x1400254f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254f7  cmp     rcx, rdi
0x1400254fa  jz      loc_14002562F
0x140025500  test    byte ptr [rcx+1Ch], 2
0x140025504  jz      loc_14002562F
0x14002550a  mov     edx, 77h ; 'w'
0x14002550f  jmp     loc_14002561C
0x140025514  cmp     r14d, 7FFFFFFFh
0x14002551b  jz      short loc_14002557C
0x14002551d  call    cs:__imp_GetCurrentThread
0x140025524  nop     dword ptr [rax+rax+00h]
0x140025529  mov     rcx, rax; hThread
0x14002552c  mov     edx, r14d; nPriority
0x14002552f  call    cs:__imp_SetThreadPriority
0x140025536  nop     dword ptr [rax+rax+00h]
0x14002553b  test    eax, eax
0x14002553d  jnz     short loc_14002557C
0x14002553f  mov     rax, cs:WPP_GLOBAL_Control
0x140025546  cmp     rax, rdi
0x140025549  jz      short loc_14002557C
0x14002554b  test    byte ptr [rax+1Ch], 2
0x14002554f  jz      short loc_14002557C
0x140025551  call    cs:__imp_GetLastError
0x140025558  nop     dword ptr [rax+rax+00h]
0x14002555d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025564  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x14002556b  mov     edx, 78h ; 'x'
0x140025570  mov     r9d, eax
0x140025573  mov     rcx, [rcx+10h]
0x140025577  call    WPP_SF_d
0x14002557c  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x140025580  call    cs:__imp_QueryPerformanceCounter
0x140025587  nop     dword ptr [rax+rax+00h]
0x14002558c  mov     rax, qword ptr [rbp+57h+var_B8]
0x140025590  lea     r14, [rbx+9118h]
0x140025597  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x14002559b  mov     r8d, 3
0x1400255a1  mov     rdx, [rbp+57h+arg_0]
0x1400255a5  mov     rcx, r14
0x1400255a8  mov     [rbx+0A4B0h], rax
0x1400255af  call    cs:__imp_WerpUnmapProcessViews
0x1400255b6  nop     dword ptr [rax+rax+00h]
0x1400255bb  mov     esi, eax
0x1400255bd  test    eax, eax
0x1400255bf  js      short loc_140025605
0x1400255c1  mov     r9d, [rbx+9134h]
0x1400255c8  test    r9d, r9d
0x1400255cb  jz      loc_140025685
0x1400255d1  mov     esi, 800704C8h
0x1400255d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255dd  cmp     rcx, rdi
0x1400255e0  jz      short loc_14002562F
0x1400255e2  test    byte ptr [rcx+1Ch], 2
0x1400255e6  jz      short loc_14002560C
0x1400255e8  mov     rcx, [rcx+10h]
0x1400255ec  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400255f3  mov     edx, 79h ; 'y'
0x1400255f8  mov     dword ptr [rsp+0F0h+var_D0], 800704C8h
0x140025600  call    WPP_SF_Dd
0x140025605  mov     rcx, cs:WPP_GLOBAL_Control
0x14002560c  cmp     rcx, rdi
0x14002560f  jz      short loc_14002562F
0x140025611  test    byte ptr [rcx+1Ch], 2
0x140025615  jz      short loc_14002562F
0x140025617  mov     edx, 7Ah ; 'z'
0x14002561c  mov     rcx, [rcx+10h]
0x140025620  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140025627  mov     r9d, esi
0x14002562a  call    WPP_SF_d
0x14002562f  mov     rcx, [rbp+57h+arg_8]
0x140025633  mov     [rbx+9078h], esi
0x140025639  call    cs:__imp_PssWalkMarkerFree
0x140025640  nop     dword ptr [rax+rax+00h]
0x140025645  lea     rcx, [rbx+9138h]
0x14002564c  call    cs:__imp_WerpAuxmdFree
0x140025653  nop     dword ptr [rax+rax+00h]
0x140025658  lea     rcx, [rbx+0A2A8h]; lpFileName
0x14002565f  call    cs:__imp_DeleteFileW
0x140025666  nop     dword ptr [rax+rax+00h]
0x14002566b  mov     eax, esi
0x14002566d  mov     rbx, [rsp+0F0h+arg_10]
0x140025675  add     rsp, 0D0h
0x14002567c  pop     r15
0x14002567e  pop     r14
0x140025680  pop     rdi
0x140025681  pop     rsi
0x140025682  pop     rbp
0x140025683  retn
0x140025685  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140025689  call    cs:__imp_QueryPerformanceCounter
0x140025690  nop     dword ptr [rax+rax+00h]
0x140025695  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x140025699  lea     rcx, [rbp+57h+var_B0]; void *
0x14002569d  sub     rax, qword ptr [rbp+57h+var_B8]
0x1400256a1  xor     edx, edx; Val
0x1400256a3  mov     r8d, 90h; Size
0x1400256a9  mov     [rbx+0A4B8h], rax
0x1400256b0  call    memset_0
0x1400256b5  mov     rax, [r14]
0x1400256b8  movups  xmm0, [rbp+57h+var_B0]
0x1400256bc  mov     dword ptr [rbx+9078h], 0
0x1400256c6  movups  xmm1, [rbp+57h+var_A0]
0x1400256ca  movups  xmmword ptr [rbx+9080h], xmm0
0x1400256d1  movups  xmm0, [rbp+57h+var_90]
0x1400256d5  movups  xmmword ptr [rbx+9090h], xmm1
0x1400256dc  movups  xmm1, [rbp+57h+var_80]
0x1400256e0  movups  xmmword ptr [rbx+90A0h], xmm0
0x1400256e7  movups  xmm0, [rbp+57h+var_70]
0x1400256eb  movups  xmmword ptr [rbx+90B0h], xmm1
0x1400256f2  movups  xmm1, [rbp+57h+var_60]
0x1400256f6  movups  xmmword ptr [rbx+90C0h], xmm0
0x1400256fd  movups  xmm0, [rbp+57h+var_50]
  ... truncated ...
```
