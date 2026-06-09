# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x18000c568`
- end: `0x18000c581`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c47c`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000c568  mov     rdx, [rcx]
0x18000c56b  mov     qword ptr [rcx], 0
0x18000c572  mov     rcx, rdx
0x18000c575  mov     rax, [rdx]
0x18000c578  mov     rax, [rax+10h]
0x18000c57c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
