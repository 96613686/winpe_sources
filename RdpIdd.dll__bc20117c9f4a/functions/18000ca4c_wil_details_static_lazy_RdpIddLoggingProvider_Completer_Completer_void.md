# wil::details::static_lazy<RdpIddLoggingProvider>::Completer::~Completer(void)

- ea: `0x18000ca4c`
- end: `0x18000caab`
- name: `??1Completer@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d614`

## callees

- `0x180001984`
- `0x18000ca4c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ca9f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<RdpIddLoggingProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000ca4c  mov     [rsp+arg_0], rbx
0x18000ca51  push    rdi
0x18000ca52  sub     rsp, 20h
0x18000ca56  cmp     dword ptr [rcx+8], 0
0x18000ca5a  mov     rdi, rcx
0x18000ca5d  jnz     short loc_18000CA8B
0x18000ca5f  mov     rbx, [rcx]
0x18000ca62  mov     rcx, [rbx+20h]; CallbackContext
0x18000ca66  mov     [rbx+10h], rcx
0x18000ca6a  mov     byte ptr [rbx+18h], 1
0x18000ca6e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000ca73  mov     rax, [rbx+8]
0x18000ca77  lea     rcx, [rbx+8]
0x18000ca7b  mov     dword ptr [rbx+1Ch], 1
0x18000ca82  mov     rax, [rax+8]
0x18000ca86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8b  mov     rcx, [rdi]
0x18000ca8e  mov     edx, [rdi+8]
0x18000ca91  lea     r8, [rcx+8]
0x18000ca95  mov     rbx, [rsp+28h+arg_0]
0x18000ca9a  add     rsp, 20h
0x18000ca9e  pop     rdi
0x18000ca9f  jmp     cs:__imp_InitOnceComplete
```
