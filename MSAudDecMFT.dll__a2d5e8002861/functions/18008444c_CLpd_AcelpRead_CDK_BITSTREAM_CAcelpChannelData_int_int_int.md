# CLpd_AcelpRead(CDK_BITSTREAM *,CAcelpChannelData *,int,int,int)

- ea: `0x18008444c`
- end: `0x1800847dd`
- name: `?CLpd_AcelpRead@@YAHPEAUCDK_BITSTREAM@@PEAUCAcelpChannelData@@HHH@Z`
- size: `913`
- prototype: `__int64 __fastcall(struct CDK_BITSTREAM *, struct CAcelpChannelData *, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180044774`

## callees

- `0x1800110c0`
- `0x180013550`
- `0x180081b60`
- `0x18008444c`
- `0x180084d24`

## pseudocode

```c
__int64 __fastcall CLpd_AcelpRead(struct CDK_BITSTREAM *a1, struct CAcelpChannelData *a2, int a3, int a4, int a5)
{
  int *v6; // r13
  int v9; // ecx
  unsigned int v10; // r15d
  char v11; // bp
  unsigned int v12; // r12d
  int v13; // edx
  unsigned int v14; // ebx
  char *v15; // r13
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 v22; // r8
  __int64 v23; // r8
  __int16 v24; // ax
  __int64 v25; // r8
  __int64 v26; // rdx
  __int16 v27; // ax
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int16 v31; // ax
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r8
  int v37; // [rsp+20h] [rbp-98h]
  int v38; // [rsp+50h] [rbp-68h] BYREF
  int v39; // [rsp+54h] [rbp-64h] BYREF
  int v40; // [rsp+58h] [rbp-60h]
  int v41; // [rsp+5Ch] [rbp-5Ch]
  int v42; // [rsp+60h] [rbp-58h]
  int v43; // [rsp+64h] [rbp-54h]
  int *v44; // [rsp+68h] [rbp-50h]
  int v45; // [rsp+D8h] [rbp+20h] BYREF

  v6 = (int *)byte_1800C2960;
  if ( (unsigned int)(a4 - 1024) >= 0x100 )
    v6 = &dword_1800C2964;
  v9 = a5;
  v44 = v6;
  a5 = 0;
  v45 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 6 * v9 + 231;
  if ( v40 <= 411 )
  {
    *(_BYTE *)a2 = a3;
    v42 = v9 + 34;
    v10 = 0;
    v41 = 128 - v9;
    v11 = *((_BYTE *)&qword_1800C2968 + a3);
    *((_BYTE *)a2 + 1) = CDKread2Bits_0(a1);
    v12 = 0;
    v13 = a4 % 256;
    v43 = a4 / 256;
    if ( a4 / 256 <= 0 )
      return v10;
    v14 = 5;
    while ( 1 )
    {
      LOBYTE(v13) = *((_BYTE *)v6 + v12);
      v10 = DecodePitchLag(
              (_DWORD)a1,
              v13,
              v42,
              v41,
              v37,
              v40,
              (__int64)&a5,
              (__int64)&v45,
              (__int64)&v39,
              (__int64)&v38);
      if ( v10 )
        return v10;
      v15 = (char *)a2 + v12;
      *((_WORD *)a2 + v12 + 1) = a5;
      v15[10] = v45;
      v15[14] = CDKreadBit((__int64)a1);
      switch ( v11 )
      {
        case 12:
          v21 = 2LL * v12;
          *((_WORD *)a2 + 4 * v21 + 9) = CDKreadBit((__int64)a1);
          *((_WORD *)a2 + 4 * v21 + 10) = CDKreadBits(a1, v14, v35);
          v24 = CDKreadBit((__int64)a1);
          goto LABEL_27;
        case 16:
          v21 = 2LL * v12;
          v31 = CDKreadBit((__int64)a1);
          goto LABEL_24;
        case 20:
          v21 = 2LL * v12;
          v31 = CDKreadBits(a1, v14, v16);
LABEL_24:
          v33 = v14;
LABEL_22:
          *((_WORD *)a2 + 4 * v21 + 9) = v31;
          *((_WORD *)a2 + 4 * v21 + 10) = CDKreadBits(a1, v33, v32);
          v24 = CDKreadBits(a1, v14, v34);
LABEL_27:
          v26 = v14;
          goto LABEL_28;
        case 28:
          v21 = 2LL * v12;
          v31 = CDKreadBits(a1, 9, v16);
          v33 = 9;
          goto LABEL_22;
      }
      if ( v11 == 36 )
        break;
      if ( v11 == 44 )
      {
        v21 = 2LL * v12;
        v27 = CDKreadBits(a1, 13, v16);
        v29 = 13;
LABEL_19:
        *((_WORD *)a2 + 4 * v21 + 9) = v27;
        *((_WORD *)a2 + 4 * v21 + 10) = CDKreadBits(a1, v29, v28);
        v24 = CDKreadBits(a1, 9, v30);
        v26 = 9;
        goto LABEL_28;
      }
      if ( v11 != 52 )
      {
        if ( v11 == 64 )
        {
          *((_WORD *)a2 + 8 * v12 + 9) = CDKread2Bits_0(a1);
          *((_WORD *)a2 + 8 * v12 + 10) = CDKread2Bits_0(a1);
          *((_WORD *)a2 + 8 * v12 + 11) = CDKread2Bits_0(a1);
          *((_WORD *)a2 + 8 * v12 + 12) = CDKread2Bits_0(a1);
          *((_WORD *)a2 + 8 * v12 + 13) = CDKreadBits(a1, v10 + 14, v17);
          *((_WORD *)a2 + 8 * v12 + 14) = CDKreadBits(a1, v10 + 14, v18);
          *((_WORD *)a2 + 8 * v12 + 15) = CDKreadBits(a1, v10 + 14, v19);
          v14 = v10 + 5;
          *((_WORD *)a2 + 8 * v12 + 16) = CDKreadBits(a1, v10 + 14, v20);
        }
        goto LABEL_29;
      }
      v21 = 2LL * v12;
      *((_WORD *)a2 + 4 * v21 + 9) = CDKreadBits(a1, 13, v16);
      *((_WORD *)a2 + 4 * v21 + 10) = CDKreadBits(a1, 13, v22);
      v24 = CDKreadBits(a1, 13, v23);
      v26 = 13;
LABEL_28:
      *((_WORD *)a2 + 4 * v21 + 11) = v24;
      *((_WORD *)a2 + 4 * v21 + 12) = CDKreadBits(a1, v26, v25);
LABEL_29:
      ++v12;
      v15[82] = CDKreadBits(a1, 7, v16);
      v6 = v44;
      if ( (int)v12 >= v43 )
        return v10;
    }
    v21 = 2LL * v12;
    v27 = CDKreadBits(a1, 9, v16);
    v29 = 9;
    goto LABEL_19;
  }
  return 16388;
}

```

## disassembly

```asm
0x18008444c  mov     r11, rsp
0x18008444f  push    rbx
0x180084450  push    rbp
0x180084451  push    rsi
0x180084452  push    rdi
0x180084453  push    r12
0x180084455  push    r13
0x180084457  push    r14
0x180084459  push    r15
0x18008445b  sub     rsp, 78h
0x18008445f  lea     eax, [r9-400h]
0x180084466  mov     rsi, rcx
0x180084469  cmp     eax, 100h
0x18008446e  lea     rcx, dword_1800C2964
0x180084475  lea     r13, byte_1800C2960
0x18008447c  mov     ebx, r9d
0x18008447f  cmovnb  r13, rcx
0x180084483  mov     r14, rdx
0x180084486  mov     ecx, [rsp+0B8h+arg_20]
0x18008448d  xor     edi, edi
0x18008448f  mov     [rsp+0B8h+var_50], r13
0x180084494  mov     [r11+28h], edi
0x180084498  mov     [r11+20h], edi
0x18008449c  lea     eax, [rcx+rcx*2]
0x18008449f  mov     [rsp+0B8h+var_64], edi
0x1800844a3  lea     eax, ds:0E7h[rax*2]
0x1800844aa  mov     [rsp+0B8h+var_68], edi
0x1800844ae  mov     [rsp+0B8h+var_60], eax
0x1800844b2  cmp     eax, 19Bh
0x1800844b7  jle     short loc_1800844C4
0x1800844b9  mov     r15d, 4004h
0x1800844bf  jmp     loc_1800847C8
0x1800844c4  lea     eax, [rcx+22h]
0x1800844c7  mov     [rdx], r8b
0x1800844ca  mov     [rsp+0B8h+var_58], eax
0x1800844ce  lea     rbp, qword_1800C2968
0x1800844d5  mov     eax, 80h
0x1800844da  mov     r15d, edi
0x1800844dd  sub     eax, ecx
0x1800844df  mov     rcx, rsi
0x1800844e2  mov     [rsp+0B8h+var_5C], eax
0x1800844e6  movsxd  rax, r8d
0x1800844e9  mov     bpl, [rax+rbp]
0x1800844ed  call    CDKread2Bits_0
0x1800844f2  mov     [r14+1], al
0x1800844f6  mov     ecx, 100h
0x1800844fb  mov     eax, ebx
0x1800844fd  mov     r12d, edi
0x180084500  cdq
0x180084501  idiv    ecx
0x180084503  mov     [rsp+0B8h+var_54], eax
0x180084507  test    eax, eax
0x180084509  jle     loc_1800847C8
0x18008450f  mov     ebx, 5
0x180084514  mov     r9d, [rsp+0B8h+var_5C]
0x180084519  lea     rax, [rsp+0B8h+var_68]
0x18008451e  mov     r8d, [rsp+0B8h+var_58]
0x180084523  mov     rcx, rsi
0x180084526  mov     [rsp+0B8h+var_70], rax
0x18008452b  lea     rax, [rsp+0B8h+var_64]
0x180084530  mov     [rsp+0B8h+var_78], rax
0x180084535  lea     rax, [rsp+0B8h+arg_18]
0x18008453d  mov     [rsp+0B8h+var_80], rax
0x180084542  lea     rax, [rsp+0B8h+arg_20]
0x18008454a  mov     [rsp+0B8h+var_88], rax
0x18008454f  mov     eax, [rsp+0B8h+var_60]
0x180084553  mov     edi, r12d
0x180084556  mov     [rsp+0B8h+var_90], eax
0x18008455a  mov     dl, [rdi+r13]
0x18008455e  call    DecodePitchLag
0x180084563  mov     r15d, eax
0x180084566  test    eax, eax
0x180084568  jnz     loc_1800847C8
0x18008456e  movzx   ecx, word ptr [rsp+0B8h+arg_20]
0x180084576  lea     r13, [rdi+r14]
0x18008457a  mov     [r14+rdi*2+2], cx
0x180084580  mov     cl, byte ptr [rsp+0B8h+arg_18]
0x180084587  mov     [r13+0Ah], cl
0x18008458b  mov     rcx, rsi
0x18008458e  call    CDKreadBit
0x180084593  mov     [r13+0Eh], al
0x180084597  cmp     bpl, 0Ch
0x18008459b  jz      loc_180084765
0x1800845a1  cmp     bpl, 10h
0x1800845a5  jz      loc_180084758
0x1800845ab  cmp     bpl, 14h
0x1800845af  jz      loc_180084747
0x1800845b5  cmp     bpl, 1Ch
0x1800845b9  jz      loc_180084712
0x1800845bf  cmp     bpl, 24h ; '$'
0x1800845c3  jz      loc_1800846FB
0x1800845c9  cmp     bpl, 2Ch ; ','
0x1800845cd  jz      loc_1800846BB
0x1800845d3  cmp     bpl, 34h ; '4'
0x1800845d7  jz      loc_18008467B
0x1800845dd  cmp     bpl, 40h ; '@'
0x1800845e1  jnz     loc_1800847A4
0x1800845e7  mov     ebx, edi
0x1800845e9  mov     rcx, rsi
0x1800845ec  add     rbx, rbx
0x1800845ef  call    CDKread2Bits_0
0x1800845f4  mov     rcx, rsi
0x1800845f7  mov     [r14+rbx*8+12h], ax
0x1800845fd  call    CDKread2Bits_0
0x180084602  mov     rcx, rsi
0x180084605  mov     [r14+rbx*8+14h], ax
0x18008460b  call    CDKread2Bits_0
0x180084610  mov     rcx, rsi
0x180084613  mov     [r14+rbx*8+16h], ax
0x180084619  call    CDKread2Bits_0
0x18008461e  lea     edx, [r15+0Eh]
0x180084622  mov     [r14+rbx*8+18h], ax
0x180084628  mov     rcx, rsi
0x18008462b  call    CDKreadBits
0x180084630  lea     edx, [r15+0Eh]
0x180084634  mov     [r14+rbx*8+1Ah], ax
0x18008463a  mov     rcx, rsi
0x18008463d  call    CDKreadBits
0x180084642  lea     edx, [r15+0Eh]
0x180084646  mov     [r14+rbx*8+1Ch], ax
0x18008464c  mov     rcx, rsi
0x18008464f  call    CDKreadBits
0x180084654  lea     edx, [r15+0Eh]
0x180084658  mov     [r14+rbx*8+1Eh], ax
0x18008465e  mov     rcx, rsi
0x180084661  call    CDKreadBits
0x180084666  lea     rcx, [rdi+2]
0x18008466a  add     rcx, rcx
0x18008466d  lea     ebx, [r15+5]
0x180084671  mov     [r14+rcx*8], ax
0x180084676  jmp     loc_1800847A4
0x18008467b  mov     edx, 0Dh
0x180084680  mov     rcx, rsi
0x180084683  add     rdi, rdi
0x180084686  call    CDKreadBits
0x18008468b  mov     edx, 0Dh
0x180084690  mov     [r14+rdi*8+12h], ax
0x180084696  mov     rcx, rsi
0x180084699  call    CDKreadBits
0x18008469e  mov     edx, 0Dh
0x1800846a3  mov     [r14+rdi*8+14h], ax
0x1800846a9  mov     rcx, rsi
0x1800846ac  call    CDKreadBits
0x1800846b1  mov     edx, 0Dh
0x1800846b6  jmp     loc_180084790
0x1800846bb  add     rdi, rdi
0x1800846be  mov     edx, 0Dh
0x1800846c3  mov     rcx, rsi
0x1800846c6  call    CDKreadBits
0x1800846cb  mov     edx, 0Dh
0x1800846d0  mov     rcx, rsi
0x1800846d3  mov     [r14+rdi*8+12h], ax
0x1800846d9  call    CDKreadBits
0x1800846de  mov     edx, 9
0x1800846e3  mov     [r14+rdi*8+14h], ax
0x1800846e9  mov     rcx, rsi
0x1800846ec  call    CDKreadBits
0x1800846f1  mov     edx, 9
0x1800846f6  jmp     loc_180084790
0x1800846fb  add     rdi, rdi
0x1800846fe  mov     edx, 9
0x180084703  mov     rcx, rsi
0x180084706  call    CDKreadBits
0x18008470b  mov     edx, 9
0x180084710  jmp     short loc_1800846D0
0x180084712  add     rdi, rdi
0x180084715  mov     edx, 9
0x18008471a  mov     rcx, rsi
0x18008471d  call    CDKreadBits
0x180084722  mov     edx, 9
0x180084727  mov     rcx, rsi
0x18008472a  mov     [r14+rdi*8+12h], ax
0x180084730  call    CDKreadBits
0x180084735  mov     edx, ebx
0x180084737  mov     [r14+rdi*8+14h], ax
0x18008473d  mov     rcx, rsi
0x180084740  call    CDKreadBits
0x180084745  jmp     short loc_18008478E
0x180084747  add     rdi, rdi
0x18008474a  mov     edx, ebx
0x18008474c  mov     rcx, rsi
0x18008474f  call    CDKreadBits
0x180084754  mov     edx, ebx
0x180084756  jmp     short loc_180084727
0x180084758  add     rdi, rdi
0x18008475b  mov     rcx, rsi
0x18008475e  call    CDKreadBit
0x180084763  jmp     short loc_180084754
0x180084765  mov     rcx, rsi
0x180084768  add     rdi, rdi
0x18008476b  call    CDKreadBit
0x180084770  mov     edx, ebx
0x180084772  mov     [r14+rdi*8+12h], ax
0x180084778  mov     rcx, rsi
0x18008477b  call    CDKreadBits
0x180084780  mov     rcx, rsi
0x180084783  mov     [r14+rdi*8+14h], ax
0x180084789  call    CDKreadBit
0x18008478e  mov     edx, ebx
0x180084790  mov     rcx, rsi
0x180084793  mov     [r14+rdi*8+16h], ax
0x180084799  call    CDKreadBits
0x18008479e  mov     [r14+rdi*8+18h], ax
0x1800847a4  mov     edx, 7
0x1800847a9  mov     rcx, rsi
0x1800847ac  call    CDKreadBits
0x1800847b1  inc     r12d
0x1800847b4  mov     [r13+52h], al
0x1800847b8  mov     r13, [rsp+0B8h+var_50]
0x1800847bd  cmp     r12d, [rsp+0B8h+var_54]
0x1800847c2  jl      loc_180084514
0x1800847c8  mov     eax, r15d
0x1800847cb  add     rsp, 78h
0x1800847cf  pop     r15
0x1800847d1  pop     r14
0x1800847d3  pop     r13
0x1800847d5  pop     r12
0x1800847d7  pop     rdi
0x1800847d8  pop     rsi
0x1800847d9  pop     rbp
0x1800847da  pop     rbx
0x1800847db  retn
```
