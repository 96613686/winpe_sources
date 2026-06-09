# DeleteContext::~DeleteContext(void)

- ea: `0x140012528`
- end: `0x140012550`
- name: `??1DeleteContext@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(DeleteContext *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140012420`
- `0x140012c58`

## callees

- `0x140006514`
- `0x14000e63c`
- `0x14000e66c`

## pseudocode

```c
void __fastcall DeleteContext::~DeleteContext(DeleteContext *this)
{
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close((char *)this + 16);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)this + 8);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(this);
}

```

## disassembly

```asm
0x140012528  push    rbx
0x14001252a  sub     rsp, 20h
0x14001252e  mov     rbx, rcx
0x140012531  add     rcx, 10h
0x140012535  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14001253a  lea     rcx, [rbx+8]
0x14001253e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012543  mov     rcx, rbx
0x140012546  add     rsp, 20h
0x14001254a  pop     rbx
0x14001254b  jmp     ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
```
