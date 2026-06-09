# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x14000c560`
- end: `0x14000c5ef`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140006cd0`
- `0x14000c364`
- `0x14000e420`

## callees

- `0x14000849c`
- `0x140008ea0`
- `0x14000c068`
- `0x14000c560`
- `0x14000dfb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c57a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c57a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c5cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c5cb`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  _BYTE v5[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v6[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v7[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v5);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v7,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v5, v2, v3, v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v5);
}

```

## disassembly

```asm
0x14000c560  push    rbx
0x14000c562  sub     rsp, 0E0h
0x14000c569  mov     rbx, rcx
0x14000c56c  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c571  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000c576  nop
0x14000c577  mov     rcx, rbx; SRWLock
0x14000c57a  call    cs:__imp_AcquireSRWLockExclusive
0x14000c580  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000c584  cmp     byte ptr [rdx+38h], 0
0x14000c588  jz      short loc_14000C594
0x14000c58a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c58f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c594  cmp     byte ptr [rbx+80h], 0
0x14000c59b  jz      short loc_14000C5AB
0x14000c59d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000c5a1  lea     rcx, [rsp+0E8h+var_88]; this
0x14000c5a6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c5ab  cmp     byte ptr [rbx+0C0h], 0
0x14000c5b2  jz      short loc_14000C5C8
0x14000c5b4  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000c5bb  lea     rcx, [rsp+0E8h+var_48]; this
0x14000c5c3  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c5c8  mov     rcx, rbx; SRWLock
0x14000c5cb  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c5d1  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c5d6  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000c5db  nop
0x14000c5dc  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c5e1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000c5e6  add     rsp, 0E0h
0x14000c5ed  pop     rbx
0x14000c5ee  retn
```
