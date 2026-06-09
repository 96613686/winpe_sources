# CTimeSyncTaskHandler::`scalar deleting destructor'(uint)

- ea: `0x180002250`
- end: `0x18000228e`
- name: `??_GCTimeSyncTaskHandler@@UEAAPEAXI@Z`
- size: `62`
- prototype: `CTimeSyncTaskHandler *__fastcall(CTimeSyncTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001484`
- `0x1800021a8`
- `0x180002250`

## pseudocode

```c
CTimeSyncTaskHandler *__fastcall CTimeSyncTaskHandler::`scalar deleting destructor'(
        CTimeSyncTaskHandler *this,
        char a2)
{
  *(_QWORD *)this = &CTimeSyncTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002250  mov     [rsp+arg_0], rbx
0x180002255  push    rdi
0x180002256  sub     rsp, 20h
0x18000225a  lea     rax, ??_7CTimeSyncTaskHandler@@6B@; const CTimeSyncTaskHandler::`vftable'
0x180002261  mov     ebx, edx
0x180002263  mov     [rcx], rax
0x180002266  mov     rdi, rcx
0x180002269  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18000226e  test    bl, 1
0x180002271  jz      short loc_180002280
0x180002273  mov     edx, 38h ; '8'; unsigned __int64
0x180002278  mov     rcx, rdi; void *
0x18000227b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002280  mov     rbx, [rsp+28h+arg_0]
0x180002285  mov     rax, rdi
0x180002288  add     rsp, 20h
0x18000228c  pop     rdi
0x18000228d  retn
```
