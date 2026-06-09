# UICollection::GetScrollTickCount(void)

- ea: `0x1800ae210`
- end: `0x1800ae310`
- name: `?GetScrollTickCount@UICollection@@UEAAHXZ`
- size: `256`
- prototype: `__int64 __fastcall(UICollection *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001743c`
- `0x1800174e8`
- `0x1800ae210`

## import_xrefs

- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x1800ae28c`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x1800ae28c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae24b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae2cb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae2f9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae24b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae2cb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae2f9`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae23f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae2c0`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae2ee`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae23f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae2c0`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800ae2ee`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae233`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae2b4`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae2e2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae233`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae2b4`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae2e2`

## pseudocode

```c
__int64 __fastcall UICollection::GetScrollTickCount(UICollection *this)
{
  char *v1; // rdi
  DirectUI::Value *Value; // rbx
  int Int; // r14d
  int v4; // ebp
  DirectUI::Element *DescendentElement; // rsi
  DirectUI::Element *v6; // rcx
  DirectUI::Value *v7; // rbx
  DirectUI::Value *v8; // rdi
  int v9; // ebx

  v1 = (char *)this - 216;
  Value = DirectUI::Element::GetValue((UICollection *)((char *)this - 216), UICollection::HeaderScrollTicksProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  v4 = 0;
  if ( !*((_QWORD *)v1 + 29) )
  {
    DescendentElement = _FindDescendentElement((struct DirectUI::Element *)v1, ItemLayout::Class);
    CSafeElementPtr<ItemRowLayout>::Unassign(v1 + 224);
    if ( DescendentElement )
    {
      *((_QWORD *)v1 + 29) = DescendentElement;
      if ( (int)DirectUI::Element::AddListener(DescendentElement, (struct DirectUI::IElementListener *)(v1 + 224)) < 0 )
        *((_QWORD *)v1 + 29) = 0;
    }
  }
  v6 = (DirectUI::Element *)*((_QWORD *)v1 + 29);
  if ( v6 )
  {
    v7 = DirectUI::Element::GetValue(v6, ItemLayout::ScrollTickCountProp, 2, 0);
    v4 = DirectUI::Value::GetInt(v7);
    DirectUI::Value::Release(v7);
  }
  v8 = DirectUI::Element::GetValue((DirectUI::Element *)v1, UICollection::FooterScrollTicksProp, 2, 0);
  v9 = DirectUI::Value::GetInt(v8);
  DirectUI::Value::Release(v8);
  return (unsigned int)(Int + v9 + v4);
}

```

## disassembly

```asm
0x1800ae210  push    rbx
0x1800ae212  push    rbp
0x1800ae213  push    rsi
0x1800ae214  push    rdi
0x1800ae215  push    r14
0x1800ae217  sub     rsp, 20h
0x1800ae21b  xor     r9d, r9d
0x1800ae21e  lea     rdi, [rcx-0D8h]
0x1800ae225  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x1800ae22c  mov     rcx, rdi
0x1800ae22f  lea     r8d, [r9+2]
0x1800ae233  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae239  mov     rcx, rax
0x1800ae23c  mov     rbx, rax
0x1800ae23f  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800ae245  mov     rcx, rbx
0x1800ae248  mov     r14d, eax
0x1800ae24b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae251  xor     ebp, ebp
0x1800ae253  cmp     [rdi+0E8h], rbp
0x1800ae25a  jnz     short loc_1800AE29A
0x1800ae25c  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x1800ae263  lea     rbx, [rdi+0E0h]
0x1800ae26a  mov     rcx, rdi; struct DirectUI::Element *
0x1800ae26d  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x1800ae272  mov     rcx, rbx
0x1800ae275  mov     rsi, rax
0x1800ae278  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x1800ae27d  test    rsi, rsi
0x1800ae280  jz      short loc_1800AE29A
0x1800ae282  mov     rdx, rbx
0x1800ae285  mov     [rbx+8], rsi
0x1800ae289  mov     rcx, rsi
0x1800ae28c  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x1800ae292  test    eax, eax
0x1800ae294  jns     short loc_1800AE29A
0x1800ae296  mov     [rbx+8], rbp
0x1800ae29a  mov     rcx, [rdi+0E8h]
0x1800ae2a1  test    rcx, rcx
0x1800ae2a4  jz      short loc_1800AE2D1
0x1800ae2a6  xor     r9d, r9d
0x1800ae2a9  lea     rdx, ?ScrollTickCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ScrollTickCountProp(void)
0x1800ae2b0  lea     r8d, [r9+2]
0x1800ae2b4  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae2ba  mov     rcx, rax
0x1800ae2bd  mov     rbx, rax
0x1800ae2c0  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800ae2c6  mov     rcx, rbx
0x1800ae2c9  mov     ebp, eax
0x1800ae2cb  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae2d1  xor     r9d, r9d
0x1800ae2d4  lea     rdx, ?FooterScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::FooterScrollTicksProp(void)
0x1800ae2db  mov     rcx, rdi
0x1800ae2de  lea     r8d, [r9+2]
0x1800ae2e2  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae2e8  mov     rcx, rax
0x1800ae2eb  mov     rdi, rax
0x1800ae2ee  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800ae2f4  mov     rcx, rdi
0x1800ae2f7  mov     ebx, eax
0x1800ae2f9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae2ff  lea     eax, [rbx+rbp]
0x1800ae302  add     eax, r14d
0x1800ae305  add     rsp, 20h
0x1800ae309  pop     r14
0x1800ae30b  pop     rdi
0x1800ae30c  pop     rsi
0x1800ae30d  pop     rbp
0x1800ae30e  pop     rbx
0x1800ae30f  retn
```
