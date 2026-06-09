# GuestStateFile::MirrorFileToInternal(ushort const *,bool,_GUID const *)

- ea: `0x140081910`
- end: `0x140081fe5`
- name: `?MirrorFileToInternal@GuestStateFile@@AEAAXPEBG_NPEBU_GUID@@@Z`
- size: `1749`
- prototype: `void __fastcall(GuestStateFile *this, const unsigned __int16 *, bool, const struct _GUID *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400222f8`
- `0x140027a4c`
- `0x14002dd68`
- `0x14002ed00`
- `0x140030100`
- `0x140031c88`
- `0x14005159c`
- `0x14005879c`
- `0x14006af38`
- `0x14007fc4c`
- `0x140081910`
- `0x140081ff0`
- `0x14008209c`
- `0x1400841e4`
- `0x1400843bc`
- `0x140085db8`
- `0x14009d7ac`
- `0x1400d2d7c`
- `0x1400e8bdc`
- `0x140110a74`
- `0x140132940`
- `0x1401335fc`
- `0x1401af3a4`
- `0x1401af3d0`
- `0x1401af454`
- `0x1401b0890`
- `0x1401b09a4`
- `0x1401b0cec`
- `0x1401b3530`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140081f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140081f5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140081a12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140081a12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140081aa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140081aa0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140081e25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140081e25`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140081f02`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140081f02`
- `VirtDisk!OpenVirtualDisk` at `0x140081bfe`
- `VirtDisk!OpenVirtualDisk` at `0x140081c4c`
- `VirtDisk!OpenVirtualDisk` at `0x140081bfe`
- `VirtDisk!OpenVirtualDisk` at `0x140081c4c`
- `VirtDisk!MirrorVirtualDisk` at `0x140081db8`
- `VirtDisk!MirrorVirtualDisk` at `0x140081db8`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140081dee`
- `VirtDisk!GetVirtualDiskOperationProgress` at `0x140081dee`

## string_xrefs

- `0x140081ac3`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140081fd3`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x140081b6b`: `GuestStateFileOpenVirtualDisk`
- `0x140081c75`: `Failed to open "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GuestStateFile::MirrorFileToInternal(
        GuestStateFile *this,
        const unsigned __int16 *a2,
        bool a3,
        const struct _GUID *a4)
{
  __int64 FilePath; // rax
  const unsigned __int16 *v9; // rdi
  bool v10; // zf
  char v11; // al
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // al
  const unsigned __int16 *v15; // rcx
  __int64 v16; // r14
  _QWORD *v17; // rax
  _QWORD *v18; // rsi
  __int64 v19; // rax
  const WCHAR *v20; // rdx
  DWORD v21; // eax
  const char *v22; // r9
  const WCHAR *v23; // rdx
  PCWSTR *v24; // rax
  unsigned __int64 v25; // r8
  unsigned __int16 **v26; // rax
  unsigned __int16 *v27; // rdx
  unsigned int v28; // esi
  unsigned __int16 **v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // r14
  __int64 v32; // rax
  unsigned int v33; // eax
  const char *v34; // r9
  DWORD VirtualDiskOperationProgress; // eax
  unsigned __int16 **v36; // rdx
  PCWSTR *v37; // rax
  unsigned int Parameters; // [rsp+20h] [rbp-E0h]
  const char *Handle; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  __int128 v44; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v47[2]; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR Path[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v51[3]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v52; // [rsp+100h] [rbp+0h]
  _VIRTUAL_DISK_PROGRESS Progress; // [rsp+108h] [rbp+8h] BYREF
  PCWSTR v54[2]; // [rsp+128h] [rbp+28h] BYREF
  __m128i v55; // [rsp+138h] [rbp+38h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+148h] [rbp+48h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS v57; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v58[34]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v59; // [rsp+2A0h] [rbp+1A0h]
  _QWORD v60[42]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v61[42]; // [rsp+430h] [rbp+330h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  memset_0(v58, 0, 0x150u);
  FilePath = GuestStateFile::GetFilePath(this, &Progress);
  v9 = (const unsigned __int16 *)FilePath;
  if ( *(_QWORD *)(FilePath + 24) > 7u )
    v9 = *(const unsigned __int16 **)FilePath;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v58);
  v58[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable';
  v42 = (struct _GUID)*((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)v58,
    &v42,
    v9,
    a2,
    a3,
    a4);
  std::wstring::_Tidy_deallocate(&Progress);
  std::wstring::wstring(v51, a2);
  *(_OWORD *)Path = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Path[0]) = 0;
  *(_OWORD *)v54 = 0;
  v55 = si128;
  LOWORD(v54[0]) = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 5);
  *(_QWORD *)&v42.Data1 = (char *)this + 40;
  v42.Data4[0] = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7))
    || (v10 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7)) == 0,
        v11 = 0,
        !v10) )
  {
    v11 = 1;
  }
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D4,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8007139FLL,
      Parameters);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
  std::wstring::assign(Path, v12);
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 88LL))(*((_QWORD *)this + 7));
  std::wstring::assign(v54, v13);
  ReleaseSRWLockShared((PSRWLOCK)this + 5);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((GuestStateFile *)((char *)this + 120));
  *(_QWORD *)&v42.Data1 = (char *)this + 120;
  v14 = 1;
  v42.Data4[0] = 1;
  while ( v14 )
  {
    if ( *((_QWORD *)this + 18) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E6,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)0x800700AALL,
        Parameters);
    v15 = (const unsigned __int16 *)v51;
    if ( v52 > 7 )
      v15 = v51[0];
    GuestStateFile::EnsureDirectoryExists(v15);
    VirtualDiskHandle = (HANDLE)-1LL;
    VirtualStorageType.DeviceId = 2;
    VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
    memset(&v57, 0, sizeof(v57));
    v57.Version = OPEN_VIRTUAL_DISK_VERSION_2;
    v57.Version3.ResiliencyGuid = (GUID)*((_OWORD *)this + 6);
    memset_0(v61, 0, sizeof(v61));
    v16 = v59;
    v17 = (_QWORD *)GuestStateFile::GetFilePath(this, &Progress);
    v18 = v17;
    if ( v17[3] > 7u )
      v18 = (_QWORD *)*v17;
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
    v61[0] = &GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable';
    v19 = std::wstring::wstring(v46, v18);
    v44 = *((_OWORD *)this + 6);
    GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(v61, &v44, v19, v16 + 8);
    std::wstring::_Tidy_deallocate(&Progress);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &VirtualDiskHandle,
      -1);
    v20 = (const WCHAR *)Path;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = Path[0];
    v21 = OpenVirtualDisk(
            &VirtualStorageType,
            v20,
            VIRTUAL_DISK_ACCESS_NONE,
            OPEN_VIRTUAL_DISK_FLAG_NONE,
            &v57,
            &VirtualDiskHandle);
    v22 = (const char *)v21;
    if ( v21 )
    {
      if ( v21 == 3 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &VirtualDiskHandle,
          -1);
        v23 = (const WCHAR *)v54;
        if ( v55.m128i_i64[1] > 7uLL )
          v23 = v54[0];
        v22 = (const char *)OpenVirtualDisk(
                              &VirtualStorageType,
                              v23,
                              VIRTUAL_DISK_ACCESS_NONE,
                              OPEN_VIRTUAL_DISK_FLAG_NONE,
                              &v57,
                              &VirtualDiskHandle);
      }
      v24 = Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v24 = (PCWSTR *)Path[0];
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x411,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        v22,
        (unsigned int)"Failed to open \"%ws\"",
        (const char *)v24);
    }
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v61);
    v41 = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v41,
      1);
    v47[0] = 1;
    v25 = v52;
    v26 = v51;
    v27 = v51[0];
    if ( v52 > 7 )
      v26 = (unsigned __int16 **)v51[0];
    v47[1] = v26;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = v41;
    v28 = 2 * a3;
    v29 = v51;
    if ( v25 > 7 )
      v29 = (unsigned __int16 **)v27;
    if ( (unsigned __int8)anonymous_namespace_::FileExists(v29) )
      v28 |= 1u;
    memset_0(v60, 0, sizeof(v60));
    v43 = v59 + 8;
    v30 = (_QWORD *)GuestStateFile::GetFilePath(this, v46);
    v31 = v30;
    if ( v30[3] > 7u )
      v31 = (_QWORD *)*v30;
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v60);
    v60[0] = &GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable';
    v32 = std::wstring::wstring(&Progress, v31);
    v45 = *((_OWORD *)this + 6);
    GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(v60, &v45, v32, v43);
    std::wstring::_Tidy_deallocate(v46);
    v33 = MirrorVirtualDisk(VirtualDiskHandle, v28, v47, (char *)this + 152);
    v34 = (const char *)v33;
    if ( v33 && v33 != 997 )
    {
      v36 = v51;
      if ( v52 > 7 )
        v36 = (unsigned __int16 **)v51[0];
      v37 = Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v37 = (PCWSTR *)Path[0];
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x441,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        v34,
        (unsigned int)"Mirror operation of \"%ws\" to \"%ws\" failed.",
        (const char *)v37,
        v36);
    }
    while ( 1 )
    {
      memset(&Progress, 0, sizeof(Progress));
      VirtualDiskOperationProgress = GetVirtualDiskOperationProgress(
                                       VirtualDiskHandle,
                                       (LPOVERLAPPED)((char *)this + 152),
                                       &Progress);
      if ( VirtualDiskOperationProgress )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x44A,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
          (const char *)VirtualDiskOperationProgress,
          Parameters);
      if ( Progress.OperationStatus != 997 )
      {
        CancelIoEx(*((HANDLE *)this + 17), (LPOVERLAPPED)((char *)this + 152));
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x451,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
          (const char *)Progress.OperationStatus,
          (unsigned int)"Mirror operation of failed.",
          Handle);
      }
      if ( Progress.CurrentValue == Progress.CompletionValue )
        break;
      Sleep(0x12Cu);
    }
    wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v60);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 136,
      &VirtualDiskHandle);
    __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
      (char *)this + 144,
      &v41);
    if ( !a3 )
      std::wstring::operator=((char *)this + 184, v51);
    GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::~GuestStateFileMirrorVirtualDisk((GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk *)v60);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::~GuestStateFileOpenVirtualDisk((GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk *)v61);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&VirtualDiskHandle);
    v14 = 0;
    v42.Data4[0] = 0;
  }
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
  std::wstring::_Tidy_deallocate(v54);
  std::wstring::_Tidy_deallocate(Path);
  std::wstring::_Tidy_deallocate(v51);
  GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::~GuestStateFileMirrorFileToInternal((GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)v58);
}

```

## disassembly

```asm
0x140081910  mov     [rsp-8+arg_10], rbx
0x140081915  push    rbp
0x140081916  push    rsi
0x140081917  push    rdi
0x140081918  push    r12
0x14008191a  push    r13
0x14008191c  push    r14
0x14008191e  push    r15
0x140081920  lea     rbp, [rsp-490h]
0x140081928  sub     rsp, 590h
0x14008192f  mov     rax, cs:__security_cookie
0x140081936  xor     rax, rsp
0x140081939  mov     [rbp+4C0h+var_40], rax
0x140081940  mov     r14, r9
0x140081943  mov     r15b, r8b
0x140081946  mov     [rsp+5C0h+var_580], r8b
0x14008194b  mov     rsi, rdx
0x14008194e  mov     rbx, rcx
0x140081951  xor     edx, edx; Val
0x140081953  mov     r8d, 150h; Size
0x140081959  lea     rcx, [rbp+4C0h+var_430]; void *
0x140081960  call    memset_0
0x140081965  lea     rdx, [rbp+4C0h+Progress]
0x140081969  mov     rcx, rbx
0x14008196c  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081971  mov     rdi, rax
0x140081974  cmp     qword ptr [rax+18h], 7
0x140081979  jbe     short loc_14008197E
0x14008197b  mov     rdi, [rax]
0x14008197e  lea     rdx, aGueststatefile_3; "GuestStateFileMirrorFileToInternal"
0x140081985  lea     rcx, [rbp+4C0h+var_430]; struct wil::details::IFailureCallback *
0x14008198c  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081991  lea     rax, ??_7GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::`vftable'
0x140081998  mov     [rbp+4C0h+var_430], rax
0x14008199f  movups  xmm0, xmmword ptr [rbx+60h]
0x1400819a3  movdqu  xmmword ptr [rsp+5C0h+var_570.Data1], xmm0
0x1400819a9  mov     [rsp+5C0h+Handle], r14; struct _GUID *
0x1400819ae  mov     byte ptr [rsp+5C0h+Parameters], r15b; int
0x1400819b3  mov     r9, rsi; unsigned __int16 *
0x1400819b6  mov     r8, rdi; unsigned __int16 *
0x1400819b9  lea     rdx, [rsp+5C0h+var_570]; struct _GUID *
0x1400819be  lea     rcx, [rbp+4C0h+var_430]; this
0x1400819c5  call    ?StartActivity@GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1_NPEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StartActivity(_GUID,ushort const *,ushort const *,bool,_GUID const *)
0x1400819ca  nop
0x1400819cb  lea     rcx, [rbp+4C0h+Progress]
0x1400819cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400819d4  mov     rdx, rsi
0x1400819d7  lea     rcx, [rbp+4C0h+var_4D8]
0x1400819db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400819e0  nop
0x1400819e1  xorps   xmm0, xmm0
0x1400819e4  movups  xmmword ptr [rbp+4C0h+Path], xmm0
0x1400819e8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400819f0  movdqu  [rbp+4C0h+var_4E8], xmm1
0x1400819f5  xor     r15d, r15d
0x1400819f8  mov     word ptr [rbp+4C0h+Path], r15w
0x1400819fd  movups  xmmword ptr [rbp+4C0h+var_498], xmm0
0x140081a01  movdqu  [rbp+4C0h+var_488], xmm1
0x140081a06  mov     word ptr [rbp+4C0h+var_498], r15w
0x140081a0b  lea     rdi, [rbx+28h]
0x140081a0f  mov     rcx, rdi; SRWLock
0x140081a12  call    cs:__imp_AcquireSRWLockShared
0x140081a19  nop     dword ptr [rax+rax+00h]
0x140081a1e  mov     qword ptr [rsp+5C0h+var_570.Data1], rdi
0x140081a23  mov     [rsp+5C0h+var_570.Data4], 1
0x140081a28  mov     rcx, [rbx+38h]
0x140081a2c  mov     rax, [rcx]
0x140081a2f  mov     rax, [rax+28h]
0x140081a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a38  test    al, al
0x140081a3a  jz      short loc_140081A53
0x140081a3c  mov     rcx, [rbx+38h]
0x140081a40  mov     rax, [rcx]
0x140081a43  mov     rax, [rax+38h]
0x140081a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a4c  test    al, al
0x140081a4e  mov     al, r15b
0x140081a51  jz      short loc_140081A55
0x140081a53  mov     al, 1
0x140081a55  mov     rcx, [rbp+4C8h]; this
0x140081a5c  test    al, al
0x140081a5e  jnz     loc_140081FCD
0x140081a64  mov     rcx, [rbx+38h]
0x140081a68  mov     rax, [rcx]
0x140081a6b  mov     rax, [rax+48h]
0x140081a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a74  mov     rdx, rax
0x140081a77  lea     rcx, [rbp+4C0h+Path]
0x140081a7b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140081a80  mov     rcx, [rbx+38h]
0x140081a84  mov     rax, [rcx]
0x140081a87  mov     rax, [rax+58h]
0x140081a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a90  mov     rdx, rax
0x140081a93  lea     rcx, [rbp+4C0h+var_498]
0x140081a97  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140081a9c  nop
0x140081a9d  mov     rcx, rdi; SRWLock
0x140081aa0  call    cs:__imp_ReleaseSRWLockShared
0x140081aa7  nop     dword ptr [rax+rax+00h]
0x140081aac  lea     r13, [rbx+78h]
0x140081ab0  mov     rcx, r13; this
0x140081ab3  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140081ab8  mov     qword ptr [rsp+5C0h+var_570.Data1], r13
0x140081abd  mov     al, 1
0x140081abf  mov     [rsp+5C0h+var_570.Data4], al
0x140081ac3  lea     rdi, aOnecoreVmCommo_13; "onecore\\vm\\common\\gueststate\\guests"...
0x140081aca  test    al, al
0x140081acc  jz      loc_140081F58
0x140081ad2  lea     r12, [rbx+90h]
0x140081ad9  mov     rcx, [rbp+4C8h]; this
0x140081ae0  cmp     [r12], r15
0x140081ae4  jnz     loc_140081F44
0x140081aea  lea     rcx, [rbp+4C0h+var_4D8]
0x140081aee  cmp     [rbp+4C0h+var_4C0], 7
0x140081af3  cmova   rcx, [rbp+4C0h+var_4D8]; unsigned __int16 *
0x140081af8  call    ?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z; GuestStateFile::EnsureDirectoryExists(ushort const *)
0x140081afd  mov     [rbp+4C0h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x140081b05  mov     [rbp+4C0h+VirtualStorageType.DeviceId], 2
0x140081b0c  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140081b13  movdqu  xmmword ptr [rbp+4C0h+VirtualStorageType.VendorId.Data1], xmm0
0x140081b18  xorps   xmm1, xmm1
0x140081b1b  movups  xmmword ptr [rbp+4C0h+var_460.Version], xmm1
0x140081b1f  movups  xmmword ptr [rbp+4C0h+var_460.4+0Ch], xmm1
0x140081b23  movups  xmmword ptr [rbp+4C0h+var_460.4+18h], xmm1
0x140081b27  mov     [rbp+4C0h+var_460.Version], 2
0x140081b2e  movups  xmm0, xmmword ptr [rbx+60h]
0x140081b32  movdqu  xmmword ptr [rbp+4C0h+var_460.4+8], xmm0
0x140081b37  xor     edx, edx; Val
0x140081b39  mov     r8d, 150h; Size
0x140081b3f  lea     rcx, [rbp+4C0h+var_190]; void *
0x140081b46  call    memset_0
0x140081b4b  mov     r14, [rbp+4C0h+var_320]
0x140081b52  lea     rdx, [rbp+4C0h+Progress]
0x140081b56  mov     rcx, rbx
0x140081b59  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081b5e  mov     rsi, rax
0x140081b61  cmp     qword ptr [rax+18h], 7
0x140081b66  jbe     short loc_140081B6B
0x140081b68  mov     rsi, [rax]
0x140081b6b  lea     rdx, aGueststatefile; "GuestStateFileOpenVirtualDisk"
0x140081b72  lea     rcx, [rbp+4C0h+var_190]; struct wil::details::IFailureCallback *
0x140081b79  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081b7e  lea     rax, ??_7GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::`vftable'
0x140081b85  mov     [rbp+4C0h+var_190], rax
0x140081b8c  mov     rdx, rsi
0x140081b8f  lea     rcx, [rbp+4C0h+var_530]
0x140081b93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081b98  movups  xmm0, xmmword ptr [rbx+60h]
0x140081b9c  movdqu  [rsp+5C0h+var_550], xmm0
0x140081ba2  lea     r9, [r14+8]
0x140081ba6  mov     r8, rax
0x140081ba9  lea     rdx, [rsp+5C0h+var_550]
0x140081bae  lea     rcx, [rbp+4C0h+var_190]
0x140081bb5  call    ?StartActivity@GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140081bba  nop
0x140081bbb  lea     rcx, [rbp+4C0h+Progress]
0x140081bbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140081bc4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140081bc8  mov     rdx, rsi
0x140081bcb  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081bcf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140081bd4  lea     rdx, [rbp+4C0h+Path]
0x140081bd8  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140081bdd  cmova   rdx, [rbp+4C0h+Path]; Path
0x140081be2  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140081be6  mov     [rsp+5C0h+Handle], rax; Handle
0x140081beb  lea     rax, [rbp+4C0h+var_460]
0x140081bef  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140081bf4  xor     r9d, r9d; Flags
0x140081bf7  xor     r8d, r8d; VirtualDiskAccessMask
0x140081bfa  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140081bfe  call    cs:__imp_OpenVirtualDisk
0x140081c05  nop     dword ptr [rax+rax+00h]
0x140081c0a  mov     r9d, eax
0x140081c0d  test    eax, eax
0x140081c0f  jz      short loc_140081C8E
0x140081c11  cmp     eax, 3
0x140081c14  jnz     short loc_140081C5B
0x140081c16  mov     rdx, rsi
0x140081c19  lea     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081c1d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140081c22  lea     rdx, [rbp+4C0h+var_498]
0x140081c26  cmp     qword ptr [rbp+4C0h+var_488+8], 7
0x140081c2b  cmova   rdx, [rbp+4C0h+var_498]; Path
0x140081c30  lea     rax, [rbp+4C0h+VirtualDiskHandle]
0x140081c34  mov     [rsp+5C0h+Handle], rax; Handle
0x140081c39  lea     rax, [rbp+4C0h+var_460]
0x140081c3d  mov     [rsp+5C0h+Parameters], rax; Parameters
0x140081c42  xor     r9d, r9d; Flags
0x140081c45  xor     r8d, r8d; VirtualDiskAccessMask
0x140081c48  lea     rcx, [rbp+4C0h+VirtualStorageType]; VirtualStorageType
0x140081c4c  call    cs:__imp_OpenVirtualDisk
0x140081c53  nop     dword ptr [rax+rax+00h]
0x140081c58  mov     r9d, eax; char *
0x140081c5b  lea     rax, [rbp+4C0h+Path]
0x140081c5f  cmp     qword ptr [rbp+4C0h+var_4E8+8], 7
0x140081c64  cmova   rax, [rbp+4C0h+Path]
0x140081c69  mov     rcx, [rbp+4C8h]; this
0x140081c70  mov     [rsp+5C0h+Handle], rax; char *
0x140081c75  lea     rax, aFailedToOpenWs; "Failed to open \"%ws\""
0x140081c7c  mov     [rsp+5C0h+Parameters], rax; unsigned int
0x140081c81  mov     r8, rdi; unsigned int
0x140081c84  mov     edx, 411h; void *
0x140081c89  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x140081c8e  lea     rcx, [rbp+4C0h+var_190]
0x140081c95  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140081c9a  mov     [rsp+5C0h+var_578], r15
0x140081c9f  mov     esi, 1
0x140081ca4  mov     edx, esi
0x140081ca6  lea     rcx, [rsp+5C0h+var_578]
0x140081cab  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140081cb0  mov     [rbp+4C0h+var_510], rsi
0x140081cb4  mov     r8, [rbp+4C0h+var_4C0]
0x140081cb8  lea     rax, [rbp+4C0h+var_4D8]
0x140081cbc  mov     rdx, [rbp+4C0h+var_4D8]
0x140081cc0  cmp     r8, 7
0x140081cc4  cmova   rax, rdx
0x140081cc8  mov     [rbp+4C0h+var_508], rax
0x140081ccc  lea     r15, [rbx+98h]
0x140081cd3  xor     r14d, r14d
0x140081cd6  mov     [rbx+98h], r14
0x140081cdd  mov     [rbx+0A0h], r14
0x140081ce4  mov     [rbx+0A8h], r14
0x140081ceb  mov     rax, [rsp+5C0h+var_578]
0x140081cf0  mov     [rbx+0B0h], rax
0x140081cf7  movzx   esi, [rsp+5C0h+var_580]
0x140081cfc  add     esi, esi
0x140081cfe  lea     rcx, [rbp+4C0h+var_4D8]
0x140081d02  cmp     r8, 7
0x140081d06  cmova   rcx, rdx
0x140081d0a  call    _anonymous_namespace___FileExists
0x140081d0f  test    al, al
0x140081d11  jz      short loc_140081D16
0x140081d13  or      esi, 1
0x140081d16  xor     edx, edx; Val
0x140081d18  mov     r8d, 150h; Size
0x140081d1e  lea     rcx, [rbp+4C0h+var_2E0]; void *
0x140081d25  call    memset_0
0x140081d2a  mov     rax, [rbp+4C0h+var_320]
0x140081d31  add     rax, 8
0x140081d35  mov     [rsp+5C0h+var_560], rax
0x140081d3a  lea     rdx, [rbp+4C0h+var_530]
0x140081d3e  mov     rcx, rbx
0x140081d41  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x140081d46  mov     r14, rax
0x140081d49  cmp     qword ptr [rax+18h], 7
0x140081d4e  jbe     short loc_140081D53
0x140081d50  mov     r14, [rax]
0x140081d53  lea     rdx, aGueststatefile_10; "GuestStateFileMirrorVirtualDisk"
0x140081d5a  lea     rcx, [rbp+4C0h+var_2E0]; struct wil::details::IFailureCallback *
0x140081d61  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081d66  lea     rax, ??_7GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::`vftable'
0x140081d6d  mov     [rbp+4C0h+var_2E0], rax
0x140081d74  mov     rdx, r14
0x140081d77  lea     rcx, [rbp+4C0h+Progress]
0x140081d7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081d80  movups  xmm0, xmmword ptr [rbx+60h]
0x140081d84  movdqu  [rbp+4C0h+var_540], xmm0
0x140081d89  mov     r9, [rsp+5C0h+var_560]
0x140081d8e  mov     r8, rax
0x140081d91  lea     rdx, [rbp+4C0h+var_540]
0x140081d95  lea     rcx, [rbp+4C0h+var_2E0]
0x140081d9c  call    ?StartActivity@GuestStateFileMirrorVirtualDisk@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMirrorVirtualDisk::StartActivity(_GUID,std::wstring,_GUID const *)
0x140081da1  nop
0x140081da2  lea     rcx, [rbp+4C0h+var_530]
0x140081da6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140081dab  mov     r9, r15
0x140081dae  lea     r8, [rbp+4C0h+var_510]
0x140081db2  mov     edx, esi
0x140081db4  mov     rcx, [rbp+4C0h+VirtualDiskHandle]
0x140081db8  call    cs:__imp_MirrorVirtualDisk
0x140081dbf  nop     dword ptr [rax+rax+00h]
0x140081dc4  mov     r9d, eax; char *
0x140081dc7  test    eax, eax
0x140081dc9  jz      short loc_140081DD6
0x140081dcb  cmp     eax, 3E5h
0x140081dd0  jnz     loc_140081EB1
0x140081dd6  xorps   xmm0, xmm0
0x140081dd9  xor     eax, eax
0x140081ddb  movups  xmmword ptr [rbp+4C0h+Progress.OperationStatus], xmm0
0x140081ddf  mov     [rbp+4C0h+Progress.CompletionValue], rax
0x140081de3  lea     r8, [rbp+4C0h+Progress]; Progress
0x140081de7  mov     rdx, r15; Overlapped
0x140081dea  mov     rcx, [rbp+4C0h+VirtualDiskHandle]; VirtualDiskHandle
0x140081dee  call    cs:__imp_GetVirtualDiskOperationProgress
0x140081df5  nop     dword ptr [rax+rax+00h]
0x140081dfa  mov     rcx, [rbp+4C8h]; this
0x140081e01  test    eax, eax
0x140081e03  jnz     loc_140081F33
0x140081e09  cmp     [rbp+4C0h+Progress.OperationStatus], 3E5h
0x140081e10  jnz     loc_140081EF8
0x140081e16  mov     rax, [rbp+4C0h+Progress.CompletionValue]
0x140081e1a  cmp     [rbp+4C0h+Progress.CurrentValue], rax
0x140081e1e  jz      short loc_140081E33
0x140081e20  mov     ecx, 12Ch; dwMilliseconds
0x140081e25  call    cs:__imp_Sleep
0x140081e2c  nop     dword ptr [rax+rax+00h]
0x140081e31  jmp     short loc_140081DD6
0x140081e33  lea     rcx, [rbp+4C0h+var_2E0]
  ... truncated ...
```
