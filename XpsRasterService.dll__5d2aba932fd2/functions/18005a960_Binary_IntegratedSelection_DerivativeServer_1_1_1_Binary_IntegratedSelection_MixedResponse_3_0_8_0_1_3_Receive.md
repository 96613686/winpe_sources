# Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005a960`
- end: `0x18005adc4`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$00$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1124`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, __int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa30`

## callees

- `0x180003180`
- `0x18005a960`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
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
  int v19; // edi
  int v20; // r15d
  int v21; // esi
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
  unsigned __int8 *v44; // r10
  __int64 v45; // r8
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
  v52 = v4;
  v6 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v59, 1, 1, (_DWORD)a3, (__int64)&v52, a1 + 8);
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
    LODWORD(v56) = 1;
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
          if ( v37 < (__int64)(v21 - 7) )
          {
            v41 = &v23[v37 + 2];
            v37 += 8 * ((unsigned __int64)(v21 - 7 - (__int64)v37 - 1) >> 3) + 8;
            do
            {
              *v39 = (85 * (*(v41 - 2) + v33[v41 - v23 - 2] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 - 2))) >> 6;
              v39[1] = (85 * (*(v41 - 1) + v33[v41 - v23 - 1] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 - 1))) >> 6;
              v39[2] = (85 * (*v41 + v33[v41 - v23] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23))) >> 6;
              v39[3] = (85 * (v41[1] + v33[v41 - v23 + 1] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 1))) >> 6;
              v39[4] = (85 * (v41[2] + v33[v41 - v23 + 2] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 2))) >> 6;
              v39[5] = (85 * (v41[3] + v33[v41 - v23 + 3] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 3))) >> 6;
              v39[6] = (85 * (v41[4] + v33[v41 - v23 + 4] + (unsigned int)*(unsigned __int8 *)(v38 + v41 - v23 + 4))) >> 6;
              v42 = (unsigned __int8 *)(v41 - v23);
              v43 = *(unsigned __int8 *)(v38 + v41 - v23 + 5);
              v41 += 8;
              v39[7] = (85 * (*(v41 - 3) + (unsigned int)v42[(_QWORD)v33 + 5] + v43)) >> 6;
              v39 += 8;
            }
            while ( v41 - 2 - v23 < v21 - 7 );
            v19 = v67;
            v20 = v63;
            v21 = v60;
          }
          if ( v37 < v21 )
          {
            v44 = &v33[-v38];
            v45 = v38 + v37;
            v46 = &v23[-v38];
            v47 = (unsigned int)(v21 - v37);
            do
            {
              v48 = v44[v45];
              ++v39;
              v49 = v46[v45++];
              *(v39 - 1) = (85 * ((unsigned int)*(unsigned __int8 *)(v45 - 1) + v48 + v49)) >> 6;
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
0x18005a960  push    rbp
0x18005a962  push    rbx
0x18005a963  push    rsi
0x18005a964  push    rdi
0x18005a965  push    r12
0x18005a967  push    r14
0x18005a969  push    r15
0x18005a96b  lea     rbp, [rsp-5D0h]
0x18005a973  sub     rsp, 6D0h
0x18005a97a  mov     rax, cs:__security_cookie
0x18005a981  xor     rax, rsp
0x18005a984  mov     [rbp+600h+var_50], rax
0x18005a98b  movups  xmm0, xmmword ptr [r9]
0x18005a98f  lea     rax, [rcx+8]
0x18005a993  mov     [rsp+700h+var_6B8], r8
0x18005a998  mov     [rsp+700h+var_6D8], rax
0x18005a99d  mov     r14, rdx
0x18005a9a0  mov     edx, 1
0x18005a9a5  mov     [rsp+700h+var_6C0], rcx
0x18005a9aa  lea     rax, [rsp+700h+var_6D0]
0x18005a9af  movaps  [rsp+700h+var_6D0], xmm0
0x18005a9b4  mov     r12, rcx
0x18005a9b7  mov     [rsp+700h+var_6E0], rax
0x18005a9bc  mov     r9, r8
0x18005a9bf  lea     rcx, [rbp+600h+var_680]
0x18005a9c3  mov     r8d, edx
0x18005a9c6  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005a9cb  mov     rbx, [r14]
0x18005a9ce  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005a9d3  mov     rsi, [rbp+600h+var_678]
0x18005a9d7  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005a9dc  mov     rdx, rbx; unsigned __int8 *
0x18005a9df  lea     rcx, [rbp+600h+var_670]; this
0x18005a9e3  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005a9e8  mov     r15, [r14+8]
0x18005a9ec  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005a9f1  add     rbx, rsi
0x18005a9f4  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005a9f9  mov     rdx, r15; unsigned __int8 *
0x18005a9fc  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005aa01  lea     rcx, [rbp+600h+var_670]; this
0x18005aa05  movzx   edi, al
0x18005aa08  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005aa0d  test    al, al
0x18005aa0f  jz      short loc_18005AA1B
0x18005aa11  test    dil, dil
0x18005aa14  jz      short loc_18005AA1B
0x18005aa16  mov     dil, 1
0x18005aa19  jmp     short loc_18005AA1E
0x18005aa1b  xor     dil, dil
0x18005aa1e  mov     r14, [r14+10h]
0x18005aa22  lea     rax, [r15+rsi]
0x18005aa26  mov     rdx, r14; unsigned __int8 *
0x18005aa29  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005aa2e  lea     r9, [rsp+700h+var_6A8]; unsigned __int8 **
0x18005aa33  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005aa38  lea     rcx, [rbp+600h+var_670]; this
0x18005aa3c  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005aa41  test    al, al
0x18005aa43  jz      loc_18005ADA3
0x18005aa49  test    dil, dil
0x18005aa4c  jz      loc_18005ADA3
0x18005aa52  lea     rax, [r14+rsi]
0x18005aa56  mov     [rsp+700h+var_38], r13
0x18005aa5e  mov     [rsp+700h+var_690], rax
0x18005aa63  xor     eax, eax
0x18005aa65  mov     r13d, eax
0x18005aa68  mov     qword ptr [rsp+700h+var_6D0], rax
0x18005aa6d  mov     dword ptr [rsp+700h+var_6A8], 1
0x18005aa75  mov     dword ptr [rsp+700h+var_6B0], eax
0x18005aa79  cmp     [rbp+600h+var_680], eax
0x18005aa7c  jle     loc_18005AD9B
0x18005aa82  movsd   xmm0, [rsp+700h+var_690]
0x18005aa88  movups  xmm1, [rsp+700h+var_6A0]
0x18005aa8d  mov     edi, [rbp+600h+var_6C]
0x18005aa93  mov     r15d, [rbp+600h+var_650]
0x18005aa97  mov     esi, [rbp+600h+var_67C]
0x18005aa9a  nop     word ptr [rax+rax+00h]
0x18005aaa0  inc     r15d
0x18005aaa3  mov     [rbp+600h+var_650], r15d
0x18005aaa7  cmp     r15d, 1
0x18005aaab  jnz     loc_18005AD73
0x18005aab1  mov     ecx, [r12+28h]
0x18005aab6  lea     r14, [rbx+r13]
0x18005aaba  mov     r10d, [r12+1Ch]
0x18005aabf  mov     r11d, eax
0x18005aac2  mov     eax, [rbp+600h+var_64C]
0x18005aac5  test    eax, eax
0x18005aac7  movsxd  r8, dword ptr [r12+34h]
0x18005aacc  cmovle  r11d, eax
0x18005aad0  movsd   [rsp+700h+var_690], xmm0
0x18005aad6  mov     eax, [r12+2Ch]
0x18005aadb  cmp     r10d, eax
0x18005aade  movups  [rsp+700h+var_6A0], xmm1
0x18005aae3  cmovl   r10d, eax
0x18005aae7  lea     r9d, [r8-1]
0x18005aaeb  sub     r10d, eax
0x18005aaee  mov     eax, [rbp+600h+var_648]
0x18005aaf1  cmp     eax, ecx
0x18005aaf3  cmovl   eax, ecx
0x18005aaf6  sub     eax, ecx
0x18005aaf8  cdq
0x18005aaf9  idiv    dword ptr [r12+30h]
0x18005aafe  movsxd  rcx, edx
0x18005ab01  imul    rcx, r8
0x18005ab05  cmp     r10d, r9d
0x18005ab08  cmovle  r9d, r10d
0x18005ab0c  mov     r10, [rsp+700h+var_690]
0x18005ab11  movsxd  rax, r9d
0x18005ab14  add     r10, r13
0x18005ab17  movsxd  r9, [rbp+600h+var_54]
0x18005ab1e  add     rcx, rax
0x18005ab21  mov     rax, [r12+38h]
0x18005ab26  neg     r11d
0x18005ab29  mov     r12, qword ptr [rsp+700h+var_6A0+8]
0x18005ab2e  add     r12, r13
0x18005ab31  lea     rax, [rax+rcx*2]
0x18005ab35  cmp     r9, 1
0x18005ab39  jge     short loc_18005AB89
0x18005ab3b  nop     dword ptr [rax+rax+00h]
0x18005ab40  cmp     r11d, esi
0x18005ab43  jge     short loc_18005AB7C
0x18005ab45  movsxd  rdx, r11d
0x18005ab48  movzx   ecx, byte ptr [r12+rdx]
0x18005ab4d  movzx   r8d, byte ptr [r14+rdx]
0x18005ab52  add     r8d, ecx
0x18005ab55  movzx   ecx, byte ptr [r10+rdx]
0x18005ab5a  add     r8d, ecx
0x18005ab5d  imul    ecx, r8d, 55h ; 'U'
0x18005ab61  shr     ecx, 6
0x18005ab64  mov     [rax], cx
0x18005ab67  add     rax, 2
0x18005ab6b  mov     ecx, dword ptr [rsp+r9*4+700h+var_6A8]
0x18005ab70  inc     r9
0x18005ab73  add     r11d, ecx
0x18005ab76  cmp     r9, 1
0x18005ab7a  jl      short loc_18005AB40
0x18005ab7c  mov     edi, [rbp+600h+var_6C]
0x18005ab82  mov     r15d, [rbp+600h+var_650]
0x18005ab86  mov     esi, [rbp+600h+var_67C]
0x18005ab89  lea     ecx, [rsi-7]
0x18005ab8c  movsxd  rdx, r11d
0x18005ab8f  movsxd  r13, ecx
0x18005ab92  cmp     rdx, r13
0x18005ab95  jge     loc_18005ACF9
0x18005ab9b  mov     rcx, r13
0x18005ab9e  lea     r9, [rdx+2]
0x18005aba2  sub     rcx, rdx
0x18005aba5  mov     r8, r14
0x18005aba8  dec     rcx
0x18005abab  add     r9, r14
0x18005abae  shr     rcx, 3
0x18005abb2  neg     r8
0x18005abb5  lea     r11d, [r11+rcx*8]
0x18005abb9  add     r11d, 8
0x18005abbd  nop     dword ptr [rax]
0x18005abc0  lea     rcx, [r8+r9]
0x18005abc4  movzx   edx, byte ptr [r12+rcx-2]
0x18005abca  movzx   ecx, byte ptr [r10+rcx-2]
0x18005abd0  add     edx, ecx
0x18005abd2  movzx   ecx, byte ptr [r9-2]
0x18005abd7  add     edx, ecx
0x18005abd9  imul    ecx, edx, 55h ; 'U'
0x18005abdc  shr     ecx, 6
0x18005abdf  mov     [rax], cx
0x18005abe2  lea     rcx, [r8+r9]
0x18005abe6  movzx   edx, byte ptr [r12+rcx-1]
0x18005abec  movzx   ecx, byte ptr [r10+rcx-1]
0x18005abf2  add     edx, ecx
0x18005abf4  movzx   ecx, byte ptr [r9-1]
0x18005abf9  add     edx, ecx
0x18005abfb  imul    ecx, edx, 55h ; 'U'
0x18005abfe  shr     ecx, 6
0x18005ac01  mov     [rax+2], cx
0x18005ac05  lea     rcx, [r8+r9]
0x18005ac09  movzx   edx, byte ptr [r12+rcx]
0x18005ac0e  movzx   ecx, byte ptr [r10+rcx]
0x18005ac13  add     edx, ecx
0x18005ac15  movzx   ecx, byte ptr [r9]
0x18005ac19  add     edx, ecx
0x18005ac1b  imul    ecx, edx, 55h ; 'U'
0x18005ac1e  shr     ecx, 6
0x18005ac21  mov     [rax+4], cx
0x18005ac25  lea     rcx, [r8+r9]
0x18005ac29  movzx   edx, byte ptr [r12+rcx+1]
0x18005ac2f  movzx   ecx, byte ptr [r10+rcx+1]
0x18005ac35  add     edx, ecx
0x18005ac37  movzx   ecx, byte ptr [r9+1]
0x18005ac3c  add     edx, ecx
0x18005ac3e  imul    ecx, edx, 55h ; 'U'
0x18005ac41  shr     ecx, 6
0x18005ac44  mov     [rax+6], cx
0x18005ac48  lea     rcx, [r8+r9]
0x18005ac4c  movzx   edx, byte ptr [r12+rcx+2]
0x18005ac52  movzx   ecx, byte ptr [r10+rcx+2]
0x18005ac58  add     edx, ecx
0x18005ac5a  movzx   ecx, byte ptr [r9+2]
0x18005ac5f  add     edx, ecx
0x18005ac61  imul    ecx, edx, 55h ; 'U'
0x18005ac64  shr     ecx, 6
0x18005ac67  mov     [rax+8], cx
0x18005ac6b  lea     rcx, [r8+r9]
0x18005ac6f  movzx   edx, byte ptr [r12+rcx+3]
0x18005ac75  movzx   ecx, byte ptr [r10+rcx+3]
0x18005ac7b  add     edx, ecx
0x18005ac7d  movzx   ecx, byte ptr [r9+3]
0x18005ac82  add     edx, ecx
0x18005ac84  imul    ecx, edx, 55h ; 'U'
0x18005ac87  shr     ecx, 6
0x18005ac8a  mov     [rax+0Ah], cx
0x18005ac8e  lea     rcx, [r8+r9]
0x18005ac92  movzx   edx, byte ptr [r12+rcx+4]
0x18005ac98  movzx   ecx, byte ptr [r10+rcx+4]
0x18005ac9e  add     edx, ecx
0x18005aca0  movzx   ecx, byte ptr [r9+4]
0x18005aca5  add     edx, ecx
0x18005aca7  imul    ecx, edx, 55h ; 'U'
0x18005acaa  shr     ecx, 6
0x18005acad  mov     [rax+0Ch], cx
0x18005acb1  lea     rcx, [r8+r9]
0x18005acb5  movzx   edx, byte ptr [r12+rcx+5]
0x18005acbb  lea     r9, [r9+8]
0x18005acbf  movzx   ecx, byte ptr [r10+rcx+5]
0x18005acc5  add     edx, ecx
0x18005acc7  movzx   ecx, byte ptr [r9-3]
0x18005accc  add     edx, ecx
0x18005acce  imul    ecx, edx, 55h ; 'U'
0x18005acd1  shr     ecx, 6
0x18005acd4  mov     [rax+0Eh], cx
0x18005acd8  lea     rcx, [r9-2]
0x18005acdc  add     rcx, r8
0x18005acdf  add     rax, 10h
0x18005ace3  cmp     rcx, r13
0x18005ace6  jl      loc_18005ABC0
0x18005acec  mov     edi, [rbp+600h+var_6C]
0x18005acf2  mov     r15d, [rbp+600h+var_650]
0x18005acf6  mov     esi, [rbp+600h+var_67C]
0x18005acf9  cmp     r11d, esi
0x18005acfc  jge     short loc_18005AD48
0x18005acfe  movsxd  r8, r11d
0x18005ad01  sub     r10, r12
0x18005ad04  add     r8, r12
0x18005ad07  sub     r14, r12
0x18005ad0a  sub     esi, r11d
0x18005ad0d  mov     r9d, esi
0x18005ad10  movzx   ecx, byte ptr [r10+r8]
0x18005ad15  lea     rax, [rax+2]
0x18005ad19  movzx   edx, byte ptr [r14+r8]
0x18005ad1e  lea     r8, [r8+1]
0x18005ad22  add     edx, ecx
0x18005ad24  movzx   ecx, byte ptr [r8-1]
0x18005ad29  add     edx, ecx
0x18005ad2b  imul    ecx, edx, 55h ; 'U'
0x18005ad2e  shr     ecx, 6
0x18005ad31  mov     [rax-2], cx
0x18005ad35  sub     r9, 1
0x18005ad39  jnz     short loc_18005AD10
0x18005ad3b  mov     edi, [rbp+600h+var_6C]
0x18005ad41  mov     r15d, [rbp+600h+var_650]
0x18005ad45  mov     esi, [rbp+600h+var_67C]
0x18005ad48  mov     r13, qword ptr [rsp+700h+var_6D0]
0x18005ad4d  mov     r12, [rsp+700h+var_6C0]
0x18005ad52  movsxd  rax, edi
0x18005ad55  inc     edi
0x18005ad57  sub     r15d, [rbp+rax*4+600h+var_644]
0x18005ad5c  mov     eax, 0
0x18005ad61  cmp     edi, [rbp+600h+var_64]
0x18005ad67  cmovge  edi, eax
0x18005ad6a  inc     [rbp+600h+var_648]
0x18005ad6d  mov     [rbp+600h+var_6C], edi
0x18005ad73  mov     rax, [rsp+700h+var_6B8]
0x18005ad78  movsxd  rax, dword ptr [rax]
0x18005ad7b  add     r13, rax
0x18005ad7e  mov     eax, dword ptr [rsp+700h+var_6B0]
0x18005ad82  inc     eax
0x18005ad84  mov     qword ptr [rsp+700h+var_6D0], r13
0x18005ad89  cmp     eax, [rbp+600h+var_680]
0x18005ad8c  mov     dword ptr [rsp+700h+var_6B0], eax
0x18005ad90  mov     eax, 0
0x18005ad95  jl      loc_18005AAA0
0x18005ad9b  mov     r13, [rsp+700h+var_38]
0x18005ada3  mov     rcx, [rbp+600h+var_50]
0x18005adaa  xor     rcx, rsp; StackCookie
0x18005adad  call    __security_check_cookie
0x18005adb2  add     rsp, 6D0h
0x18005adb9  pop     r15
0x18005adbb  pop     r14
0x18005adbd  pop     r12
0x18005adbf  pop     rdi
0x18005adc0  pop     rsi
0x18005adc1  pop     rbx
0x18005adc2  pop     rbp
0x18005adc3  retn
```
