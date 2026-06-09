# Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)

- ea: `0x18008aae0`
- end: `0x18008b059`
- name: `??$PutBooleanUnit@VUniqueFact@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1401`
- prototype: `__int64 __fastcall(int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180088f70`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x18008aae0`

## pseudocode

```c
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,3>(
        int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rbp
  char *v18; // rdi
  __int64 v19; // r14
  __int64 v20; // r12
  _WORD *v21; // rbx
  char *v22; // r15
  _WORD *v23; // rcx
  _WORD *v24; // rax
  char *v25; // r13
  __int16 v26; // dx
  __int16 v27; // dx
  unsigned __int16 v28; // dx
  int v29; // edi
  int v30; // r9d
  _QWORD *v31; // r15
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r10
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r11
  __int64 v41; // rdi
  __int16 v42; // r12
  __int64 v43; // rsi
  __int64 v44; // rbp
  __int64 v45; // rcx
  __int64 v46; // r14
  __int16 v47; // r13
  __int64 v48; // rbx
  __int64 v49; // rax
  char *v50; // r10
  __int64 v51; // r9
  __int16 v52; // r8
  __int16 v53; // dx
  int v54; // eax
  __int64 v55; // rdx
  int v57; // [rsp+20h] [rbp-C8h]
  int v58; // [rsp+24h] [rbp-C4h]
  int v59; // [rsp+28h] [rbp-C0h]
  char *v60; // [rsp+30h] [rbp-B8h]
  __int16 *v61; // [rsp+38h] [rbp-B0h]
  char *v62; // [rsp+40h] [rbp-A8h]
  _WORD *v63; // [rsp+48h] [rbp-A0h]
  _WORD *v64; // [rsp+50h] [rbp-98h]
  _WORD *v65; // [rsp+58h] [rbp-90h]
  _WORD *v66; // [rsp+60h] [rbp-88h]
  __int64 v68; // [rsp+70h] [rbp-78h]
  char v71[8]; // [rsp+88h] [rbp-60h] BYREF
  _BYTE *v72; // [rsp+90h] [rbp-58h]
  __int16 v73; // [rsp+98h] [rbp-50h] BYREF
  __int16 v74; // [rsp+9Ah] [rbp-4Eh]
  __int16 v75; // [rsp+9Ch] [rbp-4Ch]
  __int16 v76; // [rsp+9Eh] [rbp-4Ah]
  __int16 v77; // [rsp+A0h] [rbp-48h]
  __int16 v78; // [rsp+A2h] [rbp-46h]
  __int16 v79; // [rsp+A4h] [rbp-44h]

  __asm { vpxor   xmm0, xmm0, xmm0 }
  _RDX = v71;
  __asm { vmovups xmmword ptr [r11-60h], xmm0 }
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, v71);
  v11 = a4[3];
  v12 = 7;
  if ( a1 )
    a1 = 0;
  v13 = a4[2] - v11;
  v14 = a4[4] - v11;
  v15 = (__int64)a5 << 6;
  v16 = a4[5] - v11;
  v58 = a1;
  v60 = &byte_1800DE7C4[v15];
  v17 = a4[6] - v11;
  v18 = &byte_1800DE7C4[v15];
  v19 = a4[1] - v11;
  v61 = (__int16 *)((char *)&word_1800DE7C6 + v15);
  v20 = *a4 - v11;
  v21 = (__int16 *)((char *)&word_1800DE7C6 + v15);
  v62 = &byte_1800DE7C8[v15];
  v22 = &byte_1800DE7C8[v15];
  v66 = (__int16 *)((char *)&word_1800DE7CA + v15);
  v65 = (_WORD *)((char *)&dword_1800DE7CC + v15);
  v23 = (__int16 *)((char *)&word_1800DE7C2 + v15);
  v24 = (_WORD *)(0x180000000LL + v15 + 911296);
  v64 = v23;
  v63 = v24;
  v25 = (char *)&v73 - v11;
  do
  {
    v26 = *(_WORD *)(v20 + v11);
    v11 += 2;
    v27 = *v24 * v26;
    v24 = v63;
    v28 = *v21 * *(_WORD *)(v11 - 2)
        + *(_WORD *)v18 * *(_WORD *)(v13 + v11 - 2)
        + *(_WORD *)v22 * *(_WORD *)(v14 + v11 - 2)
        + *v66 * *(_WORD *)(v16 + v11 - 2)
        + *v65 * *(_WORD *)(v11 + v17 - 2)
        + *v23 * *(_WORD *)(v19 + v11 - 2)
        + v27;
    v23 = v64;
    *(_WORD *)&v25[v11 - 2] = v28 >> 6;
    --v12;
  }
  while ( v12 );
  v29 = v58;
  v30 = 1;
  v31 = a4;
  v32 = 0;
  v33 = (__int64)v58 << 6;
  v59 = 1;
  *v72 = (unsigned __int16)(v77 * *(_WORD *)&byte_1800DE7C8[v33]
                          + v78 * *(__int16 *)((char *)&word_1800DE7CA + v33)
                          + v74 * *(__int16 *)((char *)&word_1800DE7C2 + v33)
                          + v75 * *(_WORD *)&byte_1800DE7C4[v33]
                          + v79 * *(_WORD *)((char *)&dword_1800DE7CC + v33)
                          + v76 * *(__int16 *)((char *)&word_1800DE7C6 + v33)
                          + v73 * *(_WORD *)&Binary::Policy::UniqueFact::OddOperation[v33]) >> 8;
  if ( *(int *)(a3 + 12) > 1 )
  {
    v34 = 1;
    v68 = 1;
    do
    {
      v35 = 0;
      v36 = Binary::Policy::UniqueFact::GlobalCase[v29];
      v37 = 7 - v36;
      v32 += v36;
      v57 = v32;
      v38 = 7 - (int)v36;
      if ( 7 - (int)v36 > 0 )
      {
        do
        {
          *(&v73 + v35) = *(&v73 + v36 + v35);
          ++v35;
        }
        while ( v35 < v37 );
        v30 = v59;
      }
      if ( v37 < 7LL )
      {
        v39 = v31[3];
        v40 = v31[2] - v39;
        v41 = v31[5] - v39;
        v42 = *(_WORD *)v60;
        v43 = v31[6] - v39;
        v44 = *v31 - v39;
        v45 = v32;
        v46 = v31[1] - v39;
        v47 = *v61;
        v48 = v31[4] - v39;
        v49 = v39 + 2 * (v37 + v45);
        v50 = (char *)&v73 - v39 + -2 * v45;
        v51 = 7 - v38;
        do
        {
          v52 = *(_WORD *)(v49 + v44);
          v53 = *(_WORD *)(v46 + v49);
          v49 += 2;
          *(_WORD *)&v50[v49 - 2] = (unsigned __int16)(v47 * *(_WORD *)(v49 - 2)
                                                     + v42 * *(_WORD *)(v40 + v49 - 2)
                                                     + *(_WORD *)v62 * *(_WORD *)(v48 + v49 - 2)
                                                     + *v66 * *(_WORD *)(v41 + v49 - 2)
                                                     + *v65 * *(_WORD *)(v43 + v49 - 2)
                                                     + *v64 * v53
                                                     + *v63 * v52) >> 6;
          --v51;
        }
        while ( v51 );
        v31 = a4;
        v32 = v57;
        v29 = v58;
        v30 = v59;
        v34 = v68;
      }
      v54 = v29 + 1;
      v29 = 0;
      if ( v54 < 1 )
        v29 = v54;
      ++v30;
      v55 = (__int64)v29 << 6;
      v58 = v29;
      v59 = v30;
      v72[v34] = (unsigned __int16)(v77 * *(_WORD *)&byte_1800DE7C8[v55]
                                  + v78 * *(__int16 *)((char *)&word_1800DE7CA + v55)
                                  + v74 * *(__int16 *)((char *)&word_1800DE7C2 + v55)
                                  + v75 * *(_WORD *)&byte_1800DE7C4[v55]
                                  + v79 * *(_WORD *)((char *)&dword_1800DE7CC + v55)
                                  + v76 * *(__int16 *)((char *)&word_1800DE7C6 + v55)
                                  + v73 * *(_WORD *)&Binary::Policy::UniqueFact::OddOperation[v55]) >> 8;
      v68 = ++v34;
    }
    while ( v30 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, v71);
}

```

## disassembly

```asm
0x18008aae0  mov     r11, rsp
0x18008aae3  mov     [r11+8], rbx
0x18008aae7  push    rbp
0x18008aae8  push    rsi
0x18008aae9  push    rdi
0x18008aaea  push    r12
0x18008aaec  push    r13
0x18008aaee  push    r14
0x18008aaf0  push    r15
0x18008aaf2  sub     rsp, 0B0h
0x18008aaf9  mov     rax, cs:__security_cookie
0x18008ab00  xor     rax, rsp
0x18008ab03  mov     [rsp+0E8h+var_40], rax
0x18008ab0b  mov     r15, r9
0x18008ab0e  mov     [rsp+0E8h+var_80], r9
0x18008ab13  mov     r9, rdx
0x18008ab16  mov     [rsp+0E8h+var_68], rdx
0x18008ab1e  mov     edi, ecx
0x18008ab20  mov     [rsp+0E8h+var_70], r8
0x18008ab25  vpxor   xmm0, xmm0, xmm0
0x18008ab29  xor     esi, esi
0x18008ab2b  lea     rdx, [r11-60h]
0x18008ab2f  mov     rcx, r9
0x18008ab32  mov     [rsp+0E8h+var_C8], esi
0x18008ab36  vmovups xmmword ptr [r11-60h], xmm0
0x18008ab3c  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008ab41  mov     r8, [r15+18h]
0x18008ab45  lea     rdx, cs:180000000h
0x18008ab4c  mov     r10, [r15+10h]
0x18008ab50  lea     rcx, rva byte_1800DE7C4[rdx]
0x18008ab57  mov     r11, [r15+20h]
0x18008ab5b  lea     r13, [rsp+0E8h+var_50]
0x18008ab63  mov     rbp, [r15+30h]
0x18008ab67  test    edi, edi
0x18008ab69  mov     r14, [r15+8]
0x18008ab6d  mov     r9d, 7
0x18008ab73  mov     r12, [r15]
0x18008ab76  cmovnz  edi, esi
0x18008ab79  mov     rsi, [r15+28h]
0x18008ab7d  sub     r10, r8
0x18008ab80  movsxd  rax, [rsp+0E8h+arg_20]
0x18008ab88  sub     r11, r8
0x18008ab8b  shl     rax, 6
0x18008ab8f  sub     rsi, r8
0x18008ab92  add     rcx, rax
0x18008ab95  mov     [rsp+0E8h+var_C4], edi
0x18008ab99  mov     [rsp+0E8h+var_B8], rcx
0x18008ab9e  sub     rbp, r8
0x18008aba1  mov     rdi, [rsp+0E8h+var_B8]
0x18008aba6  lea     rcx, rva word_1800DE7C6[rdx]
0x18008abad  add     rcx, rax
0x18008abb0  sub     r14, r8
0x18008abb3  mov     [rsp+0E8h+var_B0], rcx
0x18008abb8  sub     r12, r8
0x18008abbb  mov     rbx, [rsp+0E8h+var_B0]
0x18008abc0  lea     rcx, rva byte_1800DE7C8[rdx]
0x18008abc7  add     rcx, rax
0x18008abca  mov     [rsp+0E8h+var_A8], rcx
0x18008abcf  lea     rcx, rva word_1800DE7CA[rdx]
0x18008abd6  mov     r15, [rsp+0E8h+var_A8]
0x18008abdb  add     rcx, rax
0x18008abde  mov     [rsp+0E8h+var_88], rcx
0x18008abe3  lea     rcx, rva dword_1800DE7CC[rdx]
0x18008abea  add     rcx, rax
0x18008abed  mov     [rsp+0E8h+var_90], rcx
0x18008abf2  lea     rcx, rva word_1800DE7C2[rdx]
0x18008abf9  add     rcx, rax
0x18008abfc  lea     rax, [rax+0DE7C0h]
0x18008ac03  add     rax, rdx
0x18008ac06  mov     [rsp+0E8h+var_98], rcx
0x18008ac0b  mov     [rsp+0E8h+var_A0], rax
0x18008ac10  sub     r13, r8
0x18008ac13  nop     dword ptr [rax+00h]
0x18008ac17  nop     word ptr [rax+rax+00000000h]
0x18008ac20  movzx   eax, word ptr [rax]
0x18008ac23  movzx   edx, word ptr [r12+r8]
0x18008ac28  lea     r8, [r8+2]
0x18008ac2c  imul    edx, eax
0x18008ac2f  movzx   eax, word ptr [rcx]
0x18008ac32  movzx   ecx, word ptr [r14+r8-2]
0x18008ac38  imul    ecx, eax
0x18008ac3b  mov     rax, [rsp+0E8h+var_90]
0x18008ac40  movzx   eax, word ptr [rax]
0x18008ac43  add     dx, cx
0x18008ac46  movzx   ecx, word ptr [r8+rbp-2]
0x18008ac4c  imul    ecx, eax
0x18008ac4f  mov     rax, [rsp+0E8h+var_88]
0x18008ac54  movzx   eax, word ptr [rax]
0x18008ac57  add     dx, cx
0x18008ac5a  movzx   ecx, word ptr [rsi+r8-2]
0x18008ac60  imul    ecx, eax
0x18008ac63  movzx   eax, word ptr [r15]
0x18008ac67  add     dx, cx
0x18008ac6a  movzx   ecx, word ptr [r11+r8-2]
0x18008ac70  imul    ecx, eax
0x18008ac73  movzx   eax, word ptr [rdi]
0x18008ac76  add     dx, cx
0x18008ac79  movzx   ecx, word ptr [r10+r8-2]
0x18008ac7f  imul    ecx, eax
0x18008ac82  movzx   eax, word ptr [rbx]
0x18008ac85  add     dx, cx
0x18008ac88  movzx   ecx, word ptr [r8-2]
0x18008ac8d  imul    ecx, eax
0x18008ac90  mov     rax, [rsp+0E8h+var_A0]
0x18008ac95  add     dx, cx
0x18008ac98  mov     rcx, [rsp+0E8h+var_98]
0x18008ac9d  shr     dx, 6
0x18008aca1  mov     [r8+r13-2], dx
0x18008aca7  sub     r9, 1
0x18008acab  jnz     loc_18008AC20
0x18008acb1  movzx   eax, [rsp+0E8h+var_50]
0x18008acb9  lea     r11, cs:180000000h
0x18008acc0  movsxd  rdi, [rsp+0E8h+var_C4]
0x18008acc5  mov     r9d, 1
0x18008accb  mov     r15, [rsp+0E8h+var_80]
0x18008acd0  mov     rdx, rdi
0x18008acd3  mov     ebx, [rsp+0E8h+var_C8]
0x18008acd7  shl     rdx, 6
0x18008acdb  mov     [rsp+0E8h+var_C0], r9
0x18008ace0  movzx   r8d, word ptr [rdx+r11+0DE7C0h]
0x18008ace9  movzx   ecx, word ptr [rdx+r11+0DE7C6h]
0x18008acf2  imul    r8d, eax
0x18008acf6  movzx   eax, [rsp+0E8h+var_4A]
0x18008acfe  imul    ecx, eax
0x18008ad01  movzx   eax, [rsp+0E8h+var_44]
0x18008ad09  add     r8w, cx
0x18008ad0d  movzx   ecx, word ptr [rdx+r11+0DE7CCh]
0x18008ad16  imul    ecx, eax
0x18008ad19  movzx   eax, [rsp+0E8h+var_4C]
0x18008ad21  add     r8w, cx
0x18008ad25  movzx   ecx, word ptr [rdx+r11+0DE7C4h]
0x18008ad2e  imul    ecx, eax
0x18008ad31  movzx   eax, [rsp+0E8h+var_4E]
0x18008ad39  add     r8w, cx
0x18008ad3d  movzx   ecx, word ptr [rdx+r11+0DE7C2h]
0x18008ad46  imul    ecx, eax
0x18008ad49  movzx   eax, [rsp+0E8h+var_46]
0x18008ad51  add     r8w, cx
0x18008ad55  movzx   ecx, word ptr [rdx+r11+0DE7CAh]
0x18008ad5e  imul    ecx, eax
0x18008ad61  movzx   eax, [rsp+0E8h+var_48]
0x18008ad69  add     r8w, cx
0x18008ad6d  movzx   ecx, word ptr [rdx+r11+0DE7C8h]
0x18008ad76  imul    ecx, eax
0x18008ad79  mov     rax, [rsp+0E8h+var_58]
0x18008ad81  add     r8w, cx
0x18008ad85  shr     r8w, 8
0x18008ad8a  mov     [rax], r8b
0x18008ad8d  mov     rax, [rsp+0E8h+var_70]
0x18008ad92  cmp     [rax+0Ch], r9d
0x18008ad96  jle     loc_18008B019
0x18008ad9c  mov     r10d, r9d
0x18008ad9f  mov     [rsp+0E8h+var_78], r9
0x18008ada4  nop     dword ptr [rax+00h]
0x18008ada8  nop     dword ptr [rax+rax+00000000h]
0x18008adb0  movsxd  rax, edi
0x18008adb3  xor     edx, edx
0x18008adb5  movsxd  rcx, ds:rva ?GlobalCase@UniqueFact@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B[r11+rax*4]; Data::StripedCategory<int,1> const Binary::Policy::UniqueFact::GlobalCase ...
0x18008adbd  mov     eax, 7
0x18008adc2  sub     eax, ecx
0x18008adc4  add     ebx, ecx
0x18008adc6  mov     [rsp+0E8h+var_C8], ebx
0x18008adca  movsxd  r8, eax
0x18008adcd  test    eax, eax
0x18008adcf  jle     short loc_18008AE01
0x18008add1  lea     r9, [rcx+rcx]
0x18008add5  nop     word ptr [rax+rax+00000000h]
0x18008ade0  lea     rax, [r9+rdx*2]
0x18008ade4  movzx   ecx, [rsp+rax+0E8h+var_50]
0x18008adec  mov     [rsp+rdx*2+0E8h+var_50], cx
0x18008adf4  inc     rdx
0x18008adf7  cmp     rdx, r8
0x18008adfa  jl      short loc_18008ADE0
0x18008adfc  mov     r9, [rsp+0E8h+var_C0]
0x18008ae01  cmp     r8, 7
0x18008ae05  jge     loc_18008AF2E
0x18008ae0b  mov     rdx, [r15+18h]
0x18008ae0f  lea     r10, [rsp+0E8h+var_50]
0x18008ae17  mov     rax, [rsp+0E8h+var_B8]
0x18008ae1c  mov     r9d, 7
0x18008ae22  mov     r11, [r15+10h]
0x18008ae26  mov     rdi, [r15+28h]
0x18008ae2a  sub     r11, rdx
0x18008ae2d  mov     rsi, [r15+30h]
0x18008ae31  sub     rdi, rdx
0x18008ae34  movzx   r12d, word ptr [rax]
0x18008ae38  sub     rsi, rdx
0x18008ae3b  mov     rax, [rsp+0E8h+var_B0]
0x18008ae40  mov     rbp, [r15]
0x18008ae43  mov     r14, [r15+8]
0x18008ae47  sub     rbp, rdx
0x18008ae4a  movsxd  rcx, ebx
0x18008ae4d  sub     r14, rdx
0x18008ae50  movzx   r13d, word ptr [rax]
0x18008ae54  mov     rbx, [r15+20h]
0x18008ae58  mov     r15, [rsp+0E8h+var_A8]
0x18008ae5d  sub     rbx, rdx
0x18008ae60  lea     rax, [r8+rcx]
0x18008ae64  add     rcx, rcx
0x18008ae67  sub     r10, rcx
0x18008ae6a  lea     rax, [rdx+rax*2]
0x18008ae6e  sub     r10, rdx
0x18008ae71  sub     r9, r8
0x18008ae74  nop     dword ptr [rax+00h]
0x18008ae78  nop     dword ptr [rax+rax+00000000h]
0x18008ae80  mov     rcx, [rsp+0E8h+var_A0]
0x18008ae85  movzx   r8d, word ptr [rax+rbp]
0x18008ae8a  movzx   edx, word ptr [r14+rax]
0x18008ae8f  lea     rax, [rax+2]
0x18008ae93  movzx   ecx, word ptr [rcx]
0x18008ae96  imul    r8d, ecx
0x18008ae9a  mov     rcx, [rsp+0E8h+var_98]
0x18008ae9f  movzx   ecx, word ptr [rcx]
0x18008aea2  imul    edx, ecx
0x18008aea5  mov     rcx, [rsp+0E8h+var_90]
0x18008aeaa  movzx   ecx, word ptr [rcx]
0x18008aead  add     r8w, dx
0x18008aeb1  movzx   edx, word ptr [rsi+rax-2]
0x18008aeb6  imul    edx, ecx
0x18008aeb9  mov     rcx, [rsp+0E8h+var_88]
0x18008aebe  movzx   ecx, word ptr [rcx]
0x18008aec1  add     r8w, dx
0x18008aec5  movzx   edx, word ptr [rdi+rax-2]
0x18008aeca  imul    edx, ecx
0x18008aecd  movzx   ecx, word ptr [r15]
0x18008aed1  add     r8w, dx
0x18008aed5  movzx   edx, word ptr [rbx+rax-2]
0x18008aeda  imul    edx, ecx
0x18008aedd  add     r8w, dx
0x18008aee1  movzx   edx, word ptr [r11+rax-2]
0x18008aee7  imul    edx, r12d
0x18008aeeb  add     r8w, dx
0x18008aeef  movzx   edx, word ptr [rax-2]
0x18008aef3  imul    edx, r13d
0x18008aef7  add     r8w, dx
0x18008aefb  shr     r8w, 6
0x18008af00  mov     [r10+rax-2], r8w
0x18008af06  sub     r9, 1
0x18008af0a  jnz     loc_18008AE80
0x18008af10  mov     r15, [rsp+0E8h+var_80]
0x18008af15  lea     r11, cs:180000000h
0x18008af1c  mov     ebx, [rsp+0E8h+var_C8]
0x18008af20  mov     edi, [rsp+0E8h+var_C4]
0x18008af24  mov     r9, [rsp+0E8h+var_C0]
0x18008af29  mov     r10, [rsp+0E8h+var_78]
0x18008af2e  lea     eax, [rdi+1]
0x18008af31  xor     edi, edi
0x18008af33  cmp     eax, 1
0x18008af36  cmovl   edi, eax
0x18008af39  movzx   eax, [rsp+0E8h+var_50]
0x18008af41  movsxd  rdx, edi
0x18008af44  inc     r9d
0x18008af47  shl     rdx, 6
0x18008af4b  mov     [rsp+0E8h+var_C4], edi
0x18008af4f  mov     [rsp+0E8h+var_C0], r9
0x18008af54  movzx   r8d, word ptr [rdx+r11+0DE7C0h]
0x18008af5d  movzx   ecx, word ptr [rdx+r11+0DE7C6h]
0x18008af66  imul    r8d, eax
0x18008af6a  movzx   eax, [rsp+0E8h+var_4A]
0x18008af72  imul    ecx, eax
0x18008af75  movzx   eax, [rsp+0E8h+var_44]
0x18008af7d  add     r8w, cx
0x18008af81  movzx   ecx, word ptr [rdx+r11+0DE7CCh]
0x18008af8a  imul    ecx, eax
0x18008af8d  movzx   eax, [rsp+0E8h+var_4C]
0x18008af95  add     r8w, cx
0x18008af99  movzx   ecx, word ptr [rdx+r11+0DE7C4h]
0x18008afa2  imul    ecx, eax
0x18008afa5  movzx   eax, [rsp+0E8h+var_4E]
0x18008afad  add     r8w, cx
0x18008afb1  movzx   ecx, word ptr [rdx+r11+0DE7C2h]
0x18008afba  imul    ecx, eax
0x18008afbd  movzx   eax, [rsp+0E8h+var_46]
0x18008afc5  add     r8w, cx
0x18008afc9  movzx   ecx, word ptr [rdx+r11+0DE7CAh]
0x18008afd2  imul    ecx, eax
0x18008afd5  movzx   eax, [rsp+0E8h+var_48]
0x18008afdd  add     r8w, cx
0x18008afe1  movzx   ecx, word ptr [rdx+r11+0DE7C8h]
0x18008afea  imul    ecx, eax
0x18008afed  mov     rax, [rsp+0E8h+var_58]
0x18008aff5  add     r8w, cx
0x18008aff9  shr     r8w, 8
0x18008affe  mov     [r10+rax], r8b
0x18008b002  inc     r10
0x18008b005  mov     rax, [rsp+0E8h+var_70]
0x18008b00a  mov     [rsp+0E8h+var_78], r10
0x18008b00f  cmp     r9d, [rax+0Ch]
0x18008b013  jl      loc_18008ADB0
0x18008b019  mov     rcx, [rsp+0E8h+var_68]
0x18008b021  lea     rdx, [rsp+0E8h+var_60]
0x18008b029  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008b02e  mov     rcx, [rsp+0E8h+var_40]
0x18008b036  xor     rcx, rsp; StackCookie
0x18008b039  call    __security_check_cookie
0x18008b03e  mov     rbx, [rsp+0E8h+arg_0]
0x18008b046  add     rsp, 0B0h
0x18008b04d  pop     r15
0x18008b04f  pop     r14
0x18008b051  pop     r13
  ... truncated ...
```
