# CLegacyRenderTarget::CollectOverlayCandidates(void)

- ea: `0x180015250`
- end: `0x180015456`
- name: `?CollectOverlayCandidates@CLegacyRenderTarget@@UEBAPEAVCOverlayContext@@XZ`
- size: `518`
- prototype: `struct COverlayContext *__fastcall(CLegacyRenderTarget *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015250`
- `0x180015658`
- `0x180042de0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800153ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800153ae`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800153bc`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800153bc`

## pseudocode

```c
struct COverlayContext *__fastcall CLegacyRenderTarget::CollectOverlayCandidates(CLegacyRenderTarget *this)
{
  __int64 v2; // rdx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  unsigned __int64 v9; // rcx
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  __int64 v12[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 0;
  v2 = *((_QWORD *)this + 3);
  if ( !v2 )
    return 0;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 4112) - *(_QWORD *)(v2 + 4104)) >> 3) )
    *(_QWORD *)(v2 + 4112) += -8 * ((__int64)(*(_QWORD *)(v2 + 4112) - *(_QWORD *)(v2 + 4104)) >> 3);
  v4 = 0;
  if ( g_pComposition )
    v4 = *((_QWORD *)g_pComposition + 110);
  if ( *(_QWORD *)(v2 + 120) == v4 )
  {
    v5 = 0;
    if ( g_pComposition )
      v5 = *((_QWORD *)g_pComposition + 110);
    if ( *(_QWORD *)(v2 + 2664) != v5 )
    {
      v6 = *(_QWORD *)(v2 + 4040);
      v7 = (*(_QWORD *)(v2 + 4048) - v6) >> 3;
      v12[0] = v7;
      if ( v7 == -1 || (v12[1] = v6) == 0 && v7 )
      {
LABEL_25:
        ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
        __debugbreak();
      }
      if ( *(_BYTE *)(v2 + 2436) )
      {
        if ( v2 == -2420 )
          goto LABEL_25;
      }
      else if ( v2 == -132 && MEMORY[0xFFFFFFFFFFFFFFFC] )
      {
        goto LABEL_25;
      }
      v8 = COcclusionContext::Compute((COcclusionContext *)(v2 + 2648), (struct CVisualTree *)v2, (__int64)v12);
      if ( v8 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x9Au, 0);
    }
    v9 = 0;
    CycleTime = 0;
    if ( ::CycleTime )
    {
      CurrentThread = GetCurrentThread();
      v11 = QueryThreadCycleTime(CurrentThread, &CycleTime);
      v9 = CycleTime;
      if ( v11 )
        qword_1803BADD8 += CycleTime - ::CycleTime;
    }
    ::CycleTime = v9;
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003292412, 0xA1u, 0);
  }
  return (CLegacyRenderTarget *)((char *)this + 56);
}

```

## disassembly

```asm
0x180015250  push    rbx
0x180015252  sub     rsp, 50h
0x180015256  cmp     qword ptr [rcx+28h], 0
0x18001525b  mov     rbx, rcx
0x18001525e  jz      short loc_180015269
0x180015260  mov     rdx, [rcx+18h]; struct CVisualTree *
0x180015264  test    rdx, rdx
0x180015267  jnz     short loc_180015271
0x180015269  xor     eax, eax
0x18001526b  add     rsp, 50h
0x18001526f  pop     rbx
0x180015270  retn
0x180015271  mov     rax, [rdx+1010h]
0x180015278  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180015282  sub     rax, [rdx+1008h]
0x180015289  sar     rax, 3
0x18001528d  imul    rax, rcx
0x180015291  mov     [rsp+58h+arg_8], rdi
0x180015296  test    rax, rax
0x180015299  jz      short loc_1800152A6
0x18001529b  imul    rax, -28h
0x18001529f  add     [rdx+1010h], rax
0x1800152a6  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800152ad  xor     edi, edi
0x1800152af  mov     ecx, edi
0x1800152b1  test    rax, rax
0x1800152b4  jz      short loc_1800152BD
0x1800152b6  mov     rcx, [rax+370h]
0x1800152bd  cmp     [rdx+78h], rcx
0x1800152c1  jnz     loc_1800153F1
0x1800152c7  mov     rcx, rdi
0x1800152ca  test    rax, rax
0x1800152cd  jz      short loc_1800152D6
0x1800152cf  mov     rcx, [rax+370h]
0x1800152d6  cmp     [rdx+0A68h], rcx
0x1800152dd  jz      loc_18001539D
0x1800152e3  cmp     [rdx+984h], dil
0x1800152ea  jnz     short loc_1800152FD
0x1800152ec  movss   xmm3, dword ptr [rdx+0A20h]
0x1800152f4  comiss  xmm3, cs:__real@3f800000
0x1800152fb  ja      short loc_180015300
0x1800152fd  xorps   xmm3, xmm3
0x180015300  mov     rcx, [rdx+0FC8h]
0x180015307  mov     rax, [rdx+0FD0h]
0x18001530e  sub     rax, rcx
0x180015311  sar     rax, 3
0x180015315  mov     [rsp+58h+var_18], rax
0x18001531a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001531e  jz      loc_180015433
0x180015324  mov     [rsp+58h+var_10], rcx
0x180015329  test    rcx, rcx
0x18001532c  jz      loc_18001544B
0x180015332  cmp     [rdx+984h], dil
0x180015339  jnz     loc_180015415
0x18001533f  mov     ecx, [rdx+80h]
0x180015345  lea     rax, [rdx+84h]
0x18001534c  mov     [rsp+58h+var_28], rcx
0x180015351  mov     [rsp+58h+var_20], rax
0x180015356  test    rax, rax
0x180015359  jz      loc_180015440
0x18001535f  lea     rax, [rsp+58h+var_18]
0x180015364  lea     rcx, [rdx+0A58h]; this
0x18001536b  mov     qword ptr [rsp+58h+var_38], rax; __int64
0x180015370  lea     r8, [rsp+58h+var_28]
0x180015375  call    ?Compute@COcclusionContext@@IEAAJPEBVCVisualTree@@AEBV?$span@$$CBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0?0@gsl@@MAEBV?$span@PEAVCOverlayContext@@$0?0@4@@Z; COcclusionContext::Compute(CVisualTree const *,gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1> const &,float,gsl::span<COverlayContext *,-1> const &)
0x18001537a  test    eax, eax
0x18001537c  jns     short loc_18001539D
0x18001537e  mov     [rsp+58h+var_30], rdi; void *
0x180015383  mov     r9d, eax; int
0x180015386  xor     r8d, r8d; unsigned int
0x180015389  mov     [rsp+58h+var_38], 9Ah; unsigned int
0x180015391  xor     edx, edx; int *
0x180015393  mov     ecx, 14h; unsigned int
0x180015398  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001539d  mov     rcx, rdi
0x1800153a0  cmp     cs:CycleTime, rcx
0x1800153a7  mov     [rsp+58h+CycleTime], rcx
0x1800153ac  jz      short loc_1800153DC
0x1800153ae  call    cs:__imp_GetCurrentThread
0x1800153b4  mov     rcx, rax; ThreadHandle
0x1800153b7  lea     rdx, [rsp+58h+CycleTime]; CycleTime
0x1800153bc  call    cs:__imp_QueryThreadCycleTime
0x1800153c2  mov     rcx, [rsp+58h+CycleTime]
0x1800153c7  test    eax, eax
0x1800153c9  jz      short loc_1800153DC
0x1800153cb  mov     rax, rcx
0x1800153ce  sub     rax, cs:CycleTime
0x1800153d5  add     cs:qword_1803BADD8, rax
0x1800153dc  mov     cs:CycleTime, rcx
0x1800153e3  mov     rdi, [rsp+58h+arg_8]
0x1800153e8  lea     rax, [rbx+38h]
0x1800153ec  jmp     loc_18001526B
0x1800153f1  mov     [rsp+58h+var_30], rdi; void *
0x1800153f6  mov     r9d, 88982F04h; int
0x1800153fc  xor     r8d, r8d; unsigned int
0x1800153ff  mov     [rsp+58h+var_38], 0A1h; unsigned int
0x180015407  xor     edx, edx; int *
0x180015409  mov     ecx, 14h; unsigned int
0x18001540e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180015413  jmp     short loc_1800153E3
0x180015415  lea     rax, [rdx+974h]
0x18001541c  mov     [rsp+58h+var_28], 1
0x180015425  mov     [rsp+58h+var_20], rax
0x18001542a  test    rax, rax
0x18001542d  jnz     loc_18001535F
0x180015433  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x18001543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543f  int     3; Trap to Debugger
0x180015440  test    rcx, rcx
0x180015443  jz      loc_18001535F
0x180015449  jmp     short loc_180015433
0x18001544b  test    rax, rax
0x18001544e  jz      loc_180015332
0x180015454  jmp     short loc_180015433
```
