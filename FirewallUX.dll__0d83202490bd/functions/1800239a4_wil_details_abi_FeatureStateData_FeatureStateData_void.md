# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800239a4`
- end: `0x180023a74`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002388c`

## callees

- `0x1800237c4`
- `0x1800239a4`
- `0x180023ca8`
- `0x1800249a8`
- `0x180025ac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023a51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023a51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023a36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a44`

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
0x1800239a4  mov     [rsp+arg_0], rbx
0x1800239a9  mov     [rsp+arg_8], rsi
0x1800239ae  push    rdi
0x1800239af  sub     rsp, 0E0h
0x1800239b6  mov     rbx, rcx
0x1800239b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800239be  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800239c3  cmp     byte ptr [rbx+40h], 0
0x1800239c7  jz      short loc_1800239D7
0x1800239c9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800239cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800239d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800239d7  cmp     byte ptr [rbx+80h], 0
0x1800239de  jz      short loc_1800239EE
0x1800239e0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800239e4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800239e9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800239ee  cmp     byte ptr [rbx+0C0h], 0
0x1800239f5  jz      short loc_180023A0B
0x1800239f7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800239fe  lea     rcx, [rsp+0E8h+var_48]; this
0x180023a06  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180023a0b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180023a10  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180023a15  lea     rcx, [rsp+0E8h+var_C8]; this
0x180023a1a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180023a1f  mov     rsi, [rbx+108h]
0x180023a26  mov     qword ptr [rbx+108h], 0
0x180023a31  test    rsi, rsi
0x180023a34  jz      short loc_180023A4A
0x180023a36  call    cs:__imp_GetProcessHeap
0x180023a3c  mov     rcx, rax; hHeap
0x180023a3f  mov     r8, rsi; lpMem
0x180023a42  xor     edx, edx; dwFlags
0x180023a44  call    cs:__imp_HeapFree
0x180023a4a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180023a51  call    cs:__imp_DeleteCriticalSection
0x180023a57  lea     rcx, [rbx+8]; this
0x180023a5b  lea     r11, [rsp+0E8h+var_8]
0x180023a63  mov     rbx, [r11+10h]
0x180023a67  mov     rsi, [r11+18h]
0x180023a6b  mov     rsp, r11
0x180023a6e  pop     rdi
0x180023a6f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
