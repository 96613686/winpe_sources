# NetioAllocateAndReferenceVacantNetBufferListEx

- ea: `0x14003c940`
- end: `0x14003cb56`
- name: `NetioAllocateAndReferenceVacantNetBufferListEx`
- size: `534`
- prototype: `ULONG_PTR __fastcall(ULONG_PTR BugCheckParameter1, USHORT, int, int, char, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003c900`

## callees

- `0x140015f60`
- `0x140016050`
- `0x140016a30`
- `0x140018640`
- `0x1400187b0`
- `0x140038160`
- `0x14003c940`
- `0x140055570`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ca4d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ca4d`
- `NDIS!NdisAllocateNetBufferList` at `0x14003c964`
- `NDIS!NdisAllocateNetBufferList` at `0x14003c964`
- `NDIS!NdisAllocateNetBuffer` at `0x14003c9e4`
- `NDIS!NdisAllocateNetBuffer` at `0x14003c9e4`

## pseudocode

```c
ULONG_PTR __fastcall NetioAllocateAndReferenceVacantNetBufferListEx(
        ULONG_PTR BugCheckParameter1,
        USHORT a2,
        int a3,
        int a4,
        char a5,
        char a6)
{
  PNET_BUFFER_LIST NetBufferList; // rax
  ULONG_PTR v10; // rbx
  __int64 *v12; // rdi
  _QWORD *p_Region; // r15
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // eax
  struct _MDL *Mdl; // rax
  struct _MDL *v18; // r14
  PNET_BUFFER NetBuffer; // rax
  PNET_BUFFER v20; // rbp
  PMDL CurrentMdl; // rcx
  char *MappedSystemVa; // rax
  int v23; // r8d
  ULONG BufferSize[22]; // [rsp+30h] [rbp-58h] BYREF

  NetBufferList = NdisAllocateNetBufferList(NetioNetBufferListPool, a2, 0);
  v10 = (ULONG_PTR)NetBufferList;
  if ( !NetBufferList )
    return 0;
  v12 = *(__int64 **)(BugCheckParameter1 + 8);
  p_Region = &NetBufferList->Link.Region;
  if ( v12 )
  {
    while ( 1 )
    {
      v14 = *((_DWORD *)v12 + 10);
      v15 = v14 + *((_DWORD *)v12 + 6);
      if ( v15 < v14 )
        break;
      v16 = v15 + a4;
      if ( v15 + a4 < v15 )
        break;
      if ( v16 + a3 < v16 )
        break;
      BufferSize[0] = v16 + a3;
      Mdl = NetioAllocateMdl(BufferSize);
      v18 = Mdl;
      if ( !Mdl )
        break;
      NetBuffer = NdisAllocateNetBuffer(NetioNetBufferPool, Mdl, BufferSize[0], 0);
      v20 = NetBuffer;
      if ( !NetBuffer )
      {
        NetioFreeMdl(v18);
        break;
      }
      *p_Region = NetBuffer;
      if ( a6 )
      {
        if ( (int)NetioRetreatNetBuffer(NetBuffer, (unsigned int)(a4 + *((_DWORD *)v12 + 6)), 0) < 0 )
          break;
        if ( *((_DWORD *)v12 + 6) )
        {
          CurrentMdl = v20->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 5) != 0 )
            MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
          else
            MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u);
          RtlCopyMdlToBufferToMode(
            (PMDL)v12[4],
            *((unsigned int *)v12 + 10),
            &MappedSystemVa[v20->CurrentMdlOffset],
            0,
            *((unsigned int *)v12 + 6),
            BufferSize);
        }
      }
      v12 = (__int64 *)*v12;
      if ( !v12 )
        break;
      p_Region = &v20->Link.Alignment;
    }
  }
  NetioInitializeNetBufferListContext(v10, BugCheckParameter1, NetiopCompleteVacantNetBufferListChain, 0);
  if ( !a5 )
  {
    if ( NetioNblTrackerEnabled )
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v10 + 72) + 132LL));
    *(_QWORD *)(v10 + 72) = 0;
    NetioDereferenceNetBufferListEx(BugCheckParameter1);
  }
  *(_DWORD *)(v10 + 136) |= 0x10000000u;
  if ( v12 || gPacketTagCount && (LOBYTE(v23) = a5 != 0, (int)WfpNblInfoClone(BugCheckParameter1, v10, v23, 0, 0) < 0) )
  {
    NetioDereferenceNetBufferListEx(v10);
    return 0;
  }
  if ( a5 )
    *(_QWORD *)(v10 + 24) = BugCheckParameter1;
  return v10;
}

```

## disassembly

```asm
0x14003c940  push    rbx
0x14003c942  push    rbp
0x14003c943  push    rsi
0x14003c944  push    rdi
0x14003c945  push    r12
0x14003c947  push    r13
0x14003c949  push    r14
0x14003c94b  push    r15
0x14003c94d  sub     rsp, 48h
0x14003c951  mov     r13d, r8d
0x14003c954  mov     rsi, rcx
0x14003c957  mov     rcx, cs:NetioNetBufferListPool; PoolHandle
0x14003c95e  xor     r8d, r8d; ContextBackFill
0x14003c961  mov     r12d, r9d
0x14003c964  call    cs:__imp_NdisAllocateNetBufferList
0x14003c96b  nop     dword ptr [rax+rax+00h]
0x14003c970  mov     rbx, rax
0x14003c973  test    rax, rax
0x14003c976  jnz     short loc_14003C97F
0x14003c978  xor     eax, eax
0x14003c97a  jmp     loc_14003CB44
0x14003c97f  mov     rdi, [rsi+8]
0x14003c983  lea     r15, [rax+8]
0x14003c987  test    rdi, rdi
0x14003c98a  jz      loc_14003CA99
0x14003c990  mov     ecx, [rdi+28h]
0x14003c993  mov     edx, [rdi+18h]
0x14003c996  add     edx, ecx
0x14003c998  cmp     edx, ecx
0x14003c99a  jb      loc_14003CA99
0x14003c9a0  lea     eax, [rdx+r12]
0x14003c9a4  cmp     eax, edx
0x14003c9a6  jb      loc_14003CA99
0x14003c9ac  lea     ecx, [rax+r13]
0x14003c9b0  cmp     ecx, eax
0x14003c9b2  jb      loc_14003CA99
0x14003c9b8  mov     [rsp+88h+BufferSize], ecx
0x14003c9bc  lea     rcx, [rsp+88h+BufferSize]; BufferSize
0x14003c9c1  call    NetioAllocateMdl
0x14003c9c6  mov     r14, rax
0x14003c9c9  test    rax, rax
0x14003c9cc  jz      loc_14003CA99
0x14003c9d2  mov     r8d, [rsp+88h+BufferSize]; DataOffset
0x14003c9d7  xor     r9d, r9d; DataLength
0x14003c9da  mov     rcx, cs:NetioNetBufferPool; PoolHandle
0x14003c9e1  mov     rdx, rax; MdlChain
0x14003c9e4  call    cs:__imp_NdisAllocateNetBuffer
0x14003c9eb  nop     dword ptr [rax+rax+00h]
0x14003c9f0  mov     rbp, rax
0x14003c9f3  test    rax, rax
0x14003c9f6  jz      loc_14003CA91
0x14003c9fc  cmp     [rsp+88h+arg_28], 0
0x14003ca04  mov     [r15], rax
0x14003ca07  jz      short loc_14003CA81
0x14003ca09  mov     edx, [rdi+18h]
0x14003ca0c  xor     r8d, r8d
0x14003ca0f  add     edx, r12d
0x14003ca12  mov     rcx, rax
0x14003ca15  call    NetioRetreatNetBuffer
0x14003ca1a  test    eax, eax
0x14003ca1c  js      short loc_14003CA99
0x14003ca1e  cmp     dword ptr [rdi+18h], 0
0x14003ca22  jz      short loc_14003CA81
0x14003ca24  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14003ca28  test    byte ptr [rcx+0Ah], 5
0x14003ca2c  jz      short loc_14003CA34
0x14003ca2e  mov     rax, [rcx+18h]
0x14003ca32  jmp     short loc_14003CA59
0x14003ca34  xor     r9d, r9d; RequestedAddress
0x14003ca37  mov     [rsp+88h+Priority], 40000000h; Priority
0x14003ca3f  xor     edx, edx; AccessMode
0x14003ca41  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003ca49  lea     r8d, [r9+1]; CacheType
0x14003ca4d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003ca54  nop     dword ptr [rax+rax+00h]
0x14003ca59  mov     ecx, [rdi+18h]
0x14003ca5c  xor     r9d, r9d
0x14003ca5f  mov     r8d, [rbp+10h]
0x14003ca63  mov     edx, [rdi+28h]
0x14003ca66  add     r8, rax
0x14003ca69  lea     rax, [rsp+88h+BufferSize]
0x14003ca6e  mov     qword ptr [rsp+88h+Priority], rax; __int64
0x14003ca73  mov     qword ptr [rsp+88h+BugCheckOnFailure], rcx; __int64
0x14003ca78  mov     rcx, [rdi+20h]; SourceMdl
0x14003ca7c  call    RtlCopyMdlToBufferToMode
0x14003ca81  mov     rdi, [rdi]
0x14003ca84  test    rdi, rdi
0x14003ca87  jz      short loc_14003CA99
0x14003ca89  mov     r15, rbp
0x14003ca8c  jmp     loc_14003C990
0x14003ca91  mov     rcx, r14; Mdl
0x14003ca94  call    NetioFreeMdl
0x14003ca99  xor     r9d, r9d
0x14003ca9c  lea     r8, NetiopCompleteVacantNetBufferListChain
0x14003caa3  mov     rdx, rsi
0x14003caa6  mov     rcx, rbx
0x14003caa9  call    NetioInitializeNetBufferListContext
0x14003caae  mov     bpl, [rsp+88h+arg_20]
0x14003cab6  test    bpl, bpl
0x14003cab9  jnz     short loc_14003CAE8
0x14003cabb  cmp     cs:NetioNblTrackerEnabled, bpl
0x14003cac2  jz      short loc_14003CACF
0x14003cac4  mov     rax, [rbx+48h]
0x14003cac8  lock dec dword ptr [rax+84h]
0x14003cacf  mov     qword ptr [rbx+48h], 0
0x14003cad7  xor     edx, edx
0x14003cad9  mov     r8d, [rsi+8Ch]
0x14003cae0  mov     rcx, rsi; BugCheckParameter1
0x14003cae3  call    NetioDereferenceNetBufferListEx
0x14003cae8  bts     dword ptr [rbx+88h], 1Ch
0x14003caf0  test    rdi, rdi
0x14003caf3  jz      short loc_14003CB10
0x14003caf5  mov     r8d, [rbx+8Ch]
0x14003cafc  mov     rcx, rbx; BugCheckParameter1
0x14003caff  mov     dl, [rsp+88h+arg_30]
0x14003cb06  call    NetioDereferenceNetBufferListEx
0x14003cb0b  jmp     loc_14003C978
0x14003cb10  cmp     cs:gPacketTagCount, 0
0x14003cb18  jbe     short loc_14003CB38
0x14003cb1a  test    bpl, bpl
0x14003cb1d  mov     byte ptr [rsp+88h+BugCheckOnFailure], 0
0x14003cb22  mov     rdx, rbx
0x14003cb25  mov     rcx, rsi
0x14003cb28  setnz   r8b
0x14003cb2c  xor     r9d, r9d
0x14003cb2f  call    WfpNblInfoClone
0x14003cb34  test    eax, eax
0x14003cb36  js      short loc_14003CAF5
0x14003cb38  test    bpl, bpl
0x14003cb3b  jz      short loc_14003CB41
0x14003cb3d  mov     [rbx+18h], rsi
0x14003cb41  mov     rax, rbx
0x14003cb44  add     rsp, 48h
0x14003cb48  pop     r15
0x14003cb4a  pop     r14
0x14003cb4c  pop     r13
0x14003cb4e  pop     r12
0x14003cb50  pop     rdi
0x14003cb51  pop     rsi
0x14003cb52  pop     rbp
0x14003cb53  pop     rbx
0x14003cb54  retn
```
