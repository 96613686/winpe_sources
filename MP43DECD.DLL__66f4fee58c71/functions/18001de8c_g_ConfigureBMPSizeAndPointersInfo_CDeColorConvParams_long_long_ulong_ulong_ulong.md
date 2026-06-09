# g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,ulong,ulong,ulong)

- ea: `0x18001de8c`
- end: `0x18001e107`
- name: `?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJKKK@Z`
- size: `635`
- prototype: `void __fastcall(struct CDeColorConvParams *, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001e208`

## callees

- `0x18001de8c`

## pseudocode

```c
void __fastcall g_ConfigureBMPSizeAndPointersInfo(struct CDeColorConvParams *a1, int a2)
{
  int *v2; // r9
  int v5; // r11d
  int v6; // eax
  int v7; // ebx
  unsigned int v8; // r10d
  int v9; // r9d
  int v10; // eax
  unsigned int v11; // r10d
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  int v15; // eax
  unsigned int v16; // eax
  bool v17; // sf
  int v18; // r10d
  int v19; // r11d
  int v20; // ebp
  int v21; // edi
  int v22; // esi
  signed int v23; // kr04_4
  int v24; // r9d
  int v25; // ecx
  int v26; // r15d
  int v27; // r11d
  int v28; // eax
  int v29; // ebx
  int v30; // r11d
  int v31; // edx
  int v32; // eax
  int v33; // eax
  int v34; // r9d

  v2 = (int *)((char *)a1 + 8);
  if ( *((_DWORD *)a1 + 13) )
  {
    v5 = *((_DWORD *)a1 + 14);
    if ( v5 )
    {
      v6 = -*v2;
      if ( *v2 > 0 )
        v6 = *v2;
      *v2 = v6;
    }
    v7 = *v2;
    v8 = *((unsigned __int16 *)a1 + 7);
    v9 = *((_DWORD *)a1 + 1);
    v10 = v8 * v9;
    v11 = v8 >> 3;
    *((_DWORD *)a1 + 17) = v11;
    v12 = (int)((v10 + 31) & 0xFFFFFFE0) / 8;
    v13 = -v7;
    *((_DWORD *)a1 + 16) = v12;
    v14 = v12;
    if ( v7 > 0 )
      v13 = v7;
    *((_DWORD *)a1 + 18) = v12 * v13;
    if ( v7 > 0 && !v5 )
    {
      v14 = -v12;
      *((_DWORD *)a1 + 16) = -v12;
    }
    *((_DWORD *)a1 + 19) = 16 * v11;
    *((_DWORD *)a1 + 20) = 8 * v11;
    *((_DWORD *)a1 + 21) = 16 * v14;
    *((_DWORD *)a1 + 22) = 8 * (v14 - v11);
    if ( v5 || v7 < 0 )
    {
      v16 = 0;
    }
    else
    {
      v15 = -v7;
      if ( v7 > 0 )
        v15 = v7;
      v16 = ((v11 * v9 + 3) & 0xFFFFFFFC) * (v15 - 1);
    }
    *((_DWORD *)a1 + 26) = v16;
    *((_DWORD *)a1 + 27) = v16;
    *((_DWORD *)a1 + 28) = v16;
    *((_DWORD *)a1 + 29) = v16;
  }
  else
  {
    v17 = -*v2 < 0;
    v18 = -*v2;
    *((_DWORD *)a1 + 17) = 1;
    if ( v17 )
      v18 = *v2;
    *v2 = v18;
    v19 = v18;
    if ( v18 < 0 )
      v19 = -v18;
    v20 = *((_DWORD *)a1 + 1);
    v21 = 4;
    v22 = 8;
    v23 = (8 * v20 + 31) & 0xFFFFFFE0;
    *((_DWORD *)a1 + 16) = v23 / 8;
    v24 = v23 / 8;
    *((_DWORD *)a1 + 18) = v19 * (v23 / 8);
    v25 = *((_DWORD *)a1 + 4);
    if ( v25 == 961893977 )
    {
      v26 = 8;
      v27 = v23 / 32;
      v28 = 4;
      v29 = v18 * (v23 / 32) / 4;
    }
    else
    {
      v26 = 16;
      v27 = v23 / 16;
      v29 = v18 * (v23 / 16) / 2;
      v28 = 8;
    }
    *((_DWORD *)a1 + 38) = v27;
    *((_DWORD *)a1 + 39) = v28;
    if ( v25 != 961893977 )
      v21 = 8;
    v30 = v28 * v27;
    if ( v20 == a2 )
    {
      v31 = 16 * v24;
    }
    else
    {
      v31 = 32 * v24;
      v21 = v26;
    }
    v32 = 16;
    if ( v20 != a2 )
      v32 = 32;
    *((_DWORD *)a1 + 19) = v32;
    if ( v20 != a2 )
      v22 = 16;
    *((_DWORD *)a1 + 20) = v22;
    if ( v20 != a2 )
      v30 *= 2;
    *((_DWORD *)a1 + 40) = v21;
    *((_DWORD *)a1 + 21) = v31;
    *((_DWORD *)a1 + 41) = v30;
    *((_QWORD *)a1 + 13) = 0;
    *((_QWORD *)a1 + 14) = 0;
    if ( v25 == 961893977 || v25 == 842094169 )
    {
      v34 = v18 * v24;
      *((_DWORD *)a1 + 30) = v34;
      *((_DWORD *)a1 + 31) = v34;
      *((_DWORD *)a1 + 32) = v34;
      *((_DWORD *)a1 + 33) = v34;
      *((_DWORD *)a1 + 34) = v34 + v29;
      *((_DWORD *)a1 + 35) = v34;
      *((_DWORD *)a1 + 36) = v34;
      *((_DWORD *)a1 + 37) = v34;
    }
    else if ( v25 == 808596553 || v25 == 1448433993 )
    {
      v33 = v18 * v24 + v29;
      *((_DWORD *)a1 + 30) = v33;
      *((_DWORD *)a1 + 31) = v33;
      *((_DWORD *)a1 + 32) = v33;
      *((_DWORD *)a1 + 33) = v33;
    }
  }
}

```

## disassembly

```asm
0x18001de8c  push    rbx
0x18001de8e  push    rbp
0x18001de8f  push    rsi
0x18001de90  push    rdi
0x18001de91  push    r14
0x18001de93  push    r15
0x18001de95  cmp     dword ptr [rcx+34h], 0
0x18001de99  lea     r9, [rcx+8]
0x18001de9d  mov     r14d, edx
0x18001dea0  mov     r8, rcx
0x18001dea3  jz      loc_18001DF70
0x18001dea9  mov     r11d, [rcx+38h]
0x18001dead  test    r11d, r11d
0x18001deb0  jz      short loc_18001DEBE
0x18001deb2  mov     eax, [r9]
0x18001deb5  neg     eax
0x18001deb7  cmovs   eax, [r9]
0x18001debb  mov     [r9], eax
0x18001debe  movzx   ecx, word ptr [rcx+0Eh]
0x18001dec2  mov     ebx, [r9]
0x18001dec5  mov     r10d, ecx
0x18001dec8  mov     r9d, [r8+4]
0x18001decc  mov     eax, r9d
0x18001decf  imul    eax, ecx
0x18001ded2  mov     ecx, ebx
0x18001ded4  shr     r10d, 3
0x18001ded8  mov     [r8+44h], r10d
0x18001dedc  add     eax, 1Fh
0x18001dedf  and     eax, 0FFFFFFE0h
0x18001dee2  cdq
0x18001dee3  and     edx, 7
0x18001dee6  add     eax, edx
0x18001dee8  sar     eax, 3
0x18001deeb  neg     ecx
0x18001deed  mov     [r8+40h], eax
0x18001def1  mov     edx, eax
0x18001def3  cmovs   ecx, ebx
0x18001def6  imul    ecx, eax
0x18001def9  mov     [r8+48h], ecx
0x18001defd  test    ebx, ebx
0x18001deff  jle     short loc_18001DF0C
0x18001df01  test    r11d, r11d
0x18001df04  jnz     short loc_18001DF0C
0x18001df06  neg     edx
0x18001df08  mov     [r8+40h], edx
0x18001df0c  mov     eax, r10d
0x18001df0f  shl     eax, 4
0x18001df12  mov     [r8+4Ch], eax
0x18001df16  lea     eax, ds:0[r10*8]
0x18001df1e  mov     [r8+50h], eax
0x18001df22  mov     eax, edx
0x18001df24  sub     edx, r10d
0x18001df27  shl     eax, 4
0x18001df2a  shl     edx, 3
0x18001df2d  mov     [r8+54h], eax
0x18001df31  mov     [r8+58h], edx
0x18001df35  test    r11d, r11d
0x18001df38  jnz     short loc_18001DF59
0x18001df3a  test    ebx, ebx
0x18001df3c  js      short loc_18001DF59
0x18001df3e  mov     eax, ebx
0x18001df40  neg     eax
0x18001df42  cmovs   eax, ebx
0x18001df45  imul    r9d, r10d
0x18001df49  dec     eax
0x18001df4b  add     r9d, 3
0x18001df4f  and     r9d, 0FFFFFFFCh
0x18001df53  imul    eax, r9d
0x18001df57  jmp     short loc_18001DF5B
0x18001df59  xor     eax, eax
0x18001df5b  mov     [r8+68h], eax
0x18001df5f  mov     [r8+6Ch], eax
0x18001df63  mov     [r8+70h], eax
0x18001df67  mov     [r8+74h], eax
0x18001df6b  jmp     loc_18001E0FE
0x18001df70  mov     r10d, [r9]
0x18001df73  neg     r10d
0x18001df76  mov     dword ptr [rcx+44h], 1
0x18001df7d  cmovs   r10d, [r9]
0x18001df81  mov     [r9], r10d
0x18001df84  mov     r11d, r10d
0x18001df87  test    r10d, r10d
0x18001df8a  jns     short loc_18001DF8F
0x18001df8c  neg     r11d
0x18001df8f  mov     ebp, [rcx+4]
0x18001df92  mov     edi, 4
0x18001df97  lea     ebx, ds:1Fh[rbp*8]
0x18001df9e  and     ebx, 0FFFFFFE0h
0x18001dfa1  lea     esi, [rdi+4]
0x18001dfa4  mov     eax, ebx
0x18001dfa6  cdq
0x18001dfa7  and     edx, 7
0x18001dfaa  add     eax, edx
0x18001dfac  sar     eax, 3
0x18001dfaf  mov     ecx, eax
0x18001dfb1  mov     [r8+40h], eax
0x18001dfb5  imul    ecx, r11d
0x18001dfb9  mov     r9d, eax
0x18001dfbc  mov     eax, ebx
0x18001dfbe  cdq
0x18001dfbf  mov     [r8+48h], ecx
0x18001dfc3  mov     ecx, [r8+10h]
0x18001dfc7  cmp     ecx, 39555659h
0x18001dfcd  jnz     short loc_18001DFEF
0x18001dfcf  and     edx, 1Fh
0x18001dfd2  mov     r15d, esi
0x18001dfd5  add     eax, edx
0x18001dfd7  sar     eax, 5
0x18001dfda  mov     r11d, eax
0x18001dfdd  imul    eax, r10d
0x18001dfe1  cdq
0x18001dfe2  and     edx, 3
0x18001dfe5  lea     ebx, [rdx+rax]
0x18001dfe8  mov     eax, edi
0x18001dfea  sar     ebx, 2
0x18001dfed  jmp     short loc_18001E00D
0x18001dfef  and     edx, 0Fh
0x18001dff2  mov     r15d, 10h
0x18001dff8  add     eax, edx
0x18001dffa  sar     eax, 4
0x18001dffd  mov     r11d, eax
0x18001e000  imul    eax, r10d
0x18001e004  cdq
0x18001e005  sub     eax, edx
0x18001e007  sar     eax, 1
0x18001e009  mov     ebx, eax
0x18001e00b  mov     eax, esi
0x18001e00d  cmp     ecx, 39555659h
0x18001e013  mov     [r8+98h], r11d
0x18001e01a  mov     [r8+9Ch], eax
0x18001e021  mov     edx, r9d
0x18001e024  cmovnz  edi, esi
0x18001e027  imul    r11d, eax
0x18001e02b  cmp     ebp, r14d
0x18001e02e  jnz     short loc_18001E035
0x18001e030  shl     edx, 4
0x18001e033  jmp     short loc_18001E03B
0x18001e035  shl     edx, 5
0x18001e038  mov     edi, r15d
0x18001e03b  cmp     ebp, r14d
0x18001e03e  mov     eax, 10h
0x18001e043  lea     r15d, [rax+10h]
0x18001e047  cmovnz  eax, r15d
0x18001e04b  mov     [r8+4Ch], eax
0x18001e04f  lea     eax, [r15-10h]
0x18001e053  cmovnz  esi, eax
0x18001e056  lea     eax, [r11+r11]
0x18001e05a  mov     [r8+50h], esi
0x18001e05e  cmovnz  r11d, eax
0x18001e062  mov     [r8+0A0h], edi
0x18001e069  mov     [r8+54h], edx
0x18001e06d  mov     [r8+0A4h], r11d
0x18001e074  mov     qword ptr [r8+68h], 0
0x18001e07c  mov     qword ptr [r8+70h], 0
0x18001e084  cmp     ecx, 39555659h
0x18001e08a  jz      short loc_18001E0C4
0x18001e08c  cmp     ecx, 32315659h
0x18001e092  jz      short loc_18001E0C4
0x18001e094  cmp     ecx, 30323449h
0x18001e09a  jz      short loc_18001E0A4
0x18001e09c  cmp     ecx, 56555949h
0x18001e0a2  jnz     short loc_18001E0FE
0x18001e0a4  imul    r9d, r10d
0x18001e0a8  lea     eax, [r9+rbx]
0x18001e0ac  mov     [r8+78h], eax
0x18001e0b0  mov     [r8+7Ch], eax
0x18001e0b4  mov     [r8+80h], eax
0x18001e0bb  mov     [r8+84h], eax
0x18001e0c2  jmp     short loc_18001E0FE
0x18001e0c4  imul    r9d, r10d
0x18001e0c8  mov     [r8+78h], r9d
0x18001e0cc  mov     [r8+7Ch], r9d
0x18001e0d0  mov     [r8+80h], r9d
0x18001e0d7  lea     eax, [r9+rbx]
0x18001e0db  mov     [r8+84h], r9d
0x18001e0e2  mov     [r8+88h], eax
0x18001e0e9  mov     [r8+8Ch], r9d
0x18001e0f0  mov     [r8+90h], r9d
0x18001e0f7  mov     [r8+94h], r9d
0x18001e0fe  pop     r15
0x18001e100  pop     r14
0x18001e102  pop     rdi
0x18001e103  pop     rsi
0x18001e104  pop     rbp
0x18001e105  pop     rbx
0x18001e106  retn
```
