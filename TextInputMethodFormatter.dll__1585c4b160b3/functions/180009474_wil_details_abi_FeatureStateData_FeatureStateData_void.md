# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009474`
- end: `0x180009544`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008fb8`

## callees

- `0x180008e40`
- `0x180009474`
- `0x180009800`
- `0x18000f028`
- `0x180011664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009521`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009521`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009506`

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
0x180009474  mov     [rsp+arg_0], rbx
0x180009479  mov     [rsp+arg_8], rsi
0x18000947e  push    rdi
0x18000947f  sub     rsp, 0E0h
0x180009486  mov     rbx, rcx
0x180009489  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000948e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009493  cmp     byte ptr [rbx+40h], 0
0x180009497  jz      short loc_1800094A7
0x180009499  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000949d  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094a2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094a7  cmp     byte ptr [rbx+80h], 0
0x1800094ae  jz      short loc_1800094BE
0x1800094b0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800094b4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800094b9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094be  cmp     byte ptr [rbx+0C0h], 0
0x1800094c5  jz      short loc_1800094DB
0x1800094c7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800094ce  lea     rcx, [rsp+0E8h+var_48]; this
0x1800094d6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094db  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094e0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800094e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094ea  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800094ef  mov     rsi, [rbx+108h]
0x1800094f6  mov     qword ptr [rbx+108h], 0
0x180009501  test    rsi, rsi
0x180009504  jz      short loc_18000951A
0x180009506  call    cs:__imp_GetProcessHeap
0x18000950c  mov     rcx, rax; hHeap
0x18000950f  mov     r8, rsi; lpMem
0x180009512  xor     edx, edx; dwFlags
0x180009514  call    cs:__imp_HeapFree
0x18000951a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009521  call    cs:__imp_DeleteCriticalSection
0x180009527  lea     rcx, [rbx+8]; this
0x18000952b  lea     r11, [rsp+0E8h+var_8]
0x180009533  mov     rbx, [r11+10h]
0x180009537  mov     rsi, [r11+18h]
0x18000953b  mov     rsp, r11
0x18000953e  pop     rdi
0x18000953f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
