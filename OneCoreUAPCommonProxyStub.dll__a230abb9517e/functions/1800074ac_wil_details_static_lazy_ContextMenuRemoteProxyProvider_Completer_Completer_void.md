# wil::details::static_lazy<ContextMenuRemoteProxyProvider>::Completer::~Completer(void)

- ea: `0x1800074ac`
- end: `0x180007506`
- name: `??1Completer@?$static_lazy@VContextMenuRemoteProxyProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003458`

## callees

- `0x180001ad8`
- `0x1800074ac`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800074ff`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ContextMenuRemoteProxyProvider>::Completer::~Completer(_DWORD *a1)
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
0x1800074ac  mov     [rsp+arg_0], rbx
0x1800074b1  push    rdi
0x1800074b2  sub     rsp, 20h
0x1800074b6  cmp     dword ptr [rcx+8], 0
0x1800074ba  mov     rdi, rcx
0x1800074bd  jnz     short loc_1800074EB
0x1800074bf  mov     rbx, [rcx]
0x1800074c2  mov     rcx, [rbx+20h]; CallbackContext
0x1800074c6  mov     [rbx+10h], rcx
0x1800074ca  mov     byte ptr [rbx+18h], 1
0x1800074ce  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800074d3  mov     rax, [rbx+8]
0x1800074d7  lea     rcx, [rbx+8]
0x1800074db  mov     dword ptr [rbx+1Ch], 1
0x1800074e2  mov     rax, [rax+8]
0x1800074e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074eb  mov     rcx, [rdi]
0x1800074ee  mov     edx, [rdi+8]
0x1800074f1  lea     r8, [rcx+8]
0x1800074f5  mov     rbx, [rsp+28h+arg_0]
0x1800074fa  add     rsp, 20h
0x1800074fe  pop     rdi
0x1800074ff  jmp     cs:__imp_InitOnceComplete
```
