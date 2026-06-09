# TrackerList::SetNoExpire(int)

- ea: `0x140004b0c`
- end: `0x140004b74`
- name: `?SetNoExpire@TrackerList@@QEAA_NH@Z`
- size: `104`
- prototype: `char __fastcall(TrackerList *this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140004108`
- `0x1400044f0`
- `0x140004850`

## callees

- `0x140004b0c`
- `0x140005294`
- `0x140005370`

## pseudocode

```c
char __fastcall TrackerList::SetNoExpire(TrackerList *this, int a2)
{
  __int64 v2; // r14
  char v4; // bl

  v2 = a2;
  v4 = 1;
  CReadWriteSpinLock::AcquireReaderLock((TrackerList *)((char *)this + 32));
  if ( *(_QWORD *)(16 * v2 + *(_QWORD *)this + 8) == -1 )
    v4 = 0;
  else
    *(_QWORD *)(16 * v2 + *(_QWORD *)this + 8) = -1;
  CReadWriteSpinLock::ReleaseReaderLock((TrackerList *)((char *)this + 32));
  return v4;
}

```

## disassembly

```asm
0x140004b0c  mov     rax, rsp
0x140004b0f  mov     [rax+10h], rbx
0x140004b13  mov     [rax+18h], rsi
0x140004b17  mov     [rax+20h], rdi
0x140004b1b  mov     [rax+8], rcx
0x140004b1f  push    r14
0x140004b21  sub     rsp, 20h
0x140004b25  movsxd  r14, edx
0x140004b28  mov     rdi, rcx
0x140004b2b  mov     bl, 1
0x140004b2d  add     rcx, 20h ; ' '; this
0x140004b31  call    ?AcquireReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireReaderLock(void)
0x140004b36  nop
0x140004b37  mov     rax, r14
0x140004b3a  shl     rax, 4
0x140004b3e  mov     rcx, [rdi]
0x140004b41  cmp     qword ptr [rax+rcx+8], 0FFFFFFFFFFFFFFFFh
0x140004b47  jnz     short loc_140004B4D
0x140004b49  xor     bl, bl
0x140004b4b  jmp     short loc_140004B53
0x140004b4d  or      qword ptr [rax+rcx+8], 0FFFFFFFFFFFFFFFFh
0x140004b53  lea     rcx, [rdi+20h]; this
0x140004b57  call    ?ReleaseReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseReaderLock(void)
0x140004b5c  mov     al, bl
0x140004b5e  mov     rbx, [rsp+28h+arg_8]
0x140004b63  mov     rsi, [rsp+28h+arg_10]
0x140004b68  mov     rdi, [rsp+28h+arg_18]
0x140004b6d  add     rsp, 20h
0x140004b71  pop     r14
0x140004b73  retn
0x140006628  push    rbp
0x14000662a  sub     rsp, 20h
0x14000662e  mov     rbp, rdx
0x140006631  mov     rcx, [rbp+30h]
0x140006635  add     rcx, 20h ; ' '; this
0x140006639  add     rsp, 20h
0x14000663d  pop     rbp
0x14000663e  jmp     ?ReleaseReaderLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseReaderLock(void)
```
