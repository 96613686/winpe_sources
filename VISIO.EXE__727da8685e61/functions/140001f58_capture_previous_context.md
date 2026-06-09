# capture_previous_context

- ea: `0x140001f58`
- end: `0x140001fcc`
- name: `capture_previous_context`
- size: `116`
- prototype: `__int64 __fastcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001e80`

## callees

- `0x140001f58`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x140001f63`
- `KERNEL32!RtlCaptureContext` at `0x140001f63`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140001f7d`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140001f7d`
- `KERNEL32!RtlVirtualUnwind` at `0x140001fb7`
- `KERNEL32!RtlVirtualUnwind` at `0x140001fb7`

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
0x140001f58  push    rbx
0x140001f5a  push    rsi
0x140001f5b  push    rdi
0x140001f5c  sub     rsp, 40h
0x140001f60  mov     rbx, rcx
0x140001f63  call    cs:RtlCaptureContext
0x140001f69  mov     rsi, [rbx+0F8h]
0x140001f70  xor     edi, edi
0x140001f72  xor     r8d, r8d; HistoryTable
0x140001f75  lea     rdx, [rsp+58h+ImageBase]; ImageBase
0x140001f7a  mov     rcx, rsi; ControlPc
0x140001f7d  call    cs:RtlLookupFunctionEntry
0x140001f83  test    rax, rax
0x140001f86  jz      short loc_140001FC4
0x140001f88  mov     rdx, [rsp+58h+ImageBase]; ImageBase
0x140001f8d  lea     rcx, [rsp+58h+arg_8]
0x140001f92  mov     [rsp+58h+ContextPointers], 0; ContextPointers
0x140001f9b  mov     r9, rax; FunctionEntry
0x140001f9e  mov     [rsp+58h+EstablisherFrame], rcx; EstablisherFrame
0x140001fa3  mov     r8, rsi; ControlPc
0x140001fa6  lea     rcx, [rsp+58h+arg_10]
0x140001fab  mov     [rsp+58h+HandlerData], rcx; HandlerData
0x140001fb0  xor     ecx, ecx; HandlerType
0x140001fb2  mov     [rsp+58h+ContextRecord], rbx; ContextRecord
0x140001fb7  call    cs:RtlVirtualUnwind
0x140001fbd  inc     edi
0x140001fbf  cmp     edi, 2
0x140001fc2  jl      short loc_140001F72
0x140001fc4  add     rsp, 40h
0x140001fc8  pop     rdi
0x140001fc9  pop     rsi
0x140001fca  pop     rbx
0x140001fcb  retn
```
