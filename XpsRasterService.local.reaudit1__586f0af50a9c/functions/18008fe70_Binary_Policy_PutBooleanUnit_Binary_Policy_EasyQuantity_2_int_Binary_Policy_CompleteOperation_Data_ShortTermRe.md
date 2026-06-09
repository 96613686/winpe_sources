# Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)

- ea: `0x18008fe70`
- end: `0x1800902f9`
- name: `??$PutBooleanUnit@VEasyQuantity@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ec30`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x18008fe70`

## pseudocode

```c
void __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,2>(
        unsigned int a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        int a5)
{
  signed int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r10
  __int64 v10; // r11
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rbp
  __int64 v14; // r9
  __int16 v15; // r12
  __int16 v16; // r13
  char *v17; // r15
  __int16 v18; // dx
  __int16 v19; // cx
  int v20; // ebx
  _QWORD *v21; // r14
  int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rsi
  __int64 v31; // rbp
  __int64 v32; // rcx
  __int16 v33; // r15
  __int64 v34; // rdi
  __int64 v35; // r14
  __int16 v36; // r12
  __int16 v37; // r13
  __int64 v38; // r8
  char *v39; // r11
  __int64 v40; // r10
  __int16 v41; // r9
  __int16 v42; // dx
  __int16 v43; // cx
  int v44; // eax
  __int64 v45; // rdx
  int v46; // [rsp+20h] [rbp-C8h]
  int v47; // [rsp+28h] [rbp-C0h]
  __int16 *v48; // [rsp+30h] [rbp-B8h]
  __int16 *v49; // [rsp+38h] [rbp-B0h]
  char *v50; // [rsp+40h] [rbp-A8h]
  int v52; // [rsp+50h] [rbp-98h]
  __int64 v53; // [rsp+58h] [rbp-90h]
  char *v55; // [rsp+68h] [rbp-80h]
  __int16 *v56; // [rsp+70h] [rbp-78h]
  __int128 v58; // [rsp+80h] [rbp-68h] BYREF
  __int16 v59; // [rsp+90h] [rbp-58h] BYREF
  __int16 v60; // [rsp+92h] [rbp-56h]
  __int16 v61; // [rsp+94h] [rbp-54h]
  __int16 v62; // [rsp+96h] [rbp-52h]
  __int16 v63; // [rsp+98h] [rbp-50h]

  v46 = a1;
  v58 = 0;
  Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)a2, &v58, a3);
  if ( a1 > 1 )
  {
    v7 = a1 & 0x80000001;
    v46 = v7;
    if ( v7 < 0 )
    {
      v7 = (((_BYTE)v7 - 1) | 0xFFFFFFFE) + 1;
      v46 = v7;
    }
    if ( v7 < 0 )
      v46 = v7 + 2;
  }
  v8 = a4[3];
  v9 = a4[2] - v8;
  v10 = a4[4] - v8;
  v11 = *a4 - v8;
  v12 = (__int64)a5 << 6;
  v13 = a4[1] - v8;
  v14 = 5;
  v55 = &byte_1800DE5C4[v12];
  v15 = *(_WORD *)&byte_1800DE5C4[v12];
  v56 = (__int16 *)((char *)&word_1800DE5C6 + v12);
  v16 = *(__int16 *)((char *)&word_1800DE5C6 + v12);
  v48 = (__int16 *)((char *)qword_1800DE5C8 + v12);
  v50 = &Binary::Policy::EasyQuantity::OddOperation[v12];
  v49 = (__int16 *)(0x180000000LL + v12 + 910786);
  v17 = (char *)&v59 - v8;
  do
  {
    v18 = *(_WORD *)(v10 + v8);
    v19 = *(_WORD *)(v9 + v8);
    v8 += 2;
    *(_WORD *)&v17[v8 - 2] = (unsigned __int16)(*(_WORD *)(v8 - 2) * v16
                                              + *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v12]
                                              * *(_WORD *)(v11 + v8 - 2)
                                              + *(_WORD *)(0x180000000LL + v12 + 910786) * *(_WORD *)(v8 + v13 - 2)
                                              + v15 * v19
                                              + *(_WORD *)((char *)qword_1800DE5C8 + v12) * v18) >> 6;
    --v14;
  }
  while ( v14 );
  v20 = v46;
  v21 = a4;
  v22 = 0;
  v23 = (__int64)v46 << 6;
  **((_BYTE **)&v58 + 1) = (unsigned __int16)(v59 * *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v23]
                                            + v61 * *(_WORD *)&byte_1800DE5C4[v23]
                                            + v62 * *(__int16 *)((char *)&word_1800DE5C6 + v23)
                                            + v63 * *(_WORD *)((char *)qword_1800DE5C8 + v23)
                                            + v60 * *(__int16 *)((char *)&word_1800DE5C2 + v23)) >> 8;
  v52 = 1;
  if ( (int)a3[3] > 1 )
  {
    v24 = 1;
    v53 = 1;
    do
    {
      v25 = Binary::Policy::EasyQuantity::GlobalCase[v20];
      v26 = 0;
      v22 += v25;
      v27 = 5 - v25;
      v47 = v22;
      v28 = 5 - (int)v25;
      if ( 5 - (int)v25 > 0 )
      {
        do
        {
          *(&v59 + v26) = *(&v59 + v25 + v26);
          ++v26;
        }
        while ( v26 < v27 );
      }
      if ( v27 < 5LL )
      {
        v29 = v21[3];
        v30 = v21[4] - v29;
        v31 = v21[1] - v29;
        v32 = v22;
        v33 = *(_WORD *)v55;
        v34 = v21[2] - v29;
        v35 = *v21 - v29;
        v36 = *v56;
        v37 = *v48;
        v38 = v29 + 2 * (v28 + v32);
        v39 = (char *)&v59 - v29 + -2 * v32;
        v40 = 5 - v28;
        v41 = *v49;
        do
        {
          v42 = *(_WORD *)(v38 + v31);
          v43 = *(_WORD *)(v38 + v35);
          v38 += 2;
          *(_WORD *)&v39[v38 - 2] = (unsigned __int16)(*(_WORD *)(v38 - 2) * v36
                                                     + v33 * *(_WORD *)(v38 + v34 - 2)
                                                     + v37 * *(_WORD *)(v38 + v30 - 2)
                                                     + *(_WORD *)v50 * v43
                                                     + v41 * v42) >> 6;
          --v40;
        }
        while ( v40 );
        v20 = v46;
        v21 = a4;
        v22 = v47;
        v24 = v53;
      }
      v44 = v20 + 1;
      v20 = 0;
      if ( v44 < 2 )
        v20 = v44;
      v45 = (__int64)v20 << 6;
      v46 = v20;
      *(_BYTE *)(v24 + *((_QWORD *)&v58 + 1)) = (unsigned __int16)(v59
                                                                 * *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v45]
                                                                 + v61 * *(_WORD *)&byte_1800DE5C4[v45]
                                                                 + v62 * *(__int16 *)((char *)&word_1800DE5C6 + v45)
                                                                 + v63 * *(_WORD *)((char *)qword_1800DE5C8 + v45)
                                                                 + v60 * *(__int16 *)((char *)&word_1800DE5C2 + v45)) >> 8;
      ++v24;
      ++v52;
      v53 = v24;
    }
    while ( v52 < a3[3] );
  }
  Binary::Policy::CompleteOperation::MoveVirtualAddition(a2);
}

```

## disassembly

```asm
0x18008fe70  mov     r11, rsp
0x18008fe73  mov     [r11+8], rbx
0x18008fe77  push    rbp
0x18008fe78  push    rsi
0x18008fe79  push    rdi
0x18008fe7a  push    r12
0x18008fe7c  push    r13
0x18008fe7e  push    r14
0x18008fe80  push    r15
0x18008fe82  sub     rsp, 0B0h
0x18008fe89  mov     rax, cs:__security_cookie
0x18008fe90  xor     rax, rsp
0x18008fe93  mov     [rsp+0E8h+var_48], rax
0x18008fe9b  mov     rax, rdx
0x18008fe9e  mov     [rsp+0E8h+var_70], rdx
0x18008fea3  mov     ebx, ecx
0x18008fea5  mov     [rsp+0E8h+var_C8], ecx
0x18008fea9  xorps   xmm0, xmm0
0x18008feac  mov     [rsp+0E8h+var_A0], r9
0x18008feb1  xor     edi, edi
0x18008feb3  mov     [rsp+0E8h+var_88], r8
0x18008feb8  mov     rcx, rax
0x18008febb  mov     [rsp+0E8h+var_C0], edi
0x18008febf  lea     rdx, [r11-68h]
0x18008fec3  mov     r14, r9
0x18008fec6  movups  xmmword ptr [r11-68h], xmm0
0x18008fecb  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008fed0  cmp     ebx, 1
0x18008fed3  jbe     short loc_18008FEF7
0x18008fed5  and     ebx, 80000001h
0x18008fedb  mov     [rsp+0E8h+var_C8], ebx
0x18008fedf  jge     short loc_18008FEEC
0x18008fee1  dec     ebx
0x18008fee3  or      ebx, 0FFFFFFFEh
0x18008fee6  inc     ebx
0x18008fee8  mov     [rsp+0E8h+var_C8], ebx
0x18008feec  test    ebx, ebx
0x18008feee  jns     short loc_18008FEF7
0x18008fef0  add     ebx, 2
0x18008fef3  mov     [rsp+0E8h+var_C8], ebx
0x18008fef7  mov     r8, [r14+18h]
0x18008fefb  lea     rdx, cs:180000000h
0x18008ff02  mov     r10, [r14+10h]
0x18008ff06  lea     rcx, rva byte_1800DE5C4[rdx]
0x18008ff0d  mov     r11, [r14+20h]
0x18008ff11  lea     r15, [rsp+0E8h+var_58]
0x18008ff19  mov     rsi, [r14]
0x18008ff1c  sub     r10, r8
0x18008ff1f  mov     rbp, [r14+8]
0x18008ff23  sub     r11, r8
0x18008ff26  movsxd  rax, [rsp+0E8h+arg_20]
0x18008ff2e  sub     rsi, r8
0x18008ff31  shl     rax, 6
0x18008ff35  sub     rbp, r8
0x18008ff38  add     rcx, rax
0x18008ff3b  mov     r9d, 5
0x18008ff41  mov     [rsp+0E8h+var_80], rcx
0x18008ff46  movzx   r12d, word ptr [rcx]
0x18008ff4a  lea     rcx, rva word_1800DE5C6[rdx]
0x18008ff51  add     rcx, rax
0x18008ff54  mov     [rsp+0E8h+var_78], rcx
0x18008ff59  movzx   r13d, word ptr [rcx]
0x18008ff5d  lea     rcx, rva qword_1800DE5C8[rdx]
0x18008ff64  add     rcx, rax
0x18008ff67  mov     [rsp+0E8h+var_B8], rcx
0x18008ff6c  lea     rcx, rva ?OddOperation@EasyQuantity@Policy@Binary@@2V?$OneContext@V?$OneContext@G$04$00$0A@$09@Data@@$01$00$0A@$0IA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,5,1,0,10>,2,1,0,128> const Binary::Policy::EasyQuantity::OddOperation ...
0x18008ff73  mov     r14, [rsp+0E8h+var_B8]
0x18008ff78  add     rcx, rax
0x18008ff7b  lea     rax, [rax+0DE5C2h]
0x18008ff82  mov     [rsp+0E8h+var_A8], rcx
0x18008ff87  add     rax, rdx
0x18008ff8a  mov     rbx, rcx
0x18008ff8d  mov     [rsp+0E8h+var_B0], rax
0x18008ff92  sub     r15, r8
0x18008ff95  mov     rdi, rax
0x18008ff98  nop     dword ptr [rax+rax+00000000h]
0x18008ffa0  movzx   eax, word ptr [r14]
0x18008ffa4  movzx   edx, word ptr [r11+r8]
0x18008ffa9  movzx   ecx, word ptr [r10+r8]
0x18008ffae  lea     r8, [r8+2]
0x18008ffb2  imul    edx, eax
0x18008ffb5  movzx   eax, word ptr [rdi]
0x18008ffb8  imul    ecx, r12d
0x18008ffbc  add     dx, cx
0x18008ffbf  movzx   ecx, word ptr [r8+rbp-2]
0x18008ffc5  imul    ecx, eax
0x18008ffc8  movzx   eax, word ptr [rbx]
0x18008ffcb  add     dx, cx
0x18008ffce  movzx   ecx, word ptr [rsi+r8-2]
0x18008ffd4  imul    ecx, eax
0x18008ffd7  movzx   eax, word ptr [r8-2]
0x18008ffdc  add     dx, cx
0x18008ffdf  mov     ecx, r13d
0x18008ffe2  imul    ecx, eax
0x18008ffe5  add     dx, cx
0x18008ffe8  shr     dx, 6
0x18008ffec  mov     [r15+r8-2], dx
0x18008fff2  sub     r9, 1
0x18008fff6  jnz     short loc_18008FFA0
0x18008fff8  movzx   eax, [rsp+0E8h+var_56]
0x180090000  lea     r9, cs:180000000h
0x180090007  movsxd  rbx, [rsp+0E8h+var_C8]
0x18009000c  mov     r14, [rsp+0E8h+var_A0]
0x180090011  mov     rdx, rbx
0x180090014  mov     edi, [rsp+0E8h+var_C0]
0x180090018  shl     rdx, 6
0x18009001c  movzx   r8d, word ptr [rdx+r9+0DE5C2h]
0x180090025  movzx   ecx, word ptr [rdx+r9+0DE5C8h]
0x18009002e  imul    r8d, eax
0x180090032  movzx   eax, [rsp+0E8h+var_50]
0x18009003a  imul    ecx, eax
0x18009003d  movzx   eax, [rsp+0E8h+var_52]
0x180090045  add     r8w, cx
0x180090049  movzx   ecx, word ptr [rdx+r9+0DE5C6h]
0x180090052  imul    ecx, eax
0x180090055  movzx   eax, [rsp+0E8h+var_54]
0x18009005d  add     r8w, cx
0x180090061  movzx   ecx, word ptr [rdx+r9+0DE5C4h]
0x18009006a  imul    ecx, eax
0x18009006d  movzx   eax, [rsp+0E8h+var_58]
0x180090075  add     r8w, cx
0x180090079  movzx   ecx, word ptr [rdx+r9+0DE5C0h]
0x180090082  imul    ecx, eax
0x180090085  mov     rax, [rsp+0E8h+var_60]
0x18009008d  add     r8w, cx
0x180090091  shr     r8w, 8
0x180090096  mov     [rax], r8b
0x180090099  mov     r8d, 1
0x18009009f  mov     rax, [rsp+0E8h+var_88]
0x1800900a4  mov     [rsp+0E8h+var_98], r8
0x1800900a9  cmp     [rax+0Ch], r8d
0x1800900ad  jle     loc_1800902BC
0x1800900b3  mov     r10d, r8d
0x1800900b6  mov     [rsp+0E8h+var_90], r8
0x1800900bb  nop     dword ptr [rax+rax+00h]
0x1800900c0  movsxd  rax, ebx
0x1800900c3  mov     ecx, 5
0x1800900c8  movsxd  rdx, ds:rva ?GlobalCase@EasyQuantity@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[r9+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::EasyQuantity::GlobalCase ...
0x1800900d0  xor     eax, eax
0x1800900d2  add     edi, edx
0x1800900d4  sub     ecx, edx
0x1800900d6  mov     [rsp+0E8h+var_C0], edi
0x1800900da  movsxd  r9, ecx
0x1800900dd  test    ecx, ecx
0x1800900df  jle     short loc_18009010C
0x1800900e1  lea     r8, [rdx+rdx]
0x1800900e5  nop     word ptr [rax+rax+00000000h]
0x1800900f0  lea     rcx, [r8+rax*2]
0x1800900f4  movzx   edx, [rsp+rcx+0E8h+var_58]
0x1800900fc  mov     [rsp+rax*2+0E8h+var_58], dx
0x180090104  inc     rax
0x180090107  cmp     rax, r9
0x18009010a  jl      short loc_1800900F0
0x18009010c  cmp     r9, 5
0x180090110  jge     loc_1800901F5
0x180090116  mov     rdx, [r14+18h]
0x18009011a  lea     r11, [rsp+0E8h+var_58]
0x180090122  mov     rsi, [r14+20h]
0x180090126  mov     r10d, 5
0x18009012c  mov     rbp, [r14+8]
0x180090130  sub     rsi, rdx
0x180090133  mov     rax, [rsp+0E8h+var_80]
0x180090138  sub     rbp, rdx
0x18009013b  mov     rbx, [rsp+0E8h+var_A8]
0x180090140  movsxd  rcx, edi
0x180090143  mov     rdi, [r14+10h]
0x180090147  movzx   r15d, word ptr [rax]
0x18009014b  sub     rdi, rdx
0x18009014e  mov     rax, [rsp+0E8h+var_78]
0x180090153  mov     r14, [r14]
0x180090156  sub     r14, rdx
0x180090159  movzx   r12d, word ptr [rax]
0x18009015d  mov     rax, [rsp+0E8h+var_B8]
0x180090162  movzx   r13d, word ptr [rax]
0x180090166  mov     rax, [rsp+0E8h+var_B0]
0x18009016b  movzx   eax, word ptr [rax]
0x18009016e  mov     [rsp+0E8h+var_C4], ax
0x180090173  lea     rax, [r9+rcx]
0x180090177  lea     r8, [rdx+rax*2]
0x18009017b  lea     rax, [rcx+rcx]
0x18009017f  sub     r11, rax
0x180090182  sub     r11, rdx
0x180090185  sub     r10, r9
0x180090188  movzx   r9d, [rsp+0E8h+var_C4]
0x18009018e  xchg    ax, ax
0x180090190  movzx   edx, word ptr [r8+rbp]
0x180090195  movzx   eax, word ptr [rbx]
0x180090198  movzx   ecx, word ptr [r8+r14]
0x18009019d  lea     r8, [r8+2]
0x1800901a1  imul    ecx, eax
0x1800901a4  movzx   eax, word ptr [r8-2]
0x1800901a9  imul    edx, r9d
0x1800901ad  add     dx, cx
0x1800901b0  movzx   ecx, word ptr [r8+rsi-2]
0x1800901b6  imul    ecx, r13d
0x1800901ba  add     dx, cx
0x1800901bd  movzx   ecx, word ptr [r8+rdi-2]
0x1800901c3  imul    ecx, r15d
0x1800901c7  add     dx, cx
0x1800901ca  mov     ecx, r12d
0x1800901cd  imul    ecx, eax
0x1800901d0  add     dx, cx
0x1800901d3  shr     dx, 6
0x1800901d7  mov     [r11+r8-2], dx
0x1800901dd  sub     r10, 1
0x1800901e1  jnz     short loc_180090190
0x1800901e3  mov     ebx, [rsp+0E8h+var_C8]
0x1800901e7  mov     r14, [rsp+0E8h+var_A0]
0x1800901ec  mov     edi, [rsp+0E8h+var_C0]
0x1800901f0  mov     r10, [rsp+0E8h+var_90]
0x1800901f5  lea     eax, [rbx+1]
0x1800901f8  xor     ebx, ebx
0x1800901fa  cmp     eax, 2
0x1800901fd  lea     r9, cs:180000000h
0x180090204  cmovl   ebx, eax
0x180090207  movzx   eax, [rsp+0E8h+var_56]
0x18009020f  movsxd  rdx, ebx
0x180090212  shl     rdx, 6
0x180090216  mov     [rsp+0E8h+var_C8], ebx
0x18009021a  movzx   r8d, word ptr [rdx+r9+0DE5C2h]
0x180090223  movzx   ecx, word ptr [rdx+r9+0DE5C8h]
0x18009022c  imul    r8d, eax
0x180090230  movzx   eax, [rsp+0E8h+var_50]
0x180090238  imul    ecx, eax
0x18009023b  movzx   eax, [rsp+0E8h+var_52]
0x180090243  add     r8w, cx
0x180090247  movzx   ecx, word ptr [rdx+r9+0DE5C6h]
0x180090250  imul    ecx, eax
0x180090253  movzx   eax, [rsp+0E8h+var_54]
0x18009025b  add     r8w, cx
0x18009025f  movzx   ecx, word ptr [rdx+r9+0DE5C4h]
0x180090268  imul    ecx, eax
0x18009026b  movzx   eax, [rsp+0E8h+var_58]
0x180090273  add     r8w, cx
0x180090277  movzx   ecx, word ptr [rdx+r9+0DE5C0h]
0x180090280  imul    ecx, eax
0x180090283  mov     rax, [rsp+0E8h+var_60]
0x18009028b  add     r8w, cx
0x18009028f  shr     r8w, 8
0x180090294  mov     [r10+rax], r8b
0x180090298  inc     r10
0x18009029b  mov     r8, [rsp+0E8h+var_98]
0x1800902a0  mov     rax, [rsp+0E8h+var_88]
0x1800902a5  inc     r8d
0x1800902a8  mov     [rsp+0E8h+var_98], r8
0x1800902ad  mov     [rsp+0E8h+var_90], r10
0x1800902b2  cmp     r8d, [rax+0Ch]
0x1800902b6  jl      loc_1800900C0
0x1800902bc  mov     rcx, [rsp+0E8h+var_70]
0x1800902c1  lea     rdx, [rsp+0E8h+var_68]
0x1800902c9  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x1800902ce  mov     rcx, [rsp+0E8h+var_48]
0x1800902d6  xor     rcx, rsp; StackCookie
0x1800902d9  call    __security_check_cookie
0x1800902de  mov     rbx, [rsp+0E8h+arg_0]
0x1800902e6  add     rsp, 0B0h
0x1800902ed  pop     r15
0x1800902ef  pop     r14
0x1800902f1  pop     r13
0x1800902f3  pop     r12
0x1800902f5  pop     rdi
0x1800902f6  pop     rsi
0x1800902f7  pop     rbp
0x1800902f8  retn
```
