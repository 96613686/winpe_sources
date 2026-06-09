# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005c580`
- end: `0x18005cb22`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$03$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1442`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aa90`

## callees

- `0x180003180`
- `0x18005c580`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r14
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  __int64 v10; // rax
  int v11; // ecx
  int v12; // r12d
  __int64 v13; // r13
  __int64 v14; // xmm1_8
  int v15; // edx
  __int128 v16; // xmm0
  int v17; // esi
  int v18; // edi
  int v19; // ecx
  int v20; // r11d
  int v21; // edx
  int v22; // r10d
  __int64 v23; // r8
  int v24; // r10d
  int v25; // r9d
  int v26; // edx
  __int64 v27; // rax
  unsigned __int8 *v28; // r14
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdi
  __int64 v32; // r10
  _WORD *v33; // r9
  _WORD *v34; // r9
  int v35; // edx
  __int64 i; // r11
  __int64 v37; // r8
  unsigned int v38; // ecx
  int v39; // eax
  int v40; // r15d
  __int64 v41; // r11
  unsigned __int8 *v42; // rax
  unsigned int v43; // edx
  unsigned int v44; // edx
  unsigned int v45; // edx
  unsigned int v46; // edx
  unsigned int v47; // edx
  unsigned int v48; // edx
  unsigned int v49; // edx
  unsigned int v50; // edx
  int v51; // r8d
  __int64 v52; // r10
  unsigned __int8 *v53; // r14
  unsigned __int8 *v54; // rdx
  __int64 v55; // r8
  unsigned int v56; // ecx
  int v57; // ecx
  unsigned __int8 *v61[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v62[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v63; // [rsp+60h] [rbp-A0h]
  __int64 v64; // [rsp+70h] [rbp-90h]
  __int64 v65; // [rsp+78h] [rbp-88h]
  int v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+84h] [rbp-7Ch]
  __int64 v68; // [rsp+88h] [rbp-78h]
  char v69[32]; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+B0h] [rbp-50h]
  int v71; // [rsp+B4h] [rbp-4Ch]
  int v72; // [rsp+B8h] [rbp-48h]
  _DWORD v73[374]; // [rsp+BCh] [rbp-44h]
  int v74; // [rsp+694h] [rbp+594h]
  int v75; // [rsp+69Ch] [rbp+59Ch]
  int v76; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v62 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v66, 2, 1, (_DWORD)a3, (__int64)v62, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v68];
  *(_QWORD *)&v63 = &v8[v68];
  *((_QWORD *)&v63 + 1) = &v8[v68 + 1];
  v64 = (__int64)&v8[v68 + 2];
  v65 = (__int64)&v8[v68 + 3];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v69,
                  v8,
                  v62,
                  v61);
  if ( (_BYTE)v10 )
  {
    v11 = v66;
    v12 = 0;
    v13 = 0;
    LODWORD(v61[0]) = 2;
    if ( v66 > 0 )
    {
      v14 = v64;
      v15 = v70;
      v16 = v63;
      v17 = v67;
      v18 = v72;
      do
      {
        v70 = ++v15;
        if ( v15 == 1 )
        {
          v19 = *(_DWORD *)(v5 + 44);
          v20 = 0;
          v21 = *(_DWORD *)(v5 + 40);
          v22 = *(_DWORD *)(v5 + 28);
          v23 = *(int *)(v5 + 52);
          if ( v71 <= 0 )
            v20 = v71;
          v63 = v16;
          if ( v22 < v19 )
            v22 = v19;
          v24 = v22 - v19;
          v25 = v23 - 1;
          if ( v18 < v21 )
            v18 = v21;
          v26 = (v18 - v21) % *(_DWORD *)(v5 + 48);
          v27 = *(_QWORD *)(v5 + 56);
          v28 = &v9[v13];
          v29 = v23 * v26;
          v30 = v76;
          if ( v24 <= v25 )
            v25 = v24;
          v31 = v13 + *((_QWORD *)&v63 + 1);
          v32 = v13 + v14;
          v33 = (_WORD *)(v27 + 2 * v29 + 2LL * v25);
          *v33 = (85
                * (*(unsigned __int8 *)(-4 * v20 + v13 + *((_QWORD *)&v63 + 1))
                 + *(unsigned __int8 *)(-4 * v20 + v13 + v14)
                 + (unsigned int)v28[-4 * v20])) >> 6;
          v34 = v33 + 1;
          v35 = *((_DWORD *)v61 + v30) - v20;
          for ( i = (int)v30 + 1; i < 1; v35 += v39 )
          {
            if ( v35 >= v17 )
              break;
            v37 = 4 * v35;
            v38 = *(unsigned __int8 *)(v37 + v31) + *(unsigned __int8 *)(v37 + v32) + v28[v37];
            if ( v38 > 0x2F4 )
              v38 = *(unsigned __int8 *)(v37 + v31 - 4) + *(unsigned __int8 *)(v37 + v32 - 4) + v28[v37 - 4];
            *v34++ = (85 * v38) >> 6;
            v39 = *((_DWORD *)v61 + i++);
          }
          v17 = v67;
          v40 = v35 - 1;
          if ( v35 - 1 < v67 - 15 )
          {
            v41 = ((unsigned int)(v67 - 15 - v35) >> 4) + 1;
            v42 = &v28[4 * v40 + 12];
            v40 += 16 * v41;
            do
            {
              v43 = *(v42 - 8) + *(unsigned __int8 *)(v31 + v42 - v28 - 8) + *(unsigned __int8 *)(v32 + v42 - v28 - 8);
              if ( v43 > 0x2F4 )
                v43 = *(v42 - 12)
                    + *(unsigned __int8 *)(v42 - v28 + v31 - 12)
                    + *(unsigned __int8 *)(v42 - v28 + v32 - 12);
              *v34 = (85 * v43) >> 6;
              v44 = *v42 + *(unsigned __int8 *)(v31 + v42 - v28) + *(unsigned __int8 *)(v32 + v42 - v28);
              if ( v44 > 0x2F4 )
                v44 = *(v42 - 4) + *(unsigned __int8 *)(v31 + v42 - v28 - 4) + *(unsigned __int8 *)(v32 + v42 - v28 - 4);
              v34[1] = (85 * v44) >> 6;
              v45 = v42[8] + *(unsigned __int8 *)(v42 - v28 + v31 + 8) + *(unsigned __int8 *)(v42 - v28 + v32 + 8);
              if ( v45 > 0x2F4 )
                v45 = v42[4] + *(unsigned __int8 *)(v42 - v28 + v31 + 4) + *(unsigned __int8 *)(v42 - v28 + v32 + 4);
              v34[2] = (85 * v45) >> 6;
              v46 = v42[16] + *(unsigned __int8 *)(v42 - v28 + v31 + 16) + *(unsigned __int8 *)(v42 - v28 + v32 + 16);
              if ( v46 > 0x2F4 )
                v46 = v42[12] + *(unsigned __int8 *)(v42 - v28 + v31 + 12) + *(unsigned __int8 *)(v42 - v28 + v32 + 12);
              v34[3] = (85 * v46) >> 6;
              v47 = v42[24] + *(unsigned __int8 *)(v42 - v28 + v31 + 24) + *(unsigned __int8 *)(v42 - v28 + v32 + 24);
              if ( v47 > 0x2F4 )
                v47 = v42[20] + *(unsigned __int8 *)(v42 - v28 + v31 + 20) + *(unsigned __int8 *)(v42 - v28 + v32 + 20);
              v34[4] = (85 * v47) >> 6;
              v48 = v42[32] + *(unsigned __int8 *)(v42 - v28 + v31 + 32) + *(unsigned __int8 *)(v42 - v28 + v32 + 32);
              if ( v48 > 0x2F4 )
                v48 = v42[28] + *(unsigned __int8 *)(v42 - v28 + v31 + 28) + *(unsigned __int8 *)(v42 - v28 + v32 + 28);
              v34[5] = (85 * v48) >> 6;
              v49 = v42[40] + *(unsigned __int8 *)(v42 - v28 + v31 + 40) + *(unsigned __int8 *)(v42 - v28 + v32 + 40);
              if ( v49 > 0x2F4 )
                v49 = v42[36] + *(unsigned __int8 *)(v42 - v28 + v31 + 36) + *(unsigned __int8 *)(v42 - v28 + v32 + 36);
              v34[6] = (85 * v49) >> 6;
              v50 = v42[48] + *(unsigned __int8 *)(v42 - v28 + v31 + 48) + *(unsigned __int8 *)(v42 - v28 + v32 + 48);
              if ( v50 > 0x2F4 )
                v50 = v42[44] + *(unsigned __int8 *)(v42 - v28 + v31 + 44) + *(unsigned __int8 *)(v42 - v28 + v32 + 44);
              v42 += 64;
              v34[7] = (85 * v50) >> 6;
              v34 += 8;
              --v41;
            }
            while ( v41 );
            v17 = v67;
          }
          v51 = v40 + 1;
          if ( v40 + 1 < v17 )
          {
            v52 = v32 - v31;
            v53 = &v28[-v31];
            v54 = (unsigned __int8 *)(v31 + 4 * v51 - 4LL);
            v55 = ((unsigned int)(v17 - v51 - 1) >> 1) + 1;
            do
            {
              v56 = v54[4] + v54[(_QWORD)v53 + 4] + v54[v52 + 4];
              if ( v56 > 0x2F4 )
                v56 = *v54 + v54[v52] + v54[(_QWORD)v53];
              v54 += 8;
              *v34++ = (85 * v56) >> 6;
              --v55;
            }
            while ( v55 );
            v17 = v67;
          }
          v5 = a1;
          v15 = v70 - v73[v74];
          v57 = v74 + 1;
          if ( v74 + 1 >= v75 )
            v57 = 0;
          v18 = v72 + 1;
          v74 = v57;
          v11 = v66;
          ++v72;
        }
        ++v12;
        v10 = *a3;
        v13 += v10;
      }
      while ( v12 < v11 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005c580  push    rbp
0x18005c582  push    rbx
0x18005c583  push    r14
0x18005c585  push    r15
0x18005c587  lea     rbp, [rsp-5E8h]
0x18005c58f  sub     rsp, 6E8h
0x18005c596  mov     rax, cs:__security_cookie
0x18005c59d  xor     rax, rsp
0x18005c5a0  mov     [rbp+600h+var_50], rax
0x18005c5a7  movups  xmm0, xmmword ptr [r9]
0x18005c5ab  lea     rax, [rcx+8]
0x18005c5af  mov     [rsp+700h+var_6C8], r8
0x18005c5b4  mov     [rsp+700h+var_6D8], rax
0x18005c5b9  mov     rbx, rdx
0x18005c5bc  mov     edx, 2
0x18005c5c1  mov     [rsp+700h+var_6D0], rcx
0x18005c5c6  mov     r14, rcx
0x18005c5c9  movaps  xmmword ptr [rsp+700h+var_6B0], xmm0
0x18005c5ce  lea     rax, [rsp+700h+var_6B0]
0x18005c5d3  mov     r9, r8
0x18005c5d6  lea     rcx, [rbp+600h+var_680]
0x18005c5da  mov     [rsp+700h+var_6E0], rax
0x18005c5df  lea     r8d, [rdx-1]
0x18005c5e3  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005c5e8  mov     rcx, [rbx+8]
0x18005c5ec  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005c5f1  mov     rax, [rbx+10h]
0x18005c5f5  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005c5fa  mov     rdx, [rbx+18h]
0x18005c5fe  xor     r15d, r15d
0x18005c601  cmp     [rbx], rcx
0x18005c604  cmovbe  rcx, [rbx]
0x18005c608  mov     rbx, [rbp+600h+var_678]
0x18005c60c  cmp     rcx, rax
0x18005c60f  cmovbe  rax, rcx
0x18005c613  lea     rcx, [rbp+600h+var_670]; this
0x18005c617  cmp     rax, rdx
0x18005c61a  cmovbe  rdx, rax; unsigned __int8 *
0x18005c61e  add     rbx, rdx
0x18005c621  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005c626  lea     rax, [rbx+1]
0x18005c62a  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005c62f  lea     rax, [rbx+2]
0x18005c633  mov     qword ptr [rsp+700h+var_690], rax
0x18005c638  lea     rax, [rbx+3]
0x18005c63c  mov     qword ptr [rsp+700h+var_690+8], rax
0x18005c641  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005c646  test    al, al
0x18005c648  jz      loc_18005CB05
0x18005c64e  mov     ecx, [rbp+600h+var_680]
0x18005c651  mov     [rsp+700h+var_30], r12
0x18005c659  mov     r12d, r15d
0x18005c65c  mov     [rsp+700h+var_38], r13
0x18005c664  mov     r13d, r15d
0x18005c667  mov     dword ptr [rsp+700h+var_6C0], 2
0x18005c66f  test    ecx, ecx
0x18005c671  jle     loc_18005CAF5
0x18005c677  movups  xmm1, [rsp+700h+var_690]
0x18005c67c  mov     edx, [rbp+600h+var_650]
0x18005c67f  movups  xmm0, [rsp+700h+var_6A0]
0x18005c684  mov     [rsp+700h+var_20], rsi
0x18005c68c  mov     esi, [rbp+600h+var_67C]
0x18005c68f  mov     [rsp+700h+var_28], rdi
0x18005c697  mov     edi, [rbp+600h+var_648]
0x18005c69a  nop     word ptr [rax+rax+00h]
0x18005c6a0  inc     edx
0x18005c6a2  mov     [rbp+600h+var_650], edx
0x18005c6a5  cmp     edx, 1
0x18005c6a8  jnz     loc_18005CACE
0x18005c6ae  mov     ecx, [r14+2Ch]
0x18005c6b2  mov     r11d, r15d
0x18005c6b5  mov     edx, [r14+28h]
0x18005c6b9  mov     eax, [rbp+600h+var_64C]
0x18005c6bc  test    eax, eax
0x18005c6be  mov     r10d, [r14+1Ch]
0x18005c6c2  movsxd  r8, dword ptr [r14+34h]
0x18005c6c6  cmovle  r11d, eax
0x18005c6ca  cmp     r10d, ecx
0x18005c6cd  movups  [rsp+700h+var_6A0], xmm0
0x18005c6d2  cmovl   r10d, ecx
0x18005c6d6  sub     r10d, ecx
0x18005c6d9  lea     r9d, [r8-1]
0x18005c6dd  cmp     edi, edx
0x18005c6df  cmovl   edi, edx
0x18005c6e2  sub     edi, edx
0x18005c6e4  mov     eax, edi
0x18005c6e6  mov     rdi, qword ptr [rsp+700h+var_6A0+8]
0x18005c6eb  cdq
0x18005c6ec  idiv    dword ptr [r14+30h]
0x18005c6f0  mov     rax, [r14+38h]
0x18005c6f4  lea     r14, [rbx+r13]
0x18005c6f8  movsxd  rcx, edx
0x18005c6fb  imul    rcx, r8
0x18005c6ff  movsxd  r8, [rbp+600h+var_54]
0x18005c706  cmp     r10d, r9d
0x18005c709  cmovle  r9d, r10d
0x18005c70d  add     rdi, r13
0x18005c710  movq    r10, xmm1
0x18005c715  lea     rax, [rax+rcx*2]
0x18005c719  add     r10, r13
0x18005c71c  movsxd  rcx, r9d
0x18005c71f  lea     r9, [rax+rcx*2]
0x18005c723  mov     eax, r11d
0x18005c726  neg     eax
0x18005c728  shl     eax, 2
0x18005c72b  movsxd  rcx, eax
0x18005c72e  movzx   eax, byte ptr [rcx+r10]
0x18005c733  movzx   edx, byte ptr [r14+rcx]
0x18005c738  add     edx, eax
0x18005c73a  movzx   eax, byte ptr [rcx+rdi]
0x18005c73e  add     edx, eax
0x18005c740  imul    eax, edx, 55h ; 'U'
0x18005c743  shr     eax, 6
0x18005c746  mov     [r9], ax
0x18005c74a  lea     eax, [r8+1]
0x18005c74e  mov     edx, dword ptr [rsp+r8*4+700h+var_6C0]
0x18005c753  add     r9, 2
0x18005c757  sub     edx, r11d
0x18005c75a  movsxd  r11, eax
0x18005c75d  cmp     r11, 1
0x18005c761  jge     short loc_18005C7C0
0x18005c763  cmp     edx, esi
0x18005c765  jge     short loc_18005C7C0
0x18005c767  lea     eax, ds:0[rdx*4]
0x18005c76e  movsxd  r8, eax
0x18005c771  movzx   eax, byte ptr [r8+r10]
0x18005c776  movzx   ecx, byte ptr [r8+r14]
0x18005c77b  add     ecx, eax
0x18005c77d  movzx   eax, byte ptr [r8+rdi]
0x18005c782  add     ecx, eax
0x18005c784  cmp     ecx, 2F4h
0x18005c78a  jbe     short loc_18005C7A2
0x18005c78c  movzx   eax, byte ptr [r8+r10-4]
0x18005c792  movzx   ecx, byte ptr [r8+r14-4]
0x18005c798  add     ecx, eax
0x18005c79a  movzx   eax, byte ptr [r8+rdi-4]
0x18005c7a0  add     ecx, eax
0x18005c7a2  imul    eax, ecx, 55h ; 'U'
0x18005c7a5  shr     eax, 6
0x18005c7a8  mov     [r9], ax
0x18005c7ac  add     r9, 2
0x18005c7b0  mov     eax, dword ptr [rsp+r11*4+700h+var_6C0]
0x18005c7b5  inc     r11
0x18005c7b8  add     edx, eax
0x18005c7ba  cmp     r11, 1
0x18005c7be  jl      short loc_18005C763
0x18005c7c0  mov     esi, [rbp+600h+var_67C]
0x18005c7c3  lea     r15d, [rdx-1]
0x18005c7c7  lea     ecx, [rsi-0Fh]
0x18005c7ca  cmp     r15d, ecx
0x18005c7cd  jge     loc_18005CA19
0x18005c7d3  sub     ecx, r15d
0x18005c7d6  movsxd  rax, r15d
0x18005c7d9  dec     ecx
0x18005c7db  add     rax, 3
0x18005c7df  shr     ecx, 4
0x18005c7e2  mov     r8, r14
0x18005c7e5  neg     r8
0x18005c7e8  inc     ecx
0x18005c7ea  mov     r11d, ecx
0x18005c7ed  lea     rax, [r14+rax*4]
0x18005c7f1  shl     ecx, 4
0x18005c7f4  add     r15d, ecx
0x18005c7f7  nop     word ptr [rax+rax+00000000h]
0x18005c800  lea     rcx, [r8+rax]
0x18005c804  movzx   edx, byte ptr [r10+rcx-8]
0x18005c80a  movzx   ecx, byte ptr [rdi+rcx-8]
0x18005c80f  add     edx, ecx
0x18005c811  movzx   ecx, byte ptr [rax-8]
0x18005c815  add     edx, ecx
0x18005c817  cmp     edx, 2F4h
0x18005c81d  jbe     short loc_18005C836
0x18005c81f  lea     rcx, [r8+rax]
0x18005c823  movzx   edx, byte ptr [rcx+r10-0Ch]
0x18005c829  movzx   ecx, byte ptr [rcx+rdi-0Ch]
0x18005c82e  add     edx, ecx
0x18005c830  movzx   ecx, byte ptr [rax-0Ch]
0x18005c834  add     edx, ecx
0x18005c836  imul    ecx, edx, 55h ; 'U'
0x18005c839  shr     ecx, 6
0x18005c83c  mov     [r9], cx
0x18005c840  lea     rcx, [r8+rax]
0x18005c844  movzx   edx, byte ptr [r10+rcx]
0x18005c849  movzx   ecx, byte ptr [rdi+rcx]
0x18005c84d  add     edx, ecx
0x18005c84f  movzx   ecx, byte ptr [rax]
0x18005c852  add     edx, ecx
0x18005c854  cmp     edx, 2F4h
0x18005c85a  jbe     short loc_18005C873
0x18005c85c  lea     rcx, [r8+rax]
0x18005c860  movzx   edx, byte ptr [r10+rcx-4]
0x18005c866  movzx   ecx, byte ptr [rdi+rcx-4]
0x18005c86b  add     edx, ecx
0x18005c86d  movzx   ecx, byte ptr [rax-4]
0x18005c871  add     edx, ecx
0x18005c873  imul    ecx, edx, 55h ; 'U'
0x18005c876  shr     ecx, 6
0x18005c879  mov     [r9+2], cx
0x18005c87e  lea     rcx, [r8+rax]
0x18005c882  movzx   edx, byte ptr [rcx+r10+8]
0x18005c888  movzx   ecx, byte ptr [rcx+rdi+8]
0x18005c88d  add     edx, ecx
0x18005c88f  movzx   ecx, byte ptr [rax+8]
0x18005c893  add     edx, ecx
0x18005c895  cmp     edx, 2F4h
0x18005c89b  jbe     short loc_18005C8B4
0x18005c89d  lea     rcx, [r8+rax]
0x18005c8a1  movzx   edx, byte ptr [rcx+r10+4]
0x18005c8a7  movzx   ecx, byte ptr [rcx+rdi+4]
0x18005c8ac  add     edx, ecx
0x18005c8ae  movzx   ecx, byte ptr [rax+4]
0x18005c8b2  add     edx, ecx
0x18005c8b4  imul    ecx, edx, 55h ; 'U'
0x18005c8b7  shr     ecx, 6
0x18005c8ba  mov     [r9+4], cx
0x18005c8bf  lea     rcx, [r8+rax]
0x18005c8c3  movzx   edx, byte ptr [rcx+r10+10h]
0x18005c8c9  movzx   ecx, byte ptr [rcx+rdi+10h]
0x18005c8ce  add     edx, ecx
0x18005c8d0  movzx   ecx, byte ptr [rax+10h]
0x18005c8d4  add     edx, ecx
0x18005c8d6  cmp     edx, 2F4h
0x18005c8dc  jbe     short loc_18005C8F5
0x18005c8de  lea     rcx, [r8+rax]
0x18005c8e2  movzx   edx, byte ptr [rcx+r10+0Ch]
0x18005c8e8  movzx   ecx, byte ptr [rcx+rdi+0Ch]
0x18005c8ed  add     edx, ecx
0x18005c8ef  movzx   ecx, byte ptr [rax+0Ch]
0x18005c8f3  add     edx, ecx
0x18005c8f5  imul    ecx, edx, 55h ; 'U'
0x18005c8f8  shr     ecx, 6
0x18005c8fb  mov     [r9+6], cx
0x18005c900  lea     rcx, [r8+rax]
0x18005c904  movzx   edx, byte ptr [rcx+r10+18h]
0x18005c90a  movzx   ecx, byte ptr [rcx+rdi+18h]
0x18005c90f  add     edx, ecx
0x18005c911  movzx   ecx, byte ptr [rax+18h]
0x18005c915  add     edx, ecx
0x18005c917  cmp     edx, 2F4h
0x18005c91d  jbe     short loc_18005C936
0x18005c91f  lea     rcx, [r8+rax]
0x18005c923  movzx   edx, byte ptr [rcx+r10+14h]
0x18005c929  movzx   ecx, byte ptr [rcx+rdi+14h]
0x18005c92e  add     edx, ecx
0x18005c930  movzx   ecx, byte ptr [rax+14h]
0x18005c934  add     edx, ecx
0x18005c936  imul    ecx, edx, 55h ; 'U'
0x18005c939  shr     ecx, 6
0x18005c93c  mov     [r9+8], cx
0x18005c941  lea     rcx, [r8+rax]
0x18005c945  movzx   edx, byte ptr [rcx+r10+20h]
0x18005c94b  movzx   ecx, byte ptr [rcx+rdi+20h]
0x18005c950  add     edx, ecx
0x18005c952  movzx   ecx, byte ptr [rax+20h]
0x18005c956  add     edx, ecx
0x18005c958  cmp     edx, 2F4h
0x18005c95e  jbe     short loc_18005C977
0x18005c960  lea     rcx, [r8+rax]
0x18005c964  movzx   edx, byte ptr [rcx+r10+1Ch]
0x18005c96a  movzx   ecx, byte ptr [rcx+rdi+1Ch]
0x18005c96f  add     edx, ecx
0x18005c971  movzx   ecx, byte ptr [rax+1Ch]
0x18005c975  add     edx, ecx
0x18005c977  imul    ecx, edx, 55h ; 'U'
0x18005c97a  shr     ecx, 6
0x18005c97d  mov     [r9+0Ah], cx
0x18005c982  lea     rcx, [r8+rax]
0x18005c986  movzx   edx, byte ptr [rcx+r10+28h]
0x18005c98c  movzx   ecx, byte ptr [rcx+rdi+28h]
0x18005c991  add     edx, ecx
0x18005c993  movzx   ecx, byte ptr [rax+28h]
0x18005c997  add     edx, ecx
0x18005c999  cmp     edx, 2F4h
0x18005c99f  jbe     short loc_18005C9B8
0x18005c9a1  lea     rcx, [r8+rax]
0x18005c9a5  movzx   edx, byte ptr [rcx+r10+24h]
0x18005c9ab  movzx   ecx, byte ptr [rcx+rdi+24h]
0x18005c9b0  add     edx, ecx
0x18005c9b2  movzx   ecx, byte ptr [rax+24h]
0x18005c9b6  add     edx, ecx
0x18005c9b8  imul    ecx, edx, 55h ; 'U'
0x18005c9bb  shr     ecx, 6
0x18005c9be  mov     [r9+0Ch], cx
0x18005c9c3  lea     rcx, [r8+rax]
0x18005c9c7  movzx   edx, byte ptr [rcx+r10+30h]
0x18005c9cd  movzx   ecx, byte ptr [rcx+rdi+30h]
0x18005c9d2  add     edx, ecx
0x18005c9d4  movzx   ecx, byte ptr [rax+30h]
0x18005c9d8  add     edx, ecx
0x18005c9da  cmp     edx, 2F4h
0x18005c9e0  jbe     short loc_18005C9F9
0x18005c9e2  lea     rcx, [r8+rax]
0x18005c9e6  movzx   edx, byte ptr [rcx+r10+2Ch]
0x18005c9ec  movzx   ecx, byte ptr [rcx+rdi+2Ch]
0x18005c9f1  add     edx, ecx
0x18005c9f3  movzx   ecx, byte ptr [rax+2Ch]
0x18005c9f7  add     edx, ecx
0x18005c9f9  imul    ecx, edx, 55h ; 'U'
0x18005c9fc  add     rax, 40h ; '@'
0x18005ca00  shr     ecx, 6
  ... truncated ...
```
