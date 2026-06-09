# Jot::CDragIndicator::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)

- ea: `0x1400b35d0`
- end: `0x1400b3958`
- name: `?Paint@CDragIndicator@Jot@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z`
- size: `904`
- prototype: `void __fastcall(Jot::CDragIndicator *__hidden this, const struct PaintContext *, const struct tagRECT *, const struct tagRECT *, unsigned int, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400b35d0`
- `0x1400b3958`
- `0x1400b3970`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b3613`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b36dc`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b3707`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b3613`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b36dc`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x1400b3707`
- `gdiplus!GdipFillPath` at `0x1400b391d`
- `gdiplus!GdipFillPath` at `0x1400b391d`
- `gdiplus!GdipAddPathLineI` at `0x1400b3776`
- `gdiplus!GdipAddPathLineI` at `0x1400b37aa`
- `gdiplus!GdipAddPathLineI` at `0x1400b37d2`
- `gdiplus!GdipAddPathLineI` at `0x1400b37f5`
- `gdiplus!GdipAddPathLineI` at `0x1400b381f`
- `gdiplus!GdipAddPathLineI` at `0x1400b3851`
- `gdiplus!GdipAddPathLineI` at `0x1400b387e`
- `gdiplus!GdipAddPathLineI` at `0x1400b38a4`
- `gdiplus!GdipAddPathLineI` at `0x1400b38c5`
- `gdiplus!GdipAddPathLineI` at `0x1400b38ed`
- `gdiplus!GdipAddPathLineI` at `0x1400b3776`
- `gdiplus!GdipAddPathLineI` at `0x1400b37aa`
- `gdiplus!GdipAddPathLineI` at `0x1400b37d2`
- `gdiplus!GdipAddPathLineI` at `0x1400b37f5`
- `gdiplus!GdipAddPathLineI` at `0x1400b381f`
- `gdiplus!GdipAddPathLineI` at `0x1400b3851`
- `gdiplus!GdipAddPathLineI` at `0x1400b387e`
- `gdiplus!GdipAddPathLineI` at `0x1400b38a4`
- `gdiplus!GdipAddPathLineI` at `0x1400b38c5`
- `gdiplus!GdipAddPathLineI` at `0x1400b38ed`
- `gdiplus!GdipDeletePath` at `0x1400b3931`
- `gdiplus!GdipDeletePath` at `0x1400b3931`
- `gdiplus!GdipCreatePath` at `0x1400b3745`
- `gdiplus!GdipCreatePath` at `0x1400b3745`
- `gdiplus!GdipDeleteGraphics` at `0x1400b393a`
- `gdiplus!GdipDeleteGraphics` at `0x1400b393a`
- `gdiplus!GdipDeleteBrush` at `0x1400b3927`
- `gdiplus!GdipDeleteBrush` at `0x1400b3927`
- `gdiplus!GdipCreateSolidFill` at `0x1400b390c`
- `gdiplus!GdipCreateSolidFill` at `0x1400b390c`
- `gdiplus!GdipCreateFromHDC` at `0x1400b3609`
- `gdiplus!GdipCreateFromHDC` at `0x1400b3609`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1400b3680`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1400b3680`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z` at `0x1400b3637`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z` at `0x1400b3637`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1400b366c`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1400b366c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b3664`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b3664`

## pseudocode

```c
void __fastcall Jot::CDragIndicator::Paint(
        Jot::CDragIndicator *this,
        const struct PaintContext *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4)
{
  __int64 v6; // r13
  Jot *v7; // rcx
  NetUI::Fill *ForegroundColor; // rax
  unsigned int PrimaryARGBColor; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  Jot *v14; // rcx
  int PageLevel; // edi
  LONG right; // esi
  unsigned int v17; // r12d
  int v18; // edi
  unsigned int v19; // r14d
  int v20; // r15d
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // r14d
  int v24; // esi
  int v25; // eax
  int v26; // ecx
  unsigned int v27; // esi
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  unsigned int v33; // r15d
  unsigned int v34; // r14d
  unsigned int v35; // r12d
  int v36; // eax
  int v37; // ecx
  unsigned int v38; // esi
  int v39; // eax
  int v40; // ecx
  unsigned int v41; // edi
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ecx
  __int64 v48; // [rsp+30h] [rbp-20h] BYREF
  __int64 v49; // [rsp+38h] [rbp-18h] BYREF
  int v50; // [rsp+40h] [rbp-10h]
  struct NetUI::Value *v51; // [rsp+90h] [rbp+40h] BYREF
  unsigned int top; // [rsp+98h] [rbp+48h]
  int v53; // [rsp+A0h] [rbp+50h]

  *((_BYTE *)a2 + 48) = 1;
  v48 = 0;
  GdipCreateFromHDC(*((_QWORD *)a2 + 2), &v48, a3, a4);
  v6 = v48;
  if ( Jot::IsLicensedForFluentUI(v7) )
  {
    v51 = 0;
    ForegroundColor = NetUI::Element::GetForegroundColor(this, &v51);
    PrimaryARGBColor = NetUI::Fill::GetPrimaryARGBColor(ForegroundColor, this);
    v10 = PrimaryARGBColor & 0xFF00 | ((PrimaryARGBColor & 0xFFFFFF) >> 16) | ((PrimaryARGBColor | 0xFFFFFF00) << 16);
    if ( v51 )
      NetUI::BaseValue::Release(v51);
  }
  else
  {
    v11 = MsoFCbvHighContrast();
    v12 = 1894;
    if ( !v11 )
      v12 = 2993;
    v13 = MsoCrCbvGet(v12);
    v10 = v13 & 0xFF00 | BYTE2(v13) | (((unsigned __int8)v13 | 0xFFFFFF00) << 16);
  }
  v53 = a3->right - a3->left;
  LODWORD(v51) = (a3->bottom - a3->top) / 2;
  PageLevel = Jot::CDragIndicator::GetPageLevel(this);
  if ( PageLevel == -1 )
    PageLevel = 1;
  if ( (*((_BYTE *)this + 195) & 1) != 0 )
  {
    right = a3->right;
    if ( Jot::IsLicensedForFluentUI(v14) )
      v17 = right - 12 * PageLevel + 12;
    else
      v17 = right - 16 * PageLevel + 16;
  }
  else
  {
    right = a3->left;
    if ( Jot::IsLicensedForFluentUI(v14) )
      v17 = right + 12 * (PageLevel - 1);
    else
      v17 = 16 * PageLevel + right - 16;
  }
  top = a3->top;
  v18 = (int)v51;
  v19 = top + (_DWORD)v51;
  v49 = 0;
  v50 = GdipCreatePath(0, &v49);
  if ( (*((_BYTE *)this + 195) & 1) != 0 )
  {
    v20 = v17 - v18;
    v21 = GdipAddPathLineI(v49, v17, top, v17 - v18 - 1, v19);
    v22 = v50;
    if ( v21 )
      v22 = v21;
    v50 = v22;
    v23 = right - v53 + v18 + 2;
    v24 = v18 + top;
    v25 = GdipAddPathLineI(v49, (unsigned int)(v20 - 1), v18 + top, v23, v18 + top);
    v26 = v50;
    if ( v25 )
      v26 = v25;
    v50 = v26;
    v27 = v24 + 1;
    v28 = GdipAddPathLineI(v49, v23, v18 + top, v23, v27);
    v29 = v50;
    if ( v28 )
      v29 = v28;
    v50 = v29;
    v30 = GdipAddPathLineI(v49, v23, v27, (unsigned int)(v20 + 1), v27);
    v31 = v50;
    if ( v30 )
      v31 = v30;
    v50 = v31;
    v32 = GdipAddPathLineI(v49, (unsigned int)(v20 + 1), v27, v17, v18 + v18 + top);
    if ( v32 )
      v50 = v32;
  }
  else
  {
    v33 = v17 + v18;
    v34 = v17 + 1;
    v35 = top + v18;
    v36 = GdipAddPathLineI(v49, v34, top, v33 + 1, top + v18);
    v37 = v50;
    if ( v36 )
      v37 = v36;
    v50 = v37;
    v38 = v53 - 1 + right - v18;
    v39 = GdipAddPathLineI(v49, v33 + 1, v35, v38, v35);
    v40 = v50;
    if ( v39 )
      v40 = v39;
    v50 = v40;
    v41 = v35 + 1;
    v42 = GdipAddPathLineI(v49, v38, v35, v38, v35 + 1);
    v43 = v50;
    if ( v42 )
      v43 = v42;
    v50 = v43;
    v44 = GdipAddPathLineI(v49, v38, v41, v33, v35 + 1);
    v45 = v50;
    if ( v44 )
      v45 = v44;
    v50 = v45;
    v46 = GdipAddPathLineI(v49, v33, v41, v34, v35 + (unsigned int)v51);
    v47 = v50;
    if ( v46 )
      v47 = v46;
    v50 = v47;
  }
  v51 = 0;
  GdipCreateSolidFill(v10, &v51);
  GdipFillPath(v6, v51, v49);
  GdipDeleteBrush(v51);
  GdipDeletePath(v49);
  GdipDeleteGraphics(v6);
}

```

## disassembly

```asm
0x1400b35d0  mov     [rsp-38h+arg_18], rbx
0x1400b35d5  push    rbp
0x1400b35d6  push    rsi
0x1400b35d7  push    rdi
0x1400b35d8  push    r12
0x1400b35da  push    r13
0x1400b35dc  push    r14
0x1400b35de  push    r15
0x1400b35e0  mov     rbp, rsp
0x1400b35e3  sub     rsp, 50h
0x1400b35e7  mov     r14, r8
0x1400b35ea  mov     rax, rdx
0x1400b35ed  mov     r15, rcx
0x1400b35f0  mov     esi, 1
0x1400b35f5  mov     [rdx+30h], sil
0x1400b35f9  mov     [rbp+var_20], 0
0x1400b3601  lea     rdx, [rbp+var_20]
0x1400b3605  mov     rcx, [rax+10h]
0x1400b3609  call    cs:__imp_GdipCreateFromHDC
0x1400b360f  mov     r13, [rbp+var_20]
0x1400b3613  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x1400b3619  test    al, al
0x1400b361b  jz      short loc_1400B366C
0x1400b361d  mov     [rbp+arg_0], 0
0x1400b3625  lea     rdx, [rbp+arg_0]; struct NetUI::Value **
0x1400b3629  mov     rcx, r15; this
0x1400b362c  call    ?GetForegroundColor@Element@NetUI@@QEBAPEBUFill@2@PEAPEAVValue@2@@Z; NetUI::Element::GetForegroundColor(NetUI::Value * *)
0x1400b3631  mov     rdx, r15
0x1400b3634  mov     rcx, rax
0x1400b3637  call    cs:__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z; NetUI::Fill::GetPrimaryARGBColor(NetUI::Element const *)
0x1400b363d  and     eax, 0FFFFFFh
0x1400b3642  mov     ebx, eax
0x1400b3644  or      ebx, 0FFFFFF00h
0x1400b364a  shl     ebx, 10h
0x1400b364d  mov     ecx, eax
0x1400b364f  shr     ecx, 10h
0x1400b3652  or      ebx, ecx
0x1400b3654  and     eax, 0FF00h
0x1400b3659  or      ebx, eax
0x1400b365b  mov     rcx, [rbp+arg_0]
0x1400b365f  test    rcx, rcx
0x1400b3662  jz      short loc_1400B36A2
0x1400b3664  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1400b366a  jmp     short loc_1400B36A2
0x1400b366c  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x1400b3672  test    eax, eax
0x1400b3674  mov     ecx, 766h
0x1400b3679  jnz     short loc_1400B3680
0x1400b367b  mov     ecx, 0BB1h
0x1400b3680  call    cs:__imp_MsoCrCbvGet
0x1400b3686  movzx   ecx, ax
0x1400b3689  movzx   ebx, al
0x1400b368c  mov     edx, 0FFFFFF00h
0x1400b3691  shr     eax, 10h
0x1400b3694  or      ebx, edx
0x1400b3696  movzx   eax, al
0x1400b3699  shl     ebx, 10h
0x1400b369c  and     ecx, edx
0x1400b369e  or      ebx, eax
0x1400b36a0  or      ebx, ecx
0x1400b36a2  mov     eax, [r14+8]
0x1400b36a6  sub     eax, [r14]
0x1400b36a9  mov     [rbp+arg_10], eax
0x1400b36ac  mov     eax, [r14+0Ch]
0x1400b36b0  sub     eax, [r14+4]
0x1400b36b4  cdq
0x1400b36b5  mov     ecx, 2
0x1400b36ba  idiv    ecx
0x1400b36bc  mov     dword ptr [rbp+arg_0], eax
0x1400b36bf  mov     rcx, r15; this
0x1400b36c2  call    ?GetPageLevel@CDragIndicator@Jot@@QEBAHXZ; Jot::CDragIndicator::GetPageLevel(void)
0x1400b36c7  mov     edi, eax
0x1400b36c9  cmp     eax, 0FFFFFFFFh
0x1400b36cc  cmovz   edi, esi
0x1400b36cf  test    [r15+0C3h], sil
0x1400b36d6  jz      short loc_1400B3704
0x1400b36d8  mov     esi, [r14+8]
0x1400b36dc  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x1400b36e2  mov     r12d, esi
0x1400b36e5  test    al, al
0x1400b36e7  jz      short loc_1400B36F8
0x1400b36e9  lea     eax, [rdi+rdi*2]
0x1400b36ec  shl     eax, 2
0x1400b36ef  sub     r12d, eax
0x1400b36f2  add     r12d, 0Ch
0x1400b36f6  jmp     short loc_1400B3729
0x1400b36f8  shl     edi, 4
0x1400b36fb  sub     r12d, edi
0x1400b36fe  add     r12d, 10h
0x1400b3702  jmp     short loc_1400B3729
0x1400b3704  mov     esi, [r14]
0x1400b3707  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x1400b370d  test    al, al
0x1400b370f  jz      short loc_1400B371F
0x1400b3711  lea     r12d, [rdi-1]
0x1400b3715  lea     r12d, [r12+r12*2]
0x1400b3719  lea     r12d, [rsi+r12*4]
0x1400b371d  jmp     short loc_1400B3729
0x1400b371f  shl     edi, 4
0x1400b3722  lea     r12d, [rsi-10h]
0x1400b3726  add     r12d, edi
0x1400b3729  mov     eax, [r14+4]
0x1400b372d  mov     [rbp+arg_8], eax
0x1400b3730  mov     edi, dword ptr [rbp+arg_0]
0x1400b3733  lea     r14d, [rax+rdi]
0x1400b3737  mov     [rbp+var_18], 0
0x1400b373f  lea     rdx, [rbp+var_18]
0x1400b3743  xor     ecx, ecx
0x1400b3745  call    cs:__imp_GdipCreatePath
0x1400b374b  mov     [rbp+var_10], eax
0x1400b374e  mov     r8d, [rbp+arg_8]
0x1400b3752  mov     rcx, [rbp+var_18]
0x1400b3756  test    byte ptr [r15+0C3h], 1
0x1400b375e  jz      loc_1400B3835
0x1400b3764  mov     r15d, r12d
0x1400b3767  sub     r15d, edi
0x1400b376a  mov     [rsp+50h+var_30], r14d
0x1400b376f  lea     r9d, [r15-1]
0x1400b3773  mov     edx, r12d
0x1400b3776  call    cs:__imp_GdipAddPathLineI
0x1400b377c  mov     ecx, [rbp+var_10]
0x1400b377f  test    eax, eax
0x1400b3781  cmovnz  ecx, eax
0x1400b3784  mov     [rbp+var_10], ecx
0x1400b3787  sub     esi, [rbp+arg_10]
0x1400b378a  mov     ecx, edi
0x1400b378c  lea     r14d, [rcx+2]
0x1400b3790  add     r14d, esi
0x1400b3793  mov     esi, [rbp+arg_8]
0x1400b3796  add     esi, ecx
0x1400b3798  mov     [rsp+50h+var_30], esi
0x1400b379c  mov     r9d, r14d
0x1400b379f  mov     r8d, esi
0x1400b37a2  lea     edx, [r15-1]
0x1400b37a6  mov     rcx, [rbp+var_18]
0x1400b37aa  call    cs:__imp_GdipAddPathLineI
0x1400b37b0  mov     ecx, [rbp+var_10]
0x1400b37b3  test    eax, eax
0x1400b37b5  cmovnz  ecx, eax
0x1400b37b8  mov     [rbp+var_10], ecx
0x1400b37bb  inc     esi
0x1400b37bd  mov     [rsp+50h+var_30], esi
0x1400b37c1  mov     r9d, r14d
0x1400b37c4  mov     r8d, [rbp+arg_8]
0x1400b37c8  add     r8d, edi
0x1400b37cb  mov     edx, r14d
0x1400b37ce  mov     rcx, [rbp+var_18]
0x1400b37d2  call    cs:__imp_GdipAddPathLineI
0x1400b37d8  mov     ecx, [rbp+var_10]
0x1400b37db  test    eax, eax
0x1400b37dd  cmovnz  ecx, eax
0x1400b37e0  mov     [rbp+var_10], ecx
0x1400b37e3  mov     [rsp+50h+var_30], esi
0x1400b37e7  lea     r9d, [r15+1]
0x1400b37eb  mov     r8d, esi
0x1400b37ee  mov     edx, r14d
0x1400b37f1  mov     rcx, [rbp+var_18]
0x1400b37f5  call    cs:__imp_GdipAddPathLineI
0x1400b37fb  mov     ecx, [rbp+var_10]
0x1400b37fe  test    eax, eax
0x1400b3800  cmovnz  ecx, eax
0x1400b3803  mov     [rbp+var_10], ecx
0x1400b3806  mov     eax, [rbp+arg_8]
0x1400b3809  add     eax, edi
0x1400b380b  add     eax, edi
0x1400b380d  mov     [rsp+50h+var_30], eax
0x1400b3811  mov     r9d, r12d
0x1400b3814  mov     r8d, esi
0x1400b3817  lea     edx, [r15+1]
0x1400b381b  mov     rcx, [rbp+var_18]
0x1400b381f  call    cs:__imp_GdipAddPathLineI
0x1400b3825  test    eax, eax
0x1400b3827  jz      loc_1400B38FE
0x1400b382d  mov     [rbp+var_10], eax
0x1400b3830  jmp     loc_1400B38FE
0x1400b3835  lea     r15d, [r12+rdi]
0x1400b3839  lea     r14d, [r12+1]
0x1400b383e  mov     r12d, edi
0x1400b3841  add     r12d, [rbp+arg_8]
0x1400b3845  mov     [rsp+50h+var_30], r12d
0x1400b384a  lea     r9d, [r15+1]
0x1400b384e  mov     edx, r14d
0x1400b3851  call    cs:__imp_GdipAddPathLineI
0x1400b3857  mov     ecx, [rbp+var_10]
0x1400b385a  test    eax, eax
0x1400b385c  cmovnz  ecx, eax
0x1400b385f  mov     [rbp+var_10], ecx
0x1400b3862  sub     esi, edi
0x1400b3864  mov     eax, [rbp+arg_10]
0x1400b3867  dec     eax
0x1400b3869  add     esi, eax
0x1400b386b  mov     [rsp+50h+var_30], r12d
0x1400b3870  mov     r9d, esi
0x1400b3873  mov     r8d, r12d
0x1400b3876  lea     edx, [r15+1]
0x1400b387a  mov     rcx, [rbp+var_18]
0x1400b387e  call    cs:__imp_GdipAddPathLineI
0x1400b3884  mov     ecx, [rbp+var_10]
0x1400b3887  test    eax, eax
0x1400b3889  cmovnz  ecx, eax
0x1400b388c  mov     [rbp+var_10], ecx
0x1400b388f  lea     edi, [r12+1]
0x1400b3894  mov     [rsp+50h+var_30], edi
0x1400b3898  mov     r9d, esi
0x1400b389b  mov     r8d, r12d
0x1400b389e  mov     edx, esi
0x1400b38a0  mov     rcx, [rbp+var_18]
0x1400b38a4  call    cs:__imp_GdipAddPathLineI
0x1400b38aa  mov     ecx, [rbp+var_10]
0x1400b38ad  test    eax, eax
0x1400b38af  cmovnz  ecx, eax
0x1400b38b2  mov     [rbp+var_10], ecx
0x1400b38b5  mov     [rsp+50h+var_30], edi
0x1400b38b9  mov     r9d, r15d
0x1400b38bc  mov     r8d, edi
0x1400b38bf  mov     edx, esi
0x1400b38c1  mov     rcx, [rbp+var_18]
0x1400b38c5  call    cs:__imp_GdipAddPathLineI
0x1400b38cb  mov     ecx, [rbp+var_10]
0x1400b38ce  test    eax, eax
0x1400b38d0  cmovnz  ecx, eax
0x1400b38d3  mov     [rbp+var_10], ecx
0x1400b38d6  mov     eax, dword ptr [rbp+arg_0]
0x1400b38d9  add     eax, r12d
0x1400b38dc  mov     [rsp+50h+var_30], eax
0x1400b38e0  mov     r9d, r14d
0x1400b38e3  mov     r8d, edi
0x1400b38e6  mov     edx, r15d
0x1400b38e9  mov     rcx, [rbp+var_18]
0x1400b38ed  call    cs:__imp_GdipAddPathLineI
0x1400b38f3  mov     ecx, [rbp+var_10]
0x1400b38f6  test    eax, eax
0x1400b38f8  cmovnz  ecx, eax
0x1400b38fb  mov     [rbp+var_10], ecx
0x1400b38fe  mov     [rbp+arg_0], 0
0x1400b3906  lea     rdx, [rbp+arg_0]
0x1400b390a  mov     ecx, ebx
0x1400b390c  call    cs:__imp_GdipCreateSolidFill
0x1400b3912  mov     r8, [rbp+var_18]
0x1400b3916  mov     rdx, [rbp+arg_0]
0x1400b391a  mov     rcx, r13
0x1400b391d  call    cs:__imp_GdipFillPath
0x1400b3923  mov     rcx, [rbp+arg_0]
0x1400b3927  call    cs:__imp_GdipDeleteBrush
0x1400b392d  mov     rcx, [rbp+var_18]
0x1400b3931  call    cs:__imp_GdipDeletePath
0x1400b3937  mov     rcx, r13
0x1400b393a  call    cs:__imp_GdipDeleteGraphics
0x1400b3940  mov     rbx, [rsp+50h+arg_18]
0x1400b3948  add     rsp, 50h
0x1400b394c  pop     r15
0x1400b394e  pop     r14
0x1400b3950  pop     r13
0x1400b3952  pop     r12
0x1400b3954  pop     rdi
0x1400b3955  pop     rsi
0x1400b3956  pop     rbp
0x1400b3957  retn
```
