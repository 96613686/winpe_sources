# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140005be8`
- end: `0x140005cb8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005ad0`

## callees

- `0x140005a08`
- `0x140005be8`
- `0x140005eec`
- `0x140006c84`
- `0x140007d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005c88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005c88`

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
0x140005be8  mov     [rsp+arg_0], rbx
0x140005bed  mov     [rsp+arg_8], rsi
0x140005bf2  push    rdi
0x140005bf3  sub     rsp, 0E0h
0x140005bfa  mov     rbx, rcx
0x140005bfd  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c02  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005c07  cmp     byte ptr [rbx+40h], 0
0x140005c0b  jz      short loc_140005C1B
0x140005c0d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140005c11  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c16  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c1b  cmp     byte ptr [rbx+80h], 0
0x140005c22  jz      short loc_140005C32
0x140005c24  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005c28  lea     rcx, [rsp+0E8h+var_88]; this
0x140005c2d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c32  cmp     byte ptr [rbx+0C0h], 0
0x140005c39  jz      short loc_140005C4F
0x140005c3b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140005c42  lea     rcx, [rsp+0E8h+var_48]; this
0x140005c4a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c4f  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c54  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005c59  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c5e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140005c63  mov     rsi, [rbx+108h]
0x140005c6a  mov     qword ptr [rbx+108h], 0
0x140005c75  test    rsi, rsi
0x140005c78  jz      short loc_140005C8E
0x140005c7a  call    cs:__imp_GetProcessHeap
0x140005c80  mov     rcx, rax; hHeap
0x140005c83  mov     r8, rsi; lpMem
0x140005c86  xor     edx, edx; dwFlags
0x140005c88  call    cs:__imp_HeapFree
0x140005c8e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005c95  call    cs:__imp_DeleteCriticalSection
0x140005c9b  lea     rcx, [rbx+8]; this
0x140005c9f  lea     r11, [rsp+0E8h+var_8]
0x140005ca7  mov     rbx, [r11+10h]
0x140005cab  mov     rsi, [r11+18h]
0x140005caf  mov     rsp, r11
0x140005cb2  pop     rdi
0x140005cb3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
