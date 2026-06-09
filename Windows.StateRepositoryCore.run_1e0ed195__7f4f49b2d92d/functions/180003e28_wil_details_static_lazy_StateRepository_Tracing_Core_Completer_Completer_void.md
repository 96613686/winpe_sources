# wil::details::static_lazy<StateRepository::Tracing::Core>::Completer::~Completer(void)

- ea: `0x180003e28`
- end: `0x180003e82`
- name: `??1Completer@?$static_lazy@VCore@Tracing@StateRepository@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ac58`

## callees

- `0x1800016d0`
- `0x180003e28`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003e7b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<StateRepository::Tracing::Core>::Completer::~Completer(_DWORD *a1)
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
0x180003e28  mov     [rsp+arg_0], rbx
0x180003e2d  push    rdi
0x180003e2e  sub     rsp, 20h
0x180003e32  cmp     dword ptr [rcx+8], 0
0x180003e36  mov     rdi, rcx
0x180003e39  jnz     short loc_180003E67
0x180003e3b  mov     rbx, [rcx]
0x180003e3e  mov     rcx, [rbx+20h]; CallbackContext
0x180003e42  mov     [rbx+10h], rcx
0x180003e46  mov     byte ptr [rbx+18h], 1
0x180003e4a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180003e4f  mov     rax, [rbx+8]
0x180003e53  lea     rcx, [rbx+8]
0x180003e57  mov     dword ptr [rbx+1Ch], 1
0x180003e5e  mov     rax, [rax+8]
0x180003e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e67  mov     rcx, [rdi]
0x180003e6a  mov     edx, [rdi+8]
0x180003e6d  lea     r8, [rcx+8]
0x180003e71  mov     rbx, [rsp+28h+arg_0]
0x180003e76  add     rsp, 20h
0x180003e7a  pop     rdi
0x180003e7b  jmp     cs:__imp_InitOnceComplete
```
