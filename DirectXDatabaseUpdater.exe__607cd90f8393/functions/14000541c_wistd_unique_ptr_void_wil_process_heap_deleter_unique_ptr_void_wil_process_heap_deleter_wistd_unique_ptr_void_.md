# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x14000541c`
- end: `0x140005441`
- name: `??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005798`

## callees

- `0x140003f30`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
        __int64 a1,
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
0x14000541c  sub     rsp, 28h
0x140005420  mov     rax, [rdx]
0x140005423  mov     qword ptr [rdx], 0
0x14000542a  lea     rdx, [rsp+28h+arg_0]
0x14000542f  mov     [rsp+28h+arg_0], rax
0x140005434  call    ??$?0PEAXUprocess_heap_deleter@wil@@@?$__compressed_pair@PEAXUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAPEAX$$QEAUprocess_heap_deleter@wil@@@Z; wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(void * &&,wil::process_heap_deleter &&)
0x140005439  mov     rax, rcx
0x14000543c  add     rsp, 28h
0x140005440  retn
```
