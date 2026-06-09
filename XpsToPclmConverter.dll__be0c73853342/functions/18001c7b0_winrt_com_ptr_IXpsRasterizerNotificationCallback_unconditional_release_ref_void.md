# winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)

- ea: `0x18001c7b0`
- end: `0x18001c7d3`
- name: `?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b130`
- `0x18001b428`
- `0x18001b474`
- `0x18001b744`
- `0x18001c1b4`

## callees

- `0x18001f010`

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
0x18001c7b0  sub     rsp, 28h
0x18001c7b4  mov     rdx, [rcx]
0x18001c7b7  mov     qword ptr [rcx], 0
0x18001c7be  mov     rax, [rdx]
0x18001c7c1  mov     rcx, rdx
0x18001c7c4  mov     rax, [rax+10h]
0x18001c7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7cd  nop
0x18001c7ce  add     rsp, 28h
0x18001c7d2  retn
```
