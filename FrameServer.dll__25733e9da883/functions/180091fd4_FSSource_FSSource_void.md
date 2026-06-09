# FSSource::~FSSource(void)

- ea: `0x180091fd4`
- end: `0x18009221b`
- name: `??1FSSource@@MEAA@XZ`
- size: `583`
- prototype: `void __fastcall(FSSource *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800922b0`

## callees

- `0x1800041f0`
- `0x180008cf0`
- `0x1800095c8`
- `0x18000a460`
- `0x18000a4a8`
- `0x180014f08`
- `0x180017574`
- `0x180091fd4`
- `0x1800a2670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180092109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009214a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009217b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800921f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180092203`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180092109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009214a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009217b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800921f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180092203`
- `MFPlat!MFUnlockWorkQueue` at `0x18009201f`
- `MFPlat!MFUnlockWorkQueue` at `0x18009201f`

## pseudocode

```c
void __fastcall FSSource::~FSSource(FSSource *this)
{
  DWORD v2; // ecx
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rcx

  *(_QWORD *)this = &FSSource::`vftable'{for `IFSSource'};
  *((_QWORD *)this + 1) = &FSSource::`vftable'{for `IFSControl'};
  *((_QWORD *)this + 2) = &FSSource::`vftable'{for `IFSErrorTelemetrySink'};
  FSSource::Shutdown(this);
  CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 288);
  v2 = *((_DWORD *)this + 71);
  if ( v2 )
  {
    MFUnlockWorkQueue(v2);
    *((_DWORD *)this + 71) = 0;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 18, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 132);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>((char *)this + 1032);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 127);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 125);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 123);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>((char *)this + 960);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 116);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 112);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 856);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 824);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 74);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 73);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 72);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 71);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  v4 = (void *)*((_QWORD *)this + 65);
  *((_QWORD *)this + 65) = 0;
  if ( v4 )
    operator delete(v4, v3);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 64);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>((char *)this + 488);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 55);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)this + 52);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)this + 49);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 40);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 39);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)this + 36);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 32);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)this + 27);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((void **)this + 24);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 22);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)this + 17);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  _InterlockedDecrement(&g_lRefModule);
}

```

## disassembly

```asm
0x180091fd4  mov     [rsp+arg_0], rbx
0x180091fd9  push    rdi
0x180091fda  sub     rsp, 20h
0x180091fde  lea     rax, ??_7FSSource@@6BIFSSource@@@; const FSSource::`vftable'{for `IFSSource'}
0x180091fe5  mov     rbx, rcx
0x180091fe8  mov     [rcx], rax
0x180091feb  lea     rax, ??_7FSSource@@6BIFSControl@@@; const FSSource::`vftable'{for `IFSControl'}
0x180091ff2  mov     [rcx+8], rax
0x180091ff6  lea     rax, ??_7FSSource@@6BIFSErrorTelemetrySink@@@; const FSSource::`vftable'{for `IFSErrorTelemetrySink'}
0x180091ffd  mov     [rcx+10h], rax
0x180092001  call    ?Shutdown@FSSource@@UEAAJXZ; FSSource::Shutdown(void)
0x180092006  lea     rdi, [rbx+120h]
0x18009200d  mov     rcx, rdi
0x180092010  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x180092015  mov     ecx, [rbx+11Ch]; dwWorkQueue
0x18009201b  test    ecx, ecx
0x18009201d  jz      short loc_18009202F
0x18009201f  call    cs:__imp_MFUnlockWorkQueue
0x180092025  mov     dword ptr [rbx+11Ch], 0
0x18009202f  cmp     cs:byte_18010EC4D, 10h
0x180092036  jb      short loc_18009205A
0x180092038  mov     rcx, cs:WPP_GLOBAL_Control
0x18009203f  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180092046  mov     edx, 12h
0x18009204b  mov     r9, rbx
0x18009204e  mov     rcx, [rcx+0D8h]
0x180092055  call    WPP_SF_q
0x18009205a  lea     rcx, [rbx+420h]; void *
0x180092061  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180092066  lea     rcx, [rbx+408h]
0x18009206d  call    ??1?$CTUnkArray@UIFSProcessActivity@@@@QEAA@XZ; CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(void)
0x180092072  lea     rcx, [rbx+3F8h]; void *
0x180092079  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18009207e  lea     rcx, [rbx+3E8h]; void *
0x180092085  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18009208a  lea     rcx, [rbx+3D8h]; void *
0x180092091  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180092096  lea     rcx, [rbx+3C0h]
0x18009209d  call    ??1?$CTUnkArray@UIFSProcessActivity@@@@QEAA@XZ; CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(void)
0x1800920a2  lea     rcx, [rbx+3A0h]; void *
0x1800920a9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800920ae  lea     rcx, [rbx+380h]; void *
0x1800920b5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800920ba  lea     rcx, [rbx+358h]
0x1800920c1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800920c6  lea     rcx, [rbx+338h]
0x1800920cd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800920d2  lea     rcx, [rbx+250h]; void *
0x1800920d9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800920de  lea     rcx, [rbx+248h]; void *
0x1800920e5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800920ea  lea     rcx, [rbx+240h]; void *
0x1800920f1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800920f6  lea     rcx, [rbx+238h]; void *
0x1800920fd  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180092102  lea     rcx, [rbx+210h]; lpCriticalSection
0x180092109  call    cs:__imp_DeleteCriticalSection
0x18009210f  mov     rcx, [rbx+208h]; void *
0x180092116  mov     qword ptr [rbx+208h], 0
0x180092121  test    rcx, rcx
0x180092124  jz      short loc_18009212B
0x180092126  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009212b  lea     rcx, [rbx+200h]; void *
0x180092132  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180092137  lea     rcx, [rbx+1E8h]
0x18009213e  call    ??1?$CTUnkArray@UIFSProcessActivity@@@@QEAA@XZ; CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(void)
0x180092143  lea     rcx, [rbx+1C0h]; lpCriticalSection
0x18009214a  call    cs:__imp_DeleteCriticalSection
0x180092150  lea     rcx, [rbx+1B8h]; void *
0x180092157  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18009215c  lea     rcx, [rbx+1A0h]; void *
0x180092163  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x180092168  lea     rcx, [rbx+188h]; void *
0x18009216f  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x180092174  lea     rcx, [rbx+160h]; lpCriticalSection
0x18009217b  call    cs:__imp_DeleteCriticalSection
0x180092181  lea     rcx, [rbx+140h]; void *
0x180092188  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18009218d  lea     rcx, [rbx+138h]; void *
0x180092194  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180092199  mov     rcx, rdi; void *
0x18009219c  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800921a1  lea     rcx, [rbx+110h]; void *
0x1800921a8  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800921ad  lea     rcx, [rbx+108h]; void *
0x1800921b4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800921b9  lea     rcx, [rbx+100h]; void *
0x1800921c0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800921c5  lea     rcx, [rbx+0D8h]; void *
0x1800921cc  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800921d1  lea     rcx, [rbx+0C0h]; void *
0x1800921d8  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800921dd  lea     rcx, [rbx+0B0h]; void *
0x1800921e4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800921e9  lea     rcx, [rbx+88h]; void *
0x1800921f0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800921f5  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800921f9  call    cs:__imp_DeleteCriticalSection
0x1800921ff  lea     rcx, [rbx+38h]; lpCriticalSection
0x180092203  call    cs:__imp_DeleteCriticalSection
0x180092209  lock dec cs:?g_lRefModule@@3JA; long g_lRefModule
0x180092210  mov     rbx, [rsp+28h+arg_0]
0x180092215  add     rsp, 20h
0x180092219  pop     rdi
0x18009221a  retn
```
