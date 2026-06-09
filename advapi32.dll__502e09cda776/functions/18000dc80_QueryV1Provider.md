# QueryV1Provider

- ea: `0x18000dc80`
- end: `0x18000e6a3`
- name: `QueryV1Provider`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d240`

## callees

- `0x18000dc80`
- `0x18000e6ac`
- `0x18000e704`
- `0x18000eac8`
- `0x18002a5f0`
- `0x18002a6a8`
- `0x18002acc4`
- `0x18002f718`
- `0x1800372d4`
- `0x180038e74`
- `0x180039070`
- `0x18003d248`
- `0x18003e354`
- `0x18003fb18`
- `0x18003fd04`
- `0x18004165c`
- `0x180063b38`
- `0x180063d64`
- `0x180063f10`
- `0x180064800`
- `0x180064844`
- `0x180064928`
- `0x180064a04`
- `0x180064af4`
- `0x180064be4`
- `0x180064cb8`
- `0x180064d50`
- `0x18007204e`
- `0x18007205a`

## import_xrefs

- `ntdll!RtlQueryPerformanceCounter` at `0x18000e109`
- `ntdll!RtlQueryPerformanceCounter` at `0x18000e145`
- `ntdll!RtlQueryPerformanceCounter` at `0x18000e109`
- `ntdll!RtlQueryPerformanceCounter` at `0x18000e145`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd2b`
- `KERNEL32!LocalFree` at `0x18000e540`
- `KERNEL32!LocalFree` at `0x18000e540`
- `KERNEL32!ReleaseMutex` at `0x18000ddcc`
- `KERNEL32!ReleaseMutex` at `0x18000ddcc`

## pseudocode

```c
__int64 QueryV1Provider(__int64 a1, __int64 a2, __int64 a3, char *a4, ...)
{
  char *v4; // rsi
  unsigned int v5; // ebx
  int v7; // r14d
  int v8; // eax
  unsigned int v9; // esi
  int v10; // ebx
  __int64 v11; // rdx
  unsigned int *v12; // r8
  unsigned int v13; // eax
  int v14; // r15d
  unsigned int v15; // ebx
  char *v16; // rax
  char *v17; // r13
  _QWORD *started; // r12
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  unsigned __int64 v23; // r15
  __int64 v24; // rdx
  __int64 v25; // r8
  _QWORD *v26; // rcx
  unsigned int v27; // eax
  int v28; // r12d
  int v29; // ecx
  int v30; // r8d
  int v31; // eax
  void *v32; // r15
  int v33; // edx
  int v34; // ecx
  int v35; // ecx
  __int64 v36; // rcx
  size_t Size; // [rsp+60h] [rbp-E8h] BYREF
  int v39; // [rsp+68h] [rbp-E0h]
  void *v40; // [rsp+70h] [rbp-D8h] BYREF
  int v41; // [rsp+84h] [rbp-C4h]
  unsigned int v42; // [rsp+88h] [rbp-C0h]
  HLOCAL hMem; // [rsp+90h] [rbp-B8h]
  void *Src; // [rsp+98h] [rbp-B0h]
  __int64 v45; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-90h]
  __int64 v48; // [rsp+C0h] [rbp-88h]
  __int64 v49; // [rsp+C8h] [rbp-80h]
  __int64 v50; // [rsp+D0h] [rbp-78h]
  char *v51; // [rsp+E0h] [rbp-68h]
  unsigned __int64 v52[2]; // [rsp+E8h] [rbp-60h] BYREF
  __int128 v53; // [rsp+F8h] [rbp-50h]
  __int64 v54; // [rsp+108h] [rbp-40h]
  __int64 v57; // [rsp+170h] [rbp+28h] BYREF
  va_list va; // [rsp+170h] [rbp+28h]
  _DWORD *v59; // [rsp+178h] [rbp+30h]
  _DWORD *v60; // [rsp+180h] [rbp+38h]
  va_list va1; // [rsp+188h] [rbp+40h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v57 = va_arg(va1, _QWORD);
  v59 = va_arg(va1, _DWORD *);
  v60 = va_arg(va1, _DWORD *);
  v4 = a4;
  v5 = a3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, (unsigned int)a3);
  v7 = 0;
  v41 = 0;
  Size = (unsigned int)v57;
  if ( !*(_QWORD *)(a2 + 88) || v5 <= 0xA && (v8 = 1554, _bittest(&v8, v5)) )
  {
    v9 = PerfpLockExtObject(a2, a2, a3);
    if ( v9 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
    }
    else
    {
      if ( !*(_QWORD *)(a2 + 88) )
      {
        v10 = *(_DWORD *)(a2 + 520);
        if ( GetCurrentThreadId() == v10 || *(_DWORD *)(a2 + 484) )
        {
LABEL_16:
          PerfpUnlockExtObject(a2);
          goto LABEL_124;
        }
        v13 = OpenExtObjectLibrary((struct EXT_OBJECT *)a2, v11, v12);
        v9 = v13;
        if ( v13 )
        {
          if ( v13 != 1058
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *(_QWORD *)(a2 + 392),
              v13);
          }
          goto LABEL_16;
        }
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
      ReleaseMutex(*(HANDLE *)(a2 + 8));
    }
    v4 = a4;
  }
  v14 = 0;
  if ( (lPerflibConfigFlags & 4) != 0 )
  {
    v15 = 4;
  }
  else
  {
    v15 = 1;
    if ( (*(_DWORD *)(a2 + 380) & 0x20) != 0 )
      v15 = lExtCounterTestLevel;
    LOBYTE(v14) = (*(_DWORD *)(a2 + 380) & 0x20) == 0;
  }
  v42 = v15;
  v40 = 0;
  if ( v15 >= 4 )
  {
    v40 = v4;
    v17 = v4;
  }
  else
  {
    v16 = (char *)operator new((unsigned int)(Size + 2048), (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
      memset_0(v16, 0, (unsigned int)(Size + 2048));
  }
  v51 = v17;
  if ( v17 )
  {
    if ( v15 >= 4 )
    {
      v49 = 0;
      v47 = 0;
      v48 = 0;
    }
    else
    {
      v49 = (__int64)v17;
      v40 = v17 + 1024;
      v48 = (__int64)&v17[(unsigned int)Size + 1024];
      v47 = v48 + 1024;
      memset_0(v17, 165, 0x400u);
      memset_0((void *)v48, 165, 0x400u);
    }
    Src = v40;
    v50 = 0;
    started = 0;
    hMem = 0;
    v39 = 0;
    v46 = 0;
    v45 = 0;
    v9 = PerfpLockExtObject(a2, a2, a3);
    LODWORD(v57) = v9;
    if ( v9 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
      if ( (unsigned int)PerfpThrottleError(1015, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
        && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
      {
        McTemplateU0zz_EtwEventWriteTransfer(v21, PERFLIB_COLLECTION_HUNG, *(_QWORD *)(a2 + 392), *(_QWORD *)(a2 + 96));
      }
    }
    else
    {
      v39 = 1;
    }
    if ( v9 || !*(_QWORD *)(a2 + 40) )
    {
      v31 = 0;
      Size = 0;
      v28 = v39;
      goto LABEL_89;
    }
    if ( v14 )
    {
      v52[1] = 0;
      v53 = 0;
      v54 = 0;
      v52[0] = 0;
      v52[1] = *(_QWORD *)(a2 + 96);
      *(_QWORD *)&v53 = *(_QWORD *)(a2 + 392);
      DWORD2(v53) = *(_DWORD *)(a2 + 56);
      HIDWORD(v53) = 1015;
      v54 = a2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      started = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)v52);
      hMem = started;
      if ( !started )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_58;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      }
    }
    v22 = WPP_GLOBAL_Control;
LABEL_58:
    v23 = (unsigned int)Size;
    if ( (*((_BYTE *)v22 + 28) & 8) != 0 && *((_BYTE *)v22 + 25) >= 4u )
      WPP_SF_SSdd(v22[2], v19, v20, *(_QWORD *)(a2 + 392), a1, Size, SBYTE4(Size));
    RtlQueryPerformanceCounter(&v46);
    v9 = CallExtObj(a2, a1, (unsigned int)&v40, (unsigned int)&Size, (__int64)&Size + 4);
    LODWORD(v57) = v9;
    RtlQueryPerformanceCounter(&v45);
    v26 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, v9, Size, HIDWORD(Size));
      v26 = WPP_GLOBAL_Control;
    }
    if ( started )
    {
      if ( (*((_BYTE *)v26 + 28) & 0x40) != 0 && *((_BYTE *)v26 + 25) >= 4u )
        WPP_SF_(v26[2], 24, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      KillPerflibFunctionTimer(started);
      hMem = 0;
    }
    v27 = Size;
    *(_DWORD *)(a2 + 468) = Size;
    if ( v27 > *(_DWORD *)(a2 + 472) )
      *(_DWORD *)(a2 + 472) = v27;
    if ( v9 == 234 && (unsigned int)v23 > *(_DWORD *)(a2 + 476) )
      *(_DWORD *)(a2 + 476) = v23;
    v50 = (__int64)v40;
    *(_QWORD *)(a2 + 400) = GetTimeAsLongLong();
    PerfpUnlockExtObject(a2);
    v28 = 0;
    v39 = 0;
    if ( (unsigned int)Size <= (unsigned int)v23 )
    {
      v32 = Src;
      if ( (unsigned __int8)ValidateObjectTypeCount((struct EXT_OBJECT *)a2, HIDWORD(Size), Size) )
      {
        v31 = Size;
      }
      else
      {
        v31 = 0;
        Size = 0;
      }
LABEL_90:
      if ( v9 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a2 + 464));
      }
      else if ( v31 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a2 + 448));
        *(_QWORD *)(a2 + 440) += v45 - v46;
        v7 = Size;
        if ( (Size & 7) != 0 && (lPerflibConfigFlags & 1) == 0 && (*(_BYTE *)(a2 + 380) & 8) == 0 )
        {
          if ( (unsigned int)PerfpThrottleError(1016, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
          {
            McTemplateU0zzpq_EtwEventWriteTransfer(
              v34,
              v33,
              *(_QWORD *)(a2 + 96),
              *(_QWORD *)(a2 + 392),
              (char)v40,
              Size);
          }
          *(_DWORD *)(a2 + 380) |= 8u;
          v7 = Size;
        }
        if ( v15 < 4 )
        {
          if ( (unsigned int)ValidateSafeBuffer(
                               (struct EXT_OBJECT *)a2,
                               HIDWORD(Size),
                               (__int64)v32,
                               v50,
                               v49,
                               v48,
                               v47,
                               v15,
                               (__int64)va) )
          {
            v7 = Size;
            memmove_0(a4, v32, (unsigned int)Size);
            v9 = v57;
            v41 = v7;
            goto LABEL_109;
          }
          v7 = 0;
          Size = 0;
          v9 = v57;
        }
        v41 = v7;
LABEL_109:
        if ( v15 < 4 )
          LocalFree(v17);
        if ( !v9 || v9 == 234 || v9 == 258 )
          goto LABEL_122;
        goto LABEL_116;
      }
      if ( v28 )
      {
        PerfpUnlockExtObject(a2);
        v39 = 0;
      }
      HIDWORD(Size) = 0;
      goto LABEL_109;
    }
    if ( (unsigned int)PerfpThrottleError(1020, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
      && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
    {
      McTemplateU0zzqq_EtwEventWriteTransfer(
        v29,
        (unsigned int)PERFLIB_INVALID_SIZE_RETURNED,
        *(_QWORD *)(a2 + 96),
        *(_QWORD *)(a2 + 392),
        v23,
        Size);
    }
    if ( (lPerflibConfigFlags & 4) == 0 && (*(_BYTE *)(a2 + 380) & 0x20) == 0 )
      DisablePerfLibrary((struct EXT_OBJECT *)a2, 1u, 0x3FCu, v23, (unsigned int)Size);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v30, *(_QWORD *)(a2 + 392), Size, v23);
    v31 = 0;
    Size = 0;
LABEL_89:
    v32 = Src;
    goto LABEL_90;
  }
  v9 = 14;
LABEL_116:
  if ( (unsigned int)PerfpThrottleError(1014, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
    && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
  {
    McTemplateU0zzq_EtwEventWriteTransfer(
      v35,
      (unsigned int)PERFLIB_COLLECT_PROC_FAILURE,
      *(_QWORD *)(a2 + 392),
      *(_QWORD *)(a2 + 96),
      v9);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
      HIDWORD(Size),
      v9);
LABEL_122:
  v36 = *(_QWORD *)(a2 + 432);
  if ( v36 )
  {
    *(_QWORD *)(v36 + 64) = *(_QWORD *)(a2 + 440);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 72LL) = *(_DWORD *)(a2 + 448);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 76LL) = *(_DWORD *)(a2 + 452);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 80LL) = *(_DWORD *)(a2 + 456);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 84LL) = *(_DWORD *)(a2 + 460);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 88LL) = *(_DWORD *)(a2 + 464);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 92LL) = *(_DWORD *)(a2 + 468);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 96LL) = *(_DWORD *)(a2 + 472);
    *(_DWORD *)(*(_QWORD *)(a2 + 432) + 100LL) = *(_DWORD *)(a2 + 476);
  }
LABEL_124:
  *v59 = v7;
  *v60 = HIDWORD(Size);
  return v9;
}

```

## disassembly

```asm
0x18000dc80  mov     [rsp+arg_18], r9
0x18000dc85  mov     [rsp+arg_8], rdx
0x18000dc8a  mov     [rsp+arg_0], rcx
0x18000dc8f  push    rbx
0x18000dc90  push    rsi
0x18000dc91  push    rdi
0x18000dc92  push    r12
0x18000dc94  push    r13
0x18000dc96  push    r14
0x18000dc98  push    r15
0x18000dc9a  sub     rsp, 110h
0x18000dca1  mov     rsi, r9
0x18000dca4  mov     ebx, r8d
0x18000dca7  mov     rdi, rdx
0x18000dcaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcb1  test    byte ptr [rcx+1Ch], 2
0x18000dcb5  jz      short loc_18000DCD5
0x18000dcb7  cmp     byte ptr [rcx+19h], 4
0x18000dcbb  jb      short loc_18000DCD5
0x18000dcbd  mov     edx, 10h
0x18000dcc2  mov     r9d, ebx
0x18000dcc5  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000dccc  mov     rcx, [rcx+10h]
0x18000dcd0  call    WPP_SF_d
0x18000dcd5  xor     ecx, ecx
0x18000dcd7  mov     dword ptr [rsp+148h+Size+4], ecx
0x18000dcdb  mov     r14d, ecx
0x18000dcde  mov     [rsp+148h+var_C4], ecx
0x18000dce5  mov     eax, dword ptr [rsp+148h+arg_20]
0x18000dcec  mov     dword ptr [rsp+148h+Size], eax
0x18000dcf0  cmp     [rdi+58h], rcx
0x18000dcf4  jz      short loc_18000DD0D
0x18000dcf6  cmp     ebx, 0Ah
0x18000dcf9  ja      loc_18000DE13
0x18000dcff  mov     eax, 612h
0x18000dd04  bt      eax, ebx
0x18000dd07  jnb     loc_18000DE13
0x18000dd0d  mov     rcx, rdi
0x18000dd10  call    PerfpLockExtObject
0x18000dd15  mov     esi, eax
0x18000dd17  test    eax, eax
0x18000dd19  jnz     loc_18000DDDA
0x18000dd1f  cmp     [rdi+58h], r14
0x18000dd23  jnz     short loc_18000DD99
0x18000dd25  mov     ebx, [rdi+208h]
0x18000dd2b  call    cs:__imp_GetCurrentThreadId
0x18000dd32  nop     dword ptr [rax+rax+00h]
0x18000dd37  cmp     eax, ebx
0x18000dd39  jz      short loc_18000DD8C
0x18000dd3b  cmp     [rdi+1E4h], r14d
0x18000dd42  jnz     short loc_18000DD8C
0x18000dd44  mov     rcx, rdi; struct EXT_OBJECT *
0x18000dd47  call    ?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z; OpenExtObjectLibrary(EXT_OBJECT *)
0x18000dd4c  mov     esi, eax
0x18000dd4e  test    eax, eax
0x18000dd50  jz      short loc_18000DD99
0x18000dd52  cmp     eax, 422h
0x18000dd57  jz      short loc_18000DD8C
0x18000dd59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd60  test    byte ptr [rcx+1Ch], 2
0x18000dd64  jz      short loc_18000DD8C
0x18000dd66  cmp     byte ptr [rcx+19h], 2
0x18000dd6a  jb      short loc_18000DD8C
0x18000dd6c  mov     edx, 11h
0x18000dd71  mov     dword ptr [rsp+148h+var_128], eax
0x18000dd75  mov     r9, [rdi+188h]
0x18000dd7c  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000dd83  mov     rcx, [rcx+10h]
0x18000dd87  call    WPP_SF_Sd
0x18000dd8c  mov     rcx, rdi
0x18000dd8f  call    PerfpUnlockExtObject
0x18000dd94  jmp     loc_18000E674
0x18000dd99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda0  test    byte ptr [rcx+1Ch], 20h
0x18000dda4  jz      short loc_18000DDC8
0x18000dda6  cmp     byte ptr [rcx+19h], 4
0x18000ddaa  jb      short loc_18000DDC8
0x18000ddac  mov     edx, 0Bh
0x18000ddb1  mov     r9, [rdi+188h]
0x18000ddb8  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000ddbf  mov     rcx, [rcx+10h]
0x18000ddc3  call    WPP_SF_S
0x18000ddc8  mov     rcx, [rdi+8]; hMutex
0x18000ddcc  call    cs:__imp_ReleaseMutex
0x18000ddd3  nop     dword ptr [rax+rax+00h]
0x18000ddd8  jmp     short loc_18000DE09
0x18000ddda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dde1  test    byte ptr [rcx+1Ch], 20h
0x18000dde5  jz      short loc_18000DE09
0x18000dde7  cmp     byte ptr [rcx+19h], 2
0x18000ddeb  jb      short loc_18000DE09
0x18000dded  mov     edx, 12h
0x18000ddf2  mov     r9, [rdi+188h]
0x18000ddf9  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000de00  mov     rcx, [rcx+10h]
0x18000de04  call    WPP_SF_S
0x18000de09  xor     ecx, ecx
0x18000de0b  mov     rsi, [rsp+148h+arg_18]
0x18000de13  mov     r15d, ecx
0x18000de16  test    byte ptr cs:?lPerflibConfigFlags@@3JA, 4; long lPerflibConfigFlags
0x18000de1d  jnz     short loc_18000DE3B
0x18000de1f  mov     eax, [rdi+17Ch]
0x18000de25  bt      eax, 5
0x18000de29  mov     ebx, 1
0x18000de2e  cmovb   ebx, cs:?lExtCounterTestLevel@@3JA; long lExtCounterTestLevel
0x18000de35  setnb   r15b
0x18000de39  jmp     short loc_18000DE40
0x18000de3b  mov     ebx, 4
0x18000de40  mov     [rsp+148h+var_C0], ebx
0x18000de47  mov     [rsp+148h+var_D8], rcx
0x18000de4c  cmp     ebx, 4
0x18000de4f  jnb     short loc_18000DE83
0x18000de51  mov     eax, dword ptr [rsp+148h+Size]
0x18000de55  add     eax, 800h
0x18000de5a  mov     esi, eax
0x18000de5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000de63  mov     ecx, eax; unsigned __int64
0x18000de65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000de6a  mov     r13, rax
0x18000de6d  test    rax, rax
0x18000de70  jz      short loc_18000DE7F
0x18000de72  mov     r8d, esi; Size
0x18000de75  xor     edx, edx; Val
0x18000de77  mov     rcx, rax; void *
0x18000de7a  call    memset_0
0x18000de7f  xor     ecx, ecx
0x18000de81  jmp     short loc_18000DE8B
0x18000de83  mov     [rsp+148h+var_D8], rsi
0x18000de88  mov     r13, rsi
0x18000de8b  mov     [rsp+148h+var_68], r13
0x18000de93  test    r13, r13
0x18000de96  jz      loc_18000E566
0x18000de9c  cmp     ebx, 4
0x18000de9f  jnb     short loc_18000DEFD
0x18000dea1  mov     [rsp+148h+var_80], r13
0x18000dea9  lea     rcx, [r13+400h]
0x18000deb0  mov     [rsp+148h+var_D8], rcx
0x18000deb5  mov     esi, dword ptr [rsp+148h+Size]
0x18000deb9  add     rsi, rcx
0x18000debc  mov     [rsp+148h+var_88], rsi
0x18000dec4  lea     rax, [rsi+400h]
0x18000decb  mov     [rsp+148h+var_90], rax
0x18000ded3  mov     edx, 0A5h; Val
0x18000ded8  mov     r8d, 400h; Size
0x18000dede  mov     rcx, r13; void *
0x18000dee1  call    memset_0
0x18000dee6  mov     edx, 0A5h; Val
0x18000deeb  mov     r8d, 400h; Size
0x18000def1  mov     rcx, rsi; void *
0x18000def4  call    memset_0
0x18000def9  xor     ecx, ecx
0x18000defb  jmp     short loc_18000DF15
0x18000defd  mov     [rsp+148h+var_80], rcx
0x18000df05  mov     [rsp+148h+var_90], rcx
0x18000df0d  mov     [rsp+148h+var_88], rcx
0x18000df15  mov     rax, [rsp+148h+var_D8]
0x18000df1a  mov     [rsp+148h+Src], rax
0x18000df22  mov     [rsp+148h+var_78], rcx
0x18000df2a  mov     r12, rcx
0x18000df2d  mov     [rsp+148h+hMem], rcx
0x18000df35  mov     [rsp+148h+var_E0], ecx
0x18000df39  mov     [rsp+148h+var_A0], 0
0x18000df45  mov     [rsp+148h+var_A8], 0
0x18000df51  mov     rcx, rdi
0x18000df54  call    PerfpLockExtObject
0x18000df59  mov     esi, eax
0x18000df5b  mov     dword ptr [rsp+148h+arg_20], eax
0x18000df62  test    eax, eax
0x18000df64  jnz     short loc_18000DF71
0x18000df66  mov     eax, 1
0x18000df6b  mov     [rsp+148h+var_E0], eax
0x18000df6f  jmp     short loc_18000DFD9
0x18000df71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df78  test    byte ptr [rcx+1Ch], 2
0x18000df7c  jz      short loc_18000DFA0
0x18000df7e  cmp     byte ptr [rcx+19h], 2
0x18000df82  jb      short loc_18000DFA0
0x18000df84  mov     edx, 13h
0x18000df89  mov     r9, [rdi+188h]
0x18000df90  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000df97  mov     rcx, [rcx+10h]
0x18000df9b  call    WPP_SF_S
0x18000dfa0  lea     r8, [rdi+1E8h]; struct ERROR_LOG *
0x18000dfa7  mov     rdx, [rdi+68h]; HKEY
0x18000dfab  mov     ecx, 3F7h; unsigned int
0x18000dfb0  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18000dfb5  test    eax, eax
0x18000dfb7  jz      short loc_18000DFD9
0x18000dfb9  test    cs:Microsoft_Windows_PerflibEnableBits, 4
0x18000dfc0  jz      short loc_18000DFD9
0x18000dfc2  mov     r9, [rdi+60h]
0x18000dfc6  mov     r8, [rdi+188h]
0x18000dfcd  lea     rdx, PERFLIB_COLLECTION_HUNG
0x18000dfd4  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000dfd9  test    esi, esi
0x18000dfdb  jnz     loc_18000E315
0x18000dfe1  cmp     qword ptr [rdi+28h], 0
0x18000dfe6  jz      loc_18000E315
0x18000dfec  test    r15d, r15d
0x18000dfef  jz      loc_18000E0BF
0x18000dff5  xorps   xmm0, xmm0
0x18000dff8  xor     eax, eax
0x18000dffa  movups  xmmword ptr [rsp+148h+var_60], xmm0
0x18000e002  movups  [rsp+148h+var_50], xmm0
0x18000e00a  mov     [rsp+148h+var_40], rax
0x18000e012  mov     [rsp+148h+var_60], rax
0x18000e01a  mov     rax, [rdi+60h]
0x18000e01e  mov     [rsp+148h+var_60+8], rax
0x18000e026  mov     rax, [rdi+188h]
0x18000e02d  mov     qword ptr [rsp+148h+var_50], rax
0x18000e035  mov     eax, [rdi+38h]
0x18000e038  mov     dword ptr [rsp+148h+var_50+8], eax
0x18000e03f  mov     dword ptr [rsp+148h+var_50+0Ch], 3F7h
0x18000e04a  mov     [rsp+148h+var_40], rdi
0x18000e052  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e059  test    byte ptr [rcx+1Ch], 40h
0x18000e05d  jz      short loc_18000E07A
0x18000e05f  cmp     byte ptr [rcx+19h], 4
0x18000e063  jb      short loc_18000E07A
0x18000e065  mov     edx, 14h
0x18000e06a  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000e071  mov     rcx, [rcx+10h]
0x18000e075  call    WPP_SF_
0x18000e07a  lea     rcx, [rsp+148h+var_60]; struct OPEN_PROC_WAIT_INFO *
0x18000e082  call    ?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z; StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)
0x18000e087  mov     r12, rax
0x18000e08a  mov     [rsp+148h+hMem], rax
0x18000e092  test    rax, rax
0x18000e095  jnz     short loc_18000E0BF
0x18000e097  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e09e  test    byte ptr [rcx+1Ch], 40h
0x18000e0a2  jz      short loc_18000E0C6
0x18000e0a4  cmp     byte ptr [rcx+19h], 2
0x18000e0a8  jb      short loc_18000E0C6
0x18000e0aa  mov     edx, 15h
0x18000e0af  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000e0b6  mov     rcx, [rcx+10h]
0x18000e0ba  call    WPP_SF_
0x18000e0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0c6  mov     r15d, dword ptr [rsp+148h+Size]
0x18000e0cb  mov     rsi, [rsp+148h+arg_0]
0x18000e0d3  test    byte ptr [rcx+1Ch], 8
0x18000e0d7  jz      short loc_18000E101
0x18000e0d9  cmp     byte ptr [rcx+19h], 4
0x18000e0dd  jb      short loc_18000E101
0x18000e0df  mov     eax, dword ptr [rsp+148h+Size+4]
0x18000e0e3  mov     dword ptr [rsp+148h+var_118], eax
0x18000e0e7  mov     dword ptr [rsp+148h+var_120], r15d
0x18000e0ec  mov     [rsp+148h+var_128], rsi
0x18000e0f1  mov     r9, [rdi+188h]
0x18000e0f8  mov     rcx, [rcx+10h]
0x18000e0fc  call    WPP_SF_SSdd
0x18000e101  lea     rcx, [rsp+148h+var_A0]
0x18000e109  call    cs:__imp_RtlQueryPerformanceCounter
0x18000e110  nop     dword ptr [rax+rax+00h]
0x18000e115  lea     rax, [rsp+148h+Size+4]
0x18000e11a  mov     [rsp+148h+var_128], rax
0x18000e11f  lea     r9, [rsp+148h+Size]
0x18000e124  lea     r8, [rsp+148h+var_D8]
0x18000e129  mov     rdx, rsi
0x18000e12c  mov     rcx, rdi
0x18000e12f  call    CallExtObj
0x18000e134  mov     esi, eax
0x18000e136  mov     dword ptr [rsp+148h+arg_20], eax
0x18000e13d  lea     rcx, [rsp+148h+var_A8]
0x18000e145  call    cs:__imp_RtlQueryPerformanceCounter
0x18000e14c  nop     dword ptr [rax+rax+00h]
0x18000e151  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e158  test    byte ptr [rcx+1Ch], 8
0x18000e15c  jz      short loc_18000E187
0x18000e15e  cmp     byte ptr [rcx+19h], 4
0x18000e162  jb      short loc_18000E187
0x18000e164  mov     eax, dword ptr [rsp+148h+Size+4]
0x18000e168  mov     dword ptr [rsp+148h+var_120], eax
0x18000e16c  mov     eax, dword ptr [rsp+148h+Size]
0x18000e170  mov     dword ptr [rsp+148h+var_128], eax
0x18000e174  mov     r9d, esi
0x18000e177  mov     rcx, [rcx+10h]
0x18000e17b  call    WPP_SF_ddd
0x18000e180  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e187  test    r12, r12
0x18000e18a  jz      short loc_18000E1C1
0x18000e18c  test    byte ptr [rcx+1Ch], 40h
0x18000e190  jz      short loc_18000E1AD
0x18000e192  cmp     byte ptr [rcx+19h], 4
0x18000e196  jb      short loc_18000E1AD
0x18000e198  mov     edx, 18h
0x18000e19d  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000e1a4  mov     rcx, [rcx+10h]
0x18000e1a8  call    WPP_SF_
0x18000e1ad  mov     rcx, r12; hMem
0x18000e1b0  call    ?KillPerflibFunctionTimer@@YAKPEAX@Z; KillPerflibFunctionTimer(void *)
0x18000e1b5  mov     [rsp+148h+hMem], 0
0x18000e1c1  mov     eax, dword ptr [rsp+148h+Size]
0x18000e1c5  mov     [rdi+1D4h], eax
0x18000e1cb  cmp     eax, [rdi+1D8h]
0x18000e1d1  jbe     short loc_18000E1D9
0x18000e1d3  mov     [rdi+1D8h], eax
0x18000e1d9  cmp     esi, 0EAh
0x18000e1df  jnz     short loc_18000E1F1
  ... truncated ...
```
