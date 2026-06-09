# wil::details::static_lazy<SettingsDownloadTelemetry>::Completer::~Completer(void)

- ea: `0x180004750`
- end: `0x1800047a6`
- name: `??1Completer@?$static_lazy@VSettingsDownloadTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b0bc`

## callees

- `0x180004750`
- `0x180007f9c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000479f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SettingsDownloadTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = SettingsDownloadTelemetryLogging::Provider();
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
0x180004750  mov     [rsp+arg_0], rbx
0x180004755  push    rdi
0x180004756  sub     rsp, 20h
0x18000475a  cmp     dword ptr [rcx+8], 0
0x18000475e  mov     rdi, rcx
0x180004761  jnz     short loc_18000478B
0x180004763  mov     rbx, [rcx]
0x180004766  call    ?Provider@SettingsDownloadTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsDownloadTelemetryLogging::Provider(void)
0x18000476b  mov     [rbx+10h], rax
0x18000476f  lea     rcx, [rbx+8]
0x180004773  mov     rax, [rbx+8]
0x180004777  mov     byte ptr [rbx+18h], 0
0x18000477b  mov     dword ptr [rbx+1Ch], 1
0x180004782  mov     rax, [rax+8]
0x180004786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478b  mov     rcx, [rdi]
0x18000478e  mov     edx, [rdi+8]
0x180004791  lea     r8, [rcx+8]
0x180004795  mov     rbx, [rsp+28h+arg_0]
0x18000479a  add     rsp, 20h
0x18000479e  pop     rdi
0x18000479f  jmp     cs:__imp_InitOnceComplete
```
