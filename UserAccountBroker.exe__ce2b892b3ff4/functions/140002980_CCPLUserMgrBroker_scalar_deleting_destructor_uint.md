# CCPLUserMgrBroker::`scalar deleting destructor'(uint)

- ea: `0x140002980`
- end: `0x1400029af`
- name: `??_GCCPLUserMgrBroker@@EEAAPEAXI@Z`
- size: `47`
- prototype: `CCPLUserMgrBroker *__fastcall(CCPLUserMgrBroker *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001184`
- `0x14000264c`
- `0x140002980`

## pseudocode

```c
CCPLUserMgrBroker *__fastcall CCPLUserMgrBroker::`scalar deleting destructor'(CCPLUserMgrBroker *this, char a2)
{
  CCPLUserMgrBroker::~CCPLUserMgrBroker(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002980  mov     [rsp+arg_0], rbx
0x140002985  push    rdi
0x140002986  sub     rsp, 20h
0x14000298a  mov     ebx, edx
0x14000298c  mov     rdi, rcx
0x14000298f  call    ??1CCPLUserMgrBroker@@EEAA@XZ; CCPLUserMgrBroker::~CCPLUserMgrBroker(void)
0x140002994  test    bl, 1
0x140002997  jz      short loc_1400029A1
0x140002999  mov     rcx, rdi; Block
0x14000299c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400029a1  mov     rbx, [rsp+28h+arg_0]
0x1400029a6  mov     rax, rdi
0x1400029a9  add     rsp, 20h
0x1400029ad  pop     rdi
0x1400029ae  retn
```
