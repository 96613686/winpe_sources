# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x180009c74`
- end: `0x180009c8d`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009ba0`
- `0x18000eef0`
- `0x18000f73c`
- `0x18000f888`
- `0x18000f9d4`
- `0x18000fb20`
- `0x18000fc74`
- `0x18000fe58`
- `0x180010278`
- `0x180010810`
- `0x180010a38`
- `0x180010bfc`
- `0x180010c28`
- `0x1800130d0`

## callees

- `0x18001c010`

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
0x180009c74  mov     rdx, [rcx]
0x180009c77  mov     qword ptr [rcx], 0
0x180009c7e  mov     rcx, rdx
0x180009c81  mov     rax, [rdx]
0x180009c84  mov     rax, [rax+10h]
0x180009c88  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
