# FltLockUserBuffer

- ea: `0x180018cc0`
- end: `0x180018fe6`
- name: `FltLockUserBuffer`
- size: `806`
- prototype: `NTSTATUS __stdcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017d00`
- `0x18007f6e0`

## callees

- `0x180009f20`
- `0x180018cc0`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x180018e58`
- `ntoskrnl!IoAllocateMdl` at `0x180018e58`
- `ntoskrnl!IoFreeMdl` at `0x180018fcb`
- `ntoskrnl!IoFreeMdl` at `0x180018fcb`
- `ntoskrnl!MmProbeAndLockProcessPages` at `0x180018ebd`
- `ntoskrnl!MmProbeAndLockProcessPages` at `0x180018ebd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x180018fb2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x180018fb2`
- `ntoskrnl!IoThreadToProcess` at `0x180018e9f`
- `ntoskrnl!IoThreadToProcess` at `0x180018e9f`

## pseudocode

```c
NTSTATUS __stdcall FltLockUserBuffer(PFLT_CALLBACK_DATA CallbackData)
{
  PVOID *p_EaBuffer; // rdi
  ULONG *p_Parameters; // rbx
  PMDL *p_MdlAddress; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  __int64 MajorFunction; // rax
  __int64 v7; // r9
  int v8; // r8d
  FLT_PARAMETERS *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // r13d
  __int64 v13; // rax
  struct _MDL *Mdl; // rcx
  char v16; // r12
  FLT_CALLBACK_DATA_FLAGS Flags; // r15d
  KPROCESSOR_MODE RequestorMode; // bl
  struct _MDL *v19; // rdi
  struct _KPROCESS *v20; // rax
  LOCK_OPERATION Operation; // [rsp+90h] [rbp+18h]

  p_EaBuffer = 0;
  p_Parameters = 0;
  p_MdlAddress = 0;
  Operation = IoReadAccess;
  Iopb = CallbackData->Iopb;
  MajorFunction = Iopb->MajorFunction;
  if ( ((_BYTE)MajorFunction == 3 || (_BYTE)MajorFunction == 4) && Iopb->MinorFunction == 2 )
    return -1073741811;
  if ( (unsigned __int8)MajorFunction > 0x1Bu )
    goto LABEL_13;
  v7 = 2 * MajorFunction;
  v8 = FltGlobals[2 * MajorFunction + 1344];
  switch ( v8 )
  {
    case 255:
      goto LABEL_13;
    case 253:
LABEL_14:
      p_Parameters = (ULONG *)&Iopb->Parameters;
      if ( (CallbackData->Flags & 2) != 0 )
      {
        p_EaBuffer = &Iopb->Parameters.Create.EaBuffer;
        Operation = IoModifyAccess;
        goto LABEL_20;
      }
      if ( (Iopb->Parameters.Read.ByteOffset.LowPart & 3) != 0 )
      {
        if ( (Iopb->Parameters.Read.ByteOffset.LowPart & 3) - 1 < 2 )
        {
          p_EaBuffer = &Iopb->Parameters.Create.EaBuffer;
          p_MdlAddress = &Iopb->Parameters.QueryEa.MdlAddress;
          v13 = (Iopb->Parameters.Read.ByteOffset.LowPart & 3) != 1;
          goto LABEL_19;
        }
        p_EaBuffer = &Iopb->Parameters.Create.EaBuffer;
        p_MdlAddress = &Iopb->Parameters.QueryEa.MdlAddress;
      }
      else
      {
        p_EaBuffer = &Iopb->Parameters.CreatePipe.Parameters;
      }
      LODWORD(v13) = 2;
LABEL_19:
      Operation = (int)v13;
LABEL_20:
      v12 = 0;
      goto LABEL_21;
    case 254:
      if ( (Iopb->MinorFunction & 0xFB) != 0 )
      {
LABEL_13:
        v12 = -1073741811;
        goto LABEL_21;
      }
      goto LABEL_14;
  }
  v9 = &Iopb->Parameters;
  v10 = LOBYTE(FltGlobals[v7 + 1345]);
  if ( (_BYTE)v10 != 0xFF )
    p_MdlAddress = (PMDL *)((char *)v9 + v10);
  p_EaBuffer = (PVOID *)((char *)&v9->Others.Argument1 + BYTE1(FltGlobals[v7 + 1345]));
  v11 = BYTE2(FltGlobals[v7 + 1345]);
  if ( (_BYTE)v11 != 0xFF )
    p_Parameters = (ULONG *)((char *)v9 + v11);
  v12 = 0;
  Operation = v8;
LABEL_21:
  if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\parametersup.c", 1000, 3221225485LL) < 0 )
    return v12;
  if ( !p_MdlAddress || !p_Parameters )
    return -1073741811;
  Mdl = *p_MdlAddress;
  if ( *p_MdlAddress )
  {
    if ( (Mdl->MdlFlags & 0x817) != 0 )
      return 0;
    v16 = 0;
  }
  else
  {
    if ( !*p_Parameters )
      return -1073741306;
    Mdl = IoAllocateMdl(*p_EaBuffer, *p_Parameters, 0, 0, 0);
    *p_MdlAddress = Mdl;
    if ( !Mdl )
      return -1073741670;
    v16 = 1;
  }
  Flags = CallbackData->Flags;
  if ( (CallbackData->Flags & 8) != 0 )
  {
    if ( !v16 )
      return 0;
    MmBuildMdlForNonPagedPool(Mdl);
LABEL_32:
    if ( v16 )
    {
      if ( (Flags & 0x80000) == 0 )
        CallbackData->Flags |= 0x80000000;
    }
    return 0;
  }
  RequestorMode = CallbackData->RequestorMode;
  v19 = *p_MdlAddress;
  v20 = IoThreadToProcess(CallbackData->Thread);
  MmProbeAndLockProcessPages(v19, v20, RequestorMode, Operation);
  if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\parametersup.c", 1135, 0) >= 0 )
    goto LABEL_32;
  if ( v16 )
  {
    IoFreeMdl(*p_MdlAddress);
    *p_MdlAddress = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180018cc0  mov     [rsp+arg_0], rcx
0x180018cc5  push    rbx
0x180018cc6  push    rsi
0x180018cc7  push    rdi
0x180018cc8  push    r12
0x180018cca  push    r13
0x180018ccc  push    r14
0x180018cce  push    r15
0x180018cd0  sub     rsp, 40h
0x180018cd4  mov     r14, rcx
0x180018cd7  xor     edi, edi
0x180018cd9  xor     ebx, ebx
0x180018cdb  xor     esi, esi
0x180018cdd  mov     [rsp+78h+var_48], rsi
0x180018ce2  mov     [rsp+78h+Operation], ebx
0x180018ce9  mov     rdx, [rcx+10h]
0x180018ced  movzx   eax, byte ptr [rdx+4]
0x180018cf1  cmp     al, 3
0x180018cf3  jnz     loc_180018F2C
0x180018cf9  cmp     byte ptr [rdx+5], 2
0x180018cfd  jz      loc_180018F41
0x180018d03  cmp     al, 1Bh
0x180018d05  ja      short loc_180018D81
0x180018d07  lea     r9, ds:0[rax*8]
0x180018d0f  lea     r10, FltGlobals
0x180018d16  mov     r8d, [r9+r10+1500h]
0x180018d1e  cmp     r8d, 0FFh
0x180018d25  jz      short loc_180018D81
0x180018d27  mov     ecx, r8d
0x180018d2a  sub     ecx, 0FDh
0x180018d30  jz      short loc_180018D89
0x180018d32  cmp     ecx, 1
0x180018d35  jz      short loc_180018D7B
0x180018d37  add     rdx, 18h
0x180018d3b  movzx   eax, byte ptr [r9+r10+1504h]
0x180018d44  cmp     al, 0FFh
0x180018d46  jz      short loc_180018D4C
0x180018d48  lea     rsi, [rdx+rax]
0x180018d4c  mov     [rsp+78h+var_48], rsi
0x180018d51  movzx   edi, byte ptr [r9+r10+1505h]
0x180018d5a  add     rdi, rdx
0x180018d5d  movzx   eax, byte ptr [r9+r10+1506h]
0x180018d66  cmp     al, 0FFh
0x180018d68  jz      short loc_180018D6E
0x180018d6a  lea     rbx, [rdx+rax]
0x180018d6e  xor     r13d, r13d
0x180018d71  mov     [rsp+78h+Operation], r8d
0x180018d79  jmp     short loc_180018DD4
0x180018d7b  test    byte ptr [rdx+5], 0FBh
0x180018d7f  jz      short loc_180018D89
0x180018d81  mov     r13d, 0C000000Dh
0x180018d87  jmp     short loc_180018DD4
0x180018d89  lea     rbx, [rdx+18h]
0x180018d8d  mov     eax, [r14]
0x180018d90  test    al, 2
0x180018d92  jnz     loc_180018F80
0x180018d98  mov     ecx, [rdx+28h]
0x180018d9b  and     ecx, 3
0x180018d9e  mov     eax, ecx
0x180018da0  jz      loc_180018F4B
0x180018da6  sub     eax, 1
0x180018da9  jz      loc_180018F94
0x180018daf  cmp     eax, 1
0x180018db2  jz      loc_180018F94
0x180018db8  lea     rdi, [rbx+20h]
0x180018dbc  lea     rsi, [rbx+28h]
0x180018dc0  mov     eax, 2
0x180018dc5  mov     [rsp+78h+Operation], eax
0x180018dcc  mov     [rsp+78h+var_48], rsi
0x180018dd1  xor     r13d, r13d
0x180018dd4  mov     r8d, 3E8h
0x180018dda  mov     [rsp+78h+Irp], 0
0x180018de3  mov     r9d, 0C000000Dh
0x180018de9  lea     rdx, aMinkernelFsFil_17; "minkernel\\fs\\filtermgr\\filter\\param"...
0x180018df0  mov     ecx, r13d
0x180018df3  call    FltpDbgStatus
0x180018df8  test    eax, eax
0x180018dfa  js      loc_180018FDE
0x180018e00  test    rsi, rsi
0x180018e03  jz      loc_180018F41
0x180018e09  test    rbx, rbx
0x180018e0c  jz      loc_180018F41
0x180018e12  mov     rcx, [rsi]
0x180018e15  test    rcx, rcx
0x180018e18  jz      short loc_180018E3C
0x180018e1a  mov     edx, 817h
0x180018e1f  test    [rcx+0Ah], dx
0x180018e23  jz      loc_180018F39
0x180018e29  xor     eax, eax
0x180018e2b  add     rsp, 40h
0x180018e2f  pop     r15
0x180018e31  pop     r14
0x180018e33  pop     r13
0x180018e35  pop     r12
0x180018e37  pop     rdi
0x180018e38  pop     rsi
0x180018e39  pop     rbx
0x180018e3a  retn
0x180018e3c  mov     edx, [rbx]; Length
0x180018e3e  test    edx, edx
0x180018e40  jz      loc_180018F6A
0x180018e46  mov     [rsp+78h+Irp], 0; Irp
0x180018e4f  xor     r9d, r9d; ChargeQuota
0x180018e52  xor     r8d, r8d; SecondaryBuffer
0x180018e55  mov     rcx, [rdi]; VirtualAddress
0x180018e58  call    cs:__imp_IoAllocateMdl
0x180018e5f  nop     dword ptr [rax+rax+00h]
0x180018e64  mov     rcx, rax; MemoryDescriptorList
0x180018e67  mov     [rsi], rax
0x180018e6a  test    rax, rax
0x180018e6d  jz      loc_180018F54
0x180018e73  mov     r12b, 1
0x180018e76  mov     [rsp+78h+arg_8], r12b
0x180018e7e  mov     r15d, [r14]
0x180018e81  mov     [rsp+78h+arg_18], r15d
0x180018e89  test    r15b, 8
0x180018e8d  jnz     loc_180018FA9
0x180018e93  movzx   ebx, byte ptr [r14+50h]
0x180018e98  mov     rdi, [rsi]
0x180018e9b  mov     rcx, [r14+8]; Thread
0x180018e9f  call    cs:__imp_IoThreadToProcess
0x180018ea6  nop     dword ptr [rax+rax+00h]
0x180018eab  mov     rdx, rax; Process
0x180018eae  mov     r9d, [rsp+78h+Operation]; Operation
0x180018eb6  movzx   r8d, bl; AccessMode
0x180018eba  mov     rcx, rdi; MemoryDescriptorList
0x180018ebd  call    cs:__imp_MmProbeAndLockProcessPages
0x180018ec4  nop     dword ptr [rax+rax+00h]
0x180018ec9  jmp     short loc_180018EEC
0x180018ecb  mov     r13d, eax
0x180018ece  mov     r14, [rsp+78h+arg_0]
0x180018ed6  mov     rsi, [rsp+78h+var_48]
0x180018edb  movzx   r12d, [rsp+78h+arg_8]
0x180018ee4  mov     r15d, [rsp+78h+arg_18]
0x180018eec  mov     r8d, 46Fh
0x180018ef2  xor     r9d, r9d
0x180018ef5  lea     rdx, aMinkernelFsFil_17; "minkernel\\fs\\filtermgr\\filter\\param"...
0x180018efc  mov     ecx, r13d
0x180018eff  call    FltpDbgStatus
0x180018f04  test    eax, eax
0x180018f06  js      loc_180018FC3
0x180018f0c  test    r12b, r12b
0x180018f0f  jz      loc_180018E29
0x180018f15  bt      r15d, 13h
0x180018f1a  jb      loc_180018E29
0x180018f20  or      dword ptr [r14], 80000000h
0x180018f27  jmp     loc_180018E29
0x180018f2c  cmp     al, 4
0x180018f2e  jnz     loc_180018D03
0x180018f34  jmp     loc_180018CF9
0x180018f39  xor     r12b, r12b
0x180018f3c  jmp     loc_180018E76
0x180018f41  mov     eax, 0C000000Dh
0x180018f46  jmp     loc_180018E2B
0x180018f4b  lea     rdi, [rbx+18h]
0x180018f4f  jmp     loc_180018DC0
0x180018f54  mov     eax, 0C000009Ah
0x180018f59  add     rsp, 40h
0x180018f5d  pop     r15
0x180018f5f  pop     r14
0x180018f61  pop     r13
0x180018f63  pop     r12
0x180018f65  pop     rdi
0x180018f66  pop     rsi
0x180018f67  pop     rbx
0x180018f68  retn
0x180018f6a  mov     eax, 0C0000206h
0x180018f6f  add     rsp, 40h
0x180018f73  pop     r15
0x180018f75  pop     r14
0x180018f77  pop     r13
0x180018f79  pop     r12
0x180018f7b  pop     rdi
0x180018f7c  pop     rsi
0x180018f7d  pop     rbx
0x180018f7e  retn
0x180018f80  lea     rdi, [rbx+20h]
0x180018f84  mov     [rsp+78h+Operation], 2
0x180018f8f  jmp     loc_180018DCC
0x180018f94  lea     rdi, [rbx+20h]
0x180018f98  lea     rsi, [rbx+28h]
0x180018f9c  xor     eax, eax
0x180018f9e  cmp     ecx, 1
0x180018fa1  setnz   al
0x180018fa4  jmp     loc_180018DC5
0x180018fa9  test    r12b, r12b
0x180018fac  jz      loc_180018E29
0x180018fb2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x180018fb9  nop     dword ptr [rax+rax+00h]
0x180018fbe  jmp     loc_180018F0C
0x180018fc3  test    r12b, r12b
0x180018fc6  jz      short loc_180018FDE
0x180018fc8  mov     rcx, [rsi]; Mdl
0x180018fcb  call    cs:__imp_IoFreeMdl
0x180018fd2  nop     dword ptr [rax+rax+00h]
0x180018fd7  mov     qword ptr [rsi], 0
0x180018fde  mov     eax, r13d
0x180018fe1  jmp     loc_180018E2B
```
