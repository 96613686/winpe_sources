# CEtwEventBracket::~CEtwEventBracket(void)

- ea: `0x1800a2cd8`
- end: `0x1800a2d14`
- name: `??1CEtwEventBracket@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CEtwEventBracket *__hidden this)`
- caller_count: `12`
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
- `0x1800c0987`
- `0x1800c0a48`
- `0x1800c0b09`
- `0x1800c0b5a`
- `0x1800c108c`

## callees

- `0x1800a2cd8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a2d03`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a2d03`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a2cec`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a2cec`

## pseudocode

```c
void __fastcall CEtwEventBracket::~CEtwEventBracket(CEtwEventBracket *this)
{
  if ( EventEnabled(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8)) )
    EventWrite(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8), 0, 0);
}

```

## disassembly

```asm
0x1800a2cd8  mov     [rsp+arg_0], rbx
0x1800a2cdd  push    rdi
0x1800a2cde  sub     rsp, 20h
0x1800a2ce2  mov     rbx, rcx
0x1800a2ce5  lea     rdx, [rcx+8]; EventDescriptor
0x1800a2ce9  mov     rcx, [rcx]; RegHandle
0x1800a2cec  call    cs:__imp_EventEnabled
0x1800a2cf2  test    al, al
0x1800a2cf4  jz      short loc_1800A2D09
0x1800a2cf6  mov     rcx, [rbx]; RegHandle
0x1800a2cf9  lea     rdx, [rbx+8]; EventDescriptor
0x1800a2cfd  xor     r9d, r9d; UserData
0x1800a2d00  xor     r8d, r8d; UserDataCount
0x1800a2d03  call    cs:__imp_EventWrite
0x1800a2d09  mov     rbx, [rsp+28h+arg_0]
0x1800a2d0e  add     rsp, 20h
0x1800a2d12  pop     rdi
0x1800a2d13  retn
```
