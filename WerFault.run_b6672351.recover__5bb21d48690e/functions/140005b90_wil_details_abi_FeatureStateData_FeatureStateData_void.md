# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140005b90`
- end: `0x140005c72`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a2e4`

## callees

- `0x140005794`
- `0x140005b90`
- `0x140006090`
- `0x140009264`
- `0x14000b9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c49`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005c36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005c22`

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
0x140005b90  mov     [rsp+arg_0], rbx
0x140005b95  mov     [rsp+arg_8], rsi
0x140005b9a  push    rdi
0x140005b9b  sub     rsp, 0E0h
0x140005ba2  mov     rbx, rcx
0x140005ba5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005baa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005baf  cmp     byte ptr [rbx+40h], 0
0x140005bb3  jz      short loc_140005BC3
0x140005bb5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140005bb9  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005bbe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005bc3  cmp     byte ptr [rbx+80h], 0
0x140005bca  jz      short loc_140005BDA
0x140005bcc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005bd0  lea     rcx, [rsp+0E8h+var_88]; this
0x140005bd5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005bda  cmp     byte ptr [rbx+0C0h], 0
0x140005be1  jz      short loc_140005BF7
0x140005be3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140005bea  lea     rcx, [rsp+0E8h+var_48]; this
0x140005bf2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005bf7  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005bfc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005c01  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c06  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140005c0b  mov     rsi, [rbx+108h]
0x140005c12  mov     qword ptr [rbx+108h], 0
0x140005c1d  test    rsi, rsi
0x140005c20  jz      short loc_140005C42
0x140005c22  call    cs:__imp_GetProcessHeap
0x140005c29  nop     dword ptr [rax+rax+00h]
0x140005c2e  mov     rcx, rax; hHeap
0x140005c31  mov     r8, rsi; lpMem
0x140005c34  xor     edx, edx; dwFlags
0x140005c36  call    cs:__imp_HeapFree
0x140005c3d  nop     dword ptr [rax+rax+00h]
0x140005c42  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005c49  call    cs:__imp_DeleteCriticalSection
0x140005c50  nop     dword ptr [rax+rax+00h]
0x140005c55  lea     rcx, [rbx+8]; this
0x140005c59  lea     r11, [rsp+0E8h+var_8]
0x140005c61  mov     rbx, [r11+10h]
0x140005c65  mov     rsi, [r11+18h]
0x140005c69  mov     rsp, r11
0x140005c6c  pop     rdi
0x140005c6d  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
