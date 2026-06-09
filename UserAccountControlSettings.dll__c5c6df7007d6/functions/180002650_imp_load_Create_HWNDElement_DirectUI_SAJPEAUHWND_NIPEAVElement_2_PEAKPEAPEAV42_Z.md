# __imp_load_?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z

- ea: `0x180002650`
- end: `0x18000265c`
- name: `__imp_load_?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z` at `0x180002650`

## pseudocode

```c
__int64 load__Create_HWNDElement_DirectUI__SAJPEAUHWND_____NIPEAVElement_2_PEAKPEAPEAV42__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002650  lea     rax, __imp_?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z; DirectUI::HWNDElement::Create(HWND__ *,bool,uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180002657  jmp     __tailMerge_dui70_dll
```
