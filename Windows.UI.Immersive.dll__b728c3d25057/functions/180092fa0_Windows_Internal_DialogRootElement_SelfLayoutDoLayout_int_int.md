# Windows::Internal::DialogRootElement::_SelfLayoutDoLayout(int,int)

- ea: `0x180092fa0`
- end: `0x180093236`
- name: `?_SelfLayoutDoLayout@DialogRootElement@Internal@Windows@@EEAAXHH@Z`
- size: `662`
- prototype: `void __fastcall(Windows::Internal::DialogRootElement *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005ae80`
- `0x180092fa0`

## import_xrefs

- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180092fd1`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180092fd1`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009304e`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180093068`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180093082`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009304e`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180093068`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180093082`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093015`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093025`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093032`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093015`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093025`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180093032`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009308f`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800930ba`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009308f`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800930ba`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009312c`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180093196`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800931c6`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800931ed`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009312c`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180093196`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800931c6`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800931ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::DialogRootElement::_SelfLayoutDoLayout(
        Windows::Internal::DialogRootElement *this,
        int a2,
        int a3)
{
  __int64 Children; // rax
  _QWORD *v7; // rdx
  int v8; // ecx
  DirectUI::Element *v9; // r14
  __int64 v10; // rax
  DirectUI::Element *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rbx
  int v15; // r14d
  LONG left; // r14d
  bool v17; // al
  int v18; // ecx
  LONG bottom; // ecx
  int v20; // eax
  int v21; // edx
  DirectUI::Element *v22; // [rsp+40h] [rbp-39h]
  struct DirectUI::Element *v23; // [rsp+48h] [rbp-31h]
  DirectUI::Element *v24; // [rsp+50h] [rbp-29h]
  struct DirectUI::Value *v25; // [rsp+60h] [rbp-19h] BYREF
  struct DirectUI::Value *v26; // [rsp+68h] [rbp-11h] BYREF
  struct DirectUI::Value *v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1h] BYREF
  const struct tagRECT *Margin; // [rsp+80h] [rbp+7h]
  __int64 v30; // [rsp+88h] [rbp+Fh]
  const struct tagRECT *v31; // [rsp+90h] [rbp+17h]
  bool Visible; // [rsp+E8h] [rbp+6Fh]
  int v33; // [rsp+F0h] [rbp+77h]
  const struct tagRECT *v34; // [rsp+F8h] [rbp+7Fh]
  int v35; // [rsp+F8h] [rbp+7Fh]

  v28 = 0;
  Children = DirectUI::Element::GetChildren(this, &v28);
  v7 = (_QWORD *)(Children + 8);
  v8 = *(_DWORD *)Children & 0x10000000;
  v9 = *(DirectUI::Element **)(Children + 8);
  v23 = v9;
  if ( v8 )
  {
    v10 = *(_QWORD *)(Children + 8);
    v9 = *(DirectUI::Element **)v9;
    v23 = v9;
  }
  else
  {
    v10 = Children + 8;
  }
  v11 = *(DirectUI::Element **)(v10 + 8);
  v24 = v11;
  if ( v8 )
    v7 = (_QWORD *)*v7;
  v22 = (DirectUI::Element *)v7[2];
  v12 = (__int64)*DirectUI::Element::GetDesiredSize(v9);
  v13 = (__int64)*DirectUI::Element::GetDesiredSize(v11);
  v14 = (__int64)*DirectUI::Element::GetDesiredSize(v22);
  v30 = v14;
  v27 = 0;
  Margin = DirectUI::Element::GetMargin(v9, &v27);
  v26 = 0;
  v34 = DirectUI::Element::GetMargin(v24, &v26);
  v25 = 0;
  v31 = DirectUI::Element::GetMargin(v22, &v25);
  Visible = DirectUI::Element::GetVisible(v9);
  v15 = 0;
  if ( Visible )
  {
    left = v34->left;
    if ( v34->left <= Margin->right )
      left = Margin->right;
    v15 = v12 + left;
  }
  v17 = DirectUI::Element::GetVisible(v22);
  v18 = 0;
  if ( v17 )
  {
    bottom = v34->bottom;
    if ( bottom <= v31->top )
      bottom = v31->top;
    v18 = HIDWORD(v30) + bottom;
  }
  v33 = a3 - v18;
  if ( (int)v13 + v15 <= a2 )
  {
    v20 = (a2 - (int)v13) / 2;
    if ( (int)v13 < (int)v14 )
      LODWORD(v14) = v13;
    v21 = 0;
    if ( v20 - v15 >= 0 )
      v21 = v20 - v15;
    v35 = v21;
    if ( v20 - v15 >= 0 )
      v15 = (a2 - (int)v13) / 2;
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v22, v13 + v15 - v14, a3 - HIDWORD(v30), v14, HIDWORD(v30));
    if ( Visible )
      DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v23, v35, 0, v12, HIDWORD(v12));
  }
  else
  {
    LODWORD(v13) = 0;
    if ( a2 - v15 >= 0 )
      LODWORD(v13) = a2 - v15;
    if ( (int)v13 < (int)v14 )
      LODWORD(v14) = v13;
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v22, a2 - v14, a3 - HIDWORD(v30), v14, HIDWORD(v30));
    if ( Visible )
      DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v23, 0, 0, v12, HIDWORD(v12));
  }
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v24, v15, 0, v13, v33);
  CValuePtr::Release((CValuePtr *)&v25);
  CValuePtr::Release((CValuePtr *)&v26);
  CValuePtr::Release((CValuePtr *)&v27);
  CValuePtr::Release((CValuePtr *)&v28);
}

```

## disassembly

```asm
0x180092fa0  mov     [rsp-8+arg_0], rbx
0x180092fa5  push    rbp
0x180092fa6  push    rsi
0x180092fa7  push    rdi
0x180092fa8  push    r12
0x180092faa  push    r13
0x180092fac  push    r14
0x180092fae  push    r15
0x180092fb0  lea     rbp, [rsp-27h]
0x180092fb5  sub     rsp, 0A0h
0x180092fbc  mov     r12d, r8d
0x180092fbf  mov     r15d, edx
0x180092fc2  mov     r13, rcx
0x180092fc5  mov     [rbp+57h+var_58], 0
0x180092fcd  lea     rdx, [rbp+57h+var_58]
0x180092fd1  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180092fd7  lea     rdx, [rax+8]
0x180092fdb  mov     ecx, [rax]
0x180092fdd  and     ecx, 10000000h
0x180092fe3  mov     r14, [rdx]
0x180092fe6  mov     [rbp+57h+var_88], r14
0x180092fea  jz      short loc_180092FF8
0x180092fec  mov     rax, r14
0x180092fef  mov     r14, [r14]
0x180092ff2  mov     [rbp+57h+var_88], r14
0x180092ff6  jmp     short loc_180092FFB
0x180092ff8  mov     rax, rdx
0x180092ffb  mov     rbx, [rax+8]
0x180092fff  mov     [rbp+57h+var_80], rbx
0x180093003  test    ecx, ecx
0x180093005  jz      short loc_18009300A
0x180093007  mov     rdx, [rdx]
0x18009300a  mov     rax, [rdx+10h]
0x18009300e  mov     [rbp+57h+var_90], rax
0x180093012  mov     rcx, r14
0x180093015  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009301b  mov     rdi, [rax]
0x18009301e  mov     [rbp+57h+var_78], rdi
0x180093022  mov     rcx, rbx
0x180093025  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009302b  mov     rsi, [rax]
0x18009302e  mov     rcx, [rbp+57h+var_90]
0x180093032  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x180093038  mov     rbx, [rax]
0x18009303b  mov     [rbp+57h+var_48], rbx
0x18009303f  mov     [rbp+57h+var_60], 0
0x180093047  lea     rdx, [rbp+57h+var_60]
0x18009304b  mov     rcx, r14
0x18009304e  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180093054  mov     [rbp+57h+var_50], rax
0x180093058  mov     [rbp+57h+var_68], 0
0x180093060  lea     rdx, [rbp+57h+var_68]
0x180093064  mov     rcx, [rbp+57h+var_80]
0x180093068  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009306e  mov     [rbp+57h+arg_18], rax
0x180093072  mov     [rbp+57h+var_70], 0
0x18009307a  lea     rdx, [rbp+57h+var_70]
0x18009307e  mov     rcx, [rbp+57h+var_90]
0x180093082  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180093088  mov     [rbp+57h+var_40], rax
0x18009308c  mov     rcx, r14
0x18009308f  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180093095  mov     [rbp+57h+arg_8], al
0x180093098  xor     r14d, r14d
0x18009309b  test    al, al
0x18009309d  jz      short loc_1800930B6
0x18009309f  mov     r14, [rbp+57h+arg_18]
0x1800930a3  mov     r14d, [r14]
0x1800930a6  mov     rax, [rbp+57h+var_50]
0x1800930aa  cmp     r14d, [rax+8]
0x1800930ae  cmovle  r14d, [rax+8]
0x1800930b3  add     r14d, edi
0x1800930b6  mov     rcx, [rbp+57h+var_90]
0x1800930ba  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800930c0  xor     ecx, ecx
0x1800930c2  mov     r8d, dword ptr [rbp+57h+var_48+4]
0x1800930c6  test    al, al
0x1800930c8  jz      short loc_1800930DF
0x1800930ca  mov     rax, [rbp+57h+arg_18]
0x1800930ce  mov     ecx, [rax+0Ch]
0x1800930d1  mov     rax, [rbp+57h+var_40]
0x1800930d5  cmp     ecx, [rax+4]
0x1800930d8  cmovle  ecx, [rax+4]
0x1800930dc  add     ecx, r8d
0x1800930df  mov     eax, r12d
0x1800930e2  sub     eax, ecx
0x1800930e4  mov     [rbp+57h+arg_10], eax
0x1800930e7  lea     eax, [rsi+r14]
0x1800930eb  mov     [rsp+0D0h+var_98], r8d
0x1800930f0  mov     r9, [rbp+57h+var_90]
0x1800930f4  cmp     eax, r15d
0x1800930f7  mov     eax, r15d
0x1800930fa  jle     short loc_180093152
0x1800930fc  sub     eax, r14d
0x1800930ff  mov     esi, 0
0x180093104  cmovns  esi, eax
0x180093107  cmp     esi, ebx
0x180093109  cmovl   ebx, esi
0x18009310c  mov     ecx, r12d
0x18009310f  sub     ecx, r8d
0x180093112  mov     eax, r15d
0x180093115  sub     eax, ebx
0x180093117  mov     [rsp+0D0h+var_A0], ebx
0x18009311b  mov     [rsp+0D0h+var_A8], ecx
0x18009311f  mov     [rsp+0D0h+var_B0], eax
0x180093123  mov     r8d, r12d
0x180093126  mov     edx, r15d
0x180093129  mov     rcx, r13
0x18009312c  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180093132  xor     ebx, ebx
0x180093134  cmp     [rbp+57h+arg_8], bl
0x180093137  jz      loc_1800931CC
0x18009313d  mov     eax, dword ptr [rbp+57h+var_78+4]
0x180093140  mov     [rsp+0D0h+var_98], eax
0x180093144  mov     [rsp+0D0h+var_A0], edi
0x180093148  mov     [rsp+0D0h+var_A8], ebx
0x18009314c  mov     [rsp+0D0h+var_B0], ebx
0x180093150  jmp     short loc_1800931B9
0x180093152  sub     eax, esi
0x180093154  cdq
0x180093155  mov     ecx, 2
0x18009315a  idiv    ecx
0x18009315c  mov     ecx, eax
0x18009315e  cmp     esi, ebx
0x180093160  cmovl   ebx, esi
0x180093163  xor     edx, edx
0x180093165  sub     ecx, r14d
0x180093168  cmovns  edx, ecx
0x18009316b  mov     dword ptr [rbp+57h+arg_18], edx
0x18009316e  test    ecx, ecx
0x180093170  cmovns  r14d, eax
0x180093174  mov     ecx, r12d
0x180093177  sub     ecx, r8d
0x18009317a  mov     eax, r14d
0x18009317d  sub     eax, ebx
0x18009317f  add     eax, esi
0x180093181  mov     [rsp+0D0h+var_A0], ebx
0x180093185  mov     [rsp+0D0h+var_A8], ecx
0x180093189  mov     [rsp+0D0h+var_B0], eax
0x18009318d  mov     r8d, r12d
0x180093190  mov     edx, r15d
0x180093193  mov     rcx, r13
0x180093196  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009319c  xor     ebx, ebx
0x18009319e  cmp     [rbp+57h+arg_8], bl
0x1800931a1  jz      short loc_1800931CC
0x1800931a3  mov     eax, dword ptr [rbp+57h+var_78+4]
0x1800931a6  mov     [rsp+0D0h+var_98], eax
0x1800931aa  mov     [rsp+0D0h+var_A0], edi
0x1800931ae  mov     [rsp+0D0h+var_A8], ebx
0x1800931b2  mov     eax, dword ptr [rbp+57h+arg_18]
0x1800931b5  mov     [rsp+0D0h+var_B0], eax
0x1800931b9  mov     r9, [rbp+57h+var_88]
0x1800931bd  mov     r8d, r12d
0x1800931c0  mov     edx, r15d
0x1800931c3  mov     rcx, r13
0x1800931c6  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800931cc  mov     eax, [rbp+57h+arg_10]
0x1800931cf  mov     [rsp+0D0h+var_98], eax
0x1800931d3  mov     [rsp+0D0h+var_A0], esi
0x1800931d7  mov     [rsp+0D0h+var_A8], ebx
0x1800931db  mov     [rsp+0D0h+var_B0], r14d
0x1800931e0  mov     r9, [rbp+57h+var_80]
0x1800931e4  mov     r8d, r12d
0x1800931e7  mov     edx, r15d
0x1800931ea  mov     rcx, r13
0x1800931ed  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800931f3  nop
0x1800931f4  lea     rcx, [rbp+57h+var_70]; this
0x1800931f8  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800931fd  nop
0x1800931fe  lea     rcx, [rbp+57h+var_68]; this
0x180093202  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180093207  nop
0x180093208  lea     rcx, [rbp+57h+var_60]; this
0x18009320c  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180093211  nop
0x180093212  lea     rcx, [rbp+57h+var_58]; this
0x180093216  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009321b  mov     rbx, [rsp+0D0h+arg_0]
0x180093223  add     rsp, 0A0h
0x18009322a  pop     r15
0x18009322c  pop     r14
0x18009322e  pop     r13
0x180093230  pop     r12
0x180093232  pop     rdi
0x180093233  pop     rsi
0x180093234  pop     rbp
0x180093235  retn
```
