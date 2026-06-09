# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800086b8`
- end: `0x180008747`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007140`
- `0x180008534`
- `0x1800096a0`

## callees

- `0x1800071c8`
- `0x1800076ac`
- `0x180008428`
- `0x1800086b8`
- `0x180009550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008723`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008723`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086d2`

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
0x1800086b8  push    rbx
0x1800086ba  sub     rsp, 0E0h
0x1800086c1  mov     rbx, rcx
0x1800086c4  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800086c9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800086ce  nop
0x1800086cf  mov     rcx, rbx; SRWLock
0x1800086d2  call    cs:__imp_AcquireSRWLockExclusive
0x1800086d8  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800086dc  cmp     byte ptr [rdx+38h], 0
0x1800086e0  jz      short loc_1800086EC
0x1800086e2  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800086e7  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800086ec  cmp     byte ptr [rbx+80h], 0
0x1800086f3  jz      short loc_180008703
0x1800086f5  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800086f9  lea     rcx, [rsp+0E8h+var_88]; this
0x1800086fe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008703  cmp     byte ptr [rbx+0C0h], 0
0x18000870a  jz      short loc_180008720
0x18000870c  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008713  lea     rcx, [rsp+0E8h+var_48]; this
0x18000871b  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008720  mov     rcx, rbx; SRWLock
0x180008723  call    cs:__imp_ReleaseSRWLockExclusive
0x180008729  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000872e  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008733  nop
0x180008734  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008739  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000873e  add     rsp, 0E0h
0x180008745  pop     rbx
0x180008746  retn
```
