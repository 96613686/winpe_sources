# createTableStmt

- ea: `0x1400269b4`
- end: `0x140026bd2`
- name: `createTableStmt`
- size: `542`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140055854`

## callees

- `0x1400269b4`
- `0x140030714`
- `0x140062c2c`
- `0x1400636dc`
- `0x14008ccd0`
- `0x1400a7308`

## string_xrefs

- `0x140026aa5`: `CREATE TABLE `

## pseudocode

```c
__int64 __fastcall createTableStmt(__int64 a1, __int64 a2)
{
  int v2; // r11d
  int v3; // ebx
  _BYTE **v4; // r8
  int i; // r9d
  _BYTE *v8; // rdx
  int v9; // ecx
  int v10; // eax
  _BYTE *v11; // rdx
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  const char *v15; // rax
  const char *v16; // r13
  const char *v17; // rax
  int v18; // ebp
  __int64 v19; // rax
  __int64 v20; // rsi
  unsigned int v22; // ebp
  __int64 v23; // rax
  _BYTE *v24; // r8
  int v25; // ecx
  int v26; // ebx
  __int64 *v27; // r15
  int v28; // r12d
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // r8
  _BYTE *v33; // rdx
  unsigned int v34; // edi
  __int64 v35; // rdi
  int v36; // ebx
  int v37; // [rsp+68h] [rbp+10h] BYREF
  const char *v38; // [rsp+70h] [rbp+18h]
  const char *v39; // [rsp+78h] [rbp+20h]

  v2 = *(__int16 *)(a2 + 54);
  v3 = 0;
  v4 = *(_BYTE ***)(a2 + 8);
  for ( i = 0; i < v2; v4 += 3 )
  {
    v8 = *v4;
    v9 = 0;
    while ( *v8 )
    {
      v10 = v9 + 1;
      if ( *v8 != 34 )
        v10 = v9;
      ++v8;
      v9 = v10 + 1;
    }
    ++i;
    v3 += v9 + 7;
  }
  v11 = *(_BYTE **)a2;
  v12 = 0;
  while ( *v11 )
  {
    v13 = v12 + 1;
    if ( *v11 != 34 )
      v13 = v12;
    ++v11;
    v12 = v13 + 1;
  }
  v14 = v3 + v12 + 2;
  v15 = ")";
  v16 = (const char *)&dword_1400ACDEC;
  if ( v14 >= 50 )
    v15 = "\n)";
  v39 = v15;
  v17 = ",";
  if ( v14 >= 50 )
    v17 = ",\n  ";
  v38 = v17;
  if ( v14 >= 50 )
    v16 = "\n  ";
  v18 = v14 + 6 * v2;
  v19 = sqlite3Malloc(v18 + 35LL);
  v20 = v19;
  if ( v19 )
  {
    v22 = v18 + 35;
    sqlite3_snprintf(v22, v19, "CREATE TABLE ");
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(v20 + v23) );
    v24 = *(_BYTE **)a2;
    v37 = v23 & 0x3FFFFFFF;
    identPut(v20, &v37, v24);
    v25 = v37;
    *(_BYTE *)(v37 + v20) = 40;
    v26 = v25 + 1;
    if ( *(__int16 *)(a2 + 54) > 0 )
    {
      v27 = *(__int64 **)(a2 + 8);
      v28 = 0;
      do
      {
        v29 = v20 + v26;
        sqlite3_snprintf(v22 - v26, v29, v16);
        if ( v29 )
        {
          v31 = -1;
          do
            ++v31;
          while ( *(_BYTE *)(v29 + v31) );
          v30 = v31 & 0x3FFFFFFF;
        }
        else
        {
          v30 = 0;
        }
        v32 = *v27;
        v16 = v38;
        v37 = v26 + v30;
        identPut(v20, &v37, v32);
        v33 = (_BYTE *)*((_QWORD *)&off_1400AA560 + *((char *)v27 + 12) - 65);
        if ( v33 )
        {
          v35 = -1;
          do
            ++v35;
          while ( v33[v35] );
          v34 = v35 & 0x3FFFFFFF;
        }
        else
        {
          v34 = 0;
        }
        v36 = v37;
        memcpy_0((void *)(v20 + v37), v33, v34);
        v26 = v34 + v36;
        ++v28;
        v27 += 3;
      }
      while ( v28 < *(__int16 *)(a2 + 54) );
    }
    sqlite3_snprintf(v22 - v26, v20 + v26, "%s", v39);
    return v20;
  }
  else
  {
    sqlite3OomFault(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x1400269b4  mov     [rsp+arg_0], rbx
0x1400269b9  push    rbp
0x1400269ba  push    rsi
0x1400269bb  push    rdi
0x1400269bc  push    r12
0x1400269be  push    r13
0x1400269c0  push    r14
0x1400269c2  push    r15
0x1400269c4  sub     rsp, 20h
0x1400269c8  movsx   r11d, word ptr [rdx+36h]
0x1400269cd  xor     ebx, ebx
0x1400269cf  mov     r8, [rdx+8]
0x1400269d3  xor     r9d, r9d
0x1400269d6  mov     r14, rdx
0x1400269d9  mov     rdi, rcx
0x1400269dc  test    r11d, r11d
0x1400269df  jle     short loc_140026A11
0x1400269e1  mov     rdx, [r8]
0x1400269e4  xor     ecx, ecx
0x1400269e6  jmp     short loc_1400269F8
0x1400269e8  cmp     r10b, 22h ; '"'
0x1400269ec  lea     eax, [rcx+1]
0x1400269ef  cmovnz  eax, ecx
0x1400269f2  inc     rdx
0x1400269f5  lea     ecx, [rax+1]
0x1400269f8  mov     r10b, [rdx]
0x1400269fb  test    r10b, r10b
0x1400269fe  jnz     short loc_1400269E8
0x140026a00  add     ebx, 7
0x140026a03  inc     r9d
0x140026a06  add     ebx, ecx
0x140026a08  add     r8, 18h
0x140026a0c  cmp     r9d, r11d
0x140026a0f  jl      short loc_1400269E1
0x140026a11  mov     rdx, [r14]
0x140026a14  xor     ecx, ecx
0x140026a16  jmp     short loc_140026A28
0x140026a18  cmp     r8b, 22h ; '"'
0x140026a1c  lea     eax, [rcx+1]
0x140026a1f  cmovnz  eax, ecx
0x140026a22  inc     rdx
0x140026a25  lea     ecx, [rax+1]
0x140026a28  mov     r8b, [rdx]
0x140026a2b  test    r8b, r8b
0x140026a2e  jnz     short loc_140026A18
0x140026a30  add     ecx, 2
0x140026a33  lea     rdx, asc_1400B9B48; "\n)"
0x140026a3a  add     ecx, ebx
0x140026a3c  lea     rax, asc_1400B79FC; ")"
0x140026a43  cmp     ecx, 32h ; '2'
0x140026a46  lea     r13, dword_1400ACDEC
0x140026a4d  cmovge  rax, rdx
0x140026a51  lea     rdx, asc_1400B9B4C; ",\n  "
0x140026a58  mov     [rsp+58h+arg_18], rax
0x140026a5d  lea     rax, asc_1400B9B44; ","
0x140026a64  cmovge  rax, rdx
0x140026a68  mov     [rsp+58h+arg_10], rax
0x140026a6d  lea     rax, asc_1400B9B40; "\n  "
0x140026a74  cmovge  r13, rax
0x140026a78  lea     eax, [r11+r11*2]
0x140026a7c  lea     ebp, [rcx+rax*2]
0x140026a7f  movsxd  rcx, ebp
0x140026a82  add     rcx, 23h ; '#'
0x140026a86  call    sqlite3Malloc
0x140026a8b  mov     rsi, rax
0x140026a8e  test    rax, rax
0x140026a91  jnz     short loc_140026AA2
0x140026a93  mov     rcx, rdi
0x140026a96  call    sqlite3OomFault
0x140026a9b  xor     eax, eax
0x140026a9d  jmp     loc_140026BBD
0x140026aa2  add     ebp, 23h ; '#'
0x140026aa5  lea     r8, aCreateTable; "CREATE TABLE "
0x140026aac  mov     ecx, ebp
0x140026aae  mov     rdx, rsi
0x140026ab1  call    sqlite3_snprintf
0x140026ab6  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026aba  inc     rax
0x140026abd  cmp     byte ptr [rsi+rax], 0
0x140026ac1  jnz     short loc_140026ABA
0x140026ac3  mov     r8, [r14]
0x140026ac6  lea     rdx, [rsp+58h+arg_8]
0x140026acb  and     eax, 3FFFFFFFh
0x140026ad0  mov     rcx, rsi
0x140026ad3  mov     [rsp+58h+arg_8], eax
0x140026ad7  call    identPut
0x140026adc  movsxd  rcx, [rsp+58h+arg_8]
0x140026ae1  xor     eax, eax
0x140026ae3  mov     byte ptr [rcx+rsi], 28h ; '('
0x140026ae7  lea     ebx, [rcx+1]
0x140026aea  cmp     ax, [r14+36h]
0x140026aef  jge     loc_140026B9F
0x140026af5  mov     r15, [r14+8]
0x140026af9  xor     r12d, r12d
0x140026afc  mov     ecx, ebp
0x140026afe  movsxd  rdi, ebx
0x140026b01  add     rdi, rsi
0x140026b04  sub     ecx, ebx
0x140026b06  mov     rdx, rdi
0x140026b09  mov     r8, r13
0x140026b0c  call    sqlite3_snprintf
0x140026b11  test    rdi, rdi
0x140026b14  jnz     short loc_140026B1A
0x140026b16  xor     eax, eax
0x140026b18  jmp     short loc_140026B2C
0x140026b1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026b1e  inc     rax
0x140026b21  cmp     byte ptr [rdi+rax], 0
0x140026b25  jnz     short loc_140026B1E
0x140026b27  and     eax, 3FFFFFFFh
0x140026b2c  mov     r8, [r15]
0x140026b2f  lea     rdx, [rsp+58h+arg_8]
0x140026b34  mov     r13, [rsp+58h+arg_10]
0x140026b39  add     eax, ebx
0x140026b3b  mov     rcx, rsi
0x140026b3e  mov     [rsp+58h+arg_8], eax
0x140026b42  call    identPut
0x140026b47  movsx   rax, byte ptr [r15+0Ch]
0x140026b4c  lea     rdx, off_1400AA560
0x140026b53  mov     rdx, [rdx+rax*8-208h]; Src
0x140026b5b  test    rdx, rdx
0x140026b5e  jnz     short loc_140026B64
0x140026b60  xor     edi, edi
0x140026b62  jmp     short loc_140026B77
0x140026b64  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140026b68  inc     rdi
0x140026b6b  cmp     byte ptr [rdx+rdi], 0
0x140026b6f  jnz     short loc_140026B68
0x140026b71  and     edi, 3FFFFFFFh
0x140026b77  movsxd  rbx, [rsp+58h+arg_8]
0x140026b7c  mov     r8d, edi; Size
0x140026b7f  lea     rcx, [rsi+rbx]; void *
0x140026b83  call    memcpy_0
0x140026b88  movsx   eax, word ptr [r14+36h]
0x140026b8d  add     ebx, edi
0x140026b8f  inc     r12d
0x140026b92  add     r15, 18h
0x140026b96  cmp     r12d, eax
0x140026b99  jl      loc_140026AFC
0x140026b9f  mov     r9, [rsp+58h+arg_18]
0x140026ba4  lea     r8, aS_6; "%s"
0x140026bab  sub     ebp, ebx
0x140026bad  movsxd  rdx, ebx
0x140026bb0  add     rdx, rsi
0x140026bb3  mov     ecx, ebp
0x140026bb5  call    sqlite3_snprintf
0x140026bba  mov     rax, rsi
0x140026bbd  mov     rbx, [rsp+58h+arg_0]
0x140026bc2  add     rsp, 20h
0x140026bc6  pop     r15
0x140026bc8  pop     r14
0x140026bca  pop     r13
0x140026bcc  pop     r12
0x140026bce  pop     rdi
0x140026bcf  pop     rsi
0x140026bd0  pop     rbp
0x140026bd1  retn
```
