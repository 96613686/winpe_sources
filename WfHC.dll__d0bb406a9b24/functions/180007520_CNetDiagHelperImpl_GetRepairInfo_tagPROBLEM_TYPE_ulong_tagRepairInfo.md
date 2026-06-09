# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180007520`
- end: `0x180007579`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007520`
- `0x18000c168`

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
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180007520  mov     [rsp+arg_0], rbx
0x180007525  mov     [rsp+arg_8], rsi
0x18000752a  push    rdi
0x18000752b  sub     rsp, 20h
0x18000752f  mov     rbx, r9
0x180007532  mov     rdi, r8
0x180007535  mov     rsi, rcx
0x180007538  test    r8, r8
0x18000753b  jnz     short loc_180007542
0x18000753d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007542  test    rbx, rbx
0x180007545  jnz     short loc_18000754C
0x180007547  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000754c  cmp     dword ptr [rsi+10h], 1
0x180007550  jz      short loc_180007557
0x180007552  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007557  mov     rsi, [rsp+28h+arg_8]
0x18000755c  mov     eax, 80004001h
0x180007561  mov     qword ptr [rbx], 0
0x180007568  mov     rbx, [rsp+28h+arg_0]
0x18000756d  mov     dword ptr [rdi], 0
0x180007573  add     rsp, 20h
0x180007577  pop     rdi
0x180007578  retn
```
