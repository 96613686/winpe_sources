# FwppAllocateDeepNetioCloneNetBufferList

- ea: `0x18001ca04`
- end: `0x18001cbb0`
- name: `FwppAllocateDeepNetioCloneNetBufferList`
- size: `428`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009200`
- `0x18001cd70`
- `0x18001e740`

## callees

- `0x1800033e0`
- `0x180004904`
- `0x180004960`
- `0x180004a60`
- `0x180007ec0`
- `0x1800080f0`
- `0x180008150`
- `0x18001ca04`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18001ca4c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001cb12`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001cb12`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18001caf7`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18001caf7`
- `NETIO!NetioCopyNetBufferListInformation` at `0x18001caac`
- `NETIO!NetioCopyNetBufferListInformation` at `0x18001caac`
- `NETIO!WfpNblInfoClone` at `0x18001cac9`
- `NETIO!WfpNblInfoClone` at `0x18001cac9`

## pseudocode

```c
__int64 __fastcall FwppAllocateDeepNetioCloneNetBufferList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _NET_BUFFER_LIST **a4)
{
  _DWORD *v5; // rbx
  __int64 v7; // rax
  struct _NET_BUFFER_LIST *v8; // rsi
  unsigned int v9; // edi
  _QWORD *PacketInfo; // rax
  PVOID v11; // rcx
  _QWORD *v12; // r14
  int v13; // ebp
  const char *v14; // rdx
  int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rax
  _DWORD *v21; // rax
  _DWORD *SecurityContext; // rax
  __int64 v23; // rax
  PVOID Entry; // [rsp+30h] [rbp-48h] BYREF
  PNET_BUFFER_LIST CloneNetBufferList[8]; // [rsp+38h] [rbp-40h] BYREF

  CloneNetBufferList[0] = 0;
  v5 = 0;
  Entry = 0;
  v7 = FwppDeepCloneNetBufferList(a1, a2, a3, CloneNetBufferList);
  v8 = CloneNetBufferList[0];
  v9 = v7;
  if ( !v7 )
  {
    PacketInfo = (_QWORD *)FwppGetPacketInfo(a1);
    v11 = MmBadPointer;
    v12 = PacketInfo;
    if ( PacketInfo == MmBadPointer )
    {
      v13 = 0;
      v14 = "FwppAllocateDeepNetioCloneNetBufferList";
      v15 = -1073741801;
    }
    else
    {
      v16 = WfpAllocFromNPagedLookasideList(&gFwpNblInfo, &Entry);
      v5 = Entry;
      v9 = v16;
      if ( v16 )
        goto LABEL_10;
      memset(Entry, 0, 0x178u);
      v13 = 1;
      v5[1] = 1;
      v5[45] = 1;
      NetioCopyNetBufferListInformation(v8, a1);
      LOBYTE(v17) = 1;
      v18 = WfpNblInfoClone(a1, v8, 0, v17, 0);
      if ( !v18 )
      {
        if ( v12 )
        {
          v21 = (_DWORD *)v12[42];
          if ( v21 )
          {
            v5[86] = *v21;
            *((_QWORD *)v5 + 42) = v5 + 86;
          }
        }
        SecurityContext = (_DWORD *)IpSecGetSecurityContext(a1);
        if ( SecurityContext && !*((_QWORD *)v5 + 42) )
        {
          v5[86] = *SecurityContext;
          *((_QWORD *)v5 + 42) = v5 + 86;
        }
        v23 = FwppSetPacketInfo(v8, v5);
        v9 = v23;
        if ( !v23 )
        {
          *a4 = v8;
          _InterlockedAdd(&dword_180048700, 1u);
          return v9;
        }
LABEL_9:
        NetioCleanupNetBufferListInformation(v8);
LABEL_10:
        if ( v5 )
          ExFreeToNPagedLookasideList(&gFwpNblInfo, v5);
        goto LABEL_12;
      }
      v15 = v18;
      v14 = "WfpNblInfoClone";
    }
    v19 = WfpReportSysErrorAsNtStatus((__int64)v11, (int)v14, v15);
    v9 = v19;
    if ( !v19 )
      return v9;
    if ( !v13 )
      goto LABEL_10;
    goto LABEL_9;
  }
LABEL_12:
  if ( v8 )
    FwppFreeDeepCloneNetBufferList(v8);
  return v9;
}

```

## disassembly

```asm
0x18001ca04  push    rbx
0x18001ca06  push    rbp
0x18001ca07  push    rsi
0x18001ca08  push    rdi
0x18001ca09  push    r12
0x18001ca0b  push    r14
0x18001ca0d  push    r15
0x18001ca0f  sub     rsp, 40h
0x18001ca13  mov     r12, r9
0x18001ca16  mov     [rsp+78h+CloneNetBufferList], 0
0x18001ca1f  xor     ebx, ebx
0x18001ca21  lea     r9, [rsp+78h+CloneNetBufferList]
0x18001ca26  mov     [rsp+78h+Entry], rbx
0x18001ca2b  mov     r15, rcx
0x18001ca2e  call    FwppDeepCloneNetBufferList
0x18001ca33  mov     rsi, [rsp+78h+CloneNetBufferList]
0x18001ca38  mov     rdi, rax
0x18001ca3b  test    rax, rax
0x18001ca3e  jnz     loc_18001CB1E
0x18001ca44  mov     rcx, r15
0x18001ca47  call    FwppGetPacketInfo
0x18001ca4c  mov     rcx, cs:MmBadPointer
0x18001ca53  mov     r14, rax
0x18001ca56  cmp     rax, [rcx]
0x18001ca59  jnz     short loc_18001CA6C
0x18001ca5b  xor     ebp, ebp
0x18001ca5d  lea     rdx, aFwppallocatede; "FwppAllocateDeepNetioCloneNetBufferList"
0x18001ca64  mov     r8d, 0C0000017h
0x18001ca6a  jmp     short loc_18001CAE3
0x18001ca6c  lea     rdx, [rsp+78h+Entry]
0x18001ca71  lea     rcx, gFwpNblInfo
0x18001ca78  call    WfpAllocFromNPagedLookasideList
0x18001ca7d  mov     rbx, [rsp+78h+Entry]
0x18001ca82  mov     rdi, rax
0x18001ca85  test    rax, rax
0x18001ca88  jnz     short loc_18001CB03
0x18001ca8a  xor     edx, edx; Val
0x18001ca8c  mov     r8d, 178h; Size
0x18001ca92  mov     rcx, rbx; void *
0x18001ca95  call    memset
0x18001ca9a  lea     ebp, [rdi+1]
0x18001ca9d  mov     rdx, r15
0x18001caa0  mov     [rbx+4], ebp
0x18001caa3  mov     rcx, rsi
0x18001caa6  mov     [rbx+0B4h], ebp
0x18001caac  call    cs:__imp_NetioCopyNetBufferListInformation
0x18001cab3  nop     dword ptr [rax+rax+00h]
0x18001cab8  mov     r9b, bpl
0x18001cabb  mov     [rsp+78h+var_58], dil
0x18001cac0  xor     r8d, r8d
0x18001cac3  mov     rdx, rsi
0x18001cac6  mov     rcx, r15
0x18001cac9  call    cs:__imp_WfpNblInfoClone
0x18001cad0  nop     dword ptr [rax+rax+00h]
0x18001cad5  test    eax, eax
0x18001cad7  jz      short loc_18001CB3D
0x18001cad9  mov     r8d, eax
0x18001cadc  lea     rdx, aWfpnblinfoclon; "WfpNblInfoClone"
0x18001cae3  call    WfpReportSysErrorAsNtStatus
0x18001cae8  mov     rdi, rax
0x18001caeb  test    rax, rax
0x18001caee  jz      short loc_18001CB2B
0x18001caf0  test    ebp, ebp
0x18001caf2  jz      short loc_18001CB03
0x18001caf4  mov     rcx, rsi
0x18001caf7  call    cs:__imp_NetioCleanupNetBufferListInformation
0x18001cafe  nop     dword ptr [rax+rax+00h]
0x18001cb03  test    rbx, rbx
0x18001cb06  jz      short loc_18001CB1E
0x18001cb08  mov     rdx, rbx; Entry
0x18001cb0b  lea     rcx, gFwpNblInfo; Lookaside
0x18001cb12  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001cb19  nop     dword ptr [rax+rax+00h]
0x18001cb1e  test    rsi, rsi
0x18001cb21  jz      short loc_18001CB2B
0x18001cb23  mov     rcx, rsi; CloneNetBufferList
0x18001cb26  call    FwppFreeDeepCloneNetBufferList
0x18001cb2b  mov     eax, edi
0x18001cb2d  add     rsp, 40h
0x18001cb31  pop     r15
0x18001cb33  pop     r14
0x18001cb35  pop     r12
0x18001cb37  pop     rdi
0x18001cb38  pop     rsi
0x18001cb39  pop     rbp
0x18001cb3a  pop     rbx
0x18001cb3b  retn
0x18001cb3d  test    r14, r14
0x18001cb40  jz      short loc_18001CB60
0x18001cb42  mov     rax, [r14+150h]
0x18001cb49  test    rax, rax
0x18001cb4c  jz      short loc_18001CB60
0x18001cb4e  mov     eax, [rax]
0x18001cb50  lea     rcx, [rbx+158h]
0x18001cb57  mov     [rcx], eax
0x18001cb59  mov     [rbx+150h], rcx
0x18001cb60  mov     rcx, r15
0x18001cb63  call    IpSecGetSecurityContext
0x18001cb68  test    rax, rax
0x18001cb6b  jz      short loc_18001CB89
0x18001cb6d  cmp     qword ptr [rbx+150h], 0
0x18001cb75  jnz     short loc_18001CB89
0x18001cb77  mov     eax, [rax]
0x18001cb79  lea     rcx, [rbx+158h]
0x18001cb80  mov     [rcx], eax
0x18001cb82  mov     [rbx+150h], rcx
0x18001cb89  mov     rdx, rbx
0x18001cb8c  mov     rcx, rsi
0x18001cb8f  call    FwppSetPacketInfo
0x18001cb94  mov     rdi, rax
0x18001cb97  test    rax, rax
0x18001cb9a  jnz     loc_18001CAF4
0x18001cba0  mov     [r12], rsi
0x18001cba4  lock add cs:dword_180048700, ebp
0x18001cbab  jmp     loc_18001CB2B
```
