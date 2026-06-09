# FltpPurgeMessageWaiters

- ea: `0x1800715e0`
- end: `0x1800716ab`
- name: `FltpPurgeMessageWaiters`
- size: `203`
- prototype: `__int64 __fastcall(PIO_CSQ Csq)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180071550`

## callees

- `0x1800148b0`
- `0x1800715e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x180071613`
- `ntoskrnl!ExReleaseFastMutex` at `0x180071613`
- `ntoskrnl!ExAcquireFastMutex` at `0x1800715fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1800715fc`
- `ntoskrnl!IofCompleteRequest` at `0x180071669`
- `ntoskrnl!IofCompleteRequest` at `0x180071669`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18007162b`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18007167d`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18007162b`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18007167d`

## pseudocode

```c
PIRP __fastcall FltpPurgeMessageWaiters(PIO_CSQ Csq)
{
  PIRP result; // rax
  __int64 v3; // rcx
  IRP *i; // rdi
  int PeekContext; // [rsp+30h] [rbp+8h] BYREF

  PeekContext = 0;
  ExAcquireFastMutex((PFAST_MUTEX)&Csq[1]);
  LOBYTE(Csq[2].CsqInsertIrp) |= 1u;
  ExReleaseFastMutex((PFAST_MUTEX)&Csq[1]);
  PeekContext = 0;
  result = IoCsqRemoveNextIrp(Csq, &PeekContext);
  for ( i = result; result; i = result )
  {
    if ( (byte_180040A43 & 1) != 0 )
      McTemplateU0sp_EtwWriteTransfer(v3, MessageSup_c3174, "FltpPurgeMessageWaiters", i);
    i->IoStatus.Status = -1073741769;
    i->IoStatus.Information = 0;
    IofCompleteRequest(i, 0);
    result = IoCsqRemoveNextIrp(Csq, &PeekContext);
  }
  return result;
}

```

## disassembly

```asm
0x1800715e0  mov     [rsp+arg_8], rbx
0x1800715e5  mov     [rsp+arg_10], rsi
0x1800715ea  push    rdi
0x1800715eb  sub     rsp, 20h
0x1800715ef  mov     rbx, rcx
0x1800715f2  xor     esi, esi
0x1800715f4  add     rcx, 40h ; '@'; FastMutex
0x1800715f8  mov     [rsp+28h+PeekContext], esi
0x1800715fc  call    cs:__imp_ExAcquireFastMutex
0x180071603  nop     dword ptr [rax+rax+00h]
0x180071608  or      byte ptr [rbx+88h], 1
0x18007160f  lea     rcx, [rbx+40h]; FastMutex
0x180071613  call    cs:__imp_ExReleaseFastMutex
0x18007161a  nop     dword ptr [rax+rax+00h]
0x18007161f  lea     rdx, [rsp+28h+PeekContext]; PeekContext
0x180071624  mov     [rsp+28h+PeekContext], esi
0x180071628  mov     rcx, rbx; Csq
0x18007162b  call    cs:__imp_IoCsqRemoveNextIrp
0x180071632  nop     dword ptr [rax+rax+00h]
0x180071637  mov     rdi, rax
0x18007163a  test    rax, rax
0x18007163d  jnz     short loc_180071650
0x18007163f  mov     rbx, [rsp+28h+arg_8]
0x180071644  mov     rsi, [rsp+28h+arg_10]
0x180071649  add     rsp, 20h
0x18007164d  pop     rdi
0x18007164e  retn
0x180071650  test    cs:byte_180040A43, 1
0x180071657  jnz     short loc_180071693
0x180071659  xor     edx, edx; PriorityBoost
0x18007165b  mov     dword ptr [rdi+30h], 0C0000037h
0x180071662  mov     rcx, rdi; Irp
0x180071665  mov     [rdi+38h], rsi
0x180071669  call    cs:__imp_IofCompleteRequest
0x180071670  nop     dword ptr [rax+rax+00h]
0x180071675  lea     rdx, [rsp+28h+PeekContext]; PeekContext
0x18007167a  mov     rcx, rbx; Csq
0x18007167d  call    cs:__imp_IoCsqRemoveNextIrp
0x180071684  nop     dword ptr [rax+rax+00h]
0x180071689  mov     rdi, rax
0x18007168c  test    rax, rax
0x18007168f  jz      short loc_18007163F
0x180071691  jmp     short loc_180071650
0x180071693  mov     r9, rdi
0x180071696  lea     r8, aFltppurgemessa; "FltpPurgeMessageWaiters"
0x18007169d  lea     rdx, MessageSup_c3174
0x1800716a4  call    McTemplateU0sp_EtwWriteTransfer
0x1800716a9  jmp     short loc_180071659
```
