# CMPEG2Parser::CalcDuration(CParseReader *)

- ea: `0x1800076c0`
- end: `0x1800077e1`
- name: `?CalcDuration@CMPEG2Parser@@AEAAXPEAVCParseReader@@@Z`
- size: `289`
- prototype: `void __fastcall(CMPEG2Parser *__hidden this, struct CParseReader *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008750`

## callees

- `0x180001048`
- `0x180001054`
- `0x1800076c0`
- `0x180007f6c`
- `0x180034010`

## pseudocode

```c
void __fastcall CMPEG2Parser::CalcDuration(CMPEG2Parser *this, struct CParseReader *a2)
{
  unsigned __int8 *v4; // rbp
  int v5; // eax
  bool v6; // zf
  int v7; // eax
  __int64 v8; // rdi
  unsigned int i; // esi
  int v10; // [rsp+30h] [rbp-38h]
  int v11; // [rsp+70h] [rbp+8h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  *((_QWORD *)this + 148) = *((_QWORD *)this + 143);
  v4 = (unsigned __int8 *)operator new[](0x100000u);
  if ( v4 )
  {
    v5 = (**(__int64 (__fastcall ***)(struct CParseReader *, char *))a2)(a2, (char *)this + 1160);
    v6 = v5 == 0;
    if ( v5 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct CParseReader *, __int64))(*(_QWORD *)a2 + 8LL))(
             a2,
             *((_QWORD *)this + 145) - 0x100000LL);
      v6 = v7 == 0;
      if ( v7 >= 0 )
        v6 = (*(unsigned int (__fastcall **)(struct CParseReader *, unsigned __int8 *, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v4,
               0x100000) == 0;
    }
    if ( v6 )
    {
      v8 = 0;
      for ( i = 0; i < 0x100000; i += v12 + v11 )
      {
        v11 = 0;
        v12 = 0;
        v13 = 0;
        if ( (int)CMPEG2Parser::FindTimeStamp(this, &v4[i], 0x100000 - i, &v11, &v13, &v12, v10) < 0 )
          break;
        v8 = v13;
      }
      if ( v8 > *((_QWORD *)this + 143) )
        *((_QWORD *)this + 144) = v8;
    }
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x1800076c0  push    rbx
0x1800076c2  push    rbp
0x1800076c3  push    rsi
0x1800076c4  push    rdi
0x1800076c5  push    r15
0x1800076c7  sub     rsp, 40h
0x1800076cb  mov     rax, [rcx+478h]
0x1800076d2  mov     rbx, rcx
0x1800076d5  mov     [rcx+4A0h], rax
0x1800076dc  mov     r15d, 100000h
0x1800076e2  mov     ecx, r15d; unsigned __int64
0x1800076e5  mov     rdi, rdx
0x1800076e8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800076ed  mov     rbp, rax
0x1800076f0  test    rax, rax
0x1800076f3  jz      loc_1800077D6
0x1800076f9  mov     rdx, [rdi]
0x1800076fc  lea     rsi, [rbx+488h]
0x180007703  mov     rcx, rdi
0x180007706  mov     rax, [rdx]
0x180007709  mov     rdx, rsi
0x18000770c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007711  test    eax, eax
0x180007713  js      short loc_180007745
0x180007715  mov     rax, [rdi]
0x180007718  mov     rcx, rdi
0x18000771b  mov     rdx, [rsi]
0x18000771e  sub     rdx, r15
0x180007721  mov     rax, [rax+8]
0x180007725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000772a  test    eax, eax
0x18000772c  js      short loc_180007745
0x18000772e  mov     rax, [rdi]
0x180007731  mov     r8d, r15d
0x180007734  mov     rdx, rbp
0x180007737  mov     rcx, rdi
0x18000773a  mov     rax, [rax+10h]
0x18000773e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007743  test    eax, eax
0x180007745  jnz     loc_1800077CE
0x18000774b  xor     edi, edi
0x18000774d  xor     esi, esi
0x18000774f  lea     rax, [rsp+68h+arg_10]
0x180007757  mov     edx, esi
0x180007759  mov     [rsp+68h+var_40], rax; int *
0x18000775e  lea     r9, [rsp+68h+arg_0]; int *
0x180007763  mov     r8d, r15d
0x180007766  mov     [rsp+68h+arg_0], 0
0x18000776e  lea     rax, [rsp+68h+arg_18]
0x180007776  mov     [rsp+68h+arg_10], 0
0x180007781  sub     r8d, esi; int
0x180007784  mov     [rsp+68h+var_48], rax; __int64 *
0x180007789  add     rdx, rbp; unsigned __int8 *
0x18000778c  mov     [rsp+68h+arg_18], 0
0x180007798  mov     rcx, rbx; this
0x18000779b  call    ?FindTimeStamp@CMPEG2Parser@@AEAAJPEBEJPEAJPEA_J1H@Z; CMPEG2Parser::FindTimeStamp(uchar const *,long,long *,__int64 *,long *,int)
0x1800077a0  test    eax, eax
0x1800077a2  js      short loc_1800077BE
0x1800077a4  mov     ecx, [rsp+68h+arg_0]
0x1800077a8  add     ecx, [rsp+68h+arg_10]
0x1800077af  mov     rdi, [rsp+68h+arg_18]
0x1800077b7  add     esi, ecx
0x1800077b9  cmp     esi, r15d
0x1800077bc  jb      short loc_18000774F
0x1800077be  cmp     rdi, [rbx+478h]
0x1800077c5  jle     short loc_1800077CE
0x1800077c7  mov     [rbx+480h], rdi
0x1800077ce  mov     rcx, rbp; void *
0x1800077d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800077d6  add     rsp, 40h
0x1800077da  pop     r15
0x1800077dc  pop     rdi
0x1800077dd  pop     rsi
0x1800077de  pop     rbp
0x1800077df  pop     rbx
0x1800077e0  retn
```
