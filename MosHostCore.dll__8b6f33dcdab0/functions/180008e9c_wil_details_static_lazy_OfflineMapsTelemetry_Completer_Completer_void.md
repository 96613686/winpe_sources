# wil::details::static_lazy<OfflineMapsTelemetry>::Completer::~Completer(void)

- ea: `0x180008e9c`
- end: `0x180008ef2`
- name: `??1Completer@?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009d0c`

## callees

- `0x180008e9c`
- `0x180009e6c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008eeb`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = OfflineMapsTraceLogging::Provider();
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
0x180008e9c  mov     [rsp+arg_0], rbx
0x180008ea1  push    rdi
0x180008ea2  sub     rsp, 20h
0x180008ea6  cmp     dword ptr [rcx+8], 0
0x180008eaa  mov     rdi, rcx
0x180008ead  jnz     short loc_180008ED7
0x180008eaf  mov     rbx, [rcx]
0x180008eb2  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180008eb7  mov     [rbx+10h], rax
0x180008ebb  lea     rcx, [rbx+8]
0x180008ebf  mov     rax, [rbx+8]
0x180008ec3  mov     byte ptr [rbx+18h], 0
0x180008ec7  mov     dword ptr [rbx+1Ch], 1
0x180008ece  mov     rax, [rax+8]
0x180008ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed7  mov     rcx, [rdi]
0x180008eda  mov     edx, [rdi+8]
0x180008edd  lea     r8, [rcx+8]
0x180008ee1  mov     rbx, [rsp+28h+arg_0]
0x180008ee6  add     rsp, 20h
0x180008eea  pop     rdi
0x180008eeb  jmp     cs:__imp_InitOnceComplete
```
