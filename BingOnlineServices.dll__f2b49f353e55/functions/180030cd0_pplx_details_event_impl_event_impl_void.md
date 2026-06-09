# pplx::details::event_impl::event_impl(void)

- ea: `0x180030cd0`
- end: `0x180030d05`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `53`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011df4`
- `0x1800149e8`
- `0x18001a458`

## callees

- `0x180030cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030cf6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030cf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030ce5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030ce5`

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
0x180030cd0  push    rbx
0x180030cd2  sub     rsp, 20h
0x180030cd6  xor     r9d, r9d; lpName
0x180030cd9  mov     rbx, rcx
0x180030cdc  xor     r8d, r8d; bInitialState
0x180030cdf  xor     ecx, ecx; lpEventAttributes
0x180030ce1  lea     edx, [r9+1]; bManualReset
0x180030ce5  call    cs:__imp_CreateEventW
0x180030ceb  mov     [rbx], rax
0x180030cee  test    rax, rax
0x180030cf1  jz      short loc_180030CFC
0x180030cf3  mov     rcx, rax; hEvent
0x180030cf6  call    cs:__imp_ResetEvent
0x180030cfc  mov     rax, rbx
0x180030cff  add     rsp, 20h
0x180030d03  pop     rbx
0x180030d04  retn
```
