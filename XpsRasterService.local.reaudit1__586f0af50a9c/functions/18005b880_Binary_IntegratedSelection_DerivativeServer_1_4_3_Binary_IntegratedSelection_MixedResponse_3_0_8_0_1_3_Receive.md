# Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,4,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005b880`
- end: `0x18005bcc2`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$00$03$02$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$03$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa60`

## callees

- `0x180003180`
- `0x18005b880`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,4,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r12
  unsigned __int8 *v6; // rbx
  __int64 v7; // rsi
  bool v8; // al
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // rbx
  bool v11; // di
  bool v12; // di
  unsigned __int8 *v13; // r14
  bool result; // al
  unsigned __int8 *v15; // r14
  int v16; // r13d
  unsigned __int8 *v17; // xmm0_8
  __int128 v18; // xmm1
  int v19; // edi
  int v20; // esi
  int v21; // edx
  unsigned __int8 *v22; // r15
  int v23; // r11d
  int v24; // ecx
  __int64 v25; // r9
  int v26; // eax
  int v27; // r10d
  int v28; // r11d
  int v29; // eax
  unsigned __int8 *v30; // r11
  unsigned __int8 *v31; // r14
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // ecx
  __int64 v35; // r10
  int v36; // r12d
  _WORD *v37; // r9
  int v38; // eax
  __int64 v39; // r12
  unsigned __int8 *v40; // r8
  unsigned __int8 *v41; // rax
  int v42; // edx
  int v43; // r12d
  int v44; // r10d
  __int64 v45; // rax
  int v46; // r10d
  unsigned int v47; // edx
  __int64 v48; // rax
  unsigned __int8 *v51[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v52; // [rsp+50h] [rbp-B0h] BYREF
  int v53; // [rsp+58h] [rbp-A8h]
  __int128 v54; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+84h] [rbp-7Ch]
  __int64 v58; // [rsp+88h] [rbp-78h]
  _BYTE v59[32]; // [rsp+90h] [rbp-70h] BYREF
  int v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+B4h] [rbp-4Ch]
  int v62; // [rsp+B8h] [rbp-48h]
  _DWORD v63[374]; // [rsp+BCh] [rbp-44h]
  int v64; // [rsp+694h] [rbp+594h]
  int v65; // [rsp+69Ch] [rbp+59Ch]
  int v66; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v51 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v56, 4, 3, a3, v51, (_DWORD *)(a1 + 8));
  v6 = *a2;
  v7 = v58;
  v8 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v59,
         *a2,
         v51,
         &v52);
  v9 = a2[1];
  v10 = &v6[v7];
  *(_QWORD *)&v54 = v10;
  v11 = v8;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v59,
          v9,
          v51,
          &v52)
     && v11;
  v13 = a2[2];
  *((_QWORD *)&v54 + 1) = &v9[v7];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v59,
             v13,
             v51,
             &v52);
  if ( result && v12 )
  {
    v55 = &v13[v7];
    result = 0;
    v15 = 0;
    v16 = 0;
    v51[0] = 0;
    v52 = (unsigned __int8 *)0x100000002LL;
    v53 = 1;
    if ( v56 > 0 )
    {
      v17 = v55;
      v18 = v54;
      v19 = v64;
      v20 = v60;
      do
      {
        v60 = ++v20;
        if ( v20 == 1 )
        {
          v21 = *(_DWORD *)(v5 + 40);
          v22 = &v15[(_QWORD)v10];
          v23 = *(_DWORD *)(v5 + 28);
          v24 = 0;
          v25 = *(int *)(v5 + 52);
          if ( v61 <= 0 )
            v24 = v61;
          v55 = v17;
          v26 = *(_DWORD *)(v5 + 44);
          v54 = v18;
          if ( v23 < v26 )
            v23 = v26;
          v27 = v25 - 1;
          v28 = v23 - v26;
          v29 = v62;
          if ( v62 < v21 )
            v29 = v21;
          if ( v28 <= v27 )
            v27 = v28;
          v30 = &v15[*((_QWORD *)&v54 + 1)];
          v31 = &v15[(_QWORD)v55];
          v32 = v27 + v25 * ((v29 - v21) % *(_DWORD *)(v5 + 48));
          v33 = *(_QWORD *)(v5 + 56);
          v34 = -v24;
          v35 = v66;
          v36 = v57;
          v37 = (_WORD *)(v33 + 2 * v32);
          if ( v66 < 3LL )
          {
            do
            {
              if ( v34 >= v36 )
                break;
              *v37++ = (85 * (v31[v34] + v30[v34] + (unsigned int)v22[v34])) >> 6;
              v38 = *((_DWORD *)&v52 + v35++);
              v34 += v38;
            }
            while ( v35 < 3 );
            v19 = v64;
            v20 = v60;
          }
          v39 = v57 - 7;
          if ( v34 < v39 )
          {
            v40 = &v22[v34 + 3];
            v34 += 8 * ((unsigned __int64)(v57 - 7 - (__int64)v34 - 1) >> 3) + 8;
            do
            {
              *v37 = (85 * (*(v40 - 3) + v31[v40 - v22 - 3] + (unsigned int)v30[v40 - v22 - 3])) >> 6;
              v37[1] = (85 * (*(v40 - 1) + v31[v40 - v22 - 1] + (unsigned int)v30[v40 - v22 - 1])) >> 6;
              v37[2] = (85 * (*v40 + v31[v40 - v22] + (unsigned int)v30[v40 - v22])) >> 6;
              v37[3] = (85 * (v40[1] + v31[v40 - v22 + 1] + (unsigned int)v30[v40 - v22 + 1])) >> 6;
              v37[4] = (85 * (v40[3] + v31[v40 - v22 + 3] + (unsigned int)v30[v40 - v22 + 3])) >> 6;
              v41 = (unsigned __int8 *)(v40 - v22);
              v42 = v30[v40 - v22 + 4];
              v40 += 8;
              v37[5] = (85 * (*(v40 - 4) + (unsigned int)v41[(_QWORD)v31 + 4] + v42)) >> 6;
              v37 += 6;
            }
            while ( v40 - 3 - v22 < v39 );
            v19 = v64;
            v20 = v60;
          }
          v43 = v57;
          v44 = 0;
          if ( v34 < v57 )
          {
            do
            {
              *v37++ = (85 * (v22[v34] + v30[v34] + (unsigned int)v31[v34])) >> 6;
              v45 = v44;
              v46 = v44 + 1;
              v34 += *((_DWORD *)&v52 + v45);
              v47 = ((unsigned int)(((unsigned __int64)(1431655765LL * v46) >> 32) - v46) >> 31)
                  + ((int)(((unsigned __int64)(1431655765LL * v46) >> 32) - v46) >> 1);
              v44 = v46 + v47 + 2 * v47;
            }
            while ( v34 < v43 );
            v19 = v64;
            v20 = v60;
          }
          v15 = v51[0];
          v5 = a1;
          v48 = v19++;
          v20 -= v63[v48];
          if ( v19 >= v65 )
            v19 = 0;
          ++v62;
          v64 = v19;
        }
        ++v16;
        v15 += *a3;
        result = 0;
        v51[0] = v15;
      }
      while ( v16 < v56 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005b880  push    rbp
0x18005b882  push    rbx
0x18005b883  push    rsi
0x18005b884  push    rdi
0x18005b885  push    r12
0x18005b887  push    r14
0x18005b889  push    r15
0x18005b88b  lea     rbp, [rsp-5D0h]
0x18005b893  sub     rsp, 6D0h
0x18005b89a  mov     rax, cs:__security_cookie
0x18005b8a1  xor     rax, rsp
0x18005b8a4  mov     [rbp+600h+var_50], rax
0x18005b8ab  movups  xmm0, xmmword ptr [r9]
0x18005b8af  lea     rax, [rcx+8]
0x18005b8b3  mov     [rsp+700h+var_6C8], r8
0x18005b8b8  mov     [rsp+700h+var_6D8], rax
0x18005b8bd  mov     r14, rdx
0x18005b8c0  mov     edx, 4
0x18005b8c5  mov     [rsp+700h+var_6D0], rcx
0x18005b8ca  mov     r12, rcx
0x18005b8cd  movaps  xmmword ptr [rsp+700h+var_6C0], xmm0
0x18005b8d2  lea     rax, [rsp+700h+var_6C0]
0x18005b8d7  mov     r9, r8
0x18005b8da  lea     rcx, [rbp+600h+var_680]
0x18005b8de  mov     [rsp+700h+var_6E0], rax
0x18005b8e3  lea     r8d, [rdx-1]
0x18005b8e7  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005b8ec  mov     rbx, [r14]
0x18005b8ef  lea     r9, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b8f4  mov     rsi, [rbp+600h+var_678]
0x18005b8f8  lea     r8, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005b8fd  mov     rdx, rbx; unsigned __int8 *
0x18005b900  lea     rcx, [rbp+600h+var_670]; this
0x18005b904  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b909  mov     r15, [r14+8]
0x18005b90d  lea     r9, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b912  add     rbx, rsi
0x18005b915  lea     r8, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005b91a  mov     rdx, r15; unsigned __int8 *
0x18005b91d  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005b922  lea     rcx, [rbp+600h+var_670]; this
0x18005b926  movzx   edi, al
0x18005b929  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b92e  test    al, al
0x18005b930  jz      short loc_18005B93C
0x18005b932  test    dil, dil
0x18005b935  jz      short loc_18005B93C
0x18005b937  mov     dil, 1
0x18005b93a  jmp     short loc_18005B93F
0x18005b93c  xor     dil, dil
0x18005b93f  mov     r14, [r14+10h]
0x18005b943  lea     rax, [r15+rsi]
0x18005b947  mov     rdx, r14; unsigned __int8 *
0x18005b94a  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005b94f  lea     r9, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b954  lea     r8, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005b959  lea     rcx, [rbp+600h+var_670]; this
0x18005b95d  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b962  test    al, al
0x18005b964  jz      loc_18005BCA1
0x18005b96a  test    dil, dil
0x18005b96d  jz      loc_18005BCA1
0x18005b973  lea     rax, [r14+rsi]
0x18005b977  mov     dword ptr [rsp+700h+var_6B0+4], 1
0x18005b97f  mov     dword ptr [rsp+700h+var_6B0], 2
0x18005b987  movsd   xmm0, [rsp+700h+var_6B0]
0x18005b98d  mov     [rsp+700h+var_690], rax
0x18005b992  xor     eax, eax
0x18005b994  mov     r14d, eax
0x18005b997  mov     [rsp+700h+var_38], r13
0x18005b99f  mov     r13d, eax
0x18005b9a2  mov     [rsp+700h+var_6C0], rax
0x18005b9a7  movsd   [rsp+700h+var_6B0], xmm0
0x18005b9ad  mov     [rsp+700h+var_6A8], 1
0x18005b9b5  cmp     [rbp+600h+var_680], eax
0x18005b9b8  jle     loc_18005BC99
0x18005b9be  movsd   xmm0, [rsp+700h+var_690]
0x18005b9c4  movups  xmm1, [rsp+700h+var_6A0]
0x18005b9c9  mov     edi, [rbp+600h+var_6C]
0x18005b9cf  mov     esi, [rbp+600h+var_650]
0x18005b9d2  inc     esi
0x18005b9d4  mov     [rbp+600h+var_650], esi
0x18005b9d7  cmp     esi, 1
0x18005b9da  jnz     loc_18005BC77
0x18005b9e0  mov     edx, [r12+28h]
0x18005b9e5  lea     r15, [rbx+r14]
0x18005b9e9  mov     r11d, [r12+1Ch]
0x18005b9ee  mov     ecx, eax
0x18005b9f0  mov     eax, [rbp+600h+var_64C]
0x18005b9f3  test    eax, eax
0x18005b9f5  movsxd  r9, dword ptr [r12+34h]
0x18005b9fa  cmovle  ecx, eax
0x18005b9fd  movsd   [rsp+700h+var_690], xmm0
0x18005ba03  mov     eax, [r12+2Ch]
0x18005ba08  cmp     r11d, eax
0x18005ba0b  movups  [rsp+700h+var_6A0], xmm1
0x18005ba10  cmovl   r11d, eax
0x18005ba14  lea     r10d, [r9-1]
0x18005ba18  sub     r11d, eax
0x18005ba1b  mov     eax, [rbp+600h+var_648]
0x18005ba1e  cmp     eax, edx
0x18005ba20  cmovl   eax, edx
0x18005ba23  sub     eax, edx
0x18005ba25  cdq
0x18005ba26  idiv    dword ptr [r12+30h]
0x18005ba2b  movsxd  r8, edx
0x18005ba2e  imul    r8, r9
0x18005ba32  cmp     r11d, r10d
0x18005ba35  cmovle  r10d, r11d
0x18005ba39  mov     r11, qword ptr [rsp+700h+var_6A0+8]
0x18005ba3e  movsxd  rax, r10d
0x18005ba41  add     r11, r14
0x18005ba44  add     r14, [rsp+700h+var_690]
0x18005ba49  add     r8, rax
0x18005ba4c  mov     rax, [r12+38h]
0x18005ba51  neg     ecx
0x18005ba53  movsxd  r10, [rbp+600h+var_54]
0x18005ba5a  mov     r12d, [rbp+600h+var_67C]
0x18005ba5e  lea     r9, [rax+r8*2]
0x18005ba62  cmp     r10, 3
0x18005ba66  jge     short loc_18005BAAD
0x18005ba68  cmp     ecx, r12d
0x18005ba6b  jge     short loc_18005BAA4
0x18005ba6d  movsxd  rdx, ecx
0x18005ba70  movzx   eax, byte ptr [r11+rdx]
0x18005ba75  movzx   r8d, byte ptr [r15+rdx]
0x18005ba7a  add     r8d, eax
0x18005ba7d  movzx   eax, byte ptr [r14+rdx]
0x18005ba82  add     r8d, eax
0x18005ba85  imul    eax, r8d, 55h ; 'U'
0x18005ba89  shr     eax, 6
0x18005ba8c  mov     [r9], ax
0x18005ba90  add     r9, 2
0x18005ba94  mov     eax, dword ptr [rsp+r10*4+700h+var_6B0]
0x18005ba99  inc     r10
0x18005ba9c  add     ecx, eax
0x18005ba9e  cmp     r10, 3
0x18005baa2  jl      short loc_18005BA68
0x18005baa4  mov     edi, [rbp+600h+var_6C]
0x18005baaa  mov     esi, [rbp+600h+var_650]
0x18005baad  mov     eax, [rbp+600h+var_67C]
0x18005bab0  add     eax, 0FFFFFFF9h
0x18005bab3  movsxd  rdx, ecx
0x18005bab6  movsxd  r12, eax
0x18005bab9  cmp     rdx, r12
0x18005babc  jge     loc_18005BBE5
0x18005bac2  mov     rax, r12
0x18005bac5  lea     r8, [rdx+3]
0x18005bac9  sub     rax, rdx
0x18005bacc  mov     r10, r15
0x18005bacf  dec     rax
0x18005bad2  add     r8, r15
0x18005bad5  shr     rax, 3
0x18005bad9  neg     r10
0x18005badc  lea     ecx, [rcx+rax*8]
0x18005badf  add     ecx, 8
0x18005bae2  nop     dword ptr [rax+00h]
0x18005bae6  nop     word ptr [rax+rax+00000000h]
0x18005baf0  lea     rax, [r10+r8]
0x18005baf4  movzx   edx, byte ptr [r11+rax-3]
0x18005bafa  movzx   eax, byte ptr [r14+rax-3]
0x18005bb00  add     edx, eax
0x18005bb02  movzx   eax, byte ptr [r8-3]
0x18005bb07  add     edx, eax
0x18005bb09  imul    eax, edx, 55h ; 'U'
0x18005bb0c  shr     eax, 6
0x18005bb0f  mov     [r9], ax
0x18005bb13  lea     rax, [r10+r8]
0x18005bb17  movzx   edx, byte ptr [r11+rax-1]
0x18005bb1d  movzx   eax, byte ptr [r14+rax-1]
0x18005bb23  add     edx, eax
0x18005bb25  movzx   eax, byte ptr [r8-1]
0x18005bb2a  add     edx, eax
0x18005bb2c  imul    eax, edx, 55h ; 'U'
0x18005bb2f  shr     eax, 6
0x18005bb32  mov     [r9+2], ax
0x18005bb37  lea     rax, [r10+r8]
0x18005bb3b  movzx   edx, byte ptr [r11+rax]
0x18005bb40  movzx   eax, byte ptr [r14+rax]
0x18005bb45  add     edx, eax
0x18005bb47  movzx   eax, byte ptr [r8]
0x18005bb4b  add     edx, eax
0x18005bb4d  imul    eax, edx, 55h ; 'U'
0x18005bb50  shr     eax, 6
0x18005bb53  mov     [r9+4], ax
0x18005bb58  lea     rax, [r10+r8]
0x18005bb5c  movzx   edx, byte ptr [r11+rax+1]
0x18005bb62  movzx   eax, byte ptr [r14+rax+1]
0x18005bb68  add     edx, eax
0x18005bb6a  movzx   eax, byte ptr [r8+1]
0x18005bb6f  add     edx, eax
0x18005bb71  imul    eax, edx, 55h ; 'U'
0x18005bb74  shr     eax, 6
0x18005bb77  mov     [r9+6], ax
0x18005bb7c  lea     rax, [r10+r8]
0x18005bb80  movzx   edx, byte ptr [r11+rax+3]
0x18005bb86  movzx   eax, byte ptr [r14+rax+3]
0x18005bb8c  add     edx, eax
0x18005bb8e  movzx   eax, byte ptr [r8+3]
0x18005bb93  add     edx, eax
0x18005bb95  imul    eax, edx, 55h ; 'U'
0x18005bb98  shr     eax, 6
0x18005bb9b  mov     [r9+8], ax
0x18005bba0  lea     rax, [r10+r8]
0x18005bba4  movzx   edx, byte ptr [r11+rax+4]
0x18005bbaa  lea     r8, [r8+8]
0x18005bbae  movzx   eax, byte ptr [r14+rax+4]
0x18005bbb4  add     edx, eax
0x18005bbb6  movzx   eax, byte ptr [r8-4]
0x18005bbbb  add     edx, eax
0x18005bbbd  imul    eax, edx, 55h ; 'U'
0x18005bbc0  shr     eax, 6
0x18005bbc3  mov     [r9+0Ah], ax
0x18005bbc8  lea     rax, [r8-3]
0x18005bbcc  add     rax, r10
0x18005bbcf  add     r9, 0Ch
0x18005bbd3  cmp     rax, r12
0x18005bbd6  jl      loc_18005BAF0
0x18005bbdc  mov     edi, [rbp+600h+var_6C]
0x18005bbe2  mov     esi, [rbp+600h+var_650]
0x18005bbe5  mov     r12d, [rbp+600h+var_67C]
0x18005bbe9  xor     r10d, r10d
0x18005bbec  cmp     ecx, r12d
0x18005bbef  jge     short loc_18005BC4D
0x18005bbf1  movsxd  rdx, ecx
0x18005bbf4  lea     r9, [r9+2]
0x18005bbf8  movzx   eax, byte ptr [r11+rdx]
0x18005bbfd  movzx   r8d, byte ptr [r14+rdx]
0x18005bc02  add     r8d, eax
0x18005bc05  movzx   eax, byte ptr [r15+rdx]
0x18005bc0a  add     r8d, eax
0x18005bc0d  imul    eax, r8d, 55h ; 'U'
0x18005bc11  shr     eax, 6
0x18005bc14  mov     [r9-2], ax
0x18005bc19  movsxd  rax, r10d
0x18005bc1c  inc     r10d
0x18005bc1f  add     ecx, dword ptr [rsp+rax*4+700h+var_6B0]
0x18005bc23  mov     eax, 55555555h
0x18005bc28  imul    r10d
0x18005bc2b  sub     edx, r10d
0x18005bc2e  sar     edx, 1
0x18005bc30  mov     eax, edx
0x18005bc32  shr     eax, 1Fh
0x18005bc35  add     edx, eax
0x18005bc37  lea     eax, [r10+rdx]
0x18005bc3b  lea     r10d, [rax+rdx*2]
0x18005bc3f  cmp     ecx, r12d
0x18005bc42  jl      short loc_18005BBF1
0x18005bc44  mov     edi, [rbp+600h+var_6C]
0x18005bc4a  mov     esi, [rbp+600h+var_650]
0x18005bc4d  mov     r14, [rsp+700h+var_6C0]
0x18005bc52  mov     r12, [rsp+700h+var_6D0]
0x18005bc57  movsxd  rax, edi
0x18005bc5a  inc     edi
0x18005bc5c  sub     esi, [rbp+rax*4+600h+var_644]
0x18005bc60  mov     eax, 0
0x18005bc65  cmp     edi, [rbp+600h+var_64]
0x18005bc6b  cmovge  edi, eax
0x18005bc6e  inc     [rbp+600h+var_648]
0x18005bc71  mov     [rbp+600h+var_6C], edi
0x18005bc77  mov     rax, [rsp+700h+var_6C8]
0x18005bc7c  inc     r13d
0x18005bc7f  movsxd  rax, dword ptr [rax]
0x18005bc82  add     r14, rax
0x18005bc85  mov     eax, 0
0x18005bc8a  mov     [rsp+700h+var_6C0], r14
0x18005bc8f  cmp     r13d, [rbp+600h+var_680]
0x18005bc93  jl      loc_18005B9D2
0x18005bc99  mov     r13, [rsp+700h+var_38]
0x18005bca1  mov     rcx, [rbp+600h+var_50]
0x18005bca8  xor     rcx, rsp; StackCookie
0x18005bcab  call    __security_check_cookie
0x18005bcb0  add     rsp, 6D0h
0x18005bcb7  pop     r15
0x18005bcb9  pop     r14
0x18005bcbb  pop     r12
0x18005bcbd  pop     rdi
0x18005bcbe  pop     rsi
0x18005bcbf  pop     rbx
0x18005bcc0  pop     rbp
0x18005bcc1  retn
```
