# Concurrency::details::_TaskProcHandle::_RunChoreBridge(void *)

- ea: `0x180012740`
- end: `0x180012773`
- name: `?_RunChoreBridge@_TaskProcHandle@details@Concurrency@@SAXPEAX@Z`
- size: `51`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180019010`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskProcHandle::_RunChoreBridge(void *a1)
{
  (*(void (__fastcall **)(void *))(*(_QWORD *)a1 + 8LL))(a1);
  (**(void (__fastcall ***)(void *, __int64))a1)(a1, 1);
}

```

## disassembly

```asm
0x180012740  push    rbx
0x180012742  sub     rsp, 20h
0x180012746  mov     rbx, rcx
0x180012749  mov     [rsp+28h+arg_0], rcx
0x18001274e  mov     rax, [rcx]
0x180012751  mov     rax, [rax+8]
0x180012755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275a  nop
0x18001275b  mov     rax, [rbx]
0x18001275e  mov     edx, 1
0x180012763  mov     rcx, rbx
0x180012766  mov     rax, [rax]
0x180012769  add     rsp, 20h
0x18001276d  pop     rbx
0x18001276e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
