# Binary::IntegratedSelection::DerivativeServer<16,4,3,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,4,3,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800618c0`
- end: `0x180061eb7`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$0BA@$03$02$0A@V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$0BA@$03$02V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1527`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ab50`

## callees

- `0x180003180`
- `0x1800618c0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<16,4,3,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,4,3,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  __int64 v10; // rax
  unsigned __int8 *v11; // rdi
  int v12; // r13d
  __int64 v13; // xmm5_8
  __int128 v14; // xmm4
  int v15; // r14d
  int v16; // r15d
  int v17; // ecx
  int v18; // r11d
  int v19; // r10d
  __int64 v20; // r8
  int v21; // eax
  int v22; // r10d
  int v23; // r9d
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int8 *v28; // r10
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // r11d
  unsigned __int8 *v33; // rsi
  _WORD *v34; // r8
  unsigned __int8 *v35; // rdi
  _WORD *v36; // r14
  float *v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rdx
  signed __int64 v40; // rax
  float v41; // xmm0_4
  int v42; // r12d
  int v43; // r9d
  __int64 v44; // rax
  int v45; // r9d
  unsigned int v46; // edx
  __int64 v47; // rax
  unsigned __int8 *v51; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v52; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v53; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h]
  int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch]
  __int64 v59; // [rsp+88h] [rbp-78h]
  char v60[32]; // [rsp+90h] [rbp-70h] BYREF
  int v61; // [rsp+B0h] [rbp-50h]
  int v62; // [rsp+B4h] [rbp-4Ch]
  int v63; // [rsp+B8h] [rbp-48h]
  _DWORD v64[374]; // [rsp+BCh] [rbp-44h]
  int v65; // [rsp+694h] [rbp+594h]
  int v66; // [rsp+69Ch] [rbp+59Ch]
  int v67; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  v53 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v57, 4, 3, a3, &v53, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v59];
  *(_QWORD *)&v54 = &v8[v59];
  *((_QWORD *)&v54 + 1) = &v8[v59 + 4];
  v55 = (__int64)&v8[v59 + 8];
  v56 = (__int64)&v8[v59 + 12];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v60,
                  v8,
                  &v52,
                  &v51);
  if ( (_BYTE)v10 )
  {
    v11 = 0;
    v12 = 0;
    *(_QWORD *)&v53 = 0x100000002LL;
    v51 = 0;
    DWORD2(v53) = 1;
    if ( v57 > 0 )
    {
      v13 = v55;
      v14 = v54;
      v15 = v65;
      v16 = v61;
      do
      {
        v61 = ++v16;
        if ( v16 == 1 )
        {
          v17 = *(_DWORD *)(v5 + 40);
          v18 = 0;
          v19 = *(_DWORD *)(v5 + 28);
          v20 = *(int *)(v5 + 52);
          if ( v62 <= 0 )
            v18 = v62;
          v21 = *(_DWORD *)(v5 + 44);
          v54 = v14;
          if ( v19 < v21 )
            v19 = v21;
          v22 = v19 - v21;
          v23 = v20 - 1;
          v24 = v63;
          if ( v63 < v17 )
            v24 = v17;
          v25 = v67;
          v26 = v20 * ((v24 - v17) % *(_DWORD *)(v5 + 48));
          if ( v22 <= v23 )
            v23 = v22;
          v27 = v23;
          v28 = &v11[*((_QWORD *)&v54 + 1)];
          v29 = v58;
          v30 = v27 + v26;
          v31 = *(_QWORD *)(v5 + 56);
          v32 = -v18;
          v33 = &v11[(_QWORD)v9];
          v34 = (_WORD *)(v31 + 2 * v30);
          v35 = &v11[v13];
          if ( v67 < 3LL )
          {
            if ( 3LL - v67 < 4 )
            {
              do
              {
LABEL_27:
                if ( v32 >= v29 )
                  break;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)&v33[16 * v32] + *(float *)&v28[16 * v32])
                                        + *(float *)&v35[16 * v32])
                                * 341.0));
                v32 += *((_DWORD *)&v53 + v25++);
              }
              while ( v25 < 3 );
            }
            else
            {
              while ( v32 < v29 )
              {
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)&v33[16 * v32] + *(float *)&v28[16 * v32])
                                        + *(float *)&v35[16 * v32])
                                * 341.0));
                v32 += *((_DWORD *)&v53 + v25);
                if ( v32 >= v29 )
                  break;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)&v33[16 * v32] + *(float *)&v28[16 * v32])
                                        + *(float *)&v35[16 * v32])
                                * 341.0));
                v32 += *((_DWORD *)&v53 + v25 + 1);
                if ( v32 >= v29 )
                  break;
                v36 = v34 + 1;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)&v33[16 * v32] + *(float *)&v28[16 * v32])
                                        + *(float *)&v35[16 * v32])
                                * 341.0));
                v32 += *((_DWORD *)&v53 + v25 + 2);
                if ( v32 >= v29 )
                  break;
                v34 = v36 + 1;
                *v36 = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v33[16 * v32] + *(float *)&v28[16 * v32])
                                      + *(float *)&v35[16 * v32])
                              * 341.0));
                v32 += *((_DWORD *)&v53 + v25 + 3);
                v25 += 4;
                if ( v25 >= 0 )
                {
                  if ( v25 >= 3 )
                    break;
                  goto LABEL_27;
                }
              }
            }
            v15 = v65;
            v16 = v61;
          }
          if ( v32 < v58 - 7 )
          {
            v37 = (float *)&v33[16 * v32 + 48];
            v38 = ((unsigned int)(v58 - 7 - v32 - 1) >> 3) + 1;
            v39 = v38;
            v32 += 8 * v38;
            do
            {
              *v34 = (int)fmaxf(
                            0.0,
                            fminf(
                              1023.0,
                              (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 - 48] + *(v37 - 12))
                                    + *(float *)&v35[(char *)v37 - (char *)v33 - 48])
                            * 341.0));
              v34[1] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 - 16] + *(v37 - 4))
                                      + *(float *)&v35[(char *)v37 - (char *)v33 - 16])
                              * 341.0));
              v34[2] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33] + *v37)
                                      + *(float *)&v35[(char *)v37 - (char *)v33])
                              * 341.0));
              v34[3] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 + 16] + v37[4])
                                      + *(float *)&v35[(char *)v37 - (char *)v33 + 16])
                              * 341.0));
              v34[4] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 + 48] + v37[12])
                                      + *(float *)&v35[(char *)v37 - (char *)v33 + 48])
                              * 341.0));
              v40 = (char *)v37 - (char *)v33;
              v41 = *(float *)&v28[(char *)v37 - (char *)v33 + 64] + v37[16];
              v37 += 32;
              v34[5] = (int)fmaxf(0.0, fminf(1023.0, (float)(v41 + *(float *)&v35[v40 + 64]) * 341.0));
              v34 += 6;
              --v39;
            }
            while ( v39 );
            v15 = v65;
            v16 = v61;
          }
          v42 = v58;
          v43 = 0;
          if ( v32 < v58 )
          {
            do
            {
              *v34++ = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[16 * v32] + *(float *)&v33[16 * v32])
                                      + *(float *)&v35[16 * v32])
                              * 341.0));
              v44 = v43;
              v45 = v43 + 1;
              v32 += *((_DWORD *)&v53 + v44);
              v46 = ((unsigned int)(((unsigned __int64)(1431655765LL * v45) >> 32) - v45) >> 31)
                  + ((int)(((unsigned __int64)(1431655765LL * v45) >> 32) - v45) >> 1);
              v43 = v45 + v46 + 2 * v46;
            }
            while ( v32 < v42 );
            v15 = v65;
            v16 = v61;
          }
          v11 = v51;
          v5 = a1;
          v47 = v15++;
          v16 -= v64[v47];
          if ( v15 >= v66 )
            v15 = 0;
          ++v63;
          v65 = v15;
        }
        ++v12;
        v10 = *a3;
        v11 += v10;
        v51 = v11;
      }
      while ( v12 < v57 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800618c0  push    rbp
0x1800618c2  push    rbx
0x1800618c3  push    rsi
0x1800618c4  push    r12
0x1800618c6  lea     rbp, [rsp-5E8h]
0x1800618ce  sub     rsp, 6E8h
0x1800618d5  mov     rax, cs:__security_cookie
0x1800618dc  xor     rax, rsp
0x1800618df  mov     [rbp+600h+var_50], rax
0x1800618e6  movups  xmm0, xmmword ptr [r9]
0x1800618ea  lea     rax, [rcx+8]
0x1800618ee  mov     [rsp+700h+var_6C8], r8
0x1800618f3  mov     [rsp+700h+var_6D8], rax
0x1800618f8  mov     rbx, rdx
0x1800618fb  mov     edx, 4
0x180061900  mov     [rsp+700h+var_6D0], rcx
0x180061905  mov     rsi, rcx
0x180061908  movaps  [rsp+700h+var_6B0], xmm0
0x18006190d  lea     rax, [rsp+700h+var_6B0]
0x180061912  mov     r9, r8
0x180061915  lea     rcx, [rbp+600h+var_680]
0x180061919  mov     [rsp+700h+var_6E0], rax
0x18006191e  lea     r8d, [rdx-1]
0x180061922  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180061927  mov     rcx, [rbx+8]
0x18006192b  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x180061930  mov     rax, [rbx+10h]
0x180061934  lea     r8, [rsp+700h+var_6B8]; unsigned __int8 **
0x180061939  mov     rdx, [rbx+18h]
0x18006193d  xor     r12d, r12d
0x180061940  cmp     [rbx], rcx
0x180061943  cmovbe  rcx, [rbx]
0x180061947  mov     rbx, [rbp+600h+var_678]
0x18006194b  cmp     rcx, rax
0x18006194e  cmovbe  rax, rcx
0x180061952  lea     rcx, [rbp+600h+var_670]; this
0x180061956  cmp     rax, rdx
0x180061959  cmovbe  rdx, rax; unsigned __int8 *
0x18006195d  add     rbx, rdx
0x180061960  mov     qword ptr [rsp+700h+var_6A0], rbx
0x180061965  lea     rax, [rbx+4]
0x180061969  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18006196e  lea     rax, [rbx+8]
0x180061972  mov     qword ptr [rsp+700h+var_690], rax
0x180061977  lea     rax, [rbx+0Ch]
0x18006197b  mov     qword ptr [rsp+700h+var_690+8], rax
0x180061980  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180061985  test    al, al
0x180061987  jz      loc_180061E9B
0x18006198d  mov     dword ptr [rsp+700h+var_6B0+4], 1
0x180061995  mov     dword ptr [rsp+700h+var_6B0], 2
0x18006199d  movsd   xmm0, qword ptr [rsp+700h+var_6B0]
0x1800619a3  mov     [rsp+700h+var_20], rdi
0x1800619ab  mov     edi, r12d
0x1800619ae  mov     [rsp+700h+var_28], r13
0x1800619b6  mov     r13d, r12d
0x1800619b9  movsd   qword ptr [rsp+700h+var_6B0], xmm0
0x1800619bf  mov     [rsp+700h+var_6C0], r12
0x1800619c4  mov     dword ptr [rsp+700h+var_6B0+8], 1
0x1800619cc  cmp     [rbp+600h+var_680], r12d
0x1800619d0  jle     loc_180061E8B
0x1800619d6  movups  xmm5, [rsp+700h+var_690]
0x1800619db  mov     [rsp+700h+var_30], r14
0x1800619e3  movups  xmm4, [rsp+700h+var_6A0]
0x1800619e8  mov     r14d, [rbp+600h+var_6C]
0x1800619ef  movss   xmm2, cs:__real@43aa8000
0x1800619f7  movss   xmm3, cs:__real@447fc000
0x1800619ff  mov     [rsp+700h+var_38], r15
0x180061a07  mov     r15d, [rbp+600h+var_650]
0x180061a0b  nop     dword ptr [rax+rax+00h]
0x180061a10  inc     r15d
0x180061a13  mov     [rbp+600h+var_650], r15d
0x180061a17  cmp     r15d, 1
0x180061a1b  jnz     loc_180061E5E
0x180061a21  mov     ecx, [rsi+28h]
0x180061a24  mov     r11d, r12d
0x180061a27  mov     eax, [rbp+600h+var_64C]
0x180061a2a  test    eax, eax
0x180061a2c  mov     r10d, [rsi+1Ch]
0x180061a30  movsxd  r8, dword ptr [rsi+34h]
0x180061a34  cmovle  r11d, eax
0x180061a38  mov     eax, [rsi+2Ch]
0x180061a3b  cmp     r10d, eax
0x180061a3e  movups  [rsp+700h+var_6A0], xmm4
0x180061a43  cmovl   r10d, eax
0x180061a47  sub     r10d, eax
0x180061a4a  lea     r9d, [r8-1]
0x180061a4e  mov     eax, [rbp+600h+var_648]
0x180061a51  cmp     eax, ecx
0x180061a53  cmovl   eax, ecx
0x180061a56  sub     eax, ecx
0x180061a58  cdq
0x180061a59  idiv    dword ptr [rsi+30h]
0x180061a5c  movsxd  rcx, edx
0x180061a5f  movsxd  rdx, [rbp+600h+var_54]
0x180061a66  imul    rcx, r8
0x180061a6a  cmp     r10d, r9d
0x180061a6d  cmovle  r9d, r10d
0x180061a71  mov     r10, qword ptr [rsp+700h+var_6A0+8]
0x180061a76  movsxd  rax, r9d
0x180061a79  add     r10, rdi
0x180061a7c  mov     r9d, [rbp+600h+var_67C]
0x180061a80  add     rcx, rax
0x180061a83  mov     rax, [rsi+38h]
0x180061a87  neg     r11d
0x180061a8a  lea     rsi, [rbx+rdi]
0x180061a8e  lea     r8, [rax+rcx*2]
0x180061a92  movq    rax, xmm5
0x180061a97  add     rdi, rax
0x180061a9a  cmp     rdx, 3
0x180061a9e  jge     loc_180061C35
0x180061aa4  mov     eax, 3
0x180061aa9  sub     rax, rdx
0x180061aac  cmp     rax, 4
0x180061ab0  jl      loc_180061BE0
0x180061ab6  cmp     r11d, r9d
0x180061ab9  jge     loc_180061C2A
0x180061abf  mov     eax, r11d
0x180061ac2  movaps  xmm1, xmm3
0x180061ac5  shl     eax, 4
0x180061ac8  movsxd  rcx, eax
0x180061acb  movss   xmm0, dword ptr [rcx+rsi]
0x180061ad0  addss   xmm0, dword ptr [rcx+r10]
0x180061ad6  addss   xmm0, dword ptr [rcx+rdi]
0x180061adb  mulss   xmm0, xmm2
0x180061adf  minss   xmm1, xmm0
0x180061ae3  xorps   xmm0, xmm0
0x180061ae6  maxss   xmm0, xmm1
0x180061aea  cvttss2si eax, xmm0
0x180061aee  mov     [r8], ax
0x180061af2  add     r8, 2
0x180061af6  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0]
0x180061afb  cmp     r11d, r9d
0x180061afe  jge     loc_180061C2A
0x180061b04  mov     eax, r11d
0x180061b07  movaps  xmm1, xmm3
0x180061b0a  shl     eax, 4
0x180061b0d  movsxd  rcx, eax
0x180061b10  movss   xmm0, dword ptr [rcx+rsi]
0x180061b15  addss   xmm0, dword ptr [rcx+r10]
0x180061b1b  addss   xmm0, dword ptr [rcx+rdi]
0x180061b20  mulss   xmm0, xmm2
0x180061b24  minss   xmm1, xmm0
0x180061b28  xorps   xmm0, xmm0
0x180061b2b  maxss   xmm0, xmm1
0x180061b2f  cvttss2si eax, xmm0
0x180061b33  mov     [r8], ax
0x180061b37  add     r8, 2
0x180061b3b  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+4]
0x180061b40  cmp     r11d, r9d
0x180061b43  jge     loc_180061C2A
0x180061b49  mov     eax, r11d
0x180061b4c  lea     r14, [r8+2]
0x180061b50  shl     eax, 4
0x180061b53  movaps  xmm1, xmm3
0x180061b56  movsxd  rcx, eax
0x180061b59  movss   xmm0, dword ptr [rcx+rsi]
0x180061b5e  addss   xmm0, dword ptr [rcx+r10]
0x180061b64  addss   xmm0, dword ptr [rcx+rdi]
0x180061b69  mulss   xmm0, xmm2
0x180061b6d  minss   xmm1, xmm0
0x180061b71  xorps   xmm0, xmm0
0x180061b74  maxss   xmm0, xmm1
0x180061b78  cvttss2si eax, xmm0
0x180061b7c  mov     [r8], ax
0x180061b80  mov     r8, r14
0x180061b83  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+8]
0x180061b88  cmp     r11d, r9d
0x180061b8b  jge     loc_180061C2A
0x180061b91  mov     eax, r11d
0x180061b94  lea     r8, [r14+2]
0x180061b98  shl     eax, 4
0x180061b9b  movaps  xmm1, xmm3
0x180061b9e  movsxd  rcx, eax
0x180061ba1  movss   xmm0, dword ptr [rcx+rsi]
0x180061ba6  addss   xmm0, dword ptr [rcx+r10]
0x180061bac  addss   xmm0, dword ptr [rcx+rdi]
0x180061bb1  mulss   xmm0, xmm2
0x180061bb5  minss   xmm1, xmm0
0x180061bb9  xorps   xmm0, xmm0
0x180061bbc  maxss   xmm0, xmm1
0x180061bc0  cvttss2si eax, xmm0
0x180061bc4  mov     [r14], ax
0x180061bc8  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+0Ch]
0x180061bcd  add     rdx, 4
0x180061bd1  mov     rax, rdx
0x180061bd4  js      loc_180061AB6
0x180061bda  cmp     rax, 3
0x180061bde  jge     short loc_180061C2A
0x180061be0  cmp     r11d, r9d
0x180061be3  jge     short loc_180061C2A
0x180061be5  mov     eax, r11d
0x180061be8  movaps  xmm1, xmm3
0x180061beb  shl     eax, 4
0x180061bee  movsxd  rcx, eax
0x180061bf1  movss   xmm0, dword ptr [rcx+rsi]
0x180061bf6  addss   xmm0, dword ptr [rcx+r10]
0x180061bfc  addss   xmm0, dword ptr [rcx+rdi]
0x180061c01  mulss   xmm0, xmm2
0x180061c05  minss   xmm1, xmm0
0x180061c09  xorps   xmm0, xmm0
0x180061c0c  maxss   xmm0, xmm1
0x180061c10  cvttss2si eax, xmm0
0x180061c14  mov     [r8], ax
0x180061c18  add     r8, 2
0x180061c1c  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0]
0x180061c21  inc     rdx
0x180061c24  cmp     rdx, 3
0x180061c28  jl      short loc_180061BE0
0x180061c2a  mov     r14d, [rbp+600h+var_6C]
0x180061c31  mov     r15d, [rbp+600h+var_650]
0x180061c35  mov     edx, [rbp+600h+var_67C]
0x180061c38  add     edx, 0FFFFFFF9h
0x180061c3b  cmp     r11d, edx
0x180061c3e  jge     loc_180061DAF
0x180061c44  sub     edx, r11d
0x180061c47  movsxd  rcx, r11d
0x180061c4a  add     rcx, 3
0x180061c4e  mov     r9, rsi
0x180061c51  shl     rcx, 4
0x180061c55  neg     r9
0x180061c58  add     rcx, rsi
0x180061c5b  lea     eax, [rdx-1]
0x180061c5e  shr     eax, 3
0x180061c61  inc     eax
0x180061c63  mov     edx, eax
0x180061c65  lea     r11d, [r11+rax*8]
0x180061c69  nop     dword ptr [rax+00000000h]
0x180061c70  lea     rax, [r9+rcx]
0x180061c74  movaps  xmm1, xmm3
0x180061c77  movss   xmm0, dword ptr [rax+r10-30h]
0x180061c7e  addss   xmm0, dword ptr [rcx-30h]
0x180061c83  addss   xmm0, dword ptr [rax+rdi-30h]
0x180061c89  mulss   xmm0, xmm2
0x180061c8d  minss   xmm1, xmm0
0x180061c91  xorps   xmm0, xmm0
0x180061c94  maxss   xmm0, xmm1
0x180061c98  movaps  xmm1, xmm3
0x180061c9b  cvttss2si eax, xmm0
0x180061c9f  mov     [r8], ax
0x180061ca3  lea     rax, [r9+rcx]
0x180061ca7  movss   xmm0, dword ptr [rax+r10-10h]
0x180061cae  addss   xmm0, dword ptr [rcx-10h]
0x180061cb3  addss   xmm0, dword ptr [rax+rdi-10h]
0x180061cb9  mulss   xmm0, xmm2
0x180061cbd  minss   xmm1, xmm0
0x180061cc1  xorps   xmm0, xmm0
0x180061cc4  maxss   xmm0, xmm1
0x180061cc8  movaps  xmm1, xmm3
0x180061ccb  cvttss2si eax, xmm0
0x180061ccf  mov     [r8+2], ax
0x180061cd4  lea     rax, [r9+rcx]
0x180061cd8  movss   xmm0, dword ptr [rax+r10]
0x180061cde  addss   xmm0, dword ptr [rcx]
0x180061ce2  addss   xmm0, dword ptr [rax+rdi]
0x180061ce7  mulss   xmm0, xmm2
0x180061ceb  minss   xmm1, xmm0
0x180061cef  xorps   xmm0, xmm0
0x180061cf2  maxss   xmm0, xmm1
0x180061cf6  movaps  xmm1, xmm3
0x180061cf9  cvttss2si eax, xmm0
0x180061cfd  mov     [r8+4], ax
0x180061d02  lea     rax, [r9+rcx]
0x180061d06  movss   xmm0, dword ptr [rax+r10+10h]
0x180061d0d  addss   xmm0, dword ptr [rcx+10h]
0x180061d12  addss   xmm0, dword ptr [rax+rdi+10h]
0x180061d18  mulss   xmm0, xmm2
0x180061d1c  minss   xmm1, xmm0
0x180061d20  xorps   xmm0, xmm0
0x180061d23  maxss   xmm0, xmm1
0x180061d27  movaps  xmm1, xmm3
0x180061d2a  cvttss2si eax, xmm0
0x180061d2e  mov     [r8+6], ax
0x180061d33  lea     rax, [r9+rcx]
0x180061d37  movss   xmm0, dword ptr [rax+r10+30h]
0x180061d3e  addss   xmm0, dword ptr [rcx+30h]
0x180061d43  addss   xmm0, dword ptr [rax+rdi+30h]
0x180061d49  mulss   xmm0, xmm2
0x180061d4d  minss   xmm1, xmm0
0x180061d51  xorps   xmm0, xmm0
0x180061d54  maxss   xmm0, xmm1
0x180061d58  movaps  xmm1, xmm3
0x180061d5b  cvttss2si eax, xmm0
0x180061d5f  mov     [r8+8], ax
0x180061d64  lea     rax, [r9+rcx]
0x180061d68  movss   xmm0, dword ptr [rax+r10+40h]
0x180061d6f  addss   xmm0, dword ptr [rcx+40h]
0x180061d74  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180061d78  addss   xmm0, dword ptr [rax+rdi+40h]
0x180061d7e  mulss   xmm0, xmm2
0x180061d82  minss   xmm1, xmm0
0x180061d86  xorps   xmm0, xmm0
0x180061d89  maxss   xmm0, xmm1
0x180061d8d  cvttss2si eax, xmm0
0x180061d91  mov     [r8+0Ah], ax
0x180061d96  add     r8, 0Ch
0x180061d9a  sub     rdx, 1
0x180061d9e  jnz     loc_180061C70
0x180061da4  mov     r14d, [rbp+600h+var_6C]
0x180061dab  mov     r15d, [rbp+600h+var_650]
  ... truncated ...
```
