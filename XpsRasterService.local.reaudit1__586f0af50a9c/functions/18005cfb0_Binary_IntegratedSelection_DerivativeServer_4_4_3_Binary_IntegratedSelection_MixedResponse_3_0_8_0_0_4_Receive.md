# Binary::IntegratedSelection::DerivativeServer<4,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,4,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005cfb0`
- end: `0x18005d3e9`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$03$03$02$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$03$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1081`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006aab0`

## callees

- `0x180003180`
- `0x18005cfb0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,4,4,3,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
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
  unsigned int v38; // eax
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
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v56, 4, 3, a3, v52, (_DWORD *)(a1 + 8));
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
    v52[0] = (unsigned __int8 *)0x100000002LL;
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
          if ( v32 < v57 - 7 )
          {
            v37 = &v33[4 * v32 + 12];
            v38 = ((unsigned int)(v57 - 7 - v32 - 1) >> 3) + 1;
            v39 = v38;
            v32 += 8 * v38;
            do
            {
              *v34 = (85 * (*(v37 - 12) + v28[v37 - v33 - 12] + (unsigned int)v35[v37 - v33 - 12])) >> 6;
              v34[1] = (85 * (*(v37 - 4) + v28[v37 - v33 - 4] + (unsigned int)v35[v37 - v33 - 4])) >> 6;
              v34[2] = (85 * (*v37 + v28[v37 - v33] + (unsigned int)v35[v37 - v33])) >> 6;
              v34[3] = (85 * (v37[4] + v28[v37 - v33 + 4] + (unsigned int)v35[v37 - v33 + 4])) >> 6;
              v34[4] = (85 * (v37[12] + v28[v37 - v33 + 12] + (unsigned int)v35[v37 - v33 + 12])) >> 6;
              v40 = (unsigned __int8 *)(v37 - v33);
              v41 = v35[v37 - v33 + 16];
              v37 += 32;
              v34[5] = (85 * (*(v37 - 16) + (unsigned int)v28[(_QWORD)v40 + 16] + v41)) >> 6;
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
0x18005cfb0  push    rbp
0x18005cfb2  push    rbx
0x18005cfb3  push    r12
0x18005cfb5  push    r15
0x18005cfb7  lea     rbp, [rsp-5E8h]
0x18005cfbf  sub     rsp, 6E8h
0x18005cfc6  mov     rax, cs:__security_cookie
0x18005cfcd  xor     rax, rsp
0x18005cfd0  mov     [rbp+600h+var_50], rax
0x18005cfd7  movups  xmm0, xmmword ptr [r9]
0x18005cfdb  lea     rax, [rcx+8]
0x18005cfdf  mov     [rsp+700h+var_6C8], r8
0x18005cfe4  mov     [rsp+700h+var_6D8], rax
0x18005cfe9  mov     rbx, rdx
0x18005cfec  mov     edx, 4
0x18005cff1  mov     [rsp+700h+var_6D0], rcx
0x18005cff6  mov     r15, rcx
0x18005cff9  movaps  xmmword ptr [rsp+700h+var_6B0], xmm0
0x18005cffe  lea     rax, [rsp+700h+var_6B0]
0x18005d003  mov     r9, r8
0x18005d006  lea     rcx, [rbp+600h+var_680]
0x18005d00a  mov     [rsp+700h+var_6E0], rax
0x18005d00f  lea     r8d, [rdx-1]
0x18005d013  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005d018  mov     rcx, [rbx+8]
0x18005d01c  lea     r9, [rsp+700h+var_6C0]; unsigned __int8 **
0x18005d021  mov     rax, [rbx+10h]
0x18005d025  lea     r8, [rsp+700h+var_6B0]; unsigned __int8 **
0x18005d02a  mov     rdx, [rbx+18h]
0x18005d02e  xor     r12d, r12d
0x18005d031  cmp     [rbx], rcx
0x18005d034  cmovbe  rcx, [rbx]
0x18005d038  mov     rbx, [rbp+600h+var_678]
0x18005d03c  cmp     rcx, rax
0x18005d03f  cmovbe  rax, rcx
0x18005d043  lea     rcx, [rbp+600h+var_670]; this
0x18005d047  cmp     rax, rdx
0x18005d04a  cmovbe  rdx, rax; unsigned __int8 *
0x18005d04e  add     rbx, rdx
0x18005d051  mov     qword ptr [rsp+700h+var_6A0], rbx
0x18005d056  lea     rax, [rbx+1]
0x18005d05a  mov     qword ptr [rsp+700h+var_6A0+8], rax
0x18005d05f  lea     rax, [rbx+2]
0x18005d063  mov     qword ptr [rsp+700h+var_690], rax
0x18005d068  lea     rax, [rbx+3]
0x18005d06c  mov     qword ptr [rsp+700h+var_690+8], rax
0x18005d071  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005d076  test    al, al
0x18005d078  jz      loc_18005D3CC
0x18005d07e  mov     dword ptr [rsp+700h+var_6B0+4], 1
0x18005d086  mov     dword ptr [rsp+700h+var_6B0], 2
0x18005d08e  movsd   xmm0, [rsp+700h+var_6B0]
0x18005d094  mov     [rsp+700h+var_30], r13
0x18005d09c  mov     r13d, r12d
0x18005d09f  mov     [rsp+700h+var_38], r14
0x18005d0a7  mov     r14d, r12d
0x18005d0aa  movsd   [rsp+700h+var_6B0], xmm0
0x18005d0b0  mov     [rsp+700h+var_6C0], r12
0x18005d0b5  mov     dword ptr [rsp+700h+var_6B0+8], 1
0x18005d0bd  cmp     [rbp+600h+var_680], r12d
0x18005d0c1  jle     loc_18005D3BC
0x18005d0c7  movups  xmm1, [rsp+700h+var_690]
0x18005d0cc  mov     [rsp+700h+var_20], rsi
0x18005d0d4  movups  xmm0, [rsp+700h+var_6A0]
0x18005d0d9  mov     esi, [rbp+600h+var_650]
0x18005d0dc  mov     [rsp+700h+var_28], rdi
0x18005d0e4  mov     edi, [rbp+600h+var_6C]
0x18005d0ea  nop     word ptr [rax+rax+00h]
0x18005d0f0  inc     esi
0x18005d0f2  mov     [rbp+600h+var_650], esi
0x18005d0f5  cmp     esi, 1
0x18005d0f8  jnz     loc_18005D38F
0x18005d0fe  mov     edx, [r15+28h]
0x18005d102  mov     ecx, r12d
0x18005d105  mov     eax, [rbp+600h+var_64C]
0x18005d108  test    eax, eax
0x18005d10a  mov     r11d, [r15+1Ch]
0x18005d10e  movsxd  r9, dword ptr [r15+34h]
0x18005d112  cmovle  ecx, eax
0x18005d115  mov     eax, [r15+2Ch]
0x18005d119  cmp     r11d, eax
0x18005d11c  mov     r12d, [rbp+600h+var_67C]
0x18005d120  cmovl   r11d, eax
0x18005d124  sub     r11d, eax
0x18005d127  lea     r10d, [r9-1]
0x18005d12b  mov     eax, [rbp+600h+var_648]
0x18005d12e  cmp     eax, edx
0x18005d130  movups  [rsp+700h+var_6A0], xmm0
0x18005d135  cmovl   eax, edx
0x18005d138  sub     eax, edx
0x18005d13a  cdq
0x18005d13b  idiv    dword ptr [r15+30h]
0x18005d13f  movsxd  r8, edx
0x18005d142  imul    r8, r9
0x18005d146  cmp     r11d, r10d
0x18005d149  cmovle  r10d, r11d
0x18005d14d  mov     r11, qword ptr [rsp+700h+var_6A0+8]
0x18005d152  movsxd  rax, r10d
0x18005d155  add     r11, r14
0x18005d158  movsxd  r10, [rbp+600h+var_54]
0x18005d15f  add     r8, rax
0x18005d162  mov     rax, [r15+38h]
0x18005d166  neg     ecx
0x18005d168  lea     r15, [rbx+r14]
0x18005d16c  lea     r9, [rax+r8*2]
0x18005d170  movq    rax, xmm1
0x18005d175  add     r14, rax
0x18005d178  cmp     r10, 3
0x18005d17c  jge     short loc_18005D1CC
0x18005d17e  xchg    ax, ax
0x18005d180  cmp     ecx, r12d
0x18005d183  jge     short loc_18005D1C3
0x18005d185  lea     eax, ds:0[rcx*4]
0x18005d18c  movsxd  rdx, eax
0x18005d18f  movzx   eax, byte ptr [rdx+r14]
0x18005d194  movzx   r8d, byte ptr [r15+rdx]
0x18005d199  add     r8d, eax
0x18005d19c  movzx   eax, byte ptr [rdx+r11]
0x18005d1a1  add     r8d, eax
0x18005d1a4  imul    eax, r8d, 55h ; 'U'
0x18005d1a8  shr     eax, 6
0x18005d1ab  mov     [r9], ax
0x18005d1af  add     r9, 2
0x18005d1b3  mov     eax, dword ptr [rsp+r10*4+700h+var_6B0]
0x18005d1b8  inc     r10
0x18005d1bb  add     ecx, eax
0x18005d1bd  cmp     r10, 3
0x18005d1c1  jl      short loc_18005D180
0x18005d1c3  mov     edi, [rbp+600h+var_6C]
0x18005d1c9  mov     esi, [rbp+600h+var_650]
0x18005d1cc  mov     edx, [rbp+600h+var_67C]
0x18005d1cf  add     edx, 0FFFFFFF9h
0x18005d1d2  cmp     ecx, edx
0x18005d1d4  jge     loc_18005D2EF
0x18005d1da  sub     edx, ecx
0x18005d1dc  movsxd  r8, ecx
0x18005d1df  add     r8, 3
0x18005d1e3  mov     r10, r15
0x18005d1e6  neg     r10
0x18005d1e9  lea     eax, [rdx-1]
0x18005d1ec  shr     eax, 3
0x18005d1ef  lea     r8, [r15+r8*4]
0x18005d1f3  inc     eax
0x18005d1f5  mov     edi, eax
0x18005d1f7  lea     ecx, [rcx+rax*8]
0x18005d1fa  nop     word ptr [rax+rax+00h]
0x18005d200  lea     rax, [r8+r10]
0x18005d204  movzx   edx, byte ptr [r14+rax-0Ch]
0x18005d20a  movzx   eax, byte ptr [rax+r11-0Ch]
0x18005d210  add     edx, eax
0x18005d212  movzx   eax, byte ptr [r8-0Ch]
0x18005d217  add     edx, eax
0x18005d219  imul    eax, edx, 55h ; 'U'
0x18005d21c  shr     eax, 6
0x18005d21f  mov     [r9], ax
0x18005d223  lea     rax, [r10+r8]
0x18005d227  movzx   edx, byte ptr [rax+r14-4]
0x18005d22d  movzx   eax, byte ptr [rax+r11-4]
0x18005d233  add     edx, eax
0x18005d235  movzx   eax, byte ptr [r8-4]
0x18005d23a  add     edx, eax
0x18005d23c  imul    eax, edx, 55h ; 'U'
0x18005d23f  shr     eax, 6
0x18005d242  mov     [r9+2], ax
0x18005d247  lea     rax, [r10+r8]
0x18005d24b  movzx   edx, byte ptr [rax+r14]
0x18005d250  movzx   eax, byte ptr [rax+r11]
0x18005d255  add     edx, eax
0x18005d257  movzx   eax, byte ptr [r8]
0x18005d25b  add     edx, eax
0x18005d25d  imul    eax, edx, 55h ; 'U'
0x18005d260  shr     eax, 6
0x18005d263  mov     [r9+4], ax
0x18005d268  lea     rax, [r10+r8]
0x18005d26c  movzx   edx, byte ptr [rax+r14+4]
0x18005d272  movzx   eax, byte ptr [rax+r11+4]
0x18005d278  add     edx, eax
0x18005d27a  movzx   eax, byte ptr [r8+4]
0x18005d27f  add     edx, eax
0x18005d281  imul    eax, edx, 55h ; 'U'
0x18005d284  shr     eax, 6
0x18005d287  mov     [r9+6], ax
0x18005d28c  lea     rax, [r8+r10]
0x18005d290  movzx   edx, byte ptr [r14+rax+0Ch]
0x18005d296  movzx   eax, byte ptr [r11+rax+0Ch]
0x18005d29c  add     edx, eax
0x18005d29e  movzx   eax, byte ptr [r8+0Ch]
0x18005d2a3  add     edx, eax
0x18005d2a5  imul    eax, edx, 55h ; 'U'
0x18005d2a8  shr     eax, 6
0x18005d2ab  mov     [r9+8], ax
0x18005d2b0  lea     rax, [r8+r10]
0x18005d2b4  movzx   edx, byte ptr [r14+rax+10h]
0x18005d2ba  lea     r8, [r8+20h]
0x18005d2be  movzx   eax, byte ptr [rax+r11+10h]
0x18005d2c4  add     edx, eax
0x18005d2c6  movzx   eax, byte ptr [r8-10h]
0x18005d2cb  add     edx, eax
0x18005d2cd  imul    eax, edx, 55h ; 'U'
0x18005d2d0  shr     eax, 6
0x18005d2d3  mov     [r9+0Ah], ax
0x18005d2d8  add     r9, 0Ch
0x18005d2dc  sub     rdi, 1
0x18005d2e0  jnz     loc_18005D200
0x18005d2e6  mov     edi, [rbp+600h+var_6C]
0x18005d2ec  mov     esi, [rbp+600h+var_650]
0x18005d2ef  mov     r12d, [rbp+600h+var_67C]
0x18005d2f3  xor     r10d, r10d
0x18005d2f6  cmp     ecx, r12d
0x18005d2f9  jge     short loc_18005D363
0x18005d2fb  nop     dword ptr [rax+rax+00h]
0x18005d300  lea     eax, ds:0[rcx*4]
0x18005d307  movsxd  rdx, eax
0x18005d30a  lea     r9, [r9+2]
0x18005d30e  movzx   eax, byte ptr [rdx+r11]
0x18005d313  movzx   r8d, byte ptr [rdx+r14]
0x18005d318  add     r8d, eax
0x18005d31b  movzx   eax, byte ptr [rdx+r15]
0x18005d320  add     r8d, eax
0x18005d323  imul    eax, r8d, 55h ; 'U'
0x18005d327  shr     eax, 6
0x18005d32a  mov     [r9-2], ax
0x18005d32f  movsxd  rax, r10d
0x18005d332  inc     r10d
0x18005d335  add     ecx, dword ptr [rsp+rax*4+700h+var_6B0]
0x18005d339  mov     eax, 55555555h
0x18005d33e  imul    r10d
0x18005d341  sub     edx, r10d
0x18005d344  sar     edx, 1
0x18005d346  mov     eax, edx
0x18005d348  shr     eax, 1Fh
0x18005d34b  add     edx, eax
0x18005d34d  lea     eax, [r10+rdx]
0x18005d351  lea     r10d, [rax+rdx*2]
0x18005d355  cmp     ecx, r12d
0x18005d358  jl      short loc_18005D300
0x18005d35a  mov     edi, [rbp+600h+var_6C]
0x18005d360  mov     esi, [rbp+600h+var_650]
0x18005d363  mov     r14, [rsp+700h+var_6C0]
0x18005d368  mov     r12d, 0
0x18005d36e  mov     r15, [rsp+700h+var_6D0]
0x18005d373  movsxd  rax, edi
0x18005d376  inc     edi
0x18005d378  sub     esi, [rbp+rax*4+600h+var_644]
0x18005d37c  cmp     edi, [rbp+600h+var_64]
0x18005d382  cmovge  edi, r12d
0x18005d386  inc     [rbp+600h+var_648]
0x18005d389  mov     [rbp+600h+var_6C], edi
0x18005d38f  mov     rax, [rsp+700h+var_6C8]
0x18005d394  inc     r13d
0x18005d397  movsxd  rax, dword ptr [rax]
0x18005d39a  add     r14, rax
0x18005d39d  mov     [rsp+700h+var_6C0], r14
0x18005d3a2  cmp     r13d, [rbp+600h+var_680]
0x18005d3a6  jl      loc_18005D0F0
0x18005d3ac  mov     rdi, [rsp+700h+var_28]
0x18005d3b4  mov     rsi, [rsp+700h+var_20]
0x18005d3bc  mov     r13, [rsp+700h+var_30]
0x18005d3c4  mov     r14, [rsp+700h+var_38]
0x18005d3cc  mov     rcx, [rbp+600h+var_50]
0x18005d3d3  xor     rcx, rsp; StackCookie
0x18005d3d6  call    __security_check_cookie
0x18005d3db  add     rsp, 6E8h
0x18005d3e2  pop     r15
0x18005d3e4  pop     r12
0x18005d3e6  pop     rbx
0x18005d3e7  pop     rbp
0x18005d3e8  retn
```
