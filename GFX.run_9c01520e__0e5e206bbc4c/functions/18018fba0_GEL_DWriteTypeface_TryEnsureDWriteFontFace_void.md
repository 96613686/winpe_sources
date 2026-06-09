# GEL::DWriteTypeface::TryEnsureDWriteFontFace(void)

- ea: `0x18018fba0`
- end: `0x1801900ef`
- name: `?TryEnsureDWriteFontFace@DWriteTypeface@GEL@@AEAAPEAUIDWriteFontFace@@XZ`
- size: `1359`
- prototype: `struct IDWriteFontFace *__fastcall(GEL::DWriteTypeface *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18018ed80`
- `0x18018f090`

## callees

- `0x1800551d0`
- `0x1800578b0`
- `0x180057e70`
- `0x180072d00`
- `0x180072d20`
- `0x180077780`
- `0x1800c3558`
- `0x180166fb0`
- `0x18018d854`
- `0x18018ec74`
- `0x18018fba0`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018fc1d`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018fc1d`
- `mso40uiWin32Client!__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z` at `0x18018ffd5`
- `mso40uiWin32Client!__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z` at `0x18018ffd5`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18018fe65`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18018fe65`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18018fed4`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18018fed4`

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
        Ofc::TCntPtr<GEL::Arc2DRadialPathGradientBrushResource>::Assign((char *)this + 32);
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
          *((_BYTE *)this + 98) = sub_18018EC74(*v2, v22, v21);
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
0x18018fba0  mov     rax, rsp
0x18018fba3  mov     [rax+10h], rbx
0x18018fba7  mov     [rax+18h], rsi
0x18018fbab  mov     [rax+20h], rdi
0x18018fbaf  push    rbp
0x18018fbb0  push    r12
0x18018fbb2  push    r13
0x18018fbb4  push    r14
0x18018fbb6  push    r15
0x18018fbb8  lea     rbp, [rax-0D8h]
0x18018fbbf  sub     rsp, 1B0h
0x18018fbc6  mov     rax, cs:__security_cookie
0x18018fbcd  xor     rax, rsp
0x18018fbd0  mov     [rbp+0D0h+var_30], rax
0x18018fbd7  mov     rsi, rcx
0x18018fbda  lea     r15, [rcx+0C0h]
0x18018fbe1  mov     rax, [r15]
0x18018fbe4  xor     r13d, r13d
0x18018fbe7  test    rax, rax
0x18018fbea  jnz     loc_18018FCC2
0x18018fbf0  mov     r12b, r13b
0x18018fbf3  lea     r14, [rcx+0C8h]
0x18018fbfa  cmp     [r14], r13
0x18018fbfd  jnz     loc_18018FCF7
0x18018fc03  cmp     [rcx+64h], r13b
0x18018fc07  jnz     loc_18018FCF2
0x18018fc0d  cmp     [rcx+0D0h], r13d
0x18018fc14  jbe     loc_18018FCF2
0x18018fc1a  mov     r12b, 1
0x18018fc1d  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018fc23  mov     rcx, rax; this
0x18018fc26  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018fc2b  mov     rdi, rax
0x18018fc2e  mov     rcx, [rax]
0x18018fc31  mov     rbx, [rcx+20h]
0x18018fc35  mov     rcx, r14
0x18018fc38  call    ??1?$TCntPtr@UIDWriteNumberSubstitution@@@Mso@@QEAA@XZ; Mso::TCntPtr<IDWriteNumberSubstitution>::~TCntPtr<IDWriteNumberSubstitution>(void)
0x18018fc3d  mov     r8, r14
0x18018fc40  mov     edx, [rsi+0D0h]
0x18018fc46  mov     rcx, rdi
0x18018fc49  mov     rax, rbx
0x18018fc4c  call    cs:__guard_dispatch_icall_fptr
0x18018fc52  test    eax, eax
0x18018fc54  jns     loc_18018FCF2
0x18018fc5a  lea     rdx, aHresult; "HRESULT"
0x18018fc61  mov     [rbp+0D0h+var_138], rdx
0x18018fc65  mov     [rbp+0D0h+var_130], eax
0x18018fc68  xorps   xmm0, xmm0
0x18018fc6b  movups  [rbp+0D0h+var_128], xmm0
0x18018fc6f  mov     qword ptr [rbp+0D0h+var_118], r13
0x18018fc73  mov     qword ptr [rbp+0D0h+var_118+8], 7
0x18018fc7b  mov     word ptr [rbp+0D0h+var_128], r13w
0x18018fc80  lea     ecx, [r13+4]
0x18018fc84  mov     [rbp+0D0h+var_108], cx
0x18018fc88  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18018fc8f  mov     [rbp+0D0h+var_140], rax
0x18018fc93  lea     rax, aFailedToGetFon; "Failed to get font family"
0x18018fc9a  mov     [rsp+1D0h+var_198], rax
0x18018fc9f  lea     rax, [rbp+0D0h+var_140]
0x18018fca3  mov     [rsp+1D0h+var_1A8], rax
0x18018fca8  lea     rax, [rsp+1D0h+var_198]
0x18018fcad  mov     [rsp+1D0h+var_1B0], rax
0x18018fcb2  call    ??$SendDiagnosticTrace@UClassifiedStructuredHrNamed@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUClassifiedStructuredHrNamed@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredHrNamed>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredHrNamed &&)
0x18018fcb7  lea     rcx, [rbp+0D0h+var_128]
0x18018fcbb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018fcc0  xor     eax, eax
0x18018fcc2  mov     rcx, [rbp+0D0h+var_30]
0x18018fcc9  xor     rcx, rsp; StackCookie
0x18018fccc  call    __security_check_cookie
0x18018fcd1  lea     r11, [rsp+1D0h+var_20]
0x18018fcd9  mov     rbx, [r11+38h]
0x18018fcdd  mov     rsi, [r11+40h]
0x18018fce1  mov     rdi, [r11+48h]
0x18018fce5  mov     rsp, r11
0x18018fce8  pop     r15
0x18018fcea  pop     r14
0x18018fcec  pop     r13
0x18018fcee  pop     r12
0x18018fcf0  pop     rbp
0x18018fcf1  retn
0x18018fcf2  cmp     [r14], r13
0x18018fcf5  jz      short loc_18018FCC0
0x18018fcf7  mov     rcx, [rsi+70h]
0x18018fcfb  test    rcx, rcx
0x18018fcfe  jz      short loc_18018FD05
0x18018fd00  call    ??_E?$TOwnerPtr@UWidthCache@GEL@@@Ofc@@QEAAPEAXI@Z; Ofc::TOwnerPtr<GEL::WidthCache>::`vector deleting destructor'(uint)
0x18018fd05  mov     [rsi+70h], r13
0x18018fd09  mov     [rsp+1D0h+var_1A0], r13
0x18018fd0e  mov     rcx, r14
0x18018fd11  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18018fd16  mov     r10, rax
0x18018fd19  mov     rcx, [rax]
0x18018fd1c  mov     rax, [rcx+38h]
0x18018fd20  lea     rcx, [rsp+1D0h+var_1A0]
0x18018fd25  mov     [rsp+1D0h+var_1B0], rcx
0x18018fd2a  mov     r9d, [rsi+0D8h]
0x18018fd31  mov     r8d, [rsi+0D4h]
0x18018fd38  mov     edx, [rsi+4Ch]
0x18018fd3b  mov     rcx, r10
0x18018fd3e  call    cs:__guard_dispatch_icall_fptr
0x18018fd44  mov     ebx, eax
0x18018fd46  test    eax, eax
0x18018fd48  jns     loc_18018FF21
0x18018fd4e  cmp     [rsi+0D0h], r13d
0x18018fd55  jbe     short loc_18018FD6C
0x18018fd57  mov     rcx, [rsi]
0x18018fd5a  mov     rax, [rcx+10h]
0x18018fd5e  mov     rcx, rsi
0x18018fd61  call    cs:__guard_dispatch_icall_fptr
0x18018fd67  mov     rcx, [rax]
0x18018fd6a  jmp     short loc_18018FD73
0x18018fd6c  lea     rcx, aRedacted; "<redacted>"
0x18018fd73  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18018fd7a  mov     [rbp+0D0h+var_70], rax
0x18018fd7e  lea     rax, aFont; "Font"
0x18018fd85  mov     [rbp+0D0h+var_68], rax
0x18018fd89  mov     [rbp+0D0h+var_60], rcx
0x18018fd8d  mov     ecx, 4
0x18018fd92  mov     [rbp+0D0h+var_58], cx
0x18018fd96  xorps   xmm0, xmm0
0x18018fd99  movups  [rbp+0D0h+var_50], xmm0
0x18018fda0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18018fda8  movdqa  [rbp+0D0h+var_40], xmm1
0x18018fdb0  mov     word ptr [rbp+0D0h+var_50], r13w
0x18018fdb8  lea     rdx, aHresult; "HRESULT"
0x18018fdbf  mov     [rbp+0D0h+var_A8], rdx
0x18018fdc3  mov     [rbp+0D0h+var_A0], ebx
0x18018fdc6  movups  [rbp+0D0h+var_98], xmm0
0x18018fdca  mov     [rbp+0D0h+var_88], r13
0x18018fdce  mov     [rbp+0D0h+var_80], 7
0x18018fdd6  mov     word ptr [rbp+0D0h+var_98], r13w
0x18018fddb  mov     [rbp+0D0h+var_78], cx
0x18018fddf  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18018fde6  mov     [rbp+0D0h+var_B0], rax
0x18018fdea  lea     rax, ??_7?$ClassifiedStructuredObject@_N@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable'
0x18018fdf1  mov     [rbp+0D0h+var_140], rax
0x18018fdf5  lea     rax, aFontloaded; "FontLoaded"
0x18018fdfc  mov     [rbp+0D0h+var_138], rax
0x18018fe00  mov     al, [rsi+64h]
0x18018fe03  mov     byte ptr [rbp+0D0h+var_130], al
0x18018fe06  mov     word ptr [rbp+0D0h+var_130+2], cx
0x18018fe0a  movups  [rbp+0D0h+var_128], xmm0
0x18018fe0e  movdqu  [rbp+0D0h+var_118], xmm1
0x18018fe13  mov     word ptr [rbp+0D0h+var_128], r13w
0x18018fe18  lea     rax, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18018fe1f  mov     [rbp+0D0h+var_E8], rax
0x18018fe23  lea     rax, aCloudindex; "CloudIndex"
0x18018fe2a  mov     [rbp+0D0h+var_E0], rax
0x18018fe2e  mov     eax, [rsi+0D0h]
0x18018fe34  mov     [rbp+0D0h+var_D8], eax
0x18018fe37  mov     [rbp+0D0h+var_D4], cx
0x18018fe3b  movups  [rbp+0D0h+var_D0], xmm0
0x18018fe3f  movdqu  [rbp+0D0h+var_C0], xmm1
0x18018fe44  mov     word ptr [rbp+0D0h+var_D0], r13w
0x18018fe49  lea     edi, [rcx-2]
0x18018fe4c  mov     r9d, edi
0x18018fe4f  lea     ebx, [rcx+6]
0x18018fe52  mov     r8d, ebx
0x18018fe55  mov     esi, 0ADh
0x18018fe5a  mov     edx, esi
0x18018fe5c  mov     r14d, 1E60B8C5h
0x18018fe62  mov     ecx, r14d
0x18018fe65  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18018fe6b  test    al, al
0x18018fe6d  jz      short loc_18018FEDA
0x18018fe6f  lea     rax, [rbp+0D0h+var_E8]
0x18018fe73  mov     [rsp+1D0h+var_190], rax
0x18018fe78  lea     rax, [rbp+0D0h+var_140]
0x18018fe7c  mov     [rsp+1D0h+var_188], rax
0x18018fe81  lea     rax, [rbp+0D0h+var_B0]
0x18018fe85  mov     [rsp+1D0h+var_180], rax
0x18018fe8a  lea     rax, [rbp+0D0h+var_70]
0x18018fe8e  mov     [rsp+1D0h+var_178], rax
0x18018fe93  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18018fe9a  mov     [rsp+1D0h+var_170], rax
0x18018fe9f  lea     rax, [rsp+1D0h+var_190]
0x18018fea4  mov     [rsp+1D0h+var_168], rax
0x18018fea9  lea     rax, [rsp+1D0h+var_170]
0x18018feae  mov     [rsp+1D0h+var_160], rax
0x18018feb3  mov     r9d, edi
0x18018feb6  lea     rax, [rsp+1D0h+var_170]
0x18018febb  mov     [rsp+1D0h+var_1A8], rax
0x18018fec0  lea     rax, aFailedToGetFir; "Failed to get first matching font"
0x18018fec7  mov     [rsp+1D0h+var_1B0], rax
0x18018fecc  mov     r8d, ebx
0x18018fecf  mov     edx, esi
0x18018fed1  mov     ecx, r14d
0x18018fed4  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
0x18018feda  lea     rcx, [rbp+0D0h+var_D0]
0x18018fede  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018fee3  lea     rcx, [rbp+0D0h+var_128]
0x18018fee7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018feec  lea     rcx, [rbp+0D0h+var_98]
0x18018fef0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018fef5  lea     rcx, [rbp+0D0h+var_50]
0x18018fefc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018ff01  mov     rcx, [rsp+1D0h+var_1A0]
0x18018ff06  test    rcx, rcx
0x18018ff09  jz      loc_18018FCC0
0x18018ff0f  mov     rax, [rcx]
0x18018ff12  mov     rax, [rax+10h]
0x18018ff16  call    cs:__guard_dispatch_icall_fptr
0x18018ff1c  jmp     loc_18018FCC0
0x18018ff21  xorps   xmm0, xmm0
0x18018ff24  xor     eax, eax
0x18018ff26  movups  [rbp+0D0h+var_100], xmm0
0x18018ff2a  mov     [rbp+0D0h+var_F0], eax
0x18018ff2d  mov     rcx, [rsp+1D0h+var_1A0]
0x18018ff32  mov     rax, [rcx]
0x18018ff35  lea     rdx, [rbp+0D0h+var_100]
0x18018ff39  mov     rax, [rax+58h]
0x18018ff3d  call    cs:__guard_dispatch_icall_fptr
0x18018ff43  movzx   eax, word ptr [rbp+0D0h+var_100]
0x18018ff47  mov     [rsi+48h], eax
0x18018ff4a  mov     [rsi+50h], r13d
0x18018ff4e  mov     rcx, [rsp+1D0h+var_1A0]
0x18018ff53  mov     rax, [rcx]
0x18018ff56  mov     rdx, r15
0x18018ff59  mov     rax, [rax+68h]
0x18018ff5d  call    cs:__guard_dispatch_icall_fptr
0x18018ff63  test    eax, eax
0x18018ff65  js      loc_1801900CC
0x18018ff6b  mov     rcx, [r15]
0x18018ff6e  mov     ebx, r13d
0x18018ff71  mov     rax, [rcx]
0x18018ff74  mov     rax, [rax+18h]
0x18018ff78  call    cs:__guard_dispatch_icall_fptr
0x18018ff7e  mov     edi, 2
0x18018ff83  test    eax, eax
0x18018ff85  jz      short loc_18018FFA3
0x18018ff87  sub     eax, 1
0x18018ff8a  jz      short loc_18018FFA3
0x18018ff8c  sub     eax, 1
0x18018ff8f  jz      short loc_18018FFA3
0x18018ff91  sub     eax, 1
0x18018ff94  jz      short loc_18018FF9F
0x18018ff96  cmp     eax, edi
0x18018ff98  jnz     short loc_18018FFA8
0x18018ff9a  lea     ebx, [rdi-1]
0x18018ff9d  jmp     short loc_18018FFA8
0x18018ff9f  mov     ebx, edi
0x18018ffa1  jmp     short loc_18018FFA8
0x18018ffa3  mov     ebx, 8
0x18018ffa8  mov     [rsi+50h], ebx
0x18018ffab  test    ebx, ebx
0x18018ffad  jz      short loc_18018FFC3
0x18018ffaf  cmp     [rsi+0D0h], r13d
0x18018ffb6  jbe     short loc_18018FFC3
0x18018ffb8  lea     rcx, [rsi+20h]
0x18018ffbc  xor     edx, edx
0x18018ffbe  call    ?Assign@?$TCntPtr@VArc2DRadialPathGradientBrushResource@GEL@@@Ofc@@AEAAXPEAVArc2DRadialPathGradientBrushResource@GEL@@@Z; Ofc::TCntPtr<GEL::Arc2DRadialPathGradientBrushResource>::Assign(GEL::Arc2DRadialPathGradientBrushResource *)
0x18018ffc3  test    r12b, r12b
0x18018ffc6  jnz     loc_1801900CC
0x18018ffcc  lea     rdx, [rsi+30h]
0x18018ffd0  mov     rcx, [rsp+1D0h+var_1A0]
0x18018ffd5  call    cs:__imp_?GetFontSignature@DWriteAssistant@Mso@@YAJAEAUIDWriteFont@@AEAUtagFONTSIGNATURE@@@Z; Mso::DWriteAssistant::GetFontSignature(IDWriteFont &,tagFONTSIGNATURE &)
0x18018ffdb  xor     eax, eax
0x18018ffdd  mov     [rsp+1D0h+var_158], rax
0x18018ffe2  mov     [rbp+0D0h+var_150], ax
0x18018ffe6  mov     [rsi+58h], rax
0x18018ffea  mov     [rsi+60h], ax
0x18018ffee  mov     [rsp+1D0h+var_198], r13
0x18018fff3  mov     rcx, [rsp+1D0h+var_1A0]
0x18018fff8  mov     rax, [rcx]
0x18018fffb  lea     r8, [rsp+1D0h+var_198]
0x180190000  lea     rdx, _GUID_acd16696_8c14_4f5d_877e_fe3fc1d32738
0x180190007  mov     rax, [rax]
0x18019000a  call    cs:__guard_dispatch_icall_fptr
0x180190010  mov     rcx, [rsp+1D0h+var_198]
0x180190015  test    rcx, rcx
0x180190018  jz      loc_1801900CC
0x18019001e  mov     rax, [rcx]
0x180190021  lea     rdx, [rsp+1D0h+var_158]
0x180190026  mov     rax, [rax+78h]
0x18019002a  call    cs:__guard_dispatch_icall_fptr
0x180190030  mov     dl, byte ptr [rsp+1D0h+var_158]
0x180190034  mov     al, dl
0x180190036  sub     al, dil
0x180190039  cmp     al, 1
0x18019003b  jbe     short loc_180190049
0x18019003d  xor     eax, eax
0x18019003f  mov     [rsi+58h], rax
0x180190043  mov     [rsi+60h], ax
0x180190047  jmp     short loc_1801900A5
0x180190049  mov     [rsi+58h], dl
0x18019004c  mov     rcx, [rsp+1D0h+var_158]
0x180190051  mov     rax, rcx
0x180190054  shr     rax, 8
0x180190058  mov     [rsi+59h], al
0x18019005b  mov     rax, rcx
0x18019005e  shr     rax, 10h
0x180190062  mov     [rsi+5Ah], al
0x180190065  mov     rax, rcx
0x180190068  shr     rax, 18h
0x18019006c  mov     [rsi+5Bh], al
0x18019006f  mov     rax, rcx
0x180190072  shr     rax, 20h
0x180190076  mov     [rsi+5Ch], al
0x180190079  mov     rax, rcx
0x18019007c  shr     rax, 28h
  ... truncated ...
```
