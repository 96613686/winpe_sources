# UIProperty::_UpdateContentValue(tagPROPVARIANT const &)

- ea: `0x1800340d0`
- end: `0x18003437e`
- name: `?_UpdateContentValue@UIProperty@@IEAAJAEBUtagPROPVARIANT@@@Z`
- size: `686`
- prototype: `int(UIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800333d0`
- `0x18012fdf4`

## callees

- `0x1800340a0`
- `0x1800340d0`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800341fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003433c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800341fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003433c`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18003414d`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18003414d`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800341ba`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800341ba`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800341a1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800341dc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800341a1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800341dc`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180034177`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180034177`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800341d2`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180034221`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800342a2`
- `DUI70!StrToID` at `0x1800341ae`
- `DUI70!StrToID` at `0x1800341ae`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180034372`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180034372`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800341eb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003426f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800341eb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003426f`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003421b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003422b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003429c`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800342ac`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003421b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003422b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003429c`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800342ac`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800340ed`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800340ed`
- `DUI70!?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180034197`
- `DUI70!?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180034211`
- `DUI70!?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180034295`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UIProperty::_UpdateContentValue(UIProperty *this, const PROPVARIANT *a2)
{
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v5; // rsi
  struct DirectUI::Element *v6; // rbp
  __int64 v7; // rax
  HRESULT v8; // eax
  unsigned int v9; // edi
  struct DirectUI::Value *String; // rax
  struct DirectUI::Value *v11; // rsi
  __int16 v12; // di
  int v13; // eax
  unsigned int v14; // ebx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PWSTR ppszDisplay; // [rsp+48h] [rbp+10h] BYREF
  struct DirectUI::Value *v22; // [rsp+50h] [rbp+18h]

  if ( *(_WORD *)a2 )
  {
    TopLevel = DirectUI::Element::GetTopLevel(this);
    v5 = TopLevel;
    v6 = 0;
    if ( TopLevel )
    {
      v7 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
      if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v7 + 80LL))(
             v7,
             UIItemsView::Class) )
      {
        v6 = v5;
      }
    }
    ppszDisplay = 0;
    v8 = PSFormatForDisplayAlloc(
           (const PROPERTYKEY *const)((char *)this + 572),
           a2,
           *((PROPDESC_FORMAT_FLAGS *)this + 148),
           &ppszDisplay);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x404,
        (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
        (const char *)(unsigned int)v8,
        v19);
      if ( ppszDisplay )
        CoTaskMemFree(ppszDisplay);
      return v9;
    }
    else
    {
      if ( !ppszDisplay || !*ppszDisplay )
      {
        DirectUI::Element::RemoveLocalValue(
          this,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::AccValueProp);
        v16 = DirectUI::Element::RemoveLocalValue(
                this,
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
        v14 = v16;
        if ( v16 >= 0 )
        {
LABEL_12:
          if ( ppszDisplay )
            CoTaskMemFree(ppszDisplay);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
          (const char *)(unsigned int)v16,
          v19);
        goto LABEL_18;
      }
      String = DirectUI::Value::CreateString(ppszDisplay, 0);
      v11 = String;
      v22 = String;
      if ( String )
      {
        DirectUI::Element::SetValue(
          this,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::AccValueProp,
          1,
          String);
        v12 = StrToID(L"GroupName");
        if ( DirectUI::Element::GetID(this) == v12 && v6 && *((_DWORD *)v6 + 107) )
          DirectUI::Element::SetAccName(this, ppszDisplay);
        v13 = DirectUI::Element::SetValue(
                this,
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                1,
                v11);
        v14 = v13;
        if ( v13 >= 0 )
        {
          DirectUI::Value::Release(v11);
          goto LABEL_12;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42B,
          (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
          (const char *)(unsigned int)v13,
          v19);
        DirectUI::Value::Release(v11);
LABEL_18:
        if ( ppszDisplay )
          CoTaskMemFree(ppszDisplay);
        return v14;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x409,
        (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
        (const char *)0x8007000ELL,
        v19);
      if ( ppszDisplay )
        CoTaskMemFree(ppszDisplay);
      return 2147942414LL;
    }
  }
  else
  {
    DirectUI::Element::RemoveLocalValue(
      this,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::AccValueProp);
    v17 = DirectUI::Element::RemoveLocalValue(
            this,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
    v18 = v17;
    if ( v17 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
      (const char *)(unsigned int)v17,
      v19);
    return v18;
  }
}

```

## disassembly

```asm
0x1800340d0  mov     [rsp+arg_0], rbx
0x1800340d5  push    rbp
0x1800340d6  push    rsi
0x1800340d7  push    rdi; int
0x1800340d8  sub     rsp, 20h
0x1800340dc  mov     rdi, rdx
0x1800340df  mov     rbx, rcx
0x1800340e2  xor     eax, eax
0x1800340e4  cmp     ax, [rdx]
0x1800340e7  jz      loc_180034295
0x1800340ed  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x1800340f3  mov     rsi, rax
0x1800340f6  xor     ebp, ebp
0x1800340f8  test    rax, rax
0x1800340fb  jz      short loc_18003412E
0x1800340fd  mov     rcx, [rax]
0x180034100  mov     rax, [rcx+118h]
0x180034107  mov     rcx, rsi
0x18003410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410f  mov     r8, rax
0x180034112  mov     rcx, [rax]
0x180034115  mov     rax, [rcx+50h]
0x180034119  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x180034120  mov     rcx, r8
0x180034123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034128  test    al, al
0x18003412a  cmovnz  rbp, rsi
0x18003412e  mov     [rsp+38h+ppszDisplay], 0
0x180034137  lea     rcx, [rbx+23Ch]; key
0x18003413e  lea     r9, [rsp+38h+ppszDisplay]; ppszDisplay
0x180034143  mov     r8d, [rbx+250h]; pdff
0x18003414a  mov     rdx, rdi; propvar
0x18003414d  call    cs:__imp_PSFormatForDisplayAlloc
0x180034153  mov     edi, eax
0x180034155  test    eax, eax
0x180034157  js      loc_1800342DC
0x18003415d  mov     rcx, [rsp+38h+ppszDisplay]
0x180034162  test    rcx, rcx
0x180034165  jz      loc_180034211
0x18003416b  cmp     word ptr [rcx], 0
0x18003416f  jz      loc_180034211
0x180034175  xor     edx, edx
0x180034177  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x18003417d  mov     rsi, rax
0x180034180  mov     [rsp+38h+arg_10], rax
0x180034185  test    rax, rax
0x180034188  jz      loc_180034315
0x18003418e  mov     r9, rax
0x180034191  mov     r8d, 1
0x180034197  mov     rdx, cs:__imp_?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccValueProp(void)
0x18003419e  mov     rcx, rbx
0x1800341a1  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800341a7  lea     rcx, aGroupname; "GroupName"
0x1800341ae  call    cs:__imp_StrToID
0x1800341b4  movzx   edi, ax
0x1800341b7  mov     rcx, rbx
0x1800341ba  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800341c0  cmp     ax, di
0x1800341c3  jz      loc_180034354
0x1800341c9  mov     r9, rsi
0x1800341cc  mov     r8d, 1
0x1800341d2  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800341d9  mov     rcx, rbx
0x1800341dc  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800341e2  mov     ebx, eax
0x1800341e4  test    eax, eax
0x1800341e6  js      short loc_180034252
0x1800341e8  mov     rcx, rsi
0x1800341eb  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800341f1  nop
0x1800341f2  mov     rcx, [rsp+38h+ppszDisplay]; pv
0x1800341f7  test    rcx, rcx
0x1800341fa  jz      short loc_180034202
0x1800341fc  call    cs:__imp_CoTaskMemFree
0x180034202  xor     eax, eax
0x180034204  mov     rbx, [rsp+38h+arg_0]
0x180034209  add     rsp, 20h
0x18003420d  pop     rdi
0x18003420e  pop     rsi
0x18003420f  pop     rbp
0x180034210  retn
0x180034211  mov     rdx, cs:__imp_?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccValueProp(void)
0x180034218  mov     rcx, rbx
0x18003421b  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180034221  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180034228  mov     rcx, rbx
0x18003422b  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180034231  mov     ebx, eax
0x180034233  test    eax, eax
0x180034235  jns     short loc_1800341F2
0x180034237  mov     rcx, [rsp+38h]; this
0x18003423c  mov     r9d, eax; char *
0x18003423f  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x180034246  mov     edx, 431h; void *
0x18003424b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034250  jmp     short loc_180034276
0x180034252  mov     rcx, [rsp+38h]; this
0x180034257  mov     r9d, ebx; char *
0x18003425a  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x180034261  mov     edx, 42Bh; void *
0x180034266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003426b  nop
0x18003426c  mov     rcx, rsi
0x18003426f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180034275  nop
0x180034276  mov     rcx, [rsp+38h+ppszDisplay]; pv
0x18003427b  test    rcx, rcx
0x18003427e  jz      short loc_180034286
0x180034280  call    cs:__imp_CoTaskMemFree
0x180034286  mov     eax, ebx
0x180034288  mov     rbx, [rsp+38h+arg_0]
0x18003428d  add     rsp, 20h
0x180034291  pop     rdi
0x180034292  pop     rsi
0x180034293  pop     rbp
0x180034294  retn
0x180034295  mov     rdx, cs:__imp_?AccValueProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccValueProp(void)
0x18003429c  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800342a2  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800342a9  mov     rcx, rbx
0x1800342ac  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800342b2  mov     ebx, eax
0x1800342b4  test    eax, eax
0x1800342b6  jns     loc_180034202
0x1800342bc  mov     rcx, [rsp+38h]; this
0x1800342c1  mov     r9d, eax; char *
0x1800342c4  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x1800342cb  mov     edx, 3FDh; void *
0x1800342d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342d5  mov     eax, ebx
0x1800342d7  jmp     loc_180034204
0x1800342dc  mov     rcx, [rsp+38h]; this
0x1800342e1  mov     r9d, edi; char *
0x1800342e4  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x1800342eb  mov     edx, 404h; void *
0x1800342f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342f5  nop
0x1800342f6  mov     rcx, [rsp+38h+ppszDisplay]; pv
0x1800342fb  test    rcx, rcx
0x1800342fe  jz      short loc_180034306
0x180034300  call    cs:__imp_CoTaskMemFree
0x180034306  mov     eax, edi
0x180034308  mov     rbx, [rsp+38h+arg_0]
0x18003430d  add     rsp, 20h
0x180034311  pop     rdi
0x180034312  pop     rsi
0x180034313  pop     rbp
0x180034314  retn
0x180034315  mov     rcx, [rsp+38h]; this
0x18003431a  mov     r9d, 8007000Eh; char *
0x180034320  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x180034327  mov     edx, 409h; void *
0x18003432c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034331  nop
0x180034332  mov     rcx, [rsp+38h+ppszDisplay]; pv
0x180034337  test    rcx, rcx
0x18003433a  jz      short loc_180034342
0x18003433c  call    cs:__imp_CoTaskMemFree
0x180034342  mov     eax, 8007000Eh
0x180034347  mov     rbx, [rsp+38h+arg_0]
0x18003434c  add     rsp, 20h
0x180034350  pop     rdi
0x180034351  pop     rsi
0x180034352  pop     rbp
0x180034353  retn
0x180034354  test    rbp, rbp
0x180034357  jz      loc_1800341C9
0x18003435d  cmp     dword ptr [rbp+1ACh], 0
0x180034364  jz      loc_1800341C9
0x18003436a  mov     rdx, [rsp+38h+ppszDisplay]
0x18003436f  mov     rcx, rbx
0x180034372  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180034378  jmp     loc_1800341C9
```
