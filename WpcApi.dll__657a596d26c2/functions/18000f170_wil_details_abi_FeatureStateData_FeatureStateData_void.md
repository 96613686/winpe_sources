# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000f170`
- end: `0x18000f240`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ee74`

## callees

- `0x18000ec8c`
- `0x18000f170`
- `0x18000f4f4`
- `0x18001128c`
- `0x180013d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f21d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f21d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f210`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f210`

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
0x18000f170  mov     [rsp+arg_0], rbx
0x18000f175  mov     [rsp+arg_8], rsi
0x18000f17a  push    rdi
0x18000f17b  sub     rsp, 0E0h
0x18000f182  mov     rbx, rcx
0x18000f185  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f18a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000f18f  cmp     byte ptr [rbx+40h], 0
0x18000f193  jz      short loc_18000F1A3
0x18000f195  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000f199  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f19e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f1a3  cmp     byte ptr [rbx+80h], 0
0x18000f1aa  jz      short loc_18000F1BA
0x18000f1ac  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000f1b0  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f1b5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f1ba  cmp     byte ptr [rbx+0C0h], 0
0x18000f1c1  jz      short loc_18000F1D7
0x18000f1c3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000f1ca  lea     rcx, [rsp+0E8h+var_48]; this
0x18000f1d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f1d7  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f1dc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000f1e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f1e6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000f1eb  mov     rsi, [rbx+108h]
0x18000f1f2  mov     qword ptr [rbx+108h], 0
0x18000f1fd  test    rsi, rsi
0x18000f200  jz      short loc_18000F216
0x18000f202  call    cs:__imp_GetProcessHeap
0x18000f208  mov     rcx, rax; hHeap
0x18000f20b  mov     r8, rsi; lpMem
0x18000f20e  xor     edx, edx; dwFlags
0x18000f210  call    cs:__imp_HeapFree
0x18000f216  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000f21d  call    cs:__imp_DeleteCriticalSection
0x18000f223  lea     rcx, [rbx+8]; this
0x18000f227  lea     r11, [rsp+0E8h+var_8]
0x18000f22f  mov     rbx, [r11+10h]
0x18000f233  mov     rsi, [r11+18h]
0x18000f237  mov     rsp, r11
0x18000f23a  pop     rdi
0x18000f23b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
