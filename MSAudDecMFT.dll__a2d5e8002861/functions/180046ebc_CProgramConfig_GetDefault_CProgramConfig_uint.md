# CProgramConfig_GetDefault(CProgramConfig *,uint)

- ea: `0x180046ebc`
- end: `0x1800471a3`
- name: `?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z`
- size: `743`
- prototype: `void __fastcall(struct CProgramConfig *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800069ec`
- `0x180012bf8`
- `0x180048018`
- `0x1800710ac`

## callees

- `0x180046ebc`
- `0x18004dd14`

## pseudocode

```c
void __fastcall CProgramConfig_GetDefault(struct CProgramConfig *a1, unsigned int a2)
{
  char v4; // cl
  char v5; // dl
  char v6; // r9
  char v7; // r8
  char v8; // cl
  char v9; // al
  char v10; // cl
  char v11; // al
  char v12; // r8
  char v13; // al
  char v14; // cl
  char v15; // r8
  char v16; // al
  char v17; // cl
  int v18; // r9d
  int v19; // r10d
  int v20; // esi
  int v21; // edi
  char v22; // cl
  int v23; // r11d
  char v24; // dl
  int v25; // esi
  int v26; // edi
  char v27; // cl
  int v28; // r11d
  char v29; // dl
  int v30; // r11d
  __int64 v31; // rdx
  char v32; // cl
  char v33; // r8
  int v34; // eax
  int v35; // edx
  __int64 v36; // rax
  char v37; // cl

  memset_0(a1, 0, 0x1D1u);
  *(_WORD *)((char *)a1 + 1) = 3841;
  if ( a2 > 0x15 )
  {
    if ( a2 == 32 )
    {
      *(_DWORD *)((char *)a1 + 3) = 16843010;
      v4 = 7;
      *((_WORD *)a1 + 8) = 256;
      v5 = 8;
      *((_BYTE *)a1 + 64) = 1;
      *((_BYTE *)a1 + 112) = 1;
      goto LABEL_36;
    }
    if ( a2 == 30 )
    {
      *(_WORD *)((char *)a1 + 3) = 1;
      *((_BYTE *)a1 + 16) = 1;
      v4 = 3;
      *((_BYTE *)a1 + 5) = 1;
      v5 = 3;
      *((_BYTE *)a1 + 112) = 0;
      goto LABEL_36;
    }
    goto LABEL_33;
  }
  v4 = 4;
  if ( a2 == 21 )
  {
    *(_WORD *)((char *)a1 + 3) = 1;
    v5 = 4;
    *((_BYTE *)a1 + 16) = 1;
    *((_BYTE *)a1 + 5) = 1;
    *((_BYTE *)a1 + 112) = 1;
    goto LABEL_36;
  }
  v5 = 2;
  if ( a2 > 6 )
  {
    if ( a2 != 7 )
    {
      switch ( a2 )
      {
        case 0xBu:
          v15 = 0;
          v17 = 0;
          v16 = 0;
          break;
        case 0xCu:
          v15 = 1;
          v16 = 1;
          v17 = 1;
          break;
        case 0xEu:
          *((_BYTE *)a1 + 50) = 1;
          goto LABEL_22;
        case 0x10u:
          *(_WORD *)((char *)a1 + 3) = 2;
          *((_WORD *)a1 + 8) = 0;
          *((_BYTE *)a1 + 5) = 0;
          goto LABEL_12;
        default:
          goto LABEL_33;
      }
      *((_BYTE *)a1 + 3) = 2;
      v4 = v17 + 6;
      *((_WORD *)a1 + 8) = 256;
      v5 = v16 + 7;
      *(_WORD *)((char *)a1 + 5) = 258;
      *((_BYTE *)a1 + 112) = 1;
      *((_BYTE *)a1 + 113) = v15;
      goto LABEL_36;
    }
LABEL_22:
    *((_BYTE *)a1 + 18) = 1;
    v6 = 2;
    *((_BYTE *)a1 + 462) = 2;
    v7 = 1;
    v13 = 3;
    goto LABEL_23;
  }
  if ( a2 == 6 )
  {
    v6 = 0;
    v7 = 0;
    v13 = 1;
LABEL_23:
    *((_BYTE *)a1 + 6) = 1;
    *((_BYTE *)a1 + 462) = v13;
    goto LABEL_24;
  }
  if ( a2 == 1 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
LABEL_26:
    v5 = v11 + 1;
    *((_BYTE *)a1 + 3) = v12 + 1;
    v4 = v10 + 1;
    *((_BYTE *)a1 + 16) = 0;
    goto LABEL_36;
  }
  if ( a2 != 2 )
  {
    if ( a2 == 3 )
    {
      v7 = 0;
      v8 = 0;
      v9 = 0;
LABEL_25:
      v12 = v7 + 1;
      v11 = v9 + 2;
      *((_BYTE *)a1 + 3) = v12;
      v10 = v8 + 2;
      *((_BYTE *)a1 + 17) = 1;
      *((_BYTE *)a1 + 462) = v11;
      *((_BYTE *)a1 + 463) = v10;
      goto LABEL_26;
    }
    if ( a2 - 4 <= 1 )
    {
      v6 = 0;
      v7 = 0;
LABEL_24:
      *((_BYTE *)a1 + 5) = 1;
      v14 = (a2 > 4) + 1;
      *((_BYTE *)a1 + 112) = a2 > 4;
      v9 = *((_BYTE *)a1 + 462) + v14;
      v8 = v6 + v14;
      goto LABEL_25;
    }
LABEL_33:
    *((_BYTE *)a1 + 461) = 0;
    return;
  }
  *((_BYTE *)a1 + 3) = 1;
  *((_BYTE *)a1 + 16) = 1;
LABEL_12:
  v4 = 2;
LABEL_36:
  *((_BYTE *)a1 + 461) = 1;
  v18 = 0;
  *((_BYTE *)a1 + 462) = v5;
  v19 = 0;
  *((_BYTE *)a1 + 463) = v4;
  v20 = 0;
  if ( *((_BYTE *)a1 + 3) )
  {
    do
    {
      v21 = v18;
      v22 = v19;
      v23 = v19 + 1;
      v24 = *((_BYTE *)a1 + v20 + 16);
      if ( !v24 )
      {
        v21 = v18 + 1;
        v23 = v19;
      }
      v19 = v23;
      if ( !v24 )
        v22 = v18;
      v18 = v21;
      *((_BYTE *)a1 + v20++ + 32) = v22;
    }
    while ( v20 < *((unsigned __int8 *)a1 + 3) );
  }
  v25 = 0;
  if ( *((_BYTE *)a1 + 4) )
  {
    do
    {
      v26 = v18;
      v27 = v19;
      v28 = v19 + 1;
      v29 = *((_BYTE *)a1 + v25 + 64);
      if ( !v29 )
      {
        v26 = v18 + 1;
        v28 = v19;
      }
      v19 = v28;
      if ( !v29 )
        v27 = v18;
      v18 = v26;
      *((_BYTE *)a1 + v25++ + 80) = v27;
    }
    while ( v25 < *((unsigned __int8 *)a1 + 4) );
  }
  v30 = 0;
  if ( *((_BYTE *)a1 + 5) )
  {
    do
    {
      v31 = v30;
      v32 = v19;
      v33 = *((_BYTE *)a1 + v30 + 112);
      if ( !v33 )
        v32 = v18;
      ++v30;
      *((_BYTE *)a1 + v31 + 128) = v32;
      if ( !v33 )
        LOBYTE(v18) = v18 + 1;
      v34 = v19 + 1;
      if ( !v33 )
        v34 = v19;
      v19 = v34;
    }
    while ( v30 < *((unsigned __int8 *)a1 + 5) );
  }
  v35 = 0;
  if ( *((_BYTE *)a1 + 6) )
  {
    do
    {
      v36 = v35;
      v37 = v35++;
      *((_BYTE *)a1 + v36 + 160) = v37;
    }
    while ( v35 < *((unsigned __int8 *)a1 + 6) );
  }
}

```

## disassembly

```asm
0x180046ebc  push    rbx
0x180046ebe  push    rsi
0x180046ebf  push    rdi
0x180046ec0  push    r14
0x180046ec2  sub     rsp, 28h
0x180046ec6  mov     edi, edx
0x180046ec8  mov     r8d, 1D1h; Size
0x180046ece  xor     edx, edx; Val
0x180046ed0  mov     rbx, rcx
0x180046ed3  call    memset_0
0x180046ed8  xor     r14d, r14d
0x180046edb  mov     word ptr [rbx+1], 0F01h
0x180046ee1  cmp     edi, 15h
0x180046ee4  ja      loc_180047045
0x180046eea  lea     ecx, [r14+4]
0x180046eee  jz      loc_18004702F
0x180046ef4  lea     edx, [rcx-2]
0x180046ef7  cmp     edi, 6
0x180046efa  ja      short loc_180046F5D
0x180046efc  jz      short loc_180046F53
0x180046efe  mov     eax, edi
0x180046f00  sub     eax, 1
0x180046f03  jz      short loc_180046F45
0x180046f05  sub     eax, 1
0x180046f08  jz      short loc_180046F36
0x180046f0a  sub     eax, 1
0x180046f0d  jz      short loc_180046F28
0x180046f0f  sub     eax, 1
0x180046f12  jz      short loc_180046F1D
0x180046f14  cmp     eax, 1
0x180046f17  jnz     loc_18004704F
0x180046f1d  mov     r9b, r14b
0x180046f20  mov     r8b, r14b
0x180046f23  jmp     loc_180046FB0
0x180046f28  mov     r8b, r14b
0x180046f2b  mov     cl, r14b
0x180046f2e  mov     al, r14b
0x180046f31  jmp     loc_180046FCC
0x180046f36  mov     byte ptr [rbx+3], 1
0x180046f3a  mov     byte ptr [rbx+10h], 1
0x180046f3e  mov     cl, dl
0x180046f40  jmp     loc_18004708E
0x180046f45  mov     cl, r14b
0x180046f48  mov     al, r14b
0x180046f4b  mov     r8b, r14b
0x180046f4e  jmp     loc_180046FE7
0x180046f53  mov     r9b, r14b
0x180046f56  mov     r8b, r14b
0x180046f59  mov     al, 1
0x180046f5b  jmp     short loc_180046FA6
0x180046f5d  mov     eax, edi
0x180046f5f  sub     eax, 7
0x180046f62  jz      short loc_180046F94
0x180046f64  sub     eax, ecx
0x180046f66  jz      loc_180047007
0x180046f6c  sub     eax, 1
0x180046f6f  jz      loc_180046FFC
0x180046f75  sub     eax, edx
0x180046f77  jz      short loc_180046F90
0x180046f79  cmp     eax, edx
0x180046f7b  jnz     loc_18004704F
0x180046f81  mov     [rbx+3], dx
0x180046f85  mov     [rbx+10h], r14w
0x180046f8a  mov     [rbx+5], r14b
0x180046f8e  jmp     short loc_180046F3E
0x180046f90  mov     byte ptr [rbx+32h], 1
0x180046f94  mov     byte ptr [rbx+12h], 1
0x180046f98  mov     r9b, dl
0x180046f9b  mov     [rbx+1CEh], dl
0x180046fa1  mov     r8b, 1
0x180046fa4  mov     al, 3
0x180046fa6  mov     byte ptr [rbx+6], 1
0x180046faa  mov     [rbx+1CEh], al
0x180046fb0  cmp     edi, ecx
0x180046fb2  mov     byte ptr [rbx+5], 1
0x180046fb6  setnbe  al
0x180046fb9  setnbe  cl
0x180046fbc  inc     cl
0x180046fbe  mov     [rbx+70h], al
0x180046fc1  mov     al, cl
0x180046fc3  add     al, [rbx+1CEh]
0x180046fc9  add     cl, r9b
0x180046fcc  inc     r8b
0x180046fcf  add     al, dl
0x180046fd1  mov     [rbx+3], r8b
0x180046fd5  add     cl, dl
0x180046fd7  mov     byte ptr [rbx+11h], 1
0x180046fdb  mov     [rbx+1CEh], al
0x180046fe1  mov     [rbx+1CFh], cl
0x180046fe7  inc     r8b
0x180046fea  lea     edx, [rax+1]
0x180046fed  mov     [rbx+3], r8b
0x180046ff1  inc     cl
0x180046ff3  mov     [rbx+10h], r14b
0x180046ff7  jmp     loc_18004708E
0x180046ffc  mov     r8b, 1
0x180046fff  mov     al, r8b
0x180047002  mov     cl, r8b
0x180047005  jmp     short loc_180047010
0x180047007  mov     r8b, r14b
0x18004700a  mov     cl, r14b
0x18004700d  mov     al, r14b
0x180047010  mov     [rbx+3], dl
0x180047013  add     cl, 6
0x180047016  mov     word ptr [rbx+10h], 100h
0x18004701c  lea     edx, [rax+7]
0x18004701f  mov     word ptr [rbx+5], 102h
0x180047025  mov     byte ptr [rbx+70h], 1
0x180047029  mov     [rbx+71h], r8b
0x18004702d  jmp     short loc_18004708E
0x18004702f  mov     word ptr [rbx+3], 1
0x180047035  mov     dl, cl
0x180047037  mov     byte ptr [rbx+10h], 1
0x18004703b  mov     byte ptr [rbx+5], 1
0x18004703f  mov     byte ptr [rbx+70h], 1
0x180047043  jmp     short loc_18004708E
0x180047045  cmp     edi, 20h ; ' '
0x180047048  jz      short loc_18004705B
0x18004704a  cmp     edi, 1Eh
0x18004704d  jz      short loc_180047076
0x18004704f  mov     [rbx+1CDh], r14b
0x180047056  jmp     loc_180047198
0x18004705b  mov     dword ptr [rbx+3], 1010102h
0x180047062  mov     cl, 7
0x180047064  mov     word ptr [rbx+10h], 100h
0x18004706a  mov     dl, 8
0x18004706c  mov     byte ptr [rbx+40h], 1
0x180047070  mov     byte ptr [rbx+70h], 1
0x180047074  jmp     short loc_18004708E
0x180047076  mov     word ptr [rbx+3], 1
0x18004707c  mov     al, 3
0x18004707e  mov     byte ptr [rbx+10h], 1
0x180047082  mov     cl, al
0x180047084  mov     byte ptr [rbx+5], 1
0x180047088  mov     dl, al
0x18004708a  mov     [rbx+70h], r14b
0x18004708e  mov     byte ptr [rbx+1CDh], 1
0x180047095  mov     r9d, r14d
0x180047098  mov     [rbx+1CEh], dl
0x18004709e  mov     r10d, r14d
0x1800470a1  mov     [rbx+1CFh], cl
0x1800470a7  mov     esi, r14d
0x1800470aa  cmp     [rbx+3], r14b
0x1800470ae  jbe     short loc_1800470EC
0x1800470b0  movsxd  r8, esi
0x1800470b3  lea     eax, [r9+1]
0x1800470b7  mov     edi, r9d
0x1800470ba  movzx   ecx, r10b
0x1800470be  lea     r11d, [r10+1]
0x1800470c2  mov     dl, [r8+rbx+10h]
0x1800470c7  test    dl, dl
0x1800470c9  cmovz   edi, eax
0x1800470cc  cmovz   r11d, r10d
0x1800470d0  movzx   eax, r9b
0x1800470d4  mov     r10d, r11d
0x1800470d7  cmovz   ecx, eax
0x1800470da  mov     r9d, edi
0x1800470dd  mov     [r8+rbx+20h], cl
0x1800470e2  inc     esi
0x1800470e4  movzx   eax, byte ptr [rbx+3]
0x1800470e8  cmp     esi, eax
0x1800470ea  jl      short loc_1800470B0
0x1800470ec  mov     esi, r14d
0x1800470ef  cmp     [rbx+4], r14b
0x1800470f3  jbe     short loc_180047131
0x1800470f5  movsxd  r8, esi
0x1800470f8  lea     eax, [r9+1]
0x1800470fc  mov     edi, r9d
0x1800470ff  movzx   ecx, r10b
0x180047103  lea     r11d, [r10+1]
0x180047107  mov     dl, [r8+rbx+40h]
0x18004710c  test    dl, dl
0x18004710e  cmovz   edi, eax
0x180047111  cmovz   r11d, r10d
0x180047115  movzx   eax, r9b
0x180047119  mov     r10d, r11d
0x18004711c  cmovz   ecx, eax
0x18004711f  mov     r9d, edi
0x180047122  mov     [r8+rbx+50h], cl
0x180047127  inc     esi
0x180047129  movzx   eax, byte ptr [rbx+4]
0x18004712d  cmp     esi, eax
0x18004712f  jl      short loc_1800470F5
0x180047131  mov     r11d, r14d
0x180047134  cmp     [rbx+5], r14b
0x180047138  jbe     short loc_180047179
0x18004713a  movsxd  rdx, r11d
0x18004713d  movzx   eax, r9b
0x180047141  movzx   ecx, r10b
0x180047145  mov     r8b, [rdx+rbx+70h]
0x18004714a  test    r8b, r8b
0x18004714d  cmovz   ecx, eax
0x180047150  inc     r11d
0x180047153  test    r8b, r8b
0x180047156  mov     [rdx+rbx+80h], cl
0x18004715d  lea     eax, [r9+1]
0x180047161  cmovz   r9d, eax
0x180047165  lea     eax, [r10+1]
0x180047169  cmovz   eax, r10d
0x18004716d  mov     r10d, eax
0x180047170  movzx   eax, byte ptr [rbx+5]
0x180047174  cmp     r11d, eax
0x180047177  jl      short loc_18004713A
0x180047179  mov     edx, r14d
0x18004717c  cmp     [rbx+6], r14b
0x180047180  jbe     short loc_180047198
0x180047182  movsxd  rax, edx
0x180047185  mov     cl, dl
0x180047187  inc     edx
0x180047189  mov     [rax+rbx+0A0h], cl
0x180047190  movzx   eax, byte ptr [rbx+6]
0x180047194  cmp     edx, eax
0x180047196  jl      short loc_180047182
0x180047198  add     rsp, 28h
0x18004719c  pop     r14
0x18004719e  pop     rdi
0x18004719f  pop     rsi
0x1800471a0  pop     rbx
0x1800471a1  retn
```
