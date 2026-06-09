# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010454`
- end: `0x180010524`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010360`

## callees

- `0x180010298`
- `0x180010454`
- `0x180010720`
- `0x180011428`
- `0x1800124ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800104f4`
- `KERNEL32!HeapFree` at `0x1800104f4`
- `KERNEL32!GetProcessHeap` at `0x1800104e6`
- `KERNEL32!GetProcessHeap` at `0x1800104e6`
- `KERNEL32!DeleteCriticalSection` at `0x180010501`
- `KERNEL32!DeleteCriticalSection` at `0x180010501`

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
0x180010454  mov     [rsp+arg_0], rbx
0x180010459  mov     [rsp+arg_8], rsi
0x18001045e  push    rdi
0x18001045f  sub     rsp, 0E0h
0x180010466  mov     rbx, rcx
0x180010469  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001046e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010473  cmp     byte ptr [rbx+40h], 0
0x180010477  jz      short loc_180010487
0x180010479  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18001047d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010482  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010487  cmp     byte ptr [rbx+80h], 0
0x18001048e  jz      short loc_18001049E
0x180010490  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010494  lea     rcx, [rsp+0E8h+var_88]; this
0x180010499  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001049e  cmp     byte ptr [rbx+0C0h], 0
0x1800104a5  jz      short loc_1800104BB
0x1800104a7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800104ae  lea     rcx, [rsp+0E8h+var_48]; this
0x1800104b6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800104bb  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800104c0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800104c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800104ca  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800104cf  mov     rsi, [rbx+108h]
0x1800104d6  mov     qword ptr [rbx+108h], 0
0x1800104e1  test    rsi, rsi
0x1800104e4  jz      short loc_1800104FA
0x1800104e6  call    cs:__imp_GetProcessHeap
0x1800104ec  mov     r8, rsi; lpMem
0x1800104ef  xor     edx, edx; dwFlags
0x1800104f1  mov     rcx, rax; hHeap
0x1800104f4  call    cs:__imp_HeapFree
0x1800104fa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180010501  call    cs:__imp_DeleteCriticalSection
0x180010507  lea     rcx, [rbx+8]; this
0x18001050b  lea     r11, [rsp+0E8h+var_8]
0x180010513  mov     rbx, [r11+10h]
0x180010517  mov     rsi, [r11+18h]
0x18001051b  mov     rsp, r11
0x18001051e  pop     rdi
0x18001051f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
