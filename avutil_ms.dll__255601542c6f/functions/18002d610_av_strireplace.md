# av_strireplace

- ea: `0x18002d610`
- end: `0x18002d70d`
- name: `av_strireplace`
- size: `253`
- prototype: `__int64 __fastcall(char *Str, char *, char *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18002d610`
- `0x18002d770`
- `0x18002e490`
- `0x18002e790`
- `0x18002e8c0`
- `0x180078c1a`
- `0x180078e90`

## pseudocode

```c
__int64 __fastcall av_strireplace(char *Str, char *a2, char *a3)
{
  unsigned int v6; // r14d
  size_t v7; // r15
  __int64 v8; // rax
  __int64 v9; // rdi
  size_t v10; // rax
  __int64 v12; // [rsp+20h] [rbp-448h] BYREF
  _BYTE v13[8]; // [rsp+30h] [rbp-438h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-430h]
  unsigned int v15; // [rsp+3Ch] [rbp-42Ch]

  v12 = 0;
  v6 = strlen(a3);
  v7 = strlen(a2);
  av_bprint_init(v13, 1, 0xFFFFFFFFLL);
  while ( 1 )
  {
    v8 = av_stristr(Str, a2);
    v9 = v8;
    if ( !v8 )
      break;
    av_bprint_append_data(v13, Str, (unsigned int)(v8 - (_DWORD)Str));
    Str = (char *)(v9 + v7);
    av_bprint_append_data(v13, a3, v6);
  }
  v10 = strlen(Str);
  av_bprint_append_data(v13, Str, v10);
  av_bprint_finalize(v13, (unsigned __int64)&v12 & -(__int64)(v14 < v15));
  return v12;
}

```

## disassembly

```asm
0x18002d610  mov     [rsp+arg_18], rbx
0x18002d615  push    rbp
0x18002d616  push    rsi
0x18002d617  push    rdi
0x18002d618  push    r14
0x18002d61a  push    r15
0x18002d61c  sub     rsp, 440h
0x18002d623  mov     rax, cs:__security_cookie
0x18002d62a  xor     rax, rsp
0x18002d62d  mov     [rsp+468h+var_38], rax
0x18002d635  mov     rbx, rcx
0x18002d638  mov     [rsp+468h+var_448], 0
0x18002d641  mov     rcx, r8; Str
0x18002d644  mov     rbp, r8
0x18002d647  mov     rsi, rdx
0x18002d64a  call    strlen
0x18002d64f  mov     rcx, rsi; Str
0x18002d652  mov     r14, rax
0x18002d655  call    strlen
0x18002d65a  or      r8d, 0FFFFFFFFh
0x18002d65e  lea     rcx, [rsp+468h+var_438]
0x18002d663  mov     edx, 1
0x18002d668  mov     r15, rax
0x18002d66b  call    av_bprint_init
0x18002d670  jmp     short loc_18002D699
0x18002d672  mov     r8d, edi
0x18002d675  lea     rcx, [rsp+468h+var_438]
0x18002d67a  sub     r8d, ebx
0x18002d67d  mov     rdx, rbx
0x18002d680  call    av_bprint_append_data
0x18002d685  mov     r8d, r14d
0x18002d688  lea     rcx, [rsp+468h+var_438]
0x18002d68d  mov     rdx, rbp
0x18002d690  lea     rbx, [rdi+r15]
0x18002d694  call    av_bprint_append_data
0x18002d699  mov     rdx, rsi
0x18002d69c  mov     rcx, rbx
0x18002d69f  call    av_stristr
0x18002d6a4  mov     rdi, rax
0x18002d6a7  test    rax, rax
0x18002d6aa  jnz     short loc_18002D672
0x18002d6ac  mov     rcx, rbx; Str
0x18002d6af  call    strlen
0x18002d6b4  mov     r8, rax
0x18002d6b7  lea     rcx, [rsp+468h+var_438]
0x18002d6bc  mov     rdx, rbx
0x18002d6bf  call    av_bprint_append_data
0x18002d6c4  mov     eax, [rsp+468h+var_42C]
0x18002d6c8  lea     rcx, [rsp+468h+var_438]
0x18002d6cd  cmp     [rsp+468h+var_430], eax
0x18002d6d1  lea     rax, [rsp+468h+var_448]
0x18002d6d6  sbb     rdx, rdx
0x18002d6d9  and     rdx, rax
0x18002d6dc  call    av_bprint_finalize
0x18002d6e1  mov     rax, [rsp+468h+var_448]
0x18002d6e6  mov     rcx, [rsp+468h+var_38]
0x18002d6ee  xor     rcx, rsp; StackCookie
0x18002d6f1  call    __security_check_cookie
0x18002d6f6  mov     rbx, [rsp+468h+arg_18]
0x18002d6fe  add     rsp, 440h
0x18002d705  pop     r15
0x18002d707  pop     r14
0x18002d709  pop     rdi
0x18002d70a  pop     rsi
0x18002d70b  pop     rbp
0x18002d70c  retn
```
