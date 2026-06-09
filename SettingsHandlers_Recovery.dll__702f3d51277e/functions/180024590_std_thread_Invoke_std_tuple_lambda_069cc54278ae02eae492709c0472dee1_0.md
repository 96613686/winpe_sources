# std::thread::_Invoke_std::tuple__lambda_069cc54278ae02eae492709c0472dee1____0_

- ea: `0x180024590`
- end: `0x1800245be`
- name: `std::thread::_Invoke_std::tuple__lambda_069cc54278ae02eae492709c0472dee1____0_`
- size: `46`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000282c`
- `0x180024590`
- `0x180024974`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002459e`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002459e`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_069cc54278ae02eae492709c0472dee1____0_(void *Block)
{
  lambda_069cc54278ae02eae492709c0472dee1_::operator()();
  _Cnd_do_broadcast_at_thread_exit();
  if ( Block )
    operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x180024590  push    rbx
0x180024592  sub     rsp, 20h
0x180024596  mov     rbx, rcx
0x180024599  call    _lambda_069cc54278ae02eae492709c0472dee1___operator__
0x18002459e  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x1800245a4  test    rbx, rbx
0x1800245a7  jz      short loc_1800245B6
0x1800245a9  mov     edx, 18h
0x1800245ae  mov     rcx, rbx; Block
0x1800245b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800245b6  xor     eax, eax
0x1800245b8  add     rsp, 20h
0x1800245bc  pop     rbx
0x1800245bd  retn
```
