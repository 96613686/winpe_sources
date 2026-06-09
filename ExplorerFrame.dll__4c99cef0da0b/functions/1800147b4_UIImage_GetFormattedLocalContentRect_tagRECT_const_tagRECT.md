# UIImage::_GetFormattedLocalContentRect(tagRECT const &,tagRECT *)

- ea: `0x1800147b4`
- end: `0x180014b8b`
- name: `?_GetFormattedLocalContentRect@UIImage@@AEAAXAEBUtagRECT@@PEAU2@@Z`
- size: `983`
- prototype: `void __fastcall(UIImage *__hidden this, const struct tagRECT *, struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800acf20`

## callees

- `0x1800147b4`
- `0x180016790`
- `0x1800abc90`
- `0x1800f7970`
- `0x18013f7d0`

## import_xrefs

- `USER32!SetRect` at `0x18001485a`
- `USER32!SetRect` at `0x18001499f`
- `USER32!SetRect` at `0x180014a7c`
- `USER32!SetRect` at `0x18001485a`
- `USER32!SetRect` at `0x18001499f`
- `USER32!SetRect` at `0x180014a7c`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18001481c`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800147e6`
- `DUI70!?GetOverhang@Element@DirectUI@@QEAA_NXZ` at `0x180014a3e`
- `DUI70!?GetOverhang@Element@DirectUI@@QEAA_NXZ` at `0x180014a3e`
- `DUI70!?HasPadding@Element@DirectUI@@QEAA_NXZ` at `0x180014877`
- `DUI70!?HasPadding@Element@DirectUI@@QEAA_NXZ` at `0x180014877`
- `DUI70!?HasBorder@Element@DirectUI@@QEAA_NXZ` at `0x180014863`
- `DUI70!?HasBorder@Element@DirectUI@@QEAA_NXZ` at `0x180014863`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18001492b`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800149a8`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18001492b`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800149a8`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800149f0`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800148a8`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180014936`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800149b3`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800148a8`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180014936`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800149b3`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001480b`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180014839`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001480b`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180014839`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180014890`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180014890`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180014a22`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180014a22`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x180014a11`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x180014a11`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800147fe`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001482c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180014a01`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800147fe`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001482c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180014a01`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x180014a52`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x180014a52`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x18001490e`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x18001490e`

## pseudocode

```c
void __fastcall UIImage::_GetFormattedLocalContentRect(UIImage *this, const struct tagRECT *a2, struct tagRECT *a3)
{
  struct tagRECT *v3; // r12
  int Int; // edi
  int yBottom; // ebx
  const struct tagRECT *Padding; // rax
  LONG left; // esi
  LONG top; // r13d
  LONG right; // edi
  LONG v12; // r12d
  bool IsRTL; // bl
  LONG v14; // ecx
  LONG v15; // eax
  LONG v16; // ecx
  LONG v17; // eax
  int v18; // edi
  int v19; // esi
  char ContentAlign; // bl
  LONG v21; // r8d
  int v22; // eax
  LONG v23; // ecx
  int v24; // ebx
  int v25; // ebx
  char v26; // bl
  const unsigned __int16 *String; // rax
  int FontSize; // eax
  int v29; // ecx
  int v30; // ecx
  LONG v31; // eax
  int v32; // ecx
  LONG v33; // eax
  LONG v34; // edx
  int v35; // r8d
  struct tagRECT *Value; // [rsp+30h] [rbp-40h] BYREF
  LONG bottom; // [rsp+38h] [rbp-38h]
  struct tagRECT rc; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT v39; // [rsp+50h] [rbp-20h] BYREF

  Value = a3;
  v3 = a3;
  rc = 0;
  *(_QWORD *)&v39.left = DirectUI::Element::GetValue(
                           this,
                           (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp,
                           1,
                           0);
  Int = DirectUI::Value::GetInt(*(DirectUI::Value **)&v39.left);
  CValuePtr::~CValuePtr((CValuePtr *)&v39);
  *(_QWORD *)&v39.left = DirectUI::Element::GetValue(
                           this,
                           (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp,
                           1,
                           0);
  yBottom = DirectUI::Value::GetInt(*(DirectUI::Value **)&v39.left);
  CValuePtr::~CValuePtr((CValuePtr *)&v39);
  SetRect(&rc, 0, 0, Int, yBottom);
  if ( DirectUI::Element::HasBorder(this) )
  {
    v39 = 0;
    DUI_GetBorderThickness(this, 1, &v39);
    DUI_ReduceBounds(&rc, &v39);
  }
  if ( DirectUI::Element::HasPadding(this) )
  {
    *(_QWORD *)&v39.left = 0;
    Padding = DirectUI::Element::GetPadding(this, (struct DirectUI::Value **)&v39);
    left = Padding->left;
    top = Padding->top;
    right = Padding->right;
    bottom = Padding->bottom;
    v12 = left;
    IsRTL = DirectUI::Element::IsRTL(this);
    if ( !IsRTL )
      v12 = right;
    CValuePtr::~CValuePtr((CValuePtr *)&v39);
    if ( !IsRTL )
      right = left;
    v14 = right + rc.left;
    rc.left = v14;
    if ( v14 > rc.right )
    {
      rc.left = rc.right;
    }
    else
    {
      v15 = rc.right - v12;
      if ( rc.right - v12 < v14 )
        v15 = v14;
      rc.right = v15;
    }
    v16 = top + rc.top;
    v3 = Value;
    rc.top = v16;
    if ( v16 > rc.bottom )
    {
      rc.top = rc.bottom;
    }
    else
    {
      v17 = rc.bottom - bottom;
      if ( rc.bottom - bottom < v16 )
        v17 = v16;
      rc.bottom = v17;
    }
  }
  if ( DirectUI::Element::HasContent(this) )
  {
    Value = (struct tagRECT *)DirectUI::Element::GetValue(
                                this,
                                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                                2,
                                0);
    if ( DirectUI::Value::GetType((DirectUI::Value *)Value) )
    {
      String = DirectUI::Value::GetString((DirectUI::Value *)Value);
      if ( String )
      {
        if ( *String && DirectUI::Element::GetOverhang(this) )
        {
          v39 = 0;
          FontSize = DirectUI::Element::GetFontSize(this);
          v29 = -FontSize;
          if ( FontSize > 0 )
            v29 = FontSize;
          SetRect(&v39, v29 / 6, 0, v29 / 6, 0);
          v30 = v39.left + rc.left;
          rc.left = v30;
          if ( v30 > rc.right )
          {
            rc.left = rc.right;
          }
          else
          {
            v31 = rc.right - v39.right;
            if ( rc.right - v39.right < v30 )
              v31 = v30;
            rc.right = v31;
          }
          v32 = v39.top + rc.top;
          rc.top = v32;
          if ( v32 > rc.bottom )
          {
            rc.top = rc.bottom;
          }
          else
          {
            v33 = rc.bottom - v39.bottom;
            if ( rc.bottom - v39.bottom < v32 )
              v33 = v32;
            rc.bottom = v33;
          }
        }
      }
    }
    CValuePtr::~CValuePtr((CValuePtr *)&Value);
  }
  v18 = rc.right - rc.left;
  v19 = rc.bottom - rc.top;
  ContentAlign = DirectUI::Element::GetContentAlign(this);
  if ( DirectUI::Element::IsRTL(this) )
  {
    if ( (ContentAlign & 3) != 0 )
    {
      if ( (ContentAlign & 3) == 2 )
        ContentAlign &= 0xFCu;
    }
    else
    {
      ContentAlign = ContentAlign & 0xFC | 2;
    }
  }
  v21 = a2->top;
  v22 = ContentAlign & 0xC;
  if ( (ContentAlign & 0xC) != 0 )
  {
    if ( v22 == 4 )
    {
      v21 += (a2->bottom - v21 - v19) / 2;
    }
    else if ( v22 == 8 )
    {
      v21 = a2->bottom - v19;
    }
  }
  v23 = a2->left;
  v24 = ContentAlign & 3;
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( v25 )
    {
      if ( v25 == 1 )
        v23 = a2->right - v18;
    }
    else
    {
      v23 += (a2->right - v23 - v18) / 2;
    }
  }
  SetRect(&rc, v23, v21, v18 + v23, v19 + v21);
  v26 = DirectUI::Element::GetContentAlign(this);
  DirectUI::Element::IsRTL(this);
  if ( (v26 & 8) != 0 )
  {
    v34 = rc.top;
    v35 = *((_DWORD *)this + 54);
    if ( rc.bottom - rc.top != v35 )
    {
      if ( rc.top <= rc.bottom - v35 )
        v34 = rc.bottom - v35;
      rc.top = v34;
    }
  }
  *v3 = rc;
}

```

## disassembly

```asm
0x1800147b4  mov     [rsp-38h+arg_18], rbx
0x1800147b9  push    rbp
0x1800147ba  push    rsi
0x1800147bb  push    rdi
0x1800147bc  push    r12
0x1800147be  push    r13
0x1800147c0  push    r14
0x1800147c2  push    r15
0x1800147c4  mov     rbp, rsp
0x1800147c7  sub     rsp, 70h
0x1800147cb  mov     rax, cs:__security_cookie
0x1800147d2  xor     rax, rsp
0x1800147d5  mov     [rbp+var_10], rax
0x1800147d9  xor     r9d, r9d
0x1800147dc  mov     [rbp+var_40], r8
0x1800147e0  mov     r12, r8
0x1800147e3  mov     r15, rdx
0x1800147e6  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x1800147ed  xorps   xmm0, xmm0
0x1800147f0  mov     r14, rcx
0x1800147f3  lea     esi, [r9+1]
0x1800147f7  mov     r8d, esi
0x1800147fa  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800147fe  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180014804  mov     rcx, rax
0x180014807  mov     qword ptr [rbp+var_20.left], rax
0x18001480b  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180014811  lea     rcx, [rbp+var_20]; this
0x180014815  mov     edi, eax
0x180014817  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18001481c  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x180014823  xor     r9d, r9d
0x180014826  mov     r8d, esi
0x180014829  mov     rcx, r14
0x18001482c  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180014832  mov     rcx, rax
0x180014835  mov     qword ptr [rbp+var_20.left], rax
0x180014839  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001483f  lea     rcx, [rbp+var_20]; this
0x180014843  mov     ebx, eax
0x180014845  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18001484a  mov     r9d, edi; xRight
0x18001484d  mov     [rsp+70h+yBottom], ebx; yBottom
0x180014851  xor     r8d, r8d; yTop
0x180014854  lea     rcx, [rbp+rc]; lprc
0x180014858  xor     edx, edx; xLeft
0x18001485a  call    cs:__imp_SetRect
0x180014860  mov     rcx, r14
0x180014863  call    cs:__imp_?HasBorder@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasBorder(void)
0x180014869  xor     r13d, r13d
0x18001486c  test    al, al
0x18001486e  jnz     loc_180014B64
0x180014874  mov     rcx, r14
0x180014877  call    cs:__imp_?HasPadding@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasPadding(void)
0x18001487d  test    al, al
0x18001487f  jz      loc_18001490B
0x180014885  lea     rdx, [rbp+var_20]
0x180014889  mov     qword ptr [rbp+var_20.left], r13
0x18001488d  mov     rcx, r14
0x180014890  call    cs:__imp_?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetPadding(DirectUI::Value * *)
0x180014896  mov     rcx, r14
0x180014899  mov     esi, [rax]
0x18001489b  mov     r13d, [rax+4]
0x18001489f  mov     edi, [rax+8]
0x1800148a2  mov     eax, [rax+0Ch]
0x1800148a5  mov     [rbp+var_38], eax
0x1800148a8  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x1800148ae  mov     r12d, esi
0x1800148b1  lea     rcx, [rbp+var_20]; this
0x1800148b5  test    al, al
0x1800148b7  mov     bl, al
0x1800148b9  cmovz   r12d, edi
0x1800148bd  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800148c2  mov     ecx, [rbp+rc.left]
0x1800148c5  test    bl, bl
0x1800148c7  mov     eax, [rbp+rc.right]
0x1800148ca  cmovz   edi, esi
0x1800148cd  add     ecx, edi
0x1800148cf  mov     [rbp+rc.left], ecx
0x1800148d2  cmp     ecx, eax
0x1800148d4  jg      loc_180014B21
0x1800148da  sub     eax, r12d
0x1800148dd  cmp     eax, ecx
0x1800148df  cmovl   eax, ecx
0x1800148e2  mov     [rbp+rc.right], eax
0x1800148e5  mov     ecx, [rbp+rc.top]
0x1800148e8  mov     eax, [rbp+rc.bottom]
0x1800148eb  add     ecx, r13d
0x1800148ee  mov     r12, [rbp+var_40]
0x1800148f2  mov     [rbp+rc.top], ecx
0x1800148f5  cmp     ecx, eax
0x1800148f7  jg      loc_180014B49
0x1800148fd  sub     eax, [rbp+var_38]
0x180014900  cmp     eax, ecx
0x180014902  cmovl   eax, ecx
0x180014905  mov     [rbp+rc.bottom], eax
0x180014908  xor     r13d, r13d
0x18001490b  mov     rcx, r14
0x18001490e  call    cs:__imp_?HasContent@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasContent(void)
0x180014914  test    al, al
0x180014916  jnz     loc_1800149F0
0x18001491c  mov     edi, [rbp+rc.right]
0x18001491f  mov     rcx, r14
0x180014922  mov     esi, [rbp+rc.bottom]
0x180014925  sub     edi, [rbp+rc.left]
0x180014928  sub     esi, [rbp+rc.top]
0x18001492b  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x180014931  mov     rcx, r14
0x180014934  mov     ebx, eax
0x180014936  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18001493c  mov     r9d, 2
0x180014942  test    al, al
0x180014944  jnz     loc_180014B31
0x18001494a  mov     r8d, [r15+4]
0x18001494e  mov     eax, ebx
0x180014950  and     eax, 0Ch
0x180014953  jz      short loc_18001496E
0x180014955  cmp     eax, 4
0x180014958  jnz     loc_180014AF8
0x18001495e  mov     eax, [r15+0Ch]
0x180014962  sub     eax, r8d
0x180014965  sub     eax, esi
0x180014967  cdq
0x180014968  idiv    r9d
0x18001496b  add     r8d, eax; yTop
0x18001496e  mov     ecx, [r15]
0x180014971  and     ebx, 3
0x180014974  jz      short loc_18001498D
0x180014976  sub     ebx, 1
0x180014979  jnz     loc_180014B0D
0x18001497f  mov     eax, [r15+8]
0x180014983  sub     eax, ecx
0x180014985  sub     eax, edi
0x180014987  cdq
0x180014988  idiv    r9d
0x18001498b  add     ecx, eax
0x18001498d  lea     eax, [rsi+r8]
0x180014991  mov     edx, ecx; xLeft
0x180014993  lea     r9d, [rdi+rcx]; xRight
0x180014997  mov     [rsp+70h+yBottom], eax; yBottom
0x18001499b  lea     rcx, [rbp+rc]; lprc
0x18001499f  call    cs:__imp_SetRect
0x1800149a5  mov     rcx, r14
0x1800149a8  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x1800149ae  mov     rcx, r14
0x1800149b1  mov     ebx, eax
0x1800149b3  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x1800149b9  test    bl, 8
0x1800149bc  jnz     loc_180014ACE
0x1800149c2  movups  xmm0, xmmword ptr [rbp+rc.left]
0x1800149c6  movdqu  xmmword ptr [r12], xmm0
0x1800149cc  mov     rcx, [rbp+var_10]
0x1800149d0  xor     rcx, rsp; StackCookie
0x1800149d3  call    __security_check_cookie
0x1800149d8  mov     rbx, [rsp+70h+arg_18]
0x1800149e0  add     rsp, 70h
0x1800149e4  pop     r15
0x1800149e6  pop     r14
0x1800149e8  pop     r13
0x1800149ea  pop     r12
0x1800149ec  pop     rdi
0x1800149ed  pop     rsi
0x1800149ee  pop     rbp
0x1800149ef  retn
0x1800149f0  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800149f7  xor     r9d, r9d
0x1800149fa  mov     rcx, r14
0x1800149fd  lea     r8d, [r9+2]
0x180014a01  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180014a07  mov     rcx, rax
0x180014a0a  mov     [rbp+var_40], rax
0x180014a0e  mov     rbx, rax
0x180014a11  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x180014a17  test    eax, eax
0x180014a19  jz      loc_180014AC0
0x180014a1f  mov     rcx, rbx
0x180014a22  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180014a28  test    rax, rax
0x180014a2b  jz      loc_180014AC0
0x180014a31  cmp     [rax], r13w
0x180014a35  jz      loc_180014AC0
0x180014a3b  mov     rcx, r14
0x180014a3e  call    cs:__imp_?GetOverhang@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetOverhang(void)
0x180014a44  test    al, al
0x180014a46  jz      short loc_180014AC0
0x180014a48  xorps   xmm0, xmm0
0x180014a4b  mov     rcx, r14
0x180014a4e  movups  xmmword ptr [rbp+var_20.left], xmm0
0x180014a52  call    cs:__imp_?GetFontSize@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontSize(void)
0x180014a58  mov     ecx, eax
0x180014a5a  mov     [rsp+70h+yBottom], r13d; yBottom
0x180014a5f  neg     ecx
0x180014a61  cmovs   ecx, eax
0x180014a64  mov     eax, 2AAAAAABh
0x180014a69  imul    ecx
0x180014a6b  xor     r8d, r8d; yTop
0x180014a6e  lea     rcx, [rbp+var_20]; lprc
0x180014a72  mov     eax, edx
0x180014a74  shr     eax, 1Fh
0x180014a77  add     edx, eax; xLeft
0x180014a79  mov     r9d, edx; xRight
0x180014a7c  call    cs:__imp_SetRect
0x180014a82  mov     ecx, [rbp+rc.left]
0x180014a85  add     ecx, [rbp+var_20.left]
0x180014a88  mov     eax, [rbp+rc.right]
0x180014a8b  mov     [rbp+rc.left], ecx
0x180014a8e  cmp     ecx, eax
0x180014a90  jg      loc_180014B29
0x180014a96  sub     eax, [rbp+var_20.right]
0x180014a99  cmp     eax, ecx
0x180014a9b  cmovl   eax, ecx
0x180014a9e  mov     [rbp+rc.right], eax
0x180014aa1  mov     ecx, [rbp+rc.top]
0x180014aa4  add     ecx, [rbp+var_20.top]
0x180014aa7  mov     eax, [rbp+rc.bottom]
0x180014aaa  mov     [rbp+rc.top], ecx
0x180014aad  cmp     ecx, eax
0x180014aaf  jg      loc_180014B51
0x180014ab5  sub     eax, [rbp+var_20.bottom]
0x180014ab8  cmp     eax, ecx
0x180014aba  cmovl   eax, ecx
0x180014abd  mov     [rbp+rc.bottom], eax
0x180014ac0  lea     rcx, [rbp+var_40]; this
0x180014ac4  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180014ac9  jmp     loc_18001491C
0x180014ace  mov     ecx, [rbp+rc.bottom]
0x180014ad1  mov     eax, ecx
0x180014ad3  mov     edx, [rbp+rc.top]
0x180014ad6  sub     eax, edx
0x180014ad8  mov     r8d, [r14+0D8h]
0x180014adf  cmp     eax, r8d
0x180014ae2  jz      loc_1800149C2
0x180014ae8  sub     ecx, r8d
0x180014aeb  cmp     edx, ecx
0x180014aed  cmovle  edx, ecx
0x180014af0  mov     [rbp+rc.top], edx
0x180014af3  jmp     loc_1800149C2
0x180014af8  cmp     eax, 8
0x180014afb  jnz     loc_18001496E
0x180014b01  mov     r8d, [r15+0Ch]
0x180014b05  sub     r8d, esi
0x180014b08  jmp     loc_18001496E
0x180014b0d  cmp     ebx, 1
0x180014b10  jnz     loc_18001498D
0x180014b16  mov     ecx, [r15+8]
0x180014b1a  sub     ecx, edi
0x180014b1c  jmp     loc_18001498D
0x180014b21  mov     [rbp+rc.left], eax
0x180014b24  jmp     loc_1800148E5
0x180014b29  mov     [rbp+rc.left], eax
0x180014b2c  jmp     loc_180014AA1
0x180014b31  mov     eax, ebx
0x180014b33  and     eax, 3
0x180014b36  jz      short loc_180014B59
0x180014b38  cmp     eax, r9d
0x180014b3b  jnz     loc_18001494A
0x180014b41  and     ebx, 0FFFFFFFCh
0x180014b44  jmp     loc_18001494A
0x180014b49  mov     [rbp+rc.top], eax
0x180014b4c  jmp     loc_180014908
0x180014b51  mov     [rbp+rc.top], eax
0x180014b54  jmp     loc_180014AC0
0x180014b59  and     ebx, 0FFFFFFFEh
0x180014b5c  or      ebx, r9d
0x180014b5f  jmp     loc_18001494A
0x180014b64  xorps   xmm0, xmm0
0x180014b67  lea     r8, [rbp+var_20]
0x180014b6b  mov     edx, esi
0x180014b6d  mov     rcx, r14
0x180014b70  movups  xmmword ptr [rbp+var_20.left], xmm0
0x180014b74  call    ?DUI_GetBorderThickness@@YAXPEAVElement@DirectUI@@W4DUI_COORDINATES_SYSTEM@@PEAUtagRECT@@@Z; DUI_GetBorderThickness(DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagRECT *)
0x180014b79  lea     rdx, [rbp+var_20]; struct tagRECT *
0x180014b7d  lea     rcx, [rbp+rc]; struct tagRECT *
0x180014b81  call    ?DUI_ReduceBounds@@YAXPEAUtagRECT@@PEBU1@@Z; DUI_ReduceBounds(tagRECT *,tagRECT const *)
0x180014b86  jmp     loc_180014874
```
