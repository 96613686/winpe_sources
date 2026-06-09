# ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(uint)

- ea: `0x140003ed8`
- end: `0x140003ef8`
- name: `??_G?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400052e0`
- `0x140005c6c`
- `0x140009f50`

## callees

- `0x140003558`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003ee9`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ee9`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(void *a1)
{
  ATL::CComObjectCached<CRemoteAssistance>::~CComObjectCached<CRemoteAssistance>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003ed8  push    rbx
0x140003eda  sub     rsp, 20h
0x140003ede  mov     rbx, rcx
0x140003ee1  call    ??1?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAA@XZ; ATL::CComObjectCached<CRemoteAssistance>::~CComObjectCached<CRemoteAssistance>(void)
0x140003ee6  mov     rcx, rbx
0x140003ee9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003eef  mov     rax, rbx
0x140003ef2  add     rsp, 20h
0x140003ef6  pop     rbx
0x140003ef7  retn
```
