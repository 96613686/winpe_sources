# FirstVisibleElementOnlyLayout::_UpdateDesiredSizeWorker(DirectUI::Element *,int,int,DirectUI::Surface *)

- ea: `0x18000eb10`
- end: `0x18000ee14`
- name: `?_UpdateDesiredSizeWorker@FirstVisibleElementOnlyLayout@@IEAA?AUtagSIZE@@PEAVElement@DirectUI@@HHPEAVSurface@4@@Z`
- size: `772`
- prototype: `struct tagSIZE __fastcall(FirstVisibleElementOnlyLayout *__hidden this, struct DirectUI::Element *, int, int, struct DirectUI::Surface *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e450`

## callees

- `0x18000eb10`
- `0x18000ee1c`
- `0x18000ee74`
- `0x18000fba0`
- `0x180210010`

## import_xrefs

- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000ec67`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000ec67`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18000ec72`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18000ec72`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ed2d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ed45`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ed2d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ed45`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18000eb48`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18000eb48`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000eb81`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000eb81`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ec47`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000ec47`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000eb91`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000eb91`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18000ecf3`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18000ecf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct tagSIZE __fastcall FirstVisibleElementOnlyLayout::_UpdateDesiredSizeWorker(
        FirstVisibleElementOnlyLayout *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3,
        int a4,
        struct DirectUI::Surface *a5)
{
  struct DirectUI::Element *v5; // rdi
  _DWORD *Children; // r15
  struct tagSIZE v8; // rbx
  DirectUI::Element *v9; // rax
  DirectUI::Value *Value; // r14
  const struct tagSIZE *Size; // rax
  __int64 v12; // r13
  int v13; // ecx
  _QWORD *v14; // rax
  int v15; // r14d
  _QWORD *v16; // rcx
  DirectUI::Element *v17; // r12
  __int64 v18; // rax
  int v19; // eax
  char v20; // dl
  UIProperty *v21; // rax
  int MaxPixelWidth; // eax
  LONG cy; // edi
  unsigned __int64 v24; // r9
  int cx; // r8d
  int v26; // eax
  LONG v27; // eax
  char ContentAlign; // di
  int v29; // r9d
  int v30; // r10d
  int v31; // edi
  LONG v32; // eax
  DirectUI::Value *v33; // rcx
  DirectUI::Value *v35; // [rsp+40h] [rbp-28h] BYREF
  struct tagSIZE v36; // [rsp+48h] [rbp-20h]
  DirectUI::Value *v37; // [rsp+50h] [rbp-18h]
  char v38; // [rsp+B0h] [rbp+48h]
  int v39; // [rsp+B8h] [rbp+50h] BYREF
  LONG v40; // [rsp+BCh] [rbp+54h]
  struct DirectUI::Element *v41; // [rsp+C0h] [rbp+58h]
  int v42; // [rsp+C8h] [rbp+60h]

  v42 = a4;
  v41 = a3;
  v5 = a3;
  *(_QWORD *)a2 = 0;
  v35 = 0;
  Children = (_DWORD *)DirectUI::Element::GetChildren(a3, &v35);
  if ( !Children )
    goto LABEL_33;
  v38 = 0;
  v8.cx = 0;
  v36 = 0;
  v37 = 0;
  v9 = (DirectUI::Element *)element_cast<UIBase>(v5);
  Value = DirectUI::Element::GetValue(v9, UIBase::VisibleMinSizeProp, 2, 0);
  v37 = Value;
  Size = DirectUI::Value::GetSize(Value);
  if ( Size )
  {
    v8 = *Size;
    v36 = v8;
    *(struct tagSIZE *)a2 = v8;
  }
  v12 = 0;
  v13 = *Children;
  if ( (*Children & 0xFFFFFFF) == 0 )
  {
LABEL_30:
    *(_QWORD *)a2 = 0;
    goto LABEL_31;
  }
  v14 = Children + 2;
  v15 = v42;
  do
  {
    if ( (v13 & 0x10000000) != 0 )
      v16 = (_QWORD *)*v14;
    else
      v16 = v14;
    v17 = (DirectUI::Element *)v16[v12];
    v18 = element_cast<UIProperty>(v17);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 360LL))(v18);
    v20 = v38;
    if ( !v38 )
    {
      if ( !v19 )
        goto LABEL_28;
      v38 = 1;
      v21 = (UIProperty *)element_cast<UIProperty>(v17);
      MaxPixelWidth = UIProperty::GetMaxPixelWidth(v21);
      if ( !MaxPixelWidth || v15 < MaxPixelWidth )
        MaxPixelWidth = v15;
      cy = v36.cy;
      v24 = (unsigned int)v36.cy;
      if ( (int)a5 > v36.cy )
        v24 = (unsigned int)a5;
      cx = v8.cx;
      if ( MaxPixelWidth > v8.cx )
        cx = MaxPixelWidth;
      DirectUI::Element::_UpdateDesiredSize(v17, (unsigned int)&v39, cx, (struct DirectUI::Surface *)v24);
      v26 = v8.cx;
      if ( v39 > v8.cx )
        v26 = v39;
      *(_DWORD *)a2 = v26;
      v27 = cy;
      if ( v40 > cy )
        v27 = v40;
      *((_DWORD *)a2 + 1) = v27;
      ContentAlign = DirectUI::Element::GetContentAlign(v17);
      if ( DirectUI::Element::IsRTL(v17) )
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
      v29 = 0;
      v30 = 0;
      if ( (ContentAlign & 3) == 1 )
      {
        if ( *(_DWORD *)a2 > v39 )
          v29 = *(_DWORD *)a2 / 2 - v39 / 2;
      }
      else if ( (ContentAlign & 3) == 2 && *(_DWORD *)a2 > v39 )
      {
        v29 = *(_DWORD *)a2 - v39;
      }
      v31 = ContentAlign & 0xC;
      if ( v31 == 4 )
      {
        v32 = *((_DWORD *)a2 + 1);
        if ( v32 > v40 )
          v30 = v32 / 2 - v40 / 2;
      }
      else if ( v31 == 8 && *((_DWORD *)a2 + 1) > v40 )
      {
        v30 = *((_DWORD *)a2 + 1) - v40;
      }
      v5 = v41;
      DirectUI::Layout::UpdateLayoutRect(v41, *(_DWORD *)a2, *((_DWORD *)a2 + 1), v17, v29, v30, v39, v40);
      goto LABEL_27;
    }
    if ( v19 )
    {
      DirectUI::Layout::UpdateLayoutRect(v5, *(_DWORD *)a2, *((_DWORD *)a2 + 1), v17, 0, 0, 0, 0);
LABEL_27:
      v20 = v38;
    }
LABEL_28:
    v12 = (unsigned int)(v12 + 1);
    v13 = *Children;
    v14 = Children + 2;
  }
  while ( (unsigned int)v12 < (*Children & 0xFFFFFFFu) );
  Value = v37;
  if ( !v20 )
    goto LABEL_30;
LABEL_31:
  if ( Value )
    DirectUI::Value::Release(Value);
LABEL_33:
  v33 = v35;
  if ( v35 )
  {
    v35 = 0;
    DirectUI::Value::Release(v33);
  }
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x18000eb10  mov     [rsp-40h+arg_18], r9d
0x18000eb15  mov     [rsp-40h+arg_10], r8
0x18000eb1a  mov     [rsp-40h+arg_0], rcx
0x18000eb1f  push    rbp
0x18000eb20  push    rbx
0x18000eb21  push    rsi
0x18000eb22  push    rdi
0x18000eb23  push    r12
0x18000eb25  push    r13
0x18000eb27  push    r14
0x18000eb29  push    r15
0x18000eb2b  mov     rbp, rsp
0x18000eb2e  sub     rsp, 68h
0x18000eb32  mov     rdi, r8
0x18000eb35  mov     rsi, rdx
0x18000eb38  xor     eax, eax
0x18000eb3a  mov     [rdx], rax
0x18000eb3d  mov     [rbp+var_28], rax
0x18000eb41  lea     rdx, [rbp+var_28]
0x18000eb45  mov     rcx, r8
0x18000eb48  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18000eb4e  mov     r15, rax
0x18000eb51  test    rax, rax
0x18000eb54  jz      loc_18000ED34
0x18000eb5a  mov     byte ptr [rbp+arg_0], 0
0x18000eb5e  xor     ebx, ebx
0x18000eb60  mov     [rbp+var_20], rbx
0x18000eb64  mov     [rbp+var_18], rbx
0x18000eb68  mov     rcx, rdi
0x18000eb6b  call    ??$element_cast@VUIBase@@@@YAPEAVUIBase@@PEAVElement@DirectUI@@@Z; element_cast<UIBase>(DirectUI::Element *)
0x18000eb70  xor     r9d, r9d
0x18000eb73  lea     r8d, [rbx+2]
0x18000eb77  lea     rdx, ?VisibleMinSizeProp@UIBase@@SAPEBUPropertyInfo@DirectUI@@XZ; UIBase::VisibleMinSizeProp(void)
0x18000eb7e  mov     rcx, rax
0x18000eb81  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000eb87  mov     r14, rax
0x18000eb8a  mov     [rbp+var_18], rax
0x18000eb8e  mov     rcx, rax
0x18000eb91  call    cs:__imp_?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Value::GetSize(void)
0x18000eb97  test    rax, rax
0x18000eb9a  jz      short loc_18000EBA6
0x18000eb9c  mov     rbx, [rax]
0x18000eb9f  mov     [rbp+var_20], rbx
0x18000eba3  mov     [rsi], rbx
0x18000eba6  xor     r13d, r13d
0x18000eba9  mov     ecx, [r15]
0x18000ebac  test    ecx, 0FFFFFFFh
0x18000ebb2  jbe     loc_18000ED1E
0x18000ebb8  lea     rax, [r15+8]
0x18000ebbc  mov     r14d, [rbp+arg_18]
0x18000ebc0  bt      ecx, 1Ch
0x18000ebc4  jnb     loc_18000EDB6
0x18000ebca  mov     rcx, [rax]
0x18000ebcd  mov     r12, [rcx+r13*8]
0x18000ebd1  mov     rcx, r12
0x18000ebd4  call    ??$element_cast@VUIProperty@@@@YAPEAVUIProperty@@PEAVElement@DirectUI@@@Z; element_cast<UIProperty>(DirectUI::Element *)
0x18000ebd9  mov     rdx, rax
0x18000ebdc  mov     rcx, [rax]
0x18000ebdf  mov     rax, [rcx+168h]
0x18000ebe6  mov     rcx, rdx
0x18000ebe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebee  mov     dl, byte ptr [rbp+arg_0]
0x18000ebf1  test    dl, dl
0x18000ebf3  jnz     loc_18000ED60
0x18000ebf9  test    eax, eax
0x18000ebfb  jz      loc_18000ECFC
0x18000ec01  mov     byte ptr [rbp+arg_0], 1
0x18000ec05  mov     rcx, r12
0x18000ec08  call    ??$element_cast@VUIProperty@@@@YAPEAVUIProperty@@PEAVElement@DirectUI@@@Z; element_cast<UIProperty>(DirectUI::Element *)
0x18000ec0d  mov     rcx, rax; this
0x18000ec10  call    ?GetMaxPixelWidth@UIProperty@@QEAAHXZ; UIProperty::GetMaxPixelWidth(void)
0x18000ec15  test    eax, eax
0x18000ec17  jnz     loc_18000EDA8
0x18000ec1d  mov     eax, r14d
0x18000ec20  mov     edi, dword ptr [rbp+var_20+4]
0x18000ec23  mov     r9d, edi
0x18000ec26  cmp     dword ptr [rbp+arg_20], edi
0x18000ec29  cmovg   r9d, dword ptr [rbp+arg_20]
0x18000ec2e  mov     r8d, ebx
0x18000ec31  cmp     eax, ebx
0x18000ec33  cmovg   r8d, eax
0x18000ec37  mov     rax, [rbp+arg_28]
0x18000ec3b  mov     [rsp+68h+var_48], rax
0x18000ec40  lea     rdx, [rbp+arg_8]
0x18000ec44  mov     rcx, r12
0x18000ec47  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18000ec4d  mov     eax, ebx
0x18000ec4f  cmp     dword ptr [rbp+arg_8], ebx
0x18000ec52  cmovg   eax, dword ptr [rbp+arg_8]
0x18000ec56  mov     [rsi], eax
0x18000ec58  mov     eax, edi
0x18000ec5a  cmp     dword ptr [rbp+arg_8+4], edi
0x18000ec5d  cmovg   eax, dword ptr [rbp+arg_8+4]
0x18000ec61  mov     [rsi+4], eax
0x18000ec64  mov     rcx, r12
0x18000ec67  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18000ec6d  mov     edi, eax
0x18000ec6f  mov     rcx, r12
0x18000ec72  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18000ec78  mov     r11d, 2
0x18000ec7e  test    al, al
0x18000ec80  jnz     loc_18000EDBE
0x18000ec86  xor     r9d, r9d
0x18000ec89  xor     r10d, r10d
0x18000ec8c  mov     edx, edi
0x18000ec8e  and     edx, 3
0x18000ec91  mov     rcx, [rbp+arg_8]
0x18000ec95  sub     edx, 1
0x18000ec98  jz      loc_18000EDF4
0x18000ec9e  cmp     edx, 1
0x18000eca1  jz      loc_18000EDE1
0x18000eca7  and     edi, 0Ch
0x18000ecaa  mov     r8d, dword ptr [rbp+arg_8+4]
0x18000ecae  cmp     edi, 4
0x18000ecb1  jnz     loc_18000ED89
0x18000ecb7  mov     eax, [rsi+4]
0x18000ecba  cmp     eax, r8d
0x18000ecbd  jle     short loc_18000ECD0
0x18000ecbf  cdq
0x18000ecc0  idiv    r11d
0x18000ecc3  mov     r10d, eax
0x18000ecc6  mov     eax, r8d
0x18000ecc9  cdq
0x18000ecca  idiv    r11d
0x18000eccd  sub     r10d, eax
0x18000ecd0  mov     [rsp+68h+var_30], r8d
0x18000ecd5  mov     [rsp+68h+var_38], ecx
0x18000ecd9  mov     [rsp+68h+var_40], r10d
0x18000ecde  mov     dword ptr [rsp+68h+var_48], r9d
0x18000ece3  mov     rdi, [rbp+arg_10]
0x18000ece7  mov     r9, r12
0x18000ecea  mov     r8d, [rsi+4]
0x18000ecee  mov     edx, [rsi]
0x18000ecf0  mov     rcx, rdi
0x18000ecf3  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18000ecf9  mov     dl, byte ptr [rbp+arg_0]
0x18000ecfc  inc     r13d
0x18000ecff  mov     ecx, [r15]
0x18000ed02  mov     eax, ecx
0x18000ed04  and     eax, 0FFFFFFFh
0x18000ed09  cmp     r13d, eax
0x18000ed0c  lea     rax, [r15+8]
0x18000ed10  jb      loc_18000EBC0
0x18000ed16  test    dl, dl
0x18000ed18  mov     r14, [rbp+var_18]
0x18000ed1c  jnz     short loc_18000ED25
0x18000ed1e  mov     qword ptr [rsi], 0
0x18000ed25  test    r14, r14
0x18000ed28  jz      short loc_18000ED34
0x18000ed2a  mov     rcx, r14
0x18000ed2d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ed33  nop
0x18000ed34  mov     rcx, [rbp+var_28]
0x18000ed38  test    rcx, rcx
0x18000ed3b  jz      short loc_18000ED4C
0x18000ed3d  mov     [rbp+var_28], 0
0x18000ed45  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ed4b  nop
0x18000ed4c  mov     rax, rsi
0x18000ed4f  add     rsp, 68h
0x18000ed53  pop     r15
0x18000ed55  pop     r14
0x18000ed57  pop     r13
0x18000ed59  pop     r12
0x18000ed5b  pop     rdi
0x18000ed5c  pop     rsi
0x18000ed5d  pop     rbx
0x18000ed5e  pop     rbp
0x18000ed5f  retn
0x18000ed60  test    eax, eax
0x18000ed62  jz      short loc_18000ECFC
0x18000ed64  mov     [rsp+68h+var_30], 0
0x18000ed6c  mov     [rsp+68h+var_38], 0
0x18000ed74  mov     [rsp+68h+var_40], 0
0x18000ed7c  mov     dword ptr [rsp+68h+var_48], 0
0x18000ed84  jmp     loc_18000ECE7
0x18000ed89  cmp     edi, 8
0x18000ed8c  jnz     loc_18000ECD0
0x18000ed92  cmp     [rsi+4], r8d
0x18000ed96  jle     loc_18000ECD0
0x18000ed9c  mov     r10d, [rsi+4]
0x18000eda0  sub     r10d, r8d
0x18000eda3  jmp     loc_18000ECD0
0x18000eda8  cmp     r14d, eax
0x18000edab  jge     loc_18000EC20
0x18000edb1  jmp     loc_18000EC1D
0x18000edb6  mov     rcx, rax
0x18000edb9  jmp     loc_18000EBCD
0x18000edbe  mov     eax, edi
0x18000edc0  and     eax, 3
0x18000edc3  jz      short loc_18000EDD6
0x18000edc5  cmp     eax, r11d
0x18000edc8  jnz     loc_18000EC86
0x18000edce  and     edi, 0FFFFFFFCh
0x18000edd1  jmp     loc_18000EC86
0x18000edd6  and     edi, 0FFFFFFFEh
0x18000edd9  or      edi, r11d
0x18000eddc  jmp     loc_18000EC86
0x18000ede1  cmp     [rsi], ecx
0x18000ede3  jle     loc_18000ECA7
0x18000ede9  mov     r9d, [rsi]
0x18000edec  sub     r9d, ecx
0x18000edef  jmp     loc_18000ECA7
0x18000edf4  cmp     [rsi], ecx
0x18000edf6  jle     loc_18000ECA7
0x18000edfc  mov     eax, [rsi]
0x18000edfe  cdq
0x18000edff  idiv    r11d
0x18000ee02  mov     r9d, eax
0x18000ee05  mov     eax, ecx
0x18000ee07  cdq
0x18000ee08  idiv    r11d
0x18000ee0b  sub     r9d, eax
0x18000ee0e  jmp     loc_18000ECA7
```
