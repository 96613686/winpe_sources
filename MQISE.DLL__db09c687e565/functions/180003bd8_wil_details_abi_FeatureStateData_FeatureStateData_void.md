# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003bd8`
- end: `0x180003cab`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `211`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003588`

## callees

- `0x18000301c`
- `0x180003bd8`
- `0x1800040b8`
- `0x180008408`
- `0x18000a2d8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003c6b`
- `KERNEL32!GetProcessHeap` at `0x180003c6b`
- `KERNEL32!HeapFree` at `0x180003c79`
- `KERNEL32!HeapFree` at `0x180003c79`
- `KERNEL32!DeleteCriticalSection` at `0x180003c87`
- `KERNEL32!DeleteCriticalSection` at `0x180003c87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180003bd8  mov     [rsp+arg_0], rbx
0x180003bdd  mov     [rsp+arg_8], rsi
0x180003be2  push    rdi
0x180003be3  sub     rsp, 0E0h
0x180003bea  mov     rbx, rcx
0x180003bed  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003bf2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003bf7  cmp     byte ptr [rbx+40h], 0
0x180003bfb  jz      short loc_180003C0B
0x180003bfd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003c01  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003c06  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003c0b  cmp     byte ptr [rbx+80h], 0
0x180003c12  jz      short loc_180003C22
0x180003c14  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003c18  lea     rcx, [rsp+0E8h+var_88]; this
0x180003c1d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003c22  cmp     byte ptr [rbx+0C0h], 0
0x180003c29  jz      short loc_180003C3F
0x180003c2b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003c32  lea     rcx, [rsp+0E8h+var_48]; this
0x180003c3a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003c3f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003c44  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003c49  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003c4e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003c53  nop
0x180003c54  mov     rsi, [rbx+108h]
0x180003c5b  mov     qword ptr [rbx+108h], 0
0x180003c66  test    rsi, rsi
0x180003c69  jz      short loc_180003C80
0x180003c6b  call    cs:__imp_GetProcessHeap
0x180003c71  mov     rcx, rax; hHeap
0x180003c74  mov     r8, rsi; lpMem
0x180003c77  xor     edx, edx; dwFlags
0x180003c79  call    cs:__imp_HeapFree
0x180003c7f  nop
0x180003c80  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003c87  call    cs:__imp_DeleteCriticalSection
0x180003c8d  nop
0x180003c8e  lea     rcx, [rbx+8]; this
0x180003c92  lea     r11, [rsp+0E8h+var_8]
0x180003c9a  mov     rbx, [r11+10h]
0x180003c9e  mov     rsi, [r11+18h]
0x180003ca2  mov     rsp, r11
0x180003ca5  pop     rdi
0x180003ca6  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
