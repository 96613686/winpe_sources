# FwpmCalloutDeleteByKey0

- ea: `0x180067c00`
- end: `0x180067c92`
- name: `FwpmCalloutDeleteByKey0`
- size: `146`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800530a0`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180008f5c`
- `0x18000a70c`
- `0x180067c00`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180067c15`
- `ntoskrnl!KeGetCurrentIrql` at `0x180067c15`

## string_xrefs

- `0x180067c2b`: `FwpmCalloutDeleteByKey0`
- `0x180067c6a`: `FwppProxyCalloutDeleteByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmCalloutDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rcx

  if ( KeGetCurrentIrql() )
  {
    v5 = 3221225659LL;
LABEL_3:
    v6 = WfpReportAppErrorAsNtStatus(v4, (__int64)"FwpmCalloutDeleteByKey0", v5);
LABEL_9:
    v7 = v6;
    return WfpErrorToFwpErr(v7);
  }
  if ( !engineHandle )
  {
    v5 = 3223453724LL;
    goto LABEL_3;
  }
  v7 = 0;
  if ( !(unsigned int)FwppSessionIsInProcess(engineHandle) )
  {
    v8 = FwppProxyCalloutDeleteByKey(*(_QWORD *)engineHandle, *((_QWORD *)engineHandle + 1), key);
    if ( v8 < 0 )
    {
      v6 = WfpReportSysErrorAsNtStatus(v9, (int)"FwppProxyCalloutDeleteByKey", v8);
      goto LABEL_9;
    }
  }
  return WfpErrorToFwpErr(v7);
}

```

## disassembly

```asm
0x180067c00  mov     [rsp+arg_0], rbx
0x180067c05  mov     [rsp+arg_8], rsi
0x180067c0a  push    rdi
0x180067c0b  sub     rsp, 30h
0x180067c0f  mov     rsi, rdx
0x180067c12  mov     rdi, rcx
0x180067c15  call    cs:__imp_KeGetCurrentIrql
0x180067c1c  nop     dword ptr [rax+rax+00h]
0x180067c21  test    al, al
0x180067c23  jz      short loc_180067C39
0x180067c25  mov     r8d, 0C00000BBh
0x180067c2b  lea     rdx, aFwpmcalloutdel; "FwpmCalloutDeleteByKey0"
0x180067c32  call    WfpReportAppErrorAsNtStatus
0x180067c37  jmp     short loc_180067C76
0x180067c39  test    rdi, rdi
0x180067c3c  jnz     short loc_180067C46
0x180067c3e  mov     r8d, 0C022001Ch
0x180067c44  jmp     short loc_180067C2B
0x180067c46  mov     rcx, rdi
0x180067c49  xor     ebx, ebx
0x180067c4b  call    FwppSessionIsInProcess
0x180067c50  test    eax, eax
0x180067c52  jnz     short loc_180067C79
0x180067c54  mov     rdx, [rdi+8]
0x180067c58  mov     r8, rsi
0x180067c5b  mov     rcx, [rdi]
0x180067c5e  call    FwppProxyCalloutDeleteByKey
0x180067c63  test    eax, eax
0x180067c65  jns     short loc_180067C79
0x180067c67  mov     r8d, eax
0x180067c6a  lea     rdx, aFwppproxycallo_4; "FwppProxyCalloutDeleteByKey"
0x180067c71  call    WfpReportSysErrorAsNtStatus
0x180067c76  mov     rbx, rax
0x180067c79  mov     rcx, rbx
0x180067c7c  call    WfpErrorToFwpErr
0x180067c81  mov     rbx, [rsp+38h+arg_0]
0x180067c86  mov     rsi, [rsp+38h+arg_8]
0x180067c8b  add     rsp, 30h
0x180067c8f  pop     rdi
0x180067c90  retn
```
