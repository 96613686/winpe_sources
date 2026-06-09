# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180008120`
- end: `0x180008170`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `80`
- prototype: `void __fastcall(ATL::CAtlComModule *this, unsigned __int8)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008010`
- `0x180008040`
- `0x180008080`

## callees

- `0x180008120`
- `0x18001b010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, unsigned __int8 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 i; // rcx

  v2 = qword_180026AD0;
  for ( i = qword_180026AD8; v2 < i; v2 += 8LL )
  {
    if ( *(_QWORD *)v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 64LL))(a2);
      i = qword_180026AD8;
    }
  }
}

```

## disassembly

```asm
0x180008120  mov     [rsp+arg_0], rbx
0x180008125  push    rdi
0x180008126  sub     rsp, 20h
0x18000812a  mov     rbx, cs:qword_180026AD0
0x180008131  movzx   edi, dl
0x180008134  mov     rcx, cs:qword_180026AD8
0x18000813b  cmp     rbx, rcx
0x18000813e  jnb     short loc_180008165
0x180008140  mov     rax, [rbx]
0x180008143  test    rax, rax
0x180008146  jz      short loc_18000815C
0x180008148  mov     rax, [rax+40h]
0x18000814c  movzx   ecx, dil
0x180008150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008155  mov     rcx, cs:qword_180026AD8
0x18000815c  add     rbx, 8
0x180008160  cmp     rbx, rcx
0x180008163  jb      short loc_180008140
0x180008165  mov     rbx, [rsp+28h+arg_0]
0x18000816a  add     rsp, 20h
0x18000816e  pop     rdi
0x18000816f  retn
```
