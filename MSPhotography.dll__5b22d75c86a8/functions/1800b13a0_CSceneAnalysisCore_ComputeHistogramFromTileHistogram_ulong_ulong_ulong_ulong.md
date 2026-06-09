# CSceneAnalysisCore::ComputeHistogramFromTileHistogram(ulong *,ulong,ulong,ulong * *)

- ea: `0x1800b13a0`
- end: `0x1800b15c9`
- name: `?ComputeHistogramFromTileHistogram@CSceneAnalysisCore@@SAJPEAKKKPEAPEAK@Z`
- size: `553`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, unsigned int, unsigned int **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800aede0`

## callees

- `0x180003088`
- `0x1800035ac`
- `0x18002a9bc`
- `0x1800a75a0`
- `0x1800b13a0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b13d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b151b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b13d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b151b`

## string_xrefs

- `0x1800b1443`: `CSceneAnalysisCore::ComputeHistogramFromTileHistogram`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisCore::ComputeHistogramFromTileHistogram(
        unsigned int *a1,
        int a2,
        __int64 a3,
        unsigned int **a4)
{
  int v6; // eax
  __int64 *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v11; // r8d
  int v12; // eax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  unsigned int *v15; // rax
  int v16; // edx
  unsigned int *v17; // rdi
  int v18; // eax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  unsigned int i; // ecx
  __int64 j; // rdx

  if ( a1 )
  {
    if ( a4 )
    {
      v15 = (unsigned int *)operator new[](0x400u, (const struct std::nothrow_t *)&std::nothrow);
      *a4 = v15;
      v17 = v15;
      if ( v15 )
      {
        v8 = 0;
        memset_0(v15, 0, 0x400u);
        for ( i = 0; i < 9; ++i )
        {
          for ( j = 0; j != 256; ++j )
            v17[j] += a1[256 * i + j];
        }
      }
      else
      {
        v18 = Windows::Media::Report((Windows::Media *)0x8007000ELL, v16);
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        v8 = v18;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( v8 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          {
            v11 = 176;
            goto LABEL_11;
          }
        }
      }
    }
    else
    {
      v12 = Windows::Media::Report((Windows::Media *)0x80004003LL, a2);
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = v12;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( v8 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        {
          v11 = 170;
          goto LABEL_11;
        }
      }
    }
  }
  else
  {
    v6 = Windows::Media::Report((Windows::Media *)0x80004003LL, a2);
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = v6;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v8 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v8 )
      {
        v11 = 169;
LABEL_11:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSceneAnalysisCore::ComputeHistogramFromTileHistogram",
          v11,
          v8);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b13a0  mov     [rsp+arg_0], rbx
0x1800b13a5  mov     [rsp+arg_8], rsi
0x1800b13aa  push    rdi
0x1800b13ab  sub     rsp, 20h
0x1800b13af  mov     rbx, r9
0x1800b13b2  mov     rsi, rcx
0x1800b13b5  test    rcx, rcx
0x1800b13b8  jnz     loc_1800B1457
0x1800b13be  mov     ecx, 80004003h; this
0x1800b13c3  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b13c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b13cf  mov     ebx, eax
0x1800b13d1  test    rcx, rcx
0x1800b13d4  jnz     short loc_1800B1417
0x1800b13d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b13dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b13e3  mov     rcx, rax
0x1800b13e6  test    rax, rax
0x1800b13e9  jz      short loc_1800B1409
0x1800b13eb  mov     rdx, [rax]
0x1800b13ee  mov     rax, [rdx+8]
0x1800b13f2  mov     edx, 7F0h
0x1800b13f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b13fc  test    eax, eax
0x1800b13fe  jz      short loc_1800B1409
0x1800b1400  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1407  jmp     short loc_1800B1417
0x1800b1409  lea     rcx, qword_18015FF10; this
0x1800b1410  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1417  cmp     byte ptr [rcx+8], 0
0x1800b141b  jz      loc_1800B15B7
0x1800b1421  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1426  test    ebx, ebx
0x1800b1428  jns     loc_1800B15B7
0x1800b142e  cmp     [rax+7CCh], ebx
0x1800b1434  jz      loc_1800B15B7
0x1800b143a  mov     r8d, 0A9h; int
0x1800b1440  mov     r9d, ebx; int
0x1800b1443  lea     rdx, aCsceneanalysis_11; "CSceneAnalysisCore::ComputeHistogramFro"...
0x1800b144a  mov     rcx, rax; this
0x1800b144d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1452  jmp     loc_1800B15B7
0x1800b1457  test    rbx, rbx
0x1800b145a  jnz     loc_1800B14E7
0x1800b1460  mov     ecx, 80004003h; this
0x1800b1465  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b146a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1471  mov     ebx, eax
0x1800b1473  test    rcx, rcx
0x1800b1476  jnz     short loc_1800B14B9
0x1800b1478  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b147e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1485  mov     rcx, rax
0x1800b1488  test    rax, rax
0x1800b148b  jz      short loc_1800B14AB
0x1800b148d  mov     rax, [rax]
0x1800b1490  mov     edx, 7F0h
0x1800b1495  mov     rax, [rax+8]
0x1800b1499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b149e  test    eax, eax
0x1800b14a0  jz      short loc_1800B14AB
0x1800b14a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b14a9  jmp     short loc_1800B14B9
0x1800b14ab  lea     rcx, qword_18015FF10; this
0x1800b14b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b14b9  cmp     byte ptr [rcx+8], 0
0x1800b14bd  jz      loc_1800B15B7
0x1800b14c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b14c8  test    ebx, ebx
0x1800b14ca  jns     loc_1800B15B7
0x1800b14d0  cmp     [rax+7CCh], ebx
0x1800b14d6  jz      loc_1800B15B7
0x1800b14dc  mov     r8d, 0AAh
0x1800b14e2  jmp     loc_1800B1440
0x1800b14e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b14ee  mov     ecx, 400h; unsigned __int64
0x1800b14f3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b14f8  mov     [rbx], rax
0x1800b14fb  mov     rdi, rax
0x1800b14fe  test    rax, rax
0x1800b1501  jnz     short loc_1800B157E
0x1800b1503  mov     ecx, 8007000Eh; this
0x1800b1508  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b150d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1514  mov     ebx, eax
0x1800b1516  test    rcx, rcx
0x1800b1519  jnz     short loc_1800B155C
0x1800b151b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1521  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1528  mov     rcx, rax
0x1800b152b  test    rax, rax
0x1800b152e  jz      short loc_1800B154E
0x1800b1530  mov     rax, [rax]
0x1800b1533  mov     edx, 7F0h
0x1800b1538  mov     rax, [rax+8]
0x1800b153c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1541  test    eax, eax
0x1800b1543  jz      short loc_1800B154E
0x1800b1545  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b154c  jmp     short loc_1800B155C
0x1800b154e  lea     rcx, qword_18015FF10; this
0x1800b1555  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b155c  cmp     byte ptr [rcx+8], 0
0x1800b1560  jz      short loc_1800B15B7
0x1800b1562  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1567  test    ebx, ebx
0x1800b1569  jns     short loc_1800B15B7
0x1800b156b  cmp     [rax+7CCh], ebx
0x1800b1571  jz      short loc_1800B15B7
0x1800b1573  mov     r8d, 0B0h
0x1800b1579  jmp     loc_1800B1440
0x1800b157e  xor     edx, edx; Val
0x1800b1580  mov     r8d, 400h; Size
0x1800b1586  mov     rcx, rdi; void *
0x1800b1589  xor     ebx, ebx
0x1800b158b  call    memset_0
0x1800b1590  xor     ecx, ecx
0x1800b1592  mov     eax, ecx
0x1800b1594  shl     eax, 8
0x1800b1597  xor     edx, edx
0x1800b1599  lea     r8, [rsi+rax*4]
0x1800b159d  mov     eax, [r8+rdx*4]
0x1800b15a1  add     [rdi+rdx*4], eax
0x1800b15a4  inc     rdx
0x1800b15a7  cmp     rdx, 100h
0x1800b15ae  jnz     short loc_1800B159D
0x1800b15b0  inc     ecx
0x1800b15b2  cmp     ecx, 9
0x1800b15b5  jb      short loc_1800B1592
0x1800b15b7  mov     rsi, [rsp+28h+arg_8]
0x1800b15bc  mov     eax, ebx
0x1800b15be  mov     rbx, [rsp+28h+arg_0]
0x1800b15c3  add     rsp, 20h
0x1800b15c7  pop     rdi
0x1800b15c8  retn
```
