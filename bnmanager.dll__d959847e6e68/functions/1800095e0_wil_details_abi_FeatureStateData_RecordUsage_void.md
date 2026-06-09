# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800095e0`
- end: `0x18000966f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800024b0`
- `0x180009424`
- `0x18000b6a0`

## callees

- `0x180004800`
- `0x180005704`
- `0x1800092e0`
- `0x1800095e0`
- `0x18000b2a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800095fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800095fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000964b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000964b`

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
0x1800095e0  push    rbx
0x1800095e2  sub     rsp, 0E0h
0x1800095e9  mov     rbx, rcx
0x1800095ec  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800095f1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800095f6  nop
0x1800095f7  mov     rcx, rbx; SRWLock
0x1800095fa  call    cs:__imp_AcquireSRWLockExclusive
0x180009600  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009604  cmp     byte ptr [rdx+38h], 0
0x180009608  jz      short loc_180009614
0x18000960a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000960f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009614  cmp     byte ptr [rbx+80h], 0
0x18000961b  jz      short loc_18000962B
0x18000961d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009621  lea     rcx, [rsp+0E8h+var_88]; this
0x180009626  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000962b  cmp     byte ptr [rbx+0C0h], 0
0x180009632  jz      short loc_180009648
0x180009634  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000963b  lea     rcx, [rsp+0E8h+var_48]; this
0x180009643  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009648  mov     rcx, rbx; SRWLock
0x18000964b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009651  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009656  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000965b  nop
0x18000965c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009661  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009666  add     rsp, 0E0h
0x18000966d  pop     rbx
0x18000966e  retn
```
