# winrt::com_ptr<IRegisteredTask>::~com_ptr<IRegisteredTask>(void)

- ea: `0x18000a5e4`
- end: `0x18000a5f8`
- name: `??1?$com_ptr@UIRegisteredTask@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017109`
- `0x18001712d`
- `0x18001713f`

## callees

- `0x18000a5e4`
- `0x180010438`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IRegisteredTask>::~com_ptr<IRegisteredTask>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<ITaskService>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000a5e4  sub     rsp, 28h
0x18000a5e8  cmp     qword ptr [rcx], 0
0x18000a5ec  jz      short loc_18000A5F3
0x18000a5ee  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x18000a5f3  add     rsp, 28h
0x18000a5f7  retn
```
