# UITilesPropertyCollection::_CreateUIProperty(IPropertyDescription *,DirectUI::Element * *)

- ea: `0x1800309f0`
- end: `0x180030cce`
- name: `?_CreateUIProperty@UITilesPropertyCollection@@IEAAJPEAUIPropertyDescription@@PEAPEAVElement@DirectUI@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(UITilesPropertyCollection *__hidden this, struct IPropertyDescription *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007ea80`

## callees

- `0x1800309f0`
- `0x180031074`
- `0x1800340a0`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b45`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180030ac3`
- `DUI70!?SetTooltip@Element@DirectUI@@QEAAJ_N@Z` at `0x180030ac3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180030b1b`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180030b1b`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180030af6`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180030af6`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030b8e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030b99`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030bd0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c0b`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c46`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c81`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030cc1`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030b8e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030b99`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030bd0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c0b`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c46`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030c81`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180030cc1`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180030aa4`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180030aa4`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180030adc`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180030adc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030b26`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030b26`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180030a7a`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180030a7a`
- `DUI70!?GetTooltip@Element@DirectUI@@QEAA_NXZ` at `0x180030ab7`
- `DUI70!?GetTooltip@Element@DirectUI@@QEAA_NXZ` at `0x180030ab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UITilesPropertyCollection::_CreateUIProperty(
        UITilesPropertyCollection *this,
        struct IPropertyDescription *a2,
        struct DirectUI::Element **a3)
{
  HRESULT (__stdcall *GetCanonicalName)(IPropertyDescription *, LPWSTR *); // rbx
  int v6; // eax
  int v7; // ebx
  DirectUI::Element *v8; // rax
  DirectUI::Element *v9; // rdi
  int v10; // eax
  bool Tooltip; // al
  int v12; // eax
  int v13; // eax
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v15; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DirectUI::Element *v18; // [rsp+68h] [rbp+28h]
  struct DirectUI::Element **v19; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  v19 = a3;
  pv = 0;
  GetCanonicalName = a2->lpVtbl->GetCanonicalName;
  CoTaskMemFree(0);
  v6 = ((__int64 (__fastcall *)(struct IPropertyDescription *, LPVOID *))GetCanonicalName)(a2, &pv);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
      (const char *)(unsigned int)v6,
      (int)&v19);
    *v19 = 0;
    goto LABEL_10;
  }
  v8 = (DirectUI::Element *)DirectUI::HNewAndZero<UIProperty>();
  v9 = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
      (const char *)(unsigned int)v7,
      (int)&v19);
    *v19 = 0;
    goto LABEL_10;
  }
  v7 = DirectUI::Element::Initialize(v8, 0, this, 0);
  if ( v7 < 0 )
  {
    DirectUI::Element::Destroy(v9, 0);
    goto LABEL_12;
  }
  v18 = v9;
  v10 = DirectUI::Element::AddListener(
          v9,
          (struct DirectUI::IElementListener *)(((unsigned __int64)this + 200)
                                              & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
      (const char *)(unsigned int)v10,
      (int)&v19);
    *v19 = 0;
    if ( v9 )
      DirectUI::Element::Destroy(v9, 1);
  }
  else
  {
    Tooltip = DirectUI::Element::GetTooltip(this);
    v12 = DirectUI::Element::SetTooltip(v9, Tooltip);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
        (const char *)(unsigned int)v12,
        (int)&v19);
      *v19 = 0;
      if ( v9 )
        DirectUI::Element::Destroy(v9, 1);
    }
    else
    {
      v13 = DirectUI::Element::SetLayoutPos(v9, -3);
      v7 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
          (const char *)(unsigned int)v13,
          (int)&v19);
        *v19 = 0;
        if ( v9 )
          DirectUI::Element::Destroy(v9, 1);
      }
      else
      {
        String = DirectUI::Value::CreateString((const unsigned __int16 *)pv, 0);
        v15 = String;
        if ( String )
        {
          v7 = DirectUI::Element::SetValue(v18, UIProperty::PropertyCanonicalNameProp, 1, String);
          DirectUI::Value::Release(v15);
          if ( v7 >= 0 )
          {
            *v19 = v18;
            v7 = 0;
            goto LABEL_10;
          }
        }
        else
        {
          v7 = -2147024882;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"shell\\explorerframe\\itemsview\\uipropertycollection.cpp",
          (const char *)(unsigned int)v7,
          (int)&v19);
        *v19 = 0;
        if ( v18 )
          DirectUI::Element::Destroy(v18, 1);
      }
    }
  }
LABEL_10:
  CoTaskMemFree(pv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800309f0  mov     [rsp-18h+arg_0], rbx
0x1800309f5  mov     [rsp-18h+arg_10], r8
0x1800309fa  push    rbp
0x1800309fb  push    rsi
0x1800309fc  push    rdi
0x1800309fd  mov     rbp, rsp
0x180030a00  sub     rsp, 40h
0x180030a04  mov     rdi, rdx
0x180030a07  mov     rsi, rcx
0x180030a0a  mov     [rbp+pv], 0
0x180030a12  mov     [rbp+arg_8], 0
0x180030a1a  lea     rax, [rbp+arg_10]
0x180030a1e  mov     [rbp+var_20], rax
0x180030a22  lea     rax, [rbp+arg_8]
0x180030a26  mov     [rbp+var_18], rax
0x180030a2a  mov     [rbp+var_10], 1
0x180030a2e  mov     rax, [rdx]
0x180030a31  mov     rbx, [rax+20h]
0x180030a35  xor     ecx, ecx; pv
0x180030a37  call    cs:__imp_CoTaskMemFree
0x180030a3d  lea     rdx, [rbp+pv]
0x180030a41  mov     rcx, rdi
0x180030a44  mov     rax, rbx
0x180030a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a4c  mov     ebx, eax
0x180030a4e  test    eax, eax
0x180030a50  js      loc_180030BA1
0x180030a56  mov     [rbp+arg_8], 0
0x180030a5e  call    ??$HNewAndZero@VUIProperty@@@DirectUI@@YAPEAVUIProperty@@XZ; DirectUI::HNewAndZero<UIProperty>(void)
0x180030a63  mov     rdi, rax
0x180030a66  test    rax, rax
0x180030a69  jz      loc_180030B5A
0x180030a6f  xor     r9d, r9d
0x180030a72  mov     r8, rsi
0x180030a75  xor     edx, edx
0x180030a77  mov     rcx, rax
0x180030a7a  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x180030a80  mov     ebx, eax
0x180030a82  mov     rcx, rdi
0x180030a85  test    eax, eax
0x180030a87  js      loc_180030B97
0x180030a8d  mov     [rbp+arg_8], rdi
0x180030a91  mov     rax, rsi
0x180030a94  lea     r8, [rsi+0C8h]
0x180030a9b  neg     rax
0x180030a9e  sbb     rdx, rdx
0x180030aa1  and     rdx, r8
0x180030aa4  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180030aaa  mov     ebx, eax
0x180030aac  test    eax, eax
0x180030aae  js      loc_180030BDC
0x180030ab4  mov     rcx, rsi
0x180030ab7  call    cs:__imp_?GetTooltip@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetTooltip(void)
0x180030abd  mov     dl, al
0x180030abf  mov     rcx, [rbp+arg_8]
0x180030ac3  call    cs:__imp_?SetTooltip@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetTooltip(bool)
0x180030ac9  mov     ebx, eax
0x180030acb  test    eax, eax
0x180030acd  js      loc_180030C17
0x180030ad3  mov     edx, 0FFFFFFFDh
0x180030ad8  mov     rcx, [rbp+arg_8]
0x180030adc  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180030ae2  mov     ebx, eax
0x180030ae4  test    eax, eax
0x180030ae6  js      loc_180030C52
0x180030aec  mov     rbx, [rbp+arg_8]
0x180030af0  xor     edx, edx
0x180030af2  mov     rcx, [rbp+pv]
0x180030af6  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x180030afc  mov     rdi, rax
0x180030aff  test    rax, rax
0x180030b02  jz      loc_180030C8D
0x180030b08  mov     r9, rax
0x180030b0b  mov     r8d, 1
0x180030b11  lea     rdx, ?PropertyCanonicalNameProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::PropertyCanonicalNameProp(void)
0x180030b18  mov     rcx, rbx
0x180030b1b  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180030b21  mov     ebx, eax
0x180030b23  mov     rcx, rdi
0x180030b26  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180030b2c  test    ebx, ebx
0x180030b2e  js      loc_180030C92
0x180030b34  mov     rcx, [rbp+arg_10]
0x180030b38  mov     rax, [rbp+arg_8]
0x180030b3c  mov     [rcx], rax
0x180030b3f  xor     ebx, ebx
0x180030b41  mov     rcx, [rbp+pv]; pv
0x180030b45  call    cs:__imp_CoTaskMemFree
0x180030b4b  mov     eax, ebx
0x180030b4d  mov     rbx, [rsp+40h+arg_0]
0x180030b52  add     rsp, 40h
0x180030b56  pop     rdi
0x180030b57  pop     rsi
0x180030b58  pop     rbp
0x180030b59  retn
0x180030b5a  mov     ebx, 8007000Eh
0x180030b5f  mov     rcx, [rbp+18h]; this
0x180030b63  mov     r9d, ebx; char *
0x180030b66  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030b6d  mov     edx, 0ADh; void *
0x180030b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b77  nop
0x180030b78  mov     rax, [rbp+arg_10]
0x180030b7c  mov     qword ptr [rax], 0
0x180030b83  mov     rcx, [rbp+arg_8]
0x180030b87  test    rcx, rcx
0x180030b8a  jz      short loc_180030B95
0x180030b8c  mov     dl, 1
0x180030b8e  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030b94  nop
0x180030b95  jmp     short loc_180030B41
0x180030b97  xor     edx, edx
0x180030b99  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030b9f  jmp     short loc_180030B5F
0x180030ba1  mov     rcx, [rbp+18h]; this
0x180030ba5  mov     r9d, eax; char *
0x180030ba8  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030baf  mov     edx, 0ACh; void *
0x180030bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bb9  nop
0x180030bba  mov     rcx, [rbp+arg_10]
0x180030bbe  mov     qword ptr [rcx], 0
0x180030bc5  mov     rcx, [rbp+arg_8]
0x180030bc9  test    rcx, rcx
0x180030bcc  jz      short loc_180030BD7
0x180030bce  mov     dl, 1
0x180030bd0  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030bd6  nop
0x180030bd7  jmp     loc_180030B41
0x180030bdc  mov     rcx, [rbp+18h]; this
0x180030be0  mov     r9d, eax; char *
0x180030be3  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030bea  mov     edx, 0B1h; void *
0x180030bef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bf4  nop
0x180030bf5  mov     rcx, [rbp+arg_10]
0x180030bf9  mov     qword ptr [rcx], 0
0x180030c00  mov     rcx, [rbp+arg_8]
0x180030c04  test    rcx, rcx
0x180030c07  jz      short loc_180030C12
0x180030c09  mov     dl, 1
0x180030c0b  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030c11  nop
0x180030c12  jmp     loc_180030B41
0x180030c17  mov     rcx, [rbp+18h]; this
0x180030c1b  mov     r9d, eax; char *
0x180030c1e  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030c25  mov     edx, 0B2h; void *
0x180030c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c2f  nop
0x180030c30  mov     rcx, [rbp+arg_10]
0x180030c34  mov     qword ptr [rcx], 0
0x180030c3b  mov     rcx, [rbp+arg_8]
0x180030c3f  test    rcx, rcx
0x180030c42  jz      short loc_180030C4D
0x180030c44  mov     dl, 1
0x180030c46  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030c4c  nop
0x180030c4d  jmp     loc_180030B41
0x180030c52  mov     rcx, [rbp+18h]; this
0x180030c56  mov     r9d, eax; char *
0x180030c59  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030c60  mov     edx, 0B3h; void *
0x180030c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c6a  nop
0x180030c6b  mov     rcx, [rbp+arg_10]
0x180030c6f  mov     qword ptr [rcx], 0
0x180030c76  mov     rcx, [rbp+arg_8]
0x180030c7a  test    rcx, rcx
0x180030c7d  jz      short loc_180030C88
0x180030c7f  mov     dl, 1
0x180030c81  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030c87  nop
0x180030c88  jmp     loc_180030B41
0x180030c8d  mov     ebx, 8007000Eh
0x180030c92  mov     rcx, [rbp+18h]; this
0x180030c96  mov     r9d, ebx; char *
0x180030c99  lea     r8, aShellExplorerf_19; "shell\\explorerframe\\itemsview\\uiprop"...
0x180030ca0  mov     edx, 0B4h; void *
0x180030ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030caa  nop
0x180030cab  mov     rax, [rbp+arg_10]
0x180030caf  mov     qword ptr [rax], 0
0x180030cb6  mov     rcx, [rbp+arg_8]
0x180030cba  test    rcx, rcx
0x180030cbd  jz      short loc_180030CC8
0x180030cbf  mov     dl, 1
0x180030cc1  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180030cc7  nop
0x180030cc8  jmp     loc_180030B41
```
