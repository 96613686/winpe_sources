# ?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ

- ea: `0x180006c38`
- end: `0x180006c77`
- name: `?acquire_exclusive@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `63`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000b510`
- `0x18000bb20`
- `0x18000c140`
- `0x18000c894`
- `0x18000cef0`
- `0x18000cfb0`
- `0x180010c78`
- `0x180010e6c`
- `0x180011330`
- `0x180011450`
- `0x180011640`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c48`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180006c59`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180006c59`

## pseudocode

```c
_QWORD *__fastcall wil::push_lock::acquire_exclusive(__int64 a1, _QWORD *a2)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  *a2 = a1;
  return a2;
}

```

## disassembly

```asm
0x180006c38  mov     [rsp+arg_0], rbx
0x180006c3d  push    rdi
0x180006c3e  sub     rsp, 20h
0x180006c42  mov     rdi, rdx
0x180006c45  mov     rbx, rcx
0x180006c48  call    cs:__imp_KeEnterCriticalRegion
0x180006c4f  nop     dword ptr [rax+rax+00h]
0x180006c54  xor     edx, edx
0x180006c56  mov     rcx, rbx
0x180006c59  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180006c60  nop     dword ptr [rax+rax+00h]
0x180006c65  mov     [rdi], rbx
0x180006c68  mov     rax, rdi
0x180006c6b  mov     rbx, [rsp+28h+arg_0]
0x180006c70  add     rsp, 20h
0x180006c74  pop     rdi
0x180006c75  retn
```
