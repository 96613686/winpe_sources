# winrt::com_ptr<ITaskService>::unconditional_release_ref(void)

- ea: `0x180010438`
- end: `0x18001045b`
- name: `?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a5e4`
- `0x180010470`
- `0x1800151d0`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<ITaskService>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180010438  sub     rsp, 28h
0x18001043c  mov     rdx, [rcx]
0x18001043f  mov     qword ptr [rcx], 0
0x180010446  mov     rax, [rdx]
0x180010449  mov     rcx, rdx
0x18001044c  mov     rax, [rax+10h]
0x180010450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010455  nop
0x180010456  add     rsp, 28h
0x18001045a  retn
```
