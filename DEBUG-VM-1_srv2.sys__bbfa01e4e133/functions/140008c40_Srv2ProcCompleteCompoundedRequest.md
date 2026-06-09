# Srv2ProcCompleteCompoundedRequest

- ea: `0x140008c40`
- end: `0x140009182`
- name: `Srv2ProcCompleteCompoundedRequest`
- size: `1346`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007090`
- `0x140008940`
- `0x14000a560`

## callees

- `0x1400014d0`
- `0x140004960`
- `0x140005070`
- `0x140006218`
- `0x140006a30`
- `0x140008c40`
- `0x140022958`
- `0x1400384d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008fb6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008fe2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008fb6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008fe2`
- `ntoskrnl!KeBugCheckEx` at `0x1400090ce`
- `ntoskrnl!KeBugCheckEx` at `0x140009144`
- `ntoskrnl!KeBugCheckEx` at `0x1400090ce`
- `ntoskrnl!KeBugCheckEx` at `0x140009144`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140009033`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140009033`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009169`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009169`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000904f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000904f`
- `srvnet!SrvNetSendData` at `0x140008f2f`
- `srvnet!SrvNetSendData` at `0x140008f2f`

## string_xrefs

- `0x140009014`: `Srv2PostToThreadPool`

## pseudocode

```c
PSLIST_ENTRY __fastcall Srv2ProcCompleteCompoundedRequest(__int64 a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // r8
  unsigned int v4; // edx
  void (__fastcall *v5)(__int64); // rax
  __int64 v6; // rax
  _QWORD **v7; // r14
  int v8; // r15d
  _QWORD *i; // rcx
  _QWORD *v10; // rsi
  _QWORD *j; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  _DWORD *v14; // rax
  _QWORD *v15; // rbp
  int v16; // edx
  void (__fastcall *v17)(_QWORD *); // rax
  _QWORD *v18; // rcx
  __int64 v19; // rcx
  unsigned int *v20; // rdi
  __int64 v21; // r8
  __int16 v22; // ax
  __int16 v23; // dx
  __int16 v24; // ax
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rsi
  __int64 v28; // r9
  __int64 v29; // rax
  PSLIST_ENTRY result; // rax
  bool v31; // zf
  __int64 v32; // rdi
  __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  int BugCheckOnFailure; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      &WPP_1f56813514af312e5a39176f5ad11993_Traceguids,
      a1,
      *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL));
  }
  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 80LL);
  if ( (*(_BYTE *)(v2 + 10) & 5) != 0 )
    v3 = *(_DWORD **)(v2 + 24);
  else
    v3 = MmMapLockedPagesSpecifyCache((PMDL)v2, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v3 )
    KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\workitem.c", 0x354u, 0, 0);
  v4 = *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL);
  if ( v4 > 0x40 )
  {
    if ( *(_QWORD *)(a1 + 432) == a1 + 432 )
      v4 = 0;
    v3[5] = v4;
  }
  if ( *(_BYTE *)(a1 + 474) )
  {
    Srv2CloseConnection(*(PVOID *)(a1 + 96));
    return (PSLIST_ENTRY)Srv2DereferenceCompoundWorkItem(a1);
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) && (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
      Smb2OutputWorkItemResponseEtw(a1);
    v5 = *(void (__fastcall **)(__int64))(a1 + 536);
    if ( v5 )
      v5(a1);
    v6 = *(_QWORD *)(a1 + 312);
    v7 = *(_QWORD ***)(v6 + 80);
    v8 = *(_DWORD *)(v6 + 36);
    for ( i = *v7; i; i = (_QWORD *)*i )
      v7 = (_QWORD **)i;
    v10 = (_QWORD *)(a1 + 432);
    for ( j = *(_QWORD **)(a1 + 432); j != v10; j = (_QWORD *)*j )
    {
      v12 = *(j - 15);
      if ( *(_DWORD *)(v12 + 36) )
      {
        v13 = *(_QWORD *)(v12 + 80);
        if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
          v14 = *(_DWORD **)(v13 + 24);
        else
          v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
        if ( !v14 )
          KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\workitem.c", 0x3A4u, 0, 0);
        v15 = j - 54;
        if ( (_QWORD *)*j == v10 )
          v16 = 0;
        else
          v16 = *(_DWORD *)(v15[39] + 36LL);
        v14[5] = v16;
        if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          Smb2OutputWorkItemResponseEtw(j - 54);
        v17 = (void (__fastcall *)(_QWORD *))v15[67];
        if ( v17 )
          v17(j - 54);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            &WPP_1f56813514af312e5a39176f5ad11993_Traceguids,
            j - 54,
            *(_DWORD *)(v15[39] + 36LL));
        }
        if ( v7 )
          *v7 = *(_QWORD **)(v15[39] + 80LL);
        v18 = *v7;
        v8 += *(_DWORD *)(v15[39] + 36LL);
        if ( *v7 )
        {
          do
          {
            v7 = (_QWORD **)v18;
            v18 = (_QWORD *)*v18;
          }
          while ( v18 );
        }
      }
    }
    v19 = *(_QWORD *)(a1 + 312);
    v20 = (unsigned int *)(a1 + 128);
    *(_QWORD *)(a1 + 152) = a1;
    *(_DWORD *)(a1 + 132) = 0;
    *(_DWORD *)(a1 + 176) = 0;
    *(_DWORD *)(a1 + 128) = v8;
    *(_QWORD *)(a1 + 136) = *(_QWORD *)(v19 + 80);
    *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 120);
    *(_QWORD *)(a1 + 144) = Srv2ProcSendComplete;
    *(_QWORD *)(a1 + 160) = Srv2DereferenceCompoundWorkItem;
    v21 = *(_QWORD *)(v19 + 80);
    v22 = *(_WORD *)(v21 + 10);
    v23 = v22 & 0xEFFF;
    v24 = v22 | 0x1000;
    if ( *(_QWORD *)(v21 + 24) == *(_QWORD *)(v19 + 24) )
      v23 = v24;
    *(_WORD *)(v21 + 10) = v23;
    if ( *(_BYTE *)(a1 + 556) )
    {
      v34 = *(_DWORD *)(a1 + 552);
      *(_DWORD *)(a1 + 132) |= 1u;
      *(_DWORD *)(a1 + 224) = v34;
    }
    v25 = *(_QWORD *)(a1 + 96);
    v26 = *(_QWORD *)(a1 + 560);
    v27 = *(_QWORD *)(v25 + 480);
    v28 = *(_QWORD *)(v25 + 496);
    if ( byte_140058150 )
    {
      v29 = *(_QWORD *)(v26 + 56);
      if ( v29 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v29 + 104) + 320LL), *v20);
        _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v26 + 56) + 104LL) + 328LL), *v20);
      }
      if ( *(_QWORD *)(v26 + 32) )
      {
        _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v26 + 40) + 168LL), *v20);
        _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v26 + 40) + 176LL), *v20);
      }
    }
    if ( (*(_DWORD *)(a1 + 484) & 0x2040) != 0 && !Smb2CompressionDisabled )
    {
      *(_DWORD *)(a1 + 216) = *(_DWORD *)(v28 + 144);
      *(_DWORD *)(a1 + 220) = *(_DWORD *)(v28 + 152);
      v36 = *(_QWORD *)(v26 + 56);
      if ( v36 )
      {
        *(_QWORD *)(a1 + 232) = *(_QWORD *)(v36 + 104) + 624LL;
        *(_QWORD *)(a1 + 240) = *(_QWORD *)(*(_QWORD *)(v26 + 56) + 104LL) + 640LL;
        v37 = *(_QWORD *)(*(_QWORD *)(v26 + 56) + 104LL) + 648LL;
      }
      else
      {
        *(_QWORD *)(a1 + 232) = 0;
        v37 = 0;
        *(_QWORD *)(a1 + 240) = 0;
      }
      *(_QWORD *)(a1 + 248) = v37;
      if ( (*(_BYTE *)(v28 + 49) & 0x20) != 0 )
        *(_DWORD *)(a1 + 132) |= 2u;
    }
    if ( *(_BYTE *)(v26 + 7) )
    {
      *(_DWORD *)(a1 + 180) = _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 196), 0xFFFFFFFF);
      *(_BYTE *)(v26 + 7) = 0;
    }
    else
    {
      *(_DWORD *)(a1 + 180) = -1;
    }
    if ( *(_DWORD *)(a1 + 216) && KeGetCurrentIrql() )
    {
      v31 = *(_DWORD *)(a1 + 8) == 5;
      *(_QWORD *)(a1 + 48) = Smb2SendDataAtPassive;
      *(_DWORD *)(a1 + 72) = 0;
      if ( v31 )
      {
        LOBYTE(BugCheckOnFailure) = 1;
        LOBYTE(v35) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, v35, 391, "Srv2PostToThreadPool", BugCheckOnFailure);
      }
      v32 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
      v33 = *(_QWORD *)(v32 + 8LL * KeGetCurrentNodeNumber() + 8);
      result = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v33 + 16), (PSLIST_ENTRY)(a1 + 32));
      if ( !result && *(_WORD *)(v33 + 66) )
        return (PSLIST_ENTRY)RfspThreadPoolNodeWakeIdleWorker(v33);
    }
    else
    {
      return (PSLIST_ENTRY)SrvNetSendData(v27, a1 + 128);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008c40  push    rbx
0x140008c42  push    r12
0x140008c44  push    r13
0x140008c46  sub     rsp, 40h
0x140008c4a  mov     rbx, rcx
0x140008c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c54  lea     r12, WPP_GLOBAL_Control
0x140008c5b  cmp     rcx, r12
0x140008c5e  jz      short loc_140008C6B
0x140008c60  mov     eax, [rcx+2Ch]
0x140008c63  test    al, 1
0x140008c65  jnz     loc_14000907F
0x140008c6b  mov     rax, [rbx+138h]
0x140008c72  xor     r13d, r13d
0x140008c75  mov     rcx, [rax+50h]; MemoryDescriptorList
0x140008c79  test    byte ptr [rcx+0Ah], 5
0x140008c7d  jz      loc_140008F9E
0x140008c83  mov     r8, [rcx+18h]
0x140008c87  test    r8, r8
0x140008c8a  jz      loc_1400090B4
0x140008c90  mov     rax, [rbx+138h]
0x140008c97  mov     edx, [rax+24h]
0x140008c9a  cmp     edx, 40h ; '@'
0x140008c9d  jbe     short loc_140008CB1
0x140008c9f  lea     rcx, [rbx+1B0h]
0x140008ca6  cmp     [rcx], rcx
0x140008ca9  cmovz   edx, r13d
0x140008cad  mov     [r8+14h], edx
0x140008cb1  cmp     [rbx+1DAh], r13b
0x140008cb8  jnz     loc_140008F6E
0x140008cbe  mov     rax, [rbx+138h]
0x140008cc5  mov     [rsp+58h+arg_8], rsi
0x140008cca  mov     [rsp+58h+arg_10], rdi
0x140008ccf  mov     [rsp+58h+var_20], r14
0x140008cd4  mov     [rsp+58h+var_28], r15
0x140008cd9  cmp     [rax+24h], r13d
0x140008cdd  jbe     short loc_140008CEC
0x140008cdf  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x140008ce6  jnz     loc_1400090DB
0x140008cec  mov     rax, [rbx+218h]
0x140008cf3  test    rax, rax
0x140008cf6  jz      short loc_140008D00
0x140008cf8  mov     rcx, rbx
0x140008cfb  call    _guard_dispatch_icall
0x140008d00  mov     rax, [rbx+138h]
0x140008d07  mov     r14, [rax+50h]
0x140008d0b  mov     r15d, [rax+24h]
0x140008d0f  mov     rcx, [r14]
0x140008d12  test    rcx, rcx
0x140008d15  jz      short loc_140008D25
0x140008d17  mov     rax, [rcx]
0x140008d1a  mov     r14, rcx
0x140008d1d  mov     rcx, rax
0x140008d20  test    rax, rax
0x140008d23  jnz     short loc_140008D17
0x140008d25  lea     rsi, [rbx+1B0h]
0x140008d2c  mov     [rsp+58h+arg_0], rbp
0x140008d31  mov     rdi, [rsi]
0x140008d34  cmp     rdi, rsi
0x140008d37  jz      loc_140008DF0
0x140008d3d  mov     rax, [rdi-78h]
0x140008d41  cmp     [rax+24h], r13d
0x140008d45  jbe     loc_140008DE8
0x140008d4b  mov     rcx, [rax+50h]; MemoryDescriptorList
0x140008d4f  test    byte ptr [rcx+0Ah], 5
0x140008d53  jz      loc_140008FCA
0x140008d59  mov     rax, [rcx+18h]
0x140008d5d  test    rax, rax
0x140008d60  jz      loc_14000912A
0x140008d66  lea     rbp, [rdi-1B0h]
0x140008d6d  cmp     [rdi], rsi
0x140008d70  jnz     loc_140008F5F
0x140008d76  mov     edx, r13d
0x140008d79  mov     [rax+14h], edx
0x140008d7c  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x140008d83  jnz     loc_1400090E8
0x140008d89  mov     rax, [rbp+218h]
0x140008d90  test    rax, rax
0x140008d93  jz      short loc_140008D9D
0x140008d95  mov     rcx, rbp
0x140008d98  call    _guard_dispatch_icall
0x140008d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008da4  cmp     rcx, r12
0x140008da7  jz      short loc_140008DB4
0x140008da9  mov     eax, [rcx+2Ch]
0x140008dac  test    al, 1
0x140008dae  jnz     loc_1400090F5
0x140008db4  test    r14, r14
0x140008db7  jz      short loc_140008DC7
0x140008db9  mov     rax, [rbp+138h]
0x140008dc0  mov     rcx, [rax+50h]
0x140008dc4  mov     [r14], rcx
0x140008dc7  mov     rax, [rbp+138h]
0x140008dce  mov     rcx, [r14]
0x140008dd1  add     r15d, [rax+24h]
0x140008dd5  test    rcx, rcx
0x140008dd8  jz      short loc_140008DE8
0x140008dda  mov     rax, [rcx]
0x140008ddd  mov     r14, rcx
0x140008de0  mov     rcx, rax
0x140008de3  test    rax, rax
0x140008de6  jnz     short loc_140008DDA
0x140008de8  mov     rdi, [rdi]
0x140008deb  jmp     loc_140008D34
0x140008df0  mov     rcx, [rbx+138h]
0x140008df7  lea     rdi, [rbx+80h]
0x140008dfe  mov     [rbx+98h], rbx
0x140008e05  mov     r9d, 0FFFFEFFFh
0x140008e0b  mov     [rbx+84h], r13d
0x140008e12  mov     [rbx+0B0h], r13d
0x140008e19  mov     [rdi], r15d
0x140008e1c  mov     rax, [rcx+50h]
0x140008e20  mov     [rbx+88h], rax
0x140008e27  mov     rax, [rbx+78h]
0x140008e2b  mov     [rbx+0A8h], rax
0x140008e32  lea     rax, Srv2ProcSendComplete
0x140008e39  mov     [rbx+90h], rax
0x140008e40  lea     rax, Srv2DereferenceCompoundWorkItem
0x140008e47  mov     [rbx+0A0h], rax
0x140008e4e  mov     r8, [rcx+50h]
0x140008e52  mov     rcx, [rcx+18h]
0x140008e56  movzx   edx, word ptr [r8+0Ah]
0x140008e5b  movzx   eax, dx
0x140008e5e  and     dx, r9w
0x140008e62  or      ax, 1000h
0x140008e66  cmp     [r8+18h], rcx
0x140008e6a  cmovz   dx, ax
0x140008e6e  mov     [r8+0Ah], dx
0x140008e73  cmp     [rbx+22Ch], r13b
0x140008e7a  jnz     loc_140009151
0x140008e80  cmp     cs:byte_140058150, r13b
0x140008e87  mov     rax, [rbx+60h]
0x140008e8b  mov     r8, [rbx+230h]
0x140008e92  mov     rsi, [rax+1E0h]
0x140008e99  mov     r9, [rax+1F0h]
0x140008ea0  jz      short loc_140008EED
0x140008ea2  mov     rax, [r8+38h]
0x140008ea6  test    rax, rax
0x140008ea9  jz      short loc_140008ECB
0x140008eab  mov     ecx, [rdi]
0x140008ead  mov     rax, [rax+68h]
0x140008eb1  lock add [rax+140h], rcx
0x140008eb9  mov     rax, [r8+38h]
0x140008ebd  mov     edx, [rdi]
0x140008ebf  mov     rcx, [rax+68h]
0x140008ec3  lock add [rcx+148h], rdx
0x140008ecb  cmp     [r8+20h], r13
0x140008ecf  jz      short loc_140008EED
0x140008ed1  mov     ecx, [rdi]
0x140008ed3  mov     rax, [r8+28h]
0x140008ed7  lock add [rax+0A8h], rcx
0x140008edf  mov     ecx, [rdi]
0x140008ee1  mov     rax, [r8+28h]
0x140008ee5  lock add [rax+0B0h], rcx
0x140008eed  test    dword ptr [rbx+1E4h], 2040h
0x140008ef7  jnz     loc_14003AAC6
0x140008efd  cmp     [r8+7], r13b
0x140008f01  jz      loc_140008F92
0x140008f07  mov     eax, 0FFFFFFFFh
0x140008f0c  lock xadd [r9+0C4h], eax
0x140008f15  mov     [rbx+0B4h], eax
0x140008f1b  mov     [r8+7], r13b
0x140008f1f  cmp     [rdi+58h], r13d
0x140008f23  jnz     loc_140009169
0x140008f29  mov     rdx, rdi
0x140008f2c  mov     rcx, rsi
0x140008f2f  call    cs:__imp_SrvNetSendData
0x140008f36  nop     dword ptr [rax+rax+00h]
0x140008f3b  mov     rbp, [rsp+58h+arg_0]
0x140008f40  mov     rdi, [rsp+58h+arg_10]
0x140008f45  mov     rsi, [rsp+58h+arg_8]
0x140008f4a  mov     r14, [rsp+58h+var_20]
0x140008f4f  mov     r15, [rsp+58h+var_28]
0x140008f54  add     rsp, 40h
0x140008f58  pop     r13
0x140008f5a  pop     r12
0x140008f5c  pop     rbx
0x140008f5d  retn
0x140008f5f  mov     rcx, [rbp+138h]
0x140008f66  mov     edx, [rcx+24h]
0x140008f69  jmp     loc_140008D79
0x140008f6e  mov     rcx, [rbx+60h]; P
0x140008f72  xor     r8d, r8d
0x140008f75  mov     edx, 6
0x140008f7a  call    Srv2CloseConnection
0x140008f7f  mov     rcx, rbx
0x140008f82  call    Srv2DereferenceCompoundWorkItem
0x140008f87  add     rsp, 40h
0x140008f8b  pop     r13
0x140008f8d  pop     r12
0x140008f8f  pop     rbx
0x140008f90  retn
0x140008f92  mov     dword ptr [rbx+0B4h], 0FFFFFFFFh
0x140008f9c  jmp     short loc_140008F1F
0x140008f9e  mov     [rsp+58h+Priority], 40000010h; Priority
0x140008fa6  xor     r9d, r9d; RequestedAddress
0x140008fa9  xor     edx, edx; AccessMode
0x140008fab  mov     [rsp+58h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140008fb0  mov     r8d, 1; CacheType
0x140008fb6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008fbd  nop     dword ptr [rax+rax+00h]
0x140008fc2  mov     r8, rax
0x140008fc5  jmp     loc_140008C87
0x140008fca  mov     [rsp+58h+Priority], 40000010h; Priority
0x140008fd2  xor     r9d, r9d; RequestedAddress
0x140008fd5  xor     edx, edx; AccessMode
0x140008fd7  mov     [rsp+58h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140008fdc  mov     r8d, 1; CacheType
0x140008fe2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008fe9  nop     dword ptr [rax+rax+00h]
0x140008fee  jmp     loc_140008D5D
0x140008ff3  cmp     dword ptr [rbx+8], 5
0x140008ff7  lea     rax, Smb2SendDataAtPassive
0x140008ffe  mov     [rbx+30h], rax
0x140009002  mov     [rbx+48h], r13d
0x140009006  jnz     short loc_140009028
0x140009008  lea     rcx, [rbx+248h]
0x14000900f  mov     byte ptr [rsp+58h+BugCheckOnFailure], 1
0x140009014  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000901b  mov     r8d, 187h
0x140009021  mov     dl, 1
0x140009023  call    SRV2_PERF_ENTER_EX
0x140009028  mov     rax, [rbx+40h]
0x14000902c  mov     rdi, [rax+88h]
0x140009033  call    cs:__imp_KeGetCurrentNodeNumber
0x14000903a  nop     dword ptr [rax+rax+00h]
0x14000903f  movzx   eax, ax
0x140009042  lea     rdx, [rbx+20h]; ListEntry
0x140009046  mov     rdi, [rdi+rax*8+8]
0x14000904b  lea     rcx, [rdi+10h]; ListHead
0x14000904f  call    cs:__imp_ExpInterlockedPushEntrySList
0x140009056  nop     dword ptr [rax+rax+00h]
0x14000905b  test    rax, rax
0x14000905e  jnz     loc_140008F3B
0x140009064  movzx   edx, word ptr [rdi+42h]
0x140009068  cmp     r13w, dx
0x14000906c  jz      loc_140008F3B
0x140009072  mov     rcx, rdi
0x140009075  call    RfspThreadPoolNodeWakeIdleWorker
0x14000907a  jmp     loc_140008F3B
0x14000907f  cmp     byte ptr [rcx+29h], 2
0x140009083  jb      loc_140008C6B
0x140009089  mov     rax, [rbx+138h]
0x140009090  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x140009097  mov     rcx, [rcx+18h]
0x14000909b  mov     edx, 0Dh
0x1400090a0  mov     r9, rbx
0x1400090a3  mov     eax, [rax+24h]
0x1400090a6  mov     [rsp+58h+BugCheckOnFailure], eax
0x1400090aa  call    WPP_SF_qD
0x1400090af  jmp     loc_140008C6B
0x1400090b4  xor     r9d, r9d; BugCheckParameter3
0x1400090b7  mov     qword ptr [rsp+58h+BugCheckOnFailure], r13; BugCheckParameter4
0x1400090bc  mov     r8d, 354h; BugCheckParameter2
0x1400090c2  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400090c9  mov     ecx, 54h ; 'T'; BugCheckCode
0x1400090ce  call    cs:__imp_KeBugCheckEx
0x1400090db  mov     rcx, rbx
0x1400090de  call    Smb2OutputWorkItemResponseEtw
0x1400090e3  jmp     loc_140008CEC
0x1400090e8  mov     rcx, rbp
0x1400090eb  call    Smb2OutputWorkItemResponseEtw
0x1400090f0  jmp     loc_140008D89
0x1400090f5  cmp     byte ptr [rcx+29h], 2
0x1400090f9  jb      loc_140008DB4
0x1400090ff  mov     rax, [rbp+138h]
0x140009106  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x14000910d  mov     rcx, [rcx+18h]
0x140009111  mov     edx, 0Eh
0x140009116  mov     r9, rbp
0x140009119  mov     eax, [rax+24h]
0x14000911c  mov     [rsp+58h+BugCheckOnFailure], eax
0x140009120  call    WPP_SF_qD
0x140009125  jmp     loc_140008DB4
0x14000912a  xor     r9d, r9d; BugCheckParameter3
0x14000912d  mov     qword ptr [rsp+58h+BugCheckOnFailure], r13; BugCheckParameter4
0x140009132  mov     r8d, 3A4h; BugCheckParameter2
0x140009138  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14000913f  mov     ecx, 54h ; 'T'; BugCheckCode
0x140009144  call    cs:__imp_KeBugCheckEx
0x140009151  mov     eax, [rbx+228h]
0x140009157  or      dword ptr [rbx+84h], 1
0x14000915e  mov     [rbx+0E0h], eax
0x140009164  jmp     loc_140008E80
0x140009169  call    cs:__imp_KeGetCurrentIrql
0x140009170  nop     dword ptr [rax+rax+00h]
0x140009175  test    al, al
0x140009177  jz      loc_140008F29
0x14000917d  jmp     loc_140008FF3
0x14003aac6  cmp     cs:Smb2CompressionDisabled, r13b
0x14003aacd  jnz     loc_140008EFD
0x14003aad3  mov     eax, [r9+90h]
0x14003aada  mov     [rdi+58h], eax
0x14003aadd  mov     eax, [r9+98h]
0x14003aae4  mov     [rdi+5Ch], eax
0x14003aae7  mov     rax, [r8+38h]
0x14003aaeb  test    rax, rax
0x14003aaee  jz      short loc_14003AB28
0x14003aaf0  mov     rax, [rax+68h]
0x14003aaf4  add     rax, 270h
  ... truncated ...
```
