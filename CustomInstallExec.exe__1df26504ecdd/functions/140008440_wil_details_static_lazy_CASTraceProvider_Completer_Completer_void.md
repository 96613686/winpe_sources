# wil::details::static_lazy<CASTraceProvider>::Completer::~Completer(void)

- ea: `0x140008440`
- end: `0x14000849a`
- name: `??1Completer@?$static_lazy@VCASTraceProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b934`

## callees

- `0x140002430`
- `0x140008440`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008493`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CASTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x140008440  mov     [rsp+arg_0], rbx
0x140008445  push    rdi
0x140008446  sub     rsp, 20h
0x14000844a  cmp     dword ptr [rcx+8], 0
0x14000844e  mov     rdi, rcx
0x140008451  jnz     short loc_14000847F
0x140008453  mov     rbx, [rcx]
0x140008456  mov     rcx, [rbx+20h]; CallbackContext
0x14000845a  mov     [rbx+10h], rcx
0x14000845e  mov     byte ptr [rbx+18h], 1
0x140008462  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140008467  mov     rax, [rbx+8]
0x14000846b  lea     rcx, [rbx+8]
0x14000846f  mov     dword ptr [rbx+1Ch], 1
0x140008476  mov     rax, [rax+8]
0x14000847a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000847f  mov     rcx, [rdi]
0x140008482  mov     edx, [rdi+8]
0x140008485  lea     r8, [rcx+8]
0x140008489  mov     rbx, [rsp+28h+arg_0]
0x14000848e  add     rsp, 20h
0x140008492  pop     rdi
0x140008493  jmp     cs:__imp_InitOnceComplete
```
