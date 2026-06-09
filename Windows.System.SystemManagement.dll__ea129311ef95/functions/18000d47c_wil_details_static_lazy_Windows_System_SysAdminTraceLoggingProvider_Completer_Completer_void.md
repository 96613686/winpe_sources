# wil::details::static_lazy<Windows::System::SysAdminTraceLoggingProvider>::Completer::~Completer(void)

- ea: `0x18000d47c`
- end: `0x18000d4d6`
- name: `??1Completer@?$static_lazy@VSysAdminTraceLoggingProvider@System@Windows@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f8a8`

## callees

- `0x180001d5c`
- `0x18000d47c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d4cf`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Windows::System::SysAdminTraceLoggingProvider>::Completer::~Completer(
        _DWORD *a1)
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
0x18000d47c  mov     [rsp+arg_0], rbx
0x18000d481  push    rdi
0x18000d482  sub     rsp, 20h
0x18000d486  cmp     dword ptr [rcx+8], 0
0x18000d48a  mov     rdi, rcx
0x18000d48d  jnz     short loc_18000D4BB
0x18000d48f  mov     rbx, [rcx]
0x18000d492  mov     rcx, [rbx+20h]; CallbackContext
0x18000d496  mov     [rbx+10h], rcx
0x18000d49a  mov     byte ptr [rbx+18h], 1
0x18000d49e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000d4a3  mov     rax, [rbx+8]
0x18000d4a7  lea     rcx, [rbx+8]
0x18000d4ab  mov     dword ptr [rbx+1Ch], 1
0x18000d4b2  mov     rax, [rax+8]
0x18000d4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4bb  mov     rcx, [rdi]
0x18000d4be  mov     edx, [rdi+8]
0x18000d4c1  lea     r8, [rcx+8]
0x18000d4c5  mov     rbx, [rsp+28h+arg_0]
0x18000d4ca  add     rsp, 20h
0x18000d4ce  pop     rdi
0x18000d4cf  jmp     cs:__imp_InitOnceComplete
```
