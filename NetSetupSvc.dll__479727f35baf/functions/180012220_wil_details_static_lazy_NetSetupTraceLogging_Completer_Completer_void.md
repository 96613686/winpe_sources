# wil::details::static_lazy<NetSetupTraceLogging>::Completer::~Completer(void)

- ea: `0x180012220`
- end: `0x18001227a`
- name: `??1Completer@?$static_lazy@VNetSetupTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016bc4`

## callees

- `0x180001010`
- `0x180012220`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012273`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
BOOL __fastcall wil::details::static_lazy<NetSetupTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180012220  mov     [rsp+arg_0], rbx
0x180012225  push    rdi
0x180012226  sub     rsp, 20h
0x18001222a  cmp     dword ptr [rcx+8], 0
0x18001222e  mov     rdi, rcx
0x180012231  jnz     short loc_18001225F
0x180012233  mov     rbx, [rcx]
0x180012236  mov     rcx, [rbx+20h]; CallbackContext
0x18001223a  mov     [rbx+10h], rcx
0x18001223e  mov     byte ptr [rbx+18h], 1
0x180012242  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180012247  mov     rax, [rbx+8]
0x18001224b  lea     rcx, [rbx+8]
0x18001224f  mov     dword ptr [rbx+1Ch], 1
0x180012256  mov     rax, [rax+8]
0x18001225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225f  mov     rcx, [rdi]
0x180012262  mov     edx, [rdi+8]
0x180012265  lea     r8, [rcx+8]
0x180012269  mov     rbx, [rsp+28h+arg_0]
0x18001226e  add     rsp, 20h
0x180012272  pop     rdi
0x180012273  jmp     cs:__imp_InitOnceComplete
```
