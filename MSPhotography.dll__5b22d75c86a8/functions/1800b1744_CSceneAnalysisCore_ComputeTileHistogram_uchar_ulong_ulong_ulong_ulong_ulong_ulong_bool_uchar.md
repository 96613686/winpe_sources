# CSceneAnalysisCore::ComputeTileHistogram(uchar *,ulong,ulong,ulong,ulong,ulong,ulong * *,bool,uchar *)

- ea: `0x1800b1744`
- end: `0x1800b1c16`
- name: `?ComputeTileHistogram@CSceneAnalysisCore@@SAJPEAEKKKKKPEAPEAK_N0@Z`
- size: `1234`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int **, bool, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800aede0`

## callees

- `0x180002930`
- `0x180003088`
- `0x1800035ac`
- `0x18002a9bc`
- `0x1800a75a0`
- `0x1800b1744`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1786`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b18f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1aa7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1b4b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1786`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b18f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1aa7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1b4b`

## string_xrefs

- `0x1800b17f3`: `CSceneAnalysisCore::ComputeTileHistogram`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisCore::ComputeTileHistogram(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int **a7,
        bool a8,
        unsigned __int8 *a9)
{
  __int64 v9; // r14
  int v12; // eax
  __int64 *v13; // rcx
  int v14; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v17; // r8d
  int v18; // eax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  unsigned int *v21; // rax
  int v22; // edx
  unsigned int *v23; // rbp
  int v24; // eax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  unsigned int v29; // r10d
  unsigned int v30; // esi
  int v31; // ecx
  unsigned int v32; // edx
  __int64 v33; // r13
  unsigned int v34; // r11d
  int v35; // ecx
  unsigned __int8 *v36; // r13
  unsigned int v37; // edi
  unsigned __int8 *v38; // r9
  unsigned int v39; // r15d
  __int64 v40; // rax
  __int64 v41; // r10
  int v42; // ecx
  int v43; // eax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  unsigned int *v46; // rax
  int v47; // edx
  unsigned int *v48; // rdi
  int v49; // eax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  char *v52; // r10
  unsigned int i; // r9d
  __int64 v54; // r8
  __int64 v55; // rax
  unsigned int *v56; // r11
  char *v57; // rcx
  __int64 v58; // rdx
  int v59; // eax
  unsigned int v61; // [rsp+70h] [rbp+8h]
  unsigned int v63; // [rsp+90h] [rbp+28h]
  unsigned int v64; // [rsp+98h] [rbp+30h]

  v9 = a4;
  if ( a1 )
  {
    if ( a7 )
    {
      if ( a2 > a4 )
        return (unsigned int)Windows::Media::Report((Windows::Media *)0x80070057LL, a2);
      v21 = (unsigned int *)operator new[](0x2400u, (const struct std::nothrow_t *)&std::nothrow);
      *a7 = v21;
      v23 = v21;
      if ( v21 )
      {
        memset_0(v21, 0, 0x2400u);
        v27 = 0;
        v28 = a3 / 3;
        v29 = a2 / 3;
        v64 = a2 / 3;
        v30 = a2 - 2 * (a2 / 3);
        v31 = v9 * (a3 / 3);
        v61 = v30;
        do
        {
          v32 = 0;
          v33 = v31 * v27;
          v34 = v28;
          v35 = 3 * v27;
          v36 = &a1[v33];
          if ( v27 == 2 )
            v34 = a3 - 2 * (a3 / 3);
          do
          {
            v37 = v29;
            v63 = (v35 + v32) << 8;
            v38 = &v36[v29 * v32];
            if ( v32 == 2 )
              v37 = v30;
            v39 = 0;
            if ( v34 )
            {
              v40 = v9;
              do
              {
                v41 = 0;
                if ( v37 )
                {
                  do
                  {
                    v42 = v38[v41];
                    v41 = (unsigned int)(v41 + 1);
                    ++v23[v63 + v42];
                  }
                  while ( (unsigned int)v41 < v37 );
                  v40 = v9;
                }
                v38 += v40;
                ++v39;
              }
              while ( v39 < v34 );
              v29 = v64;
              v35 = 3 * v27;
              v30 = v61;
            }
            ++v32;
          }
          while ( v32 < 3 );
          v28 = a3 / 3;
          ++v27;
          v31 = v9 * (a3 / 3);
        }
        while ( v27 < 3 );
        v14 = 0;
        if ( a8 )
        {
          if ( a9 )
          {
            v46 = (unsigned int *)operator new[](0x2400u, (const struct std::nothrow_t *)&std::nothrow);
            v48 = v46;
            if ( v46 )
            {
              memset_0(v46, 0, 0x2400u);
              v52 = (char *)*a7;
              for ( i = 0; i < 9; ++i )
              {
                v54 = 0;
                v55 = i << 8;
                v56 = &v48[v55];
                v57 = &v52[4 * v55];
                do
                {
                  v58 = a9[v54];
                  v59 = *(_DWORD *)&v57[4 * v54++];
                  v56[v58] += v59;
                }
                while ( v54 != 256 );
              }
              operator delete(v52);
              *a7 = v48;
            }
            else
            {
              v49 = Windows::Media::Report((Windows::Media *)0x8007000ELL, v47);
              v50 = (__int64 *)CallStackTracing::s_wpInstance;
              v14 = v49;
              if ( !CallStackTracing::s_wpInstance )
              {
                v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v51;
                if ( v51
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                {
                  v50 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v50 = &qword_18015FF10;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                }
              }
              if ( *((_BYTE *)v50 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
                {
                  v17 = 134;
                  goto LABEL_11;
                }
              }
            }
          }
          else
          {
            v43 = Windows::Media::Report((Windows::Media *)0x80004003LL, v32);
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
            v14 = v43;
            if ( !CallStackTracing::s_wpInstance )
            {
              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v45;
              if ( v45
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
              {
                v44 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &qword_18015FF10;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
              }
            }
            if ( *((_BYTE *)v44 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
              if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
              {
                v17 = 131;
                goto LABEL_11;
              }
            }
          }
        }
      }
      else
      {
        v24 = Windows::Media::Report((Windows::Media *)0x8007000ELL, v22);
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        v14 = v24;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
          {
            v17 = 92;
            goto LABEL_11;
          }
        }
      }
    }
    else
    {
      v18 = Windows::Media::Report((Windows::Media *)0x80004003LL, a2);
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      v14 = v18;
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
        if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
        {
          v17 = 78;
          goto LABEL_11;
        }
      }
    }
  }
  else
  {
    v12 = Windows::Media::Report((Windows::Media *)0x80004003LL, a2);
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = v12;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
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
      if ( v14 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v14 )
      {
        v17 = 77;
LABEL_11:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSceneAnalysisCore::ComputeTileHistogram", v17, v14);
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800b1744  mov     [rsp+arg_8], rbx
0x1800b1749  mov     [rsp+arg_10], r8d
0x1800b174e  push    rbp
0x1800b174f  push    rsi
0x1800b1750  push    rdi
0x1800b1751  push    r12
0x1800b1753  push    r13
0x1800b1755  push    r14
0x1800b1757  push    r15
0x1800b1759  sub     rsp, 30h
0x1800b175d  mov     r14d, r9d
0x1800b1760  mov     edi, edx
0x1800b1762  mov     r12, rcx
0x1800b1765  test    rcx, rcx
0x1800b1768  jnz     loc_1800B1807
0x1800b176e  mov     ecx, 80004003h; this
0x1800b1773  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b1778  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b177f  mov     ebx, eax
0x1800b1781  test    rcx, rcx
0x1800b1784  jnz     short loc_1800B17C7
0x1800b1786  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b178c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1793  mov     rcx, rax
0x1800b1796  test    rax, rax
0x1800b1799  jz      short loc_1800B17B9
0x1800b179b  mov     rdx, [rax]
0x1800b179e  mov     rax, [rdx+8]
0x1800b17a2  mov     edx, 7F0h
0x1800b17a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b17ac  test    eax, eax
0x1800b17ae  jz      short loc_1800B17B9
0x1800b17b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b17b7  jmp     short loc_1800B17C7
0x1800b17b9  lea     rcx, qword_18015FF10; this
0x1800b17c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b17c7  cmp     byte ptr [rcx+8], 0
0x1800b17cb  jz      loc_1800B1BFF
0x1800b17d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b17d6  test    ebx, ebx
0x1800b17d8  jns     loc_1800B1BFF
0x1800b17de  cmp     [rax+7CCh], ebx
0x1800b17e4  jz      loc_1800B1BFF
0x1800b17ea  mov     r8d, 4Dh ; 'M'; int
0x1800b17f0  mov     r9d, ebx; int
0x1800b17f3  lea     rdx, aCsceneanalysis_3; "CSceneAnalysisCore::ComputeTileHistogra"...
0x1800b17fa  mov     rcx, rax; this
0x1800b17fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1802  jmp     loc_1800B1BFF
0x1800b1807  mov     rsi, [rsp+68h+arg_30]
0x1800b180f  test    rsi, rsi
0x1800b1812  jnz     loc_1800B189F
0x1800b1818  mov     ecx, 80004003h; this
0x1800b181d  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b1822  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1829  mov     ebx, eax
0x1800b182b  test    rcx, rcx
0x1800b182e  jnz     short loc_1800B1871
0x1800b1830  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1836  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b183d  mov     rcx, rax
0x1800b1840  test    rax, rax
0x1800b1843  jz      short loc_1800B1863
0x1800b1845  mov     rax, [rax]
0x1800b1848  mov     edx, 7F0h
0x1800b184d  mov     rax, [rax+8]
0x1800b1851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1856  test    eax, eax
0x1800b1858  jz      short loc_1800B1863
0x1800b185a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1861  jmp     short loc_1800B1871
0x1800b1863  lea     rcx, qword_18015FF10; this
0x1800b186a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1871  cmp     byte ptr [rcx+8], 0
0x1800b1875  jz      loc_1800B1BFF
0x1800b187b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1880  test    ebx, ebx
0x1800b1882  jns     loc_1800B1BFF
0x1800b1888  cmp     [rax+7CCh], ebx
0x1800b188e  jz      loc_1800B1BFF
0x1800b1894  mov     r8d, 4Eh ; 'N'
0x1800b189a  jmp     loc_1800B17F0
0x1800b189f  cmp     edi, r14d
0x1800b18a2  jbe     short loc_1800B18B5
0x1800b18a4  mov     ecx, 80070057h; this
0x1800b18a9  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b18ae  mov     ebx, eax
0x1800b18b0  jmp     loc_1800B1BFF
0x1800b18b5  mov     r15d, 2400h
0x1800b18bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b18c2  mov     ecx, r15d; unsigned __int64
0x1800b18c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b18ca  mov     [rsi], rax
0x1800b18cd  mov     rbp, rax
0x1800b18d0  test    rax, rax
0x1800b18d3  jnz     loc_1800B1960
0x1800b18d9  mov     ecx, 8007000Eh; this
0x1800b18de  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b18e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b18ea  mov     ebx, eax
0x1800b18ec  test    rcx, rcx
0x1800b18ef  jnz     short loc_1800B1932
0x1800b18f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b18f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b18fe  mov     rcx, rax
0x1800b1901  test    rax, rax
0x1800b1904  jz      short loc_1800B1924
0x1800b1906  mov     rax, [rax]
0x1800b1909  mov     edx, 7F0h
0x1800b190e  mov     rax, [rax+8]
0x1800b1912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1917  test    eax, eax
0x1800b1919  jz      short loc_1800B1924
0x1800b191b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1922  jmp     short loc_1800B1932
0x1800b1924  lea     rcx, qword_18015FF10; this
0x1800b192b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1932  cmp     byte ptr [rcx+8], 0
0x1800b1936  jz      loc_1800B1BFF
0x1800b193c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1941  test    ebx, ebx
0x1800b1943  jns     loc_1800B1BFF
0x1800b1949  cmp     [rax+7CCh], ebx
0x1800b194f  jz      loc_1800B1BFF
0x1800b1955  mov     r8d, 5Ch ; '\'
0x1800b195b  jmp     loc_1800B17F0
0x1800b1960  mov     r8, r15; Size
0x1800b1963  xor     edx, edx; Val
0x1800b1965  mov     rcx, rbp; void *
0x1800b1968  call    memset_0
0x1800b196d  mov     ebx, [rsp+68h+arg_10]
0x1800b1974  mov     r8d, 0AAAAAAABh
0x1800b197a  mov     eax, r8d
0x1800b197d  mul     ebx
0x1800b197f  mov     eax, r8d
0x1800b1982  xor     r8d, r8d
0x1800b1985  mov     r9d, edx
0x1800b1988  shr     r9d, 1
0x1800b198b  mul     edi
0x1800b198d  lea     ecx, [r9+r9]
0x1800b1991  mov     [rsp+68h+var_48], r9d
0x1800b1996  sub     ebx, ecx
0x1800b1998  mov     r10d, edx
0x1800b199b  shr     r10d, 1
0x1800b199e  mov     ecx, r9d
0x1800b19a1  mov     esi, r10d
0x1800b19a4  mov     [rsp+68h+arg_28], r10d
0x1800b19ac  lea     eax, [r10+r10*2]
0x1800b19b0  sub     esi, eax
0x1800b19b2  add     esi, edi
0x1800b19b4  imul    ecx, r14d
0x1800b19b8  mov     [rsp+68h+arg_0], esi
0x1800b19bc  mov     [rsp+68h+var_44], ecx
0x1800b19c0  mov     r13d, r8d
0x1800b19c3  xor     edx, edx
0x1800b19c5  imul    r13d, ecx
0x1800b19c9  mov     r11d, r9d
0x1800b19cc  lea     ecx, [r8+r8*2]
0x1800b19d0  add     r13, r12
0x1800b19d3  cmp     r8d, 2
0x1800b19d7  cmovz   r11d, ebx
0x1800b19db  mov     r9d, edx
0x1800b19de  lea     eax, [rcx+rdx]
0x1800b19e1  imul    r9d, r10d
0x1800b19e5  mov     edi, r10d
0x1800b19e8  shl     eax, 8
0x1800b19eb  mov     [rsp+68h+arg_20], eax
0x1800b19f2  add     r9, r13
0x1800b19f5  cmp     edx, 2
0x1800b19f8  cmovz   edi, esi
0x1800b19fb  xor     r15d, r15d
0x1800b19fe  test    r11d, r11d
0x1800b1a01  jz      short loc_1800B1A45
0x1800b1a03  mov     esi, [rsp+68h+arg_20]
0x1800b1a0a  mov     rax, r14
0x1800b1a0d  xor     r10d, r10d
0x1800b1a10  test    edi, edi
0x1800b1a12  jz      short loc_1800B1A2A
0x1800b1a14  movzx   ecx, byte ptr [r10+r9]
0x1800b1a19  inc     r10d
0x1800b1a1c  add     ecx, esi
0x1800b1a1e  inc     dword ptr [rbp+rcx*4+0]
0x1800b1a22  cmp     r10d, edi
0x1800b1a25  jb      short loc_1800B1A14
0x1800b1a27  mov     rax, r14
0x1800b1a2a  add     r9, rax
0x1800b1a2d  inc     r15d
0x1800b1a30  cmp     r15d, r11d
0x1800b1a33  jb      short loc_1800B1A0D
0x1800b1a35  mov     r10d, [rsp+68h+arg_28]
0x1800b1a3d  lea     ecx, [r8+r8*2]
0x1800b1a41  mov     esi, [rsp+68h+arg_0]
0x1800b1a45  inc     edx; int
0x1800b1a47  cmp     edx, 3
0x1800b1a4a  jb      short loc_1800B19DB
0x1800b1a4c  mov     r9d, [rsp+68h+var_48]
0x1800b1a51  inc     r8d
0x1800b1a54  mov     ecx, [rsp+68h+var_44]
0x1800b1a58  cmp     r8d, 3
0x1800b1a5c  jb      loc_1800B19C0
0x1800b1a62  mov     rsi, [rsp+68h+arg_30]
0x1800b1a6a  xor     r14d, r14d
0x1800b1a6d  mov     ebx, r14d
0x1800b1a70  cmp     [rsp+68h+arg_38], r14b
0x1800b1a78  jz      loc_1800B1BFF
0x1800b1a7e  mov     rbp, [rsp+68h+arg_40]
0x1800b1a86  test    rbp, rbp
0x1800b1a89  jnz     loc_1800B1B16
0x1800b1a8f  mov     ecx, 80004003h; this
0x1800b1a94  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b1a99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1aa0  mov     ebx, eax
0x1800b1aa2  test    rcx, rcx
0x1800b1aa5  jnz     short loc_1800B1AE8
0x1800b1aa7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1aad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1ab4  mov     rcx, rax
0x1800b1ab7  test    rax, rax
0x1800b1aba  jz      short loc_1800B1ADA
0x1800b1abc  mov     rax, [rax]
0x1800b1abf  mov     edx, 7F0h
0x1800b1ac4  mov     rax, [rax+8]
0x1800b1ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1acd  test    eax, eax
0x1800b1acf  jz      short loc_1800B1ADA
0x1800b1ad1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1ad8  jmp     short loc_1800B1AE8
0x1800b1ada  lea     rcx, qword_18015FF10; this
0x1800b1ae1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1ae8  cmp     [rcx+8], r14b
0x1800b1aec  jz      loc_1800B1BFF
0x1800b1af2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1af7  test    ebx, ebx
0x1800b1af9  jns     loc_1800B1BFF
0x1800b1aff  cmp     [rax+7CCh], ebx
0x1800b1b05  jz      loc_1800B1BFF
0x1800b1b0b  mov     r8d, 83h
0x1800b1b11  jmp     loc_1800B17F0
0x1800b1b16  mov     r15d, 2400h
0x1800b1b1c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b1b23  mov     ecx, r15d; unsigned __int64
0x1800b1b26  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b1b2b  mov     rdi, rax
0x1800b1b2e  test    rax, rax
0x1800b1b31  jnz     short loc_1800B1BAE
0x1800b1b33  mov     ecx, 8007000Eh; this
0x1800b1b38  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b1b3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b44  mov     ebx, eax
0x1800b1b46  test    rcx, rcx
0x1800b1b49  jnz     short loc_1800B1B8C
0x1800b1b4b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1b51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b58  mov     rcx, rax
0x1800b1b5b  test    rax, rax
0x1800b1b5e  jz      short loc_1800B1B7E
0x1800b1b60  mov     rax, [rax]
0x1800b1b63  mov     edx, 7F0h
0x1800b1b68  mov     rax, [rax+8]
0x1800b1b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b71  test    eax, eax
0x1800b1b73  jz      short loc_1800B1B7E
0x1800b1b75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b7c  jmp     short loc_1800B1B8C
0x1800b1b7e  lea     rcx, qword_18015FF10; this
0x1800b1b85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1b8c  cmp     [rcx+8], r14b
0x1800b1b90  jz      short loc_1800B1BFF
0x1800b1b92  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1b97  test    ebx, ebx
0x1800b1b99  jns     short loc_1800B1BFF
0x1800b1b9b  cmp     [rax+7CCh], ebx
0x1800b1ba1  jz      short loc_1800B1BFF
0x1800b1ba3  mov     r8d, 86h
0x1800b1ba9  jmp     loc_1800B17F0
0x1800b1bae  mov     r8, r15; Size
0x1800b1bb1  xor     edx, edx; Val
0x1800b1bb3  mov     rcx, rdi; void *
0x1800b1bb6  call    memset_0
0x1800b1bbb  mov     r10, [rsi]
0x1800b1bbe  mov     r9d, r14d
0x1800b1bc1  mov     eax, r9d
0x1800b1bc4  mov     r8, r14
0x1800b1bc7  shl     eax, 8
0x1800b1bca  lea     r11, [rdi+rax*4]
0x1800b1bce  lea     rcx, [r10+rax*4]
0x1800b1bd2  movzx   edx, byte ptr [r8+rbp]
0x1800b1bd7  mov     eax, [rcx+r8*4]
0x1800b1bdb  inc     r8
0x1800b1bde  add     [r11+rdx*4], eax
0x1800b1be2  cmp     r8, 100h
0x1800b1be9  jnz     short loc_1800B1BD2
0x1800b1beb  inc     r9d
0x1800b1bee  cmp     r9d, 9
0x1800b1bf2  jb      short loc_1800B1BC1
0x1800b1bf4  mov     rcx, r10; Block
0x1800b1bf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b1bfc  mov     [rsi], rdi
0x1800b1bff  mov     eax, ebx
0x1800b1c01  mov     rbx, [rsp+68h+arg_8]
  ... truncated ...
```
