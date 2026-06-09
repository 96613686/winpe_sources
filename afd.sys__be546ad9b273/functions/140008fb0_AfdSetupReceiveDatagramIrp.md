# AfdSetupReceiveDatagramIrp

- ea: `0x140008fb0`
- end: `0x140009692`
- name: `AfdSetupReceiveDatagramIrp`
- size: `1762`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, PVOID SourceBuffer@<rdx>, ULONG SourceBytesToCopy@<r8d>, int, void *Src, int, int, char, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008210`
- `0x14000d7f0`
- `0x140019364`
- `0x1400537b0`

## callees

- `0x140008fb0`
- `0x140009920`
- `0x140009fb0`
- `0x1400303b0`
- `0x140072870`
- `0x140072880`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090f3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400092a8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000938f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000941e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090f3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400092a8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000938f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000941e`
- `ntoskrnl!IoFreeMdl` at `0x140009126`
- `ntoskrnl!IoFreeMdl` at `0x140009144`
- `ntoskrnl!IoFreeMdl` at `0x140009340`
- `ntoskrnl!IoFreeMdl` at `0x1400093be`
- `ntoskrnl!IoFreeMdl` at `0x140009466`
- `ntoskrnl!IoFreeMdl` at `0x140009126`
- `ntoskrnl!IoFreeMdl` at `0x140009144`
- `ntoskrnl!IoFreeMdl` at `0x140009340`
- `ntoskrnl!IoFreeMdl` at `0x1400093be`
- `ntoskrnl!IoFreeMdl` at `0x140009466`
- `ntoskrnl!MmUnlockPages` at `0x140009117`
- `ntoskrnl!MmUnlockPages` at `0x140009135`
- `ntoskrnl!MmUnlockPages` at `0x140009331`
- `ntoskrnl!MmUnlockPages` at `0x1400093af`
- `ntoskrnl!MmUnlockPages` at `0x140009452`
- `ntoskrnl!MmUnlockPages` at `0x140009117`
- `ntoskrnl!MmUnlockPages` at `0x140009135`
- `ntoskrnl!MmUnlockPages` at `0x140009331`
- `ntoskrnl!MmUnlockPages` at `0x1400093af`
- `ntoskrnl!MmUnlockPages` at `0x140009452`
- `ntoskrnl!IoIs32bitProcess` at `0x1400092e2`
- `ntoskrnl!IoIs32bitProcess` at `0x14000956e`
- `ntoskrnl!IoIs32bitProcess` at `0x1400092e2`
- `ntoskrnl!IoIs32bitProcess` at `0x14000956e`
- `TDI!TdiCopyBufferToMdl` at `0x140009551`
- `TDI!TdiCopyBufferToMdl` at `0x140009551`
- `NETIO!RtlCopyMdlToMdl` at `0x140009501`
- `NETIO!RtlCopyMdlToMdl` at `0x140009501`

## pseudocode

```c
__int64 __fastcall AfdSetupReceiveDatagramIrp(
        PIRP Irp,
        PVOID SourceBuffer,
        ULONG SourceBytesToCopy,
        void *a4,
        unsigned int a5,
        unsigned __int16 *Src,
        unsigned int a7,
        __int16 a8,
        char a9,
        unsigned int a10)
{
  unsigned __int16 *v10; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  int v13; // r13d
  unsigned __int64 v14; // r12
  signed int Status; // esi
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  signed int v18; // r15d
  PUNICODE_STRING FileName; // r15
  unsigned int v20; // ecx
  PVOID SecurityQos; // rax
  _DWORD *Buffer; // rcx
  LARGE_INTEGER ByteOffset; // rdi
  char v24; // r14
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdi
  PMDL v26; // rax
  struct _MDL *MdlAddress; // rcx
  unsigned __int16 *v29; // rcx
  unsigned int v30; // ecx
  _DWORD *v31; // r14
  struct _MDL *v32; // rax
  _DWORD *QuadPart; // rdx
  ULONG ByteCount; // edx
  char *v35; // rax
  char *MappedSystemVa; // rdx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  PMDL v40; // rax
  size_t v41; // rdx
  char *v42; // rcx
  size_t v43; // rax
  char *v44; // [rsp+60h] [rbp-58h]
  size_t Size; // [rsp+68h] [rbp-50h]
  size_t Sizea; // [rsp+68h] [rbp-50h]
  __int64 v47; // [rsp+70h] [rbp-48h]
  char v48; // [rsp+C0h] [rbp+8h]
  PMDL MemoryDescriptorList; // [rsp+C8h] [rbp+10h] BYREF
  void *v50; // [rsp+D8h] [rbp+20h]

  v50 = a4;
  v10 = Src;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v13 = 0;
  v14 = SourceBytesToCopy;
  v48 = 0;
  v47 = (__int64)Src;
  if ( !SourceBuffer )
  {
    if ( SourceBytesToCopy > *((_DWORD *)&Irp->Tail.CompletionKey + 6) )
      Status = -2147483643;
    else
      Status = Irp->IoStatus.Status;
    goto LABEL_4;
  }
  MdlAddress = Irp->MdlAddress;
  LODWORD(Src) = 0;
  if ( !MdlAddress )
  {
    Status = SourceBytesToCopy != 0 ? 0x80000005 : 0;
    goto LABEL_24;
  }
  Status = AfdMapMdlChain(MdlAddress);
  if ( Status < 0 )
  {
LABEL_24:
    Irp->IoStatus.Information = (unsigned int)Src;
    goto LABEL_4;
  }
  v40 = Irp->MdlAddress;
  if ( !a9 )
  {
    Status = TdiCopyBufferToMdl(SourceBuffer, 0, v14, Irp->MdlAddress, 0, (PULONG)&Src);
    goto LABEL_24;
  }
  MemoryDescriptorList = 0;
  RtlCopyMdlToMdl(SourceBuffer, a10, v40, 0, v14, &MemoryDescriptorList);
  Status = 0;
  LODWORD(Src) = (_DWORD)MemoryDescriptorList;
  if ( (unsigned __int64)MemoryDescriptorList < v14 )
    Status = -2147483643;
  Irp->IoStatus.Information = (unsigned int)MemoryDescriptorList;
LABEL_4:
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  v18 = Status;
  LODWORD(MemoryDescriptorList) = Status;
  if ( SecurityContext )
  {
    FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
    CurrentStackLocation->Parameters.QueryDirectory.FileName = 0;
    CurrentStackLocation->Parameters.WMI.ProviderId = 0;
    v13 = 252706816;
    if ( (Status >= 0
       || Status == -1073741249
       || (unsigned int)(Status + 1073741252) <= 1
       || Status == -2147483643
       || Status == -1073700846)
      && v10 )
    {
      if ( (*((_DWORD *)CurrentStackLocation->FileObject->FsContext + 2) & 0x100) != 0 )
      {
        v20 = a7;
      }
      else
      {
        v20 = v10[2] + 2;
        v10 += 3;
      }
      LODWORD(Src) = v20;
      if ( v20 > SecurityContext[1].DesiredAccess )
      {
        Status = -1073741789;
      }
      else
      {
        if ( (BYTE2(SecurityContext->AccessState) & 5) != 0 )
        {
          SecurityQos = SecurityContext[1].SecurityQos;
        }
        else
        {
          SecurityQos = MmMapLockedPagesSpecifyCache((PMDL)SecurityContext, 0, MmCached, 0, 0, 0x40000000u);
          v20 = (unsigned int)Src;
        }
        if ( SecurityQos
          && ((RtlMoveVolatileMemory(SecurityQos, v10, v20), (BYTE2(FileName->Buffer) & 5) != 0)
            ? (Buffer = FileName[1].Buffer)
            : (Buffer = MmMapLockedPagesSpecifyCache((PMDL)FileName, 0, MmCached, 0, 0, 0x40000000u)),
              Buffer) )
        {
          *Buffer = (_DWORD)Src;
        }
        else
        {
          Status = -1073741670;
        }
      }
    }
    MmUnlockPages((PMDL)SecurityContext);
    IoFreeMdl((PMDL)SecurityContext);
    MmUnlockPages((PMDL)FileName);
    IoFreeMdl((PMDL)FileName);
    v18 = (int)MemoryDescriptorList;
  }
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  if ( !ByteOffset.QuadPart )
  {
    v24 = 0;
    goto LABEL_20;
  }
  MemoryDescriptorList = (PMDL)Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = 0;
  if ( (Status & 0xC0000000) == 0xC0000000 )
    goto LABEL_41;
  if ( (*(_BYTE *)(ByteOffset.QuadPart + 10) & 5) != 0 )
    v29 = *(unsigned __int16 **)(ByteOffset.QuadPart + 24);
  else
    v29 = (unsigned __int16 *)MmMapLockedPagesSpecifyCache((PMDL)ByteOffset.QuadPart, 0, MmCached, 0, 0, 0x40000000u);
  Src = v29;
  if ( !v29 )
  {
    Status = -1073741670;
    goto LABEL_41;
  }
  if ( (a8 & 0x1000) == 0 )
  {
    v30 = 0;
    goto LABEL_39;
  }
  if ( !IoIs32bitProcess(Irp) )
  {
    v30 = a5;
LABEL_39:
    v31 = v50;
    goto LABEL_40;
  }
  v31 = v50;
  v30 = AfdComputeCMSGLength32((int *)v50, a5);
LABEL_40:
  *(_DWORD *)Src = v30;
  if ( v30 )
  {
    v32 = MemoryDescriptorList;
    if ( !MemoryDescriptorList )
    {
      v24 = 1;
      Status = -2147483643;
      goto LABEL_43;
    }
    ByteCount = MemoryDescriptorList->ByteCount;
    LODWORD(Src) = ByteCount;
    if ( v30 > ByteCount )
    {
      v48 = 1;
      Status = -2147483643;
      v30 = ByteCount;
    }
    else
    {
      LODWORD(Src) = v30;
    }
    if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
    {
      MappedSystemVa = (char *)MemoryDescriptorList->MappedSystemVa;
      v44 = MappedSystemVa;
    }
    else
    {
      v35 = (char *)MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000000u);
      v30 = (unsigned int)Src;
      MappedSystemVa = v35;
      v44 = v35;
      v32 = MemoryDescriptorList;
    }
    if ( MappedSystemVa )
    {
      Size = v30;
      if ( IoIs32bitProcess(Irp) )
      {
        v41 = Size;
        if ( Size >= 0xC )
        {
          v42 = v44;
          do
          {
            LODWORD(Src) = 0;
            LODWORD(Src) = *v31 - 4;
            v43 = ((_DWORD)Src + 3) & 0xFFFFFFFC;
            if ( v41 < v43 )
              break;
            Sizea = v41 - v43;
            RtlCopyVolatileMemory(v42 + 4, v31 + 2, 4u);
            RtlCopyVolatileMemory(v44 + 8, v31 + 3, 4u);
            RtlCopyVolatileMemory(v44, &Src, 4u);
            RtlCopyVolatileMemory(v44 + 12, v31 + 4, (unsigned int)Src - 12LL);
            v41 = Sizea;
            v31 = (_DWORD *)((char *)v31 + ((*(_QWORD *)v31 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL));
            v42 = &v44[((_DWORD)Src + 3) & 0xFFFFFFFC];
            v44 = v42;
          }
          while ( Sizea >= 0xC );
        }
        v32 = MemoryDescriptorList;
      }
      else
      {
        RtlMoveVolatileMemory(v44, v31, Size);
        v32 = MemoryDescriptorList;
      }
    }
    else
    {
      Status = -1073741670;
    }
    goto LABEL_57;
  }
LABEL_41:
  v32 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
LABEL_57:
    MmUnlockPages(v32);
    IoFreeMdl(MemoryDescriptorList);
    v24 = v48;
    goto LABEL_43;
  }
  v24 = 0;
LABEL_43:
  MmUnlockPages((PMDL)ByteOffset.QuadPart);
  IoFreeMdl((PMDL)ByteOffset.QuadPart);
LABEL_20:
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( Parameters )
  {
    CurrentStackLocation->Parameters.CreatePipe.Parameters = 0;
    v13 = 253755392;
    if ( (Status & 0xC0000000) != 0xC0000000 )
    {
      if ( (Parameters->CompletionMode & 0x50000) != 0 )
        QuadPart = (_DWORD *)Parameters->DefaultTimeout.QuadPart;
      else
        QuadPart = MmMapLockedPagesSpecifyCache((PMDL)Parameters, 0, MmCached, 0, 0, 0x40000000u);
      if ( QuadPart )
      {
        v37 = (a8 & 4) != 0 ? 0x400 : 0;
        if ( (a8 & 8) != 0 )
        {
          v37 = 3072;
          if ( (a8 & 4) == 0 )
            v37 = 2048;
        }
        v38 = v37 | 0x100;
        if ( v18 != -2147483643 )
          v38 = v37;
        v39 = v38 | 0x200;
        if ( !v24 )
          v39 = v38;
        *QuadPart = v39;
      }
      else
      {
        Status = -1073741670;
      }
    }
    MmUnlockPages((PMDL)Parameters);
    IoFreeMdl((PMDL)Parameters);
  }
  v26 = Irp->MdlAddress;
  Irp->IoStatus.Status = Status;
  AFDETW_TRACERECVDATAGRAM(
    1,
    4052,
    (__int64)CurrentStackLocation->FileObject->FsContext,
    0,
    1,
    (__int64)v26,
    v14,
    Status,
    v47,
    (__int64)Irp,
    v13,
    1);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140008fb0  mov     [rsp+arg_10], rbx
0x140008fb5  mov     [rsp+arg_18], r9
0x140008fba  push    rbp
0x140008fbb  push    rsi
0x140008fbc  push    rdi
0x140008fbd  push    r12
0x140008fbf  push    r13
0x140008fc1  push    r14
0x140008fc3  push    r15
0x140008fc5  sub     rsp, 80h
0x140008fcc  mov     r14, [rsp+0B8h+Src]
0x140008fd4  mov     r15, rdx
0x140008fd7  mov     rbp, [rcx+0B8h]
0x140008fde  xor     r13d, r13d
0x140008fe1  mov     r12d, r8d
0x140008fe4  mov     rbx, rcx
0x140008fe7  mov     [rsp+0B8h+arg_0], 0
0x140008fef  mov     edx, 80000005h
0x140008ff4  mov     [rsp+0B8h+var_48], r14
0x140008ff9  test    r15, r15
0x140008ffc  jnz     loc_1400091E3
0x140009002  cmp     r12d, [rcx+90h]
0x140009009  ja      loc_140009601
0x14000900f  mov     esi, [rcx+30h]
0x140009012  mov     rdi, [rbp+8]
0x140009016  mov     r15d, esi
0x140009019  mov     dword ptr [rsp+0B8h+MemoryDescriptorList], esi
0x140009020  test    rdi, rdi
0x140009023  jz      loc_140009158
0x140009029  mov     r15, [rbp+10h]
0x14000902d  mov     [rbp+10h], r13
0x140009031  mov     [rbp+8], r13
0x140009035  mov     r13d, 0F100000h
0x14000903b  test    esi, esi
0x14000903d  js      loc_14000921C
0x140009043  test    r14, r14
0x140009046  jz      loc_140009114
0x14000904c  mov     rax, [rbp+30h]
0x140009050  mov     rax, [rax+18h]
0x140009054  mov     eax, [rax+8]
0x140009057  bt      eax, 8
0x14000905b  jnb     loc_140009608
0x140009061  mov     ecx, [rsp+0B8h+arg_30]
0x140009068  mov     dword ptr [rsp+0B8h+Src], ecx
0x14000906f  cmp     ecx, [rdi+28h]
0x140009072  ja      loc_140009619
0x140009078  test    byte ptr [rdi+0Ah], 5
0x14000907c  jnz     loc_1400095B9
0x140009082  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x14000908a  xor     r9d, r9d; RequestedAddress
0x14000908d  xor     edx, edx; AccessMode
0x14000908f  mov     [rsp+0B8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140009097  mov     r8d, 1; CacheType
0x14000909d  mov     rcx, rdi; MemoryDescriptorList
0x1400090a0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400090a7  nop     dword ptr [rax+rax+00h]
0x1400090ac  mov     ecx, dword ptr [rsp+0B8h+Src]
0x1400090b3  test    rax, rax
0x1400090b6  jz      loc_140009250
0x1400090bc  mov     r8d, ecx; Size
0x1400090bf  mov     rdx, r14; Src
0x1400090c2  mov     rcx, rax; void *
0x1400090c5  call    RtlMoveVolatileMemory
0x1400090ca  test    byte ptr [r15+0Ah], 5
0x1400090cf  jnz     loc_1400095C2
0x1400090d5  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x1400090dd  xor     r9d, r9d; RequestedAddress
0x1400090e0  xor     edx, edx; AccessMode
0x1400090e2  mov     [rsp+0B8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400090ea  mov     r8d, 1; CacheType
0x1400090f0  mov     rcx, r15; MemoryDescriptorList
0x1400090f3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400090fa  nop     dword ptr [rax+rax+00h]
0x1400090ff  mov     rcx, rax
0x140009102  test    rcx, rcx
0x140009105  jz      loc_140009250
0x14000910b  mov     eax, dword ptr [rsp+0B8h+Src]
0x140009112  mov     [rcx], eax
0x140009114  mov     rcx, rdi; MemoryDescriptorList
0x140009117  call    cs:__imp_MmUnlockPages
0x14000911e  nop     dword ptr [rax+rax+00h]
0x140009123  mov     rcx, rdi; Mdl
0x140009126  call    cs:__imp_IoFreeMdl
0x14000912d  nop     dword ptr [rax+rax+00h]
0x140009132  mov     rcx, r15; MemoryDescriptorList
0x140009135  call    cs:__imp_MmUnlockPages
0x14000913c  nop     dword ptr [rax+rax+00h]
0x140009141  mov     rcx, r15; Mdl
0x140009144  call    cs:__imp_IoFreeMdl
0x14000914b  nop     dword ptr [rax+rax+00h]
0x140009150  mov     r15d, dword ptr [rsp+0B8h+MemoryDescriptorList]
0x140009158  mov     rdi, [rbp+18h]
0x14000915c  test    rdi, rdi
0x14000915f  jnz     loc_14000925A
0x140009165  xor     r14b, r14b
0x140009168  mov     rdi, [rbp+20h]
0x14000916c  test    rdi, rdi
0x14000916f  jnz     loc_140009351
0x140009175  mov     rax, [rsp+0B8h+var_48]
0x14000917a  xor     r9d, r9d
0x14000917d  mov     [rsp+0B8h+var_60], 1
0x140009182  mov     edx, 0FD4h
0x140009187  mov     [rsp+0B8h+var_68], r13d
0x14000918c  mov     ecx, 1
0x140009191  mov     [rsp+0B8h+var_70], rbx
0x140009196  mov     [rsp+0B8h+var_78], rax
0x14000919b  mov     rax, [rbx+8]
0x14000919f  mov     [rbx+30h], esi
0x1400091a2  mov     r8, [rbp+30h]
0x1400091a6  mov     [rsp+0B8h+var_80], esi
0x1400091aa  mov     [rsp+0B8h+var_88], r12d
0x1400091af  mov     qword ptr [rsp+0B8h+Priority], rax
0x1400091b4  mov     r8, [r8+18h]
0x1400091b8  mov     [rsp+0B8h+BugCheckOnFailure], 1
0x1400091c0  call    AFDETW_TRACERECVDATAGRAM
0x1400091c5  mov     rbx, [rsp+0B8h+arg_10]
0x1400091cd  mov     eax, esi
0x1400091cf  add     rsp, 80h
0x1400091d6  pop     r15
0x1400091d8  pop     r14
0x1400091da  pop     r13
0x1400091dc  pop     r12
0x1400091de  pop     rdi
0x1400091df  pop     rsi
0x1400091e0  pop     rbp
0x1400091e1  retn
0x1400091e3  mov     rcx, [rcx+8]; MemoryDescriptorList
0x1400091e7  mov     dword ptr [rsp+0B8h+Src], r13d
0x1400091ef  test    rcx, rcx
0x1400091f2  jz      loc_1400095F3
0x1400091f8  call    AfdMapMdlChain
0x1400091fd  mov     esi, eax
0x1400091ff  test    eax, eax
0x140009201  jns     loc_1400094C9
0x140009207  mov     edx, 80000005h
0x14000920c  mov     eax, dword ptr [rsp+0B8h+Src]
0x140009213  mov     [rbx+38h], rax
0x140009217  jmp     loc_140009012
0x14000921c  cmp     esi, 0C000023Fh
0x140009222  jz      loc_140009043
0x140009228  lea     eax, [rsi+3FFFFDC4h]
0x14000922e  cmp     eax, 1
0x140009231  jbe     loc_140009043
0x140009237  cmp     esi, edx
0x140009239  jz      loc_140009043
0x14000923f  cmp     esi, 0C000A012h
0x140009245  jz      loc_140009043
0x14000924b  jmp     loc_140009114
0x140009250  mov     esi, 0C000009Ah
0x140009255  jmp     loc_140009114
0x14000925a  mov     rax, [rbx+78h]
0x14000925e  xor     r8d, r8d
0x140009261  mov     [rsp+0B8h+MemoryDescriptorList], rax
0x140009269  mov     eax, esi
0x14000926b  and     eax, 0C0000000h
0x140009270  mov     [rbx+78h], r8
0x140009274  mov     [rbp+18h], r8
0x140009278  cmp     eax, 0C0000000h
0x14000927d  jz      loc_14000931A
0x140009283  test    byte ptr [rdi+0Ah], 5
0x140009287  jnz     loc_1400095CB
0x14000928d  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x140009295  xor     r9d, r9d; RequestedAddress
0x140009298  mov     [rsp+0B8h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x14000929d  xor     edx, edx; AccessMode
0x14000929f  mov     r8d, 1; CacheType
0x1400092a5  mov     rcx, rdi; MemoryDescriptorList
0x1400092a8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400092af  nop     dword ptr [rax+rax+00h]
0x1400092b4  mov     rcx, rax
0x1400092b7  mov     [rsp+0B8h+Src], rax
0x1400092bf  xor     r8d, r8d
0x1400092c2  test    rcx, rcx
0x1400092c5  jnz     short loc_1400092CE
0x1400092c7  mov     esi, 0C000009Ah
0x1400092cc  jmp     short loc_14000931A
0x1400092ce  test    dword ptr [rsp+0B8h+arg_38], 1000h
0x1400092d9  jz      loc_140009623
0x1400092df  mov     rcx, rbx; Irp
0x1400092e2  call    cs:__imp_IoIs32bitProcess
0x1400092e9  nop     dword ptr [rax+rax+00h]
0x1400092ee  test    al, al
0x1400092f0  jnz     loc_14000962B
0x1400092f6  mov     ecx, [rsp+0B8h+arg_20]
0x1400092fd  xor     r8d, r8d
0x140009300  mov     r14, [rsp+0B8h+arg_18]
0x140009308  mov     rax, [rsp+0B8h+Src]
0x140009310  mov     [rax], ecx
0x140009312  test    ecx, ecx
0x140009314  jnz     loc_1400093CF
0x14000931a  mov     rax, [rsp+0B8h+MemoryDescriptorList]
0x140009322  test    rax, rax
0x140009325  jnz     loc_14000944F
0x14000932b  xor     r14b, r14b
0x14000932e  mov     rcx, rdi; MemoryDescriptorList
0x140009331  call    cs:__imp_MmUnlockPages
0x140009338  nop     dword ptr [rax+rax+00h]
0x14000933d  mov     rcx, rdi; Mdl
0x140009340  call    cs:__imp_IoFreeMdl
0x140009347  nop     dword ptr [rax+rax+00h]
0x14000934c  jmp     loc_140009168
0x140009351  xor     ecx, ecx
0x140009353  mov     eax, esi
0x140009355  and     eax, 0C0000000h
0x14000935a  mov     [rbp+20h], rcx
0x14000935e  mov     r13d, 0F200000h
0x140009364  cmp     eax, 0C0000000h
0x140009369  jz      short loc_1400093AC
0x14000936b  test    byte ptr [rdi+0Ah], 5
0x14000936f  jnz     loc_1400095EA
0x140009375  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x14000937d  xor     r9d, r9d; RequestedAddress
0x140009380  mov     [rsp+0B8h+BugCheckOnFailure], ecx; BugCheckOnFailure
0x140009384  xor     edx, edx; AccessMode
0x140009386  mov     rcx, rdi; MemoryDescriptorList
0x140009389  mov     r8d, 1; CacheType
0x14000938f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140009396  nop     dword ptr [rax+rax+00h]
0x14000939b  mov     rdx, rax
0x14000939e  test    rdx, rdx
0x1400093a1  jnz     loc_140009480
0x1400093a7  mov     esi, 0C000009Ah
0x1400093ac  mov     rcx, rdi; MemoryDescriptorList
0x1400093af  call    cs:__imp_MmUnlockPages
0x1400093b6  nop     dword ptr [rax+rax+00h]
0x1400093bb  mov     rcx, rdi; Mdl
0x1400093be  call    cs:__imp_IoFreeMdl
0x1400093c5  nop     dword ptr [rax+rax+00h]
0x1400093ca  jmp     loc_140009175
0x1400093cf  mov     rax, [rsp+0B8h+MemoryDescriptorList]
0x1400093d7  test    rax, rax
0x1400093da  jz      loc_14000964C
0x1400093e0  mov     edx, [rax+28h]
0x1400093e3  mov     dword ptr [rsp+0B8h+Src], edx
0x1400093ea  cmp     ecx, edx
0x1400093ec  ja      loc_140009659
0x1400093f2  mov     dword ptr [rsp+0B8h+Src], ecx
0x1400093f9  test    byte ptr [rax+0Ah], 5
0x1400093fd  jnz     loc_1400095DC
0x140009403  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x14000940b  xor     r9d, r9d; RequestedAddress
0x14000940e  mov     [rsp+0B8h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x140009413  xor     edx, edx; AccessMode
0x140009415  mov     r8d, 1; CacheType
0x14000941b  mov     rcx, rax; MemoryDescriptorList
0x14000941e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140009425  nop     dword ptr [rax+rax+00h]
0x14000942a  mov     ecx, dword ptr [rsp+0B8h+Src]
0x140009431  mov     rdx, rax
0x140009434  mov     [rsp+0B8h+var_58], rax
0x140009439  mov     rax, [rsp+0B8h+MemoryDescriptorList]
0x140009441  test    rdx, rdx
0x140009444  jnz     loc_140009564
0x14000944a  mov     esi, 0C000009Ah
0x14000944f  mov     rcx, rax; MemoryDescriptorList
0x140009452  call    cs:__imp_MmUnlockPages
0x140009459  nop     dword ptr [rax+rax+00h]
0x14000945e  mov     rcx, [rsp+0B8h+MemoryDescriptorList]; Mdl
0x140009466  call    cs:__imp_IoFreeMdl
0x14000946d  nop     dword ptr [rax+rax+00h]
0x140009472  movzx   r14d, [rsp+0B8h+arg_0]
0x14000947b  jmp     loc_14000932E
0x140009480  mov     r8d, dword ptr [rsp+0B8h+arg_38]
0x140009488  and     r8d, 4
0x14000948c  mov     ecx, r8d
0x14000948f  neg     ecx
0x140009491  sbb     eax, eax
0x140009493  and     eax, 400h
0x140009498  test    byte ptr [rsp+0B8h+arg_38], 8
0x1400094a0  jnz     loc_14000967D
0x1400094a6  mov     ecx, eax
0x1400094a8  bts     ecx, 8
0x1400094ac  cmp     r15d, 80000005h
0x1400094b3  cmovnz  ecx, eax
0x1400094b6  mov     eax, ecx
0x1400094b8  bts     eax, 9
0x1400094bc  test    r14b, r14b
0x1400094bf  cmovz   eax, ecx
0x1400094c2  mov     [rdx], eax
0x1400094c4  jmp     loc_1400093AC
0x1400094c9  mov     rax, [rbx+8]
0x1400094cd  cmp     [rsp+0B8h+arg_40], r13b
0x1400094d5  jz      short loc_140009534
0x1400094d7  mov     edx, [rsp+0B8h+arg_48]
0x1400094de  lea     rcx, [rsp+0B8h+MemoryDescriptorList]
0x1400094e6  mov     qword ptr [rsp+0B8h+Priority], rcx
0x1400094eb  xor     r9d, r9d
0x1400094ee  mov     rcx, r15
0x1400094f1  mov     [rsp+0B8h+MemoryDescriptorList], r13
0x1400094f9  mov     r8, rax
0x1400094fc  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], r12
0x140009501  call    cs:__imp_RtlCopyMdlToMdl
0x140009508  nop     dword ptr [rax+rax+00h]
0x14000950d  mov     rax, [rsp+0B8h+MemoryDescriptorList]
0x140009515  xor     esi, esi
0x140009517  cmp     rax, r12
0x14000951a  mov     dword ptr [rsp+0B8h+Src], eax
0x140009521  mov     eax, eax
0x140009523  mov     edx, 80000005h
0x140009528  cmovb   esi, edx
  ... truncated ...
```
