# __GSHandlerCheck_SEH

- ea: `0x140001f7c`
- end: `0x140001fe4`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `EXCEPTION_DISPOSITION __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001f10`
- `0x140001f7c`

## import_xrefs

- `msvcrt!__C_specific_handler` at `0x140001fd3`
- `msvcrt!__C_specific_handler` at `0x140001fd3`

## pseudocode

```c
EXCEPTION_DISPOSITION __fastcall _GSHandlerCheck_SEH(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  char *v8; // rbx
  EXCEPTION_DISPOSITION result; // eax

  v8 = (char *)DispatcherContext->HandlerData + 16 * *(unsigned int *)DispatcherContext->HandlerData;
  _GSHandlerCheckCommon(EstablisherFrame, DispatcherContext, v8 + 4);
  result = ExceptionContinueSearch;
  if ( ((((ExceptionRecord->ExceptionFlags & 0x66) != 0) + 1) & *((_DWORD *)v8 + 1)) != 0 )
    return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
  return result;
}

```

## disassembly

```asm
0x140001f7c  push    rbx
0x140001f7e  push    rbp
0x140001f7f  push    rsi
0x140001f80  push    rdi
0x140001f81  push    r14
0x140001f83  sub     rsp, 20h
0x140001f87  mov     r10, [r9+38h]
0x140001f8b  mov     rsi, rdx
0x140001f8e  mov     r14, r8
0x140001f91  mov     rbp, rcx
0x140001f94  mov     rdx, r9
0x140001f97  mov     rcx, rsi
0x140001f9a  mov     rdi, r9
0x140001f9d  mov     ebx, [r10]
0x140001fa0  shl     rbx, 4
0x140001fa4  add     rbx, r10
0x140001fa7  lea     r8, [rbx+4]
0x140001fab  call    __GSHandlerCheckCommon
0x140001fb0  mov     eax, [rbp+4]
0x140001fb3  and     al, 66h
0x140001fb5  neg     al
0x140001fb7  mov     eax, 1
0x140001fbc  sbb     edx, edx
0x140001fbe  neg     edx
0x140001fc0  add     edx, eax
0x140001fc2  test    [rbx+4], edx
0x140001fc5  jz      short loc_140001FD9
0x140001fc7  mov     r9, rdi; DispatcherContext
0x140001fca  mov     r8, r14; ContextRecord
0x140001fcd  mov     rdx, rsi; EstablisherFrame
0x140001fd0  mov     rcx, rbp; ExceptionRecord
0x140001fd3  call    cs:__imp___C_specific_handler
0x140001fd9  add     rsp, 20h
0x140001fdd  pop     r14
0x140001fdf  pop     rdi
0x140001fe0  pop     rsi
0x140001fe1  pop     rbp
0x140001fe2  pop     rbx
0x140001fe3  retn
```
