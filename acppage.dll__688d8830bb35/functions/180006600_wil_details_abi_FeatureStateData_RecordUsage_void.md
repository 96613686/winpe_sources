# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180006600`
- end: `0x18000668d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002520`
- `0x180006414`
- `0x180007d70`

## callees

- `0x180002f20`
- `0x1800036f0`
- `0x180006118`
- `0x180006600`
- `0x180007918`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000666a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000666a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006619`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006619`

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
0x180006600  push    rbx
0x180006602  sub     rsp, 0E0h
0x180006609  mov     rbx, rcx
0x18000660c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006611  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006616  mov     rcx, rbx; SRWLock
0x180006619  call    cs:__imp_AcquireSRWLockExclusive
0x18000661f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006623  cmp     byte ptr [rdx+38h], 0
0x180006627  jz      short loc_180006633
0x180006629  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000662e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006633  cmp     byte ptr [rbx+80h], 0
0x18000663a  jz      short loc_18000664A
0x18000663c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006640  lea     rcx, [rsp+0E8h+var_88]; this
0x180006645  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000664a  cmp     byte ptr [rbx+0C0h], 0
0x180006651  jz      short loc_180006667
0x180006653  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000665a  lea     rcx, [rsp+0E8h+var_48]; this
0x180006662  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006667  mov     rcx, rbx; SRWLock
0x18000666a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006670  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006675  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000667a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000667f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006684  add     rsp, 0E0h
0x18000668b  pop     rbx
0x18000668c  retn
```
