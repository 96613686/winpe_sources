# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800099c0`
- end: `0x180009a4f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800076e0`
- `0x18000983c`
- `0x18000abf0`

## callees

- `0x180007768`
- `0x180007c4c`
- `0x180009730`
- `0x1800099c0`
- `0x18000aa98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099da`

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
0x1800099c0  push    rbx
0x1800099c2  sub     rsp, 0E0h
0x1800099c9  mov     rbx, rcx
0x1800099cc  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800099d1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800099d6  nop
0x1800099d7  mov     rcx, rbx; SRWLock
0x1800099da  call    cs:__imp_AcquireSRWLockExclusive
0x1800099e0  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800099e4  cmp     byte ptr [rdx+38h], 0
0x1800099e8  jz      short loc_1800099F4
0x1800099ea  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800099ef  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800099f4  cmp     byte ptr [rbx+80h], 0
0x1800099fb  jz      short loc_180009A0B
0x1800099fd  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009a01  lea     rcx, [rsp+0E8h+var_88]; this
0x180009a06  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009a0b  cmp     byte ptr [rbx+0C0h], 0
0x180009a12  jz      short loc_180009A28
0x180009a14  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180009a1b  lea     rcx, [rsp+0E8h+var_48]; this
0x180009a23  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009a28  mov     rcx, rbx; SRWLock
0x180009a2b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a31  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009a36  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009a3b  nop
0x180009a3c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009a41  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009a46  add     rsp, 0E0h
0x180009a4d  pop     rbx
0x180009a4e  retn
```
