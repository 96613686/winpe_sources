# Binary::IntegratedSelection::DerivativeServer<1,5,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,5,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005bcd0`
- end: `0x18005c10f`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$00$04$02$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$04$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1087`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa70`

## callees

- `0x180003180`
- `0x18005bcd0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<1,5,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,5,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int64 v5; // r13
  unsigned __int8 *v6; // rbx
  __int64 v7; // rsi
  bool v8; // al
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // rbx
  bool v11; // di
  bool v12; // di
  unsigned __int8 *v13; // r14
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // r14
  unsigned __int8 *v16; // xmm0_8
  __int128 v17; // xmm1
  int v18; // edi
  int v19; // esi
  unsigned __int8 *v20; // r15
  int v21; // edx
  int v22; // r11d
  int v23; // ecx
  __int64 v24; // r9
  int v25; // eax
  int v26; // r12d
  int v27; // r11d
  int v28; // r10d
  int v29; // eax
  unsigned __int8 *v30; // r11
  unsigned __int8 *v31; // r14
  __int64 v32; // r8
  int v33; // ecx
  __int64 v34; // r10
  _WORD *v35; // r9
  int v36; // eax
  __int64 v37; // r13
  unsigned __int8 *v38; // r8
  unsigned __int8 *v39; // rax
  int v40; // edx
  int v41; // r12d
  int v42; // r10d
  __int64 v43; // rax
  int v44; // r10d
  unsigned int v45; // edx
  __int64 v46; // rax
  unsigned __int8 *v50; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v51; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v52; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v54; // [rsp+70h] [rbp-90h]
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch]
  __int64 v57; // [rsp+88h] [rbp-78h]
  _BYTE v58[32]; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+B0h] [rbp-50h]
  int v60; // [rsp+B4h] [rbp-4Ch]
  int v61; // [rsp+B8h] [rbp-48h]
  _DWORD v62[374]; // [rsp+BCh] [rbp-44h]
  int v63; // [rsp+694h] [rbp+594h]
  int v64; // [rsp+69Ch] [rbp+59Ch]
  int v65; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  v52 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v55, 5, 3, a3, &v52, (_DWORD *)(a1 + 8));
  v6 = *a2;
  v7 = v57;
  v8 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v58,
         *a2,
         &v51,
         &v50);
  v9 = a2[1];
  v10 = &v6[v7];
  *(_QWORD *)&v53 = v10;
  v11 = v8;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v58,
          v9,
          &v51,
          &v50)
     && v11;
  v13 = a2[2];
  *((_QWORD *)&v53 + 1) = &v9[v7];
  LOBYTE(v14) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v58,
                  v13,
                  &v51,
                  &v50);
  if ( (_BYTE)v14 )
  {
    if ( v12 )
    {
      v14 = &v13[v7];
      v15 = 0;
      *(_QWORD *)&v52 = 0x200000002LL;
      v54 = v14;
      v51 = 0;
      DWORD2(v52) = 1;
      LODWORD(v50) = 0;
      if ( v55 > 0 )
      {
        v16 = v54;
        v17 = v53;
        v18 = v63;
        v19 = v59;
        do
        {
          v59 = ++v19;
          if ( v19 == 1 )
          {
            v20 = &v15[(_QWORD)v10];
            v21 = *(_DWORD *)(v5 + 40);
            v22 = *(_DWORD *)(v5 + 28);
            v23 = 0;
            v24 = *(int *)(v5 + 52);
            if ( v60 <= 0 )
              v23 = v60;
            v25 = *(_DWORD *)(v5 + 44);
            v26 = v56;
            if ( v22 < v25 )
              v22 = *(_DWORD *)(v5 + 44);
            v54 = v16;
            v27 = v22 - v25;
            v28 = v24 - 1;
            v29 = v61;
            v53 = v17;
            if ( v61 < v21 )
              v29 = v21;
            if ( v27 <= v28 )
              v28 = v27;
            v30 = &v15[*((_QWORD *)&v53 + 1)];
            v31 = &v15[(_QWORD)v54];
            v32 = v28 + v24 * ((v29 - v21) % *(_DWORD *)(v5 + 48));
            v33 = -v23;
            v34 = v65;
            v35 = (_WORD *)(*(_QWORD *)(v5 + 56) + 2 * v32);
            if ( v65 < 3LL )
            {
              do
              {
                if ( v33 >= v26 )
                  break;
                *v35++ = (85 * (v20[v33] + v31[v33] + (unsigned int)v30[v33])) >> 6;
                v36 = *((_DWORD *)&v52 + v34++);
                v33 += v36;
              }
              while ( v34 < 3 );
              v18 = v63;
              v19 = v59;
            }
            v37 = v56 - 9;
            if ( v33 < v37 )
            {
              v38 = &v20[v33 + 4];
              v33 += 10 * ((v56 - 9 - (__int64)v33 - 1) / 0xAuLL + 1);
              do
              {
                *v35 = (85 * (*(v38 - 4) + v31[v38 - v20 - 4] + (unsigned int)v30[v38 - v20 - 4])) >> 6;
                v35[1] = (85 * (*(v38 - 2) + v31[v38 - v20 - 2] + (unsigned int)v30[v38 - v20 - 2])) >> 6;
                v35[2] = (85 * (*v38 + v31[v38 - v20] + (unsigned int)v30[v38 - v20])) >> 6;
                v35[3] = (85 * (v38[1] + v31[v38 - v20 + 1] + (unsigned int)v30[v38 - v20 + 1])) >> 6;
                v35[4] = (85 * (v38[3] + v31[v38 - v20 + 3] + (unsigned int)v30[v38 - v20 + 3])) >> 6;
                v39 = (unsigned __int8 *)(v38 - v20);
                v40 = v30[v38 - v20 + 5];
                v38 += 10;
                v35[5] = (85 * (*(v38 - 5) + (unsigned int)v39[(_QWORD)v31 + 5] + v40)) >> 6;
                v35 += 6;
              }
              while ( v38 - 4 - v20 < v37 );
              v18 = v63;
              v19 = v59;
            }
            v41 = v56;
            v42 = 0;
            if ( v33 < v56 )
            {
              do
              {
                *v35++ = (85 * (v20[v33] + v30[v33] + (unsigned int)v31[v33])) >> 6;
                v43 = v42;
                v44 = v42 + 1;
                v33 += *((_DWORD *)&v52 + v43);
                v45 = ((unsigned int)(((unsigned __int64)(1431655765LL * v44) >> 32) - v44) >> 31)
                    + ((int)(((unsigned __int64)(1431655765LL * v44) >> 32) - v44) >> 1);
                v42 = v44 + v45 + 2 * v45;
              }
              while ( v33 < v41 );
              v18 = v63;
              v19 = v59;
            }
            v15 = v51;
            v5 = a1;
            v46 = v18++;
            v19 -= v62[v46];
            if ( v18 >= v64 )
              v18 = 0;
            ++v61;
            v63 = v18;
          }
          v15 += *a3;
          LODWORD(v14) = (_DWORD)v50 + 1;
          v51 = v15;
          LODWORD(v50) = (_DWORD)v14;
        }
        while ( (int)v14 < v55 );
      }
    }
  }
  return (char)v14;
}

```

## disassembly

```asm
0x18005bcd0  push    rbp
0x18005bcd2  push    rbx
0x18005bcd3  push    rsi
0x18005bcd4  push    rdi
0x18005bcd5  push    r12
0x18005bcd7  push    r13
0x18005bcd9  push    r14
0x18005bcdb  push    r15
0x18005bcdd  lea     rbp, [rsp-5C8h]
0x18005bce5  sub     rsp, 6C8h
0x18005bcec  mov     rax, cs:__security_cookie
0x18005bcf3  xor     rax, rsp
0x18005bcf6  mov     [rbp+600h+var_50], rax
0x18005bcfd  movups  xmm0, xmmword ptr [r9]
0x18005bd01  lea     rax, [rcx+8]
0x18005bd05  mov     [rsp+700h+var_6C8], r8
0x18005bd0a  mov     [rsp+700h+var_6D8], rax
0x18005bd0f  mov     r14, rdx
0x18005bd12  mov     edx, 5
0x18005bd17  mov     [rsp+700h+var_6D0], rcx
0x18005bd1c  mov     r13, rcx
0x18005bd1f  movaps  [rsp+700h+var_6B0], xmm0
0x18005bd24  lea     rax, [rsp+700h+var_6B0]
0x18005bd29  mov     r9, r8
0x18005bd2c  lea     rcx, [rbp+600h+var_680]
0x18005bd30  mov     [rsp+700h+var_6E0], rax
0x18005bd35  lea     r8d, [rdx-2]
0x18005bd39  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005bd3e  mov     rbx, [r14]
0x18005bd41  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005bd46  mov     rsi, [rbp+600h+var_678]
0x18005bd4a  lea     r8, [rsp+700h+var_6B8]; unsigned __int8 **
0x18005bd4f  mov     rdx, rbx; unsigned __int8 *
0x18005bd52  lea     rcx, [rbp+600h+var_670]; this
0x18005bd56  xor     r12d, r12d
0x18005bd59  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005bd5e  mov     r15, [r14+8]
0x18005bd62  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005bd67  add     rbx, rsi
0x18005bd6a  lea     r8, [rsp+700h+var_6B8]; unsigned __int8 **
0x18005bd6f  mov     rdx, r15; unsigned __int8 *
0x18005bd72  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005bd77  lea     rcx, [rbp+600h+var_670]; this
0x18005bd7b  movzx   edi, al
0x18005bd7e  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005bd83  test    al, al
0x18005bd85  jz      short loc_18005BD91
0x18005bd87  test    dil, dil
0x18005bd8a  jz      short loc_18005BD91
0x18005bd8c  mov     dil, 1
0x18005bd8f  jmp     short loc_18005BD94
0x18005bd91  xor     dil, dil
0x18005bd94  mov     r14, [r14+10h]
0x18005bd98  lea     rax, [r15+rsi]
0x18005bd9c  mov     rdx, r14; unsigned __int8 *
0x18005bd9f  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005bda4  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005bda9  lea     r8, [rsp+700h+var_6B8]; unsigned __int8 **
0x18005bdae  lea     rcx, [rbp+600h+var_670]; this
0x18005bdb2  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005bdb7  test    al, al
0x18005bdb9  jz      loc_18005C0EC
0x18005bdbf  test    dil, dil
0x18005bdc2  jz      loc_18005C0EC
0x18005bdc8  lea     rax, [r14+rsi]
0x18005bdcc  mov     dword ptr [rsp+700h+var_6B0+4], 2
0x18005bdd4  mov     r14, r12
0x18005bdd7  mov     dword ptr [rsp+700h+var_6B0], 2
0x18005bddf  movsd   xmm0, qword ptr [rsp+700h+var_6B0]
0x18005bde5  movsd   qword ptr [rsp+700h+var_6B0], xmm0
0x18005bdeb  mov     [rsp+700h+var_690], rax
0x18005bdf0  mov     [rsp+700h+var_6B8], r12
0x18005bdf5  mov     dword ptr [rsp+700h+var_6B0+8], 1
0x18005bdfd  mov     dword ptr [rsp+700h+var_6C0], r12d
0x18005be02  cmp     [rbp+600h+var_680], r12d
0x18005be06  jle     loc_18005C0EC
0x18005be0c  movsd   xmm0, [rsp+700h+var_690]
0x18005be12  movups  xmm1, [rsp+700h+var_6A0]
0x18005be17  mov     edi, [rbp+600h+var_6C]
0x18005be1d  mov     esi, [rbp+600h+var_650]
0x18005be20  inc     esi
0x18005be22  mov     [rbp+600h+var_650], esi
0x18005be25  cmp     esi, 1
0x18005be28  jnz     loc_18005C0C9
0x18005be2e  mov     eax, [rbp+600h+var_64C]
0x18005be31  lea     r15, [rbx+r14]
0x18005be35  mov     edx, [r13+28h]
0x18005be39  test    eax, eax
0x18005be3b  mov     r11d, [r13+1Ch]
0x18005be3f  mov     ecx, r12d
0x18005be42  movsxd  r9, dword ptr [r13+34h]
0x18005be46  cmovle  ecx, eax
0x18005be49  mov     eax, [r13+2Ch]
0x18005be4d  cmp     r11d, eax
0x18005be50  mov     r12d, [rbp+600h+var_67C]
0x18005be54  cmovl   r11d, eax
0x18005be58  movsd   [rsp+700h+var_690], xmm0
0x18005be5e  sub     r11d, eax
0x18005be61  lea     r10d, [r9-1]
0x18005be65  mov     eax, [rbp+600h+var_648]
0x18005be68  cmp     eax, edx
0x18005be6a  movups  [rsp+700h+var_6A0], xmm1
0x18005be6f  cmovl   eax, edx
0x18005be72  sub     eax, edx
0x18005be74  cdq
0x18005be75  idiv    dword ptr [r13+30h]
0x18005be79  movsxd  r8, edx
0x18005be7c  imul    r8, r9
0x18005be80  cmp     r11d, r10d
0x18005be83  cmovle  r10d, r11d
0x18005be87  mov     r11, qword ptr [rsp+700h+var_6A0+8]
0x18005be8c  movsxd  rax, r10d
0x18005be8f  add     r11, r14
0x18005be92  add     r14, [rsp+700h+var_690]
0x18005be97  add     r8, rax
0x18005be9a  mov     rax, [r13+38h]
0x18005be9e  neg     ecx
0x18005bea0  movsxd  r10, [rbp+600h+var_54]
0x18005bea7  lea     r9, [rax+r8*2]
0x18005beab  cmp     r10, 3
0x18005beaf  jge     short loc_18005BEF6
0x18005beb1  cmp     ecx, r12d
0x18005beb4  jge     short loc_18005BEED
0x18005beb6  movsxd  rdx, ecx
0x18005beb9  movzx   eax, byte ptr [r14+rdx]
0x18005bebe  movzx   r8d, byte ptr [r11+rdx]
0x18005bec3  add     r8d, eax
0x18005bec6  movzx   eax, byte ptr [r15+rdx]
0x18005becb  add     r8d, eax
0x18005bece  imul    eax, r8d, 55h ; 'U'
0x18005bed2  shr     eax, 6
0x18005bed5  mov     [r9], ax
0x18005bed9  add     r9, 2
0x18005bedd  mov     eax, dword ptr [rsp+r10*4+700h+var_6B0]
0x18005bee2  inc     r10
0x18005bee5  add     ecx, eax
0x18005bee7  cmp     r10, 3
0x18005beeb  jl      short loc_18005BEB1
0x18005beed  mov     edi, [rbp+600h+var_6C]
0x18005bef3  mov     esi, [rbp+600h+var_650]
0x18005bef6  mov     eax, [rbp+600h+var_67C]
0x18005bef9  add     eax, 0FFFFFFF7h
0x18005befc  movsxd  r12, ecx
0x18005beff  movsxd  r13, eax
0x18005bf02  cmp     r12, r13
0x18005bf05  jge     loc_18005C035
0x18005bf0b  mov     rdx, r13
0x18005bf0e  lea     r8, [r12+4]
0x18005bf13  sub     rdx, r12
0x18005bf16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005bf20  dec     rdx
0x18005bf23  mov     r10, r15
0x18005bf26  mul     rdx
0x18005bf29  add     r8, r15
0x18005bf2c  neg     r10
0x18005bf2f  shr     rdx, 3
0x18005bf33  inc     edx
0x18005bf35  lea     eax, [rdx+rdx*4]
0x18005bf38  lea     ecx, [rcx+rax*2]
0x18005bf3b  nop     dword ptr [rax+rax+00h]
0x18005bf40  lea     rax, [r10+r8]
0x18005bf44  movzx   edx, byte ptr [r11+rax-4]
0x18005bf4a  movzx   eax, byte ptr [r14+rax-4]
0x18005bf50  add     edx, eax
0x18005bf52  movzx   eax, byte ptr [r8-4]
0x18005bf57  add     edx, eax
0x18005bf59  imul    eax, edx, 55h ; 'U'
0x18005bf5c  shr     eax, 6
0x18005bf5f  mov     [r9], ax
0x18005bf63  lea     rax, [r10+r8]
0x18005bf67  movzx   edx, byte ptr [r11+rax-2]
0x18005bf6d  movzx   eax, byte ptr [r14+rax-2]
0x18005bf73  add     edx, eax
0x18005bf75  movzx   eax, byte ptr [r8-2]
0x18005bf7a  add     edx, eax
0x18005bf7c  imul    eax, edx, 55h ; 'U'
0x18005bf7f  shr     eax, 6
0x18005bf82  mov     [r9+2], ax
0x18005bf87  lea     rax, [r10+r8]
0x18005bf8b  movzx   edx, byte ptr [r11+rax]
0x18005bf90  movzx   eax, byte ptr [r14+rax]
0x18005bf95  add     edx, eax
0x18005bf97  movzx   eax, byte ptr [r8]
0x18005bf9b  add     edx, eax
0x18005bf9d  imul    eax, edx, 55h ; 'U'
0x18005bfa0  shr     eax, 6
0x18005bfa3  mov     [r9+4], ax
0x18005bfa8  lea     rax, [r10+r8]
0x18005bfac  movzx   edx, byte ptr [r11+rax+1]
0x18005bfb2  movzx   eax, byte ptr [r14+rax+1]
0x18005bfb8  add     edx, eax
0x18005bfba  movzx   eax, byte ptr [r8+1]
0x18005bfbf  add     edx, eax
0x18005bfc1  imul    eax, edx, 55h ; 'U'
0x18005bfc4  shr     eax, 6
0x18005bfc7  mov     [r9+6], ax
0x18005bfcc  lea     rax, [r10+r8]
0x18005bfd0  movzx   edx, byte ptr [r11+rax+3]
0x18005bfd6  movzx   eax, byte ptr [r14+rax+3]
0x18005bfdc  add     edx, eax
0x18005bfde  movzx   eax, byte ptr [r8+3]
0x18005bfe3  add     edx, eax
0x18005bfe5  imul    eax, edx, 55h ; 'U'
0x18005bfe8  shr     eax, 6
0x18005bfeb  mov     [r9+8], ax
0x18005bff0  lea     rax, [r10+r8]
0x18005bff4  movzx   edx, byte ptr [r11+rax+5]
0x18005bffa  lea     r8, [r8+0Ah]
0x18005bffe  movzx   eax, byte ptr [r14+rax+5]
0x18005c004  add     edx, eax
0x18005c006  movzx   eax, byte ptr [r8-5]
0x18005c00b  add     edx, eax
0x18005c00d  imul    eax, edx, 55h ; 'U'
0x18005c010  shr     eax, 6
0x18005c013  mov     [r9+0Ah], ax
0x18005c018  lea     rax, [r8-4]
0x18005c01c  add     rax, r10
0x18005c01f  add     r9, 0Ch
0x18005c023  cmp     rax, r13
0x18005c026  jl      loc_18005BF40
0x18005c02c  mov     edi, [rbp+600h+var_6C]
0x18005c032  mov     esi, [rbp+600h+var_650]
0x18005c035  mov     r12d, [rbp+600h+var_67C]
0x18005c039  xor     r10d, r10d
0x18005c03c  cmp     ecx, r12d
0x18005c03f  jge     short loc_18005C09D
0x18005c041  movsxd  rdx, ecx
0x18005c044  lea     r9, [r9+2]
0x18005c048  movzx   eax, byte ptr [r11+rdx]
0x18005c04d  movzx   r8d, byte ptr [r14+rdx]
0x18005c052  add     r8d, eax
0x18005c055  movzx   eax, byte ptr [r15+rdx]
0x18005c05a  add     r8d, eax
0x18005c05d  imul    eax, r8d, 55h ; 'U'
0x18005c061  shr     eax, 6
0x18005c064  mov     [r9-2], ax
0x18005c069  movsxd  rax, r10d
0x18005c06c  inc     r10d
0x18005c06f  add     ecx, dword ptr [rsp+rax*4+700h+var_6B0]
0x18005c073  mov     eax, 55555555h
0x18005c078  imul    r10d
0x18005c07b  sub     edx, r10d
0x18005c07e  sar     edx, 1
0x18005c080  mov     eax, edx
0x18005c082  shr     eax, 1Fh
0x18005c085  add     edx, eax
0x18005c087  lea     eax, [r10+rdx]
0x18005c08b  lea     r10d, [rax+rdx*2]
0x18005c08f  cmp     ecx, r12d
0x18005c092  jl      short loc_18005C041
0x18005c094  mov     edi, [rbp+600h+var_6C]
0x18005c09a  mov     esi, [rbp+600h+var_650]
0x18005c09d  mov     r14, [rsp+700h+var_6B8]
0x18005c0a2  mov     r12d, 0
0x18005c0a8  mov     r13, [rsp+700h+var_6D0]
0x18005c0ad  movsxd  rax, edi
0x18005c0b0  inc     edi
0x18005c0b2  sub     esi, [rbp+rax*4+600h+var_644]
0x18005c0b6  cmp     edi, [rbp+600h+var_64]
0x18005c0bc  cmovge  edi, r12d
0x18005c0c0  inc     [rbp+600h+var_648]
0x18005c0c3  mov     [rbp+600h+var_6C], edi
0x18005c0c9  mov     rax, [rsp+700h+var_6C8]
0x18005c0ce  movsxd  rax, dword ptr [rax]
0x18005c0d1  add     r14, rax
0x18005c0d4  mov     eax, dword ptr [rsp+700h+var_6C0]
0x18005c0d8  inc     eax
0x18005c0da  mov     [rsp+700h+var_6B8], r14
0x18005c0df  mov     dword ptr [rsp+700h+var_6C0], eax
0x18005c0e3  cmp     eax, [rbp+600h+var_680]
0x18005c0e6  jl      loc_18005BE20
0x18005c0ec  mov     rcx, [rbp+600h+var_50]
0x18005c0f3  xor     rcx, rsp; StackCookie
0x18005c0f6  call    __security_check_cookie
0x18005c0fb  add     rsp, 6C8h
0x18005c102  pop     r15
0x18005c104  pop     r14
0x18005c106  pop     r13
0x18005c108  pop     r12
0x18005c10a  pop     rdi
0x18005c10b  pop     rsi
0x18005c10c  pop     rbx
0x18005c10d  pop     rbp
0x18005c10e  retn
```
