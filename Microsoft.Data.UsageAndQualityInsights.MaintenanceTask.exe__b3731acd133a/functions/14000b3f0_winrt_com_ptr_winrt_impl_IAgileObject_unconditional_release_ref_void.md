# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x14000b3f0`
- end: `0x14000b409`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400098ec`
- `0x140009a40`
- `0x140009f74`
- `0x14000a494`
- `0x14000a4dc`

## callees

- `0x14000c010`

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
0x14000b3f0  mov     rdx, [rcx]
0x14000b3f3  mov     qword ptr [rcx], 0
0x14000b3fa  mov     rcx, rdx
0x14000b3fd  mov     rax, [rdx]
0x14000b400  mov     rax, [rax+10h]
0x14000b404  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
