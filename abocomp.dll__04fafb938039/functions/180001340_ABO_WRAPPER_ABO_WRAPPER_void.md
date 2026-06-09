# ABO_WRAPPER::ABO_WRAPPER(void)

- ea: `0x180001340`
- end: `0x180001476`
- name: `??0ABO_WRAPPER@@QEAA@XZ`
- size: `310`
- prototype: `ABO_WRAPPER *__fastcall(ABO_WRAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800013ce`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000143b`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800013ce`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000143b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180001378`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180001378`

## pseudocode

```c
ABO_WRAPPER *__fastcall ABO_WRAPPER::ABO_WRAPPER(ABO_WRAPPER *this)
{
  ABO_WRAPPER *result; // rax

  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &ABO_WRAPPER::`vftable'{for `IAboWrapper'};
  *((_QWORD *)this + 1) = &ABO_WRAPPER::`vftable'{for `INativeChangeListener'};
  *((_QWORD *)this + 3) = 0;
  CReaderWriterLock3::CReaderWriterLock3((ABO_WRAPPER *)((char *)this + 32));
  CLKRHashTable::CLKRHashTable(
    (ABO_WRAPPER *)((char *)this + 48),
    "HANDLE_TABLE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<PROPERTY_ID_TABLE,PROPERTY_LIST,unsigned long,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *((_QWORD *)this + 5) = &HANDLE_TABLE::`vftable';
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  CLKRHashTable::CLKRHashTable(
    (ABO_WRAPPER *)((char *)this + 152),
    "BINDING_TABLE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *((_QWORD *)this + 18) = &HANDLE_TABLE::`vftable';
  result = this;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  return result;
}

```

## disassembly

```asm
0x180001340  mov     [rsp+arg_0], rbx
0x180001345  push    rdi
0x180001346  sub     rsp, 60h
0x18000134a  lea     rax, ??_7ABO_WRAPPER@@6BIAboWrapper@@@; const ABO_WRAPPER::`vftable'{for `IAboWrapper'}
0x180001351  mov     dword ptr [rcx+10h], 1
0x180001358  mov     [rcx], rax
0x18000135b  mov     rbx, rcx
0x18000135e  lea     rax, ??_7ABO_WRAPPER@@6BINativeChangeListener@@@; const ABO_WRAPPER::`vftable'{for `INativeChangeListener'}
0x180001365  movaps  [rsp+68h+var_18], xmm6
0x18000136a  mov     [rcx+8], rax
0x18000136e  xor     edi, edi
0x180001370  mov     [rcx+18h], rdi
0x180001374  add     rcx, 20h ; ' '
0x180001378  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000137e  movsd   xmm6, cs:__real@4010000000000000
0x180001386  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18000138d  mov     [rsp+68h+var_20], dil
0x180001392  lea     rcx, [rbx+30h]
0x180001396  mov     [rsp+68h+var_28], edi
0x18000139a  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x1800013a1  mov     [rsp+68h+var_30], 1
0x1800013a9  lea     r8, ?_ExtractKey@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::_ExtractKey(void const *)
0x1800013b0  movsd   [rsp+68h+var_38], xmm6
0x1800013b6  lea     rdx, aHandleTable; "HANDLE_TABLE"
0x1800013bd  mov     [rsp+68h+var_40], rax
0x1800013c2  lea     rax, ?_EqualKeys@?$CTypedHashTable@VPROPERTY_ID_TABLE@@VPROPERTY_LIST@@KVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<PROPERTY_ID_TABLE,PROPERTY_LIST,ulong,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800013c9  mov     [rsp+68h+var_48], rax
0x1800013ce  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800013d4  mov     [rsp+68h+var_20], dil
0x1800013d9  lea     rax, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x1800013e0  mov     [rbx+28h], rax
0x1800013e4  lea     rcx, [rbx+98h]
0x1800013eb  mov     [rsp+68h+var_28], edi
0x1800013ef  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x1800013f6  mov     [rsp+68h+var_30], 1
0x1800013fe  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180001405  movsd   [rsp+68h+var_38], xmm6
0x18000140b  lea     r8, ?_ExtractKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180001412  mov     [rsp+68h+var_40], rax
0x180001417  lea     rdx, aBindingTable; "BINDING_TABLE"
0x18000141e  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSITE_NODE_TABLE@@VSITE_NODE_TABLE_ENTRY@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180001425  mov     [rbx+78h], rdi
0x180001429  mov     [rsp+68h+var_48], rax
0x18000142e  mov     [rbx+80h], edi
0x180001434  mov     [rbx+88h], rdi
0x18000143b  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180001441  movaps  xmm6, [rsp+68h+var_18]
0x180001446  lea     rax, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x18000144d  mov     [rbx+90h], rax
0x180001454  mov     rax, rbx
0x180001457  mov     [rbx+0E0h], rdi
0x18000145e  mov     [rbx+0E8h], edi
0x180001464  mov     [rbx+0F0h], rdi
0x18000146b  mov     rbx, [rsp+68h+arg_0]
0x180001470  add     rsp, 60h
0x180001474  pop     rdi
0x180001475  retn
```
