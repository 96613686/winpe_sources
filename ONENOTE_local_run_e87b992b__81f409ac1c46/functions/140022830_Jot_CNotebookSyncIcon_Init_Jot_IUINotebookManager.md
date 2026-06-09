# Jot::CNotebookSyncIcon::Init(Jot::IUINotebookManager *)

- ea: `0x140022830`
- end: `0x1400229b3`
- name: `?Init@CNotebookSyncIcon@Jot@@QEAAXPEAUIUINotebookManager@2@@Z`
- size: `387`
- prototype: `void __fastcall(Jot::CNotebookSyncIcon *__hidden this, struct Jot::IUINotebookManager *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001ee00`

## callees

- `0x140019348`
- `0x140022830`
- `0x1400229b4`
- `0x14004921c`
- `0x140049350`
- `0x140049a30`
- `0x140057580`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140022876`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140022876`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x14002288c`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x14002288c`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x140022901`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x140022901`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x140022953`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x140022953`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400228b9`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002298f`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002299c`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400228b9`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002298f`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14002299c`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140022943`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140022943`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14002289e`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400228cb`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140022928`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14002289e`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400228cb`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140022928`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14002293c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14002293c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Jot::CNotebookSyncIcon::Init(Jot::CNotebookSyncIcon *this, struct Jot::IUINotebookManager *a2)
{
  Jot *v4; // rcx
  NetUI::BaseValue *GraphicIcon; // rax
  struct NetUI::Value *v6; // rbx
  __int64 v7; // rcx
  const struct NetUI::PropertyInfo *v8; // rax
  __int16 v9[2]; // [rsp+20h] [rbp-20h] BYREF
  int v10; // [rsp+24h] [rbp-1Ch]
  char v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  NetUI::Node *v13; // [rsp+60h] [rbp+20h] BYREF
  NetUI::Node *v14; // [rsp+68h] [rbp+28h] BYREF
  NetUI::Node *v15; // [rsp+70h] [rbp+30h] BYREF
  NetUI::BaseValue *v16; // [rsp+78h] [rbp+38h] BYREF

  if ( a2 )
    (*(void (__fastcall **)(struct Jot::IUINotebookManager *))(*(_QWORD *)a2 + 8LL))(a2);
  v4 = (Jot *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 26) = a2;
  if ( v4 )
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( Jot::IsLicensedForFluentUI(v4) )
  {
    NetUI::Element::SetLayout(this, 6);
    v15 = 0;
    NetUI::Image::Create(&v15);
    NetUI::Node::SetID(v15, 0x839u);
    NetUI::Node::Add(this, (struct Node *)v15);
    v14 = 0;
    NetUI::Image::Create(&v14);
    NetUI::Node::SetID(v14, 0x83Au);
    v9[0] = -252;
    v10 = 2143289344;
    v12 = 0;
    v11 = 1;
    GraphicIcon = (NetUI::BaseValue *)NetUI::Value::CreateGraphicIcon(9039, v9);
    v6 = GraphicIcon;
    v16 = GraphicIcon;
    if ( GraphicIcon )
      NetUI::BaseValue::AddRef(GraphicIcon);
    v13 = 0;
    NetUI::Image::Create(&v13);
    if ( !v13 )
    {
      CrashWithRecovery(0x1E48C18Au, 0);
      __debugbreak();
    }
    v8 = (const struct NetUI::PropertyInfo *)NetUI::Element::ContentPropInfo(v7);
    NetUI::Node::SetValue(v13, v8, v6);
    NetUI::Element::SetIsAccessible(v13, 0);
    NetUI::Element::SetBackgroundColor(v13, 0);
    NetUI::Node::SetID(v13, 0x83Bu);
    NetUI::Element::SetBackgroundColor(v14, 0);
    NetUI::Node::Add(this, (struct Node *)v13);
    NetUI::Node::Add(this, (struct Node *)v14);
    Mso::TCntPtr<NetUI::Value>::Clear(&v16);
  }
}

```

## disassembly

```asm
0x140022830  push    rbp
0x140022832  push    rbx
0x140022833  push    rdi
0x140022834  mov     rbp, rsp
0x140022837  sub     rsp, 40h
0x14002283b  mov     rbx, rdx
0x14002283e  mov     rdi, rcx
0x140022841  test    rdx, rdx
0x140022844  jz      short loc_140022856
0x140022846  mov     rax, [rdx]
0x140022849  mov     rcx, rdx
0x14002284c  mov     rax, [rax+8]
0x140022850  call    cs:__guard_dispatch_icall_fptr
0x140022856  mov     rcx, [rdi+0D0h]
0x14002285d  mov     [rdi+0D0h], rbx
0x140022864  test    rcx, rcx
0x140022867  jz      short loc_140022876
0x140022869  mov     rax, [rcx]
0x14002286c  mov     rax, [rax+10h]
0x140022870  call    cs:__guard_dispatch_icall_fptr
0x140022876  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x14002287c  test    al, al
0x14002287e  jz      loc_1400229AB
0x140022884  mov     edx, 6
0x140022889  mov     rcx, rdi
0x14002288c  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x140022892  mov     [rbp+arg_10], 0
0x14002289a  lea     rcx, [rbp+arg_10]
0x14002289e  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x1400228a4  mov     edx, 839h; unsigned int
0x1400228a9  mov     rcx, [rbp+arg_10]; this
0x1400228ad  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x1400228b2  mov     rdx, [rbp+arg_10]
0x1400228b6  mov     rcx, rdi
0x1400228b9  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400228bf  mov     [rbp+arg_8], 0
0x1400228c7  lea     rcx, [rbp+arg_8]
0x1400228cb  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x1400228d1  mov     edx, 83Ah; unsigned int
0x1400228d6  mov     rcx, [rbp+arg_8]; this
0x1400228da  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x1400228df  mov     [rbp+var_20], 0FF04h
0x1400228e5  mov     [rbp+var_1C], 7FC00000h
0x1400228ec  mov     [rbp+var_10], 0
0x1400228f4  mov     [rbp+var_18], 1
0x1400228f8  lea     rdx, [rbp+var_20]
0x1400228fc  mov     ecx, 234Fh
0x140022901  call    cs:__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z; NetUI::Value::CreateGraphicIcon(Mso::IconId,NetUI::CreateIconParams const &)
0x140022907  mov     rbx, rax
0x14002290a  mov     [rbp+arg_18], rax
0x14002290e  test    rax, rax
0x140022911  jz      short loc_14002291C
0x140022913  mov     rcx, rax; this
0x140022916  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x14002291b  nop
0x14002291c  mov     [rbp+arg_0], 0
0x140022924  lea     rcx, [rbp+arg_0]
0x140022928  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x14002292e  cmp     [rbp+arg_0], 0
0x140022933  jnz     short loc_140022943
0x140022935  xor     edx, edx
0x140022937  mov     ecx, 1E48C18Ah
0x14002293c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140022942  int     3; Trap to Debugger
0x140022943  call    cs:__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::ContentPropInfo(void)
0x140022949  mov     r8, rbx
0x14002294c  mov     rdx, rax
0x14002294f  mov     rcx, [rbp+arg_0]
0x140022953  call    cs:__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z; NetUI::Node::SetValue(NetUI::PropertyInfo const *,NetUI::Value *)
0x140022959  xor     edx, edx; bool
0x14002295b  mov     rcx, [rbp+arg_0]; this
0x14002295f  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x140022964  xor     edx, edx; unsigned int
0x140022966  mov     rcx, [rbp+arg_0]; this
0x14002296a  call    ?SetBackgroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetBackgroundColor(ulong)
0x14002296f  mov     edx, 83Bh; unsigned int
0x140022974  mov     rcx, [rbp+arg_0]; this
0x140022978  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x14002297d  xor     edx, edx; unsigned int
0x14002297f  mov     rcx, [rbp+arg_8]; this
0x140022983  call    ?SetBackgroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetBackgroundColor(ulong)
0x140022988  mov     rdx, [rbp+arg_0]
0x14002298c  mov     rcx, rdi
0x14002298f  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x140022995  mov     rdx, [rbp+arg_8]
0x140022999  mov     rcx, rdi
0x14002299c  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400229a2  lea     rcx, [rbp+arg_18]
0x1400229a6  call    ?Clear@?$TCntPtr@VValue@NetUI@@@Mso@@QEAAXXZ; Mso::TCntPtr<NetUI::Value>::Clear(void)
0x1400229ab  add     rsp, 40h
0x1400229af  pop     rdi
0x1400229b0  pop     rbx
0x1400229b1  pop     rbp
0x1400229b2  retn
```
