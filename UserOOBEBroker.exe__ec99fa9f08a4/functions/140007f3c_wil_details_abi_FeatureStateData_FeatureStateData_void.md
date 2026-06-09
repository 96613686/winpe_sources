# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140007f3c`
- end: `0x14000800c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007c60`

## callees

- `0x140007af8`
- `0x140007f3c`
- `0x140008240`
- `0x14000afbc`
- `0x14000cd10`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007fdc`
- `KERNEL32!HeapFree` at `0x140007fdc`
- `KERNEL32!GetProcessHeap` at `0x140007fce`
- `KERNEL32!GetProcessHeap` at `0x140007fce`
- `KERNEL32!DeleteCriticalSection` at `0x140007fe9`
- `KERNEL32!DeleteCriticalSection` at `0x140007fe9`

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
0x140007f3c  mov     [rsp+arg_0], rbx
0x140007f41  mov     [rsp+arg_8], rsi
0x140007f46  push    rdi
0x140007f47  sub     rsp, 0E0h
0x140007f4e  mov     rbx, rcx
0x140007f51  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007f56  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140007f5b  cmp     byte ptr [rbx+40h], 0
0x140007f5f  jz      short loc_140007F6F
0x140007f61  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140007f65  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007f6a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007f6f  cmp     byte ptr [rbx+80h], 0
0x140007f76  jz      short loc_140007F86
0x140007f78  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140007f7c  lea     rcx, [rsp+0E8h+var_88]; this
0x140007f81  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007f86  cmp     byte ptr [rbx+0C0h], 0
0x140007f8d  jz      short loc_140007FA3
0x140007f8f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140007f96  lea     rcx, [rsp+0E8h+var_48]; this
0x140007f9e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007fa3  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007fa8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140007fad  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007fb2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140007fb7  mov     rsi, [rbx+108h]
0x140007fbe  mov     qword ptr [rbx+108h], 0
0x140007fc9  test    rsi, rsi
0x140007fcc  jz      short loc_140007FE2
0x140007fce  call    cs:__imp_GetProcessHeap
0x140007fd4  mov     rcx, rax; hHeap
0x140007fd7  mov     r8, rsi; lpMem
0x140007fda  xor     edx, edx; dwFlags
0x140007fdc  call    cs:__imp_HeapFree
0x140007fe2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140007fe9  call    cs:__imp_DeleteCriticalSection
0x140007fef  lea     rcx, [rbx+8]; this
0x140007ff3  lea     r11, [rsp+0E8h+var_8]
0x140007ffb  mov     rbx, [r11+10h]
0x140007fff  mov     rsi, [r11+18h]
0x140008003  mov     rsp, r11
0x140008006  pop     rdi
0x140008007  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
