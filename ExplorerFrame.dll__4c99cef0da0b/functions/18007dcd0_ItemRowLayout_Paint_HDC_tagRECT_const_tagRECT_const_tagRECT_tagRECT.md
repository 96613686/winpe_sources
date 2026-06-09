# ItemRowLayout::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x18007dcd0`
- end: `0x18007e072`
- name: `?Paint@ItemRowLayout@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU3@2@Z`
- size: `930`
- prototype: `void __usercall(ItemRowLayout *__hidden this@<rcx>, HDC@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fba0`
- `0x180015fe0`
- `0x180016790`
- `0x18007dcd0`
- `0x18007e078`
- `0x180081320`
- `0x18013f7d0`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18007dfcf`
- `USER32!IsRectEmpty` at `0x18007dfcf`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x18007e002`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x18007e002`
- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x18007de0a`
- `DUI70!?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ` at `0x18007de0a`
- `DUI70!?GetColorTrans@Value@DirectUI@@SAPEAV12@XZ` at `0x18007dda8`
- `DUI70!?GetColorTrans@Value@DirectUI@@SAPEAV12@XZ` at `0x18007dda8`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x18007dd1e`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x18007dd1e`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007de25`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007de9b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007dedc`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007de25`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007de9b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007dedc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007dd52`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007dd81`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007de44`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007e032`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007dd52`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007dd81`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007de44`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007e032`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18007dd44`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18007dd44`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18007de8a`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18007de8a`
- `DUI70!?GetBorderThickness@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18007decb`
- `DUI70!?GetBorderThickness@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18007decb`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18007ddc3`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18007ddc3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007dd38`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007dd68`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007ddf9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007dd38`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007dd68`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007ddf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ItemRowLayout::Paint(
        ItemRowLayout *this,
        HDC a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        struct tagRECT *a5)
{
  DirectUI::Value *Value; // rbx
  struct DirectUI::Value *v7; // r14
  _DWORD *Children; // r15
  int VirtualDirection; // r13d
  struct DirectUI::Value *v10; // rbx
  const struct tagRECT *Rect; // rax
  LONG left; // edi
  LONG right; // r12d
  bool IsRTL; // al
  LONG v15; // ecx
  LONG v16; // ebx
  LONG v17; // edx
  LONG v18; // eax
  LONG v19; // r8d
  bool v20; // zf
  unsigned int v21; // edi
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  int v24; // ebx
  unsigned __int64 ElementExtent; // rax
  int v26; // ebx
  LONG v27; // ecx
  LONG v28; // r9d
  LONG v29; // edx
  LONG v30; // edx
  LONG v31; // ecx
  LONG v32; // r9d
  LONG v33; // eax
  LONG v34; // eax
  DirectUI::Value *v35; // rcx
  LONG v36; // ecx
  LONG v37; // ecx
  LONG v38; // [rsp+40h] [rbp-89h]
  int v39; // [rsp+40h] [rbp-89h]
  struct DirectUI::Value *v40; // [rsp+48h] [rbp-81h] BYREF
  LONG bottom; // [rsp+50h] [rbp-79h]
  LONG top; // [rsp+54h] [rbp-75h]
  int Int; // [rsp+58h] [rbp-71h]
  int v44; // [rsp+5Ch] [rbp-6Dh]
  DirectUI::Value *v45; // [rsp+60h] [rbp-69h] BYREF
  struct DirectUI::Element *v46; // [rsp+68h] [rbp-61h]
  const struct tagRECT *v47; // [rsp+70h] [rbp-59h]
  HDC v48; // [rsp+78h] [rbp-51h]
  struct DirectUI::Value *v49; // [rsp+80h] [rbp-49h]
  struct tagRECT v50; // [rsp+88h] [rbp-41h] BYREF
  struct tagRECT v51; // [rsp+98h] [rbp-31h] BYREF
  struct tagRECT v52; // [rsp+A8h] [rbp-21h] BYREF
  RECT rc; // [rsp+B8h] [rbp-11h] BYREF

  v47 = a4;
  v48 = a2;
  v50 = 0;
  DirectUI::Element::Paint(this, a2, a3, a4, a5, &v50);
  Value = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorLineHeightProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  v7 = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorLineProp, 2, 0);
  v49 = v7;
  if ( Int > 0 && (struct DirectUI::Value *)DirectUI::Value::GetColorTrans() != v7 )
  {
    v45 = 0;
    Children = (_DWORD *)DirectUI::Element::GetChildren(this, &v45);
    if ( Children )
    {
      VirtualDirection = ItemLayout::GetVirtualDirection(this);
      v10 = DirectUI::Element::GetValue(this, ItemRowLayout::SeparatorPaddingProp, 2, 0);
      v40 = v10;
      Rect = DirectUI::Value::GetRect(v10);
      left = Rect->left;
      top = Rect->top;
      right = Rect->right;
      bottom = Rect->bottom;
      IsRTL = DirectUI::Element::IsRTL(this);
      v15 = left;
      if ( !IsRTL )
        v15 = right;
      v38 = v15;
      if ( !IsRTL )
        right = left;
      if ( v10 )
      {
        DirectUI::Value::Release(v10);
        v15 = v38;
      }
      v16 = v15;
      v17 = bottom;
      if ( VirtualDirection != 1 )
        v16 = bottom;
      v18 = top;
      v19 = top;
      if ( VirtualDirection != 1 )
        v19 = right;
      top = v19;
      if ( VirtualDirection != 1 )
      {
        right = v18;
        v17 = v15;
      }
      bottom = v17;
      v52 = 0;
      v40 = 0;
      v52 = *DirectUI::Element::GetPadding(this, &v40);
      if ( DirectUI::Element::IsRTL(this) )
      {
        v37 = v52.left;
        v52.left = v52.right;
        v52.right = v37;
      }
      CValuePtr::~CValuePtr((CValuePtr *)&v40);
      v51 = 0;
      v40 = 0;
      v51 = *DirectUI::Element::GetBorderThickness(this, &v40);
      if ( DirectUI::Element::IsRTL(this) )
      {
        v36 = v51.left;
        v51.left = v51.right;
        v51.right = v36;
      }
      CValuePtr::~CValuePtr((CValuePtr *)&v40);
      v44 = Int + v16 + right;
      v39 = 0;
      v20 = (*Children & 0xFFFFFFF) == 0;
      LODWORD(v40) = *Children & 0xFFFFFFF;
      v21 = 0;
      if ( !v20 )
      {
        v22 = Children + 2;
        do
        {
          if ( (*Children & 0x10000000) != 0 )
            v23 = (_QWORD *)*v22;
          else
            v23 = v22;
          v46 = (struct DirectUI::Element *)v23[v21];
          v24 = *(_DWORD *)(element_cast<UIBase>(v46) + 200);
          if ( v24 != (unsigned int)ItemLayout::GetItemCount(this) - 1 )
          {
            ElementExtent = (unsigned __int64)DUI_GetElementExtent(v46);
            if ( VirtualDirection != 1 )
              ElementExtent >>= 32;
            v26 = ElementExtent + v39;
            v27 = v50.top;
            v28 = v50.right;
            if ( VirtualDirection == 1 )
              v28 = v50.bottom;
            v29 = v50.left;
            if ( VirtualDirection != 1 )
              v29 = v50.top;
            v30 = right + v26 + v29;
            if ( VirtualDirection != 1 )
              v27 = v50.left;
            v31 = top + v27;
            v32 = v28 - bottom;
            v33 = v30;
            if ( VirtualDirection != 1 )
              v33 = v31;
            rc.left = v33;
            if ( VirtualDirection != 1 )
              v31 = v30;
            rc.top = v31;
            v34 = v30 + Int;
            if ( VirtualDirection != 1 )
              v34 = v32;
            rc.right = v34;
            if ( VirtualDirection != 1 )
              v32 = v30 + Int;
            rc.bottom = v32;
            if ( !IsRectEmpty(&rc) )
              DirectUI::Element::PaintBackground(this, v48, v7, &rc, v47, &v52, &v51);
            v39 = v26 + v44;
          }
          ++v21;
          v22 = Children + 2;
        }
        while ( v21 < (unsigned int)v40 );
      }
    }
    v35 = v45;
    if ( v45 )
    {
      v45 = 0;
      DirectUI::Value::Release(v35);
    }
  }
  if ( v7 )
    DirectUI::Value::Release(v7);
}

```

## disassembly

```asm
0x18007dcd0  push    rbp
0x18007dcd2  push    rbx
0x18007dcd3  push    rsi
0x18007dcd4  push    rdi
0x18007dcd5  push    r12
0x18007dcd7  push    r13
0x18007dcd9  push    r14
0x18007dcdb  push    r15
0x18007dcdd  lea     rbp, [rsp-0Fh]
0x18007dce2  sub     rsp, 0D8h
0x18007dce9  mov     rax, cs:__security_cookie
0x18007dcf0  xor     rax, rsp
0x18007dcf3  mov     [rbp+47h+var_48], rax
0x18007dcf7  mov     [rbp+47h+var_A0], r9
0x18007dcfb  mov     [rbp+47h+var_98], rdx
0x18007dcff  mov     rsi, rcx
0x18007dd02  mov     rax, [rbp+47h+arg_20]
0x18007dd06  xorps   xmm0, xmm0
0x18007dd09  movups  [rbp+47h+var_88], xmm0
0x18007dd0d  lea     rcx, [rbp+47h+var_88]
0x18007dd11  mov     [rsp+110h+var_E8], rcx
0x18007dd16  mov     [rsp+110h+var_F0], rax
0x18007dd1b  mov     rcx, rsi
0x18007dd1e  call    cs:__imp_?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z; DirectUI::Element::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)
0x18007dd24  xor     r9d, r9d
0x18007dd27  lea     r12d, [r9+2]
0x18007dd2b  mov     r8d, r12d
0x18007dd2e  lea     rdx, ?SeparatorLineHeightProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorLineHeightProp(void)
0x18007dd35  mov     rcx, rsi
0x18007dd38  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007dd3e  mov     rbx, rax
0x18007dd41  mov     rcx, rax
0x18007dd44  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18007dd4a  mov     edi, eax
0x18007dd4c  mov     [rbp+47h+var_B8], eax
0x18007dd4f  mov     rcx, rbx
0x18007dd52  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007dd58  xor     r9d, r9d
0x18007dd5b  mov     r8d, r12d
0x18007dd5e  lea     rdx, ?SeparatorLineProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorLineProp(void)
0x18007dd65  mov     rcx, rsi
0x18007dd68  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007dd6e  mov     r14, rax
0x18007dd71  mov     [rbp+47h+var_90], rax
0x18007dd75  test    edi, edi
0x18007dd77  jg      short loc_18007DDA8
0x18007dd79  test    r14, r14
0x18007dd7c  jz      short loc_18007DD88
0x18007dd7e  mov     rcx, r14
0x18007dd81  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007dd87  nop
0x18007dd88  mov     rcx, [rbp+47h+var_48]
0x18007dd8c  xor     rcx, rsp; StackCookie
0x18007dd8f  call    __security_check_cookie
0x18007dd94  add     rsp, 0D8h
0x18007dd9b  pop     r15
0x18007dd9d  pop     r14
0x18007dd9f  pop     r13
0x18007dda1  pop     r12
0x18007dda3  pop     rdi
0x18007dda4  pop     rsi
0x18007dda5  pop     rbx
0x18007dda6  pop     rbp
0x18007dda7  retn
0x18007dda8  call    cs:__imp_?GetColorTrans@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetColorTrans(void)
0x18007ddae  nop
0x18007ddaf  cmp     rax, r14
0x18007ddb2  jz      short loc_18007DD79
0x18007ddb4  mov     [rbp+47h+var_B0], 0
0x18007ddbc  lea     rdx, [rbp+47h+var_B0]
0x18007ddc0  mov     rcx, rsi
0x18007ddc3  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18007ddc9  mov     r15, rax
0x18007ddcc  test    rax, rax
0x18007ddcf  jz      loc_18007E021
0x18007ddd5  mov     rcx, rsi
0x18007ddd8  call    ?GetVirtualDirection@ItemLayout@@QEAA?AW4VIRTUALDIRECTION@@XZ; ItemLayout::GetVirtualDirection(void)
0x18007dddd  mov     r13d, eax
0x18007dde0  mov     [rsp+110h+var_C8], 0
0x18007dde9  xor     r9d, r9d
0x18007ddec  mov     r8d, r12d
0x18007ddef  lea     rdx, ?SeparatorPaddingProp@ItemRowLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemRowLayout::SeparatorPaddingProp(void)
0x18007ddf6  mov     rcx, rsi
0x18007ddf9  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007ddff  mov     rbx, rax
0x18007de02  mov     [rsp+110h+var_C8], rax
0x18007de07  mov     rcx, rax
0x18007de0a  call    cs:__imp_?GetRect@Value@DirectUI@@QEAAPEBUtagRECT@@XZ; DirectUI::Value::GetRect(void)
0x18007de10  mov     edi, [rax]
0x18007de12  mov     ecx, [rax+4]
0x18007de15  mov     [rbp+47h+var_BC], ecx
0x18007de18  mov     r12d, [rax+8]
0x18007de1c  mov     eax, [rax+0Ch]
0x18007de1f  mov     [rbp+47h+var_C0], eax
0x18007de22  mov     rcx, rsi
0x18007de25  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18007de2b  nop
0x18007de2c  mov     ecx, edi
0x18007de2e  test    al, al
0x18007de30  cmovz   ecx, r12d
0x18007de34  mov     [rsp+110h+var_D0], ecx
0x18007de38  cmovz   r12d, edi
0x18007de3c  test    rbx, rbx
0x18007de3f  jz      short loc_18007DE4E
0x18007de41  mov     rcx, rbx
0x18007de44  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007de4a  mov     ecx, [rsp+110h+var_D0]
0x18007de4e  mov     ebx, ecx
0x18007de50  cmp     r13d, 1
0x18007de54  mov     edx, [rbp+47h+var_C0]
0x18007de57  cmovnz  ebx, edx
0x18007de5a  mov     eax, [rbp+47h+var_BC]
0x18007de5d  mov     r8d, eax
0x18007de60  cmovnz  r8d, r12d
0x18007de64  mov     [rbp+47h+var_BC], r8d
0x18007de68  cmovnz  r12d, eax
0x18007de6c  cmovnz  edx, ecx
0x18007de6f  mov     [rbp+47h+var_C0], edx
0x18007de72  xorps   xmm0, xmm0
0x18007de75  movups  [rbp+47h+var_68], xmm0
0x18007de79  mov     [rsp+110h+var_C8], 0
0x18007de82  lea     rdx, [rsp+110h+var_C8]
0x18007de87  mov     rcx, rsi
0x18007de8a  call    cs:__imp_?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetPadding(DirectUI::Value * *)
0x18007de90  movups  xmm0, xmmword ptr [rax]
0x18007de93  movdqu  [rbp+47h+var_68], xmm0
0x18007de98  mov     rcx, rsi
0x18007de9b  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18007dea1  test    al, al
0x18007dea3  jnz     loc_18007E04F
0x18007dea9  lea     rcx, [rsp+110h+var_C8]; this
0x18007deae  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18007deb3  xorps   xmm0, xmm0
0x18007deb6  movups  [rbp+47h+var_78], xmm0
0x18007deba  mov     [rsp+110h+var_C8], 0
0x18007dec3  lea     rdx, [rsp+110h+var_C8]
0x18007dec8  mov     rcx, rsi
0x18007decb  call    cs:__imp_?GetBorderThickness@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetBorderThickness(DirectUI::Value * *)
0x18007ded1  movups  xmm0, xmmword ptr [rax]
0x18007ded4  movdqu  [rbp+47h+var_78], xmm0
0x18007ded9  mov     rcx, rsi
0x18007dedc  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18007dee2  test    al, al
0x18007dee4  jnz     loc_18007E03E
0x18007deea  lea     rcx, [rsp+110h+var_C8]; this
0x18007deef  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18007def4  lea     eax, [rbx+r12]
0x18007def8  add     eax, [rbp+47h+var_B8]
0x18007defb  mov     [rbp+47h+var_B4], eax
0x18007defe  mov     [rsp+110h+var_D0], 0
0x18007df06  mov     eax, [r15]
0x18007df09  and     eax, 0FFFFFFFh
0x18007df0e  mov     dword ptr [rsp+110h+var_C8], eax
0x18007df12  mov     edi, 0
0x18007df17  jbe     loc_18007E021
0x18007df1d  lea     rax, [r15+8]
0x18007df21  test    dword ptr [r15], 10000000h
0x18007df28  jz      loc_18007E060
0x18007df2e  mov     rcx, [rax]
0x18007df31  mov     eax, edi
0x18007df33  mov     rax, [rcx+rax*8]
0x18007df37  mov     [rbp+47h+var_A8], rax
0x18007df3b  mov     rcx, rax
0x18007df3e  call    ??$element_cast@VUIBase@@@@YAPEAVUIBase@@PEAVElement@DirectUI@@@Z; element_cast<UIBase>(DirectUI::Element *)
0x18007df43  mov     ebx, [rax+0C8h]
0x18007df49  mov     rcx, rsi; this
0x18007df4c  call    ?GetItemCount@ItemLayout@@QEAAHXZ; ItemLayout::GetItemCount(void)
0x18007df51  dec     eax
0x18007df53  cmp     ebx, eax
0x18007df55  jz      loc_18007E011
0x18007df5b  mov     rcx, [rbp+47h+var_A8]; struct DirectUI::Element *
0x18007df5f  call    ?DUI_GetElementExtent@@YA?AUtagSIZE@@PEAVElement@DirectUI@@@Z; DUI_GetElementExtent(DirectUI::Element *)
0x18007df64  mov     r10d, 1
0x18007df6a  cmp     r13d, r10d
0x18007df6d  jnz     loc_18007E068
0x18007df73  mov     ebx, [rsp+110h+var_D0]
0x18007df77  add     ebx, eax
0x18007df79  mov     ecx, dword ptr [rbp+47h+var_88+4]
0x18007df7c  mov     r9d, dword ptr [rbp+47h+var_88+8]
0x18007df80  cmp     r13d, r10d
0x18007df83  cmovz   r9d, dword ptr [rbp+47h+var_88+0Ch]
0x18007df88  mov     edx, dword ptr [rbp+47h+var_88]
0x18007df8b  cmovnz  edx, ecx
0x18007df8e  add     edx, ebx
0x18007df90  add     edx, r12d
0x18007df93  mov     r8d, [rbp+47h+var_B8]
0x18007df97  add     r8d, edx
0x18007df9a  cmp     r13d, r10d
0x18007df9d  cmovnz  ecx, dword ptr [rbp+47h+var_88]
0x18007dfa1  add     ecx, [rbp+47h+var_BC]
0x18007dfa4  sub     r9d, [rbp+47h+var_C0]
0x18007dfa8  mov     eax, edx
0x18007dfaa  cmp     r13d, r10d
0x18007dfad  cmovnz  eax, ecx
0x18007dfb0  mov     [rbp+47h+rc.left], eax
0x18007dfb3  cmovnz  ecx, edx
0x18007dfb6  mov     [rbp+47h+rc.top], ecx
0x18007dfb9  mov     eax, r8d
0x18007dfbc  cmovnz  eax, r9d
0x18007dfc0  mov     [rbp+47h+rc.right], eax
0x18007dfc3  cmovnz  r9d, r8d
0x18007dfc7  mov     [rbp+47h+rc.bottom], r9d
0x18007dfcb  lea     rcx, [rbp+47h+rc]; lprc
0x18007dfcf  call    cs:__imp_IsRectEmpty
0x18007dfd5  test    eax, eax
0x18007dfd7  jnz     short loc_18007E008
0x18007dfd9  lea     rax, [rbp+47h+var_78]
0x18007dfdd  mov     [rsp+110h+var_E0], rax
0x18007dfe2  lea     rax, [rbp+47h+var_68]
0x18007dfe6  mov     [rsp+110h+var_E8], rax
0x18007dfeb  mov     rax, [rbp+47h+var_A0]
0x18007dfef  mov     [rsp+110h+var_F0], rax
0x18007dff4  lea     r9, [rbp+47h+rc]
0x18007dff8  mov     r8, r14
0x18007dffb  mov     rdx, [rbp+47h+var_98]
0x18007dfff  mov     rcx, rsi
0x18007e002  call    cs:__imp_?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z; DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)
0x18007e008  mov     eax, [rbp+47h+var_B4]
0x18007e00b  add     eax, ebx
0x18007e00d  mov     [rsp+110h+var_D0], eax
0x18007e011  inc     edi
0x18007e013  cmp     edi, dword ptr [rsp+110h+var_C8]
0x18007e017  lea     rax, [r15+8]
0x18007e01b  jb      loc_18007DF21
0x18007e021  mov     rcx, [rbp+47h+var_B0]
0x18007e025  test    rcx, rcx
0x18007e028  jz      short loc_18007E039
0x18007e02a  mov     [rbp+47h+var_B0], 0
0x18007e032  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007e038  nop
0x18007e039  jmp     loc_18007DD79
0x18007e03e  mov     ecx, dword ptr [rbp+47h+var_78]
0x18007e041  mov     eax, dword ptr [rbp+47h+var_78+8]
0x18007e044  mov     dword ptr [rbp+47h+var_78], eax
0x18007e047  mov     dword ptr [rbp+47h+var_78+8], ecx
0x18007e04a  jmp     loc_18007DEEA
0x18007e04f  mov     ecx, dword ptr [rbp+47h+var_68]
0x18007e052  mov     eax, dword ptr [rbp+47h+var_68+8]
0x18007e055  mov     dword ptr [rbp+47h+var_68], eax
0x18007e058  mov     dword ptr [rbp+47h+var_68+8], ecx
0x18007e05b  jmp     loc_18007DEA9
0x18007e060  mov     rcx, rax
0x18007e063  jmp     loc_18007DF31
0x18007e068  shr     rax, 20h
0x18007e06c  jmp     loc_18007DF73
```
