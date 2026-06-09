# TrackerList::RemoveEntry(int)

- ea: `0x140004784`
- end: `0x14000484f`
- name: `?RemoveEntry@TrackerList@@QEAAPEAVTracker@@H@Z`
- size: `203`
- prototype: `struct Tracker *__fastcall(TrackerList *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003588`
- `0x140004280`

## callees

- `0x140004784`
- `0x1400052d0`
- `0x140005374`

## pseudocode

```c
struct Tracker *__fastcall TrackerList::RemoveEntry(TrackerList *this, int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  int v5; // eax
  __int64 v6; // r8
  int v7; // r9d

  v2 = a2;
  v4 = 0;
  CReadWriteSpinLock::AcquireWriterLock((TrackerList *)((char *)this + 32));
  if ( (int)v2 >= 0 )
  {
    v5 = *((_DWORD *)this + 2);
    if ( (int)v2 < v5 )
    {
      v6 = *(_QWORD *)this;
      v4 = *(_QWORD *)(*(_QWORD *)this + 16 * v2);
      v7 = *((_DWORD *)this + 3);
      if ( v7 == *((_DWORD *)this + 4) && v7 == -1 )
      {
        *((_DWORD *)this + 3) = v2;
        *((_DWORD *)this + 4) = v2;
        *(_DWORD *)(v6 + 16 * v2 + 8) = -1;
      }
      else if ( (int)v2 >= v5 / 2 )
      {
        *(_DWORD *)(v6 + 16LL * *((int *)this + 4) + 8) = v2;
        *(_DWORD *)(*(_QWORD *)this + 16 * v2 + 8) = -1;
        *((_DWORD *)this + 4) = v2;
      }
      else
      {
        *(_DWORD *)(v6 + 16 * v2 + 8) = v7;
        *((_DWORD *)this + 3) = v2;
      }
      *(_QWORD *)(*(_QWORD *)this + 16 * v2) = 0;
      ++*((_DWORD *)this + 5);
      if ( (int)v2 >= *((_DWORD *)this + 2) / 2 )
        ++*((_DWORD *)this + 6);
    }
  }
  CReadWriteSpinLock::ReleaseWriterLock((TrackerList *)((char *)this + 32));
  return (struct Tracker *)v4;
}

```

## disassembly

```asm
0x140004784  mov     rax, rsp
0x140004787  mov     [rax+10h], rbx
0x14000478b  mov     [rax+18h], rsi
0x14000478f  mov     [rax+20h], rdi
0x140004793  mov     [rax+8], rcx
0x140004797  push    r14
0x140004799  sub     rsp, 30h
0x14000479d  movsxd  rdi, edx
0x1400047a0  mov     rbx, rcx
0x1400047a3  xor     esi, esi
0x1400047a5  add     rcx, 20h ; ' '; this
0x1400047a9  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x1400047ae  nop
0x1400047af  test    edi, edi
0x1400047b1  js      short loc_14000482D
0x1400047b3  mov     eax, [rbx+8]
0x1400047b6  cmp     edi, eax
0x1400047b8  jge     short loc_14000482D
0x1400047ba  mov     rcx, rdi
0x1400047bd  add     rcx, rcx
0x1400047c0  mov     r8, [rbx]
0x1400047c3  mov     rsi, [r8+rcx*8]
0x1400047c7  mov     [rsp+38h+var_18], rsi
0x1400047cc  mov     r9d, [rbx+0Ch]
0x1400047d0  cmp     r9d, [rbx+10h]
0x1400047d4  jnz     short loc_1400047E9
0x1400047d6  cmp     r9d, 0FFFFFFFFh
0x1400047da  jnz     short loc_1400047E9
0x1400047dc  mov     [rbx+0Ch], edi
0x1400047df  mov     [rbx+10h], edi
0x1400047e2  or      [r8+rcx*8+8], r9d
0x1400047e7  jmp     short loc_140004813
0x1400047e9  cdq
0x1400047ea  sub     eax, edx
0x1400047ec  sar     eax, 1
0x1400047ee  cmp     edi, eax
0x1400047f0  jge     short loc_1400047FC
0x1400047f2  mov     [r8+rcx*8+8], r9d
0x1400047f7  mov     [rbx+0Ch], edi
0x1400047fa  jmp     short loc_140004813
0x1400047fc  movsxd  rax, dword ptr [rbx+10h]
0x140004800  add     rax, rax
0x140004803  mov     [r8+rax*8+8], edi
0x140004808  mov     rax, [rbx]
0x14000480b  or      dword ptr [rax+rcx*8+8], 0FFFFFFFFh
0x140004810  mov     [rbx+10h], edi
0x140004813  mov     rax, [rbx]
0x140004816  and     qword ptr [rax+rcx*8], 0
0x14000481b  inc     dword ptr [rbx+14h]
0x14000481e  mov     eax, [rbx+8]
0x140004821  cdq
0x140004822  sub     eax, edx
0x140004824  sar     eax, 1
0x140004826  cmp     edi, eax
0x140004828  jl      short loc_14000482D
0x14000482a  inc     dword ptr [rbx+18h]
0x14000482d  lea     rcx, [rbx+20h]; this
0x140004831  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x140004836  mov     rax, rsi
0x140004839  mov     rbx, [rsp+38h+arg_8]
0x14000483e  mov     rsi, [rsp+38h+arg_10]
0x140004843  mov     rdi, [rsp+38h+arg_18]
0x140004848  add     rsp, 30h
0x14000484c  pop     r14
0x14000484e  retn
0x14000660c  push    rbp
0x14000660e  sub     rsp, 20h
0x140006612  mov     rbp, rdx
0x140006615  mov     rcx, [rbp+40h]
0x140006619  add     rcx, 20h ; ' '; this
0x14000661d  add     rsp, 20h
0x140006621  pop     rbp
0x140006622  jmp     ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
```
