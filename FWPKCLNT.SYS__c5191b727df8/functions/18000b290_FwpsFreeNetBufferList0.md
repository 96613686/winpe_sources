# FwpsFreeNetBufferList0

- ea: `0x18000b290`
- end: `0x18000b53c`
- name: `FwpsFreeNetBufferList0`
- size: `684`
- prototype: `void __stdcall(NET_BUFFER_LIST *netBufferList)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007530`
- `0x180007ec0`
- `0x180008480`
- `0x180008530`
- `0x18000b290`
- `0x180020400`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000b2cf`
- `ntoskrnl!MmBadPointer` at `0x18000b2e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b348`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b3b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b348`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b3b3`
- `NDIS!NdisFreeNetBufferList` at `0x18000b51f`
- `NDIS!NdisFreeNetBufferList` at `0x18000b51f`
- `NDIS!NdisFreeReassembledNetBufferList` at `0x18000b4dc`
- `NDIS!NdisFreeReassembledNetBufferList` at `0x18000b4dc`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18000b450`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18000b495`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18000b450`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18000b495`
- `NETIO!WfpNblInfoGet` at `0x18000b2bb`
- `NETIO!WfpNblInfoGet` at `0x18000b2bb`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b30f`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b36e`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b30f`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b36e`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x18000b4a7`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x18000b4a7`

## pseudocode

```c
void __stdcall FwpsFreeNetBufferList0(NET_BUFFER_LIST *netBufferList)
{
  _QWORD *v2; // rcx
  char *v3; // rax
  char *v4; // rbx
  PVOID v5; // rdx
  __int64 v6; // rax
  bool v7; // zf
  __int64 v8; // rsi
  char *v9; // rbp
  __int64 v10; // rcx
  PVOID Entry; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  if ( !netBufferList )
    return;
  Entry = 0;
  _InterlockedDecrement(&dword_180048700);
  v2 = (_QWORD *)WfpNblInfoGet(netBufferList);
  if ( !v2 || (v3 = (char *)MmBadPointer, v2 == MmBadPointer) )
  {
    v4 = (char *)MmBadPointer;
    if ( v2 != MmBadPointer )
    {
LABEL_27:
      NdisFreeNetBufferList(netBufferList);
      return;
    }
    v3 = (char *)MmBadPointer;
  }
  else
  {
    v4 = (char *)v2[1];
  }
  if ( !v4 || v4 == v3 )
    goto LABEL_27;
  if ( (WfpNblInfoGetFlags(netBufferList) & 1) != 0 )
  {
    if ( *((_DWORD *)v4 + 44) )
    {
      v5 = netBufferList->ProtocolReserved[3];
      Entry = v5;
      if ( v5 )
      {
        ExFreeToNPagedLookasideList(&stru_180048240, v5);
        Entry = (PVOID)0xBADBADFABADBADFALL;
      }
    }
  }
  else if ( (WfpNblInfoGetFlags(netBufferList) & 2) != 0 && _InterlockedAdd(&gFwpL2, 1u) >= 0 )
  {
    (*((void (__fastcall **)(NET_BUFFER_LIST *, _QWORD, PVOID *))qword_180048108 + 5))(netBufferList, 0, &Entry);
    if ( Entry )
    {
      ExFreeToNPagedLookasideList(&stru_180048140, Entry);
      Entry = (PVOID)0xBADBADFABADBADFALL;
    }
    (*((void (__fastcall **)(NET_BUFFER_LIST *))qword_180048108 + 1))(netBufferList);
    _InterlockedDecrement(&gFwpL2);
  }
  v6 = *((_QWORD *)v4 + 2);
  if ( !v6 )
  {
    FwppFreeWfpNblInfo(v4);
    FwppSetPacketInfo(netBufferList, 0);
    goto LABEL_27;
  }
  v7 = *((_DWORD *)v4 + 6) == 41;
  v8 = *(_QWORD *)(v6 + 8);
  v12 = 0;
  if ( v7 )
  {
    v9 = (char *)*((_QWORD *)v4 + 20);
    if ( !v9 )
      v9 = v4 + 32;
    NetioRetreatNetBuffer(v8, 8);
    RtlCopyKernelBufferToMdl(v9, *(_QWORD *)(v8 + 8), *(unsigned int *)(v8 + 16), *((unsigned int *)v4 + 42), &v12);
    if ( *((_QWORD *)v4 + 20) )
      WfpNamedPoolFree(v10, (PVOID *)v4 + 20);
  }
  else
  {
    RtlCopyKernelBufferToMdl(v4 + 32, *(_QWORD *)(v8 + 8), *(unsigned int *)(v8 + 16), 20, &v12);
  }
  NetioDereferenceNetBufferListChain(*((_QWORD *)v4 + 2), 0);
  *((_QWORD *)v4 + 2) = 0;
  FwppFreeWfpNblInfo(v4);
  FwppSetPacketInfo(netBufferList, 0);
  NdisFreeReassembledNetBufferList(netBufferList, 0, 0);
}

```

## disassembly

```asm
0x18000b290  test    rcx, rcx
0x18000b293  jz      locret_18000B53A
0x18000b299  push    rdi
0x18000b29a  sub     rsp, 50h
0x18000b29e  mov     [rsp+58h+Entry], 0
0x18000b2a7  mov     rdi, rcx
0x18000b2aa  lock dec cs:dword_180048700
0x18000b2b1  mov     [rsp+58h+arg_10], rbx
0x18000b2b6  mov     [rsp+58h+var_28], r15
0x18000b2bb  call    cs:__imp_WfpNblInfoGet
0x18000b2c2  nop     dword ptr [rax+rax+00h]
0x18000b2c7  mov     rcx, rax
0x18000b2ca  test    rax, rax
0x18000b2cd  jz      short loc_18000B2E4
0x18000b2cf  mov     rdx, cs:MmBadPointer
0x18000b2d6  mov     rax, [rdx]
0x18000b2d9  cmp     rcx, rax
0x18000b2dc  jz      short loc_18000B2E4
0x18000b2de  mov     rbx, [rcx+8]
0x18000b2e2  jmp     short loc_18000B2FA
0x18000b2e4  mov     rax, cs:MmBadPointer
0x18000b2eb  mov     rbx, [rax]
0x18000b2ee  cmp     rcx, rbx
0x18000b2f1  jnz     loc_18000B51C
0x18000b2f7  mov     rax, rbx
0x18000b2fa  test    rbx, rbx
0x18000b2fd  jz      loc_18000B51C
0x18000b303  cmp     rbx, rax
0x18000b306  jz      loc_18000B51C
0x18000b30c  mov     rcx, rdi
0x18000b30f  call    cs:__imp_WfpNblInfoGetFlags
0x18000b316  nop     dword ptr [rax+rax+00h]
0x18000b31b  test    al, 1
0x18000b31d  jz      short loc_18000B368
0x18000b31f  cmp     dword ptr [rbx+0B0h], 0
0x18000b326  mov     r15b, 1
0x18000b329  jz      loc_18000B3E8
0x18000b32f  mov     rdx, [rdi+58h]; Entry
0x18000b333  mov     [rsp+58h+Entry], rdx
0x18000b338  test    rdx, rdx
0x18000b33b  jz      loc_18000B3E8
0x18000b341  lea     rcx, stru_180048240; Lookaside
0x18000b348  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000b34f  nop     dword ptr [rax+rax+00h]
0x18000b354  mov     rax, 0BADBADFABADBADFAh
0x18000b35e  mov     [rsp+58h+Entry], rax
0x18000b363  jmp     loc_18000B3E8
0x18000b368  mov     rcx, rdi
0x18000b36b  xor     r15b, r15b
0x18000b36e  call    cs:__imp_WfpNblInfoGetFlags
0x18000b375  nop     dword ptr [rax+rax+00h]
0x18000b37a  test    al, 2
0x18000b37c  jz      short loc_18000B3E8
0x18000b37e  lock add cs:gFwpL2, 1
0x18000b386  js      short loc_18000B3E8
0x18000b388  mov     rax, cs:qword_180048108
0x18000b38f  lea     r8, [rsp+58h+Entry]
0x18000b394  xor     edx, edx
0x18000b396  mov     rcx, rdi
0x18000b399  mov     rax, [rax+28h]
0x18000b39d  call    _guard_dispatch_icall
0x18000b3a2  mov     rdx, [rsp+58h+Entry]; Entry
0x18000b3a7  test    rdx, rdx
0x18000b3aa  jz      short loc_18000B3CE
0x18000b3ac  lea     rcx, stru_180048140; Lookaside
0x18000b3b3  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000b3ba  nop     dword ptr [rax+rax+00h]
0x18000b3bf  mov     rax, 0BADBADFABADBADFAh
0x18000b3c9  mov     [rsp+58h+Entry], rax
0x18000b3ce  mov     rax, cs:qword_180048108
0x18000b3d5  mov     rcx, rdi
0x18000b3d8  mov     rax, [rax+8]
0x18000b3dc  call    _guard_dispatch_icall
0x18000b3e1  lock dec cs:gFwpL2
0x18000b3e8  mov     rax, [rbx+10h]
0x18000b3ec  test    rax, rax
0x18000b3ef  jz      loc_18000B503
0x18000b3f5  cmp     dword ptr [rbx+18h], 29h ; ')'
0x18000b3f9  mov     [rsp+58h+var_18], rsi
0x18000b3fe  mov     rsi, [rax+8]
0x18000b402  mov     [rsp+58h+arg_8], 0
0x18000b40b  mov     [rsp+58h+var_20], r14
0x18000b410  jnz     short loc_18000B479
0x18000b412  mov     [rsp+58h+var_10], rbp
0x18000b417  mov     rbp, [rbx+0A0h]
0x18000b41e  test    rbp, rbp
0x18000b421  jnz     short loc_18000B427
0x18000b423  lea     rbp, [rbx+20h]
0x18000b427  mov     edx, 8
0x18000b42c  mov     rcx, rsi
0x18000b42f  call    NetioRetreatNetBuffer
0x18000b434  mov     r9d, [rbx+0A8h]
0x18000b43b  lea     rax, [rsp+58h+arg_8]
0x18000b440  mov     r8d, [rsi+10h]
0x18000b444  mov     rcx, rbp
0x18000b447  mov     rdx, [rsi+8]
0x18000b44b  mov     [rsp+58h+var_38], rax
0x18000b450  call    cs:__imp_RtlCopyKernelBufferToMdl
0x18000b457  nop     dword ptr [rax+rax+00h]
0x18000b45c  cmp     qword ptr [rbx+0A0h], 0
0x18000b464  mov     rbp, [rsp+58h+var_10]
0x18000b469  jz      short loc_18000B4A1
0x18000b46b  lea     rdx, [rbx+0A0h]
0x18000b472  call    WfpNamedPoolFree
0x18000b477  jmp     short loc_18000B4A1
0x18000b479  mov     r8d, [rsi+10h]
0x18000b47d  lea     rax, [rsp+58h+arg_8]
0x18000b482  mov     rdx, [rsi+8]
0x18000b486  lea     rcx, [rbx+20h]
0x18000b48a  mov     r9d, 14h
0x18000b490  mov     [rsp+58h+var_38], rax
0x18000b495  call    cs:__imp_RtlCopyKernelBufferToMdl
0x18000b49c  nop     dword ptr [rax+rax+00h]
0x18000b4a1  mov     rcx, [rbx+10h]
0x18000b4a5  xor     edx, edx
0x18000b4a7  call    cs:__imp_NetioDereferenceNetBufferListChain
0x18000b4ae  nop     dword ptr [rax+rax+00h]
0x18000b4b3  mov     r8, rdi
0x18000b4b6  mov     qword ptr [rbx+10h], 0
0x18000b4be  movzx   edx, r15b
0x18000b4c2  mov     rcx, rbx; Entry
0x18000b4c5  call    FwppFreeWfpNblInfo
0x18000b4ca  xor     edx, edx
0x18000b4cc  mov     rcx, rdi
0x18000b4cf  call    FwppSetPacketInfo
0x18000b4d4  xor     r8d, r8d; FreeReassembleFlags
0x18000b4d7  xor     edx, edx; DataOffsetDelta
0x18000b4d9  mov     rcx, rdi; ReassembledNetBufferList
0x18000b4dc  call    cs:__imp_NdisFreeReassembledNetBufferList
0x18000b4e3  nop     dword ptr [rax+rax+00h]
0x18000b4e8  mov     r14, [rsp+58h+var_20]
0x18000b4ed  mov     rsi, [rsp+58h+var_18]
0x18000b4f2  mov     rbx, [rsp+58h+arg_10]
0x18000b4f7  mov     r15, [rsp+58h+var_28]
0x18000b4fc  add     rsp, 50h
0x18000b500  pop     rdi
0x18000b501  retn
0x18000b503  mov     r8, rdi
0x18000b506  movzx   edx, r15b
0x18000b50a  mov     rcx, rbx; Entry
0x18000b50d  call    FwppFreeWfpNblInfo
0x18000b512  xor     edx, edx
0x18000b514  mov     rcx, rdi
0x18000b517  call    FwppSetPacketInfo
0x18000b51c  mov     rcx, rdi; NetBufferList
0x18000b51f  call    cs:__imp_NdisFreeNetBufferList
0x18000b526  nop     dword ptr [rax+rax+00h]
0x18000b52b  mov     rbx, [rsp+58h+arg_10]
0x18000b530  mov     r15, [rsp+58h+var_28]
0x18000b535  add     rsp, 50h
0x18000b539  pop     rdi
0x18000b53a  retn
```
