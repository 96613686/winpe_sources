# wil::details::static_lazy<StateRepository::Tracing::Broker>::Completer::~Completer(void)

- ea: `0x180003f8c`
- end: `0x180003fe6`
- name: `??1Completer@?$static_lazy@VBroker@Tracing@StateRepository@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000687c`

## callees

- `0x1800016d0`
- `0x180003f8c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003fdf`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<StateRepository::Tracing::Broker>::Completer::~Completer(_DWORD *a1)
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
0x180003f8c  mov     [rsp+arg_0], rbx
0x180003f91  push    rdi
0x180003f92  sub     rsp, 20h
0x180003f96  cmp     dword ptr [rcx+8], 0
0x180003f9a  mov     rdi, rcx
0x180003f9d  jnz     short loc_180003FCB
0x180003f9f  mov     rbx, [rcx]
0x180003fa2  mov     rcx, [rbx+20h]; CallbackContext
0x180003fa6  mov     [rbx+10h], rcx
0x180003faa  mov     byte ptr [rbx+18h], 1
0x180003fae  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180003fb3  mov     rax, [rbx+8]
0x180003fb7  lea     rcx, [rbx+8]
0x180003fbb  mov     dword ptr [rbx+1Ch], 1
0x180003fc2  mov     rax, [rax+8]
0x180003fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fcb  mov     rcx, [rdi]
0x180003fce  mov     edx, [rdi+8]
0x180003fd1  lea     r8, [rcx+8]
0x180003fd5  mov     rbx, [rsp+28h+arg_0]
0x180003fda  add     rsp, 20h
0x180003fde  pop     rdi
0x180003fdf  jmp     cs:__imp_InitOnceComplete
```
