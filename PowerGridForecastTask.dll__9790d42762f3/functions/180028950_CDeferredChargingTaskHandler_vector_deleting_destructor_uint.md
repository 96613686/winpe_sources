# CDeferredChargingTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180028950`
- end: `0x18002898a`
- name: `??_ECDeferredChargingTaskHandler@@UEAAPEAXI@Z`
- size: `58`
- prototype: `CDeferredChargingTaskHandler *__fastcall(CDeferredChargingTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180027fd4`
- `0x180028950`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180028976`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028976`

## pseudocode

```c
CDeferredChargingTaskHandler *__fastcall CDeferredChargingTaskHandler::`vector deleting destructor'(
        CDeferredChargingTaskHandler *this,
        char a2)
{
  *(_QWORD *)this = &CDeferredChargingTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180028950  mov     [rsp+arg_0], rbx
0x180028955  push    rdi
0x180028956  sub     rsp, 20h
0x18002895a  lea     rax, ??_7CDeferredChargingTaskHandler@@6B@; const CDeferredChargingTaskHandler::`vftable'
0x180028961  mov     ebx, edx
0x180028963  mov     [rcx], rax
0x180028966  mov     rdi, rcx
0x180028969  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18002896e  test    bl, 1
0x180028971  jz      short loc_18002897C
0x180028973  mov     rcx, rdi
0x180028976  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002897c  mov     rbx, [rsp+28h+arg_0]
0x180028981  mov     rax, rdi
0x180028984  add     rsp, 20h
0x180028988  pop     rdi
0x180028989  retn
```
