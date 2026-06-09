# SrpPolicyTransactionRollback

- ea: `0x140024218`
- end: `0x14002426f`
- name: `SrpPolicyTransactionRollback`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14002318c`
- `0x140033f50`

## callees

- `0x140024028`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140024254`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140024254`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140024225`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140024225`

## pseudocode

```c
__int64 SrpPolicyTransactionRollback()
{
  __int64 v0; // rbx

  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  v0 = qword_1400193D8;
  qword_1400193D8 = 0;
  xmmword_1400193E0 = 0;
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  return CheckReleasePolicyRef(v0);
}

```

## disassembly

```asm
0x140024218  push    rbx
0x14002421a  sub     rsp, 20h
0x14002421e  lea     rcx, Resource; Resource
0x140024225  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14002422c  nop     dword ptr [rax+rax+00h]
0x140024231  mov     rbx, cs:qword_1400193D8
0x140024238  lea     rcx, Resource; Resource
0x14002423f  xorps   xmm0, xmm0
0x140024242  mov     cs:qword_1400193D8, 0
0x14002424d  movups  cs:xmmword_1400193E0, xmm0
0x140024254  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14002425b  nop     dword ptr [rax+rax+00h]
0x140024260  mov     rcx, rbx
0x140024263  call    CheckReleasePolicyRef
0x140024268  add     rsp, 20h
0x14002426c  pop     rbx
0x14002426d  retn
```
