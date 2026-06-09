# CTryHarderItem::~CTryHarderItem(void)

- ea: `0x18003dadc`
- end: `0x18003db40`
- name: `??1CTryHarderItem@@MEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CTryHarderItem *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003db60`

## callees

- `0x1800127ac`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18003db20`
- `SHELL32!__imp_ILFree` at `0x18003db20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db16`

## pseudocode

```c
void __fastcall CTryHarderItem::~CTryHarderItem(CTryHarderItem *this)
{
  *(_QWORD *)this = &CTryHarderItem::`vftable'{for `ITryHarderItem'};
  *((_QWORD *)this + 1) = &CTryHarderItem::`vftable'{for `CObjectWithSite'};
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 7));
  CoTaskMemFree(*((LPVOID *)this + 8));
  ILFree(*((LPITEMIDLIST *)this + 4));
  _InterlockedDecrement(&g_cDllRef);
  CObjectWithSite::~CObjectWithSite((CTryHarderItem *)((char *)this + 8));
}

```

## disassembly

```asm
0x18003dadc  mov     [rsp+arg_0], rbx
0x18003dae1  push    rdi
0x18003dae2  sub     rsp, 20h
0x18003dae6  lea     rax, ??_7CTryHarderItem@@6BITryHarderItem@@@; const CTryHarderItem::`vftable'{for `ITryHarderItem'}
0x18003daed  mov     rdi, rcx
0x18003daf0  mov     [rcx], rax
0x18003daf3  lea     rax, ??_7CTryHarderItem@@6BCObjectWithSite@@@; const CTryHarderItem::`vftable'{for `CObjectWithSite'}
0x18003dafa  mov     [rcx+8], rax
0x18003dafe  mov     rcx, [rcx+30h]; pv
0x18003db02  call    cs:__imp_CoTaskMemFree
0x18003db08  mov     rcx, [rdi+38h]; pv
0x18003db0c  call    cs:__imp_CoTaskMemFree
0x18003db12  mov     rcx, [rdi+40h]; pv
0x18003db16  call    cs:__imp_CoTaskMemFree
0x18003db1c  mov     rcx, [rdi+20h]; pidl
0x18003db20  call    cs:__imp_ILFree
0x18003db26  lock dec cs:?g_cDllRef@@3JA; long g_cDllRef
0x18003db2d  lea     rcx, [rdi+8]; this
0x18003db31  mov     rbx, [rsp+28h+arg_0]
0x18003db36  add     rsp, 20h
0x18003db3a  pop     rdi
0x18003db3b  jmp     ??1CObjectWithSite@@UEAA@XZ; CObjectWithSite::~CObjectWithSite(void)
```
