# TrackerList::SetExpire(int)

- ea: `0x140004ab8`
- end: `0x140004b0b`
- name: `?SetExpire@TrackerList@@QEAAXH@Z`
- size: `83`
- prototype: `void __fastcall(TrackerList *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044f0`
- `0x140004850`

## callees

- `0x1400040d8`
- `0x140005294`
- `0x140005370`

## pseudocode

```c
void __fastcall TrackerList::SetExpire(TrackerList *this, int a2)
{
  __int64 v2; // rsi

  v2 = a2;
  CReadWriteSpinLock::AcquireReaderLock((TrackerList *)((char *)this + 32));
  *(_QWORD *)(*(_QWORD *)this + 16 * v2 + 8) = TrackerList::NewExpireTime(this);
  CReadWriteSpinLock::ReleaseReaderLock((TrackerList *)((char *)this + 32));
}

```

## disassembly

```asm
0x140004ab8  mov     [rsp+arg_8], rbx
0x140004abd  mov     [rsp+arg_10], rsi
0x140004ac2  mov     [rsp+arg_0], rcx
0x140004ac7  push    rdi
0x140004ac8  sub     rsp, 20h
0x140004acc  movsxd  rsi, edx
0x140004acf  mov     rbx, rcx
0x140004ad2  add     rcx, 20h ; ' '; this
0x140004ad6  call    ?AcquireReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireReaderLock(void)
0x140004adb  nop
0x140004adc  mov     rcx, rbx; this
0x140004adf  call    ?NewExpireTime@TrackerList@@AEAA_JXZ; TrackerList::NewExpireTime(void)
0x140004ae4  mov     r8, rsi
0x140004ae7  add     r8, r8
0x140004aea  mov     rdx, [rbx]
0x140004aed  mov     [rdx+r8*8+8], rax
0x140004af2  lea     rcx, [rbx+20h]; this
0x140004af6  call    ?ReleaseReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseReaderLock(void)
0x140004afb  mov     rbx, [rsp+28h+arg_8]
0x140004b00  mov     rsi, [rsp+28h+arg_10]
0x140004b05  add     rsp, 20h
0x140004b09  pop     rdi
0x140004b0a  retn
0x140006628  push    rbp
0x14000662a  sub     rsp, 20h
0x14000662e  mov     rbp, rdx
0x140006631  mov     rcx, [rbp+30h]
0x140006635  add     rcx, 20h ; ' '; this
0x140006639  add     rsp, 20h
0x14000663d  pop     rbp
0x14000663e  jmp     ?ReleaseReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseReaderLock(void)
```
