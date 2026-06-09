# CBoolean::ProcessTheJunction(void)

- ea: `0x10042a880`
- end: `0x10042a8b1`
- name: `?ProcessTheJunction@CBoolean@@UEAAJXZ`
- size: `49`
- prototype: `__int64 __fastcall(CBoolean *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x1004453c0`

## pseudocode

```c
__int64 __fastcall CBoolean::ProcessTheJunction(CBoolean *this)
{
  *((_WORD *)this + 286) = 0;
  C2ShapesProcessor::Classify(this);
  return (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 70) + 16LL))(
           *((_QWORD *)this + 70),
           (char *)this + 296);
}

```

## disassembly

```asm
0x10042a880  push    rbx
0x10042a882  sub     rsp, 20h
0x10042a886  mov     rbx, rcx
0x10042a889  mov     word ptr [rcx+23Ch], 0
0x10042a892  call    ?Classify@C2ShapesProcessor@@IEAAXXZ; C2ShapesProcessor::Classify(void)
0x10042a897  mov     rcx, [rbx+230h]
0x10042a89e  lea     rdx, [rbx+128h]
0x10042a8a5  mov     rax, [rcx]
0x10042a8a8  add     rsp, 20h
0x10042a8ac  pop     rbx
0x10042a8ad  jmp     qword ptr [rax+10h]
```
