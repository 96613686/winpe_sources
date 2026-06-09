# wil::details::static_lazy<StateRepository::Tracing::Client>::Completer::~Completer(void)

- ea: `0x180005378`
- end: `0x1800053d2`
- name: `??1Completer@?$static_lazy@VClient@Tracing@StateRepository@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800083fc`

## callees

- `0x1800016d0`
- `0x180005378`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800053cb`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<StateRepository::Tracing::Client>::Completer::~Completer(_DWORD *a1)
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
0x180005378  mov     [rsp+arg_0], rbx
0x18000537d  push    rdi
0x18000537e  sub     rsp, 20h
0x180005382  cmp     dword ptr [rcx+8], 0
0x180005386  mov     rdi, rcx
0x180005389  jnz     short loc_1800053B7
0x18000538b  mov     rbx, [rcx]
0x18000538e  mov     rcx, [rbx+20h]; CallbackContext
0x180005392  mov     [rbx+10h], rcx
0x180005396  mov     byte ptr [rbx+18h], 1
0x18000539a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000539f  mov     rax, [rbx+8]
0x1800053a3  lea     rcx, [rbx+8]
0x1800053a7  mov     dword ptr [rbx+1Ch], 1
0x1800053ae  mov     rax, [rax+8]
0x1800053b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b7  mov     rcx, [rdi]
0x1800053ba  mov     edx, [rdi+8]
0x1800053bd  lea     r8, [rcx+8]
0x1800053c1  mov     rbx, [rsp+28h+arg_0]
0x1800053c6  add     rsp, 20h
0x1800053ca  pop     rdi
0x1800053cb  jmp     cs:__imp_InitOnceComplete
```
