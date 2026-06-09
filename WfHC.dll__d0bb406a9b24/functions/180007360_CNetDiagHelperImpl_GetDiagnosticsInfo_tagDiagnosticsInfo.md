# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180007360`
- end: `0x1800073a5`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007360`
- `0x18000c168`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007378`

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
0x180007360  push    rbx
0x180007362  sub     rsp, 20h
0x180007366  mov     rbx, rdx
0x180007369  test    rdx, rdx
0x18000736c  jnz     short loc_180007373
0x18000736e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007373  mov     ecx, 8; cb
0x180007378  call    cs:__imp_CoTaskMemAlloc
0x18000737e  mov     [rbx], rax
0x180007381  test    rax, rax
0x180007384  jnz     short loc_18000738D
0x180007386  mov     eax, 8007000Eh
0x18000738b  jmp     short loc_18000739F
0x18000738d  mov     dword ptr [rax], 0
0x180007393  mov     rax, [rbx]
0x180007396  mov     dword ptr [rax+4], 40000000h
0x18000739d  xor     eax, eax
0x18000739f  add     rsp, 20h
0x1800073a3  pop     rbx
0x1800073a4  retn
```
