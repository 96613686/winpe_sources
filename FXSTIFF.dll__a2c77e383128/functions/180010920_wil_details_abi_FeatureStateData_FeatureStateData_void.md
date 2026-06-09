# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010920`
- end: `0x1800109f0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010608`

## callees

- `0x180010474`
- `0x180010920`
- `0x180010dec`
- `0x1800136bc`
- `0x180015228`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800109c0`
- `KERNEL32!HeapFree` at `0x1800109c0`
- `KERNEL32!GetProcessHeap` at `0x1800109b2`
- `KERNEL32!GetProcessHeap` at `0x1800109b2`
- `KERNEL32!DeleteCriticalSection` at `0x1800109cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800109cd`

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
0x180010920  mov     [rsp+arg_0], rbx
0x180010925  mov     [rsp+arg_8], rsi
0x18001092a  push    rdi
0x18001092b  sub     rsp, 0E0h
0x180010932  mov     rbx, rcx
0x180010935  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001093a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001093f  cmp     byte ptr [rbx+40h], 0
0x180010943  jz      short loc_180010953
0x180010945  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180010949  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001094e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010953  cmp     byte ptr [rbx+80h], 0
0x18001095a  jz      short loc_18001096A
0x18001095c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010960  lea     rcx, [rsp+0E8h+var_88]; this
0x180010965  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001096a  cmp     byte ptr [rbx+0C0h], 0
0x180010971  jz      short loc_180010987
0x180010973  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18001097a  lea     rcx, [rsp+0E8h+var_48]; this
0x180010982  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010987  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001098c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010991  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010996  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001099b  mov     rsi, [rbx+108h]
0x1800109a2  mov     qword ptr [rbx+108h], 0
0x1800109ad  test    rsi, rsi
0x1800109b0  jz      short loc_1800109C6
0x1800109b2  call    cs:__imp_GetProcessHeap
0x1800109b8  mov     rcx, rax; hHeap
0x1800109bb  mov     r8, rsi; lpMem
0x1800109be  xor     edx, edx; dwFlags
0x1800109c0  call    cs:__imp_HeapFree
0x1800109c6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800109cd  call    cs:__imp_DeleteCriticalSection
0x1800109d3  lea     rcx, [rbx+8]; this
0x1800109d7  lea     r11, [rsp+0E8h+var_8]
0x1800109df  mov     rbx, [r11+10h]
0x1800109e3  mov     rsi, [r11+18h]
0x1800109e7  mov     rsp, r11
0x1800109ea  pop     rdi
0x1800109eb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
