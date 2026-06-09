# Event::Create(Event::ResetMode,bool)

- ea: `0x18006968c`
- end: `0x1800696c4`
- name: `?Create@Event@@SA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@W4ResetMode@1@_N@Z`
- size: `56`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b40`
- `0x1800695d0`
- `0x180096248`
- `0x1800a5678`

## callees

- `0x18006968c`
- `0x1800a1558`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800696a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800696a7`

## pseudocode

```c
_QWORD *__fastcall Event::Create(_QWORD *a1, int a2)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, a2 == 1, 0, 0);
  if ( !EventW )
    OSException::ThrowLastError();
  *a1 = EventW;
  return a1;
}

```

## disassembly

```asm
0x18006968c  push    rbx
0x18006968e  sub     rsp, 30h
0x180069692  mov     eax, edx
0x180069694  mov     rbx, rcx
0x180069697  xor     edx, edx
0x180069699  cmp     eax, 1
0x18006969c  setz    dl; bManualReset
0x18006969f  xor     r9d, r9d; lpName
0x1800696a2  xor     r8d, r8d; bInitialState
0x1800696a5  xor     ecx, ecx; lpEventAttributes
0x1800696a7  call    cs:__imp_CreateEventW
0x1800696ad  test    rax, rax
0x1800696b0  jz      short loc_1800696BE
0x1800696b2  mov     [rbx], rax
0x1800696b5  mov     rax, rbx
0x1800696b8  add     rsp, 30h
0x1800696bc  pop     rbx
0x1800696bd  retn
0x1800696be  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
