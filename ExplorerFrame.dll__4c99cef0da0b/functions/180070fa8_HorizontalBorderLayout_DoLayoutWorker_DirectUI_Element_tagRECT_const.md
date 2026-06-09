# HorizontalBorderLayout::_DoLayoutWorker(DirectUI::Element *,tagRECT const &)

- ea: `0x180070fa8`
- end: `0x18007126b`
- name: `?_DoLayoutWorker@HorizontalBorderLayout@@IEAAXPEAVElement@DirectUI@@AEBUtagRECT@@@Z`
- size: `707`
- prototype: `void(HorizontalBorderLayout *__hidden this, struct DirectUI::Element *, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180070a70`
- `0x180070b30`

## callees

- `0x180015fe0`
- `0x180018140`
- `0x180070fa8`

## import_xrefs

- `DUI70!?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180071094`
- `DUI70!?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800711dd`
- `DUI70!?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180071094`
- `DUI70!?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800711dd`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180071124`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180071151`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800711f6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180071124`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180071151`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800711f6`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180071006`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180071006`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18007109d`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18007109d`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800710b5`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800710b5`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180071108`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18007119e`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18007125f`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180071108`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18007119e`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18007125f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall HorizontalBorderLayout::_DoLayoutWorker(
        HorizontalBorderLayout *this,
        struct DirectUI::Element *a2,
        const struct tagRECT *a3)
{
  struct DirectUI::Element *v4; // r13
  _DWORD *Children; // rax
  _DWORD *v6; // r12
  unsigned int v7; // eax
  int v8; // edi
  LONG right; // edx
  LONG left; // r8d
  LONG v11; // r14d
  LONG v12; // r15d
  LONG v13; // ebx
  LONG v14; // ecx
  int v15; // ebx
  int v16; // ebx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  unsigned int v19; // esi
  _QWORD *v20; // rdx
  int v21; // edi
  int LayoutPos; // eax
  DirectUI::Value *v23; // rcx
  DirectUI::Value *v24; // rcx
  __int64 v25; // r13
  _QWORD *v26; // rcx
  DirectUI::Element *v27; // rcx
  DirectUI::Value *v28; // rcx
  LONG top; // [rsp+40h] [rbp-30h]
  int v30; // [rsp+44h] [rbp-2Ch]
  struct DirectUI::Value *v31; // [rsp+48h] [rbp-28h] BYREF
  DirectUI::Value *v32; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+58h] [rbp-18h]
  __int64 v34; // [rsp+60h] [rbp-10h] BYREF
  struct tagSIZE ElementExtent; // [rsp+68h] [rbp-8h]
  unsigned int v36; // [rsp+B0h] [rbp+40h]
  DirectUI::Element *v37; // [rsp+B0h] [rbp+40h]
  struct DirectUI::Value *v39; // [rsp+C8h] [rbp+58h] BYREF

  v4 = a2;
  v34 = 0;
  ElementExtent = DUI_GetElementExtent(a2);
  DUI_ReduceRectByPaddingAndBorders(v4, 0, &v34);
  v32 = 0;
  Children = (_DWORD *)DirectUI::Element::GetChildren(v4, &v32);
  v6 = Children;
  if ( Children )
  {
    v7 = *Children & 0xFFFFFFF;
    v36 = v7;
    v8 = 0;
    right = a3->right;
    left = a3->left;
    v11 = right;
    v12 = a3->left;
    if ( right - a3->left > 0 )
    {
      v25 = 0;
      do
      {
        v14 = left;
        v13 = right;
        if ( (unsigned int)v25 >= v7 )
          break;
        v26 = v6 + 2;
        if ( (*v6 & 0x10000000) != 0 )
          v26 = (_QWORD *)*v26;
        v27 = (DirectUI::Element *)v26[v25];
        v39 = 0;
        v8 += DirectUI::Element::GetMinSize(v27, &v39)->cx;
        v28 = v39;
        if ( v39 )
        {
          v39 = 0;
          DirectUI::Value::Release(v28);
        }
        v25 = (unsigned int)(v25 + 1);
        right = a3->right;
        left = a3->left;
        v14 = a3->left;
        v13 = right;
        v11 = right;
        v12 = a3->left;
        v7 = v36;
      }
      while ( v8 < right - a3->left );
      v4 = a2;
    }
    else
    {
      v13 = a3->right;
      v14 = a3->left;
    }
    v15 = v13 - v14;
    top = a3->top;
    LODWORD(v39) = a3->bottom;
    if ( v8 >= v15 )
      v8 = v15;
    v16 = v15 - v8;
    v17 = 0;
    v30 = 0;
    if ( v7 )
    {
      v18 = v6 + 2;
      v19 = v36;
      do
      {
        if ( (*v6 & 0x10000000) != 0 )
          v20 = (_QWORD *)*v18;
        else
          v20 = v18;
        v37 = (DirectUI::Element *)v20[v17];
        v31 = 0;
        DirectUI::Element::GetMinSize(v37, &v31);
        v33 = (__int64)*DirectUI::Element::GetDesiredSize(v37);
        v21 = v33;
        if ( (int)v33 >= v16 )
          v21 = v16;
        LayoutPos = DirectUI::Element::GetLayoutPos(v37);
        if ( LayoutPos )
        {
          if ( LayoutPos != 2 )
          {
            if ( LayoutPos == 4 )
            {
              DirectUI::Layout::UpdateLayoutRect(
                v4,
                ElementExtent.cx - v34,
                ElementExtent.cy - HIDWORD(v34),
                v37,
                v12,
                top,
                v11 - v12,
                (_DWORD)v39 - top);
              v12 = v11;
              v16 = 0;
            }
            goto LABEL_16;
          }
          v11 -= v21;
          DirectUI::Layout::UpdateLayoutRect(
            v4,
            ElementExtent.cx - v34,
            ElementExtent.cy - HIDWORD(v34),
            v37,
            v11,
            top,
            v21,
            (_DWORD)v39 - top);
        }
        else
        {
          DirectUI::Layout::UpdateLayoutRect(
            v4,
            ElementExtent.cx - v34,
            ElementExtent.cy - HIDWORD(v34),
            v37,
            v12,
            top,
            v21,
            (_DWORD)v39 - top);
          v12 += v21;
        }
        v16 -= v21;
LABEL_16:
        v23 = v31;
        if ( v31 )
        {
          v31 = 0;
          DirectUI::Value::Release(v23);
        }
        v17 = (unsigned int)(v30 + 1);
        v30 = v17;
        v18 = v6 + 2;
      }
      while ( (unsigned int)v17 < v19 );
    }
  }
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    DirectUI::Value::Release(v24);
  }
}

```

## disassembly

```asm
0x180070fa8  mov     [rsp-38h+arg_10], rbx
0x180070fad  mov     [rsp-38h+arg_8], rdx
0x180070fb2  mov     [rsp-38h+arg_0], rcx
0x180070fb7  push    rbp
0x180070fb8  push    rsi
0x180070fb9  push    rdi
0x180070fba  push    r12
0x180070fbc  push    r13
0x180070fbe  push    r14
0x180070fc0  push    r15
0x180070fc2  mov     rbp, rsp
0x180070fc5  sub     rsp, 70h
0x180070fc9  mov     rsi, r8
0x180070fcc  mov     r13, rdx
0x180070fcf  mov     rcx, rdx; struct DirectUI::Element *
0x180070fd2  call    ?DUI_GetElementExtent@@YA?AUtagSIZE@@PEAVElement@DirectUI@@@Z; DUI_GetElementExtent(DirectUI::Element *)
0x180070fd7  mov     [rbp+var_10], 0
0x180070fdf  mov     dword ptr [rbp+var_8], eax
0x180070fe2  shr     rax, 20h
0x180070fe6  mov     dword ptr [rbp+var_8+4], eax
0x180070fe9  lea     r8, [rbp+var_10]
0x180070fed  xor     edx, edx
0x180070fef  mov     rcx, r13
0x180070ff2  call    ?DUI_ReduceRectByPaddingAndBorders@@YAXPEAVElement@DirectUI@@W4DUI_COORDINATES_SYSTEM@@PEAUtagRECT@@@Z; DUI_ReduceRectByPaddingAndBorders(DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagRECT *)
0x180070ff7  mov     [rbp+var_20], 0
0x180070fff  lea     rdx, [rbp+var_20]
0x180071003  mov     rcx, r13
0x180071006  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18007100c  mov     r12, rax
0x18007100f  test    rax, rax
0x180071012  jz      loc_180071140
0x180071018  mov     eax, [rax]
0x18007101a  and     eax, 0FFFFFFFh
0x18007101f  mov     dword ptr [rbp+arg_0], eax
0x180071022  xor     edi, edi
0x180071024  mov     edx, [rsi+8]
0x180071027  mov     r8d, [rsi]
0x18007102a  mov     ecx, edx
0x18007102c  sub     ecx, r8d
0x18007102f  mov     r14d, edx
0x180071032  mov     r15d, r8d
0x180071035  test    ecx, ecx
0x180071037  jg      loc_1800711AE
0x18007103d  mov     ebx, edx
0x18007103f  mov     ecx, r8d
0x180071042  sub     ebx, ecx
0x180071044  mov     ecx, [rsi+4]
0x180071047  mov     [rbp+var_30], ecx
0x18007104a  mov     ecx, [rsi+0Ch]
0x18007104d  mov     dword ptr [rbp+arg_18], ecx
0x180071050  cmp     edi, ebx
0x180071052  cmovge  edi, ebx
0x180071055  sub     ebx, edi
0x180071057  xor     ecx, ecx
0x180071059  mov     [rbp+var_2C], ecx
0x18007105c  test    eax, eax
0x18007105e  jz      loc_180071140
0x180071064  lea     rax, [r12+8]
0x180071069  mov     esi, dword ptr [rbp+arg_0]
0x18007106c  test    dword ptr [r12], 10000000h
0x180071074  jz      loc_180071226
0x18007107a  mov     rdx, [rax]
0x18007107d  mov     rdi, [rdx+rcx*8]
0x180071081  mov     [rbp+arg_0], rdi
0x180071085  mov     [rbp+var_28], 0
0x18007108d  lea     rdx, [rbp+var_28]
0x180071091  mov     rcx, rdi
0x180071094  call    cs:__imp_?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMinSize(DirectUI::Value * *)
0x18007109a  mov     rcx, rdi
0x18007109d  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x1800710a3  mov     rcx, [rax]
0x1800710a6  mov     [rbp+var_18], rcx
0x1800710aa  mov     edi, ecx
0x1800710ac  cmp     ecx, ebx
0x1800710ae  cmovge  edi, ebx
0x1800710b1  mov     rcx, [rbp+arg_0]
0x1800710b5  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x1800710bb  test    eax, eax
0x1800710bd  jz      loc_180071170
0x1800710c3  cmp     eax, 2
0x1800710c6  jz      loc_18007122E
0x1800710cc  cmp     eax, 4
0x1800710cf  jnz     short loc_180071113
0x1800710d1  mov     ecx, dword ptr [rbp+arg_18]
0x1800710d4  mov     r9d, [rbp+var_30]
0x1800710d8  sub     ecx, r9d
0x1800710db  mov     eax, r14d
0x1800710de  sub     eax, r15d
0x1800710e1  mov     r8d, dword ptr [rbp+var_8+4]
0x1800710e5  sub     r8d, dword ptr [rbp+var_10+4]
0x1800710e9  mov     edx, dword ptr [rbp+var_8]
0x1800710ec  sub     edx, dword ptr [rbp+var_10]
0x1800710ef  mov     [rsp+70h+var_38], ecx
0x1800710f3  mov     [rsp+70h+var_40], eax
0x1800710f7  mov     [rsp+70h+var_48], r9d
0x1800710fc  mov     [rsp+70h+var_50], r15d
0x180071101  mov     r9, [rbp+arg_0]
0x180071105  mov     rcx, r13
0x180071108  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18007110e  mov     r15d, r14d
0x180071111  xor     ebx, ebx
0x180071113  mov     rcx, [rbp+var_28]
0x180071117  test    rcx, rcx
0x18007111a  jz      short loc_18007112B
0x18007111c  mov     [rbp+var_28], 0
0x180071124  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007112a  nop
0x18007112b  mov     ecx, [rbp+var_2C]
0x18007112e  inc     ecx
0x180071130  mov     [rbp+var_2C], ecx
0x180071133  cmp     ecx, esi
0x180071135  lea     rax, [r12+8]
0x18007113a  jb      loc_18007106C
0x180071140  mov     rcx, [rbp+var_20]
0x180071144  test    rcx, rcx
0x180071147  jz      short loc_180071158
0x180071149  mov     [rbp+var_20], 0
0x180071151  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180071157  nop
0x180071158  mov     rbx, [rsp+70h+arg_10]
0x180071160  add     rsp, 70h
0x180071164  pop     r15
0x180071166  pop     r14
0x180071168  pop     r13
0x18007116a  pop     r12
0x18007116c  pop     rdi
0x18007116d  pop     rsi
0x18007116e  pop     rbp
0x18007116f  retn
0x180071170  mov     eax, dword ptr [rbp+arg_18]
0x180071173  mov     ecx, [rbp+var_30]
0x180071176  sub     eax, ecx
0x180071178  mov     r8d, dword ptr [rbp+var_8+4]
0x18007117c  sub     r8d, dword ptr [rbp+var_10+4]
0x180071180  mov     edx, dword ptr [rbp+var_8]
0x180071183  sub     edx, dword ptr [rbp+var_10]
0x180071186  mov     [rsp+70h+var_38], eax
0x18007118a  mov     [rsp+70h+var_40], edi
0x18007118e  mov     [rsp+70h+var_48], ecx
0x180071192  mov     [rsp+70h+var_50], r15d
0x180071197  mov     r9, [rbp+arg_0]
0x18007119b  mov     rcx, r13
0x18007119e  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800711a4  add     r15d, edi
0x1800711a7  sub     ebx, edi
0x1800711a9  jmp     loc_180071113
0x1800711ae  xor     r13d, r13d
0x1800711b1  mov     ecx, r8d
0x1800711b4  mov     ebx, edx
0x1800711b6  cmp     r13d, eax
0x1800711b9  jnb     short loc_18007121D
0x1800711bb  lea     rcx, [r12+8]
0x1800711c0  test    dword ptr [r12], 10000000h
0x1800711c8  jz      short loc_1800711CD
0x1800711ca  mov     rcx, [rcx]
0x1800711cd  mov     rcx, [rcx+r13*8]
0x1800711d1  mov     [rbp+arg_18], 0
0x1800711d9  lea     rdx, [rbp+arg_18]
0x1800711dd  call    cs:__imp_?GetMinSize@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMinSize(DirectUI::Value * *)
0x1800711e3  add     edi, [rax]
0x1800711e5  mov     rcx, [rbp+arg_18]
0x1800711e9  test    rcx, rcx
0x1800711ec  jz      short loc_1800711FD
0x1800711ee  mov     [rbp+arg_18], 0
0x1800711f6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800711fc  nop
0x1800711fd  inc     r13d
0x180071200  mov     edx, [rsi+8]
0x180071203  mov     r8d, [rsi]
0x180071206  mov     ecx, r8d
0x180071209  mov     ebx, edx
0x18007120b  mov     r14d, edx
0x18007120e  mov     r15d, r8d
0x180071211  mov     eax, edx
0x180071213  sub     eax, r8d
0x180071216  cmp     edi, eax
0x180071218  mov     eax, dword ptr [rbp+arg_0]
0x18007121b  jl      short loc_1800711B1
0x18007121d  mov     r13, [rbp+arg_8]
0x180071221  jmp     loc_180071042
0x180071226  mov     rdx, rax
0x180071229  jmp     loc_18007107D
0x18007122e  sub     r14d, edi
0x180071231  mov     eax, dword ptr [rbp+arg_18]
0x180071234  mov     ecx, [rbp+var_30]
0x180071237  sub     eax, ecx
0x180071239  mov     r8d, dword ptr [rbp+var_8+4]
0x18007123d  sub     r8d, dword ptr [rbp+var_10+4]
0x180071241  mov     edx, dword ptr [rbp+var_8]
0x180071244  sub     edx, dword ptr [rbp+var_10]
0x180071247  mov     [rsp+70h+var_38], eax
0x18007124b  mov     [rsp+70h+var_40], edi
0x18007124f  mov     [rsp+70h+var_48], ecx
0x180071253  mov     [rsp+70h+var_50], r14d
0x180071258  mov     r9, [rbp+arg_0]
0x18007125c  mov     rcx, r13
0x18007125f  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180071265  jmp     loc_1800711A7
```
