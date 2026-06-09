# av_opt_copy

- ea: `0x1800454e0`
- end: `0x180045593`
- name: `av_opt_copy`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800454e0`
- `0x180048b40`
- `0x180048c50`

## pseudocode

```c
__int64 __fastcall av_opt_copy(_QWORD *a1, __int64 a2)
{
  _QWORD *v2; // rbx
  unsigned int v3; // esi
  _QWORD *v6; // rdx
  _QWORD *v7; // rax
  bool v8; // zf
  __int64 v9; // rax
  char *v10; // r8
  __int64 v11; // r9
  unsigned int v12; // eax
  int v13; // eax

  v2 = 0;
  v3 = 0;
  if ( a2 && *(_QWORD *)a2 && *(_QWORD *)a2 == *a1 )
  {
    while ( 1 )
    {
      if ( v2 )
      {
        v7 = v2 + 8;
        v8 = v2[8] == 0;
        v2 += 8;
        if ( v8 )
          return v3;
        v6 = v7;
        if ( !v7 )
          return v3;
      }
      else
      {
        if ( !*(_QWORD *)a2 )
          return v3;
        v2 = *(_QWORD **)(*(_QWORD *)a2 + 16LL);
        if ( !v2 || !*v2 )
          return v3;
        v6 = *(_QWORD **)(*(_QWORD *)a2 + 16LL);
      }
      v9 = *((int *)v6 + 4);
      v10 = (char *)a1 + v9;
      v11 = v9 + a2;
      v12 = *((_DWORD *)v6 + 5);
      if ( (v12 & 0x10000) != 0 )
        v13 = sub_180048B40(a1, v6, v10, v11);
      else
        v13 = sub_180048C50(a1, v12, v10, v11);
      if ( v13 >= 0 )
        v13 = v3;
      v3 = v13;
    }
  }
  return 4294967274LL;
}

```

## disassembly

```asm
0x1800454e0  mov     [rsp+arg_0], rbx
0x1800454e5  mov     [rsp+arg_8], rbp
0x1800454ea  mov     [rsp+arg_10], rsi
0x1800454ef  push    rdi
0x1800454f0  sub     rsp, 20h
0x1800454f4  xor     ebx, ebx
0x1800454f6  xor     esi, esi
0x1800454f8  mov     rdi, rdx
0x1800454fb  mov     rbp, rcx
0x1800454fe  test    rdx, rdx
0x180045501  jz      short loc_180045579
0x180045503  mov     rax, [rdx]
0x180045506  test    rax, rax
0x180045509  jz      short loc_180045579
0x18004550b  cmp     rax, [rcx]
0x18004550e  jnz     short loc_180045579
0x180045510  test    rbx, rbx
0x180045513  jnz     short loc_180045531
0x180045515  mov     rbx, [rdi]
0x180045518  test    rbx, rbx
0x18004551b  jz      short loc_180045575
0x18004551d  mov     rbx, [rbx+10h]
0x180045521  test    rbx, rbx
0x180045524  jz      short loc_180045575
0x180045526  cmp     qword ptr [rbx], 0
0x18004552a  jz      short loc_180045575
0x18004552c  mov     rdx, rbx
0x18004552f  jmp     short loc_180045546
0x180045531  lea     rax, [rbx+40h]
0x180045535  cmp     qword ptr [rax], 0
0x180045539  mov     rbx, rax
0x18004553c  jz      short loc_180045575
0x18004553e  mov     rdx, rax
0x180045541  test    rax, rax
0x180045544  jz      short loc_180045575
0x180045546  movsxd  rax, dword ptr [rdx+10h]
0x18004554a  mov     rcx, rbp
0x18004554d  lea     r8, [rax+rbp]
0x180045551  lea     r9, [rax+rdi]
0x180045555  mov     eax, [rdx+14h]
0x180045558  bt      eax, 10h
0x18004555c  jnb     short loc_180045565
0x18004555e  call    sub_180048B40
0x180045563  jmp     short loc_18004556C
0x180045565  mov     edx, eax
0x180045567  call    sub_180048C50
0x18004556c  test    eax, eax
0x18004556e  cmovns  eax, esi
0x180045571  mov     esi, eax
0x180045573  jmp     short loc_180045510
0x180045575  mov     eax, esi
0x180045577  jmp     short loc_18004557E
0x180045579  mov     eax, 0FFFFFFEAh
0x18004557e  mov     rbx, [rsp+28h+arg_0]
0x180045583  mov     rbp, [rsp+28h+arg_8]
0x180045588  mov     rsi, [rsp+28h+arg_10]
0x18004558d  add     rsp, 20h
0x180045591  pop     rdi
0x180045592  retn
```
