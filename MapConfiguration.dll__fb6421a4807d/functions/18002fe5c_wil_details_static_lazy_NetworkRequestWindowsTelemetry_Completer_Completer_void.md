# wil::details::static_lazy<NetworkRequestWindowsTelemetry>::Completer::~Completer(void)

- ea: `0x18002fe5c`
- end: `0x18002feb2`
- name: `??1Completer@?$static_lazy@VNetworkRequestWindowsTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003224c`

## callees

- `0x18002fe5c`
- `0x18003060c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002feab`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NetworkRequestWindowsTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = BingPlatformNetworkServicesTraceLogging::Provider();
    v3.Ptr = v2[1].Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18002fe5c  mov     [rsp+arg_0], rbx
0x18002fe61  push    rdi
0x18002fe62  sub     rsp, 20h
0x18002fe66  cmp     dword ptr [rcx+8], 0
0x18002fe6a  mov     rdi, rcx
0x18002fe6d  jnz     short loc_18002FE97
0x18002fe6f  mov     rbx, [rcx]
0x18002fe72  call    ?Provider@BingPlatformNetworkServicesTraceLogging@@SAPEBU_tlgProvider_t@@XZ; BingPlatformNetworkServicesTraceLogging::Provider(void)
0x18002fe77  mov     [rbx+10h], rax
0x18002fe7b  lea     rcx, [rbx+8]
0x18002fe7f  mov     rax, [rbx+8]
0x18002fe83  mov     byte ptr [rbx+18h], 0
0x18002fe87  mov     dword ptr [rbx+1Ch], 1
0x18002fe8e  mov     rax, [rax+8]
0x18002fe92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe97  mov     rcx, [rdi]
0x18002fe9a  mov     edx, [rdi+8]
0x18002fe9d  lea     r8, [rcx+8]
0x18002fea1  mov     rbx, [rsp+28h+arg_0]
0x18002fea6  add     rsp, 20h
0x18002feaa  pop     rdi
0x18002feab  jmp     cs:__imp_InitOnceComplete
```
