# GEL::DWriteTypeface::Embed(uint,void const *,IStream &,ushort const *,ushort)

- ea: `0x18018a270`
- end: `0x18018a622`
- name: `?Embed@DWriteTypeface@GEL@@UEBAJIPEBXAEAUIStream@@PEBGG@Z`
- size: `946`
- prototype: `__int64 __usercall@<rax>(GEL::DWriteTypeface *__hidden this@<rcx>, unsigned int@<edx>, const void *@<r8>, struct IStream *@<r9>, const unsigned __int16 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180007d50`
- `0x18000b320`
- `0x180029c44`
- `0x180029fd0`
- `0x180055b26`
- `0x180055e60`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x1800795e4`
- `0x18007aa30`
- `0x180092b54`
- `0x18018a270`
- `0x18018b3ec`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z` at `0x18018a5ac`
- `mso40uiWin32Client!__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z` at `0x18018a5ac`
- `Mso30Win32Client!__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18018a2a9`
- `Mso30Win32Client!__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18018a2a9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018a3cc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018a5f7`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018a3cc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18018a5f7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a325`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a355`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a39a`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a325`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a355`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18018a39a`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x18018a2f5`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x18018a2f5`

## string_xrefs

- `0x18018a385`: `m_pDWriteFontFamily cannot be nullptr, skipping this font`

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
  v20 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v37);
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
      v25 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v37);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26) >= 700
        || (v27 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v37),
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
0x18018a270  push    rbp
0x18018a272  push    rbx
0x18018a273  push    rsi
0x18018a274  push    rdi
0x18018a275  push    r12
0x18018a277  push    r13
0x18018a279  push    r14
0x18018a27b  push    r15
0x18018a27d  lea     rbp, [rsp-38h]
0x18018a282  sub     rsp, 138h
0x18018a289  mov     rax, cs:__security_cookie
0x18018a290  xor     rax, rsp
0x18018a293  mov     [rbp+70h+var_50], rax
0x18018a297  mov     r12, r9
0x18018a29a  mov     r14, r8
0x18018a29d  mov     esi, edx
0x18018a29f  mov     rdi, rcx
0x18018a2a2  mov     r15, [rbp+70h+arg_20]
0x18018a2a9  call    cs:__imp_?GetNamespace@FontEmbedding@Text@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::Text::FontEmbedding::GetNamespace(void)
0x18018a2af  mov     [rsp+170h+var_100], rax
0x18018a2b4  lea     rax, aEmbed; "Embed"
0x18018a2bb  mov     [rsp+170h+var_F8], rax
0x18018a2c0  call    ?UseThreadCurrentParenter@Activity@Telemetry@Mso@@SAAEAUIActivityParenter@23@XZ; Mso::Telemetry::Activity::UseThreadCurrentParenter(void)
0x18018a2c5  mov     rbx, rax
0x18018a2c8  xor     edx, edx
0x18018a2ca  lea     rcx, [rbp+70h+var_F0]
0x18018a2ce  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x18018a2d3  xor     r13d, r13d
0x18018a2d6  mov     word ptr [rsp+170h+var_120+1], 100h
0x18018a2dd  mov     [rsp+170h+var_150], rax
0x18018a2e2  movzx   r9d, word ptr [rsp+170h+var_120+1]
0x18018a2e8  mov     r8, rbx
0x18018a2eb  lea     rdx, [rsp+170h+var_100]
0x18018a2f0  lea     rcx, [rsp+170h+var_110]
0x18018a2f5  call    cs:__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::IActivityParenter const &,Mso::Telemetry::ActivityAggregation,Mso::Telemetry::EventFlags const &)
0x18018a2fb  mov     dl, 1; bool
0x18018a2fd  lea     rcx, [rsp+170h+var_110]; this
0x18018a302  call    ?SetSuccess@Activity@Telemetry@Mso@@QEAAX_N@Z; Mso::Telemetry::Activity::SetSuccess(bool)
0x18018a307  xorps   xmm0, xmm0
0x18018a30a  movups  [rbp+70h+Src], xmm0
0x18018a30e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18018a316  movdqu  [rbp+70h+var_D8], xmm1
0x18018a31b  mov     word ptr [rbp+70h+Src], r13w
0x18018a320  lea     rcx, [rsp+170h+var_110]
0x18018a325  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018a32b  mov     rbx, rax
0x18018a32e  mov     rcx, [rdi]
0x18018a331  mov     rax, [rcx+10h]
0x18018a335  mov     rcx, rdi
0x18018a338  call    cs:__guard_dispatch_icall_fptr
0x18018a33e  mov     r8, [rax]
0x18018a341  lea     rdx, aFacename; "FaceName"
0x18018a348  mov     rcx, rbx
0x18018a34b  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018a350  lea     rcx, [rsp+170h+var_110]
0x18018a355  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018a35b  lea     r8, [rbp+70h+Src]
0x18018a35f  cmp     qword ptr [rbp+70h+var_D8+8], 7
0x18018a364  cmova   r8, qword ptr [rbp+70h+Src]
0x18018a369  lea     rdx, aErrormessage; "ErrorMessage"
0x18018a370  mov     rcx, rax
0x18018a373  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018a378  cmp     [rdi+0C8h], r13
0x18018a37f  jnz     short loc_18018A3D9
0x18018a381  lea     r8d, [r13+39h]
0x18018a385  lea     rdx, aMPdwritefontfa; "m_pDWriteFontFamily cannot be nullptr, "...
0x18018a38c  lea     rcx, [rbp+70h+Src]; Src
0x18018a390  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18018a395  lea     rcx, [rsp+170h+var_110]
0x18018a39a  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x18018a3a0  lea     r8, [rbp+70h+Src]
0x18018a3a4  cmp     qword ptr [rbp+70h+var_D8+8], 7
0x18018a3a9  cmova   r8, qword ptr [rbp+70h+Src]
0x18018a3ae  lea     rdx, aErrormessage; "ErrorMessage"
0x18018a3b5  mov     rcx, rax
0x18018a3b8  call    ?Add@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDPEB_WW4DataClassifications@Logging@3@@Z; Mso::Telemetry::IDataFieldCollection::Add(char const *,wchar_t const *,Mso::Logging::DataClassifications)
0x18018a3bd  nop
0x18018a3be  lea     rcx, [rbp+70h+Src]
0x18018a3c2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018a3c7  lea     rcx, [rsp+170h+var_110]
0x18018a3cc  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x18018a3d2  xor     eax, eax
0x18018a3d4  jmp     loc_18018A602
0x18018a3d9  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018a3de  mov     rbx, rax
0x18018a3e1  xor     edx, edx; Val
0x18018a3e3  lea     r8d, [rdx+5Ch]; Size
0x18018a3e7  lea     rcx, [rbp+70h+var_B0]; void *
0x18018a3eb  call    memset_0
0x18018a3f0  mov     r9d, esi
0x18018a3f3  or      r9d, 18h; unsigned int
0x18018a3f7  mov     [rsp+170h+var_128], r13b; bool
0x18018a3fc  mov     [rsp+170h+var_130], r13; unsigned __int16 *
0x18018a401  mov     [rsp+170h+var_138], r13; unsigned __int8 *
0x18018a406  mov     [rsp+170h+var_140], r13; unsigned __int8 *
0x18018a40b  mov     [rsp+170h+var_148], rbx; struct GEL::ITypefaceList *
0x18018a410  mov     [rsp+170h+var_150], r14; void *
0x18018a415  mov     r8d, 8; int
0x18018a41b  lea     rdx, [rbp+70h+var_B0]; struct tagLOGFONTW *
0x18018a41f  mov     rcx, rdi; this
0x18018a422  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x18018a427  mov     rax, [rdi]
0x18018a42a  mov     dword ptr [rsp+170h+var_148], esi
0x18018a42e  lea     rcx, [rbp+70h+var_B0]
0x18018a432  mov     [rsp+170h+var_150], rcx
0x18018a437  mov     r9, r14
0x18018a43a  mov     r8, rbx
0x18018a43d  lea     rdx, [rsp+170h+var_118]
0x18018a442  mov     rcx, rdi
0x18018a445  mov     rax, [rax+188h]
0x18018a44c  call    cs:__guard_dispatch_icall_fptr
0x18018a452  nop
0x18018a453  cmp     [rsp+170h+var_118], r13
0x18018a458  jnz     short loc_18018A45F
0x18018a45a  jmp     loc_18018A3BE
0x18018a45f  lea     rcx, [rsp+170h+var_118]
0x18018a464  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18018a469  mov     rdx, rax
0x18018a46c  mov     rcx, [rax]
0x18018a46f  mov     rax, [rcx+18h]
0x18018a473  mov     rcx, rdx
0x18018a476  call    cs:__guard_dispatch_icall_fptr
0x18018a47c  mov     r14, rax
0x18018a47f  mov     byte ptr [rsp+170h+var_120], 1
0x18018a484  mov     rcx, [rdi]
0x18018a487  mov     rax, [rcx+10h]
0x18018a48b  mov     rcx, rdi
0x18018a48e  call    cs:__guard_dispatch_icall_fptr
0x18018a494  lea     rdx, [rsp+170h+var_120]; wchar_t *
0x18018a499  mov     rcx, [rax]; this
0x18018a49c  call    ?IsEmbeddingEnabled@GEL@@YAHPEB_WPEA_N@Z; GEL::IsEmbeddingEnabled(wchar_t const *,bool *)
0x18018a4a1  mov     ebx, eax
0x18018a4a3  test    eax, eax
0x18018a4a5  jnz     loc_18018A5CC
0x18018a4ab  cmp     byte ptr [rsp+170h+var_120], r13b
0x18018a4b0  jz      loc_18018A5CC
0x18018a4b6  test    esi, esi
0x18018a4b8  jnz     loc_18018A54E
0x18018a4be  lea     rcx, [rsp+170h+var_118]
0x18018a4c3  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18018a4c8  mov     rdx, rax
0x18018a4cb  mov     rcx, [rax]
0x18018a4ce  mov     rax, [rcx+10h]
0x18018a4d2  mov     rcx, rdx
0x18018a4d5  call    cs:__guard_dispatch_icall_fptr
0x18018a4db  mov     rdx, rax
0x18018a4de  mov     rcx, [rax]
0x18018a4e1  mov     rax, [rcx+20h]
0x18018a4e5  mov     rcx, rdx
0x18018a4e8  call    cs:__guard_dispatch_icall_fptr
0x18018a4ee  cmp     eax, 2BCh
0x18018a4f3  jge     short loc_18018A529
0x18018a4f5  lea     rcx, [rsp+170h+var_118]
0x18018a4fa  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18018a4ff  mov     rdx, rax
0x18018a502  mov     rcx, [rax]
0x18018a505  mov     rax, [rcx+10h]
0x18018a509  mov     rcx, rdx
0x18018a50c  call    cs:__guard_dispatch_icall_fptr
0x18018a512  mov     rdx, rax
0x18018a515  mov     rcx, [rax]
0x18018a518  mov     rax, [rcx+30h]
0x18018a51c  mov     rcx, rdx
0x18018a51f  call    cs:__guard_dispatch_icall_fptr
0x18018a525  test    eax, eax
0x18018a527  jz      short loc_18018A54E
0x18018a529  mov     rcx, [rsp+170h+var_118]
0x18018a52e  test    rcx, rcx
0x18018a531  jz      loc_18018A3BE
0x18018a537  mov     [rsp+170h+var_118], r13
0x18018a53c  mov     rax, [rcx]
0x18018a53f  mov     rax, [rax+8]
0x18018a543  call    cs:__guard_dispatch_icall_fptr
0x18018a549  jmp     loc_18018A3BE
0x18018a54e  mov     rax, r15
0x18018a551  neg     rax
0x18018a554  sbb     ebx, ebx
0x18018a556  neg     ebx
0x18018a558  xorps   xmm0, xmm0
0x18018a55b  movups  [rbp+70h+var_C8], xmm0
0x18018a55f  mov     rax, [rdi]
0x18018a562  mov     rcx, rdi
0x18018a565  mov     rax, [rax+10h]
0x18018a569  call    cs:__guard_dispatch_icall_fptr
0x18018a56f  mov     rdx, [rax]
0x18018a572  mov     qword ptr [rsp+170h+var_128], r12
0x18018a577  lea     rax, ?WriteToStream@GEL@@YAKPEAXPEBXK@Z; GEL::WriteToStream(void *,void const *,ulong)
0x18018a57e  mov     [rsp+170h+var_130], rax
0x18018a583  lea     rax, [rbp+70h+var_C8]
0x18018a587  mov     [rsp+170h+var_138], rax
0x18018a58c  mov     byte ptr [rsp+170h+var_140], r13b
0x18018a591  mov     byte ptr [rsp+170h+var_148], 1
0x18018a596  movzx   eax, [rbp+70h+arg_28]
0x18018a59d  mov     word ptr [rsp+170h+var_150], ax
0x18018a5a2  mov     r9, r15
0x18018a5a5  lea     r8d, [rbx+4]
0x18018a5a9  mov     rcx, r14
0x18018a5ac  call    cs:__imp_?GetEmbeddedFontStream@DWriteAssistant@Mso@@YAHPEAUIDWriteFontFace@@PEB_WIPEBGG_N3AEBU_GUID@@P6AKPEAXPEBXK@Z5@Z; Mso::DWriteAssistant::GetEmbeddedFontStream(IDWriteFontFace *,wchar_t const *,uint,ushort const *,ushort,bool,bool,_GUID const &,ulong (*)(void *,void const *,ulong),void *)
0x18018a5b2  mov     ebx, eax
0x18018a5b4  mov     rcx, [rsp+170h+var_118]
0x18018a5b9  test    rcx, rcx
0x18018a5bc  jz      short loc_18018A5E9
0x18018a5be  mov     [rsp+170h+var_118], r13
0x18018a5c3  mov     rdx, [rcx]
0x18018a5c6  mov     rax, [rdx+8]
0x18018a5ca  jmp     short loc_18018A5E2
0x18018a5cc  mov     rcx, [rsp+170h+var_118]
0x18018a5d1  test    rcx, rcx
0x18018a5d4  jz      short loc_18018A5E9
0x18018a5d6  mov     [rsp+170h+var_118], r13
0x18018a5db  mov     rax, [rcx]
0x18018a5de  mov     rax, [rax+8]
0x18018a5e2  call    cs:__guard_dispatch_icall_fptr
0x18018a5e8  nop
0x18018a5e9  lea     rcx, [rbp+70h+Src]
0x18018a5ed  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018a5f2  lea     rcx, [rsp+170h+var_110]
0x18018a5f7  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x18018a5fd  nop     dword ptr [rax]
0x18018a600  mov     eax, ebx
0x18018a602  mov     rcx, [rbp+70h+var_50]
0x18018a606  xor     rcx, rsp; StackCookie
0x18018a609  call    __security_check_cookie
0x18018a60e  add     rsp, 138h
0x18018a615  pop     r15
0x18018a617  pop     r14
0x18018a619  pop     r13
0x18018a61b  pop     r12
0x18018a61d  pop     rdi
0x18018a61e  pop     rsi
0x18018a61f  pop     rbx
0x18018a620  pop     rbp
0x18018a621  retn
```
