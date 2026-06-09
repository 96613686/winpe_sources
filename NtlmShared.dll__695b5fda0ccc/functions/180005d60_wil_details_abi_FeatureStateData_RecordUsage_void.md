# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180005d60`
- end: `0x180005ded`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001fc0`
- `0x180005b74`
- `0x180007710`

## callees

- `0x1800029c0`
- `0x1800030e4`
- `0x180005878`
- `0x180005d60`
- `0x1800072e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d79`

## pseudocode

```c
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
0x180005d60  push    rbx
0x180005d62  sub     rsp, 0E0h
0x180005d69  mov     rbx, rcx
0x180005d6c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005d71  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005d76  mov     rcx, rbx; SRWLock
0x180005d79  call    cs:__imp_AcquireSRWLockExclusive
0x180005d7f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005d83  cmp     byte ptr [rdx+38h], 0
0x180005d87  jz      short loc_180005D93
0x180005d89  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005d8e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005d93  cmp     byte ptr [rbx+80h], 0
0x180005d9a  jz      short loc_180005DAA
0x180005d9c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005da0  lea     rcx, [rsp+0E8h+var_88]; this
0x180005da5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005daa  cmp     byte ptr [rbx+0C0h], 0
0x180005db1  jz      short loc_180005DC7
0x180005db3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005dba  lea     rcx, [rsp+0E8h+var_48]; this
0x180005dc2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005dc7  mov     rcx, rbx; SRWLock
0x180005dca  call    cs:__imp_ReleaseSRWLockExclusive
0x180005dd0  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005dd5  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005dda  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005ddf  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005de4  add     rsp, 0E0h
0x180005deb  pop     rbx
0x180005dec  retn
```
