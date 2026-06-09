# Binary::IntegratedSelection::DerivativeServer<16,2,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180060920`
- end: `0x180061266`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$0BA@$01$00$00V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$0BA@$01$00V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `2374`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ab30`

## callees

- `0x180003180`
- `0x180060920`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Binary::IntegratedSelection::DerivativeServer<16,2,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r14
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  bool result; // al
  int v11; // ecx
  int v12; // r12d
  __int64 v13; // r13
  __int64 v14; // xmm5_8
  int v15; // edx
  __int128 v16; // xmm4
  int v17; // esi
  int v18; // edi
  int v19; // edx
  int v20; // r11d
  int v21; // ecx
  int v22; // r10d
  __int64 v23; // r8
  int v24; // r10d
  int v25; // r9d
  int v26; // eax
  unsigned __int8 *v27; // rsi
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r14
  __int64 v33; // r10
  __int64 v34; // rax
  __int64 v35; // r9
  _WORD *v36; // rdx
  __int64 v37; // r8
  int v38; // ecx
  __int64 v39; // r10
  int v40; // eax
  __int64 v41; // r10
  int v42; // eax
  __int64 v43; // r10
  int v44; // eax
  _WORD *v45; // r11
  __int64 v46; // r10
  int v47; // eax
  __int64 v48; // r10
  int v49; // eax
  int v50; // r15d
  float *v51; // rcx
  unsigned __int8 *v52; // r8
  __int64 v53; // r10
  __int64 v54; // r11
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // r8d
  float *v64; // rcx
  __int64 v65; // r8
  int v66; // eax
  int v67; // ecx
  unsigned __int8 *v70[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v71; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v72; // [rsp+58h] [rbp-A8h]
  __int64 v73; // [rsp+68h] [rbp-98h]
  __int64 v74; // [rsp+70h] [rbp-90h]
  int v75; // [rsp+80h] [rbp-80h] BYREF
  int v76; // [rsp+84h] [rbp-7Ch]
  __int64 v77; // [rsp+88h] [rbp-78h]
  char v78[32]; // [rsp+90h] [rbp-70h] BYREF
  int v79; // [rsp+B0h] [rbp-50h]
  int v80; // [rsp+B4h] [rbp-4Ch]
  int v81; // [rsp+B8h] [rbp-48h]
  _DWORD v82[374]; // [rsp+BCh] [rbp-44h]
  int v83; // [rsp+694h] [rbp+594h]
  int v84; // [rsp+69Ch] [rbp+59Ch]
  int v85; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v70 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v75, 2, 1, (_DWORD)a3, (__int64)v70, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v77];
  *(_QWORD *)&v72 = &v8[v77];
  *((_QWORD *)&v72 + 1) = &v8[v77 + 4];
  v73 = (__int64)&v8[v77 + 8];
  v74 = (__int64)&v8[v77 + 12];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v78,
             v8,
             &v71,
             v70);
  if ( result )
  {
    v11 = v75;
    result = 0;
    v12 = 0;
    v13 = 0;
    LODWORD(v70[0]) = 2;
    if ( v75 > 0 )
    {
      v14 = v73;
      v15 = v79;
      v16 = v72;
      v17 = v81;
      v18 = v76;
      do
      {
        v79 = ++v15;
        if ( v15 == 1 )
        {
          v19 = *(_DWORD *)(v5 + 40);
          v20 = 0;
          v21 = *(_DWORD *)(v5 + 44);
          v22 = *(_DWORD *)(v5 + 28);
          v23 = *(int *)(v5 + 52);
          if ( v80 <= 0 )
            v20 = v80;
          v72 = v16;
          if ( v22 < v21 )
            v22 = v21;
          v24 = v22 - v21;
          v25 = v23 - 1;
          if ( v17 < v19 )
            v17 = v19;
          v26 = v17 - v19;
          v27 = &v9[v13];
          v28 = v26 % *(_DWORD *)(v5 + 48);
          v29 = *(_QWORD *)(v5 + 56);
          v30 = v23 * v28;
          v31 = v85;
          if ( v24 <= v25 )
            v25 = v24;
          v32 = v13 + v14;
          v33 = v25;
          v34 = v29 + 2 * v30;
          v35 = v13 + *((_QWORD *)&v72 + 1);
          v36 = (_WORD *)(v34 + 2 * (v33 + 1));
          *(_WORD *)(v34 + 2 * v33) = (int)fmaxf(
                                             0.0,
                                             fminf(
                                               1023.0,
                                               (float)((float)(*(float *)&v27[-16 * v20]
                                                             + *(float *)(v13 + *((_QWORD *)&v72 + 1) + -16 * v20))
                                                     + *(float *)(-16 * v20 + v13 + v14))
                                             * 341.0));
          LODWORD(v33) = *((_DWORD *)v70 + v31) - v20;
          v37 = (int)v31 + 1;
          v38 = v33;
          if ( v37 < 1 )
          {
            if ( 1 - v37 < 4 )
            {
              do
              {
LABEL_35:
                if ( v38 >= v18 )
                  break;
                v48 = 16 * v38;
                v49 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)(v35 + v48) + *(float *)&v27[v48]) + *(float *)(v32 + v48))
                             * 341.0));
                if ( (unsigned __int16)v49 > 0x3ECu )
                  v49 = (int)fmaxf(
                               0.0,
                               fminf(
                                 1023.0,
                                 (float)((float)(*(float *)(v35 + v48 - 16) + *(float *)&v27[v48 - 16])
                                       + *(float *)(v32 + v48 - 16))
                               * 341.0));
                *v36++ = v49;
                v38 += *((_DWORD *)v70 + v37++);
              }
              while ( v37 < 1 );
            }
            else
            {
              while ( v38 < v18 )
              {
                v39 = 16 * v38;
                v40 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)(v35 + v39) + *(float *)&v27[v39]) + *(float *)(v32 + v39))
                             * 341.0));
                if ( (unsigned __int16)v40 > 0x3ECu )
                  v40 = (int)fmaxf(
                               0.0,
                               fminf(
                                 1023.0,
                                 (float)((float)(*(float *)(v35 + v39 - 16) + *(float *)&v27[v39 - 16])
                                       + *(float *)(v32 + v39 - 16))
                               * 341.0));
                *v36++ = v40;
                v38 += *((_DWORD *)v70 + v37);
                if ( v38 >= v18 )
                  break;
                v41 = 16 * v38;
                v42 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)(v35 + v41) + *(float *)&v27[v41]) + *(float *)(v32 + v41))
                             * 341.0));
                if ( (unsigned __int16)v42 > 0x3ECu )
                  v42 = (int)fmaxf(
                               0.0,
                               fminf(
                                 1023.0,
                                 (float)((float)(*(float *)(v35 + v41 - 16) + *(float *)&v27[v41 - 16])
                                       + *(float *)(v32 + v41 - 16))
                               * 341.0));
                *v36++ = v42;
                v38 += *((_DWORD *)v70 + v37 + 1);
                if ( v38 >= v18 )
                  break;
                v43 = 16 * v38;
                v44 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)(v35 + v43) + *(float *)&v27[v43]) + *(float *)(v32 + v43))
                             * 341.0));
                if ( (unsigned __int16)v44 > 0x3ECu )
                  v44 = (int)fmaxf(
                               0.0,
                               fminf(
                                 1023.0,
                                 (float)((float)(*(float *)(v35 + v43 - 16) + *(float *)&v27[v43 - 16])
                                       + *(float *)(v32 + v43 - 16))
                               * 341.0));
                *v36 = v44;
                v45 = v36 + 1;
                v38 += *((_DWORD *)&v70[1] + v37);
                ++v36;
                if ( v38 >= v18 )
                  break;
                v46 = 16 * v38;
                v47 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)(v35 + v46) + *(float *)&v27[v46]) + *(float *)(v32 + v46))
                             * 341.0));
                if ( (unsigned __int16)v47 > 0x3ECu )
                  v47 = (int)fmaxf(
                               0.0,
                               fminf(
                                 1023.0,
                                 (float)((float)(*(float *)(v35 + v46 - 16) + *(float *)&v27[v46 - 16])
                                       + *(float *)(v32 + v46 - 16))
                               * 341.0));
                *v45 = v47;
                v36 = v45 + 1;
                v38 += *((_DWORD *)&v70[1] + v37 + 1);
                v37 += 4;
                if ( v37 >= -2 )
                {
                  if ( v37 >= 1 )
                    break;
                  goto LABEL_35;
                }
              }
            }
          }
          v18 = v76;
          v50 = v38 - 1;
          if ( v38 - 1 < v76 - 15 )
          {
            v51 = (float *)(v35 + 16 * (v50 + 1LL));
            v52 = &v27[-v35];
            v53 = v32 - v35;
            v54 = ((unsigned int)(v76 - 15 - v50 - 1) >> 4) + 1;
            v50 += 16 * v54;
            do
            {
              v55 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51] + *v51) + *(float *)((char *)v51 + v53))
                           * 341.0));
              if ( (unsigned __int16)v55 > 0x3ECu )
                v55 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 - 16] + *(v51 - 4))
                                     + *(float *)((char *)v51 + v53 - 16))
                             * 341.0));
              *v36 = v55;
              v56 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 32] + v51[8])
                                   + *(float *)((char *)v51 + v53 + 32))
                           * 341.0));
              if ( (unsigned __int16)v56 > 0x3ECu )
                v56 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 16] + v51[4])
                                     + *(float *)((char *)v51 + v53 + 16))
                             * 341.0));
              v36[1] = v56;
              v57 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 64] + v51[16])
                                   + *(float *)((char *)v51 + v53 + 64))
                           * 341.0));
              if ( (unsigned __int16)v57 > 0x3ECu )
                v57 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 48] + v51[12])
                                     + *(float *)((char *)v51 + v53 + 48))
                             * 341.0));
              v36[2] = v57;
              v58 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 96] + v51[24])
                                   + *(float *)((char *)v51 + v53 + 96))
                           * 341.0));
              if ( (unsigned __int16)v58 > 0x3ECu )
                v58 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 80] + v51[20])
                                     + *(float *)((char *)v51 + v53 + 80))
                             * 341.0));
              v36[3] = v58;
              v59 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 128] + v51[32])
                                   + *(float *)((char *)v51 + v53 + 128))
                           * 341.0));
              if ( (unsigned __int16)v59 > 0x3ECu )
                v59 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 112] + v51[28])
                                     + *(float *)((char *)v51 + v53 + 112))
                             * 341.0));
              v36[4] = v59;
              v60 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 160] + v51[40])
                                   + *(float *)((char *)v51 + v53 + 160))
                           * 341.0));
              if ( (unsigned __int16)v60 > 0x3ECu )
                v60 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 144] + v51[36])
                                     + *(float *)((char *)v51 + v53 + 144))
                             * 341.0));
              v36[5] = v60;
              v61 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v52[(_QWORD)v51 + 192] + v51[48])
                                   + *(float *)((char *)v51 + v53 + 192))
                           * 341.0));
              if ( (unsigned __int16)v61 > 0x3ECu )
                v61 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)((char *)v51 + (_QWORD)v52 + 176) + v51[44])
                                     + *(float *)((char *)v51 + v53 + 176))
                             * 341.0));
              v36[6] = v61;
              v62 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)((char *)v51 + (_QWORD)v52 + 224) + v51[56])
                                   + *(float *)((char *)v51 + v53 + 224))
                           * 341.0));
              if ( (unsigned __int16)v62 > 0x3ECu )
                v62 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(float *)&v52[(_QWORD)v51 + 208] + v51[52])
                                     + *(float *)((char *)v51 + v53 + 208))
                             * 341.0));
              v36[7] = v62;
              v51 += 64;
              v36 += 8;
              --v54;
            }
            while ( v54 );
            v18 = v76;
          }
          v63 = v50 + 1;
          if ( v50 + 1 < v18 )
          {
            v64 = (float *)(v35 + 16 * v63);
            v65 = ((unsigned int)(v18 - v63 - 1) >> 1) + 1;
            do
            {
              v66 = (int)fmaxf(
                           0.0,
                           fminf(
                             1023.0,
                             (float)((float)(*(float *)&v27[(_QWORD)v64 - v35] + *v64)
                                   + *(float *)((char *)v64 + v32 - v35))
                           * 341.0));
              if ( (unsigned __int16)v66 > 0x3ECu )
                v66 = (int)fmaxf(
                             0.0,
                             fminf(
                               1023.0,
                               (float)((float)(*(v64 - 4) + *(float *)&v27[(_QWORD)v64 - v35 - 16])
                                     + *(float *)((char *)v64 + v32 - v35 - 16))
                             * 341.0));
              *v36 = v66;
              v64 += 8;
              ++v36;
              --v65;
            }
            while ( v65 );
            v18 = v76;
          }
          v5 = a1;
          v15 = v79 - v82[v83];
          v67 = v83 + 1;
          if ( v83 + 1 >= v84 )
            v67 = 0;
          v17 = v81 + 1;
          v83 = v67;
          v11 = v75;
          ++v81;
        }
        ++v12;
        v13 += *a3;
        result = 0;
      }
      while ( v12 < v11 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180060920  push    rbp
0x180060922  push    rbx
0x180060923  push    r14
0x180060925  lea     rbp, [rsp-5F0h]
0x18006092d  sub     rsp, 6F0h
0x180060934  mov     rax, cs:__security_cookie
0x18006093b  xor     rax, rsp
0x18006093e  mov     [rbp+600h+var_50], rax
0x180060945  movups  xmm0, xmmword ptr [r9]
0x180060949  lea     rax, [rcx+8]
0x18006094d  mov     [rsp+700h+var_6C8], r8
0x180060952  mov     [rsp+700h+var_6D8], rax
0x180060957  mov     rbx, rdx
0x18006095a  mov     edx, 2
0x18006095f  mov     [rsp+700h+var_6D0], rcx
0x180060964  mov     r14, rcx
0x180060967  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x18006096c  lea     rax, [rsp+700h+var_6C0]
0x180060971  mov     r9, r8
0x180060974  lea     rcx, [rbp+600h+var_680]
0x180060978  mov     [rsp+700h+var_6E0], rax
0x18006097d  lea     r8d, [rdx-1]
0x180060981  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180060986  mov     rcx, [rbx+8]
0x18006098a  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18006098f  cmp     [rbx], rcx
0x180060992  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x180060997  mov     rax, [rbx+10h]
0x18006099b  cmovbe  rcx, [rbx]
0x18006099f  mov     rdx, [rbx+18h]
0x1800609a3  cmp     rcx, rax
0x1800609a6  mov     rbx, [rbp+600h+var_678]
0x1800609aa  cmovbe  rax, rcx
0x1800609ae  lea     rcx, [rbp+600h+var_670]; this
0x1800609b2  cmp     rax, rdx
0x1800609b5  cmovbe  rdx, rax; unsigned __int8 *
0x1800609b9  add     rbx, rdx
0x1800609bc  mov     qword ptr [rsp+700h+var_6A8], rbx
0x1800609c1  lea     rax, [rbx+4]
0x1800609c5  mov     qword ptr [rsp+700h+var_6A8+8], rax
0x1800609ca  lea     rax, [rbx+8]
0x1800609ce  mov     qword ptr [rsp+700h+var_698], rax
0x1800609d3  lea     rax, [rbx+0Ch]
0x1800609d7  mov     qword ptr [rsp+700h+var_698+8], rax
0x1800609dc  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800609e1  test    al, al
0x1800609e3  jz      loc_18006124B
0x1800609e9  mov     ecx, [rbp+600h+var_680]
0x1800609ec  xor     eax, eax
0x1800609ee  mov     [rsp+700h+var_28], r12
0x1800609f6  mov     r12d, eax
0x1800609f9  mov     [rsp+700h+var_30], r13
0x180060a01  mov     r13d, eax
0x180060a04  mov     dword ptr [rsp+700h+var_6C0], 2
0x180060a0c  test    ecx, ecx
0x180060a0e  jle     loc_18006123B
0x180060a14  movups  xmm5, [rsp+700h+var_698]
0x180060a19  mov     edx, [rbp+600h+var_650]
0x180060a1c  movups  xmm4, [rsp+700h+var_6A8]
0x180060a21  mov     [rsp+700h+var_18], rsi
0x180060a29  movss   xmm2, cs:__real@43aa8000
0x180060a31  movss   xmm3, cs:__real@447fc000
0x180060a39  mov     esi, [rbp+600h+var_648]
0x180060a3c  mov     [rsp+700h+var_20], rdi
0x180060a44  mov     edi, [rbp+600h+var_67C]
0x180060a47  mov     [rsp+700h+var_38], r15
0x180060a4f  mov     r15d, 3ECh
0x180060a55  nop     word ptr [rax+rax+00000000h]
0x180060a60  inc     edx
0x180060a62  mov     [rbp+600h+var_650], edx
0x180060a65  cmp     edx, 1
0x180060a68  jnz     loc_180061207
0x180060a6e  mov     edx, [r14+28h]
0x180060a72  mov     r11d, eax
0x180060a75  mov     ecx, [r14+2Ch]
0x180060a79  movaps  xmm1, xmm3
0x180060a7c  mov     r10d, [r14+1Ch]
0x180060a80  mov     eax, [rbp+600h+var_64C]
0x180060a83  test    eax, eax
0x180060a85  movsxd  r8, dword ptr [r14+34h]
0x180060a89  cmovle  r11d, eax
0x180060a8d  cmp     r10d, ecx
0x180060a90  movups  [rsp+700h+var_6A8], xmm4
0x180060a95  cmovl   r10d, ecx
0x180060a99  sub     r10d, ecx
0x180060a9c  lea     r9d, [r8-1]
0x180060aa0  cmp     esi, edx
0x180060aa2  cmovl   esi, edx
0x180060aa5  sub     esi, edx
0x180060aa7  mov     eax, esi
0x180060aa9  lea     rsi, [rbx+r13]
0x180060aad  cdq
0x180060aae  idiv    dword ptr [r14+30h]
0x180060ab2  mov     rax, [r14+38h]
0x180060ab6  movq    r14, xmm5
0x180060abb  movsxd  rcx, edx
0x180060abe  imul    rcx, r8
0x180060ac2  movsxd  r8, [rbp+600h+var_54]
0x180060ac9  cmp     r10d, r9d
0x180060acc  cmovle  r9d, r10d
0x180060ad0  add     r14, r13
0x180060ad3  movsxd  r10, r9d
0x180060ad6  mov     r9, qword ptr [rsp+700h+var_6A8+8]
0x180060adb  lea     rax, [rax+rcx*2]
0x180060adf  add     r9, r13
0x180060ae2  mov     ecx, r11d
0x180060ae5  neg     ecx
0x180060ae7  shl     ecx, 4
0x180060aea  movsxd  rdx, ecx
0x180060aed  movss   xmm0, dword ptr [rdx+rsi]
0x180060af2  addss   xmm0, dword ptr [r9+rdx]
0x180060af8  addss   xmm0, dword ptr [rdx+r14]
0x180060afe  lea     rdx, [r10+1]
0x180060b02  lea     rdx, [rax+rdx*2]
0x180060b06  mulss   xmm0, xmm2
0x180060b0a  minss   xmm1, xmm0
0x180060b0e  xorps   xmm0, xmm0
0x180060b11  maxss   xmm0, xmm1
0x180060b15  cvttss2si ecx, xmm0
0x180060b19  mov     [rax+r10*2], cx
0x180060b1e  lea     eax, [r8+1]
0x180060b22  mov     r10d, dword ptr [rsp+r8*4+700h+var_6C0]
0x180060b27  sub     r10d, r11d
0x180060b2a  movsxd  r8, eax
0x180060b2d  mov     ecx, r10d
0x180060b30  cmp     r8, 1
0x180060b34  jge     loc_180060DB9
0x180060b3a  mov     eax, 1
0x180060b3f  sub     rax, r8
0x180060b42  cmp     rax, 4
0x180060b46  jl      loc_180060D3F
0x180060b4c  nop     dword ptr [rax+00h]
0x180060b50  cmp     ecx, edi
0x180060b52  jge     loc_180060DB9
0x180060b58  mov     eax, ecx
0x180060b5a  movaps  xmm1, xmm3
0x180060b5d  shl     eax, 4
0x180060b60  movsxd  r10, eax
0x180060b63  movss   xmm0, dword ptr [r9+r10]
0x180060b69  addss   xmm0, dword ptr [r10+rsi]
0x180060b6f  addss   xmm0, dword ptr [r14+r10]
0x180060b75  mulss   xmm0, xmm2
0x180060b79  minss   xmm1, xmm0
0x180060b7d  xorps   xmm0, xmm0
0x180060b80  maxss   xmm0, xmm1
0x180060b84  cvttss2si eax, xmm0
0x180060b88  cmp     ax, r15w
0x180060b8c  jbe     short loc_180060BB9
0x180060b8e  movss   xmm0, dword ptr [r9+r10-10h]
0x180060b95  movaps  xmm1, xmm3
0x180060b98  addss   xmm0, dword ptr [r10+rsi-10h]
0x180060b9f  addss   xmm0, dword ptr [r14+r10-10h]
0x180060ba6  mulss   xmm0, xmm2
0x180060baa  minss   xmm1, xmm0
0x180060bae  xorps   xmm0, xmm0
0x180060bb1  maxss   xmm0, xmm1
0x180060bb5  cvttss2si eax, xmm0
0x180060bb9  mov     [rdx], ax
0x180060bbc  add     rdx, 2
0x180060bc0  add     ecx, dword ptr [rsp+r8*4+700h+var_6C0]
0x180060bc5  cmp     ecx, edi
0x180060bc7  jge     loc_180060DB9
0x180060bcd  mov     eax, ecx
0x180060bcf  movaps  xmm1, xmm3
0x180060bd2  shl     eax, 4
0x180060bd5  movsxd  r10, eax
0x180060bd8  movss   xmm0, dword ptr [r9+r10]
0x180060bde  addss   xmm0, dword ptr [r10+rsi]
0x180060be4  addss   xmm0, dword ptr [r14+r10]
0x180060bea  mulss   xmm0, xmm2
0x180060bee  minss   xmm1, xmm0
0x180060bf2  xorps   xmm0, xmm0
0x180060bf5  maxss   xmm0, xmm1
0x180060bf9  cvttss2si eax, xmm0
0x180060bfd  cmp     ax, r15w
0x180060c01  jbe     short loc_180060C2E
0x180060c03  movss   xmm0, dword ptr [r9+r10-10h]
0x180060c0a  movaps  xmm1, xmm3
0x180060c0d  addss   xmm0, dword ptr [r10+rsi-10h]
0x180060c14  addss   xmm0, dword ptr [r14+r10-10h]
0x180060c1b  mulss   xmm0, xmm2
0x180060c1f  minss   xmm1, xmm0
0x180060c23  xorps   xmm0, xmm0
0x180060c26  maxss   xmm0, xmm1
0x180060c2a  cvttss2si eax, xmm0
0x180060c2e  mov     [rdx], ax
0x180060c31  add     rdx, 2
0x180060c35  add     ecx, dword ptr [rsp+r8*4+700h+var_6C0+4]
0x180060c3a  cmp     ecx, edi
0x180060c3c  jge     loc_180060DB9
0x180060c42  mov     eax, ecx
0x180060c44  movaps  xmm1, xmm3
0x180060c47  shl     eax, 4
0x180060c4a  movsxd  r10, eax
0x180060c4d  movss   xmm0, dword ptr [r9+r10]
0x180060c53  addss   xmm0, dword ptr [r10+rsi]
0x180060c59  addss   xmm0, dword ptr [r14+r10]
0x180060c5f  mulss   xmm0, xmm2
0x180060c63  minss   xmm1, xmm0
0x180060c67  xorps   xmm0, xmm0
0x180060c6a  maxss   xmm0, xmm1
0x180060c6e  cvttss2si eax, xmm0
0x180060c72  cmp     ax, r15w
0x180060c76  jbe     short loc_180060CA3
0x180060c78  movss   xmm0, dword ptr [r9+r10-10h]
0x180060c7f  movaps  xmm1, xmm3
0x180060c82  addss   xmm0, dword ptr [r10+rsi-10h]
0x180060c89  addss   xmm0, dword ptr [r14+r10-10h]
0x180060c90  mulss   xmm0, xmm2
0x180060c94  minss   xmm1, xmm0
0x180060c98  xorps   xmm0, xmm0
0x180060c9b  maxss   xmm0, xmm1
0x180060c9f  cvttss2si eax, xmm0
0x180060ca3  mov     [rdx], ax
0x180060ca6  lea     r11, [rdx+2]
0x180060caa  add     ecx, dword ptr [rsp+r8*4+700h+var_6C0+8]
0x180060caf  mov     rdx, r11
0x180060cb2  cmp     ecx, edi
0x180060cb4  jge     loc_180060DB9
0x180060cba  mov     eax, ecx
0x180060cbc  movaps  xmm1, xmm3
0x180060cbf  shl     eax, 4
0x180060cc2  movsxd  r10, eax
0x180060cc5  movss   xmm0, dword ptr [r9+r10]
0x180060ccb  addss   xmm0, dword ptr [r10+rsi]
0x180060cd1  addss   xmm0, dword ptr [r14+r10]
0x180060cd7  mulss   xmm0, xmm2
0x180060cdb  minss   xmm1, xmm0
0x180060cdf  xorps   xmm0, xmm0
0x180060ce2  maxss   xmm0, xmm1
0x180060ce6  cvttss2si eax, xmm0
0x180060cea  cmp     ax, r15w
0x180060cee  jbe     short loc_180060D1B
0x180060cf0  movss   xmm0, dword ptr [r9+r10-10h]
0x180060cf7  movaps  xmm1, xmm3
0x180060cfa  addss   xmm0, dword ptr [r10+rsi-10h]
0x180060d01  addss   xmm0, dword ptr [r14+r10-10h]
0x180060d08  mulss   xmm0, xmm2
0x180060d0c  minss   xmm1, xmm0
0x180060d10  xorps   xmm0, xmm0
0x180060d13  maxss   xmm0, xmm1
0x180060d17  cvttss2si eax, xmm0
0x180060d1b  mov     [r11], ax
0x180060d1f  lea     rdx, [r11+2]
0x180060d23  add     ecx, dword ptr [rsp+r8*4+700h+var_6C0+0Ch]
0x180060d28  add     r8, 4
0x180060d2c  mov     rax, r8
0x180060d2f  cmp     r8, 0FFFFFFFFFFFFFFFEh
0x180060d33  jl      loc_180060B50
0x180060d39  cmp     rax, 1
0x180060d3d  jge     short loc_180060DB9
0x180060d3f  cmp     ecx, edi
0x180060d41  jge     short loc_180060DB9
0x180060d43  mov     eax, ecx
0x180060d45  movaps  xmm1, xmm3
0x180060d48  shl     eax, 4
0x180060d4b  movsxd  r10, eax
0x180060d4e  movss   xmm0, dword ptr [r9+r10]
0x180060d54  addss   xmm0, dword ptr [r10+rsi]
0x180060d5a  addss   xmm0, dword ptr [r14+r10]
0x180060d60  mulss   xmm0, xmm2
0x180060d64  minss   xmm1, xmm0
0x180060d68  xorps   xmm0, xmm0
0x180060d6b  maxss   xmm0, xmm1
0x180060d6f  cvttss2si eax, xmm0
0x180060d73  cmp     ax, r15w
0x180060d77  jbe     short loc_180060DA4
0x180060d79  movss   xmm0, dword ptr [r9+r10-10h]
0x180060d80  movaps  xmm1, xmm3
0x180060d83  addss   xmm0, dword ptr [r10+rsi-10h]
0x180060d8a  addss   xmm0, dword ptr [r14+r10-10h]
0x180060d91  mulss   xmm0, xmm2
0x180060d95  minss   xmm1, xmm0
0x180060d99  xorps   xmm0, xmm0
0x180060d9c  maxss   xmm0, xmm1
0x180060da0  cvttss2si eax, xmm0
0x180060da4  mov     [rdx], ax
0x180060da7  add     rdx, 2
0x180060dab  add     ecx, dword ptr [rsp+r8*4+700h+var_6C0]
0x180060db0  inc     r8
0x180060db3  cmp     r8, 1
0x180060db7  jl      short loc_180060D3F
0x180060db9  mov     edi, [rbp+600h+var_67C]
0x180060dbc  lea     r15d, [rcx-1]
0x180060dc0  lea     r11d, [rdi-0Fh]
0x180060dc4  cmp     r15d, r11d
0x180060dc7  jge     loc_18006112B
0x180060dcd  sub     r11d, r15d
0x180060dd0  movsxd  rcx, r15d
0x180060dd3  inc     rcx
0x180060dd6  mov     r8, rsi
0x180060dd9  shl     rcx, 4
0x180060ddd  mov     r10, r14
0x180060de0  add     rcx, r9
0x180060de3  sub     r8, r9
0x180060de6  lea     eax, [r11-1]
0x180060dea  sub     r10, r9
0x180060ded  shr     eax, 4
0x180060df0  mov     edi, 3ECh
0x180060df5  inc     eax
  ... truncated ...
```
