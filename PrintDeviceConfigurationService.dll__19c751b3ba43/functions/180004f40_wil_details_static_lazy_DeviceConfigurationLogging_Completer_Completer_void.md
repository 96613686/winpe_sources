# wil::details::static_lazy<DeviceConfigurationLogging>::Completer::~Completer(void)

- ea: `0x180004f40`
- end: `0x180004f9a`
- name: `??1Completer@?$static_lazy@VDeviceConfigurationLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800015d4`
- `0x180004f40`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180004f93`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DeviceConfigurationLogging>::Completer::~Completer(_DWORD *a1)
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
0x180004f40  mov     [rsp+arg_0], rbx
0x180004f45  push    rdi
0x180004f46  sub     rsp, 20h
0x180004f4a  cmp     dword ptr [rcx+8], 0
0x180004f4e  mov     rdi, rcx
0x180004f51  jnz     short loc_180004F7F
0x180004f53  mov     rbx, [rcx]
0x180004f56  mov     rcx, [rbx+20h]; CallbackContext
0x180004f5a  mov     [rbx+10h], rcx
0x180004f5e  mov     byte ptr [rbx+18h], 1
0x180004f62  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180004f67  mov     rax, [rbx+8]
0x180004f6b  lea     rcx, [rbx+8]
0x180004f6f  mov     dword ptr [rbx+1Ch], 1
0x180004f76  mov     rax, [rax+8]
0x180004f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7f  mov     rcx, [rdi]
0x180004f82  mov     edx, [rdi+8]
0x180004f85  lea     r8, [rcx+8]
0x180004f89  mov     rbx, [rsp+28h+arg_0]
0x180004f8e  add     rsp, 20h
0x180004f92  pop     rdi
0x180004f93  jmp     cs:__imp_InitOnceComplete
```
