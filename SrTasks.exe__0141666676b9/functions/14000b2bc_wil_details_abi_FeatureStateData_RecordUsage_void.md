# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x14000b2bc`
- end: `0x14000b349`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007be0`
- `0x14000b104`
- `0x14000c8d0`

## callees

- `0x14000854c`
- `0x140008b24`
- `0x14000afc8`
- `0x14000b2bc`
- `0x14000c504`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b2d5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b2d5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b326`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b326`

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
0x14000b2bc  push    rbx
0x14000b2be  sub     rsp, 0E0h
0x14000b2c5  mov     rbx, rcx
0x14000b2c8  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b2cd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000b2d2  mov     rcx, rbx; SRWLock
0x14000b2d5  call    cs:__imp_AcquireSRWLockExclusive
0x14000b2db  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000b2df  cmp     byte ptr [rdx+38h], 0
0x14000b2e3  jz      short loc_14000B2EF
0x14000b2e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b2ea  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b2ef  cmp     byte ptr [rbx+80h], 0
0x14000b2f6  jz      short loc_14000B306
0x14000b2f8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000b2fc  lea     rcx, [rsp+0E8h+var_88]; this
0x14000b301  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b306  cmp     byte ptr [rbx+0C0h], 0
0x14000b30d  jz      short loc_14000B323
0x14000b30f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000b316  lea     rcx, [rsp+0E8h+var_48]; this
0x14000b31e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b323  mov     rcx, rbx; SRWLock
0x14000b326  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b32c  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b331  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000b336  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b33b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000b340  add     rsp, 0E0h
0x14000b347  pop     rbx
0x14000b348  retn
```
