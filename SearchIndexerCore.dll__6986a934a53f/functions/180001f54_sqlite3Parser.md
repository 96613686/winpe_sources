# sqlite3Parser

- ea: `0x180001f54`
- end: `0x18000207e`
- name: `sqlite3Parser`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021404`

## callees

- `0x180001214`
- `0x180001edc`
- `0x180001f54`
- `0x180002090`
- `0x18000213c`
- `0x180011bcc`
- `0x18006d7c8`
- `0x1800a6c80`

## string_xrefs

- `0x180002055`: `incomplete input`

## pseudocode

```c
__int64 __fastcall sqlite3Parser(__int64 *a1, unsigned int a2, __int128 *a3)
{
  _QWORD *v4; // r14
  unsigned __int16 i; // ax
  __int64 result; // rax
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v13[3]; // [rsp+40h] [rbp-38h] BYREF

  v4 = (_QWORD *)a1[1];
  for ( i = *(_WORD *)*a1; ; i = yy_reduce(a1, v9, a2, (__int64 *)&v12, v4) )
  {
    result = yy_find_shift_action((unsigned __int16)a2, i);
    if ( (unsigned __int16)result < 0x4EDu )
      break;
    v9 = (unsigned int)(unsigned __int16)result - 1261;
    if ( !*((_BYTE *)qword_1800B4CA0 + v9) && *a1 >= (unsigned __int64)a1[2] && (unsigned int)yyGrowStack(a1) )
      return yyStackOverflow(a1);
    v12 = *a3;
  }
  if ( (unsigned __int16)result > 0x4E9u )
  {
    v11 = a1[1];
    if ( (_WORD)result == 1259 )
    {
      *a1 -= 24;
      a1[1] = v11;
    }
    else
    {
      v10 = a1[1];
      v12 = *a3;
      v13[0] = v12;
      if ( *(_BYTE *)v12 )
        sqlite3ErrorMsg(v10, "near \"%T\": syntax error", &v12);
      else
        sqlite3ErrorMsg(v10, "incomplete input");
      a1[1] = v11;
      return yy_destructor(a1, (unsigned __int16)a2, v13);
    }
  }
  else
  {
    v12 = *a3;
    return yy_shift(a1, (unsigned __int16)result, (unsigned __int16)a2, &v12);
  }
  return result;
}

```

## disassembly

```asm
0x180001f54  push    rbx
0x180001f56  push    rbp
0x180001f57  push    rsi
0x180001f58  push    rdi
0x180001f59  push    r14
0x180001f5b  sub     rsp, 50h
0x180001f5f  mov     rax, [rcx]
0x180001f62  mov     rsi, r8
0x180001f65  mov     r14, [rcx+8]
0x180001f69  mov     ebp, edx
0x180001f6b  mov     rbx, rcx
0x180001f6e  movzx   eax, word ptr [rax]
0x180001f71  movzx   edx, ax
0x180001f74  movzx   ecx, bp
0x180001f77  call    yy_find_shift_action
0x180001f7c  mov     ecx, 4EDh
0x180001f81  cmp     ax, cx
0x180001f84  jb      short loc_180001FBE
0x180001f86  movzx   edi, ax
0x180001f89  lea     rcx, qword_1800B4CA0
0x180001f90  add     edi, 0FFFFFB13h
0x180001f96  cmp     byte ptr [rdi+rcx], 0
0x180001f9a  jz      short loc_180001FF4
0x180001f9c  movups  xmm0, xmmword ptr [rsi]
0x180001f9f  lea     r9, [rsp+78h+var_48]
0x180001fa4  mov     [rsp+78h+var_58], r14
0x180001fa9  mov     r8d, ebp
0x180001fac  mov     edx, edi
0x180001fae  mov     rcx, rbx
0x180001fb1  movdqu  [rsp+78h+var_48], xmm0
0x180001fb7  call    yy_reduce
0x180001fbc  jmp     short loc_180001F71
0x180001fbe  mov     ecx, 4E9h
0x180001fc3  cmp     ax, cx
0x180001fc6  ja      loc_180002063
0x180001fcc  movups  xmm0, xmmword ptr [rsi]
0x180001fcf  lea     r9, [rsp+78h+var_48]
0x180001fd4  movzx   r8d, bp
0x180001fd8  movzx   edx, ax
0x180001fdb  mov     rcx, rbx
0x180001fde  movdqu  [rsp+78h+var_48], xmm0
0x180001fe4  call    yy_shift
0x180001fe9  add     rsp, 50h
0x180001fed  pop     r14
0x180001fef  pop     rdi
0x180001ff0  pop     rsi
0x180001ff1  pop     rbp
0x180001ff2  pop     rbx
0x180001ff3  retn
0x180001ff4  mov     rax, [rbx+10h]
0x180001ff8  cmp     [rbx], rax
0x180001ffb  jb      short loc_180001F9C
0x180001ffd  mov     rcx, rbx
0x180002000  call    yyGrowStack
0x180002005  test    eax, eax
0x180002007  jz      short loc_180001F9C
0x180002009  mov     rcx, rbx
0x18000200c  call    yyStackOverflow
0x180002011  jmp     short loc_180001FE9
0x180002013  movups  xmm0, xmmword ptr [rsi]
0x180002016  mov     rcx, rdi
0x180002019  movq    rax, xmm0
0x18000201e  movaps  [rsp+78h+var_48], xmm0
0x180002023  movdqu  [rsp+78h+var_38], xmm0
0x180002029  cmp     byte ptr [rax], 0
0x18000202c  jz      short loc_180002055
0x18000202e  lea     r8, [rsp+78h+var_48]
0x180002033  lea     rdx, aNearTSyntaxErr; "near \"%T\": syntax error"
0x18000203a  call    sqlite3ErrorMsg
0x18000203f  lea     r8, [rsp+78h+var_38]
0x180002044  mov     [rbx+8], rdi
0x180002048  movzx   edx, bp
0x18000204b  mov     rcx, rbx
0x18000204e  call    yy_destructor
0x180002053  jmp     short loc_180001FE9
0x180002055  lea     rdx, aIncompleteInpu; "incomplete input"
0x18000205c  call    sqlite3ErrorMsg
0x180002061  jmp     short loc_18000203F
0x180002063  mov     rdi, [rbx+8]
0x180002067  mov     ecx, 4EBh
0x18000206c  cmp     ax, cx
0x18000206f  jnz     short loc_180002013
0x180002071  add     qword ptr [rbx], 0FFFFFFFFFFFFFFE8h
0x180002075  mov     [rbx+8], rdi
0x180002079  jmp     loc_180001FE9
```
