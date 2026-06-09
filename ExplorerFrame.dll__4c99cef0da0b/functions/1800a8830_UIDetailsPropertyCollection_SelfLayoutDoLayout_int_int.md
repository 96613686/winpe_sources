# UIDetailsPropertyCollection::_SelfLayoutDoLayout(int,int)

- ea: `0x1800a8830`
- end: `0x1800a8c99`
- name: `?_SelfLayoutDoLayout@UIDetailsPropertyCollection@@EEAAXHH@Z`
- size: `1129`
- prototype: `void __fastcall(UIDetailsPropertyCollection *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015640`
- `0x180016790`
- `0x1800a8830`
- `0x1800abc90`
- `0x1800f7970`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `USER32!SetRect` at `0x1800a89d0`
- `USER32!SetRect` at `0x1800a8bf7`
- `USER32!SetRect` at `0x1800a89d0`
- `USER32!SetRect` at `0x1800a8bf7`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800a8aa3`
- `DUI70!?GetOverhang@Element@DirectUI@@QEAA_NXZ` at `0x1800a8bb9`
- `DUI70!?GetOverhang@Element@DirectUI@@QEAA_NXZ` at `0x1800a8bb9`
- `DUI70!?HasPadding@Element@DirectUI@@QEAA_NXZ` at `0x1800a89ea`
- `DUI70!?HasPadding@Element@DirectUI@@QEAA_NXZ` at `0x1800a89ea`
- `DUI70!?HasBorder@Element@DirectUI@@QEAA_NXZ` at `0x1800a89d9`
- `DUI70!?HasBorder@Element@DirectUI@@QEAA_NXZ` at `0x1800a89d9`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800a8b76`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800a8b0b`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800a8b0b`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a88f7`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a88f7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a8b41`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a8b41`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a8aba`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a8aba`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a89ff`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a89ff`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800a8922`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800a8945`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800a8922`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800a8945`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800a8ba1`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800a8ba1`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a8b90`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a8b90`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a8aad`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a8b80`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a8aad`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a8b80`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a8bcd`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a8bcd`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a887c`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a887c`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x1800a8a5b`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x1800a8a5b`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a8afd`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a8afd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UIDetailsPropertyCollection::_SelfLayoutDoLayout(UIDetailsPropertyCollection *this, int a2, int a3)
{
  __int64 v4; // rdi
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v6; // rbx
  __int64 v7; // rax
  struct DirectUI::IClassInfo *v8; // rsi
  DirectUI::Element *i; // rbx
  __int64 v10; // rax
  __int64 Children; // r12
  LONG v12; // r13d
  _QWORD *v13; // rdi
  _DWORD *v14; // rax
  int v15; // ecx
  _QWORD *v16; // rax
  const struct tagRECT *Padding; // rax
  LONG left; // ebx
  LONG top; // edi
  LONG right; // esi
  LONG bottom; // r15d
  LONG v22; // ecx
  LONG v23; // eax
  LONG v24; // ecx
  LONG v25; // eax
  unsigned int v26; // edx
  int v27; // ecx
  __int64 v28; // rsi
  DirectUI::Element *v29; // rsi
  int Int; // ebx
  int v31; // edi
  int v32; // ebx
  DirectUI::Value *v33; // rcx
  DirectUI::Value *Value; // rbx
  const unsigned __int16 *String; // rax
  int FontSize; // eax
  int v37; // ecx
  int v38; // ecx
  LONG v39; // eax
  int v40; // ecx
  LONG v41; // eax
  int xLeft[4]; // [rsp+40h] [rbp-29h] BYREF
  int v43; // [rsp+50h] [rbp-19h]
  int v44; // [rsp+54h] [rbp-15h]
  DirectUI::Value *v45; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT v47; // [rsp+70h] [rbp+7h] BYREF

  if ( a2 > 0 )
  {
    v43 = a3;
    v44 = a2;
    if ( a3 > 0 )
    {
      v4 = 0;
      TopLevel = DirectUI::Element::GetTopLevel(this);
      v6 = TopLevel;
      if ( TopLevel )
      {
        v7 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
        if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v7 + 80LL))(
               v7,
               UIItemsView::Class) )
        {
          v4 = *((_QWORD *)v6 + 47);
        }
      }
      v8 = LineViewer::Class;
      for ( i = this; i; i = DirectUI::Element::GetParent(i) )
      {
        v10 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)i + 280LL))(i);
        if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v10 + 80LL))(
               v10,
               v8) )
        {
          break;
        }
      }
      if ( v4 && i )
      {
        v45 = 0;
        Children = DirectUI::Element::GetChildren(this, &v45);
        if ( Children )
        {
          v12 = 0;
          v13 = 0;
          *(_QWORD *)&v47.left = 0;
          v14 = (_DWORD *)DirectUI::Element::GetChildren(i, &v47);
          if ( v14 )
          {
            v15 = *v14;
            if ( (*v14 & 0xFFFFFFF) != 0 )
            {
              v16 = v14 + 2;
              if ( (v15 & 0x10000000) != 0 )
                v16 = (_QWORD *)*v16;
              v13 = (_QWORD *)*v16;
            }
          }
          CValuePtr::~CValuePtr((CValuePtr *)&v47);
          if ( v13 )
          {
            rc = 0;
            xLeft[0] = 0;
            xLeft[1] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
            DUI_MapElementPoint(this, v13, 0, xLeft, xLeft);
            SetRect(&rc, xLeft[0], xLeft[1], xLeft[0] + rc.right - rc.left, xLeft[1] + rc.bottom - rc.top);
            if ( DirectUI::Element::HasBorder(this) )
            {
              *(_OWORD *)xLeft = 0;
              DUI_GetBorderThickness(this, 0, xLeft);
              DUI_ReduceBounds(&rc, (const struct tagRECT *)xLeft);
            }
            if ( DirectUI::Element::HasPadding(this) )
            {
              *(_QWORD *)xLeft = 0;
              Padding = DirectUI::Element::GetPadding(this, (struct DirectUI::Value **)xLeft);
              left = Padding->left;
              top = Padding->top;
              right = Padding->right;
              bottom = Padding->bottom;
              CValuePtr::~CValuePtr((CValuePtr *)xLeft);
              v22 = left + rc.left;
              rc.left = v22;
              if ( v22 > rc.right )
              {
                rc.left = rc.right;
              }
              else
              {
                v23 = rc.right - right;
                if ( rc.right - right < v22 )
                  v23 = v22;
                rc.right = v23;
              }
              v24 = top + rc.top;
              rc.top = v24;
              if ( v24 > rc.bottom )
              {
                rc.top = rc.bottom;
              }
              else
              {
                v25 = rc.bottom - bottom;
                if ( rc.bottom - bottom < v24 )
                  v25 = v24;
                rc.bottom = v25;
              }
            }
            if ( DirectUI::Element::HasContent(this) )
            {
              Value = DirectUI::Element::GetValue(
                        this,
                        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                        2,
                        0);
              *(_QWORD *)xLeft = Value;
              if ( DirectUI::Value::GetType(Value) )
              {
                String = DirectUI::Value::GetString(Value);
                if ( String )
                {
                  if ( *String && DirectUI::Element::GetOverhang(this) )
                  {
                    v47 = 0;
                    FontSize = DirectUI::Element::GetFontSize(this);
                    v37 = -FontSize;
                    if ( FontSize > 0 )
                      v37 = FontSize;
                    SetRect(&v47, v37 / 6, 0, v37 / 6, 0);
                    v38 = v47.left + rc.left;
                    rc.left = v38;
                    if ( v38 > rc.right )
                    {
                      rc.left = rc.right;
                    }
                    else
                    {
                      v39 = rc.right - v47.right;
                      if ( rc.right - v47.right < v38 )
                        v39 = v38;
                      rc.right = v39;
                    }
                    v40 = v47.top + rc.top;
                    rc.top = v40;
                    if ( v40 > rc.bottom )
                    {
                      rc.top = rc.bottom;
                    }
                    else
                    {
                      v41 = rc.bottom - v47.bottom;
                      if ( rc.bottom - v47.bottom < v40 )
                        v41 = v40;
                      rc.bottom = v41;
                    }
                  }
                }
              }
              CValuePtr::~CValuePtr((CValuePtr *)xLeft);
            }
            v12 = rc.left;
          }
          xLeft[0] = 0;
          v26 = 0;
          v47.left = 0;
          v27 = *(_DWORD *)Children;
          if ( (*(_DWORD *)Children & 0xFFFFFFF) != 0 )
          {
            do
            {
              if ( (v27 & 0x10000000) != 0 )
                v28 = *(_QWORD *)(Children + 8);
              else
                v28 = Children + 8;
              v29 = *(DirectUI::Element **)(v28 + 8LL * v26);
              *(_QWORD *)&rc.left = DirectUI::Element::GetValue(
                                      v29,
                                      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp,
                                      1,
                                      0);
              Int = DirectUI::Value::GetInt(*(DirectUI::Value **)&rc.left);
              CValuePtr::~CValuePtr((CValuePtr *)&rc);
              v31 = Int - v12;
              if ( v47.left )
                v31 = Int;
              v32 = xLeft[0];
              DirectUI::Layout::UpdateLayoutRect(this, v44, v43, v29, xLeft[0], 0, v31, v43);
              DirectUI::Element::SetVisible(v29, v31 != 0);
              xLeft[0] = v31 + v32;
              v26 = v47.left + 1;
              v47.left = v26;
              v27 = *(_DWORD *)Children;
            }
            while ( v26 < (*(_DWORD *)Children & 0xFFFFFFFu) );
          }
        }
        v33 = v45;
        if ( v45 )
        {
          v45 = 0;
          DirectUI::Value::Release(v33);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a8830  test    edx, edx
0x1800a8832  jle     locret_1800A8B6E
0x1800a8838  mov     [rsp-8+arg_18], rbx
0x1800a883d  push    rbp
0x1800a883e  push    rsi
0x1800a883f  push    rdi
0x1800a8840  push    r12
0x1800a8842  push    r13
0x1800a8844  push    r14
0x1800a8846  push    r15
0x1800a8848  lea     rbp, [rsp-27h]
0x1800a884d  sub     rsp, 90h
0x1800a8854  mov     rax, cs:__security_cookie
0x1800a885b  xor     rax, rsp
0x1800a885e  mov     [rbp+57h+var_40], rax
0x1800a8862  mov     eax, r8d
0x1800a8865  mov     [rbp+57h+var_70], eax
0x1800a8868  mov     [rbp+57h+var_6C], edx
0x1800a886b  mov     r14, rcx
0x1800a886e  xor     r15d, r15d
0x1800a8871  test    eax, eax
0x1800a8873  jle     loc_1800A8B48
0x1800a8879  mov     edi, r15d
0x1800a887c  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x1800a8882  mov     rbx, rax
0x1800a8885  test    rax, rax
0x1800a8888  jz      short loc_1800A88BD
0x1800a888a  mov     rcx, [rax]
0x1800a888d  mov     rax, [rcx+118h]
0x1800a8894  mov     rcx, rbx
0x1800a8897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a889c  mov     r8, rax
0x1800a889f  mov     rcx, [rax]
0x1800a88a2  mov     rax, [rcx+50h]
0x1800a88a6  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x1800a88ad  mov     rcx, r8
0x1800a88b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a88b5  test    al, al
0x1800a88b7  jnz     loc_1800A8C65
0x1800a88bd  mov     rsi, cs:?Class@LineViewer@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LineViewer::Class
0x1800a88c4  mov     rbx, r14
0x1800a88c7  test    r14, r14
0x1800a88ca  jz      short loc_1800A8905
0x1800a88cc  mov     rax, [rbx]
0x1800a88cf  mov     rcx, rbx
0x1800a88d2  mov     rax, [rax+118h]
0x1800a88d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a88de  mov     rcx, rax
0x1800a88e1  mov     rdx, [rax]
0x1800a88e4  mov     rax, [rdx+50h]
0x1800a88e8  mov     rdx, rsi
0x1800a88eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a88f0  test    al, al
0x1800a88f2  jnz     short loc_1800A8905
0x1800a88f4  mov     rcx, rbx
0x1800a88f7  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x1800a88fd  mov     rbx, rax
0x1800a8900  test    rax, rax
0x1800a8903  jnz     short loc_1800A88CC
0x1800a8905  test    rdi, rdi
0x1800a8908  jz      loc_1800A8B48
0x1800a890e  test    rbx, rbx
0x1800a8911  jz      loc_1800A8B48
0x1800a8917  mov     [rbp+57h+var_68], r15
0x1800a891b  lea     rdx, [rbp+57h+var_68]
0x1800a891f  mov     rcx, r14
0x1800a8922  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800a8928  mov     r12, rax
0x1800a892b  test    rax, rax
0x1800a892e  jz      loc_1800A8B34
0x1800a8934  mov     r13d, r15d
0x1800a8937  mov     rdi, r15
0x1800a893a  mov     qword ptr [rbp+57h+var_50.left], r15
0x1800a893e  lea     rdx, [rbp+57h+var_50]
0x1800a8942  mov     rcx, rbx
0x1800a8945  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800a894b  test    rax, rax
0x1800a894e  jz      short loc_1800A896A
0x1800a8950  mov     ecx, [rax]
0x1800a8952  test    ecx, 0FFFFFFFh
0x1800a8958  jbe     short loc_1800A896A
0x1800a895a  add     rax, 8
0x1800a895e  bt      ecx, 1Ch
0x1800a8962  jnb     short loc_1800A8967
0x1800a8964  mov     rax, [rax]
0x1800a8967  mov     rdi, [rax]
0x1800a896a  lea     rcx, [rbp+57h+var_50]; this
0x1800a896e  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800a8973  test    rdi, rdi
0x1800a8976  jz      loc_1800A8A6D
0x1800a897c  xorps   xmm0, xmm0
0x1800a897f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800a8983  movss   [rbp+57h+xLeft], xmm0
0x1800a8988  psrldq  xmm0, 4
0x1800a898d  movd    [rbp+57h+xLeft+4], xmm0
0x1800a8992  lea     rax, [rbp+57h+xLeft]
0x1800a8996  mov     qword ptr [rsp+0C0h+yBottom], rax
0x1800a899b  lea     r9, [rbp+57h+xLeft]
0x1800a899f  xor     r8d, r8d
0x1800a89a2  mov     rdx, rdi
0x1800a89a5  mov     rcx, r14
0x1800a89a8  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x1800a89ad  mov     eax, [rbp+57h+rc.bottom]
0x1800a89b0  sub     eax, [rbp+57h+rc.top]
0x1800a89b3  mov     r8d, [rbp+57h+xLeft+4]; yTop
0x1800a89b7  add     eax, r8d
0x1800a89ba  mov     r9d, [rbp+57h+rc.right]
0x1800a89be  sub     r9d, [rbp+57h+rc.left]
0x1800a89c2  mov     edx, [rbp+57h+xLeft]; xLeft
0x1800a89c5  add     r9d, edx; xRight
0x1800a89c8  mov     [rsp+0C0h+yBottom], eax; yBottom
0x1800a89cc  lea     rcx, [rbp+57h+rc]; lprc
0x1800a89d0  call    cs:__imp_SetRect
0x1800a89d6  mov     rcx, r14
0x1800a89d9  call    cs:__imp_?HasBorder@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasBorder(void)
0x1800a89df  test    al, al
0x1800a89e1  jnz     loc_1800A8C71
0x1800a89e7  mov     rcx, r14
0x1800a89ea  call    cs:__imp_?HasPadding@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasPadding(void)
0x1800a89f0  test    al, al
0x1800a89f2  jz      short loc_1800A8A58
0x1800a89f4  mov     qword ptr [rbp+57h+xLeft], r15
0x1800a89f8  lea     rdx, [rbp+57h+xLeft]
0x1800a89fc  mov     rcx, r14
0x1800a89ff  call    cs:__imp_?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetPadding(DirectUI::Value * *)
0x1800a8a05  mov     ebx, [rax]
0x1800a8a07  mov     edi, [rax+4]
0x1800a8a0a  mov     esi, [rax+8]
0x1800a8a0d  mov     r15d, [rax+0Ch]
0x1800a8a11  lea     rcx, [rbp+57h+xLeft]; this
0x1800a8a15  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800a8a1a  mov     ecx, [rbp+57h+rc.left]
0x1800a8a1d  add     ecx, ebx
0x1800a8a1f  mov     [rbp+57h+rc.left], ecx
0x1800a8a22  mov     eax, [rbp+57h+rc.right]
0x1800a8a25  cmp     ecx, eax
0x1800a8a27  jg      loc_1800A8C41
0x1800a8a2d  sub     eax, esi
0x1800a8a2f  cmp     eax, ecx
0x1800a8a31  cmovl   eax, ecx
0x1800a8a34  mov     [rbp+57h+rc.right], eax
0x1800a8a37  mov     ecx, [rbp+57h+rc.top]
0x1800a8a3a  add     ecx, edi
0x1800a8a3c  mov     [rbp+57h+rc.top], ecx
0x1800a8a3f  mov     eax, [rbp+57h+rc.bottom]
0x1800a8a42  cmp     ecx, eax
0x1800a8a44  jg      loc_1800A8C58
0x1800a8a4a  sub     eax, r15d
0x1800a8a4d  cmp     eax, ecx
0x1800a8a4f  cmovl   eax, ecx
0x1800a8a52  mov     [rbp+57h+rc.bottom], eax
0x1800a8a55  xor     r15d, r15d
0x1800a8a58  mov     rcx, r14
0x1800a8a5b  call    cs:__imp_?HasContent@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasContent(void)
0x1800a8a61  test    al, al
0x1800a8a63  jnz     loc_1800A8B6F
0x1800a8a69  mov     r13d, [rbp+57h+rc.left]
0x1800a8a6d  mov     [rbp+57h+xLeft], r15d
0x1800a8a71  mov     edx, r15d
0x1800a8a74  mov     [rbp+57h+var_50.left], edx
0x1800a8a77  mov     ecx, [r12]
0x1800a8a7b  test    ecx, 0FFFFFFFh
0x1800a8a81  jbe     loc_1800A8B34
0x1800a8a87  bt      ecx, 1Ch
0x1800a8a8b  jnb     loc_1800A8C49
0x1800a8a91  mov     rsi, [r12+8]
0x1800a8a96  mov     eax, edx
0x1800a8a98  mov     rsi, [rsi+rax*8]
0x1800a8a9c  xor     r9d, r9d
0x1800a8a9f  lea     r8d, [r9+1]
0x1800a8aa3  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x1800a8aaa  mov     rcx, rsi
0x1800a8aad  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800a8ab3  mov     qword ptr [rbp+57h+rc.left], rax
0x1800a8ab7  mov     rcx, rax
0x1800a8aba  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800a8ac0  mov     ebx, eax
0x1800a8ac2  lea     rcx, [rbp+57h+rc]; this
0x1800a8ac6  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800a8acb  mov     edi, ebx
0x1800a8acd  sub     edi, r13d
0x1800a8ad0  cmp     [rbp+57h+var_50.left], 0
0x1800a8ad4  cmovnz  edi, ebx
0x1800a8ad7  mov     eax, [rbp+57h+var_70]
0x1800a8ada  mov     [rsp+0C0h+var_88], eax
0x1800a8ade  mov     [rsp+0C0h+var_90], edi
0x1800a8ae2  mov     [rsp+0C0h+var_98], 0
0x1800a8aea  mov     ebx, [rbp+57h+xLeft]
0x1800a8aed  mov     [rsp+0C0h+yBottom], ebx
0x1800a8af1  mov     r9, rsi
0x1800a8af4  mov     r8d, eax
0x1800a8af7  mov     edx, [rbp+57h+var_6C]
0x1800a8afa  mov     rcx, r14
0x1800a8afd  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800a8b03  test    edi, edi
0x1800a8b05  setnz   dl
0x1800a8b08  mov     rcx, rsi
0x1800a8b0b  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800a8b11  add     ebx, edi
0x1800a8b13  mov     [rbp+57h+xLeft], ebx
0x1800a8b16  mov     edx, [rbp+57h+var_50.left]
0x1800a8b19  inc     edx
0x1800a8b1b  mov     [rbp+57h+var_50.left], edx
0x1800a8b1e  mov     ecx, [r12]
0x1800a8b22  mov     eax, ecx
0x1800a8b24  and     eax, 0FFFFFFFh
0x1800a8b29  cmp     edx, eax
0x1800a8b2b  jb      loc_1800A8A87
0x1800a8b31  xor     r15d, r15d
0x1800a8b34  mov     rcx, [rbp+57h+var_68]
0x1800a8b38  test    rcx, rcx
0x1800a8b3b  jz      short loc_1800A8B48
0x1800a8b3d  mov     [rbp+57h+var_68], r15
0x1800a8b41  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800a8b47  nop
0x1800a8b48  mov     rcx, [rbp+57h+var_40]
0x1800a8b4c  xor     rcx, rsp; StackCookie
0x1800a8b4f  call    __security_check_cookie
0x1800a8b54  mov     rbx, [rsp+0C0h+arg_18]
0x1800a8b5c  add     rsp, 90h
0x1800a8b63  pop     r15
0x1800a8b65  pop     r14
0x1800a8b67  pop     r13
0x1800a8b69  pop     r12
0x1800a8b6b  pop     rdi
0x1800a8b6c  pop     rsi
0x1800a8b6d  pop     rbp
0x1800a8b6e  retn
0x1800a8b6f  xor     r9d, r9d
0x1800a8b72  lea     r8d, [r9+2]
0x1800a8b76  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800a8b7d  mov     rcx, r14
0x1800a8b80  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800a8b86  mov     rbx, rax
0x1800a8b89  mov     qword ptr [rbp+57h+xLeft], rax
0x1800a8b8d  mov     rcx, rax
0x1800a8b90  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800a8b96  test    eax, eax
0x1800a8b98  jz      loc_1800A8C33
0x1800a8b9e  mov     rcx, rbx
0x1800a8ba1  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800a8ba7  test    rax, rax
0x1800a8baa  jz      loc_1800A8C33
0x1800a8bb0  cmp     [rax], r15w
0x1800a8bb4  jz      short loc_1800A8C33
0x1800a8bb6  mov     rcx, r14
0x1800a8bb9  call    cs:__imp_?GetOverhang@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetOverhang(void)
0x1800a8bbf  test    al, al
0x1800a8bc1  jz      short loc_1800A8C33
0x1800a8bc3  xorps   xmm0, xmm0
0x1800a8bc6  movups  xmmword ptr [rbp+57h+var_50.left], xmm0
0x1800a8bca  mov     rcx, r14
0x1800a8bcd  call    cs:__imp_?GetFontSize@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontSize(void)
0x1800a8bd3  mov     ecx, eax
0x1800a8bd5  neg     ecx
0x1800a8bd7  cmovs   ecx, eax
0x1800a8bda  mov     eax, 2AAAAAABh
0x1800a8bdf  imul    ecx
0x1800a8be1  mov     eax, edx
0x1800a8be3  shr     eax, 1Fh
0x1800a8be6  add     edx, eax; xLeft
0x1800a8be8  mov     [rsp+0C0h+yBottom], r15d; yBottom
0x1800a8bed  mov     r9d, edx; xRight
0x1800a8bf0  xor     r8d, r8d; yTop
0x1800a8bf3  lea     rcx, [rbp+57h+var_50]; lprc
0x1800a8bf7  call    cs:__imp_SetRect
0x1800a8bfd  mov     ecx, [rbp+57h+rc.left]
0x1800a8c00  add     ecx, [rbp+57h+var_50.left]
0x1800a8c03  mov     [rbp+57h+rc.left], ecx
0x1800a8c06  mov     eax, [rbp+57h+rc.right]
0x1800a8c09  cmp     ecx, eax
0x1800a8c0b  jg      short loc_1800A8C53
0x1800a8c0d  sub     eax, [rbp+57h+var_50.right]
0x1800a8c10  cmp     eax, ecx
0x1800a8c12  cmovl   eax, ecx
0x1800a8c15  mov     [rbp+57h+rc.right], eax
0x1800a8c18  mov     ecx, [rbp+57h+rc.top]
0x1800a8c1b  add     ecx, [rbp+57h+var_50.top]
0x1800a8c1e  mov     [rbp+57h+rc.top], ecx
0x1800a8c21  mov     eax, [rbp+57h+rc.bottom]
0x1800a8c24  cmp     ecx, eax
0x1800a8c26  jg      short loc_1800A8C60
0x1800a8c28  sub     eax, [rbp+57h+var_50.bottom]
0x1800a8c2b  cmp     eax, ecx
0x1800a8c2d  cmovl   eax, ecx
0x1800a8c30  mov     [rbp+57h+rc.bottom], eax
0x1800a8c33  lea     rcx, [rbp+57h+xLeft]; this
0x1800a8c37  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800a8c3c  jmp     loc_1800A8A69
0x1800a8c41  mov     [rbp+57h+rc.left], eax
0x1800a8c44  jmp     loc_1800A8A37
0x1800a8c49  lea     rsi, [r12+8]
0x1800a8c4e  jmp     loc_1800A8A96
0x1800a8c53  mov     [rbp+57h+rc.left], eax
0x1800a8c56  jmp     short loc_1800A8C18
0x1800a8c58  mov     [rbp+57h+rc.top], eax
0x1800a8c5b  jmp     loc_1800A8A55
0x1800a8c60  mov     [rbp+57h+rc.top], eax
0x1800a8c63  jmp     short loc_1800A8C33
0x1800a8c65  mov     rdi, [rbx+178h]
  ... truncated ...
```
