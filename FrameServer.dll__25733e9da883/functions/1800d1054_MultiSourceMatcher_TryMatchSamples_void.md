# MultiSourceMatcher::_TryMatchSamples(void)

- ea: `0x1800d1054`
- end: `0x1800d1478`
- name: `?_TryMatchSamples@MultiSourceMatcher@@AEAAXXZ`
- size: `1060`
- prototype: `void __fastcall(__m128i *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800cf4f0`

## callees

- `0x1800095c8`
- `0x180009608`
- `0x18000a460`
- `0x180018e9c`
- `0x1800cfe20`
- `0x1800cff38`
- `0x1800d0650`
- `0x1800d0804`
- `0x1800d0920`
- `0x1800d0d20`
- `0x1800d0f44`
- `0x1800d0fb0`
- `0x1800d1054`
- `0x1800d1870`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x1800d12ca`
- `MFPlat!MFCreateCollection` at `0x1800d12ca`
- `MFPlat!MFCreateMuxStreamSample` at `0x1800d1386`
- `MFPlat!MFCreateMuxStreamSample` at `0x1800d1386`
- `MFPlat!MFTraceError` at `0x1800d1431`
- `MFPlat!MFTraceError` at `0x1800d1431`

## pseudocode

```c
void __fastcall MultiSourceMatcher::_TryMatchSamples(__m128i *this)
{
  unsigned int v1; // r13d
  char *v3; // rax
  const struct MsmSourceState *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // esi
  __int64 v9; // r15
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  double RelativeTime; // xmm0_8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rcx
  __m128i v22; // xmm1
  __m128i v23; // xmm0
  int v24; // eax
  __int64 v25; // rdx
  unsigned int i; // r15d
  __int64 v27; // rdx
  __int64 (*v28)(void); // rax
  int v29; // eax
  __int64 v30; // rdx
  char v31; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v33; // [rsp+50h] [rbp-30h]
  __int64 v34; // [rsp+54h] [rbp-2Ch]
  void *v35; // [rsp+60h] [rbp-20h] BYREF
  int v36; // [rsp+68h] [rbp-18h]
  __int64 v37; // [rsp+6Ch] [rbp-14h]
  __int64 v38; // [rsp+C8h] [rbp+48h] BYREF
  struct IMFSample *v39; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v40; // [rsp+D8h] [rbp+58h] BYREF

  v1 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  v3 = (char *)MultiSourceMatcher::_SelectHighestIntervalSource((__int64)this, &v40);
  v4 = 0;
  if ( &v31 != v3 )
  {
    v4 = *(const struct MsmSourceState **)v3;
    *(_QWORD *)v3 = 0;
  }
  v5 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( !v4 )
  {
    v6 = 683;
    goto LABEL_58;
  }
  MultiSourceMatcher::_CheckForUnmatchableFrames((MultiSourceMatcher *)this, v4);
  if ( !(unsigned __int8)MultiSourceMatcher::_GatherAndSortFrameQueue((MultiSourceMatcher *)this) )
  {
    v6 = 692;
LABEL_58:
    MFTraceError(
      "avcore\\mf\\frameserver\\multisourcematcher\\multisourcematcher.cpp",
      v6,
      "MultiSourceMatcher::_TryMatchSamples",
      this,
      0,
      1);
    goto LABEL_59;
  }
  if ( !(unsigned __int8)MultiSourceMatcher::_SelectBestTime((MultiSourceMatcher *)this, (__int64)&v38, (__int64)&v32) )
    goto LABEL_59;
  v7 = MultiSourceMatcher::_DequeueAllSamplesUpTo((MultiSourceMatcher *)this);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids, this, v7);
    goto LABEL_55;
  }
  if ( g_useVerboseTracing && (unsigned __int8)byte_18010EC4D >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 51, &WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids, this);
  v9 = 0x7FFFFFFFFFFFFFFFLL;
  v10 = 0;
  if ( v33 )
  {
    v11 = v32;
    do
    {
      v12 = *(_QWORD *)(v11 + 8LL * v1);
      if ( v12 )
      {
        v13 = *(_QWORD *)(v12 + 32);
        v14 = v13;
        if ( v9 < v13 )
          v14 = v9;
        v9 = v14;
        v15 = *(_QWORD *)(v12 + 32);
        if ( v10 > v13 )
          v15 = v10;
        v10 = v15;
        if ( g_useVerboseTracing && (unsigned __int8)byte_18010EC4D >= 0x20u )
        {
          RelativeTime = MultiSourceMatcher::_GetRelativeTime((MultiSourceMatcher *)this, *(_QWORD *)(v12 + 32));
          WPP_SF_qDqig(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            52,
            v18,
            this,
            *(_DWORD *)(v17 + 16),
            *(_QWORD *)(v17 + 24),
            v18,
            *(_QWORD *)&RelativeTime);
          v11 = v32;
        }
      }
      ++v1;
    }
    while ( v1 < v33 );
  }
  v19 = v10 - v9;
  if ( !this[7].m128i_i64[0] )
    this[7].m128i_i64[0] = v9;
  v20 = this[9].m128i_i64[0];
  this[7].m128i_i64[1] = v9;
  v21 = v19;
  v38 = 0;
  if ( v20 < v19 )
    v21 = v20;
  v22 = _mm_unpacklo_epi64((__m128i)1uLL, (__m128i)(unsigned __int64)v19);
  v23 = _mm_loadu_si128(this + 8);
  if ( this[9].m128i_i64[1] > v19 )
    v19 = this[9].m128i_i64[1];
  this[9].m128i_i64[0] = v21;
  this[9].m128i_i64[1] = v19;
  this[8] = _mm_add_epi64(v22, v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  v24 = MFCreateCollection(&v38);
  v8 = v24;
  if ( v24 < 0 )
  {
    if ( g_wppLevels )
    {
      v25 = 53;
      goto LABEL_35;
    }
    goto LABEL_54;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v33 )
    {
      v39 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v29 = MFCreateMuxStreamSample(v38, &v39);
      v8 = v29;
      if ( v29 >= 0 )
      {
        v29 = MultiSourceMatcher::_QueueMuxSample((MultiSourceMatcher *)this, v39);
        v8 = v29;
        if ( v29 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          goto LABEL_59;
        }
        if ( g_wppLevels )
        {
          v30 = 57;
          goto LABEL_52;
        }
      }
      else if ( g_wppLevels )
      {
        v30 = 56;
LABEL_52:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids, this, v29);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      goto LABEL_54;
    }
    v27 = *(_QWORD *)(v32 + 8LL * i);
    v28 = *(__int64 (**)(void))(*(_QWORD *)v38 + 40LL);
    if ( !v27 )
      break;
    v24 = ((__int64 (__fastcall *)(__int64, _QWORD))v28)(v38, *(_QWORD *)(v27 + 24));
    v8 = v24;
    if ( v24 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_54;
      v25 = 54;
      goto LABEL_35;
    }
LABEL_43:
    ;
  }
  v24 = v28();
  v8 = v24;
  if ( v24 >= 0 )
    goto LABEL_43;
  if ( !g_wppLevels )
    goto LABEL_54;
  v25 = 55;
LABEL_35:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids, this, v24);
LABEL_54:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
LABEL_55:
  MultiSourceMatcher::_SetErrorStatus((MultiSourceMatcher *)this, v8);
LABEL_59:
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)&v32);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v35);
  if ( v4 )
    (*(void (__fastcall **)(const struct MsmSourceState *))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x1800d1054  mov     [rsp-38h+arg_0], rbx
0x1800d1059  push    rbp
0x1800d105a  push    rsi
0x1800d105b  push    rdi
0x1800d105c  push    r12
0x1800d105e  push    r13
0x1800d1060  push    r14
0x1800d1062  push    r15
0x1800d1064  mov     rbp, rsp
0x1800d1067  sub     rsp, 80h
0x1800d106e  xor     r13d, r13d
0x1800d1071  lea     rdx, [rbp+arg_18]
0x1800d1075  mov     [rbp+arg_10], r13
0x1800d1079  mov     rdi, rcx
0x1800d107c  mov     [rbp+arg_8], r13
0x1800d1080  mov     [rbp+var_20], r13
0x1800d1084  mov     [rbp+var_14], r13
0x1800d1088  mov     [rbp+var_18], r13d
0x1800d108c  mov     [rbp+var_38], r13
0x1800d1090  mov     [rbp+var_2C], r13
0x1800d1094  mov     [rbp+var_30], r13d
0x1800d1098  call    ?_SelectHighestIntervalSource@MultiSourceMatcher@@AEAA?AV?$ComPtr@UMsmSourceState@@@WRL@Microsoft@@XZ; MultiSourceMatcher::_SelectHighestIntervalSource(void)
0x1800d109d  lea     rcx, [rbp+var_40]
0x1800d10a1  mov     ebx, r13d
0x1800d10a4  cmp     rcx, rax
0x1800d10a7  jz      short loc_1800D10AF
0x1800d10a9  mov     rbx, [rax]
0x1800d10ac  mov     [rax], r13
0x1800d10af  mov     rcx, [rbp+arg_18]
0x1800d10b3  test    rcx, rcx
0x1800d10b6  jz      short loc_1800D10C8
0x1800d10b8  mov     [rbp+arg_18], r13
0x1800d10bc  mov     rax, [rcx]
0x1800d10bf  mov     rax, [rax+10h]
0x1800d10c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d10c8  test    rbx, rbx
0x1800d10cb  jz      loc_1800D140E
0x1800d10d1  mov     rdx, rbx; struct MsmSourceState *
0x1800d10d4  mov     rcx, rdi; this
0x1800d10d7  call    ?_CheckForUnmatchableFrames@MultiSourceMatcher@@AEAAXPEBUMsmSourceState@@@Z; MultiSourceMatcher::_CheckForUnmatchableFrames(MsmSourceState const *)
0x1800d10dc  lea     rdx, [rbp+var_20]
0x1800d10e0  mov     rcx, rdi; this
0x1800d10e3  call    ?_GatherAndSortFrameQueue@MultiSourceMatcher@@AEAA_NPEAV?$CTUnkArray@UMsmFrameInfo@@@@@Z; MultiSourceMatcher::_GatherAndSortFrameQueue(CTUnkArray<MsmFrameInfo> *)
0x1800d10e8  test    al, al
0x1800d10ea  jnz     short loc_1800D10F6
0x1800d10ec  mov     edx, 2B4h
0x1800d10f1  jmp     loc_1800D1413
0x1800d10f6  lea     rax, [rbp+var_38]
0x1800d10fa  mov     rdx, rbx
0x1800d10fd  mov     [rsp+80h+var_58], rax; __int64
0x1800d1102  lea     r9, [rbp+arg_10]
0x1800d1106  lea     rax, [rbp+arg_8]
0x1800d110a  mov     rcx, rdi; this
0x1800d110d  lea     r8, [rbp+var_20]
0x1800d1111  mov     [rsp+80h+var_60], rax; __int64
0x1800d1116  call    ?_SelectBestTime@MultiSourceMatcher@@AEAA_NPEBUMsmSourceState@@AEBV?$CTUnkArray@UMsmFrameInfo@@@@PEA_J2PEAV3@@Z; MultiSourceMatcher::_SelectBestTime(MsmSourceState const *,CTUnkArray<MsmFrameInfo> const &,__int64 *,__int64 *,CTUnkArray<MsmFrameInfo> *)
0x1800d111b  test    al, al
0x1800d111d  jz      loc_1800D1437
0x1800d1123  lea     rdx, [rbp+var_38]
0x1800d1127  mov     rcx, rdi; this
0x1800d112a  call    ?_DequeueAllSamplesUpTo@MultiSourceMatcher@@AEAAJAEBV?$CTUnkArray@UMsmFrameInfo@@@@@Z; MultiSourceMatcher::_DequeueAllSamplesUpTo(CTUnkArray<MsmFrameInfo> const &)
0x1800d112f  mov     esi, eax
0x1800d1131  test    eax, eax
0x1800d1133  jns     short loc_1800D116F
0x1800d1135  mov     r14d, 1
0x1800d113b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d1142  jb      loc_1800D13EE
0x1800d1148  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d114f  lea     edx, [r14+31h]
0x1800d1153  mov     r9, rdi
0x1800d1156  mov     dword ptr [rsp+80h+var_60], eax
0x1800d115a  lea     r8, WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids
0x1800d1161  mov     rcx, [rcx+10h]
0x1800d1165  call    WPP_SF_qD
0x1800d116a  jmp     loc_1800D13EE
0x1800d116f  cmp     cs:?g_useVerboseTracing@@3_NA, r13b; bool g_useVerboseTracing
0x1800d1176  lea     r12, WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids
0x1800d117d  jz      short loc_1800D11A6
0x1800d117f  cmp     cs:byte_18010EC4D, 20h ; ' '
0x1800d1186  jb      short loc_1800D11A6
0x1800d1188  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d118f  mov     edx, 33h ; '3'
0x1800d1194  mov     r9, rdi
0x1800d1197  mov     r8, r12
0x1800d119a  mov     rcx, [rcx+0D8h]
0x1800d11a1  call    WPP_SF_q
0x1800d11a6  mov     r15, 7FFFFFFFFFFFFFFFh
0x1800d11b0  mov     rsi, r13
0x1800d11b3  mov     r14d, 1
0x1800d11b9  cmp     [rbp+var_30], r13d
0x1800d11bd  jbe     loc_1800D1256
0x1800d11c3  mov     rcx, [rbp+var_38]
0x1800d11c7  mov     eax, r13d
0x1800d11ca  mov     r9, [rcx+rax*8]
0x1800d11ce  test    r9, r9
0x1800d11d1  jz      short loc_1800D1249
0x1800d11d3  mov     r8, [r9+20h]
0x1800d11d7  cmp     r15, r8
0x1800d11da  mov     rax, r8
0x1800d11dd  cmovl   rax, r15
0x1800d11e1  cmp     rsi, r8
0x1800d11e4  mov     r15, rax
0x1800d11e7  mov     rax, r8
0x1800d11ea  cmovg   rax, rsi
0x1800d11ee  cmp     cs:?g_useVerboseTracing@@3_NA, 0; bool g_useVerboseTracing
0x1800d11f5  mov     rsi, rax
0x1800d11f8  jz      short loc_1800D1249
0x1800d11fa  cmp     cs:byte_18010EC4D, 20h ; ' '
0x1800d1201  jb      short loc_1800D1249
0x1800d1203  mov     rdx, r8; __int64
0x1800d1206  mov     rcx, rdi; this
0x1800d1209  call    ?_GetRelativeTime@MultiSourceMatcher@@AEAAN_J@Z; MultiSourceMatcher::_GetRelativeTime(__int64)
0x1800d120e  mov     rax, [r9+18h]
0x1800d1212  mov     edx, 34h ; '4'
0x1800d1217  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d121e  movsd   [rsp+80h+var_48], xmm0
0x1800d1224  mov     [rsp+80h+var_50], r8
0x1800d1229  mov     [rsp+80h+var_58], rax
0x1800d122e  mov     eax, [r9+10h]
0x1800d1232  mov     r9, rdi
0x1800d1235  mov     rcx, [rcx+0D8h]
0x1800d123c  mov     dword ptr [rsp+80h+var_60], eax
0x1800d1240  call    WPP_SF_qDqig
0x1800d1245  mov     rcx, [rbp+var_38]
0x1800d1249  add     r13d, r14d
0x1800d124c  cmp     r13d, [rbp+var_30]
0x1800d1250  jb      loc_1800D11C7
0x1800d1256  sub     rsi, r15
0x1800d1259  xor     r13d, r13d
0x1800d125c  cmp     [rdi+70h], r13
0x1800d1260  jnz     short loc_1800D1266
0x1800d1262  mov     [rdi+70h], r15
0x1800d1266  mov     rax, [rdi+90h]
0x1800d126d  movq    xmm0, rsi
0x1800d1272  cmp     rax, rsi
0x1800d1275  mov     [rdi+78h], r15
0x1800d1279  mov     rcx, rsi
0x1800d127c  mov     [rbp+arg_8], r13
0x1800d1280  cmovl   rcx, rax
0x1800d1284  movq    xmm1, r14
0x1800d1289  mov     rax, [rdi+98h]
0x1800d1290  punpcklqdq xmm1, xmm0
0x1800d1294  cmp     rax, rsi
0x1800d1297  movdqu  xmm0, xmmword ptr [rdi+80h]
0x1800d129f  cmovg   rsi, rax
0x1800d12a3  mov     [rdi+90h], rcx
0x1800d12aa  lea     rcx, [rbp+arg_8]
0x1800d12ae  mov     [rdi+98h], rsi
0x1800d12b5  paddq   xmm1, xmm0
0x1800d12b9  movdqu  xmmword ptr [rdi+80h], xmm1
0x1800d12c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d12c6  lea     rcx, [rbp+arg_8]
0x1800d12ca  call    cs:__imp_MFCreateCollection
0x1800d12d0  mov     esi, eax
0x1800d12d2  test    eax, eax
0x1800d12d4  jns     short loc_1800D1307
0x1800d12d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d12dd  jb      loc_1800D13E5
0x1800d12e3  mov     edx, 35h ; '5'
0x1800d12e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d12ef  mov     r9, rdi
0x1800d12f2  mov     r8, r12
0x1800d12f5  mov     dword ptr [rsp+80h+var_60], eax
0x1800d12f9  mov     rcx, [rcx+10h]
0x1800d12fd  call    WPP_SF_qD
0x1800d1302  jmp     loc_1800D13E5
0x1800d1307  mov     r15d, r13d
0x1800d130a  cmp     r15d, [rbp+var_30]
0x1800d130e  jnb     short loc_1800D1371
0x1800d1310  mov     rcx, [rbp+var_38]
0x1800d1314  mov     eax, r15d
0x1800d1317  mov     rdx, [rcx+rax*8]
0x1800d131b  mov     rcx, [rbp+arg_8]
0x1800d131f  mov     rax, [rcx]
0x1800d1322  mov     rax, [rax+28h]
0x1800d1326  test    rdx, rdx
0x1800d1329  jz      short loc_1800D134E
0x1800d132b  mov     rdx, [rdx+18h]
0x1800d132f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1334  mov     esi, eax
0x1800d1336  test    eax, eax
0x1800d1338  jns     short loc_1800D1359
0x1800d133a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d1341  jb      loc_1800D13E5
0x1800d1347  mov     edx, 36h ; '6'
0x1800d134c  jmp     short loc_1800D12E8
0x1800d134e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1353  mov     esi, eax
0x1800d1355  test    eax, eax
0x1800d1357  js      short loc_1800D135E
0x1800d1359  add     r15d, r14d
0x1800d135c  jmp     short loc_1800D130A
0x1800d135e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d1365  jb      short loc_1800D13E5
0x1800d1367  mov     edx, 37h ; '7'
0x1800d136c  jmp     loc_1800D12E8
0x1800d1371  lea     rcx, [rbp+arg_10]
0x1800d1375  mov     [rbp+arg_10], r13
0x1800d1379  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d137e  mov     rcx, [rbp+arg_8]
0x1800d1382  lea     rdx, [rbp+arg_10]
0x1800d1386  call    cs:__imp_MFCreateMuxStreamSample
0x1800d138c  mov     esi, eax
0x1800d138e  test    eax, eax
0x1800d1390  jns     short loc_1800D13A2
0x1800d1392  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d1399  jb      short loc_1800D13DC
0x1800d139b  mov     edx, 38h ; '8'
0x1800d13a0  jmp     short loc_1800D13C2
0x1800d13a2  mov     rdx, [rbp+arg_10]; struct IMFSample *
0x1800d13a6  mov     rcx, rdi; this
0x1800d13a9  call    ?_QueueMuxSample@MultiSourceMatcher@@AEAAJPEAUIMFSample@@@Z; MultiSourceMatcher::_QueueMuxSample(IMFSample *)
0x1800d13ae  mov     esi, eax
0x1800d13b0  test    eax, eax
0x1800d13b2  jns     short loc_1800D13FA
0x1800d13b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d13bb  jb      short loc_1800D13DC
0x1800d13bd  mov     edx, 39h ; '9'
0x1800d13c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d13c9  mov     r9, rdi
0x1800d13cc  mov     r8, r12
0x1800d13cf  mov     dword ptr [rsp+80h+var_60], eax
0x1800d13d3  mov     rcx, [rcx+10h]
0x1800d13d7  call    WPP_SF_qD
0x1800d13dc  lea     rcx, [rbp+arg_10]
0x1800d13e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d13e5  lea     rcx, [rbp+arg_8]
0x1800d13e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d13ee  mov     edx, esi; int
0x1800d13f0  mov     rcx, rdi; this
0x1800d13f3  call    ?_SetErrorStatus@MultiSourceMatcher@@AEAAJJ@Z; MultiSourceMatcher::_SetErrorStatus(long)
0x1800d13f8  jmp     short loc_1800D1437
0x1800d13fa  lea     rcx, [rbp+arg_10]
0x1800d13fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d1403  lea     rcx, [rbp+arg_8]
0x1800d1407  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d140c  jmp     short loc_1800D1437
0x1800d140e  mov     edx, 2ABh
0x1800d1413  mov     dword ptr [rsp+80h+var_58], 1
0x1800d141b  lea     r8, aMultisourcemat_0; "MultiSourceMatcher::_TryMatchSamples"
0x1800d1422  mov     r9, rdi
0x1800d1425  mov     dword ptr [rsp+80h+var_60], r13d
0x1800d142a  lea     rcx, aAvcoreMfFrames_1; "avcore\\mf\\frameserver\\multisourcemat"...
0x1800d1431  call    cs:__imp_MFTraceError
0x1800d1437  lea     rcx, [rbp+var_38]; void *
0x1800d143b  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800d1440  lea     rcx, [rbp+var_20]; void *
0x1800d1444  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800d1449  test    rbx, rbx
0x1800d144c  jz      short loc_1800D145D
0x1800d144e  mov     rax, [rbx]
0x1800d1451  mov     rcx, rbx
0x1800d1454  mov     rax, [rax+10h]
0x1800d1458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d145d  mov     rbx, [rsp+80h+arg_0]
0x1800d1465  add     rsp, 80h
0x1800d146c  pop     r15
0x1800d146e  pop     r14
0x1800d1470  pop     r13
0x1800d1472  pop     r12
0x1800d1474  pop     rdi
0x1800d1475  pop     rsi
0x1800d1476  pop     rbp
0x1800d1477  retn
```
