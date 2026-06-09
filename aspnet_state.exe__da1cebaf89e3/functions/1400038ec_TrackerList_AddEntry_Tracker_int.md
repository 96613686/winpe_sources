# TrackerList::AddEntry(Tracker *,int *)

- ea: `0x1400038ec`
- end: `0x1400039aa`
- name: `?AddEntry@TrackerList@@QEAAJPEAVTracker@@PEAH@Z`
- size: `190`
- prototype: `__int64 __fastcall(TrackerList *__hidden this, struct Tracker *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003bb0`
- `0x140003edc`
- `0x140004280`

## callees

- `0x1400038ec`
- `0x140003dec`
- `0x1400052d0`
- `0x140005374`

## pseudocode

```c
__int64 __fastcall TrackerList::AddEntry(TrackerList *this, struct Tracker *a2, int *a3)
{
  unsigned int v6; // edi
  int v7; // ecx
  int v8; // r9d
  __int64 v9; // r10
  int v10; // ecx

  v6 = 0;
  *a3 = -1;
  CReadWriteSpinLock::AcquireWriterLock((TrackerList *)((char *)this + 32));
  v7 = *((_DWORD *)this + 5);
  if ( !v7 )
  {
    v6 = TrackerList::Grow(this);
    if ( v6 )
      goto LABEL_11;
    v7 = *((_DWORD *)this + 5);
  }
  v8 = *((_DWORD *)this + 3);
  v9 = *(_QWORD *)this;
  *((_DWORD *)this + 3) = *(_DWORD *)(*(_QWORD *)this + 16LL * v8 + 8);
  v10 = v7 - 1;
  *((_DWORD *)this + 5) = v10;
  if ( v8 >= *((_DWORD *)this + 2) / 2 )
    --*((_DWORD *)this + 6);
  if ( !v10 )
    *((_DWORD *)this + 4) = -1;
  if ( v8 >= 0 )
  {
    *(_QWORD *)(v9 + 16LL * v8) = a2;
    *(_QWORD *)(*(_QWORD *)this + 16LL * v8 + 8) = -1;
    *a3 = v8;
  }
  else
  {
    v6 = -2147418113;
  }
LABEL_11:
  CReadWriteSpinLock::ReleaseWriterLock((TrackerList *)((char *)this + 32));
  return v6;
}

```

## disassembly

```asm
0x1400038ec  mov     [rsp+arg_8], rbx
0x1400038f1  mov     [rsp+arg_10], rsi
0x1400038f6  mov     [rsp+arg_0], rcx
0x1400038fb  push    rdi
0x1400038fc  push    r14
0x1400038fe  push    r15
0x140003900  sub     rsp, 30h
0x140003904  mov     r14, r8
0x140003907  mov     r15, rdx
0x14000390a  mov     rbx, rcx
0x14000390d  xor     edi, edi
0x14000390f  or      dword ptr [r8], 0FFFFFFFFh
0x140003913  add     rcx, 20h ; ' '; this
0x140003917  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x14000391c  nop
0x14000391d  mov     ecx, [rbx+14h]
0x140003920  test    ecx, ecx
0x140003922  jnz     short loc_140003939
0x140003924  mov     rcx, rbx; this
0x140003927  call    ?Grow@TrackerList@@AEAAJXZ; TrackerList::Grow(void)
0x14000392c  mov     edi, eax
0x14000392e  mov     [rsp+48h+var_28], eax
0x140003932  test    eax, eax
0x140003934  jnz     short loc_14000398B
0x140003936  mov     ecx, [rbx+14h]
0x140003939  movsxd  r9, dword ptr [rbx+0Ch]
0x14000393d  mov     r8, r9
0x140003940  add     r8, r8
0x140003943  mov     r10, [rbx]
0x140003946  mov     eax, [r10+r8*8+8]
0x14000394b  mov     [rbx+0Ch], eax
0x14000394e  dec     ecx
0x140003950  mov     [rbx+14h], ecx
0x140003953  mov     eax, [rbx+8]
0x140003956  cdq
0x140003957  sub     eax, edx
0x140003959  sar     eax, 1
0x14000395b  cmp     r9d, eax
0x14000395e  jl      short loc_140003963
0x140003960  dec     dword ptr [rbx+18h]
0x140003963  test    ecx, ecx
0x140003965  jnz     short loc_14000396B
0x140003967  or      dword ptr [rbx+10h], 0FFFFFFFFh
0x14000396b  test    r9d, r9d
0x14000396e  jns     short loc_14000397B
0x140003970  mov     edi, 8000FFFFh
0x140003975  mov     [rsp+48h+var_28], edi
0x140003979  jmp     short loc_14000398B
0x14000397b  mov     [r10+r8*8], r15
0x14000397f  mov     rax, [rbx]
0x140003982  or      qword ptr [rax+r8*8+8], 0FFFFFFFFFFFFFFFFh
0x140003988  mov     [r14], r9d
0x14000398b  lea     rcx, [rbx+20h]; this
0x14000398f  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x140003994  mov     eax, edi
0x140003996  mov     rbx, [rsp+48h+arg_8]
0x14000399b  mov     rsi, [rsp+48h+arg_10]
0x1400039a0  add     rsp, 30h
0x1400039a4  pop     r15
0x1400039a6  pop     r14
0x1400039a8  pop     rdi
0x1400039a9  retn
0x1400065b6  push    rbp
0x1400065b8  sub     rsp, 20h
0x1400065bc  mov     rbp, rdx
0x1400065bf  mov     rcx, [rbp+50h]
0x1400065c3  add     rcx, 20h ; ' '; this
0x1400065c7  add     rsp, 20h
0x1400065cb  pop     rbp
0x1400065cc  jmp     ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
```
