# CPropertyMapTable::~CPropertyMapTable(void)

- ea: `0x180048bd4`
- end: `0x180048c64`
- name: `??1CPropertyMapTable@@UEAA@XZ`
- size: `144`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048e10`

## callees

- `0x1800418bc`
- `0x180048bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c2d`

## pseudocode

```c
void __fastcall CPropertyMapTable::~CPropertyMapTable(LPVOID *this)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 i; // rsi

  *this = &CPropertyMapTable::`vftable';
  CoTaskMemFree(this[2]);
  this[2] = 0;
  v2 = (unsigned __int64 *)(this + 4);
  if ( this[3] )
  {
    for ( i = 0; i < *v2; ++i )
      ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>();
    CoTaskMemFree(this[3]);
    this[3] = 0;
  }
  this[6] = 0;
  *v2 = 0;
  *this = &CTRefBase<CPropertyMapTable,IUnknown,CTRefBase_NoModuleLifetimePolicy>::`vftable';
}

```

## disassembly

```asm
0x180048bd4  mov     [rsp+arg_0], rbx
0x180048bd9  mov     [rsp+arg_8], rsi
0x180048bde  push    rdi
0x180048bdf  sub     rsp, 20h
0x180048be3  lea     rax, ??_7CPropertyMapTable@@6B@; const CPropertyMapTable::`vftable'
0x180048bea  mov     rbx, rcx
0x180048bed  mov     [rcx], rax
0x180048bf0  mov     rcx, [rcx+10h]; pv
0x180048bf4  call    cs:__imp_CoTaskMemFree
0x180048bfa  mov     qword ptr [rbx+10h], 0
0x180048c02  lea     rdi, [rbx+20h]
0x180048c06  cmp     qword ptr [rbx+18h], 0
0x180048c0b  jz      short loc_180048C3B
0x180048c0d  xor     esi, esi
0x180048c0f  cmp     [rdi], rsi
0x180048c12  jbe     short loc_180048C29
0x180048c14  mov     rax, [rbx+18h]
0x180048c18  lea     rcx, [rax+rsi*8]
0x180048c1c  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x180048c21  inc     rsi
0x180048c24  cmp     rsi, [rdi]
0x180048c27  jb      short loc_180048C14
0x180048c29  mov     rcx, [rbx+18h]; pv
0x180048c2d  call    cs:__imp_CoTaskMemFree
0x180048c33  mov     qword ptr [rbx+18h], 0
0x180048c3b  mov     rsi, [rsp+28h+arg_8]
0x180048c40  lea     rax, ??_7?$CTRefBase@VCPropertyMapTable@@UIUnknown@@VCTRefBase_NoModuleLifetimePolicy@@@@6B@; const CTRefBase<CPropertyMapTable,IUnknown,CTRefBase_NoModuleLifetimePolicy>::`vftable'
0x180048c47  mov     qword ptr [rbx+30h], 0
0x180048c4f  mov     qword ptr [rdi], 0
0x180048c56  mov     [rbx], rax
0x180048c59  mov     rbx, [rsp+28h+arg_0]
0x180048c5e  add     rsp, 20h
0x180048c62  pop     rdi
0x180048c63  retn
```
