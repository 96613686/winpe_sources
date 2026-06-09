# XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(void)

- ea: `0x180018138`
- end: `0x180018189`
- name: `??1CProviderBinaryPathEvent@XPerfAddIn@@QEAA@XZ`
- size: `81`
- prototype: `void __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180028ed7`

## callees

- `0x180018138`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
void __fastcall XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this)
{
  volatile signed __int32 *v2; // rdx
  void *v3; // rcx

  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 4) - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    operator delete(v3);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180018138  push    rbx
0x18001813a  sub     rsp, 20h
0x18001813e  mov     rdx, [rcx+20h]
0x180018142  mov     rbx, rcx
0x180018145  sub     rdx, 18h
0x180018149  or      eax, 0FFFFFFFFh
0x18001814c  lock xadd [rdx+10h], eax
0x180018151  sub     eax, 1
0x180018154  jg      short loc_180018166
0x180018156  mov     rcx, [rdx]
0x180018159  mov     rax, [rcx]
0x18001815c  mov     rax, [rax+8]
0x180018160  call    cs:__guard_dispatch_icall_fptr
0x180018166  mov     rcx, [rbx+8]; Block
0x18001816a  test    rcx, rcx
0x18001816d  jz      short loc_180018174
0x18001816f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018174  and     qword ptr [rbx+8], 0
0x180018179  and     qword ptr [rbx+10h], 0
0x18001817e  and     qword ptr [rbx+18h], 0
0x180018183  add     rsp, 20h
0x180018187  pop     rbx
0x180018188  retn
```
