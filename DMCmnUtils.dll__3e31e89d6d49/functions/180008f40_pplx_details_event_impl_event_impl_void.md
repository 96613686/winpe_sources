# pplx::details::event_impl::event_impl(void)

- ea: `0x180008f40`
- end: `0x180008f76`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800832c8`
- `0x180083434`
- `0x18008e8ac`

## callees

- `0x180008f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008f67`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008f67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008f56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008f56`

## pseudocode

```c
pplx::details::event_impl *__fastcall pplx::details::event_impl::event_impl(pplx::details::event_impl *this)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)this = EventW;
  if ( EventW )
    ResetEvent(EventW);
  return this;
}

```

## disassembly

```asm
0x180008f40  push    rbx
0x180008f42  sub     rsp, 20h
0x180008f46  mov     rbx, rcx
0x180008f49  xor     r9d, r9d; lpName
0x180008f4c  xor     ecx, ecx; lpEventAttributes
0x180008f4e  xor     r8d, r8d; bInitialState
0x180008f51  mov     edx, 1; bManualReset
0x180008f56  call    cs:__imp_CreateEventW
0x180008f5c  mov     [rbx], rax
0x180008f5f  test    rax, rax
0x180008f62  jz      short loc_180008F6D
0x180008f64  mov     rcx, rax; hEvent
0x180008f67  call    cs:__imp_ResetEvent
0x180008f6d  mov     rax, rbx
0x180008f70  add     rsp, 20h
0x180008f74  pop     rbx
0x180008f75  retn
```
