# CSpltBaseParser::NewInitBuffer(uchar * *,uint,CParseReader *)

- ea: `0x18000d148`
- end: `0x18000d246`
- name: `?NewInitBuffer@CSpltBaseParser@@IEAAIPEAPEAEIPEAVCParseReader@@@Z`
- size: `254`
- prototype: `unsigned int __fastcall(CSpltBaseParser *__hidden this, unsigned __int8 **, unsigned int, struct CParseReader *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008750`
- `0x18000a870`
- `0x18000f010`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000d148`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CSpltBaseParser::NewInitBuffer(
        CSpltBaseParser *this,
        unsigned __int8 **a2,
        unsigned int a3,
        int (__fastcall ***a4)(struct CParseReader *, unsigned __int64 *))
{
  signed __int64 v4; // rdi
  int (__fastcall **v7)(struct CParseReader *, unsigned __int64 *); // rax
  int (__fastcall **v8)(struct CParseReader *, unsigned __int64 *); // rax
  unsigned __int8 *v9; // rbp
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  CSpltBaseParser *v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v13 = this;
  v4 = a3;
  if ( a2 )
  {
    v7 = *a4;
    *a2 = 0;
    v13 = 0;
    if ( v7[4]((struct CParseReader *)a4, (unsigned __int64 *)&v13) >= 0 )
    {
      v8 = *a4;
      v14 = 0;
      if ( (*v8)((struct CParseReader *)a4, &v14) >= 0 && (v14 & 0x8000000000000000uLL) == 0LL )
      {
        if ( (__int64)v14 < v4 )
          LODWORD(v4) = v14;
        v9 = (unsigned __int8 *)operator new[]((unsigned int)v4);
        if ( v9 )
        {
          v10 = 0;
          while ( 1 )
          {
            v11 = v4;
            if ( (__int64)v13 < (unsigned int)v4 )
              v11 = (unsigned int)v13;
            if ( ((unsigned int (__fastcall *)(int (__fastcall ***)(struct CParseReader *, unsigned __int64 *), unsigned __int8 *, _QWORD))(*a4)[2])(
                   a4,
                   v9,
                   v11 - v10) )
            {
              break;
            }
            v10 = v11;
            if ( v11 >= (unsigned int)v4 )
              goto LABEL_13;
          }
          if ( v10 >= (__int64)v13 )
          {
LABEL_13:
            *a2 = v9;
            return v10;
          }
          operator delete(v9);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d148  mov     r11, rsp
0x18000d14b  mov     [r11+18h], rbx
0x18000d14f  mov     [r11+20h], rbp
0x18000d153  mov     [r11+8], rcx
0x18000d157  push    rsi
0x18000d158  push    rdi
0x18000d159  push    r12
0x18000d15b  push    r14
0x18000d15d  push    r15
0x18000d15f  sub     rsp, 20h
0x18000d163  mov     edi, r8d
0x18000d166  mov     rsi, r9
0x18000d169  mov     r14, rdx
0x18000d16c  test    rdx, rdx
0x18000d16f  jz      loc_18000D22D
0x18000d175  mov     rax, [r9]
0x18000d178  mov     rcx, r9
0x18000d17b  mov     qword ptr [rdx], 0
0x18000d182  lea     rdx, [r11+8]
0x18000d186  mov     qword ptr [r11+8], 0
0x18000d18e  mov     rax, [rax+20h]
0x18000d192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d197  test    eax, eax
0x18000d199  js      loc_18000D22D
0x18000d19f  mov     rax, [rsi]
0x18000d1a2  lea     rdx, [rsp+48h+arg_8]
0x18000d1a7  mov     rcx, rsi
0x18000d1aa  mov     [rsp+48h+arg_8], 0
0x18000d1b3  mov     rax, [rax]
0x18000d1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1bb  test    eax, eax
0x18000d1bd  js      short loc_18000D22D
0x18000d1bf  mov     rcx, [rsp+48h+arg_8]
0x18000d1c4  test    rcx, rcx
0x18000d1c7  js      short loc_18000D22D
0x18000d1c9  cmp     rcx, rdi
0x18000d1cc  cmovl   edi, ecx
0x18000d1cf  mov     ecx, edi; unsigned __int64
0x18000d1d1  mov     r12d, edi
0x18000d1d4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d1d9  mov     rbp, rax
0x18000d1dc  test    rax, rax
0x18000d1df  jz      short loc_18000D22D
0x18000d1e1  xor     ebx, ebx
0x18000d1e3  cmp     [rsp+48h+arg_0], r12
0x18000d1e8  mov     r15, r12
0x18000d1eb  mov     rax, [rsi]
0x18000d1ee  mov     rdx, rbp
0x18000d1f1  cmovl   r15, [rsp+48h+arg_0]
0x18000d1f7  mov     rcx, rsi
0x18000d1fa  mov     r8d, r15d
0x18000d1fd  sub     r8d, ebx
0x18000d200  mov     rax, [rax+10h]
0x18000d204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d209  test    eax, eax
0x18000d20b  jnz     short loc_18000D21C
0x18000d20d  mov     ebx, r15d
0x18000d210  cmp     r15d, edi
0x18000d213  jb      short loc_18000D1E3
0x18000d215  mov     [r14], rbp
0x18000d218  mov     eax, ebx
0x18000d21a  jmp     short loc_18000D22F
0x18000d21c  mov     eax, ebx
0x18000d21e  cmp     rax, [rsp+48h+arg_0]
0x18000d223  jge     short loc_18000D215
0x18000d225  mov     rcx, rbp; void *
0x18000d228  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d22d  xor     eax, eax
0x18000d22f  mov     rbx, [rsp+48h+arg_10]
0x18000d234  mov     rbp, [rsp+48h+arg_18]
0x18000d239  add     rsp, 20h
0x18000d23d  pop     r15
0x18000d23f  pop     r14
0x18000d241  pop     r12
0x18000d243  pop     rdi
0x18000d244  pop     rsi
0x18000d245  retn
```
