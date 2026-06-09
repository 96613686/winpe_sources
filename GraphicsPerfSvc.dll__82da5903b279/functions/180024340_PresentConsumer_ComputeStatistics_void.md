# PresentConsumer::ComputeStatistics(void)

- ea: `0x180024340`
- end: `0x18002493b`
- name: `?ComputeStatistics@PresentConsumer@@UEAA?AUPresentStatistics@@XZ`
- size: `1531`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000407c`
- `0x1800040e4`
- `0x1800047f0`
- `0x180004b41`
- `0x18000fbbc`
- `0x180024340`
- `0x180024d48`
- `0x1800253cc`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180024900`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180024900`

## pseudocode

```c
__int64 __fastcall PresentConsumer::ComputeStatistics(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // r8
  void *v6; // rsi
  int v7; // ecx
  int v8; // ebp
  _QWORD *v9; // rsi
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  float v12; // xmm1_4
  _QWORD *v13; // r8
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  _QWORD *v16; // r8
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  _QWORD *v20; // r8
  unsigned __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // eax
  int v25; // eax
  float v26; // xmm1_4
  int v27; // edx
  int v28; // r8d
  unsigned int v29; // eax
  unsigned __int64 v30; // rcx
  float v31; // xmm1_4
  float v32; // xmm0_4
  __int64 v33; // rcx
  float v34; // xmm0_4
  __int64 v35; // rax
  LARGE_INTEGER Frequency; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  memset_0((void *)(a2 + 16), 0, 0xA0u);
  *(_QWORD *)(a2 + 176) = 0;
  *(_QWORD *)(a2 + 184) = 0;
  memset_0((void *)(a2 + 192), 0, 0xA0u);
  *(_QWORD *)(a2 + 352) = 0;
  *(_QWORD *)(a2 + 360) = 0;
  memset_0((void *)(a2 + 368), 0, 0xA8u);
  *(_QWORD *)(a2 + 536) = 0;
  *(_QWORD *)(a2 + 544) = 0;
  memset_0((void *)(a2 + 552), 0, 0xA8u);
  v6 = (void *)(a2 + 720);
  *(_OWORD *)(a2 + 720) = 0;
  *(_OWORD *)(a2 + 736) = 0;
  *(_OWORD *)(a2 + 752) = 0;
  *(_DWORD *)(a2 + 768) = 0;
  *(_QWORD *)(a2 + 772) = 0;
  *(_QWORD *)(a2 + 780) = 0;
  *(_QWORD *)(a2 + 788) = 0;
  *(_QWORD *)(a2 + 796) = 0;
  *(_QWORD *)(a2 + 804) = 0;
  *(_QWORD *)(a2 + 812) = 0;
  *(_DWORD *)(a2 + 820) = 0;
  *(_QWORD *)(a2 + 864) = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)(a2 + 872) = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)(a2 + 824) = 0;
  *(_QWORD *)(a2 + 832) = 0;
  *(_QWORD *)(a2 + 840) = 0;
  *(_DWORD *)(a2 + 848) = 0;
  *(_DWORD *)(a2 + 852) = -1;
  *(_QWORD *)(a2 + 856) = 0;
  *(_QWORD *)(a2 + 880) = 0;
  *(_QWORD *)(a2 + 888) = 0;
  *(_QWORD *)(a2 + 896) = 0;
  *(_QWORD *)(a2 + 904) = 0;
  if ( *(_BYTE *)(a1 + 72) || (v7 = *(_DWORD *)(a1 + 528) + 1, *(_DWORD *)(a1 + 528) == -1) )
    v7 = 1;
  if ( *(_BYTE *)(a1 + 73) || (v8 = *(_DWORD *)(a1 + 624) + 1, *(_DWORD *)(a1 + 624) == -1) )
    v8 = 1;
  if ( v7 != 1 )
  {
    v9 = (_QWORD *)(a1 + 512);
    if ( *(_DWORD *)(a1 + 528) )
    {
      v10 = *v9 / (unsigned __int64)*(unsigned int *)(a1 + 528);
      v4 = *v9 % (unsigned __int64)*(unsigned int *)(a1 + 528);
    }
    else
    {
      v10 = 0;
    }
    *(_QWORD *)a2 = v10;
    *(_QWORD *)(a2 + 8) = gpm::statistics::averages<unsigned __int64>::variance(a1 + 512, v4);
    memmove_0((void *)(a2 + 16), *(const void **)(a1 + 568), 0xA0u);
    if ( *(_DWORD *)(a1 + 528) )
    {
      v4 = *v9 % (unsigned __int64)*(unsigned int *)(a1 + 528);
      v11 = *v9 / (unsigned __int64)*(unsigned int *)(a1 + 528);
    }
    else
    {
      v11 = 0;
    }
    if ( (v11 & 0x8000000000000000uLL) != 0LL )
      v12 = (float)(int)(v11 & 1 | (v11 >> 1)) + (float)(int)(v11 & 1 | (v11 >> 1));
    else
      v12 = (float)(int)v11;
    v6 = (void *)(a2 + 720);
    *(float *)(a2 + 772) = 100000.0 / v12;
  }
  if ( v8 != 1 )
  {
    v13 = (_QWORD *)(a1 + 608);
    if ( *(_DWORD *)(a1 + 624) )
    {
      v14 = *v13 / (unsigned __int64)*(unsigned int *)(a1 + 624);
      v4 = *v13 % (unsigned __int64)*(unsigned int *)(a1 + 624);
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)(a2 + 176) = v14;
    *(_QWORD *)(a2 + 184) = gpm::statistics::averages<unsigned __int64>::variance(a1 + 608, v4);
    memmove_0((void *)(a2 + 192), *(const void **)(a1 + 664), 0xA0u);
  }
  LOBYTE(v5) = 3;
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
    v4,
    v5);
  v16 = (_QWORD *)(a1 + 704);
  if ( *(_DWORD *)(a1 + 720) )
  {
    v17 = *v16 / (unsigned __int64)*(unsigned int *)(a1 + 720);
    v15 = *v16 % (unsigned __int64)*(unsigned int *)(a1 + 720);
  }
  else
  {
    v17 = 0;
  }
  *(_QWORD *)(a2 + 352) = v17;
  v18 = gpm::statistics::averages<unsigned __int64>::variance(a1 + 704, v15);
  v20 = (_QWORD *)(a1 + 784);
  *(_QWORD *)(a2 + 360) = v18;
  if ( *(_DWORD *)(a1 + 800) )
  {
    v21 = *v20 / (unsigned __int64)*(unsigned int *)(a1 + 800);
    v19 = *v20 % (unsigned __int64)*(unsigned int *)(a1 + 800);
  }
  else
  {
    v21 = 0;
  }
  *(_QWORD *)(a2 + 536) = v21;
  *(_QWORD *)(a2 + 544) = gpm::statistics::averages<unsigned __int64>::variance(a1 + 784, v19);
  memmove_0((void *)(a2 + 368), *(const void **)(a1 + 760), 0xA8u);
  memmove_0((void *)(a2 + 552), *(const void **)(a1 + 840), 0xA8u);
  if ( *(_BYTE *)(a1 + 72) )
    v24 = 0;
  else
    v24 = *(_DWORD *)(a1 + 528) + 1;
  *(_DWORD *)(a2 + 780) = v24;
  if ( *(_BYTE *)(a1 + 73) )
    v25 = 0;
  else
    v25 = *(_DWORD *)(a1 + 624) + 1;
  *(_DWORD *)(a2 + 776) = v25;
  *(_DWORD *)(a2 + 788) = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(a2 + 792) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a2 + 796) = *(_DWORD *)(a1 + 20);
  *(_DWORD *)(a2 + 800) = *(_DWORD *)(a1 + 24);
  *(_DWORD *)(a2 + 804) = *(_DWORD *)(a1 + 28);
  *(_DWORD *)(a2 + 808) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a2 + 812) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(a2 + 816) = *(_DWORD *)(a1 + 40);
  *(_QWORD *)(a2 + 824) = *(_QWORD *)(a1 + 496);
  *(_QWORD *)(a2 + 832) = *(_QWORD *)(a1 + 504);
  *(_DWORD *)(a2 + 840) = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(a2 + 844) = *(_DWORD *)(a1 + 60);
  *(_DWORD *)(a2 + 848) = *(_DWORD *)(a1 + 64);
  *(_DWORD *)(a2 + 856) = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a2 + 784) = *(_DWORD *)(a1 + 68);
  *(_QWORD *)(a2 + 864) = *(_QWORD *)(a1 + 320);
  *(_QWORD *)(a2 + 872) = *(_QWORD *)(a1 + 328);
  LOBYTE(v23) = 3;
  LOBYTE(v22) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
    v22,
    v23);
  memmove_0(v6, *(const void **)(a1 + 872), 0x34u);
  v26 = 0.0;
  *(_DWORD *)(a2 + 852) = *(_DWORD *)(a1 + 8);
  v27 = *(_DWORD *)(a1 + 928);
  v28 = *(_DWORD *)(a1 + 936) + v27 + *(_DWORD *)(a1 + 932);
  if ( v28 )
    v26 = (float)v27 / (float)v28;
  if ( v26 <= 0.2 )
    *(_DWORD *)(a1 + 940) = 0;
  else
    ++*(_DWORD *)(a1 + 940);
  if ( dword_180043068 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180043068);
    if ( dword_180043068 == -1 )
    {
      Frequency.QuadPart = 0;
      QueryPerformanceFrequency(&Frequency);
      qword_180043070 = Frequency.QuadPart / 1000;
      Init_thread_footer(&dword_180043068);
    }
  }
  *(_DWORD *)(a2 + 880) = *(_DWORD *)(a1 + 924);
  *(_DWORD *)(a2 + 892) = *(_DWORD *)(a1 + 936);
  *(_DWORD *)(a2 + 884) = *(_DWORD *)(a1 + 928);
  *(_DWORD *)(a2 + 888) = *(_DWORD *)(a1 + 932);
  *(_DWORD *)(a2 + 896) = *(_DWORD *)(a1 + 940);
  v29 = *(_DWORD *)(a1 + 976);
  if ( v29 )
    v30 = *(_QWORD *)(a1 + 960) / (unsigned __int64)v29;
  else
    v30 = 0;
  if ( qword_180043070 < 0 )
    v31 = (float)(qword_180043070 & 1 | (unsigned int)((unsigned __int64)qword_180043070 >> 1))
        + (float)(qword_180043070 & 1 | (unsigned int)((unsigned __int64)qword_180043070 >> 1));
  else
    v31 = (float)(int)qword_180043070;
  if ( (v30 & 0x8000000000000000uLL) != 0LL )
    v32 = (float)(int)(v30 & 1 | (v30 >> 1)) + (float)(int)(v30 & 1 | (v30 >> 1));
  else
    v32 = (float)(int)v30;
  *(float *)(a2 + 900) = v32 / v31;
  v33 = *(_QWORD *)(a1 + 952);
  if ( v33 < 0 )
  {
    v35 = *(_QWORD *)(a1 + 952) & 1LL | (*(_QWORD *)(a1 + 952) >> 1);
    v34 = (float)(int)v35 + (float)(int)v35;
  }
  else
  {
    v34 = (float)(int)v33;
  }
  *(float *)(a2 + 904) = v34 / v31;
  PresentConsumer::Reset((PresentConsumer *)a1);
  return a2;
}

```

## disassembly

```asm
0x180024340  push    rbx
0x180024342  push    rbp
0x180024343  push    rsi
0x180024344  push    rdi
0x180024345  push    r12
0x180024347  push    r13
0x180024349  push    r14
0x18002434b  push    r15
0x18002434d  sub     rsp, 28h
0x180024351  mov     rdi, rdx
0x180024354  xor     ebp, ebp
0x180024356  mov     rbx, rcx
0x180024359  mov     [rdx], rbp
0x18002435c  mov     [rdx+8], rbp
0x180024360  mov     esi, 0A0h
0x180024365  mov     r8d, esi; Size
0x180024368  xor     edx, edx; Val
0x18002436a  lea     rcx, [rdi+10h]; void *
0x18002436e  call    memset_0
0x180024373  lea     r15, [rdi+0C0h]
0x18002437a  mov     [rdi+0B0h], rbp
0x180024381  mov     rcx, r15; void *
0x180024384  mov     [rdi+0B8h], rbp
0x18002438b  mov     r8d, esi; Size
0x18002438e  xor     edx, edx; Val
0x180024390  call    memset_0
0x180024395  lea     r12, [rdi+170h]
0x18002439c  mov     [rdi+160h], rbp
0x1800243a3  mov     esi, 0A8h
0x1800243a8  mov     [rdi+168h], rbp
0x1800243af  mov     r8d, esi; Size
0x1800243b2  mov     rcx, r12; void *
0x1800243b5  xor     edx, edx; Val
0x1800243b7  call    memset_0
0x1800243bc  lea     r13, [rdi+228h]
0x1800243c3  mov     [rdi+218h], rbp
0x1800243ca  mov     rcx, r13; void *
0x1800243cd  mov     [rdi+220h], rbp
0x1800243d4  mov     r8d, esi; Size
0x1800243d7  xor     edx, edx; Val
0x1800243d9  call    memset_0
0x1800243de  lea     rsi, [rdi+2D0h]
0x1800243e5  xor     eax, eax
0x1800243e7  xorps   xmm0, xmm0
0x1800243ea  movups  xmmword ptr [rsi], xmm0
0x1800243ed  movups  xmmword ptr [rsi+10h], xmm0
0x1800243f1  movups  xmmword ptr [rsi+20h], xmm0
0x1800243f5  mov     [rsi+30h], eax
0x1800243f8  mov     [rdi+304h], rbp
0x1800243ff  mov     [rdi+30Ch], rbp
0x180024406  mov     [rdi+314h], rbp
0x18002440d  mov     [rdi+31Ch], rbp
0x180024414  mov     [rdi+324h], rbp
0x18002441b  mov     [rdi+32Ch], rbp
0x180024422  mov     [rdi+334h], eax
0x180024428  mov     rax, 7FFFFFFFFFFFFFFFh
0x180024432  mov     [rdi+360h], rax
0x180024439  mov     [rdi+368h], rax
0x180024440  mov     [rdi+338h], rbp
0x180024447  mov     [rdi+340h], rbp
0x18002444e  mov     [rdi+348h], rbp
0x180024455  mov     [rdi+350h], ebp
0x18002445b  mov     dword ptr [rdi+354h], 0FFFFFFFFh
0x180024465  mov     [rdi+358h], rbp
0x18002446c  mov     [rdi+370h], rbp
0x180024473  mov     [rdi+378h], rbp
0x18002447a  mov     [rdi+380h], rbp
0x180024481  mov     [rdi+388h], rbp
0x180024488  cmp     [rbx+48h], bpl
0x18002448c  jnz     short loc_18002449B
0x18002448e  mov     ecx, [rbx+210h]
0x180024494  inc     ecx
0x180024496  cmp     ecx, 1
0x180024499  jnb     short loc_1800244A0
0x18002449b  mov     ecx, 1
0x1800244a0  cmp     [rbx+49h], bpl
0x1800244a4  jnz     short loc_1800244B3
0x1800244a6  mov     ebp, [rbx+270h]
0x1800244ac  inc     ebp
0x1800244ae  cmp     ebp, 1
0x1800244b1  jnb     short loc_1800244B8
0x1800244b3  mov     ebp, 1
0x1800244b8  lea     eax, [rcx-1]
0x1800244bb  test    eax, eax
0x1800244bd  jz      loc_180024561
0x1800244c3  lea     rsi, [rbx+200h]
0x1800244ca  cmp     dword ptr [rsi+10h], 0
0x1800244ce  jz      short loc_1800244DD
0x1800244d0  mov     ecx, [rsi+10h]
0x1800244d3  xor     edx, edx
0x1800244d5  mov     rax, [rsi]
0x1800244d8  div     rcx
0x1800244db  jmp     short loc_1800244DF
0x1800244dd  xor     eax, eax
0x1800244df  mov     rcx, rsi
0x1800244e2  mov     [rdi], rax
0x1800244e5  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x1800244ea  mov     [rdi+8], rax
0x1800244ee  lea     rcx, [rdi+10h]; void *
0x1800244f2  mov     rdx, [rbx+238h]; Src
0x1800244f9  mov     r8d, 0A0h; Size
0x1800244ff  call    memmove_0
0x180024504  xor     r14d, r14d
0x180024507  cmp     [rsi+10h], r14d
0x18002450b  jz      short loc_18002451D
0x18002450d  mov     ecx, [rsi+10h]
0x180024510  xor     edx, edx
0x180024512  mov     rax, [rsi]
0x180024515  div     rcx
0x180024518  mov     rcx, rax
0x18002451b  jmp     short loc_180024520
0x18002451d  mov     rcx, r14
0x180024520  xorps   xmm1, xmm1
0x180024523  test    rcx, rcx
0x180024526  js      short loc_18002452F
0x180024528  cvtsi2ss xmm1, rcx
0x18002452d  jmp     short loc_180024544
0x18002452f  mov     rax, rcx
0x180024532  and     ecx, 1
0x180024535  shr     rax, 1
0x180024538  or      rax, rcx
0x18002453b  cvtsi2ss xmm1, rax
0x180024540  addss   xmm1, xmm1
0x180024544  movss   xmm0, cs:__real@47c35000
0x18002454c  lea     rsi, [rdi+2D0h]
0x180024553  divss   xmm0, xmm1
0x180024557  movss   dword ptr [rdi+304h], xmm0
0x18002455f  jmp     short loc_180024564
0x180024561  xor     r14d, r14d
0x180024564  lea     eax, [rbp-1]
0x180024567  test    eax, eax
0x180024569  jz      short loc_1800245B4
0x18002456b  lea     r8, [rbx+260h]
0x180024572  cmp     [r8+10h], r14d
0x180024576  jz      short loc_180024586
0x180024578  mov     ecx, [r8+10h]
0x18002457c  xor     edx, edx
0x18002457e  mov     rax, [r8]
0x180024581  div     rcx
0x180024584  jmp     short loc_180024589
0x180024586  mov     rax, r14
0x180024589  mov     rcx, r8
0x18002458c  mov     [rdi+0B0h], rax
0x180024593  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x180024598  mov     [rdi+0B8h], rax
0x18002459f  mov     r8d, 0A0h; Size
0x1800245a5  mov     rdx, [rbx+298h]; Src
0x1800245ac  mov     rcx, r15; void *
0x1800245af  call    memmove_0
0x1800245b4  mov     r8b, 3
0x1800245b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x1800245be  mov     dl, 1
0x1800245c0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800245c5  lea     r8, [rbx+2C0h]
0x1800245cc  cmp     [r8+10h], r14d
0x1800245d0  jz      short loc_1800245E0
0x1800245d2  mov     ecx, [r8+10h]
0x1800245d6  xor     edx, edx
0x1800245d8  mov     rax, [r8]
0x1800245db  div     rcx
0x1800245de  jmp     short loc_1800245E3
0x1800245e0  mov     rax, r14
0x1800245e3  mov     rcx, r8
0x1800245e6  mov     [rdi+160h], rax
0x1800245ed  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x1800245f2  lea     r8, [rbx+310h]
0x1800245f9  mov     [rdi+168h], rax
0x180024600  cmp     [r8+10h], r14d
0x180024604  jz      short loc_180024614
0x180024606  mov     ecx, [r8+10h]
0x18002460a  xor     edx, edx
0x18002460c  mov     rax, [r8]
0x18002460f  div     rcx
0x180024612  jmp     short loc_180024617
0x180024614  mov     rax, r14
0x180024617  mov     rcx, r8
0x18002461a  mov     [rdi+218h], rax
0x180024621  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x180024626  mov     [rdi+220h], rax
0x18002462d  mov     ebp, 0A8h
0x180024632  mov     rdx, [rbx+2F8h]; Src
0x180024639  mov     r8d, ebp; Size
0x18002463c  mov     rcx, r12; void *
0x18002463f  call    memmove_0
0x180024644  mov     rdx, [rbx+348h]; Src
0x18002464b  mov     r8d, ebp; Size
0x18002464e  mov     rcx, r13; void *
0x180024651  call    memmove_0
0x180024656  cmp     [rbx+48h], r14b
0x18002465a  jz      short loc_180024661
0x18002465c  mov     eax, r14d
0x18002465f  jmp     short loc_180024669
0x180024661  mov     eax, [rbx+210h]
0x180024667  inc     eax
0x180024669  mov     [rdi+30Ch], eax
0x18002466f  cmp     [rbx+49h], r14b
0x180024673  jz      short loc_18002467A
0x180024675  mov     eax, r14d
0x180024678  jmp     short loc_180024682
0x18002467a  mov     eax, [rbx+270h]
0x180024680  inc     eax
0x180024682  mov     [rdi+308h], eax
0x180024688  mov     eax, [rbx+10h]
0x18002468b  mov     [rdi+314h], eax
0x180024691  mov     eax, [rbx+0Ch]
0x180024694  mov     [rdi+318h], eax
0x18002469a  mov     eax, [rbx+14h]
0x18002469d  mov     [rdi+31Ch], eax
0x1800246a3  mov     eax, [rbx+18h]
0x1800246a6  mov     [rdi+320h], eax
0x1800246ac  mov     eax, [rbx+1Ch]
0x1800246af  mov     [rdi+324h], eax
0x1800246b5  mov     eax, [rbx+20h]
0x1800246b8  mov     [rdi+328h], eax
0x1800246be  mov     eax, [rbx+24h]
0x1800246c1  mov     [rdi+32Ch], eax
0x1800246c7  mov     eax, [rbx+28h]
0x1800246ca  mov     [rdi+330h], eax
0x1800246d0  mov     rax, [rbx+1F0h]
0x1800246d7  mov     [rdi+338h], rax
0x1800246de  mov     rax, [rbx+1F8h]
0x1800246e5  mov     [rdi+340h], rax
0x1800246ec  mov     eax, [rbx+2Ch]
0x1800246ef  mov     [rdi+348h], eax
0x1800246f5  mov     eax, [rbx+3Ch]
0x1800246f8  mov     [rdi+34Ch], eax
0x1800246fe  mov     eax, [rbx+40h]
0x180024701  mov     [rdi+350h], eax
0x180024707  mov     eax, [rbx+38h]
0x18002470a  mov     [rdi+358h], eax
0x180024710  mov     eax, [rbx+44h]
0x180024713  mov     [rdi+310h], eax
0x180024719  mov     rax, [rbx+140h]
0x180024720  mov     [rdi+360h], rax
0x180024727  mov     rax, [rbx+148h]
0x18002472e  mov     [rdi+368h], rax
0x180024735  mov     r8b, 3
0x180024738  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x18002473f  mov     dl, 1
0x180024741  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180024746  mov     rdx, [rbx+368h]; Src
0x18002474d  mov     r8d, 34h ; '4'; Size
0x180024753  mov     rcx, rsi; void *
0x180024756  call    memmove_0
0x18002475b  mov     eax, [rbx+8]
0x18002475e  xorps   xmm1, xmm1
0x180024761  mov     [rdi+354h], eax
0x180024767  mov     edx, [rbx+3A0h]
0x18002476d  mov     r8d, [rbx+3A4h]
0x180024774  add     r8d, edx
0x180024777  add     r8d, [rbx+3A8h]
0x18002477e  jz      short loc_180024794
0x180024780  mov     eax, r8d
0x180024783  xorps   xmm0, xmm0
0x180024786  cvtsi2ss xmm1, rdx
0x18002478b  cvtsi2ss xmm0, rax
0x180024790  divss   xmm1, xmm0
0x180024794  comiss  xmm1, cs:__real@3e4ccccd
0x18002479b  jbe     short loc_1800247A5
0x18002479d  inc     dword ptr [rbx+3ACh]
0x1800247a3  jmp     short loc_1800247AC
0x1800247a5  mov     [rbx+3ACh], r14d
0x1800247ac  mov     ecx, cs:_tls_index
0x1800247b2  mov     rax, gs:58h
0x1800247bb  mov     edx, 4
0x1800247c0  mov     rax, [rax+rcx*8]
0x1800247c4  mov     eax, [rdx+rax]
0x1800247c7  cmp     cs:dword_180043068, eax
0x1800247cd  jg      loc_1800248DD
0x1800247d3  mov     eax, [rbx+39Ch]
0x1800247d9  mov     [rdi+370h], eax
0x1800247df  mov     eax, [rbx+3A8h]
0x1800247e5  mov     [rdi+37Ch], eax
0x1800247eb  mov     eax, [rbx+3A0h]
0x1800247f1  mov     [rdi+374h], eax
0x1800247f7  mov     eax, [rbx+3A4h]
0x1800247fd  mov     [rdi+378h], eax
0x180024803  mov     eax, [rbx+3ACh]
0x180024809  mov     [rdi+380h], eax
0x18002480f  mov     eax, [rbx+3D0h]
0x180024815  test    eax, eax
0x180024817  jz      short loc_18002482C
0x180024819  mov     ecx, eax
0x18002481b  xor     edx, edx
0x18002481d  mov     rax, [rbx+3C0h]
0x180024824  div     rcx
0x180024827  mov     rcx, rax
0x18002482a  jmp     short loc_18002482F
0x18002482c  mov     rcx, r14
0x18002482f  mov     rdx, cs:qword_180043070
0x180024836  xorps   xmm1, xmm1
0x180024839  test    rdx, rdx
0x18002483c  js      short loc_180024845
0x18002483e  cvtsi2ss xmm1, rdx
0x180024843  jmp     short loc_18002485A
0x180024845  mov     rax, rdx
0x180024848  and     edx, 1
0x18002484b  shr     rax, 1
0x18002484e  or      rax, rdx
0x180024851  cvtsi2ss xmm1, rax
  ... truncated ...
```
