# capture_previous_context

- ea: `0x1800040c4`
- end: `0x180004135`
- name: `capture_previous_context`
- size: `113`
- prototype: `__int64 __fastcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003ff0`

## callees

- `0x1800040c4`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x1800040cf`
- `KERNEL32!RtlCaptureContext` at `0x1800040cf`
- `KERNEL32!RtlVirtualUnwind` at `0x180004120`
- `KERNEL32!RtlVirtualUnwind` at `0x180004120`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800040e9`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800040e9`

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
0x1800040c4  push    rbx
0x1800040c6  push    rsi
0x1800040c7  push    rdi
0x1800040c8  sub     rsp, 40h
0x1800040cc  mov     rbx, rcx
0x1800040cf  call    cs:__imp_RtlCaptureContext
0x1800040d5  mov     rsi, [rbx+0F8h]
0x1800040dc  xor     edi, edi
0x1800040de  xor     r8d, r8d; HistoryTable
0x1800040e1  lea     rdx, [rsp+58h+ImageBase]; ImageBase
0x1800040e6  mov     rcx, rsi; ControlPc
0x1800040e9  call    cs:__imp_RtlLookupFunctionEntry
0x1800040ef  test    rax, rax
0x1800040f2  jz      short loc_18000412D
0x1800040f4  and     [rsp+58h+var_20], 0
0x1800040fa  lea     rcx, [rsp+58h+arg_8]
0x1800040ff  mov     rdx, [rsp+58h+ImageBase]; ImageBase
0x180004104  mov     r9, rax; FunctionEntry
0x180004107  mov     [rsp+58h+EstablisherFrame], rcx; EstablisherFrame
0x18000410c  mov     r8, rsi; ControlPc
0x18000410f  lea     rcx, [rsp+58h+arg_10]
0x180004114  mov     [rsp+58h+HandlerData], rcx; HandlerData
0x180004119  xor     ecx, ecx; HandlerType
0x18000411b  mov     [rsp+58h+ContextRecord], rbx; ContextRecord
0x180004120  call    cs:__imp_RtlVirtualUnwind
0x180004126  inc     edi
0x180004128  cmp     edi, 2
0x18000412b  jl      short loc_1800040DE
0x18000412d  add     rsp, 40h
0x180004131  pop     rdi
0x180004132  pop     rsi
0x180004133  pop     rbx
0x180004134  retn
```
