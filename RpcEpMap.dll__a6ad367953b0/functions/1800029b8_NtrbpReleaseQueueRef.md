# NtrbpReleaseQueueRef

- ea: `0x1800029b8`
- end: `0x1800029f4`
- name: `NtrbpReleaseQueueRef`
- size: `60`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002924`
- `0x180009384`
- `0x1800094b0`

## callees

- `0x1800029b8`
- `0x180002a00`
- `0x180002a2c`

## pseudocode

```c
void __fastcall NtrbpReleaseQueueRef(volatile signed __int64 *a1, unsigned __int64 a2)
{
  signed __int64 v3; // rax

  _m_prefetchw((const void *)(a1 + 6));
  v3 = _InterlockedXor64(a1 + 6, a2);
  if ( (v3 & a2) != 0 && v3 == a2 )
  {
    NtrbpCleanupAllRequests();
    operator delete((void *)a1);
  }
}

```

## disassembly

```asm
0x1800029b8  push    rbx
0x1800029ba  sub     rsp, 20h
0x1800029be  mov     rbx, rcx
0x1800029c1  prefetchw byte ptr [rcx+30h]
0x1800029c5  mov     rax, [rcx+30h]
0x1800029c9  mov     r8, rax
0x1800029cc  xor     r8, rdx
0x1800029cf  lock cmpxchg [rcx+30h], r8
0x1800029d5  jnz     short loc_1800029C9
0x1800029d7  test    rdx, rax
0x1800029da  jz      short loc_1800029EE
0x1800029dc  cmp     rax, rdx
0x1800029df  jnz     short loc_1800029EE
0x1800029e1  call    NtrbpCleanupAllRequests
0x1800029e6  mov     rcx, rbx; void *
0x1800029e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800029ee  add     rsp, 20h
0x1800029f2  pop     rbx
0x1800029f3  retn
```
