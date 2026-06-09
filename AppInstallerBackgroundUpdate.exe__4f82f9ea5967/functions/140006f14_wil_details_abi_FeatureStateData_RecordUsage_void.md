# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140006f14`
- end: `0x140006fa3`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140005980`
- `0x140006d90`
- `0x140007ee0`

## callees

- `0x140005a08`
- `0x140005eec`
- `0x140006c84`
- `0x140006f14`
- `0x140007d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006f7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006f7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006f2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006f2e`

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
0x140006f14  push    rbx
0x140006f16  sub     rsp, 0E0h
0x140006f1d  mov     rbx, rcx
0x140006f20  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006f25  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006f2a  nop
0x140006f2b  mov     rcx, rbx; SRWLock
0x140006f2e  call    cs:__imp_AcquireSRWLockExclusive
0x140006f34  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140006f38  cmp     byte ptr [rdx+38h], 0
0x140006f3c  jz      short loc_140006F48
0x140006f3e  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006f43  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006f48  cmp     byte ptr [rbx+80h], 0
0x140006f4f  jz      short loc_140006F5F
0x140006f51  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140006f55  lea     rcx, [rsp+0E8h+var_88]; this
0x140006f5a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006f5f  cmp     byte ptr [rbx+0C0h], 0
0x140006f66  jz      short loc_140006F7C
0x140006f68  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140006f6f  lea     rcx, [rsp+0E8h+var_48]; this
0x140006f77  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006f7c  mov     rcx, rbx; SRWLock
0x140006f7f  call    cs:__imp_ReleaseSRWLockExclusive
0x140006f85  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006f8a  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140006f8f  nop
0x140006f90  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006f95  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140006f9a  add     rsp, 0E0h
0x140006fa1  pop     rbx
0x140006fa2  retn
```
