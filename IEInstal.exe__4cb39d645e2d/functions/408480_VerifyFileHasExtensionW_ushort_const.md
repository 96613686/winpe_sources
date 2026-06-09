# VerifyFileHasExtensionW(ushort const *)

- ea: `0x408480`
- end: `0x4084a8`
- name: `?VerifyFileHasExtensionW@@YGJPBG@Z`
- size: `40`
- prototype: `int __thiscall(const WCHAR *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x40373b`
- `0x403d84`
- `0x403ffd`
- `0x404214`
- `0x4044ae`

## callees

- `0x4083bc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x40849d`
- `ole32!CoTaskMemFree` at `0x40849d`

## pseudocode

```c
int __thiscall VerifyFileHasExtensionW(const WCHAR *this)
{
  int FullPathNameW; // esi
  unsigned __int16 **v3; // [esp+0h] [ebp-8h]
  LPVOID pv; // [esp+4h] [ebp-4h] BYREF

  FullPathNameW = AxiGetFullPathNameW(this, (unsigned __int16 *)&pv, (int)this, v3, 0);
  CoTaskMemFree(pv);
  return FullPathNameW;
}

```

## disassembly

```asm
0x408480  mov     edi, edi
0x408482  push    ebp
0x408483  mov     ebp, esp
0x408485  push    ecx; unsigned __int16 **
0x408486  push    esi; unsigned __int16 **
0x408487  push    ecx; int
0x408488  lea     eax, [ebp+pv]
0x40848b  mov     [ebp+pv], 0
0x408492  push    eax; unsigned __int16 *
0x408493  call    ?AxiGetFullPathNameW@@YGJPBGHPAPAGPAPBG@Z; AxiGetFullPathNameW(ushort const *,int,ushort * *,ushort const * *)
0x408498  push    [ebp+pv]; pv
0x40849b  mov     esi, eax
0x40849d  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x4084a3  mov     eax, esi
0x4084a5  pop     esi
0x4084a6  leave
0x4084a7  retn
```
