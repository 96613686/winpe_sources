# _invoke_watson

- ea: `0x180001d0c`
- end: `0x180001df1`
- name: `_invoke_watson`
- size: `229`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d00`

## callees

- `0x180001d0c`
- `0x180005f60`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x180001da6`
- `KERNEL32!RtlVirtualUnwind` at `0x180001da6`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001d67`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001d67`
- `KERNEL32!RtlCaptureContext` at `0x180001d52`
- `KERNEL32!RtlCaptureContext` at `0x180001d52`
- `KERNEL32!OutputDebugStringA` at `0x180001dcb`
- `KERNEL32!OutputDebugStringA` at `0x180001dcb`

## pseudocode

```c
void __cdecl __noreturn invoke_watson(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  ULONG64 Rip; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v6; // rax
  unsigned __int64 ImageBase; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+48h] [rbp-B8h] BYREF
  PVOID HandlerData; // [rsp+50h] [rbp-B0h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+60h] [rbp-A0h] BYREF
  DWORD64 retaddr; // [rsp+548h] [rbp+448h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  v6 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v6 )
  {
    RtlVirtualUnwind(0, ImageBase, Rip, v6, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&retaddr;
  }
  OutputDebugStringA("Invalid parameter passed to C runtime function.\n");
}

```

## disassembly

```asm
0x180001d0c  mov     [rsp-8+arg_0], rbx
0x180001d11  push    rbp
0x180001d12  lea     rbp, [rsp-440h]
0x180001d1a  sub     rsp, 540h
0x180001d21  mov     rax, cs:__security_cookie
0x180001d28  xor     rax, rsp
0x180001d2b  mov     [rbp+440h+var_10], rax
0x180001d32  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x180001d37  mov     [rsp+540h+var_4F8], 0
0x180001d40  mov     [rsp+540h+var_4F0], 0
0x180001d49  mov     [rsp+540h+ImageBase], 0
0x180001d52  call    cs:__imp_RtlCaptureContext
0x180001d58  mov     rbx, [rbp+440h+ContextRecord.Rip]
0x180001d5c  lea     rdx, [rsp+540h+ImageBase]; ImageBase
0x180001d61  mov     rcx, rbx; ControlPc
0x180001d64  xor     r8d, r8d; HistoryTable
0x180001d67  call    cs:__imp_RtlLookupFunctionEntry
0x180001d6d  test    rax, rax
0x180001d70  jz      short loc_180001DAE
0x180001d72  mov     rdx, [rsp+540h+ImageBase]; ImageBase
0x180001d77  lea     rcx, [rsp+540h+var_4F8]
0x180001d7c  mov     [rsp+540h+ContextPointers], 0; ContextPointers
0x180001d85  mov     r9, rax; FunctionEntry
0x180001d88  mov     [rsp+540h+EstablisherFrame], rcx; EstablisherFrame
0x180001d8d  mov     r8, rbx; ControlPc
0x180001d90  lea     rcx, [rsp+540h+var_4F0]
0x180001d95  mov     [rsp+540h+HandlerData], rcx; HandlerData
0x180001d9a  lea     rcx, [rsp+540h+ContextRecord]
0x180001d9f  mov     [rsp+540h+var_520], rcx; ContextRecord
0x180001da4  xor     ecx, ecx; HandlerType
0x180001da6  call    cs:__imp_RtlVirtualUnwind
0x180001dac  jmp     short loc_180001DC4
0x180001dae  mov     rax, [rbp+448h]
0x180001db5  mov     [rbp+440h+ContextRecord.Rip], rax
0x180001db9  lea     rax, [rbp+448h]
0x180001dc0  mov     [rbp+440h+ContextRecord.Rsp], rax
0x180001dc4  lea     rcx, OutputString; "Invalid parameter passed to C runtime f"...
0x180001dcb  call    cs:__imp_OutputDebugStringA
0x180001dd1  mov     rcx, [rbp+440h+var_10]
0x180001dd8  xor     rcx, rsp; StackCookie
0x180001ddb  call    __security_check_cookie
0x180001de0  mov     rbx, [rsp+540h+arg_0]
0x180001de8  add     rsp, 540h
0x180001def  pop     rbp
0x180001df0  retn
```
