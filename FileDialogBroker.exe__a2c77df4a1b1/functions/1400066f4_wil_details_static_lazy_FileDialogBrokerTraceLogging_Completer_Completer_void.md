# wil::details::static_lazy<FileDialogBrokerTraceLogging>::Completer::~Completer(void)

- ea: `0x1400066f4`
- end: `0x14000674e`
- name: `??1Completer@?$static_lazy@VFileDialogBrokerTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000742c`

## callees

- `0x1400015d4`
- `0x1400066f4`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140006747`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall wil::details::static_lazy<FileDialogBrokerTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x1400066f4  mov     [rsp+arg_0], rbx
0x1400066f9  push    rdi
0x1400066fa  sub     rsp, 20h
0x1400066fe  cmp     dword ptr [rcx+8], 0
0x140006702  mov     rdi, rcx
0x140006705  jnz     short loc_140006733
0x140006707  mov     rbx, [rcx]
0x14000670a  mov     rcx, [rbx+20h]; CallbackContext
0x14000670e  mov     [rbx+10h], rcx
0x140006712  mov     byte ptr [rbx+18h], 1
0x140006716  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000671b  mov     rax, [rbx+8]
0x14000671f  lea     rcx, [rbx+8]
0x140006723  mov     dword ptr [rbx+1Ch], 1
0x14000672a  mov     rax, [rax+8]
0x14000672e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006733  mov     rcx, [rdi]
0x140006736  mov     edx, [rdi+8]
0x140006739  lea     r8, [rcx+8]
0x14000673d  mov     rbx, [rsp+28h+arg_0]
0x140006742  add     rsp, 20h
0x140006746  pop     rdi
0x140006747  jmp     cs:__imp_InitOnceComplete
```
