# FwppDeepCloneNetBufferList

- ea: `0x1800033e0`
- end: `0x1800036a3`
- name: `FwppDeepCloneNetBufferList`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c88c`
- `0x18001ca04`

## callees

- `0x1800033e0`
- `0x180004904`
- `0x180004960`
- `0x18000c9b4`
- `0x18000de60`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000360d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000360d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1800035c3`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1800035c3`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180003402`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180003402`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x180003501`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x180003501`
- `NETIO!NetioAllocateMdl` at `0x18000347d`
- `NETIO!NetioAllocateMdl` at `0x18000347d`
- `NETIO!NetioAllocateMdl` at `0x1800035b3`

## pseudocode

```c
__int64 __fastcall FwppDeepCloneNetBufferList(
        struct _NET_BUFFER_LIST *a1,
        void *a2,
        void *a3,
        struct _NET_BUFFER_LIST **a4)
{
  PNET_BUFFER_LIST CloneNetBufferList; // rax
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // r8
  struct _NET_BUFFER_LIST *v8; // rbp
  struct _NET_BUFFER *FirstNetBuffer; // rbx
  int v10; // r15d
  __int64 DataLength; // r14
  __int64 DataOffset; // r12
  PMDL v13; // rax
  __int64 v14; // r8
  ULONG v15; // edx
  ULONG v16; // eax
  PMDL CurrentMdl; // rcx
  char *MappedSystemVa; // rax
  __int64 v19; // rdi
  __int64 v21; // rax
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-78h]
  ULONG v23; // [rsp+30h] [rbp-68h] BYREF
  __int64 v24; // [rsp+38h] [rbp-60h] BYREF
  PMDL MdlChain; // [rsp+40h] [rbp-58h]

  v23 = 0;
  CloneNetBufferList = NdisAllocateCloneNetBufferList(a1, a2, a3, 2u);
  v8 = CloneNetBufferList;
  if ( !CloneNetBufferList )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
    {
      WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v7, "NdisAllocateCloneNetBufferList", -1073741801);
    }
    v19 = -1073741801;
    goto LABEL_20;
  }
  FirstNetBuffer = CloneNetBufferList->FirstNetBuffer;
  v10 = 0;
  if ( !FirstNetBuffer )
    goto LABEL_15;
  do
  {
    DataLength = FirstNetBuffer->DataLength;
    DataOffset = FirstNetBuffer->DataOffset;
    MdlChain = FirstNetBuffer->MdlChain;
    v24 = 0;
    FirstNetBuffer->MdlChain = 0;
    FirstNetBuffer->Link.Region = 0;
    FirstNetBuffer->CurrentMdlOffset = 0;
    if ( (unsigned int)DataOffset > ~(_DWORD)DataLength )
    {
      v21 = WfpReportSysErrorAsNtStatus((__int64)v6, (int)"WfpUINT32Add", -1073741675);
      if ( v21 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
        {
          BugCheckOnFailure[0] = v21;
          WPP_SF_sd(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0xFu,
            v14,
            "WfpUINT32Add",
            *(_QWORD *)BugCheckOnFailure);
        }
LABEL_12:
        v10 = 1;
        goto LABEL_13;
      }
    }
    else
    {
      v23 = DataLength + DataOffset;
    }
    v13 = NetioAllocateMdl(&v23);
    FirstNetBuffer->MdlChain = v13;
    v6 = (PDEVICE_OBJECT)v13;
    if ( !v13 )
      goto LABEL_12;
    FirstNetBuffer->DataOffset = v23;
    v15 = v23;
    FirstNetBuffer->DataLength = 0;
    FirstNetBuffer->Link.Region = (ULONGLONG)v13;
    FirstNetBuffer->CurrentMdlOffset = v23;
    v16 = v23;
    if ( v23 < (unsigned int)DataLength )
    {
      NdisRetreatNetBufferDataStart(FirstNetBuffer, DataLength, 0, NetioAllocateMdl);
    }
    else
    {
      FirstNetBuffer->DataLength = DataLength;
      FirstNetBuffer->CurrentMdlOffset = v16 - DataLength;
      FirstNetBuffer->DataOffset = v15 - DataLength;
    }
    CurrentMdl = FirstNetBuffer->CurrentMdl;
    if ( (CurrentMdl->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u);
    RtlCopyMdlToKernelBuffer(MdlChain, DataOffset, &MappedSystemVa[FirstNetBuffer->CurrentMdlOffset], DataLength, &v24);
LABEL_13:
    FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
  }
  while ( FirstNetBuffer );
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
    {
      BugCheckOnFailure[0] = -1073741801;
      WPP_SF_sd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        v14,
        "NdisAllocateCloneNetBufferList",
        *(_QWORD *)BugCheckOnFailure);
    }
    v19 = -1073741801;
    FwppFreeDeepCloneNetBufferList(v8);
LABEL_20:
    WfpReportError(-1073741801, (int)"FwppDeepCloneNetBufferList");
    return v19;
  }
LABEL_15:
  v19 = 0;
  *a4 = v8;
  return v19;
}

```

## disassembly

```asm
0x1800033e0  push    rbx
0x1800033e2  push    rbp
0x1800033e3  push    rsi
0x1800033e4  push    rdi
0x1800033e5  push    r12
0x1800033e7  push    r13
0x1800033e9  push    r14
0x1800033eb  push    r15
0x1800033ed  sub     rsp, 58h
0x1800033f1  mov     r13, r9
0x1800033f4  mov     [rsp+98h+var_68], 0
0x1800033fc  mov     r9d, 2; AllocateCloneFlags
0x180003402  call    cs:__imp_NdisAllocateCloneNetBufferList
0x180003409  nop     dword ptr [rax+rax+00h]
0x18000340e  mov     rbp, rax
0x180003411  test    rax, rax
0x180003414  jz      loc_18000358A
0x18000341a  mov     rbx, [rax+8]
0x18000341e  xor     r15d, r15d
0x180003421  test    rbx, rbx
0x180003424  jz      loc_180003536
0x18000342a  lea     rsi, WPP_GLOBAL_Control
0x180003431  mov     rax, [rbx+20h]
0x180003435  mov     r14d, [rbx+18h]
0x180003439  mov     r12d, [rbx+28h]
0x18000343d  mov     [rsp+98h+var_58], rax
0x180003442  mov     eax, r14d
0x180003445  not     eax
0x180003447  mov     [rsp+98h+var_60], 0
0x180003450  mov     qword ptr [rbx+20h], 0
0x180003458  mov     qword ptr [rbx+8], 0
0x180003460  mov     dword ptr [rbx+10h], 0
0x180003467  cmp     r12d, eax
0x18000346a  ja      loc_1800035D4
0x180003470  lea     eax, [r14+r12]
0x180003474  mov     [rsp+98h+var_68], eax
0x180003478  lea     rcx, [rsp+98h+var_68]
0x18000347d  call    cs:__imp_NetioAllocateMdl
0x180003484  nop     dword ptr [rax+rax+00h]
0x180003489  mov     [rbx+20h], rax
0x18000348d  mov     rcx, rax
0x180003490  test    rax, rax
0x180003493  jz      loc_18000351F
0x180003499  mov     eax, [rsp+98h+var_68]
0x18000349d  mov     [rbx+28h], eax
0x1800034a0  mov     edx, [rsp+98h+var_68]
0x1800034a4  mov     dword ptr [rbx+18h], 0
0x1800034ab  mov     [rbx+8], rcx
0x1800034af  mov     eax, [rsp+98h+var_68]
0x1800034b3  mov     [rbx+10h], eax
0x1800034b6  mov     eax, [rsp+98h+var_68]
0x1800034ba  cmp     eax, r14d
0x1800034bd  jb      loc_1800035B3
0x1800034c3  sub     eax, r14d
0x1800034c6  mov     [rbx+18h], r14d
0x1800034ca  sub     edx, r14d
0x1800034cd  mov     [rbx+10h], eax
0x1800034d0  mov     [rbx+28h], edx
0x1800034d3  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1800034d7  test    byte ptr [rcx+0Ah], 5
0x1800034db  jz      loc_1800035F4
0x1800034e1  mov     rax, [rcx+18h]
0x1800034e5  mov     r8d, [rbx+10h]
0x1800034e9  mov     r9, r14
0x1800034ec  mov     rcx, [rsp+98h+var_58]
0x1800034f1  add     r8, rax
0x1800034f4  lea     rax, [rsp+98h+var_60]
0x1800034f9  mov     rdx, r12
0x1800034fc  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x180003501  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x180003508  nop     dword ptr [rax+rax+00h]
0x18000350d  jmp     short loc_180003525
0x18000350f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003516  cmp     rcx, rsi
0x180003519  jnz     loc_180003670
0x18000351f  mov     r15d, 1
0x180003525  mov     rbx, [rbx]
0x180003528  test    rbx, rbx
0x18000352b  jnz     loc_180003431
0x180003531  test    r15d, r15d
0x180003534  jnz     short loc_180003551
0x180003536  xor     edi, edi
0x180003538  mov     [r13+0], rbp
0x18000353c  mov     rax, rdi
0x18000353f  add     rsp, 58h
0x180003543  pop     r15
0x180003545  pop     r14
0x180003547  pop     r13
0x180003549  pop     r12
0x18000354b  pop     rdi
0x18000354c  pop     rsi
0x18000354d  pop     rbp
0x18000354e  pop     rbx
0x18000354f  retn
0x180003551  mov     rcx, cs:WPP_GLOBAL_Control
0x180003558  mov     rbx, 0FFFFFFFFC0000017h
0x18000355f  cmp     rcx, rsi
0x180003562  jz      short loc_18000356E
0x180003564  cmp     byte ptr [rcx+29h], 2
0x180003568  jnb     loc_18000361E
0x18000356e  mov     rcx, rbp; CloneNetBufferList
0x180003571  mov     rdi, rbx
0x180003574  call    FwppFreeDeepCloneNetBufferList
0x180003579  lea     rdx, aFwppdeepclonen; "FwppDeepCloneNetBufferList"
0x180003580  mov     rcx, rbx
0x180003583  call    WfpReportError
0x180003588  jmp     short loc_18000353C
0x18000358a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003591  lea     rsi, WPP_GLOBAL_Control
0x180003598  mov     rbx, 0FFFFFFFFC0000017h
0x18000359f  cmp     rcx, rsi
0x1800035a2  jz      short loc_1800035AE
0x1800035a4  cmp     byte ptr [rcx+29h], 2
0x1800035a8  jnb     loc_180003647
0x1800035ae  mov     rdi, rbx
0x1800035b1  jmp     short loc_180003579
0x1800035b3  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x1800035ba  xor     r8d, r8d; DataBackFill
0x1800035bd  mov     edx, r14d; DataOffsetDelta
0x1800035c0  mov     rcx, rbx; NetBuffer
0x1800035c3  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1800035ca  nop     dword ptr [rax+rax+00h]
0x1800035cf  jmp     loc_1800034D3
0x1800035d4  mov     r8d, 0C0000095h
0x1800035da  lea     rdx, aWfpuint32add; "WfpUINT32Add"
0x1800035e1  call    WfpReportSysErrorAsNtStatus
0x1800035e6  test    rax, rax
0x1800035e9  jz      loc_180003478
0x1800035ef  jmp     loc_18000350F
0x1800035f4  xor     r9d, r9d; RequestedAddress
0x1800035f7  mov     [rsp+98h+Priority], 40000000h; Priority
0x1800035ff  xor     edx, edx; AccessMode
0x180003601  mov     [rsp+98h+BugCheckOnFailure], 0; BugCheckOnFailure
0x180003609  lea     r8d, [r9+1]; CacheType
0x18000360d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180003614  nop     dword ptr [rax+rax+00h]
0x180003619  jmp     loc_1800034E5
0x18000361e  bt      dword ptr [rcx+2Ch], 0Ch
0x180003623  jnb     loc_18000356E
0x180003629  mov     rcx, [rcx+18h]
0x18000362d  lea     r9, aNdisallocatecl; "NdisAllocateCloneNetBufferList"
0x180003634  mov     edx, 0Ah
0x180003639  mov     [rsp+98h+BugCheckOnFailure], ebx
0x18000363d  call    WPP_SF_sd
0x180003642  jmp     loc_18000356E
0x180003647  bt      dword ptr [rcx+2Ch], 0Ch
0x18000364c  jnb     loc_1800035AE
0x180003652  mov     rcx, [rcx+18h]
0x180003656  lea     r9, aNdisallocatecl; "NdisAllocateCloneNetBufferList"
0x18000365d  mov     edx, 0Ah
0x180003662  mov     [rsp+98h+BugCheckOnFailure], ebx
0x180003666  call    WPP_SF_sd
0x18000366b  jmp     loc_1800035AE
0x180003670  cmp     byte ptr [rcx+29h], 2
0x180003674  jb      loc_18000351F
0x18000367a  bt      dword ptr [rcx+2Ch], 0Ch
0x18000367f  jnb     loc_18000351F
0x180003685  mov     rcx, [rcx+18h]
0x180003689  lea     r9, aWfpuint32add; "WfpUINT32Add"
0x180003690  mov     edx, 0Fh
0x180003695  mov     [rsp+98h+BugCheckOnFailure], eax
0x180003699  call    WPP_SF_sd
0x18000369e  jmp     loc_18000351F
```
