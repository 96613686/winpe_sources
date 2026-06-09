# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x18002a908`
- end: `0x18002a937`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x18002ab60`
- `0x18002af4c`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002a91f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002a91f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002a930`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_18002FBC0, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x18002a908  push    rbx
0x18002a90a  sub     rsp, 20h
0x18002a90e  xor     r9d, r9d
0x18002a911  mov     rbx, rdx
0x18002a914  lea     rdx, off_18002FBC0; "ShellExecute"
0x18002a91b  lea     r8d, [r9+2]
0x18002a91f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002a925  mov     rcx, rax
0x18002a928  mov     [rbx], rax
0x18002a92b  add     rsp, 20h
0x18002a92f  pop     rbx
0x18002a930  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
