# wil::details::static_lazy<TraceProvider>::Completer::~Completer(void)

- ea: `0x18000d6c0`
- end: `0x18000d71f`
- name: `??1Completer@?$static_lazy@VTraceProvider@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010b48`

## callees

- `0x180001d78`
- `0x18000d6c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d718`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<TraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000d6c0  mov     [rsp+arg_0], rbx
0x18000d6c5  push    rdi
0x18000d6c6  sub     rsp, 20h
0x18000d6ca  cmp     dword ptr [rcx+8], 0
0x18000d6ce  mov     rdi, rcx
0x18000d6d1  jnz     short loc_18000D704
0x18000d6d3  mov     rbx, [rcx]
0x18000d6d6  xor     r8d, r8d
0x18000d6d9  xor     edx, edx
0x18000d6db  mov     rcx, [rbx+20h]; CallbackContext
0x18000d6df  mov     [rbx+10h], rcx
0x18000d6e3  mov     byte ptr [rbx+18h], 1
0x18000d6e7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000d6ec  mov     rax, [rbx+8]
0x18000d6f0  lea     rcx, [rbx+8]
0x18000d6f4  mov     dword ptr [rbx+1Ch], 1
0x18000d6fb  mov     rax, [rax+8]
0x18000d6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d704  mov     rcx, [rdi]
0x18000d707  mov     edx, [rdi+8]
0x18000d70a  lea     r8, [rcx+8]
0x18000d70e  mov     rbx, [rsp+28h+arg_0]
0x18000d713  add     rsp, 20h
0x18000d717  pop     rdi
0x18000d718  jmp     cs:__imp_InitOnceComplete
```
