# CAudioDeviceGraph::~CAudioDeviceGraph(void)

- ea: `0x1400365c4`
- end: `0x1400366d4`
- name: `??1CAudioDeviceGraph@@QEAA@XZ`
- size: `272`
- prototype: `void __fastcall(CAudioDeviceGraph *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003656c`
- `0x14005ff38`

## callees

- `0x140008124`
- `0x14000e11c`
- `0x14000e590`
- `0x140016f68`
- `0x14001c5d0`
- `0x140025b50`
- `0x140034540`
- `0x1400365c4`
- `0x14003de5c`
- `0x1400516e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140036650`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003666d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140036650`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003666d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003668f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003669c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003668f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003669c`

## pseudocode

```c
void __fastcall CAudioDeviceGraph::~CAudioDeviceGraph(CAudioDeviceGraph *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  void *v5; // rcx
  void *v6; // rcx

  CAudioDeviceGraph::Cleanup(this);
  v2 = AudioDgTelemetryProvider::Provider();
  if ( *(_DWORD *)v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 1, v3) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      word_1400D14F2,
      (char *)this + 344);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 392);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 384);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 376);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 360);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 336);
  v5 = (void *)*((_QWORD *)this + 39);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 39) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 40);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 40) = 0;
  }
  *((_DWORD *)this + 82) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  ATL::CAtlList<CPipeInstance *,ATL::CElementTraits<CPipeInstance *>>::RemoveAll((char *)this + 168);
  wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>((char *)this + 152);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 144);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CAudioDeviceGraph *)((char *)this + 32));
}

```

## disassembly

```asm
0x1400365c4  push    rbx
0x1400365c6  sub     rsp, 20h
0x1400365ca  mov     rbx, rcx
0x1400365cd  call    ?Cleanup@CAudioDeviceGraph@@AEAAXXZ; CAudioDeviceGraph::Cleanup(void)
0x1400365d2  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x1400365d7  mov     r9, rax
0x1400365da  mov     edx, [rax]
0x1400365dc  cmp     edx, 4
0x1400365df  jbe     short loc_140036608
0x1400365e1  mov     edx, 1
0x1400365e6  mov     rcx, rax
0x1400365e9  call    _tlgKeywordOn
0x1400365ee  test    al, al
0x1400365f0  jz      short loc_140036608
0x1400365f2  lea     r8, [rbx+158h]
0x1400365f9  lea     rdx, word_1400D14F2
0x140036600  mov     rcx, r9
0x140036603  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140036608  lea     rcx, [rbx+188h]
0x14003660f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140036614  lea     rcx, [rbx+180h]
0x14003661b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140036620  lea     rcx, [rbx+178h]
0x140036627  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003662c  lea     rcx, [rbx+168h]
0x140036633  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140036638  lea     rcx, [rbx+150h]
0x14003663f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140036644  mov     rcx, [rbx+138h]; Block
0x14003664b  test    rcx, rcx
0x14003664e  jz      short loc_140036661
0x140036650  call    cs:__imp_free
0x140036656  mov     qword ptr [rbx+138h], 0
0x140036661  mov     rcx, [rbx+140h]; Block
0x140036668  test    rcx, rcx
0x14003666b  jz      short loc_14003667E
0x14003666d  call    cs:__imp_free
0x140036673  mov     qword ptr [rbx+140h], 0
0x14003667e  mov     dword ptr [rbx+148h], 0
0x140036688  lea     rcx, [rbx+108h]; lpCriticalSection
0x14003668f  call    cs:__imp_DeleteCriticalSection
0x140036695  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x14003669c  call    cs:__imp_DeleteCriticalSection
0x1400366a2  lea     rcx, [rbx+0A8h]
0x1400366a9  call    ?RemoveAll@?$CAtlList@PEAVCPipeInstance@@V?$CElementTraits@PEAVCPipeInstance@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CPipeInstance *,ATL::CElementTraits<CPipeInstance *>>::RemoveAll(void)
0x1400366ae  lea     rcx, [rbx+98h]
0x1400366b5  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x1400366ba  lea     rcx, [rbx+90h]
0x1400366c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400366c6  lea     rcx, [rbx+20h]; this
0x1400366ca  add     rsp, 20h
0x1400366ce  pop     rbx
0x1400366cf  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
