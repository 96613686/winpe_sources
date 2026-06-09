# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180024028`
- end: `0x18002410a`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027a5c`

## callees

- `0x180023ef4`
- `0x180024028`
- `0x1800243dc`
- `0x180026bbc`
- `0x1800283f0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800240ba`
- `KERNEL32!GetProcessHeap` at `0x1800240ba`
- `KERNEL32!HeapFree` at `0x1800240ce`
- `KERNEL32!HeapFree` at `0x1800240ce`
- `KERNEL32!DeleteCriticalSection` at `0x1800240e1`
- `KERNEL32!DeleteCriticalSection` at `0x1800240e1`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  void *v5; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v7[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v8[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v9[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v7);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v7,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v8,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v9,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v7, v2, v3, v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v7);
  v5 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x180024028  mov     [rsp+arg_0], rbx
0x18002402d  mov     [rsp+arg_8], rsi
0x180024032  push    rdi
0x180024033  sub     rsp, 0E0h
0x18002403a  mov     rbx, rcx
0x18002403d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180024042  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180024047  cmp     byte ptr [rbx+40h], 0
0x18002404b  jz      short loc_18002405B
0x18002404d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180024051  lea     rcx, [rsp+0E8h+var_C8]; this
0x180024056  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002405b  cmp     byte ptr [rbx+80h], 0
0x180024062  jz      short loc_180024072
0x180024064  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180024068  lea     rcx, [rsp+0E8h+var_88]; this
0x18002406d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180024072  cmp     byte ptr [rbx+0C0h], 0
0x180024079  jz      short loc_18002408F
0x18002407b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180024082  lea     rcx, [rsp+0E8h+var_48]; this
0x18002408a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002408f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180024094  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180024099  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002409e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800240a3  mov     rsi, [rbx+108h]
0x1800240aa  mov     qword ptr [rbx+108h], 0
0x1800240b5  test    rsi, rsi
0x1800240b8  jz      short loc_1800240DA
0x1800240ba  call    cs:__imp_GetProcessHeap
0x1800240c1  nop     dword ptr [rax+rax+00h]
0x1800240c6  mov     r8, rsi; lpMem
0x1800240c9  xor     edx, edx; dwFlags
0x1800240cb  mov     rcx, rax; hHeap
0x1800240ce  call    cs:__imp_HeapFree
0x1800240d5  nop     dword ptr [rax+rax+00h]
0x1800240da  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800240e1  call    cs:__imp_DeleteCriticalSection
0x1800240e8  nop     dword ptr [rax+rax+00h]
0x1800240ed  lea     rcx, [rbx+8]; this
0x1800240f1  lea     r11, [rsp+0E8h+var_8]
0x1800240f9  mov     rbx, [r11+10h]
0x1800240fd  mov     rsi, [r11+18h]
0x180024101  mov     rsp, r11
0x180024104  pop     rdi
0x180024105  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
