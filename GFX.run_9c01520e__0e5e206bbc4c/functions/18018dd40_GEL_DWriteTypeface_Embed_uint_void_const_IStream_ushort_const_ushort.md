# GEL::DWriteTypeface::Embed(uint,void const *,IStream &,ushort const *,ushort)

- ea: `0x18018dd40`
- end: `0x18018e0f2`
- name: `?Embed@DWriteTypeface@GEL@@UEBAJIPEBXAEAUIStream@@PEBGG@Z`
- size: `946`
- prototype: `__int64 __usercall@<rax>(GEL::DWriteTypeface *__hidden this@<rcx>, unsigned int@<edx>, const void *@<r8>, struct IStream *@<r9>, const unsigned __int16 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180007e18`
- `0x18000b5a8`
- `0x18002b340`
- `0x18002b6ec`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x1800706ec`
- `0x180077780`
- `0x180090370`
- `0x1800904c8`
- `0x1800daa88`
- `0x18018dd40`
- `0x18018eebc`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z` at `0x18018e07c`
- `mso40uiWin32Client!__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z` at `0x18018e07c`
- `Mso30Win32Client!__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18018dd79`
- `Mso30Win32Client!__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18018dd79`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018de9c`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018e0c7`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018de9c`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018e0c7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018ddf5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018de25`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018de6a`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018ddf5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018de25`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018de6a`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x18018ddc5`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x18018ddc5`

## string_xrefs

- `0x18018de55`: `m_pDWriteFontFamily cannot be nullptr, skipping this font`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GEL::DWriteTypeface::Embed(
        GEL::DWriteTypeface *this,
        int a2,
        const void *a3,
        struct IStream *a4,
        const unsigned __int16 *a5,
        unsigned __int16 a6)
{
  struct Mso::Telemetry::IActivityParenter *v10; // rbx
  __int64 v11; // rax
  struct Mso::Telemetry::IDataFieldCollection *v12; // rbx
  _QWORD *v13; // rax
  struct Mso::Telemetry::IDataFieldCollection *v14; // rax
  __int128 *p_Src; // r8
  struct Mso::Telemetry::IDataFieldCollection *v16; // rax
  __int128 *v17; // r8
  const struct GEL::ITypefaceList *DefaultTypefaces; // rbx
  __int64 v20; // rax
  Mso::DWriteAssistant *v21; // r14
  wchar_t **v22; // rax
  bool *v23; // r8
  unsigned int IsEmbeddingEnabled; // ebx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  struct IDWriteFontFace **v30; // rax
  __int64 v31; // rcx
  void (*v32)(void); // rax
  __int64 v33; // rcx
  const unsigned __int16 *v34; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v35; // [rsp+28h] [rbp-D8h]
  void *v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[16]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 Src; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+98h] [rbp-68h]
  __int128 v43; // [rsp+A8h] [rbp-58h] BYREF
  struct tagLOGFONTW v44; // [rsp+C0h] [rbp-40h] BYREF

  v39[0] = Office::Text::FontEmbedding::GetNamespace(this);
  v39[1] = "Embed";
  v10 = Mso::Telemetry::Activity::UseThreadCurrentParenter();
  v11 = Mso::Telemetry::EventFlags::EventFlags(v40, 0);
  *(_WORD *)((char *)&v36 + 1) = 256;
  Mso::Telemetry::Activity::Activity(v38, v39, v10, 256, v11);
  Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v38, 1);
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v12 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v38);
  v13 = (_QWORD *)(*(__int64 (__fastcall **)(GEL::DWriteTypeface *))(*(_QWORD *)this + 16LL))(this);
  Mso::Telemetry::IDataFieldCollection::Add(v12, "FaceName", *v13);
  v14 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v38);
  p_Src = &Src;
  if ( si128.m128i_i64[1] > 7uLL )
    p_Src = (__int128 *)Src;
  Mso::Telemetry::IDataFieldCollection::Add(v14, "ErrorMessage", p_Src);
  if ( !*((_QWORD *)this + 25) )
  {
    std::wstring::append(&Src);
    v16 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v38);
    v17 = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v17 = (__int128 *)Src;
    Mso::Telemetry::IDataFieldCollection::Add(v16, "ErrorMessage", v17);
    goto LABEL_7;
  }
  DefaultTypefaces = GEL::ITypefaceList::GetDefaultTypefaces();
  memset_0(&v44, 0, sizeof(v44));
  GEL::Typeface::GetLOGFONT(this, &v44, 8, a2 | 0x18, a3, DefaultTypefaces, 0, 0, 0, 0);
  (*(void (__fastcall **)(GEL::DWriteTypeface *, __int64 *, const struct GEL::ITypefaceList *, const void *, struct tagLOGFONTW *, int))(*(_QWORD *)this + 392LL))(
    this,
    &v37,
    DefaultTypefaces,
    a3,
    &v44,
    a2);
  if ( !v37 )
  {
LABEL_7:
    std::wstring::~wstring(&Src);
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v38);
    return 0;
  }
  v20 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(&v37);
  v21 = (Mso::DWriteAssistant *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
  LOBYTE(v36) = 1;
  v22 = (wchar_t **)(*(__int64 (__fastcall **)(GEL::DWriteTypeface *))(*(_QWORD *)this + 16LL))(this);
  IsEmbeddingEnabled = GEL::IsEmbeddingEnabled(*v22, (const wchar_t *)&v36, v23);
  if ( IsEmbeddingEnabled || !(_BYTE)v36 )
  {
    v33 = v37;
    if ( v37 )
    {
      v37 = 0;
      v32 = *(void (**)(void))(*(_QWORD *)v33 + 8LL);
      goto LABEL_20;
    }
  }
  else
  {
    if ( !a2 )
    {
      v25 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(&v37);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26) >= 700
        || (v27 = Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(&v37),
            v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27),
            (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28)) )
      {
        v29 = v37;
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        }
        goto LABEL_7;
      }
    }
    v43 = 0;
    v30 = (struct IDWriteFontFace **)(*(__int64 (__fastcall **)(GEL::DWriteTypeface *))(*(_QWORD *)this + 16LL))(this);
    LOBYTE(v35) = 1;
    LOWORD(v34) = a6;
    IsEmbeddingEnabled = Mso::DWriteAssistant::GetEmbeddedFontStream(
                           v21,
                           *v30,
                           (const wchar_t *)((unsigned int)(a5 != 0) + 4),
                           (unsigned int)a5,
                           v34,
                           v35,
                           0,
                           (bool)&v43,
                           (const struct _GUID *)GEL::WriteToStream,
                           (unsigned int (*)(void *, const void *, unsigned int))a4,
                           v36);
    v31 = v37;
    if ( v37 )
    {
      v37 = 0;
      v32 = *(void (**)(void))(*(_QWORD *)v31 + 8LL);
LABEL_20:
      v32();
    }
  }
  std::wstring::~wstring(&Src);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v38);
  return IsEmbeddingEnabled;
}

```

## disassembly

```asm
0x18018dd40  push    rbp
0x18018dd42  push    rbx
0x18018dd43  push    rsi
0x18018dd44  push    rdi
0x18018dd45  push    r12
0x18018dd47  push    r13
0x18018dd49  push    r14
0x18018dd4b  push    r15
0x18018dd4d  lea     rbp, [rsp-38h]
0x18018dd52  sub     rsp, 138h
0x18018dd59  mov     rax, cs:__security_cookie
0x18018dd60  xor     rax, rsp
0x18018dd63  mov     [rbp+70h+var_50], rax
0x18018dd67  mov     r12, r9
0x18018dd6a  mov     r14, r8
0x18018dd6d  mov     esi, edx
0x18018dd6f  mov     rdi, rcx
0x18018dd72  mov     r15, [rbp+70h+arg_20]
0x18018dd79  call    cs:__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::Text::FontEmbedding::GetNamespace(void)
0x18018dd7f  mov     [rsp+170h+var_100], rax
0x18018dd84  lea     rax, aEmbed; "Embed"
0x18018dd8b  mov     [rsp+170h+var_F8], rax
0x18018dd90  call    ?UseThreadCurrentParenter@Activity@Telemetry@Mso@@SAAEAUIActivityParenter@23@XZ; Mso::Telemetry::Activity::UseThreadCurrentParenter(void)
0x18018dd95  mov     rbx, rax
0x18018dd98  xor     edx, edx
0x18018dd9a  lea     rcx, [rbp+70h+var_F0]
0x18018dd9e  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x18018dda3  xor     r13d, r13d
0x18018dda6  mov     word ptr [rsp+170h+var_120+1], 100h
0x18018ddad  mov     [rsp+170h+var_150], rax
0x18018ddb2  movzx   r9d, word ptr [rsp+170h+var_120+1]
0x18018ddb8  mov     r8, rbx
0x18018ddbb  lea     rdx, [rsp+170h+var_100]
0x18018ddc0  lea     rcx, [rsp+170h+var_110]
0x18018ddc5  call    cs:__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::IActivityParenter const &,Mso::Telemetry::ActivityAggregation,Mso::Telemetry::EventFlags const &)
0x18018ddcb  mov     dl, 1; bool
0x18018ddcd  lea     rcx, [rsp+170h+var_110]; this
0x18018ddd2  call    ?SetSuccess@Activity@Telemetry@Mso@@QEAAX_N@Z; Mso::Telemetry::Activity::SetSuccess(bool)
0x18018ddd7  xorps   xmm0, xmm0
0x18018ddda  movups  [rbp+70h+Src], xmm0
0x18018ddde  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18018dde6  movdqu  [rbp+70h+var_D8], xmm1
0x18018ddeb  mov     word ptr [rbp+70h+Src], r13w
0x18018ddf0  lea     rcx, [rsp+170h+var_110]
0x18018ddf5  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018ddfb  mov     rbx, rax
0x18018ddfe  mov     rcx, [rdi]
0x18018de01  mov     rax, [rcx+10h]
0x18018de05  mov     rcx, rdi
0x18018de08  call    cs:__guard_dispatch_icall_fptr
0x18018de0e  mov     r8, [rax]
0x18018de11  lea     rdx, aFacename; "FaceName"
0x18018de18  mov     rcx, rbx
0x18018de1b  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018de20  lea     rcx, [rsp+170h+var_110]
0x18018de25  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018de2b  lea     r8, [rbp+70h+Src]
0x18018de2f  cmp     qword ptr [rbp+70h+var_D8+8], 7
0x18018de34  cmova   r8, qword ptr [rbp+70h+Src]
0x18018de39  lea     rdx, aErrormessage; "ErrorMessage"
0x18018de40  mov     rcx, rax
0x18018de43  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018de48  cmp     [rdi+0C8h], r13
0x18018de4f  jnz     short loc_18018DEA9
0x18018de51  lea     r8d, [r13+39h]
0x18018de55  lea     rdx, aMPdwritefontfa; "m_pDWriteFontFamily cannot be nullptr, "...
0x18018de5c  lea     rcx, [rbp+70h+Src]; Src
0x18018de60  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18018de65  lea     rcx, [rsp+170h+var_110]
0x18018de6a  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018de70  lea     r8, [rbp+70h+Src]
0x18018de74  cmp     qword ptr [rbp+70h+var_D8+8], 7
0x18018de79  cmova   r8, qword ptr [rbp+70h+Src]
0x18018de7e  lea     rdx, aErrormessage; "ErrorMessage"
0x18018de85  mov     rcx, rax
0x18018de88  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018de8d  nop
0x18018de8e  lea     rcx, [rbp+70h+Src]
0x18018de92  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018de97  lea     rcx, [rsp+170h+var_110]
0x18018de9c  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x18018dea2  xor     eax, eax
0x18018dea4  jmp     loc_18018E0D2
0x18018dea9  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018deae  mov     rbx, rax
0x18018deb1  xor     edx, edx; Val
0x18018deb3  lea     r8d, [rdx+5Ch]; Size
0x18018deb7  lea     rcx, [rbp+70h+var_B0]; void *
0x18018debb  call    memset_0
0x18018dec0  mov     r9d, esi
0x18018dec3  or      r9d, 18h; unsigned int
0x18018dec7  mov     [rsp+170h+var_128], r13b; bool
0x18018decc  mov     [rsp+170h+var_130], r13; unsigned __int16 *
0x18018ded1  mov     [rsp+170h+var_138], r13; unsigned __int8 *
0x18018ded6  mov     [rsp+170h+var_140], r13; unsigned __int8 *
0x18018dedb  mov     [rsp+170h+var_148], rbx; struct GEL::ITypefaceList *
0x18018dee0  mov     [rsp+170h+var_150], r14; void *
0x18018dee5  mov     r8d, 8; int
0x18018deeb  lea     rdx, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x18018deef  mov     rcx, rdi; this
0x18018def2  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x18018def7  mov     rax, [rdi]
0x18018defa  mov     dword ptr [rsp+170h+var_148], esi
0x18018defe  lea     rcx, [rbp+70h+var_B0]
0x18018df02  mov     [rsp+170h+var_150], rcx
0x18018df07  mov     r9, r14
0x18018df0a  mov     r8, rbx
0x18018df0d  lea     rdx, [rsp+170h+var_118]
0x18018df12  mov     rcx, rdi
0x18018df15  mov     rax, [rax+188h]
0x18018df1c  call    cs:__guard_dispatch_icall_fptr
0x18018df22  nop
0x18018df23  cmp     [rsp+170h+var_118], r13
0x18018df28  jnz     short loc_18018DF2F
0x18018df2a  jmp     loc_18018DE8E
0x18018df2f  lea     rcx, [rsp+170h+var_118]
0x18018df34  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x18018df39  mov     rdx, rax
0x18018df3c  mov     rcx, [rax]
0x18018df3f  mov     rax, [rcx+18h]
0x18018df43  mov     rcx, rdx
0x18018df46  call    cs:__guard_dispatch_icall_fptr
0x18018df4c  mov     r14, rax
0x18018df4f  mov     byte ptr [rsp+170h+var_120], 1
0x18018df54  mov     rcx, [rdi]
0x18018df57  mov     rax, [rcx+10h]
0x18018df5b  mov     rcx, rdi
0x18018df5e  call    cs:__guard_dispatch_icall_fptr
0x18018df64  lea     rdx, [rsp+170h+var_120]; wchar_t *
0x18018df69  mov     rcx, [rax]; this
0x18018df6c  call    ?IsEmbeddingEnabled@GEL@@YAHPEB_WPEA_N@Z; GEL::IsEmbeddingEnabled(wchar_t const *,bool *)
0x18018df71  mov     ebx, eax
0x18018df73  test    eax, eax
0x18018df75  jnz     loc_18018E09C
0x18018df7b  cmp     byte ptr [rsp+170h+var_120], r13b
0x18018df80  jz      loc_18018E09C
0x18018df86  test    esi, esi
0x18018df88  jnz     loc_18018E01E
0x18018df8e  lea     rcx, [rsp+170h+var_118]
0x18018df93  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x18018df98  mov     rdx, rax
0x18018df9b  mov     rcx, [rax]
0x18018df9e  mov     rax, [rcx+10h]
0x18018dfa2  mov     rcx, rdx
0x18018dfa5  call    cs:__guard_dispatch_icall_fptr
0x18018dfab  mov     rdx, rax
0x18018dfae  mov     rcx, [rax]
0x18018dfb1  mov     rax, [rcx+20h]
0x18018dfb5  mov     rcx, rdx
0x18018dfb8  call    cs:__guard_dispatch_icall_fptr
0x18018dfbe  cmp     eax, 2BCh
0x18018dfc3  jge     short loc_18018DFF9
0x18018dfc5  lea     rcx, [rsp+170h+var_118]
0x18018dfca  call    ??C?$TCntPtr@UITextRunSequence@DWriteAssistant@Mso@@@Mso@@QEBAPEAUITextRunSequence@DWriteAssistant@1@XZ; Mso::TCntPtr<Mso::DWriteAssistant::ITextRunSequence>::operator->(void)
0x18018dfcf  mov     rdx, rax
0x18018dfd2  mov     rcx, [rax]
0x18018dfd5  mov     rax, [rcx+10h]
0x18018dfd9  mov     rcx, rdx
0x18018dfdc  call    cs:__guard_dispatch_icall_fptr
0x18018dfe2  mov     rdx, rax
0x18018dfe5  mov     rcx, [rax]
0x18018dfe8  mov     rax, [rcx+30h]
0x18018dfec  mov     rcx, rdx
0x18018dfef  call    cs:__guard_dispatch_icall_fptr
0x18018dff5  test    eax, eax
0x18018dff7  jz      short loc_18018E01E
0x18018dff9  mov     rcx, [rsp+170h+var_118]
0x18018dffe  test    rcx, rcx
0x18018e001  jz      loc_18018DE8E
0x18018e007  mov     [rsp+170h+var_118], r13
0x18018e00c  mov     rax, [rcx]
0x18018e00f  mov     rax, [rax+8]
0x18018e013  call    cs:__guard_dispatch_icall_fptr
0x18018e019  jmp     loc_18018DE8E
0x18018e01e  mov     rax, r15
0x18018e021  neg     rax
0x18018e024  sbb     ebx, ebx
0x18018e026  neg     ebx
0x18018e028  xorps   xmm0, xmm0
0x18018e02b  movups  [rbp+70h+var_C8], xmm0
0x18018e02f  mov     rax, [rdi]
0x18018e032  mov     rcx, rdi
0x18018e035  mov     rax, [rax+10h]
0x18018e039  call    cs:__guard_dispatch_icall_fptr
0x18018e03f  mov     rdx, [rax]
0x18018e042  mov     qword ptr [rsp+170h+var_128], r12
0x18018e047  lea     rax, ?WriteToStream@GEL@@YAKPEAXPEBXK@Z; GEL::WriteToStream(void *,void const *,ulong)
0x18018e04e  mov     [rsp+170h+var_130], rax
0x18018e053  lea     rax, [rbp+70h+var_C8]
0x18018e057  mov     [rsp+170h+var_138], rax
0x18018e05c  mov     byte ptr [rsp+170h+var_140], r13b
0x18018e061  mov     byte ptr [rsp+170h+var_148], 1
0x18018e066  movzx   eax, [rbp+70h+arg_28]
0x18018e06d  mov     word ptr [rsp+170h+var_150], ax
0x18018e072  mov     r9, r15
0x18018e075  lea     r8d, [rbx+4]
0x18018e079  mov     rcx, r14
0x18018e07c  call    cs:__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z; Mso::DWriteAssistant::GetEmbeddedFontStream(IDWriteFontFace *,wchar_t const *,uint,ushort const *,ushort,bool,bool,_GUID const &,ulong (*)(void *,void const *,ulong),void *)
0x18018e082  mov     ebx, eax
0x18018e084  mov     rcx, [rsp+170h+var_118]
0x18018e089  test    rcx, rcx
0x18018e08c  jz      short loc_18018E0B9
0x18018e08e  mov     [rsp+170h+var_118], r13
0x18018e093  mov     rdx, [rcx]
0x18018e096  mov     rax, [rdx+8]
0x18018e09a  jmp     short loc_18018E0B2
0x18018e09c  mov     rcx, [rsp+170h+var_118]
0x18018e0a1  test    rcx, rcx
0x18018e0a4  jz      short loc_18018E0B9
0x18018e0a6  mov     [rsp+170h+var_118], r13
0x18018e0ab  mov     rax, [rcx]
0x18018e0ae  mov     rax, [rax+8]
0x18018e0b2  call    cs:__guard_dispatch_icall_fptr
0x18018e0b8  nop
0x18018e0b9  lea     rcx, [rbp+70h+Src]
0x18018e0bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018e0c2  lea     rcx, [rsp+170h+var_110]
0x18018e0c7  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x18018e0cd  nop     dword ptr [rax]
0x18018e0d0  mov     eax, ebx
0x18018e0d2  mov     rcx, [rbp+70h+var_50]
0x18018e0d6  xor     rcx, rsp; StackCookie
0x18018e0d9  call    __security_check_cookie
0x18018e0de  add     rsp, 138h
0x18018e0e5  pop     r15
0x18018e0e7  pop     r14
0x18018e0e9  pop     r13
0x18018e0eb  pop     r12
0x18018e0ed  pop     rdi
0x18018e0ee  pop     rsi
0x18018e0ef  pop     rbx
0x18018e0f0  pop     rbp
0x18018e0f1  retn
```
