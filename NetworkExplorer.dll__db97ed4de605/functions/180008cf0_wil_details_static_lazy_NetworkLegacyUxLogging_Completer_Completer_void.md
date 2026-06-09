# wil::details::static_lazy<NetworkLegacyUxLogging>::Completer::~Completer(void)

- ea: `0x180008cf0`
- end: `0x180008d4a`
- name: `??1Completer@?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d3c4`

## callees

- `0x180006aa8`
- `0x180008cf0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d43`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NetworkLegacyUxLogging>::Completer::~Completer(_DWORD *a1)
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
0x180008cf0  mov     [rsp+arg_0], rbx
0x180008cf5  push    rdi
0x180008cf6  sub     rsp, 20h
0x180008cfa  cmp     dword ptr [rcx+8], 0
0x180008cfe  mov     rdi, rcx
0x180008d01  jnz     short loc_180008D2F
0x180008d03  mov     rbx, [rcx]
0x180008d06  mov     rcx, [rbx+20h]; CallbackContext
0x180008d0a  mov     [rbx+10h], rcx
0x180008d0e  mov     byte ptr [rbx+18h], 1
0x180008d12  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180008d17  mov     rax, [rbx+8]
0x180008d1b  lea     rcx, [rbx+8]
0x180008d1f  mov     dword ptr [rbx+1Ch], 1
0x180008d26  mov     rax, [rax+8]
0x180008d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2f  mov     rcx, [rdi]
0x180008d32  mov     edx, [rdi+8]
0x180008d35  lea     r8, [rcx+8]
0x180008d39  mov     rbx, [rsp+28h+arg_0]
0x180008d3e  add     rsp, 20h
0x180008d42  pop     rdi
0x180008d43  jmp     cs:__imp_InitOnceComplete
```
