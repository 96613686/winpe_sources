# ARPFrame::InitClientCombos(ARPExpando *,CLIENTFILTER)

- ea: `0x18000b3dc`
- end: `0x18000b4c4`
- name: `?InitClientCombos@ARPFrame@@QEAAJPEAVARPExpando@@W4CLIENTFILTER@@@Z`
- size: `232`
- prototype: `int __high(struct ARPExpando *, enum CLIENTFILTER)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e7a0`

## callees

- `0x180008a88`
- `0x180008ad8`
- `0x18000aa98`
- `0x18000b13c`
- `0x18000b3dc`
- `0x18000e11c`

## import_xrefs

- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000b41c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000b41c`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b45c`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b45c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000b4a1`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000b4a1`

## pseudocode

```c
__int64 __fastcall ARPFrame::InitClientCombos(__int64 a1, struct DirectUI::Element *a2, int a3)
{
  int v6; // edi
  struct DirectUI::Element *NthChild; // rax
  DirectUI::Element *v8; // rax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h]
  __int64 v12; // [rsp+38h] [rbp-30h]
  struct DirectUI::Element *v13; // [rsp+70h] [rbp+8h] BYREF

  v13 = 0;
  v6 = DirectUI::DUIXmlParser::CreateElement(
         *(DirectUI::DUIXmlParser **)(a1 + 280),
         L"clientcategoryblock",
         0,
         a2,
         0,
         &v13);
  if ( v6 >= 0 )
  {
    TraverseTree<DirectUI::Button>(v13, (int (*)(struct DirectUI::Element *, __int64))FixDUIButtonAccessibilityCB);
    NthChild = GetNthChild(a2, 1u);
    v8 = GetNthChild(NthChild, 0);
    DirectUI::Element::Add(v8, v13);
    v10 = a3;
    v11 = 0;
    v12 = a1;
    v6 = TraverseTree<ClientPicker>(v13, SetFilterCB, &v10);
    if ( !v10 && !v11 )
    {
      DirectUI::Element::SetLayoutPos(a2, -3);
      DisableElementTreeShortcut(a2);
    }
  }
  ARPExpandable::SetExpanded(a2, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b3dc  mov     r11, rsp
0x18000b3df  push    rbx
0x18000b3e0  push    rbp
0x18000b3e1  push    rsi
0x18000b3e2  push    rdi
0x18000b3e3  sub     rsp, 48h
0x18000b3e7  lea     rax, [r11+8]
0x18000b3eb  mov     qword ptr [r11+8], 0
0x18000b3f3  mov     ebp, r8d
0x18000b3f6  mov     [r11-40h], rax
0x18000b3fa  mov     rbx, rdx
0x18000b3fd  mov     qword ptr [r11-48h], 0
0x18000b405  mov     rsi, rcx
0x18000b408  mov     r9, rdx
0x18000b40b  mov     rcx, [rcx+118h]
0x18000b412  lea     rdx, aClientcategory; "clientcategoryblock"
0x18000b419  xor     r8d, r8d
0x18000b41c  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000b422  mov     edi, eax
0x18000b424  test    eax, eax
0x18000b426  js      loc_18000B4AF
0x18000b42c  mov     rcx, [rsp+68h+arg_0]; struct DirectUI::Element *
0x18000b431  lea     rdx, ?FixDUIButtonAccessibilityCB@@YAJPEAVButton@DirectUI@@_J@Z; int (*)(struct DirectUI::Element *, __int64)
0x18000b438  call    ??$TraverseTree@VButton@DirectUI@@@@YAJPEAVElement@DirectUI@@P6AJPEAVButton@1@_J@Z2@Z; TraverseTree<DirectUI::Button>(DirectUI::Element *,long (*)(DirectUI::Button *,__int64),__int64)
0x18000b43d  mov     edx, 1; unsigned int
0x18000b442  mov     rcx, rbx; struct DirectUI::Element *
0x18000b445  call    ?GetNthChild@@YAPEAVElement@DirectUI@@PEAV12@I@Z; GetNthChild(DirectUI::Element *,uint)
0x18000b44a  xor     edx, edx; unsigned int
0x18000b44c  mov     rcx, rax; struct DirectUI::Element *
0x18000b44f  call    ?GetNthChild@@YAPEAVElement@DirectUI@@PEAV12@I@Z; GetNthChild(DirectUI::Element *,uint)
0x18000b454  mov     rdx, [rsp+68h+arg_0]
0x18000b459  mov     rcx, rax
0x18000b45c  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000b462  mov     rcx, [rsp+68h+arg_0]
0x18000b467  lea     r8, [rsp+68h+var_38]
0x18000b46c  lea     rdx, ?SetFilterCB@@YAJPEAVClientPicker@@_J@Z; SetFilterCB(ClientPicker *,__int64)
0x18000b473  mov     [rsp+68h+var_38], ebp
0x18000b477  mov     [rsp+68h+var_34], 0
0x18000b47f  mov     [rsp+68h+var_30], rsi
0x18000b484  call    ??$TraverseTree@VClientPicker@@@@YAJPEAVElement@DirectUI@@P6AJPEAVClientPicker@@_J@Z2@Z; TraverseTree<ClientPicker>(DirectUI::Element *,long (*)(ClientPicker *,__int64),__int64)
0x18000b489  cmp     [rsp+68h+var_38], 0
0x18000b48e  mov     edi, eax
0x18000b490  jnz     short loc_18000B4AF
0x18000b492  cmp     [rsp+68h+var_34], 0
0x18000b497  jnz     short loc_18000B4AF
0x18000b499  mov     edx, 0FFFFFFFDh
0x18000b49e  mov     rcx, rbx
0x18000b4a1  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000b4a7  mov     rcx, rbx; struct DirectUI::Element *
0x18000b4aa  call    ?DisableElementTreeShortcut@@YAXPEAVElement@DirectUI@@@Z; DisableElementTreeShortcut(DirectUI::Element *)
0x18000b4af  xor     edx, edx; bool
0x18000b4b1  mov     rcx, rbx; this
0x18000b4b4  call    ?SetExpanded@ARPExpandable@@QEAAJ_N@Z; ARPExpandable::SetExpanded(bool)
0x18000b4b9  mov     eax, edi
0x18000b4bb  add     rsp, 48h
0x18000b4bf  pop     rdi
0x18000b4c0  pop     rsi
0x18000b4c1  pop     rbp
0x18000b4c2  pop     rbx
0x18000b4c3  retn
```
