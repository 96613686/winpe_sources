# FontSetBuilder::AddFontFileInternal(FontFileReference const &,IBaseCacheContext *,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)

- ea: `0x180011474`
- end: `0x1800117bb`
- name: `?AddFontFileInternal@FontSetBuilder@@AEAAJAEBVFontFileReference@@PEAUIBaseCacheContext@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006c37c`

## callees

- `0x180004810`
- `0x180005610`
- `0x1800056d0`
- `0x180007668`
- `0x180011474`
- `0x1800117c4`
- `0x180011840`
- `0x180013968`
- `0x18001ae28`
- `0x18002bc8c`
- `0x18004fe48`
- `0x18004ff2c`
- `0x18004ff60`
- `0x18004ff84`
- `0x180052b20`
- `0x180053508`
- `0x180053734`
- `0x180063fac`
- `0x18006421c`
- `0x18009bbe4`
- `0x18009d96c`
- `0x1800aa650`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011736`
- `ntdll!NtSetInformationThread` at `0x18001171f`
- `ntdll!NtSetInformationThread` at `0x18001174e`
- `ntdll!NtSetInformationThread` at `0x18001171f`
- `ntdll!NtSetInformationThread` at `0x18001174e`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall FontSetBuilder::AddFontFileInternal(
        __int64 a1,
        __int64 a2,
        struct IBaseCacheContext *a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v6; // rsi
  unsigned __int16 v7; // r14
  unsigned int v8; // edi
  unsigned int v9; // ebx
  unsigned int v10; // r15d
  unsigned __int16 InstanceCount; // r12
  __int64 v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rax
  HANDLE v15; // rax
  HANDLE CurrentThread; // rax
  unsigned int i; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int ThreadInformation; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+4Ch] [rbp-B4h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  unsigned int v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+6Ch] [rbp-94h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int128 v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h]
  struct IBaseCacheContext *v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  _QWORD v33[3]; // [rsp+A8h] [rbp-58h] BYREF
  char v34[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v35[8]; // [rsp+C8h] [rbp-38h] BYREF
  char v36[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+F0h] [rbp-10h]
  char v40[56]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v41[56]; // [rsp+130h] [rbp+30h] BYREF
  char v42[112]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v43; // [rsp+1D8h] [rbp+D8h]
  _BYTE v44[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v45[8]; // [rsp+200h] [rbp+100h] BYREF
  char v46[120]; // [rsp+208h] [rbp+108h] BYREF
  char v47[16]; // [rsp+280h] [rbp+180h] BYREF

  v21 = a4;
  v31 = a3;
  v6 = a1;
  v22 = a1;
  v32 = a5;
  LowMemoryPriority::LowMemoryPriority((LowMemoryPriority *)&v20);
  v23 = a2;
  v24 = 6;
  v7 = 0;
  v25 = 0;
  v26 = -1;
  v27 = 0;
  v28 = 0;
  FontFileAnalyzer::Analyze((FontFileAnalyzer *)&v23);
  if ( (_DWORD)v24 && (unsigned int)(v24 - 1) > 1 )
  {
    if ( v20 )
    {
      i = v20;
      CurrentThread = GetCurrentThread();
      NtSetInformationThread(CurrentThread, ThreadPagePriority, &i, 4u);
    }
    return 2291683328LL;
  }
  else
  {
    FontFaceReference::FontFaceReference(v36, a2);
    v8 = v25;
    if ( v25 > 0xFFFF )
      v8 = 0xFFFF;
    ThreadInformation = v8;
    v9 = 0;
    for ( i = 0; (unsigned __int16)v9 < v8; i = v9 )
    {
      v10 = (unsigned __int16)v9;
      v37 = (unsigned __int16)v9;
      InstanceCount = FontFileAnalyzer::GetInstanceCount((FontFileAnalyzer *)&v23, (unsigned __int16)v9);
      std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v29);
      if ( InstanceCount )
      {
        v12 = v22;
        v13 = v21;
        do
        {
          if ( (unsigned __int8)FontFileAnalyzer::GetInstanceParameters(&v23, v10, v7, &v29) )
          {
            HIWORD(v38) = 1;
            v14 = v29;
            LOWORD(v38) = (__int64)(*((_QWORD *)&v29 + 1) - v29) >> 3;
          }
          else
          {
            v14 = 0;
            v38 = 0;
          }
          v39 = v14;
          FontFaceElementKeyBase::FontFaceElementKeyBase(v33, v36, a2, 2);
          v33[0] = &FontFaceElementKey::`vftable';
          FontFaceLight::FontFaceLight((FontFaceLight *)v45, v31, (const struct FontFaceElementKey *)v33);
          FontFaceKeyWithStorage::FontFaceKeyWithStorage((FontFaceKeyWithStorage *)v41, (const struct FontFaceKey *)v36);
          memset_0(v42, 0, sizeof(v42));
          v43 = 0;
          std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v44);
          FontSetBuilder::AddFontInformation(v12, v41, v45, v13, v32);
          if ( *(_QWORD *)(v6 + 32) == *(_QWORD *)(v6 + 40) )
          {
            std::vector<FontSetBuilder::FontEntryWithProperties>::_Emplace_reallocate<FontSetBuilder::FontEntryWithProperties const &>(
              v6 + 24,
              *(_QWORD *)(v6 + 32),
              v41);
          }
          else
          {
            FontSetBuilder::FontEntryWithProperties::FontEntryWithProperties(
              *(FontSetBuilder::FontEntryWithProperties **)(v6 + 32),
              (const struct FontSetBuilder::FontEntryWithProperties *)v41);
            *(_QWORD *)(v6 + 32) += 200LL;
          }
          std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(v44);
          FontFaceKeyWithStorage::~FontFaceKeyWithStorage((FontFaceKeyWithStorage *)v41);
          IntrusivePtr<FontFaceLight::FaceNameData>::~IntrusivePtr<FontFaceLight::FaceNameData>(v47);
          IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(v46);
          ComPtr<IDWriteFontCollectionLoader>::~ComPtr<IDWriteFontCollectionLoader>(v35);
          ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(v34);
          ++v7;
        }
        while ( v7 < InstanceCount );
        v9 = i;
        v8 = ThreadInformation;
        v6 = v22;
      }
      v7 = 0;
      if ( (_QWORD)v29 )
      {
        std::_Deallocate<16>((void *)v29, (v30 - v29) & 0xFFFFFFFFFFFFFFF8uLL);
        v29 = 0;
        v30 = 0;
      }
      LOWORD(v9) = v9 + 1;
    }
    FontFileReference::~FontFileReference((FontFileReference *)v40);
    if ( v20 )
    {
      ThreadInformation = v20;
      v15 = GetCurrentThread();
      NtSetInformationThread(v15, ThreadPagePriority, &ThreadInformation, 4u);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180011474  mov     [rsp-8+arg_18], rbx
0x180011479  push    rbp
0x18001147a  push    rsi
0x18001147b  push    rdi
0x18001147c  push    r12
0x18001147e  push    r13
0x180011480  push    r14
0x180011482  push    r15
0x180011484  lea     rbp, [rsp-1A0h]
0x18001148c  sub     rsp, 2A0h
0x180011493  mov     rax, cs:__security_cookie
0x18001149a  xor     rax, rsp
0x18001149d  mov     [rbp+1D0h+var_40], rax
0x1800114a4  mov     [rsp+2D0h+var_284], r9d
0x1800114a9  mov     [rbp+1D0h+var_238], r8
0x1800114ad  mov     r13, rdx
0x1800114b0  mov     rsi, rcx
0x1800114b3  mov     [rsp+2D0h+var_280], rcx
0x1800114b8  mov     rax, [rbp+1D0h+arg_20]
0x1800114bf  mov     [rbp+1D0h+var_230], rax
0x1800114c3  lea     rcx, [rsp+2D0h+var_288]; this
0x1800114c8  call    ??0LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::LowMemoryPriority(void)
0x1800114cd  nop
0x1800114ce  mov     [rsp+2D0h+var_278], r13
0x1800114d3  mov     [rsp+2D0h+var_270], 6
0x1800114dc  xor     r14d, r14d
0x1800114df  mov     [rsp+2D0h+var_268], r14d
0x1800114e4  mov     [rsp+2D0h+var_264], 0FFFFFFFFh
0x1800114ec  mov     [rsp+2D0h+var_260], r14
0x1800114f1  mov     [rsp+2D0h+var_258], r14
0x1800114f6  lea     rcx, [rsp+2D0h+var_278]; this
0x1800114fb  call    ?Analyze@FontFileAnalyzer@@AEAAXXZ; FontFileAnalyzer::Analyze(void)
0x180011500  mov     r8d, dword ptr [rsp+2D0h+var_270]
0x180011505  mov     ecx, r8d
0x180011508  test    r8d, r8d
0x18001150b  jz      short loc_18001151B
0x18001150d  sub     ecx, 1
0x180011510  jz      short loc_18001151B
0x180011512  cmp     ecx, 1
0x180011515  jnz     loc_18001172A
0x18001151b  mov     word ptr [rsp+2D0h+var_2B0], r14w
0x180011521  mov     rdx, r13
0x180011524  lea     rcx, [rbp+1D0h+var_200]
0x180011528  call    ??0FontFaceReference@@QEAA@AEBVFontFileReference@@W4DWRITE_FONT_FACE_TYPE@@ITVariationFlags@FontFaceKey@@GPEBUDWRITE_FONT_AXIS_VALUE_FIXED@@@Z; FontFaceReference::FontFaceReference(FontFileReference const &,DWRITE_FONT_FACE_TYPE,uint,FontFaceKey::VariationFlags,ushort,DWRITE_FONT_AXIS_VALUE_FIXED const *)
0x18001152d  nop
0x18001152e  mov     edi, [rsp+2D0h+var_268]
0x180011532  mov     eax, 0FFFFh
0x180011537  cmp     edi, eax
0x180011539  cmova   edi, eax
0x18001153c  mov     [rsp+2D0h+ThreadInformation], edi
0x180011540  mov     ebx, r14d
0x180011543  mov     [rsp+2D0h+var_290], ebx
0x180011547  test    edi, edi
0x180011549  jz      loc_1800116F1
0x18001154f  movzx   r15d, bx
0x180011553  mov     [rbp+1D0h+var_1F8], r15d
0x180011557  mov     edx, r15d; unsigned int
0x18001155a  lea     rcx, [rsp+2D0h+var_278]; this
0x18001155f  call    ?GetInstanceCount@FontFileAnalyzer@@QEAAGI@Z; FontFileAnalyzer::GetInstanceCount(uint)
0x180011564  movzx   r12d, ax
0x180011568  lea     rcx, [rbp+1D0h+var_250]; void *
0x18001156c  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180011571  nop
0x180011572  xor     ecx, ecx
0x180011574  cmp     cx, r12w
0x180011578  jnb     loc_1800116B7
0x18001157e  mov     rdi, [rsp+2D0h+var_280]
0x180011583  mov     ebx, [rsp+2D0h+var_284]
0x180011587  lea     r9, [rbp+1D0h+var_250]
0x18001158b  movzx   r8d, r14w
0x18001158f  mov     edx, r15d
0x180011592  lea     rcx, [rsp+2D0h+var_278]
0x180011597  call    ?GetInstanceParameters@FontFileAnalyzer@@QEAA_NIGAEAV?$vector@UDWRITE_FONT_AXIS_VALUE_FIXED@@V?$allocator@UDWRITE_FONT_AXIS_VALUE_FIXED@@@std@@@std@@@Z; FontFileAnalyzer::GetInstanceParameters(uint,ushort,std::vector<DWRITE_FONT_AXIS_VALUE_FIXED> &)
0x18001159c  test    al, al
0x18001159e  jnz     loc_180011784
0x1800115a4  xor     eax, eax
0x1800115a6  mov     [rbp+1D0h+var_1F0], eax
0x1800115a9  mov     [rbp+1D0h+var_1E0], rax
0x1800115ad  mov     r9d, 2
0x1800115b3  mov     r8, r13
0x1800115b6  lea     rdx, [rbp+1D0h+var_200]
0x1800115ba  lea     rcx, [rbp+1D0h+var_228]
0x1800115be  call    ??0FontFaceElementKeyBase@@QEAA@AEBVFontFaceKey@@AEBVFontFileReference@@W4CacheElementType@@@Z; FontFaceElementKeyBase::FontFaceElementKeyBase(FontFaceKey const &,FontFileReference const &,CacheElementType)
0x1800115c3  lea     rax, ??_7FontFaceElementKey@@6B@; const FontFaceElementKey::`vftable'
0x1800115ca  mov     [rbp+1D0h+var_228], rax
0x1800115ce  lea     r8, [rbp+1D0h+var_228]; struct FontFaceElementKey *
0x1800115d2  mov     rdx, [rbp+1D0h+var_238]; struct IBaseCacheContext *
0x1800115d6  lea     rcx, [rbp+1D0h+var_D0]; this
0x1800115dd  call    ??0FontFaceLight@@QEAA@PEAUIBaseCacheContext@@AEBVFontFaceElementKey@@@Z; FontFaceLight::FontFaceLight(IBaseCacheContext *,FontFaceElementKey const &)
0x1800115e2  nop
0x1800115e3  lea     rdx, [rbp+1D0h+var_200]; struct FontFaceKey *
0x1800115e7  lea     rcx, [rbp+1D0h+var_1A0]; this
0x1800115eb  call    ??0FontFaceKeyWithStorage@@QEAA@AEBVFontFaceKey@@@Z; FontFaceKeyWithStorage::FontFaceKeyWithStorage(FontFaceKey const &)
0x1800115f0  nop
0x1800115f1  xor     edx, edx; Val
0x1800115f3  lea     r8d, [rdx+70h]; Size
0x1800115f7  lea     rcx, [rbp+1D0h+var_168]; void *
0x1800115fb  call    memset_0
0x180011600  mov     [rbp+1D0h+var_F8], 0
0x18001160b  lea     rcx, [rbp+1D0h+var_F0]; void *
0x180011612  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180011617  nop
0x180011618  mov     rax, [rbp+1D0h+var_230]
0x18001161c  mov     [rsp+2D0h+var_2B0], rax
0x180011621  mov     r9d, ebx
0x180011624  lea     r8, [rbp+1D0h+var_D0]
0x18001162b  lea     rdx, [rbp+1D0h+var_1A0]
0x18001162f  mov     rcx, rdi
0x180011632  call    ?AddFontInformation@FontSetBuilder@@IEAAXAEAUFontEntryWithProperties@1@AEBVFontFaceLight@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z; FontSetBuilder::AddFontInformation(FontSetBuilder::FontEntryWithProperties &,FontFaceLight const &,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)
0x180011637  mov     rax, [rsi+20h]
0x18001163b  cmp     rax, [rsi+28h]
0x18001163f  jz      loc_1800117A5
0x180011645  lea     rdx, [rbp+1D0h+var_1A0]; struct FontSetBuilder::FontEntryWithProperties *
0x180011649  mov     rcx, rax; this
0x18001164c  call    ??0FontEntryWithProperties@FontSetBuilder@@QEAA@AEBU01@@Z; FontSetBuilder::FontEntryWithProperties::FontEntryWithProperties(FontSetBuilder::FontEntryWithProperties const &)
0x180011651  add     qword ptr [rsi+20h], 0C8h
0x180011659  lea     rcx, [rbp+1D0h+var_F0]
0x180011660  call    ?_Tidy@?$vector@UFeature@FontFeatureCoverageRegionBuilder@@V?$allocator@UFeature@FontFeatureCoverageRegionBuilder@@@std@@@std@@AEAAXXZ; std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(void)
0x180011665  lea     rcx, [rbp+1D0h+var_1A0]; this
0x180011669  call    ??1FontFaceKeyWithStorage@@QEAA@XZ; FontFaceKeyWithStorage::~FontFaceKeyWithStorage(void)
0x18001166e  nop
0x18001166f  lea     rcx, [rbp+1D0h+var_50]
0x180011676  call    ??1?$IntrusivePtr@UFaceNameData@FontFaceLight@@@@QEAA@XZ; IntrusivePtr<FontFaceLight::FaceNameData>::~IntrusivePtr<FontFaceLight::FaceNameData>(void)
0x18001167b  nop
0x18001167c  lea     rcx, [rbp+1D0h+var_C8]
0x180011683  call    ??1?$IntrusivePtr@VICacheReference@@@@QEAA@XZ; IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(void)
0x180011688  nop
0x180011689  lea     rcx, [rbp+1D0h+var_208]
0x18001168d  call    ??1?$ComPtr@UIDWriteFontCollectionLoader@@@@QEAA@XZ; ComPtr<IDWriteFontCollectionLoader>::~ComPtr<IDWriteFontCollectionLoader>(void)
0x180011692  nop
0x180011693  lea     rcx, [rbp+1D0h+var_210]
0x180011697  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18001169c  inc     r14w
0x1800116a0  cmp     r14w, r12w
0x1800116a4  jb      loc_180011587
0x1800116aa  mov     ebx, [rsp+2D0h+var_290]
0x1800116ae  mov     edi, [rsp+2D0h+ThreadInformation]
0x1800116b2  mov     rsi, [rsp+2D0h+var_280]
0x1800116b7  mov     rcx, qword ptr [rbp+1D0h+var_250]
0x1800116bb  xor     r14d, r14d
0x1800116be  test    rcx, rcx
0x1800116c1  jz      short loc_1800116DF
0x1800116c3  mov     rdx, [rbp+1D0h+var_240]
0x1800116c7  sub     rdx, rcx
0x1800116ca  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800116ce  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800116d3  xorps   xmm0, xmm0
0x1800116d6  movdqu  [rbp+1D0h+var_250], xmm0
0x1800116db  mov     [rbp+1D0h+var_240], r14
0x1800116df  inc     bx
0x1800116e2  mov     [rsp+2D0h+var_290], ebx
0x1800116e6  movzx   eax, bx
0x1800116e9  cmp     eax, edi
0x1800116eb  jb      loc_18001154F
0x1800116f1  lea     rcx, [rbp+1D0h+var_1D8]; this
0x1800116f5  call    ??1FontFileReference@@QEAA@XZ; FontFileReference::~FontFileReference(void)
0x1800116fa  nop
0x1800116fb  mov     eax, [rsp+2D0h+var_288]
0x1800116ff  test    eax, eax
0x180011701  jz      short loc_180011726
0x180011703  mov     [rsp+2D0h+ThreadInformation], eax
0x180011707  call    cs:__imp_GetCurrentThread
0x18001170d  mov     rcx, rax; ThreadHandle
0x180011710  mov     r9d, 4; ThreadInformationLength
0x180011716  lea     r8, [rsp+2D0h+ThreadInformation]; ThreadInformation
0x18001171b  lea     edx, [r9+14h]; ThreadInformationClass
0x18001171f  call    cs:__imp_NtSetInformationThread
0x180011725  nop
0x180011726  xor     eax, eax
0x180011728  jmp     short loc_18001175A
0x18001172a  mov     eax, [rsp+2D0h+var_288]
0x18001172e  test    eax, eax
0x180011730  jz      short loc_180011755
0x180011732  mov     [rsp+2D0h+var_290], eax
0x180011736  call    cs:__imp_GetCurrentThread
0x18001173c  mov     rcx, rax; ThreadHandle
0x18001173f  mov     r9d, 4; ThreadInformationLength
0x180011745  lea     r8, [rsp+2D0h+var_290]; ThreadInformation
0x18001174a  lea     edx, [r9+14h]; ThreadInformationClass
0x18001174e  call    cs:__imp_NtSetInformationThread
0x180011754  nop
0x180011755  mov     eax, 88985000h
0x18001175a  mov     rcx, [rbp+1D0h+var_40]
0x180011761  xor     rcx, rsp; StackCookie
0x180011764  call    __security_check_cookie
0x180011769  mov     rbx, [rsp+2D0h+arg_18]
0x180011771  add     rsp, 2A0h
0x180011778  pop     r15
0x18001177a  pop     r14
0x18001177c  pop     r13
0x18001177e  pop     r12
0x180011780  pop     rdi
0x180011781  pop     rsi
0x180011782  pop     rbp
0x180011783  retn
0x180011784  mov     eax, 1
0x180011789  mov     word ptr [rbp+1D0h+var_1F0+2], ax
0x18001178d  mov     rcx, qword ptr [rbp+1D0h+var_250+8]
0x180011791  mov     rax, qword ptr [rbp+1D0h+var_250]
0x180011795  sub     rcx, rax
0x180011798  sar     rcx, 3
0x18001179c  mov     word ptr [rbp+1D0h+var_1F0], cx
0x1800117a0  jmp     loc_1800115A9
0x1800117a5  lea     r8, [rbp+1D0h+var_1A0]
0x1800117a9  mov     rdx, rax
0x1800117ac  lea     rcx, [rsi+18h]
0x1800117b0  call    ??$_Emplace_reallocate@AEBUFontEntryWithProperties@FontSetBuilder@@@?$vector@UFontEntryWithProperties@FontSetBuilder@@V?$allocator@UFontEntryWithProperties@FontSetBuilder@@@std@@@std@@AEAAPEAUFontEntryWithProperties@FontSetBuilder@@QEAU23@AEBU23@@Z; std::vector<FontSetBuilder::FontEntryWithProperties>::_Emplace_reallocate<FontSetBuilder::FontEntryWithProperties const &>(FontSetBuilder::FontEntryWithProperties * const,FontSetBuilder::FontEntryWithProperties const &)
0x1800117b5  jmp     loc_180011659
```
