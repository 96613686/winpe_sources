# wil::details::static_lazy<DeviceConfigurationTelemetry>::Completer::~Completer(void)

- ea: `0x18000aaec`
- end: `0x18000ab42`
- name: `??1Completer@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000afcc`

## callees

- `0x18000aaec`
- `0x18000ad98`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ab3b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DeviceConfigurationTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = DeviceConfigurationLogging::Provider();
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
0x18000aaec  mov     [rsp+arg_0], rbx
0x18000aaf1  push    rdi
0x18000aaf2  sub     rsp, 20h
0x18000aaf6  cmp     dword ptr [rcx+8], 0
0x18000aafa  mov     rdi, rcx
0x18000aafd  jnz     short loc_18000AB27
0x18000aaff  mov     rbx, [rcx]
0x18000ab02  call    ?Provider@DeviceConfigurationLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceConfigurationLogging::Provider(void)
0x18000ab07  mov     [rbx+10h], rax
0x18000ab0b  lea     rcx, [rbx+8]
0x18000ab0f  mov     rax, [rbx+8]
0x18000ab13  mov     byte ptr [rbx+18h], 0
0x18000ab17  mov     dword ptr [rbx+1Ch], 1
0x18000ab1e  mov     rax, [rax+8]
0x18000ab22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab27  mov     rcx, [rdi]
0x18000ab2a  mov     edx, [rdi+8]
0x18000ab2d  lea     r8, [rcx+8]
0x18000ab31  mov     rbx, [rsp+28h+arg_0]
0x18000ab36  add     rsp, 20h
0x18000ab3a  pop     rdi
0x18000ab3b  jmp     cs:__imp_InitOnceComplete
```
