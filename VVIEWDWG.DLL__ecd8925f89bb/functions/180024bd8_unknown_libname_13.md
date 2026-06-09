# unknown_libname_13

- ea: `0x180024bd8`
- end: `0x180024bf0`
- name: `unknown_libname_13`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024bb0`

## import_xrefs

- `mfc140u!__imp_??1?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@XZ` at `0x180024be1`
- `mfc140u!__imp_??1?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@XZ` at `0x180024be1`

## pseudocode

```c
// Microsoft VisualC v7/14 64bit runtime
__int64 __fastcall unknown_libname_13(__int64 a1)
{
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::~CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(a1);
  return a1;
}

```

## disassembly

```asm
0x180024bd8  push    rbx
0x180024bda  sub     rsp, 20h
0x180024bde  mov     rbx, rcx
0x180024be1  call    cs:__imp_??1?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@XZ
0x180024be7  mov     rax, rbx
0x180024bea  add     rsp, 20h
0x180024bee  pop     rbx
0x180024bef  retn
```
