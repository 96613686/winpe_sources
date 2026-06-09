# CAudioPumpDspManager::GetAudioPumpDspResourceManager(ushort *,ushort *,ushort *,IAudioPumpDspResourceManager * *)

- ea: `0x140072350`
- end: `0x14007271e`
- name: `?GetAudioPumpDspResourceManager@CAudioPumpDspManager@@UEAAJPEAG00PEAPEAUIAudioPumpDspResourceManager@@@Z`
- size: `974`
- prototype: `int(CAudioPumpDspManager *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IAudioPumpDspResourceManager **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x14000e11c`
- `0x140022930`
- `0x14002a120`
- `0x140035554`
- `0x1400378e4`
- `0x14004f178`
- `0x14004fc3c`
- `0x1400516e8`
- `0x14005d0e0`
- `0x140071870`
- `0x140071984`
- `0x1400719f4`
- `0x140072350`
- `0x14008d9bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140072397`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140072397`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140072436`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140072436`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140072510`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140072510`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CAudioPumpDspManager::GetAudioPumpDspResourceManager(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IAudioPumpDspResourceManager **a5)
{
  RTL_SRWLOCK *v8; // rbx
  RTL_SRWLOCK *v9; // r12
  struct IAudioPumpDspResourceManager *v10; // rax
  struct IAudioPumpDspResourceManager *v12; // rax
  HRESULT v13; // eax
  unsigned int v14; // ebx
  GUID v15; // xmm6
  const struct _tlgProvider_t *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  struct IAudioPumpDspResourceManager *v19; // rsi
  int v20; // eax
  unsigned int v21; // ebx
  _QWORD *v22; // rax
  int v23; // [rsp+20h] [rbp-108h]
  int v24; // [rsp+20h] [rbp-108h]
  struct IAudioPumpDspResourceManager *v25; // [rsp+40h] [rbp-E8h] BYREF
  struct IAudioPumpDspResourceManager *v26; // [rsp+48h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v27; // [rsp+50h] [rbp-D8h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-D0h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-C8h] BYREF
  unsigned __int64 v30; // [rsp+68h] [rbp-C0h] BYREF
  int v31[2]; // [rsp+70h] [rbp-B8h] BYREF
  _OWORD v32[2]; // [rsp+80h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v34[32]; // [rsp+B0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v28 = a3;
  v8 = this + 9;
  AcquireSRWLockShared(this + 9);
  v27 = v8;
  v9 = this + 10;
  std::wstring::wstring(v32, a2);
  std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::find(
    &this[10],
    &v26,
    v32);
  std::wstring::~wstring(v32);
  if ( v26 != this[11].Ptr )
  {
    wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::try_query<IAudioPumpDspResourceManager>(
      (char *)v26 + 48,
      &v26);
    v10 = v26;
    if ( v26 )
    {
      v26 = 0;
      *a5 = v10;
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v26);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v27);
      return 0;
    }
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v26);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v27);
  AcquireSRWLockExclusive(v8);
  v26 = (struct IAudioPumpDspResourceManager *)v8;
  std::wstring::wstring(v32, a2);
  std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::find(
    &this[10],
    &v25,
    v32);
  std::wstring::~wstring(v32);
  if ( v25 != this[11].Ptr )
  {
    wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::try_query<IAudioPumpDspResourceManager>(
      (char *)v25 + 48,
      &v25);
    v12 = v25;
    if ( v25 )
    {
      v25 = 0;
      *a5 = v12;
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
      return 0;
    }
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v25);
  }
  pclsid = 0;
  if ( a4 )
  {
    v13 = CLSIDFromString(a4, &pclsid);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v15 = pclsid;
      v16 = AudioDgTelemetryProvider::Provider();
      v25 = 0;
      v32[0] = v15;
      v30 = (unsigned __int64)&this[1] & -(__int64)(this != 0);
      *(_QWORD *)v31 = v16;
      v29 = a2;
      v17 = Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceManager,IAudioPumpDspResourceManager,unsigned short * &,unsigned short * &,std::shared_ptr<CSerialWorkQueue> &,_tlgProvider_t const * &,_GUID &,IAudioDspProviderManager * &>(
              (unsigned int)&v25,
              (unsigned int)&v29,
              (unsigned int)&v28,
              (int)this + 144,
              (__int64)v31,
              (__int64)v32,
              (__int64)&v30);
      v18 = v17;
      if ( v17 >= 0 )
      {
        v27 = 0;
        v19 = v25;
        v29 = (unsigned __int16 *)v25;
        v20 = wil::com_weak_query_nothrow<IAudioPumpDspResourceManager *>(&v29, &v27);
        v21 = v20;
        if ( v20 >= 0 )
        {
          std::wstring::wstring(v34, a2);
          v22 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::_Try_emplace<std::wstring,>(
                            v9,
                            v32,
                            v34);
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(*v22 + 48LL, v27);
          std::wstring::~wstring(v34);
          v25 = 0;
          *a5 = v19;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v25);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7D,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopumpdspmanager.cpp",
            (const char *)(unsigned int)v20,
            v24);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v25);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
          return v21;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopumpdspmanager.cpp",
          (const char *)(unsigned int)v17,
          v24);
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v25);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopumpdspmanager.cpp",
        (const char *)(unsigned int)v13,
        v23);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopumpdspmanager.cpp",
      (const char *)0x80070057LL,
      v23);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140072350  mov     rax, rsp
0x140072353  push    rbx
0x140072354  push    rsi
0x140072355  push    r12
0x140072357  push    r13
0x140072359  push    r14
0x14007235b  push    r15
0x14007235d  sub     rsp, 0F8h
0x140072364  movaps  xmmword ptr [rax-48h], xmm6
0x140072368  mov     rax, cs:__security_cookie
0x14007236f  xor     rax, rsp
0x140072372  mov     [rsp+128h+var_58], rax
0x14007237a  mov     r13, r9
0x14007237d  mov     [rsp+128h+var_D0], r8
0x140072382  mov     r14, rdx
0x140072385  mov     rsi, rcx
0x140072388  mov     r15, [rsp+128h+arg_20]
0x140072390  lea     rbx, [rcx+48h]
0x140072394  mov     rcx, rbx; SRWLock
0x140072397  call    cs:__imp_AcquireSRWLockShared
0x14007239d  mov     [rsp+128h+var_D8], rbx
0x1400723a2  lea     r12, [rsi+50h]
0x1400723a6  mov     rdx, r14
0x1400723a9  lea     rcx, [rsp+128h+var_A8]
0x1400723b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400723b6  lea     r8, [rsp+128h+var_A8]
0x1400723be  lea     rdx, [rsp+128h+var_E0]
0x1400723c3  mov     rcx, r12
0x1400723c6  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::find(std::wstring const &)
0x1400723cb  lea     rcx, [rsp+128h+var_A8]
0x1400723d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400723d8  mov     rcx, [rsp+128h+var_E0]
0x1400723dd  cmp     rcx, [rsi+58h]
0x1400723e1  jz      short loc_140072429
0x1400723e3  add     rcx, 30h ; '0'
0x1400723e7  lea     rdx, [rsp+128h+var_E0]
0x1400723ec  call    ??$try_query@UIAudioPumpDspResourceManager@@@?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIAudioPumpDspResourceManager@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::try_query<IAudioPumpDspResourceManager>(void)
0x1400723f1  mov     rax, [rsp+128h+var_E0]
0x1400723f6  lea     rcx, [rsp+128h+var_E0]
0x1400723fb  test    rax, rax
0x1400723fe  jz      short loc_140072423
0x140072400  mov     [rsp+128h+var_E0], 0
0x140072409  mov     [r15], rax
0x14007240c  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140072411  nop
0x140072412  lea     rcx, [rsp+128h+var_D8]
0x140072417  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14007241c  xor     eax, eax
0x14007241e  jmp     loc_1400726F3
0x140072423  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140072428  nop
0x140072429  lea     rcx, [rsp+128h+var_D8]
0x14007242e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140072433  mov     rcx, rbx; SRWLock
0x140072436  call    cs:__imp_AcquireSRWLockExclusive
0x14007243c  mov     [rsp+128h+var_E0], rbx
0x140072441  mov     rdx, r14
0x140072444  lea     rcx, [rsp+128h+var_A8]
0x14007244c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140072451  lea     r8, [rsp+128h+var_A8]
0x140072459  lea     rdx, [rsp+128h+var_E8]
0x14007245e  mov     rcx, r12
0x140072461  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::find(std::wstring const &)
0x140072466  lea     rcx, [rsp+128h+var_A8]
0x14007246e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140072473  mov     rcx, [rsp+128h+var_E8]
0x140072478  cmp     rcx, [rsi+58h]
0x14007247c  jz      short loc_1400724C3
0x14007247e  add     rcx, 30h ; '0'
0x140072482  lea     rdx, [rsp+128h+var_E8]
0x140072487  call    ??$try_query@UIAudioPumpDspResourceManager@@@?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIAudioPumpDspResourceManager@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::try_query<IAudioPumpDspResourceManager>(void)
0x14007248c  mov     rax, [rsp+128h+var_E8]
0x140072491  lea     rcx, [rsp+128h+var_E8]
0x140072496  test    rax, rax
0x140072499  jz      short loc_1400724BE
0x14007249b  mov     [rsp+128h+var_E8], 0
0x1400724a4  mov     [r15], rax
0x1400724a7  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x1400724ac  nop
0x1400724ad  lea     rcx, [rsp+128h+var_E0]
0x1400724b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400724b7  xor     eax, eax
0x1400724b9  jmp     loc_1400726F3
0x1400724be  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x1400724c3  xorps   xmm0, xmm0
0x1400724c6  movups  xmmword ptr [rsp+128h+pclsid.Data1], xmm0
0x1400724ce  test    r13, r13
0x1400724d1  jnz     short loc_140072505
0x1400724d3  mov     rcx, [rsp+128h]; this
0x1400724db  mov     ebx, 80070057h
0x1400724e0  mov     r9d, ebx; char *
0x1400724e3  lea     r8, aAvcoreAudiocor_33; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400724ea  lea     edx, [r13+76h]; void *
0x1400724ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400724f3  nop
0x1400724f4  lea     rcx, [rsp+128h+var_E0]
0x1400724f9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400724fe  mov     eax, ebx
0x140072500  jmp     loc_1400726F3
0x140072505  lea     rdx, [rsp+128h+pclsid]; pclsid
0x14007250d  mov     rcx, r13; lpsz
0x140072510  call    cs:__imp_CLSIDFromString
0x140072516  mov     ebx, eax
0x140072518  test    eax, eax
0x14007251a  jns     short loc_14007254A
0x14007251c  mov     rcx, [rsp+128h]; this
0x140072524  mov     r9d, eax; char *
0x140072527  lea     r8, aAvcoreAudiocor_33; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007252e  mov     edx, 77h ; 'w'; void *
0x140072533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140072538  nop
0x140072539  lea     rcx, [rsp+128h+var_E0]
0x14007253e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140072543  mov     eax, ebx
0x140072545  jmp     loc_1400726F3
0x14007254a  mov     rax, rsi
0x14007254d  lea     rcx, [rsi+8]
0x140072551  neg     rax
0x140072554  sbb     rbx, rbx
0x140072557  and     rbx, rcx
0x14007255a  movups  xmm6, xmmword ptr [rsp+128h+pclsid.Data1]
0x140072562  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140072567  nop
0x140072568  mov     [rsp+128h+var_E8], 0
0x140072571  movdqu  [rsp+128h+var_A8], xmm6
0x14007257a  mov     [rsp+128h+var_C0], rbx
0x14007257f  mov     qword ptr [rsp+128h+var_B8], rax
0x140072584  mov     rax, [rsp+128h+var_D0]
0x140072589  mov     [rsp+128h+var_D0], rax
0x14007258e  mov     [rsp+128h+var_C8], r14
0x140072593  lea     r9, [rsi+90h]
0x14007259a  lea     rax, [rsp+128h+var_C0]
0x14007259f  mov     [rsp+128h+var_F8], rax
0x1400725a4  lea     rax, [rsp+128h+var_A8]
0x1400725ac  mov     [rsp+128h+var_100], rax
0x1400725b1  lea     rax, [rsp+128h+var_B8]
0x1400725b6  mov     qword ptr [rsp+128h+var_108], rax; int
0x1400725bb  lea     r8, [rsp+128h+var_D0]
0x1400725c0  lea     rdx, [rsp+128h+var_C8]
0x1400725c5  lea     rcx, [rsp+128h+var_E8]
0x1400725ca  call    ??$MakeAndInitialize@VCAudioPumpDspResourceManager@@UIAudioPumpDspResourceManager@@AEAPEAGAEAPEAGAEAV?$shared_ptr@VCSerialWorkQueue@@@std@@AEAPEBU_tlgProvider_t@@AEAU_GUID@@AEAPEAUIAudioDspProviderManager@@@Details@WRL@Microsoft@@YAJPEAPEAUIAudioPumpDspResourceManager@@AEAPEAG1AEAV?$shared_ptr@VCSerialWorkQueue@@@std@@AEAPEBU_tlgProvider_t@@AEAU_GUID@@AEAPEAUIAudioDspProviderManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceManager,IAudioPumpDspResourceManager,ushort * &,ushort * &,std::shared_ptr<CSerialWorkQueue> &,_tlgProvider_t const * &,_GUID &,IAudioDspProviderManager * &>(IAudioPumpDspResourceManager * *,ushort * &,ushort * &,std::shared_ptr<CSerialWorkQueue> &,_tlgProvider_t const * &,_GUID &,IAudioDspProviderManager * &)
0x1400725cf  mov     ebx, eax
0x1400725d1  test    eax, eax
0x1400725d3  jns     short loc_14007260E
0x1400725d5  mov     rcx, [rsp+128h]; this
0x1400725dd  mov     r9d, eax; char *
0x1400725e0  lea     r8, aAvcoreAudiocor_33; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400725e7  mov     edx, 7Ah ; 'z'; void *
0x1400725ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400725f1  nop
0x1400725f2  lea     rcx, [rsp+128h+var_E8]
0x1400725f7  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x1400725fc  nop
0x1400725fd  lea     rcx, [rsp+128h+var_E0]
0x140072602  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140072607  mov     eax, ebx
0x140072609  jmp     loc_1400726F3
0x14007260e  mov     [rsp+128h+var_D8], 0
0x140072617  mov     rsi, [rsp+128h+var_E8]
0x14007261c  mov     [rsp+128h+var_C8], rsi
0x140072621  lea     rdx, [rsp+128h+var_D8]
0x140072626  lea     rcx, [rsp+128h+var_C8]
0x14007262b  call    ??$com_weak_query_nothrow@PEAUIAudioPumpDspResourceManager@@@wil@@YAJ$$QEAPEAUIAudioPumpDspResourceManager@@PEAPEAUIWeakReference@@@Z; wil::com_weak_query_nothrow<IAudioPumpDspResourceManager *>(IAudioPumpDspResourceManager * &&,IWeakReference * *)
0x140072630  mov     ebx, eax
0x140072632  test    eax, eax
0x140072634  jns     short loc_140072677
0x140072636  mov     rcx, [rsp+128h]; this
0x14007263e  mov     r9d, eax; char *
0x140072641  lea     r8, aAvcoreAudiocor_33; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140072648  mov     edx, 7Dh ; '}'; void *
0x14007264d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140072652  nop
0x140072653  lea     rcx, [rsp+128h+var_D8]
0x140072658  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007265d  nop
0x14007265e  lea     rcx, [rsp+128h+var_E8]
0x140072663  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140072668  nop
0x140072669  lea     rcx, [rsp+128h+var_E0]
0x14007266e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140072673  mov     eax, ebx
0x140072675  jmp     short loc_1400726F3
0x140072677  mov     rdx, r14
0x14007267a  lea     rcx, [rsp+128h+var_78]
0x140072682  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140072687  nop
0x140072688  lea     r8, [rsp+128h+var_78]
0x140072690  lea     rdx, [rsp+128h+var_A8]
0x140072698  mov     rcx, r12
0x14007269b  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1400726a0  mov     rcx, [rax]
0x1400726a3  add     rcx, 30h ; '0'
0x1400726a7  mov     rdx, [rsp+128h+var_D8]
0x1400726ac  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400726b1  nop
0x1400726b2  lea     rcx, [rsp+128h+var_78]
0x1400726ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400726bf  mov     [rsp+128h+var_E8], 0
0x1400726c8  mov     [r15], rsi
0x1400726cb  lea     rcx, [rsp+128h+var_D8]
0x1400726d0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400726d5  nop
0x1400726d6  lea     rcx, [rsp+128h+var_E8]
0x1400726db  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x1400726e0  nop
0x1400726e1  lea     rcx, [rsp+128h+var_E0]
0x1400726e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400726eb  xor     eax, eax
0x1400726ed  jmp     short loc_1400726F3
0x1400726ef  mov     eax, dword ptr [rsp+128h+var_E8]
0x1400726f3  mov     rcx, [rsp+128h+var_58]
0x1400726fb  xor     rcx, rsp; StackCookie
0x1400726fe  call    __security_check_cookie
0x140072703  movaps  xmm6, [rsp+128h+var_48]
0x14007270b  add     rsp, 0F8h
0x140072712  pop     r15
0x140072714  pop     r14
0x140072716  pop     r13
0x140072718  pop     r12
0x14007271a  pop     rsi
0x14007271b  pop     rbx
0x14007271c  retn
```
