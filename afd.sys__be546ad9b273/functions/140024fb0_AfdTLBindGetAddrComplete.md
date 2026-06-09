# AfdTLBindGetAddrComplete

- ea: `0x140024fb0`
- end: `0x140025098`
- name: `AfdTLBindGetAddrComplete`
- size: `232`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140024fb0`
- `0x1400250a0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002504f`
- `ntoskrnl!IoFreeMdl` at `0x14002504f`
- `ntoskrnl!MmUnlockPages` at `0x14002503f`
- `ntoskrnl!MmUnlockPages` at `0x14002503f`
- `ntoskrnl!IofCompleteRequest` at `0x140025076`
- `ntoskrnl!IofCompleteRequest` at `0x140025076`
- `TDI!TdiCopyBufferToMdl` at `0x140024ff9`
- `TDI!TdiCopyBufferToMdl` at `0x140024ff9`

## pseudocode

```c
void __fastcall AfdTLBindGetAddrComplete(PIRP Irp, int a2, ULONG a3)
{
  NTSTATUS v5; // edi
  PVOID FsContext; // rsi
  int v7; // edx
  unsigned __int16 *v8; // rax
  PMDL MdlAddress; // rcx
  CCHAR v10; // dl

  v5 = a2;
  FsContext = Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( a2 < 0 )
  {
    v7 = 7023;
    v8 = 0;
  }
  else
  {
    v5 = TdiCopyBufferToMdl(*((PVOID *)FsContext + 30), 0, a3, Irp->MdlAddress, 0, (PULONG)FsContext + 59);
    v7 = 7022;
    v8 = (unsigned __int16 *)*((_QWORD *)FsContext + 30);
  }
  AFDETW_TRACEBIND(1, v7, (__int64)FsContext, v5, v8);
  _InterlockedExchange((volatile __int32 *)FsContext + 92, 0);
  MdlAddress = Irp->MdlAddress;
  if ( MdlAddress )
  {
    if ( (MdlAddress->MdlFlags & 2) != 0 )
      MmUnlockPages(MdlAddress);
    IoFreeMdl(Irp->MdlAddress);
    Irp->MdlAddress = 0;
  }
  v10 = AfdPriorityBoost;
  Irp->IoStatus.Information = a3;
  Irp->IoStatus.Status = v5;
  IofCompleteRequest(Irp, v10);
}

```

## disassembly

```asm
0x140024fb0  push    rbx
0x140024fb2  push    rbp
0x140024fb3  push    rsi
0x140024fb4  push    rdi
0x140024fb5  sub     rsp, 38h
0x140024fb9  mov     rax, [rcx+0B8h]
0x140024fc0  mov     rbx, rcx
0x140024fc3  mov     rbp, r8
0x140024fc6  mov     edi, edx
0x140024fc8  mov     rcx, [rax+30h]
0x140024fcc  mov     rsi, [rcx+18h]
0x140024fd0  test    edx, edx
0x140024fd2  js      loc_14002508C
0x140024fd8  mov     r9, [rbx+8]; DestinationMdlChain
0x140024fdc  lea     rax, [rsi+0ECh]
0x140024fe3  mov     rcx, [rsi+0F0h]; SourceBuffer
0x140024fea  xor     edx, edx; SourceOffset
0x140024fec  mov     [rsp+58h+BytesCopied], rax; BytesCopied
0x140024ff1  mov     [rsp+58h+DestinationOffset], 0; DestinationOffset
0x140024ff9  call    cs:__imp_TdiCopyBufferToMdl
0x140025000  nop     dword ptr [rax+rax+00h]
0x140025005  mov     edi, eax
0x140025007  mov     edx, 1B6Eh
0x14002500c  mov     rax, [rsi+0F0h]
0x140025013  mov     r9d, edi
0x140025016  mov     qword ptr [rsp+58h+DestinationOffset], rax
0x14002501b  mov     r8, rsi
0x14002501e  mov     ecx, 1
0x140025023  call    AFDETW_TRACEBIND
0x140025028  xor     eax, eax
0x14002502a  xchg    eax, [rsi+170h]
0x140025030  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140025034  test    rcx, rcx
0x140025037  jz      short loc_140025063
0x140025039  test    byte ptr [rcx+0Ah], 2
0x14002503d  jz      short loc_14002504B
0x14002503f  call    cs:__imp_MmUnlockPages
0x140025046  nop     dword ptr [rax+rax+00h]
0x14002504b  mov     rcx, [rbx+8]; Mdl
0x14002504f  call    cs:__imp_IoFreeMdl
0x140025056  nop     dword ptr [rax+rax+00h]
0x14002505b  mov     qword ptr [rbx+8], 0
0x140025063  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x14002506a  mov     rcx, rbx; Irp
0x14002506d  mov     eax, ebp
0x14002506f  mov     [rbx+38h], rax
0x140025073  mov     [rbx+30h], edi
0x140025076  call    cs:__imp_IofCompleteRequest
0x14002507d  nop     dword ptr [rax+rax+00h]
0x140025082  add     rsp, 38h
0x140025086  pop     rdi
0x140025087  pop     rsi
0x140025088  pop     rbp
0x140025089  pop     rbx
0x14002508a  retn
0x14002508c  mov     edx, 1B6Fh
0x140025091  xor     eax, eax
0x140025093  jmp     loc_140025013
```
