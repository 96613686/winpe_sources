# Binary::IntegratedSelection::DerivativeServer<4,5,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,5,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005d3f0`
- end: `0x18005d839`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$03$04$02$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$04$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1097`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aac0`

## callees

- `0x180003180`
- `0x18005d3f0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,5,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,5,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
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
  __int64 v10; // rax
  int v11; // r13d
  unsigned __int8 *v12; // r14
  __int64 v13; // xmm1_8
  __int128 v14; // xmm0
  int v15; // esi
  int v16; // edi
  int v17; // edx
  int v18; // ecx
  int v19; // r11d
  __int64 v20; // r9
  int v21; // eax
  int v22; // r12d
  int v23; // r11d
  int v24; // r10d
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned __int8 *v28; // r11
  __int64 v29; // r10
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // ecx
  unsigned __int8 *v33; // r15
  _WORD *v34; // r9
  unsigned __int8 *v35; // r14
  int v36; // eax
  unsigned __int8 *v37; // r8
  unsigned int v38; // edx
  __int64 v39; // rdi
  unsigned __int8 *v40; // rax
  int v41; // edx
  int v42; // r12d
  int v43; // r10d
  __int64 v44; // rax
  int v45; // r10d
  unsigned int v46; // edx
  __int64 v47; // rax
  unsigned __int8 *v51; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v52[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+60h] [rbp-A0h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
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

  v5 = a1;
  *(_OWORD *)v52 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v56, 5, 3, (_DWORD)a3, (__int64)v52, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v58];
  *(_QWORD *)&v53 = &v8[v58];
  *((_QWORD *)&v53 + 1) = &v8[v58 + 1];
  v54 = (__int64)&v8[v58 + 2];
  v55 = (__int64)&v8[v58 + 3];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v59,
                  v8,
                  v52,
                  &v51);
  if ( (_BYTE)v10 )
  {
    v11 = 0;
    v12 = 0;
    v52[0] = (unsigned __int8 *)0x200000002LL;
    v51 = 0;
    LODWORD(v52[1]) = 1;
    if ( v56 > 0 )
    {
      v13 = v54;
      v14 = v53;
      v15 = v60;
      v16 = v64;
      do
      {
        v60 = ++v15;
        if ( v15 == 1 )
        {
          v17 = *(_DWORD *)(v5 + 40);
          v18 = 0;
          v19 = *(_DWORD *)(v5 + 28);
          v20 = *(int *)(v5 + 52);
          if ( v61 <= 0 )
            v18 = v61;
          v21 = *(_DWORD *)(v5 + 44);
          v22 = v57;
          if ( v19 < v21 )
            v19 = *(_DWORD *)(v5 + 44);
          v23 = v19 - v21;
          v24 = v20 - 1;
          v25 = v62;
          v53 = v14;
          if ( v62 < v17 )
            v25 = v17;
          v26 = v20 * ((v25 - v17) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v24 )
            v24 = v23;
          v27 = v24;
          v28 = &v12[*((_QWORD *)&v53 + 1)];
          v29 = v66;
          v30 = v27 + v26;
          v31 = *(_QWORD *)(v5 + 56);
          v32 = -v18;
          v33 = &v12[(_QWORD)v9];
          v34 = (_WORD *)(v31 + 2 * v30);
          v35 = &v12[v13];
          if ( v66 < 3LL )
          {
            do
            {
              if ( v32 >= v22 )
                break;
              *v34++ = (85 * (v28[4 * v32] + v35[4 * v32] + (unsigned int)v33[4 * v32])) >> 6;
              v36 = *((_DWORD *)v52 + v29++);
              v32 += v36;
            }
            while ( v29 < 3 );
            v16 = v64;
            v15 = v60;
          }
          if ( v32 < v57 - 9 )
          {
            v37 = &v33[4 * v32 + 16];
            v38 = (v57 - 9 - v32 - 1) / 0xAu + 1;
            v39 = v38;
            v32 += 10 * v38;
            do
            {
              *v34 = (85 * (*(v37 - 16) + v28[v37 - v33 - 16] + (unsigned int)v35[v37 - v33 - 16])) >> 6;
              v34[1] = (85 * (*(v37 - 8) + v28[v37 - v33 - 8] + (unsigned int)v35[v37 - v33 - 8])) >> 6;
              v34[2] = (85 * (*v37 + v28[v37 - v33] + (unsigned int)v35[v37 - v33])) >> 6;
              v34[3] = (85 * (v37[4] + v28[v37 - v33 + 4] + (unsigned int)v35[v37 - v33 + 4])) >> 6;
              v34[4] = (85 * (v37[12] + v28[v37 - v33 + 12] + (unsigned int)v35[v37 - v33 + 12])) >> 6;
              v40 = (unsigned __int8 *)(v37 - v33);
              v41 = v35[v37 - v33 + 20];
              v37 += 40;
              v34[5] = (85 * (*(v37 - 20) + (unsigned int)v28[(_QWORD)v40 + 20] + v41)) >> 6;
              v34 += 6;
              --v39;
            }
            while ( v39 );
            v16 = v64;
            v15 = v60;
          }
          v42 = v57;
          v43 = 0;
          if ( v32 < v57 )
          {
            do
            {
              *v34++ = (85 * (v33[4 * v32] + v28[4 * v32] + (unsigned int)v35[4 * v32])) >> 6;
              v44 = v43;
              v45 = v43 + 1;
              v32 += *((_DWORD *)v52 + v44);
              v46 = ((unsigned int)(((unsigned __int64)(1431655765LL * v45) >> 32) - v45) >> 31)
                  + ((int)(((unsigned __int64)(1431655765LL * v45) >> 32) - v45) >> 1);
              v43 = v45 + v46 + 2 * v46;
            }
            while ( v32 < v42 );
            v16 = v64;
            v15 = v60;
          }
          v12 = v51;
          v5 = a1;
          v47 = v16++;
          v15 -= v63[v47];
          if ( v16 >= v65 )
            v16 = 0;
          ++v62;
          v64 = v16;
        }
        ++v11;
        v10 = *a3;
        v12 += v10;
        v51 = v12;
      }
      while ( v11 < v56 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005d3f0  push    rbp
0x18005d3f2  push    rbx
0x18005d3f3  push    r12
0x18005d3f5  push    r15
0x18005d3f7  lea     rbp, [rsp-5E8h]
0x18005d3ff  sub     rsp, 6E8h
0x18005d406  mov     rax, cs:__security_cookie
0x18005d40d  xor     rax, rsp
0x18005d410  mov     [rbp+600h+var_50], rax
0x18005d417  movups  xmm0, xmmword ptr [r9]
0x18005d41b  lea     rax, [rcx+8]
0x18005d41f  mov     [rsp+700h+var_6C8], r8
0x18005d424  mov     [rsp+700h+var_6D8], rax
0x18005d429  mov     rbx, rdx
0x18005d42c  mov     edx, 5
0x18005d431  mov     [rsp+700h+var_6D0], rcx
0x18005d436  mov     r15, rcx
0x18005d439  movaps  xmmword ptr [rsp+700h+var_6B0], xmm0
0x18005d43e  lea     rax, [rsp+700h+var_6B0]
0x18005d443  mov     r9, r8
0x18005d446  lea     rcx, [rbp+600h+var_680]
0x18005d44a  mov     [rsp+700h+var_6E0], rax
0x18005d44f  lea     r8d, [rdx-2]
0x18005d453  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005d458  mov     rcx, [rbx+8]
0x18005d45c  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005d461  mov     rax, [rbx+10h]
0x18005d465  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005d46a  mov     rdx, [rbx+18h]
0x18005d46e  xor     r12d, r12d
0x18005d471  cmp     [rbx], rcx
0x18005d474  cmovbe  rcx, [rbx]
0x18005d478  mov     rbx, [rbp+600h+var_678]
0x18005d47c  cmp     rcx, rax
0x18005d47f  cmovbe  rax, rcx
0x18005d483  lea     rcx, [rbp+600h+var_670]; this
0x18005d487  cmp     rax, rdx
0x18005d48a  cmovbe  rdx, rax; unsigned __int8 *
0x18005d48e  add     rbx, rdx
0x18005d491  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005d496  lea     rax, [rbx+1]
0x18005d49a  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005d49f  lea     rax, [rbx+2]
0x18005d4a3  mov     qword ptr [rsp+700h+var_690], rax
0x18005d4a8  lea     rax, [rbx+3]
0x18005d4ac  mov     qword ptr [rsp+700h+var_690+8], rax
0x18005d4b1  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005d4b6  test    al, al
0x18005d4b8  jz      loc_18005D81C
0x18005d4be  mov     dword ptr [rsp+700h+var_6B0+4], 2
0x18005d4c6  mov     dword ptr [rsp+700h+var_6B0], 2
0x18005d4ce  movsd   xmm0, [rsp+700h+var_6B0]
0x18005d4d4  mov     [rsp+700h+var_30], r13
0x18005d4dc  mov     r13d, r12d
0x18005d4df  mov     [rsp+700h+var_38], r14
0x18005d4e7  mov     r14d, r12d
0x18005d4ea  movsd   [rsp+700h+var_6B0], xmm0
0x18005d4f0  mov     [rsp+700h+var_6C0], r12
0x18005d4f5  mov     dword ptr [rsp+700h+var_6B0+8], 1
0x18005d4fd  cmp     [rbp+600h+var_680], r12d
0x18005d501  jle     loc_18005D80C
0x18005d507  movups  xmm1, [rsp+700h+var_690]
0x18005d50c  mov     [rsp+700h+var_20], rsi
0x18005d514  movups  xmm0, [rsp+700h+var_6A0]
0x18005d519  mov     esi, [rbp+600h+var_650]
0x18005d51c  mov     [rsp+700h+var_28], rdi
0x18005d524  mov     edi, [rbp+600h+var_6C]
0x18005d52a  nop     word ptr [rax+rax+00h]
0x18005d530  inc     esi
0x18005d532  mov     [rbp+600h+var_650], esi
0x18005d535  cmp     esi, 1
0x18005d538  jnz     loc_18005D7DF
0x18005d53e  mov     edx, [r15+28h]
0x18005d542  mov     ecx, r12d
0x18005d545  mov     eax, [rbp+600h+var_64C]
0x18005d548  test    eax, eax
0x18005d54a  mov     r11d, [r15+1Ch]
0x18005d54e  movsxd  r9, dword ptr [r15+34h]
0x18005d552  cmovle  ecx, eax
0x18005d555  mov     eax, [r15+2Ch]
0x18005d559  cmp     r11d, eax
0x18005d55c  mov     r12d, [rbp+600h+var_67C]
0x18005d560  cmovl   r11d, eax
0x18005d564  sub     r11d, eax
0x18005d567  lea     r10d, [r9-1]
0x18005d56b  mov     eax, [rbp+600h+var_648]
0x18005d56e  cmp     eax, edx
0x18005d570  movups  [rsp+700h+var_6A0], xmm0
0x18005d575  cmovl   eax, edx
0x18005d578  sub     eax, edx
0x18005d57a  cdq
0x18005d57b  idiv    dword ptr [r15+30h]
0x18005d57f  movsxd  r8, edx
0x18005d582  imul    r8, r9
0x18005d586  cmp     r11d, r10d
0x18005d589  cmovle  r10d, r11d
0x18005d58d  mov     r11, qword ptr [rsp+700h+var_6A0+8]
0x18005d592  movsxd  rax, r10d
0x18005d595  add     r11, r14
0x18005d598  movsxd  r10, [rbp+600h+var_54]
0x18005d59f  add     r8, rax
0x18005d5a2  mov     rax, [r15+38h]
0x18005d5a6  neg     ecx
0x18005d5a8  lea     r15, [rbx+r14]
0x18005d5ac  lea     r9, [rax+r8*2]
0x18005d5b0  movq    rax, xmm1
0x18005d5b5  add     r14, rax
0x18005d5b8  cmp     r10, 3
0x18005d5bc  jge     short loc_18005D60C
0x18005d5be  xchg    ax, ax
0x18005d5c0  cmp     ecx, r12d
0x18005d5c3  jge     short loc_18005D603
0x18005d5c5  lea     eax, ds:0[rcx*4]
0x18005d5cc  movsxd  rdx, eax
0x18005d5cf  movzx   eax, byte ptr [rdx+r14]
0x18005d5d4  movzx   r8d, byte ptr [r15+rdx]
0x18005d5d9  add     r8d, eax
0x18005d5dc  movzx   eax, byte ptr [rdx+r11]
0x18005d5e1  add     r8d, eax
0x18005d5e4  imul    eax, r8d, 55h ; 'U'
0x18005d5e8  shr     eax, 6
0x18005d5eb  mov     [r9], ax
0x18005d5ef  add     r9, 2
0x18005d5f3  mov     eax, dword ptr [rsp+r10*4+700h+var_6B0]
0x18005d5f8  inc     r10
0x18005d5fb  add     ecx, eax
0x18005d5fd  cmp     r10, 3
0x18005d601  jl      short loc_18005D5C0
0x18005d603  mov     edi, [rbp+600h+var_6C]
0x18005d609  mov     esi, [rbp+600h+var_650]
0x18005d60c  mov     edx, [rbp+600h+var_67C]
0x18005d60f  add     edx, 0FFFFFFF7h
0x18005d612  cmp     ecx, edx
0x18005d614  jge     loc_18005D73F
0x18005d61a  sub     edx, ecx
0x18005d61c  movsxd  r8, ecx
0x18005d61f  dec     edx
0x18005d621  add     r8, 4
0x18005d625  mov     eax, 0CCCCCCCDh
0x18005d62a  mov     r10, r15
0x18005d62d  mul     edx
0x18005d62f  neg     r10
0x18005d632  lea     r8, [r15+r8*4]
0x18005d636  shr     edx, 3
0x18005d639  inc     edx
0x18005d63b  mov     edi, edx
0x18005d63d  lea     eax, [rdx+rdx*4]
0x18005d640  lea     ecx, [rcx+rax*2]
0x18005d643  nop     dword ptr [rax+00h]
0x18005d647  nop     word ptr [rax+rax+00000000h]
0x18005d650  lea     rax, [r8+r10]
0x18005d654  movzx   edx, byte ptr [rax+r14-10h]
0x18005d65a  movzx   eax, byte ptr [rax+r11-10h]
0x18005d660  add     edx, eax
0x18005d662  movzx   eax, byte ptr [r8-10h]
0x18005d667  add     edx, eax
0x18005d669  imul    eax, edx, 55h ; 'U'
0x18005d66c  shr     eax, 6
0x18005d66f  mov     [r9], ax
0x18005d673  lea     rax, [r10+r8]
0x18005d677  movzx   edx, byte ptr [rax+r14-8]
0x18005d67d  movzx   eax, byte ptr [rax+r11-8]
0x18005d683  add     edx, eax
0x18005d685  movzx   eax, byte ptr [r8-8]
0x18005d68a  add     edx, eax
0x18005d68c  imul    eax, edx, 55h ; 'U'
0x18005d68f  shr     eax, 6
0x18005d692  mov     [r9+2], ax
0x18005d697  lea     rax, [r10+r8]
0x18005d69b  movzx   edx, byte ptr [rax+r14]
0x18005d6a0  movzx   eax, byte ptr [rax+r11]
0x18005d6a5  add     edx, eax
0x18005d6a7  movzx   eax, byte ptr [r8]
0x18005d6ab  add     edx, eax
0x18005d6ad  imul    eax, edx, 55h ; 'U'
0x18005d6b0  shr     eax, 6
0x18005d6b3  mov     [r9+4], ax
0x18005d6b8  lea     rax, [r10+r8]
0x18005d6bc  movzx   edx, byte ptr [rax+r14+4]
0x18005d6c2  movzx   eax, byte ptr [rax+r11+4]
0x18005d6c8  add     edx, eax
0x18005d6ca  movzx   eax, byte ptr [r8+4]
0x18005d6cf  add     edx, eax
0x18005d6d1  imul    eax, edx, 55h ; 'U'
0x18005d6d4  shr     eax, 6
0x18005d6d7  mov     [r9+6], ax
0x18005d6dc  lea     rax, [r10+r8]
0x18005d6e0  movzx   edx, byte ptr [rax+r14+0Ch]
0x18005d6e6  movzx   eax, byte ptr [rax+r11+0Ch]
0x18005d6ec  add     edx, eax
0x18005d6ee  movzx   eax, byte ptr [r8+0Ch]
0x18005d6f3  add     edx, eax
0x18005d6f5  imul    eax, edx, 55h ; 'U'
0x18005d6f8  shr     eax, 6
0x18005d6fb  mov     [r9+8], ax
0x18005d700  lea     rax, [r8+r10]
0x18005d704  movzx   edx, byte ptr [rax+r14+14h]
0x18005d70a  lea     r8, [r8+28h]
0x18005d70e  movzx   eax, byte ptr [rax+r11+14h]
0x18005d714  add     edx, eax
0x18005d716  movzx   eax, byte ptr [r8-14h]
0x18005d71b  add     edx, eax
0x18005d71d  imul    eax, edx, 55h ; 'U'
0x18005d720  shr     eax, 6
0x18005d723  mov     [r9+0Ah], ax
0x18005d728  add     r9, 0Ch
0x18005d72c  sub     rdi, 1
0x18005d730  jnz     loc_18005D650
0x18005d736  mov     edi, [rbp+600h+var_6C]
0x18005d73c  mov     esi, [rbp+600h+var_650]
0x18005d73f  mov     r12d, [rbp+600h+var_67C]
0x18005d743  xor     r10d, r10d
0x18005d746  cmp     ecx, r12d
0x18005d749  jge     short loc_18005D7B3
0x18005d74b  nop     dword ptr [rax+rax+00h]
0x18005d750  lea     eax, ds:0[rcx*4]
0x18005d757  movsxd  rdx, eax
0x18005d75a  lea     r9, [r9+2]
0x18005d75e  movzx   eax, byte ptr [rdx+r11]
0x18005d763  movzx   r8d, byte ptr [rdx+r14]
0x18005d768  add     r8d, eax
0x18005d76b  movzx   eax, byte ptr [rdx+r15]
0x18005d770  add     r8d, eax
0x18005d773  imul    eax, r8d, 55h ; 'U'
0x18005d777  shr     eax, 6
0x18005d77a  mov     [r9-2], ax
0x18005d77f  movsxd  rax, r10d
0x18005d782  inc     r10d
0x18005d785  add     ecx, dword ptr [rsp+rax*4+700h+var_6B0]
0x18005d789  mov     eax, 55555555h
0x18005d78e  imul    r10d
0x18005d791  sub     edx, r10d
0x18005d794  sar     edx, 1
0x18005d796  mov     eax, edx
0x18005d798  shr     eax, 1Fh
0x18005d79b  add     edx, eax
0x18005d79d  lea     eax, [r10+rdx]
0x18005d7a1  lea     r10d, [rax+rdx*2]
0x18005d7a5  cmp     ecx, r12d
0x18005d7a8  jl      short loc_18005D750
0x18005d7aa  mov     edi, [rbp+600h+var_6C]
0x18005d7b0  mov     esi, [rbp+600h+var_650]
0x18005d7b3  mov     r14, [rsp+700h+var_6C0]
0x18005d7b8  mov     r12d, 0
0x18005d7be  mov     r15, [rsp+700h+var_6D0]
0x18005d7c3  movsxd  rax, edi
0x18005d7c6  inc     edi
0x18005d7c8  sub     esi, [rbp+rax*4+600h+var_644]
0x18005d7cc  cmp     edi, [rbp+600h+var_64]
0x18005d7d2  cmovge  edi, r12d
0x18005d7d6  inc     [rbp+600h+var_648]
0x18005d7d9  mov     [rbp+600h+var_6C], edi
0x18005d7df  mov     rax, [rsp+700h+var_6C8]
0x18005d7e4  inc     r13d
0x18005d7e7  movsxd  rax, dword ptr [rax]
0x18005d7ea  add     r14, rax
0x18005d7ed  mov     [rsp+700h+var_6C0], r14
0x18005d7f2  cmp     r13d, [rbp+600h+var_680]
0x18005d7f6  jl      loc_18005D530
0x18005d7fc  mov     rdi, [rsp+700h+var_28]
0x18005d804  mov     rsi, [rsp+700h+var_20]
0x18005d80c  mov     r13, [rsp+700h+var_30]
0x18005d814  mov     r14, [rsp+700h+var_38]
0x18005d81c  mov     rcx, [rbp+600h+var_50]
0x18005d823  xor     rcx, rsp; StackCookie
0x18005d826  call    __security_check_cookie
0x18005d82b  add     rsp, 6E8h
0x18005d832  pop     r15
0x18005d834  pop     r12
0x18005d836  pop     rbx
0x18005d837  pop     rbp
0x18005d838  retn
```
