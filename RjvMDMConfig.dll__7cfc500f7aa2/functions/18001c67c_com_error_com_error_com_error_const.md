# _com_error::_com_error(_com_error const &)

- ea: `0x18001c67c`
- end: `0x18001c6c0`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `68`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001c67c`
- `0x18001e010`

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
0x18001c67c  push    rbx
0x18001c67e  sub     rsp, 20h
0x18001c682  mov     rbx, rcx
0x18001c685  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001c68c  mov     [rcx], rax
0x18001c68f  mov     eax, [rdx+8]
0x18001c692  mov     [rcx+8], eax
0x18001c695  mov     rcx, [rdx+10h]
0x18001c699  mov     [rbx+10h], rcx
0x18001c69d  mov     qword ptr [rbx+18h], 0
0x18001c6a5  test    rcx, rcx
0x18001c6a8  jz      short loc_18001C6B6
0x18001c6aa  mov     rax, [rcx]
0x18001c6ad  mov     rax, [rax+8]
0x18001c6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b6  mov     rax, rbx
0x18001c6b9  add     rsp, 20h
0x18001c6bd  pop     rbx
0x18001c6be  retn
```
