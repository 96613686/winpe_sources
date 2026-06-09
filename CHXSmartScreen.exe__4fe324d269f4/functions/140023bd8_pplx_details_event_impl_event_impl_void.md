# pplx::details::event_impl::event_impl(void)

- ea: `0x140023bd8`
- end: `0x140023c0f`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `55`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140014234`
- `0x140014aac`
- `0x14001ba38`

## callees

- `0x140023bd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140023c00`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140023c00`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x140023bef`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x140023bef`

## pseudocode

```c
pplx::details::event_impl *__fastcall pplx::details::event_impl::event_impl(pplx::details::event_impl *this)
{
  HANDLE Event; // rax

  Event = CreateEventExA(0, 0, 1u, 0x1F0003u);
  *(_QWORD *)this = Event;
  if ( Event )
    ResetEvent(Event);
  return this;
}

```

## disassembly

```asm
0x140023bd8  push    rbx
0x140023bda  sub     rsp, 20h
0x140023bde  xor     edx, edx; lpName
0x140023be0  mov     rbx, rcx
0x140023be3  mov     r9d, 1F0003h; dwDesiredAccess
0x140023be9  xor     ecx, ecx; lpEventAttributes
0x140023beb  lea     r8d, [rdx+1]; dwFlags
0x140023bef  call    cs:__imp_CreateEventExA
0x140023bf5  mov     [rbx], rax
0x140023bf8  test    rax, rax
0x140023bfb  jz      short loc_140023C06
0x140023bfd  mov     rcx, rax; hEvent
0x140023c00  call    cs:__imp_ResetEvent
0x140023c06  mov     rax, rbx
0x140023c09  add     rsp, 20h
0x140023c0d  pop     rbx
0x140023c0e  retn
```
