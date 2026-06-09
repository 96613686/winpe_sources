# _com_error::_com_error(_com_error const &)

- ea: `0x140009484`
- end: `0x1400094c7`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140009484`
- `0x14000a010`

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
0x140009484  push    rbx
0x140009486  sub     rsp, 20h
0x14000948a  mov     rbx, rcx
0x14000948d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140009494  mov     [rcx], rax
0x140009497  mov     eax, [rdx+8]
0x14000949a  mov     [rcx+8], eax
0x14000949d  mov     rcx, [rdx+10h]
0x1400094a1  mov     [rbx+10h], rcx
0x1400094a5  mov     qword ptr [rbx+18h], 0
0x1400094ad  test    rcx, rcx
0x1400094b0  jz      short loc_1400094BE
0x1400094b2  mov     rax, [rcx]
0x1400094b5  mov     rax, [rax+8]
0x1400094b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094be  mov     rax, rbx
0x1400094c1  add     rsp, 20h
0x1400094c5  pop     rbx
0x1400094c6  retn
```
