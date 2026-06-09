# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x18000a218`
- end: `0x18000a247`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a4a0`
- `0x18000a8e0`

## import_xrefs

- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000a240`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a22f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a22f`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_18000D960, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x18000a218  push    rbx
0x18000a21a  sub     rsp, 20h
0x18000a21e  xor     r9d, r9d
0x18000a221  mov     rbx, rdx
0x18000a224  lea     rdx, off_18000D960; "ShellExecute"
0x18000a22b  lea     r8d, [r9+2]
0x18000a22f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000a235  mov     rcx, rax
0x18000a238  mov     [rbx], rax
0x18000a23b  add     rsp, 20h
0x18000a23f  pop     rbx
0x18000a240  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
