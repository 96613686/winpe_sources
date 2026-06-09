# wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::Completer::~Completer(void)

- ea: `0x140005ed4`
- end: `0x140005f2e`
- name: `??1Completer@?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e1c0`

## callees

- `0x140002194`
- `0x140005ed4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140005f27`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::Completer::~Completer(_DWORD *a1)
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
0x140005ed4  mov     [rsp+arg_0], rbx
0x140005ed9  push    rdi
0x140005eda  sub     rsp, 20h
0x140005ede  cmp     dword ptr [rcx+8], 0
0x140005ee2  mov     rdi, rcx
0x140005ee5  jnz     short loc_140005F13
0x140005ee7  mov     rbx, [rcx]
0x140005eea  mov     rcx, [rbx+20h]; CallbackContext
0x140005eee  mov     [rbx+10h], rcx
0x140005ef2  mov     byte ptr [rbx+18h], 1
0x140005ef6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140005efb  mov     rax, [rbx+8]
0x140005eff  lea     rcx, [rbx+8]
0x140005f03  mov     dword ptr [rbx+1Ch], 1
0x140005f0a  mov     rax, [rax+8]
0x140005f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f13  mov     rcx, [rdi]
0x140005f16  mov     edx, [rdi+8]
0x140005f19  lea     r8, [rcx+8]
0x140005f1d  mov     rbx, [rsp+28h+arg_0]
0x140005f22  add     rsp, 20h
0x140005f26  pop     rdi
0x140005f27  jmp     cs:__imp_InitOnceComplete
```
