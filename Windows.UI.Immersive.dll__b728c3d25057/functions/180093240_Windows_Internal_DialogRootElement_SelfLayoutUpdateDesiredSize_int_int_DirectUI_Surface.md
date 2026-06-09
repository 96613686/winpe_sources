# Windows::Internal::DialogRootElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x180093240`
- end: `0x1800933ea`
- name: `?_SelfLayoutUpdateDesiredSize@DialogRootElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `426`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::DialogRootElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005ae80`
- `0x180093240`

## import_xrefs

- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180093275`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180093275`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932b5`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932ca`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932e2`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932b5`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932ca`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800932e2`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009330b`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180093337`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009330b`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180093337`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093302`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093356`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093395`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093302`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093356`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180093395`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct tagSIZE __fastcall Windows::Internal::DialogRootElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::DialogRootElement *this,
        __int64 a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // r14d
  __int64 Children; // rax
  _QWORD *v8; // rcx
  int v9; // edx
  DirectUI::Element *v10; // rbx
  __int64 v11; // rax
  DirectUI::Element *v12; // r13
  DirectUI::Element *v13; // rsi
  const struct tagRECT *v14; // r12
  bool Visible; // al
  int v16; // ecx
  LONG left; // ecx
  int v18; // edi
  int v19; // esi
  bool v20; // bl
  int v21; // edi
  LONG bottom; // edi
  int v23; // r14d
  struct DirectUI::Surface *v24; // r9
  int v25; // eax
  struct DirectUI::Value *v27; // [rsp+30h] [rbp-41h] BYREF
  struct DirectUI::Value *v28; // [rsp+38h] [rbp-39h] BYREF
  struct DirectUI::Value *v29; // [rsp+40h] [rbp-31h] BYREF
  __int64 v30; // [rsp+48h] [rbp-29h] BYREF
  const struct tagRECT *Margin; // [rsp+50h] [rbp-21h]
  DirectUI::Element *v32; // [rsp+58h] [rbp-19h]
  const struct tagRECT *v33; // [rsp+60h] [rbp-11h]
  char v34; // [rsp+68h] [rbp-9h] BYREF
  int v35; // [rsp+6Ch] [rbp-5h]
  char v36; // [rsp+70h] [rbp-1h] BYREF
  int v37; // [rsp+74h] [rbp+3h]
  int v38; // [rsp+D8h] [rbp+67h] BYREF
  int v39; // [rsp+DCh] [rbp+6Bh]

  v4 = (unsigned int)a4;
  *(_QWORD *)a2 = 0;
  *(_DWORD *)a2 = a3;
  v30 = 0;
  Children = DirectUI::Element::GetChildren(this, &v30);
  v8 = (_QWORD *)(Children + 8);
  v9 = *(_DWORD *)Children & 0x10000000;
  v10 = *(DirectUI::Element **)(Children + 8);
  if ( v9 )
  {
    v11 = *(_QWORD *)(Children + 8);
    v10 = *(DirectUI::Element **)v10;
  }
  else
  {
    v11 = Children + 8;
  }
  v12 = *(DirectUI::Element **)(v11 + 8);
  if ( v9 )
    v8 = (_QWORD *)*v8;
  v32 = (DirectUI::Element *)v8[2];
  v13 = v32;
  v29 = 0;
  Margin = DirectUI::Element::GetMargin(v10, &v29);
  v28 = 0;
  v14 = DirectUI::Element::GetMargin(v12, &v28);
  v27 = 0;
  v33 = DirectUI::Element::GetMargin(v13, &v27);
  DirectUI::Element::_UpdateDesiredSize(v10, (unsigned int)&v38, a3, (struct DirectUI::Surface *)v4);
  Visible = DirectUI::Element::GetVisible(v10);
  v16 = 0;
  if ( Visible )
  {
    left = v14->left;
    if ( v14->left <= Margin->right )
      left = Margin->right;
    v16 = v38 + left;
  }
  v18 = a3 - v16;
  v19 = 0;
  if ( v18 >= 0 )
    v19 = v18;
  v20 = DirectUI::Element::GetVisible(v32);
  DirectUI::Element::_UpdateDesiredSize(v32, (unsigned int)&v34, v19, (struct DirectUI::Surface *)v4);
  v21 = 0;
  if ( v20 )
  {
    bottom = v14->bottom;
    if ( bottom <= v33->top )
      bottom = v33->top;
    v21 = v35 + bottom;
  }
  v23 = v4 - v21;
  v24 = 0;
  if ( v23 >= 0 )
    v24 = (struct DirectUI::Surface *)(unsigned int)v23;
  DirectUI::Element::_UpdateDesiredSize(v12, (unsigned int)&v36, v19, v24);
  v25 = v39;
  if ( v21 + v37 > v39 )
    v25 = v21 + v37;
  *(_DWORD *)(a2 + 4) = v25;
  CValuePtr::Release((CValuePtr *)&v27);
  CValuePtr::Release((CValuePtr *)&v28);
  CValuePtr::Release((CValuePtr *)&v29);
  CValuePtr::Release((CValuePtr *)&v30);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x180093240  push    rbp
0x180093242  push    rbx
0x180093243  push    rsi
0x180093244  push    rdi
0x180093245  push    r12
0x180093247  push    r13
0x180093249  push    r14
0x18009324b  push    r15
0x18009324d  lea     rbp, [rsp-17h]
0x180093252  sub     rsp, 88h
0x180093259  mov     r14d, r9d
0x18009325c  mov     edi, r8d
0x18009325f  mov     r15, rdx
0x180093262  xor     eax, eax
0x180093264  mov     [rdx], rax
0x180093267  mov     [rdx], r8d
0x18009326a  xor     r12d, r12d
0x18009326d  mov     [rbp+4Fh+var_78], r12
0x180093271  lea     rdx, [rbp+4Fh+var_78]
0x180093275  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18009327b  lea     rcx, [rax+8]
0x18009327f  mov     edx, [rax]
0x180093281  and     edx, 10000000h
0x180093287  mov     rbx, [rcx]
0x18009328a  jz      short loc_180093294
0x18009328c  mov     rax, rbx
0x18009328f  mov     rbx, [rbx]
0x180093292  jmp     short loc_180093297
0x180093294  mov     rax, rcx
0x180093297  mov     r13, [rax+8]
0x18009329b  test    edx, edx
0x18009329d  jz      short loc_1800932A2
0x18009329f  mov     rcx, [rcx]
0x1800932a2  mov     rsi, [rcx+10h]
0x1800932a6  mov     [rbp+4Fh+var_68], rsi
0x1800932aa  mov     [rbp+4Fh+var_80], r12
0x1800932ae  lea     rdx, [rbp+4Fh+var_80]
0x1800932b2  mov     rcx, rbx
0x1800932b5  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800932bb  mov     [rbp+4Fh+var_70], rax
0x1800932bf  mov     [rbp+4Fh+var_88], r12
0x1800932c3  lea     rdx, [rbp+4Fh+var_88]
0x1800932c7  mov     rcx, r13
0x1800932ca  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800932d0  mov     r12, rax
0x1800932d3  mov     [rbp+4Fh+var_90], 0
0x1800932db  lea     rdx, [rbp+4Fh+var_90]
0x1800932df  mov     rcx, rsi
0x1800932e2  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800932e8  mov     [rbp+4Fh+var_60], rax
0x1800932ec  mov     rcx, [rbp+4Fh+arg_20]
0x1800932f0  mov     [rsp+0C0h+var_A0], rcx
0x1800932f5  mov     r9d, r14d
0x1800932f8  mov     r8d, edi
0x1800932fb  lea     rdx, [rbp+4Fh+arg_8]
0x1800932ff  mov     rcx, rbx
0x180093302  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180093308  mov     rcx, rbx
0x18009330b  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180093311  xor     ecx, ecx
0x180093313  test    al, al
0x180093315  jz      short loc_180093329
0x180093317  mov     ecx, [r12]
0x18009331b  mov     rax, [rbp+4Fh+var_70]
0x18009331f  cmp     ecx, [rax+8]
0x180093322  cmovle  ecx, [rax+8]
0x180093326  add     ecx, [rbp+4Fh+arg_8]
0x180093329  sub     edi, ecx
0x18009332b  mov     esi, 0
0x180093330  cmovns  esi, edi
0x180093333  mov     rcx, [rbp+4Fh+var_68]
0x180093337  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x18009333d  mov     bl, al
0x18009333f  mov     rax, [rbp+4Fh+arg_20]
0x180093343  mov     [rsp+0C0h+var_A0], rax
0x180093348  mov     r9d, r14d
0x18009334b  mov     r8d, esi
0x18009334e  lea     rdx, [rbp+4Fh+var_58]
0x180093352  mov     rcx, [rbp+4Fh+var_68]
0x180093356  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009335c  xor     edi, edi
0x18009335e  test    bl, bl
0x180093360  jz      short loc_180093375
0x180093362  mov     edi, [r12+0Ch]
0x180093367  mov     rax, [rbp+4Fh+var_60]
0x18009336b  cmp     edi, [rax+4]
0x18009336e  cmovle  edi, [rax+4]
0x180093372  add     edi, [rbp+4Fh+var_54]
0x180093375  sub     r14d, edi
0x180093378  mov     r9d, 0
0x18009337e  cmovns  r9d, r14d
0x180093382  mov     rax, [rbp+4Fh+arg_20]
0x180093386  mov     [rsp+0C0h+var_A0], rax
0x18009338b  mov     r8d, esi
0x18009338e  lea     rdx, [rbp+4Fh+var_50]
0x180093392  mov     rcx, r13
0x180093395  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009339b  mov     ecx, [rbp+4Fh+var_4C]
0x18009339e  add     ecx, edi
0x1800933a0  mov     eax, [rbp+4Fh+arg_C]
0x1800933a3  cmp     ecx, eax
0x1800933a5  cmovg   eax, ecx
0x1800933a8  mov     [r15+4], eax
0x1800933ac  lea     rcx, [rbp+4Fh+var_90]; this
0x1800933b0  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800933b5  nop
0x1800933b6  lea     rcx, [rbp+4Fh+var_88]; this
0x1800933ba  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800933bf  nop
0x1800933c0  lea     rcx, [rbp+4Fh+var_80]; this
0x1800933c4  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800933c9  nop
0x1800933ca  lea     rcx, [rbp+4Fh+var_78]; this
0x1800933ce  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800933d3  mov     rax, r15
0x1800933d6  add     rsp, 88h
0x1800933dd  pop     r15
0x1800933df  pop     r14
0x1800933e1  pop     r13
0x1800933e3  pop     r12
0x1800933e5  pop     rdi
0x1800933e6  pop     rsi
0x1800933e7  pop     rbx
0x1800933e8  pop     rbp
0x1800933e9  retn
```
