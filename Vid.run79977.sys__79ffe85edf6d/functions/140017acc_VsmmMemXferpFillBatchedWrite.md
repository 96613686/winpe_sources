# VsmmMemXferpFillBatchedWrite

- ea: `0x140017acc`
- end: `0x140018230`
- name: `VsmmMemXferpFillBatchedWrite`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140026b7c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140011518`
- `0x140017978`
- `0x140017acc`
- `0x140021c60`
- `0x1400fe190`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017b42`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017ea9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017b42`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017ea9`
- `ntoskrnl!ExAllocatePool2` at `0x140017d14`
- `ntoskrnl!ExAllocatePool2` at `0x140017d14`

## string_xrefs

- `0x140017bda`: `VsmmMemXferpFillBatchedWrite`
- `0x140017d5d`: `VsmmMemXferpFillBatchedWrite`
- `0x140017f52`: `VsmmMemXferpFillBatchedWrite`
- `0x140018012`: `VsmmMemXferpFillBatchedWrite`
- `0x1400180e7`: `VsmmMemXferpFillBatchedWrite`

## pseudocode

```c
__int64 __fastcall VsmmMemXferpFillBatchedWrite(_QWORD *a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v6; // edi
  unsigned __int64 i; // rsi
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  __int64 Pool2; // rax
  int v12; // ebx
  const GUID *v13; // r9
  __int64 v14; // rax
  unsigned __int8 *v15; // rdx
  const GUID *v16; // r8
  unsigned __int64 j; // rsi
  unsigned __int64 v18; // rdi
  __int64 v19; // r14
  int v21; // [rsp+30h] [rbp-208h] BYREF
  int v22; // [rsp+34h] [rbp-204h] BYREF
  __int64 v23; // [rsp+38h] [rbp-200h] BYREF
  __int64 v24; // [rsp+40h] [rbp-1F8h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-1E8h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-1C8h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-1B8h] BYREF
  int *v28; // [rsp+90h] [rbp-1A8h]
  __int64 v29; // [rsp+98h] [rbp-1A0h]
  int *v30; // [rsp+A0h] [rbp-198h]
  __int64 v31; // [rsp+A8h] [rbp-190h]
  __int64 v32; // [rsp+B0h] [rbp-188h]
  __int64 v33; // [rsp+B8h] [rbp-180h]
  int *v34; // [rsp+C0h] [rbp-178h]
  __int64 v35; // [rsp+C8h] [rbp-170h]
  __int64 v36; // [rsp+D0h] [rbp-168h]
  int v37; // [rsp+D8h] [rbp-160h] BYREF
  int v38; // [rsp+DCh] [rbp-15Ch]
  __int64 *v39; // [rsp+E0h] [rbp-158h]
  __int64 v40; // [rsp+E8h] [rbp-150h]
  _QWORD v41[32]; // [rsp+F0h] [rbp-148h] BYREF

  v24 = *(_QWORD *)(a1[2] + 8LL);
  v23 = v24;
  v6 = 0;
  for ( i = 0; i < a3; i += v8 )
  {
    v8 = 16;
    if ( a3 - i < 0x10 )
      v8 = a3 - i;
    if ( 16 * v8 )
    {
      if ( (a2 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
    }
    RtlCopyFromUser(v41, (void *)(a2 + 16 * i), 16 * v8);
    v9 = 0;
    if ( v8 )
    {
      while ( v41[2 * v9 + 1] < 0xFFFFFu )
      {
        v10 = 8 * LODWORD(v41[2 * v9 + 1]) + 48;
        if ( v10 + v6 < v6 )
        {
          v6 = 8 * LODWORD(v41[2 * v9 + 1]) + 48;
          break;
        }
        v6 += v10;
        if ( ++v9 >= v8 )
          break;
      }
    }
  }
  if ( v6 )
  {
    Pool2 = ExAllocatePool2(64, v6, 1833788502);
    a1[9] = Pool2;
    if ( !Pool2 )
    {
      v12 = -1073741670;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
        tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v22 = 2808;
        v28 = &v22;
        v30 = &v21;
        v32 = v24 + 656;
        v34 = &v37;
        v36 = *(_QWORD *)(v24 + 128);
        v37 = *(unsigned __int16 *)(v24 + 120);
        v14 = *(_QWORD *)(v24 + 648);
        v15 = (unsigned __int8 *)&unk_14004CFB8;
LABEL_20:
        v16 = 0;
        v38 = (int)v13;
LABEL_21:
        v23 = v14;
        v39 = &v23;
        v29 = 4;
        v21 = v12;
        v31 = 4;
        v33 = 16;
        v35 = 2;
        v40 = 8;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, v15, v16, v13, 0xAu, &v25);
      }
      return (unsigned int)v12;
    }
    a1[11] = 0;
    a1[10] = v6;
  }
  for ( j = 0; ; j += v18 )
  {
    if ( j >= a3 )
      return 0;
    v18 = 16;
    if ( a3 - j < 0x10 )
      v18 = a3 - j;
    if ( 16 * v18 && (a2 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v41, (void *)(a2 + 16 * j), 16 * v18);
    v19 = 0;
    if ( v18 )
      break;
LABEL_33:
    v12 = VsmmMemXferpBatchedWriteAddRanges(a1, v41, v18);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
        tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v22 = 2869;
        v28 = &v22;
        v30 = &v21;
        v32 = v24 + 656;
        v34 = &v37;
        v36 = *(_QWORD *)(v24 + 128);
        v37 = *(unsigned __int16 *)(v24 + 120);
        v14 = *(_QWORD *)(v24 + 648);
        v15 = (unsigned __int8 *)&unk_14004CEDC;
        goto LABEL_20;
      }
      return (unsigned int)v12;
    }
  }
  while ( 1 )
  {
    v12 = VsmmGpaRangeValidatePageRange(v24, v41[2 * v19], v41[2 * v19 + 1]);
    if ( v12 < 0 )
      break;
    if ( ++v19 >= v18 )
      goto LABEL_33;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
    tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v22 = 2854;
    v28 = &v22;
    v30 = &v21;
    v32 = v24 + 656;
    v34 = &v37;
    v36 = *(_QWORD *)(v24 + 128);
    v37 = *(unsigned __int16 *)(v24 + 120);
    v38 = (int)v16;
    v14 = *(_QWORD *)(v24 + 648);
    v13 = 0;
    v15 = (unsigned __int8 *)&unk_14004CE6E;
    goto LABEL_21;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140017acc  push    rbx
0x140017ace  push    rsi
0x140017acf  push    rdi
0x140017ad0  push    r12
0x140017ad2  push    r13
0x140017ad4  push    r14
0x140017ad6  push    r15
0x140017ad8  sub     rsp, 200h
0x140017adf  mov     rax, cs:__security_cookie
0x140017ae6  xor     rax, rsp
0x140017ae9  mov     [rsp+238h+var_48], rax
0x140017af1  mov     r12, r8
0x140017af4  mov     r13, rdx
0x140017af7  mov     r15, rcx
0x140017afa  mov     rax, [rcx+10h]
0x140017afe  mov     rax, [rax+8]
0x140017b02  mov     [rsp+238h+var_1F8], rax
0x140017b07  mov     [rsp+238h+var_200], rax
0x140017b0c  xor     r9d, r9d
0x140017b0f  mov     edi, r9d
0x140017b12  mov     esi, r9d
0x140017b15  cmp     rsi, r12
0x140017b18  jnb     loc_140017CFD
0x140017b1e  mov     rax, r12
0x140017b21  sub     rax, rsi
0x140017b24  mov     ebx, 10h
0x140017b29  cmp     rax, rbx
0x140017b2c  cmovb   rbx, rax
0x140017b30  mov     r8, rbx
0x140017b33  shl     r8, 4
0x140017b37  test    r8, r8
0x140017b3a  jz      short loc_140017B4E
0x140017b3c  test    r13b, 7
0x140017b40  jz      short loc_140017B4E
0x140017b42  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140017b49  nop     dword ptr [rax+rax+00h]
0x140017b4e  mov     rdx, rsi
0x140017b51  shl     rdx, 4
0x140017b55  add     rdx, r13; Src
0x140017b58  lea     rcx, [rsp+238h+var_148]; void *
0x140017b60  call    RtlCopyFromUser
0x140017b65  nop
0x140017b66  xor     r9d, r9d
0x140017b69  mov     ecx, r9d
0x140017b6c  test    rbx, rbx
0x140017b6f  jz      short loc_140017BA8
0x140017b71  mov     rax, rcx
0x140017b74  add     rax, rax
0x140017b77  cmp     [rsp+rax*8+238h+var_140], 0FFFFFh
0x140017b83  jnb     short loc_140017BA8
0x140017b85  mov     eax, dword ptr [rsp+rax*8+238h+var_140]
0x140017b8c  lea     eax, ds:30h[rax*8]
0x140017b93  lea     edx, [rax+rdi]
0x140017b96  cmp     edx, edi
0x140017b98  jb      short loc_140017BA6
0x140017b9a  mov     edi, edx
0x140017b9c  inc     rcx
0x140017b9f  cmp     rcx, rbx
0x140017ba2  jb      short loc_140017B71
0x140017ba4  jmp     short loc_140017BA8
0x140017ba6  mov     edi, eax
0x140017ba8  add     rsi, rbx
0x140017bab  jmp     loc_140017B15
0x140017bb0  mov     ebx, eax
0x140017bb2  mov     eax, cs:dword_140065110
0x140017bb8  cmp     eax, 2
0x140017bbb  jbe     loc_140017CF8
0x140017bc1  mov     edx, 100h
0x140017bc6  lea     rcx, dword_140065110
0x140017bcd  call    _tlgKeywordOn
0x140017bd2  test    al, al
0x140017bd4  jz      loc_140017CF8
0x140017bda  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140017be1  lea     rcx, [rsp+238h+var_1C8]
0x140017be6  call    _tlgCreate1Sz_char
0x140017beb  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017bf2  lea     rcx, [rsp+238h+var_1B8]
0x140017bfa  call    _tlgCreate1Sz_char
0x140017bff  mov     [rsp+238h+var_208], 0AD2h
0x140017c07  lea     rax, [rsp+238h+var_208]
0x140017c0c  mov     [rsp+238h+var_1A8], rax
0x140017c14  mov     [rsp+238h+var_1A0], 4
0x140017c20  mov     [rsp+238h+var_204], ebx
0x140017c24  lea     rax, [rsp+238h+var_204]
0x140017c29  mov     [rsp+238h+var_198], rax
0x140017c31  mov     [rsp+238h+var_190], 4
0x140017c3d  mov     rcx, [rsp+238h+var_200]
0x140017c42  lea     rax, [rcx+290h]
0x140017c49  mov     [rsp+238h+var_188], rax
0x140017c51  mov     [rsp+238h+var_180], 10h
0x140017c5d  mov     edx, 7
0x140017c62  mov     eax, edx
0x140017c64  shl     rax, 4
0x140017c68  lea     r8, [rsp+238h+var_1D0]
0x140017c6d  add     rax, r8
0x140017c70  mov     [rsp+238h+var_178], rax
0x140017c78  mov     [rsp+238h+var_170], 2
0x140017c84  mov     rax, [rcx+80h]
0x140017c8b  mov     [rsp+238h+var_168], rax
0x140017c93  movzx   eax, word ptr [rcx+78h]
0x140017c97  mov     [rsp+238h+var_160], eax
0x140017c9e  mov     [rsp+238h+var_15C], 0
0x140017ca9  mov     rax, [rcx+288h]
0x140017cb0  mov     [rsp+238h+var_200], rax
0x140017cb5  lea     rax, [rsp+238h+var_200]
0x140017cba  mov     [rsp+238h+var_158], rax
0x140017cc2  mov     [rsp+238h+var_150], 8
0x140017cce  lea     eax, [rdx+3]
0x140017cd1  lea     rcx, [rsp+238h+var_1E8]
0x140017cd6  mov     [rsp+238h+var_210], rcx
0x140017cdb  mov     [rsp+238h+var_218], eax
0x140017cdf  xor     r9d, r9d
0x140017ce2  xor     r8d, r8d
0x140017ce5  lea     rdx, unk_14004CF4A
0x140017cec  lea     rcx, dword_140065110
0x140017cf3  call    _tlgWriteTransfer_EtwWriteTransfer
0x140017cf8  jmp     loc_14001820A
0x140017cfd  test    edi, edi
0x140017cff  jz      loc_140017E79
0x140017d05  mov     ebx, edi
0x140017d07  mov     r8d, 6D4D6456h
0x140017d0d  mov     edx, edi
0x140017d0f  mov     ecx, 40h ; '@'
0x140017d14  call    cs:__imp_ExAllocatePool2
0x140017d1b  nop     dword ptr [rax+rax+00h]
0x140017d20  mov     [r15+48h], rax
0x140017d24  xor     r9d, r9d
0x140017d27  test    rax, rax
0x140017d2a  jnz     loc_140017E71
0x140017d30  mov     ebx, 0C000009Ah
0x140017d35  mov     eax, cs:dword_140065110
0x140017d3b  cmp     eax, 2
0x140017d3e  jbe     loc_14001820A
0x140017d44  mov     edx, 100h
0x140017d49  lea     rcx, dword_140065110
0x140017d50  call    _tlgKeywordOn
0x140017d55  test    al, al
0x140017d57  jz      loc_14001820A
0x140017d5d  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140017d64  lea     rcx, [rsp+238h+var_1C8]
0x140017d69  call    _tlgCreate1Sz_char
0x140017d6e  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017d75  lea     rcx, [rsp+238h+var_1B8]
0x140017d7d  call    _tlgCreate1Sz_char
0x140017d82  mov     [rsp+238h+var_204], 0AF8h
0x140017d8a  lea     rax, [rsp+238h+var_204]
0x140017d8f  mov     [rsp+238h+var_1A8], rax
0x140017d97  lea     rcx, [rsp+238h+var_208]
0x140017d9c  mov     [rsp+238h+var_198], rcx
0x140017da4  mov     r14, [rsp+238h+var_1F8]
0x140017da9  lea     rax, [r14+290h]
0x140017db0  mov     [rsp+238h+var_188], rax
0x140017db8  lea     rax, [rsp+238h+var_160]
0x140017dc0  mov     [rsp+238h+var_178], rax
0x140017dc8  mov     rax, [r14+80h]
0x140017dcf  mov     [rsp+238h+var_168], rax
0x140017dd7  movzx   eax, word ptr [r14+78h]
0x140017ddc  mov     [rsp+238h+var_160], eax
0x140017de3  mov     rax, [r14+288h]
0x140017dea  lea     rdx, unk_14004CFB8
0x140017df1  xor     r8d, r8d
0x140017df4  mov     [rsp+238h+var_15C], r9d
0x140017dfc  mov     [rsp+238h+var_200], rax
0x140017e01  lea     rax, [rsp+238h+var_200]
0x140017e06  mov     [rsp+238h+var_158], rax
0x140017e0e  lea     rax, [rsp+238h+var_1E8]
0x140017e13  mov     [rsp+238h+var_210], rax
0x140017e18  mov     [rsp+238h+var_1A0], 4
0x140017e24  mov     [rsp+238h+var_208], ebx
0x140017e28  mov     [rsp+238h+var_190], 4
0x140017e34  mov     [rsp+238h+var_180], 10h
0x140017e40  mov     [rsp+238h+var_170], 2
0x140017e4c  mov     [rsp+238h+var_150], 8
0x140017e58  mov     [rsp+238h+var_218], 0Ah
0x140017e60  lea     rcx, dword_140065110
0x140017e67  call    _tlgWriteTransfer_EtwWriteTransfer
0x140017e6c  jmp     loc_14001820A
0x140017e71  mov     [r15+58h], r9
0x140017e75  mov     [r15+50h], rbx
0x140017e79  mov     rsi, r9
0x140017e7c  cmp     rsi, r12
0x140017e7f  jnb     loc_140018207
0x140017e85  mov     rax, r12
0x140017e88  sub     rax, rsi
0x140017e8b  mov     edi, 10h
0x140017e90  cmp     rax, rdi
0x140017e93  cmovb   rdi, rax
0x140017e97  mov     r8, rdi
0x140017e9a  shl     r8, 4
0x140017e9e  test    r8, r8
0x140017ea1  jz      short loc_140017EB5
0x140017ea3  test    r13b, 7
0x140017ea7  jz      short loc_140017EB5
0x140017ea9  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140017eb0  nop     dword ptr [rax+rax+00h]
0x140017eb5  mov     rdx, rsi
0x140017eb8  shl     rdx, 4
0x140017ebc  add     rdx, r13; Src
0x140017ebf  lea     rcx, [rsp+238h+var_148]; void *
0x140017ec7  call    RtlCopyFromUser
0x140017ecc  nop
0x140017ecd  xor     r14d, r14d
0x140017ed0  test    rdi, rdi
0x140017ed3  jz      short loc_140017F0A
0x140017ed5  mov     rdx, r14
0x140017ed8  add     rdx, rdx
0x140017edb  mov     r8, [rsp+rdx*8+238h+var_140]
0x140017ee3  mov     rdx, [rsp+rdx*8+238h+var_148]
0x140017eeb  mov     rcx, [rsp+238h+var_1F8]
0x140017ef0  call    VsmmGpaRangeValidatePageRange
0x140017ef5  mov     ebx, eax
0x140017ef7  xor     r8d, r8d
0x140017efa  test    eax, eax
0x140017efc  js      loc_140017FEA
0x140017f02  inc     r14
0x140017f05  cmp     r14, rdi
0x140017f08  jb      short loc_140017ED5
0x140017f0a  mov     r8, rdi
0x140017f0d  lea     rdx, [rsp+238h+var_148]
0x140017f15  mov     rcx, r15
0x140017f18  call    VsmmMemXferpBatchedWriteAddRanges
0x140017f1d  mov     ebx, eax
0x140017f1f  xor     r9d, r9d
0x140017f22  test    eax, eax
0x140017f24  jns     loc_1400180B5
0x140017f2a  mov     eax, cs:dword_140065110
0x140017f30  cmp     eax, 2
0x140017f33  jbe     loc_14001820A
0x140017f39  mov     edx, 100h
0x140017f3e  lea     rcx, dword_140065110
0x140017f45  call    _tlgKeywordOn
0x140017f4a  test    al, al
0x140017f4c  jz      loc_14001820A
0x140017f52  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140017f59  lea     rcx, [rsp+238h+var_1C8]
0x140017f5e  call    _tlgCreate1Sz_char
0x140017f63  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017f6a  lea     rcx, [rsp+238h+var_1B8]
0x140017f72  call    _tlgCreate1Sz_char
0x140017f77  mov     [rsp+238h+var_204], 0B35h
0x140017f7f  lea     rax, [rsp+238h+var_204]
0x140017f84  mov     [rsp+238h+var_1A8], rax
0x140017f8c  lea     rcx, [rsp+238h+var_208]
0x140017f91  mov     [rsp+238h+var_198], rcx
0x140017f99  mov     rcx, [rsp+238h+var_1F8]
0x140017f9e  lea     rax, [rcx+290h]
0x140017fa5  mov     [rsp+238h+var_188], rax
0x140017fad  lea     rax, [rsp+238h+var_160]
0x140017fb5  mov     [rsp+238h+var_178], rax
0x140017fbd  mov     rax, [rcx+80h]
0x140017fc4  mov     [rsp+238h+var_168], rax
0x140017fcc  movzx   eax, word ptr [rcx+78h]
0x140017fd0  mov     [rsp+238h+var_160], eax
0x140017fd7  mov     rax, [rcx+288h]
0x140017fde  lea     rdx, unk_14004CEDC
0x140017fe5  jmp     loc_140017DF1
0x140017fea  mov     eax, cs:dword_140065110
0x140017ff0  cmp     eax, 2
0x140017ff3  jbe     loc_14001820A
0x140017ff9  mov     edx, 100h
0x140017ffe  lea     rcx, dword_140065110
0x140018005  call    _tlgKeywordOn
0x14001800a  test    al, al
0x14001800c  jz      loc_14001820A
0x140018012  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140018019  lea     rcx, [rsp+238h+var_1C8]
0x14001801e  call    _tlgCreate1Sz_char
0x140018023  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x14001802a  lea     rcx, [rsp+238h+var_1B8]
0x140018032  call    _tlgCreate1Sz_char
0x140018037  mov     [rsp+238h+var_204], 0B26h
0x14001803f  lea     rax, [rsp+238h+var_204]
0x140018044  mov     [rsp+238h+var_1A8], rax
0x14001804c  lea     rcx, [rsp+238h+var_208]
0x140018051  mov     [rsp+238h+var_198], rcx
0x140018059  mov     rcx, [rsp+238h+var_1F8]
0x14001805e  lea     rax, [rcx+290h]
0x140018065  mov     [rsp+238h+var_188], rax
0x14001806d  lea     rax, [rsp+238h+var_160]
0x140018075  mov     [rsp+238h+var_178], rax
0x14001807d  mov     rax, [rcx+80h]
0x140018084  mov     [rsp+238h+var_168], rax
0x14001808c  movzx   eax, word ptr [rcx+78h]
0x140018090  mov     [rsp+238h+var_160], eax
0x140018097  mov     [rsp+238h+var_15C], r8d
0x14001809f  mov     rax, [rcx+288h]
0x1400180a6  xor     r9d, r9d
0x1400180a9  lea     rdx, unk_14004CE6E
0x1400180b0  jmp     loc_140017DFC
0x1400180b5  add     rsi, rdi
0x1400180b8  jmp     loc_140017E7C
0x1400180bd  mov     ebx, eax
0x1400180bf  mov     eax, cs:dword_140065110
0x1400180c5  cmp     eax, 2
0x1400180c8  jbe     loc_140018205
0x1400180ce  mov     edx, 100h
0x1400180d3  lea     rcx, dword_140065110
0x1400180da  call    _tlgKeywordOn
0x1400180df  test    al, al
0x1400180e1  jz      loc_140018205
  ... truncated ...
```
