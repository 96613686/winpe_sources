# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180038d14`
- end: `0x180038de4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180038a44`

## callees

- `0x18003897c`
- `0x180038d14`
- `0x180039018`
- `0x18003a5b4`
- `0x18003bb74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038dc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038dc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038da6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038da6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038db4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038db4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180038d14  mov     [rsp+arg_0], rbx
0x180038d19  mov     [rsp+arg_8], rsi
0x180038d1e  push    rdi
0x180038d1f  sub     rsp, 0E0h
0x180038d26  mov     rbx, rcx
0x180038d29  lea     rcx, [rsp+0E8h+var_C8]; this
0x180038d2e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180038d33  cmp     byte ptr [rbx+40h], 0
0x180038d37  jz      short loc_180038D47
0x180038d39  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180038d3d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180038d42  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180038d47  cmp     byte ptr [rbx+80h], 0
0x180038d4e  jz      short loc_180038D5E
0x180038d50  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180038d54  lea     rcx, [rsp+0E8h+var_88]; this
0x180038d59  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180038d5e  cmp     byte ptr [rbx+0C0h], 0
0x180038d65  jz      short loc_180038D7B
0x180038d67  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180038d6e  lea     rcx, [rsp+0E8h+var_48]; this
0x180038d76  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180038d7b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180038d80  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180038d85  lea     rcx, [rsp+0E8h+var_C8]; this
0x180038d8a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180038d8f  mov     rsi, [rbx+108h]
0x180038d96  mov     qword ptr [rbx+108h], 0
0x180038da1  test    rsi, rsi
0x180038da4  jz      short loc_180038DBA
0x180038da6  call    cs:__imp_GetProcessHeap
0x180038dac  mov     rcx, rax; hHeap
0x180038daf  mov     r8, rsi; lpMem
0x180038db2  xor     edx, edx; dwFlags
0x180038db4  call    cs:__imp_HeapFree
0x180038dba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180038dc1  call    cs:__imp_DeleteCriticalSection
0x180038dc7  lea     rcx, [rbx+8]; this
0x180038dcb  lea     r11, [rsp+0E8h+var_8]
0x180038dd3  mov     rbx, [r11+10h]
0x180038dd7  mov     rsi, [r11+18h]
0x180038ddb  mov     rsp, r11
0x180038dde  pop     rdi
0x180038ddf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
