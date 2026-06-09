# CDesktopTree::CalcOcclusionAndCollectOverlayCandidates(void)

- ea: `0x180015460`
- end: `0x180015651`
- name: `?CalcOcclusionAndCollectOverlayCandidates@CDesktopTree@@QEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(CDesktopTree *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015210`

## callees

- `0x180015460`
- `0x180015658`
- `0x180042de0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800155a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800155a8`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800155b6`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800155b6`

## pseudocode

```c
__int64 __fastcall CDesktopTree::CalcOcclusionAndCollectOverlayCandidates(CDesktopTree *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  BOOL v10; // eax
  __int64 v12[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp+8h] BYREF

  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 514) - *((_QWORD *)this + 513)) >> 3) )
    *((_QWORD *)this + 514) += -8 * ((__int64)(*((_QWORD *)this + 514) - *((_QWORD *)this + 513)) >> 3);
  v2 = 0;
  if ( g_pComposition )
    v2 = *((_QWORD *)g_pComposition + 110);
  if ( *((_QWORD *)this + 15) == v2 )
  {
    v3 = 0;
    v4 = 0;
    if ( g_pComposition )
      v4 = *((_QWORD *)g_pComposition + 110);
    if ( *((_QWORD *)this + 333) != v4 )
    {
      v5 = *((_QWORD *)this + 505);
      v6 = (*((_QWORD *)this + 506) - v5) >> 3;
      v12[0] = v6;
      if ( v6 == -1 || (v12[1] = v5) == 0 && v6 )
      {
LABEL_22:
        ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
        __debugbreak();
      }
      if ( *((_BYTE *)this + 2436) )
      {
        if ( this == (CDesktopTree *)-2420LL )
          goto LABEL_22;
      }
      else if ( this == (CDesktopTree *)-132LL && MEMORY[0xFFFFFFFFFFFFFFFC] )
      {
        goto LABEL_22;
      }
      v7 = COcclusionContext::Compute((CDesktopTree *)((char *)this + 2648), this, (__int64)v12);
      v3 = v7;
      if ( v7 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x9Au, 0);
    }
    v8 = 0;
    CycleTime = 0;
    if ( ::CycleTime )
    {
      CurrentThread = GetCurrentThread();
      v10 = QueryThreadCycleTime(CurrentThread, &CycleTime);
      v8 = CycleTime;
      if ( v10 )
        qword_1803BADD8 += CycleTime - ::CycleTime;
    }
    ::CycleTime = v8;
  }
  else
  {
    v3 = -2003292412;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003292412, 0xA1u, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x180015460  push    rdi
0x180015462  sub     rsp, 50h
0x180015466  mov     rax, [rcx+1010h]
0x18001546d  mov     rdx, rcx; struct CVisualTree *
0x180015470  sub     rax, [rcx+1008h]
0x180015477  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180015481  sar     rax, 3
0x180015485  imul    rax, rcx
0x180015489  test    rax, rax
0x18001548c  jz      short loc_180015499
0x18001548e  imul    rax, -28h
0x180015492  add     [rdx+1010h], rax
0x180015499  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800154a0  xor     edi, edi
0x1800154a2  mov     ecx, edi
0x1800154a4  test    rax, rax
0x1800154a7  jz      short loc_1800154B0
0x1800154a9  mov     rcx, [rax+370h]
0x1800154b0  mov     [rsp+58h+arg_8], rbx
0x1800154b5  cmp     [rdx+78h], rcx
0x1800154b9  jnz     loc_1800155EA
0x1800154bf  mov     ebx, edi
0x1800154c1  mov     rcx, rdi
0x1800154c4  test    rax, rax
0x1800154c7  jz      short loc_1800154D0
0x1800154c9  mov     rcx, [rax+370h]
0x1800154d0  cmp     [rdx+0A68h], rcx
0x1800154d7  jz      loc_180015597
0x1800154dd  cmp     [rdx+984h], bl
0x1800154e3  jnz     short loc_1800154F6
0x1800154e5  movss   xmm3, dword ptr [rdx+0A20h]
0x1800154ed  comiss  xmm3, cs:__real@3f800000
0x1800154f4  ja      short loc_1800154F9
0x1800154f6  xorps   xmm3, xmm3
0x1800154f9  mov     rcx, [rdx+0FC8h]
0x180015500  mov     rax, [rdx+0FD0h]
0x180015507  sub     rax, rcx
0x18001550a  sar     rax, 3
0x18001550e  mov     [rsp+58h+var_18], rax
0x180015513  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015517  jz      loc_18001562E
0x18001551d  mov     [rsp+58h+var_10], rcx
0x180015522  test    rcx, rcx
0x180015525  jz      loc_180015646
0x18001552b  cmp     [rdx+984h], bl
0x180015531  jnz     loc_180015610
0x180015537  mov     ecx, [rdx+80h]
0x18001553d  lea     rax, [rdx+84h]
0x180015544  mov     [rsp+58h+var_28], rcx
0x180015549  mov     [rsp+58h+var_20], rax
0x18001554e  test    rax, rax
0x180015551  jz      loc_18001563B
0x180015557  lea     rax, [rsp+58h+var_18]
0x18001555c  lea     rcx, [rdx+0A58h]; this
0x180015563  mov     qword ptr [rsp+58h+var_38], rax; __int64
0x180015568  lea     r8, [rsp+58h+var_28]
0x18001556d  call    ?Compute@COcclusionContext@@IEAAJPEBVCVisualTree@@AEBV?$span@$$CBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0?0@gsl@@MAEBV?$span@PEAVCOverlayContext@@$0?0@4@@Z; COcclusionContext::Compute(CVisualTree const *,gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1> const &,float,gsl::span<COverlayContext *,-1> const &)
0x180015572  mov     ebx, eax
0x180015574  test    eax, eax
0x180015576  jns     short loc_180015597
0x180015578  mov     [rsp+58h+var_30], rdi; void *
0x18001557d  mov     r9d, eax; int
0x180015580  xor     r8d, r8d; unsigned int
0x180015583  mov     [rsp+58h+var_38], 9Ah; unsigned int
0x18001558b  xor     edx, edx; int *
0x18001558d  mov     ecx, 14h; unsigned int
0x180015592  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180015597  mov     rcx, rdi
0x18001559a  cmp     cs:CycleTime, rcx
0x1800155a1  mov     [rsp+58h+CycleTime], rcx
0x1800155a6  jz      short loc_1800155D6
0x1800155a8  call    cs:__imp_GetCurrentThread
0x1800155ae  mov     rcx, rax; ThreadHandle
0x1800155b1  lea     rdx, [rsp+58h+CycleTime]; CycleTime
0x1800155b6  call    cs:__imp_QueryThreadCycleTime
0x1800155bc  mov     rcx, [rsp+58h+CycleTime]
0x1800155c1  test    eax, eax
0x1800155c3  jz      short loc_1800155D6
0x1800155c5  mov     rax, rcx
0x1800155c8  sub     rax, cs:CycleTime
0x1800155cf  add     cs:qword_1803BADD8, rax
0x1800155d6  mov     cs:CycleTime, rcx
0x1800155dd  mov     eax, ebx
0x1800155df  mov     rbx, [rsp+58h+arg_8]
0x1800155e4  add     rsp, 50h
0x1800155e8  pop     rdi
0x1800155e9  retn
0x1800155ea  mov     ebx, 88982F04h
0x1800155ef  mov     [rsp+58h+var_30], rdi; void *
0x1800155f4  mov     r9d, ebx; int
0x1800155f7  mov     [rsp+58h+var_38], 0A1h; unsigned int
0x1800155ff  xor     r8d, r8d; unsigned int
0x180015602  xor     edx, edx; int *
0x180015604  mov     ecx, 14h; unsigned int
0x180015609  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001560e  jmp     short loc_1800155DD
0x180015610  lea     rax, [rdx+974h]
0x180015617  mov     [rsp+58h+var_28], 1
0x180015620  mov     [rsp+58h+var_20], rax
0x180015625  test    rax, rax
0x180015628  jnz     loc_180015557
0x18001562e  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x180015635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001563a  int     3; Trap to Debugger
0x18001563b  test    rcx, rcx
0x18001563e  jz      loc_180015557
0x180015644  jmp     short loc_18001562E
0x180015646  test    rax, rax
0x180015649  jz      loc_18001552B
0x18001564f  jmp     short loc_18001562E
```
