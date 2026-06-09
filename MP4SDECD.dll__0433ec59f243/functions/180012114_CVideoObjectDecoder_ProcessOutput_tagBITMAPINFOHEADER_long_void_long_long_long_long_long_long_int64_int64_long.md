# CVideoObjectDecoder::ProcessOutput(tagBITMAPINFOHEADER *,long,void *,long,long,long,long,long,long,__int64 *,__int64 *,long)

- ea: `0x180012114`
- end: `0x18001256e`
- name: `?ProcessOutput@CVideoObjectDecoder@@QEAAJPEAUtagBITMAPINFOHEADER@@JPEAXJJJJJJPEA_J2J@Z`
- size: `1114`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *this, struct tagBITMAPINFOHEADER *, int, char *, int, int, int, int, int, int, __int64 *, __int64 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013704`

## callees

- `0x180012114`
- `0x180012a08`
- `0x180013a2c`
- `0x180025294`
- `0x18002aac0`
- `0x180032478`
- `0x180043db8`
- `0x180046010`

## import_xrefs

- `mfperfhelper!__imp_ippiYCbCr420_8u_P3P2R` at `0x1800122d4`
- `mfperfhelper!__imp_ippiYCbCr420_8u_P3P2R` at `0x1800122d4`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180012372`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x1800123ca`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x1800123ed`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180012372`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x1800123ca`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x1800123ed`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::ProcessOutput(
        CVideoObjectDecoder *this,
        struct tagBITMAPINFOHEADER *a2,
        int a3,
        char *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        __int64 *a11,
        __int64 *a12,
        int a13)
{
  LONG biWidth; // r13d
  LONG biHeight; // esi
  unsigned __int8 *v17; // rbx
  unsigned __int8 *v18; // r15
  unsigned __int8 *v19; // r12
  int v20; // r11d
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rcx
  unsigned __int8 *v24; // rax
  int v25; // eax
  int v26; // ecx
  int i; // r8d
  int v28; // ecx
  __int64 result; // rax
  int v30; // esi
  __int64 v31; // rax
  struct OutputFrame *v32; // rdx
  char *v33; // rax
  bool v34; // zf
  __int64 v35; // rax
  __int64 v36; // rcx
  __int128 v37; // xmm1
  __int64 v38; // xmm0_8
  int v39; // [rsp+20h] [rbp-91h]
  unsigned int v40; // [rsp+48h] [rbp-69h]
  unsigned int v41; // [rsp+50h] [rbp-61h]
  unsigned int v42; // [rsp+58h] [rbp-59h]
  __int64 v44; // [rsp+60h] [rbp-51h]
  int v46; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v47; // [rsp+7Ch] [rbp-35h]
  unsigned int v48; // [rsp+80h] [rbp-31h]
  unsigned __int8 *v49; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int8 *v50; // [rsp+90h] [rbp-21h]
  unsigned __int8 *v51; // [rsp+98h] [rbp-19h]
  int v52; // [rsp+140h] [rbp+8Fh]
  int v53; // [rsp+148h] [rbp+97h]

  if ( a3 > 0 )
    biWidth = a3;
  else
    biWidth = a2->biWidth;
  biHeight = -a2->biHeight;
  if ( a2->biHeight > 0 )
    biHeight = a2->biHeight;
  if ( !*((_DWORD *)this + 29) )
  {
    if ( !a13 || !*((_DWORD *)this + 27) )
      return 4294967290LL;
    v31 = *((_QWORD *)this + 153);
    *((_DWORD *)this + 29) = 1;
    *((_QWORD *)this + 15) = v31;
    *((_QWORD *)this + 16) = *((_QWORD *)this + 154);
    *((_QWORD *)this + 17) = *((_QWORD *)this + 155);
    *((_QWORD *)this + 18) = *((_QWORD *)this + 32);
    *((_QWORD *)this + 19) = *((_QWORD *)this + 34);
    *(_QWORD *)((char *)this + 108) = 0;
  }
  *a11 = *((_QWORD *)this + 18);
  *a12 = *((_QWORD *)this + 19);
  if ( !a4 )
    goto LABEL_26;
  if ( !*((_DWORD *)this + 1632)
    && *((_DWORD *)this + 1640) >= 0x32u
    && *((_DWORD *)this + 1638)
    && *((_DWORD *)this + 1639)
    && *((int *)this + 1635) < 3 )
  {
    CVideoObjectDecoder::CopyToPostProc(this, (CVideoObjectDecoder *)((char *)this + 120));
    v17 = (unsigned __int8 *)*((_QWORD *)this + 670);
    v18 = (unsigned __int8 *)*((_QWORD *)this + 671);
    v19 = (unsigned __int8 *)*((_QWORD *)this + 672);
    CVideoObjectDecoder::DeblockFrame(this, v32);
  }
  else
  {
    v17 = (unsigned __int8 *)*((_QWORD *)this + 15);
    v18 = (unsigned __int8 *)*((_QWORD *)this + 16);
    v19 = (unsigned __int8 *)*((_QWORD *)this + 17);
  }
  if ( !v17 || !v18 || !v19 || !*((_DWORD *)this + 345) || !*((_DWORD *)this + 346) )
    return 4294967196LL;
  if ( g_petwPro )
    ETWWrite(this, MP4SDECD_ColorConversion_Notification_Start, 0, 0);
  v20 = *((_DWORD *)this + 333);
  v21 = a9;
  v22 = a10;
  v23 = *((int *)this + 346);
  v47 = *((_DWORD *)this + 334);
  v48 = v47;
  v24 = &v17[*((int *)this + 345)];
  v46 = v20;
  v49 = v24;
  if ( a9 > v20 )
    v21 = v20;
  v50 = &v18[v23];
  v52 = v21;
  v51 = &v19[v23];
  if ( a10 > *((_DWORD *)this + 335) )
    v22 = *((_DWORD *)this + 335);
  v53 = v22;
  if ( a2->biCompression == 842094158 )
  {
    v25 = ippiYCbCr420_8u_P3P2R(
            &v49,
            &v46,
            a4,
            (unsigned int)biWidth,
            &a4[biWidth * biHeight],
            biWidth,
            __PAIR64__(v22, v21));
LABEL_25:
    if ( !v25 )
      goto LABEL_26;
    return 4294967196LL;
  }
  if ( a2->biCompression == 842094169 )
  {
    if ( (unsigned int)ippiCopy_8u_C1R(v24, (unsigned int)v20, a4, (unsigned int)biWidth, __PAIR64__(v22, v21)) )
      return 4294967196LL;
    v30 = biWidth * biHeight;
    LODWORD(v44) = v52 / 2;
    HIDWORD(v44) = v53 / 2;
    if ( (unsigned int)ippiCopy_8u_C1R(v50, v47, &a4[5 * v30 / 4], (unsigned int)(biWidth / 2), v44) )
      return 4294967196LL;
    v25 = ippiCopy_8u_C1R(v51, v48, &a4[v30], (unsigned int)(biWidth / 2), v44);
    goto LABEL_25;
  }
  if ( a3 )
    return 4294967196LL;
  result = g_ConfigureDstBMP(
             (CVideoObjectDecoder *)((char *)this + 2336),
             a2,
             a4,
             a5,
             v39,
             a7,
             a8,
             v21,
             v22,
             v40,
             v41,
             v42);
  if ( (_DWORD)result )
    return result;
  v33 = &a4[*((int *)this + 616)];
  *((_DWORD *)this + 599) = 1;
  v34 = *((_DWORD *)this + 597) == 0;
  *((_QWORD *)this + 952) = v33;
  if ( v34 )
    CVideoObjectDecoder::RenderFrame_Planar(this, v17, v18, v19);
  else
    (*((void (__fastcall **)(CVideoObjectDecoder *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *))this + 965))(
      this,
      v17,
      v18,
      v19);
LABEL_26:
  if ( g_petwPro )
    ETWWrite(this, MP4SDECD_ColorConversion_Notification_Stop, 0, 0);
  v26 = *((_DWORD *)this + 29);
  for ( i = 1; i < v26; v26 = *((_DWORD *)this + 29) )
  {
    v35 = i++;
    v36 = 5 * v35;
    v37 = *(_OWORD *)((char *)this + 40 * v35 + 136);
    *(_OWORD *)((char *)this + 8 * v36 + 80) = *(_OWORD *)((char *)this + 40 * v35 + 120);
    v38 = *((_QWORD *)this + 5 * v35 + 19);
    *(_OWORD *)((char *)this + 8 * v36 + 96) = v37;
    *((_QWORD *)this + v36 + 14) = v38;
  }
  v28 = v26 - 1;
  *((_DWORD *)this + 29) = v28;
  return v28 > 0;
}

```

## disassembly

```asm
0x180012114  push    rbp
0x180012116  push    rbx
0x180012117  push    rsi
0x180012118  push    rdi
0x180012119  push    r12
0x18001211b  push    r13
0x18001211d  push    r14
0x18001211f  push    r15
0x180012121  lea     rbp, [rsp-7]
0x180012126  sub     rsp, 0B8h
0x18001212d  mov     rax, cs:__security_cookie
0x180012134  xor     rax, rsp
0x180012137  mov     [rbp+3Fh+var_50], rax
0x18001213b  mov     [rbp+3Fh+var_88], rdx
0x18001213f  mov     r14, r9
0x180012142  mov     r9, [rbp+3Fh+arg_58]
0x180012149  mov     rax, rdx
0x18001214c  mov     rdx, [rbp+3Fh+arg_50]
0x180012153  mov     rdi, rcx
0x180012156  mov     dword ptr [rbp+3Fh+var_90], r8d
0x18001215a  test    r8d, r8d
0x18001215d  jg      loc_180012338
0x180012163  mov     r13d, [rax+4]
0x180012167  mov     esi, [rax+8]
0x18001216a  neg     esi
0x18001216c  cmovs   esi, [rax+8]
0x180012170  cmp     dword ptr [rcx+74h], 0
0x180012174  jz      loc_1800123F8
0x18001217a  mov     rax, [rcx+90h]
0x180012181  mov     [rdx], rax
0x180012184  mov     rax, [rcx+98h]
0x18001218b  mov     [r9], rax
0x18001218e  test    r14, r14
0x180012191  jz      loc_1800122DE
0x180012197  cmp     dword ptr [rcx+1980h], 0
0x18001219e  jnz     short loc_1800121BF
0x1800121a0  cmp     dword ptr [rcx+19A0h], 32h ; '2'
0x1800121a7  jb      short loc_1800121BF
0x1800121a9  cmp     dword ptr [rcx+1998h], 0
0x1800121b0  jz      short loc_1800121BF
0x1800121b2  cmp     dword ptr [rcx+199Ch], 0
0x1800121b9  jnz     loc_180012468
0x1800121bf  mov     rbx, [rcx+78h]
0x1800121c3  mov     r15, [rcx+80h]
0x1800121ca  mov     r12, [rcx+88h]
0x1800121d1  test    rbx, rbx
0x1800121d4  jz      loc_180012340
0x1800121da  test    r15, r15
0x1800121dd  jz      loc_180012340
0x1800121e3  test    r12, r12
0x1800121e6  jz      loc_180012340
0x1800121ec  cmp     dword ptr [rdi+564h], 0
0x1800121f3  jz      loc_180012340
0x1800121f9  cmp     dword ptr [rdi+568h], 0
0x180012200  jz      loc_180012340
0x180012206  cmp     cs:g_petwPro, 0
0x18001220e  jz      short loc_180012222
0x180012210  xor     r9d, r9d
0x180012213  lea     rdx, MP4SDECD_ColorConversion_Notification_Start
0x18001221a  xor     r8d, r8d
0x18001221d  call    ETWWrite
0x180012222  mov     eax, [rdi+538h]
0x180012228  mov     r11d, [rdi+534h]
0x18001222f  mov     edx, [rbp+3Fh+arg_40]
0x180012235  mov     r8d, [rbp+3Fh+arg_48]
0x18001223c  movsxd  rcx, dword ptr [rdi+568h]
0x180012243  mov     r10, [rbp+3Fh+var_88]
0x180012247  mov     [rbp+3Fh+var_74], eax
0x18001224a  mov     [rbp+3Fh+var_70], eax
0x18001224d  movsxd  rax, dword ptr [rdi+564h]
0x180012254  add     rax, rbx
0x180012257  mov     [rbp+3Fh+var_78], r11d
0x18001225b  mov     [rbp+3Fh+var_80], rax
0x18001225f  cmp     edx, r11d
0x180012262  mov     [rbp+3Fh+var_68], rax
0x180012266  lea     rax, [rcx+r15]
0x18001226a  cmovg   edx, r11d
0x18001226e  mov     [rbp+3Fh+var_60], rax
0x180012272  lea     rax, [rcx+r12]
0x180012276  mov     [rbp+3Fh+arg_40], edx
0x18001227c  mov     [rbp+3Fh+var_58], rax
0x180012280  mov     eax, [rdi+53Ch]
0x180012286  cmp     r8d, eax
0x180012289  cmovg   r8d, eax
0x18001228d  cmp     dword ptr [r10+10h], 3231564Eh
0x180012295  mov     [rbp+3Fh+arg_48], r8d
0x18001229c  jnz     loc_180012347
0x1800122a2  mov     dword ptr [rbp+3Fh+var_90], edx
0x1800122a5  mov     r9d, r13d
0x1800122a8  mov     dword ptr [rbp+3Fh+var_90+4], r8d
0x1800122ac  lea     rdx, [rbp+3Fh+var_78]
0x1800122b0  mov     rax, [rbp+3Fh+var_90]
0x1800122b4  mov     r8, r14
0x1800122b7  mov     qword ptr [rsp+0F0h+var_C0], rax
0x1800122bc  imul    esi, r13d
0x1800122c0  mov     [rsp+0F0h+var_C8], r13d
0x1800122c5  movsxd  rcx, esi
0x1800122c8  add     rcx, r14
0x1800122cb  mov     [rsp+0F0h+var_D0], rcx
0x1800122d0  lea     rcx, [rbp+3Fh+var_68]
0x1800122d4  call    cs:__imp_ippiYCbCr420_8u_P3P2R
0x1800122da  test    eax, eax
0x1800122dc  jnz     short loc_180012340
0x1800122de  cmp     cs:g_petwPro, 0
0x1800122e6  jz      short loc_1800122FA
0x1800122e8  xor     r9d, r9d
0x1800122eb  lea     rdx, MP4SDECD_ColorConversion_Notification_Stop
0x1800122f2  xor     r8d, r8d
0x1800122f5  call    ETWWrite
0x1800122fa  mov     ecx, [rdi+74h]
0x1800122fd  mov     r8d, 1
0x180012303  cmp     ecx, r8d
0x180012306  jg      loc_18001252D
0x18001230c  dec     ecx
0x18001230e  xor     eax, eax
0x180012310  test    ecx, ecx
0x180012312  mov     [rdi+74h], ecx
0x180012315  setnle  al
0x180012318  mov     rcx, [rbp+3Fh+var_50]
0x18001231c  xor     rcx, rsp; StackCookie
0x18001231f  call    __security_check_cookie
0x180012324  add     rsp, 0B8h
0x18001232b  pop     r15
0x18001232d  pop     r14
0x18001232f  pop     r13
0x180012331  pop     r12
0x180012333  pop     rdi
0x180012334  pop     rsi
0x180012335  pop     rbx
0x180012336  pop     rbp
0x180012337  retn
0x180012338  mov     r13d, r8d
0x18001233b  jmp     loc_180012167
0x180012340  mov     eax, 0FFFFFF9Ch
0x180012345  jmp     short loc_180012318
0x180012347  cmp     dword ptr [r10+10h], 32315659h
0x18001234f  jnz     loc_1800124A0
0x180012355  mov     rcx, [rbp+3Fh+var_80]
0x180012359  mov     r9d, r13d
0x18001235c  mov     dword ptr [rbp+3Fh+var_90], edx
0x18001235f  mov     edx, r11d
0x180012362  mov     dword ptr [rbp+3Fh+var_90+4], r8d
0x180012366  mov     r8, r14
0x180012369  mov     rax, [rbp+3Fh+var_90]
0x18001236d  mov     [rsp+0F0h+var_D0], rax
0x180012372  call    cs:__imp_ippiCopy_8u_C1R
0x180012378  test    eax, eax
0x18001237a  jnz     short loc_180012340
0x18001237c  mov     ecx, 2
0x180012381  imul    esi, r13d
0x180012385  mov     eax, r13d
0x180012388  cdq
0x180012389  idiv    ecx
0x18001238b  mov     r15d, eax
0x18001238e  mov     eax, [rbp+3Fh+arg_40]
0x180012394  cdq
0x180012395  mov     r9d, r15d
0x180012398  idiv    ecx
0x18001239a  mov     dword ptr [rbp+3Fh+var_90], eax
0x18001239d  mov     eax, [rbp+3Fh+arg_48]
0x1800123a3  cdq
0x1800123a4  idiv    ecx
0x1800123a6  mov     ecx, 4
0x1800123ab  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x1800123ae  lea     eax, [rsi+rsi*4]
0x1800123b1  mov     rbx, [rbp+3Fh+var_90]
0x1800123b5  cdq
0x1800123b6  idiv    ecx
0x1800123b8  mov     edx, [rbp+3Fh+var_74]
0x1800123bb  mov     rcx, [rbp+3Fh+var_60]
0x1800123bf  movsxd  r8, eax
0x1800123c2  add     r8, r14
0x1800123c5  mov     [rsp+0F0h+var_D0], rbx
0x1800123ca  call    cs:__imp_ippiCopy_8u_C1R
0x1800123d0  test    eax, eax
0x1800123d2  jnz     loc_180012340
0x1800123d8  mov     edx, [rbp+3Fh+var_70]
0x1800123db  mov     r9d, r15d
0x1800123de  mov     rcx, [rbp+3Fh+var_58]
0x1800123e2  movsxd  r8, esi
0x1800123e5  add     r8, r14
0x1800123e8  mov     [rsp+0F0h+var_D0], rbx
0x1800123ed  call    cs:__imp_ippiCopy_8u_C1R
0x1800123f3  jmp     loc_1800122DA
0x1800123f8  cmp     [rbp+3Fh+arg_60], 0
0x1800123ff  jz      short loc_18001245E
0x180012401  cmp     dword ptr [rcx+6Ch], 0
0x180012405  jz      short loc_18001245E
0x180012407  mov     rax, [rcx+4C8h]
0x18001240e  mov     dword ptr [rcx+74h], 1
0x180012415  mov     [rcx+78h], rax
0x180012419  mov     rax, [rcx+4D0h]
0x180012420  mov     [rcx+80h], rax
0x180012427  mov     rax, [rcx+4D8h]
0x18001242e  mov     [rcx+88h], rax
0x180012435  mov     rax, [rcx+100h]
0x18001243c  mov     [rcx+90h], rax
0x180012443  mov     rax, [rcx+110h]
0x18001244a  mov     [rcx+98h], rax
0x180012451  mov     qword ptr [rcx+6Ch], 0
0x180012459  jmp     loc_18001217A
0x18001245e  mov     eax, 0FFFFFFFAh
0x180012463  jmp     loc_180012318
0x180012468  cmp     dword ptr [rcx+198Ch], 3
0x18001246f  jge     loc_1800121BF
0x180012475  lea     rdx, [rcx+78h]; struct OutputFrame *
0x180012479  call    ?CopyToPostProc@CVideoObjectDecoder@@AEAAXPEAUOutputFrame@@@Z; CVideoObjectDecoder::CopyToPostProc(OutputFrame *)
0x18001247e  mov     rbx, [rdi+14F0h]
0x180012485  mov     rcx, rdi; this
0x180012488  mov     r15, [rdi+14F8h]
0x18001248f  mov     r12, [rdi+1500h]
0x180012496  call    ?DeblockFrame@CVideoObjectDecoder@@AEAAXPEAUOutputFrame@@@Z; CVideoObjectDecoder::DeblockFrame(OutputFrame *)
0x18001249b  jmp     loc_1800121D1
0x1800124a0  cmp     dword ptr [rbp+3Fh+var_90], 0
0x1800124a4  jnz     loc_180012340
0x1800124aa  mov     eax, [rbp+3Fh+arg_38]
0x1800124b0  lea     rcx, [rdi+920h]; struct CDeColorConvParams *
0x1800124b7  mov     r9d, [rbp+3Fh+arg_20]; int
0x1800124bb  mov     [rsp+0F0h+var_B0], r8d; int
0x1800124c0  mov     r8, r14; void *
0x1800124c3  mov     [rsp+0F0h+var_B8], edx; int
0x1800124c7  mov     rdx, r10; struct tagBITMAPINFOHEADER *
0x1800124ca  mov     [rsp+0F0h+var_C0], eax; int
0x1800124ce  mov     eax, [rbp+3Fh+arg_30]
0x1800124d1  mov     [rsp+0F0h+var_C8], eax; int
0x1800124d5  call    ?g_ConfigureDstBMP@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@PEAXJJJJJJKKK@Z; g_ConfigureDstBMP(CDeColorConvParams *,tagBITMAPINFOHEADER *,void *,long,long,long,long,long,long,ulong,ulong,ulong)
0x1800124da  test    eax, eax
0x1800124dc  jnz     loc_180012318
0x1800124e2  movsxd  rax, dword ptr [rdi+9A0h]
0x1800124e9  mov     r9, r12; unsigned __int8 *
0x1800124ec  add     rax, r14
0x1800124ef  mov     dword ptr [rdi+95Ch], 1
0x1800124f9  cmp     dword ptr [rdi+954h], 0
0x180012500  mov     r8, r15; unsigned __int8 *
0x180012503  mov     [rdi+1DC0h], rax
0x18001250a  mov     rdx, rbx; unsigned __int8 *
0x18001250d  mov     rcx, rdi; this
0x180012510  jz      short loc_180012523
0x180012512  mov     rax, [rdi+1E28h]
0x180012519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001251e  jmp     loc_1800122DE
0x180012523  call    ?RenderFrame_Planar@CVideoObjectDecoder@@AEAAXPEAE00@Z; CVideoObjectDecoder::RenderFrame_Planar(uchar *,uchar *,uchar *)
0x180012528  jmp     loc_1800122DE
0x18001252d  movsxd  rax, r8d
0x180012530  inc     r8d
0x180012533  lea     rcx, [rax+rax*4]
0x180012537  lea     rdx, [rax+rax*4]
0x18001253b  movups  xmm0, xmmword ptr [rdi+rdx*8+78h]
0x180012540  movups  xmm1, xmmword ptr [rdi+rdx*8+88h]
0x180012548  movups  xmmword ptr [rdi+rcx*8+50h], xmm0
0x18001254d  movsd   xmm0, qword ptr [rdi+rdx*8+98h]
0x180012556  movups  xmmword ptr [rdi+rcx*8+60h], xmm1
0x18001255b  movsd   qword ptr [rdi+rcx*8+70h], xmm0
0x180012561  mov     ecx, [rdi+74h]
0x180012564  cmp     r8d, ecx
0x180012567  jl      short loc_18001252D
0x180012569  jmp     loc_18001230C
```
