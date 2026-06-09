# _GetCustomText(DirectUI::Element *,DirectUI::Value * *)

- ea: `0x18002a02c`
- end: `0x18002a07b`
- name: `?_GetCustomText@@YAPEBGPEAVElement@DirectUI@@PEAPEAVValue@2@@Z`
- size: `79`
- prototype: `const unsigned __int16 *__fastcall(struct DirectUI::Element *, struct DirectUI::Value **)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180029d20`

## callees

- `0x18002a02c`

## import_xrefs

- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002a066`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002a066`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002a058`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002a058`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18002a047`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18002a047`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18002a03c`

## pseudocode

```c
const unsigned __int16 *__fastcall _GetCustomText(struct DirectUI::Element *a1, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax
  DirectUI::Value *v4; // rdi

  Value = DirectUI::Element::GetValue(
            a1,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
            1,
            0);
  *a2 = Value;
  v4 = Value;
  if ( !Value || Value == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    return 0;
  else
    return DirectUI::Value::GetString(v4);
}

```

## disassembly

```asm
0x18002a02c  mov     [rsp+arg_0], rbx
0x18002a031  push    rdi
0x18002a032  sub     rsp, 20h
0x18002a036  xor     r9d, r9d
0x18002a039  mov     rbx, rdx
0x18002a03c  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x18002a043  lea     r8d, [r9+1]
0x18002a047  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18002a04d  mov     [rbx], rax
0x18002a050  mov     rdi, rax
0x18002a053  test    rax, rax
0x18002a056  jz      short loc_18002A06E
0x18002a058  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18002a05e  cmp     rdi, rax
0x18002a061  jz      short loc_18002A06E
0x18002a063  mov     rcx, rdi
0x18002a066  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002a06c  jmp     short loc_18002A070
0x18002a06e  xor     eax, eax
0x18002a070  mov     rbx, [rsp+28h+arg_0]
0x18002a075  add     rsp, 20h
0x18002a079  pop     rdi
0x18002a07a  retn
```
