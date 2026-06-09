# ReplacePolicyRef

- ea: `0x140024044`
- end: `0x140024099`
- name: `ReplacePolicyRef`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001fef0`
- `0x14002318c`
- `0x140024184`

## callees

- `0x140024028`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140024079`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140024079`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140024058`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140024058`

## pseudocode

```c
__int64 __fastcall ReplacePolicyRef(__int64 a1)
{
  __int64 v2; // rbx

  ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_140019300);
  v2 = qword_1400193F8;
  qword_1400193F8 = a1;
  ExReleaseResourceAndLeaveCriticalRegion(&stru_140019300);
  return CheckReleasePolicyRef(v2);
}

```

## disassembly

```asm
0x140024044  mov     [rsp+arg_0], rbx
0x140024049  push    rdi
0x14002404a  sub     rsp, 20h
0x14002404e  mov     rdi, rcx
0x140024051  lea     rcx, stru_140019300; Resource
0x140024058  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14002405f  nop     dword ptr [rax+rax+00h]
0x140024064  mov     rbx, cs:qword_1400193F8
0x14002406b  lea     rcx, stru_140019300; Resource
0x140024072  mov     cs:qword_1400193F8, rdi
0x140024079  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140024080  nop     dword ptr [rax+rax+00h]
0x140024085  mov     rcx, rbx
0x140024088  call    CheckReleasePolicyRef
0x14002408d  mov     rbx, [rsp+28h+arg_0]
0x140024092  add     rsp, 20h
0x140024096  pop     rdi
0x140024097  retn
```
