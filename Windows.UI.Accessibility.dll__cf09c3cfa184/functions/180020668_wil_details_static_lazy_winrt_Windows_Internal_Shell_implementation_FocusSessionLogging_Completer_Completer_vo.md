# wil::details::static_lazy<winrt::Windows::Internal::Shell::implementation::FocusSessionLogging>::Completer::~Completer(void)

- ea: `0x180020668`
- end: `0x1800206c2`
- name: `??1Completer@?$static_lazy@VFocusSessionLogging@implementation@Shell@Internal@Windows@winrt@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800244b4`

## callees

- `0x180001738`
- `0x180020668`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800206bb`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<winrt::Windows::Internal::Shell::implementation::FocusSessionLogging>::Completer::~Completer(
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
0x180020668  mov     [rsp+arg_0], rbx
0x18002066d  push    rdi
0x18002066e  sub     rsp, 20h
0x180020672  cmp     dword ptr [rcx+8], 0
0x180020676  mov     rdi, rcx
0x180020679  jnz     short loc_1800206A7
0x18002067b  mov     rbx, [rcx]
0x18002067e  mov     rcx, [rbx+20h]; CallbackContext
0x180020682  mov     [rbx+10h], rcx
0x180020686  mov     byte ptr [rbx+18h], 1
0x18002068a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002068f  mov     rax, [rbx+8]
0x180020693  lea     rcx, [rbx+8]
0x180020697  mov     dword ptr [rbx+1Ch], 1
0x18002069e  mov     rax, [rax+8]
0x1800206a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a7  mov     rcx, [rdi]
0x1800206aa  mov     edx, [rdi+8]
0x1800206ad  lea     r8, [rcx+8]
0x1800206b1  mov     rbx, [rsp+28h+arg_0]
0x1800206b6  add     rsp, 20h
0x1800206ba  pop     rdi
0x1800206bb  jmp     cs:__imp_InitOnceComplete
```
