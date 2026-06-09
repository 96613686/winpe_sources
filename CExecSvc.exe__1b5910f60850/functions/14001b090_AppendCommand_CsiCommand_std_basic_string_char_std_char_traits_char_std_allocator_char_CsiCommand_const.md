# AppendCommand<CsiCommand>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,CsiCommand const &)

- ea: `0x14001b090`
- end: `0x14001b0f0`
- name: `??$AppendCommand@UCsiCommand@@@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUCsiCommand@@@Z`
- size: `96`
- prototype: `void *__fastcall(_QWORD *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bad0`

## callees

- `0x140004061`
- `0x14001b090`
- `0x14001b24c`

## pseudocode

```c
void *__fastcall AppendCommand<CsiCommand>(_QWORD *a1, unsigned __int8 *a2)
{
  __int64 v2; // r8
  size_t v3; // rdi
  bool v4; // cc
  char *v5; // rbx
  void *result; // rax

  v2 = a1[2];
  v3 = a2[27];
  if ( v3 > a1[3] - v2 )
    return (void *)std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                     a1,
                     a2[27]);
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
0x14001b090  mov     [rsp+arg_0], rbx
0x14001b095  push    rdi
0x14001b096  sub     rsp, 30h
0x14001b09a  mov     r8, [rcx+10h]
0x14001b09e  mov     rax, [rcx+18h]
0x14001b0a2  movzx   edi, byte ptr [rdx+1Bh]
0x14001b0a6  sub     rax, r8
0x14001b0a9  cmp     rdi, rax
0x14001b0ac  ja      short loc_14001B0D5
0x14001b0ae  cmp     qword ptr [rcx+18h], 0Fh
0x14001b0b3  lea     rax, [r8+rdi]
0x14001b0b7  mov     [rcx+10h], rax
0x14001b0bb  jbe     short loc_14001B0C0
0x14001b0bd  mov     rcx, [rcx]
0x14001b0c0  lea     rbx, [r8+rcx]
0x14001b0c4  mov     r8, rdi; Size
0x14001b0c7  mov     rcx, rbx; void *
0x14001b0ca  call    memmove_0
0x14001b0cf  mov     byte ptr [rbx+rdi], 0
0x14001b0d3  jmp     short loc_14001B0E5
0x14001b0d5  mov     r9, rdx
0x14001b0d8  mov     [rsp+38h+Size], rdi; Size
0x14001b0dd  mov     rdx, rdi
0x14001b0e0  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14001b0e5  mov     rbx, [rsp+38h+arg_0]
0x14001b0ea  add     rsp, 30h
0x14001b0ee  pop     rdi
0x14001b0ef  retn
```
