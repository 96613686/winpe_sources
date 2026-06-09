# FwppAllocateL2CloneNetBufferList

- ea: `0x180007ce4`
- end: `0x180007eb6`
- name: `FwppAllocateL2CloneNetBufferList`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180009200`

## callees

- `0x180004904`
- `0x180007ce4`
- `0x180007ec0`
- `0x18000c9b4`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007ddb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007ddb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180007d16`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180007d16`
- `NDIS!NdisFreeCloneNetBufferList` at `0x180007df2`
- `NDIS!NdisFreeCloneNetBufferList` at `0x180007df2`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180007cf7`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180007cf7`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x180007dc0`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x180007dc0`
- `NETIO!NetioCopyNetBufferListInformation` at `0x180007d75`
- `NETIO!NetioCopyNetBufferListInformation` at `0x180007d75`
- `NETIO!WfpNblInfoClone` at `0x180007d92`
- `NETIO!WfpNblInfoClone` at `0x180007d92`

## string_xrefs

- `0x180007e37`: `ExAllocateFromNPagedLookasideList`
- `0x180007e4f`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppAllocateL2CloneNetBufferList(
        struct _NET_BUFFER_LIST *a1,
        void *a2,
        void *a3,
        ULONG a4,
        PNET_BUFFER_LIST *a5)
{
  __int64 v7; // rcx
  PNET_BUFFER_LIST CloneNetBufferList; // rbx
  __int64 v9; // rcx
  _DWORD *v10; // r14
  int v11; // esi
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // edi
  __int64 v16; // rax
  const char *v18; // rdx
  int v19; // r8d
  __int64 v20; // rax
  PVOID v21; // rax

  CloneNetBufferList = NdisAllocateCloneNetBufferList(a1, a2, a3, a4);
  if ( CloneNetBufferList )
  {
    v10 = ExAllocateFromNPagedLookasideList(&gFwpNblInfo);
    if ( !v10 )
    {
      v20 = WfpReportSysErrorAsNtStatus(v9, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
      v15 = v20;
      if ( v20 )
      {
        WfpReportError(v20, (int)"WfpAllocFromNPagedLookasideList");
LABEL_11:
        NdisFreeCloneNetBufferList(CloneNetBufferList, a4);
        return v15;
      }
    }
    memset(v10, 0, 0x178u);
    v11 = 1;
    v10[1] = 1;
    if ( _InterlockedIncrement(&gFwpL2) >= 0 )
    {
      (*((void (__fastcall **)(struct _NET_BUFFER_LIST *))qword_180048108 + 2))(a1);
      _InterlockedDecrement(&gFwpL2);
    }
    NetioCopyNetBufferListInformation(CloneNetBufferList, a1);
    LOBYTE(v12) = 1;
    v13 = WfpNblInfoClone(a1, CloneNetBufferList, 0, v12, 0);
    if ( !v13 )
    {
      v14 = FwppSetPacketInfo(CloneNetBufferList, v10);
      v15 = v14;
      if ( !v14 )
      {
        CloneNetBufferList->ParentNetBufferList = a1;
        v21 = a1->NetBufferListInfo[14];
        ++a1->ChildRefCount;
        CloneNetBufferList->NetBufferListInfo[14] = v21;
        CloneNetBufferList->NetBufferListInfo[6] = a1->NetBufferListInfo[6];
        *a5 = CloneNetBufferList;
        _InterlockedAdd(&dword_180048700, 1u);
        return v15;
      }
LABEL_7:
      NetioCleanupNetBufferListInformation(CloneNetBufferList);
      goto LABEL_8;
    }
    v19 = v13;
    v18 = "WfpNblInfoClone";
  }
  else
  {
    v10 = 0;
    v18 = "NdisAllocateCloneNetBufferList";
    v11 = 0;
    v19 = -1073741801;
  }
  v16 = WfpReportSysErrorAsNtStatus(v7, (int)v18, v19);
  v15 = v16;
  if ( !v16 )
    return v15;
  if ( v11 )
    goto LABEL_7;
LABEL_8:
  if ( v10 )
    ExFreeToNPagedLookasideList(&gFwpNblInfo, v10);
  if ( CloneNetBufferList )
    goto LABEL_11;
  return v15;
}

```

## disassembly

```asm
0x180007ce4  push    rbx
0x180007ce6  push    rbp
0x180007ce7  push    rsi
0x180007ce8  push    rdi
0x180007ce9  push    r14
0x180007ceb  push    r15
0x180007ced  sub     rsp, 38h
0x180007cf1  mov     r15d, r9d
0x180007cf4  mov     rbp, rcx
0x180007cf7  call    cs:__imp_NdisAllocateCloneNetBufferList
0x180007cfe  nop     dword ptr [rax+rax+00h]
0x180007d03  mov     rbx, rax
0x180007d06  test    rax, rax
0x180007d09  jz      loc_180007E1D
0x180007d0f  lea     rcx, gFwpNblInfo; Lookaside
0x180007d16  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180007d1d  nop     dword ptr [rax+rax+00h]
0x180007d22  mov     r14, rax
0x180007d25  test    rax, rax
0x180007d28  jz      loc_180007E31
0x180007d2e  xor     edx, edx; Val
0x180007d30  mov     r8d, 178h; Size
0x180007d36  mov     rcx, r14; void *
0x180007d39  call    memset
0x180007d3e  mov     esi, 1
0x180007d43  mov     [r14+4], esi
0x180007d47  mov     eax, esi
0x180007d49  lock xadd cs:gFwpL2, eax
0x180007d51  add     eax, esi
0x180007d53  js      short loc_180007D6F
0x180007d55  mov     rax, cs:qword_180048108
0x180007d5c  mov     rcx, rbp
0x180007d5f  mov     rax, [rax+10h]
0x180007d63  call    _guard_dispatch_icall
0x180007d68  lock dec cs:gFwpL2
0x180007d6f  mov     rdx, rbp
0x180007d72  mov     rcx, rbx
0x180007d75  call    cs:__imp_NetioCopyNetBufferListInformation
0x180007d7c  nop     dword ptr [rax+rax+00h]
0x180007d81  mov     r9b, sil
0x180007d84  mov     [rsp+68h+var_48], 0
0x180007d89  xor     r8d, r8d
0x180007d8c  mov     rdx, rbx
0x180007d8f  mov     rcx, rbp
0x180007d92  call    cs:__imp_WfpNblInfoClone
0x180007d99  nop     dword ptr [rax+rax+00h]
0x180007d9e  test    eax, eax
0x180007da0  jnz     loc_180007E60
0x180007da6  mov     rdx, r14
0x180007da9  mov     rcx, rbx
0x180007dac  call    FwppSetPacketInfo
0x180007db1  mov     rdi, rax
0x180007db4  test    rax, rax
0x180007db7  jz      loc_180007E79
0x180007dbd  mov     rcx, rbx
0x180007dc0  call    cs:__imp_NetioCleanupNetBufferListInformation
0x180007dc7  nop     dword ptr [rax+rax+00h]
0x180007dcc  test    r14, r14
0x180007dcf  jz      short loc_180007DE7
0x180007dd1  mov     rdx, r14; Entry
0x180007dd4  lea     rcx, gFwpNblInfo; Lookaside
0x180007ddb  call    cs:__imp_ExFreeToNPagedLookasideList
0x180007de2  nop     dword ptr [rax+rax+00h]
0x180007de7  test    rbx, rbx
0x180007dea  jz      short loc_180007E0D
0x180007dec  mov     edx, r15d; FreeCloneFlags
0x180007def  mov     rcx, rbx; CloneNetBufferList
0x180007df2  call    cs:__imp_NdisFreeCloneNetBufferList
0x180007df9  nop     dword ptr [rax+rax+00h]
0x180007dfe  jmp     short loc_180007E0D
0x180007e00  call    WfpReportSysErrorAsNtStatus
0x180007e05  mov     rdi, rax
0x180007e08  test    rax, rax
0x180007e0b  jnz     short loc_180007E6C
0x180007e0d  mov     eax, edi
0x180007e0f  add     rsp, 38h
0x180007e13  pop     r15
0x180007e15  pop     r14
0x180007e17  pop     rdi
0x180007e18  pop     rsi
0x180007e19  pop     rbp
0x180007e1a  pop     rbx
0x180007e1b  retn
0x180007e1d  xor     r14d, r14d
0x180007e20  lea     rdx, aNdisallocatecl; "NdisAllocateCloneNetBufferList"
0x180007e27  xor     esi, esi
0x180007e29  mov     r8d, 0C0000017h
0x180007e2f  jmp     short loc_180007E00
0x180007e31  mov     r8d, 0C0000017h
0x180007e37  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180007e3e  call    WfpReportSysErrorAsNtStatus
0x180007e43  mov     rdi, rax
0x180007e46  test    rax, rax
0x180007e49  jz      loc_180007D2E
0x180007e4f  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180007e56  mov     rcx, rax
0x180007e59  call    WfpReportError
0x180007e5e  jmp     short loc_180007DEC
0x180007e60  mov     r8d, eax
0x180007e63  lea     rdx, aWfpnblinfoclon; "WfpNblInfoClone"
0x180007e6a  jmp     short loc_180007E00
0x180007e6c  test    esi, esi
0x180007e6e  jz      loc_180007DCC
0x180007e74  jmp     loc_180007DBD
0x180007e79  mov     [rbx+18h], rbp
0x180007e7d  mov     rax, [rbp+100h]
0x180007e84  add     [rbp+84h], esi
0x180007e8a  mov     [rbx+100h], rax
0x180007e91  mov     rax, [rbp+0C0h]
0x180007e98  mov     [rbx+0C0h], rax
0x180007e9f  mov     rax, [rsp+68h+arg_20]
0x180007ea7  mov     [rax], rbx
0x180007eaa  lock add cs:dword_180048700, esi
0x180007eb1  jmp     loc_180007E0D
```
