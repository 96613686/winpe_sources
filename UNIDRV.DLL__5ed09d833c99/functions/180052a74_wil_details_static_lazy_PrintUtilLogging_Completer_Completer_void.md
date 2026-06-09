# wil::details::static_lazy<PrintUtilLogging>::Completer::~Completer(void)

- ea: `0x180052a74`
- end: `0x180052ad3`
- name: `??1Completer@?$static_lazy@VPrintUtilLogging@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180057fe4`

## callees

- `0x180040240`
- `0x180052a74`
- `0x180077010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180052ac7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PrintUtilLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
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
0x180052a74  mov     [rsp+arg_0], rbx
0x180052a79  push    rdi
0x180052a7a  sub     rsp, 20h
0x180052a7e  cmp     dword ptr [rcx+8], 0
0x180052a82  mov     rdi, rcx
0x180052a85  jnz     short loc_180052AB3
0x180052a87  mov     rbx, [rcx]
0x180052a8a  mov     rcx, [rbx+20h]; CallbackContext
0x180052a8e  mov     [rbx+10h], rcx
0x180052a92  mov     byte ptr [rbx+18h], 1
0x180052a96  call    TraceLoggingRegisterEx_EventRegister_2U
0x180052a9b  mov     rax, [rbx+8]
0x180052a9f  lea     rcx, [rbx+8]
0x180052aa3  mov     dword ptr [rbx+1Ch], 1
0x180052aaa  mov     rax, [rax+8]
0x180052aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ab3  mov     rcx, [rdi]
0x180052ab6  mov     edx, [rdi+8]
0x180052ab9  lea     r8, [rcx+8]
0x180052abd  mov     rbx, [rsp+28h+arg_0]
0x180052ac2  add     rsp, 20h
0x180052ac6  pop     rdi
0x180052ac7  jmp     cs:__imp_InitOnceComplete
```
