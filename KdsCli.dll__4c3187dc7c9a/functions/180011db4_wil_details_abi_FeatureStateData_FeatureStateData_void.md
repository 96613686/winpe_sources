# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180011db4`
- end: `0x180011e84`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011cc0`

## callees

- `0x180011b2c`
- `0x180011db4`
- `0x180012104`
- `0x180014694`
- `0x180015cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011e61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011e61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e46`

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
0x180011db4  mov     [rsp+arg_0], rbx
0x180011db9  mov     [rsp+arg_8], rsi
0x180011dbe  push    rdi
0x180011dbf  sub     rsp, 0E0h
0x180011dc6  mov     rbx, rcx
0x180011dc9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011dce  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011dd3  cmp     byte ptr [rbx+40h], 0
0x180011dd7  jz      short loc_180011DE7
0x180011dd9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180011ddd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011de2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011de7  cmp     byte ptr [rbx+80h], 0
0x180011dee  jz      short loc_180011DFE
0x180011df0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180011df4  lea     rcx, [rsp+0E8h+var_88]; this
0x180011df9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011dfe  cmp     byte ptr [rbx+0C0h], 0
0x180011e05  jz      short loc_180011E1B
0x180011e07  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180011e0e  lea     rcx, [rsp+0E8h+var_48]; this
0x180011e16  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011e1b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e20  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180011e25  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e2a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180011e2f  mov     rsi, [rbx+108h]
0x180011e36  mov     qword ptr [rbx+108h], 0
0x180011e41  test    rsi, rsi
0x180011e44  jz      short loc_180011E5A
0x180011e46  call    cs:__imp_GetProcessHeap
0x180011e4c  mov     r8, rsi; lpMem
0x180011e4f  xor     edx, edx; dwFlags
0x180011e51  mov     rcx, rax; hHeap
0x180011e54  call    cs:__imp_HeapFree
0x180011e5a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180011e61  call    cs:__imp_DeleteCriticalSection
0x180011e67  lea     rcx, [rbx+8]; this
0x180011e6b  lea     r11, [rsp+0E8h+var_8]
0x180011e73  mov     rbx, [r11+10h]
0x180011e77  mov     rsi, [r11+18h]
0x180011e7b  mov     rsp, r11
0x180011e7e  pop     rdi
0x180011e7f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
