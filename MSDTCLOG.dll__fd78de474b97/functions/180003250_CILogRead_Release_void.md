# CILogRead::Release(void)

- ea: `0x180003250`
- end: `0x180003288`
- name: `?Release@CILogRead@@UEAAKXZ`
- size: `56`
- prototype: `unsigned int __fastcall(CILogRead *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x180003250`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogRead::Release(CILogRead *this)
{
  unsigned int v2; // ebx

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1));
  if ( !v2 )
    operator delete(this);
  return v2;
}

```

## disassembly

```asm
0x180003250  mov     [rsp+arg_0], rbx
0x180003255  push    rdi
0x180003256  sub     rsp, 20h
0x18000325a  mov     rdi, rcx
0x18000325d  mov     rcx, [rcx+8]
0x180003261  mov     rax, [rcx]
0x180003264  mov     rax, [rax+28h]
0x180003268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000326d  mov     ebx, eax
0x18000326f  test    eax, eax
0x180003271  jnz     short loc_18000327B
0x180003273  mov     rcx, rdi; Block
0x180003276  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000327b  mov     eax, ebx
0x18000327d  mov     rbx, [rsp+28h+arg_0]
0x180003282  add     rsp, 20h
0x180003286  pop     rdi
0x180003287  retn
```
