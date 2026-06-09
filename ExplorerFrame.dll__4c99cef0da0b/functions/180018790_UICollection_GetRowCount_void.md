# UICollection::GetRowCount(void)

- ea: `0x180018790`
- end: `0x18001889c`
- name: `?GetRowCount@UICollection@@UEAAHXZ`
- size: `268`
- prototype: `__int64 __fastcall(UICollection *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001743c`
- `0x1800174e8`
- `0x180018790`

## import_xrefs

- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018813`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018813`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800187ca`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018851`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001887f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800187ca`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018851`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001887f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800187bf`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018846`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018874`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800187bf`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018846`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018874`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800187b3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001883a`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018868`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800187b3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001883a`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018868`

## pseudocode

```c
__int64 __fastcall UICollection::GetRowCount(UICollection *this)
{
  char *v1; // rbp
  DirectUI::Value *Value; // rbx
  int Int; // edi
  BOOL v4; // r14d
  DirectUI::Element *DescendentElement; // rdi
  DirectUI::Value *v6; // rbx
  int v7; // esi
  DirectUI::Value *v8; // rbx
  int v9; // edi

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
  v6 = DirectUI::Element::GetValue(*((DirectUI::Element **)v1 + 29), ItemLayout::RowCountProp, 2, 0);
  v7 = DirectUI::Value::GetInt(v6);
  DirectUI::Value::Release(v6);
  v8 = DirectUI::Element::GetValue((DirectUI::Element *)v1, UICollection::FooterScrollTicksProp, 2, 0);
  v9 = DirectUI::Value::GetInt(v8);
  DirectUI::Value::Release(v8);
  return v7 + v4 + (unsigned int)(v9 != 0);
}

```

## disassembly

```asm
0x180018790  push    rbx
0x180018792  push    rbp
0x180018793  push    rsi
0x180018794  push    rdi
0x180018795  push    r14
0x180018797  sub     rsp, 20h
0x18001879b  xor     r9d, r9d
0x18001879e  lea     rbp, [rcx-0D8h]
0x1800187a5  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x1800187ac  mov     rcx, rbp
0x1800187af  lea     r8d, [r9+2]
0x1800187b3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800187b9  mov     rcx, rax
0x1800187bc  mov     rbx, rax
0x1800187bf  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800187c5  mov     rcx, rbx
0x1800187c8  mov     edi, eax
0x1800187ca  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800187d0  xor     r14d, r14d
0x1800187d3  test    edi, edi
0x1800187d5  setnz   r14b
0x1800187d9  cmp     qword ptr [rbp+0E8h], 0
0x1800187e1  jnz     short loc_180018825
0x1800187e3  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x1800187ea  lea     rbx, [rbp+0E0h]
0x1800187f1  mov     rcx, rbp; struct DirectUI::Element *
0x1800187f4  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x1800187f9  mov     rcx, rbx
0x1800187fc  mov     rdi, rax
0x1800187ff  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018804  test    rdi, rdi
0x180018807  jz      short loc_180018825
0x180018809  mov     rdx, rbx
0x18001880c  mov     [rbx+8], rdi
0x180018810  mov     rcx, rdi
0x180018813  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018819  test    eax, eax
0x18001881b  jns     short loc_180018825
0x18001881d  mov     qword ptr [rbx+8], 0
0x180018825  mov     rcx, [rbp+0E8h]
0x18001882c  lea     rdx, ?RowCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::RowCountProp(void)
0x180018833  xor     r9d, r9d
0x180018836  lea     r8d, [r9+2]
0x18001883a  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180018840  mov     rcx, rax
0x180018843  mov     rbx, rax
0x180018846  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001884c  mov     rcx, rbx
0x18001884f  mov     esi, eax
0x180018851  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018857  xor     r9d, r9d
0x18001885a  lea     rdx, ?FooterScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::FooterScrollTicksProp(void)
0x180018861  mov     rcx, rbp
0x180018864  lea     r8d, [r9+2]
0x180018868  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001886e  mov     rcx, rax
0x180018871  mov     rbx, rax
0x180018874  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001887a  mov     rcx, rbx
0x18001887d  mov     edi, eax
0x18001887f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018885  xor     eax, eax
0x180018887  test    edi, edi
0x180018889  setnz   al
0x18001888c  add     eax, r14d
0x18001888f  add     eax, esi
0x180018891  add     rsp, 20h
0x180018895  pop     r14
0x180018897  pop     rdi
0x180018898  pop     rsi
0x180018899  pop     rbp
0x18001889a  pop     rbx
0x18001889b  retn
```
