# winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)

- ea: `0x18000a740`
- end: `0x18000a764`
- name: `?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ`
- size: `36`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007410`
- `0x180008470`

## callees

- `0x18001cdf0`

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
0x18000a740  sub     rsp, 28h
0x18000a744  mov     rdx, [rcx]
0x18000a747  mov     qword ptr [rcx], 0
0x18000a74e  mov     rax, [rdx]
0x18000a751  mov     rcx, rdx
0x18000a754  mov     rax, [rax+10h]
0x18000a758  call    cs:__guard_dispatch_icall_fptr
0x18000a75e  nop
0x18000a75f  add     rsp, 28h
0x18000a763  retn
```
