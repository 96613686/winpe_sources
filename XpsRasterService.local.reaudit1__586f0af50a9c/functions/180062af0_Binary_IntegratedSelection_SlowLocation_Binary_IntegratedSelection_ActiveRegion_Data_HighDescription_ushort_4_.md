# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,1,16,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x180062af0`
- end: `0x180063053`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@V?$MixedResponse@$02$00$0BA@$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `1379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800568d0`

## callees

- `0x180058980`
- `0x180062af0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>,Binary::IntegratedSelection::MixedResponse<3,1,16,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // r11d
  __int64 v4; // rbx
  int v8; // r11d
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rax
  int v16; // edi
  __int64 v17; // r13
  int v18; // edx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // r13
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // r13
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  __int64 v35; // r13
  __int64 i; // rdi
  __int64 v37; // rsi
  int v38; // ecx
  int v39; // r8d
  int v40; // r13d
  __int64 v41; // r15
  int v42; // esi
  int v43; // edi
  char v44; // al
  int v45; // r9d
  __int64 v46; // rdx
  int v47; // ecx
  int v48; // edi
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  __int64 v53; // [rsp+20h] [rbp-10h]
  __int64 v54; // [rsp+70h] [rbp+40h] BYREF
  __int64 v55; // [rsp+78h] [rbp+48h] BYREF
  __int64 v56; // [rsp+88h] [rbp+58h] BYREF

  v54 = (__int64)a1;
  v3 = a1[8];
  v4 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += 8LL * v8;
  v9 = a1[11];
  if ( v9 == 1 )
  {
    v10 = (int)a1[388];
    v11 = *a3;
    v12 = *(_DWORD *)a2 - v8;
    LODWORD(v54) = v10;
    if ( (_DWORD)v10 == 1 )
    {
      v20 = a1[3];
      if ( v20 > (int)v11 )
        v20 = v11;
      if ( v20 <= v12 )
        v12 = v20;
      LODWORD(v54) = v12;
      v21 = 8LL * (v12 / 8);
      LOBYTE(v15) = 8 * (v12 / 8);
      if ( (unsigned __int64)(v21 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        LOBYTE(v15) = 8 * (v12 / 8);
        v56 = (int)v21;
        if ( (int)v21 > 0 )
        {
          v22 = 2;
          v23 = 0;
          v24 = 6;
          do
          {
            v25 = *(_QWORD *)(a2 + 8) + 8 * v23;
            v55 = v25;
            v26 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v26 > 0x3ECu && (int)v4 > 0 )
            {
              v55 = v25 - 8;
              v26 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1) - 6) = v26;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 - 1);
            v27 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v27 > 0x3ECu && v22 - 1 > 0 )
            {
              v55 -= 8;
              v27 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 - 4) = v27;
            v28 = *(_QWORD *)(a2 + 8) + 8LL * v22;
            v55 = v28;
            v29 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v29 > 0x3ECu && v22 > 0 )
            {
              v55 = v28 - 8;
              v29 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 - 2) = v29;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 + 1);
            v30 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v30 > 0x3ECu && v22 + 1 > 0 )
            {
              v55 -= 8;
              v30 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(v24 + *((_QWORD *)a3 + 1)) = v30;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 + 2);
            v31 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v31 > 0x3ECu && v22 + 2 > 0 )
            {
              v55 -= 8;
              v31 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 + 2) = v31;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 + 3);
            v32 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v32 > 0x3ECu && v22 + 3 > 0 )
            {
              v55 -= 8;
              v32 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 + 4) = v32;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 + 4);
            v33 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v33 > 0x3ECu && v22 + 4 > 0 )
            {
              v55 -= 8;
              v33 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            *(_WORD *)(*((_QWORD *)a3 + 1) + v24 + 6) = v33;
            v55 = *(_QWORD *)(a2 + 8) + 8LL * (v22 + 5);
            v34 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            if ( (unsigned __int16)v34 > 0x3ECu && v22 + 5 > 0 )
            {
              v55 -= 8;
              v34 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
            }
            v15 = *((_QWORD *)a3 + 1);
            LODWORD(v4) = v4 + 8;
            v22 += 8;
            *(_WORD *)(v15 + v24 + 8) = v34;
            v24 += 16;
            v23 = (int)v4;
          }
          while ( (int)v4 < v56 );
        }
      }
      v35 = (int)v54;
      for ( i = (int)v4; i < v35; ++i )
      {
        v37 = *(_QWORD *)(a2 + 8) + 8LL * (int)v4;
        v54 = v37;
        v38 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v54);
        if ( (unsigned __int16)v38 > 0x3ECu && (int)v4 > 0 )
        {
          v54 = v37 - 8;
          v38 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v54);
        }
        v15 = *((_QWORD *)a3 + 1);
        LODWORD(v4) = v4 + 1;
        *(_WORD *)(v15 + 2 * i) = v38;
      }
    }
    else
    {
      v13 = v10 * v11;
      v14 = 0;
      if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
      {
        LOBYTE(v15) = 0;
      }
      else
      {
        v14 = v13;
        LOBYTE(v15) = 1;
      }
      v16 = 0;
      if ( !(_BYTE)v15 )
        v14 = 0;
      if ( a1[3] <= v14 )
        v14 = a1[3];
      if ( v14 > v12 )
        v14 = v12;
      if ( v14 > 0 )
      {
        do
        {
          v17 = *(_QWORD *)(a2 + 8) + 8LL * v16;
          v55 = v17;
          v18 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
          if ( (unsigned __int16)v18 > 0x3ECu && v16 > 0 )
          {
            v55 = v17 - 8;
            v18 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v55);
          }
          v15 = *((_QWORD *)a3 + 1);
          v19 = v4;
          v16 += v54;
          ++v4;
          *(_WORD *)(v15 + 2 * v19) = v18;
        }
        while ( v16 < v14 );
      }
    }
  }
  else
  {
    v39 = a1[9];
    v40 = v9;
    if ( v9 <= 0 )
      v40 = 1;
    if ( v39 < 0 || v39 >= v40 )
    {
      v39 %= v40;
      if ( v39 < 0 )
        v39 += v40;
    }
    v41 = *a3;
    v42 = v39;
    v43 = 0;
    if ( (unsigned __int64)(v41 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v44 = 0;
    }
    else
    {
      v43 = v41 * a1[762];
      v44 = 1;
    }
    if ( !v44 )
      v43 = 0;
    v45 = v43 / v9;
    v46 = (unsigned int)((int)v41 >> 31);
    LODWORD(v46) = (int)v41 % v9;
    LODWORD(v15) = (int)v41 / v9;
    if ( (int)v41 % v9 > 0 )
    {
      do
      {
        v45 += a1[v39 + 388];
        v47 = v39 + 1;
        v39 = 0;
        if ( v47 < v40 )
          v39 = v47;
        --v46;
      }
      while ( v46 );
    }
    v48 = 0;
    v49 = *(_DWORD *)a2 - v8;
    if ( v45 > a1[3] )
      v45 = a1[3];
    if ( v45 <= v49 )
      v49 = v45;
    LODWORD(v55) = v49;
    if ( v49 > 0 )
    {
      v53 = 0;
      do
      {
        v56 = *(_QWORD *)(a2 + 8) + 8LL * v48;
        v50 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v56);
        if ( (unsigned __int16)v50 > 0x3ECu && v48 > 0 )
        {
          v56 -= 8;
          v50 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<unsigned short *>,4,1>>(&v56);
        }
        *(_WORD *)(v53 + *((_QWORD *)a3 + 1)) = v50;
        v15 = v42;
        v51 = v42 + 1;
        v53 += 2;
        v42 = 0;
        v48 += *(_DWORD *)(v54 + 4 * v15 + 1552);
        if ( v51 < v40 )
          v42 = v51;
      }
      while ( v48 < (int)v55 );
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180062af0  mov     [rsp-38h+arg_10], rbx
0x180062af5  mov     [rsp-38h+arg_0], rcx
0x180062afa  push    rbp
0x180062afb  push    rsi
0x180062afc  push    rdi
0x180062afd  push    r12
0x180062aff  push    r13
0x180062b01  push    r14
0x180062b03  push    r15
0x180062b05  mov     rbp, rsp
0x180062b08  sub     rsp, 30h
0x180062b0c  mov     r11d, [rcx+20h]
0x180062b10  xor     ebx, ebx
0x180062b12  test    r11d, r11d
0x180062b15  mov     r10, rcx
0x180062b18  mov     r14, r8
0x180062b1b  mov     r12, rdx
0x180062b1e  cmovg   r11d, ebx
0x180062b22  neg     r11d
0x180062b25  movsxd  rax, r11d
0x180062b28  shl     rax, 3
0x180062b2c  add     [rdx+8], rax
0x180062b30  mov     ecx, [rcx+2Ch]
0x180062b33  cmp     ecx, 1
0x180062b36  jnz     loc_180062F03
0x180062b3c  movsxd  rax, dword ptr [r10+610h]
0x180062b43  mov     r9d, 0FFFFFFFFh
0x180062b49  mov     edx, [rdx]
0x180062b4b  movsxd  rcx, dword ptr [r8]
0x180062b4e  sub     edx, r11d
0x180062b51  mov     dword ptr [rbp+arg_0], eax
0x180062b54  cmp     eax, 1
0x180062b57  jz      loc_180062BF6
0x180062b5d  imul    rcx, rax
0x180062b61  mov     eax, 80000000h
0x180062b66  mov     esi, ebx
0x180062b68  add     rax, rcx
0x180062b6b  cmp     rax, r9
0x180062b6e  ja      short loc_180062B76
0x180062b70  mov     esi, ecx
0x180062b72  mov     al, 1
0x180062b74  jmp     short loc_180062B78
0x180062b76  xor     al, al
0x180062b78  test    al, al
0x180062b7a  mov     edi, ebx
0x180062b7c  cmovz   esi, ebx
0x180062b7f  cmp     [r10+0Ch], esi
0x180062b83  cmovle  esi, [r10+0Ch]
0x180062b88  cmp     esi, edx
0x180062b8a  cmovg   esi, edx
0x180062b8d  test    esi, esi
0x180062b8f  jle     loc_18006303B
0x180062b95  mov     r15d, 3ECh
0x180062b9b  nop     dword ptr [rax+rax+00h]
0x180062ba0  mov     rax, [r12+8]
0x180062ba5  movsxd  rcx, edi
0x180062ba8  lea     r13, [rax+rcx*8]
0x180062bac  lea     rcx, [rbp+arg_8]
0x180062bb0  mov     [rbp+arg_8], r13
0x180062bb4  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062bb9  cvttss2si edx, xmm0
0x180062bbd  cmp     dx, r15w
0x180062bc1  jbe     short loc_180062BDC
0x180062bc3  test    edi, edi
0x180062bc5  jle     short loc_180062BDC
0x180062bc7  lea     rax, [r13-8]
0x180062bcb  lea     rcx, [rbp+arg_8]
0x180062bcf  mov     [rbp+arg_8], rax
0x180062bd3  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062bd8  cvttss2si edx, xmm0
0x180062bdc  mov     rax, [r14+8]
0x180062be0  mov     rcx, rbx
0x180062be3  add     edi, dword ptr [rbp+arg_0]
0x180062be6  inc     rbx
0x180062be9  mov     [rax+rcx*2], dx
0x180062bed  cmp     edi, esi
0x180062bef  jl      short loc_180062BA0
0x180062bf1  jmp     loc_18006303B
0x180062bf6  mov     eax, [r10+0Ch]
0x180062bfa  mov     r15d, 3ECh
0x180062c00  cmp     eax, ecx
0x180062c02  cmovg   eax, ecx
0x180062c05  cmp     eax, edx
0x180062c07  cmovle  edx, eax
0x180062c0a  mov     eax, edx
0x180062c0c  mov     dword ptr [rbp+arg_0], edx
0x180062c0f  cdq
0x180062c10  and     edx, 7
0x180062c13  add     eax, edx
0x180062c15  sar     eax, 3
0x180062c18  movsxd  rcx, eax
0x180062c1b  mov     eax, 80000000h
0x180062c20  shl     rcx, 3
0x180062c24  add     rax, rcx
0x180062c27  cmp     rax, r9
0x180062c2a  ja      loc_180062E97
0x180062c30  movsxd  rax, ecx
0x180062c33  mov     [rbp+arg_18], rax
0x180062c37  test    ecx, ecx
0x180062c39  jle     loc_180062E97
0x180062c3f  mov     edi, 2
0x180062c44  mov     rcx, rbx
0x180062c47  lea     esi, [rdi+4]
0x180062c4a  nop     word ptr [rax+rax+00h]
0x180062c50  mov     rax, [r12+8]
0x180062c55  lea     r13, [rax+rcx*8]
0x180062c59  lea     rcx, [rbp+arg_8]
0x180062c5d  mov     [rbp+arg_8], r13
0x180062c61  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062c66  cvttss2si ecx, xmm0
0x180062c6a  cmp     cx, r15w
0x180062c6e  jbe     short loc_180062C89
0x180062c70  test    ebx, ebx
0x180062c72  jle     short loc_180062C89
0x180062c74  lea     rax, [r13-8]
0x180062c78  lea     rcx, [rbp+arg_8]
0x180062c7c  mov     [rbp+arg_8], rax
0x180062c80  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062c85  cvttss2si ecx, xmm0
0x180062c89  mov     rax, [r14+8]
0x180062c8d  lea     r13d, [rdi-1]
0x180062c91  mov     [rsi+rax-6], cx
0x180062c96  mov     rax, [r12+8]
0x180062c9b  movsxd  rcx, r13d
0x180062c9e  lea     rax, [rax+rcx*8]
0x180062ca2  lea     rcx, [rbp+arg_8]
0x180062ca6  mov     [rbp+arg_8], rax
0x180062caa  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062caf  cvttss2si ecx, xmm0
0x180062cb3  cmp     cx, r15w
0x180062cb7  jbe     short loc_180062CD0
0x180062cb9  test    r13d, r13d
0x180062cbc  jle     short loc_180062CD0
0x180062cbe  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062cc3  lea     rcx, [rbp+arg_8]
0x180062cc7  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062ccc  cvttss2si ecx, xmm0
0x180062cd0  mov     rax, [r14+8]
0x180062cd4  mov     [rax+rsi-4], cx
0x180062cd9  mov     rax, [r12+8]
0x180062cde  movsxd  rcx, edi
0x180062ce1  lea     r13, [rax+rcx*8]
0x180062ce5  lea     rcx, [rbp+arg_8]
0x180062ce9  mov     [rbp+arg_8], r13
0x180062ced  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062cf2  cvttss2si ecx, xmm0
0x180062cf6  cmp     cx, r15w
0x180062cfa  jbe     short loc_180062D15
0x180062cfc  test    edi, edi
0x180062cfe  jle     short loc_180062D15
0x180062d00  lea     rax, [r13-8]
0x180062d04  lea     rcx, [rbp+arg_8]
0x180062d08  mov     [rbp+arg_8], rax
0x180062d0c  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062d11  cvttss2si ecx, xmm0
0x180062d15  mov     rax, [r14+8]
0x180062d19  lea     r13d, [rdi+1]
0x180062d1d  mov     [rax+rsi-2], cx
0x180062d22  mov     rax, [r12+8]
0x180062d27  movsxd  rcx, r13d
0x180062d2a  lea     rax, [rax+rcx*8]
0x180062d2e  lea     rcx, [rbp+arg_8]
0x180062d32  mov     [rbp+arg_8], rax
0x180062d36  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062d3b  cvttss2si ecx, xmm0
0x180062d3f  cmp     cx, r15w
0x180062d43  jbe     short loc_180062D5C
0x180062d45  test    r13d, r13d
0x180062d48  jle     short loc_180062D5C
0x180062d4a  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062d4f  lea     rcx, [rbp+arg_8]
0x180062d53  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062d58  cvttss2si ecx, xmm0
0x180062d5c  mov     rax, [r14+8]
0x180062d60  lea     r13d, [rdi+2]
0x180062d64  mov     [rsi+rax], cx
0x180062d68  mov     rax, [r12+8]
0x180062d6d  movsxd  rcx, r13d
0x180062d70  lea     rax, [rax+rcx*8]
0x180062d74  lea     rcx, [rbp+arg_8]
0x180062d78  mov     [rbp+arg_8], rax
0x180062d7c  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062d81  cvttss2si ecx, xmm0
0x180062d85  cmp     cx, r15w
0x180062d89  jbe     short loc_180062DA2
0x180062d8b  test    r13d, r13d
0x180062d8e  jle     short loc_180062DA2
0x180062d90  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062d95  lea     rcx, [rbp+arg_8]
0x180062d99  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062d9e  cvttss2si ecx, xmm0
0x180062da2  mov     rax, [r14+8]
0x180062da6  lea     r13d, [rdi+3]
0x180062daa  mov     [rax+rsi+2], cx
0x180062daf  mov     rax, [r12+8]
0x180062db4  movsxd  rcx, r13d
0x180062db7  lea     rax, [rax+rcx*8]
0x180062dbb  lea     rcx, [rbp+arg_8]
0x180062dbf  mov     [rbp+arg_8], rax
0x180062dc3  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062dc8  cvttss2si ecx, xmm0
0x180062dcc  cmp     cx, r15w
0x180062dd0  jbe     short loc_180062DE9
0x180062dd2  test    r13d, r13d
0x180062dd5  jle     short loc_180062DE9
0x180062dd7  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062ddc  lea     rcx, [rbp+arg_8]
0x180062de0  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062de5  cvttss2si ecx, xmm0
0x180062de9  mov     rax, [r14+8]
0x180062ded  lea     r13d, [rdi+4]
0x180062df1  mov     [rax+rsi+4], cx
0x180062df6  mov     rax, [r12+8]
0x180062dfb  movsxd  rcx, r13d
0x180062dfe  lea     rax, [rax+rcx*8]
0x180062e02  lea     rcx, [rbp+arg_8]
0x180062e06  mov     [rbp+arg_8], rax
0x180062e0a  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062e0f  cvttss2si ecx, xmm0
0x180062e13  cmp     cx, r15w
0x180062e17  jbe     short loc_180062E30
0x180062e19  test    r13d, r13d
0x180062e1c  jle     short loc_180062E30
0x180062e1e  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062e23  lea     rcx, [rbp+arg_8]
0x180062e27  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062e2c  cvttss2si ecx, xmm0
0x180062e30  mov     rax, [r14+8]
0x180062e34  lea     r13d, [rdi+5]
0x180062e38  mov     [rax+rsi+6], cx
0x180062e3d  mov     rax, [r12+8]
0x180062e42  movsxd  rcx, r13d
0x180062e45  lea     rax, [rax+rcx*8]
0x180062e49  lea     rcx, [rbp+arg_8]
0x180062e4d  mov     [rbp+arg_8], rax
0x180062e51  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062e56  cvttss2si ecx, xmm0
0x180062e5a  cmp     cx, r15w
0x180062e5e  jbe     short loc_180062E77
0x180062e60  test    r13d, r13d
0x180062e63  jle     short loc_180062E77
0x180062e65  add     [rbp+arg_8], 0FFFFFFFFFFFFFFF8h
0x180062e6a  lea     rcx, [rbp+arg_8]
0x180062e6e  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062e73  cvttss2si ecx, xmm0
0x180062e77  mov     rax, [r14+8]
0x180062e7b  add     ebx, 8
0x180062e7e  add     edi, 8
0x180062e81  mov     [rax+rsi+8], cx
0x180062e86  add     rsi, 10h
0x180062e8a  movsxd  rcx, ebx
0x180062e8d  cmp     rcx, [rbp+arg_18]
0x180062e91  jl      loc_180062C50
0x180062e97  movsxd  r13, dword ptr [rbp+arg_0]
0x180062e9b  movsxd  rdi, ebx
0x180062e9e  cmp     rdi, r13
0x180062ea1  jge     loc_18006303B
0x180062ea7  nop     word ptr [rax+rax+00000000h]
0x180062eb0  mov     rax, [r12+8]
0x180062eb5  movsxd  rcx, ebx
0x180062eb8  lea     rsi, [rax+rcx*8]
0x180062ebc  lea     rcx, [rbp+arg_0]
0x180062ec0  mov     [rbp+arg_0], rsi
0x180062ec4  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062ec9  cvttss2si ecx, xmm0
0x180062ecd  cmp     cx, r15w
0x180062ed1  jbe     short loc_180062EEC
0x180062ed3  test    ebx, ebx
0x180062ed5  jle     short loc_180062EEC
0x180062ed7  lea     rax, [rsi-8]
0x180062edb  lea     rcx, [rbp+arg_0]
0x180062edf  mov     [rbp+arg_0], rax
0x180062ee3  call    ??$Convert@V?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$ActiveRegion@V?$HighDescription@PEAG@Data@@$03$00@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1>>(Binary::IntegratedSelection::ActiveRegion<Data::HighDescription<ushort *>,4,1> const &)
0x180062ee8  cvttss2si ecx, xmm0
0x180062eec  mov     rax, [r14+8]
0x180062ef0  inc     ebx
0x180062ef2  mov     [rax+rdi*2], cx
0x180062ef6  inc     rdi
0x180062ef9  cmp     rdi, r13
0x180062efc  jl      short loc_180062EB0
0x180062efe  jmp     loc_18006303B
0x180062f03  mov     r8d, [r10+24h]
0x180062f07  test    ecx, ecx
0x180062f09  mov     r13d, ecx
0x180062f0c  mov     eax, 1
0x180062f11  cmovle  r13d, eax
0x180062f15  test    r8d, r8d
0x180062f18  js      short loc_180062F1F
0x180062f1a  cmp     r8d, r13d
0x180062f1d  jl      short loc_180062F30
0x180062f1f  mov     eax, r8d
0x180062f22  cdq
0x180062f23  idiv    r13d
0x180062f26  mov     r8d, edx
0x180062f29  test    edx, edx
0x180062f2b  jns     short loc_180062F30
0x180062f2d  add     r8d, r13d
0x180062f30  movsxd  r15, dword ptr [r14]
0x180062f33  mov     eax, 80000000h
0x180062f38  movsxd  rdx, dword ptr [r10+0BE8h]
  ... truncated ...
```
