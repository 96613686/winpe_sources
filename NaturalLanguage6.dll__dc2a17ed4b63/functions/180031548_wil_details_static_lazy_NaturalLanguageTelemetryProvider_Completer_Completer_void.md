# wil::details::static_lazy<NaturalLanguageTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180031548`
- end: `0x1800315ad`
- name: `??1Completer@?$static_lazy@VNaturalLanguageTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031470`
- `0x1800a1aa2`

## callees

- `0x180001008`
- `0x180031548`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003159b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003159b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NaturalLanguageTelemetryProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v2 + 8) + 8LL))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180031548  push    rdi
0x18003154a  sub     rsp, 30h
0x18003154e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180031557  mov     [rsp+38h+arg_0], rbx
0x18003155c  mov     rdi, rcx
0x18003155f  cmp     dword ptr [rcx+8], 0
0x180031563  jnz     short loc_180031591
0x180031565  mov     rbx, [rcx]
0x180031568  mov     rcx, [rbx+20h]; CallbackContext
0x18003156c  mov     [rbx+10h], rcx
0x180031570  mov     byte ptr [rbx+18h], 1
0x180031574  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180031579  mov     dword ptr [rbx+1Ch], 1
0x180031580  mov     rax, [rbx+8]
0x180031584  lea     rcx, [rbx+8]
0x180031588  mov     rax, [rax+8]
0x18003158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031591  mov     rcx, [rdi]; lpInitOnce
0x180031594  lea     r8, [rcx+8]; lpContext
0x180031598  mov     edx, [rdi+8]; dwFlags
0x18003159b  call    cs:__imp_InitOnceComplete
0x1800315a1  nop
0x1800315a2  mov     rbx, [rsp+38h+arg_0]
0x1800315a7  add     rsp, 30h
0x1800315ab  pop     rdi
0x1800315ac  retn
```
