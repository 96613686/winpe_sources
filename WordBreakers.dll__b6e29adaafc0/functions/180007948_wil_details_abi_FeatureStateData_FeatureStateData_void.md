# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180007948`
- end: `0x180007a18`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007830`

## callees

- `0x180007768`
- `0x180007948`
- `0x180007c4c`
- `0x180009730`
- `0x18000aa98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079e8`

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
0x180007948  mov     [rsp+arg_0], rbx
0x18000794d  mov     [rsp+arg_8], rsi
0x180007952  push    rdi
0x180007953  sub     rsp, 0E0h
0x18000795a  mov     rbx, rcx
0x18000795d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007962  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007967  cmp     byte ptr [rbx+40h], 0
0x18000796b  jz      short loc_18000797B
0x18000796d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180007971  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007976  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000797b  cmp     byte ptr [rbx+80h], 0
0x180007982  jz      short loc_180007992
0x180007984  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180007988  lea     rcx, [rsp+0E8h+var_88]; this
0x18000798d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007992  cmp     byte ptr [rbx+0C0h], 0
0x180007999  jz      short loc_1800079AF
0x18000799b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800079a2  lea     rcx, [rsp+0E8h+var_48]; this
0x1800079aa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800079af  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800079b4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800079b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800079be  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800079c3  mov     rsi, [rbx+108h]
0x1800079ca  mov     qword ptr [rbx+108h], 0
0x1800079d5  test    rsi, rsi
0x1800079d8  jz      short loc_1800079EE
0x1800079da  call    cs:__imp_GetProcessHeap
0x1800079e0  mov     rcx, rax; hHeap
0x1800079e3  mov     r8, rsi; lpMem
0x1800079e6  xor     edx, edx; dwFlags
0x1800079e8  call    cs:__imp_HeapFree
0x1800079ee  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800079f5  call    cs:__imp_DeleteCriticalSection
0x1800079fb  lea     rcx, [rbx+8]; this
0x1800079ff  lea     r11, [rsp+0E8h+var_8]
0x180007a07  mov     rbx, [r11+10h]
0x180007a0b  mov     rsi, [r11+18h]
0x180007a0f  mov     rsp, r11
0x180007a12  pop     rdi
0x180007a13  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
