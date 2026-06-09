# Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005c120`
- end: `0x18005c57a`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$03$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1114`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa80`

## callees

- `0x180003180`
- `0x18005c120`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
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
  unsigned __int8 *v11; // r12
  int v12; // r13d
  __int64 v13; // xmm1_8
  __int128 v14; // xmm0
  int v15; // esi
  int v16; // edi
  int v17; // r15d
  int v18; // ecx
  int v19; // r11d
  int v20; // r10d
  __int64 v21; // r8
  int v22; // eax
  int v23; // r10d
  int v24; // r9d
  int v25; // eax
  __int64 v26; // rcx
  unsigned __int8 *v27; // r10
  int v28; // r11d
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int8 *v33; // r14
  unsigned __int8 *v34; // r12
  _WORD *v35; // rax
  int v36; // ecx
  unsigned __int8 *v37; // r9
  unsigned int v38; // ecx
  __int64 v39; // rdi
  unsigned __int8 *v40; // rcx
  int v41; // edx
  unsigned __int8 *v42; // r10
  __int64 v43; // r14
  unsigned __int8 *v44; // r8
  __int64 v45; // r9
  int v46; // ecx
  int v47; // edx
  __int64 v48; // rax
  unsigned __int8 *v51[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v52; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+68h] [rbp-98h]
  __int64 v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+84h] [rbp-7Ch]
  __int64 v58; // [rsp+88h] [rbp-78h]
  char v59[32]; // [rsp+90h] [rbp-70h] BYREF
  int v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+B4h] [rbp-4Ch]
  int v62; // [rsp+B8h] [rbp-48h]
  _DWORD v63[374]; // [rsp+BCh] [rbp-44h]
  int v64; // [rsp+694h] [rbp+594h]
  int v65; // [rsp+69Ch] [rbp+59Ch]
  int v66; // [rsp+6ACh] [rbp+5ACh]

  *(_OWORD *)v51 = *a4;
  v5 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v56, 1, 1, (_DWORD)a3, (__int64)v51, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v58];
  *(_QWORD *)&v53 = &v8[v58];
  *((_QWORD *)&v53 + 1) = &v8[v58 + 1];
  v54 = (__int64)&v8[v58 + 2];
  v55 = (__int64)&v8[v58 + 3];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v59,
             v8,
             &v52,
             v51);
  if ( result )
  {
    result = 0;
    v11 = 0;
    v12 = 0;
    v51[0] = 0;
    LODWORD(v52) = 1;
    if ( v56 > 0 )
    {
      v13 = v54;
      v14 = v53;
      v15 = v57;
      v16 = v64;
      v17 = v60;
      do
      {
        v60 = ++v17;
        if ( v17 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = 0;
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v61 <= 0 )
            v19 = v61;
          v22 = *(_DWORD *)(v5 + 44);
          v53 = v14;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v20 - v22;
          v24 = v21 - 1;
          v25 = v62;
          if ( v62 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v24 )
            v24 = v23;
          v27 = &v51[0][v13];
          v28 = -v19;
          v29 = v24;
          v30 = v66;
          v31 = v29 + v26;
          v32 = *(_QWORD *)(v5 + 56);
          v33 = &v11[(_QWORD)v9];
          v34 = &v11[*((_QWORD *)&v53 + 1)];
          v35 = (_WORD *)(v32 + 2 * v31);
          if ( v66 < 1LL )
          {
            do
            {
              if ( v28 >= v15 )
                break;
              *v35++ = (85 * (v34[4 * v28] + v27[4 * v28] + (unsigned int)v33[4 * v28])) >> 6;
              v36 = *((_DWORD *)&v52 + v30++);
              v28 += v36;
            }
            while ( v30 < 1 );
            v16 = v64;
            v17 = v60;
            v15 = v57;
          }
          if ( v28 < v15 - 7 )
          {
            v37 = &v33[4 * v28 + 8];
            v38 = ((unsigned int)(v15 - 7 - v28 - 1) >> 3) + 1;
            v39 = v38;
            v28 += 8 * v38;
            do
            {
              *v35 = (85 * (*(v37 - 8) + v34[v37 - v33 - 8] + (unsigned int)v27[v37 - v33 - 8])) >> 6;
              v35[1] = (85 * (*(v37 - 4) + v34[v37 - v33 - 4] + (unsigned int)v27[v37 - v33 - 4])) >> 6;
              v35[2] = (85 * (*v37 + v34[v37 - v33] + (unsigned int)v27[v37 - v33])) >> 6;
              v35[3] = (85 * (v37[4] + v34[v37 - v33 + 4] + (unsigned int)v27[v37 - v33 + 4])) >> 6;
              v35[4] = (85 * (v37[8] + v34[v37 - v33 + 8] + (unsigned int)v27[v37 - v33 + 8])) >> 6;
              v35[5] = (85 * (v37[12] + v34[v37 - v33 + 12] + (unsigned int)v27[v37 - v33 + 12])) >> 6;
              v35[6] = (85 * (v37[16] + v34[v37 - v33 + 16] + (unsigned int)v27[v37 - v33 + 16])) >> 6;
              v40 = (unsigned __int8 *)(v37 - v33);
              v41 = v27[v37 - v33 + 20];
              v37 += 32;
              v35[7] = (85 * (*(v37 - 12) + (unsigned int)v34[(_QWORD)v40 + 20] + v41)) >> 6;
              v35 += 8;
              --v39;
            }
            while ( v39 );
            v16 = v64;
            v17 = v60;
            v15 = v57;
          }
          if ( v28 < v15 )
          {
            v42 = (unsigned __int8 *)(v27 - v34);
            v43 = v33 - v34;
            v44 = &v34[4 * v28];
            v45 = (unsigned int)(v15 - v28);
            do
            {
              v46 = v44[(_QWORD)v42];
              ++v35;
              v47 = v44[v43];
              v44 += 4;
              *(v35 - 1) = (85 * ((unsigned int)*(v44 - 4) + v46 + v47)) >> 6;
              --v45;
            }
            while ( v45 );
            v16 = v64;
            v17 = v60;
            v15 = v57;
          }
          v11 = v51[0];
          v5 = a1;
          v48 = v16++;
          v17 -= v63[v48];
          if ( v16 >= v65 )
            v16 = 0;
          ++v62;
          v64 = v16;
        }
        ++v12;
        v11 += *a3;
        result = 0;
        v51[0] = v11;
      }
      while ( v12 < v56 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005c120  push    rbp
0x18005c122  push    rbx
0x18005c123  push    r14
0x18005c125  lea     rbp, [rsp-5F0h]
0x18005c12d  sub     rsp, 6F0h
0x18005c134  mov     rax, cs:__security_cookie
0x18005c13b  xor     rax, rsp
0x18005c13e  mov     [rbp+600h+var_50], rax
0x18005c145  movups  xmm0, xmmword ptr [r9]
0x18005c149  lea     rax, [rcx+8]
0x18005c14d  mov     [rsp+700h+var_6C8], r8
0x18005c152  mov     [rsp+700h+var_6D8], rax
0x18005c157  mov     rbx, rdx
0x18005c15a  mov     edx, 1
0x18005c15f  mov     [rsp+700h+var_6D0], rcx
0x18005c164  lea     rax, [rsp+700h+var_6C0]
0x18005c169  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x18005c16e  mov     r14, rcx
0x18005c171  mov     [rsp+700h+var_6E0], rax
0x18005c176  mov     r9, r8
0x18005c179  lea     rcx, [rbp+600h+var_680]
0x18005c17d  mov     r8d, edx
0x18005c180  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005c185  mov     rcx, [rbx+8]
0x18005c189  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005c18e  cmp     [rbx], rcx
0x18005c191  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005c196  mov     rax, [rbx+10h]
0x18005c19a  cmovbe  rcx, [rbx]
0x18005c19e  mov     rdx, [rbx+18h]
0x18005c1a2  cmp     rcx, rax
0x18005c1a5  mov     rbx, [rbp+600h+var_678]
0x18005c1a9  cmovbe  rax, rcx
0x18005c1ad  lea     rcx, [rbp+600h+var_670]; this
0x18005c1b1  cmp     rax, rdx
0x18005c1b4  cmovbe  rdx, rax; unsigned __int8 *
0x18005c1b8  add     rbx, rdx
0x18005c1bb  mov     qword ptr [rsp+700h+var_6A8], rbx
0x18005c1c0  lea     rax, [rbx+1]
0x18005c1c4  mov     qword ptr [rsp+700h+var_6A8+8], rax
0x18005c1c9  lea     rax, [rbx+2]
0x18005c1cd  mov     qword ptr [rsp+700h+var_698], rax
0x18005c1d2  lea     rax, [rbx+3]
0x18005c1d6  mov     qword ptr [rsp+700h+var_698+8], rax
0x18005c1db  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005c1e0  test    al, al
0x18005c1e2  jz      loc_18005C55F
0x18005c1e8  xor     eax, eax
0x18005c1ea  mov     [rsp+700h+var_28], r12
0x18005c1f2  mov     r12d, eax
0x18005c1f5  mov     [rsp+700h+var_30], r13
0x18005c1fd  mov     r13d, eax
0x18005c200  mov     [rsp+700h+var_6C0], rax
0x18005c205  mov     dword ptr [rsp+700h+var_6B0], 1
0x18005c20d  cmp     [rbp+600h+var_680], eax
0x18005c210  jle     loc_18005C54F
0x18005c216  movups  xmm1, [rsp+700h+var_698]
0x18005c21b  mov     [rsp+700h+var_18], rsi
0x18005c223  movups  xmm0, [rsp+700h+var_6A8]
0x18005c228  mov     esi, [rbp+600h+var_67C]
0x18005c22b  mov     [rsp+700h+var_20], rdi
0x18005c233  mov     edi, [rbp+600h+var_6C]
0x18005c239  mov     [rsp+700h+var_38], r15
0x18005c241  mov     r15d, [rbp+600h+var_650]
0x18005c245  inc     r15d
0x18005c248  mov     [rbp+600h+var_650], r15d
0x18005c24c  cmp     r15d, 1
0x18005c250  jnz     loc_18005C515
0x18005c256  mov     ecx, [r14+28h]
0x18005c25a  mov     r11d, eax
0x18005c25d  mov     eax, [rbp+600h+var_64C]
0x18005c260  test    eax, eax
0x18005c262  mov     r10d, [r14+1Ch]
0x18005c266  movsxd  r8, dword ptr [r14+34h]
0x18005c26a  cmovle  r11d, eax
0x18005c26e  mov     eax, [r14+2Ch]
0x18005c272  cmp     r10d, eax
0x18005c275  movups  [rsp+700h+var_6A8], xmm0
0x18005c27a  cmovl   r10d, eax
0x18005c27e  sub     r10d, eax
0x18005c281  lea     r9d, [r8-1]
0x18005c285  mov     eax, [rbp+600h+var_648]
0x18005c288  cmp     eax, ecx
0x18005c28a  cmovl   eax, ecx
0x18005c28d  sub     eax, ecx
0x18005c28f  cdq
0x18005c290  idiv    dword ptr [r14+30h]
0x18005c294  movsxd  rcx, edx
0x18005c297  imul    rcx, r8
0x18005c29b  cmp     r10d, r9d
0x18005c29e  cmovle  r9d, r10d
0x18005c2a2  movq    r10, xmm1
0x18005c2a7  add     r10, [rsp+700h+var_6C0]
0x18005c2ac  neg     r11d
0x18005c2af  movsxd  rax, r9d
0x18005c2b2  movsxd  r9, [rbp+600h+var_54]
0x18005c2b9  add     rcx, rax
0x18005c2bc  mov     rax, [r14+38h]
0x18005c2c0  lea     r14, [rbx+r12]
0x18005c2c4  add     r12, qword ptr [rsp+700h+var_6A8+8]
0x18005c2c9  lea     rax, [rax+rcx*2]
0x18005c2cd  cmp     r9, 1
0x18005c2d1  jge     short loc_18005C324
0x18005c2d3  cmp     r11d, esi
0x18005c2d6  jge     short loc_18005C317
0x18005c2d8  lea     ecx, ds:0[r11*4]
0x18005c2e0  movsxd  rdx, ecx
0x18005c2e3  movzx   ecx, byte ptr [rdx+r10]
0x18005c2e8  movzx   r8d, byte ptr [r14+rdx]
0x18005c2ed  add     r8d, ecx
0x18005c2f0  movzx   ecx, byte ptr [rdx+r12]
0x18005c2f5  add     r8d, ecx
0x18005c2f8  imul    ecx, r8d, 55h ; 'U'
0x18005c2fc  shr     ecx, 6
0x18005c2ff  mov     [rax], cx
0x18005c302  add     rax, 2
0x18005c306  mov     ecx, dword ptr [rsp+r9*4+700h+var_6B0]
0x18005c30b  inc     r9
0x18005c30e  add     r11d, ecx
0x18005c311  cmp     r9, 1
0x18005c315  jl      short loc_18005C2D3
0x18005c317  mov     edi, [rbp+600h+var_6C]
0x18005c31d  mov     r15d, [rbp+600h+var_650]
0x18005c321  mov     esi, [rbp+600h+var_67C]
0x18005c324  lea     edx, [rsi-7]
0x18005c327  cmp     r11d, edx
0x18005c32a  jge     loc_18005C493
0x18005c330  sub     edx, r11d
0x18005c333  movsxd  r9, r11d
0x18005c336  add     r9, 2
0x18005c33a  mov     r8, r14
0x18005c33d  neg     r8
0x18005c340  lea     ecx, [rdx-1]
0x18005c343  shr     ecx, 3
0x18005c346  lea     r9, [r14+r9*4]
0x18005c34a  inc     ecx
0x18005c34c  mov     edi, ecx
0x18005c34e  lea     r11d, [r11+rcx*8]
0x18005c352  nop     dword ptr [rax+00h]
0x18005c356  nop     word ptr [rax+rax+00000000h]
0x18005c360  lea     rcx, [r9+r8]
0x18005c364  movzx   edx, byte ptr [rcx+r10-8]
0x18005c36a  movzx   ecx, byte ptr [rcx+r12-8]
0x18005c370  add     edx, ecx
0x18005c372  movzx   ecx, byte ptr [r9-8]
0x18005c377  add     edx, ecx
0x18005c379  imul    ecx, edx, 55h ; 'U'
0x18005c37c  shr     ecx, 6
0x18005c37f  mov     [rax], cx
0x18005c382  lea     rcx, [r9+r8]
0x18005c386  movzx   edx, byte ptr [rcx+r10-4]
0x18005c38c  movzx   ecx, byte ptr [rcx+r12-4]
0x18005c392  add     edx, ecx
0x18005c394  movzx   ecx, byte ptr [r9-4]
0x18005c399  add     edx, ecx
0x18005c39b  imul    ecx, edx, 55h ; 'U'
0x18005c39e  shr     ecx, 6
0x18005c3a1  mov     [rax+2], cx
0x18005c3a5  lea     rcx, [r9+r8]
0x18005c3a9  movzx   edx, byte ptr [rcx+r10]
0x18005c3ae  movzx   ecx, byte ptr [rcx+r12]
0x18005c3b3  add     edx, ecx
0x18005c3b5  movzx   ecx, byte ptr [r9]
0x18005c3b9  add     edx, ecx
0x18005c3bb  imul    ecx, edx, 55h ; 'U'
0x18005c3be  shr     ecx, 6
0x18005c3c1  mov     [rax+4], cx
0x18005c3c5  lea     rcx, [r9+r8]
0x18005c3c9  movzx   edx, byte ptr [rcx+r10+4]
0x18005c3cf  movzx   ecx, byte ptr [rcx+r12+4]
0x18005c3d5  add     edx, ecx
0x18005c3d7  movzx   ecx, byte ptr [r9+4]
0x18005c3dc  add     edx, ecx
0x18005c3de  imul    ecx, edx, 55h ; 'U'
0x18005c3e1  shr     ecx, 6
0x18005c3e4  mov     [rax+6], cx
0x18005c3e8  lea     rcx, [r9+r8]
0x18005c3ec  movzx   edx, byte ptr [rcx+r10+8]
0x18005c3f2  movzx   ecx, byte ptr [rcx+r12+8]
0x18005c3f8  add     edx, ecx
0x18005c3fa  movzx   ecx, byte ptr [r9+8]
0x18005c3ff  add     edx, ecx
0x18005c401  imul    ecx, edx, 55h ; 'U'
0x18005c404  shr     ecx, 6
0x18005c407  mov     [rax+8], cx
0x18005c40b  lea     rcx, [r9+r8]
0x18005c40f  movzx   edx, byte ptr [rcx+r10+0Ch]
0x18005c415  movzx   ecx, byte ptr [rcx+r12+0Ch]
0x18005c41b  add     edx, ecx
0x18005c41d  movzx   ecx, byte ptr [r9+0Ch]
0x18005c422  add     edx, ecx
0x18005c424  imul    ecx, edx, 55h ; 'U'
0x18005c427  shr     ecx, 6
0x18005c42a  mov     [rax+0Ah], cx
0x18005c42e  lea     rcx, [r9+r8]
0x18005c432  movzx   edx, byte ptr [rcx+r10+10h]
0x18005c438  movzx   ecx, byte ptr [rcx+r12+10h]
0x18005c43e  add     edx, ecx
0x18005c440  movzx   ecx, byte ptr [r9+10h]
0x18005c445  add     edx, ecx
0x18005c447  imul    ecx, edx, 55h ; 'U'
0x18005c44a  shr     ecx, 6
0x18005c44d  mov     [rax+0Ch], cx
0x18005c451  lea     rcx, [r9+r8]
0x18005c455  movzx   edx, byte ptr [rcx+r10+14h]
0x18005c45b  lea     r9, [r9+20h]
0x18005c45f  movzx   ecx, byte ptr [rcx+r12+14h]
0x18005c465  add     edx, ecx
0x18005c467  movzx   ecx, byte ptr [r9-0Ch]
0x18005c46c  add     edx, ecx
0x18005c46e  imul    ecx, edx, 55h ; 'U'
0x18005c471  shr     ecx, 6
0x18005c474  mov     [rax+0Eh], cx
0x18005c478  add     rax, 10h
0x18005c47c  sub     rdi, 1
0x18005c480  jnz     loc_18005C360
0x18005c486  mov     edi, [rbp+600h+var_6C]
0x18005c48c  mov     r15d, [rbp+600h+var_650]
0x18005c490  mov     esi, [rbp+600h+var_67C]
0x18005c493  cmp     r11d, esi
0x18005c496  jge     short loc_18005C4EA
0x18005c498  lea     ecx, ds:0[r11*4]
0x18005c4a0  sub     r10, r12
0x18005c4a3  movsxd  r8, ecx
0x18005c4a6  sub     r14, r12
0x18005c4a9  add     r8, r12
0x18005c4ac  sub     esi, r11d
0x18005c4af  mov     r9d, esi
0x18005c4b2  movzx   ecx, byte ptr [r10+r8]
0x18005c4b7  lea     rax, [rax+2]
0x18005c4bb  movzx   edx, byte ptr [r14+r8]
0x18005c4c0  lea     r8, [r8+4]
0x18005c4c4  add     edx, ecx
0x18005c4c6  movzx   ecx, byte ptr [r8-4]
0x18005c4cb  add     edx, ecx
0x18005c4cd  imul    ecx, edx, 55h ; 'U'
0x18005c4d0  shr     ecx, 6
0x18005c4d3  mov     [rax-2], cx
0x18005c4d7  sub     r9, 1
0x18005c4db  jnz     short loc_18005C4B2
0x18005c4dd  mov     edi, [rbp+600h+var_6C]
0x18005c4e3  mov     r15d, [rbp+600h+var_650]
0x18005c4e7  mov     esi, [rbp+600h+var_67C]
0x18005c4ea  mov     r12, [rsp+700h+var_6C0]
0x18005c4ef  mov     r14, [rsp+700h+var_6D0]
0x18005c4f4  movsxd  rax, edi
0x18005c4f7  inc     edi
0x18005c4f9  sub     r15d, [rbp+rax*4+600h+var_644]
0x18005c4fe  mov     eax, 0
0x18005c503  cmp     edi, [rbp+600h+var_64]
0x18005c509  cmovge  edi, eax
0x18005c50c  inc     [rbp+600h+var_648]
0x18005c50f  mov     [rbp+600h+var_6C], edi
0x18005c515  mov     rax, [rsp+700h+var_6C8]
0x18005c51a  inc     r13d
0x18005c51d  movsxd  rax, dword ptr [rax]
0x18005c520  add     r12, rax
0x18005c523  mov     eax, 0
0x18005c528  mov     [rsp+700h+var_6C0], r12
0x18005c52d  cmp     r13d, [rbp+600h+var_680]
0x18005c531  jl      loc_18005C245
0x18005c537  mov     r15, [rsp+700h+var_38]
0x18005c53f  mov     rdi, [rsp+700h+var_20]
0x18005c547  mov     rsi, [rsp+700h+var_18]
0x18005c54f  mov     r12, [rsp+700h+var_28]
0x18005c557  mov     r13, [rsp+700h+var_30]
0x18005c55f  mov     rcx, [rbp+600h+var_50]
0x18005c566  xor     rcx, rsp; StackCookie
0x18005c569  call    __security_check_cookie
0x18005c56e  add     rsp, 6F0h
0x18005c575  pop     r14
0x18005c577  pop     rbx
0x18005c578  pop     rbp
0x18005c579  retn
```
