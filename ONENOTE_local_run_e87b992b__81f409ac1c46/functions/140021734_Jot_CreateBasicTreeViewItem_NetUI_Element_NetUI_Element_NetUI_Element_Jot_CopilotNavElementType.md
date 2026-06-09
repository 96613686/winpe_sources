# Jot::CreateBasicTreeViewItem(NetUI::Element * *,NetUI::Element * *,NetUI::Element * *,Jot::CopilotNavElementType)

- ea: `0x140021734`
- end: `0x1400218f1`
- name: `?CreateBasicTreeViewItem@Jot@@YAXPEAPEAVElement@NetUI@@00W4CopilotNavElementType@1@@Z`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x140023a84`
- `0x14007fc60`

## callees

- `0x140019348`
- `0x14001c4b0`
- `0x14001c570`
- `0x140020ab0`
- `0x140021734`
- `0x1400218f4`
- `0x1400242e0`
- `0x14002a850`
- `0x140049910`
- `0x140049aa4`
- `0x1400569a0`
- `0x140057580`

## import_xrefs

- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x14002177b`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400217b2`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140021820`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x14002177b`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400217b2`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140021820`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x140021883`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x140021883`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x14002187a`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x14002187a`
- `mso40uiWin32Client!__imp_?Create@TreeViewExpander@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400217d0`
- `mso40uiWin32Client!__imp_?Create@TreeViewExpander@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400217d0`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002176d`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400217a4`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400217e0`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140021805`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002176d`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400217a4`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400217e0`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140021805`
- `mso40uiWin32Client!__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z` at `0x1400218dd`
- `mso40uiWin32Client!__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z` at `0x1400218dd`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400217f7`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400217f7`
- `mso40uiWin32Client!__imp_?Create@TreeViewChildren@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140021798`
- `mso40uiWin32Client!__imp_?Create@TreeViewChildren@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140021798`

## pseudocode

```c
int __fastcall Jot::CreateBasicTreeViewItem(
        struct NetUI::Element **a1,
        struct NetUI::Element **a2,
        struct NetUI::Element **a3,
        int a4)
{
  bool v8; // r8
  int v9; // r8d
  NetUI::Node *v10; // rbx
  const struct NetUI::IClassInfo *StaticClassInfo; // rax
  int result; // eax
  struct NetUI::Element *v13; // [rsp+50h] [rbp+8h] BYREF
  Jot::NavigationUI *v14; // [rsp+58h] [rbp+10h] BYREF

  Jot::CHoWoTreeViewItem::Create(a1);
  v13 = 0;
  Jot::CHoWoTVIContent::Create(&v13);
  NetUI::Node::Add(*a1, (struct Node *)v13);
  NetUI::Element::SetLayout(*a1, 8);
  NetUI::Element::SetExpandToFillHoriz(*a1, 1);
  NetUI::Element::SetExpandToFillVert(*a1, 0);
  NetUI::TreeViewChildren::Create(a3);
  NetUI::Node::Add(*a1, (struct Node *)*a3);
  NetUI::Element::SetLayout(*a3, 8);
  NetUI::Element::SetExpandToFillHoriz(*a3, 1);
  v14 = 0;
  NetUI::TreeViewExpander::Create(&v14);
  NetUI::Node::Add(v13, (struct Node *)v14);
  Jot::NavigationUI::FSetElementVisible(v14, 0, v8);
  NetUI::Element::Create(0, a2);
  NetUI::Node::Add(v13, (struct Node *)*a2);
  NetUI::Node::SetID(*a2, 0x32u);
  NetUI::Element::SetLayout(*a2, 5);
  NetUI::Element::SetAlignChildren(*a2, 3);
  NetUI::Element::SetExpandToFillHoriz(*a2, 1);
  NetUI::Element::SetExpandToFillVert(*a2, 0);
  if ( a4 == 4 || a4 == 7 || (unsigned int)(a4 - 9) < 2 )
    v9 = 0;
  else
    v9 = 4;
  NetUI::Element::SetPadding(v13, 4, v9, 0, 4);
  v10 = *a1;
  StaticClassInfo = (const struct NetUI::IClassInfo *)NetUI::TreeViewItem::GetStaticClassInfo();
  if ( !v10 || !NetUI::Node::IsSubclassOf(v10, StaticClassInfo) )
    v10 = 0;
  if ( v10 )
    _castguard_slow_path_check_user_handled(*(_QWORD *)v10, 51856, 2064);
  result = (*(__int64 (__fastcall **)(NetUI::Node *))(*(_QWORD *)v10 + 72LL))(v10);
  if ( !a4 )
  {
    NetUI::TreeViewItem::SetHasChildren(v10, 1);
    return NetUI::TreeViewItem::SetIsCollapsed(v10, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140021734  mov     [rsp+arg_10], rbx
0x140021739  push    rbp
0x14002173a  push    rdi
0x14002173b  push    r14
0x14002173d  sub     rsp, 30h
0x140021741  mov     ebp, r9d
0x140021744  mov     rbx, r8
0x140021747  mov     rdi, rdx
0x14002174a  mov     r14, rcx
0x14002174d  call    ?Create@CHoWoTreeViewItem@Jot@@SAJPEAPEAVElement@NetUI@@@Z; Jot::CHoWoTreeViewItem::Create(NetUI::Element * *)
0x140021752  lea     rcx, [rsp+48h+arg_0]; struct NetUI::Element **
0x140021757  mov     [rsp+48h+arg_0], 0
0x140021760  call    ?Create@CHoWoTVIContent@Jot@@SAJPEAPEAVElement@NetUI@@@Z; Jot::CHoWoTVIContent::Create(NetUI::Element * *)
0x140021765  mov     rdx, [rsp+48h+arg_0]
0x14002176a  mov     rcx, [r14]
0x14002176d  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x140021773  mov     rcx, [r14]
0x140021776  mov     edx, 8
0x14002177b  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x140021781  mov     rcx, [r14]; this
0x140021784  mov     dl, 1; bool
0x140021786  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x14002178b  mov     rcx, [r14]; this
0x14002178e  xor     edx, edx; bool
0x140021790  call    ?SetExpandToFillVert@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillVert(bool)
0x140021795  mov     rcx, rbx
0x140021798  call    cs:__imp_?Create@TreeViewChildren@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::TreeViewChildren::Create(NetUI::Element * *)
0x14002179e  mov     rdx, [rbx]
0x1400217a1  mov     rcx, [r14]
0x1400217a4  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400217aa  mov     rcx, [rbx]
0x1400217ad  mov     edx, 8
0x1400217b2  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x1400217b8  mov     rcx, [rbx]; this
0x1400217bb  mov     dl, 1; bool
0x1400217bd  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x1400217c2  lea     rcx, [rsp+48h+arg_8]
0x1400217c7  mov     [rsp+48h+arg_8], 0
0x1400217d0  call    cs:__imp_?Create@TreeViewExpander@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::TreeViewExpander::Create(NetUI::Element * *)
0x1400217d6  mov     rdx, [rsp+48h+arg_8]
0x1400217db  mov     rcx, [rsp+48h+arg_0]
0x1400217e0  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400217e6  mov     rcx, [rsp+48h+arg_8]; this
0x1400217eb  xor     edx, edx; struct NetUI::Element *
0x1400217ed  call    ?FSetElementVisible@NavigationUI@Jot@@YA_NPEAVElement@NetUI@@_N@Z; Jot::NavigationUI::FSetElementVisible(NetUI::Element *,bool)
0x1400217f2  mov     rdx, rdi
0x1400217f5  xor     ecx, ecx
0x1400217f7  call    cs:__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z; NetUI::Element::Create(uint,NetUI::Element * *)
0x1400217fd  mov     rdx, [rdi]
0x140021800  mov     rcx, [rsp+48h+arg_0]
0x140021805  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14002180b  mov     rcx, [rdi]; this
0x14002180e  mov     edx, 32h ; '2'; unsigned int
0x140021813  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x140021818  mov     rcx, [rdi]
0x14002181b  mov     edx, 5
0x140021820  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x140021826  mov     rcx, [rdi]; this
0x140021829  mov     edx, 3; int
0x14002182e  call    ?SetAlignChildren@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetAlignChildren(int)
0x140021833  mov     rcx, [rdi]; this
0x140021836  mov     dl, 1; bool
0x140021838  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x14002183d  mov     rcx, [rdi]; this
0x140021840  xor     edx, edx; bool
0x140021842  call    ?SetExpandToFillVert@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillVert(bool)
0x140021847  mov     r8d, ebp
0x14002184a  mov     edx, 4
0x14002184f  sub     r8d, edx
0x140021852  jz      short loc_14002186B
0x140021854  sub     r8d, 3
0x140021858  jz      short loc_14002186B
0x14002185a  sub     r8d, 2
0x14002185e  jz      short loc_14002186B
0x140021860  cmp     r8d, 1
0x140021864  jz      short loc_14002186B
0x140021866  mov     r8d, edx
0x140021869  jmp     short loc_14002186E
0x14002186b  xor     r8d, r8d
0x14002186e  mov     rcx, [rsp+48h+arg_0]
0x140021873  xor     r9d, r9d
0x140021876  mov     [rsp+48h+var_28], edx
0x14002187a  call    cs:__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z; NetUI::Element::SetPadding(int,int,int,int)
0x140021880  mov     rbx, [r14]
0x140021883  call    cs:__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ; NetUI::TreeViewItem::GetStaticClassInfo(void)
0x140021889  test    rbx, rbx
0x14002188c  jz      short loc_14002189D
0x14002188e  mov     rdx, rax; struct NetUI::IClassInfo *
0x140021891  mov     rcx, rbx; this
0x140021894  call    ?IsSubclassOf@Node@NetUI@@QEBA_NPEBUIClassInfo@2@@Z; NetUI::Node::IsSubclassOf(NetUI::IClassInfo const *)
0x140021899  test    al, al
0x14002189b  jnz     short loc_14002189F
0x14002189d  xor     ebx, ebx
0x14002189f  test    rbx, rbx
0x1400218a2  jz      short loc_1400218B7
0x1400218a4  mov     rcx, [rbx]
0x1400218a7  mov     edx, 0CA90h
0x1400218ac  mov     r8d, 810h
0x1400218b2  call    __castguard_slow_path_check_user_handled
0x1400218b7  mov     rax, [rbx]
0x1400218ba  mov     rcx, rbx
0x1400218bd  mov     rax, [rax+48h]
0x1400218c1  call    cs:__guard_dispatch_icall_fptr
0x1400218c7  test    ebp, ebp
0x1400218c9  jnz     short loc_1400218E3
0x1400218cb  mov     dl, 1; bool
0x1400218cd  mov     rcx, rbx; this
0x1400218d0  call    ?SetHasChildren@TreeViewItem@NetUI@@QEAAJ_N@Z; NetUI::TreeViewItem::SetHasChildren(bool)
0x1400218d5  xor     r8d, r8d
0x1400218d8  xor     edx, edx
0x1400218da  mov     rcx, rbx
0x1400218dd  call    cs:__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z; NetUI::TreeViewItem::SetIsCollapsed(bool,bool)
0x1400218e3  mov     rbx, [rsp+48h+arg_10]
0x1400218e8  add     rsp, 30h
0x1400218ec  pop     r14
0x1400218ee  pop     rdi
0x1400218ef  pop     rbp
0x1400218f0  retn
```
