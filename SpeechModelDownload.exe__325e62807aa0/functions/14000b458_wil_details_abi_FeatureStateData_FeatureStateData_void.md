# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14000b458`
- end: `0x14000b528`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b13c`

## callees

- `0x14000b050`
- `0x14000b458`
- `0x14000b75c`
- `0x140010e84`
- `0x1400124a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b505`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b505`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b4ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b4f8`

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
0x14000b458  mov     [rsp+arg_0], rbx
0x14000b45d  mov     [rsp+arg_8], rsi
0x14000b462  push    rdi
0x14000b463  sub     rsp, 0E0h
0x14000b46a  mov     rbx, rcx
0x14000b46d  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b472  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000b477  cmp     byte ptr [rbx+40h], 0
0x14000b47b  jz      short loc_14000B48B
0x14000b47d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000b481  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b486  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b48b  cmp     byte ptr [rbx+80h], 0
0x14000b492  jz      short loc_14000B4A2
0x14000b494  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000b498  lea     rcx, [rsp+0E8h+var_88]; this
0x14000b49d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b4a2  cmp     byte ptr [rbx+0C0h], 0
0x14000b4a9  jz      short loc_14000B4BF
0x14000b4ab  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000b4b2  lea     rcx, [rsp+0E8h+var_48]; this
0x14000b4ba  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b4bf  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4c4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000b4c9  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4ce  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000b4d3  mov     rsi, [rbx+108h]
0x14000b4da  mov     qword ptr [rbx+108h], 0
0x14000b4e5  test    rsi, rsi
0x14000b4e8  jz      short loc_14000B4FE
0x14000b4ea  call    cs:__imp_GetProcessHeap
0x14000b4f0  mov     rcx, rax; hHeap
0x14000b4f3  mov     r8, rsi; lpMem
0x14000b4f6  xor     edx, edx; dwFlags
0x14000b4f8  call    cs:__imp_HeapFree
0x14000b4fe  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000b505  call    cs:__imp_DeleteCriticalSection
0x14000b50b  lea     rcx, [rbx+8]; this
0x14000b50f  lea     r11, [rsp+0E8h+var_8]
0x14000b517  mov     rbx, [r11+10h]
0x14000b51b  mov     rsi, [r11+18h]
0x14000b51f  mov     rsp, r11
0x14000b522  pop     rdi
0x14000b523  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
