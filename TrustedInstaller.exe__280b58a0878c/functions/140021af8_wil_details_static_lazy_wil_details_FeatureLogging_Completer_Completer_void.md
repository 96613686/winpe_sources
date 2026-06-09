# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140021af8`
- end: `0x140021b52`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400223c4`

## callees

- `0x140001a48`
- `0x140021af8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140021b4b`

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
0x140021af8  mov     [rsp+arg_0], rbx
0x140021afd  push    rdi
0x140021afe  sub     rsp, 20h
0x140021b02  cmp     dword ptr [rcx+8], 0
0x140021b06  mov     rdi, rcx
0x140021b09  jnz     short loc_140021B37
0x140021b0b  mov     rbx, [rcx]
0x140021b0e  mov     rcx, [rbx+20h]; CallbackContext
0x140021b12  mov     [rbx+10h], rcx
0x140021b16  mov     byte ptr [rbx+18h], 1
0x140021b1a  call    TraceLoggingRegisterEx_EventRegister_2U
0x140021b1f  mov     rax, [rbx+8]
0x140021b23  lea     rcx, [rbx+8]
0x140021b27  mov     dword ptr [rbx+1Ch], 1
0x140021b2e  mov     rax, [rax+8]
0x140021b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021b37  mov     rcx, [rdi]
0x140021b3a  mov     edx, [rdi+8]
0x140021b3d  lea     r8, [rcx+8]
0x140021b41  mov     rbx, [rsp+28h+arg_0]
0x140021b46  add     rsp, 20h
0x140021b4a  pop     rdi
0x140021b4b  jmp     cs:__imp_InitOnceComplete
```
