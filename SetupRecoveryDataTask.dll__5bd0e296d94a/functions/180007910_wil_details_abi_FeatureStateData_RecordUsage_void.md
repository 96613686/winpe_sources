# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180007910`
- end: `0x1800079c1`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800022d0`
- `0x1800076d4`
- `0x180009c50`

## callees

- `0x180002eb4`
- `0x180003718`
- `0x1800073d8`
- `0x180007910`
- `0x1800097d4`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000793c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000793c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000798d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000798d`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  _BYTE v5[64]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v6[64]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v7[64]; // [rsp+A0h] [rbp-58h] BYREF

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
0x180007910  push    rbx
0x180007912  sub     rsp, 0F0h
0x180007919  mov     rax, cs:__security_cookie
0x180007920  xor     rax, rsp
0x180007923  mov     [rsp+0F8h+var_18], rax
0x18000792b  mov     rbx, rcx
0x18000792e  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007933  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007938  nop
0x180007939  mov     rcx, rbx; SRWLock
0x18000793c  call    cs:__imp_AcquireSRWLockExclusive
0x180007942  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180007946  cmp     byte ptr [rdx+38h], 0
0x18000794a  jz      short loc_180007956
0x18000794c  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007951  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007956  cmp     byte ptr [rbx+80h], 0
0x18000795d  jz      short loc_18000796D
0x18000795f  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180007963  lea     rcx, [rsp+0F8h+var_98]; this
0x180007968  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000796d  cmp     byte ptr [rbx+0C0h], 0
0x180007974  jz      short loc_18000798A
0x180007976  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000797d  lea     rcx, [rsp+0F8h+var_58]; this
0x180007985  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000798a  mov     rcx, rbx; SRWLock
0x18000798d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007993  lea     rcx, [rsp+0F8h+var_D8]; this
0x180007998  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000799d  nop
0x18000799e  lea     rcx, [rsp+0F8h+var_D8]; this
0x1800079a3  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800079a8  mov     rcx, [rsp+0F8h+var_18]
0x1800079b0  xor     rcx, rsp; StackCookie
0x1800079b3  call    __security_check_cookie
0x1800079b8  add     rsp, 0F0h
0x1800079bf  pop     rbx
0x1800079c0  retn
```
