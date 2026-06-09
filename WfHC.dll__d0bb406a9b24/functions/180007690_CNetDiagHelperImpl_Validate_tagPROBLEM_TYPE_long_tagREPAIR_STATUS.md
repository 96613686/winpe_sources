# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x180007690`
- end: `0x1800076e8`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007690`
- `0x18000c168`

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
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x180007690  mov     [rsp+arg_0], rbx
0x180007695  mov     [rsp+arg_8], rsi
0x18000769a  push    rdi
0x18000769b  sub     rsp, 20h
0x18000769f  mov     rbx, r9
0x1800076a2  mov     rdi, r8
0x1800076a5  mov     rsi, rcx
0x1800076a8  test    r8, r8
0x1800076ab  jnz     short loc_1800076B2
0x1800076ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800076b2  test    rbx, rbx
0x1800076b5  jnz     short loc_1800076BC
0x1800076b7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800076bc  cmp     dword ptr [rsi+10h], 1
0x1800076c0  jz      short loc_1800076C7
0x1800076c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800076c7  mov     rsi, [rsp+28h+arg_8]
0x1800076cc  mov     eax, 80004001h
0x1800076d1  mov     dword ptr [rdi], 0
0x1800076d7  mov     dword ptr [rbx], 0
0x1800076dd  mov     rbx, [rsp+28h+arg_0]
0x1800076e2  add     rsp, 20h
0x1800076e6  pop     rdi
0x1800076e7  retn
```
