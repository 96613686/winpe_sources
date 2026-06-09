# av_thread_message_queue_nb_elems

- ea: `0x180051bf0`
- end: `0x180051c2b`
- name: `av_thread_message_queue_nb_elems`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051c18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051c04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051c04`

## pseudocode

```c
__int64 __fastcall av_thread_message_queue_nb_elems(RTL_SRWLOCK *a1)
{
  RTL_SRWLOCK *v1; // rdi
  __int64 *v2; // rbx

  v1 = a1 + 1;
  v2 = (__int64 *)a1;
  AcquireSRWLockExclusive(a1 + 1);
  LODWORD(v2) = av_fifo_can_read(*v2);
  ReleaseSRWLockExclusive(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180051bf0  mov     [rsp+arg_0], rbx
0x180051bf5  push    rdi
0x180051bf6  sub     rsp, 20h
0x180051bfa  lea     rdi, [rcx+8]
0x180051bfe  mov     rbx, rcx
0x180051c01  mov     rcx, rdi; SRWLock
0x180051c04  call    cs:AcquireSRWLockExclusive
0x180051c0a  mov     rcx, [rbx]
0x180051c0d  call    av_fifo_can_read
0x180051c12  mov     rcx, rdi; SRWLock
0x180051c15  mov     rbx, rax
0x180051c18  call    cs:ReleaseSRWLockExclusive
0x180051c1e  mov     eax, ebx
0x180051c20  mov     rbx, [rsp+28h+arg_0]
0x180051c25  add     rsp, 20h
0x180051c29  pop     rdi
0x180051c2a  retn
```
