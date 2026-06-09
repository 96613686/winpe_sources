# CEtwEventBracket::CEtwEventBracket(_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18000e18c`
- end: `0x18000e1d9`
- name: `??0CEtwEventBracket@@QEAA@AEBU_EVENT_DESCRIPTOR@@0@Z`
- size: `77`
- prototype: `CEtwEventBracket *(CEtwEventBracket *__hidden this, const struct _EVENT_DESCRIPTOR *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ecc0`
- `0x18000eee0`
- `0x18000f670`
- `0x18000fb70`
- `0x18000fd0c`
- `0x180010670`

## callees

- `0x18000e18c`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x18000e1af`
- `ADVAPI32!EventEnabled` at `0x18000e1af`
- `ADVAPI32!EventWrite` at `0x18000e1c5`
- `ADVAPI32!EventWrite` at `0x18000e1c5`

## pseudocode

```c
CEtwEventBracket *__fastcall CEtwEventBracket::CEtwEventBracket(
        CEtwEventBracket *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _EVENT_DESCRIPTOR *a3)
{
  REGHANDLE v5; // rcx

  v5 = DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context;
  *(_QWORD *)this = DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context;
  *(struct _EVENT_DESCRIPTOR *)((char *)this + 8) = *a3;
  if ( EventEnabled(v5, a2) )
    EventWrite(*(_QWORD *)this, a2, 0, 0);
  return this;
}

```

## disassembly

```asm
0x18000e18c  mov     [rsp+arg_0], rbx
0x18000e191  push    rdi
0x18000e192  sub     rsp, 20h
0x18000e196  mov     rbx, rcx
0x18000e199  mov     rdi, rdx
0x18000e19c  mov     rcx, cs:DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context; RegHandle
0x18000e1a3  mov     [rbx], rcx
0x18000e1a6  movups  xmm0, xmmword ptr [r8]
0x18000e1aa  movdqu  xmmword ptr [rbx+8], xmm0
0x18000e1af  call    cs:__imp_EventEnabled
0x18000e1b5  test    al, al
0x18000e1b7  jz      short loc_18000E1CB
0x18000e1b9  mov     rcx, [rbx]; RegHandle
0x18000e1bc  xor     r9d, r9d; UserData
0x18000e1bf  xor     r8d, r8d; UserDataCount
0x18000e1c2  mov     rdx, rdi; EventDescriptor
0x18000e1c5  call    cs:__imp_EventWrite
0x18000e1cb  mov     rax, rbx
0x18000e1ce  mov     rbx, [rsp+28h+arg_0]
0x18000e1d3  add     rsp, 20h
0x18000e1d7  pop     rdi
0x18000e1d8  retn
```
