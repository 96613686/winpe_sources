# RadioManager::_InsertInstanceToList(IUIRadioInstanceInternal *)

- ea: `0x180020d50`
- end: `0x1800213cc`
- name: `?_InsertInstanceToList@RadioManager@@AEAAJPEAUIUIRadioInstanceInternal@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(RadioManager *__hidden this, struct IUIRadioInstanceInternal *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c72c`

## callees

- `0x180003fa0`
- `0x180004624`
- `0x180006a0c`
- `0x180006b98`
- `0x1800071c0`
- `0x180007568`
- `0x180007d28`
- `0x180008640`
- `0x18000a078`
- `0x18000a6a0`
- `0x18000a89c`
- `0x18000aa18`
- `0x18000b814`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000d784`
- `0x18001a914`
- `0x18001c51c`
- `0x1800201ac`
- `0x180020d50`
- `0x18002195c`
- `0x180023308`
- `0x18002378c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ff9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021111`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ff9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021111`

## string_xrefs

- `0x180020e32`: `IUIRadioInstanceInternal::GetMediaRMSignature`
- `0x180020e41`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`
- `0x1800211ca`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall RadioManager::_InsertInstanceToList(struct _RTL_CRITICAL_SECTION *this, const wchar_t *a2)
{
  char *v4; // rdi
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  HANDLE *p_LockSemaphore; // r14
  _QWORD *v14; // rbx
  _QWORD *i; // r15
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v23; // r8
  __int64 v24; // r8
  _QWORD *v25; // rdx
  char *v26; // rbx
  RadioManager *v27; // r13
  RadioManager *v28; // r15
  __int64 v29; // r9
  void (__fastcall *v30)(const wchar_t *, _QWORD, _QWORD); // rdi
  __int64 SystemState; // rax
  __int64 (__fastcall *v32)(const wchar_t *, GUID *, __int64 **); // rdi
  unsigned int v33; // eax
  char *v34; // rdi
  char *v35; // r14
  __int64 v36; // rcx
  __int64 v37; // r9
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  void (__fastcall *v42)(char *, _QWORD, __int64 *, __int64, int, int, _DWORD); // r11
  __int64 v43; // rax
  unsigned int v44; // edi
  __int64 v45; // rcx
  int v46; // [rsp+20h] [rbp-F8h]
  const char *v47; // [rsp+28h] [rbp-F0h]
  const char *v48; // [rsp+28h] [rbp-F0h]
  const char *v49; // [rsp+28h] [rbp-F0h]
  const char *v50; // [rsp+28h] [rbp-F0h]
  const char *v51; // [rsp+28h] [rbp-F0h]
  int v52; // [rsp+28h] [rbp-F0h]
  const wchar_t *v53; // [rsp+50h] [rbp-C8h] BYREF
  __int64 *v54; // [rsp+58h] [rbp-C0h] BYREF
  RadioManager *v55[2]; // [rsp+60h] [rbp-B8h] BYREF
  char *v56; // [rsp+70h] [rbp-A8h] BYREF
  const wchar_t *v57; // [rsp+78h] [rbp-A0h] BYREF
  struct _GUID *v58; // [rsp+80h] [rbp-98h] BYREF
  const wchar_t *v59; // [rsp+88h] [rbp-90h] BYREF
  __int64 *v60; // [rsp+90h] [rbp-88h] BYREF
  unsigned int v61; // [rsp+98h] [rbp-80h] BYREF
  __int64 *v62; // [rsp+A0h] [rbp-78h] BYREF
  __int64 *v63; // [rsp+A8h] [rbp-70h] BYREF
  struct _GUID v64; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v65; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-48h]
  unsigned __int64 v67; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v55[0] = (RadioManager *)this;
  v61 = 0;
  v4 = (char *)operator new(0x60u);
  *(_QWORD *)v4 = 0;
  *(_OWORD *)(v4 + 8) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *((_QWORD *)v4 + 4) = 7;
  *((_WORD *)v4 + 4) = 0;
  *(_OWORD *)(v4 + 40) = 0;
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 8) = 7;
  *((_WORD *)v4 + 20) = 0;
  *(_OWORD *)(v4 + 72) = 0;
  v4[88] = 0;
  v56 = v4;
  if ( *(const wchar_t **)v4 != a2 )
  {
    v53 = a2;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v53);
    v5 = *(_QWORD *)v4;
    *(_QWORD *)v4 = a2;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v64 = 0;
  v6 = (*(__int64 (__fastcall **)(const wchar_t *, struct _GUID *))(*(_QWORD *)a2 + 48LL))(a2, &v64);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x203,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (const char *)v6,
    (int)"IUIRadioInstanceInternal::GetMediaRMSignature",
    v47);
  v62 = 0;
  v7 = (*(__int64 (__fastcall **)(const wchar_t *, __int64 **))(*(_QWORD *)a2 + 56LL))(a2, &v62);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x206,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (const char *)v7,
    (int)"IUIRadioInstanceInternal::GetInstanceSignature",
    v48);
  v63 = 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, __int64 **))(*(_QWORD *)a2 + 72LL))(a2, &v63);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x20A,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (const char *)v8,
    (int)"IUIRadioInstanceInternal::GetInstanceFriendlyName",
    v49);
  v9 = (*(__int64 (__fastcall **)(const wchar_t *, unsigned int *))(*(_QWORD *)a2 + 64LL))(a2, &v61);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x20D,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (const char *)v9,
    (int)"IUIRadioInstanceInternal::GetInstanceDeviceRadioState",
    v50);
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v53 = (const wchar_t *)RMToString((const enum _DEVICE_RADIO_STATE *)&v61);
    v54 = v63;
    v60 = v62;
    v57 = (const wchar_t *)RmGuidToMediaTypeString(&v64);
    v58 = &v64;
    v59 = (const wchar_t *)"New RadioInstance inserted";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v10,
      (unsigned __int8 *)&unk_18002FC60,
      v11,
      v12,
      &v59,
      (__int64 *)&v58,
      &v57,
      &v60,
      &v54,
      &v53);
  }
  LODWORD(v60) = v61 & 4;
  v4[88] = (_DWORD)v60 == 0;
  EnterCriticalSection(this + 6);
  v53 = (const wchar_t *)&this[6];
  p_LockSemaphore = &this[7].LockSemaphore;
  v14 = p_LockSemaphore[1];
  for ( i = *p_LockSemaphore; i != v14; ++i )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v62 + v16) );
    v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*i + 40LL);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v17, *(_QWORD *)(v18 + 56), v19, v20) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v53);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>((void **)&v63);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>((void **)&v62);
      std::default_delete<RADIO_INSTANCE>::operator()(v21, v4);
      return 0;
    }
  }
  *(struct _GUID *)(v4 + 72) = v64;
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)v62 + v23) );
  std::wstring::_Assign<wchar_t>(v4 + 40, v62);
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)v63 + v24) );
  std::wstring::_Assign<wchar_t>(v4 + 8, v63);
  v25 = p_LockSemaphore[1];
  if ( v25 == p_LockSemaphore[2] )
  {
    std::vector<std::unique_ptr<RADIO_INSTANCE>>::_Emplace_reallocate<std::unique_ptr<RADIO_INSTANCE>>(
      p_LockSemaphore,
      v25,
      &v56);
    v26 = v56;
  }
  else
  {
    v26 = 0;
    v56 = 0;
    *v25 = v4;
    p_LockSemaphore[1] = (char *)p_LockSemaphore[1] + 8;
  }
  v27 = v55[0];
  v28 = (RadioManager *)((char *)v55[0] + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v55[0] + 48));
  v55[0] = v28;
  ++*((_DWORD *)v28 + 15);
  ProtectedSystemState::RefreshSysUIEnabled(v28);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v55);
  LOBYTE(v29) = 0;
  std::_Sort_unchecked<std::unique_ptr<RADIO_INSTANCE> *,std::less<void>>(
    *p_LockSemaphore,
    p_LockSemaphore[1],
    ((_BYTE *)p_LockSemaphore[1] - (_BYTE *)*p_LockSemaphore) >> 3,
    v29);
  v30 = *(void (__fastcall **)(const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a2 + 104LL);
  SystemState = ProtectedSystemState::GetSystemState(v28, v55);
  v30(a2, *(unsigned int *)(SystemState + 4), 0);
  if ( !(_DWORD)v60 )
  {
    v60 = 0;
    v32 = **(__int64 (__fastcall ***)(const wchar_t *, GUID *, __int64 **))a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
    v33 = v32(a2, &GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2, &v60);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
      (const char *)v33,
      (int)"IUIRadioInstanceInternal::QueryInterface(IUIRadioInstance)",
      v51);
    v65 = 0;
    v66 = 0;
    v67 = 7;
    LOWORD(v65) = 0;
    v34 = (char *)*p_LockSemaphore;
    v35 = (char *)p_LockSemaphore[1];
    while ( v34 != v35 )
    {
      v36 = *(_QWORD *)v34;
      if ( *(_QWORD *)(*(_QWORD *)v34 + 72LL) == *(_QWORD *)&v64.Data1 && *(_QWORD *)(v36 + 80) == *(_QWORD *)v64.Data4 )
      {
        v37 = -1;
        do
          ++v37;
        while ( *((_WORD *)v62 + v37) );
        v38 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36 + 40);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v38, *(_QWORD *)(v39 + 16), v40, v41) )
          break;
      }
      if ( *(_BYTE *)(*(_QWORD *)v34 + 88LL) )
        std::wstring::operator=(&v65, *(_QWORD *)v34 + 40LL);
      v34 += 8;
    }
    v42 = *(void (__fastcall **)(char *, _QWORD, __int64 *, __int64, int, int, _DWORD))(*((_QWORD *)v27 + 4) + 32LL);
    if ( v66 )
      v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v65);
    else
      v43 = 0;
    LOBYTE(v52) = 1;
    LOBYTE(v46) = 1;
    v42((char *)v27 + 32, 0, v60, v43, v46, v52, 0);
    v44 = v61;
    v54 = (__int64 *)a2;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v54);
    RadioManager::_AlignRadioInstanceWithToggleSwitch(v27, &v54, v44);
    if ( v54 )
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    if ( v67 > 7 )
      std::_Deallocate<16>(v65, 2 * v67 + 2);
    v66 = 0;
    v67 = 7;
    LOWORD(v65) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  }
  RadioManager::_NotifySysRadioChanged(v27);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v53);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>((void **)&v63);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>((void **)&v62);
  if ( v26 )
    std::default_delete<RADIO_INSTANCE>::operator()(v45, v26);
  return 0;
}

```

## disassembly

```asm
0x180020d50  mov     r11, rsp
0x180020d53  mov     [r11+18h], rbx
0x180020d57  mov     [r11+20h], rsi
0x180020d5b  push    rdi
0x180020d5c  push    r12
0x180020d5e  push    r13
0x180020d60  push    r14
0x180020d62  push    r15
0x180020d64  sub     rsp, 0F0h
0x180020d6b  mov     rax, cs:__security_cookie
0x180020d72  xor     rax, rsp
0x180020d75  mov     [rsp+118h+var_38], rax
0x180020d7d  mov     rsi, rdx
0x180020d80  mov     r14, rcx
0x180020d83  mov     [rsp+118h+var_B8], rcx
0x180020d88  xor     ebx, ebx
0x180020d8a  mov     [r11-80h], ebx
0x180020d8e  lea     ecx, [rbx+60h]; Size
0x180020d91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d96  mov     rdi, rax
0x180020d99  mov     [rax], rbx
0x180020d9c  lea     r13, [rax+8]
0x180020da0  xorps   xmm0, xmm0
0x180020da3  movups  xmmword ptr [r13+0], xmm0
0x180020da8  mov     [r13+10h], rbx
0x180020dac  lea     ecx, [rbx+7]
0x180020daf  mov     [r13+18h], rcx
0x180020db3  mov     [r13+0], bx
0x180020db8  lea     r12, [rax+28h]
0x180020dbc  movups  xmmword ptr [r12], xmm0
0x180020dc1  mov     [r12+10h], rbx
0x180020dc6  mov     [r12+18h], rcx
0x180020dcb  mov     [r12], bx
0x180020dd0  movups  xmmword ptr [rax+48h], xmm0
0x180020dd4  mov     [rax+58h], bl
0x180020dd7  mov     [rsp+118h+var_A8], rax
0x180020ddc  cmp     [rax], rsi
0x180020ddf  jz      short loc_180020E08
0x180020de1  mov     [rsp+118h+var_C8], rsi
0x180020de6  lea     rcx, [rsp+118h+var_C8]
0x180020deb  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x180020df0  mov     rcx, [rdi]
0x180020df3  mov     [rdi], rsi
0x180020df6  test    rcx, rcx
0x180020df9  jz      short loc_180020E08
0x180020dfb  mov     rax, [rcx]
0x180020dfe  mov     rax, [rax+10h]
0x180020e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e07  nop
0x180020e08  xorps   xmm0, xmm0
0x180020e0b  movups  xmmword ptr [rsp+118h+var_68.Data1], xmm0
0x180020e13  mov     rax, [rsi]
0x180020e16  lea     rdx, [rsp+118h+var_68]
0x180020e1e  mov     rcx, rsi
0x180020e21  mov     rax, [rax+30h]
0x180020e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2a  mov     rcx, [rsp+118h]; this
0x180020e32  lea     rdx, aIuiradioinstan; "IUIRadioInstanceInternal::GetMediaRMSig"...
0x180020e39  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x180020e3e  mov     r9d, eax; char *
0x180020e41  lea     r15, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180020e48  mov     r8, r15; unsigned int
0x180020e4b  mov     edx, 203h; void *
0x180020e50  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020e55  nop
0x180020e56  mov     [rsp+118h+var_78], rbx
0x180020e5e  mov     rax, [rsi]
0x180020e61  lea     rdx, [rsp+118h+var_78]
0x180020e69  mov     rcx, rsi
0x180020e6c  mov     rax, [rax+38h]
0x180020e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e75  mov     rcx, [rsp+118h]; this
0x180020e7d  lea     rdx, aIuiradioinstan_2; "IUIRadioInstanceInternal::GetInstanceSi"...
0x180020e84  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x180020e89  mov     r9d, eax; char *
0x180020e8c  mov     r8, r15; unsigned int
0x180020e8f  mov     edx, 206h; void *
0x180020e94  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020e99  nop
0x180020e9a  mov     [rsp+118h+var_70], rbx
0x180020ea2  mov     rax, [rsi]
0x180020ea5  lea     rdx, [rsp+118h+var_70]
0x180020ead  mov     rcx, rsi
0x180020eb0  mov     rax, [rax+48h]
0x180020eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eb9  mov     rcx, [rsp+118h]; this
0x180020ec1  lea     rdx, aIuiradioinstan_3; "IUIRadioInstanceInternal::GetInstanceFr"...
0x180020ec8  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x180020ecd  mov     r9d, eax; char *
0x180020ed0  mov     r8, r15; unsigned int
0x180020ed3  mov     edx, 20Ah; void *
0x180020ed8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020edd  mov     rax, [rsi]
0x180020ee0  lea     rdx, [rsp+118h+var_80]
0x180020ee8  mov     rcx, rsi
0x180020eeb  mov     rax, [rax+40h]
0x180020eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef4  mov     rcx, [rsp+118h]; this
0x180020efc  lea     rdx, aIuiradioinstan_0; "IUIRadioInstanceInternal::GetInstanceDe"...
0x180020f03  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x180020f08  mov     r9d, eax; char *
0x180020f0b  mov     r8, r15; unsigned int
0x180020f0e  mov     edx, 20Dh; void *
0x180020f13  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020f18  mov     eax, cs:dword_180037050
0x180020f1e  cmp     eax, 4
0x180020f21  jbe     loc_180020FD8
0x180020f27  lea     rcx, [rsp+118h+var_80]; enum _DEVICE_RADIO_STATE *
0x180020f2f  call    ?RMToString@@YAPEBDAEBW4_DEVICE_RADIO_STATE@@@Z; RMToString(_DEVICE_RADIO_STATE const &)
0x180020f34  mov     [rsp+118h+var_C8], rax
0x180020f39  mov     rax, [rsp+118h+var_70]
0x180020f41  mov     [rsp+118h+var_C0], rax
0x180020f46  mov     rax, [rsp+118h+var_78]
0x180020f4e  mov     [rsp+118h+var_88], rax
0x180020f56  lea     rcx, [rsp+118h+var_68]; struct _GUID *
0x180020f5e  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180020f63  mov     [rsp+118h+var_A0], rax
0x180020f68  lea     rax, [rsp+118h+var_68]
0x180020f70  mov     [rsp+118h+var_98], rax
0x180020f78  lea     rax, aNewRadioinstan; "New RadioInstance inserted"
0x180020f7f  mov     [rsp+118h+var_90], rax
0x180020f87  lea     rax, [rsp+118h+var_C8]
0x180020f8c  mov     [rsp+118h+var_D0], rax
0x180020f91  lea     rax, [rsp+118h+var_C0]
0x180020f96  mov     [rsp+118h+var_D8], rax
0x180020f9b  lea     rax, [rsp+118h+var_88]
0x180020fa3  mov     [rsp+118h+var_E0], rax
0x180020fa8  lea     rax, [rsp+118h+var_A0]
0x180020fad  mov     [rsp+118h+var_E8], rax
0x180020fb2  lea     rax, [rsp+118h+var_98]
0x180020fba  mov     [rsp+118h+var_F0], rax
0x180020fbf  lea     rax, [rsp+118h+var_90]
0x180020fc7  mov     qword ptr [rsp+118h+var_F8], rax
0x180020fcc  lea     rdx, unk_18002FC60
0x180020fd3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@53@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x180020fd8  mov     eax, [rsp+118h+var_80]
0x180020fdf  and     eax, 4
0x180020fe2  mov     dword ptr [rsp+118h+var_88], eax
0x180020fe9  setz    al
0x180020fec  mov     [rdi+58h], al
0x180020fef  lea     rbx, [r14+0F0h]
0x180020ff6  mov     rcx, rbx; lpCriticalSection
0x180020ff9  call    cs:__imp_EnterCriticalSection
0x180020fff  mov     [rsp+118h+var_C8], rbx
0x180021004  add     r14, 130h
0x18002100b  mov     rbx, [r14+8]
0x18002100f  mov     r15, [r14]
0x180021012  xor     ecx, ecx
0x180021014  jmp     short loc_18002104E
0x180021016  mov     r8, [rsp+118h+var_78]
0x18002101e  mov     rdx, [r15]
0x180021021  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021025  inc     r9
0x180021028  cmp     [r8+r9*2], cx
0x18002102d  jnz     short loc_180021025
0x18002102f  lea     rcx, [rdx+28h]
0x180021033  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021038  mov     rdx, [rdx+38h]
0x18002103c  mov     rcx, rax
0x18002103f  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180021044  xor     ecx, ecx
0x180021046  test    al, al
0x180021048  jnz     short loc_180021055
0x18002104a  add     r15, 8
0x18002104e  cmp     r15, rbx
0x180021051  jnz     short loc_180021016
0x180021053  jmp     short loc_18002108B
0x180021055  lea     rcx, [rsp+118h+var_C8]
0x18002105a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002105f  nop
0x180021060  lea     rcx, [rsp+118h+var_70]
0x180021068  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18002106d  nop
0x18002106e  lea     rcx, [rsp+118h+var_78]
0x180021076  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18002107b  nop
0x18002107c  mov     rdx, rdi
0x18002107f  call    ??R?$default_delete@URADIO_INSTANCE@@@std@@QEBAXPEAURADIO_INSTANCE@@@Z; std::default_delete<RADIO_INSTANCE>::operator()(RADIO_INSTANCE *)
0x180021084  xor     eax, eax
0x180021086  jmp     loc_18002139E
0x18002108b  movups  xmm0, xmmword ptr [rsp+118h+var_68.Data1]
0x180021093  movdqu  xmmword ptr [rdi+48h], xmm0
0x180021098  mov     rdx, [rsp+118h+var_78]
0x1800210a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800210a4  inc     r8
0x1800210a7  cmp     [rdx+r8*2], cx
0x1800210ac  jnz     short loc_1800210A4
0x1800210ae  mov     rcx, r12
0x1800210b1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800210b6  mov     rdx, [rsp+118h+var_70]
0x1800210be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800210c2  xor     r12d, r12d
0x1800210c5  inc     r8
0x1800210c8  cmp     [rdx+r8*2], r12w
0x1800210cd  jnz     short loc_1800210C5
0x1800210cf  mov     rcx, r13
0x1800210d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800210d7  mov     rdx, [r14+8]
0x1800210db  cmp     rdx, [r14+10h]
0x1800210df  jz      short loc_1800210F3
0x1800210e1  mov     rbx, r12
0x1800210e4  mov     [rsp+118h+var_A8], rbx
0x1800210e9  mov     [rdx], rdi
0x1800210ec  add     qword ptr [r14+8], 8
0x1800210f1  jmp     short loc_180021105
0x1800210f3  lea     r8, [rsp+118h+var_A8]
0x1800210f8  mov     rcx, r14
0x1800210fb  call    ??$_Emplace_reallocate@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@?$vector@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@V?$allocator@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<RADIO_INSTANCE>>::_Emplace_reallocate<std::unique_ptr<RADIO_INSTANCE>>(std::unique_ptr<RADIO_INSTANCE> * const,std::unique_ptr<RADIO_INSTANCE> &&)
0x180021100  mov     rbx, [rsp+118h+var_A8]
0x180021105  mov     r13, [rsp+118h+var_B8]
0x18002110a  lea     r15, [r13+30h]
0x18002110e  mov     rcx, r15; lpCriticalSection
0x180021111  call    cs:__imp_EnterCriticalSection
0x180021117  mov     [rsp+118h+var_B8], r15
0x18002111c  inc     dword ptr [r15+3Ch]
0x180021120  mov     rcx, r15; this
0x180021123  call    ?RefreshSysUIEnabled@ProtectedSystemState@@AEAAXXZ; ProtectedSystemState::RefreshSysUIEnabled(void)
0x180021128  lea     rcx, [rsp+118h+var_B8]
0x18002112d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180021132  mov     rdx, [r14+8]
0x180021136  mov     r9b, r12b
0x180021139  mov     r8, rdx
0x18002113c  sub     r8, [r14]
0x18002113f  sar     r8, 3
0x180021143  mov     rcx, [r14]
0x180021146  call    ??$_Sort_unchecked@PEAV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@U?$less@X@2@@std@@YAXPEAV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::unique_ptr<RADIO_INSTANCE> *,std::less<void>>(std::unique_ptr<RADIO_INSTANCE> *,std::unique_ptr<RADIO_INSTANCE> *,__int64,std::less<void>)
0x18002114b  mov     rax, [rsi]
0x18002114e  mov     rdi, [rax+68h]
0x180021152  lea     rdx, [rsp+118h+var_B8]
0x180021157  mov     rcx, r15
0x18002115a  call    ?GetSystemState@ProtectedSystemState@@QEBA?AUSystemState@@XZ; ProtectedSystemState::GetSystemState(void)
0x18002115f  xor     r8d, r8d
0x180021162  mov     edx, [rax+4]
0x180021165  mov     rcx, rsi
0x180021168  mov     rax, rdi
0x18002116b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021170  cmp     dword ptr [rsp+118h+var_88], r12d
0x180021178  jnz     loc_180021355
0x18002117e  mov     [rsp+118h+var_88], r12
0x180021186  mov     rax, [rsi]
0x180021189  mov     rdi, [rax]
0x18002118c  lea     rcx, [rsp+118h+var_88]
0x180021194  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021199  lea     r8, [rsp+118h+var_88]
0x1800211a1  lea     rdx, _GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2
0x1800211a8  mov     rcx, rsi
0x1800211ab  mov     rax, rdi
0x1800211ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b3  mov     rcx, [rsp+118h]; this
0x1800211bb  lea     rdx, aIuiradioinstan_4; "IUIRadioInstanceInternal::QueryInterfac"...
0x1800211c2  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x1800211c7  mov     r9d, eax; char *
0x1800211ca  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x1800211d1  mov     edx, 23Eh; void *
0x1800211d6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800211db  xorps   xmm0, xmm0
0x1800211de  movups  [rsp+118h+var_58], xmm0
0x1800211e6  mov     [rsp+118h+var_48], r12
0x1800211ee  mov     r15d, 7
0x1800211f4  mov     [rsp+118h+var_40], r15
0x1800211fc  mov     word ptr [rsp+118h+var_58], r12w
0x180021205  mov     rdi, [r14]
0x180021208  mov     r14, [r14+8]
0x18002120c  cmp     rdi, r14
0x18002120f  jz      short loc_180021282
0x180021211  mov     rcx, [rdi]
0x180021214  mov     rax, [rcx+48h]
0x180021218  cmp     rax, qword ptr [rsp+118h+var_68.Data1]
0x180021220  jnz     short loc_180021262
0x180021222  mov     rax, [rcx+50h]
0x180021226  cmp     rax, qword ptr [rsp+118h+var_68.Data4]
0x18002122e  jnz     short loc_180021262
0x180021230  mov     r8, [rsp+118h+var_78]
0x180021238  lea     rdx, [rcx+28h]
0x18002123c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021240  inc     r9
0x180021243  cmp     [r8+r9*2], r12w
0x180021248  jnz     short loc_180021240
0x18002124a  mov     rcx, rdx
0x18002124d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021252  mov     rdx, [rdx+10h]
0x180021256  mov     rcx, rax
0x180021259  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18002125e  test    al, al
0x180021260  jnz     short loc_180021282
0x180021262  mov     rdx, [rdi]
0x180021265  cmp     [rdx+58h], r12b
0x180021269  jz      short loc_18002127C
0x18002126b  add     rdx, 28h ; '('
0x18002126f  lea     rcx, [rsp+118h+var_58]
0x180021277  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002127c  add     rdi, 8
0x180021280  jmp     short loc_18002120C
0x180021282  mov     rax, [r13+20h]
0x180021286  mov     r11, [rax+20h]
0x18002128a  cmp     [rsp+118h+var_48], r12
0x180021292  jnz     short loc_180021299
0x180021294  mov     rax, r12
0x180021297  jmp     short loc_1800212A6
0x180021299  lea     rcx, [rsp+118h+var_58]
  ... truncated ...
```
