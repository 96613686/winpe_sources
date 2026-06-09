# _com_error::_com_error(_com_error const &)

- ea: `0x1800153f8`
- end: `0x180015444`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `76`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800153f8`
- `0x180018010`

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
0x1800153f8  push    rbx
0x1800153fa  sub     rsp, 30h
0x1800153fe  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015407  mov     rbx, rcx
0x18001540a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180015411  mov     [rcx], rax
0x180015414  mov     eax, [rdx+8]
0x180015417  mov     [rcx+8], eax
0x18001541a  mov     rcx, [rdx+10h]
0x18001541e  mov     [rbx+10h], rcx
0x180015422  mov     qword ptr [rbx+18h], 0
0x18001542a  test    rcx, rcx
0x18001542d  jz      short loc_18001543B
0x18001542f  mov     rax, [rcx]
0x180015432  mov     rax, [rax+8]
0x180015436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543b  mov     rax, rbx
0x18001543e  add     rsp, 30h
0x180015442  pop     rbx
0x180015443  retn
```
