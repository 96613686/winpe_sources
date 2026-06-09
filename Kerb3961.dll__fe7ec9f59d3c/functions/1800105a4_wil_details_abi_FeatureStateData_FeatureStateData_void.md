# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800105a4`
- end: `0x180010674`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010364`

## callees

- `0x18001029c`
- `0x1800105a4`
- `0x180010870`
- `0x1800152d0`
- `0x180017520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010636`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010644`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010651`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010651`

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
0x1800105a4  mov     [rsp+arg_0], rbx
0x1800105a9  mov     [rsp+arg_8], rsi
0x1800105ae  push    rdi
0x1800105af  sub     rsp, 0E0h
0x1800105b6  mov     rbx, rcx
0x1800105b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800105be  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800105c3  cmp     byte ptr [rbx+40h], 0
0x1800105c7  jz      short loc_1800105D7
0x1800105c9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800105cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800105d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800105d7  cmp     byte ptr [rbx+80h], 0
0x1800105de  jz      short loc_1800105EE
0x1800105e0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800105e4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800105e9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800105ee  cmp     byte ptr [rbx+0C0h], 0
0x1800105f5  jz      short loc_18001060B
0x1800105f7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800105fe  lea     rcx, [rsp+0E8h+var_48]; this
0x180010606  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001060b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010610  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010615  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001061a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001061f  mov     rsi, [rbx+108h]
0x180010626  mov     qword ptr [rbx+108h], 0
0x180010631  test    rsi, rsi
0x180010634  jz      short loc_18001064A
0x180010636  call    cs:__imp_GetProcessHeap
0x18001063c  mov     r8, rsi; lpMem
0x18001063f  xor     edx, edx; dwFlags
0x180010641  mov     rcx, rax; hHeap
0x180010644  call    cs:__imp_HeapFree
0x18001064a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180010651  call    cs:__imp_DeleteCriticalSection
0x180010657  lea     rcx, [rbx+8]; this
0x18001065b  lea     r11, [rsp+0E8h+var_8]
0x180010663  mov     rbx, [r11+10h]
0x180010667  mov     rsi, [r11+18h]
0x18001066b  mov     rsp, r11
0x18001066e  pop     rdi
0x18001066f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
