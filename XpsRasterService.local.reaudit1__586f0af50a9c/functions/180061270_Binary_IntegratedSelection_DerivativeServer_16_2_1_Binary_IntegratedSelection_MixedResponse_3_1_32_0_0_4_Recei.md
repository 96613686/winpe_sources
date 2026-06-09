# Binary::IntegratedSelection::DerivativeServer<16,2,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180061270`
- end: `0x1800618ae`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$0BA@$01$00$0A@V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$0BA@$01$00V?$MixedResponse@$02$00$0CA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1598`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ab30`

## callees

- `0x180003180`
- `0x180061270`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<16,2,1,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,16,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,32,0>,0>,0>(
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
  __int64 v37; // r8
  float v38; // xmm0_4
  unsigned __int8 *v39; // r10
  __int64 v40; // r9
  float *v41; // rcx
  __int64 v42; // r8
  float v43; // xmm0_4
  __int64 v44; // rax
  unsigned __int8 *v47[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v48; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  int v52; // [rsp+80h] [rbp-80h] BYREF
  int v53; // [rsp+84h] [rbp-7Ch]
  __int64 v54; // [rsp+88h] [rbp-78h]
  char v55[32]; // [rsp+90h] [rbp-70h] BYREF
  int v56; // [rsp+B0h] [rbp-50h]
  int v57; // [rsp+B4h] [rbp-4Ch]
  int v58; // [rsp+B8h] [rbp-48h]
  _DWORD v59[374]; // [rsp+BCh] [rbp-44h]
  int v60; // [rsp+694h] [rbp+594h]
  int v61; // [rsp+69Ch] [rbp+59Ch]
  int v62; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v47 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v52, 2, 1, a3, v47, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v54];
  *(_QWORD *)&v49 = &v8[v54];
  *((_QWORD *)&v49 + 1) = &v8[v54 + 4];
  v50 = (__int64)&v8[v54 + 8];
  v51 = (__int64)&v8[v54 + 12];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v55,
             v8,
             &v48,
             v47);
  if ( result )
  {
    result = 0;
    v11 = 0;
    v12 = 0;
    LODWORD(v47[0]) = 2;
    if ( v52 > 0 )
    {
      v13 = v50;
      v14 = v49;
      v15 = v53;
      v16 = v60;
      v17 = v56;
      do
      {
        v56 = ++v17;
        if ( v17 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = 0;
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v57 <= 0 )
            v19 = v57;
          v22 = *(_DWORD *)(v5 + 44);
          v49 = v14;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v21 - 1;
          v24 = v20 - v22;
          v25 = v58;
          if ( v58 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          v27 = v62;
          if ( v24 <= v23 )
            v23 = v24;
          v28 = -v19;
          v29 = &v9[v11];
          v30 = v23 + v26;
          v31 = *(_QWORD *)(v5 + 56);
          v32 = v11 + v13;
          v33 = v11 + *((_QWORD *)&v49 + 1);
          v34 = (_WORD *)(v31 + 2 * v30);
          if ( v62 < 1LL )
          {
            if ( 1LL - v62 < 4 )
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
                v28 += *((_DWORD *)v47 + v27++);
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
                v28 += *((_DWORD *)v47 + v27);
                if ( v28 >= v15 )
                  break;
                *v34++ = (int)fmaxf(
                                0.0,
                                fminf(
                                  1023.0,
                                  (float)((float)(*(float *)(16 * v28 + v33) + *(float *)&v29[16 * v28])
                                        + *(float *)(16 * v28 + v32))
                                * 341.0));
                v28 += *((_DWORD *)v47 + v27 + 1);
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
                v28 += *((_DWORD *)&v47[1] + v27);
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
                v28 += *((_DWORD *)&v47[1] + v27 + 1);
                v27 += 4;
                if ( v27 >= -2 )
                {
                  if ( v27 >= 1 )
                    break;
                  goto LABEL_27;
                }
              }
            }
            v16 = v60;
            v17 = v56;
            v15 = v53;
          }
          if ( v28 < v15 - 15 )
          {
            v36 = (float *)&v29[16 * v28 + 64];
            v37 = ((unsigned int)(v15 - 15 - v28 - 1) >> 4) + 1;
            v28 += 16 * v37;
            do
            {
              *v34 = (int)fmaxf(
                            0.0,
                            fminf(
                              1023.0,
                              (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 - 64) + *(v36 - 16))
                                    + *(float *)((char *)v36 - (char *)v29 + v32 - 64))
                            * 341.0));
              v34[1] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)(v33 + (char *)v36 - (char *)v29 - 32) + *(v36 - 8))
                                      + *(float *)(v32 + (char *)v36 - (char *)v29 - 32))
                              * 341.0));
              v34[2] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)(v33 + (char *)v36 - (char *)v29) + *v36)
                                      + *(float *)(v32 + (char *)v36 - (char *)v29))
                              * 341.0));
              v34[3] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 32) + v36[8])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 32))
                              * 341.0));
              v34[4] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 64) + v36[16])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 64))
                              * 341.0));
              v34[5] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 96) + v36[24])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 96))
                              * 341.0));
              v34[6] = (int)fmaxf(
                              0.0,
                              fminf(
                                1023.0,
                                (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 128) + v36[32])
                                      + *(float *)((char *)v36 - (char *)v29 + v32 + 128))
                              * 341.0));
              v38 = (float)((float)(*(float *)((char *)v36 - (char *)v29 + v33 + 160) + v36[40])
                          + *(float *)((char *)v36 - (char *)v29 + v32 + 160))
                  * 341.0;
              v36 += 64;
              v34[7] = (int)fmaxf(0.0, fminf(1023.0, v38));
              v34 += 8;
              --v37;
            }
            while ( v37 );
            v16 = v60;
            v17 = v56;
            v15 = v53;
          }
          if ( v28 < v15 )
          {
            v39 = &v29[-v33];
            v40 = v32 - v33;
            v41 = (float *)(v33 + 16 * v28);
            v42 = ((unsigned int)(v15 - v28 - 1) >> 1) + 1;
            do
            {
              v43 = (float)(*(float *)((char *)v41 + (_QWORD)v39) + *v41) + *(float *)((char *)v41 + v40);
              v41 += 8;
              *v34++ = (int)fmaxf(0.0, fminf(1023.0, v43 * 341.0));
              --v42;
            }
            while ( v42 );
            v16 = v60;
            v17 = v56;
            v15 = v53;
          }
          v5 = a1;
          v44 = v16++;
          v17 -= v59[v44];
          if ( v16 >= v61 )
            v16 = 0;
          ++v58;
          v60 = v16;
        }
        ++v12;
        v11 += *a3;
        result = 0;
      }
      while ( v12 < v52 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180061270  push    rbp
0x180061272  push    rbx
0x180061273  push    rsi
0x180061274  lea     rbp, [rsp-5F0h]
0x18006127c  sub     rsp, 6F0h
0x180061283  mov     rax, cs:__security_cookie
0x18006128a  xor     rax, rsp
0x18006128d  mov     [rbp+600h+var_50], rax
0x180061294  movups  xmm0, xmmword ptr [r9]
0x180061298  lea     rax, [rcx+8]
0x18006129c  mov     [rsp+700h+var_6C8], r8
0x1800612a1  mov     [rsp+700h+var_6D8], rax
0x1800612a6  mov     rbx, rdx
0x1800612a9  mov     edx, 2
0x1800612ae  mov     [rsp+700h+var_6D0], rcx
0x1800612b3  mov     rsi, rcx
0x1800612b6  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x1800612bb  lea     rax, [rsp+700h+var_6C0]
0x1800612c0  mov     r9, r8
0x1800612c3  lea     rcx, [rbp+600h+var_680]
0x1800612c7  mov     [rsp+700h+var_6E0], rax
0x1800612cc  lea     r8d, [rdx-1]
0x1800612d0  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x1800612d5  mov     rcx, [rbx+8]
0x1800612d9  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x1800612de  cmp     [rbx], rcx
0x1800612e1  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x1800612e6  mov     rax, [rbx+10h]
0x1800612ea  cmovbe  rcx, [rbx]
0x1800612ee  mov     rdx, [rbx+18h]
0x1800612f2  cmp     rcx, rax
0x1800612f5  mov     rbx, [rbp+600h+var_678]
0x1800612f9  cmovbe  rax, rcx
0x1800612fd  lea     rcx, [rbp+600h+var_670]; this
0x180061301  cmp     rax, rdx
0x180061304  cmovbe  rdx, rax; unsigned __int8 *
0x180061308  add     rbx, rdx
0x18006130b  mov     qword ptr [rsp+700h+var_6A8], rbx
0x180061310  lea     rax, [rbx+4]
0x180061314  mov     qword ptr [rsp+700h+var_6A8+8], rax
0x180061319  lea     rax, [rbx+8]
0x18006131d  mov     qword ptr [rsp+700h+var_698], rax
0x180061322  lea     rax, [rbx+0Ch]
0x180061326  mov     qword ptr [rsp+700h+var_698+8], rax
0x18006132b  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180061330  test    al, al
0x180061332  jz      loc_180061894
0x180061338  xor     eax, eax
0x18006133a  mov     [rsp+700h+var_20], r12
0x180061342  mov     r12d, eax
0x180061345  mov     [rsp+700h+var_28], r13
0x18006134d  mov     r13d, eax
0x180061350  mov     dword ptr [rsp+700h+var_6C0], 2
0x180061358  cmp     [rbp+600h+var_680], eax
0x18006135b  jle     loc_180061884
0x180061361  movups  xmm5, [rsp+700h+var_698]
0x180061366  mov     [rsp+700h+var_18], rdi
0x18006136e  movups  xmm4, [rsp+700h+var_6A8]
0x180061373  mov     edi, [rbp+600h+var_67C]
0x180061376  movss   xmm2, cs:__real@43aa8000
0x18006137e  movss   xmm3, cs:__real@447fc000
0x180061386  mov     [rsp+700h+var_30], r14
0x18006138e  mov     r14d, [rbp+600h+var_6C]
0x180061395  mov     [rsp+700h+var_38], r15
0x18006139d  mov     r15d, [rbp+600h+var_650]
0x1800613a1  inc     r15d
0x1800613a4  mov     [rbp+600h+var_650], r15d
0x1800613a8  cmp     r15d, 1
0x1800613ac  jnz     loc_18006184F
0x1800613b2  mov     ecx, [rsi+28h]
0x1800613b5  mov     r11d, eax
0x1800613b8  mov     r10d, [rsi+1Ch]
0x1800613bc  mov     eax, [rbp+600h+var_64C]
0x1800613bf  test    eax, eax
0x1800613c1  movsxd  r8, dword ptr [rsi+34h]
0x1800613c5  cmovle  r11d, eax
0x1800613c9  mov     eax, [rsi+2Ch]
0x1800613cc  cmp     r10d, eax
0x1800613cf  movups  [rsp+700h+var_6A8], xmm4
0x1800613d4  cmovl   r10d, eax
0x1800613d8  lea     r9d, [r8-1]
0x1800613dc  sub     r10d, eax
0x1800613df  mov     eax, [rbp+600h+var_648]
0x1800613e2  cmp     eax, ecx
0x1800613e4  cmovl   eax, ecx
0x1800613e7  sub     eax, ecx
0x1800613e9  cdq
0x1800613ea  idiv    dword ptr [rsi+30h]
0x1800613ed  movsxd  rcx, edx
0x1800613f0  imul    rcx, r8
0x1800613f4  movsxd  r8, [rbp+600h+var_54]
0x1800613fb  cmp     r10d, r9d
0x1800613fe  cmovle  r9d, r10d
0x180061402  neg     r11d
0x180061405  movsxd  rax, r9d
0x180061408  lea     r10, [rbx+r12]
0x18006140c  add     rcx, rax
0x18006140f  movq    r9, xmm5
0x180061414  mov     rax, [rsi+38h]
0x180061418  add     r9, r12
0x18006141b  mov     rsi, qword ptr [rsp+700h+var_6A8+8]
0x180061420  add     rsi, r12
0x180061423  lea     rdx, [rax+rcx*2]
0x180061427  cmp     r8, 1
0x18006142b  jge     loc_1800615CA
0x180061431  mov     eax, 1
0x180061436  sub     rax, r8
0x180061439  cmp     rax, 4
0x18006143d  jl      loc_180061572
0x180061443  cmp     r11d, edi
0x180061446  jge     loc_1800615BC
0x18006144c  mov     eax, r11d
0x18006144f  movaps  xmm1, xmm3
0x180061452  shl     eax, 4
0x180061455  movsxd  rcx, eax
0x180061458  movss   xmm0, dword ptr [rcx+rsi]
0x18006145d  addss   xmm0, dword ptr [rcx+r10]
0x180061463  addss   xmm0, dword ptr [rcx+r9]
0x180061469  mulss   xmm0, xmm2
0x18006146d  minss   xmm1, xmm0
0x180061471  xorps   xmm0, xmm0
0x180061474  maxss   xmm0, xmm1
0x180061478  cvttss2si eax, xmm0
0x18006147c  mov     [rdx], ax
0x18006147f  add     rdx, 2
0x180061483  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0]
0x180061488  cmp     r11d, edi
0x18006148b  jge     loc_1800615BC
0x180061491  mov     eax, r11d
0x180061494  movaps  xmm1, xmm3
0x180061497  shl     eax, 4
0x18006149a  movsxd  rcx, eax
0x18006149d  movss   xmm0, dword ptr [rcx+rsi]
0x1800614a2  addss   xmm0, dword ptr [rcx+r10]
0x1800614a8  addss   xmm0, dword ptr [rcx+r9]
0x1800614ae  mulss   xmm0, xmm2
0x1800614b2  minss   xmm1, xmm0
0x1800614b6  xorps   xmm0, xmm0
0x1800614b9  maxss   xmm0, xmm1
0x1800614bd  cvttss2si eax, xmm0
0x1800614c1  mov     [rdx], ax
0x1800614c4  add     rdx, 2
0x1800614c8  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+4]
0x1800614cd  cmp     r11d, edi
0x1800614d0  jge     loc_1800615BC
0x1800614d6  mov     eax, r11d
0x1800614d9  lea     r14, [rdx+2]
0x1800614dd  shl     eax, 4
0x1800614e0  movaps  xmm1, xmm3
0x1800614e3  movsxd  rcx, eax
0x1800614e6  movss   xmm0, dword ptr [rcx+rsi]
0x1800614eb  addss   xmm0, dword ptr [rcx+r10]
0x1800614f1  addss   xmm0, dword ptr [rcx+r9]
0x1800614f7  mulss   xmm0, xmm2
0x1800614fb  minss   xmm1, xmm0
0x1800614ff  xorps   xmm0, xmm0
0x180061502  maxss   xmm0, xmm1
0x180061506  cvttss2si eax, xmm0
0x18006150a  mov     [rdx], ax
0x18006150d  mov     rdx, r14
0x180061510  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+8]
0x180061515  cmp     r11d, edi
0x180061518  jge     loc_1800615BC
0x18006151e  mov     eax, r11d
0x180061521  lea     rdx, [r14+2]
0x180061525  shl     eax, 4
0x180061528  movaps  xmm1, xmm3
0x18006152b  movsxd  rcx, eax
0x18006152e  movss   xmm0, dword ptr [rcx+rsi]
0x180061533  addss   xmm0, dword ptr [rcx+r10]
0x180061539  addss   xmm0, dword ptr [rcx+r9]
0x18006153f  mulss   xmm0, xmm2
0x180061543  minss   xmm1, xmm0
0x180061547  xorps   xmm0, xmm0
0x18006154a  maxss   xmm0, xmm1
0x18006154e  cvttss2si eax, xmm0
0x180061552  mov     [r14], ax
0x180061556  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0+0Ch]
0x18006155b  add     r8, 4
0x18006155f  mov     rax, r8
0x180061562  cmp     r8, 0FFFFFFFFFFFFFFFEh
0x180061566  jl      loc_180061443
0x18006156c  cmp     rax, 1
0x180061570  jge     short loc_1800615BC
0x180061572  cmp     r11d, edi
0x180061575  jge     short loc_1800615BC
0x180061577  mov     eax, r11d
0x18006157a  movaps  xmm1, xmm3
0x18006157d  shl     eax, 4
0x180061580  movsxd  rcx, eax
0x180061583  movss   xmm0, dword ptr [rcx+rsi]
0x180061588  addss   xmm0, dword ptr [rcx+r10]
0x18006158e  addss   xmm0, dword ptr [rcx+r9]
0x180061594  mulss   xmm0, xmm2
0x180061598  minss   xmm1, xmm0
0x18006159c  xorps   xmm0, xmm0
0x18006159f  maxss   xmm0, xmm1
0x1800615a3  cvttss2si eax, xmm0
0x1800615a7  mov     [rdx], ax
0x1800615aa  add     rdx, 2
0x1800615ae  add     r11d, dword ptr [rsp+r8*4+700h+var_6C0]
0x1800615b3  inc     r8
0x1800615b6  cmp     r8, 1
0x1800615ba  jl      short loc_180061572
0x1800615bc  mov     r14d, [rbp+600h+var_6C]
0x1800615c3  mov     r15d, [rbp+600h+var_650]
0x1800615c7  mov     edi, [rbp+600h+var_67C]
0x1800615ca  lea     r8d, [rdi-0Fh]
0x1800615ce  cmp     r11d, r8d
0x1800615d1  jge     loc_1800617B1
0x1800615d7  sub     r8d, r11d
0x1800615da  movsxd  rcx, r11d
0x1800615dd  add     rcx, 4
0x1800615e1  mov     rdi, r10
0x1800615e4  shl     rcx, 4
0x1800615e8  neg     rdi
0x1800615eb  add     rcx, r10
0x1800615ee  lea     eax, [r8-1]
0x1800615f2  shr     eax, 4
0x1800615f5  inc     eax
0x1800615f7  mov     r8d, eax
0x1800615fa  shl     eax, 4
0x1800615fd  add     r11d, eax
0x180061600  lea     rax, [rcx+rdi]
0x180061604  movaps  xmm1, xmm3
0x180061607  movss   xmm0, dword ptr [rax+rsi-40h]
0x18006160d  addss   xmm0, dword ptr [rcx-40h]
0x180061612  addss   xmm0, dword ptr [rax+r9-40h]
0x180061619  mulss   xmm0, xmm2
0x18006161d  minss   xmm1, xmm0
0x180061621  xorps   xmm0, xmm0
0x180061624  maxss   xmm0, xmm1
0x180061628  movaps  xmm1, xmm3
0x18006162b  cvttss2si eax, xmm0
0x18006162f  mov     [rdx], ax
0x180061632  lea     rax, [rcx+rdi]
0x180061636  movss   xmm0, dword ptr [rsi+rax-20h]
0x18006163c  addss   xmm0, dword ptr [rcx-20h]
0x180061641  addss   xmm0, dword ptr [r9+rax-20h]
0x180061648  mulss   xmm0, xmm2
0x18006164c  minss   xmm1, xmm0
0x180061650  xorps   xmm0, xmm0
0x180061653  maxss   xmm0, xmm1
0x180061657  movaps  xmm1, xmm3
0x18006165a  cvttss2si eax, xmm0
0x18006165e  mov     [rdx+2], ax
0x180061662  lea     rax, [rcx+rdi]
0x180061666  movss   xmm0, dword ptr [rsi+rax]
0x18006166b  addss   xmm0, dword ptr [rcx]
0x18006166f  addss   xmm0, dword ptr [r9+rax]
0x180061675  mulss   xmm0, xmm2
0x180061679  minss   xmm1, xmm0
0x18006167d  xorps   xmm0, xmm0
0x180061680  maxss   xmm0, xmm1
0x180061684  movaps  xmm1, xmm3
0x180061687  cvttss2si eax, xmm0
0x18006168b  mov     [rdx+4], ax
0x18006168f  lea     rax, [rcx+rdi]
0x180061693  movss   xmm0, dword ptr [rax+rsi+20h]
0x180061699  addss   xmm0, dword ptr [rcx+20h]
0x18006169e  addss   xmm0, dword ptr [rax+r9+20h]
0x1800616a5  mulss   xmm0, xmm2
0x1800616a9  minss   xmm1, xmm0
0x1800616ad  xorps   xmm0, xmm0
0x1800616b0  maxss   xmm0, xmm1
0x1800616b4  movaps  xmm1, xmm3
0x1800616b7  cvttss2si eax, xmm0
0x1800616bb  mov     [rdx+6], ax
0x1800616bf  lea     rax, [rcx+rdi]
0x1800616c3  movss   xmm0, dword ptr [rax+rsi+40h]
0x1800616c9  addss   xmm0, dword ptr [rcx+40h]
0x1800616ce  addss   xmm0, dword ptr [rax+r9+40h]
0x1800616d5  mulss   xmm0, xmm2
0x1800616d9  minss   xmm1, xmm0
0x1800616dd  xorps   xmm0, xmm0
0x1800616e0  maxss   xmm0, xmm1
0x1800616e4  movaps  xmm1, xmm3
0x1800616e7  cvttss2si eax, xmm0
0x1800616eb  mov     [rdx+8], ax
0x1800616ef  lea     rax, [rcx+rdi]
0x1800616f3  movss   xmm0, dword ptr [rax+rsi+60h]
0x1800616f9  addss   xmm0, dword ptr [rcx+60h]
0x1800616fe  addss   xmm0, dword ptr [rax+r9+60h]
0x180061705  mulss   xmm0, xmm2
0x180061709  minss   xmm1, xmm0
0x18006170d  xorps   xmm0, xmm0
0x180061710  maxss   xmm0, xmm1
0x180061714  movaps  xmm1, xmm3
0x180061717  cvttss2si eax, xmm0
0x18006171b  mov     [rdx+0Ah], ax
0x18006171f  lea     rax, [rcx+rdi]
0x180061723  movss   xmm0, dword ptr [rax+rsi+80h]
0x18006172c  addss   xmm0, dword ptr [rcx+80h]
0x180061734  addss   xmm0, dword ptr [rax+r9+80h]
0x18006173e  mulss   xmm0, xmm2
0x180061742  minss   xmm1, xmm0
0x180061746  xorps   xmm0, xmm0
0x180061749  maxss   xmm0, xmm1
0x18006174d  cvttss2si eax, xmm0
0x180061751  mov     [rdx+0Ch], ax
  ... truncated ...
```
