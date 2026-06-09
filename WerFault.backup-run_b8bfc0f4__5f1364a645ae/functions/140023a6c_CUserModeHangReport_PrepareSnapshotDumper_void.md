# CUserModeHangReport::PrepareSnapshotDumper(void)

- ea: `0x140023a6c`
- end: `0x140023fac`
- name: `?PrepareSnapshotDumper@CUserModeHangReport@@AEAAJXZ`
- size: `1344`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140024af0`
- `0x140025020`

## callees

- `0x1400030a8`
- `0x140011a04`
- `0x14001211c`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x14001e9a4`
- `0x140022c1c`
- `0x140023a6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023cbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023d89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023cbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023d89`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140023ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140023ca7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140023cca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140023d95`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140023cca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140023d95`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023c98`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023dda`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023ec4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023c98`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023dda`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140023ec4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140023ea1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140023ea1`
- `wer!WerpInitializeImageCache` at `0x140023baa`
- `wer!WerpInitializeImageCache` at `0x140023baa`
- `wer!WerpAuxmdFree` at `0x140023e94`
- `wer!WerpAuxmdFree` at `0x140023e94`
- `wer!WerpUnmapProcessViews` at `0x140023e03`
- `wer!WerpUnmapProcessViews` at `0x140023e03`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x140023e87`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerFree` at `0x140023e87`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140023c16`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140023c16`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x140023c68`
- `api-ms-win-core-processsnapshot-l1-1-0!PssWalkMarkerCreate` at `0x140023c68`

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
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  bool v32; // [rsp+28h] [rbp-71h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-69h] BYREF
  LARGE_INTEGER v34; // [rsp+38h] [rbp-61h] BYREF
  _OWORD v35[11]; // [rsp+40h] [rbp-59h] BYREF
  void *v36; // [rsp+100h] [rbp+67h] BYREF
  __int64 v37; // [rsp+108h] [rbp+6Fh] BYREF

  SnapshotForProcess = CHangReport::FindSnapshotForProcess(this, **((_DWORD **)this + 2988));
  v36 = 0;
  result = *((unsigned int *)this + 9246);
  v37 = 0;
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
           v32) )
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
    v36 = 0;
    v7 = PssQuerySnapshot(SnapshotForProcess, 1, &v36, 8);
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
    v7 = PssWalkMarkerCreate(0, &v37);
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
    v7 = CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(this, v36);
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
      v21 = v37;
      *((_DWORD *)this + 9246) = v7;
      PssWalkMarkerFree(v21);
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
    QueryPerformanceCounter(&v34);
    v19 = v36;
    *((_QWORD *)this + 5270) = v34.QuadPart - PerformanceCount.QuadPart;
    v7 = WerpUnmapProcessViews((char *)this + 37144, v19, 3);
    if ( v7 >= 0 )
    {
      v20 = *((unsigned int *)this + 9293);
      if ( !(_DWORD)v20 )
      {
        QueryPerformanceCounter(&PerformanceCount);
        *((_QWORD *)this + 5271) = PerformanceCount.QuadPart - v34.QuadPart;
        memset_0(v35, 0, 0x90u);
        v22 = *((_QWORD *)this + 4643);
        v23 = v35[0];
        *((_DWORD *)this + 9246) = 0;
        v24 = v35[1];
        *((_OWORD *)this + 2312) = v23;
        v25 = v35[2];
        *((_OWORD *)this + 2313) = v24;
        v26 = v35[3];
        *((_OWORD *)this + 2314) = v25;
        v27 = v35[4];
        *((_OWORD *)this + 2315) = v26;
        v28 = v35[5];
        *((_OWORD *)this + 2316) = v27;
        v29 = v35[6];
        *((_OWORD *)this + 2317) = v28;
        v30 = v35[7];
        *((_OWORD *)this + 2318) = v29;
        v31 = v35[8];
        *((_OWORD *)this + 2319) = v30;
        *((_OWORD *)this + 2320) = v31;
        *((_QWORD *)this + 4625) = v22;
        *((_DWORD *)this + 9252) = *((_DWORD *)this + 9288);
        *((_QWORD *)this + 4627) = (char *)this + 37176;
        *((_QWORD *)this + 4629) = (char *)this + 41368;
        *((_QWORD *)this + 4631) = v37;
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
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
        v20,
        -2147023672);
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
0x140023a6c  mov     [rsp-8+arg_10], rbx
0x140023a71  push    rbp
0x140023a72  push    rsi
0x140023a73  push    rdi
0x140023a74  push    r14
0x140023a76  push    r15
0x140023a78  lea     rbp, [rsp-37h]
0x140023a7d  sub     rsp, 0D0h
0x140023a84  mov     rdx, [rcx+5D60h]
0x140023a8b  mov     rbx, rcx
0x140023a8e  mov     edx, [rdx]; unsigned int
0x140023a90  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x140023a95  mov     r15, rax
0x140023a98  mov     [rbp+57h+arg_0], 0
0x140023aa0  mov     eax, [rbx+9078h]
0x140023aa6  mov     edi, 1
0x140023aab  mov     [rbp+57h+arg_8], 0
0x140023ab3  cmp     eax, edi
0x140023ab5  jl      loc_140023EA9
0x140023abb  test    r15, r15
0x140023abe  jnz     short loc_140023AFD
0x140023ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ac7  lea     rdi, WPP_GLOBAL_Control
0x140023ace  cmp     rcx, rdi
0x140023ad1  jz      short loc_140023AED
0x140023ad3  test    byte ptr [rcx+1Ch], 2
0x140023ad7  jz      short loc_140023AED
0x140023ad9  mov     rcx, [rcx+10h]
0x140023add  lea     edx, [r15+70h]
0x140023ae1  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023ae8  call    WPP_SF_
0x140023aed  mov     eax, 80070490h
0x140023af2  mov     [rbx+9078h], eax
0x140023af8  jmp     loc_140023EA9
0x140023afd  xor     r9d, r9d; unsigned int
0x140023b00  mov     [rsp+0F0h+var_D0], 0; bool *
0x140023b09  lea     r8, aFailsnapshotdu; "FailSnapshotDumper"
0x140023b10  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023b17  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x140023b1e  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140023b23  test    eax, eax
0x140023b25  jz      short loc_140023B5C
0x140023b27  mov     rcx, cs:WPP_GLOBAL_Control
0x140023b2e  lea     rdi, WPP_GLOBAL_Control
0x140023b35  cmp     rcx, rdi
0x140023b38  jz      short loc_140023B55
0x140023b3a  test    byte ptr [rcx+1Ch], 4
0x140023b3e  jz      short loc_140023B55
0x140023b40  mov     rcx, [rcx+10h]
0x140023b44  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023b4b  mov     edx, 71h ; 'q'
0x140023b50  call    WPP_SF_
0x140023b55  mov     eax, 80070465h
0x140023b5a  jmp     short loc_140023AF2
0x140023b5c  cmp     dword ptr [rbx+0A4C0h], 0
0x140023b63  jnz     loc_140023BFF
0x140023b69  lea     rcx, aBd; "BD"
0x140023b70  call    UtilIsNamedEventSet
0x140023b75  cmp     eax, edi
0x140023b77  jnz     short loc_140023B9E
0x140023b79  lea     rcx, aDf_0; "DF"
0x140023b80  call    UtilIsNamedEventSet
0x140023b85  cmp     eax, edi
0x140023b87  jnz     short loc_140023B9E
0x140023b89  lea     rcx, aJl; "JL"
0x140023b90  call    UtilIsNamedEventSet
0x140023b95  mov     edx, 8000000h
0x140023b9a  cmp     eax, edi
0x140023b9c  jz      short loc_140023BA3
0x140023b9e  mov     edx, 2000000h
0x140023ba3  lea     rcx, [rbx+0A198h]
0x140023baa  call    cs:__imp_?WerpInitializeImageCache@@YAJPEAUWERP_IMAGE_CACHE@@K@Z; WerpInitializeImageCache(WERP_IMAGE_CACHE *,ulong)
0x140023bb0  mov     ecx, eax
0x140023bb2  mov     esi, eax
0x140023bb4  not     ecx
0x140023bb6  shr     ecx, 1Fh
0x140023bb9  mov     [rbx+0A4C0h], ecx
0x140023bbf  test    eax, eax
0x140023bc1  jns     short loc_140023BFF
0x140023bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140023bca  lea     rdi, WPP_GLOBAL_Control
0x140023bd1  cmp     rcx, rdi
0x140023bd4  jz      short loc_140023BF4
0x140023bd6  test    byte ptr [rcx+1Ch], 2
0x140023bda  jz      short loc_140023BF4
0x140023bdc  mov     rcx, [rcx+10h]
0x140023be0  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023be7  mov     edx, 72h ; 'r'
0x140023bec  mov     r9d, eax
0x140023bef  call    WPP_SF_d
0x140023bf4  mov     [rbx+9078h], esi
0x140023bfa  jmp     loc_140023EA7
0x140023bff  mov     r9d, 8
0x140023c05  mov     [rbp+57h+arg_0], 0
0x140023c0d  lea     r8, [rbp+57h+arg_0]
0x140023c11  mov     edx, edi
0x140023c13  mov     rcx, r15
0x140023c16  call    cs:__imp_PssQuerySnapshot
0x140023c1c  mov     esi, eax
0x140023c1e  test    eax, eax
0x140023c20  jz      short loc_140023C62
0x140023c22  mov     rcx, cs:WPP_GLOBAL_Control
0x140023c29  lea     rdi, WPP_GLOBAL_Control
0x140023c30  cmp     rcx, rdi
0x140023c33  jz      short loc_140023C53
0x140023c35  test    byte ptr [rcx+1Ch], 2
0x140023c39  jz      short loc_140023C53
0x140023c3b  mov     edx, 73h ; 's'
0x140023c40  mov     rcx, [rcx+10h]
0x140023c44  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023c4b  mov     r9d, esi
0x140023c4e  call    WPP_SF_d
0x140023c53  test    esi, esi
0x140023c55  jle     short loc_140023BF4
0x140023c57  movzx   esi, si
0x140023c5a  or      esi, 80070000h
0x140023c60  jmp     short loc_140023BF4
0x140023c62  lea     rdx, [rbp+57h+arg_8]
0x140023c66  xor     ecx, ecx
0x140023c68  call    cs:__imp_PssWalkMarkerCreate
0x140023c6e  mov     esi, eax
0x140023c70  test    eax, eax
0x140023c72  jz      short loc_140023C94
0x140023c74  mov     rcx, cs:WPP_GLOBAL_Control
0x140023c7b  lea     rdi, WPP_GLOBAL_Control
0x140023c82  cmp     rcx, rdi
0x140023c85  jz      short loc_140023C53
0x140023c87  test    byte ptr [rcx+1Ch], 2
0x140023c8b  jz      short loc_140023C53
0x140023c8d  mov     edx, 74h ; 't'
0x140023c92  jmp     short loc_140023C40
0x140023c94  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140023c98  call    cs:__imp_QueryPerformanceCounter
0x140023c9e  call    cs:__imp_GetCurrentThread
0x140023ca4  mov     rcx, rax; hThread
0x140023ca7  call    cs:__imp_GetThreadPriority
0x140023cad  lea     rdi, WPP_GLOBAL_Control
0x140023cb4  mov     r14d, eax
0x140023cb7  cmp     eax, 7FFFFFFFh
0x140023cbc  jz      short loc_140023D13
0x140023cbe  call    cs:__imp_GetCurrentThread
0x140023cc4  mov     rcx, rax; hThread
0x140023cc7  or      edx, 0FFFFFFFFh; nPriority
0x140023cca  call    cs:__imp_SetThreadPriority
0x140023cd0  test    eax, eax
0x140023cd2  jnz     short loc_140023D4A
0x140023cd4  mov     rax, cs:WPP_GLOBAL_Control
0x140023cdb  cmp     rax, rdi
0x140023cde  jz      short loc_140023D0B
0x140023ce0  test    byte ptr [rax+1Ch], 2
0x140023ce4  jz      short loc_140023D0B
0x140023ce6  call    cs:__imp_GetLastError
0x140023cec  mov     rcx, cs:WPP_GLOBAL_Control
0x140023cf3  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023cfa  mov     edx, 75h ; 'u'
0x140023cff  mov     r9d, eax
0x140023d02  mov     rcx, [rcx+10h]
0x140023d06  call    WPP_SF_d
0x140023d0b  mov     r14d, 7FFFFFFFh
0x140023d11  jmp     short loc_140023D4A
0x140023d13  mov     rax, cs:WPP_GLOBAL_Control
0x140023d1a  cmp     rax, rdi
0x140023d1d  jz      short loc_140023D4A
0x140023d1f  test    byte ptr [rax+1Ch], 2
0x140023d23  jz      short loc_140023D4A
0x140023d25  call    cs:__imp_GetLastError
0x140023d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023d32  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023d39  mov     edx, 76h ; 'v'
0x140023d3e  mov     r9d, eax
0x140023d41  mov     rcx, [rcx+10h]
0x140023d45  call    WPP_SF_d
0x140023d4a  mov     rdx, [rbp+57h+arg_0]; void *
0x140023d4e  mov     rcx, rbx; this
0x140023d51  call    ?DumpProcessDataSegsRegisteredBlocks@CUserModeHangReport@@AEAAJPEAX@Z; CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(void *)
0x140023d56  mov     esi, eax
0x140023d58  test    eax, eax
0x140023d5a  jns     short loc_140023D80
0x140023d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023d63  cmp     rcx, rdi
0x140023d66  jz      loc_140023E7D
0x140023d6c  test    byte ptr [rcx+1Ch], 2
0x140023d70  jz      loc_140023E7D
0x140023d76  mov     edx, 77h ; 'w'
0x140023d7b  jmp     loc_140023E6A
0x140023d80  cmp     r14d, 7FFFFFFFh
0x140023d87  jz      short loc_140023DD6
0x140023d89  call    cs:__imp_GetCurrentThread
0x140023d8f  mov     rcx, rax; hThread
0x140023d92  mov     edx, r14d; nPriority
0x140023d95  call    cs:__imp_SetThreadPriority
0x140023d9b  test    eax, eax
0x140023d9d  jnz     short loc_140023DD6
0x140023d9f  mov     rax, cs:WPP_GLOBAL_Control
0x140023da6  cmp     rax, rdi
0x140023da9  jz      short loc_140023DD6
0x140023dab  test    byte ptr [rax+1Ch], 2
0x140023daf  jz      short loc_140023DD6
0x140023db1  call    cs:__imp_GetLastError
0x140023db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140023dbe  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023dc5  mov     edx, 78h ; 'x'
0x140023dca  mov     r9d, eax
0x140023dcd  mov     rcx, [rcx+10h]
0x140023dd1  call    WPP_SF_d
0x140023dd6  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x140023dda  call    cs:__imp_QueryPerformanceCounter
0x140023de0  mov     rax, qword ptr [rbp+57h+var_B8]
0x140023de4  lea     r14, [rbx+9118h]
0x140023deb  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x140023def  mov     r8d, 3
0x140023df5  mov     rdx, [rbp+57h+arg_0]
0x140023df9  mov     rcx, r14
0x140023dfc  mov     [rbx+0A4B0h], rax
0x140023e03  call    cs:__imp_WerpUnmapProcessViews
0x140023e09  mov     esi, eax
0x140023e0b  test    eax, eax
0x140023e0d  js      short loc_140023E53
0x140023e0f  mov     r9d, [rbx+9134h]
0x140023e16  test    r9d, r9d
0x140023e19  jz      loc_140023EC0
0x140023e1f  mov     esi, 800704C8h
0x140023e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e2b  cmp     rcx, rdi
0x140023e2e  jz      short loc_140023E7D
0x140023e30  test    byte ptr [rcx+1Ch], 2
0x140023e34  jz      short loc_140023E5A
0x140023e36  mov     rcx, [rcx+10h]
0x140023e3a  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023e41  mov     edx, 79h ; 'y'
0x140023e46  mov     dword ptr [rsp+0F0h+var_D0], 800704C8h
0x140023e4e  call    WPP_SF_Dd
0x140023e53  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e5a  cmp     rcx, rdi
0x140023e5d  jz      short loc_140023E7D
0x140023e5f  test    byte ptr [rcx+1Ch], 2
0x140023e63  jz      short loc_140023E7D
0x140023e65  mov     edx, 7Ah ; 'z'
0x140023e6a  mov     rcx, [rcx+10h]
0x140023e6e  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023e75  mov     r9d, esi
0x140023e78  call    WPP_SF_d
0x140023e7d  mov     rcx, [rbp+57h+arg_8]
0x140023e81  mov     [rbx+9078h], esi
0x140023e87  call    cs:__imp_PssWalkMarkerFree
0x140023e8d  lea     rcx, [rbx+9138h]
0x140023e94  call    cs:__imp_WerpAuxmdFree
0x140023e9a  lea     rcx, [rbx+0A2A8h]; lpFileName
0x140023ea1  call    cs:__imp_DeleteFileW
0x140023ea7  mov     eax, esi
0x140023ea9  mov     rbx, [rsp+0F0h+arg_10]
0x140023eb1  add     rsp, 0D0h
0x140023eb8  pop     r15
0x140023eba  pop     r14
0x140023ebc  pop     rdi
0x140023ebd  pop     rsi
0x140023ebe  pop     rbp
0x140023ebf  retn
0x140023ec0  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140023ec4  call    cs:__imp_QueryPerformanceCounter
0x140023eca  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x140023ece  lea     rcx, [rbp+57h+var_B0]; void *
0x140023ed2  sub     rax, qword ptr [rbp+57h+var_B8]
0x140023ed6  xor     edx, edx; Val
0x140023ed8  mov     r8d, 90h; Size
0x140023ede  mov     [rbx+0A4B8h], rax
0x140023ee5  call    memset_0
0x140023eea  mov     rax, [r14]
0x140023eed  movups  xmm0, [rbp+57h+var_B0]
0x140023ef1  mov     dword ptr [rbx+9078h], 0
0x140023efb  movups  xmm1, [rbp+57h+var_A0]
0x140023eff  movups  xmmword ptr [rbx+9080h], xmm0
0x140023f06  movups  xmm0, [rbp+57h+var_90]
0x140023f0a  movups  xmmword ptr [rbx+9090h], xmm1
0x140023f11  movups  xmm1, [rbp+57h+var_80]
0x140023f15  movups  xmmword ptr [rbx+90A0h], xmm0
0x140023f1c  movups  xmm0, [rbp+57h+var_70]
0x140023f20  movups  xmmword ptr [rbx+90B0h], xmm1
0x140023f27  movups  xmm1, [rbp+57h+var_60]
0x140023f2b  movups  xmmword ptr [rbx+90C0h], xmm0
0x140023f32  movups  xmm0, [rbp+57h+var_50]
0x140023f36  movups  xmmword ptr [rbx+90D0h], xmm1
0x140023f3d  movups  xmm1, [rbp+57h+var_40]
0x140023f41  movups  xmmword ptr [rbx+90E0h], xmm0
0x140023f48  movups  xmm0, [rbp+57h+var_30]
0x140023f4c  movups  xmmword ptr [rbx+90F0h], xmm1
0x140023f53  movups  xmmword ptr [rbx+9100h], xmm0
0x140023f5a  mov     [rbx+9088h], rax
0x140023f61  mov     eax, [rbx+9120h]
0x140023f67  mov     [rbx+9090h], eax
0x140023f6d  lea     rax, [rbx+9138h]
0x140023f74  mov     [rbx+9098h], rax
0x140023f7b  lea     rax, [rbx+0A198h]
0x140023f82  mov     [rbx+90A8h], rax
0x140023f89  mov     rax, [rbp+57h+arg_8]
0x140023f8d  mov     [rbx+90B8h], rax
0x140023f94  xor     eax, eax
0x140023f96  mov     dword ptr [rbx+9080h], 3
0x140023fa0  mov     [rbx+90B0h], r15
0x140023fa7  jmp     loc_140023EA9
  ... truncated ...
```
