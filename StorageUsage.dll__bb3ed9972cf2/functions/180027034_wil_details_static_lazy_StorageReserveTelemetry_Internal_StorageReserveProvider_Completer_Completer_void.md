# wil::details::static_lazy<StorageReserveTelemetry::Internal::StorageReserveProvider>::Completer::~Completer(void)

- ea: `0x180027034`
- end: `0x18002708e`
- name: `??1Completer@?$static_lazy@VStorageReserveProvider@Internal@StorageReserveTelemetry@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a480`

## callees

- `0x18000417c`
- `0x180027034`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180027087`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<StorageReserveTelemetry::Internal::StorageReserveProvider>::Completer::~Completer(
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
    TraceLoggingRegisterEx_EventRegister_2U(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180027034  mov     [rsp+arg_0], rbx
0x180027039  push    rdi
0x18002703a  sub     rsp, 20h
0x18002703e  cmp     dword ptr [rcx+8], 0
0x180027042  mov     rdi, rcx
0x180027045  jnz     short loc_180027073
0x180027047  mov     rbx, [rcx]
0x18002704a  mov     rcx, [rbx+20h]; CallbackContext
0x18002704e  mov     [rbx+10h], rcx
0x180027052  mov     byte ptr [rbx+18h], 1
0x180027056  call    TraceLoggingRegisterEx_EventRegister_2U
0x18002705b  mov     rax, [rbx+8]
0x18002705f  lea     rcx, [rbx+8]
0x180027063  mov     dword ptr [rbx+1Ch], 1
0x18002706a  mov     rax, [rax+8]
0x18002706e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027073  mov     rcx, [rdi]
0x180027076  mov     edx, [rdi+8]
0x180027079  lea     r8, [rcx+8]
0x18002707d  mov     rbx, [rsp+28h+arg_0]
0x180027082  add     rsp, 20h
0x180027086  pop     rdi
0x180027087  jmp     cs:__imp_InitOnceComplete
```
