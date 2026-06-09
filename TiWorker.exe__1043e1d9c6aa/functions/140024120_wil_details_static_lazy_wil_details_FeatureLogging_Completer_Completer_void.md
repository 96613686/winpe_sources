# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140024120`
- end: `0x14002417a`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140024e28`

## callees

- `0x140001a48`
- `0x140024120`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140024173`

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
0x140024120  mov     [rsp+arg_0], rbx
0x140024125  push    rdi
0x140024126  sub     rsp, 20h
0x14002412a  cmp     dword ptr [rcx+8], 0
0x14002412e  mov     rdi, rcx
0x140024131  jnz     short loc_14002415F
0x140024133  mov     rbx, [rcx]
0x140024136  mov     rcx, [rbx+20h]; CallbackContext
0x14002413a  mov     [rbx+10h], rcx
0x14002413e  mov     byte ptr [rbx+18h], 1
0x140024142  call    TraceLoggingRegisterEx_EventRegister_2U
0x140024147  mov     rax, [rbx+8]
0x14002414b  lea     rcx, [rbx+8]
0x14002414f  mov     dword ptr [rbx+1Ch], 1
0x140024156  mov     rax, [rax+8]
0x14002415a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002415f  mov     rcx, [rdi]
0x140024162  mov     edx, [rdi+8]
0x140024165  lea     r8, [rcx+8]
0x140024169  mov     rbx, [rsp+28h+arg_0]
0x14002416e  add     rsp, 20h
0x140024172  pop     rdi
0x140024173  jmp     cs:__imp_InitOnceComplete
```
