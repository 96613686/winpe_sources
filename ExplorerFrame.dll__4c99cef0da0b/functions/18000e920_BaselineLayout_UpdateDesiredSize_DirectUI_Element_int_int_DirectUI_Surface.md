# BaselineLayout::UpdateDesiredSize(DirectUI::Element *,int,int,DirectUI::Surface *)

- ea: `0x18000e920`
- end: `0x18000eb09`
- name: `?UpdateDesiredSize@BaselineLayout@@UEAA?AUtagSIZE@@PEAVElement@DirectUI@@HHPEAVSurface@4@@Z`
- size: `489`
- prototype: `struct tagSIZE __fastcall(BaselineLayout *__hidden this, struct DirectUI::Element *, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e920`
- `0x18000ee1c`
- `0x1801f8e74`
- `0x180210010`

## import_xrefs

- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18000e9b9`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18000e9d5`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18000e9b9`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x18000e9d5`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18000e986`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18000e986`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000ea47`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000ea47`
- `DUI70!StrToID` at `0x18000ea3b`
- `DUI70!StrToID` at `0x18000ea3b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ea99`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ea99`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18000e9a4`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18000e9a4`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ea08`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ea21`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000eace`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ea08`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ea21`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000eace`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct tagSIZE __fastcall BaselineLayout::UpdateDesiredSize(
        BaselineLayout *this,
        struct DirectUI::Element *a2,
        DirectUI::Element *a3,
        int a4,
        struct DirectUI::Surface *a5,
        struct DirectUI::Surface *a6)
{
  DirectUI::Element *v10; // rdi
  __int64 v11; // rax
  __int64 Children; // rbx
  DirectUI::Element *ChildFromLayoutIndex; // r12
  __int64 v14; // rax
  DirectUI::Element *v15; // r15
  struct DirectUI::Surface *v16; // r12
  unsigned __int16 v17; // ax
  struct DirectUI::Element *Descendent; // rax
  __int64 v19; // rax
  DirectUI::Element *v20; // rbx
  DirectUI::Element *v21; // rcx
  void (__fastcall *v22)(DirectUI::Element *, _QWORD); // rax
  DirectUI::Value *v23; // rcx
  int MaxLineHeight; // eax
  void (__fastcall *v26)(DirectUI::Element *, _QWORD); // r8
  char v27; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-Ch]
  char v29; // [rsp+38h] [rbp-8h] BYREF
  int v30; // [rsp+3Ch] [rbp-4h]
  DirectUI::Value *v31; // [rsp+88h] [rbp+48h] BYREF
  DirectUI::Element *v32; // [rsp+90h] [rbp+50h] BYREF

  *(_QWORD *)a2 = 0;
  v10 = 0;
  if ( a3 )
  {
    v11 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)a3 + 280LL))(a3);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v11 + 80LL))(
           v11,
           UIItem::Class) )
    {
      v10 = a3;
    }
  }
  if ( DirectUI::Layout::GetLayoutChildCount(this, a3) >= 2 )
  {
    v31 = 0;
    Children = DirectUI::Element::GetChildren(a3, &v31);
    ChildFromLayoutIndex = (DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(this, a3, 0, Children);
    v32 = ChildFromLayoutIndex;
    v14 = DirectUI::Layout::GetChildFromLayoutIndex(this, a3, 1, Children);
    v15 = (DirectUI::Element *)v14;
    if ( ChildFromLayoutIndex && v14 )
    {
      v16 = a6;
      DirectUI::Element::_UpdateDesiredSize(v32, (unsigned int)&v29, a4, (struct DirectUI::Surface *)(unsigned int)a5);
      DirectUI::Element::_UpdateDesiredSize(v15, (unsigned int)&v32, a4, (struct DirectUI::Surface *)(unsigned int)a5);
      *(_DWORD *)a2 = a4;
      *((_DWORD *)a2 + 1) = v30 + HIDWORD(v32);
      v17 = StrToID(L"footer");
      Descendent = DirectUI::Element::FindDescendent(a3, v17);
      v19 = element_cast<UIProperty>(Descendent);
      v20 = (DirectUI::Element *)v19;
      if ( !v19 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 360LL))(v19) )
      {
        v21 = v10;
        v22 = *(void (__fastcall **)(DirectUI::Element *, _QWORD))(*(_QWORD *)v10 + 416LL);
LABEL_10:
        v22(v21, 0);
        goto LABEL_11;
      }
      DirectUI::Element::_UpdateDesiredSize(v20, (unsigned int)&v27, a4, (struct DirectUI::Surface *)(unsigned int)a5);
      MaxLineHeight = GetMaxLineHeight(v15, v16);
      v26 = *(void (__fastcall **)(DirectUI::Element *, _QWORD))(*(_QWORD *)v10 + 416LL);
      v21 = v10;
      if ( SHIDWORD(v32) <= MaxLineHeight )
      {
        *((_DWORD *)a2 + 1) += v28;
        v22 = v26;
        goto LABEL_10;
      }
      (*(void (__fastcall **)(DirectUI::Element *, _QWORD))(*(_QWORD *)v10 + 416LL))(v10, v28);
    }
LABEL_11:
    v23 = v31;
    if ( v31 )
    {
      v31 = 0;
      DirectUI::Value::Release(v23);
    }
  }
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x18000e920  mov     [rsp-38h+arg_0], rbx
0x18000e925  push    rbp
0x18000e926  push    rsi
0x18000e927  push    rdi
0x18000e928  push    r12
0x18000e92a  push    r13
0x18000e92c  push    r14
0x18000e92e  push    r15
0x18000e930  mov     rbp, rsp
0x18000e933  sub     rsp, 40h
0x18000e937  mov     r13d, r9d
0x18000e93a  mov     rsi, r8
0x18000e93d  mov     r14, rdx
0x18000e940  mov     r15, rcx
0x18000e943  xor     eax, eax
0x18000e945  mov     [rdx], rax
0x18000e948  xor     edi, edi
0x18000e94a  test    r8, r8
0x18000e94d  jz      short loc_18000E980
0x18000e94f  mov     rax, [r8]
0x18000e952  mov     rcx, r8
0x18000e955  mov     rax, [rax+118h]
0x18000e95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e961  mov     r8, rax
0x18000e964  mov     rcx, [rax]
0x18000e967  mov     rax, [rcx+50h]
0x18000e96b  mov     rdx, cs:?Class@UIItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItem::Class
0x18000e972  mov     rcx, r8
0x18000e975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97a  test    al, al
0x18000e97c  cmovnz  rdi, rsi
0x18000e980  mov     rdx, rsi
0x18000e983  mov     rcx, r15
0x18000e986  call    cs:__imp_?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z; DirectUI::Layout::GetLayoutChildCount(DirectUI::Element *)
0x18000e98c  cmp     eax, 2
0x18000e98f  jb      loc_18000EAA0
0x18000e995  mov     [rbp+arg_8], 0
0x18000e99d  lea     rdx, [rbp+arg_8]
0x18000e9a1  mov     rcx, rsi
0x18000e9a4  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18000e9aa  mov     rbx, rax
0x18000e9ad  mov     r9, rax
0x18000e9b0  xor     r8d, r8d
0x18000e9b3  mov     rdx, rsi
0x18000e9b6  mov     rcx, r15
0x18000e9b9  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x18000e9bf  mov     r12, rax
0x18000e9c2  mov     [rbp+arg_10], rax
0x18000e9c6  mov     r9, rbx
0x18000e9c9  mov     r8d, 1
0x18000e9cf  mov     rdx, rsi
0x18000e9d2  mov     rcx, r15
0x18000e9d5  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x18000e9db  mov     r15, rax
0x18000e9de  test    r12, r12
0x18000e9e1  jz      loc_18000EA88
0x18000e9e7  test    rax, rax
0x18000e9ea  jz      loc_18000EA88
0x18000e9f0  mov     r12, [rbp+arg_28]
0x18000e9f4  mov     [rsp+40h+var_20], r12
0x18000e9f9  mov     r9d, dword ptr [rbp+arg_20]
0x18000e9fd  mov     r8d, r13d
0x18000ea00  lea     rdx, [rbp+var_8]
0x18000ea04  mov     rcx, [rbp+arg_10]
0x18000ea08  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18000ea0e  mov     [rsp+40h+var_20], r12
0x18000ea13  mov     r9d, dword ptr [rbp+arg_20]
0x18000ea17  mov     r8d, r13d
0x18000ea1a  lea     rdx, [rbp+arg_10]
0x18000ea1e  mov     rcx, r15
0x18000ea21  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18000ea27  mov     [r14], r13d
0x18000ea2a  mov     ecx, dword ptr [rbp+arg_10+4]
0x18000ea2d  add     ecx, [rbp+var_4]
0x18000ea30  mov     [r14+4], ecx
0x18000ea34  lea     rcx, aFooter; "footer"
0x18000ea3b  call    cs:__imp_StrToID
0x18000ea41  movzx   edx, ax
0x18000ea44  mov     rcx, rsi
0x18000ea47  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000ea4d  mov     rcx, rax
0x18000ea50  call    ??$element_cast@VUIProperty@@@@YAPEAVUIProperty@@PEAVElement@DirectUI@@@Z; element_cast<UIProperty>(DirectUI::Element *)
0x18000ea55  mov     rbx, rax
0x18000ea58  test    rax, rax
0x18000ea5b  jz      short loc_18000EA73
0x18000ea5d  mov     rcx, [rax]
0x18000ea60  mov     rax, [rcx+168h]
0x18000ea67  mov     rcx, rbx
0x18000ea6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea6f  test    eax, eax
0x18000ea71  jnz     short loc_18000EABB
0x18000ea73  mov     rax, [rdi]
0x18000ea76  mov     rcx, rdi
0x18000ea79  mov     rax, [rax+1A0h]
0x18000ea80  xor     edx, edx
0x18000ea82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea87  nop
0x18000ea88  mov     rcx, [rbp+arg_8]
0x18000ea8c  test    rcx, rcx
0x18000ea8f  jz      short loc_18000EAA0
0x18000ea91  mov     [rbp+arg_8], 0
0x18000ea99  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ea9f  nop
0x18000eaa0  mov     rax, r14
0x18000eaa3  mov     rbx, [rsp+40h+arg_0]
0x18000eaab  add     rsp, 40h
0x18000eaaf  pop     r15
0x18000eab1  pop     r14
0x18000eab3  pop     r13
0x18000eab5  pop     r12
0x18000eab7  pop     rdi
0x18000eab8  pop     rsi
0x18000eab9  pop     rbp
0x18000eaba  retn
0x18000eabb  mov     [rsp+40h+var_20], r12
0x18000eac0  mov     r9d, dword ptr [rbp+arg_20]
0x18000eac4  mov     r8d, r13d
0x18000eac7  lea     rdx, [rbp+var_10]
0x18000eacb  mov     rcx, rbx
0x18000eace  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18000ead4  mov     rdx, r12; struct DirectUI::Surface *
0x18000ead7  mov     rcx, r15; struct DirectUI::Element *
0x18000eada  call    ?GetMaxLineHeight@@YAHPEAVElement@DirectUI@@PEAVSurface@2@@Z; GetMaxLineHeight(DirectUI::Element *,DirectUI::Surface *)
0x18000eadf  mov     rdx, [rdi]
0x18000eae2  mov     r8, [rdx+1A0h]
0x18000eae9  mov     rcx, rdi
0x18000eaec  cmp     dword ptr [rbp+arg_10+4], eax
0x18000eaef  jg      short loc_18000EAFD
0x18000eaf1  mov     eax, [rbp+var_C]
0x18000eaf4  add     [r14+4], eax
0x18000eaf8  mov     rax, r8
0x18000eafb  jmp     short loc_18000EA80
0x18000eafd  mov     edx, [rbp+var_C]
0x18000eb00  mov     rax, r8
0x18000eb03  jmp     loc_18000EA82
```
