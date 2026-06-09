# __GSHandlerCheck_SEH

- ea: `0x1800032b0`
- end: `0x180003318`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `EXCEPTION_DISPOSITION __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003244`
- `0x1800032b0`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x180003307`
- `api-ms-win-core-crt-l1-1-0!__C_specific_handler` at `0x180003307`

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
0x1800032b0  push    rbx
0x1800032b2  push    rbp
0x1800032b3  push    rsi
0x1800032b4  push    rdi
0x1800032b5  push    r14
0x1800032b7  sub     rsp, 20h
0x1800032bb  mov     r10, [r9+38h]
0x1800032bf  mov     rsi, rdx
0x1800032c2  mov     r14, r8
0x1800032c5  mov     rbp, rcx
0x1800032c8  mov     rdx, r9
0x1800032cb  mov     rcx, rsi
0x1800032ce  mov     rdi, r9
0x1800032d1  mov     ebx, [r10]
0x1800032d4  shl     rbx, 4
0x1800032d8  add     rbx, r10
0x1800032db  lea     r8, [rbx+4]
0x1800032df  call    __GSHandlerCheckCommon
0x1800032e4  mov     eax, [rbp+4]
0x1800032e7  and     al, 66h
0x1800032e9  neg     al
0x1800032eb  mov     eax, 1
0x1800032f0  sbb     edx, edx
0x1800032f2  neg     edx
0x1800032f4  add     edx, eax
0x1800032f6  test    [rbx+4], edx
0x1800032f9  jz      short loc_18000330D
0x1800032fb  mov     r9, rdi; DispatcherContext
0x1800032fe  mov     r8, r14; ContextRecord
0x180003301  mov     rdx, rsi; EstablisherFrame
0x180003304  mov     rcx, rbp; ExceptionRecord
0x180003307  call    cs:__imp___C_specific_handler
0x18000330d  add     rsp, 20h
0x180003311  pop     r14
0x180003313  pop     rdi
0x180003314  pop     rsi
0x180003315  pop     rbp
0x180003316  pop     rbx
0x180003317  retn
```
