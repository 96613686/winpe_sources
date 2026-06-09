# CspHandleRawRead

- ea: `0x14001e20c`
- end: `0x14001e36c`
- name: `CspHandleRawRead`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001e628`

## callees

- `0x14001e20c`
- `0x14001e5f4`
- `0x14001f07c`
- `0x14002074c`

## pseudocode

```c
char __fastcall CspHandleRawRead(_DWORD *a1, __int64 a2, char a3, _WORD *a4)
{
  bool v4; // cf
  __int64 v5; // r8
  __int64 v6; // rdi
  unsigned int v7; // eax
  unsigned int v8; // ebp
  __int64 v10; // rax
  __int64 v11; // rsi
  int v12; // eax
  __int64 v13; // r8
  bool v14; // zf

  v4 = a3 != 0;
  v5 = (unsigned int)a1[34];
  v6 = a2;
  v7 = *(_DWORD *)(a2 + 128) - v5 - *(_DWORD *)(a2 + 40);
  v8 = v4 + 1;
  while ( v7 >= v8 )
  {
    v10 = (unsigned int)a1[36];
    if ( a1[35] == (_DWORD)v10 )
      break;
    if ( LOWORD(a1[5 * v10 + 114]) != 1 )
      goto LABEL_8;
    v11 = 5 * ((unsigned int)v10 + 23LL);
    if ( !a1[5 * (unsigned int)v10 + 115] )
      goto LABEL_8;
    a4 = (_WORD *)&a1[5 * (unsigned int)v10 + 117] + 1;
    if ( !*a4 )
      goto LABEL_8;
    a1[32] = a1[5 * (unsigned int)v10 + 118];
    v12 = WriteMessageOutput((_DWORD)a1, v6, v5, (_DWORD)a4, v8);
    if ( v12 < 0 )
    {
      *(_DWORD *)(v6 + 8) = v12;
      CspResetInputEventIfEmpty(a1, a2, v13, a4);
      goto LABEL_13;
    }
    a1[34] += v8;
    v14 = LOWORD(a1[v11 + 1])-- == 1;
    v5 = (unsigned int)a1[34];
    if ( v14 )
    {
LABEL_8:
      a2 = ((unsigned int)(a1[36] + 1) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
      a1[36] = a1[36] + 1 - 100 * ((a2 + (((unsigned __int64)(unsigned int)(a1[36] + 1) - a2) >> 1)) >> 6);
    }
    v7 = *(_DWORD *)(v6 + 128) - *(_DWORD *)(v6 + 40) - v5;
  }
  CspResetInputEventIfEmpty(a1, a2, v5, a4);
  if ( a1[34] )
  {
    *(_DWORD *)(v6 + 8) = 0;
    *(_QWORD *)(v6 + 16) = (unsigned int)a1[34];
    *(_DWORD *)(v6 + 156) = a1[32];
    *(_DWORD *)(v6 + 160) = a1[34];
LABEL_13:
    CspCompleteConsoleIo(a1, v6);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e20c  push    rbx
0x14001e20e  push    rbp
0x14001e20f  push    rsi
0x14001e210  push    rdi
0x14001e211  push    r14
0x14001e213  push    r15
0x14001e215  sub     rsp, 38h
0x14001e219  mov     eax, [rdx+80h]
0x14001e21f  neg     r8b
0x14001e222  mov     r8d, [rcx+88h]
0x14001e229  mov     r15d, 1
0x14001e22f  sbb     ebp, ebp
0x14001e231  mov     rdi, rdx
0x14001e234  neg     ebp
0x14001e236  sub     eax, r8d
0x14001e239  sub     eax, [rdx+28h]
0x14001e23c  add     ebp, r15d
0x14001e23f  xor     r14d, r14d
0x14001e242  mov     rbx, rcx
0x14001e245  jmp     loc_14001E301
0x14001e24a  mov     eax, [rbx+90h]
0x14001e250  cmp     [rbx+8Ch], eax
0x14001e256  jz      loc_14001E309
0x14001e25c  mov     ecx, eax
0x14001e25e  lea     rax, [rax+rax*4]
0x14001e262  cmp     [rbx+rax*4+1C8h], r15w
0x14001e26b  jnz     short loc_14001E2C3
0x14001e26d  lea     rsi, [rcx+17h]
0x14001e271  lea     rsi, [rsi+rsi*4]
0x14001e275  cmp     [rbx+rsi*4], r14d
0x14001e279  jz      short loc_14001E2C3
0x14001e27b  lea     r9, [rbx+0Ah]
0x14001e27f  lea     r9, [r9+rsi*4]
0x14001e283  cmp     [r9], r14w
0x14001e287  jz      short loc_14001E2C3
0x14001e289  mov     eax, [rbx+rsi*4+0Ch]
0x14001e28d  mov     rdx, rdi
0x14001e290  mov     rcx, rbx
0x14001e293  mov     [rbx+80h], eax
0x14001e299  mov     [rsp+68h+var_48], ebp
0x14001e29d  call    WriteMessageOutput
0x14001e2a2  test    eax, eax
0x14001e2a4  js      loc_14001E350
0x14001e2aa  add     [rbx+88h], ebp
0x14001e2b0  mov     eax, 0FFFFh
0x14001e2b5  add     [rbx+rsi*4+4], ax
0x14001e2ba  mov     r8d, [rbx+88h]
0x14001e2c1  jnz     short loc_14001E2F5
0x14001e2c3  mov     ecx, [rbx+90h]
0x14001e2c9  mov     rax, 47AE147AE147AE15h
0x14001e2d3  add     ecx, r15d
0x14001e2d6  mul     rcx
0x14001e2d9  mov     eax, ecx
0x14001e2db  sub     rax, rdx
0x14001e2de  shr     rax, 1
0x14001e2e1  add     rax, rdx
0x14001e2e4  shr     rax, 6
0x14001e2e8  imul    rax, 64h ; 'd'
0x14001e2ec  sub     rcx, rax
0x14001e2ef  mov     [rbx+90h], ecx
0x14001e2f5  mov     eax, [rdi+80h]
0x14001e2fb  sub     eax, [rdi+28h]
0x14001e2fe  sub     eax, r8d
0x14001e301  cmp     eax, ebp
0x14001e303  jnb     loc_14001E24A
0x14001e309  mov     rcx, rbx
0x14001e30c  call    CspResetInputEventIfEmpty
0x14001e311  cmp     [rbx+88h], r14d
0x14001e318  jbe     short loc_14001E35D
0x14001e31a  mov     [rdi+8], r14d
0x14001e31e  mov     eax, [rbx+88h]
0x14001e324  mov     [rdi+10h], rax
0x14001e328  mov     eax, [rbx+80h]
0x14001e32e  mov     [rdi+9Ch], eax
0x14001e334  mov     eax, [rbx+88h]
0x14001e33a  mov     [rdi+0A0h], eax
0x14001e340  mov     rdx, rdi
0x14001e343  mov     rcx, rbx
0x14001e346  call    CspCompleteConsoleIo
0x14001e34b  mov     al, r15b
0x14001e34e  jmp     short loc_14001E35F
0x14001e350  mov     rcx, rbx
0x14001e353  mov     [rdi+8], eax
0x14001e356  call    CspResetInputEventIfEmpty
0x14001e35b  jmp     short loc_14001E340
0x14001e35d  xor     al, al
0x14001e35f  add     rsp, 38h
0x14001e363  pop     r15
0x14001e365  pop     r14
0x14001e367  pop     rdi
0x14001e368  pop     rsi
0x14001e369  pop     rbp
0x14001e36a  pop     rbx
0x14001e36b  retn
```
