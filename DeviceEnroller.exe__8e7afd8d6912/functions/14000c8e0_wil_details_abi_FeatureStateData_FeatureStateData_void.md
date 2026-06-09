# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14000c8e0`
- end: `0x14000c9b0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c1b0`

## callees

- `0x14000bec0`
- `0x14000c8e0`
- `0x14000cc3c`
- `0x14001535c`
- `0x140018ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000c98d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000c98d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c980`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c980`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c972`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c972`

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
0x14000c8e0  mov     [rsp+arg_0], rbx
0x14000c8e5  mov     [rsp+arg_8], rsi
0x14000c8ea  push    rdi
0x14000c8eb  sub     rsp, 0E0h
0x14000c8f2  mov     rbx, rcx
0x14000c8f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c8fa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000c8ff  cmp     byte ptr [rbx+40h], 0
0x14000c903  jz      short loc_14000C913
0x14000c905  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000c909  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c90e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c913  cmp     byte ptr [rbx+80h], 0
0x14000c91a  jz      short loc_14000C92A
0x14000c91c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000c920  lea     rcx, [rsp+0E8h+var_88]; this
0x14000c925  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c92a  cmp     byte ptr [rbx+0C0h], 0
0x14000c931  jz      short loc_14000C947
0x14000c933  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000c93a  lea     rcx, [rsp+0E8h+var_48]; this
0x14000c942  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c947  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c94c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000c951  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c956  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000c95b  mov     rsi, [rbx+108h]
0x14000c962  mov     qword ptr [rbx+108h], 0
0x14000c96d  test    rsi, rsi
0x14000c970  jz      short loc_14000C986
0x14000c972  call    cs:__imp_GetProcessHeap
0x14000c978  mov     rcx, rax; hHeap
0x14000c97b  mov     r8, rsi; lpMem
0x14000c97e  xor     edx, edx; dwFlags
0x14000c980  call    cs:__imp_HeapFree
0x14000c986  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000c98d  call    cs:__imp_DeleteCriticalSection
0x14000c993  lea     rcx, [rbx+8]; this
0x14000c997  lea     r11, [rsp+0E8h+var_8]
0x14000c99f  mov     rbx, [r11+10h]
0x14000c9a3  mov     rsi, [r11+18h]
0x14000c9a7  mov     rsp, r11
0x14000c9aa  pop     rdi
0x14000c9ab  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
