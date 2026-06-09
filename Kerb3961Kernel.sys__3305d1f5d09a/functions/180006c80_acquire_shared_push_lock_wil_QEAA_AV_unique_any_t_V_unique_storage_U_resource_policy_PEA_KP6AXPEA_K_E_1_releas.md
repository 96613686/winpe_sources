# ?acquire_shared@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ

- ea: `0x180006c80`
- end: `0x180006cbf`
- name: `?acquire_shared@push_lock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_KP6AXPEA_K@_E$1?release_push_lock_shared@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEA_KPEA_K$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `63`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000bcd0`
- `0x18000bdc0`
- `0x18000beb0`
- `0x18000c230`
- `0x18000c580`
- `0x18000c710`
- `0x18000cbd0`
- `0x18000cd60`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180006ca1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180006ca1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c90`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c90`

## pseudocode

```c
_QWORD *__fastcall wil::push_lock::acquire_shared(__int64 a1, _QWORD *a2)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  *a2 = a1;
  return a2;
}

```

## disassembly

```asm
0x180006c80  mov     [rsp+arg_0], rbx
0x180006c85  push    rdi
0x180006c86  sub     rsp, 20h
0x180006c8a  mov     rdi, rdx
0x180006c8d  mov     rbx, rcx
0x180006c90  call    cs:__imp_KeEnterCriticalRegion
0x180006c97  nop     dword ptr [rax+rax+00h]
0x180006c9c  xor     edx, edx
0x180006c9e  mov     rcx, rbx
0x180006ca1  call    cs:__imp_ExAcquirePushLockSharedEx
0x180006ca8  nop     dword ptr [rax+rax+00h]
0x180006cad  mov     [rdi], rbx
0x180006cb0  mov     rax, rdi
0x180006cb3  mov     rbx, [rsp+28h+arg_0]
0x180006cb8  add     rsp, 20h
0x180006cbc  pop     rdi
0x180006cbd  retn
```
