# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x18000c1c0`
- end: `0x18000c218`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c1c0`
- `0x18000fa98`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Validate(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x18000c1c0  mov     [rsp+arg_0], rbx
0x18000c1c5  mov     [rsp+arg_8], rsi
0x18000c1ca  push    rdi
0x18000c1cb  sub     rsp, 20h
0x18000c1cf  mov     rbx, r9
0x18000c1d2  mov     rdi, r8
0x18000c1d5  mov     rsi, rcx
0x18000c1d8  test    r8, r8
0x18000c1db  jnz     short loc_18000C1E2
0x18000c1dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c1e2  test    rbx, rbx
0x18000c1e5  jnz     short loc_18000C1EC
0x18000c1e7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c1ec  cmp     dword ptr [rsi+10h], 1
0x18000c1f0  jz      short loc_18000C1F7
0x18000c1f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c1f7  mov     rsi, [rsp+28h+arg_8]
0x18000c1fc  mov     eax, 80004001h
0x18000c201  mov     dword ptr [rdi], 0
0x18000c207  mov     dword ptr [rbx], 0
0x18000c20d  mov     rbx, [rsp+28h+arg_0]
0x18000c212  add     rsp, 20h
0x18000c216  pop     rdi
0x18000c217  retn
```
