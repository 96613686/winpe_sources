# CEnumMetadataItem::CEnumMetadataItem(IWICMetadataReader *)

- ea: `0x18002d930`
- end: `0x18002d9ba`
- name: `??0CEnumMetadataItem@@QEAA@PEAUIWICMetadataReader@@@Z`
- size: `138`
- prototype: `CEnumMetadataItem *__fastcall(CEnumMetadataItem *__hidden this, struct IWICMetadataReader *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002be80`
- `0x18002da10`

## callees

- `0x1800096bc`
- `0x180033010`

## pseudocode

```c
CEnumMetadataItem *__fastcall CEnumMetadataItem::CEnumMetadataItem(
        CEnumMetadataItem *this,
        struct IWICMetadataReader *a2)
{
  CEnumMetadataItem *result; // rax

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CMILCOMBase::`vftable';
  _InterlockedIncrement(&g_cActiveObjects);
  CMTALock::CMTALock((CEnumMetadataItem *)((char *)this + 16));
  *((_QWORD *)this + 12) = a2;
  *(_QWORD *)this = &CEnumMetadataItem::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 2) = &CEnumMetadataItem::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 9) = &CEnumMetadataItem::`vftable'{for `IWICEnumMetadataItem'};
  ((void (__fastcall *)(struct IWICMetadataReader *))a2->lpVtbl->AddRef)(a2);
  result = this;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 22) = 0;
  return result;
}

```

## disassembly

```asm
0x18002d930  mov     [rsp+arg_0], rbx
0x18002d935  mov     [rsp+arg_8], rsi
0x18002d93a  push    rdi
0x18002d93b  sub     rsp, 20h
0x18002d93f  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18002d946  mov     dword ptr [rcx+8], 0
0x18002d94d  mov     [rcx], rax
0x18002d950  mov     rdi, rdx
0x18002d953  mov     rsi, rcx
0x18002d956  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002d95d  add     rcx, 10h; this
0x18002d961  call    ??0CMTALock@@QEAA@XZ; CMTALock::CMTALock(void)
0x18002d966  lea     rax, ??_7CEnumMetadataItem@@6BCMILCOMBase@@@; const CEnumMetadataItem::`vftable'{for `CMILCOMBase'}
0x18002d96d  mov     [rsi+60h], rdi
0x18002d971  mov     [rsi], rax
0x18002d974  mov     rcx, rdi
0x18002d977  lea     rax, ??_7CEnumMetadataItem@@6BCMTALock@@@; const CEnumMetadataItem::`vftable'{for `CMTALock'}
0x18002d97e  mov     [rsi+10h], rax
0x18002d982  lea     rax, ??_7CEnumMetadataItem@@6BIWICEnumMetadataItem@@@; const CEnumMetadataItem::`vftable'{for `IWICEnumMetadataItem'}
0x18002d989  mov     [rsi+48h], rax
0x18002d98d  mov     rax, [rdi]
0x18002d990  mov     rax, [rax+8]
0x18002d994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d999  mov     rbx, [rsp+28h+arg_0]
0x18002d99e  mov     rax, rsi
0x18002d9a1  mov     dword ptr [rsi+50h], 0
0x18002d9a8  mov     dword ptr [rsi+58h], 0
0x18002d9af  mov     rsi, [rsp+28h+arg_8]
0x18002d9b4  add     rsp, 20h
0x18002d9b8  pop     rdi
0x18002d9b9  retn
```
