# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800087f0`
- end: `0x18000887f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004cf0`
- `0x180008634`
- `0x18000a620`

## callees

- `0x1800057d0`
- `0x180005ef0`
- `0x1800084f0`
- `0x1800087f0`
- `0x18000a228`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000885b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000885b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000880a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000880a`

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
0x1800087f0  push    rbx
0x1800087f2  sub     rsp, 0E0h
0x1800087f9  mov     rbx, rcx
0x1800087fc  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008801  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008806  nop
0x180008807  mov     rcx, rbx; SRWLock
0x18000880a  call    cs:__imp_AcquireSRWLockExclusive
0x180008810  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008814  cmp     byte ptr [rdx+38h], 0
0x180008818  jz      short loc_180008824
0x18000881a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000881f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008824  cmp     byte ptr [rbx+80h], 0
0x18000882b  jz      short loc_18000883B
0x18000882d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008831  lea     rcx, [rsp+0E8h+var_88]; this
0x180008836  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000883b  cmp     byte ptr [rbx+0C0h], 0
0x180008842  jz      short loc_180008858
0x180008844  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000884b  lea     rcx, [rsp+0E8h+var_48]; this
0x180008853  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008858  mov     rcx, rbx; SRWLock
0x18000885b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008861  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008866  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000886b  nop
0x18000886c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008871  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008876  add     rsp, 0E0h
0x18000887d  pop     rbx
0x18000887e  retn
```
