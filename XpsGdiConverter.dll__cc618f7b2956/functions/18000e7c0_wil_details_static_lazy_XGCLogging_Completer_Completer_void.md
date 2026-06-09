# wil::details::static_lazy<XGCLogging>::Completer::~Completer(void)

- ea: `0x18000e7c0`
- end: `0x18000e81a`
- name: `??1Completer@?$static_lazy@VXGCLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011fc8`

## callees

- `0x1800016d4`
- `0x18000e7c0`
- `0x18004a010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18000e813`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<XGCLogging>::Completer::~Completer(_DWORD *a1)
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
0x18000e7c0  mov     [rsp+arg_0], rbx
0x18000e7c5  push    rdi
0x18000e7c6  sub     rsp, 20h
0x18000e7ca  cmp     dword ptr [rcx+8], 0
0x18000e7ce  mov     rdi, rcx
0x18000e7d1  jnz     short loc_18000E7FF
0x18000e7d3  mov     rbx, [rcx]
0x18000e7d6  mov     rcx, [rbx+20h]; CallbackContext
0x18000e7da  mov     [rbx+10h], rcx
0x18000e7de  mov     byte ptr [rbx+18h], 1
0x18000e7e2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e7e7  mov     rax, [rbx+8]
0x18000e7eb  lea     rcx, [rbx+8]
0x18000e7ef  mov     dword ptr [rbx+1Ch], 1
0x18000e7f6  mov     rax, [rax+8]
0x18000e7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ff  mov     rcx, [rdi]
0x18000e802  mov     edx, [rdi+8]
0x18000e805  lea     r8, [rcx+8]
0x18000e809  mov     rbx, [rsp+28h+arg_0]
0x18000e80e  add     rsp, 20h
0x18000e812  pop     rdi
0x18000e813  jmp     cs:__imp_InitOnceComplete
```
