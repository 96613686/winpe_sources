# OpenExtObjectLibrary(EXT_OBJECT *)

- ea: `0x180038fbc`
- end: `0x18003993f`
- name: `?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z`
- size: `2435`
- prototype: `__int64 __fastcall(struct EXT_OBJECT *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014e50`

## callees

- `0x180015c38`
- `0x180015e40`
- `0x180027230`
- `0x18002ccac`
- `0x18002ff64`
- `0x1800351f0`
- `0x1800354a8`
- `0x1800374bc`
- `0x180038fbc`
- `0x180039948`
- `0x180039aec`
- `0x18003b2bc`
- `0x18003b57c`
- `0x18003b748`
- `0x180057c58`
- `0x180057dfc`
- `0x1800585a0`
- `0x180058678`
- `0x180058794`
- `0x180058e9c`
- `0x180058fa8`
- `0x18005904c`
- `0x180059108`
- `0x18005918c`
- `0x180065090`
- `0x180066010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003963c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003963c`
- `KERNEL32!GetLastError` at `0x18003922b`
- `KERNEL32!GetLastError` at `0x18003934e`
- `KERNEL32!GetLastError` at `0x1800393f9`
- `KERNEL32!GetLastError` at `0x1800394a2`
- `KERNEL32!GetLastError` at `0x180039799`
- `KERNEL32!GetLastError` at `0x18003922b`
- `KERNEL32!GetLastError` at `0x18003934e`
- `KERNEL32!GetLastError` at `0x1800393f9`
- `KERNEL32!GetLastError` at `0x1800394a2`
- `KERNEL32!GetLastError` at `0x180039799`
- `KERNEL32!GetProcAddress` at `0x180039330`
- `KERNEL32!GetProcAddress` at `0x1800393e6`
- `KERNEL32!GetProcAddress` at `0x18003948f`
- `KERNEL32!GetProcAddress` at `0x180039330`
- `KERNEL32!GetProcAddress` at `0x1800393e6`
- `KERNEL32!GetProcAddress` at `0x18003948f`
- `KERNEL32!FreeLibrary` at `0x180039777`
- `KERNEL32!FreeLibrary` at `0x180039777`
- `KERNEL32!LoadLibraryExW` at `0x1800391c3`
- `KERNEL32!LoadLibraryExW` at `0x1800391c3`
- `KERNEL32!GetModuleFileNameW` at `0x180039221`
- `KERNEL32!GetModuleFileNameW` at `0x180039221`
- `KERNEL32!SetErrorMode` at `0x18003918e`
- `KERNEL32!SetErrorMode` at `0x180039888`
- `KERNEL32!SetErrorMode` at `0x18003918e`
- `KERNEL32!SetErrorMode` at `0x180039888`

## pseudocode

```c
__int64 __fastcall OpenExtObjectLibrary(struct EXT_OBJECT *a1, __int64 a2, unsigned int *a3)
{
  int *v4; // r13
  unsigned int LastError; // edi
  const unsigned __int16 near *const *v6; // r15
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int IsRelative; // eax
  HMODULE Library; // rax
  int v12; // edx
  int v13; // r8d
  int v14; // r12d
  __int64 v15; // rcx
  FARPROC ProcAddress; // rax
  DWORD v17; // eax
  int v18; // r8d
  int v19; // ecx
  FARPROC v20; // rax
  DWORD v21; // eax
  int v22; // ecx
  FARPROC v23; // rax
  DWORD v24; // eax
  int v25; // r8d
  int v26; // ecx
  BOOL v27; // ecx
  int v28; // ecx
  HMODULE *v29; // rdi
  DWORD v30; // eax
  int v31; // edx
  int v32; // r8d
  int v33; // eax
  unsigned int v34; // r15d
  unsigned int v35; // r12d
  __int64 v36; // rcx
  __int64 *v37; // rdx
  unsigned int v39; // [rsp+40h] [rbp-2D8h] BYREF
  int v40; // [rsp+44h] [rbp-2D4h]
  _QWORD *v41; // [rsp+48h] [rbp-2D0h]
  UINT uMode; // [rsp+50h] [rbp-2C8h] BYREF
  unsigned __int8 v43[4]; // [rsp+54h] [rbp-2C4h] BYREF
  HMODULE *v44; // [rsp+58h] [rbp-2C0h]
  HKEY *v45; // [rsp+60h] [rbp-2B8h]
  int v46; // [rsp+68h] [rbp-2B0h]
  int v47; // [rsp+6Ch] [rbp-2ACh]
  HLOCAL hMem; // [rsp+70h] [rbp-2A8h]
  const unsigned __int16 near *const *v49; // [rsp+78h] [rbp-2A0h]
  struct EXT_OBJECT *v50; // [rsp+80h] [rbp-298h]
  __int64 (__fastcall **v51)(_QWORD); // [rsp+88h] [rbp-290h]
  char *v52; // [rsp+90h] [rbp-288h]
  __int128 v53; // [rsp+98h] [rbp-280h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-270h]
  struct EXT_OBJECT *v55; // [rsp+B8h] [rbp-260h]
  __int128 v56; // [rsp+C0h] [rbp-258h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-248h] BYREF

  v50 = a1;
  *(_DWORD *)v43 = 0;
  v56 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
      *((_QWORD *)a1 + 49));
  v4 = (int *)((char *)a1 + 380);
  v52 = (char *)a1 + 380;
  if ( (*((_BYTE *)a1 + 380) & 0x10) != 0 )
  {
    LastError = 1058;
LABEL_122:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, LastError);
    return LastError;
  }
  v40 = 0;
  v47 = 0;
  v44 = (HMODULE *)((char *)a1 + 88);
  if ( *((_QWORD *)a1 + 11) )
  {
    LastError = 0;
    *((_QWORD *)a1 + 50) = GetTimeAsLongLong();
    goto LABEL_118;
  }
  v6 = &NULL_STRING;
  if ( *((_QWORD *)a1 + 49) )
    v6 = (const unsigned __int16 near *const *)*((_QWORD *)a1 + 49);
  v49 = v6;
  uMode = 0;
  v39 = 4;
  *(_DWORD *)v43 = 0;
  v45 = (HKEY *)((char *)a1 + 104);
  LastError = PrivateRegQueryValueExT(*((HKEY *)a1 + 13), L"Disable Performance Counters", a3, &uMode, v43, &v39, 1);
  v39 = LastError;
  if ( LastError || uMode != 4 )
  {
    LastError = 0;
    v39 = 0;
    *v4 &= ~0x10u;
  }
  else
  {
    *v4 &= ~0x10u;
    v7 = *v4;
    if ( *(_DWORD *)v43 == 1 )
    {
      *v4 = v7 | 0x10;
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 14;
        goto LABEL_19;
      }
    }
    else if ( *(_DWORD *)v43 == 4 )
    {
      v40 = 1;
      v47 = 1;
      *v4 = v7 | 0x10;
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = LastError + 16;
LABEL_19:
        WPP_SF_S(v8[2], v9, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
      }
    }
  }
  if ( (*(_BYTE *)v4 & 0x10) == 0 )
  {
    uMode = SetErrorMode(1u);
    v41 = (_QWORD *)((char *)a1 + 96);
    IsRelative = PerflibciPathIsRelative(*((_QWORD *)a1 + 12));
    Library = LoadLibraryExW(*((LPCWSTR *)a1 + 12), 0, IsRelative != 0 ? 4096 : 2304);
    *v44 = Library;
    if ( Library )
    {
      v14 = 0;
      hMem = 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, *v41, (char)Library);
      if ( !GetModuleFileNameW(*v44, Filename, 0x104u) )
      {
        LastError = GetLastError();
        v39 = LastError;
      }
      if ( !LastError && *((__int64 *)a1 + 52) > 0 )
      {
        if ( (unsigned int)ServiceIsTrustedByDefault(v6) )
          goto LABEL_33;
        v56 = 0;
        LastError = GetPerfDllFileInfo(Filename, (struct DLL_VALIDATION_DATA *)&v56);
        v39 = LastError;
        if ( LastError )
          goto LABEL_40;
        if ( *(_OWORD *)((char *)a1 + 408) == v56 )
        {
LABEL_33:
          *v4 |= 0x20u;
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
          if ( PerfpThrottleError(0x7D3u, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
          {
            McTemplateU0zz_EtwEventWriteTransfer(v15, PERFLIB_NOT_TRUSTED_FILE, *v41, v6);
          }
        }
      }
LABEL_40:
      ProcAddress = GetProcAddress(*v44, *((LPCSTR *)a1 + 3));
      v51 = (__int64 (__fastcall **)(_QWORD))((char *)a1 + 16);
      *((_QWORD *)a1 + 2) = ProcAddress;
      if ( !ProcAddress )
      {
        v17 = GetLastError();
        LastError = v17;
        v39 = v17;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v18, (_DWORD)v6, *((_QWORD *)a1 + 3), v17);
        if ( PerfpThrottleError(0x3EDu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
        {
          McTemplateU0szzq_EtwEventWriteTransfer(
            v19,
            (unsigned int)PERFLIB_OPEN_PROC_NOT_FOUND,
            *((_QWORD *)a1 + 3),
            *v41,
            (__int64)v6,
            LastError);
        }
      }
      if ( !LastError )
      {
        v20 = GetProcAddress(*v44, *((LPCSTR *)a1 + 6));
        *((_QWORD *)a1 + 5) = v20;
        if ( !v20 )
        {
          v21 = GetLastError();
          LastError = v21;
          v39 = v21;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              (unsigned int)WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
              (_DWORD)v6,
              v21);
          if ( PerfpThrottleError(0x3EEu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
          {
            McTemplateU0szzq_EtwEventWriteTransfer(
              v22,
              (unsigned int)PERFLIB_COLLECT_PROC_NOT_FOUND,
              *((_QWORD *)a1 + 6),
              *v41,
              (__int64)v6,
              LastError);
          }
        }
        if ( !LastError )
        {
          v23 = GetProcAddress(*v44, *((LPCSTR *)a1 + 9));
          *((_QWORD *)a1 + 8) = v23;
          if ( !v23 )
          {
            v24 = GetLastError();
            LastError = v24;
            v39 = v24;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v25, (_DWORD)v6, *((_QWORD *)a1 + 9), v24);
            if ( PerfpThrottleError(0x3EFu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
              && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
            {
              McTemplateU0szzq_EtwEventWriteTransfer(
                v26,
                (unsigned int)PERFLIB_CLOSE_PROC_NOT_FOUND,
                *((_QWORD *)a1 + 9),
                *v41,
                (__int64)v6,
                LastError);
            }
          }
        }
      }
      v27 = (lPerflibConfigFlags & 4) == 0 && (*v4 & 0x20) == 0;
      if ( !LastError )
      {
        *(_QWORD *)&v53 = 0;
        *((_QWORD *)&v53 + 1) = *v41;
        *(_QWORD *)&v54 = v6;
        DWORD2(v54) = *((_DWORD *)a1 + 15);
        HIDWORD(v54) = 2002;
        v55 = a1;
        if ( v27 )
        {
          hMem = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)&v53);
          if ( !hMem && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids);
        }
        else
        {
          hMem = 0;
        }
        if ( *v51 )
        {
          v14 = (*v51)(*((_QWORD *)a1 + 4));
          v46 = v14;
        }
        else
        {
          v14 = 127;
          v46 = 127;
        }
        if ( v14 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              (unsigned int)WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
              (_DWORD)v6,
              v14);
          if ( v14 == 5 )
          {
            *((_DWORD *)a1 + 130) = GetCurrentThreadId();
            *((_DWORD *)a1 + 121) = 0;
          }
          else
          {
            ++*((_DWORD *)a1 + 121);
          }
        }
        else
        {
          *((_DWORD *)a1 + 130) = 0;
          _InterlockedIncrement((volatile signed __int32 *)a1 + 113);
        }
        if ( hMem )
          LastError = KillPerflibFunctionTimer(hMem);
        if ( !v14 )
          goto LABEL_97;
        if ( PerfpThrottleError(0x3F0u, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
        {
          McTemplateU0zzq_EtwEventWriteTransfer(v28, (unsigned int)PERFLIB_OPEN_PROC_FAILURE, (_DWORD)v6, *v41, v14);
        }
      }
      if ( v14 )
      {
        *v51 = 0;
        *((_QWORD *)a1 + 5) = 0;
        *((_QWORD *)a1 + 8) = 0;
        v29 = v44;
        if ( *v44 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
          FreeLibrary(*v29);
          *v29 = 0;
        }
        LastError = v14;
        goto LABEL_116;
      }
LABEL_97:
      *((_QWORD *)a1 + 50) = GetTimeAsLongLong();
LABEL_116:
      SetErrorMode(uMode);
      goto LABEL_118;
    }
    v30 = GetLastError();
    LastError = v30;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, (_DWORD)v6, *((_QWORD *)a1 + 12), v30);
    v33 = v40;
    if ( LastError == 193 )
      v33 = 1;
    v40 = v33;
    v34 = 1021;
    if ( LastError != 193 )
      v34 = 1023;
    v35 = 4;
    if ( LastError != 193 )
      v35 = 0;
    if ( PerfpThrottleError(v34, *v45, (struct ERROR_LOG *)((char *)a1 + 488)) )
    {
      if ( v34 == 1021 )
      {
        if ( (Microsoft_Windows_PerflibEnableBits & 2) == 0 )
          goto LABEL_114;
        v37 = PERFLIB_INVALID_WOW32_PERF_DLL;
      }
      else
      {
        if ( (Microsoft_Windows_PerflibEnableBits & 2) == 0 )
          goto LABEL_114;
        v37 = PERFLIB_CANNOT_LOAD_PERF_DLL;
      }
      McTemplateU0zq_EtwEventWriteTransfer(v36, v37, *v41, LastError);
    }
LABEL_114:
    if ( LastError == 193 )
      DisablePerfLibrary(a1, v35, v34, 0xC1u, 0);
    goto LABEL_116;
  }
LABEL_118:
  if ( v40 )
  {
    LastError = OpenRemoteExtObjectLibrary((__int64)a1);
    if ( !LastError )
      *v4 &= ~0x10u;
  }
  if ( LastError )
    goto LABEL_122;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x180038fbc  mov     [rsp+arg_8], rbx
0x180038fc1  mov     [rsp+arg_10], rsi
0x180038fc6  push    rdi
0x180038fc7  push    r12
0x180038fc9  push    r13
0x180038fcb  push    r14
0x180038fcd  push    r15
0x180038fcf  sub     rsp, 2F0h
0x180038fd6  mov     rax, cs:__security_cookie
0x180038fdd  xor     rax, rsp
0x180038fe0  mov     [rsp+318h+var_38], rax
0x180038fe8  mov     rsi, rcx
0x180038feb  mov     [rsp+318h+var_298], rcx
0x180038ff3  xor     ebx, ebx
0x180038ff5  mov     dword ptr [rsp+318h+var_2C4], ebx
0x180038ff9  xorps   xmm0, xmm0
0x180038ffc  movups  [rsp+318h+var_258], xmm0
0x180039004  xorps   xmm1, xmm1
0x180039007  xor     eax, eax
0x180039009  movups  [rsp+318h+var_280], xmm1
0x180039011  movups  [rsp+318h+var_270], xmm1
0x180039019  mov     [rsp+318h+var_260], rax
0x180039021  mov     rcx, cs:WPP_GLOBAL_Control
0x180039028  lea     r14d, [rbx+4]
0x18003902c  test    [rcx+1Ch], r14b
0x180039030  jz      short loc_180039052
0x180039032  cmp     [rcx+19h], r14b
0x180039036  jb      short loc_180039052
0x180039038  lea     edx, [rbx+0Dh]
0x18003903b  mov     r9, [rsi+188h]
0x180039042  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x180039049  mov     rcx, [rcx+10h]
0x18003904d  call    WPP_SF_S
0x180039052  lea     r13, [rsi+17Ch]
0x180039059  mov     [rsp+318h+var_288], r13
0x180039061  test    byte ptr [r13+0], 10h
0x180039066  jz      short loc_180039072
0x180039068  mov     edi, 422h
0x18003906d  jmp     loc_1800398BB
0x180039072  mov     [rsp+318h+var_2D4], ebx
0x180039076  mov     [rsp+318h+var_2AC], ebx
0x18003907a  lea     rax, [rsi+58h]
0x18003907e  mov     [rsp+318h+var_2C0], rax
0x180039083  cmp     [rax], rbx
0x180039086  jnz     loc_180039890
0x18003908c  mov     rax, [rsi+188h]
0x180039093  lea     r15, ?NULL_STRING@@3QBGB; ushort const near * const NULL_STRING
0x18003909a  test    rax, rax
0x18003909d  cmovnz  r15, rax
0x1800390a1  mov     [rsp+318h+var_2A0], r15
0x1800390a6  mov     [rsp+318h+uMode], ebx
0x1800390aa  mov     [rsp+318h+var_2D8], r14d
0x1800390af  mov     dword ptr [rsp+318h+var_2C4], ebx
0x1800390b3  lea     rax, [rsi+68h]
0x1800390b7  mov     [rsp+318h+var_2B8], rax
0x1800390bc  mov     r12d, 1
0x1800390c2  mov     [rsp+318h+var_2E8], r12d; int
0x1800390c7  lea     rcx, [rsp+318h+var_2D8]
0x1800390cc  mov     [rsp+318h+var_2F0], rcx; unsigned int *
0x1800390d1  lea     rcx, [rsp+318h+var_2C4]
0x1800390d6  mov     [rsp+318h+var_2F8], rcx; unsigned __int8 *
0x1800390db  lea     r9, [rsp+318h+uMode]; unsigned int *
0x1800390e0  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x1800390e7  mov     rcx, [rax]; KeyHandle
0x1800390ea  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800390ef  mov     edi, eax
0x1800390f1  mov     [rsp+318h+var_2D8], eax
0x1800390f5  test    eax, eax
0x1800390f7  jnz     short loc_180039175
0x1800390f9  cmp     [rsp+318h+uMode], r14d
0x1800390fe  jnz     short loc_180039175
0x180039100  and     dword ptr [r13+0], 0FFFFFFEFh
0x180039105  mov     eax, [r13+0]
0x180039109  mov     ecx, dword ptr [rsp+318h+var_2C4]
0x18003910d  sub     ecx, r12d
0x180039110  jz      short loc_180039141
0x180039112  cmp     ecx, 3
0x180039115  jnz     short loc_180039180
0x180039117  mov     ecx, r12d
0x18003911a  mov     [rsp+318h+var_2D4], ecx
0x18003911e  mov     [rsp+318h+var_2AC], ecx
0x180039122  or      eax, 10h
0x180039125  mov     [r13+0], eax
0x180039129  mov     rcx, cs:WPP_GLOBAL_Control
0x180039130  test    [rcx+1Ch], r14b
0x180039134  jz      short loc_180039180
0x180039136  cmp     byte ptr [rcx+19h], 3
0x18003913a  jb      short loc_180039180
0x18003913c  lea     edx, [rdi+10h]
0x18003913f  jmp     short loc_180039160
0x180039141  or      eax, 10h
0x180039144  mov     [r13+0], eax
0x180039148  mov     rcx, cs:WPP_GLOBAL_Control
0x18003914f  test    [rcx+1Ch], r14b
0x180039153  jz      short loc_180039180
0x180039155  cmp     byte ptr [rcx+19h], 3
0x180039159  jb      short loc_180039180
0x18003915b  mov     edx, 0Eh
0x180039160  mov     r9, r15
0x180039163  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003916a  mov     rcx, [rcx+10h]
0x18003916e  call    WPP_SF_S
0x180039173  jmp     short loc_180039180
0x180039175  mov     edi, ebx
0x180039177  mov     [rsp+318h+var_2D8], ebx
0x18003917b  and     dword ptr [r13+0], 0FFFFFFEFh
0x180039180  test    byte ptr [r13+0], 10h
0x180039185  jnz     loc_18003989E
0x18003918b  mov     ecx, r12d; uMode
0x18003918e  call    cs:__imp_SetErrorMode
0x180039194  mov     [rsp+318h+uMode], eax
0x180039198  lea     r12, [rsi+60h]
0x18003919c  mov     [rsp+318h+var_2D0], r12
0x1800391a1  mov     rcx, [r12]
0x1800391a5  call    PerflibciPathIsRelative
0x1800391aa  neg     eax
0x1800391ac  sbb     r8d, r8d
0x1800391af  and     r8d, 700h
0x1800391b6  add     r8d, 900h; dwFlags
0x1800391bd  xor     edx, edx; hFile
0x1800391bf  mov     rcx, [r12]; lpLibFileName
0x1800391c3  call    cs:__imp_LoadLibraryExW
0x1800391c9  mov     rcx, [rsp+318h+var_2C0]
0x1800391ce  mov     [rcx], rax
0x1800391d1  test    rax, rax
0x1800391d4  jz      loc_180039799
0x1800391da  mov     r12d, ebx
0x1800391dd  mov     [rsp+318h+hMem], rbx
0x1800391e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391e9  test    [rcx+1Ch], r14b
0x1800391ed  jz      short loc_18003920B
0x1800391ef  cmp     [rcx+19h], r14b
0x1800391f3  jb      short loc_18003920B
0x1800391f5  mov     [rsp+318h+var_2F8], rax
0x1800391fa  mov     r9, [rsp+318h+var_2D0]
0x1800391ff  mov     r9, [r9]
0x180039202  mov     rcx, [rcx+10h]
0x180039206  call    WPP_SF_Sq
0x18003920b  mov     r8d, 104h; nSize
0x180039211  lea     rdx, [rsp+318h+Filename]; lpFilename
0x180039219  mov     rax, [rsp+318h+var_2C0]
0x18003921e  mov     rcx, [rax]; hModule
0x180039221  call    cs:__imp_GetModuleFileNameW
0x180039227  test    eax, eax
0x180039229  jnz     short loc_180039237
0x18003922b  call    cs:__imp_GetLastError
0x180039231  mov     edi, eax
0x180039233  mov     [rsp+318h+var_2D8], eax
0x180039237  test    edi, edi
0x180039239  jnz     loc_180039324
0x18003923f  cmp     [rsi+1A0h], rbx
0x180039246  jle     loc_180039324
0x18003924c  mov     rcx, r15
0x18003924f  call    ServiceIsTrustedByDefault
0x180039254  test    eax, eax
0x180039256  jnz     short loc_1800392B5
0x180039258  xorps   xmm0, xmm0
0x18003925b  movups  [rsp+318h+var_258], xmm0
0x180039263  lea     rdx, [rsp+318h+var_258]; struct DLL_VALIDATION_DATA *
0x18003926b  lea     rcx, [rsp+318h+Filename]; unsigned __int16 *
0x180039273  call    ?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z; GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)
0x180039278  mov     edi, eax
0x18003927a  mov     [rsp+318h+var_2D8], eax
0x18003927e  test    eax, eax
0x180039280  jnz     loc_180039324
0x180039286  mov     eax, dword ptr [rsp+318h+var_258+4]
0x18003928d  cmp     [rsi+19Ch], eax
0x180039293  jnz     short loc_1800392BC
0x180039295  mov     eax, dword ptr [rsp+318h+var_258]
0x18003929c  cmp     [rsi+198h], eax
0x1800392a2  jnz     short loc_1800392BC
0x1800392a4  mov     rax, qword ptr [rsp+318h+var_258+8]
0x1800392ac  cmp     [rsi+1A0h], rax
0x1800392b3  jnz     short loc_1800392BC
0x1800392b5  or      dword ptr [r13+0], 20h
0x1800392ba  jmp     short loc_180039324
0x1800392bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392c3  test    [rcx+1Ch], r14b
0x1800392c7  jz      short loc_1800392E7
0x1800392c9  cmp     byte ptr [rcx+19h], 2
0x1800392cd  jb      short loc_1800392E7
0x1800392cf  mov     edx, 12h
0x1800392d4  mov     r9, r15
0x1800392d7  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x1800392de  mov     rcx, [rcx+10h]
0x1800392e2  call    WPP_SF_S
0x1800392e7  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x1800392ee  mov     rdx, [rsp+318h+var_2B8]
0x1800392f3  mov     rdx, [rdx]; HKEY
0x1800392f6  mov     ecx, 7D3h; unsigned int
0x1800392fb  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180039300  test    eax, eax
0x180039302  jz      short loc_180039324
0x180039304  test    cs:Microsoft_Windows_PerflibEnableBits, r14b
0x18003930b  jz      short loc_180039324
0x18003930d  mov     r9, r15
0x180039310  mov     rax, [rsp+318h+var_2D0]
0x180039315  mov     r8, [rax]
0x180039318  lea     rdx, PERFLIB_NOT_TRUSTED_FILE
0x18003931f  call    McTemplateU0zz_EtwEventWriteTransfer
0x180039324  mov     rdx, [rsi+18h]; lpProcName
0x180039328  mov     rax, [rsp+318h+var_2C0]
0x18003932d  mov     rcx, [rax]; hModule
0x180039330  call    cs:__imp_GetProcAddress
0x180039336  lea     rcx, [rsi+10h]
0x18003933a  mov     [rsp+318h+var_290], rcx
0x180039342  mov     [rcx], rax
0x180039345  test    rax, rax
0x180039348  jnz     loc_1800393D2
0x18003934e  call    cs:__imp_GetLastError
0x180039354  mov     edi, eax
0x180039356  mov     [rsp+318h+var_2D8], eax
0x18003935a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039361  test    [rcx+1Ch], r14b
0x180039365  jz      short loc_18003938B
0x180039367  cmp     byte ptr [rcx+19h], 2
0x18003936b  jb      short loc_18003938B
0x18003936d  mov     edx, 13h
0x180039372  mov     dword ptr [rsp+318h+var_2F0], eax
0x180039376  mov     rax, [rsi+18h]
0x18003937a  mov     [rsp+318h+var_2F8], rax
0x18003937f  mov     r9, r15
0x180039382  mov     rcx, [rcx+10h]
0x180039386  call    WPP_SF_Ssd
0x18003938b  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x180039392  mov     rax, [rsp+318h+var_2B8]
0x180039397  mov     rdx, [rax]; HKEY
0x18003939a  mov     ecx, 3EDh; unsigned int
0x18003939f  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x1800393a4  test    eax, eax
0x1800393a6  jz      short loc_1800393D2
0x1800393a8  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x1800393af  jz      short loc_1800393D2
0x1800393b1  mov     dword ptr [rsp+318h+var_2F0], edi
0x1800393b5  mov     [rsp+318h+var_2F8], r15
0x1800393ba  mov     rax, [rsp+318h+var_2D0]
0x1800393bf  mov     r9, [rax]
0x1800393c2  mov     r8, [rsi+18h]
0x1800393c6  lea     rdx, PERFLIB_OPEN_PROC_NOT_FOUND
0x1800393cd  call    McTemplateU0szzq_EtwEventWriteTransfer
0x1800393d2  test    edi, edi
0x1800393d4  jnz     loc_180039526
0x1800393da  mov     rdx, [rsi+30h]; lpProcName
0x1800393de  mov     rax, [rsp+318h+var_2C0]
0x1800393e3  mov     rcx, [rax]; hModule
0x1800393e6  call    cs:__imp_GetProcAddress
0x1800393ec  mov     [rsi+28h], rax
0x1800393f0  test    rax, rax
0x1800393f3  jnz     loc_18003947B
0x1800393f9  call    cs:__imp_GetLastError
0x1800393ff  mov     edi, eax
0x180039401  mov     [rsp+318h+var_2D8], eax
0x180039405  mov     rcx, cs:WPP_GLOBAL_Control
0x18003940c  test    [rcx+1Ch], r14b
0x180039410  jz      short loc_180039434
0x180039412  cmp     byte ptr [rcx+19h], 2
0x180039416  jb      short loc_180039434
0x180039418  mov     edx, 14h
0x18003941d  mov     dword ptr [rsp+318h+var_2F8], eax
0x180039421  mov     r9, r15
0x180039424  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003942b  mov     rcx, [rcx+10h]
0x18003942f  call    WPP_SF_Sd
0x180039434  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x18003943b  mov     rax, [rsp+318h+var_2B8]
0x180039440  mov     rdx, [rax]; HKEY
0x180039443  mov     ecx, 3EEh; unsigned int
0x180039448  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18003944d  test    eax, eax
0x18003944f  jz      short loc_18003947B
0x180039451  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180039458  jz      short loc_18003947B
0x18003945a  mov     dword ptr [rsp+318h+var_2F0], edi
0x18003945e  mov     [rsp+318h+var_2F8], r15
0x180039463  mov     rax, [rsp+318h+var_2D0]
0x180039468  mov     r9, [rax]
0x18003946b  mov     r8, [rsi+30h]
0x18003946f  lea     rdx, PERFLIB_COLLECT_PROC_NOT_FOUND
0x180039476  call    McTemplateU0szzq_EtwEventWriteTransfer
0x18003947b  test    edi, edi
0x18003947d  jnz     loc_180039526
0x180039483  mov     rdx, [rsi+48h]; lpProcName
0x180039487  mov     rax, [rsp+318h+var_2C0]
0x18003948c  mov     rcx, [rax]; hModule
0x18003948f  call    cs:__imp_GetProcAddress
0x180039495  mov     [rsi+40h], rax
0x180039499  test    rax, rax
0x18003949c  jnz     loc_180039526
0x1800394a2  call    cs:__imp_GetLastError
0x1800394a8  mov     edi, eax
0x1800394aa  mov     [rsp+318h+var_2D8], eax
0x1800394ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394b5  test    [rcx+1Ch], r14b
0x1800394b9  jz      short loc_1800394DF
0x1800394bb  cmp     byte ptr [rcx+19h], 2
0x1800394bf  jb      short loc_1800394DF
0x1800394c1  mov     edx, 15h
0x1800394c6  mov     dword ptr [rsp+318h+var_2F0], eax
0x1800394ca  mov     rax, [rsi+48h]
0x1800394ce  mov     [rsp+318h+var_2F8], rax
  ... truncated ...
```
