# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x140007eec`
- end: `0x140007f05`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003eec`
- `0x14000406c`
- `0x140004648`
- `0x140004bdc`
- `0x140004c98`
- `0x140004ce4`
- `0x140007964`

## callees

- `0x140012010`

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
0x140007eec  mov     rdx, [rcx]
0x140007eef  mov     qword ptr [rcx], 0
0x140007ef6  mov     rcx, rdx
0x140007ef9  mov     rax, [rdx]
0x140007efc  mov     rax, [rax+10h]
0x140007f00  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
