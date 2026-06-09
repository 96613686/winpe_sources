# _com_error::_com_error(_com_error const &)

- ea: `0x140008c2c`
- end: `0x140008c70`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `68`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008c2c`
- `0x14001a010`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, const struct _com_error *a2)
{
  __int64 v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v3 = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 2) = v3;
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return this;
}

```

## disassembly

```asm
0x140008c2c  push    rbx
0x140008c2e  sub     rsp, 20h
0x140008c32  mov     rbx, rcx
0x140008c35  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140008c3c  mov     [rcx], rax
0x140008c3f  mov     eax, [rdx+8]
0x140008c42  mov     [rcx+8], eax
0x140008c45  mov     rcx, [rdx+10h]
0x140008c49  mov     [rbx+10h], rcx
0x140008c4d  mov     qword ptr [rbx+18h], 0
0x140008c55  test    rcx, rcx
0x140008c58  jz      short loc_140008C66
0x140008c5a  mov     rax, [rcx]
0x140008c5d  mov     rax, [rax+8]
0x140008c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c66  mov     rax, rbx
0x140008c69  add     rsp, 20h
0x140008c6d  pop     rbx
0x140008c6e  retn
```
