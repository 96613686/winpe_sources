# Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)

- ea: `0x180089230`
- end: `0x1800896b9`
- name: `??$PutBooleanUnit@VEasyQuantity@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1161`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800880e0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180089230`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,3>(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  signed int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rbp
  __int64 v18; // r9
  __int16 v19; // r12
  __int16 v20; // r13
  char *v21; // r15
  __int16 v22; // dx
  __int16 v23; // cx
  int v24; // ebx
  _QWORD *v25; // r14
  int v26; // edi
  __int64 v27; // rdx
  __int64 v28; // r10
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rbp
  __int64 v36; // rcx
  __int16 v37; // r15
  __int64 v38; // rdi
  __int64 v39; // r14
  __int16 v40; // r12
  __int16 v41; // r13
  __int64 v42; // r8
  char *v43; // r11
  __int64 v44; // r10
  __int16 v45; // r9
  __int16 v46; // dx
  __int16 v47; // cx
  int v48; // eax
  __int64 v49; // rdx
  int v51; // [rsp+20h] [rbp-C8h]
  int v52; // [rsp+28h] [rbp-C0h]
  __int16 *v53; // [rsp+30h] [rbp-B8h]
  __int16 *v54; // [rsp+38h] [rbp-B0h]
  char *v55; // [rsp+40h] [rbp-A8h]
  int v57; // [rsp+50h] [rbp-98h]
  __int64 v58; // [rsp+58h] [rbp-90h]
  char *v60; // [rsp+68h] [rbp-80h]
  __int16 *v61; // [rsp+70h] [rbp-78h]
  _BYTE v63[8]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE *v64; // [rsp+88h] [rbp-60h]
  __int16 v65; // [rsp+90h] [rbp-58h] BYREF
  __int16 v66; // [rsp+92h] [rbp-56h]
  __int16 v67; // [rsp+94h] [rbp-54h]
  __int16 v68; // [rsp+96h] [rbp-52h]
  __int16 v69; // [rsp+98h] [rbp-50h]

  v51 = a1;
  __asm { vpxor   xmm0, xmm0, xmm0 }
  _RDX = v63;
  __asm { vmovups xmmword ptr [r11-68h], xmm0 }
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, v63);
  if ( a1 > 1 )
  {
    v11 = a1 & 0x80000001;
    v51 = v11;
    if ( v11 < 0 )
    {
      v11 = (((_BYTE)v11 - 1) | 0xFFFFFFFE) + 1;
      v51 = v11;
    }
    if ( v11 < 0 )
      v51 = v11 + 2;
  }
  v12 = a4[3];
  v13 = a4[2] - v12;
  v14 = a4[4] - v12;
  v15 = *a4 - v12;
  v16 = (__int64)a5 << 6;
  v17 = a4[1] - v12;
  v18 = 5;
  v60 = &byte_1800DE5C4[v16];
  v19 = *(_WORD *)&byte_1800DE5C4[v16];
  v61 = (__int16 *)((char *)&word_1800DE5C6 + v16);
  v20 = *(__int16 *)((char *)&word_1800DE5C6 + v16);
  v53 = (__int16 *)((char *)qword_1800DE5C8 + v16);
  v55 = &Binary::Policy::EasyQuantity::OddOperation[v16];
  v54 = (__int16 *)(0x180000000LL + v16 + 910786);
  v21 = (char *)&v65 - v12;
  do
  {
    v22 = *(_WORD *)(v14 + v12);
    v23 = *(_WORD *)(v13 + v12);
    v12 += 2;
    *(_WORD *)&v21[v12 - 2] = (unsigned __int16)(*(_WORD *)(v12 - 2) * v20
                                               + *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v16]
                                               * *(_WORD *)(v15 + v12 - 2)
                                               + *(_WORD *)(0x180000000LL + v16 + 910786) * *(_WORD *)(v12 + v17 - 2)
                                               + v19 * v23
                                               + *(_WORD *)((char *)qword_1800DE5C8 + v16) * v22) >> 6;
    --v18;
  }
  while ( v18 );
  v24 = v51;
  v25 = a4;
  v26 = 0;
  v27 = (__int64)v51 << 6;
  *v64 = (unsigned __int16)(v65 * *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v27]
                          + v67 * *(_WORD *)&byte_1800DE5C4[v27]
                          + v68 * *(__int16 *)((char *)&word_1800DE5C6 + v27)
                          + v69 * *(_WORD *)((char *)qword_1800DE5C8 + v27)
                          + v66 * *(__int16 *)((char *)&word_1800DE5C2 + v27)) >> 8;
  v57 = 1;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v28 = 1;
    v58 = 1;
    do
    {
      v29 = Binary::Policy::EasyQuantity::GlobalCase[v24];
      v30 = 0;
      v26 += v29;
      v31 = 5 - v29;
      v52 = v26;
      v32 = 5 - (int)v29;
      if ( 5 - (int)v29 > 0 )
      {
        do
        {
          *(&v65 + v30) = *(&v65 + v29 + v30);
          ++v30;
        }
        while ( v30 < v31 );
      }
      if ( v31 < 5LL )
      {
        v33 = v25[3];
        v34 = v25[4] - v33;
        v35 = v25[1] - v33;
        v36 = v26;
        v37 = *(_WORD *)v60;
        v38 = v25[2] - v33;
        v39 = *v25 - v33;
        v40 = *v61;
        v41 = *v53;
        v42 = v33 + 2 * (v32 + v36);
        v43 = (char *)&v65 - v33 + -2 * v36;
        v44 = 5 - v32;
        v45 = *v54;
        do
        {
          v46 = *(_WORD *)(v42 + v35);
          v47 = *(_WORD *)(v42 + v39);
          v42 += 2;
          *(_WORD *)&v43[v42 - 2] = (unsigned __int16)(*(_WORD *)(v42 - 2) * v40
                                                     + v37 * *(_WORD *)(v42 + v38 - 2)
                                                     + v41 * *(_WORD *)(v42 + v34 - 2)
                                                     + *(_WORD *)v55 * v47
                                                     + v45 * v46) >> 6;
          --v44;
        }
        while ( v44 );
        v24 = v51;
        v25 = a4;
        v26 = v52;
        v28 = v58;
      }
      v48 = v24 + 1;
      v24 = 0;
      if ( v48 < 2 )
        v24 = v48;
      v49 = (__int64)v24 << 6;
      v51 = v24;
      v64[v28++] = (unsigned __int16)(v65 * *(_WORD *)&Binary::Policy::EasyQuantity::OddOperation[v49]
                                    + v67 * *(_WORD *)&byte_1800DE5C4[v49]
                                    + v68 * *(__int16 *)((char *)&word_1800DE5C6 + v49)
                                    + v69 * *(_WORD *)((char *)qword_1800DE5C8 + v49)
                                    + v66 * *(__int16 *)((char *)&word_1800DE5C2 + v49)) >> 8;
      ++v57;
      v58 = v28;
    }
    while ( v57 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, v63);
}

```

## disassembly

```asm
0x180089230  mov     r11, rsp
0x180089233  mov     [r11+8], rbx
0x180089237  push    rbp
0x180089238  push    rsi
0x180089239  push    rdi
0x18008923a  push    r12
0x18008923c  push    r13
0x18008923e  push    r14
0x180089240  push    r15
0x180089242  sub     rsp, 0B0h
0x180089249  mov     rax, cs:__security_cookie
0x180089250  xor     rax, rsp
0x180089253  mov     [rsp+0E8h+var_48], rax
0x18008925b  mov     rax, rdx
0x18008925e  mov     [rsp+0E8h+var_70], rdx
0x180089263  mov     ebx, ecx
0x180089265  mov     [rsp+0E8h+var_C8], ecx
0x180089269  vpxor   xmm0, xmm0, xmm0
0x18008926d  xor     edi, edi
0x18008926f  mov     [rsp+0E8h+var_A0], r9
0x180089274  mov     rcx, rax
0x180089277  mov     [rsp+0E8h+var_88], r8
0x18008927c  lea     rdx, [r11-68h]
0x180089280  mov     [rsp+0E8h+var_C0], edi
0x180089284  mov     r14, r9
0x180089287  vmovups xmmword ptr [r11-68h], xmm0
0x18008928d  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180089292  cmp     ebx, 1
0x180089295  jbe     short loc_1800892B9
0x180089297  and     ebx, 80000001h
0x18008929d  mov     [rsp+0E8h+var_C8], ebx
0x1800892a1  jge     short loc_1800892AE
0x1800892a3  dec     ebx
0x1800892a5  or      ebx, 0FFFFFFFEh
0x1800892a8  inc     ebx
0x1800892aa  mov     [rsp+0E8h+var_C8], ebx
0x1800892ae  test    ebx, ebx
0x1800892b0  jns     short loc_1800892B9
0x1800892b2  add     ebx, 2
0x1800892b5  mov     [rsp+0E8h+var_C8], ebx
0x1800892b9  mov     r8, [r14+18h]
0x1800892bd  lea     rdx, cs:180000000h
0x1800892c4  mov     r10, [r14+10h]
0x1800892c8  lea     rcx, rva byte_1800DE5C4[rdx]
0x1800892cf  mov     r11, [r14+20h]
0x1800892d3  lea     r15, [rsp+0E8h+var_58]
0x1800892db  mov     rsi, [r14]
0x1800892de  sub     r10, r8
0x1800892e1  mov     rbp, [r14+8]
0x1800892e5  sub     r11, r8
0x1800892e8  movsxd  rax, [rsp+0E8h+arg_20]
0x1800892f0  sub     rsi, r8
0x1800892f3  shl     rax, 6
0x1800892f7  sub     rbp, r8
0x1800892fa  add     rcx, rax
0x1800892fd  mov     r9d, 5
0x180089303  mov     [rsp+0E8h+var_80], rcx
0x180089308  movzx   r12d, word ptr [rcx]
0x18008930c  lea     rcx, rva word_1800DE5C6[rdx]
0x180089313  add     rcx, rax
0x180089316  mov     [rsp+0E8h+var_78], rcx
0x18008931b  movzx   r13d, word ptr [rcx]
0x18008931f  lea     rcx, rva qword_1800DE5C8[rdx]
0x180089326  add     rcx, rax
0x180089329  mov     [rsp+0E8h+var_B8], rcx
0x18008932e  lea     rcx, rva ?OddOperation@EasyQuantity@Policy@Binary@@2V?$OneContext@V?$OneContext@G$04$00$0A@$09@Data@@$01$00$0A@$0IA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,5,1,0,10>,2,1,0,128> const Binary::Policy::EasyQuantity::OddOperation ...
0x180089335  mov     r14, [rsp+0E8h+var_B8]
0x18008933a  add     rcx, rax
0x18008933d  lea     rax, [rax+0DE5C2h]
0x180089344  mov     [rsp+0E8h+var_A8], rcx
0x180089349  add     rax, rdx
0x18008934c  mov     rbx, rcx
0x18008934f  mov     [rsp+0E8h+var_B0], rax
0x180089354  sub     r15, r8
0x180089357  mov     rdi, rax
0x18008935a  nop     word ptr [rax+rax+00h]
0x180089360  movzx   eax, word ptr [r14]
0x180089364  movzx   edx, word ptr [r11+r8]
0x180089369  movzx   ecx, word ptr [r10+r8]
0x18008936e  lea     r8, [r8+2]
0x180089372  imul    edx, eax
0x180089375  movzx   eax, word ptr [rdi]
0x180089378  imul    ecx, r12d
0x18008937c  add     dx, cx
0x18008937f  movzx   ecx, word ptr [r8+rbp-2]
0x180089385  imul    ecx, eax
0x180089388  movzx   eax, word ptr [rbx]
0x18008938b  add     dx, cx
0x18008938e  movzx   ecx, word ptr [rsi+r8-2]
0x180089394  imul    ecx, eax
0x180089397  movzx   eax, word ptr [r8-2]
0x18008939c  add     dx, cx
0x18008939f  mov     ecx, r13d
0x1800893a2  imul    ecx, eax
0x1800893a5  add     dx, cx
0x1800893a8  shr     dx, 6
0x1800893ac  mov     [r15+r8-2], dx
0x1800893b2  sub     r9, 1
0x1800893b6  jnz     short loc_180089360
0x1800893b8  movzx   eax, [rsp+0E8h+var_56]
0x1800893c0  lea     r9, cs:180000000h
0x1800893c7  movsxd  rbx, [rsp+0E8h+var_C8]
0x1800893cc  mov     r14, [rsp+0E8h+var_A0]
0x1800893d1  mov     rdx, rbx
0x1800893d4  mov     edi, [rsp+0E8h+var_C0]
0x1800893d8  shl     rdx, 6
0x1800893dc  movzx   r8d, word ptr [rdx+r9+0DE5C2h]
0x1800893e5  movzx   ecx, word ptr [rdx+r9+0DE5C8h]
0x1800893ee  imul    r8d, eax
0x1800893f2  movzx   eax, [rsp+0E8h+var_50]
0x1800893fa  imul    ecx, eax
0x1800893fd  movzx   eax, [rsp+0E8h+var_52]
0x180089405  add     r8w, cx
0x180089409  movzx   ecx, word ptr [rdx+r9+0DE5C6h]
0x180089412  imul    ecx, eax
0x180089415  movzx   eax, [rsp+0E8h+var_54]
0x18008941d  add     r8w, cx
0x180089421  movzx   ecx, word ptr [rdx+r9+0DE5C4h]
0x18008942a  imul    ecx, eax
0x18008942d  movzx   eax, [rsp+0E8h+var_58]
0x180089435  add     r8w, cx
0x180089439  movzx   ecx, word ptr [rdx+r9+0DE5C0h]
0x180089442  imul    ecx, eax
0x180089445  mov     rax, [rsp+0E8h+var_60]
0x18008944d  add     r8w, cx
0x180089451  shr     r8w, 8
0x180089456  mov     [rax], r8b
0x180089459  mov     r8d, 1
0x18008945f  mov     rax, [rsp+0E8h+var_88]
0x180089464  mov     [rsp+0E8h+var_98], r8
0x180089469  cmp     [rax+0Ch], r8d
0x18008946d  jle     loc_18008967C
0x180089473  mov     r10d, r8d
0x180089476  mov     [rsp+0E8h+var_90], r8
0x18008947b  nop     dword ptr [rax+rax+00h]
0x180089480  movsxd  rax, ebx
0x180089483  mov     ecx, 5
0x180089488  movsxd  rdx, ds:rva ?GlobalCase@EasyQuantity@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[r9+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::EasyQuantity::GlobalCase ...
0x180089490  xor     eax, eax
0x180089492  add     edi, edx
0x180089494  sub     ecx, edx
0x180089496  mov     [rsp+0E8h+var_C0], edi
0x18008949a  movsxd  r9, ecx
0x18008949d  test    ecx, ecx
0x18008949f  jle     short loc_1800894CC
0x1800894a1  lea     r8, [rdx+rdx]
0x1800894a5  nop     word ptr [rax+rax+00000000h]
0x1800894b0  lea     rcx, [r8+rax*2]
0x1800894b4  movzx   edx, [rsp+rcx+0E8h+var_58]
0x1800894bc  mov     [rsp+rax*2+0E8h+var_58], dx
0x1800894c4  inc     rax
0x1800894c7  cmp     rax, r9
0x1800894ca  jl      short loc_1800894B0
0x1800894cc  cmp     r9, 5
0x1800894d0  jge     loc_1800895B5
0x1800894d6  mov     rdx, [r14+18h]
0x1800894da  lea     r11, [rsp+0E8h+var_58]
0x1800894e2  mov     rsi, [r14+20h]
0x1800894e6  mov     r10d, 5
0x1800894ec  mov     rbp, [r14+8]
0x1800894f0  sub     rsi, rdx
0x1800894f3  mov     rax, [rsp+0E8h+var_80]
0x1800894f8  sub     rbp, rdx
0x1800894fb  mov     rbx, [rsp+0E8h+var_A8]
0x180089500  movsxd  rcx, edi
0x180089503  mov     rdi, [r14+10h]
0x180089507  movzx   r15d, word ptr [rax]
0x18008950b  sub     rdi, rdx
0x18008950e  mov     rax, [rsp+0E8h+var_78]
0x180089513  mov     r14, [r14]
0x180089516  sub     r14, rdx
0x180089519  movzx   r12d, word ptr [rax]
0x18008951d  mov     rax, [rsp+0E8h+var_B8]
0x180089522  movzx   r13d, word ptr [rax]
0x180089526  mov     rax, [rsp+0E8h+var_B0]
0x18008952b  movzx   eax, word ptr [rax]
0x18008952e  mov     [rsp+0E8h+var_C4], ax
0x180089533  lea     rax, [r9+rcx]
0x180089537  lea     r8, [rdx+rax*2]
0x18008953b  lea     rax, [rcx+rcx]
0x18008953f  sub     r11, rax
0x180089542  sub     r11, rdx
0x180089545  sub     r10, r9
0x180089548  movzx   r9d, [rsp+0E8h+var_C4]
0x18008954e  xchg    ax, ax
0x180089550  movzx   edx, word ptr [r8+rbp]
0x180089555  movzx   eax, word ptr [rbx]
0x180089558  movzx   ecx, word ptr [r8+r14]
0x18008955d  lea     r8, [r8+2]
0x180089561  imul    ecx, eax
0x180089564  movzx   eax, word ptr [r8-2]
0x180089569  imul    edx, r9d
0x18008956d  add     dx, cx
0x180089570  movzx   ecx, word ptr [r8+rsi-2]
0x180089576  imul    ecx, r13d
0x18008957a  add     dx, cx
0x18008957d  movzx   ecx, word ptr [r8+rdi-2]
0x180089583  imul    ecx, r15d
0x180089587  add     dx, cx
0x18008958a  mov     ecx, r12d
0x18008958d  imul    ecx, eax
0x180089590  add     dx, cx
0x180089593  shr     dx, 6
0x180089597  mov     [r11+r8-2], dx
0x18008959d  sub     r10, 1
0x1800895a1  jnz     short loc_180089550
0x1800895a3  mov     ebx, [rsp+0E8h+var_C8]
0x1800895a7  mov     r14, [rsp+0E8h+var_A0]
0x1800895ac  mov     edi, [rsp+0E8h+var_C0]
0x1800895b0  mov     r10, [rsp+0E8h+var_90]
0x1800895b5  lea     eax, [rbx+1]
0x1800895b8  xor     ebx, ebx
0x1800895ba  cmp     eax, 2
0x1800895bd  lea     r9, cs:180000000h
0x1800895c4  cmovl   ebx, eax
0x1800895c7  movzx   eax, [rsp+0E8h+var_56]
0x1800895cf  movsxd  rdx, ebx
0x1800895d2  shl     rdx, 6
0x1800895d6  mov     [rsp+0E8h+var_C8], ebx
0x1800895da  movzx   r8d, word ptr [rdx+r9+0DE5C2h]
0x1800895e3  movzx   ecx, word ptr [rdx+r9+0DE5C8h]
0x1800895ec  imul    r8d, eax
0x1800895f0  movzx   eax, [rsp+0E8h+var_50]
0x1800895f8  imul    ecx, eax
0x1800895fb  movzx   eax, [rsp+0E8h+var_52]
0x180089603  add     r8w, cx
0x180089607  movzx   ecx, word ptr [rdx+r9+0DE5C6h]
0x180089610  imul    ecx, eax
0x180089613  movzx   eax, [rsp+0E8h+var_54]
0x18008961b  add     r8w, cx
0x18008961f  movzx   ecx, word ptr [rdx+r9+0DE5C4h]
0x180089628  imul    ecx, eax
0x18008962b  movzx   eax, [rsp+0E8h+var_58]
0x180089633  add     r8w, cx
0x180089637  movzx   ecx, word ptr [rdx+r9+0DE5C0h]
0x180089640  imul    ecx, eax
0x180089643  mov     rax, [rsp+0E8h+var_60]
0x18008964b  add     r8w, cx
0x18008964f  shr     r8w, 8
0x180089654  mov     [r10+rax], r8b
0x180089658  inc     r10
0x18008965b  mov     r8, [rsp+0E8h+var_98]
0x180089660  mov     rax, [rsp+0E8h+var_88]
0x180089665  inc     r8d
0x180089668  mov     [rsp+0E8h+var_98], r8
0x18008966d  mov     [rsp+0E8h+var_90], r10
0x180089672  cmp     r8d, [rax+0Ch]
0x180089676  jl      loc_180089480
0x18008967c  mov     rcx, [rsp+0E8h+var_70]
0x180089681  lea     rdx, [rsp+0E8h+var_68]
0x180089689  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008968e  mov     rcx, [rsp+0E8h+var_48]
0x180089696  xor     rcx, rsp; StackCookie
0x180089699  call    __security_check_cookie
0x18008969e  mov     rbx, [rsp+0E8h+arg_0]
0x1800896a6  add     rsp, 0B0h
0x1800896ad  pop     r15
0x1800896af  pop     r14
0x1800896b1  pop     r13
0x1800896b3  pop     r12
0x1800896b5  pop     rdi
0x1800896b6  pop     rsi
0x1800896b7  pop     rbp
0x1800896b8  retn
```
