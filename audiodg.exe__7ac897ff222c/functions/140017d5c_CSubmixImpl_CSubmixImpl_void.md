# CSubmixImpl::~CSubmixImpl(void)

- ea: `0x140017d5c`
- end: `0x140017ef1`
- name: `??1CSubmixImpl@@QEAA@XZ`
- size: `405`
- prototype: `void __fastcall(CSubmixImpl *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140017d30`
- `0x140034ea8`

## callees

- `0x140008124`
- `0x14000a378`
- `0x14000a3d0`
- `0x14000ad48`
- `0x140016f68`
- `0x140017d5c`
- `0x14001c0dc`
- `0x14001c8f0`
- `0x14001c9ac`
- `0x14001d42c`
- `0x14001d500`
- `0x1400349d4`
- `0x140044ce4`
- `0x14005d4ac`
- `0x14006a1d0`
- `0x14007e378`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017e0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017e66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017e0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017e66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140017eb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140017ecc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140017eb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140017ecc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017e3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017e3d`

## pseudocode

```c
void __fastcall CSubmixImpl::~CSubmixImpl(CSubmixImpl *this)
{
  char *v2; // r14
  struct ISubmix *v3; // rdx
  unsigned __int64 v4; // rax
  void *v5; // rax
  __int64 i; // rdx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CSubmixImpl::`vftable';
  v2 = (char *)this + 304;
  v3 = (struct ISubmix *)*((_QWORD *)this + 38);
  if ( v3 )
    CSubmixImpl::DisconnectFromRightSubmix(this, v3);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  while ( *((_QWORD *)this + 11) )
  {
    ATL::CAtlList<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>>>::RemoveHead(
      (char *)this + 72,
      &v7);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7) )
    {
      lpCriticalSection = 0;
      if ( GetHistoryBufferManager((struct CAudioHistoryBufferManager **)&lpCriticalSection) >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7);
        CAudioHistoryBufferManager::Remove(lpCriticalSection, v4);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  if ( this != (CSubmixImpl *)-176LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  while ( *((_QWORD *)this + 17) )
  {
    v5 = (void *)ATL::CAtlList<CChildSubmixInstance *,ATL::CElementTraits<CChildSubmixInstance *>>::RemoveHead((char *)this + 120);
    operator delete(v5);
  }
  EnterCriticalSection(&g_CritSecSubmixList);
  for ( i = SubmixList; i; i = *(_QWORD *)i )
  {
    if ( *(CSubmixImpl **)(i + 16) == this )
    {
      ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::RemoveAt();
      break;
    }
  }
  LeaveCriticalSection(&g_CritSecSubmixList);
  PublishDeviceGraphWnfState();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v2);
  CFormatConverterPipe::~CFormatConverterPipe((CSubmixImpl *)((char *)this + 272));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 264);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    (char *)this + 224,
    0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    (char *)this + 216,
    0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  ATL::CAtlList<CChildSubmixInstance *,ATL::CElementTraits<CChildSubmixInstance *>>::RemoveAll((char *)this + 120);
  ATL::CAtlList<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>>>::RemoveAll((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::CAutoPtr<CPipeInstance>::Free((char *)this + 24);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 8);
}

```

## disassembly

```asm
0x140017d5c  mov     [rsp+arg_10], rbx
0x140017d61  push    rsi
0x140017d62  push    rdi
0x140017d63  push    r14
0x140017d65  sub     rsp, 20h
0x140017d69  mov     rdi, rcx
0x140017d6c  lea     rax, ??_7CSubmixImpl@@6B@; const CSubmixImpl::`vftable'
0x140017d73  mov     [rcx], rax
0x140017d76  lea     r14, [rcx+130h]
0x140017d7d  mov     rdx, [r14]; struct ISubmix *
0x140017d80  test    rdx, rdx
0x140017d83  jz      short loc_140017D8A
0x140017d85  call    ?DisconnectFromRightSubmix@CSubmixImpl@@UEAAXPEAUISubmix@@@Z; CSubmixImpl::DisconnectFromRightSubmix(ISubmix *)
0x140017d8a  lea     rbx, [rdi+0B0h]
0x140017d91  mov     rcx, rbx; lpCriticalSection
0x140017d94  call    cs:__imp_EnterCriticalSection
0x140017d9a  jmp     short loc_140017DFF
0x140017d9c  lea     rdx, [rsp+38h+arg_0]
0x140017da1  lea     rcx, [rdi+48h]
0x140017da5  call    ?RemoveHead@?$CAtlList@V?$com_ptr_t@UIStreamInstanceInternal@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@V?$com_ptr_t@UIStreamInstanceInternal@@Uerr_returncode_policy@wil@@@wil@@@ATL@@@ATL@@QEAA?AV?$com_ptr_t@UIStreamInstanceInternal@@Uerr_returncode_policy@wil@@@wil@@XZ; ATL::CAtlList<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>>>::RemoveHead(void)
0x140017daa  mov     rcx, [rsp+38h+arg_0]
0x140017daf  mov     rax, [rcx]
0x140017db2  mov     rax, [rax+78h]
0x140017db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017dbb  test    rax, rax
0x140017dbe  jz      short loc_140017DF5
0x140017dc0  mov     [rsp+38h+lpCriticalSection], 0
0x140017dc9  lea     rcx, [rsp+38h+lpCriticalSection]; struct CAudioHistoryBufferManager **
0x140017dce  call    ?GetHistoryBufferManager@@YAJPEAPEAVCAudioHistoryBufferManager@@@Z; GetHistoryBufferManager(CAudioHistoryBufferManager * *)
0x140017dd3  test    eax, eax
0x140017dd5  js      short loc_140017DF5
0x140017dd7  mov     rcx, [rsp+38h+arg_0]
0x140017ddc  mov     rax, [rcx]
0x140017ddf  mov     rax, [rax+78h]
0x140017de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017de8  mov     rdx, rax; unsigned __int64
0x140017deb  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x140017df0  call    ?Remove@CAudioHistoryBufferManager@@QEAAJ_K@Z; CAudioHistoryBufferManager::Remove(unsigned __int64)
0x140017df5  lea     rcx, [rsp+38h+arg_0]
0x140017dfa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140017dff  cmp     qword ptr [rdi+58h], 0
0x140017e04  ja      short loc_140017D9C
0x140017e06  test    rbx, rbx
0x140017e09  jz      short loc_140017E2C
0x140017e0b  mov     rcx, rbx; lpCriticalSection
0x140017e0e  call    cs:__imp_LeaveCriticalSection
0x140017e14  jmp     short loc_140017E2C
0x140017e16  lea     rcx, [rdi+78h]
0x140017e1a  call    ?RemoveHead@?$CAtlList@PEAVCChildSubmixInstance@@V?$CElementTraits@PEAVCChildSubmixInstance@@@ATL@@@ATL@@QEAAPEAVCChildSubmixInstance@@XZ; ATL::CAtlList<CChildSubmixInstance *,ATL::CElementTraits<CChildSubmixInstance *>>::RemoveHead(void)
0x140017e1f  mov     edx, 10h
0x140017e24  mov     rcx, rax; Block
0x140017e27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140017e2c  cmp     qword ptr [rdi+88h], 0
0x140017e34  ja      short loc_140017E16
0x140017e36  lea     rcx, ?g_CritSecSubmixList@@3Vcritical_section@wil@@A; lpCriticalSection
0x140017e3d  call    cs:__imp_EnterCriticalSection
0x140017e43  mov     rdx, cs:?SubmixList@@3V?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@A; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>> SubmixList
0x140017e4a  test    rdx, rdx
0x140017e4d  jz      short loc_140017E5F
0x140017e4f  cmp     [rdx+10h], rdi
0x140017e53  jz      short loc_140017E5A
0x140017e55  mov     rdx, [rdx]
0x140017e58  jmp     short loc_140017E4A
0x140017e5a  call    ?RemoveAt@?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::RemoveAt(__POSITION *)
0x140017e5f  lea     rcx, ?g_CritSecSubmixList@@3Vcritical_section@wil@@A; lpCriticalSection
0x140017e66  call    cs:__imp_LeaveCriticalSection
0x140017e6c  call    ?PublishDeviceGraphWnfState@@YAXXZ; PublishDeviceGraphWnfState(void)
0x140017e71  mov     rcx, r14
0x140017e74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140017e79  lea     rcx, [rdi+110h]; this
0x140017e80  call    ??1CFormatConverterPipe@@QEAA@XZ; CFormatConverterPipe::~CFormatConverterPipe(void)
0x140017e85  lea     rcx, [rdi+108h]
0x140017e8c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140017e91  lea     rcx, [rdi+0E0h]
0x140017e98  xor     edx, edx
0x140017e9a  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x140017e9f  lea     rcx, [rdi+0D8h]
0x140017ea6  xor     edx, edx
0x140017ea8  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x140017ead  mov     rcx, rbx; lpCriticalSection
0x140017eb0  call    cs:__imp_DeleteCriticalSection
0x140017eb6  lea     rcx, [rdi+78h]
0x140017eba  call    ?RemoveAll@?$CAtlList@PEAVCChildSubmixInstance@@V?$CElementTraits@PEAVCChildSubmixInstance@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CChildSubmixInstance *,ATL::CElementTraits<CChildSubmixInstance *>>::RemoveAll(void)
0x140017ebf  lea     rcx, [rdi+48h]
0x140017ec3  call    ?RemoveAll@?$CAtlList@V?$com_ptr_t@UIStreamInstanceInternal@@Uerr_returncode_policy@wil@@@wil@@V?$CElementTraits@V?$com_ptr_t@UIStreamInstanceInternal@@Uerr_returncode_policy@wil@@@wil@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>,ATL::CElementTraits<wil::com_ptr_t<IStreamInstanceInternal,wil::err_returncode_policy>>>::RemoveAll(void)
0x140017ec8  lea     rcx, [rdi+20h]; lpCriticalSection
0x140017ecc  call    cs:__imp_DeleteCriticalSection
0x140017ed2  lea     rcx, [rdi+18h]
0x140017ed6  call    ?Free@?$CAutoPtr@VCPipeInstance@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CPipeInstance>::Free(void)
0x140017edb  lea     rcx, [rdi+8]
0x140017edf  mov     rbx, [rsp+38h+arg_10]
0x140017ee4  add     rsp, 20h
0x140017ee8  pop     r14
0x140017eea  pop     rdi
0x140017eeb  pop     rsi
0x140017eec  jmp     ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
```
