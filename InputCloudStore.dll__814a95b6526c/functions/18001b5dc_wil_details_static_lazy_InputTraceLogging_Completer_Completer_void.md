# wil::details::static_lazy<InputTraceLogging>::Completer::~Completer(void)

- ea: `0x18001b5dc`
- end: `0x18001b636`
- name: `??1Completer@?$static_lazy@VInputTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023f24`

## callees

- `0x18000165c`
- `0x18001b5dc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b62f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<InputTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x18001b5dc  mov     [rsp+arg_0], rbx
0x18001b5e1  push    rdi
0x18001b5e2  sub     rsp, 20h
0x18001b5e6  cmp     dword ptr [rcx+8], 0
0x18001b5ea  mov     rdi, rcx
0x18001b5ed  jnz     short loc_18001B61B
0x18001b5ef  mov     rbx, [rcx]
0x18001b5f2  mov     rcx, [rbx+20h]; CallbackContext
0x18001b5f6  mov     [rbx+10h], rcx
0x18001b5fa  mov     byte ptr [rbx+18h], 1
0x18001b5fe  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001b603  mov     rax, [rbx+8]
0x18001b607  lea     rcx, [rbx+8]
0x18001b60b  mov     dword ptr [rbx+1Ch], 1
0x18001b612  mov     rax, [rax+8]
0x18001b616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b61b  mov     rcx, [rdi]
0x18001b61e  mov     edx, [rdi+8]
0x18001b621  lea     r8, [rcx+8]
0x18001b625  mov     rbx, [rsp+28h+arg_0]
0x18001b62a  add     rsp, 20h
0x18001b62e  pop     rdi
0x18001b62f  jmp     cs:__imp_InitOnceComplete
```
