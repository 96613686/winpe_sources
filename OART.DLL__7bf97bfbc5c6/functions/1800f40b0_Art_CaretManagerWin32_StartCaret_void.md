# Art::CaretManagerWin32::StartCaret(void)

- ea: `0x1800f40b0`
- end: `0x1800f4797`
- name: `?StartCaret@CaretManagerWin32@Art@@EEAAXXZ`
- size: `1767`
- prototype: `void __fastcall(Art::CaretManagerWin32 *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x180009c30`
- `0x18001df54`
- `0x180024f50`
- `0x180030d88`
- `0x180037370`
- `0x180068980`
- `0x180070fe0`
- `0x1800713c0`
- `0x180071720`
- `0x1800f40b0`
- `0x1800f47a0`
- `0x1800f47dc`
- `0x180125dc0`
- `0x1802d38e4`
- `0x180369820`
- `0x180369e70`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x1800f4477`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x1800f4617`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x1800f4477`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x1800f4617`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x1800f437c`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x1800f437c`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1800f460b`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1800f460b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800f4767`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800f4767`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800f45e1`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800f45e1`
- `GDI32!DeleteObject` at `0x1800f471d`
- `GDI32!DeleteObject` at `0x1800f471d`
- `USER32!CreateCaret` at `0x1800f4491`
- `USER32!CreateCaret` at `0x1800f464d`
- `USER32!CreateCaret` at `0x1800f4491`
- `USER32!CreateCaret` at `0x1800f464d`
- `USER32!SetCaretPos` at `0x1800f44ad`
- `USER32!SetCaretPos` at `0x1800f4669`
- `USER32!SetCaretPos` at `0x1800f44ad`
- `USER32!SetCaretPos` at `0x1800f4669`
- `USER32!HideCaret` at `0x1800f470f`
- `USER32!HideCaret` at `0x1800f470f`
- `USER32!ShowCaret` at `0x1800f474f`
- `USER32!ShowCaret` at `0x1800f474f`

## pseudocode

```c
void __fastcall Art::CaretManagerWin32::StartCaret(Art::CaretManagerWin32 *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  HWND v4; // r13
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // r10
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // edx
  __int64 v24; // rcx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // r10
  volatile signed __int32 *v28; // rcx
  HBITMAP HBITMAPFromImage; // rbx
  int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  struct Ofc::CProxyPtrImpl *v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // rdx
  bool v37; // al
  unsigned int v38; // ebx
  __int64 v39; // r9
  Gfx *v40; // rax
  unsigned int v41; // r8d
  struct Ofc::CProxyPtrImpl *v42; // rax
  struct Ofc::CProxyPtrImpl **Checked; // rax
  struct Ofc::CProxyPtrImpl *v44; // rax
  HBITMAP *v45; // rdi
  HBITMAP v46; // rax
  unsigned int v47; // ebx
  __int64 v48; // r9
  __int64 v49; // rax
  Gfx **v50; // rax
  unsigned int v51; // r8d
  void *v52; // rax
  Art::IE2oView *v53; // rax
  Art::SelectionLayerNode *SelectionLayerNode; // rax
  Art::SelectionLayerNode *v55; // r15
  struct Ofc::CProxyPtrImpl *v56; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v57; // [rsp+38h] [rbp-1C0h] BYREF
  struct Ofc::CProxyPtrImpl *v58; // [rsp+40h] [rbp-1B8h] BYREF
  HBITMAP v59; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v60; // [rsp+50h] [rbp-1A8h] BYREF
  Ofc::CProxyPtrImpl *v61; // [rsp+58h] [rbp-1A0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-198h] BYREF
  int *v63; // [rsp+70h] [rbp-188h]
  struct Ofc::CProxyPtrImpl *v64; // [rsp+88h] [rbp-170h]
  char *v65; // [rsp+90h] [rbp-168h]
  Art::CaretManagerWin32 *v66; // [rsp+98h] [rbp-160h]
  int v67; // [rsp+A0h] [rbp-158h] BYREF
  __m128i v68; // [rsp+A4h] [rbp-154h]
  __int64 v69; // [rsp+B8h] [rbp-140h]
  __int128 v70; // [rsp+C0h] [rbp-138h]
  int v71; // [rsp+D0h] [rbp-128h]
  __int128 v72; // [rsp+D8h] [rbp-120h]
  int v73; // [rsp+E8h] [rbp-110h]
  __int16 v74; // [rsp+ECh] [rbp-10Ch]
  int v75; // [rsp+F0h] [rbp-108h] BYREF
  int v76; // [rsp+F4h] [rbp-104h]
  int v77; // [rsp+F8h] [rbp-100h]
  int v78; // [rsp+FCh] [rbp-FCh]
  _BYTE v79[120]; // [rsp+100h] [rbp-F8h] BYREF
  __int64 v80; // [rsp+178h] [rbp-80h]
  char v81; // [rsp+1A8h] [rbp-50h]

  v66 = this;
  Art::View::Info::Info((Art::View::Info *)v79);
  Art::View::Info::operator=(v79, *((_QWORD *)this + 1) + 40LL);
  if ( *((_BYTE *)this + 32) )
  {
    v65 = (char *)this + 33;
    if ( (*((_BYTE *)this + 33) || *((_BYTE *)this + 34))
      && Art::View::FActive(*((Art::View **)this + 1))
      && (v81 & 1) == 0 )
    {
      v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 224LL);
      if ( v2 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v2 + 16LL))(
          v2,
          &GUID_a2912880_a140_4113_9a75_6d2d6a4dffd5,
          &v60);
        v3 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(&v60);
        v4 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
        v5 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
        }
        (*(void (__fastcall **)(_QWORD, __m128i *, _QWORD, _QWORD, char))(**((_QWORD **)this + 2) + 272LL))(
          *((_QWORD *)this + 2),
          &si128,
          0,
          0,
          1);
        v6 = ((__int64 (*)(void))Ofc::Round<__int64,double>)();
        v9 = v6;
        if ( v6 < (__int64)0xFFFFFFFF80000000uLL )
        {
          v9 = 0xFFFFFFFF80000000uLL;
        }
        else if ( v6 > 0x7FFFFFFF )
        {
          v9 = 0x7FFFFFFF;
        }
        v10 = Ofc::Round<__int64,double>(0x7FFFFFFF, v7, v8, v9);
        v15 = v10;
        if ( v10 < v14 )
        {
          v15 = v14;
        }
        else if ( v10 > v11 )
        {
          v15 = v11;
        }
        v16 = Ofc::Round<__int64,double>(v11, v15, v12, v13);
        v21 = v16;
        if ( v16 < v20 )
        {
          v21 = v20;
        }
        else if ( v16 > v18 )
        {
          v21 = v18;
        }
        v22 = Ofc::Round<__int64,double>(v18, v17, v21, v19);
        if ( v22 < v27 )
        {
          LODWORD(v22) = v27;
        }
        else if ( v22 > v24 )
        {
          LODWORD(v22) = v24;
        }
        v75 = v22;
        v76 = v25;
        v77 = v23;
        v78 = v26;
        v57 = 0;
        v28 = *(volatile signed __int32 **)(*((_QWORD *)this + 1) + 56LL);
        if ( *((_DWORD *)v28 + 1) != (_DWORD)v27 )
          _InterlockedAdd(v28 + 1, 1u);
        v56 = (struct Ofc::CProxyPtrImpl *)v28;
        v61 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v28);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v56);
        if ( !*((_QWORD *)v61 + 2)
          || (v52 = Ofc::CProxyPtrImpl::GetChecked(v61),
              (*(unsigned __int8 (__fastcall **)(void *, int *, _BYTE *, __int64 *))(*(_QWORD *)v52 + 152LL))(
                v52,
                &v75,
                v79,
                &v57)) )
        {
          *((_BYTE *)this + 34) = 1;
          HBITMAPFromImage = 0;
          v59 = 0;
          v30 = v77 - v75;
          if ( v77 - v75 <= 0 || (v31 = v78 - v76, v78 - v76 <= 0) )
          {
            CreateCaret(v4, 0, v30, v78 - v76);
            SetCaretPos(v75 + v57, v76 + HIDWORD(v57));
          }
          else
          {
            v58 = (struct Ofc::CProxyPtrImpl *)__PAIR64__(v31, v30);
            si128.m128i_i64[0] = v80;
            v56 = (struct Ofc::CProxyPtrImpl *)__PAIR64__(v31, v30);
            v32 = 0;
            v33 = 2;
            do
            {
              *(_DWORD *)((char *)&v58 + v32) = *(_DWORD *)((char *)&v56 + v32);
              v32 += 4;
              --v33;
            }
            while ( v33 );
            Gfx::IBitmapTarget::Create(&v56, &v58, &si128, 1, 8);
            v34 = v56;
            v56 = 0;
            v64 = v34;
            v35 = 0;
            v36 = 4;
            do
            {
              si128.m128i_i32[v35] = *(int *)((char *)&v75 + v35 * 4);
              ++v35;
              --v36;
            }
            while ( v36 );
            v67 = 0;
            v68 = si128;
            v69 = 0;
            v70 = 0;
            v71 = 3;
            v72 = 0;
            v73 = 1;
            v74 = 256;
            si128.m128i_i64[0] = (__int64)this;
            si128.m128i_i64[1] = (__int64)&v75;
            v63 = &v67;
            sub_1802D38E4(v34, 0, &si128);
            if ( byte_180E1C7E0 < 0 )
              v37 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E1C7E0);
            else
              v37 = byte_180E1C7E0 != 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            if ( v37 )
            {
              v47 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
              v49 = (*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *))(v48 + 464))(v34);
              v50 = (Gfx **)GEL::IImage::Create(&si128, v49);
              HBITMAPFromImage = Gfx::CreateHBITMAPFromImage(*v50, (const struct GEL::IImage *)v47, v51);
              v59 = HBITMAPFromImage;
              if ( si128.m128i_i64[0] )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)si128.m128i_i64[0] + 8LL))(si128.m128i_i64[0]);
            }
            else
            {
              v38 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
              v40 = (Gfx *)(*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *))(v39 + 472))(v34);
              HBITMAPFromImage = Gfx::CreateHBITMAPFromImage(v40, (const struct GEL::IImage *)v38, v41);
              v59 = HBITMAPFromImage;
            }
            CreateCaret(v4, HBITMAPFromImage, 0, 0);
            SetCaretPos(v75 + v57, v76 + HIDWORD(v57));
            v42 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 3));
            v58 = v42;
            if ( *((_QWORD *)v42 + 2) )
            {
              Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v42);
              v44 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(Checked[20]);
              v56 = v44;
              if ( *((_QWORD *)v44 + 2) && *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v44) + 6) )
              {
                *((_BYTE *)this + 34) = 0;
                v53 = (Art::IE2oView *)Ofc::CProxyPtrImpl::GetChecked(v56);
                SelectionLayerNode = Art::IE2oView::GetSelectionLayerNode(v53);
                v55 = SelectionLayerNode;
                if ( *((_BYTE *)this + 35) )
                {
                  Art::SelectionLayerNode::SetCaretShape(
                    SelectionLayerNode,
                    *((struct Gfx::IShapeBuilder **)this + 2),
                    1);
                  *((_BYTE *)this + 35) = 0;
                }
                Art::SelectionLayerNode::ShowHideCaret(v55, 1);
                HideCaret(v4);
              }
              Ofc::CProxyPtrImpl::DtorStrongRelease(&v56);
            }
            if ( *((_BYTE *)this + 34) )
            {
              if ( ShowCaret(v4) )
                *((_BYTE *)this + 34) = 0;
              else
                MsoShipAssertTagProc(9176066);
            }
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v58);
            if ( v34 )
              (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v34 + 8LL))(v34);
          }
          *((_BYTE *)this + 33) = 0;
          v45 = (HBITMAP *)((char *)this + 40);
          Ofc::CHBitmap::Reset((Art::CaretManagerWin32 *)((char *)this + 40));
          if ( (HBITMAP *)((char *)this + 40) != &v59 )
          {
            Ofc::CHBitmap::Reset((Art::CaretManagerWin32 *)((char *)this + 40));
            v46 = *v45;
            *v45 = HBITMAPFromImage;
            HBITMAPFromImage = v46;
            v59 = v46;
          }
          if ( HBITMAPFromImage )
          {
            Ofc::CHBitmap::Reset((Art::CaretManagerWin32 *)((char *)this + 40));
            *v45 = HBITMAPFromImage;
          }
          Art::CaretManager::QueueTextSelectionChangedEvent(this);
          if ( HBITMAPFromImage )
            DeleteObject(HBITMAPFromImage);
        }
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v61);
      }
    }
  }
  Art::View::Info::~Info((Art::View::Info *)v79);
}

```

## disassembly

```asm
0x1800f40b0  mov     [rsp+arg_8], rbx
0x1800f40b5  mov     [rsp+arg_10], rsi
0x1800f40ba  push    rdi
0x1800f40bb  push    r12
0x1800f40bd  push    r13
0x1800f40bf  push    r14
0x1800f40c1  push    r15
0x1800f40c3  sub     rsp, 1D0h
0x1800f40ca  mov     rax, cs:__security_cookie
0x1800f40d1  xor     rax, rsp
0x1800f40d4  mov     [rsp+1F8h+var_38], rax
0x1800f40dc  mov     r14, rcx
0x1800f40df  mov     [rsp+1F8h+var_160], rcx
0x1800f40e7  xor     esi, esi
0x1800f40e9  lea     rcx, [rsp+1F8h+var_F8]; this
0x1800f40f1  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1800f40f6  mov     rdx, [r14+8]
0x1800f40fa  add     rdx, 28h ; '('
0x1800f40fe  lea     rcx, [rsp+1F8h+var_F8]
0x1800f4106  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1800f410b  cmp     [r14+20h], sil
0x1800f410f  jz      loc_1800F457A
0x1800f4115  lea     r12, [r14+21h]
0x1800f4119  mov     [rsp+1F8h+var_168], r12
0x1800f4121  cmp     [r12], sil
0x1800f4125  jz      loc_1800F4728
0x1800f412b  mov     rcx, [r14+8]; this
0x1800f412f  call    ?FActive@View@Art@@QEBA_NXZ; Art::View::FActive(void)
0x1800f4134  test    al, al
0x1800f4136  jz      loc_1800F457A
0x1800f413c  mov     r15d, 1
0x1800f4142  test    [rsp+1F8h+var_50], r15b
0x1800f414a  jnz     loc_1800F457A
0x1800f4150  mov     rax, [r14+8]
0x1800f4154  mov     rcx, [rax+0E0h]
0x1800f415b  test    rcx, rcx
0x1800f415e  jz      loc_1800F457A
0x1800f4164  mov     [rsp+1F8h+var_1A8], rsi
0x1800f4169  mov     rax, [rcx]
0x1800f416c  lea     r8, [rsp+1F8h+var_1A8]
0x1800f4171  lea     rdx, _GUID_a2912880_a140_4113_9a75_6d2d6a4dffd5
0x1800f4178  mov     rax, [rax+10h]
0x1800f417c  call    cs:__guard_dispatch_icall_fptr
0x1800f4182  lea     rcx, [rsp+1F8h+var_1A8]
0x1800f4187  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x1800f418c  mov     rdx, rax
0x1800f418f  mov     rcx, [rax]
0x1800f4192  mov     rax, [rcx+28h]
0x1800f4196  mov     rcx, rdx
0x1800f4199  call    cs:__guard_dispatch_icall_fptr
0x1800f419f  mov     r13, rax
0x1800f41a2  mov     rdx, [rsp+1F8h+var_1A8]
0x1800f41a7  test    rdx, rdx
0x1800f41aa  jz      short loc_1800F41C1
0x1800f41ac  mov     [rsp+1F8h+var_1A8], rsi
0x1800f41b1  mov     rcx, [rdx]
0x1800f41b4  mov     rax, [rcx+8]
0x1800f41b8  mov     rcx, rdx
0x1800f41bb  call    cs:__guard_dispatch_icall_fptr
0x1800f41c1  mov     rcx, [r14+10h]
0x1800f41c5  mov     rax, [rcx]
0x1800f41c8  mov     byte ptr [rsp+1F8h+var_1D8], r15b
0x1800f41cd  xor     r9d, r9d
0x1800f41d0  xor     r8d, r8d
0x1800f41d3  lea     rdx, [rsp+1F8h+var_198]
0x1800f41d8  mov     rax, [rax+110h]
0x1800f41df  call    cs:__guard_dispatch_icall_fptr
0x1800f41e5  movsd   xmm0, qword ptr [rax]
0x1800f41e9  comisd  xmm0, qword ptr [rax+10h]
0x1800f41ee  jbe     loc_1800F45B4
0x1800f41f4  xorps   xmm3, xmm3
0x1800f41f7  xorps   xmm2, xmm2
0x1800f41fa  movaps  xmm0, xmm2
0x1800f41fd  unpckhpd xmm0, xmm2
0x1800f4201  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1800f4206  mov     r9, rax
0x1800f4209  mov     r10, 0FFFFFFFF80000000h
0x1800f4210  mov     ecx, 7FFFFFFFh
0x1800f4215  cmp     rax, r10
0x1800f4218  jl      loc_1800F46B1
0x1800f421e  cmp     rax, rcx
0x1800f4221  cmovg   r9, rcx
0x1800f4225  movaps  xmm0, xmm2
0x1800f4228  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1800f422d  mov     rdx, rax
0x1800f4230  cmp     rax, r10
0x1800f4233  jl      loc_1800F46B9
0x1800f4239  cmp     rax, rcx
0x1800f423c  cmovg   rdx, rcx
0x1800f4240  movaps  xmm0, xmm3
0x1800f4243  unpckhpd xmm0, xmm3
0x1800f4247  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1800f424c  mov     r8, rax
0x1800f424f  cmp     rax, r10
0x1800f4252  jl      loc_1800F46C1
0x1800f4258  cmp     rax, rcx
0x1800f425b  cmovg   r8, rcx
0x1800f425f  movaps  xmm0, xmm3
0x1800f4262  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1800f4267  cmp     rax, r10
0x1800f426a  jl      loc_1800F46C9
0x1800f4270  cmp     rax, rcx
0x1800f4273  cmovg   rax, rcx
0x1800f4277  mov     [rsp+1F8h+var_108], eax
0x1800f427e  mov     [rsp+1F8h+var_104], r8d
0x1800f4286  mov     [rsp+1F8h+var_100], edx
0x1800f428d  mov     [rsp+1F8h+var_FC], r9d
0x1800f4295  mov     [rsp+1F8h+var_1C0], rsi
0x1800f429a  mov     rax, rsi
0x1800f429d  mov     [rsp+1F8h+var_1C0], rax
0x1800f42a2  mov     rax, [r14+8]
0x1800f42a6  mov     rcx, [rax+38h]; struct Ofc::CProxyPtrImpl *
0x1800f42aa  mov     eax, [rcx+4]
0x1800f42ad  cmp     eax, r10d
0x1800f42b0  jnz     loc_1800F45D0
0x1800f42b6  mov     [rsp+1F8h+var_1C8], rcx
0x1800f42bb  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1800f42c0  mov     [rsp+1F8h+var_1A0], rax
0x1800f42c5  lea     rcx, [rsp+1F8h+var_1C8]; struct Ofc::CProxyPtrImpl **
0x1800f42ca  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800f42cf  mov     rcx, [rsp+1F8h+var_1A0]; this
0x1800f42d4  cmp     [rcx+10h], rsi
0x1800f42d8  jnz     loc_1800F4674
0x1800f42de  mov     [r14+22h], r15b
0x1800f42e2  mov     rbx, rsi
0x1800f42e5  mov     [rsp+1F8h+var_1B0], rbx
0x1800f42ea  mov     r8d, [rsp+1F8h+var_100]
0x1800f42f2  sub     r8d, [rsp+1F8h+var_108]; nWidth
0x1800f42fa  mov     r9d, [rsp+1F8h+var_FC]
0x1800f4302  mov     ecx, [rsp+1F8h+var_104]
0x1800f4309  test    r8d, r8d
0x1800f430c  jle     loc_1800F4645
0x1800f4312  mov     eax, r9d
0x1800f4315  sub     eax, ecx
0x1800f4317  test    eax, eax
0x1800f4319  jle     loc_1800F4645
0x1800f431f  mov     dword ptr [rsp+1F8h+var_1B8], r8d
0x1800f4324  mov     dword ptr [rsp+1F8h+var_1B8+4], eax
0x1800f4328  movsd   xmm0, [rsp+1F8h+var_80]
0x1800f4331  movsd   qword ptr [rsp+1F8h+var_198], xmm0
0x1800f4337  mov     dword ptr [rsp+1F8h+var_1C8], r8d
0x1800f433c  mov     rax, [rsp+1F8h+var_1B8]
0x1800f4341  shr     rax, 20h
0x1800f4345  mov     dword ptr [rsp+1F8h+var_1C8+4], eax
0x1800f4349  mov     rcx, rsi
0x1800f434c  mov     edx, 2
0x1800f4351  mov     eax, dword ptr [rsp+rcx+1F8h+var_1C8]
0x1800f4355  mov     dword ptr [rsp+rcx+1F8h+var_1B8], eax
0x1800f4359  lea     rcx, [rcx+4]
0x1800f435d  sub     rdx, r15
0x1800f4360  jnz     short loc_1800F4351
0x1800f4362  mov     [rsp+1F8h+var_1D8], 8
0x1800f436a  mov     r9d, r15d
0x1800f436d  lea     r8, [rsp+1F8h+var_198]
0x1800f4372  lea     rdx, [rsp+1F8h+var_1B8]
0x1800f4377  lea     rcx, [rsp+1F8h+var_1C8]
0x1800f437c  call    cs:__imp_?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,uint)
0x1800f4382  mov     rdi, [rsp+1F8h+var_1C8]
0x1800f4387  mov     [rsp+1F8h+var_1C8], rsi
0x1800f438c  mov     [rsp+1F8h+var_170], rdi
0x1800f4394  mov     rcx, rsi
0x1800f4397  mov     edx, 4
0x1800f439c  mov     eax, [rsp+rcx+1F8h+var_108]
0x1800f43a3  mov     dword ptr [rsp+rcx+1F8h+var_198], eax
0x1800f43a7  lea     rcx, [rcx+4]
0x1800f43ab  sub     rdx, r15
0x1800f43ae  jnz     short loc_1800F439C
0x1800f43b0  mov     [rsp+1F8h+var_158], esi
0x1800f43b7  movups  xmm0, [rsp+1F8h+var_198]
0x1800f43bc  movdqu  [rsp+1F8h+var_154], xmm0
0x1800f43c5  mov     [rsp+1F8h+var_140], rsi
0x1800f43cd  xorps   xmm1, xmm1
0x1800f43d0  movdqa  [rsp+1F8h+var_138], xmm1
0x1800f43d9  mov     [rsp+1F8h+var_128], 3
0x1800f43e4  xorps   xmm0, xmm0
0x1800f43e7  movups  [rsp+1F8h+var_120], xmm0
0x1800f43ef  mov     [rsp+1F8h+var_110], r15d
0x1800f43f7  mov     [rsp+1F8h+var_10C], 100h
0x1800f4401  mov     qword ptr [rsp+1F8h+var_198], r14
0x1800f4406  lea     rax, [rsp+1F8h+var_108]
0x1800f440e  mov     qword ptr [rsp+1F8h+var_198+8], rax
0x1800f4413  lea     rax, [rsp+1F8h+var_158]
0x1800f441b  mov     [rsp+1F8h+var_188], rax
0x1800f4420  lea     r8, [rsp+1F8h+var_198]
0x1800f4425  mov     rcx, rdi
0x1800f4428  call    sub_1802D38E4
0x1800f442d  mov     al, cs:byte_180E1C7E0
0x1800f4433  test    al, al
0x1800f4435  js      loc_1800F45DA
0x1800f443b  setnz   al
0x1800f443e  mov     r9, [rdi]
0x1800f4441  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x1800f4449  lea     rcx, [rsp+1F8h+var_198]; this
0x1800f444e  movups  [rsp+1F8h+var_198], xmm0
0x1800f4453  test    al, al
0x1800f4455  jnz     loc_1800F45EC
0x1800f445b  call    ?ToCOLORREF@Color@GEL@@QEBAKXZ; GEL::Color::ToCOLORREF(void)
0x1800f4460  mov     ebx, eax
0x1800f4462  mov     rcx, rdi
0x1800f4465  mov     rax, [r9+1D8h]
0x1800f446c  call    cs:__guard_dispatch_icall_fptr
0x1800f4472  mov     edx, ebx
0x1800f4474  mov     rcx, rax
0x1800f4477  call    cs:__imp_?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z; Gfx::CreateHBITMAPFromImage(GEL::IImage const &,ulong)
0x1800f447d  mov     rbx, rax
0x1800f4480  mov     [rsp+1F8h+var_1B0], rax
0x1800f4485  xor     r9d, r9d; nHeight
0x1800f4488  xor     r8d, r8d; nWidth
0x1800f448b  mov     rdx, rbx; hBitmap
0x1800f448e  mov     rcx, r13; hWnd
0x1800f4491  call    cs:__imp_CreateCaret
0x1800f4497  mov     edx, dword ptr [rsp+1F8h+var_1C0+4]
0x1800f449b  add     edx, [rsp+1F8h+var_104]; Y
0x1800f44a2  mov     ecx, dword ptr [rsp+1F8h+var_1C0]
0x1800f44a6  add     ecx, [rsp+1F8h+var_108]; X
0x1800f44ad  call    cs:__imp_SetCaretPos
0x1800f44b3  mov     rcx, [r14+18h]; struct Ofc::CProxyPtrImpl *
0x1800f44b7  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1800f44bc  mov     [rsp+1F8h+var_1B8], rax
0x1800f44c1  cmp     [rax+10h], rsi
0x1800f44c5  jz      short loc_1800F44F4
0x1800f44c7  mov     rcx, rax; this
0x1800f44ca  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800f44cf  mov     rcx, [rax+0A0h]; struct Ofc::CProxyPtrImpl *
0x1800f44d6  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1800f44db  mov     [rsp+1F8h+var_1C8], rax
0x1800f44e0  cmp     [rax+10h], rsi
0x1800f44e4  jnz     loc_1800F46D1
0x1800f44ea  lea     rcx, [rsp+1F8h+var_1C8]; struct Ofc::CProxyPtrImpl **
0x1800f44ef  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800f44f4  cmp     [r14+22h], sil
0x1800f44f8  jnz     loc_1800F474C
0x1800f44fe  lea     rcx, [rsp+1F8h+var_1B8]; struct Ofc::CProxyPtrImpl **
0x1800f4503  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800f4508  nop
0x1800f4509  test    rdi, rdi
0x1800f450c  jz      short loc_1800F451E
0x1800f450e  mov     rax, [rdi]
0x1800f4511  mov     rcx, rdi
0x1800f4514  mov     rax, [rax+8]
0x1800f4518  call    cs:__guard_dispatch_icall_fptr
0x1800f451e  mov     [r12], sil
0x1800f4522  lea     rdi, [r14+28h]
0x1800f4526  mov     rcx, rdi; this
0x1800f4529  call    ?Reset@CHBitmap@Ofc@@QEAAXXZ; Ofc::CHBitmap::Reset(void)
0x1800f452e  lea     rax, [rsp+1F8h+var_1B0]
0x1800f4533  cmp     rdi, rax
0x1800f4536  jz      short loc_1800F454E
0x1800f4538  mov     rcx, rdi; this
0x1800f453b  call    ?Reset@CHBitmap@Ofc@@QEAAXXZ; Ofc::CHBitmap::Reset(void)
0x1800f4540  mov     rax, [rdi]
0x1800f4543  mov     [rdi], rbx
0x1800f4546  mov     rbx, rax
0x1800f4549  mov     [rsp+1F8h+var_1B0], rax
0x1800f454e  test    rbx, rbx
0x1800f4551  jz      short loc_1800F455E
0x1800f4553  mov     rcx, rdi; this
0x1800f4556  call    ?Reset@CHBitmap@Ofc@@QEAAXXZ; Ofc::CHBitmap::Reset(void)
0x1800f455b  mov     [rdi], rbx
0x1800f455e  mov     rcx, r14; this
0x1800f4561  call    ?QueueTextSelectionChangedEvent@CaretManager@Art@@QEBAXXZ; Art::CaretManager::QueueTextSelectionChangedEvent(void)
0x1800f4566  test    rbx, rbx
0x1800f4569  jnz     loc_1800F471A
0x1800f456f  lea     rcx, [rsp+1F8h+var_1A0]; struct Ofc::CProxyPtrImpl **
0x1800f4574  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800f4579  nop
0x1800f457a  lea     rcx, [rsp+1F8h+var_F8]; this
0x1800f4582  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x1800f4587  mov     rcx, [rsp+1F8h+var_38]
0x1800f458f  xor     rcx, rsp; StackCookie
0x1800f4592  call    __security_check_cookie
0x1800f4597  lea     r11, [rsp+1F8h+var_28]
0x1800f459f  mov     rbx, [r11+38h]
0x1800f45a3  mov     rsi, [r11+40h]
0x1800f45a7  mov     rsp, r11
0x1800f45aa  pop     r15
0x1800f45ac  pop     r14
0x1800f45ae  pop     r13
0x1800f45b0  pop     r12
0x1800f45b2  pop     rdi
0x1800f45b3  retn
0x1800f45b4  movsd   xmm0, qword ptr [rax+8]
0x1800f45b9  comisd  xmm0, qword ptr [rax+18h]
0x1800f45be  ja      loc_1800F41F4
0x1800f45c4  movups  xmm3, xmmword ptr [rax]
0x1800f45c7  movups  xmm2, xmmword ptr [rax+10h]
0x1800f45cb  jmp     loc_1800F41FA
0x1800f45d0  lock add [rcx+4], r15d
0x1800f45d5  jmp     loc_1800F42B6
0x1800f45da  lea     rcx, byte_180E1C7E0
0x1800f45e1  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800f45e7  jmp     loc_1800F443E
0x1800f45ec  call    ?ToCOLORREF@Color@GEL@@QEBAKXZ; GEL::Color::ToCOLORREF(void)
0x1800f45f1  mov     ebx, eax
0x1800f45f3  mov     rcx, rdi
0x1800f45f6  mov     rax, [r9+1D0h]
0x1800f45fd  call    cs:__guard_dispatch_icall_fptr
0x1800f4603  mov     rdx, rax
0x1800f4606  lea     rcx, [rsp+1F8h+var_198]
0x1800f460b  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z; GEL::IImage::Create(ARC::IPlatformBitmap &)
  ... truncated ...
```
