# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000cde8`
- end: `0x18000ceb8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800100dc`

## callees

- `0x18000caac`
- `0x18000cde8`
- `0x18000d0ec`
- `0x18000f254`
- `0x180010a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ce95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ce95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce88`

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
0x18000cde8  mov     [rsp+arg_0], rbx
0x18000cded  mov     [rsp+arg_8], rsi
0x18000cdf2  push    rdi
0x18000cdf3  sub     rsp, 0E0h
0x18000cdfa  mov     rbx, rcx
0x18000cdfd  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ce02  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ce07  cmp     byte ptr [rbx+40h], 0
0x18000ce0b  jz      short loc_18000CE1B
0x18000ce0d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000ce11  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ce16  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ce1b  cmp     byte ptr [rbx+80h], 0
0x18000ce22  jz      short loc_18000CE32
0x18000ce24  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000ce28  lea     rcx, [rsp+0E8h+var_88]; this
0x18000ce2d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ce32  cmp     byte ptr [rbx+0C0h], 0
0x18000ce39  jz      short loc_18000CE4F
0x18000ce3b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000ce42  lea     rcx, [rsp+0E8h+var_48]; this
0x18000ce4a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ce4f  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ce54  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000ce59  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ce5e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000ce63  mov     rsi, [rbx+108h]
0x18000ce6a  mov     qword ptr [rbx+108h], 0
0x18000ce75  test    rsi, rsi
0x18000ce78  jz      short loc_18000CE8E
0x18000ce7a  call    cs:__imp_GetProcessHeap
0x18000ce80  mov     rcx, rax; hHeap
0x18000ce83  mov     r8, rsi; lpMem
0x18000ce86  xor     edx, edx; dwFlags
0x18000ce88  call    cs:__imp_HeapFree
0x18000ce8e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000ce95  call    cs:__imp_DeleteCriticalSection
0x18000ce9b  lea     rcx, [rbx+8]; this
0x18000ce9f  lea     r11, [rsp+0E8h+var_8]
0x18000cea7  mov     rbx, [r11+10h]
0x18000ceab  mov     rsi, [r11+18h]
0x18000ceaf  mov     rsp, r11
0x18000ceb2  pop     rdi
0x18000ceb3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
