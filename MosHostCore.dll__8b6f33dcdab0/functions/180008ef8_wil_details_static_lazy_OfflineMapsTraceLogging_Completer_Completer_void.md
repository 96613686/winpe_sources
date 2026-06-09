# wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)

- ea: `0x180008ef8`
- end: `0x180008f52`
- name: `??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000afdc`

## callees

- `0x18000170c`
- `0x180008ef8`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008f4b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180008ef8  mov     [rsp+arg_0], rbx
0x180008efd  push    rdi
0x180008efe  sub     rsp, 20h
0x180008f02  cmp     dword ptr [rcx+8], 0
0x180008f06  mov     rdi, rcx
0x180008f09  jnz     short loc_180008F37
0x180008f0b  mov     rbx, [rcx]
0x180008f0e  mov     rcx, [rbx+20h]; CallbackContext
0x180008f12  mov     [rbx+10h], rcx
0x180008f16  mov     byte ptr [rbx+18h], 1
0x180008f1a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180008f1f  mov     rax, [rbx+8]
0x180008f23  lea     rcx, [rbx+8]
0x180008f27  mov     dword ptr [rbx+1Ch], 1
0x180008f2e  mov     rax, [rax+8]
0x180008f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f37  mov     rcx, [rdi]
0x180008f3a  mov     edx, [rdi+8]
0x180008f3d  lea     r8, [rcx+8]
0x180008f41  mov     rbx, [rsp+28h+arg_0]
0x180008f46  add     rsp, 20h
0x180008f4a  pop     rdi
0x180008f4b  jmp     cs:__imp_InitOnceComplete
```
