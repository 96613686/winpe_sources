# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180005b40`
- end: `0x180005bda`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002360`
- `0x18000595c`
- `0x1800074b0`

## callees

- `0x180002d04`
- `0x1800031ec`
- `0x180005830`
- `0x180005b40`
- `0x180007000`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180005b59`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005b59`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005bb0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005bb0`

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
0x180005b40  push    rbx
0x180005b42  sub     rsp, 0E0h
0x180005b49  mov     rbx, rcx
0x180005b4c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005b51  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005b56  mov     rcx, rbx; SRWLock
0x180005b59  call    cs:__imp_AcquireSRWLockExclusive
0x180005b60  nop     dword ptr [rax+rax+00h]
0x180005b65  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005b69  cmp     byte ptr [rdx+38h], 0
0x180005b6d  jz      short loc_180005B79
0x180005b6f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005b74  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005b79  cmp     byte ptr [rbx+80h], 0
0x180005b80  jz      short loc_180005B90
0x180005b82  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005b86  lea     rcx, [rsp+0E8h+var_88]; this
0x180005b8b  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005b90  cmp     byte ptr [rbx+0C0h], 0
0x180005b97  jz      short loc_180005BAD
0x180005b99  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005ba0  lea     rcx, [rsp+0E8h+var_48]; this
0x180005ba8  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005bad  mov     rcx, rbx; SRWLock
0x180005bb0  call    cs:__imp_ReleaseSRWLockExclusive
0x180005bb7  nop     dword ptr [rax+rax+00h]
0x180005bbc  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005bc1  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005bc6  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005bcb  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005bd0  add     rsp, 0E0h
0x180005bd7  pop     rbx
0x180005bd8  retn
```
