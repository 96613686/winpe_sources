# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1400104d0`
- end: `0x14001055d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140005860`
- `0x140010314`
- `0x140011920`

## callees

- `0x140005ba8`
- `0x14000627c`
- `0x14001004c`
- `0x1400104d0`
- `0x14001175c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001053a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001053a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400104e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400104e9`

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
0x1400104d0  push    rbx
0x1400104d2  sub     rsp, 0E0h
0x1400104d9  mov     rbx, rcx
0x1400104dc  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400104e1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400104e6  mov     rcx, rbx; SRWLock
0x1400104e9  call    cs:__imp_AcquireSRWLockExclusive
0x1400104ef  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400104f3  cmp     byte ptr [rdx+38h], 0
0x1400104f7  jz      short loc_140010503
0x1400104f9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400104fe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140010503  cmp     byte ptr [rbx+80h], 0
0x14001050a  jz      short loc_14001051A
0x14001050c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140010510  lea     rcx, [rsp+0E8h+var_88]; this
0x140010515  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14001051a  cmp     byte ptr [rbx+0C0h], 0
0x140010521  jz      short loc_140010537
0x140010523  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14001052a  lea     rcx, [rsp+0E8h+var_48]; this
0x140010532  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140010537  mov     rcx, rbx; SRWLock
0x14001053a  call    cs:__imp_ReleaseSRWLockExclusive
0x140010540  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010545  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14001054a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14001054f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140010554  add     rsp, 0E0h
0x14001055b  pop     rbx
0x14001055c  retn
```
