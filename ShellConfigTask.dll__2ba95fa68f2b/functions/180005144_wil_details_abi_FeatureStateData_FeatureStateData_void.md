# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005144`
- end: `0x180005214`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a118`

## callees

- `0x180004c50`
- `0x180005144`
- `0x180005620`
- `0x180008fb8`
- `0x18000ba9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800051f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800051f1`

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
0x180005144  mov     [rsp+arg_0], rbx
0x180005149  mov     [rsp+arg_8], rsi
0x18000514e  push    rdi
0x18000514f  sub     rsp, 0E0h
0x180005156  mov     rbx, rcx
0x180005159  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000515e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005163  cmp     byte ptr [rbx+40h], 0
0x180005167  jz      short loc_180005177
0x180005169  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000516d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005172  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005177  cmp     byte ptr [rbx+80h], 0
0x18000517e  jz      short loc_18000518E
0x180005180  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005184  lea     rcx, [rsp+0E8h+var_88]; this
0x180005189  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000518e  cmp     byte ptr [rbx+0C0h], 0
0x180005195  jz      short loc_1800051AB
0x180005197  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000519e  lea     rcx, [rsp+0E8h+var_48]; this
0x1800051a6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800051ab  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800051b0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800051b5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800051ba  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800051bf  mov     rsi, [rbx+108h]
0x1800051c6  mov     qword ptr [rbx+108h], 0
0x1800051d1  test    rsi, rsi
0x1800051d4  jz      short loc_1800051EA
0x1800051d6  call    cs:__imp_GetProcessHeap
0x1800051dc  mov     rcx, rax; hHeap
0x1800051df  mov     r8, rsi; lpMem
0x1800051e2  xor     edx, edx; dwFlags
0x1800051e4  call    cs:__imp_HeapFree
0x1800051ea  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800051f1  call    cs:__imp_DeleteCriticalSection
0x1800051f7  lea     rcx, [rbx+8]; this
0x1800051fb  lea     r11, [rsp+0E8h+var_8]
0x180005203  mov     rbx, [r11+10h]
0x180005207  mov     rsi, [r11+18h]
0x18000520b  mov     rsp, r11
0x18000520e  pop     rdi
0x18000520f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
