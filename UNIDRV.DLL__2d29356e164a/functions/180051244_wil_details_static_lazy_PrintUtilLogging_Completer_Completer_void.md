# wil::details::static_lazy<PrintUtilLogging>::Completer::~Completer(void)

- ea: `0x180051244`
- end: `0x18005129e`
- name: `??1Completer@?$static_lazy@VPrintUtilLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005659c`

## callees

- `0x18003f114`
- `0x180051244`
- `0x180075010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180051297`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PrintUtilLogging>::Completer::~Completer(_DWORD *a1)
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
0x180051244  mov     [rsp+arg_0], rbx
0x180051249  push    rdi
0x18005124a  sub     rsp, 20h
0x18005124e  cmp     dword ptr [rcx+8], 0
0x180051252  mov     rdi, rcx
0x180051255  jnz     short loc_180051283
0x180051257  mov     rbx, [rcx]
0x18005125a  mov     rcx, [rbx+20h]; CallbackContext
0x18005125e  mov     [rbx+10h], rcx
0x180051262  mov     byte ptr [rbx+18h], 1
0x180051266  call    TraceLoggingRegisterEx_EventRegister_2U
0x18005126b  mov     rax, [rbx+8]
0x18005126f  lea     rcx, [rbx+8]
0x180051273  mov     dword ptr [rbx+1Ch], 1
0x18005127a  mov     rax, [rax+8]
0x18005127e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051283  mov     rcx, [rdi]
0x180051286  mov     edx, [rdi+8]
0x180051289  lea     r8, [rcx+8]
0x18005128d  mov     rbx, [rsp+28h+arg_0]
0x180051292  add     rsp, 20h
0x180051296  pop     rdi
0x180051297  jmp     cs:__imp_InitOnceComplete
```
