# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180003754`
- end: `0x180003779`
- name: `??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039f0`

## callees

- `0x180002dac`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a2;
  *a2 = 0;
  v5 = v2;
  wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
    a1,
    &v5);
  return v3;
}

```

## disassembly

```asm
0x180003754  sub     rsp, 28h
0x180003758  mov     rax, [rdx]
0x18000375b  mov     qword ptr [rdx], 0
0x180003762  lea     rdx, [rsp+28h+arg_0]
0x180003767  mov     [rsp+28h+arg_0], rax
0x18000376c  call    ??$?0PEAXUprocess_heap_deleter@wil@@@?$__compressed_pair@PEAXUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAPEAX$$QEAUprocess_heap_deleter@wil@@@Z; wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(void * &&,wil::process_heap_deleter &&)
0x180003771  mov     rax, rcx
0x180003774  add     rsp, 28h
0x180003778  retn
```
