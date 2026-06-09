# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180009174`
- end: `0x180009203`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007180`
- `0x180008ff0`
- `0x18000a680`

## callees

- `0x180007548`
- `0x180007a48`
- `0x180008ee4`
- `0x180009174`
- `0x18000a52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000918e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000918e`

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
0x180009174  push    rbx
0x180009176  sub     rsp, 0E0h
0x18000917d  mov     rbx, rcx
0x180009180  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009185  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000918a  nop
0x18000918b  mov     rcx, rbx; SRWLock
0x18000918e  call    cs:__imp_AcquireSRWLockExclusive
0x180009194  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009198  cmp     byte ptr [rdx+38h], 0
0x18000919c  jz      short loc_1800091A8
0x18000919e  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800091a3  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091a8  cmp     byte ptr [rbx+80h], 0
0x1800091af  jz      short loc_1800091BF
0x1800091b1  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800091b5  lea     rcx, [rsp+0E8h+var_88]; this
0x1800091ba  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091bf  cmp     byte ptr [rbx+0C0h], 0
0x1800091c6  jz      short loc_1800091DC
0x1800091c8  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800091cf  lea     rcx, [rsp+0E8h+var_48]; this
0x1800091d7  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091dc  mov     rcx, rbx; SRWLock
0x1800091df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800091ea  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800091ef  nop
0x1800091f0  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800091f5  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800091fa  add     rsp, 0E0h
0x180009201  pop     rbx
0x180009202  retn
```
