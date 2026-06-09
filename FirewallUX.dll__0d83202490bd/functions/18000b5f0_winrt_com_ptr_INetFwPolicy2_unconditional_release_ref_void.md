# winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)

- ea: `0x18000b5f0`
- end: `0x18000b613`
- name: `?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005a4c`
- `0x18000b860`
- `0x18000f104`
- `0x1800104e8`
- `0x1800139a4`
- `0x180026784`
- `0x180027268`
- `0x18002761c`
- `0x180028918`

## callees

- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000b5f0  sub     rsp, 28h
0x18000b5f4  mov     rdx, [rcx]
0x18000b5f7  mov     qword ptr [rcx], 0
0x18000b5fe  mov     rax, [rdx]
0x18000b601  mov     rcx, rdx
0x18000b604  mov     rax, [rax+10h]
0x18000b608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60d  nop
0x18000b60e  add     rsp, 28h
0x18000b612  retn
```
