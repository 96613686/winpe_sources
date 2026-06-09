# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x18000bf90`
- end: `0x18000bfd5`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bf90`
- `0x18000fa98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfa8`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetDiagnosticsInfo(CNetDiagHelperImpl *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v3; // rax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v3 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  *a2 = v3;
  if ( !v3 )
    return 2147942414LL;
  v3->cost = 0;
  (*a2)->flags = 0x40000000;
  return 0;
}

```

## disassembly

```asm
0x18000bf90  push    rbx
0x18000bf92  sub     rsp, 20h
0x18000bf96  mov     rbx, rdx
0x18000bf99  test    rdx, rdx
0x18000bf9c  jnz     short loc_18000BFA3
0x18000bf9e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bfa3  mov     ecx, 8; cb
0x18000bfa8  call    cs:__imp_CoTaskMemAlloc
0x18000bfae  mov     [rbx], rax
0x18000bfb1  test    rax, rax
0x18000bfb4  jnz     short loc_18000BFBD
0x18000bfb6  mov     eax, 8007000Eh
0x18000bfbb  jmp     short loc_18000BFCF
0x18000bfbd  mov     dword ptr [rax], 0
0x18000bfc3  mov     rax, [rbx]
0x18000bfc6  mov     dword ptr [rax+4], 40000000h
0x18000bfcd  xor     eax, eax
0x18000bfcf  add     rsp, 20h
0x18000bfd3  pop     rbx
0x18000bfd4  retn
```
