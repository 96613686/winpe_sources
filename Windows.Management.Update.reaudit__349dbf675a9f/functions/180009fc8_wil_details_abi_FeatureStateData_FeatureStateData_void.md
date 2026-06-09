# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009fc8`
- end: `0x18000a0a7`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e5e8`

## callees

- `0x180009b58`
- `0x180009fc8`
- `0x18000a4f4`
- `0x18000d53c`
- `0x18000fa30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a07e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a07e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a06b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a06b`

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
0x180009fc8  mov     [rsp+arg_0], rbx
0x180009fcd  mov     [rsp+arg_8], rsi
0x180009fd2  push    rdi
0x180009fd3  sub     rsp, 0E0h
0x180009fda  mov     rbx, rcx
0x180009fdd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009fe2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009fe7  cmp     byte ptr [rbx+40h], 0
0x180009feb  jz      short loc_180009FFB
0x180009fed  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009ff1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009ff6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009ffb  cmp     byte ptr [rbx+80h], 0
0x18000a002  jz      short loc_18000A012
0x18000a004  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000a008  lea     rcx, [rsp+0E8h+var_88]; this
0x18000a00d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a012  cmp     byte ptr [rbx+0C0h], 0
0x18000a019  jz      short loc_18000A02F
0x18000a01b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000a022  lea     rcx, [rsp+0E8h+var_48]; this
0x18000a02a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a02f  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a034  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a039  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a03e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a043  mov     rsi, [rbx+108h]
0x18000a04a  and     qword ptr [rbx+108h], 0
0x18000a052  test    rsi, rsi
0x18000a055  jz      short loc_18000A077
0x18000a057  call    cs:__imp_GetProcessHeap
0x18000a05e  nop     dword ptr [rax+rax+00h]
0x18000a063  mov     rcx, rax; hHeap
0x18000a066  mov     r8, rsi; lpMem
0x18000a069  xor     edx, edx; dwFlags
0x18000a06b  call    cs:__imp_HeapFree
0x18000a072  nop     dword ptr [rax+rax+00h]
0x18000a077  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000a07e  call    cs:__imp_DeleteCriticalSection
0x18000a085  nop     dword ptr [rax+rax+00h]
0x18000a08a  lea     rcx, [rbx+8]; this
0x18000a08e  lea     r11, [rsp+0E8h+var_8]
0x18000a096  mov     rbx, [r11+10h]
0x18000a09a  mov     rsi, [r11+18h]
0x18000a09e  mov     rsp, r11
0x18000a0a1  pop     rdi
0x18000a0a2  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
