# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const * const)

- ea: `0x140002ed4`
- end: `0x140002fec`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z`
- size: `280`
- prototype: `char *__fastcall(char *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003188`

## callees

- `0x140002408`
- `0x140002ed4`
- `0x14000fa80`
- `0x14000fa8c`

## pseudocode

```c
char *__fastcall std::wstring::replace(char *a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  char *v7; // rcx

  v4 = a3;
  v5 = *((_QWORD *)a1 + 2);
  if ( v5 < a3 )
    v4 = v5;
  if ( v4 )
  {
    v6 = v5 - v4;
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v7 = a1;
    else
      v7 = *(char **)a1;
    memmove_0(v7, &v7[2 * v4], 2 * v6 + 2);
    *((_QWORD *)a1 + 2) = v6;
  }
  return a1;
}

```

## disassembly

```asm
0x140002ed4  push    rbx
0x140002ed6  push    rsi
0x140002ed7  push    rdi
0x140002ed8  push    r12
0x140002eda  push    r14
0x140002edc  push    r15
0x140002ede  sub     rsp, 48h
0x140002ee2  mov     rdi, rcx
0x140002ee5  mov     r9, r8
0x140002ee8  mov     rcx, [rcx+10h]
0x140002eec  cmp     rcx, r8
0x140002eef  cmovb   r9, rcx
0x140002ef3  test    r9, r9
0x140002ef6  jz      loc_140002FDB
0x140002efc  mov     rdx, [rdi+18h]
0x140002f00  mov     rbx, rcx
0x140002f03  sub     rbx, r9
0x140002f06  test    r9, r9
0x140002f09  jz      short loc_140002F33
0x140002f0b  cmp     rdx, 7
0x140002f0f  jbe     short loc_140002F16
0x140002f11  mov     rcx, [rdi]
0x140002f14  jmp     short loc_140002F19
0x140002f16  mov     rcx, rdi; void *
0x140002f19  lea     r8, ds:2[rbx*2]; Size
0x140002f21  lea     rdx, [rcx+r9*2]; Src
0x140002f25  call    memmove_0
0x140002f2a  mov     [rdi+10h], rbx
0x140002f2e  jmp     loc_140002FDB
0x140002f33  mov     r14, r9
0x140002f36  mov     rax, rdx
0x140002f39  neg     r14
0x140002f3c  sub     rax, rcx
0x140002f3f  cmp     r14, rax
0x140002f42  ja      short loc_140002FBF
0x140002f44  lea     rax, [rcx+r14]
0x140002f48  mov     [rdi+10h], rax
0x140002f4c  cmp     rdx, 7
0x140002f50  jbe     short loc_140002F57
0x140002f52  mov     r15, [rdi]
0x140002f55  jmp     short loc_140002F5A
0x140002f57  mov     r15, rdi
0x140002f5a  lea     r12, qword_140012EF0
0x140002f61  lea     rdx, [r15+r9*2]; Src
0x140002f65  cmp     r12, r15
0x140002f68  jbe     short loc_140002F83
0x140002f6a  lea     rax, [r15+rcx*2]
0x140002f6e  cmp     r12, rax
0x140002f71  ja      short loc_140002F83
0x140002f73  cmp     rdx, r12
0x140002f76  jbe     short loc_140002F83
0x140002f78  mov     rsi, rdx
0x140002f7b  sub     rsi, r12
0x140002f7e  sar     rsi, 1
0x140002f81  jmp     short loc_140002F85
0x140002f83  xor     esi, esi
0x140002f85  lea     r8, ds:2[rbx*2]; Size
0x140002f8d  lea     rcx, [rdx+r14*2]; void *
0x140002f91  call    memmove_0
0x140002f96  lea     rbx, [rsi+rsi]
0x140002f9a  mov     rdx, r12; Src
0x140002f9d  mov     r8, rbx; Size
0x140002fa0  mov     rcx, r15; void *
0x140002fa3  call    memmove_0
0x140002fa8  lea     rax, [r14+rsi]
0x140002fac  imul    r8, rsi, -2; Size
0x140002fb0  lea     rdx, [r12+rax*2]; Src
0x140002fb4  lea     rcx, [rbx+r15]; void *
0x140002fb8  call    memcpy_0
0x140002fbd  jmp     short loc_140002FDB
0x140002fbf  mov     [rsp+78h+var_48], 0
0x140002fc8  mov     rdx, r14
0x140002fcb  mov     rcx, rdi
0x140002fce  mov     [rsp+78h+var_58], r9
0x140002fd3  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x140002fd8  mov     rdi, rax
0x140002fdb  mov     rax, rdi
0x140002fde  add     rsp, 48h
0x140002fe2  pop     r15
0x140002fe4  pop     r14
0x140002fe6  pop     r12
0x140002fe8  pop     rdi
0x140002fe9  pop     rsi
0x140002fea  pop     rbx
0x140002feb  retn
```
