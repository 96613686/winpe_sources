# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180006320`
- end: `0x1800063af`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002790`
- `0x180006164`
- `0x180008150`

## callees

- `0x180003274`
- `0x1800039e4`
- `0x180006020`
- `0x180006320`
- `0x180007d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000633a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000633a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000638b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000638b`

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
0x180006320  push    rbx
0x180006322  sub     rsp, 0E0h
0x180006329  mov     rbx, rcx
0x18000632c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006331  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006336  nop
0x180006337  mov     rcx, rbx; SRWLock
0x18000633a  call    cs:__imp_AcquireSRWLockExclusive
0x180006340  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006344  cmp     byte ptr [rdx+38h], 0
0x180006348  jz      short loc_180006354
0x18000634a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000634f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006354  cmp     byte ptr [rbx+80h], 0
0x18000635b  jz      short loc_18000636B
0x18000635d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006361  lea     rcx, [rsp+0E8h+var_88]; this
0x180006366  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000636b  cmp     byte ptr [rbx+0C0h], 0
0x180006372  jz      short loc_180006388
0x180006374  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000637b  lea     rcx, [rsp+0E8h+var_48]; this
0x180006383  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006388  mov     rcx, rbx; SRWLock
0x18000638b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006391  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006396  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000639b  nop
0x18000639c  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800063a1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800063a6  add     rsp, 0E0h
0x1800063ad  pop     rbx
0x1800063ae  retn
```
