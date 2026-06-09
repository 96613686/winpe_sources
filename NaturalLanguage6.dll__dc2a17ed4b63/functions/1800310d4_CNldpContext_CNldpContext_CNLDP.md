# CNldpContext::CNldpContext(CNLDP *)

- ea: `0x1800310d4`
- end: `0x180031158`
- name: `??0CNldpContext@@QEAA@PEAVCNLDP@@@Z`
- size: `132`
- prototype: `CNldpContext *__fastcall(CNldpContext *__hidden this, struct CNLDP *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001681c`

## callees

- `0x180031160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031121`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031121`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180031109`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180031109`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CNldpContext *__fastcall CNldpContext::CNldpContext(CNldpContext *this, struct CNLDP *a2)
{
  CContext::CContext(this);
  *((_DWORD *)this + 130) = 0;
  *((_QWORD *)this + 64) = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 63) = CreateEventW(0, 0, 1, 0);
  *(_QWORD *)this = &CNldpContext::`vftable';
  *((_QWORD *)this + 66) = a2;
  *((_QWORD *)this + 67) = 0;
  return this;
}

```

## disassembly

```asm
0x1800310d4  mov     [rsp+arg_0], rcx
0x1800310d9  push    rdi
0x1800310da  sub     rsp, 30h
0x1800310de  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800310e7  mov     [rsp+38h+arg_8], rbx
0x1800310ec  mov     rbx, rdx
0x1800310ef  mov     rdi, rcx
0x1800310f2  call    ??0CContext@@QEAA@XZ; CContext::CContext(void)
0x1800310f7  nop
0x1800310f8  mov     dword ptr [rdi+208h], 0
0x180031102  xor     r8d, r8d; lpName
0x180031105  xor     edx, edx; bInitialOwner
0x180031107  xor     ecx, ecx; lpMutexAttributes
0x180031109  call    cs:__imp_CreateMutexW
0x18003110f  mov     [rdi+200h], rax
0x180031116  xor     r9d, r9d; lpName
0x180031119  xor     edx, edx; bManualReset
0x18003111b  xor     ecx, ecx; lpEventAttributes
0x18003111d  lea     r8d, [r9+1]; bInitialState
0x180031121  call    cs:__imp_CreateEventW
0x180031127  mov     [rdi+1F8h], rax
0x18003112e  lea     rax, ??_7CNldpContext@@6B@; const CNldpContext::`vftable'
0x180031135  mov     [rdi], rax
0x180031138  mov     [rdi+210h], rbx
0x18003113f  mov     qword ptr [rdi+218h], 0
0x18003114a  mov     rax, rdi
0x18003114d  mov     rbx, [rsp+38h+arg_8]
0x180031152  add     rsp, 30h
0x180031156  pop     rdi
0x180031157  retn
```
