# ConnectionPointContainer::~ConnectionPointContainer(void)

- ea: `0x18001bff0`
- end: `0x18001c011`
- name: `??1ConnectionPointContainer@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(ConnectionPointContainer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c048`
- `0x180025e72`

## callees

- `0x1800195ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c00a`

## pseudocode

```c
void __fastcall ConnectionPointContainer::~ConnectionPointContainer(struct _RTL_CRITICAL_SECTION *this)
{
  std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::_Tidy(&this[1].LockCount);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18001bff0  push    rbx
0x18001bff2  sub     rsp, 20h
0x18001bff6  mov     rbx, rcx
0x18001bff9  add     rcx, 30h ; '0'
0x18001bffd  call    ?_Tidy@?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::_Tidy(void)
0x18001c002  mov     rcx, rbx
0x18001c005  add     rsp, 20h
0x18001c009  pop     rbx
0x18001c00a  jmp     cs:__imp_DeleteCriticalSection
```
