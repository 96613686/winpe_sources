# LineScroller::GetViewableAreaOfDescendent(DirectUI::Element *,int,int)

- ea: `0x1800108e8`
- end: `0x180010aa4`
- name: `?GetViewableAreaOfDescendent@LineScroller@@QEAA?AUtagSIZE@@PEAVElement@DirectUI@@HH@Z`
- size: `444`
- prototype: `struct tagSIZE(LineScroller *__hidden this, struct DirectUI::Element *, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000af60`
- `0x1800ab330`

## callees

- `0x1800108e8`
- `0x180010aac`
- `0x180010b5c`
- `0x180016790`
- `0x1800a0b10`

## import_xrefs

- `DUI70!?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18001091d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001098b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800109ce`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001098b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800109ce`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18001097f`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800109c2`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18001097f`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800109c2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001092e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180010973`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800109b6`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001092e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180010973`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800109b6`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18001093f`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18001093f`
- `DUI70!?GetXScrollable@Viewer@DirectUI@@QEAA_NXZ` at `0x180010a5f`
- `DUI70!?GetXScrollable@Viewer@DirectUI@@QEAA_NXZ` at `0x180010a5f`
- `DUI70!?GetYScrollable@Viewer@DirectUI@@QEAA_NXZ` at `0x180010a76`
- `DUI70!?GetYScrollable@Viewer@DirectUI@@QEAA_NXZ` at `0x180010a76`
- `DUI70!?GetClassInfoPtr@Viewer@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010a30`
- `DUI70!?GetClassInfoPtr@Viewer@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010a30`

## pseudocode

```c
struct tagSIZE __fastcall LineScroller::GetViewableAreaOfDescendent(
        LineScroller *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3,
        int a4,
        int a5)
{
  DirectUI::Element *Ancestor; // rax
  DirectUI::Value *v10; // rbx
  DirectUI::Value *v11; // rdi
  bool Bool; // si
  int v13; // r14d
  DirectUI::Value *v14; // rsi
  bool v15; // di
  int v16; // r8d
  int v17; // ebp
  int v18; // ecx
  int v19; // edx
  struct DirectUI::IClassInfo *ClassInfoPtr; // rax
  struct DirectUI::Element *AncestorElement; // rax
  DirectUI::Viewer *v23; // rdi
  bool YScrollable; // al
  int v25; // ecx
  DirectUI::Value *Value; // [rsp+88h] [rbp+10h] BYREF

  *(_QWORD *)a2 = 0;
  Ancestor = (DirectUI::Element *)FindAncestorElement<LineViewer>(a3);
  if ( Ancestor )
  {
    Value = DirectUI::Element::GetValue(
              Ancestor,
              (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LastDSConstProp,
              1,
              0);
    v10 = (DirectUI::Value *)*DirectUI::Value::GetSize(Value);
    CValuePtr::~CValuePtr((CValuePtr *)&Value);
    Value = v10;
    v11 = DirectUI::Element::GetValue(this, LineScroller::RealXScrollableProp, 2, 0);
    Bool = DirectUI::Value::GetBool(v11);
    DirectUI::Value::Release(v11);
    if ( Bool )
      v13 = 0x7FFFFFFF - (_DWORD)v10;
    else
      v13 = (int)v10;
    v14 = DirectUI::Element::GetValue(this, LineScroller::RealYScrollableProp, 2, 0);
    v15 = DirectUI::Value::GetBool(v14);
    DirectUI::Value::Release(v14);
    v16 = HIDWORD(Value);
    if ( v15 )
      v17 = 0x7FFFFFFF - HIDWORD(v10);
    else
      v17 = HIDWORD(v10);
  }
  else
  {
    ClassInfoPtr = (struct DirectUI::IClassInfo *)DirectUI::Viewer::GetClassInfoPtr();
    AncestorElement = _FindAncestorElement(a3, ClassInfoPtr);
    v23 = AncestorElement;
    if ( !AncestorElement )
      return (struct tagSIZE)a2;
    Value = (DirectUI::Value *)DUI_GetElementLastDSConst(AncestorElement);
    LODWORD(v10) = (_DWORD)Value;
    v13 = (int)Value;
    if ( DirectUI::Viewer::GetXScrollable(v23) )
      v13 = 0x7FFFFFFF;
    YScrollable = DirectUI::Viewer::GetYScrollable(v23);
    v16 = HIDWORD(Value);
    v25 = HIDWORD(Value);
    if ( YScrollable )
      v25 = 0x7FFFFFFF;
    v17 = v25;
  }
  v18 = a4 + (_DWORD)v10 - v13;
  if ( v18 >= 0 )
  {
    if ( v18 > (int)v10 )
      v18 = (int)v10;
  }
  else
  {
    v18 = 0;
  }
  *(_DWORD *)a2 = v18;
  v19 = a5 + v16 - v17;
  if ( v19 >= 0 )
  {
    if ( v19 > v16 )
      v19 = v16;
  }
  else
  {
    v19 = 0;
  }
  *((_DWORD *)a2 + 1) = v19;
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800108e8  push    rbx
0x1800108ea  push    rbp
0x1800108eb  push    rsi
0x1800108ec  push    rdi
0x1800108ed  push    r12
0x1800108ef  push    r13
0x1800108f1  push    r14
0x1800108f3  push    r15
0x1800108f5  sub     rsp, 38h
0x1800108f9  mov     r12, rcx
0x1800108fc  mov     qword ptr [rdx], 0
0x180010903  mov     rcx, r8
0x180010906  mov     r13d, r9d
0x180010909  mov     rbx, r8
0x18001090c  mov     r15, rdx
0x18001090f  call    ??$FindAncestorElement@VLineViewer@@@@YAPEAVLineViewer@@PEAVElement@DirectUI@@@Z; FindAncestorElement<LineViewer>(DirectUI::Element *)
0x180010914  test    rax, rax
0x180010917  jz      loc_180010A30
0x18001091d  mov     rdx, cs:__imp_?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LastDSConstProp(void)
0x180010924  xor     r9d, r9d
0x180010927  mov     rcx, rax
0x18001092a  lea     r8d, [r9+1]
0x18001092e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180010934  mov     rcx, rax
0x180010937  mov     [rsp+78h+arg_8], rax
0x18001093f  call    cs:__imp_?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Value::GetSize(void)
0x180010945  lea     rcx, [rsp+78h+arg_8]; this
0x18001094d  mov     rbx, [rax]
0x180010950  mov     [rsp+78h+var_58], rbx
0x180010955  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18001095a  xor     r9d, r9d
0x18001095d  mov     [rsp+78h+arg_8], rbx
0x180010965  lea     rdx, ?RealXScrollableProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealXScrollableProp(void)
0x18001096c  mov     rcx, r12
0x18001096f  lea     r8d, [r9+2]
0x180010973  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180010979  mov     rcx, rax
0x18001097c  mov     rdi, rax
0x18001097f  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x180010985  mov     rcx, rdi
0x180010988  mov     sil, al
0x18001098b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180010991  mov     ebp, 7FFFFFFFh
0x180010996  test    sil, sil
0x180010999  jz      loc_180010A93
0x18001099f  mov     r14d, ebp
0x1800109a2  sub     r14d, ebx
0x1800109a5  xor     r9d, r9d
0x1800109a8  lea     rdx, ?RealYScrollableProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealYScrollableProp(void)
0x1800109af  mov     rcx, r12
0x1800109b2  lea     r8d, [r9+2]
0x1800109b6  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800109bc  mov     rcx, rax
0x1800109bf  mov     rsi, rax
0x1800109c2  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x1800109c8  mov     rcx, rsi
0x1800109cb  mov     dil, al
0x1800109ce  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800109d4  mov     r8d, dword ptr [rsp+78h+arg_8+4]
0x1800109dc  test    dil, dil
0x1800109df  jz      loc_180010A9B
0x1800109e5  sub     ebp, dword ptr [rsp+78h+var_58+4]
0x1800109e9  mov     ecx, ebx
0x1800109eb  sub     ecx, r14d
0x1800109ee  add     ecx, r13d
0x1800109f1  jns     short loc_180010A20
0x1800109f3  xor     ecx, ecx
0x1800109f5  mov     edx, r8d
0x1800109f8  mov     [r15], ecx
0x1800109fb  sub     edx, ebp
0x1800109fd  add     edx, [rsp+78h+arg_20]
0x180010a04  jns     short loc_180010A27
0x180010a06  xor     edx, edx
0x180010a08  mov     [r15+4], edx
0x180010a0c  mov     rax, r15
0x180010a0f  add     rsp, 38h
0x180010a13  pop     r15
0x180010a15  pop     r14
0x180010a17  pop     r13
0x180010a19  pop     r12
0x180010a1b  pop     rdi
0x180010a1c  pop     rsi
0x180010a1d  pop     rbp
0x180010a1e  pop     rbx
0x180010a1f  retn
0x180010a20  cmp     ecx, ebx
0x180010a22  cmovg   ecx, ebx
0x180010a25  jmp     short loc_1800109F5
0x180010a27  cmp     edx, r8d
0x180010a2a  cmovg   edx, r8d
0x180010a2e  jmp     short loc_180010A08
0x180010a30  call    cs:__imp_?GetClassInfoPtr@Viewer@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Viewer::GetClassInfoPtr(void)
0x180010a36  mov     rdx, rax; struct DirectUI::IClassInfo *
0x180010a39  mov     rcx, rbx; struct DirectUI::Element *
0x180010a3c  call    ?_FindAncestorElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindAncestorElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180010a41  mov     rdi, rax
0x180010a44  test    rax, rax
0x180010a47  jz      short loc_180010A0C
0x180010a49  mov     rcx, rax; struct DirectUI::Element *
0x180010a4c  call    ?DUI_GetElementLastDSConst@@YA?AUtagSIZE@@PEAVElement@DirectUI@@@Z; DUI_GetElementLastDSConst(DirectUI::Element *)
0x180010a51  mov     rcx, rdi
0x180010a54  mov     [rsp+78h+arg_8], rax
0x180010a5c  mov     rbx, rax
0x180010a5f  call    cs:__imp_?GetXScrollable@Viewer@DirectUI@@QEAA_NXZ; DirectUI::Viewer::GetXScrollable(void)
0x180010a65  mov     r14d, ebx
0x180010a68  mov     ebp, 7FFFFFFFh
0x180010a6d  test    al, al
0x180010a6f  mov     rcx, rdi
0x180010a72  cmovnz  r14d, ebp
0x180010a76  call    cs:__imp_?GetYScrollable@Viewer@DirectUI@@QEAA_NXZ; DirectUI::Viewer::GetYScrollable(void)
0x180010a7c  mov     r8d, dword ptr [rsp+78h+arg_8+4]
0x180010a84  test    al, al
0x180010a86  mov     ecx, r8d
0x180010a89  cmovnz  ecx, ebp
0x180010a8c  mov     ebp, ecx
0x180010a8e  jmp     loc_1800109E9
0x180010a93  mov     r14d, ebx
0x180010a96  jmp     loc_1800109A5
0x180010a9b  mov     ebp, dword ptr [rsp+78h+var_58+4]
0x180010a9f  jmp     loc_1800109E9
```
