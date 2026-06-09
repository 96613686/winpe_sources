# BfPreReadWrite

- ea: `0x140006010`
- end: `0x1400060db`
- name: `BfPreReadWrite`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006010`
- `0x1400060f0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400060c8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400060c8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400060a9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400060a9`

## pseudocode

```c
__int64 __fastcall BfPreReadWrite(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  if ( a1->Iopb->TargetFileObject && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) == 0 )
    BfCheckAndSwitchTarget(a1);
  return 1;
}

```

## disassembly

```asm
0x140006010  push    rbx
0x140006012  push    rbp
0x140006013  push    rsi
0x140006014  push    rdi
0x140006015  sub     rsp, 28h
0x140006019  mov     rax, [rcx+10h]
0x14000601d  mov     rdi, r8
0x140006020  mov     rbx, rcx
0x140006023  mov     [rsp+48h+arg_0], 0
0x140006028  cmp     qword ptr [rax+8], 0
0x14000602d  jnz     short loc_14000603E
0x14000602f  mov     eax, 1
0x140006034  add     rsp, 28h
0x140006038  pop     rdi
0x140006039  pop     rsi
0x14000603a  pop     rbp
0x14000603b  pop     rbx
0x14000603c  retn
0x14000603e  mov     rax, [rdx+20h]
0x140006042  mov     r9d, [rax+50h]
0x140006046  bt      r9d, 16h
0x14000604b  jb      short loc_14000602F
0x14000604d  lea     r9, [rsp+48h+arg_0]
0x140006052  call    BfCheckAndSwitchTarget
0x140006057  test    eax, eax
0x140006059  js      short loc_14000602F
0x14000605b  cmp     [rsp+48h+arg_0], 0
0x140006060  jz      short loc_14000602F
0x140006062  mov     rax, [rbx+10h]
0x140006066  cmp     byte ptr [rax+4], 4
0x14000606a  jnz     short loc_1400060D4
0x14000606c  mov     rdx, [rdi]
0x14000606f  test    rdx, rdx
0x140006072  jz      short loc_1400060D4
0x140006074  mov     rcx, [rdx+8]
0x140006078  test    rcx, rcx
0x14000607b  jz      short loc_1400060D4
0x14000607d  mov     rbp, [rcx+18h]
0x140006081  mov     rcx, [rax+28h]
0x140006085  mov     ebx, [rax+18h]
0x140006088  mov     rax, 7FFFFFFFFFFFFFFFh
0x140006092  add     rbx, rcx
0x140006095  cmp     rbx, rcx
0x140006098  cmovl   rbx, rax
0x14000609c  cmp     rbx, [rbp+28h]
0x1400060a0  jg      short loc_1400060D4
0x1400060a2  lea     rsi, [rdx+18h]
0x1400060a6  mov     rcx, rsi; RunRef
0x1400060a9  call    cs:__imp_ExAcquireRundownProtection
0x1400060b0  nop     dword ptr [rax+rax+00h]
0x1400060b5  test    al, al
0x1400060b7  jz      short loc_1400060D4
0x1400060b9  cmp     rbx, [rbp+28h]
0x1400060bd  jg      short loc_1400060C5
0x1400060bf  or      qword ptr [rdi], 1
0x1400060c3  jmp     short loc_1400060D4
0x1400060c5  mov     rcx, rsi; RunRef
0x1400060c8  call    cs:__imp_ExReleaseRundownProtection
0x1400060cf  nop     dword ptr [rax+rax+00h]
0x1400060d4  xor     eax, eax
0x1400060d6  jmp     loc_140006034
```
