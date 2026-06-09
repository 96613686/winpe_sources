# VsmmPhuStoreItemRemoveAndFree

- ea: `0x1400b458c`
- end: `0x1400b4625`
- name: `VsmmPhuStoreItemRemoveAndFree`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140078a58`
- `0x1400a3630`
- `0x1400b88dc`
- `0x1400b9dac`

## callees

- `0x1400347a4`
- `0x140034b64`
- `0x1400b42ec`
- `0x1400ba7e4`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400b45ab`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b45c2`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b45ab`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b45c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4600`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4600`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreItemRemoveAndFree(__int64 a1, char *a2)
{
  char v5; // [rsp+20h] [rbp-18h]
  char v6; // [rsp+28h] [rbp-10h]

  VidObjectLockAcquireExclusive(a1);
  RtlRbRemoveNode(a1 + 1264, a2);
  RtlRbRemoveNode(a1 + 1280, a2 + 24);
  --*(_QWORD *)(a1 + 1296);
  VidObjectLockRelease(a1);
  v6 = 1;
  v5 = 1;
  VsmmPhuStoreItemDataSet(a1, a2, 0, 0, v5, v6);
  ExFreePoolWithTag(a2, 0x6D4D6456u);
  return VsmmPhuStorepSerializationChargeDecrease(a1, 64);
}

```

## disassembly

```asm
0x1400b458c  mov     [rsp+arg_0], rbx
0x1400b4591  push    rdi
0x1400b4592  sub     rsp, 30h
0x1400b4596  mov     rbx, rdx
0x1400b4599  mov     rdi, rcx
0x1400b459c  call    VidObjectLockAcquireExclusive
0x1400b45a1  lea     rcx, [rdi+4F0h]
0x1400b45a8  mov     rdx, rbx
0x1400b45ab  call    cs:__imp_RtlRbRemoveNode
0x1400b45b2  nop     dword ptr [rax+rax+00h]
0x1400b45b7  lea     rdx, [rbx+18h]
0x1400b45bb  lea     rcx, [rdi+500h]
0x1400b45c2  call    cs:__imp_RtlRbRemoveNode
0x1400b45c9  nop     dword ptr [rax+rax+00h]
0x1400b45ce  dec     qword ptr [rdi+510h]
0x1400b45d5  mov     rcx, rdi
0x1400b45d8  call    VidObjectLockRelease
0x1400b45dd  xor     r9d, r9d
0x1400b45e0  mov     [rsp+38h+var_10], 1
0x1400b45e5  xor     r8d, r8d
0x1400b45e8  mov     [rsp+38h+var_18], 1
0x1400b45ed  mov     rdx, rbx
0x1400b45f0  mov     rcx, rdi
0x1400b45f3  call    VsmmPhuStoreItemDataSet
0x1400b45f8  mov     edx, 6D4D6456h; Tag
0x1400b45fd  mov     rcx, rbx; P
0x1400b4600  call    cs:__imp_ExFreePoolWithTag
0x1400b4607  nop     dword ptr [rax+rax+00h]
0x1400b460c  mov     edx, 40h ; '@'
0x1400b4611  mov     rcx, rdi
0x1400b4614  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b4619  mov     rbx, [rsp+38h+arg_0]
0x1400b461e  add     rsp, 30h
0x1400b4622  pop     rdi
0x1400b4623  retn
```
