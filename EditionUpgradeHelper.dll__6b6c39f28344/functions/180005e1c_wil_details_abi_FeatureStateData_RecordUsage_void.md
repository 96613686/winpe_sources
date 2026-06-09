# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180005e1c`
- end: `0x180005ea9`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002630`
- `0x180005c64`
- `0x180007640`

## callees

- `0x180002f9c`
- `0x180003574`
- `0x180005b1c`
- `0x180005e1c`
- `0x180007280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e86`

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
0x180005e1c  push    rbx
0x180005e1e  sub     rsp, 0E0h
0x180005e25  mov     rbx, rcx
0x180005e28  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005e2d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005e32  mov     rcx, rbx; SRWLock
0x180005e35  call    cs:__imp_AcquireSRWLockExclusive
0x180005e3b  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005e3f  cmp     byte ptr [rdx+38h], 0
0x180005e43  jz      short loc_180005E4F
0x180005e45  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005e4a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005e4f  cmp     byte ptr [rbx+80h], 0
0x180005e56  jz      short loc_180005E66
0x180005e58  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005e5c  lea     rcx, [rsp+0E8h+var_88]; this
0x180005e61  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005e66  cmp     byte ptr [rbx+0C0h], 0
0x180005e6d  jz      short loc_180005E83
0x180005e6f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005e76  lea     rcx, [rsp+0E8h+var_48]; this
0x180005e7e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005e83  mov     rcx, rbx; SRWLock
0x180005e86  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e8c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005e91  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005e96  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005e9b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005ea0  add     rsp, 0E0h
0x180005ea7  pop     rbx
0x180005ea8  retn
```
