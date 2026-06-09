# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005b2c`
- end: `0x180005bfc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800057a0`

## callees

- `0x1800055ec`
- `0x180005b2c`
- `0x180005f98`
- `0x18000cad8`
- `0x18001090c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005bd9`
- `KERNEL32!DeleteCriticalSection` at `0x180005bd9`
- `KERNEL32!GetProcessHeap` at `0x180005bbe`
- `KERNEL32!GetProcessHeap` at `0x180005bbe`
- `KERNEL32!HeapFree` at `0x180005bcc`
- `KERNEL32!HeapFree` at `0x180005bcc`

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
0x180005b2c  mov     [rsp+arg_0], rbx
0x180005b31  mov     [rsp+arg_8], rsi
0x180005b36  push    rdi
0x180005b37  sub     rsp, 0E0h
0x180005b3e  mov     rbx, rcx
0x180005b41  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005b46  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005b4b  cmp     byte ptr [rbx+40h], 0
0x180005b4f  jz      short loc_180005B5F
0x180005b51  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005b55  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005b5a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005b5f  cmp     byte ptr [rbx+80h], 0
0x180005b66  jz      short loc_180005B76
0x180005b68  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005b6c  lea     rcx, [rsp+0E8h+var_88]; this
0x180005b71  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005b76  cmp     byte ptr [rbx+0C0h], 0
0x180005b7d  jz      short loc_180005B93
0x180005b7f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005b86  lea     rcx, [rsp+0E8h+var_48]; this
0x180005b8e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005b93  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005b98  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005b9d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005ba2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005ba7  mov     rsi, [rbx+108h]
0x180005bae  mov     qword ptr [rbx+108h], 0
0x180005bb9  test    rsi, rsi
0x180005bbc  jz      short loc_180005BD2
0x180005bbe  call    cs:__imp_GetProcessHeap
0x180005bc4  mov     rcx, rax; hHeap
0x180005bc7  mov     r8, rsi; lpMem
0x180005bca  xor     edx, edx; dwFlags
0x180005bcc  call    cs:__imp_HeapFree
0x180005bd2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180005bd9  call    cs:__imp_DeleteCriticalSection
0x180005bdf  lea     rcx, [rbx+8]; this
0x180005be3  lea     r11, [rsp+0E8h+var_8]
0x180005beb  mov     rbx, [r11+10h]
0x180005bef  mov     rsi, [r11+18h]
0x180005bf3  mov     rsp, r11
0x180005bf6  pop     rdi
0x180005bf7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
