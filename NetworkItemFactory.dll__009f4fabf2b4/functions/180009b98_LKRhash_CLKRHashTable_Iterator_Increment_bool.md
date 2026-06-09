# LKRhash::CLKRHashTable_Iterator::_Increment(bool)

- ea: `0x180009b98`
- end: `0x180009c6f`
- name: `?_Increment@CLKRHashTable_Iterator@LKRhash@@IEAA_N_N@Z`
- size: `215`
- prototype: `bool __fastcall(LKRhash::CLKRHashTable_Iterator *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004524`
- `0x180007f80`

## callees

- `0x180003090`
- `0x180008070`
- `0x180009b98`
- `0x180009c78`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LKRhash::CLKRHashTable_Iterator::_Increment(LKRhash::CLKRHashTable_Iterator *this, char a2)
{
  _QWORD *v3; // rdi
  __int16 v4; // cx
  __int64 v5; // rdx
  __int64 v6; // rax
  char result; // al
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  __int16 v9; // [rsp+34h] [rbp-14h]

  v3 = (_QWORD *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1)
    || (LKRhash::CLKRLinearHashTable_Iterator::_Increment((LKRhash::CLKRHashTable_Iterator *)((char *)this + 8), a2),
        !*v3) )
  {
    v4 = *((_WORD *)this + 16) + 1;
    *((_WORD *)this + 16) = v4;
    v5 = *(_QWORD *)this;
    if ( v4 >= *(_DWORD *)(*(_QWORD *)this + 20LL) )
    {
LABEL_9:
      *(_QWORD *)this = 0;
      result = 0;
      *((_WORD *)this + 16) = 0;
      return result;
    }
    while ( 1 )
    {
      v6 = LKRhash::CLKRLinearHashTable::Begin(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 8LL * v4), (__int64)v8);
      LKRhash::CLKRLinearHashTable_Iterator::operator=(v3, v6);
      if ( v8[0] )
      {
        if ( v9 != -1 )
          (*(void (__fastcall **)(_QWORD, __int64))(v8[0] + 56LL))(*(_QWORD *)(v8[1] + 8LL * v9 + 24), 0xFFFFFFFFLL);
      }
      if ( *v3 )
        break;
      v4 = *((_WORD *)this + 16) + 1;
      *((_WORD *)this + 16) = v4;
      v5 = *(_QWORD *)this;
      if ( v4 >= *(_DWORD *)(*(_QWORD *)this + 20LL) )
        goto LABEL_9;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180009b98  mov     [rsp+arg_0], rbx
0x180009b9d  mov     [rsp+arg_8], rsi
0x180009ba2  push    rdi
0x180009ba3  sub     rsp, 40h
0x180009ba7  mov     sil, dl
0x180009baa  mov     rbx, rcx
0x180009bad  lea     rdi, [rcx+8]
0x180009bb1  cmp     qword ptr [rdi], 0
0x180009bb5  jz      short loc_180009BC9
0x180009bb7  mov     rcx, rdi; this
0x180009bba  call    ?_Increment@CLKRLinearHashTable_Iterator@LKRhash@@IEAA_N_N@Z; LKRhash::CLKRLinearHashTable_Iterator::_Increment(bool)
0x180009bbf  cmp     qword ptr [rdi], 0
0x180009bc3  jnz     loc_180009C6B
0x180009bc9  movzx   ecx, word ptr [rbx+20h]
0x180009bcd  inc     cx
0x180009bd0  mov     [rbx+20h], cx
0x180009bd4  mov     rdx, [rbx]
0x180009bd7  movsx   eax, cx
0x180009bda  cmp     eax, [rdx+14h]
0x180009bdd  jge     short loc_180009C4E
0x180009bdf  or      esi, 0FFFFFFFFh
0x180009be2  movsx   rax, cx
0x180009be6  mov     rcx, [rdx+18h]
0x180009bea  lea     rdx, [rsp+48h+var_28]
0x180009bef  mov     rcx, [rcx+rax*8]
0x180009bf3  call    ?Begin@CLKRLinearHashTable@LKRhash@@QEAA?AVCLKRLinearHashTable_Iterator@2@XZ; LKRhash::CLKRLinearHashTable::Begin(void)
0x180009bf8  nop
0x180009bf9  mov     rdx, rax
0x180009bfc  mov     rcx, rdi
0x180009bff  call    ??4CLKRLinearHashTable_Iterator@LKRhash@@QEAAAEAV01@AEBV01@@Z; LKRhash::CLKRLinearHashTable_Iterator::operator=(LKRhash::CLKRLinearHashTable_Iterator const &)
0x180009c04  nop
0x180009c05  mov     rax, [rsp+48h+var_28]
0x180009c0a  test    rax, rax
0x180009c0d  jz      short loc_180009C32
0x180009c0f  cmp     [rsp+48h+var_14], si
0x180009c14  jz      short loc_180009C32
0x180009c16  movsx   r8, [rsp+48h+var_14]
0x180009c1c  mov     edx, esi
0x180009c1e  mov     rcx, [rsp+48h+var_20]
0x180009c23  mov     rcx, [rcx+r8*8+18h]
0x180009c28  mov     rax, [rax+38h]
0x180009c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c31  nop
0x180009c32  cmp     qword ptr [rdi], 0
0x180009c36  jnz     short loc_180009C6B
0x180009c38  movzx   ecx, word ptr [rbx+20h]
0x180009c3c  inc     cx
0x180009c3f  mov     [rbx+20h], cx
0x180009c43  mov     rdx, [rbx]
0x180009c46  movsx   eax, cx
0x180009c49  cmp     eax, [rdx+14h]
0x180009c4c  jl      short loc_180009BE2
0x180009c4e  mov     qword ptr [rbx], 0
0x180009c55  xor     eax, eax
0x180009c57  mov     [rbx+20h], ax
0x180009c5b  mov     rbx, [rsp+48h+arg_0]
0x180009c60  mov     rsi, [rsp+48h+arg_8]
0x180009c65  add     rsp, 40h
0x180009c69  pop     rdi
0x180009c6a  retn
0x180009c6b  mov     al, 1
0x180009c6d  jmp     short loc_180009C5B
```
