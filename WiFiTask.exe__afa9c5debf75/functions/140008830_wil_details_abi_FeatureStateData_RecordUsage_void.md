# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140008830`
- end: `0x1400088bf`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002370`
- `0x140008634`
- `0x14000afe0`

## callees

- `0x1400031c4`
- `0x140003c44`
- `0x140008334`
- `0x140008830`
- `0x14000ab6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000884a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000884a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000889b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000889b`

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
0x140008830  push    rbx
0x140008832  sub     rsp, 0E0h
0x140008839  mov     rbx, rcx
0x14000883c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008841  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008846  nop
0x140008847  mov     rcx, rbx; SRWLock
0x14000884a  call    cs:__imp_AcquireSRWLockExclusive
0x140008850  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140008854  cmp     byte ptr [rdx+38h], 0
0x140008858  jz      short loc_140008864
0x14000885a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000885f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008864  cmp     byte ptr [rbx+80h], 0
0x14000886b  jz      short loc_14000887B
0x14000886d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140008871  lea     rcx, [rsp+0E8h+var_88]; this
0x140008876  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000887b  cmp     byte ptr [rbx+0C0h], 0
0x140008882  jz      short loc_140008898
0x140008884  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000888b  lea     rcx, [rsp+0E8h+var_48]; this
0x140008893  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008898  mov     rcx, rbx; SRWLock
0x14000889b  call    cs:__imp_ReleaseSRWLockExclusive
0x1400088a1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400088a6  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1400088ab  nop
0x1400088ac  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400088b1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1400088b6  add     rsp, 0E0h
0x1400088bd  pop     rbx
0x1400088be  retn
```
