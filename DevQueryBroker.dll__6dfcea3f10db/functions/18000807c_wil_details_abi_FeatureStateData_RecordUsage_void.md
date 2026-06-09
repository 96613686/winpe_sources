# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000807c`
- end: `0x180008109`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048f0`
- `0x180007ec4`
- `0x1800097c0`

## callees

- `0x18000525c`
- `0x180005834`
- `0x180007d7c`
- `0x18000807c`
- `0x180009400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008095`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008095`

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
0x18000807c  push    rbx
0x18000807e  sub     rsp, 0E0h
0x180008085  mov     rbx, rcx
0x180008088  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000808d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008092  mov     rcx, rbx; SRWLock
0x180008095  call    cs:__imp_AcquireSRWLockExclusive
0x18000809b  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000809f  cmp     byte ptr [rdx+38h], 0
0x1800080a3  jz      short loc_1800080AF
0x1800080a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800080aa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800080af  cmp     byte ptr [rbx+80h], 0
0x1800080b6  jz      short loc_1800080C6
0x1800080b8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800080bc  lea     rcx, [rsp+0E8h+var_88]; this
0x1800080c1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800080c6  cmp     byte ptr [rbx+0C0h], 0
0x1800080cd  jz      short loc_1800080E3
0x1800080cf  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800080d6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800080de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800080e3  mov     rcx, rbx; SRWLock
0x1800080e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080ec  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800080f1  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800080f6  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800080fb  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008100  add     rsp, 0E0h
0x180008107  pop     rbx
0x180008108  retn
```
