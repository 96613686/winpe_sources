# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005cb30`
- end: `0x18005cfa8`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$03$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa90`

## callees

- `0x180003180`
- `0x18005cb30`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r15
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
  int v17; // r14d
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
  unsigned __int8 *v33; // r15
  unsigned __int8 *v34; // r12
  _WORD *v35; // rax
  int v36; // ecx
  unsigned __int8 *v37; // r9
  __int64 v38; // rdi
  unsigned __int8 *v39; // rcx
  int v40; // edx
  unsigned __int8 *v41; // r10
  unsigned __int8 *v42; // r8
  __int64 v43; // r15
  __int64 v44; // r9
  int v45; // ecx
  int v46; // edx
  __int64 v47; // rax
  unsigned __int8 *v50[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v51; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v52; // [rsp+58h] [rbp-A8h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch]
  __int64 v57; // [rsp+88h] [rbp-78h]
  char v58[32]; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+B0h] [rbp-50h]
  int v60; // [rsp+B4h] [rbp-4Ch]
  int v61; // [rsp+B8h] [rbp-48h]
  _DWORD v62[374]; // [rsp+BCh] [rbp-44h]
  int v63; // [rsp+694h] [rbp+594h]
  int v64; // [rsp+69Ch] [rbp+59Ch]
  int v65; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v50 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v55, 2, 1, a3, v50, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v57];
  *(_QWORD *)&v52 = &v8[v57];
  *((_QWORD *)&v52 + 1) = &v8[v57 + 1];
  v53 = (__int64)&v8[v57 + 2];
  v54 = (__int64)&v8[v57 + 3];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v58,
             v8,
             &v51,
             v50);
  if ( result )
  {
    result = 0;
    v11 = 0;
    v12 = 0;
    v50[0] = 0;
    LODWORD(v51) = 2;
    if ( v55 > 0 )
    {
      v13 = v53;
      v14 = v52;
      v15 = v63;
      v16 = v56;
      v17 = v59;
      do
      {
        v59 = ++v17;
        if ( v17 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = 0;
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v60 <= 0 )
            v19 = v60;
          v22 = *(_DWORD *)(v5 + 44);
          v52 = v14;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v20 - v22;
          v24 = v21 - 1;
          v25 = v61;
          if ( v61 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v24 )
            v24 = v23;
          v27 = &v50[0][v13];
          v28 = -v19;
          v29 = v24;
          v30 = v65;
          v31 = v29 + v26;
          v32 = *(_QWORD *)(v5 + 56);
          v33 = &v11[(_QWORD)v9];
          v34 = &v11[*((_QWORD *)&v52 + 1)];
          v35 = (_WORD *)(v32 + 2 * v31);
          if ( v65 < 1LL )
          {
            do
            {
              if ( v28 >= v16 )
                break;
              *v35++ = (85 * (v34[4 * v28] + v27[4 * v28] + (unsigned int)v33[4 * v28])) >> 6;
              v36 = *((_DWORD *)&v51 + v30++);
              v28 += v36;
            }
            while ( v30 < 1 );
            v15 = v63;
            v17 = v59;
            v16 = v56;
          }
          if ( v28 < v16 - 15 )
          {
            v37 = &v33[4 * v28 + 16];
            v38 = ((unsigned int)(v16 - 15 - v28 - 1) >> 4) + 1;
            v28 += 16 * v38;
            do
            {
              *v35 = (85 * (*(v37 - 16) + v34[v37 - v33 - 16] + (unsigned int)v27[v37 - v33 - 16])) >> 6;
              v35[1] = (85 * (*(v37 - 8) + v34[v37 - v33 - 8] + (unsigned int)v27[v37 - v33 - 8])) >> 6;
              v35[2] = (85 * (*v37 + v34[v37 - v33] + (unsigned int)v27[v37 - v33])) >> 6;
              v35[3] = (85 * (v37[8] + v34[v37 - v33 + 8] + (unsigned int)v27[v37 - v33 + 8])) >> 6;
              v35[4] = (85 * (v37[16] + v34[v37 - v33 + 16] + (unsigned int)v27[v37 - v33 + 16])) >> 6;
              v35[5] = (85 * (v37[24] + v34[v37 - v33 + 24] + (unsigned int)v27[v37 - v33 + 24])) >> 6;
              v35[6] = (85 * (v37[32] + v27[v37 - v33 + 32] + (unsigned int)v34[v37 - v33 + 32])) >> 6;
              v39 = (unsigned __int8 *)(v37 - v33);
              v40 = v27[v37 - v33 + 40];
              v37 += 64;
              v35[7] = (85 * (*(v37 - 24) + (unsigned int)v34[(_QWORD)v39 + 40] + v40)) >> 6;
              v35 += 8;
              --v38;
            }
            while ( v38 );
            v15 = v63;
            v17 = v59;
            v16 = v56;
          }
          if ( v28 < v16 )
          {
            v41 = (unsigned __int8 *)(v27 - v34);
            v42 = &v34[4 * v28];
            v43 = v33 - v34;
            v44 = ((unsigned int)(v16 - v28 - 1) >> 1) + 1;
            do
            {
              v45 = v42[(_QWORD)v41];
              ++v35;
              v46 = v42[v43];
              v42 += 8;
              *(v35 - 1) = (85 * ((unsigned int)*(v42 - 8) + v45 + v46)) >> 6;
              --v44;
            }
            while ( v44 );
            v15 = v63;
            v17 = v59;
            v16 = v56;
          }
          v11 = v50[0];
          v5 = a1;
          v47 = v15++;
          v17 -= v62[v47];
          if ( v15 >= v64 )
            v15 = 0;
          ++v61;
          v63 = v15;
        }
        ++v12;
        v11 += *a3;
        result = 0;
        v50[0] = v11;
      }
      while ( v12 < v55 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005cb30  push    rbp
0x18005cb32  push    rbx
0x18005cb33  push    r15
0x18005cb35  lea     rbp, [rsp-5F0h]
0x18005cb3d  sub     rsp, 6F0h
0x18005cb44  mov     rax, cs:__security_cookie
0x18005cb4b  xor     rax, rsp
0x18005cb4e  mov     [rbp+600h+var_50], rax
0x18005cb55  movups  xmm0, xmmword ptr [r9]
0x18005cb59  lea     rax, [rcx+8]
0x18005cb5d  mov     [rsp+700h+var_6C8], r8
0x18005cb62  mov     [rsp+700h+var_6D8], rax
0x18005cb67  mov     rbx, rdx
0x18005cb6a  mov     edx, 2
0x18005cb6f  mov     [rsp+700h+var_6D0], rcx
0x18005cb74  mov     r15, rcx
0x18005cb77  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x18005cb7c  lea     rax, [rsp+700h+var_6C0]
0x18005cb81  mov     r9, r8
0x18005cb84  lea     rcx, [rbp+600h+var_680]
0x18005cb88  mov     [rsp+700h+var_6E0], rax
0x18005cb8d  lea     r8d, [rdx-1]
0x18005cb91  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005cb96  mov     rcx, [rbx+8]
0x18005cb9a  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005cb9f  cmp     [rbx], rcx
0x18005cba2  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005cba7  mov     rax, [rbx+10h]
0x18005cbab  cmovbe  rcx, [rbx]
0x18005cbaf  mov     rdx, [rbx+18h]
0x18005cbb3  cmp     rcx, rax
0x18005cbb6  mov     rbx, [rbp+600h+var_678]
0x18005cbba  cmovbe  rax, rcx
0x18005cbbe  lea     rcx, [rbp+600h+var_670]; this
0x18005cbc2  cmp     rax, rdx
0x18005cbc5  cmovbe  rdx, rax; unsigned __int8 *
0x18005cbc9  add     rbx, rdx
0x18005cbcc  mov     qword ptr [rsp+700h+var_6A8], rbx
0x18005cbd1  lea     rax, [rbx+1]
0x18005cbd5  mov     qword ptr [rsp+700h+var_6A8+8], rax
0x18005cbda  lea     rax, [rbx+2]
0x18005cbde  mov     qword ptr [rsp+700h+var_698], rax
0x18005cbe3  lea     rax, [rbx+3]
0x18005cbe7  mov     qword ptr [rsp+700h+var_698+8], rax
0x18005cbec  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005cbf1  test    al, al
0x18005cbf3  jz      loc_18005CF8D
0x18005cbf9  xor     eax, eax
0x18005cbfb  mov     [rsp+700h+var_28], r12
0x18005cc03  mov     r12d, eax
0x18005cc06  mov     [rsp+700h+var_30], r13
0x18005cc0e  mov     r13d, eax
0x18005cc11  mov     [rsp+700h+var_6C0], rax
0x18005cc16  mov     dword ptr [rsp+700h+var_6B0], 2
0x18005cc1e  cmp     [rbp+600h+var_680], eax
0x18005cc21  jle     loc_18005CF7D
0x18005cc27  movups  xmm1, [rsp+700h+var_698]
0x18005cc2c  mov     [rsp+700h+var_18], rsi
0x18005cc34  movups  xmm0, [rsp+700h+var_6A8]
0x18005cc39  mov     esi, [rbp+600h+var_6C]
0x18005cc3f  mov     [rsp+700h+var_20], rdi
0x18005cc47  mov     edi, [rbp+600h+var_67C]
0x18005cc4a  mov     [rsp+700h+var_38], r14
0x18005cc52  mov     r14d, [rbp+600h+var_650]
0x18005cc56  nop     word ptr [rax+rax+00000000h]
0x18005cc60  inc     r14d
0x18005cc63  mov     [rbp+600h+var_650], r14d
0x18005cc67  cmp     r14d, 1
0x18005cc6b  jnz     loc_18005CF43
0x18005cc71  mov     ecx, [r15+28h]
0x18005cc75  mov     r11d, eax
0x18005cc78  mov     eax, [rbp+600h+var_64C]
0x18005cc7b  test    eax, eax
0x18005cc7d  mov     r10d, [r15+1Ch]
0x18005cc81  movsxd  r8, dword ptr [r15+34h]
0x18005cc85  cmovle  r11d, eax
0x18005cc89  mov     eax, [r15+2Ch]
0x18005cc8d  cmp     r10d, eax
0x18005cc90  movups  [rsp+700h+var_6A8], xmm0
0x18005cc95  cmovl   r10d, eax
0x18005cc99  sub     r10d, eax
0x18005cc9c  lea     r9d, [r8-1]
0x18005cca0  mov     eax, [rbp+600h+var_648]
0x18005cca3  cmp     eax, ecx
0x18005cca5  cmovl   eax, ecx
0x18005cca8  sub     eax, ecx
0x18005ccaa  cdq
0x18005ccab  idiv    dword ptr [r15+30h]
0x18005ccaf  movsxd  rcx, edx
0x18005ccb2  imul    rcx, r8
0x18005ccb6  cmp     r10d, r9d
0x18005ccb9  cmovle  r9d, r10d
0x18005ccbd  movq    r10, xmm1
0x18005ccc2  add     r10, [rsp+700h+var_6C0]
0x18005ccc7  neg     r11d
0x18005ccca  movsxd  rax, r9d
0x18005cccd  movsxd  r9, [rbp+600h+var_54]
0x18005ccd4  add     rcx, rax
0x18005ccd7  mov     rax, [r15+38h]
0x18005ccdb  lea     r15, [rbx+r12]
0x18005ccdf  add     r12, qword ptr [rsp+700h+var_6A8+8]
0x18005cce4  lea     rax, [rax+rcx*2]
0x18005cce8  cmp     r9, 1
0x18005ccec  jge     short loc_18005CD41
0x18005ccee  xchg    ax, ax
0x18005ccf0  cmp     r11d, edi
0x18005ccf3  jge     short loc_18005CD34
0x18005ccf5  lea     ecx, ds:0[r11*4]
0x18005ccfd  movsxd  rdx, ecx
0x18005cd00  movzx   ecx, byte ptr [rdx+r10]
0x18005cd05  movzx   r8d, byte ptr [r15+rdx]
0x18005cd0a  add     r8d, ecx
0x18005cd0d  movzx   ecx, byte ptr [rdx+r12]
0x18005cd12  add     r8d, ecx
0x18005cd15  imul    ecx, r8d, 55h ; 'U'
0x18005cd19  shr     ecx, 6
0x18005cd1c  mov     [rax], cx
0x18005cd1f  add     rax, 2
0x18005cd23  mov     ecx, dword ptr [rsp+r9*4+700h+var_6B0]
0x18005cd28  inc     r9
0x18005cd2b  add     r11d, ecx
0x18005cd2e  cmp     r9, 1
0x18005cd32  jl      short loc_18005CCF0
0x18005cd34  mov     esi, [rbp+600h+var_6C]
0x18005cd3a  mov     r14d, [rbp+600h+var_650]
0x18005cd3e  mov     edi, [rbp+600h+var_67C]
0x18005cd41  lea     edx, [rdi-0Fh]
0x18005cd44  cmp     r11d, edx
0x18005cd47  jge     loc_18005CEB3
0x18005cd4d  sub     edx, r11d
0x18005cd50  movsxd  r9, r11d
0x18005cd53  add     r9, 4
0x18005cd57  mov     r8, r15
0x18005cd5a  neg     r8
0x18005cd5d  lea     ecx, [rdx-1]
0x18005cd60  shr     ecx, 4
0x18005cd63  lea     r9, [r15+r9*4]
0x18005cd67  inc     ecx
0x18005cd69  mov     edi, ecx
0x18005cd6b  shl     ecx, 4
0x18005cd6e  add     r11d, ecx
0x18005cd71  nop     dword ptr [rax+00h]
0x18005cd75  nop     word ptr [rax+rax+00000000h]
0x18005cd80  lea     rcx, [r8+r9]
0x18005cd84  movzx   edx, byte ptr [rcx+r10-10h]
0x18005cd8a  movzx   ecx, byte ptr [rcx+r12-10h]
0x18005cd90  add     edx, ecx
0x18005cd92  movzx   ecx, byte ptr [r9-10h]
0x18005cd97  add     edx, ecx
0x18005cd99  imul    ecx, edx, 55h ; 'U'
0x18005cd9c  shr     ecx, 6
0x18005cd9f  mov     [rax], cx
0x18005cda2  lea     rcx, [r8+r9]
0x18005cda6  movzx   edx, byte ptr [rcx+r10-8]
0x18005cdac  movzx   ecx, byte ptr [rcx+r12-8]
0x18005cdb2  add     edx, ecx
0x18005cdb4  movzx   ecx, byte ptr [r9-8]
0x18005cdb9  add     edx, ecx
0x18005cdbb  imul    ecx, edx, 55h ; 'U'
0x18005cdbe  shr     ecx, 6
0x18005cdc1  mov     [rax+2], cx
0x18005cdc5  lea     rcx, [r8+r9]
0x18005cdc9  movzx   edx, byte ptr [rcx+r10]
0x18005cdce  movzx   ecx, byte ptr [rcx+r12]
0x18005cdd3  add     edx, ecx
0x18005cdd5  movzx   ecx, byte ptr [r9]
0x18005cdd9  add     edx, ecx
0x18005cddb  imul    ecx, edx, 55h ; 'U'
0x18005cdde  shr     ecx, 6
0x18005cde1  mov     [rax+4], cx
0x18005cde5  lea     rcx, [r8+r9]
0x18005cde9  movzx   edx, byte ptr [rcx+r10+8]
0x18005cdef  movzx   ecx, byte ptr [rcx+r12+8]
0x18005cdf5  add     edx, ecx
0x18005cdf7  movzx   ecx, byte ptr [r9+8]
0x18005cdfc  add     edx, ecx
0x18005cdfe  imul    ecx, edx, 55h ; 'U'
0x18005ce01  shr     ecx, 6
0x18005ce04  mov     [rax+6], cx
0x18005ce08  lea     rcx, [r8+r9]
0x18005ce0c  movzx   edx, byte ptr [rcx+r10+10h]
0x18005ce12  movzx   ecx, byte ptr [rcx+r12+10h]
0x18005ce18  add     edx, ecx
0x18005ce1a  movzx   ecx, byte ptr [r9+10h]
0x18005ce1f  add     edx, ecx
0x18005ce21  imul    ecx, edx, 55h ; 'U'
0x18005ce24  shr     ecx, 6
0x18005ce27  mov     [rax+8], cx
0x18005ce2b  lea     rcx, [r8+r9]
0x18005ce2f  movzx   edx, byte ptr [rcx+r10+18h]
0x18005ce35  movzx   ecx, byte ptr [rcx+r12+18h]
0x18005ce3b  add     edx, ecx
0x18005ce3d  movzx   ecx, byte ptr [r9+18h]
0x18005ce42  add     edx, ecx
0x18005ce44  imul    ecx, edx, 55h ; 'U'
0x18005ce47  shr     ecx, 6
0x18005ce4a  mov     [rax+0Ah], cx
0x18005ce4e  lea     rcx, [r8+r9]
0x18005ce52  movzx   edx, byte ptr [rcx+r12+20h]
0x18005ce58  movzx   ecx, byte ptr [rcx+r10+20h]
0x18005ce5e  add     edx, ecx
0x18005ce60  movzx   ecx, byte ptr [r9+20h]
0x18005ce65  add     edx, ecx
0x18005ce67  imul    ecx, edx, 55h ; 'U'
0x18005ce6a  shr     ecx, 6
0x18005ce6d  mov     [rax+0Ch], cx
0x18005ce71  lea     rcx, [r8+r9]
0x18005ce75  movzx   edx, byte ptr [rcx+r10+28h]
0x18005ce7b  lea     r9, [r9+40h]
0x18005ce7f  movzx   ecx, byte ptr [rcx+r12+28h]
0x18005ce85  add     edx, ecx
0x18005ce87  movzx   ecx, byte ptr [r9-18h]
0x18005ce8c  add     edx, ecx
0x18005ce8e  imul    ecx, edx, 55h ; 'U'
0x18005ce91  shr     ecx, 6
0x18005ce94  mov     [rax+0Eh], cx
0x18005ce98  add     rax, 10h
0x18005ce9c  sub     rdi, 1
0x18005cea0  jnz     loc_18005CD80
0x18005cea6  mov     esi, [rbp+600h+var_6C]
0x18005ceac  mov     r14d, [rbp+600h+var_650]
0x18005ceb0  mov     edi, [rbp+600h+var_67C]
0x18005ceb3  cmp     r11d, edi
0x18005ceb6  jge     short loc_18005CF18
0x18005ceb8  sub     edi, r11d
0x18005cebb  lea     ecx, ds:0[r11*4]
0x18005cec3  movsxd  r8, ecx
0x18005cec6  sub     r10, r12
0x18005cec9  add     r8, r12
0x18005cecc  sub     r15, r12
0x18005cecf  lea     r9d, [rdi-1]
0x18005ced3  shr     r9d, 1
0x18005ced6  inc     r9d
0x18005ced9  nop     dword ptr [rax+00000000h]
0x18005cee0  movzx   ecx, byte ptr [r10+r8]
0x18005cee5  lea     rax, [rax+2]
0x18005cee9  movzx   edx, byte ptr [r15+r8]
0x18005ceee  lea     r8, [r8+8]
0x18005cef2  add     edx, ecx
0x18005cef4  movzx   ecx, byte ptr [r8-8]
0x18005cef9  add     edx, ecx
0x18005cefb  imul    ecx, edx, 55h ; 'U'
0x18005cefe  shr     ecx, 6
0x18005cf01  mov     [rax-2], cx
0x18005cf05  sub     r9, 1
0x18005cf09  jnz     short loc_18005CEE0
0x18005cf0b  mov     esi, [rbp+600h+var_6C]
0x18005cf11  mov     r14d, [rbp+600h+var_650]
0x18005cf15  mov     edi, [rbp+600h+var_67C]
0x18005cf18  mov     r12, [rsp+700h+var_6C0]
0x18005cf1d  mov     r15, [rsp+700h+var_6D0]
0x18005cf22  movsxd  rax, esi
0x18005cf25  inc     esi
0x18005cf27  sub     r14d, [rbp+rax*4+600h+var_644]
0x18005cf2c  mov     eax, 0
0x18005cf31  cmp     esi, [rbp+600h+var_64]
0x18005cf37  cmovge  esi, eax
0x18005cf3a  inc     [rbp+600h+var_648]
0x18005cf3d  mov     [rbp+600h+var_6C], esi
0x18005cf43  mov     rax, [rsp+700h+var_6C8]
0x18005cf48  inc     r13d
0x18005cf4b  movsxd  rax, dword ptr [rax]
0x18005cf4e  add     r12, rax
0x18005cf51  mov     eax, 0
0x18005cf56  mov     [rsp+700h+var_6C0], r12
0x18005cf5b  cmp     r13d, [rbp+600h+var_680]
0x18005cf5f  jl      loc_18005CC60
0x18005cf65  mov     r14, [rsp+700h+var_38]
0x18005cf6d  mov     rdi, [rsp+700h+var_20]
0x18005cf75  mov     rsi, [rsp+700h+var_18]
0x18005cf7d  mov     r12, [rsp+700h+var_28]
0x18005cf85  mov     r13, [rsp+700h+var_30]
0x18005cf8d  mov     rcx, [rbp+600h+var_50]
0x18005cf94  xor     rcx, rsp; StackCookie
0x18005cf97  call    __security_check_cookie
0x18005cf9c  add     rsp, 6F0h
0x18005cfa3  pop     r15
0x18005cfa5  pop     rbx
0x18005cfa6  pop     rbp
0x18005cfa7  retn
```
