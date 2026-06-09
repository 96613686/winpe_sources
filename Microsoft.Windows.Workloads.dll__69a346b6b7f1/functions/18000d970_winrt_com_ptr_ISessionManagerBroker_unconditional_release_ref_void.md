# winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)

- ea: `0x18000d970`
- end: `0x18000d994`
- name: `?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007150`
- `0x18000a340`
- `0x180021b10`
- `0x180022260`
- `0x1800229c0`
- `0x180023620`
- `0x180023860`
- `0x180023c50`
- `0x180024120`
- `0x18003aec0`

## callees

- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000d970  sub     rsp, 28h
0x18000d974  mov     rdx, [rcx]
0x18000d977  mov     qword ptr [rcx], 0
0x18000d97e  mov     rax, [rdx]
0x18000d981  mov     rcx, rdx
0x18000d984  mov     rax, [rax+10h]
0x18000d988  call    cs:__guard_dispatch_icall_fptr
0x18000d98e  nop
0x18000d98f  add     rsp, 28h
0x18000d993  retn
```
