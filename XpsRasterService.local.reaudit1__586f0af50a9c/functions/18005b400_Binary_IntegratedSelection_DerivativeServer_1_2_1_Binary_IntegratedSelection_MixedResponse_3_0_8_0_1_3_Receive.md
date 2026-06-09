# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005b400`
- end: `0x18005b874`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$00$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa40`

## callees

- `0x180003180`
- `0x18005b400`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int128 v4; // xmm0
  __int64 v6; // r12
  unsigned __int8 *v7; // rbx
  __int64 v8; // rsi
  bool v9; // al
  unsigned __int8 *v10; // r15
  unsigned __int8 *v11; // rbx
  bool v12; // di
  bool v13; // di
  unsigned __int8 *v14; // r14
  bool result; // al
  __int64 v16; // r13
  unsigned __int8 *v17; // xmm0_8
  __int128 v18; // xmm1
  int v19; // esi
  int v20; // r15d
  int v21; // edi
  int v22; // ecx
  unsigned __int8 *v23; // r14
  int v24; // r10d
  int v25; // r11d
  __int64 v26; // r8
  int v27; // eax
  int v28; // r9d
  int v29; // r10d
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int8 *v33; // r10
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rax
  int v37; // r11d
  __int64 v38; // r12
  _WORD *v39; // rax
  int v40; // ecx
  unsigned __int8 *v41; // r9
  unsigned __int8 *v42; // rcx
  int v43; // edx
  __int64 v44; // r8
  unsigned __int8 *v45; // r10
  unsigned __int8 *v46; // r14
  __int64 v47; // r9
  int v48; // ecx
  int v49; // edx
  __int64 v50; // rax
  bool v51; // cc
  __int128 v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h]
  int *v54; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v55; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v56; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v57; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+80h] [rbp-80h] BYREF
  int v60; // [rsp+84h] [rbp-7Ch]
  __int64 v61; // [rsp+88h] [rbp-78h]
  _BYTE v62[32]; // [rsp+90h] [rbp-70h] BYREF
  int v63; // [rsp+B0h] [rbp-50h]
  int v64; // [rsp+B4h] [rbp-4Ch]
  int v65; // [rsp+B8h] [rbp-48h]
  _DWORD v66[374]; // [rsp+BCh] [rbp-44h]
  int v67; // [rsp+694h] [rbp+594h]
  int v68; // [rsp+69Ch] [rbp+59Ch]
  int v69; // [rsp+6ACh] [rbp+5ACh]

  v4 = *a4;
  v54 = a3;
  v53 = a1;
  v6 = a1;
  v52 = v4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v59, 2, 1, a3, &v52, (_DWORD *)(a1 + 8));
  v7 = *a2;
  v8 = v61;
  v9 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v62,
         *a2,
         &v55,
         &v56);
  v10 = a2[1];
  v11 = &v7[v8];
  *(_QWORD *)&v57 = v11;
  v12 = v9;
  v13 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v62,
          v10,
          &v55,
          &v56)
     && v12;
  v14 = a2[2];
  *((_QWORD *)&v57 + 1) = &v10[v8];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v62,
             v14,
             &v55,
             &v56);
  if ( result && v13 )
  {
    v58 = &v14[v8];
    result = 0;
    v16 = 0;
    *(_QWORD *)&v52 = 0;
    LODWORD(v56) = 2;
    LODWORD(v55) = 0;
    if ( v59 > 0 )
    {
      v17 = v58;
      v18 = v57;
      v19 = v67;
      v20 = v63;
      v21 = v60;
      do
      {
        v63 = ++v20;
        if ( v20 == 1 )
        {
          v22 = *(_DWORD *)(v6 + 40);
          v23 = &v11[v16];
          v24 = *(_DWORD *)(v6 + 28);
          v25 = 0;
          v26 = *(int *)(v6 + 52);
          if ( v64 <= 0 )
            v25 = v64;
          v58 = v17;
          v27 = *(_DWORD *)(v6 + 44);
          v57 = v18;
          if ( v24 < v27 )
            v24 = v27;
          v28 = v26 - 1;
          v29 = v24 - v27;
          v30 = v65;
          if ( v65 < v22 )
            v30 = v22;
          v31 = v26 * ((v30 - v22) % *(_DWORD *)(v6 + 48));
          if ( v29 <= v28 )
            v28 = v29;
          v32 = v28;
          v33 = &v58[v16];
          v34 = v69;
          v35 = v32 + v31;
          v36 = *(_QWORD *)(v6 + 56);
          v37 = -v25;
          v38 = v16 + *((_QWORD *)&v57 + 1);
          v39 = (_WORD *)(v36 + 2 * v35);
          if ( v69 < 1LL )
          {
            do
            {
              if ( v37 >= v21 )
                break;
              *v39++ = (85 * (v33[v37] + *(unsigned __int8 *)(v38 + v37) + (unsigned int)v23[v37])) >> 6;
              v40 = *((_DWORD *)&v56 + v34++);
              v37 += v40;
            }
            while ( v34 < 1 );
            v19 = v67;
            v20 = v63;
            v21 = v60;
          }
          if ( v37 < (__int64)(v21 - 15) )
          {
            v41 = &v23[v37 + 4];
            v37 += 16 * (((unsigned __int64)(v21 - 15 - (__int64)v37 - 1) >> 4) + 1);
            do
            {
              *v39 = (85 * (*(v41 - 4) + v33[v41 - v23 - 4] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 - 4))) >> 6;
              v39[1] = (85 * (*(v41 - 2) + v33[v41 - v23 - 2] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 - 2))) >> 6;
              v39[2] = (85 * (*v41 + v33[v41 - v23] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23))) >> 6;
              v39[3] = (85 * (v41[2] + v33[v41 - v23 + 2] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 2))) >> 6;
              v39[4] = (85 * (v41[4] + v33[v41 - v23 + 4] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 4))) >> 6;
              v39[5] = (85 * (v41[6] + v33[v41 - v23 + 6] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 6))) >> 6;
              v39[6] = (85 * (v41[8] + v33[v41 - v23 + 8] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 8))) >> 6;
              v42 = (unsigned __int8 *)(v41 - v23);
              v43 = *(unsigned __int8 *)(v38 + v41 - v23 + 10);
              v41 += 16;
              v39[7] = (85 * (*(v41 - 6) + (unsigned int)v42[(_QWORD)v33 + 10] + v43)) >> 6;
              v39 += 8;
            }
            while ( v41 - 4 - v23 < v21 - 15 );
            v19 = v67;
            v20 = v63;
            v21 = v60;
          }
          if ( v37 < v21 )
          {
            v44 = v38 + v37;
            v45 = &v33[-v38];
            v46 = &v23[-v38];
            v47 = ((unsigned int)(v21 - v37 - 1) >> 1) + 1;
            do
            {
              v48 = v45[v44];
              ++v39;
              v49 = v46[v44];
              v44 += 2;
              *(v39 - 1) = (85 * ((unsigned int)*(unsigned __int8 *)(v44 - 2) + v48 + v49)) >> 6;
              --v47;
            }
            while ( v47 );
            v19 = v67;
            v20 = v63;
            v21 = v60;
          }
          v16 = v52;
          v6 = v53;
          v50 = v19++;
          v20 -= v66[v50];
          if ( v19 >= v68 )
            v19 = 0;
          ++v65;
          v67 = v19;
        }
        v16 += *v54;
        *(_QWORD *)&v52 = v16;
        v51 = (int)v55 + 1 < v59;
        LODWORD(v55) = (_DWORD)v55 + 1;
        result = 0;
      }
      while ( v51 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005b400  push    rbp
0x18005b402  push    rbx
0x18005b403  push    rsi
0x18005b404  push    rdi
0x18005b405  push    r12
0x18005b407  push    r14
0x18005b409  push    r15
0x18005b40b  lea     rbp, [rsp-5D0h]
0x18005b413  sub     rsp, 6D0h
0x18005b41a  mov     rax, cs:__security_cookie
0x18005b421  xor     rax, rsp
0x18005b424  mov     [rbp+600h+var_50], rax
0x18005b42b  movups  xmm0, xmmword ptr [r9]
0x18005b42f  lea     rax, [rcx+8]
0x18005b433  mov     [rsp+700h+var_6B8], r8
0x18005b438  mov     [rsp+700h+var_6D8], rax
0x18005b43d  mov     r14, rdx
0x18005b440  mov     edx, 2
0x18005b445  mov     [rsp+700h+var_6C0], rcx
0x18005b44a  mov     r12, rcx
0x18005b44d  movaps  [rsp+700h+var_6D0], xmm0
0x18005b452  lea     rax, [rsp+700h+var_6D0]
0x18005b457  mov     r9, r8
0x18005b45a  lea     rcx, [rbp+600h+var_680]
0x18005b45e  mov     [rsp+700h+var_6E0], rax
0x18005b463  lea     r8d, [rdx-1]
0x18005b467  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005b46c  mov     rbx, [r14]
0x18005b46f  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005b474  mov     rsi, [rbp+600h+var_678]
0x18005b478  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b47d  mov     rdx, rbx; unsigned __int8 *
0x18005b480  lea     rcx, [rbp+600h+var_670]; this
0x18005b484  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b489  mov     r15, [r14+8]
0x18005b48d  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005b492  add     rbx, rsi
0x18005b495  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b49a  mov     rdx, r15; unsigned __int8 *
0x18005b49d  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005b4a2  lea     rcx, [rbp+600h+var_670]; this
0x18005b4a6  movzx   edi, al
0x18005b4a9  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b4ae  test    al, al
0x18005b4b0  jz      short loc_18005B4BC
0x18005b4b2  test    dil, dil
0x18005b4b5  jz      short loc_18005B4BC
0x18005b4b7  mov     dil, 1
0x18005b4ba  jmp     short loc_18005B4BF
0x18005b4bc  xor     dil, dil
0x18005b4bf  mov     r14, [r14+10h]
0x18005b4c3  lea     rax, [r15+rsi]
0x18005b4c7  mov     rdx, r14; unsigned __int8 *
0x18005b4ca  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005b4cf  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005b4d4  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005b4d9  lea     rcx, [rbp+600h+var_670]; this
0x18005b4dd  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005b4e2  test    al, al
0x18005b4e4  jz      loc_18005B853
0x18005b4ea  test    dil, dil
0x18005b4ed  jz      loc_18005B853
0x18005b4f3  lea     rax, [r14+rsi]
0x18005b4f7  mov     [rsp+700h+var_38], r13
0x18005b4ff  mov     [rsp+700h+var_690], rax
0x18005b504  xor     eax, eax
0x18005b506  mov     r13d, eax
0x18005b509  mov     qword ptr [rsp+700h+var_6D0], rax
0x18005b50e  mov     dword ptr [rsp+700h+var_6A8], 2
0x18005b516  mov     dword ptr [rsp+700h+var_6B0], eax
0x18005b51a  cmp     [rbp+600h+var_680], eax
0x18005b51d  jle     loc_18005B84B
0x18005b523  movsd   xmm0, [rsp+700h+var_690]
0x18005b529  movups  xmm1, [rsp+700h+var_6A0]
0x18005b52e  mov     esi, [rbp+600h+var_6C]
0x18005b534  mov     r15d, [rbp+600h+var_650]
0x18005b538  mov     edi, [rbp+600h+var_67C]
0x18005b53b  nop     dword ptr [rax+rax+00h]
0x18005b540  inc     r15d
0x18005b543  mov     [rbp+600h+var_650], r15d
0x18005b547  cmp     r15d, 1
0x18005b54b  jnz     loc_18005B823
0x18005b551  mov     ecx, [r12+28h]
0x18005b556  lea     r14, [rbx+r13]
0x18005b55a  mov     r10d, [r12+1Ch]
0x18005b55f  mov     r11d, eax
0x18005b562  mov     eax, [rbp+600h+var_64C]
0x18005b565  test    eax, eax
0x18005b567  movsxd  r8, dword ptr [r12+34h]
0x18005b56c  cmovle  r11d, eax
0x18005b570  movsd   [rsp+700h+var_690], xmm0
0x18005b576  mov     eax, [r12+2Ch]
0x18005b57b  cmp     r10d, eax
0x18005b57e  movups  [rsp+700h+var_6A0], xmm1
0x18005b583  cmovl   r10d, eax
0x18005b587  lea     r9d, [r8-1]
0x18005b58b  sub     r10d, eax
0x18005b58e  mov     eax, [rbp+600h+var_648]
0x18005b591  cmp     eax, ecx
0x18005b593  cmovl   eax, ecx
0x18005b596  sub     eax, ecx
0x18005b598  cdq
0x18005b599  idiv    dword ptr [r12+30h]
0x18005b59e  movsxd  rcx, edx
0x18005b5a1  imul    rcx, r8
0x18005b5a5  cmp     r10d, r9d
0x18005b5a8  cmovle  r9d, r10d
0x18005b5ac  mov     r10, [rsp+700h+var_690]
0x18005b5b1  movsxd  rax, r9d
0x18005b5b4  add     r10, r13
0x18005b5b7  movsxd  r9, [rbp+600h+var_54]
0x18005b5be  add     rcx, rax
0x18005b5c1  mov     rax, [r12+38h]
0x18005b5c6  neg     r11d
0x18005b5c9  mov     r12, qword ptr [rsp+700h+var_6A0+8]
0x18005b5ce  add     r12, r13
0x18005b5d1  lea     rax, [rax+rcx*2]
0x18005b5d5  cmp     r9, 1
0x18005b5d9  jge     short loc_18005B629
0x18005b5db  nop     dword ptr [rax+rax+00h]
0x18005b5e0  cmp     r11d, edi
0x18005b5e3  jge     short loc_18005B61C
0x18005b5e5  movsxd  rdx, r11d
0x18005b5e8  movzx   ecx, byte ptr [r12+rdx]
0x18005b5ed  movzx   r8d, byte ptr [r14+rdx]
0x18005b5f2  add     r8d, ecx
0x18005b5f5  movzx   ecx, byte ptr [r10+rdx]
0x18005b5fa  add     r8d, ecx
0x18005b5fd  imul    ecx, r8d, 55h ; 'U'
0x18005b601  shr     ecx, 6
0x18005b604  mov     [rax], cx
0x18005b607  add     rax, 2
0x18005b60b  mov     ecx, dword ptr [rsp+r9*4+700h+var_6A8]
0x18005b610  inc     r9
0x18005b613  add     r11d, ecx
0x18005b616  cmp     r9, 1
0x18005b61a  jl      short loc_18005B5E0
0x18005b61c  mov     esi, [rbp+600h+var_6C]
0x18005b622  mov     r15d, [rbp+600h+var_650]
0x18005b626  mov     edi, [rbp+600h+var_67C]
0x18005b629  lea     ecx, [rdi-0Fh]
0x18005b62c  movsxd  rdx, r11d
0x18005b62f  movsxd  r13, ecx
0x18005b632  cmp     rdx, r13
0x18005b635  jge     loc_18005B799
0x18005b63b  mov     rcx, r13
0x18005b63e  lea     r9, [r14+4]
0x18005b642  sub     rcx, rdx
0x18005b645  mov     r8, r14
0x18005b648  dec     rcx
0x18005b64b  add     r9, rdx
0x18005b64e  shr     rcx, 4
0x18005b652  neg     r8
0x18005b655  inc     ecx
0x18005b657  shl     ecx, 4
0x18005b65a  add     r11d, ecx
0x18005b65d  nop     dword ptr [rax]
0x18005b660  lea     rcx, [r9+r8]
0x18005b664  movzx   edx, byte ptr [r12+rcx-4]
0x18005b66a  movzx   ecx, byte ptr [r10+rcx-4]
0x18005b670  add     edx, ecx
0x18005b672  movzx   ecx, byte ptr [r9-4]
0x18005b677  add     edx, ecx
0x18005b679  imul    ecx, edx, 55h ; 'U'
0x18005b67c  shr     ecx, 6
0x18005b67f  mov     [rax], cx
0x18005b682  lea     rcx, [r9+r8]
0x18005b686  movzx   edx, byte ptr [r12+rcx-2]
0x18005b68c  movzx   ecx, byte ptr [r10+rcx-2]
0x18005b692  add     edx, ecx
0x18005b694  movzx   ecx, byte ptr [r9-2]
0x18005b699  add     edx, ecx
0x18005b69b  imul    ecx, edx, 55h ; 'U'
0x18005b69e  shr     ecx, 6
0x18005b6a1  mov     [rax+2], cx
0x18005b6a5  lea     rcx, [r9+r8]
0x18005b6a9  movzx   edx, byte ptr [r12+rcx]
0x18005b6ae  movzx   ecx, byte ptr [r10+rcx]
0x18005b6b3  add     edx, ecx
0x18005b6b5  movzx   ecx, byte ptr [r9]
0x18005b6b9  add     edx, ecx
0x18005b6bb  imul    ecx, edx, 55h ; 'U'
0x18005b6be  shr     ecx, 6
0x18005b6c1  mov     [rax+4], cx
0x18005b6c5  lea     rcx, [r9+r8]
0x18005b6c9  movzx   edx, byte ptr [r12+rcx+2]
0x18005b6cf  movzx   ecx, byte ptr [r10+rcx+2]
0x18005b6d5  add     edx, ecx
0x18005b6d7  movzx   ecx, byte ptr [r9+2]
0x18005b6dc  add     edx, ecx
0x18005b6de  imul    ecx, edx, 55h ; 'U'
0x18005b6e1  shr     ecx, 6
0x18005b6e4  mov     [rax+6], cx
0x18005b6e8  lea     rcx, [r9+r8]
0x18005b6ec  movzx   edx, byte ptr [r12+rcx+4]
0x18005b6f2  movzx   ecx, byte ptr [r10+rcx+4]
0x18005b6f8  add     edx, ecx
0x18005b6fa  movzx   ecx, byte ptr [r9+4]
0x18005b6ff  add     edx, ecx
0x18005b701  imul    ecx, edx, 55h ; 'U'
0x18005b704  shr     ecx, 6
0x18005b707  mov     [rax+8], cx
0x18005b70b  lea     rcx, [r9+r8]
0x18005b70f  movzx   edx, byte ptr [r12+rcx+6]
0x18005b715  movzx   ecx, byte ptr [r10+rcx+6]
0x18005b71b  add     edx, ecx
0x18005b71d  movzx   ecx, byte ptr [r9+6]
0x18005b722  add     edx, ecx
0x18005b724  imul    ecx, edx, 55h ; 'U'
0x18005b727  shr     ecx, 6
0x18005b72a  mov     [rax+0Ah], cx
0x18005b72e  lea     rcx, [r9+r8]
0x18005b732  movzx   edx, byte ptr [r12+rcx+8]
0x18005b738  movzx   ecx, byte ptr [r10+rcx+8]
0x18005b73e  add     edx, ecx
0x18005b740  movzx   ecx, byte ptr [r9+8]
0x18005b745  add     edx, ecx
0x18005b747  imul    ecx, edx, 55h ; 'U'
0x18005b74a  shr     ecx, 6
0x18005b74d  mov     [rax+0Ch], cx
0x18005b751  lea     rcx, [r9+r8]
0x18005b755  movzx   edx, byte ptr [r12+rcx+0Ah]
0x18005b75b  lea     r9, [r9+10h]
0x18005b75f  movzx   ecx, byte ptr [r10+rcx+0Ah]
0x18005b765  add     edx, ecx
0x18005b767  movzx   ecx, byte ptr [r9-6]
0x18005b76c  add     edx, ecx
0x18005b76e  imul    ecx, edx, 55h ; 'U'
0x18005b771  shr     ecx, 6
0x18005b774  mov     [rax+0Eh], cx
0x18005b778  lea     rcx, [r9-4]
0x18005b77c  add     rcx, r8
0x18005b77f  add     rax, 10h
0x18005b783  cmp     rcx, r13
0x18005b786  jl      loc_18005B660
0x18005b78c  mov     esi, [rbp+600h+var_6C]
0x18005b792  mov     r15d, [rbp+600h+var_650]
0x18005b796  mov     edi, [rbp+600h+var_67C]
0x18005b799  cmp     r11d, edi
0x18005b79c  jge     short loc_18005B7F8
0x18005b79e  sub     edi, r11d
0x18005b7a1  movsxd  r8, r11d
0x18005b7a4  add     r8, r12
0x18005b7a7  sub     r10, r12
0x18005b7aa  sub     r14, r12
0x18005b7ad  lea     r9d, [rdi-1]
0x18005b7b1  shr     r9d, 1
0x18005b7b4  inc     r9d
0x18005b7b7  nop     word ptr [rax+rax+00000000h]
0x18005b7c0  movzx   ecx, byte ptr [r8+r10]
0x18005b7c5  lea     rax, [rax+2]
0x18005b7c9  movzx   edx, byte ptr [r8+r14]
0x18005b7ce  lea     r8, [r8+2]
0x18005b7d2  add     edx, ecx
0x18005b7d4  movzx   ecx, byte ptr [r8-2]
0x18005b7d9  add     edx, ecx
0x18005b7db  imul    ecx, edx, 55h ; 'U'
0x18005b7de  shr     ecx, 6
0x18005b7e1  mov     [rax-2], cx
0x18005b7e5  sub     r9, 1
0x18005b7e9  jnz     short loc_18005B7C0
0x18005b7eb  mov     esi, [rbp+600h+var_6C]
0x18005b7f1  mov     r15d, [rbp+600h+var_650]
0x18005b7f5  mov     edi, [rbp+600h+var_67C]
0x18005b7f8  mov     r13, qword ptr [rsp+700h+var_6D0]
0x18005b7fd  mov     r12, [rsp+700h+var_6C0]
0x18005b802  movsxd  rax, esi
0x18005b805  inc     esi
0x18005b807  sub     r15d, [rbp+rax*4+600h+var_644]
0x18005b80c  mov     eax, 0
0x18005b811  cmp     esi, [rbp+600h+var_64]
0x18005b817  cmovge  esi, eax
0x18005b81a  inc     [rbp+600h+var_648]
0x18005b81d  mov     [rbp+600h+var_6C], esi
0x18005b823  mov     rax, [rsp+700h+var_6B8]
0x18005b828  movsxd  rax, dword ptr [rax]
0x18005b82b  add     r13, rax
0x18005b82e  mov     eax, dword ptr [rsp+700h+var_6B0]
0x18005b832  inc     eax
0x18005b834  mov     qword ptr [rsp+700h+var_6D0], r13
0x18005b839  cmp     eax, [rbp+600h+var_680]
0x18005b83c  mov     dword ptr [rsp+700h+var_6B0], eax
0x18005b840  mov     eax, 0
0x18005b845  jl      loc_18005B540
0x18005b84b  mov     r13, [rsp+700h+var_38]
0x18005b853  mov     rcx, [rbp+600h+var_50]
0x18005b85a  xor     rcx, rsp; StackCookie
0x18005b85d  call    __security_check_cookie
0x18005b862  add     rsp, 6D0h
0x18005b869  pop     r15
0x18005b86b  pop     r14
0x18005b86d  pop     r12
0x18005b86f  pop     rdi
0x18005b870  pop     rsi
0x18005b871  pop     rbx
0x18005b872  pop     rbp
0x18005b873  retn
```
