# FSClientContext::~FSClientContext(void)

- ea: `0x180067900`
- end: `0x180067aa3`
- name: `??1FSClientContext@@MEAA@XZ`
- size: `419`
- prototype: `void __fastcall(FSClientContext *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180067b40`

## callees

- `0x180005d98`
- `0x180005ed4`
- `0x180008cf0`
- `0x1800095c8`
- `0x18000a460`
- `0x180017574`
- `0x1800198f4`
- `0x1800671bc`
- `0x180067808`
- `0x180067870`
- `0x180067900`
- `0x1800687d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067a82`

## pseudocode

```c
void __fastcall FSClientContext::~FSClientContext(FSClientContext *this)
{
  __int64 **v2; // rdi
  __int64 *v3; // rdx
  __int64 *v4; // rcx
  __int64 v5; // rax

  *(_QWORD *)this = &FSClientContext::`vftable'{for `IFSClientContext'};
  *((_QWORD *)this + 1) = &FSClientContext::`vftable'{for `IFSVMKSEventSignalCallback'};
  FSClientContext::CloseContext(this);
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, this);
  v2 = (__int64 **)((char *)this + 1312);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = (__int64 *)v3[1];
    v5 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v5 + 8) = v4;
    utl::_ContainerBase<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>,utl::allocator<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>>>::_DeleteNode<utl::_DlistNode<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>>>();
  }
  *((_QWORD *)this + 166) = 0;
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 1296);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 1280);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 1224);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 992);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 976);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 968);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 960);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 928);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 896);
  CTUnkArray<FSVMServerKSEvent>::~CTUnkArray<FSVMServerKSEvent>((char *)this + 872);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 864);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 856);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 800);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 792);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 744);
  CVPtrList::~CVPtrList((FSClientContext *)((char *)this + 296));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  `vector destructor iterator'(
    (char *)this + 176,
    0x18u,
    3u,
    CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>);
  `vector destructor iterator'(
    (char *)this + 104,
    0x18u,
    3u,
    CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 24);
  _InterlockedDecrement(&g_lRefModule);
}

```

## disassembly

```asm
0x180067900  mov     [rsp+arg_0], rbx
0x180067905  push    rdi
0x180067906  sub     rsp, 20h
0x18006790a  lea     rax, ??_7FSClientContext@@6BIFSClientContext@@@; const FSClientContext::`vftable'{for `IFSClientContext'}
0x180067911  mov     rbx, rcx
0x180067914  mov     [rcx], rax
0x180067917  lea     rax, ??_7FSClientContext@@6BIFSVMKSEventSignalCallback@@@; const FSClientContext::`vftable'{for `IFSVMKSEventSignalCallback'}
0x18006791e  mov     [rcx+8], rax
0x180067922  call    ?CloseContext@FSClientContext@@UEAAXXZ; FSClientContext::CloseContext(void)
0x180067927  mov     edx, 10h
0x18006792c  cmp     cs:byte_18010EC4D, dl
0x180067932  jb      short loc_180067951
0x180067934  mov     rcx, cs:WPP_GLOBAL_Control
0x18006793b  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x180067942  mov     r9, rbx
0x180067945  mov     rcx, [rcx+0D8h]
0x18006794c  call    WPP_SF_q
0x180067951  lea     rdi, [rbx+520h]
0x180067958  mov     rdx, [rdi]
0x18006795b  cmp     rdx, rdi
0x18006795e  jz      short loc_180067975
0x180067960  mov     rcx, [rdx+8]
0x180067964  mov     rax, [rdx]
0x180067967  mov     [rcx], rax
0x18006796a  mov     [rax+8], rcx
0x18006796e  call    ??$_DeleteNode@U?$_DlistNode@U?$pair@UKSIDENTIFIER@@V?$list@UKSIDENTIFIER@@V?$allocator@UKSIDENTIFIER@@@utl@@@utl@@@utl@@@utl@@@?$_ContainerBase@U?$pair@UKSIDENTIFIER@@V?$list@UKSIDENTIFIER@@V?$allocator@UKSIDENTIFIER@@@utl@@@utl@@@utl@@V?$allocator@U?$pair@UKSIDENTIFIER@@V?$list@UKSIDENTIFIER@@V?$allocator@UKSIDENTIFIER@@@utl@@@utl@@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@U?$pair@UKSIDENTIFIER@@V?$list@UKSIDENTIFIER@@V?$allocator@UKSIDENTIFIER@@@utl@@@utl@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>,utl::allocator<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>>>::_DeleteNode<utl::_DlistNode<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>>>(utl::_DlistNode<utl::pair<KSIDENTIFIER,utl::list<KSIDENTIFIER,utl::allocator<KSIDENTIFIER>>>> *)
0x180067973  jmp     short loc_180067958
0x180067975  lea     rcx, [rbx+510h]; void *
0x18006797c  mov     qword ptr [rdi+10h], 0
0x180067984  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067989  lea     rcx, [rbx+500h]
0x180067990  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180067995  lea     rcx, [rbx+4C8h]
0x18006799c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800679a1  lea     rcx, [rbx+3E0h]
0x1800679a8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800679ad  lea     rcx, [rbx+3D0h]; void *
0x1800679b4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800679b9  lea     rcx, [rbx+3C8h]; void *
0x1800679c0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800679c5  lea     rcx, [rbx+3C0h]; void *
0x1800679cc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800679d1  lea     rcx, [rbx+3A0h]; void *
0x1800679d8  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800679dd  lea     rcx, [rbx+380h]; void *
0x1800679e4  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800679e9  lea     rcx, [rbx+368h]
0x1800679f0  call    ??1?$CTUnkArray@VFSVMServerKSEvent@@@@QEAA@XZ; CTUnkArray<FSVMServerKSEvent>::~CTUnkArray<FSVMServerKSEvent>(void)
0x1800679f5  lea     rcx, [rbx+360h]; void *
0x1800679fc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067a01  lea     rcx, [rbx+358h]; void *
0x180067a08  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067a0d  lea     rcx, [rbx+320h]; void *
0x180067a14  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067a19  lea     rcx, [rbx+318h]; void *
0x180067a20  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067a25  lea     rcx, [rbx+2E8h]
0x180067a2c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180067a31  lea     rcx, [rbx+128h]; this
0x180067a38  call    ??1CVPtrList@@QEAA@XZ; CVPtrList::~CVPtrList(void)
0x180067a3d  lea     rcx, [rbx+100h]; lpCriticalSection
0x180067a44  call    cs:__imp_DeleteCriticalSection
0x180067a4a  mov     edi, 18h
0x180067a4f  lea     rcx, [rbx+0B0h]; void *
0x180067a56  lea     r9, ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; void (*)(void *)
0x180067a5d  mov     edx, edi; unsigned __int64
0x180067a5f  lea     r8d, [rdi-15h]; unsigned __int64
0x180067a63  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180067a68  lea     rcx, [rbx+68h]; void *
0x180067a6c  mov     edx, edi; unsigned __int64
0x180067a6e  lea     r9, ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; void (*)(void *)
0x180067a75  lea     r8d, [rdi-15h]; unsigned __int64
0x180067a79  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180067a7e  lea     rcx, [rbx+38h]; lpCriticalSection
0x180067a82  call    cs:__imp_DeleteCriticalSection
0x180067a88  lea     rcx, [rbx+18h]; void *
0x180067a8c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180067a91  lock dec cs:?g_lRefModule@@3JA; long g_lRefModule
0x180067a98  mov     rbx, [rsp+28h+arg_0]
0x180067a9d  add     rsp, 20h
0x180067aa1  pop     rdi
0x180067aa2  retn
```
