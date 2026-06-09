# WskProTLActivateComplete

- ea: `0x140026ab0`
- end: `0x140026beb`
- name: `WskProTLActivateComplete`
- size: `315`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140026ab0`
- `0x140026dd0`
- `0x140072920`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140026b30`
- `ntoskrnl!IofCompleteRequest` at `0x140026b30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026ade`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026ade`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026b14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026bbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026b14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026bbd`

## pseudocode

```c
__int64 __fastcall WskProTLActivateComplete(PIRP Irp, NTSTATUS a2, __int64 a3, struct _ACCESS_STATE *a4)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rbx
  KIRQL v9; // al
  KIRQL v10; // r8
  __int16 SecurityQos; // cx
  __int64 v13; // r12
  void (__fastcall **AccessState)(_QWORD, _QWORD); // r13
  _QWORD *p_Length; // rax
  _OWORD v16[5]; // [rsp+20h] [rbp-58h] BYREF

  SecurityContext = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
  HIDWORD(SecurityContext->SecurityQos) &= ~1u;
  v10 = v9;
  SecurityQos = (__int16)SecurityContext->SecurityQos;
  if ( LOWORD(SecurityContext->SecurityQos) == 0xACE3 )
  {
    if ( a2 < 0 )
    {
      HIDWORD(SecurityContext->SecurityQos) |= 0x20u;
    }
    else
    {
      *(_QWORD *)&SecurityContext[1].DesiredAccess = a3;
      SecurityContext[2].AccessState = a4;
      BYTE2(SecurityContext->SecurityQos) = 1;
    }
    goto LABEL_4;
  }
  if ( a2 < 0 )
  {
LABEL_4:
    KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v9);
    goto LABEL_5;
  }
  v13 = *(_QWORD *)&SecurityContext[1].DesiredAccess;
  AccessState = (void (__fastcall **)(_QWORD, _QWORD))SecurityContext[2].AccessState;
  v16[0] = 0;
  if ( SecurityQos == -21276 )
  {
    LOWORD(SecurityContext->SecurityQos) = -21279;
    *(_QWORD *)&SecurityContext[3].DesiredAccess = (char *)SecurityContext + 80;
    SecurityContext[3].AccessState = (PACCESS_STATE)&SecurityContext[3].AccessState;
    p_Length = &SecurityContext[3].SecurityQos->Length;
    LODWORD(SecurityContext[4].SecurityQos) = 0;
    if ( p_Length )
      SecurityContext[3].SecurityQos = (PSECURITY_QUALITY_OF_SERVICE)*p_Length;
    else
      SecurityContext[3].SecurityQos = 0;
  }
  *(_QWORD *)&SecurityContext[1].DesiredAccess = a3;
  SecurityContext[2].AccessState = a4;
  BYTE2(SecurityContext->SecurityQos) = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v10);
  *(_QWORD *)&v16[0] = AfdTLDontCareIOCompletion;
  (*AccessState)(v13, v16);
LABEL_5:
  Irp->IoStatus.Status = a2;
  IofCompleteRequest(Irp, ((a2 >> 31) & 0xFE) + 2);
  return WskProReleaseTLEndpoint(SecurityContext);
}

```

## disassembly

```asm
0x140026ab0  push    rbx
0x140026ab2  push    rbp
0x140026ab3  push    rsi
0x140026ab4  push    rdi
0x140026ab5  push    r12
0x140026ab7  push    r13
0x140026ab9  push    r14
0x140026abb  push    r15
0x140026abd  sub     rsp, 38h
0x140026ac1  mov     rax, [rcx+0B8h]
0x140026ac8  mov     rsi, rcx
0x140026acb  mov     r14, r9
0x140026ace  mov     r15, r8
0x140026ad1  mov     edi, edx
0x140026ad3  mov     rbx, [rax+8]
0x140026ad7  lea     rbp, [rbx+10h]
0x140026adb  mov     rcx, rbp; SpinLock
0x140026ade  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026ae5  nop     dword ptr [rax+rax+00h]
0x140026aea  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140026aee  mov     r8b, al
0x140026af1  movzx   ecx, word ptr [rbx]
0x140026af4  mov     eax, 0ACE3h
0x140026af9  cmp     cx, ax
0x140026afc  jnz     short loc_140026B5C
0x140026afe  test    edi, edi
0x140026b00  js      short loc_140026B56
0x140026b02  mov     [rbx+28h], r15
0x140026b06  mov     [rbx+38h], r14
0x140026b0a  mov     byte ptr [rbx+2], 1
0x140026b0e  mov     dl, r8b; NewIrql
0x140026b11  mov     rcx, rbp; SpinLock
0x140026b14  call    cs:__imp_KeReleaseSpinLock
0x140026b1b  nop     dword ptr [rax+rax+00h]
0x140026b20  mov     [rsi+30h], edi
0x140026b23  mov     rcx, rsi; Irp
0x140026b26  sar     edi, 1Fh
0x140026b29  and     dil, 0FEh
0x140026b2d  lea     edx, [rdi+2]; PriorityBoost
0x140026b30  call    cs:__imp_IofCompleteRequest
0x140026b37  nop     dword ptr [rax+rax+00h]
0x140026b3c  mov     rcx, rbx
0x140026b3f  call    WskProReleaseTLEndpoint
0x140026b44  add     rsp, 38h
0x140026b48  pop     r15
0x140026b4a  pop     r14
0x140026b4c  pop     r13
0x140026b4e  pop     r12
0x140026b50  pop     rdi
0x140026b51  pop     rsi
0x140026b52  pop     rbp
0x140026b53  pop     rbx
0x140026b54  retn
0x140026b56  or      dword ptr [rbx+4], 20h
0x140026b5a  jmp     short loc_140026B0E
0x140026b5c  test    edi, edi
0x140026b5e  js      short loc_140026B0E
0x140026b60  mov     r12, [rbx+28h]
0x140026b64  mov     eax, 0ACE4h
0x140026b69  mov     r13, [rbx+38h]
0x140026b6d  xorps   xmm0, xmm0
0x140026b70  movups  [rsp+78h+var_58], xmm0
0x140026b75  cmp     cx, ax
0x140026b78  jnz     short loc_140026BAB
0x140026b7a  lea     rax, [rbx+50h]
0x140026b7e  mov     word ptr [rbx], 0ACE1h
0x140026b83  mov     [rax+8], rax
0x140026b87  mov     [rax], rax
0x140026b8a  mov     rax, [rbx+48h]
0x140026b8e  mov     dword ptr [rbx+60h], 0
0x140026b95  test    rax, rax
0x140026b98  jz      short loc_140026BA3
0x140026b9a  mov     rax, [rax]
0x140026b9d  mov     [rbx+48h], rax
0x140026ba1  jmp     short loc_140026BAB
0x140026ba3  mov     qword ptr [rbx+48h], 0
0x140026bab  mov     dl, r8b; NewIrql
0x140026bae  mov     [rbx+28h], r15
0x140026bb2  mov     rcx, rbp; SpinLock
0x140026bb5  mov     [rbx+38h], r14
0x140026bb9  mov     byte ptr [rbx+2], 1
0x140026bbd  call    cs:__imp_KeReleaseSpinLock
0x140026bc4  nop     dword ptr [rax+rax+00h]
0x140026bc9  lea     rax, AfdTLDontCareIOCompletion
0x140026bd0  mov     rcx, r12
0x140026bd3  mov     qword ptr [rsp+78h+var_58], rax
0x140026bd8  lea     rdx, [rsp+78h+var_58]
0x140026bdd  mov     rax, [r13+0]
0x140026be1  call    _guard_dispatch_icall
0x140026be6  jmp     loc_140026B20
```
