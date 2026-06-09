# Art::CaretManagerWin32::StartCaret(void)

- ea: `0x18029b1b0`
- end: `0x18029b816`
- name: `?StartCaret@CaretManagerWin32@Art@@EEAAXXZ`
- size: `1638`
- prototype: `void __fastcall(Art::CaretManagerWin32 *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x18000e858`
- `0x18003a234`
- `0x1800d1790`
- `0x18010de00`
- `0x18010fe70`
- `0x18011efe4`
- `0x1801cad80`
- `0x180278de0`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x18029ada4`
- `0x18029b1b0`
- `0x18029b960`
- `0x18029c3cc`
- `0x18029c604`
- `0x180387980`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x18029b5c9`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x18029b605`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x18029b5c9`
- `gfx!?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z` at `0x18029b605`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x18029b4c3`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x18029b4c3`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x18029b5f8`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x18029b5f8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18029b707`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18029b707`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18029b58e`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18029b58e`
- `GDI32!DeleteObject` at `0x18029b7ca`
- `GDI32!DeleteObject` at `0x18029b7ca`
- `USER32!CreateCaret` at `0x18029b636`
- `USER32!CreateCaret` at `0x18029b758`
- `USER32!CreateCaret` at `0x18029b636`
- `USER32!CreateCaret` at `0x18029b758`
- `USER32!SetCaretPos` at `0x18029b652`
- `USER32!SetCaretPos` at `0x18029b774`
- `USER32!SetCaretPos` at `0x18029b652`
- `USER32!SetCaretPos` at `0x18029b774`
- `USER32!HideCaret` at `0x18029b6d8`
- `USER32!HideCaret` at `0x18029b6d8`
- `USER32!ShowCaret` at `0x18029b6f2`
- `USER32!ShowCaret` at `0x18029b6f2`

## pseudocode

```c
void __fastcall Art::CaretManagerWin32::StartCaret(Art::CaretManagerWin32 *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  HWND v4; // r13
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // r9d
  int v15; // r10d
  void *v16; // rax
  HBITMAP HBITMAPFromImage; // rbx
  int v18; // r8d
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  struct Ofc::CProxyPtrImpl *v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rdx
  bool v25; // al
  unsigned int v26; // ebx
  __int64 v27; // r9
  Gfx *v28; // rax
  unsigned int v29; // r8d
  unsigned int v30; // ebx
  __int64 v31; // r9
  __int64 v32; // rax
  Gfx **v33; // rax
  unsigned int v34; // r8d
  struct Ofc::CProxyPtrImpl *v35; // rax
  struct Ofc::CProxyPtrImpl **Checked; // rax
  struct Ofc::CProxyPtrImpl *v37; // rax
  Art::IE2oView *v38; // rax
  Art::SelectionLayerNode *SelectionLayerNode; // rax
  Art::SelectionLayerNode *v40; // r15
  HBITMAP *v41; // rdi
  HBITMAP v42; // rax
  struct Ofc::CProxyPtrImpl *v43; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v44; // [rsp+38h] [rbp-1C0h] BYREF
  struct Ofc::CProxyPtrImpl *v45; // [rsp+40h] [rbp-1B8h] BYREF
  HBITMAP v46; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-1A8h] BYREF
  Ofc::CProxyPtrImpl *v48; // [rsp+58h] [rbp-1A0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-198h] BYREF
  int *v50; // [rsp+70h] [rbp-188h]
  struct Ofc::CProxyPtrImpl *v51; // [rsp+88h] [rbp-170h]
  Art::CaretManagerWin32 *v52; // [rsp+90h] [rbp-168h]
  char *v53; // [rsp+98h] [rbp-160h]
  int v54; // [rsp+A0h] [rbp-158h] BYREF
  __m128i v55; // [rsp+A4h] [rbp-154h]
  __int64 v56; // [rsp+B8h] [rbp-140h]
  __int128 v57; // [rsp+C0h] [rbp-138h]
  int v58; // [rsp+D0h] [rbp-128h]
  __int128 v59; // [rsp+D8h] [rbp-120h]
  int v60; // [rsp+E8h] [rbp-110h]
  __int16 v61; // [rsp+ECh] [rbp-10Ch]
  int v62; // [rsp+F0h] [rbp-108h] BYREF
  int v63; // [rsp+F4h] [rbp-104h]
  int v64; // [rsp+F8h] [rbp-100h]
  int v65; // [rsp+FCh] [rbp-FCh]
  _BYTE v66[120]; // [rsp+100h] [rbp-F8h] BYREF
  __int64 v67; // [rsp+178h] [rbp-80h]
  char v68; // [rsp+1A8h] [rbp-50h]

  v52 = this;
  Art::View::Info::Info((Art::View::Info *)v66);
  Art::View::Info::operator=(v66, *((_QWORD *)this + 1) + 40LL);
  if ( *((_BYTE *)this + 32) )
  {
    v53 = (char *)this + 33;
    if ( (*((_BYTE *)this + 33) || *((_BYTE *)this + 34))
      && Art::View::FActive(*((Art::View **)this + 1))
      && (v68 & 1) == 0 )
    {
      v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 224LL);
      if ( v2 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v2 + 16LL))(
          v2,
          &GUID_a2912880_a140_4113_9a75_6d2d6a4dffd5,
          &v47);
        v3 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(&v47);
        v4 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
        v5 = v47;
        if ( v47 )
        {
          v47 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
        }
        (*(void (__fastcall **)(_QWORD, __m128i *, _QWORD, _QWORD, char))(**((_QWORD **)this + 2) + 272LL))(
          *((_QWORD *)this + 2),
          &si128,
          0,
          0,
          1);
        ((__int64 (*)(void))Ofc::Round<__int64,double>)();
        Ofc::Round<__int64,double>(0xFFFFFFFF80000000uLL, 0x7FFFFFFF);
        Ofc::Round<__int64,double>(v7, v6);
        v10 = Ofc::Round<__int64,double>(v9, v8);
        if ( v10 >= v12 )
        {
          LODWORD(v12) = v10;
          if ( v10 > v11 )
            LODWORD(v12) = v11;
        }
        v62 = v12;
        v63 = v14;
        v64 = v13;
        v65 = v15;
        v44 = 0;
        v43 = Ofc::CProxyPtrImpl::WeakAddRef(*(struct Ofc::CProxyPtrImpl **)(*((_QWORD *)this + 1) + 56LL));
        v48 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v43);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v43);
        if ( !*((_QWORD *)v48 + 2)
          || (v16 = Ofc::CProxyPtrImpl::GetChecked(v48),
              (*(unsigned __int8 (__fastcall **)(void *, int *, _BYTE *, __int64 *))(*(_QWORD *)v16 + 152LL))(
                v16,
                &v62,
                v66,
                &v44)) )
        {
          *((_BYTE *)this + 34) = 1;
          HBITMAPFromImage = 0;
          v46 = 0;
          v18 = v64 - v62;
          if ( v64 - v62 <= 0 || (v19 = v65 - v63, v65 - v63 <= 0) )
          {
            CreateCaret(v4, 0, v18, v65 - v63);
            SetCaretPos(v62 + v44, v63 + HIDWORD(v44));
          }
          else
          {
            v45 = (struct Ofc::CProxyPtrImpl *)__PAIR64__(v19, v18);
            si128.m128i_i64[0] = v67;
            v43 = (struct Ofc::CProxyPtrImpl *)__PAIR64__(v19, v18);
            v20 = 0;
            v21 = 2;
            do
            {
              *(_DWORD *)((char *)&v45 + v20) = *(_DWORD *)((char *)&v43 + v20);
              v20 += 4;
              --v21;
            }
            while ( v21 );
            Gfx::IBitmapTarget::Create(&v43, &v45, &si128, 1, 8);
            v22 = v43;
            v43 = 0;
            v51 = v22;
            v23 = 0;
            v24 = 4;
            do
            {
              si128.m128i_i32[v23] = *(int *)((char *)&v62 + v23 * 4);
              ++v23;
              --v24;
            }
            while ( v24 );
            v54 = 0;
            v55 = si128;
            v56 = 0;
            v57 = 0;
            v58 = 3;
            v59 = 0;
            v60 = 1;
            v61 = 256;
            si128.m128i_i64[0] = (__int64)this;
            si128.m128i_i64[1] = (__int64)&v62;
            v50 = &v54;
            sub_180387980(v22, 0, &si128);
            if ( byte_180E1C578 < 0 )
              v25 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E1C578);
            else
              v25 = byte_180E1C578 != 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            if ( v25 )
            {
              v30 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
              v32 = (*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *))(v31 + 464))(v22);
              v33 = (Gfx **)GEL::IImage::Create(&si128, v32);
              HBITMAPFromImage = Gfx::CreateHBITMAPFromImage(*v33, (const struct GEL::IImage *)v30, v34);
              v46 = HBITMAPFromImage;
              if ( si128.m128i_i64[0] )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)si128.m128i_i64[0] + 8LL))(si128.m128i_i64[0]);
            }
            else
            {
              v26 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
              v28 = (Gfx *)(*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *))(v27 + 472))(v22);
              HBITMAPFromImage = Gfx::CreateHBITMAPFromImage(v28, (const struct GEL::IImage *)v26, v29);
              v46 = HBITMAPFromImage;
            }
            CreateCaret(v4, HBITMAPFromImage, 0, 0);
            SetCaretPos(v62 + v44, v63 + HIDWORD(v44));
            v35 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 3));
            v45 = v35;
            if ( *((_QWORD *)v35 + 2) )
            {
              Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v35);
              v37 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(Checked[20]);
              v43 = v37;
              if ( *((_QWORD *)v37 + 2) && *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v37) + 6) )
              {
                *((_BYTE *)this + 34) = 0;
                v38 = (Art::IE2oView *)Ofc::CProxyPtrImpl::GetChecked(v43);
                SelectionLayerNode = Art::IE2oView::GetSelectionLayerNode(v38);
                v40 = SelectionLayerNode;
                if ( *((_BYTE *)this + 35) )
                {
                  Art::SelectionLayerNode::SetCaretShape(
                    SelectionLayerNode,
                    *((struct Gfx::IShapeBuilder **)this + 2),
                    1);
                  *((_BYTE *)this + 35) = 0;
                }
                Art::SelectionLayerNode::ShowHideCaret(v40, 1);
                HideCaret(v4);
              }
              Ofc::CProxyPtrImpl::DtorStrongRelease(&v43);
            }
            if ( *((_BYTE *)this + 34) )
            {
              if ( ShowCaret(v4) )
                *((_BYTE *)this + 34) = 0;
              else
                MsoShipAssertTagProc(9176066);
            }
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v45);
            if ( v22 )
              (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v22 + 8LL))(v22);
          }
          *((_BYTE *)this + 33) = 0;
          v41 = (HBITMAP *)((char *)this + 40);
          Ofc::CHBitmap::~CHBitmap((Art::CaretManagerWin32 *)((char *)this + 40));
          if ( (HBITMAP *)((char *)this + 40) != &v46 )
          {
            Ofc::CHBitmap::~CHBitmap((Art::CaretManagerWin32 *)((char *)this + 40));
            v42 = *v41;
            *v41 = HBITMAPFromImage;
            HBITMAPFromImage = v42;
            v46 = v42;
          }
          if ( HBITMAPFromImage )
          {
            Ofc::CHBitmap::~CHBitmap((Art::CaretManagerWin32 *)((char *)this + 40));
            *v41 = HBITMAPFromImage;
          }
          Art::CaretManager::QueueTextSelectionChangedEvent(this);
          if ( HBITMAPFromImage )
            DeleteObject(HBITMAPFromImage);
        }
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v48);
      }
    }
  }
  Art::View::Info::~Info((Art::View::Info *)v66);
}

```

## disassembly

```asm
0x18029b1b0  mov     [rsp+arg_8], rbx
0x18029b1b5  mov     [rsp+arg_10], rsi
0x18029b1ba  push    rdi
0x18029b1bb  push    r12
0x18029b1bd  push    r13
0x18029b1bf  push    r14
0x18029b1c1  push    r15
0x18029b1c3  sub     rsp, 1D0h
0x18029b1ca  mov     rax, cs:__security_cookie
0x18029b1d1  xor     rax, rsp
0x18029b1d4  mov     [rsp+1F8h+var_38], rax
0x18029b1dc  mov     r14, rcx
0x18029b1df  mov     [rsp+1F8h+var_168], rcx
0x18029b1e7  xor     esi, esi
0x18029b1e9  lea     rcx, [rsp+1F8h+var_F8]; this
0x18029b1f1  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x18029b1f6  mov     rdx, [r14+8]
0x18029b1fa  add     rdx, 28h ; '('
0x18029b1fe  lea     rcx, [rsp+1F8h+var_F8]
0x18029b206  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x18029b20b  cmp     [r14+20h], sil
0x18029b20f  jz      loc_18029B7DC
0x18029b215  lea     r12, [r14+21h]
0x18029b219  mov     [rsp+1F8h+var_160], r12
0x18029b221  cmp     [r12], sil
0x18029b225  jnz     short loc_18029B231
0x18029b227  cmp     [r14+22h], sil
0x18029b22b  jz      loc_18029B7DC
0x18029b231  mov     rcx, [r14+8]; this
0x18029b235  call    ?FActive@View@Art@@QEBA_NXZ; Art::View::FActive(void)
0x18029b23a  test    al, al
0x18029b23c  jz      loc_18029B7DC
0x18029b242  test    [rsp+1F8h+var_50], 1
0x18029b24a  jnz     loc_18029B7DC
0x18029b250  mov     rax, [r14+8]
0x18029b254  mov     rcx, [rax+0E0h]
0x18029b25b  test    rcx, rcx
0x18029b25e  jz      loc_18029B7DC
0x18029b264  mov     [rsp+1F8h+var_1A8], rsi
0x18029b269  mov     rax, [rcx]
0x18029b26c  lea     r8, [rsp+1F8h+var_1A8]
0x18029b271  lea     rdx, _GUID_a2912880_a140_4113_9a75_6d2d6a4dffd5
0x18029b278  mov     rax, [rax+10h]
0x18029b27c  call    cs:__guard_dispatch_icall_fptr
0x18029b282  lea     rcx, [rsp+1F8h+var_1A8]
0x18029b287  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x18029b28c  mov     rdx, rax
0x18029b28f  mov     rcx, [rax]
0x18029b292  mov     rax, [rcx+28h]
0x18029b296  mov     rcx, rdx
0x18029b299  call    cs:__guard_dispatch_icall_fptr
0x18029b29f  mov     r13, rax
0x18029b2a2  mov     rdx, [rsp+1F8h+var_1A8]
0x18029b2a7  test    rdx, rdx
0x18029b2aa  jz      short loc_18029B2C1
0x18029b2ac  mov     [rsp+1F8h+var_1A8], rsi
0x18029b2b1  mov     rcx, [rdx]
0x18029b2b4  mov     rax, [rcx+8]
0x18029b2b8  mov     rcx, rdx
0x18029b2bb  call    cs:__guard_dispatch_icall_fptr
0x18029b2c1  mov     rcx, [r14+10h]
0x18029b2c5  mov     rax, [rcx]
0x18029b2c8  mov     byte ptr [rsp+1F8h+var_1D8], 1
0x18029b2cd  xor     r9d, r9d
0x18029b2d0  xor     r8d, r8d
0x18029b2d3  lea     rdx, [rsp+1F8h+var_198]
0x18029b2d8  mov     rax, [rax+110h]
0x18029b2df  call    cs:__guard_dispatch_icall_fptr
0x18029b2e5  movsd   xmm0, qword ptr [rax]
0x18029b2e9  comisd  xmm0, qword ptr [rax+10h]
0x18029b2ee  ja      short loc_18029B305
0x18029b2f0  movsd   xmm0, qword ptr [rax+8]
0x18029b2f5  comisd  xmm0, qword ptr [rax+18h]
0x18029b2fa  ja      short loc_18029B305
0x18029b2fc  movups  xmm3, xmmword ptr [rax]
0x18029b2ff  movups  xmm2, xmmword ptr [rax+10h]
0x18029b303  jmp     short loc_18029B30B
0x18029b305  xorps   xmm3, xmm3
0x18029b308  xorps   xmm2, xmm2
0x18029b30b  movaps  xmm0, xmm2
0x18029b30e  unpckhpd xmm0, xmm2
0x18029b312  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x18029b317  mov     r10, rax
0x18029b31a  mov     rcx, 0FFFFFFFF80000000h
0x18029b321  mov     edx, 7FFFFFFFh
0x18029b326  cmp     rax, rcx
0x18029b329  jge     short loc_18029B330
0x18029b32b  mov     r10, rcx
0x18029b32e  jmp     short loc_18029B337
0x18029b330  cmp     r10, rdx
0x18029b333  cmovg   r10, rdx
0x18029b337  movaps  xmm0, xmm2
0x18029b33a  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x18029b33f  mov     r8, rax
0x18029b342  cmp     rax, rcx
0x18029b345  jge     short loc_18029B34C
0x18029b347  mov     r8, rcx
0x18029b34a  jmp     short loc_18029B353
0x18029b34c  cmp     r8, rdx
0x18029b34f  cmovg   r8, rdx
0x18029b353  movaps  xmm0, xmm3
0x18029b356  unpckhpd xmm0, xmm3
0x18029b35a  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x18029b35f  mov     r9, rax
0x18029b362  cmp     rax, rcx
0x18029b365  jge     short loc_18029B36C
0x18029b367  mov     r9, rcx
0x18029b36a  jmp     short loc_18029B373
0x18029b36c  cmp     r9, rdx
0x18029b36f  cmovg   r9, rdx
0x18029b373  movaps  xmm0, xmm3
0x18029b376  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x18029b37b  cmp     rax, rcx
0x18029b37e  jl      short loc_18029B38A
0x18029b380  mov     rcx, rax
0x18029b383  cmp     rax, rdx
0x18029b386  cmovg   rcx, rdx
0x18029b38a  mov     [rsp+1F8h+var_108], ecx
0x18029b391  mov     [rsp+1F8h+var_104], r9d
0x18029b399  mov     [rsp+1F8h+var_100], r8d
0x18029b3a1  mov     [rsp+1F8h+var_FC], r10d
0x18029b3a9  mov     [rsp+1F8h+var_1C0], rsi
0x18029b3ae  mov     rax, rsi
0x18029b3b1  mov     [rsp+1F8h+var_1C0], rax
0x18029b3b6  mov     rcx, [r14+8]
0x18029b3ba  mov     rcx, [rcx+38h]; struct Ofc::CProxyPtrImpl *
0x18029b3be  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x18029b3c3  mov     [rsp+1F8h+var_1C8], rax
0x18029b3c8  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x18029b3cb  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029b3d0  mov     [rsp+1F8h+var_1A0], rax
0x18029b3d5  lea     rcx, [rsp+1F8h+var_1C8]; struct Ofc::CProxyPtrImpl **
0x18029b3da  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18029b3df  mov     rcx, [rsp+1F8h+var_1A0]; this
0x18029b3e4  cmp     [rcx+10h], rsi
0x18029b3e8  jz      short loc_18029B422
0x18029b3ea  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029b3ef  mov     r10, rax
0x18029b3f2  mov     rcx, [rax]
0x18029b3f5  mov     rax, [rcx+98h]
0x18029b3fc  lea     r9, [rsp+1F8h+var_1C0]
0x18029b401  lea     r8, [rsp+1F8h+var_F8]
0x18029b409  lea     rdx, [rsp+1F8h+var_108]
0x18029b411  mov     rcx, r10
0x18029b414  call    cs:__guard_dispatch_icall_fptr
0x18029b41a  test    al, al
0x18029b41c  jz      loc_18029B7D1
0x18029b422  mov     byte ptr [r14+22h], 1
0x18029b427  mov     rbx, rsi
0x18029b42a  mov     [rsp+1F8h+var_1B0], rbx
0x18029b42f  mov     r8d, [rsp+1F8h+var_100]
0x18029b437  sub     r8d, [rsp+1F8h+var_108]; nWidth
0x18029b43f  mov     r9d, [rsp+1F8h+var_FC]
0x18029b447  mov     ecx, [rsp+1F8h+var_104]
0x18029b44e  test    r8d, r8d
0x18029b451  jle     loc_18029B750
0x18029b457  mov     eax, r9d
0x18029b45a  sub     eax, ecx
0x18029b45c  test    eax, eax
0x18029b45e  jle     loc_18029B750
0x18029b464  mov     dword ptr [rsp+1F8h+var_1B8], r8d
0x18029b469  mov     dword ptr [rsp+1F8h+var_1B8+4], eax
0x18029b46d  movsd   xmm0, [rsp+1F8h+var_80]
0x18029b476  movsd   qword ptr [rsp+1F8h+var_198], xmm0
0x18029b47c  mov     dword ptr [rsp+1F8h+var_1C8], r8d
0x18029b481  mov     rax, [rsp+1F8h+var_1B8]
0x18029b486  shr     rax, 20h
0x18029b48a  mov     dword ptr [rsp+1F8h+var_1C8+4], eax
0x18029b48e  mov     rcx, rsi
0x18029b491  mov     edx, 2
0x18029b496  mov     eax, dword ptr [rsp+rcx+1F8h+var_1C8]
0x18029b49a  mov     dword ptr [rsp+rcx+1F8h+var_1B8], eax
0x18029b49e  lea     rcx, [rcx+4]
0x18029b4a2  sub     rdx, 1
0x18029b4a6  jnz     short loc_18029B496
0x18029b4a8  mov     [rsp+1F8h+var_1D8], 8
0x18029b4b0  lea     r9d, [rdx+1]
0x18029b4b4  lea     r8, [rsp+1F8h+var_198]
0x18029b4b9  lea     rdx, [rsp+1F8h+var_1B8]
0x18029b4be  lea     rcx, [rsp+1F8h+var_1C8]
0x18029b4c3  call    cs:__imp_?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,uint)
0x18029b4c9  mov     rdi, [rsp+1F8h+var_1C8]
0x18029b4ce  mov     [rsp+1F8h+var_1C8], rsi
0x18029b4d3  mov     [rsp+1F8h+var_170], rdi
0x18029b4db  mov     rcx, rsi
0x18029b4de  mov     edx, 4
0x18029b4e3  mov     eax, [rsp+rcx+1F8h+var_108]
0x18029b4ea  mov     dword ptr [rsp+rcx+1F8h+var_198], eax
0x18029b4ee  lea     rcx, [rcx+4]
0x18029b4f2  sub     rdx, 1
0x18029b4f6  jnz     short loc_18029B4E3
0x18029b4f8  mov     [rsp+1F8h+var_158], esi
0x18029b4ff  movups  xmm0, [rsp+1F8h+var_198]
0x18029b504  movdqu  [rsp+1F8h+var_154], xmm0
0x18029b50d  mov     [rsp+1F8h+var_140], rsi
0x18029b515  xorps   xmm1, xmm1
0x18029b518  movdqa  [rsp+1F8h+var_138], xmm1
0x18029b521  mov     [rsp+1F8h+var_128], 3
0x18029b52c  xorps   xmm0, xmm0
0x18029b52f  movups  [rsp+1F8h+var_120], xmm0
0x18029b537  mov     [rsp+1F8h+var_110], 1
0x18029b542  mov     [rsp+1F8h+var_10C], 100h
0x18029b54c  mov     qword ptr [rsp+1F8h+var_198], r14
0x18029b551  lea     rax, [rsp+1F8h+var_108]
0x18029b559  mov     qword ptr [rsp+1F8h+var_198+8], rax
0x18029b55e  lea     rax, [rsp+1F8h+var_158]
0x18029b566  mov     [rsp+1F8h+var_188], rax
0x18029b56b  lea     r8, [rsp+1F8h+var_198]
0x18029b570  mov     rcx, rdi
0x18029b573  call    sub_180387980
0x18029b578  mov     al, cs:byte_180E1C578
0x18029b57e  test    al, al
0x18029b580  js      short loc_18029B587
0x18029b582  setnz   al
0x18029b585  jmp     short loc_18029B594
0x18029b587  lea     rcx, byte_180E1C578
0x18029b58e  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x18029b594  mov     r9, [rdi]
0x18029b597  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x18029b59f  lea     rcx, [rsp+1F8h+var_198]; this
0x18029b5a4  movups  [rsp+1F8h+var_198], xmm0
0x18029b5a9  test    al, al
0x18029b5ab  jnz     short loc_18029B5D9
0x18029b5ad  call    ?ToCOLORREF@Color@GEL@@QEBAKXZ; GEL::Color::ToCOLORREF(void)
0x18029b5b2  mov     ebx, eax
0x18029b5b4  mov     rcx, rdi
0x18029b5b7  mov     rax, [r9+1D8h]
0x18029b5be  call    cs:__guard_dispatch_icall_fptr
0x18029b5c4  mov     edx, ebx
0x18029b5c6  mov     rcx, rax
0x18029b5c9  call    cs:__imp_?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z; Gfx::CreateHBITMAPFromImage(GEL::IImage const &,ulong)
0x18029b5cf  mov     rbx, rax
0x18029b5d2  mov     [rsp+1F8h+var_1B0], rax
0x18029b5d7  jmp     short loc_18029B62A
0x18029b5d9  call    ?ToCOLORREF@Color@GEL@@QEBAKXZ; GEL::Color::ToCOLORREF(void)
0x18029b5de  mov     ebx, eax
0x18029b5e0  mov     rcx, rdi
0x18029b5e3  mov     rax, [r9+1D0h]
0x18029b5ea  call    cs:__guard_dispatch_icall_fptr
0x18029b5f0  mov     rdx, rax
0x18029b5f3  lea     rcx, [rsp+1F8h+var_198]
0x18029b5f8  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z; GEL::IImage::Create(ARC::IPlatformBitmap &)
0x18029b5fe  nop
0x18029b5ff  nop
0x18029b600  mov     edx, ebx
0x18029b602  mov     rcx, [rax]
0x18029b605  call    cs:__imp_?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z; Gfx::CreateHBITMAPFromImage(GEL::IImage const &,ulong)
0x18029b60b  mov     rbx, rax
0x18029b60e  mov     [rsp+1F8h+var_1B0], rax
0x18029b613  mov     rcx, qword ptr [rsp+1F8h+var_198]
0x18029b618  test    rcx, rcx
0x18029b61b  jz      short loc_18029B62A
0x18029b61d  mov     rax, [rcx]
0x18029b620  mov     rax, [rax+8]
0x18029b624  call    cs:__guard_dispatch_icall_fptr
0x18029b62a  xor     r9d, r9d; nHeight
0x18029b62d  xor     r8d, r8d; nWidth
0x18029b630  mov     rdx, rbx; hBitmap
0x18029b633  mov     rcx, r13; hWnd
0x18029b636  call    cs:__imp_CreateCaret
0x18029b63c  mov     edx, dword ptr [rsp+1F8h+var_1C0+4]
0x18029b640  add     edx, [rsp+1F8h+var_104]; Y
0x18029b647  mov     ecx, dword ptr [rsp+1F8h+var_1C0]
0x18029b64b  add     ecx, [rsp+1F8h+var_108]; X
0x18029b652  call    cs:__imp_SetCaretPos
0x18029b658  mov     rcx, [r14+18h]; struct Ofc::CProxyPtrImpl *
0x18029b65c  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029b661  mov     [rsp+1F8h+var_1B8], rax
0x18029b666  cmp     [rax+10h], rsi
0x18029b66a  jz      short loc_18029B6E9
0x18029b66c  mov     rcx, rax; this
0x18029b66f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029b674  mov     rcx, [rax+0A0h]; struct Ofc::CProxyPtrImpl *
0x18029b67b  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029b680  mov     [rsp+1F8h+var_1C8], rax
0x18029b685  cmp     [rax+10h], rsi
0x18029b689  jz      short loc_18029B6DF
0x18029b68b  mov     rcx, rax; this
0x18029b68e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029b693  cmp     [rax+30h], rsi
0x18029b697  jz      short loc_18029B6DF
0x18029b699  mov     [r14+22h], sil
0x18029b69d  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18029b6a2  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029b6a7  mov     rcx, rax; this
0x18029b6aa  call    ?GetSelectionLayerNode@IE2oView@Art@@QEAAAEAUILayerNode@2@XZ; Art::IE2oView::GetSelectionLayerNode(void)
0x18029b6af  mov     r15, rax
0x18029b6b2  cmp     [r14+23h], sil
0x18029b6b6  jz      short loc_18029B6CB
0x18029b6b8  mov     r8b, 1; bool
0x18029b6bb  mov     rdx, [r14+10h]; struct Gfx::IShapeBuilder *
0x18029b6bf  mov     rcx, rax; this
0x18029b6c2  call    ?SetCaretShape@SelectionLayerNode@Art@@QEAAXPEAUIShapeBuilder@Gfx@@_N@Z; Art::SelectionLayerNode::SetCaretShape(Gfx::IShapeBuilder *,bool)
0x18029b6c7  mov     [r14+23h], sil
0x18029b6cb  mov     dl, 1; bool
0x18029b6cd  mov     rcx, r15; this
0x18029b6d0  call    ?ShowHideCaret@SelectionLayerNode@Art@@QEAAX_N@Z; Art::SelectionLayerNode::ShowHideCaret(bool)
0x18029b6d5  mov     rcx, r13; hWnd
0x18029b6d8  call    cs:__imp_HideCaret
0x18029b6de  nop
  ... truncated ...
```
