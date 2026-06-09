# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180002320`
- end: `0x180002370`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `80`
- prototype: `void __fastcall(ATL::CAtlComModule *this, unsigned __int8)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fd4`
- `0x180002070`
- `0x180002130`

## callees

- `0x180002320`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, unsigned __int8 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 i; // rcx

  v2 = qword_180012950;
  for ( i = qword_180012958; v2 < i; v2 += 8LL )
  {
    if ( *(_QWORD *)v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 64LL))(a2);
      i = qword_180012958;
    }
  }
}

```

## disassembly

```asm
0x180002320  mov     [rsp+arg_0], rbx
0x180002325  push    rdi
0x180002326  sub     rsp, 20h
0x18000232a  mov     rbx, cs:qword_180012950
0x180002331  movzx   edi, dl
0x180002334  mov     rcx, cs:qword_180012958
0x18000233b  cmp     rbx, rcx
0x18000233e  jnb     short loc_180002365
0x180002340  mov     rax, [rbx]
0x180002343  test    rax, rax
0x180002346  jz      short loc_18000235C
0x180002348  mov     rax, [rax+40h]
0x18000234c  movzx   ecx, dil
0x180002350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002355  mov     rcx, cs:qword_180012958
0x18000235c  add     rbx, 8
0x180002360  cmp     rbx, rcx
0x180002363  jb      short loc_180002340
0x180002365  mov     rbx, [rsp+28h+arg_0]
0x18000236a  add     rsp, 20h
0x18000236e  pop     rdi
0x18000236f  retn
```
