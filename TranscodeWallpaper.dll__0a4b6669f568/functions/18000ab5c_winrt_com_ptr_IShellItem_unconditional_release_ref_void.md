# winrt::com_ptr<IShellItem>::unconditional_release_ref(void)

- ea: `0x18000ab5c`
- end: `0x18000ab7f`
- name: `?unconditional_release_ref@?$com_ptr@UIShellItem@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007698`
- `0x18000ceb0`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IShellItem>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000ab5c  sub     rsp, 28h
0x18000ab60  mov     rdx, [rcx]
0x18000ab63  mov     qword ptr [rcx], 0
0x18000ab6a  mov     rax, [rdx]
0x18000ab6d  mov     rcx, rdx
0x18000ab70  mov     rax, [rax+10h]
0x18000ab74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab79  nop
0x18000ab7a  add     rsp, 28h
0x18000ab7e  retn
```
