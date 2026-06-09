# ItemRowLayout::_SearchForSectionInVirtualUIGroupItemList(int (*)(SectionInfo const &,unsigned __int64),unsigned __int64,SectionInfo *)

- ea: `0x180082070`
- end: `0x1800825ef`
- name: `?_SearchForSectionInVirtualUIGroupItemList@ItemRowLayout@@AEAAHP6AHAEBVSectionInfo@@_K@Z1PEAV2@@Z`
- size: `1407`
- prototype: `__int64 __fastcall(ItemRowLayout *__hidden this, int (*)(const struct SectionInfo *, unsigned __int64), unsigned __int64, struct SectionInfo *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800816e0`
- `0x180081890`
- `0x1800819e0`

## callees

- `0x180015fe0`
- `0x180016790`
- `0x180082070`
- `0x180082600`
- `0x180082650`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `USER32!SetRect` at `0x1800824d5`
- `USER32!SetRect` at `0x1800824d5`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x180082454`
- `DUI70!?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z` at `0x180082454`
- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x180082101`
- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x180082101`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800825b4`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800825b4`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180082466`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180082466`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008211d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008214e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008231e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082507`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008211d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008214e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008231e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082507`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180082143`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800824fa`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180082143`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800824fa`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180082301`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180082301`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800820f0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180082137`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800824ee`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800820f0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180082137`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800824ee`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800824a3`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800824a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ItemRowLayout::_SearchForSectionInVirtualUIGroupItemList(
        ItemRowLayout *this,
        __int64 (__fastcall *a2)(__int128 *, __int64),
        __int64 a3,
        struct SectionInfo *a4)
{
  __int64 v5; // rsi
  DirectUI::Value *Value; // rbx
  const struct tagRECT *Rect; // rax
  DirectUI::Value *v10; // rdi
  int Int; // ebx
  int SeparatorLineHeight; // r12d
  __int128 v13; // xmm6
  __int128 v14; // xmm8
  __int128 v15; // xmm9
  __m128i v16; // xmm7
  unsigned __int64 i; // rdi
  __int128 v18; // xmm11
  __int64 v19; // xmm10_8
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  __int64 Children; // rax
  _DWORD *v27; // r13
  DirectUI::Value *v28; // rcx
  unsigned int v30; // r12d
  _QWORD *v31; // rax
  _QWORD *v32; // rbx
  DirectUI::Element *v33; // rbx
  DirectUI::Element *v34; // rdi
  __int64 v35; // rax
  const struct tagPOINT *Location; // rax
  LONG x; // esi
  int v38; // eax
  int v39; // esi
  __int64 v40; // rbx
  DirectUI::Value *v41; // rbx
  LONG v42; // edi
  LONG right; // esi
  LONG top; // ebx
  LONG left; // eax
  int v46; // eax
  int v47; // eax
  LONG cx; // ebx
  int y; // [rsp+30h] [rbp-D0h]
  LONG v50; // [rsp+30h] [rbp-D0h]
  struct DirectUI::Value *v51; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h]
  int bottom; // [rsp+44h] [rbp-BCh]
  __int64 v54; // [rsp+48h] [rbp-B8h]
  DirectUI::Value *v55; // [rsp+50h] [rbp-B0h]
  DirectUI::Value *v56; // [rsp+58h] [rbp-A8h] BYREF
  int yTop[2]; // [rsp+60h] [rbp-A0h]
  struct tagRECT rc; // [rsp+68h] [rbp-98h] BYREF
  __int128 v59; // [rsp+80h] [rbp-80h] BYREF
  __int128 v60; // [rsp+90h] [rbp-70h]
  __int128 v61; // [rsp+A0h] [rbp-60h]
  __int128 v62; // [rsp+B0h] [rbp-50h]
  __m128i v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+D0h] [rbp-30h]

  v5 = a3;
  v54 = a3;
  v52 = 1;
  Value = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorPaddingProp, 2, 0);
  v55 = Value;
  Rect = DirectUI::Value::GetRect(Value);
  LODWORD(v51) = Rect->top;
  bottom = Rect->bottom;
  if ( Value )
    DirectUI::Value::Release(Value);
  v10 = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorLineHeightProp, 2, 0);
  Int = DirectUI::Value::GetInt(v10);
  DirectUI::Value::Release(v10);
  if ( Int > 0 )
    SeparatorLineHeight = ItemRowLayout::GetSeparatorLineHeight(this);
  else
    SeparatorLineHeight = 0;
  v13 = 0;
  v60 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v64 = 0;
  DWORD2(v60) = -1;
  for ( i = 0; ; ++i )
  {
    v18 = v60;
    v19 = v64;
    if ( i >= *((_QWORD *)this + 28) )
      break;
    v20 = *(_QWORD *)(*((_QWORD *)this + 27) + 8 * i);
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    DWORD2(v60) = i;
    DWORD2(v59) = 3;
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 184LL))(v20);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
    v63.m128i_i32[0] = _mm_cvtsi128_si32(_mm_srli_si128(v16, 4));
    v63.m128i_i32[1] = v63.m128i_i32[0] + v22;
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 184LL))(v20);
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 56LL))(v23);
    v63.m128i_i32[2] = _mm_cvtsi128_si32(_mm_srli_si128(v16, 12));
    v63.m128i_i32[3] = v63.m128i_i32[2] + v24;
    LODWORD(v64) = i;
    HIDWORD(v64) = i + 1;
    *(_QWORD *)&v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 184LL))(v20);
    v25 = a2(&v59, v5);
    v52 = v25;
    if ( !v25 )
    {
      *(_OWORD *)a4 = v59;
      *((_OWORD *)a4 + 1) = v60;
      *((_OWORD *)a4 + 2) = v61;
      *((_OWORD *)a4 + 3) = v62;
      *((__m128i *)a4 + 4) = v63;
      *((_QWORD *)a4 + 10) = v64;
      goto LABEL_13;
    }
    if ( v25 < 0 )
    {
      v52 = 1;
      break;
    }
    v13 = v59;
    v14 = v61;
    v15 = v62;
    v16 = v63;
    v5 = v54;
  }
  *(_OWORD *)a4 = v13;
  *((_OWORD *)a4 + 1) = v18;
  *((_OWORD *)a4 + 2) = v14;
  *((_OWORD *)a4 + 3) = v15;
  *((__m128i *)a4 + 4) = v16;
  *((_QWORD *)a4 + 10) = v19;
LABEL_13:
  v56 = 0;
  Children = DirectUI::Element::GetChildren(this, &v56);
  v27 = (_DWORD *)Children;
  if ( Children )
  {
    LODWORD(v54) = (_DWORD)v51 + (SeparatorLineHeight + 1) / 2;
    bottom += SeparatorLineHeight / 2;
    LODWORD(v55) = (*(__int64 (__fastcall **)(ItemRowLayout *, __int64))(*(_QWORD *)this + 536LL))(this, Children);
    v30 = 0;
    if ( (_DWORD)v55 )
    {
      v31 = v27 + 2;
      do
      {
        if ( (*v27 & 0x10000000) != 0 )
          v32 = (_QWORD *)*v31;
        else
          v32 = v31;
        v33 = (DirectUI::Element *)v32[v30];
        v34 = 0;
        if ( v33 )
        {
          v35 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v33 + 280LL))(v33);
          if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v35 + 80LL))(
                 v35,
                 UIBase::Class) )
          {
            v34 = v33;
          }
        }
        if ( *((_DWORD *)v34 + 50) == *((_DWORD *)a4 + 6) )
        {
          *((_QWORD *)a4 + 2) = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v34 + 424LL))(v34);
          *((_QWORD *)a4 + 7) = v34;
          rc = 0;
          v51 = 0;
          Location = DirectUI::Element::GetLocation(v34, &v51);
          y = Location->y;
          x = Location->x;
          if ( DirectUI::Element::IsRTL(v34) && (*(_QWORD *)yTop = DirectUI::Element::GetParent(v34)) != 0 )
          {
            cx = DUI_GetElementExtent(v34).cx;
            v38 = DUI_GetElementExtent(*(struct DirectUI::Element **)yTop).cx - cx - x;
          }
          else
          {
            v38 = x;
          }
          v39 = v38;
          yTop[0] = v38;
          yTop[1] = y;
          CValuePtr::~CValuePtr((CValuePtr *)&v51);
          v51 = 0;
          v40 = (__int64)*DirectUI::Element::GetExtent(v34, &v51);
          CValuePtr::~CValuePtr((CValuePtr *)&v51);
          SetRect(&rc, v39, yTop[1], v40 + v39, y + HIDWORD(v40));
          v41 = DirectUI::Element::GetValue(this, ItemLayout::VirtualDirectionProp, 2, 0);
          LODWORD(v51) = DirectUI::Value::GetInt(v41);
          DirectUI::Value::Release(v41);
          v42 = rc.bottom;
          right = rc.right;
          top = rc.top;
          left = rc.left;
          v50 = rc.left;
          if ( (_DWORD)v51 == 1 )
          {
            v42 = rc.right;
            right = rc.bottom;
            top = rc.left;
            left = rc.top;
            v50 = rc.top;
          }
          if ( (_DWORD)v54 || bottom )
          {
            if ( *((_DWORD *)a4 + 6) )
            {
              v46 = 0;
              if ( bottom >= 0 )
                v46 = bottom;
              top -= v46;
            }
            if ( *((_DWORD *)a4 + 6) != (unsigned int)ItemLayout::GetSectionCount(this) - 1 )
            {
              v47 = 0;
              if ( (int)v54 >= 0 )
                v47 = v54;
              v42 += v47;
            }
            left = v50;
          }
          *((_DWORD *)a4 + 8) = 1;
          *((_DWORD *)a4 + 9) = left;
          *((_DWORD *)a4 + 10) = top;
          *((_DWORD *)a4 + 11) = right;
          *((_DWORD *)a4 + 12) = v42;
          *((_DWORD *)a4 + 13) = (_DWORD)v51;
        }
        ++v30;
        v31 = v27 + 2;
      }
      while ( v30 < (unsigned int)v55 );
    }
  }
  v28 = v56;
  if ( v56 )
  {
    v56 = 0;
    DirectUI::Value::Release(v28);
  }
  return v52;
}

```

## disassembly

```asm
0x180082070  mov     rax, rsp
0x180082073  push    rbp
0x180082074  push    rbx
0x180082075  push    rsi
0x180082076  push    rdi
0x180082077  push    r12
0x180082079  push    r13
0x18008207b  push    r14
0x18008207d  push    r15
0x18008207f  lea     rbp, [rsp-58h]
0x180082084  sub     rsp, 158h
0x18008208b  movaps  xmmword ptr [rax-58h], xmm6
0x18008208f  movaps  xmmword ptr [rax-68h], xmm7
0x180082093  movaps  xmmword ptr [rax-78h], xmm8
0x180082098  movaps  xmmword ptr [rax-88h], xmm9
0x1800820a0  movaps  xmmword ptr [rax-98h], xmm10
0x1800820a8  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800820b0  mov     rax, cs:__security_cookie
0x1800820b7  xor     rax, rsp
0x1800820ba  mov     [rbp+90h+var_B0], rax
0x1800820be  mov     r15, r9
0x1800820c1  mov     rsi, r8
0x1800820c4  mov     [rsp+190h+var_148], r8
0x1800820c9  mov     r13, rdx
0x1800820cc  mov     r14, rcx
0x1800820cf  mov     [rsp+190h+var_150], 1
0x1800820d7  mov     [rsp+190h+var_140], 0
0x1800820e0  xor     r9d, r9d
0x1800820e3  mov     r8d, 2
0x1800820e9  lea     rdx, ?SeparatorPaddingProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorPaddingProp(void)
0x1800820f0  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800820f6  mov     rbx, rax
0x1800820f9  mov     [rsp+190h+var_140], rax
0x1800820fe  mov     rcx, rax
0x180082101  call    cs:__imp_?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ; DirectUI::Value::GetRect(void)
0x180082107  mov     ecx, [rax+4]
0x18008210a  mov     dword ptr [rsp+190h+var_158], ecx
0x18008210e  mov     eax, [rax+0Ch]
0x180082111  mov     [rsp+190h+var_14C], eax
0x180082115  test    rbx, rbx
0x180082118  jz      short loc_180082124
0x18008211a  mov     rcx, rbx
0x18008211d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082123  nop
0x180082124  xor     r9d, r9d
0x180082127  mov     r8d, 2
0x18008212d  lea     rdx, ?SeparatorLineHeightProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorLineHeightProp(void)
0x180082134  mov     rcx, r14
0x180082137  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18008213d  mov     rdi, rax
0x180082140  mov     rcx, rax
0x180082143  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180082149  mov     ebx, eax
0x18008214b  mov     rcx, rdi
0x18008214e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082154  test    ebx, ebx
0x180082156  jg      loc_1800825A1
0x18008215c  xor     r12d, r12d
0x18008215f  xorps   xmm6, xmm6
0x180082162  xor     eax, eax
0x180082164  movups  [rbp+90h+var_100], xmm6
0x180082168  xorps   xmm8, xmm8
0x18008216c  xorps   xmm9, xmm9
0x180082170  xorps   xmm7, xmm7
0x180082173  mov     [rbp+90h+var_C0], rax
0x180082177  mov     dword ptr [rbp+90h+var_100+8], 0FFFFFFFFh
0x18008217e  xor     edi, edi
0x180082180  movaps  xmm11, [rbp+90h+var_100]
0x180082185  movsd   xmm10, [rbp+90h+var_C0]
0x18008218b  cmp     rdi, [r14+0E0h]
0x180082192  jnb     loc_1800822D4
0x180082198  mov     rax, [r14+0D8h]
0x18008219f  mov     rbx, [rax+rdi*8]
0x1800821a3  xorps   xmm0, xmm0
0x1800821a6  xor     eax, eax
0x1800821a8  movups  [rbp+90h+var_110], xmm0
0x1800821ac  movups  [rbp+90h+var_100], xmm0
0x1800821b0  movups  [rbp+90h+var_F0], xmm0
0x1800821b4  movups  [rbp+90h+var_E0], xmm0
0x1800821b8  movups  [rbp+90h+var_D0], xmm0
0x1800821bc  mov     [rbp+90h+var_C0], rax
0x1800821c0  mov     dword ptr [rbp+90h+var_100+8], edi
0x1800821c3  mov     dword ptr [rbp+90h+var_110+8], 3
0x1800821ca  mov     rax, [rbx]
0x1800821cd  mov     rcx, rbx
0x1800821d0  mov     rax, [rax+0B8h]
0x1800821d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800821dc  mov     rdx, rax
0x1800821df  mov     rcx, [rax]
0x1800821e2  mov     rax, [rcx+30h]
0x1800821e6  mov     rcx, rdx
0x1800821e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800821ee  movdqa  xmm0, xmm7
0x1800821f2  psrldq  xmm0, 4
0x1800821f7  movd    ecx, xmm0
0x1800821fb  mov     dword ptr [rbp+90h+var_D0], ecx
0x1800821fe  add     eax, ecx
0x180082200  mov     dword ptr [rbp+90h+var_D0+4], eax
0x180082203  mov     rax, [rbx]
0x180082206  mov     rcx, rbx
0x180082209  mov     rax, [rax+0B8h]
0x180082210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082215  mov     rdx, rax
0x180082218  mov     rcx, [rax]
0x18008221b  mov     rax, [rcx+38h]
0x18008221f  mov     rcx, rdx
0x180082222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082227  movdqa  xmm0, xmm7
0x18008222b  psrldq  xmm0, 0Ch
0x180082230  movd    edx, xmm0
0x180082234  mov     dword ptr [rbp+90h+var_D0+8], edx
0x180082237  add     eax, edx
0x180082239  mov     dword ptr [rbp+90h+var_D0+0Ch], eax
0x18008223c  mov     dword ptr [rbp+90h+var_C0], edi
0x18008223f  lea     eax, [rdi+1]
0x180082242  mov     dword ptr [rbp+90h+var_C0+4], eax
0x180082245  mov     rax, [rbx]
0x180082248  mov     rcx, rbx
0x18008224b  mov     rax, [rax+0B8h]
0x180082252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082257  mov     qword ptr [rbp+90h+var_100], rax
0x18008225b  mov     rdx, rsi
0x18008225e  lea     rcx, [rbp+90h+var_110]
0x180082262  mov     rax, r13
0x180082265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008226a  mov     [rsp+190h+var_150], eax
0x18008226e  test    eax, eax
0x180082270  jz      short loc_180082293
0x180082272  js      short loc_1800822CC
0x180082274  movaps  xmm6, [rbp+90h+var_110]
0x180082278  movaps  xmm8, [rbp+90h+var_F0]
0x18008227d  movaps  xmm9, [rbp+90h+var_E0]
0x180082282  movaps  xmm7, [rbp+90h+var_D0]
0x180082286  inc     rdi
0x180082289  mov     rsi, [rsp+190h+var_148]
0x18008228e  jmp     loc_180082180
0x180082293  movaps  xmm0, [rbp+90h+var_110]
0x180082297  movaps  xmmword ptr [r15], xmm0
0x18008229b  movaps  xmm1, [rbp+90h+var_100]
0x18008229f  movaps  xmmword ptr [r15+10h], xmm1
0x1800822a4  movaps  xmm0, [rbp+90h+var_F0]
0x1800822a8  movaps  xmmword ptr [r15+20h], xmm0
0x1800822ad  movaps  xmm1, [rbp+90h+var_E0]
0x1800822b1  movaps  xmmword ptr [r15+30h], xmm1
0x1800822b6  movaps  xmm0, [rbp+90h+var_D0]
0x1800822ba  movaps  xmmword ptr [r15+40h], xmm0
0x1800822bf  movsd   xmm1, [rbp+90h+var_C0]
0x1800822c4  movsd   qword ptr [r15+50h], xmm1
0x1800822ca  jmp     short loc_1800822F2
0x1800822cc  mov     [rsp+190h+var_150], 1
0x1800822d4  movaps  xmmword ptr [r15], xmm6
0x1800822d8  movaps  xmmword ptr [r15+10h], xmm11
0x1800822dd  movaps  xmmword ptr [r15+20h], xmm8
0x1800822e2  movaps  xmmword ptr [r15+30h], xmm9
0x1800822e7  movaps  xmmword ptr [r15+40h], xmm7
0x1800822ec  movsd   qword ptr [r15+50h], xmm10
0x1800822f2  xor     esi, esi
0x1800822f4  mov     [rsp+190h+var_138], rsi
0x1800822f9  lea     rdx, [rsp+190h+var_138]
0x1800822fe  mov     rcx, r14
0x180082301  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180082307  mov     r13, rax
0x18008230a  test    rax, rax
0x18008230d  jnz     short loc_18008236B
0x18008230f  mov     rcx, [rsp+190h+var_138]
0x180082314  test    rcx, rcx
0x180082317  jz      short loc_180082325
0x180082319  mov     [rsp+190h+var_138], rsi
0x18008231e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082324  nop
0x180082325  mov     eax, [rsp+190h+var_150]
0x180082329  mov     rcx, [rbp+90h+var_B0]
0x18008232d  xor     rcx, rsp; StackCookie
0x180082330  call    __security_check_cookie
0x180082335  lea     r11, [rsp+190h+var_38]
0x18008233d  movaps  xmm6, xmmword ptr [r11-18h]
0x180082342  movaps  xmm7, xmmword ptr [r11-28h]
0x180082347  movaps  xmm8, xmmword ptr [r11-38h]
0x18008234c  movaps  xmm9, xmmword ptr [r11-48h]
0x180082351  movaps  xmm10, xmmword ptr [r11-58h]
0x180082356  movaps  xmm11, xmmword ptr [r11-68h]
0x18008235b  mov     rsp, r11
0x18008235e  pop     r15
0x180082360  pop     r14
0x180082362  pop     r13
0x180082364  pop     r12
0x180082366  pop     rdi
0x180082367  pop     rsi
0x180082368  pop     rbx
0x180082369  pop     rbp
0x18008236a  retn
0x18008236b  lea     eax, [r12+1]
0x180082370  cdq
0x180082371  sub     eax, edx
0x180082373  sar     eax, 1
0x180082375  add     eax, dword ptr [rsp+190h+var_158]
0x180082379  mov     dword ptr [rsp+190h+var_148], eax
0x18008237d  mov     eax, r12d
0x180082380  cdq
0x180082381  sub     eax, edx
0x180082383  sar     eax, 1
0x180082385  add     eax, [rsp+190h+var_14C]
0x180082389  mov     [rsp+190h+var_14C], eax
0x18008238d  mov     rax, [r14]
0x180082390  mov     rdx, r13
0x180082393  mov     rcx, r14
0x180082396  mov     rax, [rax+218h]
0x18008239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800823a2  mov     dword ptr [rsp+190h+var_140], eax
0x1800823a6  mov     r12d, esi
0x1800823a9  test    eax, eax
0x1800823ab  jz      loc_18008230F
0x1800823b1  lea     rax, [r13+8]
0x1800823b5  test    dword ptr [r13+0], 10000000h
0x1800823bd  jz      loc_1800825E6
0x1800823c3  mov     rbx, [rax]
0x1800823c6  mov     eax, r12d
0x1800823c9  mov     rbx, [rbx+rax*8]
0x1800823cd  mov     rdi, rsi
0x1800823d0  test    rbx, rbx
0x1800823d3  jz      short loc_180082406
0x1800823d5  mov     rax, [rbx]
0x1800823d8  mov     rcx, rbx
0x1800823db  mov     rax, [rax+118h]
0x1800823e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800823e7  mov     r8, rax
0x1800823ea  mov     rcx, [rax]
0x1800823ed  mov     rax, [rcx+50h]
0x1800823f1  mov     rdx, cs:?Class@UIBase@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIBase::Class
0x1800823f8  mov     rcx, r8
0x1800823fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082400  test    al, al
0x180082402  cmovnz  rdi, rbx
0x180082406  mov     eax, [r15+18h]
0x18008240a  cmp     [rdi+0C8h], eax
0x180082410  jz      short loc_180082425
0x180082412  inc     r12d
0x180082415  cmp     r12d, dword ptr [rsp+190h+var_140]
0x18008241a  lea     rax, [r13+8]
0x18008241e  jb      short loc_1800823B5
0x180082420  jmp     loc_18008230F
0x180082425  mov     rax, [rdi]
0x180082428  mov     rcx, rdi
0x18008242b  mov     rax, [rax+1A8h]
0x180082432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082437  mov     [r15+10h], rax
0x18008243b  mov     [r15+38h], rdi
0x18008243f  xorps   xmm0, xmm0
0x180082442  movups  xmmword ptr [rsp+190h+rc.left], xmm0
0x180082447  mov     [rsp+190h+var_158], rsi
0x18008244c  lea     rdx, [rsp+190h+var_158]
0x180082451  mov     rcx, rdi
0x180082454  call    cs:__imp_?GetLocation@Element@DirectUI@@QEAAPEBUtagPOINT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetLocation(DirectUI::Value * *)
0x18008245a  mov     ecx, [rax+4]
0x18008245d  mov     [rsp+190h+var_160], ecx
0x180082461  mov     esi, [rax]
0x180082463  mov     rcx, rdi
0x180082466  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18008246c  test    al, al
0x18008246e  jnz     loc_1800825B1
0x180082474  mov     eax, esi
0x180082476  mov     esi, [rsp+190h+var_160]
0x18008247a  shl     rsi, 20h
0x18008247e  mov     ecx, eax
0x180082480  or      rsi, rcx
0x180082483  mov     qword ptr [rsp+190h+yTop], rsi
0x180082488  lea     rcx, [rsp+190h+var_158]; this
0x18008248d  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180082492  mov     [rsp+190h+var_158], 0
0x18008249b  lea     rdx, [rsp+190h+var_158]
0x1800824a0  mov     rcx, rdi
0x1800824a3  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x1800824a9  mov     rbx, [rax]
0x1800824ac  lea     rcx, [rsp+190h+var_158]; this
0x1800824b1  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800824b6  mov     rax, rbx
0x1800824b9  shr     rax, 20h
0x1800824bd  add     eax, [rsp+190h+var_160]
0x1800824c1  lea     r9d, [rbx+rsi]; xRight
0x1800824c5  mov     [rsp+190h+yBottom], eax; yBottom
0x1800824c9  mov     r8d, [rsp+190h+yTop+4]; yTop
0x1800824ce  mov     edx, esi; xLeft
0x1800824d0  lea     rcx, [rsp+190h+rc]; lprc
0x1800824d5  call    cs:__imp_SetRect
0x1800824db  xor     r9d, r9d
0x1800824de  mov     r8d, 2
0x1800824e4  lea     rdx, ?VirtualDirectionProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::VirtualDirectionProp(void)
0x1800824eb  mov     rcx, r14
0x1800824ee  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800824f4  mov     rbx, rax
0x1800824f7  mov     rcx, rax
0x1800824fa  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180082500  mov     dword ptr [rsp+190h+var_158], eax
0x180082504  mov     rcx, rbx
0x180082507  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18008250d  mov     edi, [rsp+190h+rc.bottom]
0x180082511  mov     esi, [rsp+190h+rc.right]
0x180082515  mov     ebx, [rsp+190h+rc.top]
0x180082519  mov     eax, [rsp+190h+rc.left]
0x18008251d  mov     [rsp+190h+var_160], eax
  ... truncated ...
```
