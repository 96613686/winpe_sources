# Srv2DeviceControl

- ea: `0x14008c260`
- end: `0x14008c3f6`
- name: `Srv2DeviceControl`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14008c120`

## callees

- `0x14002019c`
- `0x140059338`
- `0x140059540`
- `0x14008c260`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008c3c3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14008c3c3`
- `ntoskrnl!IofCompleteRequest` at `0x14008c39d`
- `ntoskrnl!IofCompleteRequest` at `0x14008c39d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14008c296`
- `ntoskrnl!IoGetCurrentProcess` at `0x14008c296`
- `ntoskrnl!ProbeForRead` at `0x14009b70c`
- `ntoskrnl!ProbeForRead` at `0x14009b724`
- `ntoskrnl!ProbeForRead` at `0x14009b70c`
- `ntoskrnl!ProbeForRead` at `0x14009b724`

## pseudocode

```c
__int64 __fastcall Srv2DeviceControl(__int64 a1, IRP *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int LowPart; // r13d
  SIZE_T Length; // r12
  struct _IRP *Parameters; // rdi
  PVOID MappedSystemVa; // rsi
  PMDL MdlAddress; // rcx
  struct _IRP *MasterIrp; // r15
  int Options; // [rsp+90h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
  }
  if ( IoGetCurrentProcess() != Srv2ServerProcess )
  {
    v3 = Srv2QueueIrpToSystem(a2);
    goto LABEL_4;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (LowPart & 3) != 0 )
  {
    if ( (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 1
      || (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 2 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      if ( (_DWORD)Length )
      {
        MdlAddress = a2->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MappedSystemVa )
        {
          v4 = -1073741670;
          goto LABEL_17;
        }
      }
      else
      {
        MappedSystemVa = 0;
      }
      LODWORD(Parameters) = (_DWORD)MasterIrp;
      goto LABEL_9;
    }
    if ( (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 3 )
    {
      Parameters = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
      MappedSystemVa = a2->UserBuffer;
      if ( a2->RequestorMode == 1 )
      {
        ProbeForRead(Parameters, CurrentStackLocation->Parameters.Create.Options, 1u);
        ProbeForRead(MappedSystemVa, Length, 1u);
      }
      goto LABEL_9;
    }
    Parameters = 0;
  }
  else
  {
    Parameters = a2->AssociatedIrp.MasterIrp;
  }
  MappedSystemVa = Parameters;
LABEL_9:
  v3 = Srv2ProcessFsctl(
         (int)CurrentStackLocation->FileObject,
         (int)a2 + 48,
         (int)Parameters,
         Options,
         (__int64)MappedSystemVa,
         Length,
         LowPart,
         (__int64)&a2->IoStatus,
         (__int64)CurrentStackLocation->DeviceObject,
         a2);
LABEL_4:
  v4 = v3;
  if ( v3 != 259 )
  {
LABEL_17:
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x14008c260  mov     [rsp+arg_0], rbx
0x14008c265  mov     [rsp+arg_18], rsi
0x14008c26a  mov     [rsp+arg_8], rdx
0x14008c26f  push    rdi
0x14008c270  push    r12
0x14008c272  push    r13
0x14008c274  push    r14
0x14008c276  push    r15
0x14008c278  sub     rsp, 50h
0x14008c27c  mov     rbx, rdx
0x14008c27f  lea     rax, WPP_GLOBAL_Control
0x14008c286  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c28d  cmp     rcx, rax
0x14008c290  jnz     loc_14008C34A
0x14008c296  call    cs:__imp_IoGetCurrentProcess
0x14008c29d  nop     dword ptr [rax+rax+00h]
0x14008c2a2  cmp     rax, cs:Srv2ServerProcess
0x14008c2a9  jz      short loc_14008C2DE
0x14008c2ab  mov     rcx, rbx; Context
0x14008c2ae  call    Srv2QueueIrpToSystem
0x14008c2b3  mov     edi, eax
0x14008c2b5  cmp     edi, 103h
0x14008c2bb  jnz     loc_14008C395
0x14008c2c1  mov     eax, edi
0x14008c2c3  lea     r11, [rsp+78h+var_28]
0x14008c2c8  mov     rbx, [r11+30h]
0x14008c2cc  mov     rsi, [r11+48h]
0x14008c2d0  mov     rsp, r11
0x14008c2d3  pop     r15
0x14008c2d5  pop     r14
0x14008c2d7  pop     r13
0x14008c2d9  pop     r12
0x14008c2db  pop     rdi
0x14008c2dc  retn
0x14008c2de  mov     r14, [rbx+0B8h]
0x14008c2e5  mov     r13d, [r14+18h]
0x14008c2e9  mov     ecx, [r14+10h]
0x14008c2ed  mov     [rsp+78h+arg_10], ecx
0x14008c2f4  mov     r12d, [r14+8]
0x14008c2f8  mov     eax, r13d
0x14008c2fb  and     eax, 3
0x14008c2fe  jnz     loc_14008C3D4
0x14008c304  mov     rdi, [rbx+18h]
0x14008c308  mov     rsi, rdi
0x14008c30b  lea     rdx, [rbx+30h]; int
0x14008c30f  mov     [rsp+78h+Irp], rbx; Irp
0x14008c314  mov     rax, [r14+28h]
0x14008c318  mov     [rsp+78h+var_38], rax; __int64
0x14008c31d  mov     [rsp+78h+var_40], rdx; __int64
0x14008c322  mov     [rsp+78h+var_48], r13d; int
0x14008c327  mov     [rsp+78h+Priority], r12d; int
0x14008c32c  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi; __int64
0x14008c331  mov     r9d, [rsp+78h+arg_10]; int
0x14008c339  mov     r8, rdi; int
0x14008c33c  mov     rcx, [r14+30h]; int
0x14008c340  call    Srv2ProcessFsctl
0x14008c345  jmp     loc_14008C2B3
0x14008c34a  mov     eax, [rcx+2Ch]
0x14008c34d  test    al, 4
0x14008c34f  jz      loc_14008C296
0x14008c355  cmp     byte ptr [rcx+29h], 2
0x14008c359  jb      loc_14008C296
0x14008c35f  mov     edx, 0Fh
0x14008c364  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c36b  mov     rcx, [rcx+18h]
0x14008c36f  call    WPP_SF_
0x14008c374  jmp     loc_14008C296
0x14008c379  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14008c37d  test    byte ptr [rcx+0Ah], 5
0x14008c381  jz      short loc_14008C3AE
0x14008c383  mov     rsi, [rcx+18h]
0x14008c387  test    rsi, rsi
0x14008c38a  jnz     loc_14009B756
0x14008c390  mov     edi, 0C000009Ah
0x14008c395  mov     [rbx+30h], edi
0x14008c398  mov     dl, 2; PriorityBoost
0x14008c39a  mov     rcx, rbx; Irp
0x14008c39d  call    cs:__imp_IofCompleteRequest
0x14008c3a4  nop     dword ptr [rax+rax+00h]
0x14008c3a9  jmp     loc_14008C2C1
0x14008c3ae  mov     [rsp+78h+Priority], 40000010h; Priority
0x14008c3b6  mov     [rsp+78h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14008c3ba  xor     r9d, r9d; RequestedAddress
0x14008c3bd  xor     edx, edx; AccessMode
0x14008c3bf  lea     r8d, [r9+1]; CacheType
0x14008c3c3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008c3ca  nop     dword ptr [rax+rax+00h]
0x14008c3cf  mov     rsi, rax
0x14008c3d2  jmp     short loc_14008C387
0x14008c3d4  sub     eax, 1
0x14008c3d7  jz      loc_14009B745
0x14008c3dd  sub     eax, 1
0x14008c3e0  jz      loc_14009B745
0x14008c3e6  cmp     eax, 1
0x14008c3e9  jz      loc_14009B6EE
0x14008c3ef  xor     edi, edi
0x14008c3f1  jmp     loc_14008C308
0x14009b6ee  mov     rdi, [r14+20h]
0x14009b6f2  mov     rsi, [rbx+70h]
0x14009b6f6  cmp     byte ptr [rbx+40h], 1
0x14009b6fa  jnz     loc_14008C30B
0x14009b700  mov     rdx, rcx; Length
0x14009b703  mov     r8d, 1; Alignment
0x14009b709  mov     rcx, rdi; Address
0x14009b70c  call    cs:__imp_ProbeForRead
0x14009b713  nop     dword ptr [rax+rax+00h]
0x14009b718  mov     rdx, r12; Length
0x14009b71b  mov     r8d, 1; Alignment
0x14009b721  mov     rcx, rsi; Address
0x14009b724  call    cs:__imp_ProbeForRead
0x14009b72b  nop     dword ptr [rax+rax+00h]
0x14009b730  nop
0x14009b731  jmp     loc_14008C30B
0x14009b736  mov     edi, eax
0x14009b738  mov     rbx, [rsp+78h+arg_8]
0x14009b740  jmp     loc_14008C2B5
0x14009b745  mov     r15, [rbx+18h]
0x14009b749  xor     edi, edi
0x14009b74b  test    r12d, r12d
0x14009b74e  jnz     loc_14008C379
0x14009b754  mov     esi, edi
0x14009b756  mov     rdi, r15
0x14009b759  jmp     loc_14008C30B
```
