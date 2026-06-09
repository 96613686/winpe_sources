# wil::details::static_lazy<BingPlatformNetworkServicesTraceLogging>::Completer::~Completer(void)

- ea: `0x18002fdfc`
- end: `0x18002fe56`
- name: `??1Completer@?$static_lazy@VBingPlatformNetworkServicesTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003218c`

## callees

- `0x180001760`
- `0x18002fdfc`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002fe4f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<BingPlatformNetworkServicesTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x18002fdfc  mov     [rsp+arg_0], rbx
0x18002fe01  push    rdi
0x18002fe02  sub     rsp, 20h
0x18002fe06  cmp     dword ptr [rcx+8], 0
0x18002fe0a  mov     rdi, rcx
0x18002fe0d  jnz     short loc_18002FE3B
0x18002fe0f  mov     rbx, [rcx]
0x18002fe12  mov     rcx, [rbx+20h]; CallbackContext
0x18002fe16  mov     [rbx+10h], rcx
0x18002fe1a  mov     byte ptr [rbx+18h], 1
0x18002fe1e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002fe23  mov     rax, [rbx+8]
0x18002fe27  lea     rcx, [rbx+8]
0x18002fe2b  mov     dword ptr [rbx+1Ch], 1
0x18002fe32  mov     rax, [rax+8]
0x18002fe36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe3b  mov     rcx, [rdi]
0x18002fe3e  mov     edx, [rdi+8]
0x18002fe41  lea     r8, [rcx+8]
0x18002fe45  mov     rbx, [rsp+28h+arg_0]
0x18002fe4a  add     rsp, 20h
0x18002fe4e  pop     rdi
0x18002fe4f  jmp     cs:__imp_InitOnceComplete
```
