# wil::details::static_lazy<CodeIntegrity::Management::Telemetry::ManageCIProvider>::Completer::~Completer(void)

- ea: `0x1800054ec`
- end: `0x180005546`
- name: `??1Completer@?$static_lazy@VManageCIProvider@Telemetry@Management@CodeIntegrity@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800085f4`

## callees

- `0x180001864`
- `0x1800054ec`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000553f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CodeIntegrity::Management::Telemetry::ManageCIProvider>::Completer::~Completer(
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
0x1800054ec  mov     [rsp+arg_0], rbx
0x1800054f1  push    rdi
0x1800054f2  sub     rsp, 20h
0x1800054f6  cmp     dword ptr [rcx+8], 0
0x1800054fa  mov     rdi, rcx
0x1800054fd  jnz     short loc_18000552B
0x1800054ff  mov     rbx, [rcx]
0x180005502  mov     rcx, [rbx+20h]; CallbackContext
0x180005506  mov     [rbx+10h], rcx
0x18000550a  mov     byte ptr [rbx+18h], 1
0x18000550e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180005513  mov     rax, [rbx+8]
0x180005517  lea     rcx, [rbx+8]
0x18000551b  mov     dword ptr [rbx+1Ch], 1
0x180005522  mov     rax, [rax+8]
0x180005526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552b  mov     rcx, [rdi]
0x18000552e  mov     edx, [rdi+8]
0x180005531  lea     r8, [rcx+8]
0x180005535  mov     rbx, [rsp+28h+arg_0]
0x18000553a  add     rsp, 20h
0x18000553e  pop     rdi
0x18000553f  jmp     cs:__imp_InitOnceComplete
```
