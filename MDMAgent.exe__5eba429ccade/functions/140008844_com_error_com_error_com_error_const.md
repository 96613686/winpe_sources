# _com_error::_com_error(_com_error const &)

- ea: `0x140008844`
- end: `0x140008887`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008844`
- `0x140019010`

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
0x140008844  push    rbx
0x140008846  sub     rsp, 20h
0x14000884a  mov     rbx, rcx
0x14000884d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140008854  mov     [rcx], rax
0x140008857  mov     eax, [rdx+8]
0x14000885a  mov     [rcx+8], eax
0x14000885d  mov     rcx, [rdx+10h]
0x140008861  mov     [rbx+10h], rcx
0x140008865  mov     qword ptr [rbx+18h], 0
0x14000886d  test    rcx, rcx
0x140008870  jz      short loc_14000887E
0x140008872  mov     rax, [rcx]
0x140008875  mov     rax, [rax+8]
0x140008879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000887e  mov     rax, rbx
0x140008881  add     rsp, 20h
0x140008885  pop     rbx
0x140008886  retn
```
