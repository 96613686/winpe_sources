# Smb2WaitForOplockBreakReal

- ea: `0x14006b780`
- end: `0x14006b960`
- name: `Smb2WaitForOplockBreakReal`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x14001ffc4`
- `0x14002019c`
- `0x14006b780`
- `0x140080708`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006b7f7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006b7f7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006b79d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006b79d`
- `ntoskrnl!IofCallDriver` at `0x14006b8cc`
- `ntoskrnl!IofCallDriver` at `0x14006b8cc`
- `ntoskrnl!IoReuseIrp` at `0x14006b7cd`
- `ntoskrnl!IoReuseIrp` at `0x14006b7cd`

## string_xrefs

- `0x14006b93d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`

## pseudocode

```c
NTSTATUS __fastcall Smb2WaitForOplockBreakReal(_QWORD *a1)
{
  __int64 v1; // rbp
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v4; // rdx
  IRP *v5; // rcx
  struct _DEVICE_OBJECT *v6; // r14
  IRP *v7; // rdi
  __int64 v8; // rbx
  USHORT CurrentNodeNumber; // ax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 v11; // rdx
  struct _IO_STACK_LOCATION *v12; // rax
  char v14; // [rsp+20h] [rbp-38h]

  v1 = a1[70];
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(*(_QWORD *)(v1 + 80) + 96LL));
  v5 = (IRP *)a1[15];
  v6 = RelatedDeviceObject;
  if ( v5->StackCount >= RelatedDeviceObject->StackSize && (Microsoft_Windows_SMBServerEnableBits & 0x10) == 0 )
  {
    IoReuseIrp(v5, 0);
LABEL_4:
    v7 = (IRP *)a1[15];
    v7->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(*(_QWORD *)(v1 + 80) + 96LL);
    v8 = *(_QWORD *)(a1[8] + 136LL);
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    CurrentStackLocation = v7->Tail.Overlay.CurrentStackLocation;
    LOBYTE(v11) = 3;
    v14 = 1;
    v7->Tail.Overlay.Thread = *(PETHREAD *)(*(_QWORD *)(v8 + 8LL * CurrentNodeNumber + 8) + 224LL);
    v7->RequestorMode = 0;
    v7->IoStatus.Status = 0;
    v7->IoStatus.Information = 0;
    a1[6] = Smb2CreateContinueOnOplockAck;
    v12 = v7->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)Srv2PostOnCompletion;
    v12[-1].Context = a1;
    v12[-1].Control = -32;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 13;
    CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(v1 + 80) + 96LL);
    CurrentStackLocation[-1].DeviceObject = v6;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 589844;
    v7->MdlAddress = 0;
    v7->AssociatedIrp.MasterIrp = 0;
    v7->UserBuffer = 0;
    v7->Flags = 16;
    SRV2_PERF_ENTER_EX(a1 + 73, v11, 3295, "Smb2WaitForOplockBreakReal", v14);
    return IofCallDriver(v6, v7);
  }
  LOBYTE(v4) = RelatedDeviceObject->StackSize;
  if ( (int)Srv2AllocateLargerIrp(a1, v4) >= 0 )
    goto LABEL_4;
  Smb2CloseFile(*(_QWORD *)(v1 + 72));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
  }
  Smb2SetError(a1, 3221225626LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 3248);
  return Srv2CompleteWorkItem((__int64)a1, 0);
}

```

## disassembly

```asm
0x14006b780  push    rbx
0x14006b782  push    rbp
0x14006b783  push    rsi
0x14006b784  push    rdi
0x14006b785  push    r14
0x14006b787  sub     rsp, 30h
0x14006b78b  mov     rbp, [rcx+230h]
0x14006b792  mov     rsi, rcx
0x14006b795  mov     rcx, [rbp+50h]
0x14006b799  mov     rcx, [rcx+60h]; FileObject
0x14006b79d  call    cs:__imp_IoGetRelatedDeviceObject
0x14006b7a4  nop     dword ptr [rax+rax+00h]
0x14006b7a9  mov     rcx, [rsi+78h]; Irp
0x14006b7ad  mov     r14, rax
0x14006b7b0  mov     r8b, [rax+4Ch]
0x14006b7b4  cmp     [rcx+42h], r8b
0x14006b7b8  jl      loc_14006B8E4
0x14006b7be  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14006b7c5  jnz     loc_14006B8E4
0x14006b7cb  xor     edx, edx; Iostatus
0x14006b7cd  call    cs:__imp_IoReuseIrp
0x14006b7d4  nop     dword ptr [rax+rax+00h]
0x14006b7d9  mov     rax, [rbp+50h]
0x14006b7dd  mov     rdi, [rsi+78h]
0x14006b7e1  mov     rcx, [rax+60h]
0x14006b7e5  mov     [rdi+0C0h], rcx
0x14006b7ec  mov     rax, [rsi+40h]
0x14006b7f0  mov     rbx, [rax+88h]
0x14006b7f7  call    cs:__imp_KeGetCurrentNodeNumber
0x14006b7fe  nop     dword ptr [rax+rax+00h]
0x14006b803  mov     r8, [rdi+0B8h]
0x14006b80a  lea     r9, aSmb2waitforopl; "Smb2WaitForOplockBreakReal"
0x14006b811  movzx   eax, ax
0x14006b814  mov     dl, 3
0x14006b816  mov     [rsp+58h+var_38], 1
0x14006b81b  mov     rcx, [rbx+rax*8+8]
0x14006b820  mov     rax, [rcx+0E0h]
0x14006b827  lea     rcx, Srv2PostOnCompletion
0x14006b82e  mov     [rdi+98h], rax
0x14006b835  lea     rax, Smb2CreateContinueOnOplockAck
0x14006b83c  mov     byte ptr [rdi+40h], 0
0x14006b840  mov     dword ptr [rdi+30h], 0
0x14006b847  mov     qword ptr [rdi+38h], 0
0x14006b84f  mov     [rsi+30h], rax
0x14006b853  mov     rax, [rdi+0B8h]
0x14006b85a  mov     [rax-10h], rcx
0x14006b85e  mov     [rax-8], rsi
0x14006b862  mov     byte ptr [rax-45h], 0E0h
0x14006b866  mov     word ptr [r8-48h], 0Dh
0x14006b86d  mov     rax, [rbp+50h]
0x14006b871  mov     rcx, [rax+60h]
0x14006b875  mov     [r8-18h], rcx
0x14006b879  lea     rcx, [rsi+248h]
0x14006b880  mov     [r8-20h], r14
0x14006b884  mov     dword ptr [r8-40h], 0
0x14006b88c  mov     dword ptr [r8-38h], 0
0x14006b894  mov     dword ptr [r8-30h], 90014h
0x14006b89c  mov     r8d, 0CDFh
0x14006b8a2  mov     qword ptr [rdi+8], 0
0x14006b8aa  mov     qword ptr [rdi+18h], 0
0x14006b8b2  mov     qword ptr [rdi+70h], 0
0x14006b8ba  mov     dword ptr [rdi+10h], 10h
0x14006b8c1  call    SRV2_PERF_ENTER_EX
0x14006b8c6  mov     rdx, rdi; Irp
0x14006b8c9  mov     rcx, r14; DeviceObject
0x14006b8cc  call    cs:__imp_IofCallDriver
0x14006b8d3  nop     dword ptr [rax+rax+00h]
0x14006b8d8  add     rsp, 30h
0x14006b8dc  pop     r14
0x14006b8de  pop     rdi
0x14006b8df  pop     rsi
0x14006b8e0  pop     rbp
0x14006b8e1  pop     rbx
0x14006b8e2  retn
0x14006b8e4  mov     dl, r8b
0x14006b8e7  mov     rcx, rsi
0x14006b8ea  call    Srv2AllocateLargerIrp
0x14006b8ef  test    eax, eax
0x14006b8f1  jns     loc_14006B7D9
0x14006b8f7  mov     rcx, [rbp+48h]
0x14006b8fb  call    Smb2CloseFile
0x14006b900  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b907  lea     rax, WPP_GLOBAL_Control
0x14006b90e  cmp     rcx, rax
0x14006b911  jz      short loc_14006B937
0x14006b913  test    dword ptr [rcx+2Ch], 100000h
0x14006b91a  jz      short loc_14006B937
0x14006b91c  cmp     byte ptr [rcx+29h], 1
0x14006b920  jb      short loc_14006B937
0x14006b922  mov     rcx, [rcx+18h]
0x14006b926  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b92d  mov     edx, 4Dh ; 'M'
0x14006b932  call    WPP_SF_
0x14006b937  mov     r9d, 0CB0h
0x14006b93d  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006b944  mov     edx, 0C000009Ah
0x14006b949  mov     rcx, rsi
0x14006b94c  call    _Smb2SetError
0x14006b951  xor     edx, edx
0x14006b953  mov     rcx, rsi
0x14006b956  call    Srv2CompleteWorkItem
0x14006b95b  jmp     loc_14006B8D8
```
