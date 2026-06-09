# Binary::IntegratedSelection::DerivativeServer<16,5,3,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,5,3,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180061ec0`
- end: `0x1800624c7`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$0BA@$04$02$0A@V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$0BA@$04$02V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1543`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ab60`

## callees

- `0x180003180`
- `0x180061ec0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<16,5,3,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,5,3,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(
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
  unsigned int v38; // edx
  __int64 v39; // r14
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
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v57, 5, 3, a3, &v53, (_DWORD *)(a1 + 8));
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
    *(_QWORD *)&v53 = 0x200000002LL;
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
          if ( v32 < v58 - 9 )
          {
            v37 = (float *)&v33[16 * v32 + 64];
            v38 = (v58 - 9 - v32 - 1) / 0xAu + 1;
            v39 = v38;
            v32 += 10 * v38;
            do
            {
              *v34 = (int)fmaxf(
                            0.0,
                            fminf(
                              1023.0,
                              (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 - 64] + *(v37 - 16))
                                    + *(float *)&v35[(char *)v37 - (char *)v33 - 64])
                            * 341.0));
              v34[1] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)&v28[(char *)v37 - (char *)v33 - 32] + *(v37 - 8))
                                      + *(float *)&v35[(char *)v37 - (char *)v33 - 32])
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
              v41 = *(float *)&v28[(char *)v37 - (char *)v33 + 80] + v37[20];
              v37 += 40;
              v34[5] = (int)fmaxf(0.0, fminf(1023.0, (float)(v41 + *(float *)&v35[v40 + 80]) * 341.0));
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
0x180061ec0  push    rbp
0x180061ec2  push    rbx
0x180061ec3  push    rsi
0x180061ec4  push    r12
0x180061ec6  lea     rbp, [rsp-5E8h]
0x180061ece  sub     rsp, 6E8h
0x180061ed5  mov     rax, cs:__security_cookie
0x180061edc  xor     rax, rsp
0x180061edf  mov     [rbp+600h+var_50], rax
0x180061ee6  movups  xmm0, xmmword ptr [r9]
0x180061eea  lea     rax, [rcx+8]
0x180061eee  mov     [rsp+700h+var_6C8], r8
0x180061ef3  mov     [rsp+700h+var_6D8], rax
0x180061ef8  mov     rbx, rdx
0x180061efb  mov     edx, 5
0x180061f00  mov     [rsp+700h+var_6D0], rcx
0x180061f05  mov     rsi, rcx
0x180061f08  movaps  [rsp+700h+var_6B0], xmm0
0x180061f0d  lea     rax, [rsp+700h+var_6B0]
0x180061f12  mov     r9, r8
0x180061f15  lea     rcx, [rbp+600h+var_680]
0x180061f19  mov     [rsp+700h+var_6E0], rax
0x180061f1e  lea     r8d, [rdx-2]
0x180061f22  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180061f27  mov     rcx, [rbx+8]
0x180061f2b  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x180061f30  mov     rax, [rbx+10h]
0x180061f34  lea     r8, [rsp+700h+var_6B8]; unsigned __int8 **
0x180061f39  mov     rdx, [rbx+18h]
0x180061f3d  xor     r12d, r12d
0x180061f40  cmp     [rbx], rcx
0x180061f43  cmovbe  rcx, [rbx]
0x180061f47  mov     rbx, [rbp+600h+var_678]
0x180061f4b  cmp     rcx, rax
0x180061f4e  cmovbe  rax, rcx
0x180061f52  lea     rcx, [rbp+600h+var_670]; this
0x180061f56  cmp     rax, rdx
0x180061f59  cmovbe  rdx, rax; unsigned __int8 *
0x180061f5d  add     rbx, rdx
0x180061f60  mov     qword ptr [rsp+700h+var_6A0], rbx
0x180061f65  lea     rax, [rbx+4]
0x180061f69  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x180061f6e  lea     rax, [rbx+8]
0x180061f72  mov     qword ptr [rsp+700h+var_690], rax
0x180061f77  lea     rax, [rbx+0Ch]
0x180061f7b  mov     qword ptr [rsp+700h+var_690+8], rax
0x180061f80  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180061f85  test    al, al
0x180061f87  jz      loc_1800624AB
0x180061f8d  mov     dword ptr [rsp+700h+var_6B0+4], 2
0x180061f95  mov     dword ptr [rsp+700h+var_6B0], 2
0x180061f9d  movsd   xmm0, qword ptr [rsp+700h+var_6B0]
0x180061fa3  mov     [rsp+700h+var_20], rdi
0x180061fab  mov     edi, r12d
0x180061fae  mov     [rsp+700h+var_28], r13
0x180061fb6  mov     r13d, r12d
0x180061fb9  movsd   qword ptr [rsp+700h+var_6B0], xmm0
0x180061fbf  mov     [rsp+700h+var_6C0], r12
0x180061fc4  mov     dword ptr [rsp+700h+var_6B0+8], 1
0x180061fcc  cmp     [rbp+600h+var_680], r12d
0x180061fd0  jle     loc_18006249B
0x180061fd6  movups  xmm5, [rsp+700h+var_690]
0x180061fdb  mov     [rsp+700h+var_30], r14
0x180061fe3  movups  xmm4, [rsp+700h+var_6A0]
0x180061fe8  mov     r14d, [rbp+600h+var_6C]
0x180061fef  movss   xmm2, cs:__real@43aa8000
0x180061ff7  movss   xmm3, cs:__real@447fc000
0x180061fff  mov     [rsp+700h+var_38], r15
0x180062007  mov     r15d, [rbp+600h+var_650]
0x18006200b  nop     dword ptr [rax+rax+00h]
0x180062010  inc     r15d
0x180062013  mov     [rbp+600h+var_650], r15d
0x180062017  cmp     r15d, 1
0x18006201b  jnz     loc_18006246E
0x180062021  mov     ecx, [rsi+28h]
0x180062024  mov     r11d, r12d
0x180062027  mov     eax, [rbp+600h+var_64C]
0x18006202a  test    eax, eax
0x18006202c  mov     r10d, [rsi+1Ch]
0x180062030  movsxd  r8, dword ptr [rsi+34h]
0x180062034  cmovle  r11d, eax
0x180062038  mov     eax, [rsi+2Ch]
0x18006203b  cmp     r10d, eax
0x18006203e  movups  [rsp+700h+var_6A0], xmm4
0x180062043  cmovl   r10d, eax
0x180062047  sub     r10d, eax
0x18006204a  lea     r9d, [r8-1]
0x18006204e  mov     eax, [rbp+600h+var_648]
0x180062051  cmp     eax, ecx
0x180062053  cmovl   eax, ecx
0x180062056  sub     eax, ecx
0x180062058  cdq
0x180062059  idiv    dword ptr [rsi+30h]
0x18006205c  movsxd  rcx, edx
0x18006205f  movsxd  rdx, [rbp+600h+var_54]
0x180062066  imul    rcx, r8
0x18006206a  cmp     r10d, r9d
0x18006206d  cmovle  r9d, r10d
0x180062071  mov     r10, qword ptr [rsp+700h+var_6A0+8]
0x180062076  movsxd  rax, r9d
0x180062079  add     r10, rdi
0x18006207c  mov     r9d, [rbp+600h+var_67C]
0x180062080  add     rcx, rax
0x180062083  mov     rax, [rsi+38h]
0x180062087  neg     r11d
0x18006208a  lea     rsi, [rbx+rdi]
0x18006208e  lea     r8, [rax+rcx*2]
0x180062092  movq    rax, xmm5
0x180062097  add     rdi, rax
0x18006209a  cmp     rdx, 3
0x18006209e  jge     loc_180062235
0x1800620a4  mov     eax, 3
0x1800620a9  sub     rax, rdx
0x1800620ac  cmp     rax, 4
0x1800620b0  jl      loc_1800621E0
0x1800620b6  cmp     r11d, r9d
0x1800620b9  jge     loc_18006222A
0x1800620bf  mov     eax, r11d
0x1800620c2  movaps  xmm1, xmm3
0x1800620c5  shl     eax, 4
0x1800620c8  movsxd  rcx, eax
0x1800620cb  movss   xmm0, dword ptr [rcx+rsi]
0x1800620d0  addss   xmm0, dword ptr [rcx+r10]
0x1800620d6  addss   xmm0, dword ptr [rcx+rdi]
0x1800620db  mulss   xmm0, xmm2
0x1800620df  minss   xmm1, xmm0
0x1800620e3  xorps   xmm0, xmm0
0x1800620e6  maxss   xmm0, xmm1
0x1800620ea  cvttss2si eax, xmm0
0x1800620ee  mov     [r8], ax
0x1800620f2  add     r8, 2
0x1800620f6  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0]
0x1800620fb  cmp     r11d, r9d
0x1800620fe  jge     loc_18006222A
0x180062104  mov     eax, r11d
0x180062107  movaps  xmm1, xmm3
0x18006210a  shl     eax, 4
0x18006210d  movsxd  rcx, eax
0x180062110  movss   xmm0, dword ptr [rcx+rsi]
0x180062115  addss   xmm0, dword ptr [rcx+r10]
0x18006211b  addss   xmm0, dword ptr [rcx+rdi]
0x180062120  mulss   xmm0, xmm2
0x180062124  minss   xmm1, xmm0
0x180062128  xorps   xmm0, xmm0
0x18006212b  maxss   xmm0, xmm1
0x18006212f  cvttss2si eax, xmm0
0x180062133  mov     [r8], ax
0x180062137  add     r8, 2
0x18006213b  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+4]
0x180062140  cmp     r11d, r9d
0x180062143  jge     loc_18006222A
0x180062149  mov     eax, r11d
0x18006214c  lea     r14, [r8+2]
0x180062150  shl     eax, 4
0x180062153  movaps  xmm1, xmm3
0x180062156  movsxd  rcx, eax
0x180062159  movss   xmm0, dword ptr [rcx+rsi]
0x18006215e  addss   xmm0, dword ptr [rcx+r10]
0x180062164  addss   xmm0, dword ptr [rcx+rdi]
0x180062169  mulss   xmm0, xmm2
0x18006216d  minss   xmm1, xmm0
0x180062171  xorps   xmm0, xmm0
0x180062174  maxss   xmm0, xmm1
0x180062178  cvttss2si eax, xmm0
0x18006217c  mov     [r8], ax
0x180062180  mov     r8, r14
0x180062183  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+8]
0x180062188  cmp     r11d, r9d
0x18006218b  jge     loc_18006222A
0x180062191  mov     eax, r11d
0x180062194  lea     r8, [r14+2]
0x180062198  shl     eax, 4
0x18006219b  movaps  xmm1, xmm3
0x18006219e  movsxd  rcx, eax
0x1800621a1  movss   xmm0, dword ptr [rcx+rsi]
0x1800621a6  addss   xmm0, dword ptr [rcx+r10]
0x1800621ac  addss   xmm0, dword ptr [rcx+rdi]
0x1800621b1  mulss   xmm0, xmm2
0x1800621b5  minss   xmm1, xmm0
0x1800621b9  xorps   xmm0, xmm0
0x1800621bc  maxss   xmm0, xmm1
0x1800621c0  cvttss2si eax, xmm0
0x1800621c4  mov     [r14], ax
0x1800621c8  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0+0Ch]
0x1800621cd  add     rdx, 4
0x1800621d1  mov     rax, rdx
0x1800621d4  js      loc_1800620B6
0x1800621da  cmp     rax, 3
0x1800621de  jge     short loc_18006222A
0x1800621e0  cmp     r11d, r9d
0x1800621e3  jge     short loc_18006222A
0x1800621e5  mov     eax, r11d
0x1800621e8  movaps  xmm1, xmm3
0x1800621eb  shl     eax, 4
0x1800621ee  movsxd  rcx, eax
0x1800621f1  movss   xmm0, dword ptr [rcx+rsi]
0x1800621f6  addss   xmm0, dword ptr [rcx+r10]
0x1800621fc  addss   xmm0, dword ptr [rcx+rdi]
0x180062201  mulss   xmm0, xmm2
0x180062205  minss   xmm1, xmm0
0x180062209  xorps   xmm0, xmm0
0x18006220c  maxss   xmm0, xmm1
0x180062210  cvttss2si eax, xmm0
0x180062214  mov     [r8], ax
0x180062218  add     r8, 2
0x18006221c  add     r11d, dword ptr [rsp+rdx*4+700h+var_6B0]
0x180062221  inc     rdx
0x180062224  cmp     rdx, 3
0x180062228  jl      short loc_1800621E0
0x18006222a  mov     r14d, [rbp+600h+var_6C]
0x180062231  mov     r15d, [rbp+600h+var_650]
0x180062235  mov     edx, [rbp+600h+var_67C]
0x180062238  add     edx, 0FFFFFFF7h
0x18006223b  cmp     r11d, edx
0x18006223e  jge     loc_1800623C2
0x180062244  sub     edx, r11d
0x180062247  movsxd  rcx, r11d
0x18006224a  dec     edx
0x18006224c  add     rcx, 4
0x180062250  shl     rcx, 4
0x180062254  mov     eax, 0CCCCCCCDh
0x180062259  mul     edx
0x18006225b  mov     r9, rsi
0x18006225e  add     rcx, rsi
0x180062261  shr     edx, 3
0x180062264  neg     r9
0x180062267  inc     edx
0x180062269  mov     r14d, edx
0x18006226c  lea     eax, [rdx+rdx*4]
0x18006226f  lea     r11d, [r11+rax*2]
0x180062273  nop     dword ptr [rax+00h]
0x180062277  nop     word ptr [rax+rax+00000000h]
0x180062280  lea     rax, [r9+rcx]
0x180062284  movaps  xmm1, xmm3
0x180062287  movss   xmm0, dword ptr [rax+r10-40h]
0x18006228e  addss   xmm0, dword ptr [rcx-40h]
0x180062293  addss   xmm0, dword ptr [rax+rdi-40h]
0x180062299  mulss   xmm0, xmm2
0x18006229d  minss   xmm1, xmm0
0x1800622a1  xorps   xmm0, xmm0
0x1800622a4  maxss   xmm0, xmm1
0x1800622a8  movaps  xmm1, xmm3
0x1800622ab  cvttss2si eax, xmm0
0x1800622af  mov     [r8], ax
0x1800622b3  lea     rax, [r9+rcx]
0x1800622b7  movss   xmm0, dword ptr [rax+r10-20h]
0x1800622be  addss   xmm0, dword ptr [rcx-20h]
0x1800622c3  addss   xmm0, dword ptr [rax+rdi-20h]
0x1800622c9  mulss   xmm0, xmm2
0x1800622cd  minss   xmm1, xmm0
0x1800622d1  xorps   xmm0, xmm0
0x1800622d4  maxss   xmm0, xmm1
0x1800622d8  movaps  xmm1, xmm3
0x1800622db  cvttss2si eax, xmm0
0x1800622df  mov     [r8+2], ax
0x1800622e4  lea     rax, [r9+rcx]
0x1800622e8  movss   xmm0, dword ptr [rax+r10]
0x1800622ee  addss   xmm0, dword ptr [rcx]
0x1800622f2  addss   xmm0, dword ptr [rax+rdi]
0x1800622f7  mulss   xmm0, xmm2
0x1800622fb  minss   xmm1, xmm0
0x1800622ff  xorps   xmm0, xmm0
0x180062302  maxss   xmm0, xmm1
0x180062306  movaps  xmm1, xmm3
0x180062309  cvttss2si eax, xmm0
0x18006230d  mov     [r8+4], ax
0x180062312  lea     rax, [r9+rcx]
0x180062316  movss   xmm0, dword ptr [rax+r10+10h]
0x18006231d  addss   xmm0, dword ptr [rcx+10h]
0x180062322  addss   xmm0, dword ptr [rax+rdi+10h]
0x180062328  mulss   xmm0, xmm2
0x18006232c  minss   xmm1, xmm0
0x180062330  xorps   xmm0, xmm0
0x180062333  maxss   xmm0, xmm1
0x180062337  movaps  xmm1, xmm3
0x18006233a  cvttss2si eax, xmm0
0x18006233e  mov     [r8+6], ax
0x180062343  lea     rax, [r9+rcx]
0x180062347  movss   xmm0, dword ptr [rax+r10+30h]
0x18006234e  addss   xmm0, dword ptr [rcx+30h]
0x180062353  addss   xmm0, dword ptr [rax+rdi+30h]
0x180062359  mulss   xmm0, xmm2
0x18006235d  minss   xmm1, xmm0
0x180062361  xorps   xmm0, xmm0
0x180062364  maxss   xmm0, xmm1
0x180062368  movaps  xmm1, xmm3
0x18006236b  cvttss2si eax, xmm0
0x18006236f  mov     [r8+8], ax
0x180062374  lea     rax, [r9+rcx]
0x180062378  movss   xmm0, dword ptr [rax+r10+50h]
0x18006237f  addss   xmm0, dword ptr [rcx+50h]
0x180062384  add     rcx, 0A0h
0x18006238b  addss   xmm0, dword ptr [rax+rdi+50h]
0x180062391  mulss   xmm0, xmm2
0x180062395  minss   xmm1, xmm0
0x180062399  xorps   xmm0, xmm0
0x18006239c  maxss   xmm0, xmm1
0x1800623a0  cvttss2si eax, xmm0
0x1800623a4  mov     [r8+0Ah], ax
0x1800623a9  add     r8, 0Ch
  ... truncated ...
```
