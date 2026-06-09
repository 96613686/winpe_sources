# CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180002210`
- end: `0x180002242`
- name: `??_E?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001484`
- `0x180002210`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002210  push    rbx
0x180002212  sub     rsp, 20h
0x180002216  lea     rax, ??_7?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vftable'
0x18000221d  mov     rbx, rcx
0x180002220  mov     [rcx], rax
0x180002223  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000222a  test    dl, 1
0x18000222d  jz      short loc_180002239
0x18000222f  mov     edx, 10h; unsigned __int64
0x180002234  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002239  mov     rax, rbx
0x18000223c  add     rsp, 20h
0x180002240  pop     rbx
0x180002241  retn
```
