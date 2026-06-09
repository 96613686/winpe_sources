# wil::details::static_lazy<HostNameVerifierProvider>::Completer::~Completer(void)

- ea: `0x14000a28c`
- end: `0x14000a2e6`
- name: `??1Completer@?$static_lazy@VHostNameVerifierProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fe34`

## callees

- `0x1400019f0`
- `0x14000a28c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000a2df`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<HostNameVerifierProvider>::Completer::~Completer(_DWORD *a1)
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
0x14000a28c  mov     [rsp+arg_0], rbx
0x14000a291  push    rdi
0x14000a292  sub     rsp, 20h
0x14000a296  cmp     dword ptr [rcx+8], 0
0x14000a29a  mov     rdi, rcx
0x14000a29d  jnz     short loc_14000A2CB
0x14000a29f  mov     rbx, [rcx]
0x14000a2a2  mov     rcx, [rbx+20h]; CallbackContext
0x14000a2a6  mov     [rbx+10h], rcx
0x14000a2aa  mov     byte ptr [rbx+18h], 1
0x14000a2ae  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000a2b3  mov     rax, [rbx+8]
0x14000a2b7  lea     rcx, [rbx+8]
0x14000a2bb  mov     dword ptr [rbx+1Ch], 1
0x14000a2c2  mov     rax, [rax+8]
0x14000a2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2cb  mov     rcx, [rdi]
0x14000a2ce  mov     edx, [rdi+8]
0x14000a2d1  lea     r8, [rcx+8]
0x14000a2d5  mov     rbx, [rsp+28h+arg_0]
0x14000a2da  add     rsp, 20h
0x14000a2de  pop     rdi
0x14000a2df  jmp     cs:__imp_InitOnceComplete
```
