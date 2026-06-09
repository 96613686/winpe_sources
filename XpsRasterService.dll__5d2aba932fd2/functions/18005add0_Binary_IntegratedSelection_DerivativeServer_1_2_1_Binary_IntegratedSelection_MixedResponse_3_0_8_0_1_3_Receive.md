# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005add0`
- end: `0x18005b3ef`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$00$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$00@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1567`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, __int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa40`

## callees

- `0x180003180`
- `0x18005add0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int128 v4; // xmm0
  __int64 v6; // r13
  unsigned __int8 *v7; // rbx
  __int64 v8; // rsi
  bool v9; // al
  unsigned __int8 *v10; // r15
  unsigned __int8 *v11; // rbx
  bool v12; // di
  bool v13; // di
  unsigned __int8 *v14; // r14
  bool result; // al
  int v16; // ecx
  unsigned __int8 *v17; // r15
  int v18; // r12d
  int v19; // r11d
  int v20; // edx
  int v21; // edi
  int v22; // ecx
  __int64 v23; // r14
  int v24; // edx
  int v25; // esi
  int v26; // r10d
  __int64 v27; // r8
  int v28; // r10d
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned __int8 *v32; // r11
  int v33; // esi
  unsigned __int8 *v34; // r10
  _WORD *v35; // r9
  int v36; // esi
  _WORD *v37; // r9
  __int64 i; // r8
  unsigned int v39; // ecx
  int v40; // eax
  int v41; // r13d
  __int64 v42; // r15
  __int64 v43; // rsi
  unsigned __int8 *v44; // rax
  unsigned __int8 *v45; // rcx
  unsigned __int8 *v46; // r12
  unsigned __int8 *v47; // r14
  unsigned __int8 *v48; // r13
  unsigned int v49; // edx
  unsigned __int8 *v50; // r8
  unsigned __int8 *v51; // rdi
  unsigned int v52; // edx
  unsigned __int8 *v53; // r8
  unsigned int v54; // edx
  unsigned int v55; // edx
  unsigned int v56; // edx
  unsigned int v57; // edx
  unsigned int v58; // edx
  unsigned int v59; // edx
  int v60; // ecx
  __int64 v61; // r10
  unsigned __int8 *v62; // rdx
  __int64 v63; // r14
  __int64 v64; // r8
  unsigned int v65; // ecx
  int v66; // ecx
  int v67; // [rsp+30h] [rbp-D0h]
  __int128 v68; // [rsp+38h] [rbp-C8h]
  unsigned __int8 *v69; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v70; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v71; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v72; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v73; // [rsp+78h] [rbp-88h]
  __int128 v74; // [rsp+80h] [rbp-80h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h]
  int *v76; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v77; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v78; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v79[2]; // [rsp+B0h] [rbp-50h]
  __int128 v80; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v81; // [rsp+C8h] [rbp-38h]
  int v82; // [rsp+D0h] [rbp-30h] BYREF
  int v83; // [rsp+D4h] [rbp-2Ch]
  __int64 v84; // [rsp+D8h] [rbp-28h]
  _BYTE v85[32]; // [rsp+E0h] [rbp-20h] BYREF
  int v86; // [rsp+100h] [rbp+0h]
  int v87; // [rsp+104h] [rbp+4h]
  int v88; // [rsp+108h] [rbp+8h]
  _DWORD v89[374]; // [rsp+10Ch] [rbp+Ch]
  int v90; // [rsp+6E4h] [rbp+5E4h]
  int v91; // [rsp+6ECh] [rbp+5ECh]
  int v92; // [rsp+6FCh] [rbp+5FCh]

  v4 = *a4;
  v76 = a3;
  v75 = a1;
  v6 = a1;
  v74 = v4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v82, 2, 1, (_DWORD)a3, (__int64)&v74, a1 + 8);
  v7 = *a2;
  v8 = v84;
  v9 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v85,
         *a2,
         &v78,
         &v77);
  v10 = a2[1];
  v11 = &v7[v8];
  *(_QWORD *)&v68 = v11;
  v12 = v9;
  v13 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v85,
          v10,
          &v78,
          &v77)
     && v12;
  v14 = a2[2];
  *((_QWORD *)&v68 + 1) = &v10[v8];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v85,
             v14,
             &v78,
             &v77);
  if ( result && v13 )
  {
    v16 = v82;
    result = 0;
    v17 = 0;
    v77 = 0;
    v18 = 0;
    v79[0] = 2;
    v67 = 0;
    if ( v82 > 0 )
    {
      v69 = &v14[v8];
      v19 = v88;
      v20 = v86;
      v21 = v83;
      do
      {
        v86 = ++v20;
        if ( v20 == 1 )
        {
          v22 = *(_DWORD *)(v6 + 44);
          v23 = (__int64)&v17[(_QWORD)v11];
          v24 = *(_DWORD *)(v6 + 40);
          v25 = 0;
          v26 = *(_DWORD *)(v6 + 28);
          v27 = *(int *)(v6 + 52);
          if ( v87 <= 0 )
            v25 = v87;
          v81 = v69;
          v80 = v68;
          if ( v26 < v22 )
            v26 = v22;
          *(_QWORD *)&v74 = &v17[(_QWORD)v11];
          v28 = v26 - v22;
          v29 = v27 - 1;
          if ( v19 < v24 )
            v19 = v24;
          v30 = v27 * ((v19 - v24) % *(_DWORD *)(v6 + 48));
          v31 = v92;
          if ( v28 <= v29 )
            v29 = v28;
          v32 = &v17[*((_QWORD *)&v80 + 1)];
          v33 = -v25;
          v34 = &v81[(_QWORD)v17];
          v35 = (_WORD *)(*(_QWORD *)(v6 + 56) + 2 * v30 + 2LL * v29);
          *v35 = (85
                * (v17[*((_QWORD *)&v80 + 1) + v33]
                 + v81[(_QWORD)v17 + v33]
                 + (unsigned int)*(unsigned __int8 *)(v33 + v23))) >> 6;
          v36 = v79[v31] + v33;
          v37 = v35 + 1;
          for ( i = (int)v31 + 1; i < 1; v36 += v40 )
          {
            if ( v36 >= v21 )
              break;
            v39 = v34[v36] + v32[v36] + *(unsigned __int8 *)(v23 + v36);
            if ( v39 > 0x2F4 )
              v39 = v34[v36 - 1] + v32[v36 - 1] + *(unsigned __int8 *)(v23 + v36 - 1);
            *v37++ = (85 * v39) >> 6;
            v40 = v79[i++];
          }
          v21 = v83;
          v41 = v36 - 1;
          v42 = v83 - 15;
          if ( v36 - 1 < v42 )
          {
            v43 = -v23;
            v44 = (unsigned __int8 *)(v23 + v41 + 3LL);
            v45 = &v11[-v23];
            v46 = &v11[(_QWORD)v77 - v23];
            v71 = &v11[(_QWORD)(v77 - 1) - v23];
            v72 = &v11[(_QWORD)(v77 + 1) - v23];
            v70 = &v11[(_QWORD)(v77 + 5) - v23];
            v47 = &v11[(_QWORD)(v77 + 7) - v23];
            v73 = &v45[(_QWORD)(v77 + 11)];
            LODWORD(v78) = ((v42 - v41 - 1) & 0xFFFFFFF0) + 16 + v41;
            v48 = &v77[(_QWORD)v45 + 9];
            do
            {
              v49 = *(v44 - 2) + v44[v43 - 2 + (_QWORD)v34] + v44[v43 - 2 + (_QWORD)v32];
              if ( v49 <= 0x2F4 )
              {
                v50 = &v44[v43 - 3];
              }
              else
              {
                v50 = &v44[v43 - 3];
                v49 = *(v44 - 3) + v50[(_QWORD)v34] + v50[(_QWORD)v32];
              }
              v51 = &v50[(_QWORD)v34];
              *v37 = (85 * v49) >> 6;
              v52 = *v44 + v44[v43 + (_QWORD)v34] + v44[v43 + (_QWORD)v32];
              if ( v52 > 0x2F4 )
                v52 = v51[2] + v50[(_QWORD)v32 + 2] + v44[(_QWORD)v71];
              v53 = &v50[(_QWORD)v32];
              v37[1] = (85 * v52) >> 6;
              v54 = v44[2] + v44[v43 + 2 + (_QWORD)v34] + v44[v43 + 2 + (_QWORD)v32];
              if ( v54 > 0x2F4 )
                v54 = v53[4] + v51[4] + v44[(_QWORD)v72];
              v37[2] = (85 * v54) >> 6;
              v55 = v44[4] + v44[v43 + 4 + (_QWORD)v34] + v44[v43 + 4 + (_QWORD)v32];
              if ( v55 > 0x2F4 )
                v55 = v51[6] + v53[6] + v44[(_QWORD)v46 + 3];
              v37[3] = (85 * v55) >> 6;
              v56 = v44[6] + v44[v43 + 6 + (_QWORD)v34] + v44[v43 + 6 + (_QWORD)v32];
              if ( v56 > 0x2F4 )
                v56 = v51[8] + v53[8] + v44[(_QWORD)v70];
              v37[4] = (85 * v56) >> 6;
              v57 = v44[8] + v44[v43 + 8 + (_QWORD)v34] + v44[v43 + 8 + (_QWORD)v32];
              if ( v57 > 0x2F4 )
                v57 = v51[10] + v53[10] + v44[(_QWORD)v47];
              v37[5] = (85 * v57) >> 6;
              v58 = v44[10] + v44[v43 + 10 + (_QWORD)v34] + v44[v43 + 10 + (_QWORD)v32];
              if ( v58 > 0x2F4 )
                v58 = v51[12] + v53[12] + v48[(_QWORD)v44];
              v37[6] = (85 * v58) >> 6;
              v59 = v44[12] + v44[v43 + 12 + (_QWORD)v34] + v44[v43 + 12 + (_QWORD)v32];
              if ( v59 > 0x2F4 )
                v59 = v51[14] + v53[14] + v44[(_QWORD)v73];
              v44 += 16;
              v37[7] = (85 * v59) >> 6;
              v37 += 8;
            }
            while ( (__int64)&v44[v43 - 3] < v42 );
            v21 = v83;
            v11 = (unsigned __int8 *)v68;
            v23 = v74;
            v41 = (int)v78;
            v18 = v67;
          }
          v60 = v41 + 1;
          if ( v41 + 1 < v21 )
          {
            v61 = v34 - v32;
            v62 = &v32[v60 - 1];
            v63 = v23 - (_QWORD)v32;
            v64 = ((unsigned int)(v21 - v60 - 1) >> 1) + 1;
            do
            {
              v65 = v62[1] + v62[v61 + 1] + v62[v63 + 1];
              if ( v65 > 0x2F4 )
                v65 = *v62 + v62[v61] + v62[v63];
              v62 += 2;
              *v37++ = (85 * v65) >> 6;
              --v64;
            }
            while ( v64 );
            v21 = v83;
          }
          v17 = v77;
          v20 = v86 - v89[v90];
          v66 = v90 + 1;
          v6 = v75;
          if ( v90 + 1 >= v91 )
            v66 = 0;
          v19 = v88 + 1;
          v90 = v66;
          v16 = v82;
          ++v88;
        }
        v67 = ++v18;
        v17 += *v76;
        result = 0;
        v77 = v17;
      }
      while ( v18 < v16 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005add0  push    rbp
0x18005add2  push    rbx
0x18005add3  push    rsi
0x18005add4  push    rdi
0x18005add5  push    r13
0x18005add7  push    r14
0x18005add9  push    r15
0x18005addb  lea     rbp, [rsp-620h]
0x18005ade3  sub     rsp, 720h
0x18005adea  mov     rax, cs:__security_cookie
0x18005adf1  xor     rax, rsp
0x18005adf4  mov     [rbp+650h+var_50], rax
0x18005adfb  movups  xmm0, xmmword ptr [r9]
0x18005adff  lea     rax, [rcx+8]
0x18005ae03  mov     [rbp+650h+var_6B8], r8
0x18005ae07  mov     [rsp+750h+var_728], rax
0x18005ae0c  mov     r14, rdx
0x18005ae0f  mov     edx, 2
0x18005ae14  mov     [rbp+650h+var_6C0], rcx
0x18005ae18  mov     r13, rcx
0x18005ae1b  movaps  [rbp+650h+var_6D0], xmm0
0x18005ae1f  lea     rax, [rbp+650h+var_6D0]
0x18005ae23  mov     r9, r8
0x18005ae26  lea     rcx, [rbp+650h+var_680]
0x18005ae2a  mov     [rsp+750h+var_730], rax
0x18005ae2f  lea     r8d, [rdx-1]
0x18005ae33  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005ae38  mov     rbx, [r14]
0x18005ae3b  lea     r9, [rbp+650h+var_6B0]; unsigned __int8 **
0x18005ae3f  mov     rsi, [rbp+650h+var_678]
0x18005ae43  lea     r8, [rbp+650h+var_6A8]; unsigned __int8 **
0x18005ae47  mov     rdx, rbx; unsigned __int8 *
0x18005ae4a  lea     rcx, [rbp+650h+var_670]; this
0x18005ae4e  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005ae53  mov     r15, [r14+8]
0x18005ae57  lea     r9, [rbp+650h+var_6B0]; unsigned __int8 **
0x18005ae5b  add     rbx, rsi
0x18005ae5e  lea     r8, [rbp+650h+var_6A8]; unsigned __int8 **
0x18005ae62  mov     rdx, r15; unsigned __int8 *
0x18005ae65  mov     qword ptr [rsp+750h+var_718], rbx
0x18005ae6a  lea     rcx, [rbp+650h+var_670]; this
0x18005ae6e  movzx   edi, al
0x18005ae71  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005ae76  test    al, al
0x18005ae78  jz      short loc_18005AE84
0x18005ae7a  test    dil, dil
0x18005ae7d  jz      short loc_18005AE84
0x18005ae7f  mov     dil, 1
0x18005ae82  jmp     short loc_18005AE87
0x18005ae84  xor     dil, dil
0x18005ae87  mov     r14, [r14+10h]
0x18005ae8b  lea     rax, [r15+rsi]
0x18005ae8f  mov     rdx, r14; unsigned __int8 *
0x18005ae92  mov     qword ptr [rsp+750h+var_718+8], rax
0x18005ae97  lea     r9, [rbp+650h+var_6B0]; unsigned __int8 **
0x18005ae9b  lea     r8, [rbp+650h+var_6A8]; unsigned __int8 **
0x18005ae9f  lea     rcx, [rbp+650h+var_670]; this
0x18005aea3  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005aea8  test    al, al
0x18005aeaa  jz      loc_18005B3CE
0x18005aeb0  test    dil, dil
0x18005aeb3  jz      loc_18005B3CE
0x18005aeb9  mov     ecx, [rbp+650h+var_680]
0x18005aebc  lea     rax, [r14+rsi]
0x18005aec0  mov     [rsp+750h+var_708], rax
0x18005aec5  xor     eax, eax
0x18005aec7  mov     [rsp+750h+var_38], r12
0x18005aecf  mov     r15d, eax
0x18005aed2  mov     [rbp+650h+var_6B0], rax
0x18005aed6  mov     r12d, eax
0x18005aed9  mov     [rbp+650h+var_6A0], 2
0x18005aee0  mov     [rsp+750h+var_720], eax
0x18005aee4  test    ecx, ecx
0x18005aee6  jle     loc_18005B3C6
0x18005aeec  movsd   xmm0, [rsp+750h+var_708]
0x18005aef2  movups  xmm1, [rsp+750h+var_718]
0x18005aef7  mov     r11d, [rbp+650h+var_648]
0x18005aefb  mov     edx, [rbp+650h+var_650]
0x18005aefe  mov     edi, [rbp+650h+var_67C]
0x18005af01  inc     edx
0x18005af03  mov     [rbp+650h+var_650], edx
0x18005af06  cmp     edx, 1
0x18005af09  jnz     loc_18005B3A2
0x18005af0f  mov     ecx, [r13+2Ch]
0x18005af13  lea     r14, [rbx+r15]
0x18005af17  mov     edx, [r13+28h]
0x18005af1b  mov     esi, eax
0x18005af1d  mov     eax, [rbp+650h+var_64C]
0x18005af20  test    eax, eax
0x18005af22  mov     r10d, [r13+1Ch]
0x18005af26  movsxd  r8, dword ptr [r13+34h]
0x18005af2a  cmovle  esi, eax
0x18005af2d  cmp     r10d, ecx
0x18005af30  movsd   [rbp+650h+var_688], xmm0
0x18005af35  movups  [rbp+650h+var_698], xmm1
0x18005af39  cmovl   r10d, ecx
0x18005af3d  mov     qword ptr [rbp+650h+var_6D0], r14
0x18005af41  sub     r10d, ecx
0x18005af44  lea     r9d, [r8-1]
0x18005af48  cmp     r11d, edx
0x18005af4b  cmovl   r11d, edx
0x18005af4f  sub     r11d, edx
0x18005af52  mov     eax, r11d
0x18005af55  mov     r11, qword ptr [rbp+650h+var_698+8]
0x18005af59  cdq
0x18005af5a  idiv    dword ptr [r13+30h]
0x18005af5e  mov     rax, [r13+38h]
0x18005af62  movsxd  rcx, edx
0x18005af65  imul    rcx, r8
0x18005af69  movsxd  r8, [rbp+650h+var_54]
0x18005af70  cmp     r10d, r9d
0x18005af73  cmovle  r9d, r10d
0x18005af77  add     r11, r15
0x18005af7a  mov     r10, [rbp+650h+var_688]
0x18005af7e  neg     esi
0x18005af80  lea     rax, [rax+rcx*2]
0x18005af84  add     r10, r15
0x18005af87  movsxd  rcx, r9d
0x18005af8a  lea     r9, [rax+rcx*2]
0x18005af8e  movsxd  rcx, esi
0x18005af91  movzx   eax, byte ptr [rcx+r10]
0x18005af96  movzx   edx, byte ptr [rcx+r14]
0x18005af9b  add     edx, eax
0x18005af9d  movzx   eax, byte ptr [rcx+r11]
0x18005afa2  add     edx, eax
0x18005afa4  imul    eax, edx, 55h ; 'U'
0x18005afa7  shr     eax, 6
0x18005afaa  mov     [r9], ax
0x18005afae  lea     eax, [r8+1]
0x18005afb2  add     esi, [rbp+r8*4+650h+var_6A0]
0x18005afb7  add     r9, 2
0x18005afbb  movsxd  r8, eax
0x18005afbe  cmp     r8, 1
0x18005afc2  jge     short loc_18005B01A
0x18005afc4  cmp     esi, edi
0x18005afc6  jge     short loc_18005B01A
0x18005afc8  movsxd  rdx, esi
0x18005afcb  movzx   eax, byte ptr [r11+rdx]
0x18005afd0  movzx   ecx, byte ptr [r14+rdx]
0x18005afd5  add     ecx, eax
0x18005afd7  movzx   eax, byte ptr [r10+rdx]
0x18005afdc  add     ecx, eax
0x18005afde  cmp     ecx, 2F4h
0x18005afe4  jbe     short loc_18005AFFC
0x18005afe6  movzx   eax, byte ptr [r11+rdx-1]
0x18005afec  movzx   ecx, byte ptr [r14+rdx-1]
0x18005aff2  add     ecx, eax
0x18005aff4  movzx   eax, byte ptr [r10+rdx-1]
0x18005affa  add     ecx, eax
0x18005affc  imul    eax, ecx, 55h ; 'U'
0x18005afff  shr     eax, 6
0x18005b002  mov     [r9], ax
0x18005b006  add     r9, 2
0x18005b00a  mov     eax, [rbp+r8*4+650h+var_6A0]
0x18005b00f  inc     r8
0x18005b012  add     esi, eax
0x18005b014  cmp     r8, 1
0x18005b018  jl      short loc_18005AFC4
0x18005b01a  mov     edi, [rbp+650h+var_67C]
0x18005b01d  lea     r13d, [rsi-1]
0x18005b021  movsxd  rdx, r13d
0x18005b024  lea     eax, [rdi-0Fh]
0x18005b027  movsxd  r15, eax
0x18005b02a  cmp     rdx, r15
0x18005b02d  jge     loc_18005B2F5
0x18005b033  mov     rsi, r14
0x18005b036  lea     rax, [rdx+3]
0x18005b03a  neg     rsi
0x18005b03d  add     rax, r14
0x18005b040  lea     rcx, [rbx+rsi]
0x18005b044  mov     rbx, [rbp+650h+var_6B0]
0x18005b048  lea     r12, [rcx+rbx]
0x18005b04c  lea     r8, [rbx-1]
0x18005b050  add     r8, rcx
0x18005b053  mov     [rsp+750h+var_6E8], r8
0x18005b058  lea     r8, [rbx+1]
0x18005b05c  add     r8, rcx
0x18005b05f  mov     [rsp+750h+var_6E0], r8
0x18005b064  lea     r8, [rbx+5]
0x18005b068  add     r8, rcx
0x18005b06b  mov     [rsp+750h+var_700], r8
0x18005b070  lea     r8, [rbx+7]
0x18005b074  add     r8, rcx
0x18005b077  mov     [rsp+750h+var_6F8], r8
0x18005b07c  lea     r8, [rbx+9]
0x18005b080  mov     r14, [rsp+750h+var_6F8]
0x18005b085  add     r8, rcx
0x18005b088  add     rbx, 0Bh
0x18005b08c  add     rcx, rbx
0x18005b08f  mov     rbx, [rsp+750h+var_700]
0x18005b094  mov     [rsp+750h+var_6D8], rcx
0x18005b099  mov     rcx, r15
0x18005b09c  sub     rcx, rdx
0x18005b09f  dec     rcx
0x18005b0a2  and     ecx, 0FFFFFFF0h
0x18005b0a5  add     ecx, 10h
0x18005b0a8  add     r13d, ecx
0x18005b0ab  mov     dword ptr [rbp+650h+var_6A8], r13d
0x18005b0af  mov     r13, r8
0x18005b0b2  nop     dword ptr [rax+00h]
0x18005b0b6  nop     word ptr [rax+rax+00000000h]
0x18005b0c0  lea     rcx, [rsi+rax]
0x18005b0c4  movzx   edx, byte ptr [rcx+r11-2]
0x18005b0ca  movzx   ecx, byte ptr [rcx+r10-2]
0x18005b0d0  add     edx, ecx
0x18005b0d2  movzx   ecx, byte ptr [rax-2]
0x18005b0d6  add     edx, ecx
0x18005b0d8  cmp     edx, 2F4h
0x18005b0de  jbe     short loc_18005B0FB
0x18005b0e0  lea     r8, [rsi-3]
0x18005b0e4  add     r8, rax
0x18005b0e7  movzx   ecx, byte ptr [r10+r8]
0x18005b0ec  movzx   edx, byte ptr [r11+r8]
0x18005b0f1  add     edx, ecx
0x18005b0f3  movzx   ecx, byte ptr [rax-3]
0x18005b0f7  add     edx, ecx
0x18005b0f9  jmp     short loc_18005B102
0x18005b0fb  lea     r8, [rax-3]
0x18005b0ff  add     r8, rsi
0x18005b102  imul    ecx, edx, 55h ; 'U'
0x18005b105  lea     rdi, [r10+r8]
0x18005b109  shr     ecx, 6
0x18005b10c  mov     [r9], cx
0x18005b110  lea     rcx, [rax+rsi]
0x18005b114  movzx   edx, byte ptr [r11+rcx]
0x18005b119  movzx   ecx, byte ptr [r10+rcx]
0x18005b11e  add     edx, ecx
0x18005b120  movzx   ecx, byte ptr [rax]
0x18005b123  add     edx, ecx
0x18005b125  cmp     edx, 2F4h
0x18005b12b  jbe     short loc_18005B144
0x18005b12d  mov     rcx, [rsp+750h+var_6E8]
0x18005b132  movzx   edx, byte ptr [rcx+rax]
0x18005b136  movzx   ecx, byte ptr [r11+r8+2]
0x18005b13c  add     edx, ecx
0x18005b13e  movzx   ecx, byte ptr [rdi+2]
0x18005b142  add     edx, ecx
0x18005b144  imul    ecx, edx, 55h ; 'U'
0x18005b147  add     r8, r11
0x18005b14a  shr     ecx, 6
0x18005b14d  mov     [r9+2], cx
0x18005b152  lea     rcx, [rax+rsi]
0x18005b156  movzx   edx, byte ptr [r11+rcx+2]
0x18005b15c  movzx   ecx, byte ptr [r10+rcx+2]
0x18005b162  add     edx, ecx
0x18005b164  movzx   ecx, byte ptr [rax+2]
0x18005b168  add     edx, ecx
0x18005b16a  cmp     edx, 2F4h
0x18005b170  jbe     short loc_18005B188
0x18005b172  mov     rcx, [rsp+750h+var_6E0]
0x18005b177  movzx   edx, byte ptr [rcx+rax]
0x18005b17b  movzx   ecx, byte ptr [rdi+4]
0x18005b17f  add     edx, ecx
0x18005b181  movzx   ecx, byte ptr [r8+4]
0x18005b186  add     edx, ecx
0x18005b188  imul    ecx, edx, 55h ; 'U'
0x18005b18b  shr     ecx, 6
0x18005b18e  mov     [r9+4], cx
0x18005b193  lea     rcx, [rax+rsi]
0x18005b197  movzx   edx, byte ptr [r11+rcx+4]
0x18005b19d  movzx   ecx, byte ptr [r10+rcx+4]
0x18005b1a3  add     edx, ecx
0x18005b1a5  movzx   ecx, byte ptr [rax+4]
0x18005b1a9  add     edx, ecx
0x18005b1ab  cmp     edx, 2F4h
0x18005b1b1  jbe     short loc_18005B1C6
0x18005b1b3  movzx   ecx, byte ptr [r8+6]
0x18005b1b8  movzx   edx, byte ptr [r12+rax+3]
0x18005b1be  add     edx, ecx
0x18005b1c0  movzx   ecx, byte ptr [rdi+6]
0x18005b1c4  add     edx, ecx
0x18005b1c6  imul    ecx, edx, 55h ; 'U'
0x18005b1c9  shr     ecx, 6
0x18005b1cc  mov     [r9+6], cx
0x18005b1d1  lea     rcx, [rax+rsi]
0x18005b1d5  movzx   edx, byte ptr [r11+rcx+6]
0x18005b1db  movzx   ecx, byte ptr [r10+rcx+6]
0x18005b1e1  add     edx, ecx
0x18005b1e3  movzx   ecx, byte ptr [rax+6]
0x18005b1e7  add     edx, ecx
0x18005b1e9  cmp     edx, 2F4h
0x18005b1ef  jbe     short loc_18005B202
0x18005b1f1  movzx   ecx, byte ptr [r8+8]
0x18005b1f6  movzx   edx, byte ptr [rbx+rax]
0x18005b1fa  add     edx, ecx
0x18005b1fc  movzx   ecx, byte ptr [rdi+8]
0x18005b200  add     edx, ecx
0x18005b202  imul    ecx, edx, 55h ; 'U'
0x18005b205  shr     ecx, 6
0x18005b208  mov     [r9+8], cx
0x18005b20d  lea     rcx, [rax+rsi]
0x18005b211  movzx   edx, byte ptr [r11+rcx+8]
0x18005b217  movzx   ecx, byte ptr [r10+rcx+8]
0x18005b21d  add     edx, ecx
0x18005b21f  movzx   ecx, byte ptr [rax+8]
0x18005b223  add     edx, ecx
0x18005b225  cmp     edx, 2F4h
0x18005b22b  jbe     short loc_18005B23F
0x18005b22d  movzx   ecx, byte ptr [r8+0Ah]
0x18005b232  movzx   edx, byte ptr [r14+rax]
  ... truncated ...
```
