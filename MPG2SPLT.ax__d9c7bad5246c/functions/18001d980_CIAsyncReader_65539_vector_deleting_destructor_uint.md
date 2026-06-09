# CIAsyncReader<65539>::`vector deleting destructor'(uint)

- ea: `0x18001d980`
- end: `0x18001d9cc`
- name: `??_E?$CIAsyncReader@$0BAAAD@@@UEAAPEAXI@Z`
- size: `76`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x18001d980`
- `0x180034010`

## pseudocode

```c
_QWORD **__fastcall CIAsyncReader<65539>::`vector deleting destructor'(_QWORD **a1, char a2)
{
  *a1 = &CIAsyncReader<65539>::`vftable';
  (*(void (__fastcall **)(_QWORD *))(*a1[8197] + 16LL))(a1[8197]);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001d980  mov     [rsp+arg_0], rbx
0x18001d985  push    rdi
0x18001d986  sub     rsp, 20h
0x18001d98a  lea     rax, ??_7?$CIAsyncReader@$0BAAAD@@@6B@; const CIAsyncReader<65539>::`vftable'
0x18001d991  mov     rdi, rcx
0x18001d994  mov     [rcx], rax
0x18001d997  mov     ebx, edx
0x18001d999  mov     rcx, [rcx+10028h]
0x18001d9a0  mov     rax, [rcx]
0x18001d9a3  mov     rax, [rax+10h]
0x18001d9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ac  test    bl, 1
0x18001d9af  jz      short loc_18001D9BE
0x18001d9b1  mov     edx, 10030h; unsigned __int64
0x18001d9b6  mov     rcx, rdi; void *
0x18001d9b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d9be  mov     rbx, [rsp+28h+arg_0]
0x18001d9c3  mov     rax, rdi
0x18001d9c6  add     rsp, 20h
0x18001d9ca  pop     rdi
0x18001d9cb  retn
```
