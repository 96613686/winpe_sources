# wil::details::static_lazy<PrinterCleanUpLogging>::Completer::~Completer(void)

- ea: `0x18000a7f0`
- end: `0x18000a84a`
- name: `??1Completer@?$static_lazy@VPrinterCleanUpLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f59c`

## callees

- `0x180001790`
- `0x18000a7f0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a843`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PrinterCleanUpLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000a7f0  mov     [rsp+arg_0], rbx
0x18000a7f5  push    rdi
0x18000a7f6  sub     rsp, 20h
0x18000a7fa  cmp     dword ptr [rcx+8], 0
0x18000a7fe  mov     rdi, rcx
0x18000a801  jnz     short loc_18000A82F
0x18000a803  mov     rbx, [rcx]
0x18000a806  mov     rcx, [rbx+20h]; CallbackContext
0x18000a80a  mov     [rbx+10h], rcx
0x18000a80e  mov     byte ptr [rbx+18h], 1
0x18000a812  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000a817  mov     rax, [rbx+8]
0x18000a81b  lea     rcx, [rbx+8]
0x18000a81f  mov     dword ptr [rbx+1Ch], 1
0x18000a826  mov     rax, [rax+8]
0x18000a82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a82f  mov     rcx, [rdi]
0x18000a832  mov     edx, [rdi+8]
0x18000a835  lea     r8, [rcx+8]
0x18000a839  mov     rbx, [rsp+28h+arg_0]
0x18000a83e  add     rsp, 20h
0x18000a842  pop     rdi
0x18000a843  jmp     cs:__imp_InitOnceComplete
```
