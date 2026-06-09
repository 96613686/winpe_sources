# LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(void)

- ea: `0x180009b54`
- end: `0x180009b91`
- name: `?_FreeSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAA_NXZ`
- size: `61`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089a4`
- `0x180008bf4`
- `0x180009574`
- `0x18000a330`

## callees

- `0x18000b010`

## pseudocode

```c
bool __fastcall LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(LKRhash::CLKRLinearHashTable *this)
{
  bool result; // al

  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 18) + 8LL))(
    *((_QWORD *)this + 18),
    *((_QWORD *)this + 13),
    3);
  result = 1;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 29) = 0;
  return result;
}

```

## disassembly

```asm
0x180009b54  push    rbx
0x180009b56  sub     rsp, 20h
0x180009b5a  mov     rbx, rcx
0x180009b5d  mov     r8d, 3
0x180009b63  mov     rcx, [rcx+90h]
0x180009b6a  mov     rdx, [rbx+68h]
0x180009b6e  mov     rax, [rcx]
0x180009b71  mov     rax, [rax+8]
0x180009b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7a  mov     al, 1
0x180009b7c  mov     qword ptr [rbx+68h], 0
0x180009b84  mov     dword ptr [rbx+74h], 0
0x180009b8b  add     rsp, 20h
0x180009b8f  pop     rbx
0x180009b90  retn
```
