# CILogWrite::Release(void)

- ea: `0x180004fb0`
- end: `0x180004fe8`
- name: `?Release@CILogWrite@@UEAAKXZ`
- size: `56`
- prototype: `unsigned int __fastcall(CILogWrite *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x180004fb0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogWrite::Release(CILogWrite *this)
{
  unsigned int v2; // ebx

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
  if ( !v2 )
    operator delete(this);
  return v2;
}

```

## disassembly

```asm
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  push    rdi
0x180004fb6  sub     rsp, 20h
0x180004fba  mov     rdi, rcx
0x180004fbd  mov     rcx, [rcx+8]
0x180004fc1  mov     rax, [rcx]
0x180004fc4  mov     rax, [rax+30h]
0x180004fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fcd  mov     ebx, eax
0x180004fcf  test    eax, eax
0x180004fd1  jnz     short loc_180004FDB
0x180004fd3  mov     rcx, rdi; Block
0x180004fd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004fdb  mov     eax, ebx
0x180004fdd  mov     rbx, [rsp+28h+arg_0]
0x180004fe2  add     rsp, 20h
0x180004fe6  pop     rdi
0x180004fe7  retn
```
