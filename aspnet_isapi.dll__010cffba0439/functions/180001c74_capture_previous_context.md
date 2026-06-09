# capture_previous_context

- ea: `0x180001c74`
- end: `0x180001ce5`
- name: `capture_previous_context`
- size: `113`
- prototype: `__int64 __fastcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001ba0`

## callees

- `0x180001c74`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x180001cd0`
- `KERNEL32!RtlVirtualUnwind` at `0x180001cd0`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001c99`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001c99`
- `KERNEL32!RtlCaptureContext` at `0x180001c7f`
- `KERNEL32!RtlCaptureContext` at `0x180001c7f`

## pseudocode

```c
struct _IMAGE_RUNTIME_FUNCTION_ENTRY *__fastcall capture_previous_context(PCONTEXT ContextRecord)
{
  ULONG64 Rip; // rsi
  int i; // edi
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *result; // rax
  unsigned __int64 ImageBase; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+68h] [rbp+10h] BYREF
  PVOID HandlerData; // [rsp+70h] [rbp+18h] BYREF

  RtlCaptureContext(ContextRecord);
  Rip = ContextRecord->Rip;
  for ( i = 0; i < 2; ++i )
  {
    result = RtlLookupFunctionEntry(Rip, &ImageBase, 0);
    if ( !result )
      break;
    result = (struct _IMAGE_RUNTIME_FUNCTION_ENTRY *)RtlVirtualUnwind(
                                                       0,
                                                       ImageBase,
                                                       Rip,
                                                       result,
                                                       ContextRecord,
                                                       &HandlerData,
                                                       &EstablisherFrame,
                                                       0);
  }
  return result;
}

```

## disassembly

```asm
0x180001c74  push    rbx
0x180001c76  push    rsi
0x180001c77  push    rdi
0x180001c78  sub     rsp, 40h
0x180001c7c  mov     rbx, rcx
0x180001c7f  call    cs:__imp_RtlCaptureContext
0x180001c85  mov     rsi, [rbx+0F8h]
0x180001c8c  xor     edi, edi
0x180001c8e  xor     r8d, r8d; HistoryTable
0x180001c91  lea     rdx, [rsp+58h+ImageBase]; ImageBase
0x180001c96  mov     rcx, rsi; ControlPc
0x180001c99  call    cs:__imp_RtlLookupFunctionEntry
0x180001c9f  test    rax, rax
0x180001ca2  jz      short loc_180001CDD
0x180001ca4  and     [rsp+58h+var_20], 0
0x180001caa  lea     rcx, [rsp+58h+arg_8]
0x180001caf  mov     rdx, [rsp+58h+ImageBase]; ImageBase
0x180001cb4  mov     r9, rax; FunctionEntry
0x180001cb7  mov     [rsp+58h+EstablisherFrame], rcx; EstablisherFrame
0x180001cbc  mov     r8, rsi; ControlPc
0x180001cbf  lea     rcx, [rsp+58h+arg_10]
0x180001cc4  mov     [rsp+58h+HandlerData], rcx; HandlerData
0x180001cc9  xor     ecx, ecx; HandlerType
0x180001ccb  mov     [rsp+58h+ContextRecord], rbx; ContextRecord
0x180001cd0  call    cs:__imp_RtlVirtualUnwind
0x180001cd6  inc     edi
0x180001cd8  cmp     edi, 2
0x180001cdb  jl      short loc_180001C8E
0x180001cdd  add     rsp, 40h
0x180001ce1  pop     rdi
0x180001ce2  pop     rsi
0x180001ce3  pop     rbx
0x180001ce4  retn
```
