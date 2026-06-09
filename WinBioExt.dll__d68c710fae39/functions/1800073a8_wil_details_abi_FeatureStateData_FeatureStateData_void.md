# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800073a8`
- end: `0x180007478`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007290`

## callees

- `0x1800071c8`
- `0x1800073a8`
- `0x1800076ac`
- `0x180008428`
- `0x180009550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007455`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000743a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000743a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007448`

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
0x1800073a8  mov     [rsp+arg_0], rbx
0x1800073ad  mov     [rsp+arg_8], rsi
0x1800073b2  push    rdi
0x1800073b3  sub     rsp, 0E0h
0x1800073ba  mov     rbx, rcx
0x1800073bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073c2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800073c7  cmp     byte ptr [rbx+40h], 0
0x1800073cb  jz      short loc_1800073DB
0x1800073cd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800073d1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073d6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073db  cmp     byte ptr [rbx+80h], 0
0x1800073e2  jz      short loc_1800073F2
0x1800073e4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800073e8  lea     rcx, [rsp+0E8h+var_88]; this
0x1800073ed  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073f2  cmp     byte ptr [rbx+0C0h], 0
0x1800073f9  jz      short loc_18000740F
0x1800073fb  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180007402  lea     rcx, [rsp+0E8h+var_48]; this
0x18000740a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000740f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007414  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180007419  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000741e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180007423  mov     rsi, [rbx+108h]
0x18000742a  mov     qword ptr [rbx+108h], 0
0x180007435  test    rsi, rsi
0x180007438  jz      short loc_18000744E
0x18000743a  call    cs:__imp_GetProcessHeap
0x180007440  mov     rcx, rax; hHeap
0x180007443  mov     r8, rsi; lpMem
0x180007446  xor     edx, edx; dwFlags
0x180007448  call    cs:__imp_HeapFree
0x18000744e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180007455  call    cs:__imp_DeleteCriticalSection
0x18000745b  lea     rcx, [rbx+8]; this
0x18000745f  lea     r11, [rsp+0E8h+var_8]
0x180007467  mov     rbx, [r11+10h]
0x18000746b  mov     rsi, [r11+18h]
0x18000746f  mov     rsp, r11
0x180007472  pop     rdi
0x180007473  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
