# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140009804`
- end: `0x140009893`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400069f0`
- `0x140009680`
- `0x14000b650`

## callees

- `0x140007004`
- `0x140007724`
- `0x140009574`
- `0x140009804`
- `0x14000b254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000986f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000986f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000981e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000981e`

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
0x140009804  push    rbx
0x140009806  sub     rsp, 0E0h
0x14000980d  mov     rbx, rcx
0x140009810  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009815  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000981a  nop
0x14000981b  mov     rcx, rbx; SRWLock
0x14000981e  call    cs:__imp_AcquireSRWLockExclusive
0x140009824  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140009828  cmp     byte ptr [rdx+38h], 0
0x14000982c  jz      short loc_140009838
0x14000982e  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009833  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140009838  cmp     byte ptr [rbx+80h], 0
0x14000983f  jz      short loc_14000984F
0x140009841  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140009845  lea     rcx, [rsp+0E8h+var_88]; this
0x14000984a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000984f  cmp     byte ptr [rbx+0C0h], 0
0x140009856  jz      short loc_14000986C
0x140009858  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000985f  lea     rcx, [rsp+0E8h+var_48]; this
0x140009867  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000986c  mov     rcx, rbx; SRWLock
0x14000986f  call    cs:__imp_ReleaseSRWLockExclusive
0x140009875  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000987a  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000987f  nop
0x140009880  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009885  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000988a  add     rsp, 0E0h
0x140009891  pop     rbx
0x140009892  retn
```
