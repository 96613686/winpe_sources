# Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::InternalAddRef(void)

- ea: `0x18000ebb0`
- end: `0x18000ebf0`
- name: `?InternalAddRef@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@IEBAXXZ`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d8ec`

## callees

- `0x18000ebb0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::InternalAddRef(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)a1;
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
  return result;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp+arg_0], rcx
0x18000ebb5  sub     rsp, 38h
0x18000ebb9  mov     rax, [rsp+38h+arg_0]
0x18000ebbe  cmp     qword ptr [rax], 0
0x18000ebc2  jz      short loc_18000EBEB
0x18000ebc4  mov     rax, [rsp+38h+arg_0]
0x18000ebc9  mov     rax, [rax]
0x18000ebcc  mov     rcx, [rsp+38h+arg_0]
0x18000ebd1  mov     rcx, [rcx]
0x18000ebd4  mov     rax, [rax]
0x18000ebd7  mov     rax, [rax+8]
0x18000ebdb  mov     [rsp+38h+var_18], rax
0x18000ebe0  mov     rax, [rsp+38h+var_18]
0x18000ebe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebea  nop
0x18000ebeb  add     rsp, 38h
0x18000ebef  retn
```
