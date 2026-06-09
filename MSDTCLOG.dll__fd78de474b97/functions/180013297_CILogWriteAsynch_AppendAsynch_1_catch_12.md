# _CILogWriteAsynch::AppendAsynch_::_1_::catch$12

- ea: `0x180013297`
- end: `0x180013309`
- name: `_CILogWriteAsynch::AppendAsynch_::_1_::catch$12`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogWriteAsynch::AppendAsynch_::_1_::catch_12(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  *(_DWORD *)(a2 + 64) = *(_DWORD *)(a2 + 72);
  *(_QWORD *)(a2 + 80) = 0;
  v3 = *(_QWORD *)(a2 + 160);
  (**(void (__fastcall ***)(__int64))(v3 + 32))(v3 + 32);
  *(_DWORD *)(*(_QWORD *)(v3 + 152) + 24LL * *(unsigned int *)(a2 + 168) + 16) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v3 + 32) + 8LL))(v3 + 32);
  return 0;
}

```

## disassembly

```asm
0x180013297  mov     [rsp+arg_8], rdx
0x18001329c  push    rbx
0x18001329d  push    rbp
0x18001329e  push    rdi
0x18001329f  sub     rsp, 40h
0x1800132a3  mov     rbp, rdx
0x1800132a6  mov     eax, [rbp+48h]
0x1800132a9  mov     [rbp+40h], eax
0x1800132ac  mov     qword ptr [rbp+50h], 0
0x1800132b4  mov     rbx, [rbp+0A0h]
0x1800132bb  lea     rdi, [rbx+20h]
0x1800132bf  mov     rax, [rdi]
0x1800132c2  mov     rcx, rdi
0x1800132c5  mov     rax, [rax]
0x1800132c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132cd  mov     eax, [rbp+0A8h]
0x1800132d3  lea     rdx, [rax+rax*2]
0x1800132d7  mov     rax, [rbx+98h]
0x1800132de  mov     dword ptr [rax+rdx*8+10h], 0
0x1800132e6  mov     rax, [rdi]
0x1800132e9  mov     rcx, rdi
0x1800132ec  mov     rax, [rax+8]
0x1800132f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f5  nop
0x1800132f6  mov     rax, 0
0x180013300  add     rsp, 40h
0x180013304  pop     rdi
0x180013305  pop     rbp
0x180013306  pop     rbx
0x180013307  retn
```
