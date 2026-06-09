# FwppAllocateDeepL2CloneNetBufferList

- ea: `0x18001c88c`
- end: `0x18001c9fb`
- name: `FwppAllocateDeepL2CloneNetBufferList`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180009200`
- `0x18001cd70`

## callees

- `0x1800033e0`
- `0x180004904`
- `0x180004960`
- `0x180007ec0`
- `0x1800080f0`
- `0x18001c88c`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001c999`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001c999`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18001c97e`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18001c97e`
- `NETIO!NetioCopyNetBufferListInformation` at `0x18001c937`
- `NETIO!NetioCopyNetBufferListInformation` at `0x18001c937`
- `NETIO!WfpNblInfoClone` at `0x18001c954`
- `NETIO!WfpNblInfoClone` at `0x18001c954`

## pseudocode

```c
__int64 __fastcall FwppAllocateDeepL2CloneNetBufferList(__int64 a1, __int64 a2, __int64 a3, PNET_BUFFER_LIST *a4)
{
  __int64 v6; // rax
  PNET_BUFFER_LIST v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // rax
  _DWORD *v10; // rsi
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v16; // rax
  PNET_BUFFER_LIST CloneNetBufferList; // [rsp+30h] [rbp-38h] BYREF
  PVOID Entry[6]; // [rsp+38h] [rbp-30h] BYREF

  CloneNetBufferList = 0;
  Entry[0] = 0;
  v6 = FwppDeepCloneNetBufferList(a1, a2, a3, &CloneNetBufferList);
  v7 = CloneNetBufferList;
  v8 = v6;
  if ( !v6 )
  {
    v9 = WfpAllocFromNPagedLookasideList(&gFwpNblInfo, Entry);
    v10 = Entry[0];
    v8 = v9;
    if ( !v9 )
    {
      memset(Entry[0], 0, 0x178u);
      v10[1] = 1;
      v10[45] = 1;
      if ( _InterlockedAdd(&gFwpL2, 1u) >= 0 )
      {
        (*((void (__fastcall **)(__int64))qword_180048108 + 2))(a1);
        _InterlockedDecrement(&gFwpL2);
      }
      NetioCopyNetBufferListInformation(v7, a1);
      LOBYTE(v11) = 1;
      v12 = WfpNblInfoClone(a1, v7, 0, v11, 0);
      if ( v12 )
      {
        v14 = WfpReportSysErrorAsNtStatus(v13, (int)"WfpNblInfoClone", v12);
        v8 = v14;
        if ( !v14 )
          return v8;
      }
      else
      {
        v16 = FwppSetPacketInfo(v7, v10);
        v8 = v16;
        if ( !v16 )
        {
          v7->NetBufferListInfo[14] = *(PVOID *)(a1 + 256);
          v7->NetBufferListInfo[6] = *(PVOID *)(a1 + 192);
          *a4 = v7;
          _InterlockedIncrement(&dword_180048700);
          return v8;
        }
      }
      NetioCleanupNetBufferListInformation(v7);
    }
    if ( v10 )
      ExFreeToNPagedLookasideList(&gFwpNblInfo, v10);
  }
  if ( v7 )
    FwppFreeDeepCloneNetBufferList(v7);
  return v8;
}

```

## disassembly

```asm
0x18001c88c  push    rbx
0x18001c88e  push    rbp
0x18001c88f  push    rsi
0x18001c890  push    rdi
0x18001c891  push    r14
0x18001c893  sub     rsp, 40h
0x18001c897  mov     r14, r9
0x18001c89a  mov     [rsp+68h+CloneNetBufferList], 0
0x18001c8a3  lea     r9, [rsp+68h+CloneNetBufferList]
0x18001c8a8  mov     [rsp+68h+Entry], 0
0x18001c8b1  mov     rbp, rcx
0x18001c8b4  call    FwppDeepCloneNetBufferList
0x18001c8b9  mov     rbx, [rsp+68h+CloneNetBufferList]
0x18001c8be  mov     rdi, rax
0x18001c8c1  test    rax, rax
0x18001c8c4  jnz     loc_18001C9A5
0x18001c8ca  lea     rdx, [rsp+68h+Entry]
0x18001c8cf  lea     rcx, gFwpNblInfo
0x18001c8d6  call    WfpAllocFromNPagedLookasideList
0x18001c8db  mov     rsi, [rsp+68h+Entry]
0x18001c8e0  mov     rdi, rax
0x18001c8e3  test    rax, rax
0x18001c8e6  jnz     loc_18001C98A
0x18001c8ec  xor     edx, edx; Val
0x18001c8ee  mov     r8d, 178h; Size
0x18001c8f4  mov     rcx, rsi; void *
0x18001c8f7  call    memset
0x18001c8fc  mov     dword ptr [rsi+4], 1
0x18001c903  mov     dword ptr [rsi+0B4h], 1
0x18001c90d  lock add cs:gFwpL2, 1
0x18001c915  js      short loc_18001C931
0x18001c917  mov     rax, cs:qword_180048108
0x18001c91e  mov     rcx, rbp
0x18001c921  mov     rax, [rax+10h]
0x18001c925  call    _guard_dispatch_icall
0x18001c92a  lock dec cs:gFwpL2
0x18001c931  mov     rdx, rbp
0x18001c934  mov     rcx, rbx
0x18001c937  call    cs:__imp_NetioCopyNetBufferListInformation
0x18001c93e  nop     dword ptr [rax+rax+00h]
0x18001c943  mov     r9b, 1
0x18001c946  mov     [rsp+68h+var_48], 0
0x18001c94b  xor     r8d, r8d
0x18001c94e  mov     rdx, rbx
0x18001c951  mov     rcx, rbp
0x18001c954  call    cs:__imp_WfpNblInfoClone
0x18001c95b  nop     dword ptr [rax+rax+00h]
0x18001c960  test    eax, eax
0x18001c962  jz      short loc_18001C9C0
0x18001c964  mov     r8d, eax
0x18001c967  lea     rdx, aWfpnblinfoclon; "WfpNblInfoClone"
0x18001c96e  call    WfpReportSysErrorAsNtStatus
0x18001c973  mov     rdi, rax
0x18001c976  test    rax, rax
0x18001c979  jz      short loc_18001C9B2
0x18001c97b  mov     rcx, rbx
0x18001c97e  call    cs:__imp_NetioCleanupNetBufferListInformation
0x18001c985  nop     dword ptr [rax+rax+00h]
0x18001c98a  test    rsi, rsi
0x18001c98d  jz      short loc_18001C9A5
0x18001c98f  mov     rdx, rsi; Entry
0x18001c992  lea     rcx, gFwpNblInfo; Lookaside
0x18001c999  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001c9a0  nop     dword ptr [rax+rax+00h]
0x18001c9a5  test    rbx, rbx
0x18001c9a8  jz      short loc_18001C9B2
0x18001c9aa  mov     rcx, rbx; CloneNetBufferList
0x18001c9ad  call    FwppFreeDeepCloneNetBufferList
0x18001c9b2  mov     eax, edi
0x18001c9b4  add     rsp, 40h
0x18001c9b8  pop     r14
0x18001c9ba  pop     rdi
0x18001c9bb  pop     rsi
0x18001c9bc  pop     rbp
0x18001c9bd  pop     rbx
0x18001c9be  retn
0x18001c9c0  mov     rdx, rsi
0x18001c9c3  mov     rcx, rbx
0x18001c9c6  call    FwppSetPacketInfo
0x18001c9cb  mov     rdi, rax
0x18001c9ce  test    rax, rax
0x18001c9d1  jnz     short loc_18001C97B
0x18001c9d3  mov     rax, [rbp+100h]
0x18001c9da  mov     [rbx+100h], rax
0x18001c9e1  mov     rax, [rbp+0C0h]
0x18001c9e8  mov     [rbx+0C0h], rax
0x18001c9ef  mov     [r14], rbx
0x18001c9f2  lock inc cs:dword_180048700
0x18001c9f9  jmp     short loc_18001C9B2
```
