# QueryV1Provider

- ea: `0x180014e50`
- end: `0x180015854`
- name: `QueryV1Provider`
- size: `2564`
- prototype: `__int64(__int64, __int64, unsigned int, char *, ...)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014430`

## callees

- `0x180014e50`
- `0x18001585c`
- `0x1800158ac`
- `0x180015c38`
- `0x180027178`
- `0x180027230`
- `0x180028330`
- `0x18002ccac`
- `0x1800336d0`
- `0x1800351f0`
- `0x1800354a8`
- `0x180038fbc`
- `0x18003b2bc`
- `0x18003b57c`
- `0x18003b748`
- `0x18003d048`
- `0x180057a4c`
- `0x180057c58`
- `0x180057dfc`
- `0x180058678`
- `0x1800586b0`
- `0x180058794`
- `0x18005886c`
- `0x18005895c`
- `0x180058a4c`
- `0x180058b18`
- `0x180058ba8`
- `0x18006504e`
- `0x18006505a`

## import_xrefs

- `ntdll!RtlQueryPerformanceCounter` at `0x1800152cd`
- `ntdll!RtlQueryPerformanceCounter` at `0x180015303`
- `ntdll!RtlQueryPerformanceCounter` at `0x1800152cd`
- `ntdll!RtlQueryPerformanceCounter` at `0x180015303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014efb`
- `KERNEL32!LocalFree` at `0x1800156f8`
- `KERNEL32!LocalFree` at `0x1800156f8`
- `KERNEL32!ReleaseMutex` at `0x180014f96`
- `KERNEL32!ReleaseMutex` at `0x180014f96`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 QueryV1Provider(__int64 a1, __int64 a2, unsigned int a3, char *a4, ...)
{
  char *v4; // rsi
  int v7; // r14d
  int v8; // eax
  unsigned int v9; // esi
  int v10; // ebx
  unsigned int v11; // eax
  int v12; // r15d
  unsigned int v13; // ebx
  char *v14; // rax
  char *v15; // r13
  void *started; // r12
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  unsigned __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r8
  _QWORD *v24; // rcx
  unsigned int v25; // eax
  int v26; // r12d
  int v27; // ecx
  int v28; // r8d
  int v29; // eax
  void *v30; // r15
  int v31; // edx
  int v32; // ecx
  int v33; // ecx
  __int64 v34; // rcx
  size_t Size; // [rsp+60h] [rbp-E8h] BYREF
  int v37; // [rsp+68h] [rbp-E0h]
  void *v38; // [rsp+70h] [rbp-D8h] BYREF
  int v39; // [rsp+84h] [rbp-C4h]
  unsigned int v40; // [rsp+88h] [rbp-C0h]
  HLOCAL hMem; // [rsp+90h] [rbp-B8h]
  void *Src; // [rsp+98h] [rbp-B0h]
  __int64 v43; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-90h]
  __int64 v46; // [rsp+C0h] [rbp-88h]
  __int64 v47; // [rsp+C8h] [rbp-80h]
  __int64 v48; // [rsp+D0h] [rbp-78h]
  char *v49; // [rsp+E0h] [rbp-68h]
  unsigned __int64 v50[2]; // [rsp+E8h] [rbp-60h] BYREF
  __int128 v51; // [rsp+F8h] [rbp-50h]
  __int64 v52; // [rsp+108h] [rbp-40h]
  __int64 v55; // [rsp+170h] [rbp+28h] BYREF
  va_list va; // [rsp+170h] [rbp+28h]
  _DWORD *v57; // [rsp+178h] [rbp+30h]
  _DWORD *v58; // [rsp+180h] [rbp+38h]
  va_list va1; // [rsp+188h] [rbp+40h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v55 = va_arg(va1, _QWORD);
  v57 = va_arg(va1, _DWORD *);
  v58 = va_arg(va1, _DWORD *);
  v4 = a4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, a3);
  v7 = 0;
  v39 = 0;
  Size = (unsigned int)v55;
  if ( !*(_QWORD *)(a2 + 88) || a3 <= 0xA && (v8 = 1554, _bittest(&v8, a3)) )
  {
    v9 = PerfpLockExtObject(a2);
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
        v11 = OpenExtObjectLibrary((struct EXT_OBJECT *)a2);
        v9 = v11;
        if ( v11 )
        {
          if ( v11 != 1058
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *(_QWORD *)(a2 + 392),
              v11);
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
  v12 = 0;
  if ( (lPerflibConfigFlags & 4) != 0 )
  {
    v13 = 4;
  }
  else
  {
    v13 = 1;
    if ( (*(_DWORD *)(a2 + 380) & 0x20) != 0 )
      v13 = lExtCounterTestLevel;
    LOBYTE(v12) = (*(_DWORD *)(a2 + 380) & 0x20) == 0;
  }
  v40 = v13;
  v38 = 0;
  if ( v13 >= 4 )
  {
    v38 = v4;
    v15 = v4;
  }
  else
  {
    v14 = (char *)operator new((unsigned int)(Size + 2048), (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    if ( v14 )
      memset_0(v14, 0, (unsigned int)(Size + 2048));
  }
  v49 = v15;
  if ( v15 )
  {
    if ( v13 >= 4 )
    {
      v47 = 0;
      v45 = 0;
      v46 = 0;
    }
    else
    {
      v47 = (__int64)v15;
      v38 = v15 + 1024;
      v46 = (__int64)&v15[(unsigned int)Size + 1024];
      v45 = v46 + 1024;
      memset_0(v15, 165, 0x400u);
      memset_0((void *)v46, 165, 0x400u);
    }
    Src = v38;
    v48 = 0;
    started = 0;
    hMem = 0;
    v37 = 0;
    v44 = 0;
    v43 = 0;
    v9 = PerfpLockExtObject(a2);
    LODWORD(v55) = v9;
    if ( v9 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
      if ( PerfpThrottleError(0x3F7u, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
        && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
      {
        McTemplateU0zz_EtwEventWriteTransfer(v19, PERFLIB_COLLECTION_HUNG, *(_QWORD *)(a2 + 392), *(_QWORD *)(a2 + 96));
      }
    }
    else
    {
      v37 = 1;
    }
    if ( v9 || !*(_QWORD *)(a2 + 40) )
    {
      v29 = 0;
      Size = 0;
      v26 = v37;
      goto LABEL_89;
    }
    if ( v12 )
    {
      v50[1] = 0;
      v51 = 0;
      v52 = 0;
      v50[0] = 0;
      v50[1] = *(_QWORD *)(a2 + 96);
      *(_QWORD *)&v51 = *(_QWORD *)(a2 + 392);
      DWORD2(v51) = *(_DWORD *)(a2 + 56);
      HIDWORD(v51) = 1015;
      v52 = a2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      started = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)v50);
      hMem = started;
      if ( !started )
      {
        v20 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_58;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      }
    }
    v20 = WPP_GLOBAL_Control;
LABEL_58:
    v21 = (unsigned int)Size;
    if ( (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 4u )
      WPP_SF_SSdd(v20[2], v17, v18, *(_QWORD *)(a2 + 392), a1, Size, SBYTE4(Size));
    RtlQueryPerformanceCounter(&v44);
    v9 = CallExtObj(a2, a1, (unsigned int)&v38, (unsigned int)&Size, (__int64)&Size + 4);
    LODWORD(v55) = v9;
    RtlQueryPerformanceCounter(&v43);
    v24 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, v9, Size, HIDWORD(Size));
      v24 = WPP_GLOBAL_Control;
    }
    if ( started )
    {
      if ( (*((_BYTE *)v24 + 28) & 0x40) != 0 && *((_BYTE *)v24 + 25) >= 4u )
        WPP_SF_(v24[2], 24, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      KillPerflibFunctionTimer(started);
      hMem = 0;
    }
    v25 = Size;
    *(_DWORD *)(a2 + 468) = Size;
    if ( v25 > *(_DWORD *)(a2 + 472) )
      *(_DWORD *)(a2 + 472) = v25;
    if ( v9 == 234 && (unsigned int)v21 > *(_DWORD *)(a2 + 476) )
      *(_DWORD *)(a2 + 476) = v21;
    v48 = (__int64)v38;
    *(_QWORD *)(a2 + 400) = GetTimeAsLongLong();
    PerfpUnlockExtObject(a2);
    v26 = 0;
    v37 = 0;
    if ( (unsigned int)Size <= (unsigned int)v21 )
    {
      v30 = Src;
      if ( (unsigned __int8)ValidateObjectTypeCount((struct EXT_OBJECT *)a2, HIDWORD(Size), Size) )
      {
        v29 = Size;
      }
      else
      {
        v29 = 0;
        Size = 0;
      }
LABEL_90:
      if ( v9 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a2 + 464));
      }
      else if ( v29 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a2 + 448));
        *(_QWORD *)(a2 + 440) += v43 - v44;
        v7 = Size;
        if ( (Size & 7) != 0 && (lPerflibConfigFlags & 1) == 0 && (*(_BYTE *)(a2 + 380) & 8) == 0 )
        {
          if ( PerfpThrottleError(0x3F8u, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
          {
            McTemplateU0zzpq_EtwEventWriteTransfer(
              v32,
              v31,
              *(_QWORD *)(a2 + 96),
              *(_QWORD *)(a2 + 392),
              (char)v38,
              Size);
          }
          *(_DWORD *)(a2 + 380) |= 8u;
          v7 = Size;
        }
        if ( v13 < 4 )
        {
          if ( (unsigned int)ValidateSafeBuffer(
                               (struct EXT_OBJECT *)a2,
                               HIDWORD(Size),
                               (__int64)v30,
                               v48,
                               v47,
                               v46,
                               v45,
                               v13,
                               (__int64)va) )
          {
            v7 = Size;
            memmove_0(a4, v30, (unsigned int)Size);
            v9 = v55;
            v39 = v7;
            goto LABEL_109;
          }
          v7 = 0;
          Size = 0;
          v9 = v55;
        }
        v39 = v7;
LABEL_109:
        if ( v13 < 4 )
          LocalFree(v15);
        if ( !v9 || v9 == 234 || v9 == 258 )
          goto LABEL_122;
        goto LABEL_116;
      }
      if ( v26 )
      {
        PerfpUnlockExtObject(a2);
        v37 = 0;
      }
      HIDWORD(Size) = 0;
      goto LABEL_109;
    }
    if ( PerfpThrottleError(0x3FCu, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
      && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
    {
      McTemplateU0zzqq_EtwEventWriteTransfer(
        v27,
        (unsigned int)PERFLIB_INVALID_SIZE_RETURNED,
        *(_QWORD *)(a2 + 96),
        *(_QWORD *)(a2 + 392),
        v21,
        Size);
    }
    if ( (lPerflibConfigFlags & 4) == 0 && (*(_BYTE *)(a2 + 380) & 0x20) == 0 )
      DisablePerfLibrary((struct EXT_OBJECT *)a2, 1u, 0x3FCu, v21, (unsigned int)Size);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v28, *(_QWORD *)(a2 + 392), Size, v21);
    v29 = 0;
    Size = 0;
LABEL_89:
    v30 = Src;
    goto LABEL_90;
  }
  v9 = 14;
LABEL_116:
  if ( PerfpThrottleError(0x3F6u, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
    && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
  {
    McTemplateU0zzq_EtwEventWriteTransfer(
      v33,
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
  v34 = *(_QWORD *)(a2 + 432);
  if ( v34 )
  {
    *(_QWORD *)(v34 + 64) = *(_QWORD *)(a2 + 440);
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
  *v57 = v7;
  *v58 = HIDWORD(Size);
  return v9;
}

```

## disassembly

```asm
0x180014e50  mov     [rsp+arg_18], r9
0x180014e55  mov     [rsp+arg_8], rdx
0x180014e5a  mov     [rsp+arg_0], rcx
0x180014e5f  push    rbx
0x180014e60  push    rsi
0x180014e61  push    rdi
0x180014e62  push    r12
0x180014e64  push    r13
0x180014e66  push    r14
0x180014e68  push    r15
0x180014e6a  sub     rsp, 110h
0x180014e71  mov     rsi, r9
0x180014e74  mov     ebx, r8d
0x180014e77  mov     rdi, rdx
0x180014e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e81  test    byte ptr [rcx+1Ch], 2
0x180014e85  jz      short loc_180014EA5
0x180014e87  cmp     byte ptr [rcx+19h], 4
0x180014e8b  jb      short loc_180014EA5
0x180014e8d  mov     edx, 10h
0x180014e92  mov     r9d, ebx
0x180014e95  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180014e9c  mov     rcx, [rcx+10h]
0x180014ea0  call    WPP_SF_d
0x180014ea5  xor     ecx, ecx
0x180014ea7  mov     dword ptr [rsp+148h+Size+4], ecx
0x180014eab  mov     r14d, ecx
0x180014eae  mov     [rsp+148h+var_C4], ecx
0x180014eb5  mov     eax, dword ptr [rsp+148h+arg_20]
0x180014ebc  mov     dword ptr [rsp+148h+Size], eax
0x180014ec0  cmp     [rdi+58h], rcx
0x180014ec4  jz      short loc_180014EDD
0x180014ec6  cmp     ebx, 0Ah
0x180014ec9  ja      loc_180014FD7
0x180014ecf  mov     eax, 612h
0x180014ed4  bt      eax, ebx
0x180014ed7  jnb     loc_180014FD7
0x180014edd  mov     rcx, rdi
0x180014ee0  call    PerfpLockExtObject
0x180014ee5  mov     esi, eax
0x180014ee7  test    eax, eax
0x180014ee9  jnz     loc_180014F9E
0x180014eef  cmp     [rdi+58h], r14
0x180014ef3  jnz     short loc_180014F63
0x180014ef5  mov     ebx, [rdi+208h]
0x180014efb  call    cs:__imp_GetCurrentThreadId
0x180014f01  cmp     eax, ebx
0x180014f03  jz      short loc_180014F56
0x180014f05  cmp     [rdi+1E4h], r14d
0x180014f0c  jnz     short loc_180014F56
0x180014f0e  mov     rcx, rdi; struct EXT_OBJECT *
0x180014f11  call    ?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z; OpenExtObjectLibrary(EXT_OBJECT *)
0x180014f16  mov     esi, eax
0x180014f18  test    eax, eax
0x180014f1a  jz      short loc_180014F63
0x180014f1c  cmp     eax, 422h
0x180014f21  jz      short loc_180014F56
0x180014f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f2a  test    byte ptr [rcx+1Ch], 2
0x180014f2e  jz      short loc_180014F56
0x180014f30  cmp     byte ptr [rcx+19h], 2
0x180014f34  jb      short loc_180014F56
0x180014f36  mov     edx, 11h
0x180014f3b  mov     dword ptr [rsp+148h+var_128], eax
0x180014f3f  mov     r9, [rdi+188h]
0x180014f46  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180014f4d  mov     rcx, [rcx+10h]
0x180014f51  call    WPP_SF_Sd
0x180014f56  mov     rcx, rdi
0x180014f59  call    PerfpUnlockExtObject
0x180014f5e  jmp     loc_180015826
0x180014f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f6a  test    byte ptr [rcx+1Ch], 20h
0x180014f6e  jz      short loc_180014F92
0x180014f70  cmp     byte ptr [rcx+19h], 4
0x180014f74  jb      short loc_180014F92
0x180014f76  mov     edx, 0Bh
0x180014f7b  mov     r9, [rdi+188h]
0x180014f82  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180014f89  mov     rcx, [rcx+10h]
0x180014f8d  call    WPP_SF_S
0x180014f92  mov     rcx, [rdi+8]; hMutex
0x180014f96  call    cs:__imp_ReleaseMutex
0x180014f9c  jmp     short loc_180014FCD
0x180014f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa5  test    byte ptr [rcx+1Ch], 20h
0x180014fa9  jz      short loc_180014FCD
0x180014fab  cmp     byte ptr [rcx+19h], 2
0x180014faf  jb      short loc_180014FCD
0x180014fb1  mov     edx, 12h
0x180014fb6  mov     r9, [rdi+188h]
0x180014fbd  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180014fc4  mov     rcx, [rcx+10h]
0x180014fc8  call    WPP_SF_S
0x180014fcd  xor     ecx, ecx
0x180014fcf  mov     rsi, [rsp+148h+arg_18]
0x180014fd7  mov     r15d, ecx
0x180014fda  test    byte ptr cs:?lPerflibConfigFlags@@3JA, 4; long lPerflibConfigFlags
0x180014fe1  jnz     short loc_180014FFF
0x180014fe3  mov     eax, [rdi+17Ch]
0x180014fe9  bt      eax, 5
0x180014fed  mov     ebx, 1
0x180014ff2  cmovb   ebx, cs:?lExtCounterTestLevel@@3JA; long lExtCounterTestLevel
0x180014ff9  setnb   r15b
0x180014ffd  jmp     short loc_180015004
0x180014fff  mov     ebx, 4
0x180015004  mov     [rsp+148h+var_C0], ebx
0x18001500b  mov     [rsp+148h+var_D8], rcx
0x180015010  cmp     ebx, 4
0x180015013  jnb     short loc_180015047
0x180015015  mov     eax, dword ptr [rsp+148h+Size]
0x180015019  add     eax, 800h
0x18001501e  mov     esi, eax
0x180015020  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015027  mov     ecx, eax; unsigned __int64
0x180015029  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001502e  mov     r13, rax
0x180015031  test    rax, rax
0x180015034  jz      short loc_180015043
0x180015036  mov     r8d, esi; Size
0x180015039  xor     edx, edx; Val
0x18001503b  mov     rcx, rax; void *
0x18001503e  call    memset_0
0x180015043  xor     ecx, ecx
0x180015045  jmp     short loc_18001504F
0x180015047  mov     [rsp+148h+var_D8], rsi
0x18001504c  mov     r13, rsi
0x18001504f  mov     [rsp+148h+var_68], r13
0x180015057  test    r13, r13
0x18001505a  jz      loc_180015718
0x180015060  cmp     ebx, 4
0x180015063  jnb     short loc_1800150C1
0x180015065  mov     [rsp+148h+var_80], r13
0x18001506d  lea     rcx, [r13+400h]
0x180015074  mov     [rsp+148h+var_D8], rcx
0x180015079  mov     esi, dword ptr [rsp+148h+Size]
0x18001507d  add     rsi, rcx
0x180015080  mov     [rsp+148h+var_88], rsi
0x180015088  lea     rax, [rsi+400h]
0x18001508f  mov     [rsp+148h+var_90], rax
0x180015097  mov     edx, 0A5h; Val
0x18001509c  mov     r8d, 400h; Size
0x1800150a2  mov     rcx, r13; void *
0x1800150a5  call    memset_0
0x1800150aa  mov     edx, 0A5h; Val
0x1800150af  mov     r8d, 400h; Size
0x1800150b5  mov     rcx, rsi; void *
0x1800150b8  call    memset_0
0x1800150bd  xor     ecx, ecx
0x1800150bf  jmp     short loc_1800150D9
0x1800150c1  mov     [rsp+148h+var_80], rcx
0x1800150c9  mov     [rsp+148h+var_90], rcx
0x1800150d1  mov     [rsp+148h+var_88], rcx
0x1800150d9  mov     rax, [rsp+148h+var_D8]
0x1800150de  mov     [rsp+148h+Src], rax
0x1800150e6  mov     [rsp+148h+var_78], rcx
0x1800150ee  mov     r12, rcx
0x1800150f1  mov     [rsp+148h+hMem], rcx
0x1800150f9  mov     [rsp+148h+var_E0], ecx
0x1800150fd  mov     [rsp+148h+var_A0], 0
0x180015109  mov     [rsp+148h+var_A8], 0
0x180015115  mov     rcx, rdi
0x180015118  call    PerfpLockExtObject
0x18001511d  mov     esi, eax
0x18001511f  mov     dword ptr [rsp+148h+arg_20], eax
0x180015126  test    eax, eax
0x180015128  jnz     short loc_180015135
0x18001512a  mov     eax, 1
0x18001512f  mov     [rsp+148h+var_E0], eax
0x180015133  jmp     short loc_18001519D
0x180015135  mov     rcx, cs:WPP_GLOBAL_Control
0x18001513c  test    byte ptr [rcx+1Ch], 2
0x180015140  jz      short loc_180015164
0x180015142  cmp     byte ptr [rcx+19h], 2
0x180015146  jb      short loc_180015164
0x180015148  mov     edx, 13h
0x18001514d  mov     r9, [rdi+188h]
0x180015154  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18001515b  mov     rcx, [rcx+10h]
0x18001515f  call    WPP_SF_S
0x180015164  lea     r8, [rdi+1E8h]; struct ERROR_LOG *
0x18001516b  mov     rdx, [rdi+68h]; HKEY
0x18001516f  mov     ecx, 3F7h; unsigned int
0x180015174  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180015179  test    eax, eax
0x18001517b  jz      short loc_18001519D
0x18001517d  test    cs:Microsoft_Windows_PerflibEnableBits, 4
0x180015184  jz      short loc_18001519D
0x180015186  mov     r9, [rdi+60h]
0x18001518a  mov     r8, [rdi+188h]
0x180015191  lea     rdx, PERFLIB_COLLECTION_HUNG
0x180015198  call    McTemplateU0zz_EtwEventWriteTransfer
0x18001519d  test    esi, esi
0x18001519f  jnz     loc_1800154CD
0x1800151a5  cmp     qword ptr [rdi+28h], 0
0x1800151aa  jz      loc_1800154CD
0x1800151b0  test    r15d, r15d
0x1800151b3  jz      loc_180015283
0x1800151b9  xorps   xmm0, xmm0
0x1800151bc  xor     eax, eax
0x1800151be  movups  xmmword ptr [rsp+148h+var_60], xmm0
0x1800151c6  movups  [rsp+148h+var_50], xmm0
0x1800151ce  mov     [rsp+148h+var_40], rax
0x1800151d6  mov     [rsp+148h+var_60], rax
0x1800151de  mov     rax, [rdi+60h]
0x1800151e2  mov     [rsp+148h+var_60+8], rax
0x1800151ea  mov     rax, [rdi+188h]
0x1800151f1  mov     qword ptr [rsp+148h+var_50], rax
0x1800151f9  mov     eax, [rdi+38h]
0x1800151fc  mov     dword ptr [rsp+148h+var_50+8], eax
0x180015203  mov     dword ptr [rsp+148h+var_50+0Ch], 3F7h
0x18001520e  mov     [rsp+148h+var_40], rdi
0x180015216  mov     rcx, cs:WPP_GLOBAL_Control
0x18001521d  test    byte ptr [rcx+1Ch], 40h
0x180015221  jz      short loc_18001523E
0x180015223  cmp     byte ptr [rcx+19h], 4
0x180015227  jb      short loc_18001523E
0x180015229  mov     edx, 14h
0x18001522e  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180015235  mov     rcx, [rcx+10h]
0x180015239  call    WPP_SF_
0x18001523e  lea     rcx, [rsp+148h+var_60]; struct OPEN_PROC_WAIT_INFO *
0x180015246  call    ?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z; StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)
0x18001524b  mov     r12, rax
0x18001524e  mov     [rsp+148h+hMem], rax
0x180015256  test    rax, rax
0x180015259  jnz     short loc_180015283
0x18001525b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015262  test    byte ptr [rcx+1Ch], 40h
0x180015266  jz      short loc_18001528A
0x180015268  cmp     byte ptr [rcx+19h], 2
0x18001526c  jb      short loc_18001528A
0x18001526e  mov     edx, 15h
0x180015273  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18001527a  mov     rcx, [rcx+10h]
0x18001527e  call    WPP_SF_
0x180015283  mov     rcx, cs:WPP_GLOBAL_Control
0x18001528a  mov     r15d, dword ptr [rsp+148h+Size]
0x18001528f  mov     rsi, [rsp+148h+arg_0]
0x180015297  test    byte ptr [rcx+1Ch], 8
0x18001529b  jz      short loc_1800152C5
0x18001529d  cmp     byte ptr [rcx+19h], 4
0x1800152a1  jb      short loc_1800152C5
0x1800152a3  mov     eax, dword ptr [rsp+148h+Size+4]
0x1800152a7  mov     dword ptr [rsp+148h+var_118], eax
0x1800152ab  mov     dword ptr [rsp+148h+var_120], r15d
0x1800152b0  mov     [rsp+148h+var_128], rsi
0x1800152b5  mov     r9, [rdi+188h]
0x1800152bc  mov     rcx, [rcx+10h]
0x1800152c0  call    WPP_SF_SSdd
0x1800152c5  lea     rcx, [rsp+148h+var_A0]
0x1800152cd  call    cs:__imp_RtlQueryPerformanceCounter
0x1800152d3  lea     rax, [rsp+148h+Size+4]
0x1800152d8  mov     [rsp+148h+var_128], rax
0x1800152dd  lea     r9, [rsp+148h+Size]
0x1800152e2  lea     r8, [rsp+148h+var_D8]
0x1800152e7  mov     rdx, rsi
0x1800152ea  mov     rcx, rdi
0x1800152ed  call    CallExtObj
0x1800152f2  mov     esi, eax
0x1800152f4  mov     dword ptr [rsp+148h+arg_20], eax
0x1800152fb  lea     rcx, [rsp+148h+var_A8]
0x180015303  call    cs:__imp_RtlQueryPerformanceCounter
0x180015309  mov     rcx, cs:WPP_GLOBAL_Control
0x180015310  test    byte ptr [rcx+1Ch], 8
0x180015314  jz      short loc_18001533F
0x180015316  cmp     byte ptr [rcx+19h], 4
0x18001531a  jb      short loc_18001533F
0x18001531c  mov     eax, dword ptr [rsp+148h+Size+4]
0x180015320  mov     dword ptr [rsp+148h+var_120], eax
0x180015324  mov     eax, dword ptr [rsp+148h+Size]
0x180015328  mov     dword ptr [rsp+148h+var_128], eax
0x18001532c  mov     r9d, esi
0x18001532f  mov     rcx, [rcx+10h]
0x180015333  call    WPP_SF_ddd
0x180015338  mov     rcx, cs:WPP_GLOBAL_Control
0x18001533f  test    r12, r12
0x180015342  jz      short loc_180015379
0x180015344  test    byte ptr [rcx+1Ch], 40h
0x180015348  jz      short loc_180015365
0x18001534a  cmp     byte ptr [rcx+19h], 4
0x18001534e  jb      short loc_180015365
0x180015350  mov     edx, 18h
0x180015355  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18001535c  mov     rcx, [rcx+10h]
0x180015360  call    WPP_SF_
0x180015365  mov     rcx, r12; hMem
0x180015368  call    ?KillPerflibFunctionTimer@@YAKPEAX@Z; KillPerflibFunctionTimer(void *)
0x18001536d  mov     [rsp+148h+hMem], 0
0x180015379  mov     eax, dword ptr [rsp+148h+Size]
0x18001537d  mov     [rdi+1D4h], eax
0x180015383  cmp     eax, [rdi+1D8h]
0x180015389  jbe     short loc_180015391
0x18001538b  mov     [rdi+1D8h], eax
0x180015391  cmp     esi, 0EAh
0x180015397  jnz     short loc_1800153A9
0x180015399  cmp     r15d, [rdi+1DCh]
0x1800153a0  jbe     short loc_1800153A9
0x1800153a2  mov     [rdi+1DCh], r15d
0x1800153a9  mov     rax, [rsp+148h+var_D8]
  ... truncated ...
```
