# g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,ulong,ulong,ulong)

- ea: `0x18001df4c`
- end: `0x18001e1c7`
- name: `?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJKKK@Z`
- size: `635`
- prototype: `void __fastcall(struct CDeColorConvParams *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001e2c8`

## callees

- `0x18001df4c`

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
0x18001df4c  push    rbx
0x18001df4e  push    rbp
0x18001df4f  push    rsi
0x18001df50  push    rdi
0x18001df51  push    r14
0x18001df53  push    r15
0x18001df55  cmp     dword ptr [rcx+34h], 0
0x18001df59  lea     r9, [rcx+8]
0x18001df5d  mov     r14d, edx
0x18001df60  mov     r8, rcx
0x18001df63  jz      loc_18001E030
0x18001df69  mov     r11d, [rcx+38h]
0x18001df6d  test    r11d, r11d
0x18001df70  jz      short loc_18001DF7E
0x18001df72  mov     eax, [r9]
0x18001df75  neg     eax
0x18001df77  cmovs   eax, [r9]
0x18001df7b  mov     [r9], eax
0x18001df7e  movzx   ecx, word ptr [rcx+0Eh]
0x18001df82  mov     ebx, [r9]
0x18001df85  mov     r10d, ecx
0x18001df88  mov     r9d, [r8+4]
0x18001df8c  mov     eax, r9d
0x18001df8f  imul    eax, ecx
0x18001df92  mov     ecx, ebx
0x18001df94  shr     r10d, 3
0x18001df98  mov     [r8+44h], r10d
0x18001df9c  add     eax, 1Fh
0x18001df9f  and     eax, 0FFFFFFE0h
0x18001dfa2  cdq
0x18001dfa3  and     edx, 7
0x18001dfa6  add     eax, edx
0x18001dfa8  sar     eax, 3
0x18001dfab  neg     ecx
0x18001dfad  mov     [r8+40h], eax
0x18001dfb1  mov     edx, eax
0x18001dfb3  cmovs   ecx, ebx
0x18001dfb6  imul    ecx, eax
0x18001dfb9  mov     [r8+48h], ecx
0x18001dfbd  test    ebx, ebx
0x18001dfbf  jle     short loc_18001DFCC
0x18001dfc1  test    r11d, r11d
0x18001dfc4  jnz     short loc_18001DFCC
0x18001dfc6  neg     edx
0x18001dfc8  mov     [r8+40h], edx
0x18001dfcc  mov     eax, r10d
0x18001dfcf  shl     eax, 4
0x18001dfd2  mov     [r8+4Ch], eax
0x18001dfd6  lea     eax, ds:0[r10*8]
0x18001dfde  mov     [r8+50h], eax
0x18001dfe2  mov     eax, edx
0x18001dfe4  sub     edx, r10d
0x18001dfe7  shl     eax, 4
0x18001dfea  shl     edx, 3
0x18001dfed  mov     [r8+54h], eax
0x18001dff1  mov     [r8+58h], edx
0x18001dff5  test    r11d, r11d
0x18001dff8  jnz     short loc_18001E019
0x18001dffa  test    ebx, ebx
0x18001dffc  js      short loc_18001E019
0x18001dffe  mov     eax, ebx
0x18001e000  neg     eax
0x18001e002  cmovs   eax, ebx
0x18001e005  imul    r9d, r10d
0x18001e009  dec     eax
0x18001e00b  add     r9d, 3
0x18001e00f  and     r9d, 0FFFFFFFCh
0x18001e013  imul    eax, r9d
0x18001e017  jmp     short loc_18001E01B
0x18001e019  xor     eax, eax
0x18001e01b  mov     [r8+68h], eax
0x18001e01f  mov     [r8+6Ch], eax
0x18001e023  mov     [r8+70h], eax
0x18001e027  mov     [r8+74h], eax
0x18001e02b  jmp     loc_18001E1BE
0x18001e030  mov     r10d, [r9]
0x18001e033  neg     r10d
0x18001e036  mov     dword ptr [rcx+44h], 1
0x18001e03d  cmovs   r10d, [r9]
0x18001e041  mov     [r9], r10d
0x18001e044  mov     r11d, r10d
0x18001e047  test    r10d, r10d
0x18001e04a  jns     short loc_18001E04F
0x18001e04c  neg     r11d
0x18001e04f  mov     ebp, [rcx+4]
0x18001e052  mov     edi, 4
0x18001e057  lea     ebx, ds:1Fh[rbp*8]
0x18001e05e  and     ebx, 0FFFFFFE0h
0x18001e061  lea     esi, [rdi+4]
0x18001e064  mov     eax, ebx
0x18001e066  cdq
0x18001e067  and     edx, 7
0x18001e06a  add     eax, edx
0x18001e06c  sar     eax, 3
0x18001e06f  mov     ecx, eax
0x18001e071  mov     [r8+40h], eax
0x18001e075  imul    ecx, r11d
0x18001e079  mov     r9d, eax
0x18001e07c  mov     eax, ebx
0x18001e07e  cdq
0x18001e07f  mov     [r8+48h], ecx
0x18001e083  mov     ecx, [r8+10h]
0x18001e087  cmp     ecx, 39555659h
0x18001e08d  jnz     short loc_18001E0AF
0x18001e08f  and     edx, 1Fh
0x18001e092  mov     r15d, esi
0x18001e095  add     eax, edx
0x18001e097  sar     eax, 5
0x18001e09a  mov     r11d, eax
0x18001e09d  imul    eax, r10d
0x18001e0a1  cdq
0x18001e0a2  and     edx, 3
0x18001e0a5  lea     ebx, [rdx+rax]
0x18001e0a8  mov     eax, edi
0x18001e0aa  sar     ebx, 2
0x18001e0ad  jmp     short loc_18001E0CD
0x18001e0af  and     edx, 0Fh
0x18001e0b2  mov     r15d, 10h
0x18001e0b8  add     eax, edx
0x18001e0ba  sar     eax, 4
0x18001e0bd  mov     r11d, eax
0x18001e0c0  imul    eax, r10d
0x18001e0c4  cdq
0x18001e0c5  sub     eax, edx
0x18001e0c7  sar     eax, 1
0x18001e0c9  mov     ebx, eax
0x18001e0cb  mov     eax, esi
0x18001e0cd  cmp     ecx, 39555659h
0x18001e0d3  mov     [r8+98h], r11d
0x18001e0da  mov     [r8+9Ch], eax
0x18001e0e1  mov     edx, r9d
0x18001e0e4  cmovnz  edi, esi
0x18001e0e7  imul    r11d, eax
0x18001e0eb  cmp     ebp, r14d
0x18001e0ee  jnz     short loc_18001E0F5
0x18001e0f0  shl     edx, 4
0x18001e0f3  jmp     short loc_18001E0FB
0x18001e0f5  shl     edx, 5
0x18001e0f8  mov     edi, r15d
0x18001e0fb  cmp     ebp, r14d
0x18001e0fe  mov     eax, 10h
0x18001e103  lea     r15d, [rax+10h]
0x18001e107  cmovnz  eax, r15d
0x18001e10b  mov     [r8+4Ch], eax
0x18001e10f  lea     eax, [r15-10h]
0x18001e113  cmovnz  esi, eax
0x18001e116  lea     eax, [r11+r11]
0x18001e11a  mov     [r8+50h], esi
0x18001e11e  cmovnz  r11d, eax
0x18001e122  mov     [r8+0A0h], edi
0x18001e129  mov     [r8+54h], edx
0x18001e12d  mov     [r8+0A4h], r11d
0x18001e134  mov     qword ptr [r8+68h], 0
0x18001e13c  mov     qword ptr [r8+70h], 0
0x18001e144  cmp     ecx, 39555659h
0x18001e14a  jz      short loc_18001E184
0x18001e14c  cmp     ecx, 32315659h
0x18001e152  jz      short loc_18001E184
0x18001e154  cmp     ecx, 30323449h
0x18001e15a  jz      short loc_18001E164
0x18001e15c  cmp     ecx, 56555949h
0x18001e162  jnz     short loc_18001E1BE
0x18001e164  imul    r9d, r10d
0x18001e168  lea     eax, [r9+rbx]
0x18001e16c  mov     [r8+78h], eax
0x18001e170  mov     [r8+7Ch], eax
0x18001e174  mov     [r8+80h], eax
0x18001e17b  mov     [r8+84h], eax
0x18001e182  jmp     short loc_18001E1BE
0x18001e184  imul    r9d, r10d
0x18001e188  mov     [r8+78h], r9d
0x18001e18c  mov     [r8+7Ch], r9d
0x18001e190  mov     [r8+80h], r9d
0x18001e197  lea     eax, [r9+rbx]
0x18001e19b  mov     [r8+84h], r9d
0x18001e1a2  mov     [r8+88h], eax
0x18001e1a9  mov     [r8+8Ch], r9d
0x18001e1b0  mov     [r8+90h], r9d
0x18001e1b7  mov     [r8+94h], r9d
0x18001e1be  pop     r15
0x18001e1c0  pop     r14
0x18001e1c2  pop     rdi
0x18001e1c3  pop     rsi
0x18001e1c4  pop     rbp
0x18001e1c5  pop     rbx
0x18001e1c6  retn
```
