# CSceneAnalysisCore::ComputeHistogramLookup(uchar,uchar,uchar *)

- ea: `0x1800b15d0`
- end: `0x1800b16f0`
- name: `?ComputeHistogramLookup@CSceneAnalysisCore@@SAJEEPEAE@Z`
- size: `288`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800afb38`
- `0x1800b0550`

## callees

- `0x18002a9bc`
- `0x1800a75a0`
- `0x1800b15d0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b15fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b15fa`

## string_xrefs

- `0x1800b1661`: `CSceneAnalysisCore::ComputeHistogramLookup`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisCore::ComputeHistogramLookup(
        unsigned __int8 a1,
        unsigned __int8 a2,
        unsigned __int8 *a3)
{
  int v4; // eax
  __int64 *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // r8
  float v10; // xmm0_4

  if ( a3 )
  {
    if ( a2 > a1 )
    {
      v6 = 0;
      v9 = 0;
      do
      {
        v10 = fmaxf((float)((float)((float)(int)(v9 - a1) * 255.0) / (float)(unsigned __int8)(a2 - a1)) + 0.5, 0.0);
        if ( v10 >= 255.0 )
          v10 = FLOAT_255_0;
        a3[v9] = (int)v10;
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (int)v9 < 256 );
    }
    else
    {
      return (unsigned int)Windows::Media::Report((Windows::Media *)0x80070057LL, a2);
    }
  }
  else
  {
    v4 = Windows::Media::Report((Windows::Media *)0x80004003LL, a2);
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = v4;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( v6 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSceneAnalysisCore::ComputeHistogramLookup", 46, v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b15d0  push    rbx
0x1800b15d2  sub     rsp, 20h
0x1800b15d6  mov     r9, r8
0x1800b15d9  test    r8, r8
0x1800b15dc  jnz     loc_1800B1678
0x1800b15e2  mov     ecx, 80004003h; this
0x1800b15e7  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b15ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b15f3  mov     ebx, eax
0x1800b15f5  test    rcx, rcx
0x1800b15f8  jnz     short loc_1800B163B
0x1800b15fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1600  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1607  mov     rcx, rax
0x1800b160a  test    rax, rax
0x1800b160d  jz      short loc_1800B162D
0x1800b160f  mov     rdx, [rax]
0x1800b1612  mov     rax, [rdx+8]
0x1800b1616  mov     edx, 7F0h
0x1800b161b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1620  test    eax, eax
0x1800b1622  jz      short loc_1800B162D
0x1800b1624  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b162b  jmp     short loc_1800B163B
0x1800b162d  lea     rcx, qword_18015FF10; this
0x1800b1634  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b163b  cmp     byte ptr [rcx+8], 0
0x1800b163f  jz      loc_1800B16E8
0x1800b1645  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b164a  test    ebx, ebx
0x1800b164c  jns     loc_1800B16E8
0x1800b1652  cmp     [rax+7CCh], ebx
0x1800b1658  jz      loc_1800B16E8
0x1800b165e  mov     r9d, ebx; int
0x1800b1661  lea     rdx, aCsceneanalysis_15; "CSceneAnalysisCore::ComputeHistogramLoo"...
0x1800b1668  mov     r8d, 2Eh ; '.'; int
0x1800b166e  mov     rcx, rax; this
0x1800b1671  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1676  jmp     short loc_1800B16E8
0x1800b1678  cmp     dl, cl
0x1800b167a  ja      short loc_1800B168A
0x1800b167c  mov     ecx, 80070057h; this
0x1800b1681  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b1686  mov     ebx, eax
0x1800b1688  jmp     short loc_1800B16E8
0x1800b168a  movss   xmm1, cs:__real@437f0000
0x1800b1692  xor     ebx, ebx
0x1800b1694  xor     r8d, r8d
0x1800b1697  movzx   r10d, cl
0x1800b169b  sub     dl, cl
0x1800b169d  movzx   eax, dl
0x1800b16a0  movd    xmm2, eax
0x1800b16a4  cvtdq2ps xmm2, xmm2
0x1800b16a7  mov     eax, r8d
0x1800b16aa  sub     eax, r10d
0x1800b16ad  movd    xmm0, eax
0x1800b16b1  cvtdq2ps xmm0, xmm0
0x1800b16b4  mulss   xmm0, xmm1
0x1800b16b8  divss   xmm0, xmm2
0x1800b16bc  addss   xmm0, cs:__real@3f000000
0x1800b16c4  maxss   xmm0, cs:__real@00000000
0x1800b16cc  comiss  xmm1, xmm0
0x1800b16cf  ja      short loc_1800B16D4
0x1800b16d1  movaps  xmm0, xmm1
0x1800b16d4  cvttss2si ecx, xmm0
0x1800b16d8  mov     [r8+r9], cl
0x1800b16dc  inc     r8d
0x1800b16df  cmp     r8d, 100h
0x1800b16e6  jl      short loc_1800B16A7
0x1800b16e8  mov     eax, ebx
0x1800b16ea  add     rsp, 20h
0x1800b16ee  pop     rbx
0x1800b16ef  retn
```
