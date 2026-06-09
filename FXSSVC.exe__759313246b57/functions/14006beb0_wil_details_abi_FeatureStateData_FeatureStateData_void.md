# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14006beb0`
- end: `0x14006bf92`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006fbbc`

## callees

- `0x14006bd54`
- `0x14006beb0`
- `0x14006c3ac`
- `0x14006ed6c`
- `0x140070b94`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14006bf42`
- `KERNEL32!GetProcessHeap` at `0x14006bf42`
- `KERNEL32!HeapFree` at `0x14006bf56`
- `KERNEL32!HeapFree` at `0x14006bf56`
- `KERNEL32!DeleteCriticalSection` at `0x14006bf69`
- `KERNEL32!DeleteCriticalSection` at `0x14006bf69`

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
0x14006beb0  mov     [rsp+arg_0], rbx
0x14006beb5  mov     [rsp+arg_8], rsi
0x14006beba  push    rdi
0x14006bebb  sub     rsp, 0E0h
0x14006bec2  mov     rbx, rcx
0x14006bec5  lea     rcx, [rsp+0E8h+var_C8]; this
0x14006beca  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14006becf  cmp     byte ptr [rbx+40h], 0
0x14006bed3  jz      short loc_14006BEE3
0x14006bed5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14006bed9  lea     rcx, [rsp+0E8h+var_C8]; this
0x14006bede  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14006bee3  cmp     byte ptr [rbx+80h], 0
0x14006beea  jz      short loc_14006BEFA
0x14006beec  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14006bef0  lea     rcx, [rsp+0E8h+var_88]; this
0x14006bef5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14006befa  cmp     byte ptr [rbx+0C0h], 0
0x14006bf01  jz      short loc_14006BF17
0x14006bf03  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14006bf0a  lea     rcx, [rsp+0E8h+var_48]; this
0x14006bf12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14006bf17  lea     rcx, [rsp+0E8h+var_C8]; this
0x14006bf1c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14006bf21  lea     rcx, [rsp+0E8h+var_C8]; this
0x14006bf26  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14006bf2b  mov     rsi, [rbx+108h]
0x14006bf32  mov     qword ptr [rbx+108h], 0
0x14006bf3d  test    rsi, rsi
0x14006bf40  jz      short loc_14006BF62
0x14006bf42  call    cs:__imp_GetProcessHeap
0x14006bf49  nop     dword ptr [rax+rax+00h]
0x14006bf4e  mov     rcx, rax; hHeap
0x14006bf51  mov     r8, rsi; lpMem
0x14006bf54  xor     edx, edx; dwFlags
0x14006bf56  call    cs:__imp_HeapFree
0x14006bf5d  nop     dword ptr [rax+rax+00h]
0x14006bf62  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14006bf69  call    cs:__imp_DeleteCriticalSection
0x14006bf70  nop     dword ptr [rax+rax+00h]
0x14006bf75  lea     rcx, [rbx+8]; this
0x14006bf79  lea     r11, [rsp+0E8h+var_8]
0x14006bf81  mov     rbx, [r11+10h]
0x14006bf85  mov     rsi, [r11+18h]
0x14006bf89  mov     rsp, r11
0x14006bf8c  pop     rdi
0x14006bf8d  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
