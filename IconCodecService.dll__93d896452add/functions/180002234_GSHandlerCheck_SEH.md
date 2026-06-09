# __GSHandlerCheck_SEH

- ea: `0x180002234`
- end: `0x18000229c`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `EXCEPTION_DISPOSITION __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002234`
- `0x1800022b4`

## import_xrefs

- `msvcrt!__C_specific_handler` at `0x18000228b`
- `msvcrt!__C_specific_handler` at `0x18000228b`

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
0x180002234  push    rbx
0x180002236  push    rbp
0x180002237  push    rsi
0x180002238  push    rdi
0x180002239  push    r14
0x18000223b  sub     rsp, 20h
0x18000223f  mov     r10, [r9+38h]
0x180002243  mov     rsi, rdx
0x180002246  mov     r14, r8
0x180002249  mov     rbp, rcx
0x18000224c  mov     rdx, r9
0x18000224f  mov     rcx, rsi
0x180002252  mov     rdi, r9
0x180002255  mov     ebx, [r10]
0x180002258  shl     rbx, 4
0x18000225c  add     rbx, r10
0x18000225f  lea     r8, [rbx+4]
0x180002263  call    __GSHandlerCheckCommon
0x180002268  mov     eax, [rbp+4]
0x18000226b  and     al, 66h
0x18000226d  neg     al
0x18000226f  mov     eax, 1
0x180002274  sbb     edx, edx
0x180002276  neg     edx
0x180002278  add     edx, eax
0x18000227a  test    [rbx+4], edx
0x18000227d  jz      short loc_180002291
0x18000227f  mov     r9, rdi; DispatcherContext
0x180002282  mov     r8, r14; ContextRecord
0x180002285  mov     rdx, rsi; EstablisherFrame
0x180002288  mov     rcx, rbp; ExceptionRecord
0x18000228b  call    cs:__imp___C_specific_handler
0x180002291  add     rsp, 20h
0x180002295  pop     r14
0x180002297  pop     rdi
0x180002298  pop     rsi
0x180002299  pop     rbp
0x18000229a  pop     rbx
0x18000229b  retn
```
