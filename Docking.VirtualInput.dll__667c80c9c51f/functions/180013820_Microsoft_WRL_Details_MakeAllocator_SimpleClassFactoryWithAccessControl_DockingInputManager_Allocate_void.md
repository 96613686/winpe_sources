# Microsoft::WRL::Details::MakeAllocator<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Allocate(void)

- ea: `0x180013820`
- end: `0x180013856`
- name: `?Allocate@?$MakeAllocator@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Details@WRL@Microsoft@@QEAAPEAXXZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012f94`

## callees

- `0x180004164`

## pseudocode

```c
void *__fastcall Microsoft::WRL::Details::MakeAllocator<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Allocate(
        _QWORD *a1)
{
  void *result; // rax

  result = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180013820  mov     [rsp+arg_0], rcx
0x180013825  sub     rsp, 38h
0x180013829  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013830  mov     ecx, 18h; unsigned __int64
0x180013835  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001383a  mov     [rsp+38h+var_18], rax
0x18001383f  mov     rax, [rsp+38h+arg_0]
0x180013844  mov     rcx, [rsp+38h+var_18]
0x180013849  mov     [rax], rcx
0x18001384c  mov     rax, [rsp+38h+var_18]
0x180013851  add     rsp, 38h
0x180013855  retn
```
