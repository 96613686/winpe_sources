# UIBase::DrawTextHandleRTL(HWND__ *,Gdiplus::Graphics &,ushort const *,Gdiplus::Font const *,tagRECT const &,Gdiplus::StringFormat *,Gdiplus::Brush const *)

- ea: `0x18002b2f8`
- end: `0x18002b542`
- name: `?DrawTextHandleRTL@UIBase@@YAXPEAUHWND__@@AEAVGraphics@Gdiplus@@PEBGPEBVFont@4@AEBUtagRECT@@PEAVStringFormat@4@PEBVBrush@4@@Z`
- size: `586`
- prototype: `void __usercall(HWND hWnd@<rcx>, HWND this@<rdx>, wchar_t *String@<r8>, const unsigned __int16 *@<r9>, const struct Gdiplus::Font *, const struct tagRECT *, struct Gdiplus::StringFormat *, const struct Gdiplus::Brush *)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180005434`
- `0x180025248`
- `0x18002ad08`
- `0x180076fcc`

## callees

- `0x180004908`
- `0x180026724`
- `0x1800296f8`
- `0x18002b2f8`
- `0x18003cff4`
- `0x18003d5e4`
- `0x1800726a0`
- `0x1800729ac`
- `0x1800729d8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18002b410`
- `USER32!SystemParametersInfoW` at `0x18002b433`
- `USER32!SystemParametersInfoW` at `0x18002b410`
- `USER32!SystemParametersInfoW` at `0x18002b433`
- `USER32!GetWindowLongW` at `0x18002b393`
- `USER32!GetWindowLongW` at `0x18002b393`
- `gdiplus!GdipGetTextRenderingHint` at `0x18002b3e5`
- `gdiplus!GdipGetTextRenderingHint` at `0x18002b3e5`
- `gdiplus!GdipGetStringFormatDigitSubstitution` at `0x18002b367`
- `gdiplus!GdipGetStringFormatDigitSubstitution` at `0x18002b367`
- `gdiplus!GdipGetStringFormatFlags` at `0x18002b3b3`
- `gdiplus!GdipGetStringFormatFlags` at `0x18002b3b3`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002b316`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002b316`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UIBase::DrawTextHandleRTL(
        HWND hWnd,
        UIBase *this,
        wchar_t *String,
        const unsigned __int16 *a4,
        const struct Gdiplus::Font *a5,
        const struct tagRECT *a6,
        struct Gdiplus::StringFormat *a7)
{
  __int64 BaseStringManager; // rdx
  struct Base::String *v12; // r9
  LONG StringFormatDigitSubstitution; // eax
  __int64 v14; // rdx
  int v15; // r15d
  __int64 v16; // r8
  LONG StringFormatFlags; // eax
  char v18; // r13
  int TextRenderingHint; // eax
  unsigned int v20; // esi
  __int64 v21; // rdx
  const struct Gdiplus::Brush *v22; // [rsp+30h] [rbp-78h]
  unsigned int v23; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 v24[2]; // [rsp+44h] [rbp-64h] BYREF
  unsigned int pvParam; // [rsp+48h] [rbp-60h] BYREF
  int v26; // [rsp+4Ch] [rbp-5Ch] BYREF
  struct Gdiplus::Graphics *v27; // [rsp+50h] [rbp-58h] BYREF
  float v28[20]; // [rsp+58h] [rbp-50h] BYREF

  try
  {
    BaseStringManager = Base::String::GetBaseStringManager();
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v27, BaseStringManager);
    *(_DWORD *)v24 = 0;
    if ( UIBase::GetStringDigitSubstitute(String, v24, (enum Gdiplus::StringDigitSubstitute *)&v27, v12) )
      String = (wchar_t *)v27;
    v23 = 0;
    StringFormatDigitSubstitution = GdipGetStringFormatDigitSubstitution(*(_QWORD *)&a6->left, 0, &v23);
    if ( StringFormatDigitSubstitution )
      a6->right = StringFormatDigitSubstitution;
    v15 = *(_DWORD *)v24;
    if ( *(_DWORD *)v24 != v23 )
      Gdiplus::StringFormat::SetDigitSubstitution(a6, v14, *(unsigned int *)v24);
    if ( (GetWindowLongW(hWnd, -20) & 0x400000) != 0 )
    {
      *(_DWORD *)v24 = 0;
      StringFormatFlags = GdipGetStringFormatFlags(*(_QWORD *)&a6->left, v24);
      if ( StringFormatFlags )
        a6->right = StringFormatFlags;
      v18 = 1;
      Gdiplus::StringFormat::SetFormatFlags(a6, *(_DWORD *)v24 | 1u);
      pvParam = 0;
      TextRenderingHint = GdipGetTextRenderingHint(*(_QWORD *)this, &pvParam);
      if ( TextRenderingHint )
        *((_DWORD *)this + 2) = TextRenderingHint;
      v20 = pvParam;
      if ( pvParam == 5
        || !pvParam
        && (pvParam = 0, SystemParametersInfoW(0x4Au, 0, &pvParam, 0))
        && pvParam
        && (v26 = 0, SystemParametersInfoW(0x200Au, 0, &v26, 0))
        && (v26 & 2) != 0 )
      {
        Gdiplus::Graphics::SetTextRenderingHint(this, 4);
      }
      else
      {
        v18 = 0;
      }
      UIBase::DrawTextHorizontallyFlipped(this, (struct Gdiplus::Graphics *)String, a4, a5, a6, a7, v22);
      if ( v18 )
        Gdiplus::Graphics::SetTextRenderingHint(this, v20);
      Gdiplus::StringFormat::SetFormatFlags(a6, *(unsigned int *)v24);
    }
    else
    {
      v28[0] = (float)*(int *)a5;
      v28[1] = (float)*((int *)a5 + 1);
      v28[2] = (float)(*((_DWORD *)a5 + 2) - *(_DWORD *)a5);
      v28[3] = (float)(*((_DWORD *)a5 + 3) - *((_DWORD *)a5 + 1));
      Gdiplus::Graphics::DrawString(this, String, v16, a4, v28, a6, a7);
    }
    if ( v15 != v23 )
      Gdiplus::StringFormat::SetDigitSubstitution(a6, v21, v23);
    Base::String::~String((Base::String *)&v27);
  }
  catch ( Base::Exception )
  {
  }
}

```

## disassembly

```asm
0x18002b2f8  mov     [rsp+arg_18], r9
0x18002b2fd  push    rbx
0x18002b2fe  push    rsi
0x18002b2ff  push    rdi
0x18002b300  push    r12
0x18002b302  push    r13
0x18002b304  push    r15
0x18002b306  sub     rsp, 78h
0x18002b30a  mov     r13, r9
0x18002b30d  mov     r12, r8
0x18002b310  mov     rdi, rdx
0x18002b313  mov     rsi, rcx
0x18002b316  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002b31c  nop
0x18002b31d  mov     rdx, rax
0x18002b320  lea     rcx, [rsp+0A8h+var_58]
0x18002b325  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002b32a  nop
0x18002b32b  mov     dword ptr [rsp+0A8h+var_64], 0
0x18002b333  lea     r8, [rsp+0A8h+var_58]; enum Gdiplus::StringDigitSubstitute *
0x18002b338  lea     rdx, [rsp+0A8h+var_64]; unsigned __int16 *
0x18002b33d  mov     rcx, r12; String
0x18002b340  call    ?GetStringDigitSubstitute@UIBase@@YA_NPEBGPEAW4StringDigitSubstitute@Gdiplus@@PEAVString@Base@@@Z; UIBase::GetStringDigitSubstitute(ushort const *,Gdiplus::StringDigitSubstitute *,Base::String *)
0x18002b345  test    al, al
0x18002b347  cmovnz  r12, [rsp+0A8h+var_58]
0x18002b34d  mov     rbx, [rsp+0A8h+arg_28]
0x18002b355  mov     [rsp+0A8h+var_68], 0
0x18002b35d  lea     r8, [rsp+0A8h+var_68]
0x18002b362  xor     edx, edx
0x18002b364  mov     rcx, [rbx]
0x18002b367  call    cs:__imp_GdipGetStringFormatDigitSubstitution
0x18002b36d  test    eax, eax
0x18002b36f  jz      short loc_18002B374
0x18002b371  mov     [rbx+8], eax
0x18002b374  mov     r15d, dword ptr [rsp+0A8h+var_64]
0x18002b379  cmp     r15d, [rsp+0A8h+var_68]
0x18002b37e  jz      short loc_18002B38B
0x18002b380  mov     r8d, r15d
0x18002b383  mov     rcx, rbx
0x18002b386  call    ?SetDigitSubstitution@StringFormat@Gdiplus@@QEAA?AW4Status@2@GW4StringDigitSubstitute@2@@Z; Gdiplus::StringFormat::SetDigitSubstitution(ushort,Gdiplus::StringDigitSubstitute)
0x18002b38b  mov     edx, 0FFFFFFECh; nIndex
0x18002b390  mov     rcx, rsi; hWnd
0x18002b393  call    cs:__imp_GetWindowLongW
0x18002b399  bt      eax, 16h
0x18002b39d  jnb     loc_18002B4A0
0x18002b3a3  mov     dword ptr [rsp+0A8h+var_64], 0
0x18002b3ab  lea     rdx, [rsp+0A8h+var_64]
0x18002b3b0  mov     rcx, [rbx]
0x18002b3b3  call    cs:__imp_GdipGetStringFormatFlags
0x18002b3b9  test    eax, eax
0x18002b3bb  jz      short loc_18002B3C0
0x18002b3bd  mov     [rbx+8], eax
0x18002b3c0  mov     edx, dword ptr [rsp+0A8h+var_64]
0x18002b3c4  mov     r13d, 1
0x18002b3ca  or      edx, r13d
0x18002b3cd  mov     rcx, rbx
0x18002b3d0  call    ?SetFormatFlags@StringFormat@Gdiplus@@QEAA?AW4Status@2@H@Z; Gdiplus::StringFormat::SetFormatFlags(int)
0x18002b3d5  mov     [rsp+0A8h+pvParam], 0
0x18002b3dd  lea     rdx, [rsp+0A8h+pvParam]
0x18002b3e2  mov     rcx, [rdi]
0x18002b3e5  call    cs:__imp_GdipGetTextRenderingHint
0x18002b3eb  test    eax, eax
0x18002b3ed  jz      short loc_18002B3F2
0x18002b3ef  mov     [rdi+8], eax
0x18002b3f2  mov     esi, [rsp+0A8h+pvParam]
0x18002b3f6  cmp     esi, 5
0x18002b3f9  jz      short loc_18002B449
0x18002b3fb  test    esi, esi
0x18002b3fd  jnz     short loc_18002B444
0x18002b3ff  mov     [rsp+0A8h+pvParam], esi
0x18002b403  xor     r9d, r9d; fWinIni
0x18002b406  lea     r8, [rsp+0A8h+pvParam]; pvParam
0x18002b40b  xor     edx, edx; uiParam
0x18002b40d  lea     ecx, [rsi+4Ah]; uiAction
0x18002b410  call    cs:__imp_SystemParametersInfoW
0x18002b416  test    eax, eax
0x18002b418  jz      short loc_18002B444
0x18002b41a  cmp     [rsp+0A8h+pvParam], esi
0x18002b41e  jz      short loc_18002B444
0x18002b420  mov     [rsp+0A8h+var_5C], esi
0x18002b424  xor     r9d, r9d; fWinIni
0x18002b427  lea     r8, [rsp+0A8h+var_5C]; pvParam
0x18002b42c  xor     edx, edx; uiParam
0x18002b42e  mov     ecx, 200Ah; uiAction
0x18002b433  call    cs:__imp_SystemParametersInfoW
0x18002b439  test    eax, eax
0x18002b43b  jz      short loc_18002B444
0x18002b43d  test    byte ptr [rsp+0A8h+var_5C], 2
0x18002b442  jnz     short loc_18002B449
0x18002b444  xor     r13b, r13b
0x18002b447  jmp     short loc_18002B456
0x18002b449  mov     edx, 4
0x18002b44e  mov     rcx, rdi
0x18002b451  call    ?SetTextRenderingHint@Graphics@Gdiplus@@QEAA?AW4Status@2@W4TextRenderingHint@2@@Z; Gdiplus::Graphics::SetTextRenderingHint(Gdiplus::TextRenderingHint)
0x18002b456  mov     rax, [rsp+0A8h+arg_30]
0x18002b45e  mov     [rsp+0A8h+var_80], rax; struct Gdiplus::StringFormat *
0x18002b463  mov     [rsp+0A8h+var_88], rbx; struct tagRECT *
0x18002b468  mov     r9, [rsp+0A8h+arg_20]; struct Gdiplus::Font *
0x18002b470  mov     r8, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002b478  mov     rdx, r12; struct Gdiplus::Graphics *
0x18002b47b  mov     rcx, rdi; this
0x18002b47e  call    ?DrawTextHorizontallyFlipped@UIBase@@YAXAEAVGraphics@Gdiplus@@PEBGPEBVFont@3@AEBUtagRECT@@PEAVStringFormat@3@PEBVBrush@3@@Z; UIBase::DrawTextHorizontallyFlipped(Gdiplus::Graphics &,ushort const *,Gdiplus::Font const *,tagRECT const &,Gdiplus::StringFormat *,Gdiplus::Brush const *)
0x18002b483  test    r13b, r13b
0x18002b486  jz      short loc_18002B492
0x18002b488  mov     edx, esi
0x18002b48a  mov     rcx, rdi
0x18002b48d  call    ?SetTextRenderingHint@Graphics@Gdiplus@@QEAA?AW4Status@2@W4TextRenderingHint@2@@Z; Gdiplus::Graphics::SetTextRenderingHint(Gdiplus::TextRenderingHint)
0x18002b492  mov     edx, dword ptr [rsp+0A8h+var_64]
0x18002b496  mov     rcx, rbx
0x18002b499  call    ?SetFormatFlags@StringFormat@Gdiplus@@QEAA?AW4Status@2@H@Z; Gdiplus::StringFormat::SetFormatFlags(int)
0x18002b49e  jmp     short loc_18002B512
0x18002b4a0  mov     rcx, [rsp+0A8h+arg_20]
0x18002b4a8  movd    xmm0, dword ptr [rcx]
0x18002b4ac  cvtdq2ps xmm0, xmm0
0x18002b4af  movss   [rsp+0A8h+var_50], xmm0
0x18002b4b5  movd    xmm1, dword ptr [rcx+4]
0x18002b4ba  cvtdq2ps xmm1, xmm1
0x18002b4bd  movss   [rsp+0A8h+var_4C], xmm1
0x18002b4c3  mov     eax, [rcx+8]
0x18002b4c6  sub     eax, [rcx]
0x18002b4c8  movd    xmm0, eax
0x18002b4cc  cvtdq2ps xmm0, xmm0
0x18002b4cf  movss   [rsp+0A8h+var_48], xmm0
0x18002b4d5  mov     eax, [rcx+0Ch]
0x18002b4d8  sub     eax, [rcx+4]
0x18002b4db  movd    xmm0, eax
0x18002b4df  cvtdq2ps xmm0, xmm0
0x18002b4e2  movss   [rsp+0A8h+var_44], xmm0
0x18002b4e8  mov     rax, [rsp+0A8h+arg_30]
0x18002b4f0  mov     [rsp+0A8h+var_78], rax
0x18002b4f5  mov     [rsp+0A8h+var_80], rbx
0x18002b4fa  lea     rax, [rsp+0A8h+var_50]
0x18002b4ff  mov     [rsp+0A8h+var_88], rax
0x18002b504  mov     r9, r13
0x18002b507  mov     rdx, r12
0x18002b50a  mov     rcx, rdi
0x18002b50d  call    ?DrawString@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBGHPEBVFont@2@AEBVRectF@2@PEBVStringFormat@2@PEBVBrush@2@@Z; Gdiplus::Graphics::DrawString(ushort const *,int,Gdiplus::Font const *,Gdiplus::RectF const &,Gdiplus::StringFormat const *,Gdiplus::Brush const *)
0x18002b512  cmp     r15d, [rsp+0A8h+var_68]
0x18002b517  jz      short loc_18002B527
0x18002b519  mov     r8d, [rsp+0A8h+var_68]
0x18002b51e  mov     rcx, rbx
0x18002b521  call    ?SetDigitSubstitution@StringFormat@Gdiplus@@QEAA?AW4Status@2@GW4StringDigitSubstitute@2@@Z; Gdiplus::StringFormat::SetDigitSubstitution(ushort,Gdiplus::StringDigitSubstitute)
0x18002b526  nop
0x18002b527  lea     rcx, [rsp+0A8h+var_58]; this
0x18002b52c  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002b531  nop
0x18002b532  jmp     short $+2
0x18002b534  add     rsp, 78h
0x18002b538  pop     r15
0x18002b53a  pop     r13
0x18002b53c  pop     r12
0x18002b53e  pop     rdi
0x18002b53f  pop     rsi
0x18002b540  pop     rbx
0x18002b541  retn
```
