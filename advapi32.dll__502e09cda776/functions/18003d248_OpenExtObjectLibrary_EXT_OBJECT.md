# OpenExtObjectLibrary(EXT_OBJECT *)

- ea: `0x18003d248`
- end: `0x18003dc20`
- name: `?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z`
- size: `2520`
- prototype: `unsigned int __fastcall(struct EXT_OBJECT *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dc80`

## callees

- `0x18000eac8`
- `0x18000ecf0`
- `0x18002a6a8`
- `0x18002f718`
- `0x180033e14`
- `0x180038e74`
- `0x180039070`
- `0x18003b544`
- `0x18003d248`
- `0x18003dc28`
- `0x18003dde8`
- `0x18003e354`
- `0x18003fb18`
- `0x18003fd04`
- `0x180063d64`
- `0x180063f10`
- `0x180064724`
- `0x180064800`
- `0x180064928`
- `0x180065088`
- `0x180065194`
- `0x180065238`
- `0x1800652fc`
- `0x180065384`
- `0x1800720b0`
- `0x180074010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d904`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d904`
- `KERNEL32!GetLastError` at `0x18003d4c9`
- `KERNEL32!GetLastError` at `0x18003d5f8`
- `KERNEL32!GetLastError` at `0x18003d6af`
- `KERNEL32!GetLastError` at `0x18003d764`
- `KERNEL32!GetLastError` at `0x18003da6d`
- `KERNEL32!GetLastError` at `0x18003d4c9`
- `KERNEL32!GetLastError` at `0x18003d5f8`
- `KERNEL32!GetLastError` at `0x18003d6af`
- `KERNEL32!GetLastError` at `0x18003d764`
- `KERNEL32!GetLastError` at `0x18003da6d`
- `KERNEL32!GetProcAddress` at `0x18003d5d4`
- `KERNEL32!GetProcAddress` at `0x18003d696`
- `KERNEL32!GetProcAddress` at `0x18003d74b`
- `KERNEL32!GetProcAddress` at `0x18003d5d4`
- `KERNEL32!GetProcAddress` at `0x18003d696`
- `KERNEL32!GetProcAddress` at `0x18003d74b`
- `KERNEL32!FreeLibrary` at `0x18003da45`
- `KERNEL32!FreeLibrary` at `0x18003da45`
- `KERNEL32!LoadLibraryExW` at `0x18003d455`
- `KERNEL32!LoadLibraryExW` at `0x18003d455`
- `KERNEL32!GetModuleFileNameW` at `0x18003d4b9`
- `KERNEL32!GetModuleFileNameW` at `0x18003d4b9`
- `KERNEL32!SetErrorMode` at `0x18003d41a`
- `KERNEL32!SetErrorMode` at `0x18003db62`
- `KERNEL32!SetErrorMode` at `0x18003d41a`
- `KERNEL32!SetErrorMode` at `0x18003db62`

## pseudocode

```c
__int64 __fastcall OpenExtObjectLibrary(struct EXT_OBJECT *a1, __int64 a2, unsigned int *a3)
{
  int *v4; // r13
  DWORD LastError; // edi
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
    LastError = OpenRemoteExtObjectLibrary(a1);
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
0x18003d248  mov     [rsp+arg_8], rbx
0x18003d24d  mov     [rsp+arg_10], rsi
0x18003d252  push    rdi
0x18003d253  push    r12
0x18003d255  push    r13
0x18003d257  push    r14
0x18003d259  push    r15
0x18003d25b  sub     rsp, 2F0h
0x18003d262  mov     rax, cs:__security_cookie
0x18003d269  xor     rax, rsp
0x18003d26c  mov     [rsp+318h+var_38], rax
0x18003d274  mov     rsi, rcx
0x18003d277  mov     [rsp+318h+var_298], rcx
0x18003d27f  xor     ebx, ebx
0x18003d281  mov     dword ptr [rsp+318h+var_2C4], ebx
0x18003d285  xorps   xmm0, xmm0
0x18003d288  movups  [rsp+318h+var_258], xmm0
0x18003d290  xorps   xmm1, xmm1
0x18003d293  xor     eax, eax
0x18003d295  movups  [rsp+318h+var_280], xmm1
0x18003d29d  movups  [rsp+318h+var_270], xmm1
0x18003d2a5  mov     [rsp+318h+var_260], rax
0x18003d2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d2b4  lea     r14d, [rbx+4]
0x18003d2b8  test    [rcx+1Ch], r14b
0x18003d2bc  jz      short loc_18003D2DE
0x18003d2be  cmp     [rcx+19h], r14b
0x18003d2c2  jb      short loc_18003D2DE
0x18003d2c4  lea     edx, [rbx+0Dh]
0x18003d2c7  mov     r9, [rsi+188h]
0x18003d2ce  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003d2d5  mov     rcx, [rcx+10h]
0x18003d2d9  call    WPP_SF_S
0x18003d2de  lea     r13, [rsi+17Ch]
0x18003d2e5  mov     [rsp+318h+var_288], r13
0x18003d2ed  test    byte ptr [r13+0], 10h
0x18003d2f2  jz      short loc_18003D2FE
0x18003d2f4  mov     edi, 422h
0x18003d2f9  jmp     loc_18003DB9B
0x18003d2fe  mov     [rsp+318h+var_2D4], ebx
0x18003d302  mov     [rsp+318h+var_2AC], ebx
0x18003d306  lea     rax, [rsi+58h]
0x18003d30a  mov     [rsp+318h+var_2C0], rax
0x18003d30f  cmp     [rax], rbx
0x18003d312  jnz     loc_18003DB70
0x18003d318  mov     rax, [rsi+188h]
0x18003d31f  lea     r15, ?NULL_STRING@@3QBGB; ushort const near * const NULL_STRING
0x18003d326  test    rax, rax
0x18003d329  cmovnz  r15, rax
0x18003d32d  mov     [rsp+318h+var_2A0], r15
0x18003d332  mov     [rsp+318h+uMode], ebx
0x18003d336  mov     [rsp+318h+var_2D8], r14d
0x18003d33b  mov     dword ptr [rsp+318h+var_2C4], ebx
0x18003d33f  lea     rax, [rsi+68h]
0x18003d343  mov     [rsp+318h+var_2B8], rax
0x18003d348  mov     r12d, 1
0x18003d34e  mov     [rsp+318h+var_2E8], r12d; int
0x18003d353  lea     rcx, [rsp+318h+var_2D8]
0x18003d358  mov     [rsp+318h+var_2F0], rcx; unsigned int *
0x18003d35d  lea     rcx, [rsp+318h+var_2C4]
0x18003d362  mov     [rsp+318h+var_2F8], rcx; unsigned __int8 *
0x18003d367  lea     r9, [rsp+318h+uMode]; unsigned int *
0x18003d36c  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x18003d373  mov     rcx, [rax]; KeyHandle
0x18003d376  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18003d37b  mov     edi, eax
0x18003d37d  mov     [rsp+318h+var_2D8], eax
0x18003d381  test    eax, eax
0x18003d383  jnz     short loc_18003D401
0x18003d385  cmp     [rsp+318h+uMode], r14d
0x18003d38a  jnz     short loc_18003D401
0x18003d38c  and     dword ptr [r13+0], 0FFFFFFEFh
0x18003d391  mov     eax, [r13+0]
0x18003d395  mov     ecx, dword ptr [rsp+318h+var_2C4]
0x18003d399  sub     ecx, r12d
0x18003d39c  jz      short loc_18003D3CD
0x18003d39e  cmp     ecx, 3
0x18003d3a1  jnz     short loc_18003D40C
0x18003d3a3  mov     ecx, r12d
0x18003d3a6  mov     [rsp+318h+var_2D4], ecx
0x18003d3aa  mov     [rsp+318h+var_2AC], ecx
0x18003d3ae  or      eax, 10h
0x18003d3b1  mov     [r13+0], eax
0x18003d3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3bc  test    [rcx+1Ch], r14b
0x18003d3c0  jz      short loc_18003D40C
0x18003d3c2  cmp     byte ptr [rcx+19h], 3
0x18003d3c6  jb      short loc_18003D40C
0x18003d3c8  lea     edx, [rdi+10h]
0x18003d3cb  jmp     short loc_18003D3EC
0x18003d3cd  or      eax, 10h
0x18003d3d0  mov     [r13+0], eax
0x18003d3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3db  test    [rcx+1Ch], r14b
0x18003d3df  jz      short loc_18003D40C
0x18003d3e1  cmp     byte ptr [rcx+19h], 3
0x18003d3e5  jb      short loc_18003D40C
0x18003d3e7  mov     edx, 0Eh
0x18003d3ec  mov     r9, r15
0x18003d3ef  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003d3f6  mov     rcx, [rcx+10h]
0x18003d3fa  call    WPP_SF_S
0x18003d3ff  jmp     short loc_18003D40C
0x18003d401  mov     edi, ebx
0x18003d403  mov     [rsp+318h+var_2D8], ebx
0x18003d407  and     dword ptr [r13+0], 0FFFFFFEFh
0x18003d40c  test    byte ptr [r13+0], 10h
0x18003d411  jnz     loc_18003DB7E
0x18003d417  mov     ecx, r12d; uMode
0x18003d41a  call    cs:__imp_SetErrorMode
0x18003d421  nop     dword ptr [rax+rax+00h]
0x18003d426  mov     [rsp+318h+uMode], eax
0x18003d42a  lea     r12, [rsi+60h]
0x18003d42e  mov     [rsp+318h+var_2D0], r12
0x18003d433  mov     rcx, [r12]
0x18003d437  call    PerflibciPathIsRelative
0x18003d43c  neg     eax
0x18003d43e  sbb     r8d, r8d
0x18003d441  and     r8d, 700h
0x18003d448  add     r8d, 900h; dwFlags
0x18003d44f  xor     edx, edx; hFile
0x18003d451  mov     rcx, [r12]; lpLibFileName
0x18003d455  call    cs:__imp_LoadLibraryExW
0x18003d45c  nop     dword ptr [rax+rax+00h]
0x18003d461  mov     rcx, [rsp+318h+var_2C0]
0x18003d466  mov     [rcx], rax
0x18003d469  test    rax, rax
0x18003d46c  jz      loc_18003DA6D
0x18003d472  mov     r12d, ebx
0x18003d475  mov     [rsp+318h+hMem], rbx
0x18003d47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d481  test    [rcx+1Ch], r14b
0x18003d485  jz      short loc_18003D4A3
0x18003d487  cmp     [rcx+19h], r14b
0x18003d48b  jb      short loc_18003D4A3
0x18003d48d  mov     [rsp+318h+var_2F8], rax
0x18003d492  mov     r9, [rsp+318h+var_2D0]
0x18003d497  mov     r9, [r9]
0x18003d49a  mov     rcx, [rcx+10h]
0x18003d49e  call    WPP_SF_Sq
0x18003d4a3  mov     r8d, 104h; nSize
0x18003d4a9  lea     rdx, [rsp+318h+Filename]; lpFilename
0x18003d4b1  mov     rax, [rsp+318h+var_2C0]
0x18003d4b6  mov     rcx, [rax]; hModule
0x18003d4b9  call    cs:__imp_GetModuleFileNameW
0x18003d4c0  nop     dword ptr [rax+rax+00h]
0x18003d4c5  test    eax, eax
0x18003d4c7  jnz     short loc_18003D4DB
0x18003d4c9  call    cs:__imp_GetLastError
0x18003d4d0  nop     dword ptr [rax+rax+00h]
0x18003d4d5  mov     edi, eax
0x18003d4d7  mov     [rsp+318h+var_2D8], eax
0x18003d4db  test    edi, edi
0x18003d4dd  jnz     loc_18003D5C8
0x18003d4e3  cmp     [rsi+1A0h], rbx
0x18003d4ea  jle     loc_18003D5C8
0x18003d4f0  mov     rcx, r15
0x18003d4f3  call    ServiceIsTrustedByDefault
0x18003d4f8  test    eax, eax
0x18003d4fa  jnz     short loc_18003D559
0x18003d4fc  xorps   xmm0, xmm0
0x18003d4ff  movups  [rsp+318h+var_258], xmm0
0x18003d507  lea     rdx, [rsp+318h+var_258]; struct DLL_VALIDATION_DATA *
0x18003d50f  lea     rcx, [rsp+318h+Filename]; unsigned __int16 *
0x18003d517  call    ?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z; GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)
0x18003d51c  mov     edi, eax
0x18003d51e  mov     [rsp+318h+var_2D8], eax
0x18003d522  test    eax, eax
0x18003d524  jnz     loc_18003D5C8
0x18003d52a  mov     eax, dword ptr [rsp+318h+var_258+4]
0x18003d531  cmp     [rsi+19Ch], eax
0x18003d537  jnz     short loc_18003D560
0x18003d539  mov     eax, dword ptr [rsp+318h+var_258]
0x18003d540  cmp     [rsi+198h], eax
0x18003d546  jnz     short loc_18003D560
0x18003d548  mov     rax, qword ptr [rsp+318h+var_258+8]
0x18003d550  cmp     [rsi+1A0h], rax
0x18003d557  jnz     short loc_18003D560
0x18003d559  or      dword ptr [r13+0], 20h
0x18003d55e  jmp     short loc_18003D5C8
0x18003d560  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d567  test    [rcx+1Ch], r14b
0x18003d56b  jz      short loc_18003D58B
0x18003d56d  cmp     byte ptr [rcx+19h], 2
0x18003d571  jb      short loc_18003D58B
0x18003d573  mov     edx, 12h
0x18003d578  mov     r9, r15
0x18003d57b  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003d582  mov     rcx, [rcx+10h]
0x18003d586  call    WPP_SF_S
0x18003d58b  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x18003d592  mov     rdx, [rsp+318h+var_2B8]
0x18003d597  mov     rdx, [rdx]; HKEY
0x18003d59a  mov     ecx, 7D3h; unsigned int
0x18003d59f  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18003d5a4  test    eax, eax
0x18003d5a6  jz      short loc_18003D5C8
0x18003d5a8  test    cs:Microsoft_Windows_PerflibEnableBits, r14b
0x18003d5af  jz      short loc_18003D5C8
0x18003d5b1  mov     r9, r15
0x18003d5b4  mov     rax, [rsp+318h+var_2D0]
0x18003d5b9  mov     r8, [rax]
0x18003d5bc  lea     rdx, PERFLIB_NOT_TRUSTED_FILE
0x18003d5c3  call    McTemplateU0zz_EtwEventWriteTransfer
0x18003d5c8  mov     rdx, [rsi+18h]; lpProcName
0x18003d5cc  mov     rax, [rsp+318h+var_2C0]
0x18003d5d1  mov     rcx, [rax]; hModule
0x18003d5d4  call    cs:__imp_GetProcAddress
0x18003d5db  nop     dword ptr [rax+rax+00h]
0x18003d5e0  lea     rcx, [rsi+10h]
0x18003d5e4  mov     [rsp+318h+var_290], rcx
0x18003d5ec  mov     [rcx], rax
0x18003d5ef  test    rax, rax
0x18003d5f2  jnz     loc_18003D682
0x18003d5f8  call    cs:__imp_GetLastError
0x18003d5ff  nop     dword ptr [rax+rax+00h]
0x18003d604  mov     edi, eax
0x18003d606  mov     [rsp+318h+var_2D8], eax
0x18003d60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d611  test    [rcx+1Ch], r14b
0x18003d615  jz      short loc_18003D63B
0x18003d617  cmp     byte ptr [rcx+19h], 2
0x18003d61b  jb      short loc_18003D63B
0x18003d61d  mov     edx, 13h
0x18003d622  mov     dword ptr [rsp+318h+var_2F0], eax
0x18003d626  mov     rax, [rsi+18h]
0x18003d62a  mov     [rsp+318h+var_2F8], rax
0x18003d62f  mov     r9, r15
0x18003d632  mov     rcx, [rcx+10h]
0x18003d636  call    WPP_SF_Ssd
0x18003d63b  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x18003d642  mov     rax, [rsp+318h+var_2B8]
0x18003d647  mov     rdx, [rax]; HKEY
0x18003d64a  mov     ecx, 3EDh; unsigned int
0x18003d64f  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18003d654  test    eax, eax
0x18003d656  jz      short loc_18003D682
0x18003d658  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x18003d65f  jz      short loc_18003D682
0x18003d661  mov     dword ptr [rsp+318h+var_2F0], edi
0x18003d665  mov     [rsp+318h+var_2F8], r15
0x18003d66a  mov     rax, [rsp+318h+var_2D0]
0x18003d66f  mov     r9, [rax]
0x18003d672  mov     r8, [rsi+18h]
0x18003d676  lea     rdx, PERFLIB_OPEN_PROC_NOT_FOUND
0x18003d67d  call    McTemplateU0szzq_EtwEventWriteTransfer
0x18003d682  test    edi, edi
0x18003d684  jnz     loc_18003D7EE
0x18003d68a  mov     rdx, [rsi+30h]; lpProcName
0x18003d68e  mov     rax, [rsp+318h+var_2C0]
0x18003d693  mov     rcx, [rax]; hModule
0x18003d696  call    cs:__imp_GetProcAddress
0x18003d69d  nop     dword ptr [rax+rax+00h]
0x18003d6a2  mov     [rsi+28h], rax
0x18003d6a6  test    rax, rax
0x18003d6a9  jnz     loc_18003D737
0x18003d6af  call    cs:__imp_GetLastError
0x18003d6b6  nop     dword ptr [rax+rax+00h]
0x18003d6bb  mov     edi, eax
0x18003d6bd  mov     [rsp+318h+var_2D8], eax
0x18003d6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d6c8  test    [rcx+1Ch], r14b
0x18003d6cc  jz      short loc_18003D6F0
0x18003d6ce  cmp     byte ptr [rcx+19h], 2
0x18003d6d2  jb      short loc_18003D6F0
0x18003d6d4  mov     edx, 14h
0x18003d6d9  mov     dword ptr [rsp+318h+var_2F8], eax
0x18003d6dd  mov     r9, r15
0x18003d6e0  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18003d6e7  mov     rcx, [rcx+10h]
0x18003d6eb  call    WPP_SF_Sd
0x18003d6f0  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x18003d6f7  mov     rax, [rsp+318h+var_2B8]
0x18003d6fc  mov     rdx, [rax]; HKEY
0x18003d6ff  mov     ecx, 3EEh; unsigned int
0x18003d704  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18003d709  test    eax, eax
0x18003d70b  jz      short loc_18003D737
0x18003d70d  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x18003d714  jz      short loc_18003D737
0x18003d716  mov     dword ptr [rsp+318h+var_2F0], edi
0x18003d71a  mov     [rsp+318h+var_2F8], r15
0x18003d71f  mov     rax, [rsp+318h+var_2D0]
0x18003d724  mov     r9, [rax]
0x18003d727  mov     r8, [rsi+30h]
0x18003d72b  lea     rdx, PERFLIB_COLLECT_PROC_NOT_FOUND
0x18003d732  call    McTemplateU0szzq_EtwEventWriteTransfer
0x18003d737  test    edi, edi
0x18003d739  jnz     loc_18003D7EE
0x18003d73f  mov     rdx, [rsi+48h]; lpProcName
0x18003d743  mov     rax, [rsp+318h+var_2C0]
0x18003d748  mov     rcx, [rax]; hModule
0x18003d74b  call    cs:__imp_GetProcAddress
0x18003d752  nop     dword ptr [rax+rax+00h]
0x18003d757  mov     [rsi+40h], rax
0x18003d75b  test    rax, rax
0x18003d75e  jnz     loc_18003D7EE
0x18003d764  call    cs:__imp_GetLastError
0x18003d76b  nop     dword ptr [rax+rax+00h]
0x18003d770  mov     edi, eax
  ... truncated ...
```
