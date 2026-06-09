# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140003abc`
- end: `0x140003b8c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003850`

## callees

- `0x140003660`
- `0x140003abc`
- `0x140003e0c`
- `0x140007c10`
- `0x140009dbc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003b5c`
- `KERNEL32!HeapFree` at `0x140003b5c`
- `KERNEL32!DeleteCriticalSection` at `0x140003b69`
- `KERNEL32!DeleteCriticalSection` at `0x140003b69`
- `KERNEL32!GetProcessHeap` at `0x140003b4e`
- `KERNEL32!GetProcessHeap` at `0x140003b4e`

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
0x140003abc  mov     [rsp+arg_0], rbx
0x140003ac1  mov     [rsp+arg_8], rsi
0x140003ac6  push    rdi
0x140003ac7  sub     rsp, 0E0h
0x140003ace  mov     rbx, rcx
0x140003ad1  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003ad6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140003adb  cmp     byte ptr [rbx+40h], 0
0x140003adf  jz      short loc_140003AEF
0x140003ae1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140003ae5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003aea  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003aef  cmp     byte ptr [rbx+80h], 0
0x140003af6  jz      short loc_140003B06
0x140003af8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140003afc  lea     rcx, [rsp+0E8h+var_88]; this
0x140003b01  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003b06  cmp     byte ptr [rbx+0C0h], 0
0x140003b0d  jz      short loc_140003B23
0x140003b0f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140003b16  lea     rcx, [rsp+0E8h+var_48]; this
0x140003b1e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003b23  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003b28  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140003b2d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003b32  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140003b37  mov     rsi, [rbx+108h]
0x140003b3e  mov     qword ptr [rbx+108h], 0
0x140003b49  test    rsi, rsi
0x140003b4c  jz      short loc_140003B62
0x140003b4e  call    cs:__imp_GetProcessHeap
0x140003b54  mov     r8, rsi; lpMem
0x140003b57  xor     edx, edx; dwFlags
0x140003b59  mov     rcx, rax; hHeap
0x140003b5c  call    cs:__imp_HeapFree
0x140003b62  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140003b69  call    cs:__imp_DeleteCriticalSection
0x140003b6f  lea     rcx, [rbx+8]; this
0x140003b73  lea     r11, [rsp+0E8h+var_8]
0x140003b7b  mov     rbx, [r11+10h]
0x140003b7f  mov     rsi, [r11+18h]
0x140003b83  mov     rsp, r11
0x140003b86  pop     rdi
0x140003b87  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
