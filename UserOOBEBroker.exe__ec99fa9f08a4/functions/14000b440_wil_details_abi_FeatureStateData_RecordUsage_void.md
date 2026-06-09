# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x14000b440`
- end: `0x14000b4cf`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140006c70`
- `0x14000b288`
- `0x14000d080`

## callees

- `0x140007af8`
- `0x140008240`
- `0x14000afbc`
- `0x14000b440`
- `0x14000cd10`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b45a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b45a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b4ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b4ab`

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
0x14000b440  push    rbx
0x14000b442  sub     rsp, 0E0h
0x14000b449  mov     rbx, rcx
0x14000b44c  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b451  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000b456  nop
0x14000b457  mov     rcx, rbx; SRWLock
0x14000b45a  call    cs:__imp_AcquireSRWLockExclusive
0x14000b460  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000b464  cmp     byte ptr [rdx+38h], 0
0x14000b468  jz      short loc_14000B474
0x14000b46a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b46f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b474  cmp     byte ptr [rbx+80h], 0
0x14000b47b  jz      short loc_14000B48B
0x14000b47d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000b481  lea     rcx, [rsp+0E8h+var_88]; this
0x14000b486  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b48b  cmp     byte ptr [rbx+0C0h], 0
0x14000b492  jz      short loc_14000B4A8
0x14000b494  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000b49b  lea     rcx, [rsp+0E8h+var_48]; this
0x14000b4a3  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b4a8  mov     rcx, rbx; SRWLock
0x14000b4ab  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b4b1  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4b6  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000b4bb  nop
0x14000b4bc  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4c1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000b4c6  add     rsp, 0E0h
0x14000b4cd  pop     rbx
0x14000b4ce  retn
```
