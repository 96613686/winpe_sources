# _CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__list__

- ea: `0x18000a610`
- end: `0x18000a65b`
- name: `_CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__list__`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019e0`
- `0x18000a610`

## pseudocode

```c
void __fastcall CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__list__()
{
  _QWORD **v0; // rcx
  _QWORD *v1; // rcx
  _QWORD *v2; // rbx

  v0 = (_QWORD **)qword_180010610;
  **((_QWORD **)qword_180010610 + 1) = 0;
  v1 = *v0;
  if ( v1 )
  {
    do
    {
      v2 = (_QWORD *)*v1;
      operator delete(v1);
      v1 = v2;
    }
    while ( v2 );
  }
  operator delete(qword_180010610);
}

```

## disassembly

```asm
0x18000a610  push    rbx
0x18000a612  sub     rsp, 20h
0x18000a616  mov     rcx, cs:qword_180010610
0x18000a61d  mov     rax, [rcx+8]
0x18000a621  mov     qword ptr [rax], 0
0x18000a628  mov     rcx, [rcx]; void *
0x18000a62b  test    rcx, rcx
0x18000a62e  jz      short loc_18000A645
0x18000a630  mov     rbx, [rcx]
0x18000a633  mov     edx, 18h; unsigned __int64
0x18000a638  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a63d  mov     rcx, rbx
0x18000a640  test    rbx, rbx
0x18000a643  jnz     short loc_18000A630
0x18000a645  mov     rcx, cs:qword_180010610; void *
0x18000a64c  mov     edx, 18h; unsigned __int64
0x18000a651  add     rsp, 20h
0x18000a655  pop     rbx
0x18000a656  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
