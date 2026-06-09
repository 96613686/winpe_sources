# CRawImageReader::~CRawImageReader(void)

- ea: `0x1800a5344`
- end: `0x1800a54b0`
- name: `??1CRawImageReader@@UEAA@XZ`
- size: `364`
- prototype: `void __fastcall(CRawImageReader *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a5840`

## callees

- `0x180006bc0`
- `0x180007700`
- `0x1800967ac`
- `0x18009c44c`
- `0x1800a5240`
- `0x1800a5344`
- `0x1800ac600`
- `0x1800af2bc`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a548f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a548f`

## pseudocode

```c
void __fastcall CRawImageReader::~CRawImageReader(CRawImageReader *this)
{
  _QWORD *v2; // rcx
  LibRaw *v3; // rcx
  __int64 v4; // rcx
  struct libraw_processed_image_t *v5; // rcx

  *(_QWORD *)this = &CRawImageReader::`vftable';
  v2 = (_QWORD *)((char *)this + 8);
  *v2 = &CRawImageReader::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CRawImageReader::LogInstance(v2, 0);
  v3 = (LibRaw *)*((_QWORD *)this + 18);
  if ( v3 )
  {
    LibRaw::recycle(v3);
    v4 = *((_QWORD *)this + 18);
    if ( v4 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 1);
  }
  v5 = (struct libraw_processed_image_t *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    LibRaw::dcraw_clear_mem(v5);
    *((_QWORD *)this + 17) = 0;
  }
  *((_QWORD *)this + 120) = &CAggregationStats<unsigned __int64>::`vftable';
  *((_QWORD *)this + 111) = &CAggregationStats<unsigned __int64>::`vftable';
  *((_QWORD *)this + 102) = &CAggregationStats<unsigned __int64>::`vftable';
  *((_QWORD *)this + 93) = &CAggregationStats<unsigned __int64>::`vftable';
  *((_QWORD *)this + 84) = &CAggregationStats<unsigned __int64>::`vftable';
  *((_QWORD *)this + 75) = &CAggregationStats<unsigned __int64>::`vftable';
  CMFBaseStringT<char>::~CMFBaseStringT<char>((char *)this + 432);
  CMFBaseStringT<char>::~CMFBaseStringT<char>((char *)this + 280);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 272);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 264);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 256);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 248);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 232);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 224);
  std::vector<CRawImageReader::IFDDataEntry>::_Tidy((char *)this + 200);
  std::vector<CRawImageReader::IFDDataEntry>::_Tidy((char *)this + 176);
  std::vector<CRawImageReader::IFDDataEntry>::_Tidy((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_DWORD *)this + 13) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 40);
}

```

## disassembly

```asm
0x1800a5344  push    rbx
0x1800a5346  sub     rsp, 30h
0x1800a534a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a5353  mov     rbx, rcx
0x1800a5356  lea     rax, ??_7CRawImageReader@@6B@; const CRawImageReader::`vftable'
0x1800a535d  mov     [rcx], rax
0x1800a5360  add     rcx, 8
0x1800a5364  lea     rax, ??_7CRawImageReader@@6BIMFTelemetryComponent@@@; const CRawImageReader::`vftable'{for `IMFTelemetryComponent'}
0x1800a536b  mov     [rcx], rax
0x1800a536e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a5375  mov     [rbx+10h], rax
0x1800a5379  xor     edx, edx
0x1800a537b  call    ?LogInstance@CRawImageReader@@UEAAXW4_MF_TELEMETRY_SESSION_LOG_REASON@@@Z; CRawImageReader::LogInstance(_MF_TELEMETRY_SESSION_LOG_REASON)
0x1800a5380  mov     rcx, [rbx+90h]; this
0x1800a5387  test    rcx, rcx
0x1800a538a  jz      short loc_1800A53AE
0x1800a538c  call    ?recycle@LibRaw@@QEAAXXZ; LibRaw::recycle(void)
0x1800a5391  mov     rcx, [rbx+90h]
0x1800a5398  test    rcx, rcx
0x1800a539b  jz      short loc_1800A53AE
0x1800a539d  mov     rax, [rcx]
0x1800a53a0  mov     edx, 1
0x1800a53a5  mov     rax, [rax+20h]
0x1800a53a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a53ae  mov     rcx, [rbx+88h]; struct libraw_processed_image_t *
0x1800a53b5  test    rcx, rcx
0x1800a53b8  jz      short loc_1800A53CA
0x1800a53ba  call    ?dcraw_clear_mem@LibRaw@@SAXPEAUlibraw_processed_image_t@@@Z; LibRaw::dcraw_clear_mem(libraw_processed_image_t *)
0x1800a53bf  mov     qword ptr [rbx+88h], 0
0x1800a53ca  lea     rax, ??_7?$CAggregationStats@_K@@6B@; const CAggregationStats<unsigned __int64>::`vftable'
0x1800a53d1  mov     [rbx+3C0h], rax
0x1800a53d8  mov     [rbx+378h], rax
0x1800a53df  mov     [rbx+330h], rax
0x1800a53e6  mov     [rbx+2E8h], rax
0x1800a53ed  mov     [rbx+2A0h], rax
0x1800a53f4  mov     [rbx+258h], rax
0x1800a53fb  lea     rcx, [rbx+1B0h]
0x1800a5402  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x1800a5407  lea     rcx, [rbx+118h]
0x1800a540e  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x1800a5413  lea     rcx, [rbx+110h]
0x1800a541a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a541f  lea     rcx, [rbx+108h]
0x1800a5426  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a542b  lea     rcx, [rbx+100h]
0x1800a5432  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a5437  lea     rcx, [rbx+0F8h]
0x1800a543e  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a5443  lea     rcx, [rbx+0F0h]
0x1800a544a  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a544f  lea     rcx, [rbx+0E8h]
0x1800a5456  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a545b  lea     rcx, [rbx+0E0h]
0x1800a5462  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a5467  lea     rcx, [rbx+0C8h]
0x1800a546e  call    ?_Tidy@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@AEAAXXZ; std::vector<CRawImageReader::IFDDataEntry>::_Tidy(void)
0x1800a5473  lea     rcx, [rbx+0B0h]
0x1800a547a  call    ?_Tidy@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@AEAAXXZ; std::vector<CRawImageReader::IFDDataEntry>::_Tidy(void)
0x1800a547f  lea     rcx, [rbx+98h]
0x1800a5486  call    ?_Tidy@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@AEAAXXZ; std::vector<CRawImageReader::IFDDataEntry>::_Tidy(void)
0x1800a548b  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800a548f  call    cs:__imp_DeleteCriticalSection
0x1800a5496  nop     dword ptr [rax+rax+00h]
0x1800a549b  mov     dword ptr [rbx+34h], 0C0000001h
0x1800a54a2  lea     rcx, [rbx+28h]
0x1800a54a6  add     rsp, 30h
0x1800a54aa  pop     rbx
0x1800a54ab  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
