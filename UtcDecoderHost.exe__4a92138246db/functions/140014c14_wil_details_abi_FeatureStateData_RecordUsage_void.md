# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140014c14`
- end: `0x140014ca3`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140012310`
- `0x140014a90`
- `0x140015eb0`

## callees

- `0x140012d54`
- `0x1400134f0`
- `0x140014984`
- `0x140014c14`
- `0x140015d64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014c2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014c2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014c7f`

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
0x140014c14  push    rbx
0x140014c16  sub     rsp, 0E0h
0x140014c1d  mov     rbx, rcx
0x140014c20  lea     rcx, [rsp+0E8h+var_C8]; this
0x140014c25  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140014c2a  nop
0x140014c2b  mov     rcx, rbx; SRWLock
0x140014c2e  call    cs:__imp_AcquireSRWLockExclusive
0x140014c34  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140014c38  cmp     byte ptr [rdx+38h], 0
0x140014c3c  jz      short loc_140014C48
0x140014c3e  lea     rcx, [rsp+0E8h+var_C8]; this
0x140014c43  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140014c48  cmp     byte ptr [rbx+80h], 0
0x140014c4f  jz      short loc_140014C5F
0x140014c51  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140014c55  lea     rcx, [rsp+0E8h+var_88]; this
0x140014c5a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140014c5f  cmp     byte ptr [rbx+0C0h], 0
0x140014c66  jz      short loc_140014C7C
0x140014c68  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140014c6f  lea     rcx, [rsp+0E8h+var_48]; this
0x140014c77  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140014c7c  mov     rcx, rbx; SRWLock
0x140014c7f  call    cs:__imp_ReleaseSRWLockExclusive
0x140014c85  lea     rcx, [rsp+0E8h+var_C8]; this
0x140014c8a  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140014c8f  nop
0x140014c90  lea     rcx, [rsp+0E8h+var_C8]; this
0x140014c95  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140014c9a  add     rsp, 0E0h
0x140014ca1  pop     rbx
0x140014ca2  retn
```
