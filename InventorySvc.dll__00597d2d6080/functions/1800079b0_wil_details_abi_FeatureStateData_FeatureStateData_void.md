# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800079b0`
- end: `0x180007a80`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e74c`

## callees

- `0x18000724c`
- `0x1800079b0`
- `0x180007e8c`
- `0x18000d71c`
- `0x18000fb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a50`

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
0x1800079b0  mov     [rsp+arg_0], rbx
0x1800079b5  mov     [rsp+arg_8], rsi
0x1800079ba  push    rdi
0x1800079bb  sub     rsp, 0E0h
0x1800079c2  mov     rbx, rcx
0x1800079c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800079ca  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800079cf  cmp     byte ptr [rbx+40h], 0
0x1800079d3  jz      short loc_1800079E3
0x1800079d5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800079d9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800079de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800079e3  cmp     byte ptr [rbx+80h], 0
0x1800079ea  jz      short loc_1800079FA
0x1800079ec  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800079f0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800079f5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800079fa  cmp     byte ptr [rbx+0C0h], 0
0x180007a01  jz      short loc_180007A17
0x180007a03  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180007a0a  lea     rcx, [rsp+0E8h+var_48]; this
0x180007a12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007a17  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007a1c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180007a21  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007a26  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180007a2b  mov     rsi, [rbx+108h]
0x180007a32  mov     qword ptr [rbx+108h], 0
0x180007a3d  test    rsi, rsi
0x180007a40  jz      short loc_180007A56
0x180007a42  call    cs:__imp_GetProcessHeap
0x180007a48  mov     rcx, rax; hHeap
0x180007a4b  mov     r8, rsi; lpMem
0x180007a4e  xor     edx, edx; dwFlags
0x180007a50  call    cs:__imp_HeapFree
0x180007a56  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180007a5d  call    cs:__imp_DeleteCriticalSection
0x180007a63  lea     rcx, [rbx+8]; this
0x180007a67  lea     r11, [rsp+0E8h+var_8]
0x180007a6f  mov     rbx, [r11+10h]
0x180007a73  mov     rsi, [r11+18h]
0x180007a77  mov     rsp, r11
0x180007a7a  pop     rdi
0x180007a7b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
