# WriteHorVCounters

- ea: `0x180052b68`
- end: `0x180052ea0`
- name: `WriteHorVCounters`
- size: `824`
- prototype: `__int64 __fastcall(__int64, __int16, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18005201c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004f8e4`
- `0x180050d8c`
- `0x180050dd4`
- `0x180050ea8`
- `0x180052b68`
- `0x180052ea8`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall WriteHorVCounters(__int64 a1, __int16 a2, int a3, unsigned int a4)
{
  int v4; // esi
  __int16 v5; // r12
  unsigned int v7; // r14d
  _QWORD *v8; // rdi
  __int64 v9; // rdx
  int v10; // ecx
  unsigned int v11; // esi
  __int64 v12; // r15
  unsigned int v13; // r13d
  __int64 v14; // r14
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // r11
  __int64 v18; // r11
  int v19; // edi
  int v20; // r13d
  __int64 v21; // r15
  unsigned int *v22; // r12
  unsigned int *v23; // r14
  bool v24; // zf
  int v27; // [rsp+24h] [rbp-DCh]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  unsigned int v31[20]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32[20]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v33[20]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = a3;
  v5 = a2;
  v7 = a4;
  memset_0(v31, 0, 0x44u);
  memset_0(v33, 0, 0x44u);
  memset_0(v32, 0, 0x44u);
  v8 = (_QWORD *)(a1 + 26080);
  if ( !*(_QWORD *)(a1 + 26080) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(a1 + 304))(
            a1 + 26080,
            18432,
            *(_QWORD *)(a1 + 312)) )
      XCF_FatalErrorHandler((_JBTYPE *)a1, 7);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 352))(*v8, 0, 18432);
  }
  v9 = *v8;
  v10 = v4;
  v29 = *v8;
  v27 = v4;
  if ( v4 )
  {
    v11 = v7;
    do
    {
      v12 = 0;
      *(_QWORD *)v31 = 0;
      if ( *(_WORD *)(a1 + 25816) )
      {
        v13 = v10 - 1;
        v14 = 0;
        do
        {
          if ( *(_WORD *)(a1 + 24 * v14 + 22760) == v5 )
          {
            v15 = *(_DWORD *)(a1 + 24 * v14 + 22764);
            if ( _bittest(&v15, v13) )
            {
              v16 = v29 + 144 * v12;
              PSVCopy(a1, (unsigned int *)v16, *(unsigned int **)(a1 + 24 * v14 + 22744));
              PSVCopy(a1, (unsigned int *)(v16 + 68), *(unsigned int **)(a1 + 8 * v17 + 22752));
              *(_WORD *)(v16 + 136) = *(_WORD *)(a1 + 8 * v18 + 22760);
              *(_DWORD *)(v16 + 140) = *(_DWORD *)(a1 + 8 * v18 + 22764);
              if ( *(_DWORD *)(a1 + 488) )
              {
                PStackValueAdd(a1, v33, (unsigned int *)(v29 + 144 * v12), (unsigned int *)(v16 + 68));
              }
              else
              {
                v33[1] = *(_DWORD *)(v16 + 4) + *(_DWORD *)(v16 + 72);
                v33[0] = 0;
              }
              PSVCopy(a1, v32, (unsigned int *)(v29 + 144 * v12));
              PSVSubtract(a1, (unsigned int *)(v29 + 144 * v12), v32, v31);
              PSVCopy(a1, v31, v33);
              v5 = a2;
              v12 = (unsigned int)(v12 + 1);
            }
          }
          v14 = (unsigned int)(v14 + 1);
        }
        while ( (unsigned int)v14 < *(unsigned __int16 *)(a1 + 25816) );
        v11 = a4;
        v10 = v27;
        v9 = v29;
      }
      v19 = v12 - 1;
      v20 = 1;
      if ( (int)v12 - 1 >= 0 )
      {
        v21 = v19;
        do
        {
          v22 = (unsigned int *)(144 * v21 + v9 + 68);
          v23 = (unsigned int *)(144 * v21 + v9);
          if ( v20 )
          {
            *(_QWORD *)v32 = 0;
            PSVSubtract(a1, v31, v32, (unsigned int *)(144 * v21 + v9 + 68));
            WriteReversedCounterArg(a1, v31, v11);
            if ( *(_DWORD *)(a1 + 488) )
            {
              PStackValueAdd(a1, v31, v23, v22);
            }
            else
            {
              v31[1] = v23[1] + v23[18];
              v31[0] = 0;
            }
            WriteReversedCounterArg(a1, v31, v11);
            v20 = 0;
          }
          else
          {
            WriteReversedCounterArg(a1, (unsigned int *)(144 * v21 + v9 + 68), v11);
            WriteReversedCounterArg(a1, v23, v11);
          }
          v9 = v29;
          --v21;
          --v19;
        }
        while ( v19 >= 0 );
        v10 = v27;
      }
      v9 = v29;
      v24 = v10-- == 1;
      v5 = a2;
      v27 = v10;
    }
    while ( !v24 );
    v4 = a3;
    v7 = a4;
  }
  v31[1] = v4 << 16;
  v31[0] = 0;
  return WriteReversedCounterArg(a1, v31, v7);
}

```

## disassembly

```asm
0x180052b68  push    rbp
0x180052b6a  push    rbx
0x180052b6b  push    rsi
0x180052b6c  push    rdi
0x180052b6d  push    r12
0x180052b6f  push    r13
0x180052b71  push    r14
0x180052b73  push    r15
0x180052b75  lea     rbp, [rsp-48h]
0x180052b7a  sub     rsp, 148h
0x180052b81  mov     rax, cs:__security_cookie
0x180052b88  xor     rax, rsp
0x180052b8b  mov     [rbp+80h+var_50], rax
0x180052b8f  mov     esi, r8d
0x180052b92  mov     [rsp+180h+var_148], r8d
0x180052b97  movzx   r12d, dx
0x180052b9b  mov     [rsp+180h+var_160], dx
0x180052ba0  mov     rbx, rcx
0x180052ba3  mov     [rsp+180h+var_158], r9d
0x180052ba8  mov     edi, 44h ; 'D'
0x180052bad  lea     rcx, [rsp+180h+var_140]; void *
0x180052bb2  mov     r8d, edi; Size
0x180052bb5  xor     edx, edx; Val
0x180052bb7  mov     r14d, r9d
0x180052bba  call    memset_0
0x180052bbf  mov     r8d, edi; Size
0x180052bc2  lea     rcx, [rbp+80h+var_A0]; void *
0x180052bc6  xor     edx, edx; Val
0x180052bc8  call    memset_0
0x180052bcd  mov     r8d, edi; Size
0x180052bd0  lea     rcx, [rbp+80h+var_F0]; void *
0x180052bd4  xor     edx, edx; Val
0x180052bd6  call    memset_0
0x180052bdb  lea     rdi, [rbx+65E0h]
0x180052be2  cmp     qword ptr [rdi], 0
0x180052be6  jnz     short loc_180052C23
0x180052be8  mov     r8, [rbx+138h]
0x180052bef  mov     r15d, 4800h
0x180052bf5  mov     rax, [rbx+130h]
0x180052bfc  mov     edx, r15d
0x180052bff  mov     rcx, rdi
0x180052c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c07  test    eax, eax
0x180052c09  jz      loc_180052E92
0x180052c0f  mov     rcx, [rdi]
0x180052c12  mov     r8d, r15d
0x180052c15  mov     rax, [rbx+160h]
0x180052c1c  xor     edx, edx
0x180052c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c23  mov     rdx, [rdi]
0x180052c26  mov     ecx, esi
0x180052c28  mov     [rsp+180h+var_150], rdx
0x180052c2d  mov     [rsp+180h+var_15C], ecx
0x180052c31  test    esi, esi
0x180052c33  jz      loc_180052E52
0x180052c39  mov     esi, r14d
0x180052c3c  xor     r15d, r15d
0x180052c3f  mov     qword ptr [rsp+180h+var_140], 0
0x180052c48  xor     eax, eax
0x180052c4a  cmp     ax, [rbx+64D8h]
0x180052c51  jnb     loc_180052D63
0x180052c57  mov     rsi, [rsp+180h+var_150]
0x180052c5c  lea     r13d, [rcx-1]
0x180052c60  xor     r14d, r14d
0x180052c63  lea     r11, [r14+r14*2]
0x180052c67  cmp     [rbx+r11*8+58E8h], r12w
0x180052c70  jnz     loc_180052D43
0x180052c76  mov     eax, [rbx+r11*8+58ECh]
0x180052c7e  bt      eax, r13d
0x180052c82  jnb     loc_180052D43
0x180052c88  mov     r8, [rbx+r11*8+58D8h]
0x180052c90  lea     rdi, [r15+r15*8]
0x180052c94  shl     rdi, 4
0x180052c98  mov     rcx, rbx
0x180052c9b  add     rdi, rsi
0x180052c9e  mov     rdx, rdi
0x180052ca1  call    PSVCopy
0x180052ca6  mov     r8, [rbx+r11*8+58E0h]
0x180052cae  lea     rdx, [rdi+44h]
0x180052cb2  mov     rcx, rbx
0x180052cb5  call    PSVCopy
0x180052cba  movzx   edx, word ptr [rbx+r11*8+58E8h]
0x180052cc3  mov     [rdi+88h], dx
0x180052cca  mov     eax, [rbx+r11*8+58ECh]
0x180052cd2  mov     [rdi+8Ch], eax
0x180052cd8  cmp     dword ptr [rbx+1E8h], 0
0x180052cdf  jnz     short loc_180052CF3
0x180052ce1  mov     eax, [rdi+48h]
0x180052ce4  add     eax, [rdi+4]
0x180052ce7  mov     [rbp+80h+var_9C], eax
0x180052cea  mov     [rbp+80h+var_A0], 0
0x180052cf1  jmp     short loc_180052D06
0x180052cf3  lea     r9, [rdi+44h]
0x180052cf7  mov     r8, rdi
0x180052cfa  lea     rdx, [rbp+80h+var_A0]
0x180052cfe  mov     rcx, rbx
0x180052d01  call    PStackValueAdd
0x180052d06  mov     r8, rdi
0x180052d09  lea     rdx, [rbp+80h+var_F0]
0x180052d0d  mov     rcx, rbx
0x180052d10  call    PSVCopy
0x180052d15  lea     r9, [rsp+180h+var_140]
0x180052d1a  mov     rcx, rbx
0x180052d1d  lea     r8, [rbp+80h+var_F0]
0x180052d21  mov     rdx, rdi
0x180052d24  call    PSVSubtract
0x180052d29  lea     r8, [rbp+80h+var_A0]
0x180052d2d  mov     rcx, rbx
0x180052d30  lea     rdx, [rsp+180h+var_140]
0x180052d35  call    PSVCopy
0x180052d3a  movzx   r12d, [rsp+180h+var_160]
0x180052d40  inc     r15d
0x180052d43  movzx   eax, word ptr [rbx+64D8h]
0x180052d4a  inc     r14d
0x180052d4d  cmp     r14d, eax
0x180052d50  jb      loc_180052C63
0x180052d56  mov     esi, [rsp+180h+var_158]
0x180052d5a  mov     ecx, [rsp+180h+var_15C]
0x180052d5e  mov     rdx, [rsp+180h+var_150]
0x180052d63  lea     edi, [r15-1]
0x180052d67  mov     r13d, 1
0x180052d6d  test    edi, edi
0x180052d6f  js      loc_180052E31
0x180052d75  movsxd  r15, edi
0x180052d78  lea     rax, [r15+r15*8]
0x180052d7c  mov     rcx, rbx
0x180052d7f  shl     rax, 4
0x180052d83  lea     r12, [rdx+44h]
0x180052d87  add     r12, rax
0x180052d8a  lea     r14, [rax+rdx]
0x180052d8e  test    r13d, r13d
0x180052d91  jz      short loc_180052E03
0x180052d93  mov     r9, r12
0x180052d96  mov     qword ptr [rbp+80h+var_F0], 0
0x180052d9e  lea     r8, [rbp+80h+var_F0]
0x180052da2  lea     rdx, [rsp+180h+var_140]
0x180052da7  call    PSVSubtract
0x180052dac  mov     r8d, esi
0x180052daf  lea     rdx, [rsp+180h+var_140]
0x180052db4  mov     rcx, rbx
0x180052db7  call    WriteReversedCounterArg
0x180052dbc  cmp     dword ptr [rbx+1E8h], 0
0x180052dc3  jnz     short loc_180052DDB
0x180052dc5  mov     eax, [r14+48h]
0x180052dc9  add     eax, [r14+4]
0x180052dcd  mov     [rsp+180h+var_140+4], eax
0x180052dd1  mov     [rsp+180h+var_140], 0
0x180052dd9  jmp     short loc_180052DEE
0x180052ddb  mov     r9, r12
0x180052dde  lea     rdx, [rsp+180h+var_140]
0x180052de3  mov     r8, r14
0x180052de6  mov     rcx, rbx
0x180052de9  call    PStackValueAdd
0x180052dee  mov     r8d, esi
0x180052df1  lea     rdx, [rsp+180h+var_140]
0x180052df6  mov     rcx, rbx
0x180052df9  call    WriteReversedCounterArg
0x180052dfe  xor     r13d, r13d
0x180052e01  jmp     short loc_180052E1C
0x180052e03  mov     r8d, esi
0x180052e06  mov     rdx, r12
0x180052e09  call    WriteReversedCounterArg
0x180052e0e  mov     r8d, esi
0x180052e11  mov     rdx, r14
0x180052e14  mov     rcx, rbx
0x180052e17  call    WriteReversedCounterArg
0x180052e1c  mov     rdx, [rsp+180h+var_150]
0x180052e21  dec     r15
0x180052e24  sub     edi, 1
0x180052e27  jns     loc_180052D78
0x180052e2d  mov     ecx, [rsp+180h+var_15C]
0x180052e31  mov     rdx, [rsp+180h+var_150]
0x180052e36  add     ecx, 0FFFFFFFFh
0x180052e39  movzx   r12d, [rsp+180h+var_160]
0x180052e3f  mov     [rsp+180h+var_15C], ecx
0x180052e43  jnz     loc_180052C3C
0x180052e49  mov     esi, [rsp+180h+var_148]
0x180052e4d  mov     r14d, [rsp+180h+var_158]
0x180052e52  shl     esi, 10h
0x180052e55  lea     rdx, [rsp+180h+var_140]
0x180052e5a  mov     r8d, r14d
0x180052e5d  mov     [rsp+180h+var_140+4], esi
0x180052e61  mov     rcx, rbx
0x180052e64  mov     [rsp+180h+var_140], 0
0x180052e6c  call    WriteReversedCounterArg
0x180052e71  mov     rcx, [rbp+80h+var_50]
0x180052e75  xor     rcx, rsp; StackCookie
0x180052e78  call    __security_check_cookie
0x180052e7d  add     rsp, 148h
0x180052e84  pop     r15
0x180052e86  pop     r14
0x180052e88  pop     r13
0x180052e8a  pop     r12
0x180052e8c  pop     rdi
0x180052e8d  pop     rsi
0x180052e8e  pop     rbx
0x180052e8f  pop     rbp
0x180052e90  retn
0x180052e92  mov     edx, 7
0x180052e97  mov     rcx, rbx
0x180052e9a  call    XCF_FatalErrorHandler
```
