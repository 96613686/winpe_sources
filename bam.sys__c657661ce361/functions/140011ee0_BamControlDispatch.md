# BamControlDispatch

- ea: `0x140011ee0`
- end: `0x140011fc8`
- name: `BamControlDispatch`
- size: `232`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140011ee0`
- `0x140011fd0`
- `0x14001202c`
- `0x140014648`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x140011f6e`
- `ntoskrnl!IoThreadToProcess` at `0x140011fb2`
- `ntoskrnl!IoThreadToProcess` at `0x140011f6e`
- `ntoskrnl!IoThreadToProcess` at `0x140011fb2`
- `ntoskrnl!IofCompleteRequest` at `0x140011f22`
- `ntoskrnl!IofCompleteRequest` at `0x140011f22`

## pseudocode

```c
__int64 __fastcall BamControlDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  UCHAR MajorFunction; // al
  unsigned int v5; // edi
  DWORD LowPart; // eax
  DWORD v8; // eax
  struct _IRP *MasterIrp; // rsi
  int v10; // eax
  PEPROCESS v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // eax
  PEPROCESS v14; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( !CurrentStackLocation->MajorFunction )
    goto LABEL_11;
  if ( MajorFunction == 14 )
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    a2->IoStatus.Information = 0;
    v8 = LowPart - 2228228;
    if ( v8 )
    {
      if ( v8 != 4 )
      {
        v5 = -1073741808;
        goto LABEL_14;
      }
      v14 = IoThreadToProcess(a2->Tail.Overlay.Thread);
      v13 = BampSeverConnectionWithChildProcesses(v14);
    }
    else
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      v10 = BampProcessWindowReportVerify(MasterIrp, CurrentStackLocation->Parameters.Create.Options);
      a2->IoStatus.Status = v10;
      v5 = v10;
      if ( v10 < 0 )
        goto LABEL_6;
      v11 = IoThreadToProcess(a2->Tail.Overlay.Thread);
      v13 = BampProcessWindowReportApply(MasterIrp, v12, v11);
    }
    v5 = v13;
    a2->IoStatus.Status = v13;
    goto LABEL_6;
  }
  if ( MajorFunction == 2 )
  {
LABEL_11:
    a2->IoStatus.Information = 0;
    goto LABEL_5;
  }
  a2->IoStatus.Information = 0;
  if ( MajorFunction != 18 )
  {
    v5 = -1073741637;
LABEL_14:
    a2->IoStatus.Status = v5;
    goto LABEL_6;
  }
LABEL_5:
  v5 = 0;
  a2->IoStatus.Status = 0;
LABEL_6:
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x140011ee0  mov     [rsp+arg_0], rbx
0x140011ee5  mov     [rsp+arg_8], rsi
0x140011eea  push    rdi
0x140011eeb  sub     rsp, 20h
0x140011eef  mov     rbx, rdx
0x140011ef2  xor     r10d, r10d
0x140011ef5  mov     rdx, [rdx+0B8h]
0x140011efc  mov     al, [rdx]
0x140011efe  test    al, al
0x140011f00  jz      loc_140011F8C
0x140011f06  cmp     al, 0Eh
0x140011f08  jz      short loc_140011F41
0x140011f0a  cmp     al, 2
0x140011f0c  jz      short loc_140011F8C
0x140011f0e  mov     [rbx+38h], r10
0x140011f12  cmp     al, 12h
0x140011f14  jnz     short loc_140011F92
0x140011f16  mov     edi, r10d
0x140011f19  mov     [rbx+30h], r10d
0x140011f1d  xor     edx, edx; PriorityBoost
0x140011f1f  mov     rcx, rbx; Irp
0x140011f22  call    cs:__imp_IofCompleteRequest
0x140011f29  nop     dword ptr [rax+rax+00h]
0x140011f2e  mov     rbx, [rsp+28h+arg_0]
0x140011f33  mov     eax, edi
0x140011f35  mov     rsi, [rsp+28h+arg_8]
0x140011f3a  add     rsp, 20h
0x140011f3e  pop     rdi
0x140011f3f  retn
0x140011f41  mov     eax, [rdx+18h]
0x140011f44  mov     [rbx+38h], r10
0x140011f48  sub     eax, 220004h
0x140011f4d  jnz     short loc_140011FA6
0x140011f4f  mov     rsi, [rbx+18h]
0x140011f53  mov     edx, [rdx+10h]
0x140011f56  mov     rcx, rsi
0x140011f59  call    BampProcessWindowReportVerify
0x140011f5e  mov     [rbx+30h], eax
0x140011f61  mov     edi, eax
0x140011f63  test    eax, eax
0x140011f65  js      short loc_140011F1D
0x140011f67  mov     rcx, [rbx+98h]; Thread
0x140011f6e  call    cs:__imp_IoThreadToProcess
0x140011f75  nop     dword ptr [rax+rax+00h]
0x140011f7a  mov     r8, rax
0x140011f7d  mov     rcx, rsi
0x140011f80  call    BampProcessWindowReportApply
0x140011f85  mov     edi, eax
0x140011f87  mov     [rbx+30h], eax
0x140011f8a  jmp     short loc_140011F1D
0x140011f8c  mov     [rbx+38h], r10
0x140011f90  jmp     short loc_140011F16
0x140011f92  mov     edi, 0C00000BBh
0x140011f97  jmp     short loc_140011F9E
0x140011f99  mov     edi, 0C0000010h
0x140011f9e  mov     [rbx+30h], edi
0x140011fa1  jmp     loc_140011F1D
0x140011fa6  cmp     eax, 4
0x140011fa9  jnz     short loc_140011F99
0x140011fab  mov     rcx, [rbx+98h]; Thread
0x140011fb2  call    cs:__imp_IoThreadToProcess
0x140011fb9  nop     dword ptr [rax+rax+00h]
0x140011fbe  mov     rcx, rax
0x140011fc1  call    BampSeverConnectionWithChildProcesses
0x140011fc6  jmp     short loc_140011F85
```
