# WskProTLControlRequestCompletion

- ea: `0x140035ea0`
- end: `0x140035fef`
- name: `WskProTLControlRequestCompletion`
- size: `335`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140035ea0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035fb6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035fb6`
- `ntoskrnl!IofCompleteRequest` at `0x140035fcf`
- `ntoskrnl!IofCompleteRequest` at `0x140035fcf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035fa6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035fa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ee4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035ee4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035f47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035f5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035f5e`

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
0x140035ea0  mov     [rsp+arg_0], rbx
0x140035ea5  mov     [rsp+arg_10], rbp
0x140035eaa  push    rsi
0x140035eab  push    rdi
0x140035eac  push    r14
0x140035eae  sub     rsp, 20h
0x140035eb2  mov     rbp, [rcx+0B8h]
0x140035eb9  mov     r14, r8
0x140035ebc  mov     edi, edx
0x140035ebe  mov     rsi, rcx
0x140035ec1  mov     rax, [rbp+10h]
0x140035ec5  test    rax, rax
0x140035ec8  jz      loc_140035F6A
0x140035ece  mov     rbp, [rbp+8]
0x140035ed2  cmp     rax, 1
0x140035ed6  jnz     short loc_140035EF7
0x140035ed8  test    edx, edx
0x140035eda  js      loc_140035F6A
0x140035ee0  lea     rcx, [rbp+10h]; SpinLock
0x140035ee4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035eeb  nop     dword ptr [rax+rax+00h]
0x140035ef0  bts     dword ptr [rbp+4], 0Eh
0x140035ef5  jmp     short loc_140035F58
0x140035ef7  cmp     rax, 2
0x140035efb  jnz     short loc_140035F18
0x140035efd  test    edi, edi
0x140035eff  js      short loc_140035F6A
0x140035f01  lea     rcx, [rbp+10h]; SpinLock
0x140035f05  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035f0c  nop     dword ptr [rax+rax+00h]
0x140035f11  btr     dword ptr [rbp+4], 0Eh
0x140035f16  jmp     short loc_140035F58
0x140035f18  cmp     rax, 3
0x140035f1c  jnz     short loc_140035F39
0x140035f1e  test    edi, edi
0x140035f20  js      short loc_140035F6A
0x140035f22  lea     rcx, [rbp+10h]; SpinLock
0x140035f26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035f2d  nop     dword ptr [rax+rax+00h]
0x140035f32  btr     dword ptr [rbp+4], 0Fh
0x140035f37  jmp     short loc_140035F58
0x140035f39  cmp     rax, 4
0x140035f3d  jnz     short loc_140035F6A
0x140035f3f  test    edi, edi
0x140035f41  js      short loc_140035F6A
0x140035f43  lea     rcx, [rbp+10h]; SpinLock
0x140035f47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035f4e  nop     dword ptr [rax+rax+00h]
0x140035f53  bts     dword ptr [rbp+4], 0Fh
0x140035f58  mov     dl, al; NewIrql
0x140035f5a  lea     rcx, [rbp+10h]; SpinLock
0x140035f5e  call    cs:__imp_KeReleaseSpinLock
0x140035f65  nop     dword ptr [rax+rax+00h]
0x140035f6a  mov     [rsi+38h], r14
0x140035f6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140035f72  mov     [rsi+30h], edi
0x140035f75  lock xadd [rsi+78h], rax
0x140035f7b  sub     rax, 1
0x140035f7f  jg      short loc_140035FDB
0x140035f81  test    rax, rax
0x140035f84  jz      short loc_140035F8F
0x140035f86  mov     ecx, 0Eh
0x140035f8b  int     29h; Win8: RtlFailFast(ecx)
0x140035f8d  jmp     short loc_140035FDB
0x140035f8f  xchg    rax, [rsi+68h]
0x140035f93  test    rax, rax
0x140035f96  jnz     short loc_140035FC2
0x140035f98  cmp     [rsi+44h], al
0x140035f9b  jz      short loc_140035FC2
0x140035f9d  lea     rcx, [rsp+38h+Irql]; Irql
0x140035fa2  mov     [rsp+38h+Irql], al
0x140035fa6  call    cs:__imp_IoAcquireCancelSpinLock
0x140035fad  nop     dword ptr [rax+rax+00h]
0x140035fb2  mov     cl, [rsp+38h+Irql]; Irql
0x140035fb6  call    cs:__imp_IoReleaseCancelSpinLock
0x140035fbd  nop     dword ptr [rax+rax+00h]
0x140035fc2  sar     edi, 1Fh
0x140035fc5  mov     rcx, rsi; Irp
0x140035fc8  and     dil, 0FEh
0x140035fcc  lea     edx, [rdi+2]; PriorityBoost
0x140035fcf  call    cs:__imp_IofCompleteRequest
0x140035fd6  nop     dword ptr [rax+rax+00h]
0x140035fdb  mov     rbx, [rsp+38h+arg_0]
0x140035fe0  mov     rbp, [rsp+38h+arg_10]
0x140035fe5  add     rsp, 20h
0x140035fe9  pop     r14
0x140035feb  pop     rdi
0x140035fec  pop     rsi
0x140035fed  retn
```
