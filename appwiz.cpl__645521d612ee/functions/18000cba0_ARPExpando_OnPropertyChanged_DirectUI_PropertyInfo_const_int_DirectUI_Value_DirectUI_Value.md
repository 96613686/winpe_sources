# ARPExpando::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)

- ea: `0x18000cba0`
- end: `0x18000cc9c`
- name: `?OnPropertyChanged@ARPExpando@@UEAAXPEBUPropertyInfo@DirectUI@@HPEAVValue@3@1@Z`
- size: `252`
- prototype: `void __usercall(ARPExpando *__hidden this@<rcx>, const struct DirectUI::PropertyInfo *@<rdx>, int@<r8d>, struct DirectUI::Value *@<r9>, struct DirectUI::Value *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008ad8`
- `0x18000ac0c`
- `0x18000b13c`
- `0x18000bdfc`
- `0x18000cba0`
- `0x18000fd28`

## import_xrefs

- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc26`
- `DUI70!?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc76`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000cc6e`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000cc6e`
- `DUI70!?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cbc5`
- `DUI70!?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc5e`
- `DUI70!?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z` at `0x18000cbbf`
- `DUI70!?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z` at `0x18000cbbf`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18000cc2d`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18000cc2d`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18000cc37`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18000cc37`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000cc19`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000cc19`

## pseudocode

```c
void __fastcall ARPExpando::OnPropertyChanged(
        ARPExpando *this,
        const struct DirectUI::PropertyInfo *a2,
        int a3,
        struct DirectUI::Value *a4,
        struct DirectUI::Value *a5)
{
  DirectUI::Element *NthChild; // rbx
  DirectUI::Element *DescendentByName; // rax

  DirectUI::Element::OnPropertyChanged(this, a2, a3, a4, a5);
  if ( !DirectUI::PropNotify::IsEqual(a2, a3, DirectUI::Element::SelectedProp) )
  {
    if ( a2 == (const struct DirectUI::PropertyInfo *)&off_1800774B8 && (*((_DWORD *)a2 + 2) & 3) == a3 )
    {
      NthChild = GetNthChild(this, 1u);
      if ( NthChild )
      {
        *((_BYTE *)this + 200) = 1;
        if ( DirectUI::Value::GetBool(a5) )
          DirectUI::Element::RemoveLocalValue(
            NthChild,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp);
        else
          DirectUI::Element::SetHeight(NthChild, 0);
        TraverseTree<ClientPicker>(NthChild, _SetParentExpandedProp, a5);
      }
      DescendentByName = FindDescendentByName(this, L"arrow");
      DirectUI::Element::SetValue(
        DescendentByName,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::SelectedProp,
        1,
        a5);
    }
    else if ( DirectUI::PropNotify::IsEqual(a2, a3, DirectUI::Element::ExtentProp) )
    {
      ARPExpando::_SyncExtent(this);
    }
  }
}

```

## disassembly

```asm
0x18000cba0  push    rbx
0x18000cba2  push    rbp
0x18000cba3  push    rsi
0x18000cba4  push    rdi
0x18000cba5  sub     rsp, 38h
0x18000cba9  mov     rsi, [rsp+58h+arg_20]
0x18000cbb1  mov     ebp, r8d
0x18000cbb4  mov     [rsp+58h+var_38], rsi
0x18000cbb9  mov     rbx, rdx
0x18000cbbc  mov     rdi, rcx
0x18000cbbf  call    cs:__imp_?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z; DirectUI::Element::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x18000cbc5  mov     r8, cs:__imp_?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18000cbcc  mov     edx, ebp; int
0x18000cbce  mov     rcx, rbx; struct DirectUI::PropertyInfo *
0x18000cbd1  call    ?IsEqual@PropNotify@DirectUI@@SA_NPEBUPropertyInfo@2@HP6APEBU32@XZ@Z; DirectUI::PropNotify::IsEqual(DirectUI::PropertyInfo const *,int,DirectUI::PropertyInfo const * (*)(void))
0x18000cbd6  test    al, al
0x18000cbd8  jnz     loc_18000CC93
0x18000cbde  lea     rax, off_1800774B8; "Expanded"
0x18000cbe5  cmp     rbx, rax
0x18000cbe8  jnz     loc_18000CC76
0x18000cbee  mov     eax, [rbx+8]
0x18000cbf1  and     eax, 3
0x18000cbf4  cmp     eax, ebp
0x18000cbf6  jnz     short loc_18000CC76
0x18000cbf8  mov     ebp, 1
0x18000cbfd  mov     rcx, rdi; struct DirectUI::Element *
0x18000cc00  mov     edx, ebp; unsigned int
0x18000cc02  call    ?GetNthChild@@YAPEAVElement@DirectUI@@PEAV12@I@Z; GetNthChild(DirectUI::Element *,uint)
0x18000cc07  mov     rbx, rax
0x18000cc0a  test    rax, rax
0x18000cc0d  jz      short loc_18000CC4F
0x18000cc0f  mov     rcx, rsi
0x18000cc12  mov     [rdi+0C8h], bpl
0x18000cc19  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18000cc1f  mov     rcx, rbx
0x18000cc22  test    al, al
0x18000cc24  jz      short loc_18000CC35
0x18000cc26  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x18000cc2d  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18000cc33  jmp     short loc_18000CC3D
0x18000cc35  xor     edx, edx
0x18000cc37  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x18000cc3d  mov     r8, rsi
0x18000cc40  lea     rdx, ?_SetParentExpandedProp@@YAJPEAVClientPicker@@_J@Z; _SetParentExpandedProp(ClientPicker *,__int64)
0x18000cc47  mov     rcx, rbx
0x18000cc4a  call    ??$TraverseTree@VClientPicker@@@@YAJPEAVElement@DirectUI@@P6AJPEAVClientPicker@@_J@Z2@Z; TraverseTree<ClientPicker>(DirectUI::Element *,long (*)(ClientPicker *,__int64),__int64)
0x18000cc4f  lea     rdx, aArrow; "arrow"
0x18000cc56  mov     rcx, rdi; struct DirectUI::Element *
0x18000cc59  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x18000cc5e  mov     rdx, cs:__imp_?SelectedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::SelectedProp(void)
0x18000cc65  mov     r9, rsi
0x18000cc68  mov     r8d, ebp
0x18000cc6b  mov     rcx, rax
0x18000cc6e  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000cc74  jmp     short loc_18000CC93
0x18000cc76  mov     r8, cs:__imp_?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18000cc7d  mov     edx, ebp; int
0x18000cc7f  mov     rcx, rbx; struct DirectUI::PropertyInfo *
0x18000cc82  call    ?IsEqual@PropNotify@DirectUI@@SA_NPEBUPropertyInfo@2@HP6APEBU32@XZ@Z; DirectUI::PropNotify::IsEqual(DirectUI::PropertyInfo const *,int,DirectUI::PropertyInfo const * (*)(void))
0x18000cc87  test    al, al
0x18000cc89  jz      short loc_18000CC93
0x18000cc8b  mov     rcx, rdi; this
0x18000cc8e  call    ?_SyncExtent@ARPExpando@@AEAAXXZ; ARPExpando::_SyncExtent(void)
0x18000cc93  add     rsp, 38h
0x18000cc97  pop     rdi
0x18000cc98  pop     rsi
0x18000cc99  pop     rbp
0x18000cc9a  pop     rbx
0x18000cc9b  retn
```
