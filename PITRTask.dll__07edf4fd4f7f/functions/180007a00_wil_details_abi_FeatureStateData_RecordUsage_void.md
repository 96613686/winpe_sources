# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180007a00`
- end: `0x180007ab1`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800024e0`
- `0x1800077c4`
- `0x180009f30`

## callees

- `0x180003368`
- `0x180003c88`
- `0x1800074c8`
- `0x180007a00`
- `0x180009aac`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007a7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007a2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007a2c`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  _BYTE v2[64]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v3[64]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v4[64]; // [rsp+A0h] [rbp-58h] BYREF

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
0x180007a00  push    rbx
0x180007a02  sub     rsp, 0F0h
0x180007a09  mov     rax, cs:__security_cookie
0x180007a10  xor     rax, rsp
0x180007a13  mov     [rsp+0F8h+var_18], rax
0x180007a1b  mov     rbx, rcx
0x180007a1e  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007a23  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007a28  nop
0x180007a29  mov     rcx, rbx; SRWLock
0x180007a2c  call    cs:__imp_AcquireSRWLockExclusive
0x180007a32  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180007a36  cmp     byte ptr [rdx+38h], 0
0x180007a3a  jz      short loc_180007A46
0x180007a3c  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007a41  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007a46  cmp     byte ptr [rbx+80h], 0
0x180007a4d  jz      short loc_180007A5D
0x180007a4f  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180007a53  lea     rcx, [rsp+0F8h+var_98]; this
0x180007a58  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007a5d  cmp     byte ptr [rbx+0C0h], 0
0x180007a64  jz      short loc_180007A7A
0x180007a66  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180007a6d  lea     rcx, [rsp+0F8h+var_58]; this
0x180007a75  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007a7a  mov     rcx, rbx; SRWLock
0x180007a7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007a83  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007a88  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180007a8d  nop
0x180007a8e  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007a93  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180007a98  mov     rcx, [rsp+0F8h+var_18]
0x180007aa0  xor     rcx, rsp; StackCookie
0x180007aa3  call    __security_check_cookie
0x180007aa8  add     rsp, 0F0h
0x180007aaf  pop     rbx
0x180007ab0  retn
```
