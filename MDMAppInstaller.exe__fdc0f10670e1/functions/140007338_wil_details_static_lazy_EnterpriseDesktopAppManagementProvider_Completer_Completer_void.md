# wil::details::static_lazy<EnterpriseDesktopAppManagementProvider>::Completer::~Completer(void)

- ea: `0x140007338`
- end: `0x140007392`
- name: `??1Completer@?$static_lazy@VEnterpriseDesktopAppManagementProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007ba4`

## callees

- `0x140001654`
- `0x140007338`
- `0x14001c010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14000738b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<EnterpriseDesktopAppManagementProvider>::Completer::~Completer(_DWORD *a1)
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
0x140007338  mov     [rsp+arg_0], rbx
0x14000733d  push    rdi
0x14000733e  sub     rsp, 20h
0x140007342  cmp     dword ptr [rcx+8], 0
0x140007346  mov     rdi, rcx
0x140007349  jnz     short loc_140007377
0x14000734b  mov     rbx, [rcx]
0x14000734e  mov     rcx, [rbx+20h]; CallbackContext
0x140007352  mov     [rbx+10h], rcx
0x140007356  mov     byte ptr [rbx+18h], 1
0x14000735a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000735f  mov     rax, [rbx+8]
0x140007363  lea     rcx, [rbx+8]
0x140007367  mov     dword ptr [rbx+1Ch], 1
0x14000736e  mov     rax, [rax+8]
0x140007372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007377  mov     rcx, [rdi]
0x14000737a  mov     edx, [rdi+8]
0x14000737d  lea     r8, [rcx+8]
0x140007381  mov     rbx, [rsp+28h+arg_0]
0x140007386  add     rsp, 20h
0x14000738a  pop     rdi
0x14000738b  jmp     cs:__imp_InitOnceComplete
```
