# winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)

- ea: `0x18000b62c`
- end: `0x18000b64f`
- name: `?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009cb8`
- `0x180009dd8`
- `0x18000a870`
- `0x18000ac30`
- `0x18000be40`
- `0x18000c1d0`
- `0x18000c3e8`

## callees

- `0x18000e010`

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
0x18000b62c  sub     rsp, 28h
0x18000b630  mov     rdx, [rcx]
0x18000b633  mov     qword ptr [rcx], 0
0x18000b63a  mov     rax, [rdx]
0x18000b63d  mov     rcx, rdx
0x18000b640  mov     rax, [rax+10h]
0x18000b644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b649  nop
0x18000b64a  add     rsp, 28h
0x18000b64e  retn
```
