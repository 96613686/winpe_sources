# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003ab8`
- end: `0x180003b88`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800037ec`

## callees

- `0x180003620`
- `0x180003ab8`
- `0x180003f2c`
- `0x1800068a4`
- `0x180008a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b58`

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
0x180003ab8  mov     [rsp+arg_0], rbx
0x180003abd  mov     [rsp+arg_8], rsi
0x180003ac2  push    rdi
0x180003ac3  sub     rsp, 0E0h
0x180003aca  mov     rbx, rcx
0x180003acd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003ad2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ad7  cmp     byte ptr [rbx+40h], 0
0x180003adb  jz      short loc_180003AEB
0x180003add  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003ae1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003ae6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003aeb  cmp     byte ptr [rbx+80h], 0
0x180003af2  jz      short loc_180003B02
0x180003af4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003af8  lea     rcx, [rsp+0E8h+var_88]; this
0x180003afd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003b02  cmp     byte ptr [rbx+0C0h], 0
0x180003b09  jz      short loc_180003B1F
0x180003b0b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003b12  lea     rcx, [rsp+0E8h+var_48]; this
0x180003b1a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003b1f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003b24  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003b29  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003b2e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003b33  mov     rsi, [rbx+108h]
0x180003b3a  mov     qword ptr [rbx+108h], 0
0x180003b45  test    rsi, rsi
0x180003b48  jz      short loc_180003B5E
0x180003b4a  call    cs:__imp_GetProcessHeap
0x180003b50  mov     rcx, rax; hHeap
0x180003b53  mov     r8, rsi; lpMem
0x180003b56  xor     edx, edx; dwFlags
0x180003b58  call    cs:__imp_HeapFree
0x180003b5e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003b65  call    cs:__imp_DeleteCriticalSection
0x180003b6b  lea     rcx, [rbx+8]; this
0x180003b6f  lea     r11, [rsp+0E8h+var_8]
0x180003b77  mov     rbx, [r11+10h]
0x180003b7b  mov     rsi, [r11+18h]
0x180003b7f  mov     rsp, r11
0x180003b82  pop     rdi
0x180003b83  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
