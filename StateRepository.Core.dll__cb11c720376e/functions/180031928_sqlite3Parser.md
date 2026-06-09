# sqlite3Parser

- ea: `0x180031928`
- end: `0x180031b32`
- name: `sqlite3Parser`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180030d98`

## callees

- `0x180031928`
- `0x180031b38`
- `0x18005dae0`
- `0x180060ce8`
- `0x180064ddc`
- `0x180099520`

## string_xrefs

- `0x180031b0c`: `incomplete input`

## pseudocode

```c
__int16 __fastcall sqlite3Parser(__int64 *a1, unsigned int a2, __int128 *a3)
{
  _QWORD *v3; // rsi
  unsigned __int16 i; // di
  __int64 v8; // r9
  unsigned __int16 v9; // cx
  int v10; // r10d
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int128 v14; // xmm6
  __int16 result; // ax
  unsigned __int64 v16; // rdi
  int v17; // eax
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int128 v20; // [rsp+30h] [rbp-78h] BYREF
  __int128 v21; // [rsp+40h] [rbp-68h] BYREF

  v3 = (_QWORD *)a1[1];
  for ( i = *(_WORD *)*a1; ; i = yy_reduce(a1, v12, a2, (__int64 *)&v20, v3) )
  {
    if ( i <= 0x246u )
    {
      v8 = i;
      v9 = a2;
      v10 = (unsigned __int16)word_1800A9FF0[i];
      while ( 1 )
      {
        v11 = (unsigned int)v9 + v10;
        if ( word_1800A8D30[v11] == v9 )
        {
          i = word_1800A7BE0[v11];
          goto LABEL_6;
        }
        if ( !word_1800AA480[v9] )
          break;
        v9 = word_1800AA480[v9];
      }
      v16 = (unsigned int)v9 + v10 - (unsigned __int64)v9;
      if ( word_1800A8DFC[v16] == 102 && v9 )
        i = word_1800A7CAC[v16];
      else
        i = word_1800A6A90[v8];
    }
LABEL_6:
    if ( i < 0x4E9u )
      break;
    v12 = (unsigned int)i - 1257;
    if ( !byte_1800A70F0[v12] && *a1 >= (unsigned __int64)a1[2] && (unsigned int)yyGrowStack(a1) )
      return yyStackOverflow(a1);
    v20 = *a3;
  }
  if ( i > 0x4E5u )
  {
    v18 = a1[1];
    result = 1255;
    if ( i == 1255 )
    {
      *a1 -= 24;
      a1[1] = v18;
    }
    else
    {
      v19 = a1[1];
      v20 = *a3;
      v21 = v20;
      if ( *(_BYTE *)v20 )
        sqlite3ErrorMsg(v19, "near \"%T\": syntax error", &v20);
      else
        sqlite3ErrorMsg(v19, "incomplete input");
      a1[1] = v18;
      return yy_destructor(a1, (unsigned __int16)a2, &v21);
    }
  }
  else
  {
    *a1 += 24;
    v13 = *a1;
    v14 = *a3;
    if ( *a1 > (unsigned __int64)a1[2] )
    {
      v17 = yyGrowStack(a1);
      v13 = *a1;
      if ( v17 )
      {
        *a1 = v13 - 24;
        return yyStackOverflow(a1);
      }
    }
    *(_WORD *)(v13 + 2) = a2;
    result = i + 412;
    *(_OWORD *)(v13 + 8) = v14;
    if ( i <= 0x246u )
      result = i;
    *(_WORD *)v13 = result;
  }
  return result;
}

```

## disassembly

```asm
0x180031928  push    rbx
0x18003192a  push    rbp
0x18003192b  push    rsi
0x18003192c  push    rdi
0x18003192d  push    r12
0x18003192f  push    r13
0x180031931  push    r14
0x180031933  push    r15
0x180031935  sub     rsp, 68h
0x180031939  mov     rax, [rcx]
0x18003193c  lea     r15, cs:180000000h
0x180031943  mov     rsi, [rcx+8]
0x180031947  mov     rbp, r8
0x18003194a  movaps  [rsp+0A8h+var_58], xmm6
0x18003194f  mov     r14d, edx
0x180031952  mov     rbx, rcx
0x180031955  mov     r13d, 246h
0x18003195b  movzx   edi, word ptr [rax]
0x18003195e  xor     r12d, r12d
0x180031961  cmp     di, r13w
0x180031965  ja      short loc_18003199A
0x180031967  movzx   r9d, di
0x18003196b  movzx   ecx, r14w
0x18003196f  movzx   r10d, ds:rva word_1800A9FF0[r15+r9*2]
0x180031978  movzx   r8d, cx
0x18003197c  lea     eax, [r8+r10]
0x180031980  mov     edi, eax
0x180031982  cmp     ds:rva word_1800A8D30[r15+rax*2], cx
0x18003198b  jnz     loc_180031A50
0x180031991  movzx   edi, ds:rva word_1800A7BE0[r15+rax*2]
0x18003199a  mov     eax, 4E9h
0x18003199f  cmp     di, ax
0x1800319a2  jb      short loc_1800319DD
0x1800319a4  movzx   edi, di
0x1800319a7  add     edi, 0FFFFFB17h
0x1800319ad  cmp     [rdi+r15+0A70F0h], r12b
0x1800319b5  jz      short loc_180031A32
0x1800319b7  movups  xmm0, xmmword ptr [rbp+0]
0x1800319bb  lea     r9, [rsp+0A8h+var_78]
0x1800319c0  mov     [rsp+0A8h+var_88], rsi
0x1800319c5  mov     r8d, r14d
0x1800319c8  mov     edx, edi
0x1800319ca  mov     rcx, rbx
0x1800319cd  movdqu  [rsp+0A8h+var_78], xmm0
0x1800319d3  call    yy_reduce
0x1800319d8  movzx   edi, ax
0x1800319db  jmp     short loc_180031961
0x1800319dd  mov     eax, 4E5h
0x1800319e2  cmp     di, ax
0x1800319e5  ja      loc_180031AC2
0x1800319eb  add     qword ptr [rbx], 18h
0x1800319ef  mov     rcx, [rbx]
0x1800319f2  movups  xmm6, xmmword ptr [rbp+0]
0x1800319f6  cmp     rcx, [rbx+10h]
0x1800319fa  ja      loc_180031AAD
0x180031a00  mov     eax, 19Ch
0x180031a05  mov     [rcx+2], r14w
0x180031a0a  add     eax, edi
0x180031a0c  cmp     di, r13w
0x180031a10  movdqu  xmmword ptr [rcx+8], xmm6
0x180031a15  cmovbe  ax, di
0x180031a19  mov     [rcx], ax
0x180031a1c  movaps  xmm6, [rsp+0A8h+var_58]
0x180031a21  add     rsp, 68h
0x180031a25  pop     r15
0x180031a27  pop     r14
0x180031a29  pop     r13
0x180031a2b  pop     r12
0x180031a2d  pop     rdi
0x180031a2e  pop     rsi
0x180031a2f  pop     rbp
0x180031a30  pop     rbx
0x180031a31  retn
0x180031a32  mov     rax, [rbx+10h]
0x180031a36  cmp     [rbx], rax
0x180031a39  jb      loc_1800319B7
0x180031a3f  mov     rcx, rbx
0x180031a42  call    yyGrowStack
0x180031a47  test    eax, eax
0x180031a49  jnz     short loc_180031AA0
0x180031a4b  jmp     loc_1800319B7
0x180031a50  movzx   eax, cx
0x180031a53  movzx   edx, ds:rva word_1800AA480[r15+rax*2]
0x180031a5c  test    dx, dx
0x180031a5f  jnz     short loc_180031A7E
0x180031a61  sub     rdi, r8
0x180031a64  cmp     ds:rva word_1800A8DFC[r15+rdi*2], 66h ; 'f'
0x180031a6e  jz      short loc_180031A86
0x180031a70  movzx   edi, ds:rva word_1800A6A90[r15+r9*2]
0x180031a79  jmp     loc_18003199A
0x180031a7e  movzx   ecx, dx
0x180031a81  jmp     loc_180031978
0x180031a86  test    cx, cx
0x180031a89  jz      short loc_180031A70
0x180031a8b  movzx   edi, ds:rva word_1800A7CAC[r15+rdi*2]
0x180031a94  jmp     loc_18003199A
0x180031a99  lea     rax, [rcx-18h]
0x180031a9d  mov     [rbx], rax
0x180031aa0  mov     rcx, rbx
0x180031aa3  call    yyStackOverflow
0x180031aa8  jmp     loc_180031A1C
0x180031aad  mov     rcx, rbx
0x180031ab0  call    yyGrowStack
0x180031ab5  mov     rcx, [rbx]
0x180031ab8  test    eax, eax
0x180031aba  jz      loc_180031A00
0x180031ac0  jmp     short loc_180031A99
0x180031ac2  mov     rsi, [rbx+8]
0x180031ac6  mov     eax, 4E7h
0x180031acb  cmp     di, ax
0x180031ace  jnz     short loc_180031ADD
0x180031ad0  add     qword ptr [rbx], 0FFFFFFFFFFFFFFE8h
0x180031ad4  mov     [rbx+8], rsi
0x180031ad8  jmp     loc_180031A1C
0x180031add  movups  xmm0, xmmword ptr [rbp+0]
0x180031ae1  mov     rcx, rsi
0x180031ae4  movq    rax, xmm0
0x180031ae9  movaps  [rsp+0A8h+var_78], xmm0
0x180031aee  movdqu  [rsp+0A8h+var_68], xmm0
0x180031af4  cmp     [rax], r12b
0x180031af7  jz      short loc_180031B0C
0x180031af9  lea     r8, [rsp+0A8h+var_78]
0x180031afe  lea     rdx, aNearTSyntaxErr; "near \"%T\": syntax error"
0x180031b05  call    sqlite3ErrorMsg
0x180031b0a  jmp     short loc_180031B18
0x180031b0c  lea     rdx, aIncompleteInpu; "incomplete input"
0x180031b13  call    sqlite3ErrorMsg
0x180031b18  lea     r8, [rsp+0A8h+var_68]
0x180031b1d  mov     [rbx+8], rsi
0x180031b21  movzx   edx, r14w
0x180031b25  mov     rcx, rbx
0x180031b28  call    yy_destructor
0x180031b2d  jmp     loc_180031A1C
```
