# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180023404`
- end: `0x1800234d4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023310`

## callees

- `0x18002317c`
- `0x180023404`
- `0x180023754`
- `0x180025ebc`
- `0x1800274d0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180023496`
- `KERNEL32!GetProcessHeap` at `0x180023496`
- `KERNEL32!HeapFree` at `0x1800234a4`
- `KERNEL32!HeapFree` at `0x1800234a4`
- `KERNEL32!DeleteCriticalSection` at `0x1800234b1`
- `KERNEL32!DeleteCriticalSection` at `0x1800234b1`

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
0x180023404  mov     [rsp+arg_0], rbx
0x180023409  mov     [rsp+arg_8], rsi
0x18002340e  push    rdi
0x18002340f  sub     rsp, 0E0h
0x180023416  mov     rbx, rcx
0x180023419  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002341e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180023423  cmp     byte ptr [rbx+40h], 0
0x180023427  jz      short loc_180023437
0x180023429  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18002342d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180023432  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180023437  cmp     byte ptr [rbx+80h], 0
0x18002343e  jz      short loc_18002344E
0x180023440  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180023444  lea     rcx, [rsp+0E8h+var_88]; this
0x180023449  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002344e  cmp     byte ptr [rbx+0C0h], 0
0x180023455  jz      short loc_18002346B
0x180023457  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18002345e  lea     rcx, [rsp+0E8h+var_48]; this
0x180023466  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002346b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180023470  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180023475  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002347a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18002347f  mov     rsi, [rbx+108h]
0x180023486  mov     qword ptr [rbx+108h], 0
0x180023491  test    rsi, rsi
0x180023494  jz      short loc_1800234AA
0x180023496  call    cs:__imp_GetProcessHeap
0x18002349c  mov     r8, rsi; lpMem
0x18002349f  xor     edx, edx; dwFlags
0x1800234a1  mov     rcx, rax; hHeap
0x1800234a4  call    cs:__imp_HeapFree
0x1800234aa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800234b1  call    cs:__imp_DeleteCriticalSection
0x1800234b7  lea     rcx, [rbx+8]; this
0x1800234bb  lea     r11, [rsp+0E8h+var_8]
0x1800234c3  mov     rbx, [r11+10h]
0x1800234c7  mov     rsi, [r11+18h]
0x1800234cb  mov     rsp, r11
0x1800234ce  pop     rdi
0x1800234cf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
