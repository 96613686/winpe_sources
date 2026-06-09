# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x18000c010`
- end: `0x18000c029`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800033c0`
- `0x18000355c`
- `0x180003730`
- `0x1800038cc`
- `0x180003a28`
- `0x180003be4`
- `0x180004340`
- `0x180004ae8`
- `0x180005540`
- `0x1800057c4`
- `0x180005854`
- `0x1800062e0`
- `0x180006920`
- `0x180007250`

## callees

- `0x18000d010`

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
0x18000c010  mov     rdx, [rcx]
0x18000c013  mov     qword ptr [rcx], 0
0x18000c01a  mov     rcx, rdx
0x18000c01d  mov     rax, [rdx]
0x18000c020  mov     rax, [rax+10h]
0x18000c024  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
