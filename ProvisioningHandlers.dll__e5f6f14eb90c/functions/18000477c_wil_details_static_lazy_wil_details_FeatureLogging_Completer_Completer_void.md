# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18000477c`
- end: `0x1800047db`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2b4`

## callees

- `0x180001a30`
- `0x18000477c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800047cf`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
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
0x18000477c  mov     [rsp+arg_0], rbx
0x180004781  push    rdi
0x180004782  sub     rsp, 20h
0x180004786  cmp     dword ptr [rcx+8], 0
0x18000478a  mov     rdi, rcx
0x18000478d  jnz     short loc_1800047BB
0x18000478f  mov     rbx, [rcx]
0x180004792  mov     rcx, [rbx+20h]; CallbackContext
0x180004796  mov     [rbx+10h], rcx
0x18000479a  mov     byte ptr [rbx+18h], 1
0x18000479e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800047a3  mov     rax, [rbx+8]
0x1800047a7  lea     rcx, [rbx+8]
0x1800047ab  mov     dword ptr [rbx+1Ch], 1
0x1800047b2  mov     rax, [rax+8]
0x1800047b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047bb  mov     rcx, [rdi]
0x1800047be  mov     edx, [rdi+8]
0x1800047c1  lea     r8, [rcx+8]
0x1800047c5  mov     rbx, [rsp+28h+arg_0]
0x1800047ca  add     rsp, 20h
0x1800047ce  pop     rdi
0x1800047cf  jmp     cs:__imp_InitOnceComplete
```
