# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180002d94`
- end: `0x180002e64`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b54`

## callees

- `0x1800029c0`
- `0x180002d94`
- `0x1800030e4`
- `0x180005878`
- `0x1800072e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e26`

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
0x180002d94  mov     [rsp+arg_0], rbx
0x180002d99  mov     [rsp+arg_8], rsi
0x180002d9e  push    rdi
0x180002d9f  sub     rsp, 0E0h
0x180002da6  mov     rbx, rcx
0x180002da9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002dae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180002db3  cmp     byte ptr [rbx+40h], 0
0x180002db7  jz      short loc_180002DC7
0x180002db9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180002dbd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002dc2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002dc7  cmp     byte ptr [rbx+80h], 0
0x180002dce  jz      short loc_180002DDE
0x180002dd0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180002dd4  lea     rcx, [rsp+0E8h+var_88]; this
0x180002dd9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002dde  cmp     byte ptr [rbx+0C0h], 0
0x180002de5  jz      short loc_180002DFB
0x180002de7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180002dee  lea     rcx, [rsp+0E8h+var_48]; this
0x180002df6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002dfb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002e00  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180002e05  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002e0a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180002e0f  mov     rsi, [rbx+108h]
0x180002e16  mov     qword ptr [rbx+108h], 0
0x180002e21  test    rsi, rsi
0x180002e24  jz      short loc_180002E3A
0x180002e26  call    cs:__imp_GetProcessHeap
0x180002e2c  mov     r8, rsi; lpMem
0x180002e2f  xor     edx, edx; dwFlags
0x180002e31  mov     rcx, rax; hHeap
0x180002e34  call    cs:__imp_HeapFree
0x180002e3a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180002e41  call    cs:__imp_DeleteCriticalSection
0x180002e47  lea     rcx, [rbx+8]; this
0x180002e4b  lea     r11, [rsp+0E8h+var_8]
0x180002e53  mov     rbx, [r11+10h]
0x180002e57  mov     rsi, [r11+18h]
0x180002e5b  mov     rsp, r11
0x180002e5e  pop     rdi
0x180002e5f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
