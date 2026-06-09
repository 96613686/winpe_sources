# wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(void)

- ea: `0x18001a6d0`
- end: `0x18001a72a`
- name: `??1Completer@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022fe0`

## callees

- `0x180001010`
- `0x18001a6d0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a723`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
BOOL __fastcall wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x18001a6d0  mov     [rsp+arg_0], rbx
0x18001a6d5  push    rdi
0x18001a6d6  sub     rsp, 20h
0x18001a6da  cmp     dword ptr [rcx+8], 0
0x18001a6de  mov     rdi, rcx
0x18001a6e1  jnz     short loc_18001A70F
0x18001a6e3  mov     rbx, [rcx]
0x18001a6e6  mov     rcx, [rbx+20h]; CallbackContext
0x18001a6ea  mov     [rbx+10h], rcx
0x18001a6ee  mov     byte ptr [rbx+18h], 1
0x18001a6f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001a6f7  mov     rax, [rbx+8]
0x18001a6fb  lea     rcx, [rbx+8]
0x18001a6ff  mov     dword ptr [rbx+1Ch], 1
0x18001a706  mov     rax, [rax+8]
0x18001a70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a70f  mov     rcx, [rdi]
0x18001a712  mov     edx, [rdi+8]
0x18001a715  lea     r8, [rcx+8]
0x18001a719  mov     rbx, [rsp+28h+arg_0]
0x18001a71e  add     rsp, 20h
0x18001a722  pop     rdi
0x18001a723  jmp     cs:__imp_InitOnceComplete
```
