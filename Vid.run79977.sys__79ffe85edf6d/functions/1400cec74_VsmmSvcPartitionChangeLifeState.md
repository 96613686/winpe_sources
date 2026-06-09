# VsmmSvcPartitionChangeLifeState

- ea: `0x1400cec74`
- end: `0x1400cee23`
- name: `VsmmSvcPartitionChangeLifeState`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14008cb38`

## callees

- `0x1400386a0`
- `0x1400cec74`
- `0x1400cf318`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400cecd4`
- `ntoskrnl!ProbeForRead` at `0x1400cecd4`
- `ntoskrnl!IoFreeMdl` at `0x1400cedfa`
- `ntoskrnl!IoFreeMdl` at `0x1400cedfa`
- `ntoskrnl!IoAllocateMdl` at `0x1400cecf0`
- `ntoskrnl!IoAllocateMdl` at `0x1400cecf0`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ced1f`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ced1f`
- `ntoskrnl!MmUnlockPages` at `0x1400cede6`
- `ntoskrnl!MmUnlockPages` at `0x1400cede6`

## pseudocode

```c
__int64 __fastcall VsmmSvcPartitionChangeLifeState(__int64 a1, int a2, volatile void *a3, ULONG a4)
{
  char v7; // r14
  struct _MDL *v8; // rdi
  int v9; // edx
  int v10; // ebx
  unsigned int v11; // r12d
  struct _MDL *Mdl; // rax
  __int64 ByteOffset_low; // r9
  __int16 ByteCount; // ax
  struct _MDL *v15; // r8
  int Irp; // [rsp+20h] [rbp-48h]

  v7 = 0;
  v8 = 0;
  v9 = a2 - 1;
  if ( v9 )
  {
    if ( v9 != 1 )
    {
LABEL_3:
      v10 = -1073741811;
      goto LABEL_16;
    }
    v11 = 1;
  }
  else
  {
    v11 = 0;
  }
  if ( a3 )
  {
    ProbeForRead(a3, a4, 1u);
    Mdl = IoAllocateMdl((PVOID)a3, a4, 0, 0, 0);
    v8 = Mdl;
    if ( !Mdl )
    {
      v10 = -1073741670;
      goto LABEL_16;
    }
    MmProbeAndLockPages(Mdl, 0, IoReadAccess);
    v7 = 1;
    if ( ((v8->ByteCount + ((v8->ByteOffset + LODWORD(v8->StartVa)) & 0xFFF) + 4095LL) & 0xFFFFFFFFFFFFF000uLL) > 0x8000 )
    {
      v10 = -1073741811;
      VidTraceErrorInternal0("VsmmSvcPartitionChangeLifeState", "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c", 346);
      goto LABEL_16;
    }
    ByteOffset_low = LOWORD(v8->ByteOffset);
    ByteCount = v8->ByteCount;
    v15 = v8 + 1;
  }
  else
  {
    if ( a4 )
      goto LABEL_3;
    ByteCount = 0;
    v15 = 0;
    ByteOffset_low = 0;
  }
  LOWORD(Irp) = ByteCount;
  v10 = VsmmSvcpCallChangePartitionState(*(_QWORD *)(a1 + 648), v11, v15, ByteOffset_low, Irp);
  if ( v10 >= 0 )
    v10 = 0;
LABEL_16:
  if ( v7 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400cec74  mov     [rsp+arg_0], rbx
0x1400cec79  mov     [rsp+arg_10], rsi
0x1400cec7e  push    rdi
0x1400cec7f  push    r12
0x1400cec81  push    r13
0x1400cec83  push    r14
0x1400cec85  push    r15
0x1400cec87  sub     rsp, 40h
0x1400cec8b  mov     ebx, r9d
0x1400cec8e  mov     r15, r8
0x1400cec91  mov     r13, rcx
0x1400cec94  xor     esi, esi
0x1400cec96  mov     r14b, sil
0x1400cec99  mov     edi, esi
0x1400cec9b  mov     [rsp+68h+var_30], rsi
0x1400ceca0  sub     edx, 1
0x1400ceca3  jz      short loc_1400CECBC
0x1400ceca5  cmp     edx, 1
0x1400ceca8  jz      short loc_1400CECB4
0x1400cecaa  mov     ebx, 0C000000Dh
0x1400cecaf  jmp     loc_1400CEDDE
0x1400cecb4  mov     r12d, 1
0x1400cecba  jmp     short loc_1400CECBF
0x1400cecbc  mov     r12d, esi
0x1400cecbf  test    r15, r15
0x1400cecc2  jz      loc_1400CEDB2
0x1400cecc8  mov     rdx, rbx; Length
0x1400ceccb  mov     r8d, 1; Alignment
0x1400cecd1  mov     rcx, r15; Address
0x1400cecd4  call    cs:__imp_ProbeForRead
0x1400cecdb  nop     dword ptr [rax+rax+00h]
0x1400cece0  mov     qword ptr [rsp+68h+Irp], rsi; Irp
0x1400cece5  xor     r9d, r9d; ChargeQuota
0x1400cece8  xor     r8d, r8d; SecondaryBuffer
0x1400ceceb  mov     edx, ebx; Length
0x1400ceced  mov     rcx, r15; VirtualAddress
0x1400cecf0  call    cs:__imp_IoAllocateMdl
0x1400cecf7  nop     dword ptr [rax+rax+00h]
0x1400cecfc  mov     rdi, rax
0x1400cecff  mov     [rsp+68h+var_30], rax
0x1400ced04  test    rax, rax
0x1400ced07  jnz     short loc_1400CED17
0x1400ced09  mov     ebx, 0C000009Ah
0x1400ced0e  mov     [rsp+68h+var_38], ebx
0x1400ced12  jmp     loc_1400CEDDE
0x1400ced17  xor     r8d, r8d; Operation
0x1400ced1a  xor     edx, edx; AccessMode
0x1400ced1c  mov     rcx, rdi; MemoryDescriptorList
0x1400ced1f  call    cs:__imp_MmProbeAndLockPages
0x1400ced26  nop     dword ptr [rax+rax+00h]
0x1400ced2b  nop
0x1400ced2c  mov     r14b, 1
0x1400ced2f  mov     ecx, [rdi+20h]
0x1400ced32  add     ecx, [rdi+2Ch]
0x1400ced35  and     ecx, 0FFFh
0x1400ced3b  mov     eax, [rdi+28h]
0x1400ced3e  add     rcx, 0FFFh
0x1400ced45  add     rcx, rax
0x1400ced48  and     rcx, 0FFFFFFFFFFFFF000h
0x1400ced4f  cmp     rcx, 8000h
0x1400ced56  jbe     short loc_1400CED78
0x1400ced58  mov     ebx, 0C000000Dh
0x1400ced5d  mov     r8d, 15Ah
0x1400ced63  lea     rdx, aOnecoreVmVidSy_4; "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c"
0x1400ced6a  lea     rcx, aVsmmsvcpartiti_2; "VsmmSvcPartitionChangeLifeState"
0x1400ced71  call    VidTraceErrorInternal0
0x1400ced76  jmp     short loc_1400CEDDE
0x1400ced78  movzx   r9d, word ptr [rdi+2Ch]
0x1400ced7d  movzx   eax, word ptr [rdi+28h]
0x1400ced81  lea     r8, [rdi+30h]
0x1400ced85  jmp     short loc_1400CEDC3
0x1400ced87  mov     ebx, eax
0x1400ced89  mov     [rsp+68h+var_38], eax
0x1400ced8d  mov     r8d, 14Eh
0x1400ced93  lea     rdx, aOnecoreVmVidSy_4; "onecore\\vm\\vid\\sys\\vsmm\\vsmmsvc.c"
0x1400ced9a  lea     rcx, aVsmmsvcpartiti_2; "VsmmSvcPartitionChangeLifeState"
0x1400ceda1  call    VidTraceErrorInternal0
0x1400ceda6  xor     esi, esi
0x1400ceda8  mov     r14b, sil
0x1400cedab  mov     rdi, [rsp+68h+var_30]
0x1400cedb0  jmp     short loc_1400CEDDE
0x1400cedb2  test    r9d, r9d
0x1400cedb5  jnz     loc_1400CECAA
0x1400cedbb  mov     eax, esi
0x1400cedbd  mov     r8, rsi
0x1400cedc0  mov     r9d, esi
0x1400cedc3  mov     word ptr [rsp+68h+Irp], ax
0x1400cedc8  mov     edx, r12d
0x1400cedcb  mov     rcx, [r13+288h]
0x1400cedd2  call    VsmmSvcpCallChangePartitionState
0x1400cedd7  mov     ebx, eax
0x1400cedd9  test    eax, eax
0x1400ceddb  cmovns  ebx, esi
0x1400cedde  test    r14b, r14b
0x1400cede1  jz      short loc_1400CEDF2
0x1400cede3  mov     rcx, rdi; MemoryDescriptorList
0x1400cede6  call    cs:__imp_MmUnlockPages
0x1400ceded  nop     dword ptr [rax+rax+00h]
0x1400cedf2  test    rdi, rdi
0x1400cedf5  jz      short loc_1400CEE06
0x1400cedf7  mov     rcx, rdi; Mdl
0x1400cedfa  call    cs:__imp_IoFreeMdl
0x1400cee01  nop     dword ptr [rax+rax+00h]
0x1400cee06  mov     eax, ebx
0x1400cee08  lea     r11, [rsp+68h+var_28]
0x1400cee0d  mov     rbx, [r11+30h]
0x1400cee11  mov     rsi, [r11+40h]
0x1400cee15  mov     rsp, r11
0x1400cee18  pop     r15
0x1400cee1a  pop     r14
0x1400cee1c  pop     r13
0x1400cee1e  pop     r12
0x1400cee20  pop     rdi
0x1400cee21  retn
```
