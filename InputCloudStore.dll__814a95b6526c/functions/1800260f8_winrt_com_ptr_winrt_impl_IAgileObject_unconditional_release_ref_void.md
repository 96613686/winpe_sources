# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x1800260f8`
- end: `0x180026111`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001296c`
- `0x180014d2c`
- `0x18001a7f8`
- `0x18001b738`
- `0x18001b874`
- `0x18001b9ac`
- `0x180024824`

## callees

- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800260f8  mov     rdx, [rcx]
0x1800260fb  mov     qword ptr [rcx], 0
0x180026102  mov     rcx, rdx
0x180026105  mov     rax, [rdx]
0x180026108  mov     rax, [rax+10h]
0x18002610c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
