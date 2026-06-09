# AppendCommand<CsiSmallCommand>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,CsiSmallCommand const &)

- ea: `0x14001b0f8`
- end: `0x14001b158`
- name: `??$AppendCommand@UCsiSmallCommand@@@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUCsiSmallCommand@@@Z`
- size: `96`
- prototype: `void *__fastcall(_QWORD *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bad0`

## callees

- `0x140004061`
- `0x14001b0f8`
- `0x14001b24c`

## pseudocode

```c
void *__fastcall AppendCommand<CsiSmallCommand>(_QWORD *a1, unsigned __int8 *a2)
{
  __int64 v2; // r8
  size_t v3; // rdi
  bool v4; // cc
  char *v5; // rbx
  void *result; // rax

  v2 = a1[2];
  v3 = a2[4];
  if ( v3 > a1[3] - v2 )
    return (void *)std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                     a1,
                     a2[4]);
  v4 = a1[3] <= 0xFu;
  a1[2] = v2 + v3;
  if ( !v4 )
    a1 = (_QWORD *)*a1;
  v5 = (char *)a1 + v2;
  result = memmove_0((char *)a1 + v2, a2, v3);
  v5[v3] = 0;
  return result;
}

```

## disassembly

```asm
0x14001b0f8  mov     [rsp+arg_0], rbx
0x14001b0fd  push    rdi
0x14001b0fe  sub     rsp, 30h
0x14001b102  mov     r8, [rcx+10h]
0x14001b106  mov     rax, [rcx+18h]
0x14001b10a  movzx   edi, byte ptr [rdx+4]
0x14001b10e  sub     rax, r8
0x14001b111  cmp     rdi, rax
0x14001b114  ja      short loc_14001B13D
0x14001b116  cmp     qword ptr [rcx+18h], 0Fh
0x14001b11b  lea     rax, [r8+rdi]
0x14001b11f  mov     [rcx+10h], rax
0x14001b123  jbe     short loc_14001B128
0x14001b125  mov     rcx, [rcx]
0x14001b128  lea     rbx, [r8+rcx]
0x14001b12c  mov     r8, rdi; Size
0x14001b12f  mov     rcx, rbx; void *
0x14001b132  call    memmove_0
0x14001b137  mov     byte ptr [rbx+rdi], 0
0x14001b13b  jmp     short loc_14001B14D
0x14001b13d  mov     r9, rdx
0x14001b140  mov     [rsp+38h+Size], rdi; Size
0x14001b145  mov     rdx, rdi
0x14001b148  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14001b14d  mov     rbx, [rsp+38h+arg_0]
0x14001b152  add     rsp, 30h
0x14001b156  pop     rdi
0x14001b157  retn
```
