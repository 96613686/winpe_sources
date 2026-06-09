# FltpCancelMessageWaiter

- ea: `0x18001d7a0`
- end: `0x18001d822`
- name: `FltpCancelMessageWaiter`
- size: `130`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800148b0`
- `0x18001d7a0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18001d7cd`
- `ntoskrnl!KeWaitForSingleObject` at `0x18001d7cd`
- `ntoskrnl!IofCompleteRequest` at `0x18001d7f2`
- `ntoskrnl!IofCompleteRequest` at `0x18001d7f2`

## pseudocode

```c
void __fastcall FltpCancelMessageWaiter(PIO_CSQ Csq, PIRP Irp)
{
  __int64 v3; // rcx
  LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  KeWaitForSingleObject(&Csq[2].CsqPeekNextIrp, Executive, 0, 0, &Timeout);
  if ( (byte_180040A43 & 1) != 0 )
    McTemplateU0sp_EtwWriteTransfer(v3, MessageSup_c3614, "FltpCancelMessageWaiter", Irp);
  Irp->IoStatus.Status = -1073741536;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x18001d7a0  mov     [rsp+arg_8], rbx
0x18001d7a5  push    rdi
0x18001d7a6  sub     rsp, 30h
0x18001d7aa  mov     rbx, rdx
0x18001d7ad  lea     rax, [rsp+38h+arg_0]
0x18001d7b2  xor     edi, edi
0x18001d7b4  mov     [rsp+38h+Timeout], rax; Timeout
0x18001d7b9  xor     edx, edx; WaitReason
0x18001d7bb  mov     qword ptr [rsp+38h+arg_0], rdi
0x18001d7c0  add     rcx, 98h; Object
0x18001d7c7  xor     r9d, r9d; Alertable
0x18001d7ca  xor     r8d, r8d; WaitMode
0x18001d7cd  call    cs:__imp_KeWaitForSingleObject
0x18001d7d4  nop     dword ptr [rax+rax+00h]
0x18001d7d9  test    cs:byte_180040A43, 1
0x18001d7e0  jnz     short loc_18001D80A
0x18001d7e2  xor     edx, edx; PriorityBoost
0x18001d7e4  mov     dword ptr [rbx+30h], 0C0000120h
0x18001d7eb  mov     rcx, rbx; Irp
0x18001d7ee  mov     [rbx+38h], rdi
0x18001d7f2  call    cs:__imp_IofCompleteRequest
0x18001d7f9  nop     dword ptr [rax+rax+00h]
0x18001d7fe  mov     rbx, [rsp+38h+arg_8]
0x18001d803  add     rsp, 30h
0x18001d807  pop     rdi
0x18001d808  retn
0x18001d80a  mov     r9, rbx
0x18001d80d  lea     r8, aFltpcancelmess; "FltpCancelMessageWaiter"
0x18001d814  lea     rdx, MessageSup_c3614
0x18001d81b  call    McTemplateU0sp_EtwWriteTransfer
0x18001d820  jmp     short loc_18001D7E2
```
