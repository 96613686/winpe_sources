# WskProTLControlRequestCompletion

- ea: `0x140035e80`
- end: `0x140035fcf`
- name: `WskProTLControlRequestCompletion`
- size: `335`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140035e80`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035f96`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035f96`
- `ntoskrnl!IofCompleteRequest` at `0x140035faf`
- `ntoskrnl!IofCompleteRequest` at `0x140035faf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035f86`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035f86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ec4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ee5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f06`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ec4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ee5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f06`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035f3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035f3e`

## pseudocode

```c
void __fastcall WskProTLControlRequestCompletion(PIRP Irp, NTSTATUS a2, ULONG_PTR a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PUNICODE_STRING FileName; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rbp
  KIRQL v9; // al
  signed __int64 v10; // rax
  bool v11; // cc
  signed __int64 v12; // rax
  KIRQL Irql; // [rsp+48h] [rbp+10h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  if ( FileName )
  {
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( FileName == (PUNICODE_STRING)1 )
    {
      if ( a2 < 0 )
        goto LABEL_15;
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
      HIDWORD(SecurityContext->SecurityQos) |= 0x4000u;
      goto LABEL_14;
    }
    if ( FileName == (PUNICODE_STRING)2 )
    {
      if ( a2 < 0 )
        goto LABEL_15;
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
      HIDWORD(SecurityContext->SecurityQos) &= ~0x4000u;
      goto LABEL_14;
    }
    if ( FileName == (PUNICODE_STRING)3 )
    {
      if ( a2 < 0 )
        goto LABEL_15;
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
      HIDWORD(SecurityContext->SecurityQos) &= ~0x8000u;
      goto LABEL_14;
    }
    if ( FileName == (PUNICODE_STRING)4 && a2 >= 0 )
    {
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
      HIDWORD(SecurityContext->SecurityQos) |= 0x8000u;
LABEL_14:
      KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v9);
    }
  }
LABEL_15:
  Irp->IoStatus.Information = a3;
  Irp->IoStatus.Status = a2;
  v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)&Irp->Tail, 0xFFFFFFFFFFFFFFFFuLL);
  v11 = v10 <= 1;
  v12 = v10 - 1;
  if ( v11 )
  {
    if ( v12 )
      __fastfail(0xEu);
    if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
    {
      if ( Irp->Cancel )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
      }
    }
    IofCompleteRequest(Irp, ((a2 >> 31) & 0xFE) + 2);
  }
}

```

## disassembly

```asm
0x140035e80  mov     [rsp+arg_0], rbx
0x140035e85  mov     [rsp+arg_10], rbp
0x140035e8a  push    rsi
0x140035e8b  push    rdi
0x140035e8c  push    r14
0x140035e8e  sub     rsp, 20h
0x140035e92  mov     rbp, [rcx+0B8h]
0x140035e99  mov     r14, r8
0x140035e9c  mov     edi, edx
0x140035e9e  mov     rsi, rcx
0x140035ea1  mov     rax, [rbp+10h]
0x140035ea5  test    rax, rax
0x140035ea8  jz      loc_140035F4A
0x140035eae  mov     rbp, [rbp+8]
0x140035eb2  cmp     rax, 1
0x140035eb6  jnz     short loc_140035ED7
0x140035eb8  test    edx, edx
0x140035eba  js      loc_140035F4A
0x140035ec0  lea     rcx, [rbp+10h]; SpinLock
0x140035ec4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035ecb  nop     dword ptr [rax+rax+00h]
0x140035ed0  bts     dword ptr [rbp+4], 0Eh
0x140035ed5  jmp     short loc_140035F38
0x140035ed7  cmp     rax, 2
0x140035edb  jnz     short loc_140035EF8
0x140035edd  test    edi, edi
0x140035edf  js      short loc_140035F4A
0x140035ee1  lea     rcx, [rbp+10h]; SpinLock
0x140035ee5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035eec  nop     dword ptr [rax+rax+00h]
0x140035ef1  btr     dword ptr [rbp+4], 0Eh
0x140035ef6  jmp     short loc_140035F38
0x140035ef8  cmp     rax, 3
0x140035efc  jnz     short loc_140035F19
0x140035efe  test    edi, edi
0x140035f00  js      short loc_140035F4A
0x140035f02  lea     rcx, [rbp+10h]; SpinLock
0x140035f06  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035f0d  nop     dword ptr [rax+rax+00h]
0x140035f12  btr     dword ptr [rbp+4], 0Fh
0x140035f17  jmp     short loc_140035F38
0x140035f19  cmp     rax, 4
0x140035f1d  jnz     short loc_140035F4A
0x140035f1f  test    edi, edi
0x140035f21  js      short loc_140035F4A
0x140035f23  lea     rcx, [rbp+10h]; SpinLock
0x140035f27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035f2e  nop     dword ptr [rax+rax+00h]
0x140035f33  bts     dword ptr [rbp+4], 0Fh
0x140035f38  mov     dl, al; NewIrql
0x140035f3a  lea     rcx, [rbp+10h]; SpinLock
0x140035f3e  call    cs:__imp_KeReleaseSpinLock
0x140035f45  nop     dword ptr [rax+rax+00h]
0x140035f4a  mov     [rsi+38h], r14
0x140035f4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140035f52  mov     [rsi+30h], edi
0x140035f55  lock xadd [rsi+78h], rax
0x140035f5b  sub     rax, 1
0x140035f5f  jg      short loc_140035FBB
0x140035f61  test    rax, rax
0x140035f64  jz      short loc_140035F6F
0x140035f66  mov     ecx, 0Eh
0x140035f6b  int     29h; Win8: RtlFailFast(ecx)
0x140035f6d  jmp     short loc_140035FBB
0x140035f6f  xchg    rax, [rsi+68h]
0x140035f73  test    rax, rax
0x140035f76  jnz     short loc_140035FA2
0x140035f78  cmp     [rsi+44h], al
0x140035f7b  jz      short loc_140035FA2
0x140035f7d  lea     rcx, [rsp+38h+Irql]; Irql
0x140035f82  mov     [rsp+38h+Irql], al
0x140035f86  call    cs:__imp_IoAcquireCancelSpinLock
0x140035f8d  nop     dword ptr [rax+rax+00h]
0x140035f92  mov     cl, [rsp+38h+Irql]; Irql
0x140035f96  call    cs:__imp_IoReleaseCancelSpinLock
0x140035f9d  nop     dword ptr [rax+rax+00h]
0x140035fa2  sar     edi, 1Fh
0x140035fa5  mov     rcx, rsi; Irp
0x140035fa8  and     dil, 0FEh
0x140035fac  lea     edx, [rdi+2]; PriorityBoost
0x140035faf  call    cs:__imp_IofCompleteRequest
0x140035fb6  nop     dword ptr [rax+rax+00h]
0x140035fbb  mov     rbx, [rsp+38h+arg_0]
0x140035fc0  mov     rbp, [rsp+38h+arg_10]
0x140035fc5  add     rsp, 20h
0x140035fc9  pop     r14
0x140035fcb  pop     rdi
0x140035fcc  pop     rsi
0x140035fcd  retn
```
