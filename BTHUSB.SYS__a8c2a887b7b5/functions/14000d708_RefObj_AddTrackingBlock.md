# RefObj_AddTrackingBlock

- ea: `0x14000d708`
- end: `0x14000d808`
- name: `RefObj_AddTrackingBlock`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008120`
- `0x140009a10`

## callees

- `0x14000d708`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d7cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d7cb`
- `ntoskrnl!ExAllocatePool2` at `0x14000d78b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d78b`

## pseudocode

```c
void __fastcall RefObj_AddTrackingBlock(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  signed __int32 v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 Pool2; // rax
  _QWORD *v12; // rbx
  KSPIN_LOCK *v13; // rcx
  KIRQL v14; // al
  __int64 v15; // rdx

  v8 = _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 1028LL), 1u);
  v9 = *(_QWORD *)(a1 + 16);
  v10 = 5LL * (v8 % 25);
  *(_QWORD *)(v9 + 8 * v10 + 32) = a3;
  *(_DWORD *)(v9 + 8 * v10 + 24) = 0;
  *(_DWORD *)(v9 + 8 * v10 + 40) = a2;
  *(_QWORD *)(v9 + 8 * v10 + 48) = a4;
  *(_QWORD *)(v9 + 8 * v10 + 56) = MEMORY[0xFFFFF78000000320];
  Pool2 = ExAllocatePool2(64, 40, 1415996754);
  v12 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 24) = a3;
    *(_QWORD *)(Pool2 + 8) = a4;
    *(_DWORD *)(Pool2 + 32) = a2;
    v13 = (KSPIN_LOCK *)(*(_QWORD *)(a1 + 16) + 8LL);
    *(_QWORD *)(Pool2 + 16) = MEMORY[0xFFFFF78000000320];
    v14 = KeAcquireSpinLockRaiseToDpc(v13);
    v15 = *(_QWORD *)(a1 + 16);
    *v12 = *(_QWORD *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = v12;
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL), v14);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL));
  }
}

```

## disassembly

```asm
0x14000d708  push    rbx
0x14000d70a  push    rbp
0x14000d70b  push    rsi
0x14000d70c  push    rdi
0x14000d70d  push    r14
0x14000d70f  sub     rsp, 20h
0x14000d713  mov     r10, [rcx+10h]
0x14000d717  mov     rsi, r9
0x14000d71a  mov     rbp, r8
0x14000d71d  mov     r14d, edx
0x14000d720  mov     rdi, rcx
0x14000d723  mov     eax, 1
0x14000d728  lock xadd [r10+404h], eax
0x14000d731  mov     rcx, [rcx+10h]
0x14000d735  mov     r10d, eax
0x14000d738  mov     eax, 51EB851Fh
0x14000d73d  imul    r10d
0x14000d740  sar     edx, 3
0x14000d743  mov     eax, edx
0x14000d745  shr     eax, 1Fh
0x14000d748  add     edx, eax
0x14000d74a  imul    eax, edx, 19h
0x14000d74d  sub     r10d, eax
0x14000d750  movsxd  rax, r10d
0x14000d753  lea     rdx, [rax+rax*4]
0x14000d757  mov     [rcx+rdx*8+20h], r8
0x14000d75c  mov     r8d, 54666552h
0x14000d762  mov     dword ptr [rcx+rdx*8+18h], 0
0x14000d76a  mov     [rcx+rdx*8+28h], r14d
0x14000d76f  mov     [rcx+rdx*8+30h], r9
0x14000d774  mov     rax, ds:0FFFFF78000000320h
0x14000d77e  mov     [rcx+rdx*8+38h], rax
0x14000d783  mov     edx, 28h ; '('
0x14000d788  lea     ecx, [rdx+18h]
0x14000d78b  call    cs:__imp_ExAllocatePool2
0x14000d792  nop     dword ptr [rax+rax+00h]
0x14000d797  mov     rbx, rax
0x14000d79a  test    rax, rax
0x14000d79d  jnz     short loc_14000D7A9
0x14000d79f  mov     rax, [rdi+10h]
0x14000d7a3  lock inc dword ptr [rax+4]
0x14000d7a7  jmp     short loc_14000D7FC
0x14000d7a9  mov     [rax+18h], rbp
0x14000d7ad  mov     [rax+8], rsi
0x14000d7b1  mov     [rax+20h], r14d
0x14000d7b5  mov     rax, ds:0FFFFF78000000320h
0x14000d7bf  mov     rcx, [rdi+10h]
0x14000d7c3  add     rcx, 8; SpinLock
0x14000d7c7  mov     [rbx+10h], rax
0x14000d7cb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d7d2  nop     dword ptr [rax+rax+00h]
0x14000d7d7  mov     rdx, [rdi+10h]
0x14000d7db  mov     rcx, [rdx+10h]
0x14000d7df  mov     [rbx], rcx
0x14000d7e2  mov     [rdx+10h], rbx
0x14000d7e6  mov     dl, al; NewIrql
0x14000d7e8  mov     rcx, [rdi+10h]
0x14000d7ec  add     rcx, 8; SpinLock
0x14000d7f0  call    cs:__imp_KeReleaseSpinLock
0x14000d7f7  nop     dword ptr [rax+rax+00h]
0x14000d7fc  add     rsp, 20h
0x14000d800  pop     r14
0x14000d802  pop     rdi
0x14000d803  pop     rsi
0x14000d804  pop     rbp
0x14000d805  pop     rbx
0x14000d806  retn
```
