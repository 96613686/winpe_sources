# Smb2IssueChangeNotify

- ea: `0x140086f00`
- end: `0x140087261`
- name: `Smb2IssueChangeNotify`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086de0`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x1400152a0`
- `0x1400157f0`
- `0x1400186f0`
- `0x1400222ec`
- `0x1400224b8`
- `0x140022958`
- `0x140086f00`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400870e3`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400870e3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140086f6e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140086f6e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140086f17`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140086f17`
- `ntoskrnl!IofCallDriver` at `0x1400870ae`
- `ntoskrnl!IofCallDriver` at `0x1400870ae`
- `ntoskrnl!IoFreeIrp` at `0x14008714e`
- `ntoskrnl!IoFreeIrp` at `0x14008714e`
- `ntoskrnl!IoAllocateIrpEx` at `0x140087132`
- `ntoskrnl!IoAllocateIrpEx` at `0x140087132`
- `ntoskrnl!IoReuseIrp` at `0x140086f48`
- `ntoskrnl!IoReuseIrp` at `0x140086f48`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400870c5`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400870c5`

## pseudocode

```c
__int64 __fastcall Smb2IssueChangeNotify(__int64 a1)
{
  __int64 v1; // rsi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  IRP *v4; // rcx
  struct _DEVICE_OBJECT *v5; // rbp
  char StackSize; // r8
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  SECURITY_STATUS v14; // edi
  __int64 v16; // rdx
  __int64 Irp; // rdi
  __int64 v18; // r9
  __int64 v19; // rdx
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v1 + 88));
  v4 = *(IRP **)(a1 + 120);
  v5 = RelatedDeviceObject;
  StackSize = RelatedDeviceObject->StackSize;
  if ( v4->StackCount < StackSize || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v16 = 15;
    if ( StackSize > 15 )
      v16 = (unsigned __int8)RelatedDeviceObject->StackSize;
    Irp = IoAllocateIrpEx(-1, v16, 0);
    if ( !Irp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
          a1,
          -1073741670);
      }
      v18 = 905;
      v19 = 3221225626LL;
      goto LABEL_31;
    }
    IoFreeIrp(*(PIRP *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = Irp;
  }
  else
  {
    IoReuseIrp(v4, 0);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = *(_QWORD *)(v1 + 88);
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8) + 224LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  v8 = *(_QWORD *)(a1 + 120);
  v9 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(a1 + 48) = Smb2ContinueChangeNotify;
  v10 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(v10 - 16) = Srv2PostOnCompletionAndClearCancel;
  *(_QWORD *)(v10 - 8) = a1;
  *(_BYTE *)(v10 - 69) = -32;
  *(_WORD *)(v9 - 72) = 524;
  *(_QWORD *)(v9 - 24) = *(_QWORD *)(v1 + 88);
  *(_QWORD *)(v9 - 32) = v5;
  *(_BYTE *)(v9 - 70) = *(_BYTE *)(v1 + 200);
  *(_DWORD *)(v9 - 64) = *(_DWORD *)(v1 + 196);
  *(_DWORD *)(v9 - 56) = *(_DWORD *)(v1 + 192);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  v11 = *(_QWORD *)(v1 + 160);
  v12 = *(_QWORD *)(a1 + 120);
  if ( (v5->Flags & 0x10) != 0 )
    *(_QWORD *)(v12 + 8) = *(_QWORD *)(v11 + 56);
  else
    *(_QWORD *)(v12 + 24) = *(_QWORD *)(v11 + 24);
  LOBYTE(v12) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v12, 965, "Smb2IssueChangeNotify", 1);
  LOBYTE(v13) = 1;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v13) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids, a1);
    }
    v18 = 973;
    v19 = 3221225760LL;
    goto LABEL_31;
  }
  v14 = Smb2ImpersonateWorkItem(v1);
  if ( v14 < 0 )
  {
    Srv2UnmarkWorkItemCancellable(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        (unsigned int)v14);
    }
    v18 = 986;
    v19 = (unsigned int)v14;
LABEL_31:
    Smb2SetError(a1, v19, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", v18);
    return Srv2CompleteWorkItem(a1, 0);
  }
  Srv2ReferenceConnection(a1);
  IofCallDriver(v5, *(PIRP *)(a1 + 120));
  PsAssignImpersonationToken(KeGetCurrentThread(), 0);
  Interval.QuadPart = -5000;
  KeDelayExecutionThread(0, 0, &Interval);
  if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
    return Srv2DereferenceWorkItem(a1);
  else
    return Smb2GoAsync2(a1);
}

```

## disassembly

```asm
0x140086f00  push    rbx
0x140086f02  push    rbp
0x140086f03  push    rsi
0x140086f04  push    rdi
0x140086f05  sub     rsp, 38h
0x140086f09  mov     rsi, [rcx+230h]
0x140086f10  mov     rbx, rcx
0x140086f13  mov     rcx, [rsi+58h]; FileObject
0x140086f17  call    cs:__imp_IoGetRelatedDeviceObject
0x140086f1e  nop     dword ptr [rax+rax+00h]
0x140086f23  mov     rcx, [rbx+78h]; Irp
0x140086f27  mov     rbp, rax
0x140086f2a  movzx   r8d, byte ptr [rax+4Ch]
0x140086f2f  cmp     [rcx+42h], r8b
0x140086f33  jl      loc_14008711C
0x140086f39  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140086f40  jnz     loc_14008711C
0x140086f46  xor     edx, edx; Iostatus
0x140086f48  call    cs:__imp_IoReuseIrp
0x140086f4f  nop     dword ptr [rax+rax+00h]
0x140086f54  mov     rax, [rsi+58h]
0x140086f58  mov     rcx, [rbx+78h]
0x140086f5c  mov     [rcx+0C0h], rax
0x140086f63  mov     rax, [rbx+40h]
0x140086f67  mov     rdi, [rax+88h]
0x140086f6e  call    cs:__imp_KeGetCurrentNodeNumber
0x140086f75  nop     dword ptr [rax+rax+00h]
0x140086f7a  movzx   eax, ax
0x140086f7d  xor     r8d, r8d
0x140086f80  mov     rcx, [rdi+rax*8+8]
0x140086f85  mov     rax, [rbx+78h]
0x140086f89  mov     rdx, [rcx+0E0h]
0x140086f90  mov     [rax+98h], rdx
0x140086f97  lea     rdx, Smb2ContinueChangeNotify
0x140086f9e  mov     rax, [rbx+78h]
0x140086fa2  mov     byte ptr [rax+40h], 0
0x140086fa6  mov     rax, [rbx+78h]
0x140086faa  mov     [rax+8], r8
0x140086fae  mov     rax, [rbx+78h]
0x140086fb2  mov     [rax+18h], r8
0x140086fb6  mov     rax, [rbx+78h]
0x140086fba  mov     [rax+70h], r8
0x140086fbe  mov     rax, [rbx+78h]
0x140086fc2  mov     [rax+30h], r8d
0x140086fc6  mov     rax, [rbx+78h]
0x140086fca  mov     [rax+38h], r8
0x140086fce  mov     rax, [rbx+78h]
0x140086fd2  mov     rcx, [rax+0B8h]
0x140086fd9  mov     [rbx+30h], rdx
0x140086fdd  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x140086fe4  mov     rax, [rax+0B8h]
0x140086feb  mov     [rax-10h], rdx
0x140086fef  mov     [rax-8], rbx
0x140086ff3  mov     byte ptr [rax-45h], 0E0h
0x140086ff7  mov     word ptr [rcx-48h], 20Ch
0x140086ffd  mov     rax, [rsi+58h]
0x140087001  mov     [rcx-18h], rax
0x140087005  mov     [rcx-20h], rbp
0x140087009  movzx   eax, byte ptr [rsi+0C8h]
0x140087010  mov     [rcx-46h], al
0x140087013  mov     eax, [rsi+0C4h]
0x140087019  mov     [rcx-40h], eax
0x14008701c  mov     eax, [rsi+0C0h]
0x140087022  mov     [rcx-38h], eax
0x140087025  mov     rax, [rbx+78h]
0x140087029  mov     [rax+18h], r8
0x14008702d  mov     rax, [rbx+78h]
0x140087031  mov     [rax+8], r8
0x140087035  mov     rax, [rbx+78h]
0x140087039  mov     [rax+70h], r8
0x14008703d  mov     eax, [rbp+30h]
0x140087040  mov     rcx, [rsi+0A0h]
0x140087047  mov     rdx, [rbx+78h]
0x14008704b  test    al, 10h
0x14008704d  jnz     loc_140087163
0x140087053  mov     rax, [rcx+18h]
0x140087057  mov     [rdx+18h], rax
0x14008705b  lea     rcx, [rbx+248h]
0x140087062  mov     byte ptr [rsp+58h+var_38], 1
0x140087067  lea     r9, aSmb2issuechang; "Smb2IssueChangeNotify"
0x14008706e  mov     r8d, 3C5h
0x140087074  mov     dl, 3
0x140087076  call    SRV2_PERF_ENTER_EX
0x14008707b  mov     dl, 1
0x14008707d  mov     rcx, rbx
0x140087080  call    Srv2MarkWorkItemCancellable
0x140087085  test    eax, eax
0x140087087  js      loc_140087170
0x14008708d  mov     rcx, rsi
0x140087090  call    Smb2ImpersonateWorkItem
0x140087095  mov     edi, eax
0x140087097  mov     rcx, rbx
0x14008709a  test    eax, eax
0x14008709c  js      loc_1400871BC
0x1400870a2  call    Srv2ReferenceConnection
0x1400870a7  mov     rdx, [rbx+78h]; Irp
0x1400870ab  mov     rcx, rbp; DeviceObject
0x1400870ae  call    cs:__imp_IofCallDriver
0x1400870b5  nop     dword ptr [rax+rax+00h]
0x1400870ba  mov     rcx, gs:188h; Thread
0x1400870c3  xor     edx, edx; Token
0x1400870c5  call    cs:__imp_PsAssignImpersonationToken
0x1400870cc  nop     dword ptr [rax+rax+00h]
0x1400870d1  lea     r8, [rsp+58h+Interval]; Interval
0x1400870d6  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFEC78h
0x1400870df  xor     edx, edx; Alertable
0x1400870e1  xor     ecx, ecx; WaitMode
0x1400870e3  call    cs:__imp_KeDelayExecutionThread
0x1400870ea  nop     dword ptr [rax+rax+00h]
0x1400870ef  mov     rcx, rbx
0x1400870f2  call    Srv2MarkWorkItemPending
0x1400870f7  mov     rcx, rbx
0x1400870fa  test    eax, eax
0x1400870fc  jz      short loc_14008710D
0x1400870fe  call    Srv2DereferenceWorkItem
0x140087103  add     rsp, 38h
0x140087107  pop     rdi
0x140087108  pop     rsi
0x140087109  pop     rbp
0x14008710a  pop     rbx
0x14008710b  retn
0x14008710d  call    Smb2GoAsync2
0x140087112  add     rsp, 38h
0x140087116  pop     rdi
0x140087117  pop     rsi
0x140087118  pop     rbp
0x140087119  pop     rbx
0x14008711a  retn
0x14008711c  mov     edx, 0Fh
0x140087121  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140087128  cmp     r8b, dl
0x14008712b  cmovg   edx, r8d
0x14008712f  xor     r8d, r8d
0x140087132  call    cs:__imp_IoAllocateIrpEx
0x140087139  nop     dword ptr [rax+rax+00h]
0x14008713e  mov     rdi, rax
0x140087141  test    rax, rax
0x140087144  jz      loc_14008720D
0x14008714a  mov     rcx, [rbx+78h]; Irp
0x14008714e  call    cs:__imp_IoFreeIrp
0x140087155  nop     dword ptr [rax+rax+00h]
0x14008715a  mov     [rbx+78h], rdi
0x14008715e  jmp     loc_140086F54
0x140087163  mov     rax, [rcx+38h]
0x140087167  mov     [rdx+8], rax
0x14008716b  jmp     loc_14008705B
0x140087170  mov     rcx, cs:WPP_GLOBAL_Control
0x140087177  lea     rax, WPP_GLOBAL_Control
0x14008717e  cmp     rcx, rax
0x140087181  jz      loc_14009AECA
0x140087187  test    dword ptr [rcx+2Ch], 4000000h
0x14008718e  jz      loc_14009AECA
0x140087194  cmp     byte ptr [rcx+29h], 1
0x140087198  jb      loc_14009AECA
0x14008719e  mov     rcx, [rcx+18h]
0x1400871a2  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x1400871a9  mov     edx, 18h
0x1400871ae  mov     r9, rbx
0x1400871b1  call    WPP_SF_q
0x1400871b6  nop
0x1400871b7  jmp     loc_14009AECA
0x1400871bc  call    Srv2UnmarkWorkItemCancellable
0x1400871c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400871c8  lea     rax, WPP_GLOBAL_Control
0x1400871cf  cmp     rcx, rax
0x1400871d2  jz      loc_14009AED7
0x1400871d8  test    dword ptr [rcx+2Ch], 4000000h
0x1400871df  jz      loc_14009AED7
0x1400871e5  cmp     byte ptr [rcx+29h], 1
0x1400871e9  jb      loc_14009AED7
0x1400871ef  mov     rcx, [rcx+18h]
0x1400871f3  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x1400871fa  mov     edx, 19h
0x1400871ff  mov     r9d, edi
0x140087202  call    WPP_SF_d
0x140087207  nop
0x140087208  jmp     loc_14009AED7
0x14008720d  mov     rcx, cs:WPP_GLOBAL_Control
0x140087214  lea     rax, WPP_GLOBAL_Control
0x14008721b  cmp     rcx, rax
0x14008721e  jz      loc_14009AEE1
0x140087224  test    dword ptr [rcx+2Ch], 4000000h
0x14008722b  jz      loc_14009AEE1
0x140087231  cmp     byte ptr [rcx+29h], 1
0x140087235  jb      loc_14009AEE1
0x14008723b  mov     rcx, [rcx+18h]
0x14008723f  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x140087246  mov     edx, 17h
0x14008724b  mov     [rsp+58h+var_38], 0C000009Ah
0x140087253  mov     r9, rbx
0x140087256  call    WPP_SF_qD
0x14008725b  nop
0x14008725c  jmp     loc_14009AEE1
0x14009aeca  mov     r9d, 3CDh
0x14009aed0  mov     edx, 0C0000120h
0x14009aed5  jmp     short loc_14009AEEC
0x14009aed7  mov     r9d, 3DAh
0x14009aedd  mov     edx, edi
0x14009aedf  jmp     short loc_14009AEEC
0x14009aee1  mov     r9d, 389h
0x14009aee7  mov     edx, 0C000009Ah
0x14009aeec  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14009aef3  mov     rcx, rbx
0x14009aef6  call    _Smb2SetError
0x14009aefb  xor     edx, edx
0x14009aefd  mov     rcx, rbx
0x14009af00  call    Srv2CompleteWorkItem
0x14009af05  nop
0x14009af06  jmp     loc_140087103
```
