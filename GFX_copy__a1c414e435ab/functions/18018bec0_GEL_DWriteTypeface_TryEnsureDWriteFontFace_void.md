# GEL::DWriteTypeface::TryEnsureDWriteFontFace(void)

- ea: `0x18018bec0`
- end: `0x18018c40f`
- name: `?TryEnsureDWriteFontFace@DWriteTypeface@GEL@@AEAAPEAUIDWriteFontFace@@XZ`
- size: `1359`
- prototype: `struct IDWriteFontFace *__fastcall(GEL::DWriteTypeface *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18018b2b0`
- `0x18018b5c0`

## callees

- `0x18001fcb0`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x180066410`
- `0x18007aa30`
- `0x1800be640`
- `0x180104700`
- `0x180189d84`
- `0x18018b1a4`
- `0x18018bec0`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018bf3d`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018bf3d`
- `mso40uiWin32Client!__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z` at `0x18018c2f5`
- `mso40uiWin32Client!__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z` at `0x18018c2f5`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18018c185`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18018c185`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18018c1f4`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18018c1f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IDWriteFontFace *__fastcall GEL::DWriteTypeface::TryEnsureDWriteFontFace(GEL::DWriteTypeface *this)
{
  _QWORD *v2; // r15
  struct IDWriteFontFace *result; // rax
  char v4; // r12
  _QWORD *v5; // r14
  Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  struct Mso::DWriteAssistant::IFontCollection *FontCollection; // rdi
  __int64 (__fastcall *v8)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, _QWORD *); // rbx
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  int v13; // ebx
  const wchar_t *v14; // rcx
  int v15; // eax
  struct tagFONTSIGNATURE *v16; // r8
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // ebx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  Mso::DWriteAssistant *v25; // [rsp+38h] [rbp-D0h] BYREF
  const char *v26; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v27[4]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v28[3]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+80h] [rbp-88h] BYREF
  __int16 v30; // [rsp+88h] [rbp-80h]
  void **v31; // [rsp+98h] [rbp-70h] BYREF
  const char *v32; // [rsp+A0h] [rbp-68h]
  int v33; // [rsp+A8h] [rbp-60h]
  __int128 v34; // [rsp+B0h] [rbp-58h] BYREF
  __m128i v35; // [rsp+C0h] [rbp-48h]
  __int16 v36; // [rsp+D0h] [rbp-38h]
  __int128 v37; // [rsp+D8h] [rbp-30h] BYREF
  int v38; // [rsp+E8h] [rbp-20h]
  _QWORD v39[2]; // [rsp+F0h] [rbp-18h] BYREF
  int v40; // [rsp+100h] [rbp-8h]
  __int16 v41; // [rsp+104h] [rbp-4h]
  _OWORD v42[2]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v43[2]; // [rsp+128h] [rbp+20h] BYREF
  int v44; // [rsp+138h] [rbp+30h]
  __int128 v45; // [rsp+140h] [rbp+38h] BYREF
  __int64 v46; // [rsp+150h] [rbp+48h]
  __int64 v47; // [rsp+158h] [rbp+50h]
  __int16 v48; // [rsp+160h] [rbp+58h]
  _QWORD v49[3]; // [rsp+168h] [rbp+60h] BYREF
  __int16 v50; // [rsp+180h] [rbp+78h]
  __int128 v51; // [rsp+188h] [rbp+80h] BYREF
  __m128i si128; // [rsp+198h] [rbp+90h]

  v2 = (_QWORD *)((char *)this + 192);
  result = (struct IDWriteFontFace *)*((_QWORD *)this + 24);
  if ( !result )
  {
    v4 = 0;
    v5 = (_QWORD *)((char *)this + 200);
    if ( !*((_QWORD *)this + 25) )
    {
      if ( !*((_BYTE *)this + 100) )
      {
        if ( *((_DWORD *)this + 52) )
        {
          v4 = 1;
          ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(this);
          FontCollection = Mso::DWriteAssistant::ResourceManager::GetFontCollection(ResourceManagerInstance);
          v8 = *(__int64 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, _QWORD *))(*(_QWORD *)FontCollection + 32LL);
          Mso::TCntPtr<IDWriteNumberSubstitution>::~TCntPtr<IDWriteNumberSubstitution>(v5);
          v9 = v8(FontCollection, *((unsigned int *)this + 52), v5);
          if ( v9 < 0 )
          {
            v32 = "HRESULT";
            v33 = v9;
            v34 = 0;
            v35.m128i_i64[0] = 0;
            v35.m128i_i64[1] = 7;
            LOWORD(v34) = 0;
            v36 = 4;
            v31 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
            v26 = "Failed to get font family";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredHrNamed>(
              4,
              (unsigned int)"HRESULT",
              v10,
              v11,
              (__int64)&v26,
              (__int64)&v31);
            std::wstring::~wstring(&v34);
            return 0;
          }
        }
      }
      if ( !*v5 )
        return 0;
    }
    if ( *((_QWORD *)this + 14) )
      Ofc::TOwnerPtr<GEL::WidthCache>::`vector deleting destructor'();
    *((_QWORD *)this + 14) = 0;
    v25 = 0;
    v12 = Mso::TCntPtr<IWICImagingFactory>::operator->(v5);
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, Mso::DWriteAssistant **))(*(_QWORD *)v12 + 56LL))(
            v12,
            *((unsigned int *)this + 19),
            *((unsigned int *)this + 53),
            *((unsigned int *)this + 54),
            &v25);
    if ( v13 < 0 )
    {
      if ( *((_DWORD *)this + 52) )
        v14 = *(const wchar_t **)(*(__int64 (__fastcall **)(GEL::DWriteTypeface *))(*(_QWORD *)this + 16LL))(this);
      else
        v14 = L"<redacted>";
      v49[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v49[1] = "Font";
      v49[2] = v14;
      v50 = 4;
      v51 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v51) = 0;
      v43[1] = "HRESULT";
      v44 = v13;
      v45 = 0;
      v46 = 0;
      v47 = 7;
      LOWORD(v45) = 0;
      v48 = 4;
      v43[0] = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
      v31 = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
      v32 = "FontLoaded";
      LOBYTE(v33) = *((_BYTE *)this + 100);
      HIWORD(v33) = 4;
      v34 = 0;
      v35 = si128;
      LOWORD(v34) = 0;
      v39[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v39[1] = "CloudIndex";
      v40 = *((_DWORD *)this + 52);
      v41 = 4;
      v42[0] = 0;
      v42[1] = si128;
      LOWORD(v42[0]) = 0;
      if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(509655237, 173, 10, 2) )
      {
        v27[0] = v39;
        v27[1] = &v31;
        v27[2] = v43;
        v27[3] = v49;
        v28[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v28[1] = v27;
        v28[2] = v28;
        Mso::Logging::MsoSendStructuredTraceTag(509655237, 173, 10, 2, "Failed to get first matching font", v28);
      }
      std::wstring::~wstring(v42);
      std::wstring::~wstring(&v34);
      std::wstring::~wstring(&v45);
      std::wstring::~wstring(&v51);
      if ( v25 )
        (*(void (__fastcall **)(Mso::DWriteAssistant *))(*(_QWORD *)v25 + 16LL))(v25);
      return 0;
    }
    v37 = 0;
    v38 = 0;
    (*(void (__fastcall **)(Mso::DWriteAssistant *, __int128 *))(*(_QWORD *)v25 + 88LL))(v25, &v37);
    *((_DWORD *)this + 18) = (unsigned __int16)v37;
    *((_DWORD *)this + 20) = 0;
    if ( (*(int (__fastcall **)(Mso::DWriteAssistant *, _QWORD *))(*(_QWORD *)v25 + 104LL))(v25, v2) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 24LL))(*v2);
      if ( v15 && (v17 = v15 - 1) != 0 && (v18 = v17 - 1) != 0 )
      {
        v19 = v18 - 1;
        if ( v19 )
          v20 = v19 == 2;
        else
          v20 = 2;
      }
      else
      {
        v20 = 8;
      }
      *((_DWORD *)this + 20) = v20;
      if ( v20 && *((_DWORD *)this + 52) )
        Ofc::TCntPtr<GEL::Arc2DRadialPathGradientBrushResource>::Assign((char *)this + 32, 0);
      if ( !v4 )
      {
        Mso::DWriteAssistant::GetFontSignature(v25, (GEL::DWriteTypeface *)((char *)this + 48), v16);
        v29 = 0;
        v30 = 0;
        *((_QWORD *)this + 11) = 0;
        *((_WORD *)this + 48) = 0;
        v26 = 0;
        (**(void (__fastcall ***)(Mso::DWriteAssistant *, GUID *, const char **))v25)(
          v25,
          &GUID_acd16696_8c14_4f5d_877e_fe3fc1d32738,
          &v26);
        if ( v26 )
        {
          (*(void (__fastcall **)(const char *, __int64 *))(*(_QWORD *)v26 + 120LL))(v26, &v29);
          LOBYTE(v22) = v29;
          if ( (unsigned __int8)(v29 - 2) <= 1u )
          {
            *((_BYTE *)this + 88) = v29;
            v23 = v29;
            *((_BYTE *)this + 89) = BYTE1(v29);
            *((_BYTE *)this + 90) = BYTE2(v23);
            *((_BYTE *)this + 91) = BYTE3(v23);
            *((_BYTE *)this + 92) = BYTE4(v23);
            *((_BYTE *)this + 93) = BYTE5(v23);
            *((_BYTE *)this + 94) = BYTE6(v23);
            *((_BYTE *)this + 95) = HIBYTE(v23);
            *((_WORD *)this + 48) = v30;
          }
          else
          {
            *((_QWORD *)this + 11) = 0;
            *((_WORD *)this + 48) = 0;
          }
          LOBYTE(v21) = BYTE1(v29);
          *((_BYTE *)this + 98) = sub_18018B1A4(*v2, v22, v21);
          if ( v26 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v26 + 16LL))(v26);
        }
      }
    }
    v24 = *v2;
    if ( v25 )
      (*(void (__fastcall **)(Mso::DWriteAssistant *))(*(_QWORD *)v25 + 16LL))(v25);
    return (struct IDWriteFontFace *)v24;
  }
  return result;
}

```

## disassembly

```asm
0x18018bec0  mov     rax, rsp
0x18018bec3  mov     [rax+10h], rbx
0x18018bec7  mov     [rax+18h], rsi
0x18018becb  mov     [rax+20h], rdi
0x18018becf  push    rbp
0x18018bed0  push    r12
0x18018bed2  push    r13
0x18018bed4  push    r14
0x18018bed6  push    r15
0x18018bed8  lea     rbp, [rax-0D8h]
0x18018bedf  sub     rsp, 1B0h
0x18018bee6  mov     rax, cs:__security_cookie
0x18018beed  xor     rax, rsp
0x18018bef0  mov     [rbp+0D0h+var_30], rax
0x18018bef7  mov     rsi, rcx
0x18018befa  lea     r15, [rcx+0C0h]
0x18018bf01  mov     rax, [r15]
0x18018bf04  xor     r13d, r13d
0x18018bf07  test    rax, rax
0x18018bf0a  jnz     loc_18018BFE2
0x18018bf10  mov     r12b, r13b
0x18018bf13  lea     r14, [rcx+0C8h]
0x18018bf1a  cmp     [r14], r13
0x18018bf1d  jnz     loc_18018C017
0x18018bf23  cmp     [rcx+64h], r13b
0x18018bf27  jnz     loc_18018C012
0x18018bf2d  cmp     [rcx+0D0h], r13d
0x18018bf34  jbe     loc_18018C012
0x18018bf3a  mov     r12b, 1
0x18018bf3d  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018bf43  mov     rcx, rax; this
0x18018bf46  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018bf4b  mov     rdi, rax
0x18018bf4e  mov     rcx, [rax]
0x18018bf51  mov     rbx, [rcx+20h]
0x18018bf55  mov     rcx, r14
0x18018bf58  call    ??1?$TCntPtr@UIDWriteNumberSubstitution@@@Mso@@QEAA@XZ; Mso::TCntPtr<IDWriteNumberSubstitution>::~TCntPtr<IDWriteNumberSubstitution>(void)
0x18018bf5d  mov     r8, r14
0x18018bf60  mov     edx, [rsi+0D0h]
0x18018bf66  mov     rcx, rdi
0x18018bf69  mov     rax, rbx
0x18018bf6c  call    cs:__guard_dispatch_icall_fptr
0x18018bf72  test    eax, eax
0x18018bf74  jns     loc_18018C012
0x18018bf7a  lea     rdx, aHresult; "HRESULT"
0x18018bf81  mov     [rbp+0D0h+var_138], rdx
0x18018bf85  mov     [rbp+0D0h+var_130], eax
0x18018bf88  xorps   xmm0, xmm0
0x18018bf8b  movups  [rbp+0D0h+var_128], xmm0
0x18018bf8f  mov     qword ptr [rbp+0D0h+var_118], r13
0x18018bf93  mov     qword ptr [rbp+0D0h+var_118+8], 7
0x18018bf9b  mov     word ptr [rbp+0D0h+var_128], r13w
0x18018bfa0  lea     ecx, [r13+4]
0x18018bfa4  mov     [rbp+0D0h+var_108], cx
0x18018bfa8  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18018bfaf  mov     [rbp+0D0h+var_140], rax
0x18018bfb3  lea     rax, aFailedToGetFon; "Failed to get font family"
0x18018bfba  mov     [rsp+1D0h+var_198], rax
0x18018bfbf  lea     rax, [rbp+0D0h+var_140]
0x18018bfc3  mov     [rsp+1D0h+var_1A8], rax
0x18018bfc8  lea     rax, [rsp+1D0h+var_198]
0x18018bfcd  mov     [rsp+1D0h+var_1B0], rax
0x18018bfd2  call    ??$SendDiagnosticTrace@UClassifiedStructuredHrNamed@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUClassifiedStructuredHrNamed@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredHrNamed>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredHrNamed &&)
0x18018bfd7  lea     rcx, [rbp+0D0h+var_128]
0x18018bfdb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018bfe0  xor     eax, eax
0x18018bfe2  mov     rcx, [rbp+0D0h+var_30]
0x18018bfe9  xor     rcx, rsp; StackCookie
0x18018bfec  call    __security_check_cookie
0x18018bff1  lea     r11, [rsp+1D0h+var_20]
0x18018bff9  mov     rbx, [r11+38h]
0x18018bffd  mov     rsi, [r11+40h]
0x18018c001  mov     rdi, [r11+48h]
0x18018c005  mov     rsp, r11
0x18018c008  pop     r15
0x18018c00a  pop     r14
0x18018c00c  pop     r13
0x18018c00e  pop     r12
0x18018c010  pop     rbp
0x18018c011  retn
0x18018c012  cmp     [r14], r13
0x18018c015  jz      short loc_18018BFE0
0x18018c017  mov     rcx, [rsi+70h]
0x18018c01b  test    rcx, rcx
0x18018c01e  jz      short loc_18018C025
0x18018c020  call    ??_E?$TOwnerPtr@UWidthCache@GEL@@@Ofc@@QEAAPEAXI@Z; Ofc::TOwnerPtr<GEL::WidthCache>::`vector deleting destructor'(uint)
0x18018c025  mov     [rsi+70h], r13
0x18018c029  mov     [rsp+1D0h+var_1A0], r13
0x18018c02e  mov     rcx, r14
0x18018c031  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18018c036  mov     r10, rax
0x18018c039  mov     rcx, [rax]
0x18018c03c  mov     rax, [rcx+38h]
0x18018c040  lea     rcx, [rsp+1D0h+var_1A0]
0x18018c045  mov     [rsp+1D0h+var_1B0], rcx
0x18018c04a  mov     r9d, [rsi+0D8h]
0x18018c051  mov     r8d, [rsi+0D4h]
0x18018c058  mov     edx, [rsi+4Ch]
0x18018c05b  mov     rcx, r10
0x18018c05e  call    cs:__guard_dispatch_icall_fptr
0x18018c064  mov     ebx, eax
0x18018c066  test    eax, eax
0x18018c068  jns     loc_18018C241
0x18018c06e  cmp     [rsi+0D0h], r13d
0x18018c075  jbe     short loc_18018C08C
0x18018c077  mov     rcx, [rsi]
0x18018c07a  mov     rax, [rcx+10h]
0x18018c07e  mov     rcx, rsi
0x18018c081  call    cs:__guard_dispatch_icall_fptr
0x18018c087  mov     rcx, [rax]
0x18018c08a  jmp     short loc_18018C093
0x18018c08c  lea     rcx, aRedacted; "<redacted>"
0x18018c093  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18018c09a  mov     [rbp+0D0h+var_70], rax
0x18018c09e  lea     rax, aFont; "Font"
0x18018c0a5  mov     [rbp+0D0h+var_68], rax
0x18018c0a9  mov     [rbp+0D0h+var_60], rcx
0x18018c0ad  mov     ecx, 4
0x18018c0b2  mov     [rbp+0D0h+var_58], cx
0x18018c0b6  xorps   xmm0, xmm0
0x18018c0b9  movups  [rbp+0D0h+var_50], xmm0
0x18018c0c0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18018c0c8  movdqa  [rbp+0D0h+var_40], xmm1
0x18018c0d0  mov     word ptr [rbp+0D0h+var_50], r13w
0x18018c0d8  lea     rdx, aHresult; "HRESULT"
0x18018c0df  mov     [rbp+0D0h+var_A8], rdx
0x18018c0e3  mov     [rbp+0D0h+var_A0], ebx
0x18018c0e6  movups  [rbp+0D0h+var_98], xmm0
0x18018c0ea  mov     [rbp+0D0h+var_88], r13
0x18018c0ee  mov     [rbp+0D0h+var_80], 7
0x18018c0f6  mov     word ptr [rbp+0D0h+var_98], r13w
0x18018c0fb  mov     [rbp+0D0h+var_78], cx
0x18018c0ff  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18018c106  mov     [rbp+0D0h+var_B0], rax
0x18018c10a  lea     rax, ??_7?$ClassifiedStructuredObject@_N@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable'
0x18018c111  mov     [rbp+0D0h+var_140], rax
0x18018c115  lea     rax, aFontloaded; "FontLoaded"
0x18018c11c  mov     [rbp+0D0h+var_138], rax
0x18018c120  mov     al, [rsi+64h]
0x18018c123  mov     byte ptr [rbp+0D0h+var_130], al
0x18018c126  mov     word ptr [rbp+0D0h+var_130+2], cx
0x18018c12a  movups  [rbp+0D0h+var_128], xmm0
0x18018c12e  movdqu  [rbp+0D0h+var_118], xmm1
0x18018c133  mov     word ptr [rbp+0D0h+var_128], r13w
0x18018c138  lea     rax, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18018c13f  mov     [rbp+0D0h+var_E8], rax
0x18018c143  lea     rax, aCloudindex; "CloudIndex"
0x18018c14a  mov     [rbp+0D0h+var_E0], rax
0x18018c14e  mov     eax, [rsi+0D0h]
0x18018c154  mov     [rbp+0D0h+var_D8], eax
0x18018c157  mov     [rbp+0D0h+var_D4], cx
0x18018c15b  movups  [rbp+0D0h+var_D0], xmm0
0x18018c15f  movdqu  [rbp+0D0h+var_C0], xmm1
0x18018c164  mov     word ptr [rbp+0D0h+var_D0], r13w
0x18018c169  lea     edi, [rcx-2]
0x18018c16c  mov     r9d, edi
0x18018c16f  lea     ebx, [rcx+6]
0x18018c172  mov     r8d, ebx
0x18018c175  mov     esi, 0ADh
0x18018c17a  mov     edx, esi
0x18018c17c  mov     r14d, 1E60B8C5h
0x18018c182  mov     ecx, r14d
0x18018c185  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18018c18b  test    al, al
0x18018c18d  jz      short loc_18018C1FA
0x18018c18f  lea     rax, [rbp+0D0h+var_E8]
0x18018c193  mov     [rsp+1D0h+var_190], rax
0x18018c198  lea     rax, [rbp+0D0h+var_140]
0x18018c19c  mov     [rsp+1D0h+var_188], rax
0x18018c1a1  lea     rax, [rbp+0D0h+var_B0]
0x18018c1a5  mov     [rsp+1D0h+var_180], rax
0x18018c1aa  lea     rax, [rbp+0D0h+var_70]
0x18018c1ae  mov     [rsp+1D0h+var_178], rax
0x18018c1b3  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18018c1ba  mov     [rsp+1D0h+var_170], rax
0x18018c1bf  lea     rax, [rsp+1D0h+var_190]
0x18018c1c4  mov     [rsp+1D0h+var_168], rax
0x18018c1c9  lea     rax, [rsp+1D0h+var_170]
0x18018c1ce  mov     [rsp+1D0h+var_160], rax
0x18018c1d3  mov     r9d, edi
0x18018c1d6  lea     rax, [rsp+1D0h+var_170]
0x18018c1db  mov     [rsp+1D0h+var_1A8], rax
0x18018c1e0  lea     rax, aFailedToGetFir; "Failed to get first matching font"
0x18018c1e7  mov     [rsp+1D0h+var_1B0], rax
0x18018c1ec  mov     r8d, ebx
0x18018c1ef  mov     edx, esi
0x18018c1f1  mov     ecx, r14d
0x18018c1f4  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
0x18018c1fa  lea     rcx, [rbp+0D0h+var_D0]
0x18018c1fe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018c203  lea     rcx, [rbp+0D0h+var_128]
0x18018c207  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018c20c  lea     rcx, [rbp+0D0h+var_98]
0x18018c210  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018c215  lea     rcx, [rbp+0D0h+var_50]
0x18018c21c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018c221  mov     rcx, [rsp+1D0h+var_1A0]
0x18018c226  test    rcx, rcx
0x18018c229  jz      loc_18018BFE0
0x18018c22f  mov     rax, [rcx]
0x18018c232  mov     rax, [rax+10h]
0x18018c236  call    cs:__guard_dispatch_icall_fptr
0x18018c23c  jmp     loc_18018BFE0
0x18018c241  xorps   xmm0, xmm0
0x18018c244  xor     eax, eax
0x18018c246  movups  [rbp+0D0h+var_100], xmm0
0x18018c24a  mov     [rbp+0D0h+var_F0], eax
0x18018c24d  mov     rcx, [rsp+1D0h+var_1A0]
0x18018c252  mov     rax, [rcx]
0x18018c255  lea     rdx, [rbp+0D0h+var_100]
0x18018c259  mov     rax, [rax+58h]
0x18018c25d  call    cs:__guard_dispatch_icall_fptr
0x18018c263  movzx   eax, word ptr [rbp+0D0h+var_100]
0x18018c267  mov     [rsi+48h], eax
0x18018c26a  mov     [rsi+50h], r13d
0x18018c26e  mov     rcx, [rsp+1D0h+var_1A0]
0x18018c273  mov     rax, [rcx]
0x18018c276  mov     rdx, r15
0x18018c279  mov     rax, [rax+68h]
0x18018c27d  call    cs:__guard_dispatch_icall_fptr
0x18018c283  test    eax, eax
0x18018c285  js      loc_18018C3EC
0x18018c28b  mov     rcx, [r15]
0x18018c28e  mov     ebx, r13d
0x18018c291  mov     rax, [rcx]
0x18018c294  mov     rax, [rax+18h]
0x18018c298  call    cs:__guard_dispatch_icall_fptr
0x18018c29e  mov     edi, 2
0x18018c2a3  test    eax, eax
0x18018c2a5  jz      short loc_18018C2C3
0x18018c2a7  sub     eax, 1
0x18018c2aa  jz      short loc_18018C2C3
0x18018c2ac  sub     eax, 1
0x18018c2af  jz      short loc_18018C2C3
0x18018c2b1  sub     eax, 1
0x18018c2b4  jz      short loc_18018C2BF
0x18018c2b6  cmp     eax, edi
0x18018c2b8  jnz     short loc_18018C2C8
0x18018c2ba  lea     ebx, [rdi-1]
0x18018c2bd  jmp     short loc_18018C2C8
0x18018c2bf  mov     ebx, edi
0x18018c2c1  jmp     short loc_18018C2C8
0x18018c2c3  mov     ebx, 8
0x18018c2c8  mov     [rsi+50h], ebx
0x18018c2cb  test    ebx, ebx
0x18018c2cd  jz      short loc_18018C2E3
0x18018c2cf  cmp     [rsi+0D0h], r13d
0x18018c2d6  jbe     short loc_18018C2E3
0x18018c2d8  lea     rcx, [rsi+20h]
0x18018c2dc  xor     edx, edx
0x18018c2de  call    ?Assign@?$TCntPtr@VArc2DRadialPathGradientBrushResource@GEL@@@Ofc@@AEAAXPEAVArc2DRadialPathGradientBrushResource@GEL@@@Z; Ofc::TCntPtr<GEL::Arc2DRadialPathGradientBrushResource>::Assign(GEL::Arc2DRadialPathGradientBrushResource *)
0x18018c2e3  test    r12b, r12b
0x18018c2e6  jnz     loc_18018C3EC
0x18018c2ec  lea     rdx, [rsi+30h]
0x18018c2f0  mov     rcx, [rsp+1D0h+var_1A0]
0x18018c2f5  call    cs:__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z; Mso::DWriteAssistant::GetFontSignature(IDWriteFont &,tagFONTSIGNATURE &)
0x18018c2fb  xor     eax, eax
0x18018c2fd  mov     [rsp+1D0h+var_158], rax
0x18018c302  mov     [rbp+0D0h+var_150], ax
0x18018c306  mov     [rsi+58h], rax
0x18018c30a  mov     [rsi+60h], ax
0x18018c30e  mov     [rsp+1D0h+var_198], r13
0x18018c313  mov     rcx, [rsp+1D0h+var_1A0]
0x18018c318  mov     rax, [rcx]
0x18018c31b  lea     r8, [rsp+1D0h+var_198]
0x18018c320  lea     rdx, _GUID_acd16696_8c14_4f5d_877e_fe3fc1d32738
0x18018c327  mov     rax, [rax]
0x18018c32a  call    cs:__guard_dispatch_icall_fptr
0x18018c330  mov     rcx, [rsp+1D0h+var_198]
0x18018c335  test    rcx, rcx
0x18018c338  jz      loc_18018C3EC
0x18018c33e  mov     rax, [rcx]
0x18018c341  lea     rdx, [rsp+1D0h+var_158]
0x18018c346  mov     rax, [rax+78h]
0x18018c34a  call    cs:__guard_dispatch_icall_fptr
0x18018c350  mov     dl, byte ptr [rsp+1D0h+var_158]
0x18018c354  mov     al, dl
0x18018c356  sub     al, dil
0x18018c359  cmp     al, 1
0x18018c35b  jbe     short loc_18018C369
0x18018c35d  xor     eax, eax
0x18018c35f  mov     [rsi+58h], rax
0x18018c363  mov     [rsi+60h], ax
0x18018c367  jmp     short loc_18018C3C5
0x18018c369  mov     [rsi+58h], dl
0x18018c36c  mov     rcx, [rsp+1D0h+var_158]
0x18018c371  mov     rax, rcx
0x18018c374  shr     rax, 8
0x18018c378  mov     [rsi+59h], al
0x18018c37b  mov     rax, rcx
0x18018c37e  shr     rax, 10h
0x18018c382  mov     [rsi+5Ah], al
0x18018c385  mov     rax, rcx
0x18018c388  shr     rax, 18h
0x18018c38c  mov     [rsi+5Bh], al
0x18018c38f  mov     rax, rcx
0x18018c392  shr     rax, 20h
0x18018c396  mov     [rsi+5Ch], al
0x18018c399  mov     rax, rcx
0x18018c39c  shr     rax, 28h
  ... truncated ...
```
