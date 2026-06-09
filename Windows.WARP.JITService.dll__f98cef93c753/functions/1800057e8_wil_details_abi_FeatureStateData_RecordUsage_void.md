# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800057e8`
- end: `0x180005877`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006050`
- `0x180007030`

## callees

- `0x1800044ec`
- `0x18000531c`
- `0x1800053e4`
- `0x1800057e8`
- `0x180005880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005802`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005802`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005853`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005853`

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
0x1800057e8  push    rbx
0x1800057ea  sub     rsp, 0E0h
0x1800057f1  mov     rbx, rcx
0x1800057f4  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800057f9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800057fe  nop
0x1800057ff  mov     rcx, rbx; SRWLock
0x180005802  call    cs:__imp_AcquireSRWLockExclusive
0x180005808  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000580c  cmp     byte ptr [rdx+38h], 0
0x180005810  jz      short loc_18000581C
0x180005812  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005817  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000581c  cmp     byte ptr [rbx+80h], 0
0x180005823  jz      short loc_180005833
0x180005825  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005829  lea     rcx, [rsp+0E8h+var_88]; this
0x18000582e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005833  cmp     byte ptr [rbx+0C0h], 0
0x18000583a  jz      short loc_180005850
0x18000583c  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005843  lea     rcx, [rsp+0E8h+var_48]; this
0x18000584b  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005850  mov     rcx, rbx; SRWLock
0x180005853  call    cs:__imp_ReleaseSRWLockExclusive
0x180005859  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000585e  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005863  nop
0x180005864  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005869  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000586e  add     rsp, 0E0h
0x180005875  pop     rbx
0x180005876  retn
```
