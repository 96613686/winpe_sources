# capture_previous_context

- ea: `0x140002868`
- end: `0x1400028dc`
- name: `capture_previous_context`
- size: `116`
- prototype: `__int64 __fastcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140002790`

## callees

- `0x140002868`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x140002873`
- `KERNEL32!RtlCaptureContext` at `0x140002873`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000288d`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000288d`
- `KERNEL32!RtlVirtualUnwind` at `0x1400028c7`
- `KERNEL32!RtlVirtualUnwind` at `0x1400028c7`

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
0x140002868  push    rbx
0x14000286a  push    rsi
0x14000286b  push    rdi
0x14000286c  sub     rsp, 40h
0x140002870  mov     rbx, rcx
0x140002873  call    cs:__imp_RtlCaptureContext
0x140002879  mov     rsi, [rbx+0F8h]
0x140002880  xor     edi, edi
0x140002882  xor     r8d, r8d; HistoryTable
0x140002885  lea     rdx, [rsp+58h+ImageBase]; ImageBase
0x14000288a  mov     rcx, rsi; ControlPc
0x14000288d  call    cs:__imp_RtlLookupFunctionEntry
0x140002893  test    rax, rax
0x140002896  jz      short loc_1400028D4
0x140002898  mov     rdx, [rsp+58h+ImageBase]; ImageBase
0x14000289d  lea     rcx, [rsp+58h+arg_8]
0x1400028a2  mov     [rsp+58h+ContextPointers], 0; ContextPointers
0x1400028ab  mov     r9, rax; FunctionEntry
0x1400028ae  mov     [rsp+58h+EstablisherFrame], rcx; EstablisherFrame
0x1400028b3  mov     r8, rsi; ControlPc
0x1400028b6  lea     rcx, [rsp+58h+arg_10]
0x1400028bb  mov     [rsp+58h+HandlerData], rcx; HandlerData
0x1400028c0  xor     ecx, ecx; HandlerType
0x1400028c2  mov     [rsp+58h+ContextRecord], rbx; ContextRecord
0x1400028c7  call    cs:__imp_RtlVirtualUnwind
0x1400028cd  inc     edi
0x1400028cf  cmp     edi, 2
0x1400028d2  jl      short loc_140002882
0x1400028d4  add     rsp, 40h
0x1400028d8  pop     rdi
0x1400028d9  pop     rsi
0x1400028da  pop     rbx
0x1400028db  retn
```
