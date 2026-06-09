# WskProTLConnectComplete

- ea: `0x140026c00`
- end: `0x140026dc6`
- name: `WskProTLConnectComplete`
- size: `454`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140061430`

## callees

- `0x140026c00`
- `0x140026dd0`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140026d1d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140026d1d`
- `ntoskrnl!IofCompleteRequest` at `0x140026d3a`
- `ntoskrnl!IofCompleteRequest` at `0x140026d3a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140026d0e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140026d0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026c39`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026c39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026cae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026ce8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026cae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026ce8`

## pseudocode

```c
__int64 __fastcall WskProTLConnectComplete(PIRP Irp, NTSTATUS a2, __int64 a3, struct _ACCESS_STATE *a4)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  KIRQL v8; // al
  KIRQL v9; // dl
  __int64 v10; // r12
  void (__fastcall **AccessState)(_QWORD, _QWORD); // r13
  PSECURITY_QUALITY_OF_SERVICE SecurityQos; // rax
  __int64 v13; // rax
  __int16 v14; // bx
  bool v15; // bl
  __int64 v16; // rcx
  PACCESS_STATE v17; // rax
  __int128 v19; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v20[10]; // [rsp+30h] [rbp-50h] BYREF
  KIRQL Irql; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v22; // [rsp+D0h] [rbp+50h]

  v22 = a3;
  SecurityContext = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
  HIDWORD(SecurityContext->SecurityQos) &= ~2u;
  v9 = v8;
  if ( a2 < 0 )
  {
    v15 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v8);
  }
  else
  {
    v10 = *(_QWORD *)&SecurityContext[1].DesiredAccess;
    AccessState = (void (__fastcall **)(_QWORD, _QWORD))SecurityContext[2].AccessState;
    v19 = 0;
    if ( LOWORD(SecurityContext->SecurityQos) == 0xACE4 )
    {
      LOWORD(SecurityContext->SecurityQos) = -21278;
      *(_OWORD *)&SecurityContext[3].AccessState = 0;
      *(_OWORD *)&SecurityContext[4].SecurityQos = 0;
      SecurityQos = SecurityContext[3].SecurityQos;
      if ( SecurityQos )
        SecurityContext[3].SecurityQos = *(PSECURITY_QUALITY_OF_SERVICE *)&SecurityQos->ContextTrackingMode;
      else
        SecurityContext[3].SecurityQos = 0;
    }
    v13 = v22;
    SecurityContext[2].AccessState = a4;
    v14 = (__int16)SecurityContext[1].AccessState;
    *(_QWORD *)&SecurityContext[1].DesiredAccess = v13;
    BYTE2(SecurityContext->SecurityQos) = 2;
    KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v9);
    *(_QWORD *)&v19 = AfdTLDontCareIOCompletion;
    (*AccessState)(v10, &v19);
    v15 = (v14 & 0x10) != 0;
  }
  if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) && Irp->Cancel )
  {
    Irql = 0;
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
  }
  Irp->IoStatus.Status = a2;
  IofCompleteRequest(Irp, ((a2 >> 31) & 0xFE) + 2);
  if ( v15 )
  {
    memset(v20, 0, sizeof(v20));
    v16 = *(_QWORD *)&SecurityContext[1].DesiredAccess;
    v20[0] = AfdTLDontCareIOCompletion;
    v20[1] = SecurityContext;
    v20[4] = &AfdTLSockOptEnable;
    v17 = SecurityContext[2].AccessState;
    v20[2] = 0xFFFD00000000LL;
    LODWORD(v20[3]) = 52;
    v20[5] = 4;
    (*(void (__fastcall **)(__int64, _QWORD *))&v17->SecurityEvaluated)(v16, v20);
  }
  return WskProReleaseTLEndpoint(SecurityContext);
}

```

## disassembly

```asm
0x140026c00  mov     [rsp-38h+arg_0], rbx
0x140026c05  mov     [rsp-38h+arg_10], r8
0x140026c0a  push    rbp
0x140026c0b  push    rsi
0x140026c0c  push    rdi
0x140026c0d  push    r12
0x140026c0f  push    r13
0x140026c11  push    r14
0x140026c13  push    r15
0x140026c15  mov     rbp, rsp
0x140026c18  sub     rsp, 80h
0x140026c1f  mov     rax, [rcx+0B8h]
0x140026c26  mov     r14, rcx
0x140026c29  mov     rbx, r9
0x140026c2c  mov     esi, edx
0x140026c2e  mov     rdi, [rax+8]
0x140026c32  lea     r15, [rdi+10h]
0x140026c36  mov     rcx, r15; SpinLock
0x140026c39  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026c40  nop     dword ptr [rax+rax+00h]
0x140026c45  and     dword ptr [rdi+4], 0FFFFFFFDh
0x140026c49  xor     r12d, r12d
0x140026c4c  mov     dl, al; NewIrql
0x140026c4e  test    esi, esi
0x140026c50  js      loc_140026CE2
0x140026c56  mov     r12, [rdi+28h]
0x140026c5a  mov     eax, 0ACE4h
0x140026c5f  xorps   xmm0, xmm0
0x140026c62  mov     r13, [rdi+38h]
0x140026c66  movups  [rbp+var_60], xmm0
0x140026c6a  cmp     [rdi], ax
0x140026c6d  jnz     short loc_140026C97
0x140026c6f  mov     word ptr [rdi], 0ACE2h
0x140026c74  movups  xmmword ptr [rdi+50h], xmm0
0x140026c78  movups  xmmword ptr [rdi+60h], xmm0
0x140026c7c  mov     rax, [rdi+48h]
0x140026c80  test    rax, rax
0x140026c83  jz      short loc_140026C8F
0x140026c85  mov     rax, [rax+8]
0x140026c89  mov     [rdi+48h], rax
0x140026c8d  jmp     short loc_140026C97
0x140026c8f  mov     qword ptr [rdi+48h], 0
0x140026c97  mov     rax, [rbp+arg_10]
0x140026c9b  mov     rcx, r15; SpinLock
0x140026c9e  mov     [rdi+38h], rbx
0x140026ca2  movzx   ebx, word ptr [rdi+20h]
0x140026ca6  mov     [rdi+28h], rax
0x140026caa  mov     byte ptr [rdi+2], 2
0x140026cae  call    cs:__imp_KeReleaseSpinLock
0x140026cb5  nop     dword ptr [rax+rax+00h]
0x140026cba  lea     rax, AfdTLDontCareIOCompletion
0x140026cc1  mov     rcx, r12
0x140026cc4  mov     qword ptr [rbp+var_60], rax
0x140026cc8  lea     rdx, [rbp+var_60]
0x140026ccc  mov     rax, [r13+0]
0x140026cd0  call    _guard_dispatch_icall
0x140026cd5  xor     r12d, r12d
0x140026cd8  bt      bx, 4
0x140026cdd  setb    bl
0x140026ce0  jmp     short loc_140026CF4
0x140026ce2  mov     rcx, r15; SpinLock
0x140026ce5  mov     bl, r12b
0x140026ce8  call    cs:__imp_KeReleaseSpinLock
0x140026cef  nop     dword ptr [rax+rax+00h]
0x140026cf4  mov     rax, r12
0x140026cf7  xchg    rax, [r14+68h]
0x140026cfb  test    rax, rax
0x140026cfe  jnz     short loc_140026D29
0x140026d00  cmp     [r14+44h], r12b
0x140026d04  jz      short loc_140026D29
0x140026d06  lea     rcx, [rbp+Irql]; Irql
0x140026d0a  mov     [rbp+Irql], r12b
0x140026d0e  call    cs:__imp_IoAcquireCancelSpinLock
0x140026d15  nop     dword ptr [rax+rax+00h]
0x140026d1a  mov     cl, [rbp+Irql]; Irql
0x140026d1d  call    cs:__imp_IoReleaseCancelSpinLock
0x140026d24  nop     dword ptr [rax+rax+00h]
0x140026d29  mov     [r14+30h], esi
0x140026d2d  mov     rcx, r14; Irp
0x140026d30  sar     esi, 1Fh
0x140026d33  and     sil, 0FEh
0x140026d37  lea     edx, [rsi+2]; PriorityBoost
0x140026d3a  call    cs:__imp_IofCompleteRequest
0x140026d41  nop     dword ptr [rax+rax+00h]
0x140026d46  test    bl, bl
0x140026d48  jz      short loc_140026DA2
0x140026d4a  xor     edx, edx; Val
0x140026d4c  lea     rcx, [rbp+var_50]; void *
0x140026d50  lea     r8d, [rdx+50h]; Size
0x140026d54  call    memset
0x140026d59  mov     rcx, [rdi+28h]
0x140026d5d  lea     rax, AfdTLDontCareIOCompletion
0x140026d64  mov     [rbp+var_50], rax
0x140026d68  lea     rdx, [rbp+var_50]
0x140026d6c  lea     rax, AfdTLSockOptEnable
0x140026d73  mov     [rbp+var_48], rdi
0x140026d77  mov     [rbp+var_30], rax
0x140026d7b  mov     rax, [rdi+38h]
0x140026d7f  mov     [rbp+var_40], r12d
0x140026d83  mov     [rbp+var_3C], 0FFFDh
0x140026d8a  mov     [rbp+var_38], 34h ; '4'
0x140026d91  mov     [rbp+var_28], 4
0x140026d99  mov     rax, [rax+8]
0x140026d9d  call    _guard_dispatch_icall
0x140026da2  mov     rcx, rdi
0x140026da5  call    WskProReleaseTLEndpoint
0x140026daa  mov     rbx, [rsp+80h+arg_0]
0x140026db2  add     rsp, 80h
0x140026db9  pop     r15
0x140026dbb  pop     r14
0x140026dbd  pop     r13
0x140026dbf  pop     r12
0x140026dc1  pop     rdi
0x140026dc2  pop     rsi
0x140026dc3  pop     rbp
0x140026dc4  retn
```
