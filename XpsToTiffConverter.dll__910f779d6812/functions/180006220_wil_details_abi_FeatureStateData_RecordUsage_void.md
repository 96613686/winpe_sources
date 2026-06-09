# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180006220`
- end: `0x1800062af`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022c0`
- `0x180006064`
- `0x180008230`

## callees

- `0x180002f54`
- `0x180003884`
- `0x180005f28`
- `0x180006220`
- `0x180007e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000623a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000623a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000628b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000628b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  _BYTE v2[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v3[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v4[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v2);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v2,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v3,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v2);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v2);
}

```

## disassembly

```asm
0x180006220  push    rbx
0x180006222  sub     rsp, 0E0h
0x180006229  mov     rbx, rcx
0x18000622c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006231  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006236  nop
0x180006237  mov     rcx, rbx; SRWLock
0x18000623a  call    cs:__imp_AcquireSRWLockExclusive
0x180006240  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006244  cmp     byte ptr [rdx+38h], 0
0x180006248  jz      short loc_180006254
0x18000624a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000624f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006254  cmp     byte ptr [rbx+80h], 0
0x18000625b  jz      short loc_18000626B
0x18000625d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006261  lea     rcx, [rsp+0E8h+var_88]; this
0x180006266  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000626b  cmp     byte ptr [rbx+0C0h], 0
0x180006272  jz      short loc_180006288
0x180006274  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000627b  lea     rcx, [rsp+0E8h+var_48]; this
0x180006283  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006288  mov     rcx, rbx; SRWLock
0x18000628b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006291  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006296  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000629b  nop
0x18000629c  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800062a1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800062a6  add     rsp, 0E0h
0x1800062ad  pop     rbx
0x1800062ae  retn
```
