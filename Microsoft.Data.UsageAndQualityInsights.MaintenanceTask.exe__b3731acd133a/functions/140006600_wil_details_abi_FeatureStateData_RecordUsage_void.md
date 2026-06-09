# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140006600`
- end: `0x14000668f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002450`
- `0x140006404`
- `0x1400085b0`

## callees

- `0x140002fac`
- `0x140003864`
- `0x1400060fc`
- `0x140006600`
- `0x140008144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000661a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000661a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000666b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000666b`

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
0x140006600  push    rbx
0x140006602  sub     rsp, 0E0h
0x140006609  mov     rbx, rcx
0x14000660c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006611  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006616  nop
0x140006617  mov     rcx, rbx; SRWLock
0x14000661a  call    cs:__imp_AcquireSRWLockExclusive
0x140006620  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140006624  cmp     byte ptr [rdx+38h], 0
0x140006628  jz      short loc_140006634
0x14000662a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000662f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006634  cmp     byte ptr [rbx+80h], 0
0x14000663b  jz      short loc_14000664B
0x14000663d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140006641  lea     rcx, [rsp+0E8h+var_88]; this
0x140006646  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000664b  cmp     byte ptr [rbx+0C0h], 0
0x140006652  jz      short loc_140006668
0x140006654  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000665b  lea     rcx, [rsp+0E8h+var_48]; this
0x140006663  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006668  mov     rcx, rbx; SRWLock
0x14000666b  call    cs:__imp_ReleaseSRWLockExclusive
0x140006671  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006676  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000667b  nop
0x14000667c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006681  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140006686  add     rsp, 0E0h
0x14000668d  pop     rbx
0x14000668e  retn
```
