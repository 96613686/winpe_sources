# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14005eec4`
- end: `0x14005ef94`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14005ed9c`

## callees

- `0x14005ecd4`
- `0x14005eec4`
- `0x14005f1c8`
- `0x1400618a4`
- `0x140062b0c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14005ef56`
- `KERNEL32!GetProcessHeap` at `0x14005ef56`
- `KERNEL32!DeleteCriticalSection` at `0x14005ef71`
- `KERNEL32!DeleteCriticalSection` at `0x14005ef71`
- `KERNEL32!HeapFree` at `0x14005ef64`
- `KERNEL32!HeapFree` at `0x14005ef64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14005eec4  mov     [rsp+arg_0], rbx
0x14005eec9  mov     [rsp+arg_8], rsi
0x14005eece  push    rdi
0x14005eecf  sub     rsp, 0E0h
0x14005eed6  mov     rbx, rcx
0x14005eed9  lea     rcx, [rsp+0E8h+var_C8]; this
0x14005eede  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14005eee3  cmp     byte ptr [rbx+40h], 0
0x14005eee7  jz      short loc_14005EEF7
0x14005eee9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14005eeed  lea     rcx, [rsp+0E8h+var_C8]; this
0x14005eef2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14005eef7  cmp     byte ptr [rbx+80h], 0
0x14005eefe  jz      short loc_14005EF0E
0x14005ef00  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14005ef04  lea     rcx, [rsp+0E8h+var_88]; this
0x14005ef09  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14005ef0e  cmp     byte ptr [rbx+0C0h], 0
0x14005ef15  jz      short loc_14005EF2B
0x14005ef17  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14005ef1e  lea     rcx, [rsp+0E8h+var_48]; this
0x14005ef26  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14005ef2b  lea     rcx, [rsp+0E8h+var_C8]; this
0x14005ef30  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14005ef35  lea     rcx, [rsp+0E8h+var_C8]; this
0x14005ef3a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14005ef3f  mov     rsi, [rbx+108h]
0x14005ef46  mov     qword ptr [rbx+108h], 0
0x14005ef51  test    rsi, rsi
0x14005ef54  jz      short loc_14005EF6A
0x14005ef56  call    cs:__imp_GetProcessHeap
0x14005ef5c  mov     rcx, rax; hHeap
0x14005ef5f  mov     r8, rsi; lpMem
0x14005ef62  xor     edx, edx; dwFlags
0x14005ef64  call    cs:__imp_HeapFree
0x14005ef6a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14005ef71  call    cs:__imp_DeleteCriticalSection
0x14005ef77  lea     rcx, [rbx+8]; this
0x14005ef7b  lea     r11, [rsp+0E8h+var_8]
0x14005ef83  mov     rbx, [r11+10h]
0x14005ef87  mov     rsi, [r11+18h]
0x14005ef8b  mov     rsp, r11
0x14005ef8e  pop     rdi
0x14005ef8f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
