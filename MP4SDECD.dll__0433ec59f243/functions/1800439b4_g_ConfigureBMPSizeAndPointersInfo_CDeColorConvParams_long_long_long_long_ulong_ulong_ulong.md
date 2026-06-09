# g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,long,long,ulong,ulong,ulong)

- ea: `0x1800439b4`
- end: `0x180043ca8`
- name: `?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJJJKKK@Z`
- size: `756`
- prototype: `void __fastcall(struct CDeColorConvParams *, int, __int64, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180043db8`

## callees

- `0x1800439b4`

## pseudocode

```c
void __fastcall g_ConfigureBMPSizeAndPointersInfo(struct CDeColorConvParams *a1, int a2, __int64 a3, int a4, int a5)
{
  int *v5; // r11
  int v8; // ebx
  int v9; // eax
  int v10; // edi
  unsigned int v11; // r10d
  int v12; // r11d
  int v13; // eax
  unsigned int v14; // r10d
  int v15; // eax
  int v16; // ecx
  int v17; // r9d
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  bool v21; // sf
  int v22; // ecx
  int v23; // r9d
  int v24; // r10d
  int v25; // esi
  int v26; // ebp
  int v27; // r15d
  int v28; // ebx
  int v29; // r9d
  int v30; // edi
  int v31; // eax
  int v32; // r9d
  int v33; // r10d
  int v34; // edx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx

  v5 = (int *)((char *)a1 + 8);
  if ( *((_DWORD *)a1 + 13) )
  {
    v8 = *((_DWORD *)a1 + 14);
    if ( v8 )
    {
      v9 = -*v5;
      if ( *v5 > 0 )
        v9 = *v5;
      *v5 = v9;
    }
    v10 = *v5;
    v11 = *((unsigned __int16 *)a1 + 7);
    v12 = *((_DWORD *)a1 + 1);
    v13 = v11 * v12;
    v14 = v11 >> 3;
    *((_DWORD *)a1 + 20) = v14;
    v15 = (int)((v13 + 31) & 0xFFFFFFE0) / 8;
    v16 = -v10;
    v17 = v15;
    *((_DWORD *)a1 + 19) = v15;
    if ( v10 > 0 )
      v16 = v10;
    *((_DWORD *)a1 + 21) = v15 * v16;
    if ( v10 > 0 && !v8 )
    {
      v17 = -v15;
      *((_DWORD *)a1 + 19) = -v15;
    }
    *((_DWORD *)a1 + 22) = 16 * v14;
    *((_DWORD *)a1 + 23) = 8 * v14;
    *((_DWORD *)a1 + 24) = 16 * v17;
    *((_DWORD *)a1 + 25) = 8 * (v17 - v14);
    if ( v8 || v10 < 0 )
    {
      v19 = (a4 * v14 + 3) & 0xFFFFFFFC;
    }
    else
    {
      v18 = -v10;
      if ( v10 > 0 )
        v18 = v10;
      v19 = ((a4 * v14 + 3) & 0xFFFFFFFC) + ((v14 * v12 + 3) & 0xFFFFFFFC) * (v18 - 1);
    }
    v20 = a5 * v17 + v19;
    *((_DWORD *)a1 + 32) = v20;
    *((_DWORD *)a1 + 33) = v20;
    *((_DWORD *)a1 + 34) = v20;
    *((_DWORD *)a1 + 35) = v20;
  }
  else
  {
    v21 = -*v5 < 0;
    v22 = -*v5;
    *((_DWORD *)a1 + 20) = 1;
    if ( v21 )
      v22 = *v5;
    *v5 = v22;
    v23 = v22;
    if ( v22 < 0 )
      v23 = -v22;
    v24 = *((_DWORD *)a1 + 1);
    v25 = 8;
    v26 = *((_DWORD *)a1 + 4);
    *((_DWORD *)a1 + 19) = v24;
    v27 = 16;
    *((_DWORD *)a1 + 21) = v23 * ((int)((8 * v24 + 31) & 0xFFFFFFE0) / 8);
    if ( v26 == 961893977 )
    {
      v28 = 4;
      v29 = v24 / 4;
      v30 = v22 * (v24 / 4) / 4;
      v31 = 8;
    }
    else
    {
      v28 = 8;
      v29 = v24 / 2;
      v30 = v22 * (v24 / 2) / 2;
      v31 = 16;
    }
    *((_DWORD *)a1 + 44) = v29;
    *((_DWORD *)a1 + 45) = v28;
    if ( v24 == a2 || v26 == 842094169 )
    {
      v32 = v28 * v29;
      v31 = v28;
      v33 = 16 * v24;
    }
    else
    {
      v25 = 16;
      v27 = 32;
      v32 = 2 * v28 * v29;
      v33 = 32 * v24;
    }
    *((_DWORD *)a1 + 22) = v27;
    *((_DWORD *)a1 + 23) = v25;
    *((_DWORD *)a1 + 46) = v31;
    *((_DWORD *)a1 + 24) = v33;
    *((_DWORD *)a1 + 47) = v32;
    v34 = *((_DWORD *)a1 + 4);
    v35 = *((_DWORD *)a1 + 19);
    if ( v34 == 842094158 )
    {
      *((_DWORD *)a1 + 46) = 2 * v31;
      *((_DWORD *)a1 + 47) = 2 * v32;
    }
    *((_QWORD *)a1 + 16) = 0;
    *((_QWORD *)a1 + 17) = 0;
    if ( v34 == 961893977 || v34 == 842094169 || v34 == 842094158 )
    {
      v37 = *((_DWORD *)a1 + 2) * v35;
      *((_DWORD *)a1 + 36) = v37;
      *((_DWORD *)a1 + 37) = v37;
      *((_DWORD *)a1 + 38) = v37;
      *((_DWORD *)a1 + 39) = v37;
      *((_DWORD *)a1 + 40) = v37 + v30;
      *((_DWORD *)a1 + 41) = v37 + v30;
      *((_DWORD *)a1 + 42) = v37 + v30;
      *((_DWORD *)a1 + 43) = v37 + v30;
    }
    else if ( v34 == 808596553 || v34 == 1448433993 )
    {
      v36 = *((_DWORD *)a1 + 2) * v35;
      *((_DWORD *)a1 + 40) = v36;
      *((_DWORD *)a1 + 41) = v36;
      *((_DWORD *)a1 + 42) = v36;
      *((_DWORD *)a1 + 43) = v36;
      *((_DWORD *)a1 + 36) = v36 + v30;
      *((_DWORD *)a1 + 37) = v36 + v30;
      *((_DWORD *)a1 + 38) = v36 + v30;
      *((_DWORD *)a1 + 39) = v36 + v30;
    }
  }
}

```

## disassembly

```asm
0x1800439b4  push    rbx
0x1800439b6  push    rbp
0x1800439b7  push    rsi
0x1800439b8  push    rdi
0x1800439b9  push    r12
0x1800439bb  push    r13
0x1800439bd  push    r14
0x1800439bf  push    r15
0x1800439c1  cmp     dword ptr [rcx+34h], 0
0x1800439c5  lea     r11, [rcx+8]
0x1800439c9  mov     ebp, r9d
0x1800439cc  mov     r14d, edx
0x1800439cf  mov     r8, rcx
0x1800439d2  jz      loc_180043ACE
0x1800439d8  mov     ebx, [rcx+38h]
0x1800439db  test    ebx, ebx
0x1800439dd  jz      short loc_1800439EB
0x1800439df  mov     eax, [r11]
0x1800439e2  neg     eax
0x1800439e4  cmovs   eax, [r11]
0x1800439e8  mov     [r11], eax
0x1800439eb  movzx   ecx, word ptr [rcx+0Eh]
0x1800439ef  mov     esi, 8
0x1800439f4  mov     edi, [r11]
0x1800439f7  mov     r10d, ecx
0x1800439fa  mov     r11d, [r8+4]
0x1800439fe  mov     eax, r11d
0x180043a01  imul    eax, ecx
0x180043a04  mov     ecx, edi
0x180043a06  shr     r10d, 3
0x180043a0a  mov     [r8+50h], r10d
0x180043a0e  add     eax, 1Fh
0x180043a11  and     eax, 0FFFFFFE0h
0x180043a14  cdq
0x180043a15  idiv    esi
0x180043a17  neg     ecx
0x180043a19  mov     r9d, eax
0x180043a1c  mov     [r8+4Ch], eax
0x180043a20  cmovs   ecx, edi
0x180043a23  imul    ecx, eax
0x180043a26  mov     [r8+54h], ecx
0x180043a2a  test    edi, edi
0x180043a2c  jle     short loc_180043A39
0x180043a2e  test    ebx, ebx
0x180043a30  jnz     short loc_180043A39
0x180043a32  neg     r9d
0x180043a35  mov     [r8+4Ch], r9d
0x180043a39  mov     eax, r10d
0x180043a3c  shl     eax, 4
0x180043a3f  mov     [r8+58h], eax
0x180043a43  lea     eax, ds:0[r10*8]
0x180043a4b  mov     [r8+5Ch], eax
0x180043a4f  mov     eax, r9d
0x180043a52  shl     eax, 4
0x180043a55  mov     [r8+60h], eax
0x180043a59  mov     eax, r9d
0x180043a5c  sub     eax, r10d
0x180043a5f  shl     eax, 3
0x180043a62  mov     [r8+64h], eax
0x180043a66  test    ebx, ebx
0x180043a68  jnz     short loc_180043A98
0x180043a6a  test    edi, edi
0x180043a6c  js      short loc_180043A98
0x180043a6e  mov     eax, edi
0x180043a70  neg     eax
0x180043a72  cmovs   eax, edi
0x180043a75  imul    r11d, r10d
0x180043a79  imul    r10d, ebp
0x180043a7d  dec     eax
0x180043a7f  add     r11d, 3
0x180043a83  and     r11d, 0FFFFFFFCh
0x180043a87  add     r10d, 3
0x180043a8b  imul    eax, r11d
0x180043a8f  and     r10d, 0FFFFFFFCh
0x180043a93  add     eax, r10d
0x180043a96  jmp     short loc_180043AA4
0x180043a98  mov     eax, r10d
0x180043a9b  imul    eax, ebp
0x180043a9e  add     eax, 3
0x180043aa1  and     eax, 0FFFFFFFCh
0x180043aa4  imul    r9d, [rsp+40h+arg_20]
0x180043aaa  add     eax, r9d
0x180043aad  mov     [r8+80h], eax
0x180043ab4  mov     [r8+84h], eax
0x180043abb  mov     [r8+88h], eax
0x180043ac2  mov     [r8+8Ch], eax
0x180043ac9  jmp     loc_180043C9B
0x180043ace  mov     ecx, [r11]
0x180043ad1  neg     ecx
0x180043ad3  mov     dword ptr [r8+50h], 1
0x180043adb  cmovs   ecx, [r11]
0x180043adf  mov     [r11], ecx
0x180043ae2  mov     r9d, ecx
0x180043ae5  test    ecx, ecx
0x180043ae7  jns     short loc_180043AEC
0x180043ae9  neg     r9d
0x180043aec  mov     r10d, [r8+4]
0x180043af0  mov     esi, 8
0x180043af5  mov     ebp, [r8+10h]
0x180043af9  mov     [r8+4Ch], r10d
0x180043afd  lea     eax, ds:1Fh[r10*8]
0x180043b05  and     eax, 0FFFFFFE0h
0x180043b08  lea     r15d, [rsi+8]
0x180043b0c  cdq
0x180043b0d  idiv    esi
0x180043b0f  imul    eax, r9d
0x180043b13  mov     [r8+54h], eax
0x180043b17  mov     eax, r10d
0x180043b1a  cdq
0x180043b1b  cmp     ebp, 39555659h
0x180043b21  jnz     short loc_180043B37
0x180043b23  lea     ebx, [rsi-4]
0x180043b26  idiv    ebx
0x180043b28  mov     r9d, eax
0x180043b2b  imul    eax, ecx
0x180043b2e  cdq
0x180043b2f  idiv    ebx
0x180043b31  mov     edi, eax
0x180043b33  mov     eax, esi
0x180043b35  jmp     short loc_180043B51
0x180043b37  mov     r11d, 2
0x180043b3d  mov     ebx, esi
0x180043b3f  idiv    r11d
0x180043b42  mov     r9d, eax
0x180043b45  imul    eax, ecx
0x180043b48  cdq
0x180043b49  idiv    r11d
0x180043b4c  mov     edi, eax
0x180043b4e  mov     eax, r15d
0x180043b51  mov     [r8+0B0h], r9d
0x180043b58  mov     [r8+0B4h], ebx
0x180043b5f  cmp     r10d, r14d
0x180043b62  jz      short loc_180043B82
0x180043b64  cmp     ebp, 32315659h
0x180043b6a  jz      short loc_180043B82
0x180043b6c  imul    r9d, ebx
0x180043b70  mov     esi, r15d
0x180043b73  mov     r15d, 20h ; ' '
0x180043b79  add     r9d, r9d
0x180043b7c  shl     r10d, 5
0x180043b80  jmp     short loc_180043B8C
0x180043b82  imul    r9d, ebx
0x180043b86  mov     eax, ebx
0x180043b88  shl     r10d, 4
0x180043b8c  mov     r14d, 58h ; 'X'
0x180043b92  mov     r13, r8
0x180043b95  mov     rbp, r8
0x180043b98  mov     r12, r8
0x180043b9b  mov     [r8+r14], r15d
0x180043b9f  lea     edx, [r14+4]
0x180043ba3  mov     [rdx+r8], esi
0x180043ba7  lea     ecx, [rdx+4]
0x180043baa  lea     ebx, [rdx+5Ch]
0x180043bad  mov     [rbx+r8], eax
0x180043bb1  mov     [r8+rcx], r10d
0x180043bb5  mov     r10d, 3231564Eh
0x180043bbb  mov     [r8+0BCh], r9d
0x180043bc2  mov     edx, [r8+10h]
0x180043bc6  mov     ecx, [r8+4Ch]
0x180043bca  cmp     edx, r10d
0x180043bcd  jnz     short loc_180043BE0
0x180043bcf  add     eax, eax
0x180043bd1  mov     [rbx+r8], eax
0x180043bd5  lea     eax, [r9+r9]
0x180043bd9  mov     [r8+0BCh], eax
0x180043be0  xor     eax, eax
0x180043be2  mov     [r8+80h], rax
0x180043be9  mov     [r8+88h], rax
0x180043bf0  cmp     edx, 39555659h
0x180043bf6  jz      short loc_180043C5B
0x180043bf8  cmp     edx, 32315659h
0x180043bfe  jz      short loc_180043C5B
0x180043c00  cmp     edx, r10d
0x180043c03  jz      short loc_180043C5B
0x180043c05  cmp     edx, 30323449h
0x180043c0b  jz      short loc_180043C19
0x180043c0d  cmp     edx, 56555949h
0x180043c13  jnz     loc_180043C9B
0x180043c19  imul    ecx, [r8+8]
0x180043c1e  mov     [r8+0A0h], ecx
0x180043c25  mov     [r8+0A4h], ecx
0x180043c2c  mov     [r8+0A8h], ecx
0x180043c33  lea     eax, [rcx+rdi]
0x180043c36  mov     [r8+0ACh], ecx
0x180043c3d  mov     [r8+90h], eax
0x180043c44  mov     [r8+94h], eax
0x180043c4b  mov     [r8+98h], eax
0x180043c52  mov     [r8+9Ch], eax
0x180043c59  jmp     short loc_180043C9B
0x180043c5b  imul    ecx, [r8+8]
0x180043c60  mov     [r8+90h], ecx
0x180043c67  mov     [r8+94h], ecx
0x180043c6e  mov     [r8+98h], ecx
0x180043c75  lea     eax, [rcx+rdi]
0x180043c78  mov     [r8+9Ch], ecx
0x180043c7f  mov     [r8+0A0h], eax
0x180043c86  mov     [r8+0A4h], eax
0x180043c8d  mov     [r8+0A8h], eax
0x180043c94  mov     [r8+0ACh], eax
0x180043c9b  pop     r15
0x180043c9d  pop     r14
0x180043c9f  pop     r13
0x180043ca1  pop     r12
0x180043ca3  pop     rdi
0x180043ca4  pop     rsi
0x180043ca5  pop     rbp
0x180043ca6  pop     rbx
0x180043ca7  retn
```
