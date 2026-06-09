# winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)

- ea: `0x18000f3c0`
- end: `0x18000f3e3`
- name: `?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dc78`
- `0x18000e0d0`
- `0x18000e1a0`
- `0x18000e494`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000f3c0  sub     rsp, 28h
0x18000f3c4  mov     rdx, [rcx]
0x18000f3c7  mov     qword ptr [rcx], 0
0x18000f3ce  mov     rax, [rdx]
0x18000f3d1  mov     rcx, rdx
0x18000f3d4  mov     rax, [rax+10h]
0x18000f3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3dd  nop
0x18000f3de  add     rsp, 28h
0x18000f3e2  retn
```
