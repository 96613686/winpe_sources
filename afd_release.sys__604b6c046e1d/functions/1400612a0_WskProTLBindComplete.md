# WskProTLBindComplete

- ea: `0x1400612a0`
- end: `0x140061421`
- name: `WskProTLBindComplete`
- size: `385`
- prototype: `void __fastcall(PIRP Irp, NTSTATUS)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140026dd0`
- `0x1400612a0`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400613fe`
- `ntoskrnl!IofCompleteRequest` at `0x1400613fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400612cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400613cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400612cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400613cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400612e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400613e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400612e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400613e9`

## pseudocode

```c
void __fastcall WskProTLBindComplete(PIRP Irp, NTSTATUS a2)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  KIRQL v5; // al
  CCHAR v6; // dl
  PSECURITY_QUALITY_OF_SERVICE SecurityQos; // rcx
  unsigned int v8; // eax
  PSECURITY_QUALITY_OF_SERVICE v9; // rcx
  KIRQL v10; // al
  _QWORD v11[18]; // [rsp+30h] [rbp-39h] BYREF

  SecurityContext = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( a2 < 0 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
    HIDWORD(SecurityContext->SecurityQos) &= ~1u;
    KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v5);
    v6 = 0;
LABEL_10:
    Irp->IoStatus.Status = a2;
    IofCompleteRequest(Irp, v6);
    WskProReleaseTLEndpoint((__int64)SecurityContext);
    return;
  }
  if ( LOWORD(SecurityContext->SecurityQos) == 0xACE3 )
  {
    memset(v11, 0, 0x68u);
    SecurityQos = SecurityContext[2].SecurityQos;
    v11[0] = WskProTLActivateComplete;
    v11[3] = *(_QWORD *)&SecurityContext[1].DesiredAccess;
    v11[11] = WskProTLClientMessageDispatch;
    v11[1] = Irp;
    LODWORD(v11[2]) = 0x80000000;
    v11[9] = SecurityContext;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)&SecurityQos[3].ImpersonationLevel + 24LL))(
           *(_QWORD *)&SecurityQos[2].ContextTrackingMode,
           v11);
  }
  else
  {
    if ( LOWORD(SecurityContext->SecurityQos) != 0xACE1 )
    {
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SecurityContext->DesiredAccess);
      HIDWORD(SecurityContext->SecurityQos) &= ~1u;
      BYTE2(SecurityContext->SecurityQos) = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)&SecurityContext->DesiredAccess, v10);
      v6 = 2;
      goto LABEL_10;
    }
    memset(v11, 0, 0x68u);
    v9 = SecurityContext[2].SecurityQos;
    v11[0] = WskProTLActivateComplete;
    v11[3] = *(_QWORD *)&SecurityContext[1].DesiredAccess;
    v11[11] = WskProTLClientListenDispatch;
    v11[1] = Irp;
    LODWORD(v11[2]) = -2147483647;
    v11[9] = SecurityContext;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)&v9[3].ImpersonationLevel + 32LL))(
           *(_QWORD *)&v9[2].ContextTrackingMode,
           v11);
  }
  if ( v8 != 259 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v11[0])(v11[1], v8, v11[10], v11[12]);
}

```

## disassembly

```asm
0x1400612a0  push    rbp
0x1400612a2  push    rbx
0x1400612a3  push    rsi
0x1400612a4  push    rdi
0x1400612a5  push    r14
0x1400612a7  lea     rbp, [rsp-37h]
0x1400612ac  sub     rsp, 0A0h
0x1400612b3  mov     rax, [rcx+0B8h]
0x1400612ba  mov     r14d, edx
0x1400612bd  mov     rsi, rcx
0x1400612c0  mov     rdi, [rax+8]
0x1400612c4  test    edx, edx
0x1400612c6  jns     short loc_1400612F5
0x1400612c8  lea     rcx, [rdi+10h]; SpinLock
0x1400612cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400612d3  nop     dword ptr [rax+rax+00h]
0x1400612d8  and     dword ptr [rdi+4], 0FFFFFFFEh
0x1400612dc  lea     rcx, [rdi+10h]; SpinLock
0x1400612e0  mov     dl, al; NewIrql
0x1400612e2  call    cs:__imp_KeReleaseSpinLock
0x1400612e9  nop     dword ptr [rax+rax+00h]
0x1400612ee  xor     edx, edx
0x1400612f0  jmp     loc_1400613F7
0x1400612f5  movzx   eax, word ptr [rdi]
0x1400612f8  mov     ecx, 0ACE3h
0x1400612fd  cmp     ax, cx
0x140061300  jnz     short loc_14006134C
0x140061302  xor     edx, edx; Val
0x140061304  lea     rcx, [rbp+57h+var_90]; void *
0x140061308  lea     r8d, [rdx+68h]; Size
0x14006130c  call    memset
0x140061311  mov     rcx, [rdi+30h]
0x140061315  lea     rax, WskProTLActivateComplete
0x14006131c  mov     [rbp+57h+var_90], rax
0x140061320  mov     rax, [rdi+28h]
0x140061324  mov     [rbp+57h+var_78], rax
0x140061328  lea     rax, WskProTLClientMessageDispatch
0x14006132f  mov     [rbp+57h+var_38], rax
0x140061333  mov     [rbp+57h+var_88], rsi
0x140061337  mov     [rbp+57h+var_80], 80000000h
0x14006133e  mov     [rbp+57h+var_48], rdi
0x140061342  mov     rax, [rcx+28h]
0x140061346  mov     rax, [rax+18h]
0x14006134a  jmp     short loc_14006139E
0x14006134c  mov     ecx, 0ACE1h
0x140061351  cmp     ax, cx
0x140061354  jnz     short loc_1400613CB
0x140061356  xor     edx, edx; Val
0x140061358  lea     rcx, [rbp+57h+var_90]; void *
0x14006135c  lea     r8d, [rdx+68h]; Size
0x140061360  call    memset
0x140061365  mov     rcx, [rdi+30h]
0x140061369  lea     rax, WskProTLActivateComplete
0x140061370  mov     [rbp+57h+var_90], rax
0x140061374  mov     rax, [rdi+28h]
0x140061378  mov     [rbp+57h+var_78], rax
0x14006137c  lea     rax, WskProTLClientListenDispatch
0x140061383  mov     [rbp+57h+var_38], rax
0x140061387  mov     [rbp+57h+var_88], rsi
0x14006138b  mov     [rbp+57h+var_80], 80000001h
0x140061392  mov     [rbp+57h+var_48], rdi
0x140061396  mov     rax, [rcx+28h]
0x14006139a  mov     rax, [rax+20h]
0x14006139e  mov     rcx, [rcx+20h]
0x1400613a2  lea     rdx, [rbp+57h+var_90]
0x1400613a6  call    _guard_dispatch_icall
0x1400613ab  cmp     eax, 103h
0x1400613b0  jz      short loc_140061412
0x1400613b2  mov     r9, [rbp+57h+var_30]
0x1400613b6  mov     edx, eax
0x1400613b8  mov     rax, [rbp+57h+var_90]
0x1400613bc  mov     r8, [rbp+57h+var_40]
0x1400613c0  mov     rcx, [rbp+57h+var_88]
0x1400613c4  call    _guard_dispatch_icall
0x1400613c9  jmp     short loc_140061412
0x1400613cb  lea     rcx, [rdi+10h]; SpinLock
0x1400613cf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400613d6  nop     dword ptr [rax+rax+00h]
0x1400613db  and     dword ptr [rdi+4], 0FFFFFFFEh
0x1400613df  lea     rcx, [rdi+10h]; SpinLock
0x1400613e3  mov     dl, al; NewIrql
0x1400613e5  mov     byte ptr [rdi+2], 1
0x1400613e9  call    cs:__imp_KeReleaseSpinLock
0x1400613f0  nop     dword ptr [rax+rax+00h]
0x1400613f5  mov     dl, 2; PriorityBoost
0x1400613f7  mov     rcx, rsi; Irp
0x1400613fa  mov     [rsi+30h], r14d
0x1400613fe  call    cs:__imp_IofCompleteRequest
0x140061405  nop     dword ptr [rax+rax+00h]
0x14006140a  mov     rcx, rdi
0x14006140d  call    WskProReleaseTLEndpoint
0x140061412  add     rsp, 0A0h
0x140061419  pop     r14
0x14006141b  pop     rdi
0x14006141c  pop     rsi
0x14006141d  pop     rbx
0x14006141e  pop     rbp
0x14006141f  retn
```
