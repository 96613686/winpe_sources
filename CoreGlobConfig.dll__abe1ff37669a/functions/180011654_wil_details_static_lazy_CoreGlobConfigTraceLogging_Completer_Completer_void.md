# wil::details::static_lazy<CoreGlobConfigTraceLogging>::Completer::~Completer(void)

- ea: `0x180011654`
- end: `0x1800116ae`
- name: `??1Completer@?$static_lazy@VCoreGlobConfigTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x180001968`
- `0x180011654`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800116a7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CoreGlobConfigTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180011654  mov     [rsp+arg_0], rbx
0x180011659  push    rdi
0x18001165a  sub     rsp, 20h
0x18001165e  cmp     dword ptr [rcx+8], 0
0x180011662  mov     rdi, rcx
0x180011665  jnz     short loc_180011693
0x180011667  mov     rbx, [rcx]
0x18001166a  mov     rcx, [rbx+20h]; CallbackContext
0x18001166e  mov     [rbx+10h], rcx
0x180011672  mov     byte ptr [rbx+18h], 1
0x180011676  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001167b  mov     rax, [rbx+8]
0x18001167f  lea     rcx, [rbx+8]
0x180011683  mov     dword ptr [rbx+1Ch], 1
0x18001168a  mov     rax, [rax+8]
0x18001168e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011693  mov     rcx, [rdi]
0x180011696  mov     edx, [rdi+8]
0x180011699  lea     r8, [rcx+8]
0x18001169d  mov     rbx, [rsp+28h+arg_0]
0x1800116a2  add     rsp, 20h
0x1800116a6  pop     rdi
0x1800116a7  jmp     cs:__imp_InitOnceComplete
```
