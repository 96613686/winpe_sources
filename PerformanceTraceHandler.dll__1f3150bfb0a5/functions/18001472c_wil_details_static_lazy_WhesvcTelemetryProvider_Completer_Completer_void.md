# wil::details::static_lazy<WhesvcTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18001472c`
- end: `0x180014786`
- name: `??1Completer@?$static_lazy@VWhesvcTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017e4c`

## callees

- `0x18000175c`
- `0x18001472c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001477f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<WhesvcTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x18001472c  mov     [rsp+arg_0], rbx
0x180014731  push    rdi
0x180014732  sub     rsp, 20h
0x180014736  cmp     dword ptr [rcx+8], 0
0x18001473a  mov     rdi, rcx
0x18001473d  jnz     short loc_18001476B
0x18001473f  mov     rbx, [rcx]
0x180014742  mov     rcx, [rbx+20h]; CallbackContext
0x180014746  mov     [rbx+10h], rcx
0x18001474a  mov     byte ptr [rbx+18h], 1
0x18001474e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180014753  mov     rax, [rbx+8]
0x180014757  lea     rcx, [rbx+8]
0x18001475b  mov     dword ptr [rbx+1Ch], 1
0x180014762  mov     rax, [rax+8]
0x180014766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001476b  mov     rcx, [rdi]
0x18001476e  mov     edx, [rdi+8]
0x180014771  lea     r8, [rcx+8]
0x180014775  mov     rbx, [rsp+28h+arg_0]
0x18001477a  add     rsp, 20h
0x18001477e  pop     rdi
0x18001477f  jmp     cs:__imp_InitOnceComplete
```
