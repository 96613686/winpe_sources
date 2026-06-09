# CSecureProcessDump::StaticCancelCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140006ba0`
- end: `0x140006c09`
- name: `?StaticCancelCallback@CSecureProcessDump@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `105`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006ba0`
- `0x14000e598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006bba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006bdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006bba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006bdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006bef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006bef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140006bd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140006bd1`

## pseudocode

```c
void __fastcall CSecureProcessDump::StaticCancelCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  struct _TP_WAIT *v5; // rcx

  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance, 0, Wait, WaitResult);
  EnterCriticalSection((LPCRITICAL_SECTION)Context);
  v5 = (struct _TP_WAIT *)*((_QWORD *)Context + 314);
  if ( v5 )
    SetThreadpoolWait(v5, 0, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 48));
  *((_DWORD *)Context + 282) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 48));
  LeaveCriticalSection((LPCRITICAL_SECTION)Context);
}

```

## disassembly

```asm
0x140006ba0  mov     [rsp+arg_0], rbx
0x140006ba5  push    rdi
0x140006ba6  sub     rsp, 20h
0x140006baa  mov     rdi, rdx
0x140006bad  test    rdx, rdx
0x140006bb0  jnz     short loc_140006BB7
0x140006bb2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140006bb7  mov     rcx, rdi; lpCriticalSection
0x140006bba  call    cs:__imp_EnterCriticalSection
0x140006bc0  mov     rcx, [rdi+9D0h]; pwa
0x140006bc7  test    rcx, rcx
0x140006bca  jz      short loc_140006BD7
0x140006bcc  xor     r8d, r8d; pftTimeout
0x140006bcf  xor     edx, edx; h
0x140006bd1  call    cs:__imp_SetThreadpoolWait
0x140006bd7  lea     rcx, [rdi+30h]; lpCriticalSection
0x140006bdb  call    cs:__imp_EnterCriticalSection
0x140006be1  lea     rcx, [rdi+30h]; lpCriticalSection
0x140006be5  mov     dword ptr [rdi+468h], 1
0x140006bef  call    cs:__imp_LeaveCriticalSection
0x140006bf5  mov     rcx, rdi
0x140006bf8  mov     rbx, [rsp+28h+arg_0]
0x140006bfd  add     rsp, 20h
0x140006c01  pop     rdi
0x140006c02  jmp     cs:__imp_LeaveCriticalSection
```
