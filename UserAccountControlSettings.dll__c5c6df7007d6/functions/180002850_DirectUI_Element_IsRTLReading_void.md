# DirectUI::Element::IsRTLReading(void)

- ea: `0x180002850`
- end: `0x180002856`
- name: `?IsRTLReading@Element@DirectUI@@UEAA_NXZ_0`
- size: `6`
- prototype: `bool __fastcall(DirectUI::Element *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?IsRTLReading@Element@DirectUI@@UEAA_NXZ` at `0x180002850`

## pseudocode

```c
// attributes: thunk
bool __fastcall DirectUI::Element::IsRTLReading(DirectUI::Element *this)
{
  return __imp_?IsRTLReading@Element@DirectUI@@UEAA_NXZ(this);
}

```

## disassembly

```asm
0x180002850  jmp     cs:__imp_?IsRTLReading@Element@DirectUI@@UEAA_NXZ
```
