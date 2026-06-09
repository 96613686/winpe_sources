# ARPExpandable::SetExpanded(bool)

- ea: `0x18000e11c`
- end: `0x18000e171`
- name: `?SetExpanded@ARPExpandable@@QEAAJ_N@Z`
- size: `85`
- prototype: `__int64 __fastcall(ARPExpandable *__hidden this, bool)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009da0`
- `0x18000b3dc`
- `0x18000c620`
- `0x18000c780`
- `0x18000e7a0`

## callees

- `0x18000e11c`

## import_xrefs

- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x18000e12b`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x18000e12b`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x18000e153`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x18000e153`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e15e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e15e`

## pseudocode

```c
__int64 __fastcall ARPExpandable::SetExpanded(ARPExpandable *this, bool a2)
{
  struct DirectUI::Value *Bool; // rax
  DirectUI::Value *v4; // rdi
  unsigned int v6; // ebx

  Bool = DirectUI::Value::CreateBool(a2);
  v4 = Bool;
  if ( !Bool )
    return 2147942414LL;
  v6 = DirectUI::Element::SetValue(this, (const struct DirectUI::PropertyInfo *)&off_1800774B8, 1, Bool);
  DirectUI::Value::Release(v4);
  return v6;
}

```

## disassembly

```asm
0x18000e11c  mov     [rsp+arg_0], rbx
0x18000e121  push    rdi
0x18000e122  sub     rsp, 20h
0x18000e126  mov     rbx, rcx
0x18000e129  mov     cl, dl
0x18000e12b  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x18000e131  mov     rdi, rax
0x18000e134  test    rax, rax
0x18000e137  jnz     short loc_18000E140
0x18000e139  mov     eax, 8007000Eh
0x18000e13e  jmp     short loc_18000E166
0x18000e140  mov     r9, rdi
0x18000e143  lea     rdx, off_1800774B8; "Expanded"
0x18000e14a  mov     r8d, 1
0x18000e150  mov     rcx, rbx
0x18000e153  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x18000e159  mov     rcx, rdi
0x18000e15c  mov     ebx, eax
0x18000e15e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e164  mov     eax, ebx
0x18000e166  mov     rbx, [rsp+28h+arg_0]
0x18000e16b  add     rsp, 20h
0x18000e16f  pop     rdi
0x18000e170  retn
```
