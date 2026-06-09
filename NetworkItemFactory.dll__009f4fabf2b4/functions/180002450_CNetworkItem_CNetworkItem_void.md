# CNetworkItem::~CNetworkItem(void)

- ea: `0x180002450`
- end: `0x180002537`
- name: `??1CNetworkItem@@AEAA@XZ`
- size: `231`
- prototype: `void __fastcall(CNetworkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002d70`

## callees

- `0x180002450`
- `0x18000b010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800024e6`
- `ole32!PropVariantClear` at `0x1800024f0`
- `ole32!PropVariantClear` at `0x1800024fd`
- `ole32!PropVariantClear` at `0x18000250a`
- `ole32!PropVariantClear` at `0x180002517`
- `ole32!PropVariantClear` at `0x180002524`
- `ole32!PropVariantClear` at `0x1800024e6`
- `ole32!PropVariantClear` at `0x1800024f0`
- `ole32!PropVariantClear` at `0x1800024fd`
- `ole32!PropVariantClear` at `0x18000250a`
- `ole32!PropVariantClear` at `0x180002517`
- `ole32!PropVariantClear` at `0x180002524`
- `ole32!CoTaskMemFree` at `0x1800024ae`
- `ole32!CoTaskMemFree` at `0x1800024b8`
- `ole32!CoTaskMemFree` at `0x1800024c2`
- `ole32!CoTaskMemFree` at `0x1800024cf`
- `ole32!CoTaskMemFree` at `0x1800024dc`
- `ole32!CoTaskMemFree` at `0x1800024ae`
- `ole32!CoTaskMemFree` at `0x1800024b8`
- `ole32!CoTaskMemFree` at `0x1800024c2`
- `ole32!CoTaskMemFree` at `0x1800024cf`
- `ole32!CoTaskMemFree` at `0x1800024dc`
- `ole32!CoReleaseMarshalData` at `0x180002494`
- `ole32!CoReleaseMarshalData` at `0x180002494`

## pseudocode

```c
void __fastcall CNetworkItem::~CNetworkItem(CNetworkItem *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CNetworkItem::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v2 + 40LL))(v2, 0, 0, 0) >= 0 )
      CoReleaseMarshalData(*((LPSTREAM *)this + 2));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
  }
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 27));
  CoTaskMemFree(*((LPVOID *)this + 35));
  PropVariantClear((PROPVARIANT *)this + 9);
  PropVariantClear((PROPVARIANT *)this + 12);
  PropVariantClear((PROPVARIANT *)this + 29);
  PropVariantClear((PROPVARIANT *)this + 24);
  PropVariantClear((PROPVARIANT *)this + 16);
  PropVariantClear((PROPVARIANT *)this + 19);
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x180002450  push    rbx
0x180002452  sub     rsp, 30h
0x180002456  mov     rbx, rcx
0x180002459  lea     rax, ??_7CNetworkItem@@6B@; const CNetworkItem::`vftable'
0x180002460  mov     [rcx], rax
0x180002463  mov     rcx, [rcx+10h]
0x180002467  test    rcx, rcx
0x18000246a  jz      short loc_1800024AA
0x18000246c  mov     [rsp+38h+arg_0], 0
0x180002475  mov     rax, [rcx]
0x180002478  xor     r9d, r9d
0x18000247b  xor     r8d, r8d
0x18000247e  mov     rdx, [rsp+38h+arg_0]
0x180002483  mov     rax, [rax+28h]
0x180002487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248c  test    eax, eax
0x18000248e  js      short loc_18000249A
0x180002490  mov     rcx, [rbx+10h]; pStm
0x180002494  call    cs:__imp_CoReleaseMarshalData
0x18000249a  mov     rcx, [rbx+10h]
0x18000249e  mov     rax, [rcx]
0x1800024a1  mov     rax, [rax+10h]
0x1800024a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024aa  mov     rcx, [rbx+18h]; pv
0x1800024ae  call    cs:__imp_CoTaskMemFree
0x1800024b4  mov     rcx, [rbx+20h]; pv
0x1800024b8  call    cs:__imp_CoTaskMemFree
0x1800024be  mov     rcx, [rbx+30h]; pv
0x1800024c2  call    cs:__imp_CoTaskMemFree
0x1800024c8  mov     rcx, [rbx+0D8h]; pv
0x1800024cf  call    cs:__imp_CoTaskMemFree
0x1800024d5  mov     rcx, [rbx+118h]; pv
0x1800024dc  call    cs:__imp_CoTaskMemFree
0x1800024e2  lea     rcx, [rbx+48h]; pvar
0x1800024e6  call    cs:__imp_PropVariantClear
0x1800024ec  lea     rcx, [rbx+60h]; pvar
0x1800024f0  call    cs:__imp_PropVariantClear
0x1800024f6  lea     rcx, [rbx+0E8h]; pvar
0x1800024fd  call    cs:__imp_PropVariantClear
0x180002503  lea     rcx, [rbx+0C0h]; pvar
0x18000250a  call    cs:__imp_PropVariantClear
0x180002510  lea     rcx, [rbx+80h]; pvar
0x180002517  call    cs:__imp_PropVariantClear
0x18000251d  lea     rcx, [rbx+98h]; pvar
0x180002524  call    cs:__imp_PropVariantClear
0x18000252a  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180002531  add     rsp, 30h
0x180002535  pop     rbx
0x180002536  retn
```
