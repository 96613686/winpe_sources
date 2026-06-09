# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180002e38`
- end: `0x180002f1a`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006658`

## callees

- `0x180002d04`
- `0x180002e38`
- `0x1800031ec`
- `0x180005830`
- `0x180007000`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002eca`
- `KERNEL32!GetProcessHeap` at `0x180002eca`
- `KERNEL32!HeapFree` at `0x180002ede`
- `KERNEL32!HeapFree` at `0x180002ede`
- `KERNEL32!DeleteCriticalSection` at `0x180002ef1`
- `KERNEL32!DeleteCriticalSection` at `0x180002ef1`

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
0x180002e38  mov     [rsp+arg_0], rbx
0x180002e3d  mov     [rsp+arg_8], rsi
0x180002e42  push    rdi
0x180002e43  sub     rsp, 0E0h
0x180002e4a  mov     rbx, rcx
0x180002e4d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002e52  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180002e57  cmp     byte ptr [rbx+40h], 0
0x180002e5b  jz      short loc_180002E6B
0x180002e5d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180002e61  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002e66  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002e6b  cmp     byte ptr [rbx+80h], 0
0x180002e72  jz      short loc_180002E82
0x180002e74  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180002e78  lea     rcx, [rsp+0E8h+var_88]; this
0x180002e7d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002e82  cmp     byte ptr [rbx+0C0h], 0
0x180002e89  jz      short loc_180002E9F
0x180002e8b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180002e92  lea     rcx, [rsp+0E8h+var_48]; this
0x180002e9a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002e9f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002ea4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180002ea9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002eae  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180002eb3  mov     rsi, [rbx+108h]
0x180002eba  mov     qword ptr [rbx+108h], 0
0x180002ec5  test    rsi, rsi
0x180002ec8  jz      short loc_180002EEA
0x180002eca  call    cs:__imp_GetProcessHeap
0x180002ed1  nop     dword ptr [rax+rax+00h]
0x180002ed6  mov     r8, rsi; lpMem
0x180002ed9  xor     edx, edx; dwFlags
0x180002edb  mov     rcx, rax; hHeap
0x180002ede  call    cs:__imp_HeapFree
0x180002ee5  nop     dword ptr [rax+rax+00h]
0x180002eea  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180002ef1  call    cs:__imp_DeleteCriticalSection
0x180002ef8  nop     dword ptr [rax+rax+00h]
0x180002efd  lea     rcx, [rbx+8]; this
0x180002f01  lea     r11, [rsp+0E8h+var_8]
0x180002f09  mov     rbx, [r11+10h]
0x180002f0d  mov     rsi, [r11+18h]
0x180002f11  mov     rsp, r11
0x180002f14  pop     rdi
0x180002f15  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
