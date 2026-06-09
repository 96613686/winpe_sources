# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000af60`
- end: `0x18000b042`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010000`

## callees

- `0x18000ab6c`
- `0x18000af60`
- `0x18000b480`
- `0x18000eec4`
- `0x180011658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b019`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aff2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aff2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b006`

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
0x18000af60  mov     [rsp+arg_0], rbx
0x18000af65  mov     [rsp+arg_8], rsi
0x18000af6a  push    rdi
0x18000af6b  sub     rsp, 0E0h
0x18000af72  mov     rbx, rcx
0x18000af75  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af7a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000af7f  cmp     byte ptr [rbx+40h], 0
0x18000af83  jz      short loc_18000AF93
0x18000af85  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000af89  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af8e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af93  cmp     byte ptr [rbx+80h], 0
0x18000af9a  jz      short loc_18000AFAA
0x18000af9c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000afa0  lea     rcx, [rsp+0E8h+var_88]; this
0x18000afa5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000afaa  cmp     byte ptr [rbx+0C0h], 0
0x18000afb1  jz      short loc_18000AFC7
0x18000afb3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000afba  lea     rcx, [rsp+0E8h+var_48]; this
0x18000afc2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000afc7  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000afcc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000afd1  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000afd6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000afdb  mov     rsi, [rbx+108h]
0x18000afe2  mov     qword ptr [rbx+108h], 0
0x18000afed  test    rsi, rsi
0x18000aff0  jz      short loc_18000B012
0x18000aff2  call    cs:__imp_GetProcessHeap
0x18000aff9  nop     dword ptr [rax+rax+00h]
0x18000affe  mov     rcx, rax; hHeap
0x18000b001  mov     r8, rsi; lpMem
0x18000b004  xor     edx, edx; dwFlags
0x18000b006  call    cs:__imp_HeapFree
0x18000b00d  nop     dword ptr [rax+rax+00h]
0x18000b012  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000b019  call    cs:__imp_DeleteCriticalSection
0x18000b020  nop     dword ptr [rax+rax+00h]
0x18000b025  lea     rcx, [rbx+8]; this
0x18000b029  lea     r11, [rsp+0E8h+var_8]
0x18000b031  mov     rbx, [r11+10h]
0x18000b035  mov     rsi, [r11+18h]
0x18000b039  mov     rsp, r11
0x18000b03c  pop     rdi
0x18000b03d  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
