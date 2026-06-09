# UICollection::GetSectionCount(void)

- ea: `0x1800179e0`
- end: `0x180017af3`
- name: `?GetSectionCount@UICollection@@UEAAHXZ`
- size: `275`
- prototype: `__int64 __fastcall(UICollection *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001743c`
- `0x1800174e8`
- `0x1800179e0`

## import_xrefs

- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180017a66`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180017a66`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017a1a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017aa9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017ad9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017a1a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017aa9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017ad9`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017a0f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017a9e`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017ace`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017a0f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017a9e`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180017ace`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017a03`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017a92`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017ac2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017a03`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017a92`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180017ac2`

## pseudocode

```c
__int64 __fastcall UICollection::GetSectionCount(UICollection *this)
{
  char *v1; // rbx
  DirectUI::Value *Value; // rdi
  int Int; // esi
  BOOL v4; // ebp
  DirectUI::Element *DescendentElement; // rsi
  DirectUI::Value *v6; // rdi
  int v7; // esi
  DirectUI::Value *v8; // rbx

  v1 = (char *)this - 216;
  Value = DirectUI::Element::GetValue((UICollection *)((char *)this - 216), UICollection::HeaderScrollTicksProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  v4 = Int != 0;
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
  v6 = DirectUI::Element::GetValue(*((DirectUI::Element **)v1 + 29), ItemLayout::SectionCountProp, 2, 0);
  v7 = DirectUI::Value::GetInt(v6);
  DirectUI::Value::Release(v6);
  v8 = DirectUI::Element::GetValue((DirectUI::Element *)v1, UICollection::FooterScrollTicksProp, 2, 0);
  LODWORD(v6) = DirectUI::Value::GetInt(v8);
  DirectUI::Value::Release(v8);
  return v7 + v4 + (unsigned int)((_DWORD)v6 != 0);
}

```

## disassembly

```asm
0x1800179e0  push    rbx
0x1800179e2  push    rbp
0x1800179e3  push    rsi
0x1800179e4  push    rdi
0x1800179e5  sub     rsp, 28h
0x1800179e9  lea     rbx, [rcx-0D8h]
0x1800179f0  xor     r9d, r9d
0x1800179f3  mov     rcx, rbx
0x1800179f6  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x1800179fd  mov     r8d, 2
0x180017a03  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180017a09  mov     rcx, rax
0x180017a0c  mov     rdi, rax
0x180017a0f  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180017a15  mov     rcx, rdi
0x180017a18  mov     esi, eax
0x180017a1a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017a20  xor     ebp, ebp
0x180017a22  test    esi, esi
0x180017a24  setnz   bpl
0x180017a28  cmp     qword ptr [rbx+0E8h], 0
0x180017a30  jnz     short loc_180017A7B
0x180017a32  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180017a39  mov     rcx, rbx; struct DirectUI::Element *
0x180017a3c  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180017a41  lea     rcx, [rbx+0E0h]
0x180017a48  mov     rsi, rax
0x180017a4b  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180017a50  test    rsi, rsi
0x180017a53  jz      short loc_180017A7B
0x180017a55  lea     rdx, [rbx+0E0h]
0x180017a5c  mov     [rbx+0E8h], rsi
0x180017a63  mov     rcx, rsi
0x180017a66  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180017a6c  test    eax, eax
0x180017a6e  jns     short loc_180017A7B
0x180017a70  mov     qword ptr [rbx+0E8h], 0
0x180017a7b  mov     rcx, [rbx+0E8h]
0x180017a82  lea     rdx, ?SectionCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::SectionCountProp(void)
0x180017a89  xor     r9d, r9d
0x180017a8c  mov     r8d, 2
0x180017a92  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180017a98  mov     rcx, rax
0x180017a9b  mov     rdi, rax
0x180017a9e  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180017aa4  mov     rcx, rdi
0x180017aa7  mov     esi, eax
0x180017aa9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017aaf  xor     r9d, r9d
0x180017ab2  lea     rdx, ?FooterScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::FooterScrollTicksProp(void)
0x180017ab9  mov     r8d, 2
0x180017abf  mov     rcx, rbx
0x180017ac2  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180017ac8  mov     rcx, rax
0x180017acb  mov     rbx, rax
0x180017ace  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180017ad4  mov     rcx, rbx
0x180017ad7  mov     edi, eax
0x180017ad9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017adf  xor     eax, eax
0x180017ae1  test    edi, edi
0x180017ae3  setnz   al
0x180017ae6  add     eax, ebp
0x180017ae8  add     eax, esi
0x180017aea  add     rsp, 28h
0x180017aee  pop     rdi
0x180017aef  pop     rsi
0x180017af0  pop     rbp
0x180017af1  pop     rbx
0x180017af2  retn
```
