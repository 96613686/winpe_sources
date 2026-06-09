# XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(void)

- ea: `0x18001b838`
- end: `0x18001b872`
- name: `??1CProviderBinaryPathEvent@XPerfAddIn@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028a33`

## callees

- `0x18001b688`
- `0x18001b838`
- `0x18002a010`

## pseudocode

```c
void __fastcall XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this)
{
  volatile signed __int32 *v2; // rdx

  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 3) - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  std::vector<_GUID>::~vector<_GUID>(this);
}

```

## disassembly

```asm
0x18001b838  push    rbx
0x18001b83a  sub     rsp, 20h
0x18001b83e  mov     rdx, [rcx+18h]
0x18001b842  mov     rbx, rcx
0x18001b845  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001b849  or      eax, 0FFFFFFFFh
0x18001b84c  lock xadd [rdx+10h], eax
0x18001b851  sub     eax, 1
0x18001b854  jg      short loc_18001B865
0x18001b856  mov     rcx, [rdx]
0x18001b859  mov     rax, [rcx]
0x18001b85c  mov     rax, [rax+8]
0x18001b860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b865  mov     rcx, rbx
0x18001b868  add     rsp, 20h
0x18001b86c  pop     rbx
0x18001b86d  jmp     ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
```
