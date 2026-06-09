# PrjfStopImpersonating

- ea: `0x14003e548`
- end: `0x14003e5a5`
- name: `PrjfStopImpersonating`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140038f1c`
- `0x14003ac68`

## callees

- `0x14000b1d0`
- `0x14003e548`

## import_xrefs

- `ntoskrnl!ZwSetInformationThread` at `0x14003e589`
- `ntoskrnl!ZwSetInformationThread` at `0x14003e589`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e552`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e552`

## pseudocode

```c
NTSTATUS __fastcall PrjfStopImpersonating(__int64 a1)
{
  struct _KPROCESS *v1; // rbx
  __int64 v2; // rcx
  NTSTATUS result; // eax
  __int64 ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(struct _KPROCESS **)(a1 + 32);
  if ( IoGetCurrentProcess() != v1 )
    return MicrosoftTelemetryAssertTriggeredNoArgsKM(v2);
  ThreadInformation = 0;
  result = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( result < 0 )
    return MicrosoftTelemetryAssertTriggeredNoArgsKM(v2);
  return result;
}

```

## disassembly

```asm
0x14003e548  push    rbx
0x14003e54a  sub     rsp, 20h
0x14003e54e  mov     rbx, [rcx+20h]
0x14003e552  call    cs:__imp_IoGetCurrentProcess
0x14003e559  nop     dword ptr [rax+rax+00h]
0x14003e55e  cmp     rax, rbx
0x14003e561  jz      short loc_14003E56A
0x14003e563  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003e568  jmp     short loc_14003E59E
0x14003e56a  mov     r9d, 8; ThreadInformationLength
0x14003e570  mov     [rsp+28h+ThreadInformation], 0
0x14003e579  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x14003e57e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14003e585  lea     edx, [r9-3]; ThreadInformationClass
0x14003e589  call    cs:__imp_ZwSetInformationThread
0x14003e590  nop     dword ptr [rax+rax+00h]
0x14003e595  test    eax, eax
0x14003e597  jns     short loc_14003E59E
0x14003e599  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003e59e  add     rsp, 20h
0x14003e5a2  pop     rbx
0x14003e5a3  retn
```
