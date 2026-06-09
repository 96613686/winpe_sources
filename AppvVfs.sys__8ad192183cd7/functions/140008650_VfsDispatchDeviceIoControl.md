# VfsDispatchDeviceIoControl

- ea: `0x140008650`
- end: `0x1400086e0`
- name: `VfsDispatchDeviceIoControl`
- size: `144`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008650`
- `0x140009784`
- `0x140009d44`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400086c6`
- `ntoskrnl!IofCompleteRequest` at `0x1400086c6`

## pseudocode

```c
__int64 __fastcall VfsDispatchDeviceIoControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  DWORD LowPart; // eax
  struct _IRP *MasterIrp; // rcx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( (LowPart & 3) != 0 )
    goto LABEL_10;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( !MasterIrp || CurrentStackLocation->Parameters.Create.Options < 8 || LowPart != -1501003772 )
    goto LABEL_10;
  v6 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v6 != 1 )
  {
    if ( v6 == 2 )
    {
      v7 = VfsMessageRemoveMappings(MasterIrp);
      goto LABEL_9;
    }
LABEL_10:
    v8 = -1073741811;
    goto LABEL_11;
  }
  v7 = VfsMessageAddMappings(MasterIrp);
LABEL_9:
  v8 = v7;
LABEL_11:
  a2->IoStatus.Status = v8;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v8;
}

```

## disassembly

```asm
0x140008650  mov     [rsp+arg_0], rbx
0x140008655  mov     [rsp+arg_8], rdx
0x14000865a  push    rdi
0x14000865b  sub     rsp, 30h
0x14000865f  mov     rdi, rdx
0x140008662  mov     [rsp+38h+var_18], 0
0x14000866a  mov     rdx, [rdx+0B8h]
0x140008671  mov     eax, [rdx+18h]
0x140008674  test    al, 3
0x140008676  jnz     short loc_1400086AD
0x140008678  mov     rcx, [rdi+18h]
0x14000867c  test    rcx, rcx
0x14000867f  jz      short loc_1400086AD
0x140008681  mov     edx, [rdx+10h]
0x140008684  cmp     edx, 8
0x140008687  jb      short loc_1400086AD
0x140008689  cmp     eax, 0A6888004h
0x14000868e  jnz     short loc_1400086AD
0x140008690  mov     eax, [rcx+4]
0x140008693  cmp     eax, 1
0x140008696  jnz     short loc_14000869F
0x140008698  call    VfsMessageAddMappings
0x14000869d  jmp     short loc_1400086A9
0x14000869f  cmp     eax, 2
0x1400086a2  jnz     short loc_1400086AD
0x1400086a4  call    VfsMessageRemoveMappings
0x1400086a9  mov     ebx, eax
0x1400086ab  jmp     short loc_1400086B2
0x1400086ad  mov     ebx, 0C000000Dh
0x1400086b2  mov     [rsp+38h+var_18], ebx
0x1400086b6  mov     [rdi+30h], ebx
0x1400086b9  mov     qword ptr [rdi+38h], 0
0x1400086c1  xor     edx, edx; PriorityBoost
0x1400086c3  mov     rcx, rdi; Irp
0x1400086c6  call    cs:__imp_IofCompleteRequest
0x1400086cd  nop     dword ptr [rax+rax+00h]
0x1400086d2  mov     eax, ebx
0x1400086d4  mov     rbx, [rsp+38h+arg_0]
0x1400086d9  add     rsp, 30h
0x1400086dd  pop     rdi
0x1400086de  retn
0x140014cef  push    rbp
0x140014cf1  sub     rsp, 20h
0x140014cf5  mov     rbp, rdx
0x140014cf8  mov     rcx, [rbp+48h]
0x140014cfc  mov     eax, [rbp+20h]
0x140014cff  mov     [rcx+30h], eax
0x140014d02  mov     qword ptr [rcx+38h], 0
0x140014d0a  add     rsp, 20h
0x140014d0e  pop     rbp
0x140014d0f  retn
```
