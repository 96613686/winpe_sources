# ItemRowLayout::_SelfLayoutDoLayout(int,int)

- ea: `0x180081400`
- end: `0x1800816d1`
- name: `?_SelfLayoutDoLayout@ItemRowLayout@@UEAAXHH@Z`
- size: `721`
- prototype: `void __fastcall(ItemRowLayout *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180081320`
- `0x180081400`
- `0x180082600`
- `0x180210010`

## import_xrefs

- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x1800814c4`
- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x1800814c4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008145a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800814d8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180081585`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180081662`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008145a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800814d8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180081585`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180081662`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x180081579`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x180081579`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180081657`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180081657`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180081439`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180081439`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800814b3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008156d`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008164b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800814b3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008156d`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008164b`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18008153f`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18008153f`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800815ee`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800815ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ItemRowLayout::_SelfLayoutDoLayout(ItemRowLayout *this, int a2, int a3)
{
  _DWORD *Children; // r12
  DirectUI::Value *v7; // rcx
  int v8; // eax
  DirectUI::Value *Value; // rbx
  const struct tagRECT *Rect; // rax
  LONG top; // esi
  LONG bottom; // edi
  int SeparatorLineHeight; // ecx
  int v14; // r13d
  int v15; // r14d
  unsigned int v16; // r15d
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  const struct tagSIZE *DesiredSize; // rax
  LONG cy; // esi
  LONG cx; // ecx
  DirectUI::Value *v22; // rbx
  bool Bool; // di
  LONG v24; // r8d
  LONG v25; // r9d
  int v26; // edx
  int v27; // ecx
  DirectUI::Element *v28; // rdi
  DirectUI::Element *v29; // rsi
  __int64 v30; // rax
  DirectUI::Value *v31; // rdi
  int Int; // ebx
  LONG v33; // [rsp+40h] [rbp-68h]
  int v34; // [rsp+44h] [rbp-64h]
  unsigned int v35; // [rsp+48h] [rbp-60h]
  int v36; // [rsp+50h] [rbp-58h]
  DirectUI::Value *v37; // [rsp+58h] [rbp-50h] BYREF
  DirectUI::Element *v38; // [rsp+60h] [rbp-48h]
  int VirtualDirection; // [rsp+C8h] [rbp+20h]

  if ( a2 > 0 && a3 > 0 )
  {
    v37 = 0;
    Children = (_DWORD *)DirectUI::Element::GetChildren(this, &v37);
    if ( Children )
    {
      VirtualDirection = ItemLayout::GetVirtualDirection(this);
      v8 = a3;
      if ( VirtualDirection != 1 )
        v8 = a2;
      v36 = v8;
      Value = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorPaddingProp, 2, 0);
      Rect = DirectUI::Value::GetRect(Value);
      top = Rect->top;
      bottom = Rect->bottom;
      if ( Value )
        DirectUI::Value::Release(Value);
      if ( (int)ItemRowLayout::GetSeparatorLineHeight(this) > 0 )
        SeparatorLineHeight = ItemRowLayout::GetSeparatorLineHeight(this);
      else
        SeparatorLineHeight = 0;
      v14 = bottom + SeparatorLineHeight / 2;
      v34 = SeparatorLineHeight + bottom + top;
      v15 = 0;
      v35 = *Children & 0xFFFFFFF;
      v16 = 0;
      if ( v35 )
      {
        v17 = Children + 2;
        do
        {
          if ( (*Children & 0x10000000) != 0 )
            v18 = (_QWORD *)*v17;
          else
            v18 = v17;
          v38 = (DirectUI::Element *)v18[v16];
          DesiredSize = DirectUI::Element::GetDesiredSize(v38);
          cy = DesiredSize->cy;
          cx = DesiredSize->cx;
          if ( VirtualDirection != 1 )
            cx = DesiredSize->cy;
          v33 = cx;
          if ( VirtualDirection != 1 )
            cy = DesiredSize->cx;
          v22 = DirectUI::Element::GetValue(this, ItemRowLayout::UseItemWidthProp, 2, 0);
          Bool = DirectUI::Value::GetBool(v22);
          DirectUI::Value::Release(v22);
          v24 = v36;
          if ( Bool )
            v24 = cy;
          if ( VirtualDirection == 1 )
          {
            v25 = v33;
          }
          else
          {
            v25 = v24;
            v24 = v33;
          }
          v26 = 0;
          if ( VirtualDirection != 1 )
            v26 = v15;
          v27 = v15;
          if ( VirtualDirection != 1 )
            v27 = 0;
          v28 = v38;
          DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v38, v27, v26, v25, v24);
          v15 += v33;
          if ( v34 )
          {
            v29 = 0;
            if ( v28 )
            {
              v30 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v28 + 280LL))(v28);
              if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v30 + 80LL))(
                     v30,
                     UIBase::Class) )
              {
                v29 = v28;
              }
            }
            v31 = DirectUI::Element::GetValue(this, ItemLayout::ItemCountProp, 2, 0);
            Int = DirectUI::Value::GetInt(v31);
            DirectUI::Value::Release(v31);
            if ( *((_DWORD *)v29 + 50) != Int - 1 )
            {
              v15 += v34;
              if ( v16 == v35 - 1 && v14 < 0 )
                v15 -= v14;
            }
          }
          ++v16;
          v17 = Children + 2;
        }
        while ( v16 < v35 );
      }
    }
    v7 = v37;
    if ( v37 )
    {
      v37 = 0;
      DirectUI::Value::Release(v7);
    }
  }
}

```

## disassembly

```asm
0x180081400  test    edx, edx
0x180081402  jle     short locret_180081478
0x180081404  mov     rax, rsp
0x180081407  mov     [rax+8], rbx
0x18008140b  mov     [rax+18h], r8d
0x18008140f  mov     [rax+10h], edx
0x180081412  push    rbp
0x180081413  push    rsi
0x180081414  push    rdi
0x180081415  push    r12
0x180081417  push    r13
0x180081419  push    r14
0x18008141b  push    r15
0x18008141d  sub     rsp, 70h
0x180081421  mov     ebx, r8d
0x180081424  mov     edi, edx
0x180081426  mov     rbp, rcx
0x180081429  test    ebx, ebx
0x18008142b  jle     short loc_180081461
0x18008142d  mov     qword ptr [rax-50h], 0
0x180081435  lea     rdx, [rax-50h]
0x180081439  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18008143f  mov     r12, rax
0x180081442  test    rax, rax
0x180081445  jnz     short loc_180081479
0x180081447  mov     rcx, [rsp+0A8h+var_50]
0x18008144c  test    rcx, rcx
0x18008144f  jz      short loc_180081461
0x180081451  mov     [rsp+0A8h+var_50], 0
0x18008145a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180081460  nop
0x180081461  mov     rbx, [rsp+0A8h+arg_0]
0x180081469  add     rsp, 70h
0x18008146d  pop     r15
0x18008146f  pop     r14
0x180081471  pop     r13
0x180081473  pop     r12
0x180081475  pop     rdi
0x180081476  pop     rsi
0x180081477  pop     rbp
0x180081478  retn
0x180081479  mov     rcx, rbp
0x18008147c  call    ?GetVirtualDirection@ItemLayout@@QEAA?AW4VIRTUALDIRECTION@@XZ; ItemLayout::GetVirtualDirection(void)
0x180081481  mov     esi, eax
0x180081483  mov     [rsp+0A8h+arg_18], eax
0x18008148a  mov     eax, ebx
0x18008148c  cmp     esi, 1
0x18008148f  cmovnz  eax, edi
0x180081492  mov     [rsp+0A8h+var_58], eax
0x180081496  mov     [rsp+0A8h+var_60], 0
0x18008149f  xor     r9d, r9d
0x1800814a2  lea     r14d, [r9+2]
0x1800814a6  mov     r8d, r14d
0x1800814a9  lea     rdx, ?SeparatorPaddingProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorPaddingProp(void)
0x1800814b0  mov     rcx, rbp
0x1800814b3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800814b9  mov     rbx, rax
0x1800814bc  mov     [rsp+0A8h+var_60], rax
0x1800814c1  mov     rcx, rax
0x1800814c4  call    cs:__imp_?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ; DirectUI::Value::GetRect(void)
0x1800814ca  mov     esi, [rax+4]
0x1800814cd  mov     edi, [rax+0Ch]
0x1800814d0  test    rbx, rbx
0x1800814d3  jz      short loc_1800814DF
0x1800814d5  mov     rcx, rbx
0x1800814d8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800814de  nop
0x1800814df  mov     rcx, rbp; this
0x1800814e2  call    ?GetSeparatorLineHeight@ItemRowLayout@@QEAAHXZ; ItemRowLayout::GetSeparatorLineHeight(void)
0x1800814e7  test    eax, eax
0x1800814e9  jg      loc_1800816B6
0x1800814ef  xor     ecx, ecx
0x1800814f1  mov     eax, ecx
0x1800814f3  cdq
0x1800814f4  idiv    r14d
0x1800814f7  lea     r13d, [rdi+rax]
0x1800814fb  lea     eax, [rdi+rsi]
0x1800814fe  add     eax, ecx
0x180081500  mov     [rsp+0A8h+var_64], eax
0x180081504  xor     r14d, r14d
0x180081507  mov     eax, [r12]
0x18008150b  and     eax, 0FFFFFFFh
0x180081510  mov     dword ptr [rsp+0A8h+var_60], eax
0x180081514  mov     r15d, r14d
0x180081517  jbe     loc_180081447
0x18008151d  lea     rax, [r12+8]
0x180081522  test    dword ptr [r12], 10000000h
0x18008152a  jz      loc_1800816AE
0x180081530  mov     rcx, [rax]
0x180081533  mov     eax, r15d
0x180081536  mov     rcx, [rcx+rax*8]
0x18008153a  mov     [rsp+0A8h+var_48], rcx
0x18008153f  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x180081545  mov     esi, [rax+4]
0x180081548  mov     ecx, [rax]
0x18008154a  cmp     [rsp+0A8h+arg_18], 1
0x180081552  cmovnz  ecx, esi
0x180081555  mov     [rsp+0A8h+var_68], ecx
0x180081559  cmovnz  esi, [rax]
0x18008155c  xor     r9d, r9d
0x18008155f  lea     r8d, [r9+2]
0x180081563  lea     rdx, ?UseItemWidthProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::UseItemWidthProp(void)
0x18008156a  mov     rcx, rbp
0x18008156d  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180081573  mov     rbx, rax
0x180081576  mov     rcx, rax
0x180081579  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18008157f  mov     dil, al
0x180081582  mov     rcx, rbx
0x180081585  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18008158b  mov     r8d, [rsp+0A8h+var_58]
0x180081590  test    dil, dil
0x180081593  cmovnz  r8d, esi
0x180081597  mov     esi, [rsp+0A8h+arg_18]
0x18008159e  mov     ebx, [rsp+0A8h+var_68]
0x1800815a2  cmp     esi, 1
0x1800815a5  jnz     loc_1800816C5
0x1800815ab  mov     r9d, ebx
0x1800815ae  xor     edx, edx
0x1800815b0  cmp     esi, 1
0x1800815b3  cmovnz  edx, r14d
0x1800815b7  mov     ecx, r14d
0x1800815ba  xor     eax, eax
0x1800815bc  cmp     esi, 1
0x1800815bf  cmovnz  ecx, eax
0x1800815c2  mov     [rsp+0A8h+var_70], r8d
0x1800815c7  mov     [rsp+0A8h+var_78], r9d
0x1800815cc  mov     [rsp+0A8h+var_80], edx
0x1800815d0  mov     [rsp+0A8h+var_88], ecx
0x1800815d4  mov     rdi, [rsp+0A8h+var_48]
0x1800815d9  mov     r9, rdi
0x1800815dc  mov     r8d, [rsp+0A8h+arg_10]
0x1800815e4  mov     edx, [rsp+0A8h+arg_8]
0x1800815eb  mov     rcx, rbp
0x1800815ee  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800815f4  add     r14d, ebx
0x1800815f7  cmp     [rsp+0A8h+var_64], 0
0x1800815fc  jz      loc_180081683
0x180081602  xor     esi, esi
0x180081604  test    rdi, rdi
0x180081607  jz      short loc_18008163A
0x180081609  mov     rax, [rdi]
0x18008160c  mov     rcx, rdi
0x18008160f  mov     rax, [rax+118h]
0x180081616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008161b  mov     r8, rax
0x18008161e  mov     rcx, [rax]
0x180081621  mov     rax, [rcx+50h]
0x180081625  mov     rdx, cs:?Class@UIBase@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIBase::Class
0x18008162c  mov     rcx, r8
0x18008162f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081634  test    al, al
0x180081636  cmovnz  rsi, rdi
0x18008163a  xor     r9d, r9d
0x18008163d  lea     r8d, [r9+2]
0x180081641  lea     rdx, ?ItemCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ItemCountProp(void)
0x180081648  mov     rcx, rbp
0x18008164b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180081651  mov     rdi, rax
0x180081654  mov     rcx, rax
0x180081657  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18008165d  mov     ebx, eax
0x18008165f  mov     rcx, rdi
0x180081662  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180081668  lea     eax, [rbx-1]
0x18008166b  cmp     [rsi+0C8h], eax
0x180081671  jz      short loc_180081683
0x180081673  add     r14d, [rsp+0A8h+var_64]
0x180081678  mov     eax, dword ptr [rsp+0A8h+var_60]
0x18008167c  dec     eax
0x18008167e  cmp     r15d, eax
0x180081681  jz      short loc_18008169B
0x180081683  inc     r15d
0x180081686  cmp     r15d, dword ptr [rsp+0A8h+var_60]
0x18008168b  lea     rax, [r12+8]
0x180081690  jb      loc_180081522
0x180081696  jmp     loc_180081447
0x18008169b  test    r13d, r13d
0x18008169e  jns     short loc_180081683
0x1800816a0  mov     eax, r13d
0x1800816a3  neg     eax
0x1800816a5  cmovs   eax, r13d
0x1800816a9  add     r14d, eax
0x1800816ac  jmp     short loc_180081683
0x1800816ae  mov     rcx, rax
0x1800816b1  jmp     loc_180081533
0x1800816b6  mov     rcx, rbp; this
0x1800816b9  call    ?GetSeparatorLineHeight@ItemRowLayout@@QEAAHXZ; ItemRowLayout::GetSeparatorLineHeight(void)
0x1800816be  mov     ecx, eax
0x1800816c0  jmp     loc_1800814F1
0x1800816c5  mov     r9d, r8d
0x1800816c8  mov     r8d, ebx
0x1800816cb  jmp     loc_1800815AE
```
