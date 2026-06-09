# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x18000c140`
- end: `0x18000c199`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c140`
- `0x18000fa98`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetRepairInfo(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18000c140  mov     [rsp+arg_0], rbx
0x18000c145  mov     [rsp+arg_8], rsi
0x18000c14a  push    rdi
0x18000c14b  sub     rsp, 20h
0x18000c14f  mov     rbx, r9
0x18000c152  mov     rdi, r8
0x18000c155  mov     rsi, rcx
0x18000c158  test    r8, r8
0x18000c15b  jnz     short loc_18000C162
0x18000c15d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c162  test    rbx, rbx
0x18000c165  jnz     short loc_18000C16C
0x18000c167  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c16c  cmp     dword ptr [rsi+10h], 1
0x18000c170  jz      short loc_18000C177
0x18000c172  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c177  mov     rsi, [rsp+28h+arg_8]
0x18000c17c  mov     eax, 80004001h
0x18000c181  mov     qword ptr [rbx], 0
0x18000c188  mov     rbx, [rsp+28h+arg_0]
0x18000c18d  mov     dword ptr [rdi], 0
0x18000c193  add     rsp, 20h
0x18000c197  pop     rdi
0x18000c198  retn
```
