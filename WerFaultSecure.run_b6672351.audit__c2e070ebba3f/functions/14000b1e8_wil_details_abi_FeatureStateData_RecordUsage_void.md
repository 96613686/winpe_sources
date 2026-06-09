# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x14000b1e8`
- end: `0x14000b277`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007e60`
- `0x14000b064`
- `0x14000d7a0`

## callees

- `0x140008654`
- `0x140008ca8`
- `0x14000af58`
- `0x14000b1e8`
- `0x14000c754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b202`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b202`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b253`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b253`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14000b1e8  push    rbx
0x14000b1ea  sub     rsp, 0E0h
0x14000b1f1  mov     rbx, rcx
0x14000b1f4  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b1f9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000b1fe  nop
0x14000b1ff  mov     rcx, rbx; SRWLock
0x14000b202  call    cs:__imp_AcquireSRWLockExclusive
0x14000b208  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000b20c  cmp     byte ptr [rdx+38h], 0
0x14000b210  jz      short loc_14000B21C
0x14000b212  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b217  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b21c  cmp     byte ptr [rbx+80h], 0
0x14000b223  jz      short loc_14000B233
0x14000b225  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000b229  lea     rcx, [rsp+0E8h+var_88]; this
0x14000b22e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b233  cmp     byte ptr [rbx+0C0h], 0
0x14000b23a  jz      short loc_14000B250
0x14000b23c  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000b243  lea     rcx, [rsp+0E8h+var_48]; this
0x14000b24b  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b250  mov     rcx, rbx; SRWLock
0x14000b253  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b259  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b25e  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000b263  nop
0x14000b264  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b269  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000b26e  add     rsp, 0E0h
0x14000b275  pop     rbx
0x14000b276  retn
```
