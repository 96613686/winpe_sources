# ItemGridLayout::GetInfoForSection(int,SectionInfo const *,SectionInfo *)

- ea: `0x1800157c0`
- end: `0x180015c54`
- name: `?GetInfoForSection@ItemGridLayout@@UEAAXHPEBVSectionInfo@@PEAV2@@Z`
- size: `1172`
- prototype: `void(ItemGridLayout *__hidden this, int, const struct SectionInfo *, struct SectionInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800157c0`
- `0x180016790`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `USER32!UnionRect` at `0x180015abe`
- `USER32!UnionRect` at `0x180015abe`
- `USER32!SetRect` at `0x180015aa3`
- `USER32!SetRect` at `0x180015aa3`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x180015a3c`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x180015a3c`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015bd3`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015bd3`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180015a4e`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180015a4e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015845`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015886`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800159dc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015b0f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015b40`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015845`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015886`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800159dc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015b0f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015b40`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001583a`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001587b`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180015b04`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001583a`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001587b`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180015b04`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800158f0`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800158f0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001582e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001586f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015af8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001582e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001586f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015af8`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180015925`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180015925`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800158b9`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800158b9`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015a74`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015bf4`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015c15`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015a74`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015bf4`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180015c15`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ItemGridLayout::GetInfoForSection(
        ItemGridLayout *this,
        int a2,
        const struct SectionInfo *a3,
        struct SectionInfo *a4)
{
  struct SectionInfo *v4; // r14
  DirectUI::Element *v6; // r12
  DirectUI::Value *Value; // rdi
  int Int; // ebx
  void (__fastcall *v9)(DirectUI::Element *, _QWORD, _QWORD, struct SectionInfo *); // rsi
  DirectUI::Value *v10; // rbx
  unsigned int v11; // edi
  LONG top; // r13d
  LONG left; // ebx
  LONG right; // r15d
  LONG v15; // edi
  DirectUI::Value *Unset; // rsi
  struct DirectUI::Value *v17; // rbx
  unsigned int v18; // r13d
  struct DirectUI::Value *Children; // rdi
  DirectUI::Element *v20; // rax
  unsigned int Index; // eax
  int v22; // r15d
  unsigned int i; // ebx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  char v28; // al
  DirectUI::Value *v29; // rcx
  unsigned int v30; // edi
  unsigned int v31; // r15d
  struct DirectUI::Value *v32; // rsi
  char *v33; // r12
  DirectUI::Element *v34; // r12
  const struct tagPOINT *Location; // rax
  int x; // r13d
  __int64 v37; // rbx
  DirectUI::Value *v38; // rbx
  LONG bottom; // r12d
  DirectUI::Element *Parent; // rbx
  __int64 v41; // rdi
  __int64 v42; // rbx
  struct DirectUI::Value *v43; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-61h]
  int yTop; // [rsp+3Ch] [rbp-5Dh]
  int v46; // [rsp+40h] [rbp-59h]
  DirectUI::Value *v47; // [rsp+48h] [rbp-51h] BYREF
  struct DirectUI::Value *v48; // [rsp+50h] [rbp-49h] BYREF
  LONG v49; // [rsp+58h] [rbp-41h]
  __int64 v50; // [rsp+68h] [rbp-31h]
  DirectUI::Value *v51; // [rsp+70h] [rbp-29h]
  DirectUI::Value *v52; // [rsp+78h] [rbp-21h]
  struct SectionInfo *v53; // [rsp+80h] [rbp-19h]
  ItemGridLayout *v54; // [rsp+88h] [rbp-11h]
  struct tagRECT rcDst; // [rsp+90h] [rbp-9h] BYREF
  struct tagRECT rc; // [rsp+A0h] [rbp+7h] BYREF

  v4 = a4;
  v53 = a4;
  v6 = this;
  v54 = this;
  memset_0(a4, 0, 0x58u);
  *((_DWORD *)v4 + 6) = -1;
  if ( a2 < 0 )
    return;
  Value = DirectUI::Element::GetValue(v6, ItemLayout::SectionCountProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  if ( a2 >= Int )
    return;
  v9 = *(void (__fastcall **)(DirectUI::Element *, _QWORD, _QWORD, struct SectionInfo *))(*(_QWORD *)v6 + 504LL);
  v10 = DirectUI::Element::GetValue(v6, ItemLayout::ItemCountProp, 2, 0);
  v11 = DirectUI::Value::GetInt(v10);
  DirectUI::Value::Release(v10);
  v9(v6, (unsigned int)a2, v11, v4);
  top = 0;
  left = 0;
  yTop = 0;
  right = 0;
  v15 = 0;
  v49 = 0;
  v46 = 0;
  Unset = (DirectUI::Value *)DirectUI::Value::GetUnset();
  v52 = Unset;
  v51 = Unset;
  if ( *((_DWORD *)v4 + 21) != *((_DWORD *)v4 + 20) )
  {
    v17 = 0;
    v43 = 0;
    v18 = 0;
    v44 = 0;
    v47 = 0;
    Children = (struct DirectUI::Value *)DirectUI::Element::GetChildren(v6, &v47);
    if ( Children )
    {
      v20 = (DirectUI::Element *)(*(__int64 (__fastcall **)(DirectUI::Element *, _QWORD))(*(_QWORD *)v6 + 368LL))(
                                   v6,
                                   *((unsigned int *)v4 + 20));
      if ( v20 )
      {
        Index = DirectUI::Element::GetIndex(v20);
        v18 = Index;
        v22 = Index + *((_DWORD *)v4 + 21) - *((_DWORD *)v4 + 20);
        if ( v22 <= (*(_DWORD *)Children & 0xFFFFFFF) )
        {
          for ( i = Index; i < v22; ++i )
          {
            v24 = (_QWORD *)((char *)Children + 8);
            if ( (*(_DWORD *)Children & 0x10000000) != 0 )
              v24 = (_QWORD *)*v24;
            v25 = v24[i];
            v50 = v25;
            v26 = 0;
            *(_QWORD *)&rcDst.left = 0;
            if ( v25 )
            {
              v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 280LL))(v25);
              v28 = (*(__int64 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v27 + 80LL))(
                      v27,
                      UIBase::Class);
              v26 = *(_QWORD *)&rcDst.left;
              if ( v28 )
                v26 = v50;
            }
            if ( *(_DWORD *)(v26 + 200) != i + *((_DWORD *)v4 + 20) - v18 )
            {
              v17 = v43;
              v18 = (unsigned int)v43;
              goto LABEL_17;
            }
          }
          v17 = Children;
          v43 = Children;
          v44 = v18;
          Unset = v47;
          v52 = v47;
          v29 = 0;
          v47 = 0;
          v51 = v52;
          goto LABEL_18;
        }
        v18 = v44;
      }
    }
LABEL_17:
    v29 = v47;
LABEL_18:
    if ( v29 )
    {
      v47 = 0;
      DirectUI::Value::Release(v29);
    }
    if ( v17 )
    {
      rcDst = 0;
      v30 = *((_DWORD *)v4 + 21) - *((_DWORD *)v4 + 20);
      v46 = v30;
      v31 = 0;
      if ( v30 )
      {
        v32 = v43;
        do
        {
          if ( (*(_DWORD *)v32 & 0x10000000) != 0 )
            v33 = (char *)*((_QWORD *)v32 + 1);
          else
            v33 = (char *)v32 + 8;
          v34 = *(DirectUI::Element **)&v33[8 * v31 + 8 * v18];
          rc = 0;
          v48 = 0;
          Location = DirectUI::Element::GetLocation(v34, &v48);
          yTop = Location->y;
          x = Location->x;
          if ( DirectUI::Element::IsRTL(v34) )
          {
            Parent = DirectUI::Element::GetParent(v34);
            if ( Parent )
            {
              v43 = 0;
              v41 = (__int64)*DirectUI::Element::GetExtent(v34, &v43);
              CValuePtr::~CValuePtr((CValuePtr *)&v43);
              v43 = 0;
              v42 = (__int64)*DirectUI::Element::GetExtent(Parent, &v43);
              CValuePtr::~CValuePtr((CValuePtr *)&v43);
              x = v42 - x - v41;
              v30 = v46;
            }
          }
          CValuePtr::~CValuePtr((CValuePtr *)&v48);
          v43 = 0;
          v37 = (__int64)*DirectUI::Element::GetExtent(v34, &v43);
          v50 = v37;
          CValuePtr::~CValuePtr((CValuePtr *)&v43);
          SetRect(&rc, x, yTop, v37 + x, yTop + HIDWORD(v50));
          if ( v31 )
            UnionRect(&rcDst, &rcDst, &rc);
          else
            rcDst = rc;
          ++v31;
          v18 = v44;
        }
        while ( v31 < v30 );
        Unset = v52;
        v4 = v53;
        v6 = v54;
      }
      v46 = 1;
      v38 = DirectUI::Element::GetValue(v6, ItemLayout::VirtualDirectionProp, 2, 0);
      v15 = DirectUI::Value::GetInt(v38);
      DirectUI::Value::Release(v38);
      right = rcDst.right;
      left = rcDst.left;
      top = rcDst.top;
      if ( v15 != 1 )
      {
        top = rcDst.left;
        left = rcDst.top;
      }
      bottom = rcDst.bottom;
      if ( v15 != 1 )
      {
        bottom = rcDst.right;
        right = rcDst.bottom;
      }
    }
    else
    {
      v15 = v49;
      left = v49;
      right = v49;
      top = v49;
      bottom = v49;
    }
    goto LABEL_34;
  }
  bottom = yTop;
LABEL_34:
  if ( Unset )
    DirectUI::Value::Release(Unset);
  if ( v46 )
  {
    *((_DWORD *)v4 + 8) = 1;
    *((_DWORD *)v4 + 9) = top;
    *((_DWORD *)v4 + 10) = left;
    *((_DWORD *)v4 + 11) = bottom;
    *((_DWORD *)v4 + 12) = right;
    *((_DWORD *)v4 + 13) = v15;
  }
}

```

## disassembly

```asm
0x1800157c0  mov     [rsp-8+arg_10], rbx
0x1800157c5  push    rbp
0x1800157c6  push    rsi
0x1800157c7  push    rdi
0x1800157c8  push    r12
0x1800157ca  push    r13
0x1800157cc  push    r14
0x1800157ce  push    r15
0x1800157d0  lea     rbp, [rsp-27h]
0x1800157d5  sub     rsp, 0C0h
0x1800157dc  mov     rax, cs:__security_cookie
0x1800157e3  xor     rax, rsp
0x1800157e6  mov     [rbp+57h+var_40], rax
0x1800157ea  mov     r14, r9
0x1800157ed  mov     [rbp+57h+var_70], r9
0x1800157f1  mov     r15d, edx
0x1800157f4  mov     r12, rcx
0x1800157f7  mov     [rbp+57h+var_68], rcx
0x1800157fb  xor     edx, edx; Val
0x1800157fd  lea     r8d, [rdx+58h]; Size
0x180015801  mov     rcx, r9; void *
0x180015804  call    memset_0
0x180015809  mov     dword ptr [r14+18h], 0FFFFFFFFh
0x180015811  test    r15d, r15d
0x180015814  js      loc_180015B69
0x18001581a  xor     r9d, r9d
0x18001581d  lea     r13d, [r9+2]
0x180015821  mov     r8d, r13d
0x180015824  lea     rdx, ?SectionCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::SectionCountProp(void)
0x18001582b  mov     rcx, r12
0x18001582e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180015834  mov     rdi, rax
0x180015837  mov     rcx, rax
0x18001583a  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180015840  mov     ebx, eax
0x180015842  mov     rcx, rdi
0x180015845  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001584b  cmp     r15d, ebx
0x18001584e  jge     loc_180015B69
0x180015854  mov     rax, [r12]
0x180015858  mov     rsi, [rax+1F8h]
0x18001585f  xor     r9d, r9d
0x180015862  mov     r8d, r13d
0x180015865  lea     rdx, ?ItemCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ItemCountProp(void)
0x18001586c  mov     rcx, r12
0x18001586f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180015875  mov     rbx, rax
0x180015878  mov     rcx, rax
0x18001587b  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180015881  mov     edi, eax
0x180015883  mov     rcx, rbx
0x180015886  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001588c  mov     r9, r14
0x18001588f  mov     r8d, edi
0x180015892  mov     edx, r15d
0x180015895  mov     rcx, r12
0x180015898  mov     rax, rsi
0x18001589b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a0  xor     eax, eax
0x1800158a2  mov     r13d, eax
0x1800158a5  mov     ebx, eax
0x1800158a7  mov     [rbp+57h+yTop], eax
0x1800158aa  mov     r15d, eax
0x1800158ad  mov     edi, eax
0x1800158af  mov     [rbp+57h+var_98], eax
0x1800158b2  mov     [rbp+57h+var_B0], eax
0x1800158b5  mov     [rbp+57h+var_80], rax
0x1800158b9  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800158bf  mov     rsi, rax
0x1800158c2  mov     [rbp+57h+var_78], rax
0x1800158c6  mov     [rbp+57h+var_80], rax
0x1800158ca  mov     eax, [r14+54h]
0x1800158ce  cmp     eax, [r14+50h]
0x1800158d2  jz      loc_180015C4A
0x1800158d8  xor     ebx, ebx
0x1800158da  mov     [rbp+57h+var_C0], rbx
0x1800158de  xor     r13d, r13d
0x1800158e1  mov     [rbp+57h+var_B8], r13d
0x1800158e5  mov     [rbp+57h+var_A8], rbx
0x1800158e9  lea     rdx, [rbp+57h+var_A8]
0x1800158ed  mov     rcx, r12
0x1800158f0  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800158f6  mov     rdi, rax
0x1800158f9  test    rax, rax
0x1800158fc  jz      loc_1800159CB
0x180015902  mov     rcx, [r12]
0x180015906  mov     rax, [rcx+170h]
0x18001590d  mov     edx, [r14+50h]
0x180015911  mov     rcx, r12
0x180015914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015919  test    rax, rax
0x18001591c  jz      loc_1800159CB
0x180015922  mov     rcx, rax
0x180015925  call    cs:__imp_?GetIndex@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetIndex(void)
0x18001592b  mov     r13d, eax
0x18001592e  mov     r15d, [r14+54h]
0x180015932  sub     r15d, [r14+50h]
0x180015936  add     r15d, eax
0x180015939  mov     ecx, [rdi]
0x18001593b  and     ecx, 0FFFFFFFh
0x180015941  cmp     r15d, ecx
0x180015944  jg      loc_180015C41
0x18001594a  mov     ebx, eax
0x18001594c  cmp     ebx, r15d
0x18001594f  jnb     loc_180015BAE
0x180015955  lea     rcx, [rdi+8]
0x180015959  test    dword ptr [rdi], 10000000h
0x18001595f  jz      short loc_180015964
0x180015961  mov     rcx, [rcx]
0x180015964  mov     eax, ebx
0x180015966  mov     rdx, [rcx+rax*8]
0x18001596a  mov     [rbp+57h+var_88], rdx
0x18001596e  xor     ecx, ecx
0x180015970  mov     qword ptr [rbp+57h+rcDst.left], rcx
0x180015974  test    rdx, rdx
0x180015977  jz      short loc_1800159AF
0x180015979  mov     rax, [rdx]
0x18001597c  mov     rcx, rdx
0x18001597f  mov     rax, [rax+118h]
0x180015986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598b  mov     r8, rax
0x18001598e  mov     rcx, [rax]
0x180015991  mov     rax, [rcx+50h]
0x180015995  mov     rdx, cs:?Class@UIBase@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIBase::Class
0x18001599c  mov     rcx, r8
0x18001599f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a4  mov     rcx, qword ptr [rbp+57h+rcDst.left]
0x1800159a8  test    al, al
0x1800159aa  cmovnz  rcx, [rbp+57h+var_88]
0x1800159af  mov     eax, [r14+50h]
0x1800159b3  sub     eax, r13d
0x1800159b6  add     eax, ebx
0x1800159b8  cmp     [rcx+0C8h], eax
0x1800159be  jnz     short loc_1800159C4
0x1800159c0  inc     ebx
0x1800159c2  jmp     short loc_18001594C
0x1800159c4  mov     rbx, [rbp+57h+var_C0]
0x1800159c8  mov     r13d, ebx
0x1800159cb  mov     rcx, [rbp+57h+var_A8]
0x1800159cf  test    rcx, rcx
0x1800159d2  jz      short loc_1800159E3
0x1800159d4  mov     [rbp+57h+var_A8], 0
0x1800159dc  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800159e2  nop
0x1800159e3  test    rbx, rbx
0x1800159e6  jz      loc_180015B9E
0x1800159ec  xorps   xmm0, xmm0
0x1800159ef  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800159f3  mov     edi, [r14+54h]
0x1800159f7  sub     edi, [r14+50h]
0x1800159fb  mov     [rbp+57h+var_B0], edi
0x1800159fe  mov     r15d, 0
0x180015a04  jz      loc_180015AE0
0x180015a0a  mov     rsi, [rbp+57h+var_C0]
0x180015a0e  test    dword ptr [rsi], 10000000h
0x180015a14  jz      loc_180015C38
0x180015a1a  mov     r12, [rsi+8]
0x180015a1e  lea     eax, [r15+r13]
0x180015a22  mov     r12, [r12+rax*8]
0x180015a26  xorps   xmm0, xmm0
0x180015a29  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180015a2d  mov     [rbp+57h+var_A0], 0
0x180015a35  lea     rdx, [rbp+57h+var_A0]
0x180015a39  mov     rcx, r12
0x180015a3c  call    cs:__imp_?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetLocation(DirectUI::Value * *)
0x180015a42  mov     ecx, [rax+4]
0x180015a45  mov     [rbp+57h+yTop], ecx
0x180015a48  mov     r13d, [rax]
0x180015a4b  mov     rcx, r12
0x180015a4e  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x180015a54  test    al, al
0x180015a56  jnz     loc_180015BD0
0x180015a5c  lea     rcx, [rbp+57h+var_A0]; this
0x180015a60  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015a65  mov     [rbp+57h+var_C0], 0
0x180015a6d  lea     rdx, [rbp+57h+var_C0]
0x180015a71  mov     rcx, r12
0x180015a74  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180015a7a  mov     rbx, [rax]
0x180015a7d  mov     [rbp+57h+var_88], rbx
0x180015a81  lea     rcx, [rbp+57h+var_C0]; this
0x180015a85  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015a8a  mov     ecx, dword ptr [rbp+57h+var_88+4]
0x180015a8d  mov     r8d, [rbp+57h+yTop]; yTop
0x180015a91  add     ecx, r8d
0x180015a94  lea     r9d, [rbx+r13]; xRight
0x180015a98  mov     [rsp+0F0h+yBottom], ecx; yBottom
0x180015a9c  mov     edx, r13d; xLeft
0x180015a9f  lea     rcx, [rbp+57h+rc]; lprc
0x180015aa3  call    cs:__imp_SetRect
0x180015aa9  test    r15d, r15d
0x180015aac  jz      loc_180015B90
0x180015ab2  lea     r8, [rbp+57h+rc]; lprcSrc2
0x180015ab6  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x180015aba  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180015abe  call    cs:__imp_UnionRect
0x180015ac4  inc     r15d
0x180015ac7  cmp     r15d, edi
0x180015aca  mov     r13d, [rbp+57h+var_B8]
0x180015ace  jb      loc_180015A0E
0x180015ad4  mov     rsi, [rbp+57h+var_78]
0x180015ad8  mov     r14, [rbp+57h+var_70]
0x180015adc  mov     r12, [rbp+57h+var_68]
0x180015ae0  mov     [rbp+57h+var_B0], 1
0x180015ae7  xor     r9d, r9d
0x180015aea  lea     r8d, [r9+2]
0x180015aee  lea     rdx, ?VirtualDirectionProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::VirtualDirectionProp(void)
0x180015af5  mov     rcx, r12
0x180015af8  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180015afe  mov     rbx, rax
0x180015b01  mov     rcx, rax
0x180015b04  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180015b0a  mov     edi, eax
0x180015b0c  mov     rcx, rbx
0x180015b0f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180015b15  mov     r15d, [rbp+57h+rcDst.right]
0x180015b19  mov     ebx, [rbp+57h+rcDst.left]
0x180015b1c  mov     r13d, [rbp+57h+rcDst.top]
0x180015b20  cmp     edi, 1
0x180015b23  cmovnz  r13d, ebx
0x180015b27  cmovnz  ebx, [rbp+57h+rcDst.top]
0x180015b2b  mov     r12d, [rbp+57h+rcDst.bottom]
0x180015b2f  cmovnz  r12d, r15d
0x180015b33  cmovnz  r15d, [rbp+57h+rcDst.bottom]
0x180015b38  test    rsi, rsi
0x180015b3b  jz      short loc_180015B47
0x180015b3d  mov     rcx, rsi
0x180015b40  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180015b46  nop
0x180015b47  cmp     [rbp+57h+var_B0], 0
0x180015b4b  jz      short loc_180015B69
0x180015b4d  mov     dword ptr [r14+20h], 1
0x180015b55  mov     [r14+24h], r13d
0x180015b59  mov     [r14+28h], ebx
0x180015b5d  mov     [r14+2Ch], r12d
0x180015b61  mov     [r14+30h], r15d
0x180015b65  mov     [r14+34h], edi
0x180015b69  mov     rcx, [rbp+57h+var_40]
0x180015b6d  xor     rcx, rsp; StackCookie
0x180015b70  call    __security_check_cookie
0x180015b75  mov     rbx, [rsp+0F0h+arg_10]
0x180015b7d  add     rsp, 0C0h
0x180015b84  pop     r15
0x180015b86  pop     r14
0x180015b88  pop     r13
0x180015b8a  pop     r12
0x180015b8c  pop     rdi
0x180015b8d  pop     rsi
0x180015b8e  pop     rbp
0x180015b8f  retn
0x180015b90  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x180015b94  movdqa  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180015b99  jmp     loc_180015AC4
0x180015b9e  mov     edi, [rbp+57h+var_98]
0x180015ba1  mov     ebx, edi
0x180015ba3  mov     r15d, edi
0x180015ba6  mov     r13d, edi
0x180015ba9  mov     r12d, edi
0x180015bac  jmp     short loc_180015B38
0x180015bae  mov     rbx, rdi
0x180015bb1  mov     [rbp+57h+var_C0], rbx
0x180015bb5  mov     [rbp+57h+var_B8], r13d
0x180015bb9  mov     rsi, [rbp+57h+var_A8]
0x180015bbd  mov     [rbp+57h+var_78], rsi
0x180015bc1  xor     ecx, ecx
0x180015bc3  mov     [rbp+57h+var_A8], rcx
0x180015bc7  mov     [rbp+57h+var_80], rsi
0x180015bcb  jmp     loc_1800159CF
0x180015bd0  mov     rcx, r12
0x180015bd3  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180015bd9  mov     rbx, rax
0x180015bdc  test    rax, rax
0x180015bdf  jz      loc_180015A5C
0x180015be5  mov     [rbp+57h+var_C0], 0
0x180015bed  lea     rdx, [rbp+57h+var_C0]
0x180015bf1  mov     rcx, r12
0x180015bf4  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180015bfa  mov     rdi, [rax]
0x180015bfd  lea     rcx, [rbp+57h+var_C0]; this
0x180015c01  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015c06  mov     [rbp+57h+var_C0], 0
0x180015c0e  lea     rdx, [rbp+57h+var_C0]
0x180015c12  mov     rcx, rbx
0x180015c15  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180015c1b  mov     rbx, [rax]
0x180015c1e  lea     rcx, [rbp+57h+var_C0]; this
0x180015c22  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015c27  sub     ebx, r13d
0x180015c2a  mov     r13d, ebx
0x180015c2d  sub     r13d, edi
0x180015c30  mov     edi, [rbp+57h+var_B0]
0x180015c33  jmp     loc_180015A5C
0x180015c38  lea     r12, [rsi+8]
0x180015c3c  jmp     loc_180015A1E
0x180015c41  mov     r13d, [rbp+57h+var_B8]
0x180015c45  jmp     loc_1800159CB
0x180015c4a  mov     r12d, [rbp+57h+yTop]
0x180015c4e  jmp     loc_180015B38
```
