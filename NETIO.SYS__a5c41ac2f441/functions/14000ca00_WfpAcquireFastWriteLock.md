# WfpAcquireFastWriteLock

- ea: `0x14000ca00`
- end: `0x14000ca8f`
- name: `WfpAcquireFastWriteLock`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a32c`
- `0x14000c4e0`
- `0x14000c774`
- `0x14000c810`
- `0x14001b4e8`
- `0x14001be68`
- `0x14001cce0`
- `0x14001ce18`
- `0x14001cea0`
- `0x14001d050`
- `0x14002d9a0`
- `0x140039568`
- `0x14004bd30`
- `0x14004c350`
- `0x14004ee50`
- `0x14004f7b0`
- `0x140068ee0`
- `0x140068f50`
- `0x14006c170`
- `0x14006c238`
- `0x14006c348`

## callees

- `0x14000ca00`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ca4a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ca4a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ca15`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ca15`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ca2d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ca2d`

## pseudocode

```c
void __fastcall WfpAcquireFastWriteLock(PNDIS_RW_LOCK_EX *a1, struct _LOCK_STATE_EX *a2)
{
  KIRQL CurrentIrql; // bl
  __int64 v5; // rdx

  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite(*a1, a2, 0);
  if ( CurrentIrql != 2 )
  {
    if ( gWfpPerProContext )
    {
      v5 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v5 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v5 = 4;
    }
  }
}

```

## disassembly

```asm
0x14000ca00  mov     [rsp+arg_0], rbx
0x14000ca05  mov     [rsp+arg_8], rsi
0x14000ca0a  push    rdi
0x14000ca0b  sub     rsp, 20h
0x14000ca0f  mov     rdi, rdx
0x14000ca12  mov     rsi, rcx
0x14000ca15  call    cs:__imp_KeGetCurrentIrql
0x14000ca1c  nop     dword ptr [rax+rax+00h]
0x14000ca21  mov     rcx, [rsi]; Lock
0x14000ca24  xor     r8d, r8d; Flags
0x14000ca27  mov     rdx, rdi; LockState
0x14000ca2a  movzx   ebx, al
0x14000ca2d  call    cs:__imp_NdisAcquireRWLockWrite
0x14000ca34  nop     dword ptr [rax+rax+00h]
0x14000ca39  cmp     bl, 2
0x14000ca3c  jz      short loc_14000CA7E
0x14000ca3e  cmp     cs:gWfpPerProContext, 0
0x14000ca46  jz      short loc_14000CA7E
0x14000ca48  xor     ecx, ecx; ProcNumber
0x14000ca4a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000ca51  nop     dword ptr [rax+rax+00h]
0x14000ca56  imul    eax, cs:gWfpPerProContextSize
0x14000ca5d  mov     ecx, eax
0x14000ca5f  mov     rax, cs:gWfpPerProContext
0x14000ca66  mov     rdx, [rcx+rax]
0x14000ca6a  mov     rax, ds:0FFFFF78000000008h
0x14000ca74  mov     [rdx+8], rax
0x14000ca78  mov     dword ptr [rdx], 4
0x14000ca7e  mov     rbx, [rsp+28h+arg_0]
0x14000ca83  mov     rsi, [rsp+28h+arg_8]
0x14000ca88  add     rsp, 20h
0x14000ca8c  pop     rdi
0x14000ca8d  retn
```
