# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009a94`
- end: `0x180009b64`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009740`

## callees

- `0x180009574`
- `0x180009a94`
- `0x180009f08`
- `0x18000cea4`
- `0x18000f1b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b34`

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
0x180009a94  mov     [rsp+arg_0], rbx
0x180009a99  mov     [rsp+arg_8], rsi
0x180009a9e  push    rdi
0x180009a9f  sub     rsp, 0E0h
0x180009aa6  mov     rbx, rcx
0x180009aa9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009aae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009ab3  cmp     byte ptr [rbx+40h], 0
0x180009ab7  jz      short loc_180009AC7
0x180009ab9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009abd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009ac2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009ac7  cmp     byte ptr [rbx+80h], 0
0x180009ace  jz      short loc_180009ADE
0x180009ad0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009ad4  lea     rcx, [rsp+0E8h+var_88]; this
0x180009ad9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009ade  cmp     byte ptr [rbx+0C0h], 0
0x180009ae5  jz      short loc_180009AFB
0x180009ae7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180009aee  lea     rcx, [rsp+0E8h+var_48]; this
0x180009af6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009afb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009b00  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009b05  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009b0a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009b0f  mov     rsi, [rbx+108h]
0x180009b16  mov     qword ptr [rbx+108h], 0
0x180009b21  test    rsi, rsi
0x180009b24  jz      short loc_180009B3A
0x180009b26  call    cs:__imp_GetProcessHeap
0x180009b2c  mov     rcx, rax; hHeap
0x180009b2f  mov     r8, rsi; lpMem
0x180009b32  xor     edx, edx; dwFlags
0x180009b34  call    cs:__imp_HeapFree
0x180009b3a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009b41  call    cs:__imp_DeleteCriticalSection
0x180009b47  lea     rcx, [rbx+8]; this
0x180009b4b  lea     r11, [rsp+0E8h+var_8]
0x180009b53  mov     rbx, [r11+10h]
0x180009b57  mov     rsi, [r11+18h]
0x180009b5b  mov     rsp, r11
0x180009b5e  pop     rdi
0x180009b5f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
