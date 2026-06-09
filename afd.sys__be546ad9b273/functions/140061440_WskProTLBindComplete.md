# WskProTLBindComplete

- ea: `0x140061440`
- end: `0x1400615c1`
- name: `WskProTLBindComplete`
- size: `385`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140026dd0`
- `0x140061440`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14006159e`
- `ntoskrnl!IofCompleteRequest` at `0x14006159e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006146c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006156f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006146c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006156f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061482`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061589`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061482`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061589`

## pseudocode

```c
__int64 __fastcall WskProTLBindComplete(PIRP Irp, NTSTATUS a2)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  KIRQL v5; // al
  CCHAR v6; // dl
  PSECURITY_QUALITY_OF_SERVICE SecurityQos; // rcx
  __int64 result; // rax
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
    return WskProReleaseTLEndpoint(SecurityContext);
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
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)&SecurityQos[3].ImpersonationLevel + 24LL))(
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
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)&v9[3].ImpersonationLevel + 32LL))(
               *(_QWORD *)&v9[2].ContextTrackingMode,
               v11);
  }
  if ( (_DWORD)result != 259 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v11[0])(
             v11[1],
             (unsigned int)result,
             v11[10],
             v11[12]);
  return result;
}

```

## disassembly

```asm
0x140061440  push    rbp
0x140061442  push    rbx
0x140061443  push    rsi
0x140061444  push    rdi
0x140061445  push    r14
0x140061447  lea     rbp, [rsp-37h]
0x14006144c  sub     rsp, 0A0h
0x140061453  mov     rax, [rcx+0B8h]
0x14006145a  mov     r14d, edx
0x14006145d  mov     rsi, rcx
0x140061460  mov     rdi, [rax+8]
0x140061464  test    edx, edx
0x140061466  jns     short loc_140061495
0x140061468  lea     rcx, [rdi+10h]; SpinLock
0x14006146c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140061473  nop     dword ptr [rax+rax+00h]
0x140061478  and     dword ptr [rdi+4], 0FFFFFFFEh
0x14006147c  lea     rcx, [rdi+10h]; SpinLock
0x140061480  mov     dl, al; NewIrql
0x140061482  call    cs:__imp_KeReleaseSpinLock
0x140061489  nop     dword ptr [rax+rax+00h]
0x14006148e  xor     edx, edx
0x140061490  jmp     loc_140061597
0x140061495  movzx   eax, word ptr [rdi]
0x140061498  mov     ecx, 0ACE3h
0x14006149d  cmp     ax, cx
0x1400614a0  jnz     short loc_1400614EC
0x1400614a2  xor     edx, edx; Val
0x1400614a4  lea     rcx, [rbp+57h+var_90]; void *
0x1400614a8  lea     r8d, [rdx+68h]; Size
0x1400614ac  call    memset
0x1400614b1  mov     rcx, [rdi+30h]
0x1400614b5  lea     rax, WskProTLActivateComplete
0x1400614bc  mov     [rbp+57h+var_90], rax
0x1400614c0  mov     rax, [rdi+28h]
0x1400614c4  mov     [rbp+57h+var_78], rax
0x1400614c8  lea     rax, WskProTLClientMessageDispatch
0x1400614cf  mov     [rbp+57h+var_38], rax
0x1400614d3  mov     [rbp+57h+var_88], rsi
0x1400614d7  mov     [rbp+57h+var_80], 80000000h
0x1400614de  mov     [rbp+57h+var_48], rdi
0x1400614e2  mov     rax, [rcx+28h]
0x1400614e6  mov     rax, [rax+18h]
0x1400614ea  jmp     short loc_14006153E
0x1400614ec  mov     ecx, 0ACE1h
0x1400614f1  cmp     ax, cx
0x1400614f4  jnz     short loc_14006156B
0x1400614f6  xor     edx, edx; Val
0x1400614f8  lea     rcx, [rbp+57h+var_90]; void *
0x1400614fc  lea     r8d, [rdx+68h]; Size
0x140061500  call    memset
0x140061505  mov     rcx, [rdi+30h]
0x140061509  lea     rax, WskProTLActivateComplete
0x140061510  mov     [rbp+57h+var_90], rax
0x140061514  mov     rax, [rdi+28h]
0x140061518  mov     [rbp+57h+var_78], rax
0x14006151c  lea     rax, WskProTLClientListenDispatch
0x140061523  mov     [rbp+57h+var_38], rax
0x140061527  mov     [rbp+57h+var_88], rsi
0x14006152b  mov     [rbp+57h+var_80], 80000001h
0x140061532  mov     [rbp+57h+var_48], rdi
0x140061536  mov     rax, [rcx+28h]
0x14006153a  mov     rax, [rax+20h]
0x14006153e  mov     rcx, [rcx+20h]
0x140061542  lea     rdx, [rbp+57h+var_90]
0x140061546  call    _guard_dispatch_icall
0x14006154b  cmp     eax, 103h
0x140061550  jz      short loc_1400615B2
0x140061552  mov     r9, [rbp+57h+var_30]
0x140061556  mov     edx, eax
0x140061558  mov     rax, [rbp+57h+var_90]
0x14006155c  mov     r8, [rbp+57h+var_40]
0x140061560  mov     rcx, [rbp+57h+var_88]
0x140061564  call    _guard_dispatch_icall
0x140061569  jmp     short loc_1400615B2
0x14006156b  lea     rcx, [rdi+10h]; SpinLock
0x14006156f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140061576  nop     dword ptr [rax+rax+00h]
0x14006157b  and     dword ptr [rdi+4], 0FFFFFFFEh
0x14006157f  lea     rcx, [rdi+10h]; SpinLock
0x140061583  mov     dl, al; NewIrql
0x140061585  mov     byte ptr [rdi+2], 1
0x140061589  call    cs:__imp_KeReleaseSpinLock
0x140061590  nop     dword ptr [rax+rax+00h]
0x140061595  mov     dl, 2; PriorityBoost
0x140061597  mov     rcx, rsi; Irp
0x14006159a  mov     [rsi+30h], r14d
0x14006159e  call    cs:__imp_IofCompleteRequest
0x1400615a5  nop     dword ptr [rax+rax+00h]
0x1400615aa  mov     rcx, rdi
0x1400615ad  call    WskProReleaseTLEndpoint
0x1400615b2  add     rsp, 0A0h
0x1400615b9  pop     r14
0x1400615bb  pop     rdi
0x1400615bc  pop     rsi
0x1400615bd  pop     rbx
0x1400615be  pop     rbp
0x1400615bf  retn
```
