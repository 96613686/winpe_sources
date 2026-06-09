# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180008900`
- end: `0x180008992`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002210`
- `0x180008704`
- `0x18000ab20`

## callees

- `0x18000301c`
- `0x1800040b8`
- `0x180008408`
- `0x180008900`
- `0x18000a2d8`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000896d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000896d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000891a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000891a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180008900  push    rbx
0x180008902  sub     rsp, 0E0h
0x180008909  mov     rbx, rcx
0x18000890c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008911  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008916  nop
0x180008917  mov     rcx, rbx; SRWLock
0x18000891a  call    cs:__imp_AcquireSRWLockExclusive
0x180008920  nop
0x180008921  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008925  cmp     byte ptr [rdx+38h], 0
0x180008929  jz      short loc_180008935
0x18000892b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008930  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008935  cmp     byte ptr [rbx+80h], 0
0x18000893c  jz      short loc_18000894C
0x18000893e  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008942  lea     rcx, [rsp+0E8h+var_88]; this
0x180008947  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000894c  cmp     byte ptr [rbx+0C0h], 0
0x180008953  jz      short loc_18000896A
0x180008955  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000895c  lea     rcx, [rsp+0E8h+var_48]; this
0x180008964  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008969  nop
0x18000896a  mov     rcx, rbx; SRWLock
0x18000896d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008973  nop
0x180008974  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008979  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000897e  nop
0x18000897f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008984  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008989  add     rsp, 0E0h
0x180008990  pop     rbx
0x180008991  retn
```
