# Binary::IntegratedSelection::DerivativeServer<16,1,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800602f0`
- end: `0x18006090e`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$0BA@$00$00$0A@V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$0BA@$00$00V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1566`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ab20`

## callees

- `0x180003180`
- `0x1800602f0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<16,1,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  bool result; // al
  __int64 v11; // r12
  int v12; // r13d
  __int64 v13; // xmm5_8
  __int128 v14; // xmm4
  int v15; // edi
  int v16; // r14d
  int v17; // r15d
  int v18; // ecx
  int v19; // r11d
  int v20; // r10d
  __int64 v21; // r8
  int v22; // eax
  int v23; // r9d
  int v24; // r10d
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r8
  int v28; // r11d
  unsigned __int8 *v29; // r10
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r9
  __int64 v33; // rsi
  _WORD *v34; // rdx
  _WORD *v35; // r14
  float *v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // r8
  float v39; // xmm0_4
  unsigned __int8 *v40; // r10
  __int64 v41; // r9
  float *v42; // rcx
  __int64 v43; // r8
  float v44; // xmm0_4
  __int64 v45; // rax
  unsigned __int8 *v48[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v49; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+80h] [rbp-80h] BYREF
  int v54; // [rsp+84h] [rbp-7Ch]
  __int64 v55; // [rsp+88h] [rbp-78h]
  char v56[32]; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+B0h] [rbp-50h]
  int v58; // [rsp+B4h] [rbp-4Ch]
  int v59; // [rsp+B8h] [rbp-48h]
  _DWORD v60[374]; // [rsp+BCh] [rbp-44h]
  int v61; // [rsp+694h] [rbp+594h]
  int v62; // [rsp+69Ch] [rbp+59Ch]
  int v63; // [rsp+6ACh] [rbp+5ACh]

  *(_OWORD *)v48 = *a4;
  v5 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v53, 1, 1, (_DWORD)a3, (__int64)v48, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v55];
  *(_QWORD *)&v50 = &v8[v55];
  *((_QWORD *)&v50 + 1) = &v8[v55 + 4];
  v51 = (__int64)&v8[v55 + 8];
  v52 = (__int64)&v8[v55 + 12];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v56,
             v8,
             &v49,
             v48);
  if ( result )
  {
    result = 0;
    v11 = 0;
    v12 = 0;
    LODWORD(v48[0]) = 1;
    if ( v53 > 0 )
    {
      v13 = v51;
      v14 = v50;
      v15 = v54;
      v16 = v61;
      v17 = v57;
      do
      {
        v57 = ++v17;
        if ( v17 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = 0;
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v58 <= 0 )
            v19 = v58;
          v22 = *(_DWORD *)(v5 + 44);
          v50 = v14;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v21 - 1;
          v24 = v20 - v22;
          v25 = v59;
          if ( v59 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          v27 = v63;
          if ( v24 <= v23 )
            v23 = v24;
          v28 = -v19;
          v29 = &v9[v11];
          v30 = v23 + v26;
          v31 = *(_QWORD *)(v5 + 56);
          v32 = v11 + v13;
          v33 = v11 + *((_QWORD *)&v50 + 1);
          v34 = (_WORD *)(v31 + 2 * v30);
          if ( v63 < 1LL )
          {
            if ( 1LL - v63 < 4 )
            {
              do
              {
LABEL_27:
                if ( v28 >= v15 )
                  break;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                        + *(float *)(16 * v28 + v32))
                                * 341.0));
                v28 += *((_DWORD *)v48 + v27++);
              }
              while ( v27 < 1 );
            }
            else
            {
              while ( v28 < v15 )
              {
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                        + *(float *)(16 * v28 + v32))
                                * 341.0));
                v28 += *((_DWORD *)v48 + v27);
                if ( v28 >= v15 )
                  break;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                        + *(float *)(16 * v28 + v32))
                                * 341.0));
                v28 += *((_DWORD *)v48 + v27 + 1);
                if ( v28 >= v15 )
                  break;
                v35 = v34 + 1;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                        + *(float *)(16 * v28 + v32))
                                * 341.0));
                v28 += *((_DWORD *)&v48[1] + v27);
                if ( v28 >= v15 )
                  break;
                v34 = v35 + 1;
                *v35 = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                      + *(float *)(16 * v28 + v32))
                              * 341.0));
                v28 += *((_DWORD *)&v48[1] + v27 + 1);
                v27 += 4;
                if ( v27 >= -2 )
                {
                  if ( v27 >= 1 )
                    break;
                  goto LABEL_27;
                }
              }
            }
            v16 = v61;
            v17 = v57;
            v15 = v54;
          }
          if ( v28 < v15 - 7 )
          {
            v36 = (float *)&v29[16 * v28 + 32];
            v37 = ((unsigned int)(v15 - 7 - v28 - 1) >> 3) + 1;
            v38 = v37;
            v28 += 8 * v37;
            do
            {
              *v34 = (int)fmaxf(
                            0.0,
                            fminf(
                              1023.0,
                              (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 - 32) + *(v36 - 8))
                                    + *(float *)((char *)v36 - (char *)v29 + v32 - 32))
                            * 341.0));
              v34[1] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 - 16) + *(v36 - 4))
                                      + *(float *)((char *)v36 - (char *)v29 + v32 - 16))
                              * 341.0));
              v34[2] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33) + *v36)
                                      + *(float *)((char *)v36 - (char *)v29 + v32))
                              * 341.0));
              v34[3] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 16) + v36[4])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 16))
                              * 341.0));
              v34[4] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 32) + v36[8])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 32))
                              * 341.0));
              v34[5] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 48) + v36[12])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 48))
                              * 341.0));
              v34[6] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 64) + v36[16])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 64))
                              * 341.0));
              v39 = (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 80) + v36[20])
                          + *(float *)((char *)v36 - (char *)v29 + v32 + 80))
                  * 341.0;
              v36 += 32;
              v34[7] = (int)fmaxf(0.0, fminf(1023.0, v39));
              v34 += 8;
              --v38;
            }
            while ( v38 );
            v16 = v61;
            v17 = v57;
            v15 = v54;
          }
          if ( v28 < v15 )
          {
            v40 = &v29[-v33];
            v41 = v32 - v33;
            v42 = (float *)(v33 + 16 * v28);
            v43 = (unsigned int)(v15 - v28);
            do
            {
              v44 = (float)(*(float *)((char *)v42 + (_QWORD)v40) + *v42) + *(float *)((char *)v42 + v41);
              v42 += 4;
              *v34++ = (int)fmaxf(0.0, fminf(1023.0, v44 * 341.0));
              --v43;
            }
            while ( v43 );
            v16 = v61;
            v17 = v57;
            v15 = v54;
          }
          v5 = a1;
          v45 = v16++;
          v17 -= v60[v45];
          if ( v16 >= v62 )
            v16 = 0;
          ++v59;
          v61 = v16;
        }
        ++v12;
        v11 += *a3;
        result = 0;
      }
      while ( v12 < v53 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800602f0  push    rbp
0x1800602f2  push    rbx
0x1800602f3  push    rsi
0x1800602f4  lea     rbp, [rsp-5F0h]
0x1800602fc  sub     rsp, 6F0h
0x180060303  mov     rax, cs:__security_cookie
0x18006030a  xor     rax, rsp
0x18006030d  mov     [rbp+600h+var_50], rax
0x180060314  movups  xmm0, xmmword ptr [r9]
0x180060318  lea     rax, [rcx+8]
0x18006031c  mov     [rsp+700h+var_6C8], r8
0x180060321  mov     [rsp+700h+var_6D8], rax
0x180060326  mov     rbx, rdx
0x180060329  mov     edx, 1
0x18006032e  mov     [rsp+700h+var_6D0], rcx
0x180060333  lea     rax, [rsp+700h+var_6C0]
0x180060338  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x18006033d  mov     rsi, rcx
0x180060340  mov     [rsp+700h+var_6E0], rax
0x180060345  mov     r9, r8
0x180060348  lea     rcx, [rbp+600h+var_680]
0x18006034c  mov     r8d, edx
0x18006034f  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180060354  mov     rcx, [rbx+8]
0x180060358  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18006035d  cmp     [rbx], rcx
0x180060360  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x180060365  mov     rax, [rbx+10h]
0x180060369  cmovbe  rcx, [rbx]
0x18006036d  mov     rdx, [rbx+18h]
0x180060371  cmp     rcx, rax
0x180060374  mov     rbx, [rbp+600h+var_678]
0x180060378  cmovbe  rax, rcx
0x18006037c  lea     rcx, [rbp+600h+var_670]; this
0x180060380  cmp     rax, rdx
0x180060383  cmovbe  rdx, rax; unsigned __int8 *
0x180060387  add     rbx, rdx
0x18006038a  mov     qword ptr [rsp+700h+var_6A8], rbx
0x18006038f  lea     rax, [rbx+4]
0x180060393  mov     qword ptr [rsp+700h+var_6A8+8], rax
0x180060398  lea     rax, [rbx+8]
0x18006039c  mov     qword ptr [rsp+700h+var_698], rax
0x1800603a1  lea     rax, [rbx+0Ch]
0x1800603a5  mov     qword ptr [rsp+700h+var_698+8], rax
0x1800603aa  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800603af  test    al, al
0x1800603b1  jz      loc_1800608F4
0x1800603b7  xor     eax, eax
0x1800603b9  mov     [rsp+700h+var_20], r12
0x1800603c1  mov     r12d, eax
0x1800603c4  mov     [rsp+700h+var_28], r13
0x1800603cc  mov     r13d, eax
0x1800603cf  mov     dword ptr [rsp+700h+var_6C0], 1
0x1800603d7  cmp     [rbp+600h+var_680], eax
0x1800603da  jle     loc_1800608E4
0x1800603e0  movups  xmm5, [rsp+700h+var_698]
0x1800603e5  mov     [rsp+700h+var_18], rdi
0x1800603ed  movups  xmm4, [rsp+700h+var_6A8]
0x1800603f2  mov     edi, [rbp+600h+var_67C]
0x1800603f5  movss   xmm2, cs:__real@43aa8000
0x1800603fd  movss   xmm3, cs:__real@447fc000
0x180060405  mov     [rsp+700h+var_30], r14
0x18006040d  mov     r14d, [rbp+600h+var_6C]
0x180060414  mov     [rsp+700h+var_38], r15
0x18006041c  mov     r15d, [rbp+600h+var_650]
0x180060420  inc     r15d
0x180060423  mov     [rbp+600h+var_650], r15d
0x180060427  cmp     r15d, 1
0x18006042b  jnz     loc_1800608AF
0x180060431  mov     ecx, [rsi+28h]
0x180060434  mov     r11d, eax
0x180060437  mov     r10d, [rsi+1Ch]
0x18006043b  mov     eax, [rbp+600h+var_64C]
0x18006043e  test    eax, eax
0x180060440  movsxd  r8, dword ptr [rsi+34h]
0x180060444  cmovle  r11d, eax
0x180060448  mov     eax, [rsi+2Ch]
0x18006044b  cmp     r10d, eax
0x18006044e  movups  [rsp+700h+var_6A8], xmm4
0x180060453  cmovl   r10d, eax
0x180060457  lea     r9d, [r8-1]
0x18006045b  sub     r10d, eax
0x18006045e  mov     eax, [rbp+600h+var_648]
0x180060461  cmp     eax, ecx
0x180060463  cmovl   eax, ecx
0x180060466  sub     eax, ecx
0x180060468  cdq
0x180060469  idiv    dword ptr [rsi+30h]
0x18006046c  movsxd  rcx, edx
0x18006046f  imul    rcx, r8
0x180060473  movsxd  r8, [rbp+600h+var_54]
0x18006047a  cmp     r10d, r9d
0x18006047d  cmovle  r9d, r10d
0x180060481  neg     r11d
0x180060484  movsxd  rax, r9d
0x180060487  lea     r10, [rbx+r12]
0x18006048b  add     rcx, rax
0x18006048e  movq    r9, xmm5
0x180060493  mov     rax, [rsi+38h]
0x180060497  add     r9, r12
0x18006049a  mov     rsi, qword ptr [rsp+700h+var_6A8+8]
0x18006049f  add     rsi, r12
0x1800604a2  lea     rdx, [rax+rcx*2]
0x1800604a6  cmp     r8, 1
0x1800604aa  jge     loc_180060649
0x1800604b0  mov     eax, 1
0x1800604b5  sub     rax, r8
0x1800604b8  cmp     rax, 4
0x1800604bc  jl      loc_1800605F1
0x1800604c2  cmp     r11d, edi
0x1800604c5  jge     loc_18006063B
0x1800604cb  mov     eax, r11d
0x1800604ce  movaps  xmm1, xmm3
0x1800604d1  shl     eax, 4
0x1800604d4  movsxd  rcx, eax
0x1800604d7  movss   xmm0, dword ptr [rcx+rsi]
0x1800604dc  addss   xmm0, dword ptr [rcx+r10]
0x1800604e2  addss   xmm0, dword ptr [rcx+r9]
0x1800604e8  mulss   xmm0, xmm2
0x1800604ec  minss   xmm1, xmm0
0x1800604f0  xorps   xmm0, xmm0
0x1800604f3  maxss   xmm0, xmm1
0x1800604f7  cvttss2si eax, xmm0
0x1800604fb  mov     [rdx], ax
0x1800604fe  add     rdx, 2
0x180060502  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0]
0x180060507  cmp     r11d, edi
0x18006050a  jge     loc_18006063B
0x180060510  mov     eax, r11d
0x180060513  movaps  xmm1, xmm3
0x180060516  shl     eax, 4
0x180060519  movsxd  rcx, eax
0x18006051c  movss   xmm0, dword ptr [rcx+rsi]
0x180060521  addss   xmm0, dword ptr [rcx+r10]
0x180060527  addss   xmm0, dword ptr [rcx+r9]
0x18006052d  mulss   xmm0, xmm2
0x180060531  minss   xmm1, xmm0
0x180060535  xorps   xmm0, xmm0
0x180060538  maxss   xmm0, xmm1
0x18006053c  cvttss2si eax, xmm0
0x180060540  mov     [rdx], ax
0x180060543  add     rdx, 2
0x180060547  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+4]
0x18006054c  cmp     r11d, edi
0x18006054f  jge     loc_18006063B
0x180060555  mov     eax, r11d
0x180060558  lea     r14, [rdx+2]
0x18006055c  shl     eax, 4
0x18006055f  movaps  xmm1, xmm3
0x180060562  movsxd  rcx, eax
0x180060565  movss   xmm0, dword ptr [rcx+rsi]
0x18006056a  addss   xmm0, dword ptr [rcx+r10]
0x180060570  addss   xmm0, dword ptr [rcx+r9]
0x180060576  mulss   xmm0, xmm2
0x18006057a  minss   xmm1, xmm0
0x18006057e  xorps   xmm0, xmm0
0x180060581  maxss   xmm0, xmm1
0x180060585  cvttss2si eax, xmm0
0x180060589  mov     [rdx], ax
0x18006058c  mov     rdx, r14
0x18006058f  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+8]
0x180060594  cmp     r11d, edi
0x180060597  jge     loc_18006063B
0x18006059d  mov     eax, r11d
0x1800605a0  lea     rdx, [r14+2]
0x1800605a4  shl     eax, 4
0x1800605a7  movaps  xmm1, xmm3
0x1800605aa  movsxd  rcx, eax
0x1800605ad  movss   xmm0, dword ptr [rcx+rsi]
0x1800605b2  addss   xmm0, dword ptr [rcx+r10]
0x1800605b8  addss   xmm0, dword ptr [rcx+r9]
0x1800605be  mulss   xmm0, xmm2
0x1800605c2  minss   xmm1, xmm0
0x1800605c6  xorps   xmm0, xmm0
0x1800605c9  maxss   xmm0, xmm1
0x1800605cd  cvttss2si eax, xmm0
0x1800605d1  mov     [r14], ax
0x1800605d5  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+0Ch]
0x1800605da  add     r8, 4
0x1800605de  mov     rax, r8
0x1800605e1  cmp     r8, 0FFFFFFFFFFFFFFFEh
0x1800605e5  jl      loc_1800604C2
0x1800605eb  cmp     rax, 1
0x1800605ef  jge     short loc_18006063B
0x1800605f1  cmp     r11d, edi
0x1800605f4  jge     short loc_18006063B
0x1800605f6  mov     eax, r11d
0x1800605f9  movaps  xmm1, xmm3
0x1800605fc  shl     eax, 4
0x1800605ff  movsxd  rcx, eax
0x180060602  movss   xmm0, dword ptr [rcx+rsi]
0x180060607  addss   xmm0, dword ptr [rcx+r10]
0x18006060d  addss   xmm0, dword ptr [rcx+r9]
0x180060613  mulss   xmm0, xmm2
0x180060617  minss   xmm1, xmm0
0x18006061b  xorps   xmm0, xmm0
0x18006061e  maxss   xmm0, xmm1
0x180060622  cvttss2si eax, xmm0
0x180060626  mov     [rdx], ax
0x180060629  add     rdx, 2
0x18006062d  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0]
0x180060632  inc     r8
0x180060635  cmp     r8, 1
0x180060639  jl      short loc_1800605F1
0x18006063b  mov     r14d, [rbp+600h+var_6C]
0x180060642  mov     r15d, [rbp+600h+var_650]
0x180060646  mov     edi, [rbp+600h+var_67C]
0x180060649  lea     r8d, [rdi-7]
0x18006064d  cmp     r11d, r8d
0x180060650  jge     loc_18006081C
0x180060656  sub     r8d, r11d
0x180060659  movsxd  rcx, r11d
0x18006065c  add     rcx, 2
0x180060660  mov     rdi, r10
0x180060663  shl     rcx, 4
0x180060667  neg     rdi
0x18006066a  add     rcx, r10
0x18006066d  lea     eax, [r8-1]
0x180060671  shr     eax, 3
0x180060674  inc     eax
0x180060676  mov     r8d, eax
0x180060679  lea     r11d, [r11+rax*8]
0x18006067d  nop     dword ptr [rax]
0x180060680  lea     rax, [rdi+rcx]
0x180060684  movaps  xmm1, xmm3
0x180060687  movss   xmm0, dword ptr [rax+rsi-20h]
0x18006068d  addss   xmm0, dword ptr [rcx-20h]
0x180060692  addss   xmm0, dword ptr [rax+r9-20h]
0x180060699  mulss   xmm0, xmm2
0x18006069d  minss   xmm1, xmm0
0x1800606a1  xorps   xmm0, xmm0
0x1800606a4  maxss   xmm0, xmm1
0x1800606a8  movaps  xmm1, xmm3
0x1800606ab  cvttss2si eax, xmm0
0x1800606af  mov     [rdx], ax
0x1800606b2  lea     rax, [rdi+rcx]
0x1800606b6  movss   xmm0, dword ptr [rax+rsi-10h]
0x1800606bc  addss   xmm0, dword ptr [rcx-10h]
0x1800606c1  addss   xmm0, dword ptr [rax+r9-10h]
0x1800606c8  mulss   xmm0, xmm2
0x1800606cc  minss   xmm1, xmm0
0x1800606d0  xorps   xmm0, xmm0
0x1800606d3  maxss   xmm0, xmm1
0x1800606d7  movaps  xmm1, xmm3
0x1800606da  cvttss2si eax, xmm0
0x1800606de  mov     [rdx+2], ax
0x1800606e2  lea     rax, [rdi+rcx]
0x1800606e6  movss   xmm0, dword ptr [rax+rsi]
0x1800606eb  addss   xmm0, dword ptr [rcx]
0x1800606ef  addss   xmm0, dword ptr [rax+r9]
0x1800606f5  mulss   xmm0, xmm2
0x1800606f9  minss   xmm1, xmm0
0x1800606fd  xorps   xmm0, xmm0
0x180060700  maxss   xmm0, xmm1
0x180060704  movaps  xmm1, xmm3
0x180060707  cvttss2si eax, xmm0
0x18006070b  mov     [rdx+4], ax
0x18006070f  lea     rax, [rdi+rcx]
0x180060713  movss   xmm0, dword ptr [rax+rsi+10h]
0x180060719  addss   xmm0, dword ptr [rcx+10h]
0x18006071e  addss   xmm0, dword ptr [rax+r9+10h]
0x180060725  mulss   xmm0, xmm2
0x180060729  minss   xmm1, xmm0
0x18006072d  xorps   xmm0, xmm0
0x180060730  maxss   xmm0, xmm1
0x180060734  movaps  xmm1, xmm3
0x180060737  cvttss2si eax, xmm0
0x18006073b  mov     [rdx+6], ax
0x18006073f  lea     rax, [rdi+rcx]
0x180060743  movss   xmm0, dword ptr [rax+rsi+20h]
0x180060749  addss   xmm0, dword ptr [rcx+20h]
0x18006074e  addss   xmm0, dword ptr [rax+r9+20h]
0x180060755  mulss   xmm0, xmm2
0x180060759  minss   xmm1, xmm0
0x18006075d  xorps   xmm0, xmm0
0x180060760  maxss   xmm0, xmm1
0x180060764  movaps  xmm1, xmm3
0x180060767  cvttss2si eax, xmm0
0x18006076b  mov     [rdx+8], ax
0x18006076f  lea     rax, [rdi+rcx]
0x180060773  movss   xmm0, dword ptr [rax+rsi+30h]
0x180060779  addss   xmm0, dword ptr [rcx+30h]
0x18006077e  addss   xmm0, dword ptr [rax+r9+30h]
0x180060785  mulss   xmm0, xmm2
0x180060789  minss   xmm1, xmm0
0x18006078d  xorps   xmm0, xmm0
0x180060790  maxss   xmm0, xmm1
0x180060794  movaps  xmm1, xmm3
0x180060797  cvttss2si eax, xmm0
0x18006079b  mov     [rdx+0Ah], ax
0x18006079f  lea     rax, [rdi+rcx]
0x1800607a3  movss   xmm0, dword ptr [rax+rsi+40h]
0x1800607a9  addss   xmm0, dword ptr [rcx+40h]
0x1800607ae  addss   xmm0, dword ptr [rax+r9+40h]
0x1800607b5  mulss   xmm0, xmm2
0x1800607b9  minss   xmm1, xmm0
0x1800607bd  xorps   xmm0, xmm0
0x1800607c0  maxss   xmm0, xmm1
0x1800607c4  cvttss2si eax, xmm0
0x1800607c8  mov     [rdx+0Ch], ax
  ... truncated ...
```
