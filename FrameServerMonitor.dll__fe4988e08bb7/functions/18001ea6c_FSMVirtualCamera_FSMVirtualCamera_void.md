# FSMVirtualCamera::~FSMVirtualCamera(void)

- ea: `0x18001ea6c`
- end: `0x18001ebb0`
- name: `??1FSMVirtualCamera@@MEAA@XZ`
- size: `324`
- prototype: `void __fastcall(FSMVirtualCamera *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ebf0`

## callees

- `0x180001dc0`
- `0x180005f98`
- `0x1800060e8`
- `0x180006f3c`
- `0x180007020`
- `0x18000b388`
- `0x18000cffc`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18001ea4c`
- `0x18001ea6c`
- `0x18002a3d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eb93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eb9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eb93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eb9d`

## pseudocode

```c
void __fastcall FSMVirtualCamera::~FSMVirtualCamera(FSMVirtualCamera *this)
{
  __int64 v2; // rcx
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rcx

  *(_QWORD *)this = &FSMVirtualCamera::`vftable'{for `FSMObject'};
  *((_QWORD *)this + 5) = &FSMVirtualCamera::`vftable'{for `IFSMVirtualCamera'};
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 21, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, v2);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((char *)this + 680);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((char *)this + 648);
  *((_QWORD *)this + 74) = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((FSMVirtualCamera *)((char *)this + 592));
  wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>((char *)this + 584);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 72);
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>((char *)this + 552);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 68);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 67);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 66);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 496);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 464);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 448);
  v4 = (void *)*((_QWORD *)this + 54);
  *((_QWORD *)this + 54) = 0;
  if ( v4 )
    operator delete(v4, v3);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 400);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 368);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 336);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  FSMObject::~FSMObject(this);
}

```

## disassembly

```asm
0x18001ea6c  push    rbx
0x18001ea6e  sub     rsp, 20h
0x18001ea72  lea     rax, ??_7FSMVirtualCamera@@6BFSMObject@@@; const FSMVirtualCamera::`vftable'{for `FSMObject'}
0x18001ea79  mov     rbx, rcx
0x18001ea7c  mov     [rcx], rax
0x18001ea7f  lea     rax, ??_7FSMVirtualCamera@@6BIFSMVirtualCamera@@@; const FSMVirtualCamera::`vftable'{for `IFSMVirtualCamera'}
0x18001ea86  mov     [rcx+28h], rax
0x18001ea8a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001ea8f  cmp     al, 10h
0x18001ea91  jb      short loc_18001EAB5
0x18001ea93  mov     r9, rcx
0x18001ea96  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001ea9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaa4  mov     edx, 15h
0x18001eaa9  mov     rcx, [rcx+0D8h]
0x18001eab0  call    WPP_SF_q
0x18001eab5  lea     rcx, [rbx+2A8h]
0x18001eabc  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001eac1  lea     rcx, [rbx+288h]
0x18001eac8  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001eacd  lea     rcx, [rbx+250h]; this
0x18001ead4  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x18001eadb  mov     [rcx], rax
0x18001eade  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18001eae3  lea     rcx, [rbx+248h]
0x18001eaea  call    ??1?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>(void)
0x18001eaef  lea     rcx, [rbx+240h]
0x18001eaf6  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001eafb  lea     rcx, [rbx+228h]
0x18001eb02  call    ??1?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(void)
0x18001eb07  lea     rcx, [rbx+220h]
0x18001eb0e  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001eb13  lea     rcx, [rbx+218h]
0x18001eb1a  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001eb1f  lea     rcx, [rbx+210h]
0x18001eb26  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001eb2b  lea     rcx, [rbx+1F0h]
0x18001eb32  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001eb37  lea     rcx, [rbx+1D0h]
0x18001eb3e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001eb43  lea     rcx, [rbx+1C0h]
0x18001eb4a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001eb4f  mov     rcx, [rbx+1B0h]; void *
0x18001eb56  mov     qword ptr [rbx+1B0h], 0
0x18001eb61  test    rcx, rcx
0x18001eb64  jz      short loc_18001EB6B
0x18001eb66  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001eb6b  lea     rcx, [rbx+190h]
0x18001eb72  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001eb77  lea     rcx, [rbx+170h]
0x18001eb7e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001eb83  lea     rcx, [rbx+150h]
0x18001eb8a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001eb8f  lea     rcx, [rbx+60h]; lpCriticalSection
0x18001eb93  call    cs:__imp_DeleteCriticalSection
0x18001eb99  lea     rcx, [rbx+38h]; lpCriticalSection
0x18001eb9d  call    cs:__imp_DeleteCriticalSection
0x18001eba3  mov     rcx, rbx; this
0x18001eba6  add     rsp, 20h
0x18001ebaa  pop     rbx
0x18001ebab  jmp     ??1FSMObject@@MEAA@XZ; FSMObject::~FSMObject(void)
```
