# CEtwEventBracket::CEtwEventBracket(_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)

- ea: `0x1800a2a88`
- end: `0x1800a2ad5`
- name: `??0CEtwEventBracket@@QEAA@AEBU_EVENT_DESCRIPTOR@@0@Z`
- size: `77`
- prototype: `CEtwEventBracket *(CEtwEventBracket *__hidden this, const struct _EVENT_DESCRIPTOR *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a3180`
- `0x1800a32c0`
- `0x1800a3430`
- `0x1800a3570`
- `0x1800a37a0`
- `0x1800a3930`
- `0x1800a8d20`

## callees

- `0x1800a2a88`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a2ac1`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a2ac1`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a2aab`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a2aab`

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
0x1800a2a88  mov     [rsp+arg_0], rbx
0x1800a2a8d  push    rdi
0x1800a2a8e  sub     rsp, 20h
0x1800a2a92  mov     rbx, rcx
0x1800a2a95  mov     rdi, rdx
0x1800a2a98  mov     rcx, cs:DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context; RegHandle
0x1800a2a9f  mov     [rbx], rcx
0x1800a2aa2  movups  xmm0, xmmword ptr [r8]
0x1800a2aa6  movdqu  xmmword ptr [rbx+8], xmm0
0x1800a2aab  call    cs:__imp_EventEnabled
0x1800a2ab1  test    al, al
0x1800a2ab3  jz      short loc_1800A2AC7
0x1800a2ab5  mov     rcx, [rbx]; RegHandle
0x1800a2ab8  xor     r9d, r9d; UserData
0x1800a2abb  xor     r8d, r8d; UserDataCount
0x1800a2abe  mov     rdx, rdi; EventDescriptor
0x1800a2ac1  call    cs:__imp_EventWrite
0x1800a2ac7  mov     rax, rbx
0x1800a2aca  mov     rbx, [rsp+28h+arg_0]
0x1800a2acf  add     rsp, 20h
0x1800a2ad3  pop     rdi
0x1800a2ad4  retn
```
