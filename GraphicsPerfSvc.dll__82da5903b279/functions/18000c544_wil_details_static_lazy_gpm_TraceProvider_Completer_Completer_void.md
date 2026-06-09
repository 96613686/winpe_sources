# wil::details::static_lazy<gpm::TraceProvider>::Completer::~Completer(void)

- ea: `0x18000c544`
- end: `0x18000c59e`
- name: `??1Completer@?$static_lazy@VTraceProvider@gpm@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d7e0`

## callees

- `0x180001754`
- `0x18000c544`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c597`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<gpm::TraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000c544  mov     [rsp+arg_0], rbx
0x18000c549  push    rdi
0x18000c54a  sub     rsp, 20h
0x18000c54e  cmp     dword ptr [rcx+8], 0
0x18000c552  mov     rdi, rcx
0x18000c555  jnz     short loc_18000C583
0x18000c557  mov     rbx, [rcx]
0x18000c55a  mov     rcx, [rbx+20h]; CallbackContext
0x18000c55e  mov     [rbx+10h], rcx
0x18000c562  mov     byte ptr [rbx+18h], 1
0x18000c566  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c56b  mov     rax, [rbx+8]
0x18000c56f  lea     rcx, [rbx+8]
0x18000c573  mov     dword ptr [rbx+1Ch], 1
0x18000c57a  mov     rax, [rax+8]
0x18000c57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c583  mov     rcx, [rdi]
0x18000c586  mov     edx, [rdi+8]
0x18000c589  lea     r8, [rcx+8]
0x18000c58d  mov     rbx, [rsp+28h+arg_0]
0x18000c592  add     rsp, 20h
0x18000c596  pop     rdi
0x18000c597  jmp     cs:__imp_InitOnceComplete
```
