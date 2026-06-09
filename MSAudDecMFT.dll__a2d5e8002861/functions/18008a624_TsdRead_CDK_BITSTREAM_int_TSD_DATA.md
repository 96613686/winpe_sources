# TsdRead(CDK_BITSTREAM *,int,TSD_DATA *)

- ea: `0x18008a624`
- end: `0x18008a89d`
- name: `?TsdRead@@YAHPEAUCDK_BITSTREAM@@HPEAUTSD_DATA@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(struct CDK_BITSTREAM *, int, struct TSD_DATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007cc98`

## callees

- `0x1800110c0`
- `0x1800175b0`
- `0x18004d320`
- `0x18004dd14`
- `0x18008a624`
- `0x18008a8a4`
- `0x18008a904`

## pseudocode

```c
__int64 __fastcall TsdRead(struct CDK_BITSTREAM *a1, __int64 a2, struct TSD_DATA *a3)
{
  size_t v3; // r15
  unsigned int v7; // edi
  __int64 *v8; // rsi
  int v9; // eax
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // edx
  __int64 v15; // r8
  int v16; // r12d
  int v17; // esi
  int i; // r14d
  __int16 v19; // ax
  int v20; // edi
  int v21; // r12d
  struct TSD_DATA *v22; // r14
  int k; // edx
  __int64 m; // rdx
  int v25; // r8d
  unsigned __int16 v26; // ax
  __int64 n; // rdi
  _BYTE v28[8]; // [rsp+30h] [rbp-30h] BYREF
  struct TSD_DATA *v29; // [rsp+38h] [rbp-28h]
  __int16 j; // [rsp+40h] [rbp-20h] BYREF
  __int64 v31; // [rsp+42h] [rbp-1Eh]
  __int64 v32; // [rsp+50h] [rbp-10h]

  v3 = (int)a2;
  v29 = a3;
  if ( (_DWORD)a2 == 32 )
  {
    v7 = 4;
    v8 = qword_1800D19C0;
  }
  else
  {
    if ( (_DWORD)a2 != 64 )
      return 1;
    v7 = 5;
    v8 = qword_1800D1980;
  }
  v9 = *((_DWORD *)a1 + 1);
  if ( v9 )
  {
    v11 = v9 - 1;
    v12 = (*(_DWORD *)a1 >> (v9 - 1)) & 1;
  }
  else
  {
    v10 = CDK_get32((char *)a1 + 8, a2, a3);
    *(_DWORD *)a1 = v10;
    v11 = 31;
    v12 = v10 >> 31;
  }
  *((_DWORD *)a1 + 1) = v11;
  *(_BYTE *)a3 = v12;
  if ( (_BYTE)v12 )
  {
    *((_BYTE *)a3 + 1) = v3;
    v13 = CDKreadBits(a1, v7, (__int64)a3);
    v32 = 0;
    v31 = 0;
    v16 = *((unsigned __int8 *)v8 + v13);
    v17 = v13 + 1;
    if ( (int)v3 > 0 )
    {
      LOBYTE(v14) = -1;
      memset_0((char *)a3 + 2, v14, v3);
    }
    for ( i = 3; i >= 0; --i )
    {
      if ( v16 > 16 * i )
      {
        v19 = CDKreadBits(a1, (unsigned int)(v16 - 16 * i), v15);
        v16 = 16 * i;
        *((_WORD *)&v32 + (unsigned int)i) = v19;
      }
    }
    v20 = v3 - 1;
    v21 = 2;
    for ( j = v3 - v17; v21 <= v17; ++v21 )
    {
      longmult1(&j, (unsigned int)(unsigned __int16)(v3 - 1 - v17) + v21, &j);
      longdiv(&j, (unsigned __int16)v21, &j, v28);
    }
    v22 = v29;
    while ( v20 >= 0 )
    {
      if ( v17 > v20 )
      {
        LOBYTE(v14) = 1;
        memset_0((char *)v22 + v20 - (__int64)(v20 + 1) + 3, v14, v20 + 1);
        break;
      }
      for ( k = 3; k > 0; --k )
      {
        if ( *((_WORD *)&v32 + (unsigned int)k) != *(&j + (unsigned int)k) )
          break;
      }
      if ( *((_WORD *)&v32 + k) < (unsigned __int16)*(&j + k) )
      {
        v26 = longmult1(&j, (unsigned __int16)(v20 - v17), &j);
      }
      else
      {
        LODWORD(v15) = 0;
        for ( m = 0; m != 4; ++m )
        {
          v25 = *((unsigned __int16 *)&v32 + m) - (unsigned __int16)*(&j + m) + v15;
          *((_WORD *)&v32 + m) = v25;
          v15 = (unsigned int)(v25 >> 16);
        }
        *((_BYTE *)v22 + v20 + 2) = 1;
        if ( v17 == 1 )
          break;
        longmult1(&j, (unsigned __int16)v17--, &j);
        v26 = v20;
      }
      longdiv(&j, v26, &j, v28);
      --v20;
    }
    for ( n = 0; (int)n < (int)v3; n = (unsigned int)(n + 1) )
    {
      if ( *((_BYTE *)v22 + n + 2) == 1 )
        *((_BYTE *)v22 + n + 2) = CDKreadBits(a1, 3, v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008a624  mov     [rsp-38h+arg_18], rbx
0x18008a629  push    rbp
0x18008a62a  push    rsi
0x18008a62b  push    rdi
0x18008a62c  push    r12
0x18008a62e  push    r13
0x18008a630  push    r14
0x18008a632  push    r15
0x18008a634  mov     rbp, rsp
0x18008a637  sub     rsp, 60h
0x18008a63b  mov     rax, cs:__security_cookie
0x18008a642  xor     rax, rsp
0x18008a645  mov     [rbp+var_8], rax
0x18008a649  movsxd  r15, edx
0x18008a64c  mov     r14, r8
0x18008a64f  mov     [rbp+var_28], r8
0x18008a653  mov     r13, rcx
0x18008a656  cmp     r15d, 20h ; ' '
0x18008a65a  jz      short loc_18008A67A
0x18008a65c  cmp     r15d, 40h ; '@'
0x18008a660  jz      short loc_18008A66C
0x18008a662  mov     eax, 1
0x18008a667  jmp     loc_18008A878
0x18008a66c  mov     edi, 5
0x18008a671  lea     rsi, qword_1800D1980
0x18008a678  jmp     short loc_18008A686
0x18008a67a  mov     edi, 4
0x18008a67f  lea     rsi, qword_1800D19C0
0x18008a686  mov     eax, [rcx+4]
0x18008a689  mov     ebx, 1
0x18008a68e  test    eax, eax
0x18008a690  jnz     short loc_18008A6A7
0x18008a692  add     rcx, 8
0x18008a696  call    CDK_get32
0x18008a69b  mov     [r13+0], eax
0x18008a69f  lea     ecx, [rbx+1Eh]
0x18008a6a2  shr     eax, 1Fh
0x18008a6a5  jmp     short loc_18008A6B2
0x18008a6a7  lea     ecx, [rax-1]
0x18008a6aa  mov     eax, [r13+0]
0x18008a6ae  shr     eax, cl
0x18008a6b0  and     eax, ebx
0x18008a6b2  mov     [r13+4], ecx
0x18008a6b6  mov     [r14], al
0x18008a6b9  test    al, al
0x18008a6bb  jz      loc_18008A876
0x18008a6c1  mov     edx, edi
0x18008a6c3  mov     [r14+1], r15b
0x18008a6c7  mov     rcx, r13
0x18008a6ca  call    CDKreadBits
0x18008a6cf  movsxd  rcx, eax
0x18008a6d2  mov     [rbp+var_10], 0
0x18008a6da  mov     [rbp+var_1E], 0
0x18008a6e2  movzx   r12d, byte ptr [rcx+rsi]
0x18008a6e7  lea     rcx, [r14+2]; void *
0x18008a6eb  lea     esi, [rax+1]
0x18008a6ee  test    r15d, r15d
0x18008a6f1  jle     short loc_18008A6FD
0x18008a6f3  mov     r8, r15; Size
0x18008a6f6  mov     dl, 0FFh; Val
0x18008a6f8  call    memset_0
0x18008a6fd  mov     r14d, 3
0x18008a703  mov     edi, r14d
0x18008a706  shl     edi, 4
0x18008a709  cmp     r12d, edi
0x18008a70c  jle     short loc_18008A727
0x18008a70e  sub     r12d, edi
0x18008a711  mov     rcx, r13
0x18008a714  mov     edx, r12d
0x18008a717  call    CDKreadBits
0x18008a71c  mov     ecx, r14d
0x18008a71f  mov     r12d, edi
0x18008a722  mov     word ptr [rbp+rcx*2+var_10], ax
0x18008a727  sub     r14d, ebx
0x18008a72a  jns     short loc_18008A703
0x18008a72c  lea     edi, [r15-1]
0x18008a730  mov     r12d, 2
0x18008a736  movzx   r14d, di
0x18008a73a  sub     r14w, si
0x18008a73e  lea     eax, [rbx+r14]
0x18008a742  mov     [rbp+var_20], ax
0x18008a746  cmp     esi, r12d
0x18008a749  jl      short loc_18008A779
0x18008a74b  lea     edx, [r14+r12]
0x18008a74f  lea     r8, [rbp+var_20]
0x18008a753  lea     rcx, [rbp+var_20]
0x18008a757  call    longmult1
0x18008a75c  lea     r9, [rbp+var_30]
0x18008a760  movzx   edx, r12w
0x18008a764  lea     rcx, [rbp+var_20]
0x18008a768  lea     r8, [rbp+var_20]
0x18008a76c  call    longdiv
0x18008a771  add     r12d, ebx
0x18008a774  cmp     r12d, esi
0x18008a777  jle     short loc_18008A74B
0x18008a779  mov     r14, [rbp+var_28]
0x18008a77d  mov     r12d, 3
0x18008a783  test    edi, edi
0x18008a785  js      loc_18008A851
0x18008a78b  cmp     esi, edi
0x18008a78d  jg      loc_18008A834
0x18008a793  mov     edx, r12d
0x18008a796  mov     ecx, edx
0x18008a798  movzx   eax, [rbp+rcx*2+var_20]
0x18008a79d  cmp     word ptr [rbp+rcx*2+var_10], ax
0x18008a7a2  jnz     short loc_18008A7AA
0x18008a7a4  sub     edx, ebx
0x18008a7a6  test    edx, edx
0x18008a7a8  jg      short loc_18008A796
0x18008a7aa  movsxd  rcx, edx
0x18008a7ad  movzx   eax, [rbp+rcx*2+var_20]
0x18008a7b2  cmp     word ptr [rbp+rcx*2+var_10], ax
0x18008a7b7  jb      short loc_18008A803
0x18008a7b9  xor     r8d, r8d
0x18008a7bc  xor     edx, edx
0x18008a7be  movzx   ecx, word ptr [rbp+rdx*2+var_10]
0x18008a7c3  movzx   eax, [rbp+rdx*2+var_20]
0x18008a7c8  sub     ecx, eax
0x18008a7ca  add     r8d, ecx
0x18008a7cd  mov     word ptr [rbp+rdx*2+var_10], r8w
0x18008a7d3  add     rdx, rbx
0x18008a7d6  sar     r8d, 10h
0x18008a7da  cmp     rdx, 4
0x18008a7de  jnz     short loc_18008A7BE
0x18008a7e0  movsxd  rax, edi
0x18008a7e3  mov     [rax+r14+2], bl
0x18008a7e8  cmp     esi, ebx
0x18008a7ea  jz      short loc_18008A851
0x18008a7ec  movzx   edx, si
0x18008a7ef  lea     r8, [rbp+var_20]
0x18008a7f3  lea     rcx, [rbp+var_20]
0x18008a7f7  call    longmult1
0x18008a7fc  sub     esi, ebx
0x18008a7fe  movzx   eax, di
0x18008a801  jmp     short loc_18008A819
0x18008a803  movzx   edx, di
0x18008a806  lea     r8, [rbp+var_20]
0x18008a80a  sub     dx, si
0x18008a80d  lea     rcx, [rbp+var_20]
0x18008a811  movzx   eax, di
0x18008a814  call    longmult1
0x18008a819  lea     r9, [rbp+var_30]
0x18008a81d  movzx   edx, ax
0x18008a820  lea     r8, [rbp+var_20]
0x18008a824  lea     rcx, [rbp+var_20]
0x18008a828  call    longdiv
0x18008a82d  sub     edi, ebx
0x18008a82f  jmp     loc_18008A783
0x18008a834  lea     eax, [rdi+1]
0x18008a837  mov     dl, bl; Val
0x18008a839  movsxd  rcx, eax
0x18008a83c  mov     r8, rcx; Size
0x18008a83f  movsxd  rax, edi
0x18008a842  sub     rax, rcx
0x18008a845  lea     rcx, [r14+3]
0x18008a849  add     rcx, rax; void *
0x18008a84c  call    memset_0
0x18008a851  xor     edi, edi
0x18008a853  test    r15d, r15d
0x18008a856  jle     short loc_18008A876
0x18008a858  cmp     [rdi+r14+2], bl
0x18008a85d  jnz     short loc_18008A86F
0x18008a85f  mov     edx, r12d
0x18008a862  mov     rcx, r13
0x18008a865  call    CDKreadBits
0x18008a86a  mov     [rdi+r14+2], al
0x18008a86f  add     edi, ebx
0x18008a871  cmp     edi, r15d
0x18008a874  jl      short loc_18008A858
0x18008a876  xor     eax, eax
0x18008a878  mov     rcx, [rbp+var_8]
0x18008a87c  xor     rcx, rsp; StackCookie
0x18008a87f  call    __security_check_cookie
0x18008a884  mov     rbx, [rsp+60h+arg_18]
0x18008a88c  add     rsp, 60h
0x18008a890  pop     r15
0x18008a892  pop     r14
0x18008a894  pop     r13
0x18008a896  pop     r12
0x18008a898  pop     rdi
0x18008a899  pop     rsi
0x18008a89a  pop     rbp
0x18008a89b  retn
```
