# _com_error::_com_error(_com_error const &)

- ea: `0x140014028`
- end: `0x14001406b`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140014028`
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
0x140014028  push    rbx
0x14001402a  sub     rsp, 20h
0x14001402e  mov     rbx, rcx
0x140014031  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140014038  mov     [rcx], rax
0x14001403b  mov     eax, [rdx+8]
0x14001403e  mov     [rcx+8], eax
0x140014041  mov     rcx, [rdx+10h]
0x140014045  mov     [rbx+10h], rcx
0x140014049  mov     qword ptr [rbx+18h], 0
0x140014051  test    rcx, rcx
0x140014054  jz      short loc_140014062
0x140014056  mov     rax, [rcx]
0x140014059  mov     rax, [rax+8]
0x14001405d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014062  mov     rax, rbx
0x140014065  add     rsp, 20h
0x140014069  pop     rbx
0x14001406a  retn
```
