# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010fb8`
- end: `0x18001109a`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014d30`

## callees

- `0x180010c5c`
- `0x180010fb8`
- `0x1800114b4`
- `0x180013ee0`
- `0x180015cb8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001105e`
- `KERNEL32!HeapFree` at `0x18001105e`
- `KERNEL32!GetProcessHeap` at `0x18001104a`
- `KERNEL32!GetProcessHeap` at `0x18001104a`
- `KERNEL32!DeleteCriticalSection` at `0x180011071`
- `KERNEL32!DeleteCriticalSection` at `0x180011071`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v4[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v6[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  v2 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x180010fb8  mov     [rsp+arg_0], rbx
0x180010fbd  mov     [rsp+arg_8], rsi
0x180010fc2  push    rdi
0x180010fc3  sub     rsp, 0E0h
0x180010fca  mov     rbx, rcx
0x180010fcd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010fd2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010fd7  cmp     byte ptr [rbx+40h], 0
0x180010fdb  jz      short loc_180010FEB
0x180010fdd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180010fe1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010fe6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010feb  cmp     byte ptr [rbx+80h], 0
0x180010ff2  jz      short loc_180011002
0x180010ff4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010ff8  lea     rcx, [rsp+0E8h+var_88]; this
0x180010ffd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011002  cmp     byte ptr [rbx+0C0h], 0
0x180011009  jz      short loc_18001101F
0x18001100b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180011012  lea     rcx, [rsp+0E8h+var_48]; this
0x18001101a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001101f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011024  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180011029  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001102e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180011033  mov     rsi, [rbx+108h]
0x18001103a  mov     qword ptr [rbx+108h], 0
0x180011045  test    rsi, rsi
0x180011048  jz      short loc_18001106A
0x18001104a  call    cs:__imp_GetProcessHeap
0x180011051  nop     dword ptr [rax+rax+00h]
0x180011056  mov     rcx, rax; hHeap
0x180011059  mov     r8, rsi; lpMem
0x18001105c  xor     edx, edx; dwFlags
0x18001105e  call    cs:__imp_HeapFree
0x180011065  nop     dword ptr [rax+rax+00h]
0x18001106a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180011071  call    cs:__imp_DeleteCriticalSection
0x180011078  nop     dword ptr [rax+rax+00h]
0x18001107d  lea     rcx, [rbx+8]; this
0x180011081  lea     r11, [rsp+0E8h+var_8]
0x180011089  mov     rbx, [r11+10h]
0x18001108d  mov     rsi, [r11+18h]
0x180011091  mov     rsp, r11
0x180011094  pop     rdi
0x180011095  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
