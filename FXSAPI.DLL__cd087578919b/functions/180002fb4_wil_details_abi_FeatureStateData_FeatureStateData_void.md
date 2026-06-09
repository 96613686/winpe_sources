# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180002fb4`
- end: `0x180003096`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000785c`

## callees

- `0x180002d0c`
- `0x180002fb4`
- `0x1800034b0`
- `0x180006a0c`
- `0x1800088f8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003046`
- `KERNEL32!GetProcessHeap` at `0x180003046`
- `KERNEL32!DeleteCriticalSection` at `0x18000306d`
- `KERNEL32!DeleteCriticalSection` at `0x18000306d`
- `KERNEL32!HeapFree` at `0x18000305a`
- `KERNEL32!HeapFree` at `0x18000305a`

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
0x180002fb4  mov     [rsp+arg_0], rbx
0x180002fb9  mov     [rsp+arg_8], rsi
0x180002fbe  push    rdi
0x180002fbf  sub     rsp, 0E0h
0x180002fc6  mov     rbx, rcx
0x180002fc9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002fce  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180002fd3  cmp     byte ptr [rbx+40h], 0
0x180002fd7  jz      short loc_180002FE7
0x180002fd9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180002fdd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002fe2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002fe7  cmp     byte ptr [rbx+80h], 0
0x180002fee  jz      short loc_180002FFE
0x180002ff0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180002ff4  lea     rcx, [rsp+0E8h+var_88]; this
0x180002ff9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002ffe  cmp     byte ptr [rbx+0C0h], 0
0x180003005  jz      short loc_18000301B
0x180003007  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000300e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003016  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000301b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003020  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003025  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000302a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000302f  mov     rsi, [rbx+108h]
0x180003036  mov     qword ptr [rbx+108h], 0
0x180003041  test    rsi, rsi
0x180003044  jz      short loc_180003066
0x180003046  call    cs:__imp_GetProcessHeap
0x18000304d  nop     dword ptr [rax+rax+00h]
0x180003052  mov     rcx, rax; hHeap
0x180003055  mov     r8, rsi; lpMem
0x180003058  xor     edx, edx; dwFlags
0x18000305a  call    cs:__imp_HeapFree
0x180003061  nop     dword ptr [rax+rax+00h]
0x180003066  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000306d  call    cs:__imp_DeleteCriticalSection
0x180003074  nop     dword ptr [rax+rax+00h]
0x180003079  lea     rcx, [rbx+8]; this
0x18000307d  lea     r11, [rsp+0E8h+var_8]
0x180003085  mov     rbx, [r11+10h]
0x180003089  mov     rsi, [r11+18h]
0x18000308d  mov     rsp, r11
0x180003090  pop     rdi
0x180003091  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
