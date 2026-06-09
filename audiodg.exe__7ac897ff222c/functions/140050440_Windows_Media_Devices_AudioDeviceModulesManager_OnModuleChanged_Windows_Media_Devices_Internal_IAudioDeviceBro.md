# Windows::Media::Devices::AudioDeviceModulesManager::OnModuleChanged(Windows::Media::Devices::Internal::IAudioDeviceBroker *,Windows::Media::Devices::Internal::IAudioDeviceBrokerChangedEventArgs *)

- ea: `0x140050440`
- end: `0x140050a4b`
- name: `?OnModuleChanged@AudioDeviceModulesManager@Devices@Media@Windows@@QEAAJPEAUIAudioDeviceBroker@Internal@234@PEAUIAudioDeviceBrokerChangedEventArgs@6234@@Z`
- size: `1547`
- prototype: `__int64 __fastcall(Windows::Media::Devices::AudioDeviceModulesManager *__hidden this, struct Windows::Media::Devices::Internal::IAudioDeviceBroker *, struct Windows::Media::Devices::Internal::IAudioDeviceBrokerChangedEventArgs *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140035d34`
- `0x1400378e4`
- `0x140050440`
- `0x140055254`
- `0x140059a0c`
- `0x140059f34`
- `0x14005d0e0`
- `0x14008444c`
- `0x140085058`
- `0x140087134`
- `0x140088ac0`
- `0x14008a870`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140050a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140050a20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140050473`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140050473`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400505bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400505bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140050974`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140050594`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140050594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140050520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140050520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400505ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005090d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400505ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005090d`

## string_xrefs

- `0x140050770`: `Windows.Storage.Streams.DataWriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Windows::Media::Devices::AudioDeviceModulesManager::OnModuleChanged(
        RTL_SRWLOCK *this,
        struct Windows::Media::Devices::Internal::IAudioDeviceBroker *a2,
        struct Windows::Media::Devices::Internal::IAudioDeviceBrokerChangedEventArgs *a3)
{
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int *v13; // rbx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  int ActivationFactory; // esi
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // r14
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, _QWORD, void **); // r14
  void *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64 *); // r14
  __int64 v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // rsi
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-61h] BYREF
  void *v36; // [rsp+30h] [rbp-59h] BYREF
  __int64 v37; // [rsp+38h] [rbp-51h] BYREF
  __int64 v38; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  __int64 v40; // [rsp+50h] [rbp-39h] BYREF
  __int64 v41; // [rsp+58h] [rbp-31h] BYREF
  __int64 v42; // [rsp+60h] [rbp-29h] BYREF
  int v43; // [rsp+68h] [rbp-21h] BYREF
  __int64 v44; // [rsp+70h] [rbp-19h] BYREF
  unsigned int *v45; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v46[2]; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  __int64 v48; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = this + 8;
  AcquireSRWLockExclusive(this + 8);
  v46[0] = v5;
  v42 = 0;
  v41 = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  v37 = 0;
  v36 = 0;
  v44 = 0;
  v45 = 0;
  LODWORD(cb) = 0;
  string = 0;
  v43 = 0;
  if ( LOBYTE(this[16].Ptr) && this[14].Ptr )
  {
    v6 = *(_QWORD *)a3;
    v40 = 0;
    v7 = (*(__int64 (__fastcall **)(struct Windows::Media::Devices::Internal::IAudioDeviceBrokerChangedEventArgs *, __int64 *))(v6 + 48))(
           a3,
           &v40);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = (unsigned int)v7;
      v10 = 883;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)v9,
        (int)string);
      goto LABEL_12;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, SIZE_T *))(*(_QWORD *)v40 + 56LL))(v40, &cb);
    v8 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v10 = 884;
      goto LABEL_11;
    }
    if ( (unsigned int)cb < 0x28 )
    {
      v8 = 0;
LABEL_12:
      WindowsDeleteString(string);
      string = 0;
LABEL_56:
      wil::com_ptr_t<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,wil::err_returncode_policy>::~com_ptr_t<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,wil::err_returncode_policy>(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v46);
      return v8;
    }
    v13 = (unsigned int *)CoTaskMemAlloc((unsigned int)cb);
    v45 = v13;
    if ( !v13 )
    {
      v8 = -2147024882;
      v9 = 2147942414LL;
      v10 = 892;
      goto LABEL_11;
    }
    v14 = v42;
    v42 = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&hstringHeader,
                      (const unsigned __int16 (*)[35])v12);
    ActivationFactory = RoGetActivationFactory(*v15, &GUID_11fcbfc8_f93a_471b_b121_f379e349313c, &v42);
    if ( ActivationFactory < 0 )
    {
      v17 = 894;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      CoTaskMemFree(v13);
      v8 = ActivationFactory;
      goto LABEL_56;
    }
    v18 = v42;
    v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v42 + 48LL);
    v20 = v41;
    v41 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    ActivationFactory = v19(v18, v40, &v41);
    if ( ActivationFactory < 0 )
    {
      v17 = 895;
      goto LABEL_17;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v41 + 112LL))(
                          v41,
                          (unsigned int)cb,
                          v13);
    if ( ActivationFactory < 0 )
    {
      v17 = 896;
      goto LABEL_17;
    }
    WindowsDeleteString(string);
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *((_OWORD *)v13 + 1);
    ActivationFactory = GuidToHString((struct _GUID *)&hstringHeader, &string);
    if ( ActivationFactory < 0 )
    {
      v17 = 900;
      goto LABEL_17;
    }
    v21 = v37;
    v37 = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    ActivationFactory = Windows::Media::Devices::AudioDeviceModulesManager::FindAllByIdAndInstance(
                          this,
                          string,
                          v13[8],
                          &v37);
    if ( ActivationFactory < 0 )
    {
      v17 = 901;
      goto LABEL_17;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 56LL))(v37, &v43);
    if ( ActivationFactory < 0 )
    {
      v17 = 905;
      goto LABEL_17;
    }
    if ( v43 != 1 )
    {
      v22 = -2147467259;
      v23 = 906;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)(unsigned int)v22,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      CoTaskMemFree(v13);
      v8 = v22;
      goto LABEL_56;
    }
    v24 = v37;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v37 + 48LL);
    v26 = v36;
    v36 = 0;
    if ( v26 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
    ActivationFactory = v25(v24, 0, &v36);
    if ( ActivationFactory < 0 )
    {
      v17 = 909;
      goto LABEL_17;
    }
    if ( !v36 )
    {
      v22 = -2147467259;
      v23 = 910;
      goto LABEL_55;
    }
    v27 = v38;
    v38 = 0;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v48 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.Streams.DataWriter",
      0x23u,
      0x22u);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(v48, &v38);
    if ( ActivationFactory < 0 )
    {
      v17 = 914;
      goto LABEL_17;
    }
    if ( v38 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v38 + 96LL))(
                            v38,
                            (unsigned int)(cb - 40),
                            v13 + 10);
      if ( ActivationFactory < 0 )
      {
        v17 = 918;
        goto LABEL_17;
      }
      v28 = v38;
      v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 248LL);
      v30 = v39;
      v39 = 0;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      ActivationFactory = v29(v28, &v39);
      if ( ActivationFactory < 0 )
      {
        v17 = 919;
        goto LABEL_17;
      }
    }
    v44 = v39;
    hstringHeader.Reserved.Reserved1 = v36;
    v31 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,Windows::Media::Devices::IAudioDeviceModule *,Windows::Storage::Streams::IBuffer *>(
                       &v45,
                       &hstringHeader,
                       &v44);
    v32 = *v31;
    *v31 = 0;
    v44 = v32;
    if ( v45 )
    {
      v45 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Devices::IAudioDeviceModuleNotificationEventArgs,Microsoft::WRL::FtmBase>::Release();
    }
    v22 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>(
            &this[10],
            this,
            v32);
    if ( v22 < 0 )
    {
      v23 = 926;
      goto LABEL_55;
    }
    WindowsDeleteString(string);
    string = 0;
    CoTaskMemFree(v13);
    wil::com_ptr_t<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,wil::err_returncode_policy>::~com_ptr_t<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,wil::err_returncode_policy>(&v44);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v46);
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x140050440  mov     [rsp-8+arg_8], rbx
0x140050445  push    rbp
0x140050446  push    rsi
0x140050447  push    rdi
0x140050448  push    r14
0x14005044a  push    r15
0x14005044c  lea     rbp, [rsp-37h]
0x140050451  sub     rsp, 0C0h
0x140050458  mov     rax, cs:__security_cookie
0x14005045f  xor     rax, rsp
0x140050462  mov     [rbp+57h+var_30], rax
0x140050466  mov     rsi, r8
0x140050469  mov     rdi, rcx
0x14005046c  lea     rbx, [rcx+40h]
0x140050470  mov     rcx, rbx; SRWLock
0x140050473  call    cs:__imp_AcquireSRWLockExclusive
0x140050479  mov     [rbp+57h+var_60], rbx
0x14005047d  xor     r15d, r15d
0x140050480  mov     [rbp+57h+var_80], r15
0x140050484  mov     [rbp+57h+var_88], r15
0x140050488  mov     [rbp+57h+var_A0], r15
0x14005048c  mov     [rbp+57h+var_90], r15
0x140050490  mov     [rbp+57h+var_98], r15
0x140050494  mov     [rbp+57h+var_A8], r15
0x140050498  mov     [rbp+57h+var_B0], r15
0x14005049c  mov     [rbp+57h+var_70], r15
0x1400504a0  mov     [rbp+57h+var_68], r15
0x1400504a4  mov     dword ptr [rbp+57h+cb], r15d
0x1400504a8  mov     [rbp+57h+string], r15
0x1400504ac  mov     [rbp+57h+var_78], r15d
0x1400504b0  cmp     [rdi+80h], r15b
0x1400504b7  jz      loc_140050972
0x1400504bd  cmp     [rdi+70h], r15
0x1400504c1  jz      loc_140050972
0x1400504c7  mov     rax, [rsi]
0x1400504ca  mov     [rbp+57h+var_90], r15
0x1400504ce  lea     rdx, [rbp+57h+var_90]
0x1400504d2  mov     rcx, rsi
0x1400504d5  mov     rax, [rax+30h]
0x1400504d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400504de  mov     ebx, eax
0x1400504e0  test    eax, eax
0x1400504e2  jns     short loc_1400504EE
0x1400504e4  mov     r9d, eax
0x1400504e7  mov     edx, 373h
0x1400504ec  jmp     short loc_14005053F
0x1400504ee  mov     rcx, [rbp+57h+var_90]
0x1400504f2  mov     rax, [rcx]
0x1400504f5  lea     rdx, [rbp+57h+cb]
0x1400504f9  mov     rax, [rax+38h]
0x1400504fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050502  mov     ebx, eax
0x140050504  test    eax, eax
0x140050506  jns     short loc_140050512
0x140050508  mov     r9d, eax
0x14005050b  mov     edx, 374h
0x140050510  jmp     short loc_14005053F
0x140050512  cmp     dword ptr [rbp+57h+cb], 28h ; '('
0x140050516  jnb     short loc_14005051D
0x140050518  mov     ebx, r15d
0x14005051b  jmp     short loc_140050550
0x14005051d  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x140050520  call    cs:__imp_CoTaskMemAlloc
0x140050526  mov     rbx, rax
0x140050529  mov     [rbp+57h+var_68], rax
0x14005052d  test    rax, rax
0x140050530  jnz     short loc_140050563
0x140050532  mov     ebx, 8007000Eh
0x140050537  mov     r9d, ebx; char *
0x14005053a  mov     edx, 37Ch; void *
0x14005053f  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x140050546  mov     rcx, [rbp+5Fh]; this
0x14005054a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005054f  nop
0x140050550  mov     rcx, [rbp+57h+string]; string
0x140050554  call    cs:__imp_WindowsDeleteString
0x14005055a  mov     [rbp+57h+string], r15
0x14005055e  jmp     loc_14005089C
0x140050563  mov     rcx, [rbp+57h+var_80]
0x140050567  mov     [rbp+57h+var_80], r15
0x14005056b  test    rcx, rcx
0x14005056e  jz      short loc_14005057D
0x140050570  mov     rax, [rcx]
0x140050573  mov     rax, [rax+10h]
0x140050577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005057c  nop
0x14005057d  lea     rcx, [rbp+57h+hstringHeader]; string
0x140050581  call    ??$?0$0CD@@StringReference@Internal@Windows@@QEAA@AEAY0CD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[35])
0x140050586  lea     r8, [rbp+57h+var_80]
0x14005058a  lea     rdx, _GUID_11fcbfc8_f93a_471b_b121_f379e349313c
0x140050591  mov     rcx, [rax]
0x140050594  call    cs:__imp_RoGetActivationFactory
0x14005059a  mov     esi, eax
0x14005059c  test    eax, eax
0x14005059e  jns     short loc_1400505D7
0x1400505a0  mov     edx, 37Eh; void *
0x1400505a5  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x1400505ac  mov     r9d, esi; char *
0x1400505af  mov     rcx, [rbp+5Fh]; this
0x1400505b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400505b8  nop
0x1400505b9  mov     rcx, [rbp+57h+string]; string
0x1400505bd  call    cs:__imp_WindowsDeleteString
0x1400505c3  mov     [rbp+57h+string], r15
0x1400505c7  mov     rcx, rbx; pv
0x1400505ca  call    cs:__imp_CoTaskMemFree
0x1400505d0  mov     ebx, esi
0x1400505d2  jmp     loc_14005089C
0x1400505d7  mov     rsi, [rbp+57h+var_80]
0x1400505db  mov     rax, [rsi]
0x1400505de  mov     r14, [rax+30h]
0x1400505e2  mov     rcx, [rbp+57h+var_88]
0x1400505e6  mov     [rbp+57h+var_88], r15
0x1400505ea  test    rcx, rcx
0x1400505ed  jz      short loc_1400505FC
0x1400505ef  mov     rdx, [rcx]
0x1400505f2  mov     rax, [rdx+10h]
0x1400505f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400505fb  nop
0x1400505fc  lea     r8, [rbp+57h+var_88]
0x140050600  mov     rdx, [rbp+57h+var_90]
0x140050604  mov     rcx, rsi
0x140050607  mov     rax, r14
0x14005060a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005060f  mov     esi, eax
0x140050611  test    eax, eax
0x140050613  jns     short loc_14005061C
0x140050615  mov     edx, 37Fh
0x14005061a  jmp     short loc_1400505A5
0x14005061c  mov     rcx, [rbp+57h+var_88]
0x140050620  mov     rax, [rcx]
0x140050623  mov     r8, rbx
0x140050626  mov     edx, dword ptr [rbp+57h+cb]
0x140050629  mov     rax, [rax+70h]
0x14005062d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050632  mov     esi, eax
0x140050634  test    eax, eax
0x140050636  jns     short loc_140050642
0x140050638  mov     edx, 380h
0x14005063d  jmp     loc_1400505A5
0x140050642  mov     rcx, [rbp+57h+string]; string
0x140050646  call    cs:__imp_WindowsDeleteString
0x14005064c  mov     [rbp+57h+string], r15
0x140050650  movups  xmm0, xmmword ptr [rbx+10h]
0x140050654  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x140050659  lea     rdx, [rbp+57h+string]; HSTRING *
0x14005065d  lea     rcx, [rbp+57h+hstringHeader]; struct _GUID
0x140050661  call    ?GuidToHString@@YAJU_GUID@@PEAPEAUHSTRING__@@@Z; GuidToHString(_GUID,HSTRING__ * *)
0x140050666  mov     esi, eax
0x140050668  test    eax, eax
0x14005066a  jns     short loc_140050676
0x14005066c  mov     edx, 384h
0x140050671  jmp     loc_1400505A5
0x140050676  mov     rcx, [rbp+57h+var_A8]
0x14005067a  mov     [rbp+57h+var_A8], r15
0x14005067e  test    rcx, rcx
0x140050681  jz      short loc_140050690
0x140050683  mov     rax, [rcx]
0x140050686  mov     rax, [rax+10h]
0x14005068a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005068f  nop
0x140050690  lea     r9, [rbp+57h+var_A8]
0x140050694  mov     r8d, [rbx+20h]
0x140050698  mov     rdx, [rbp+57h+string]
0x14005069c  mov     rcx, rdi
0x14005069f  call    ?FindAllByIdAndInstance@AudioDeviceModulesManager@Devices@Media@Windows@@AEAAJPEAUHSTRING__@@IPEAPEAU?$IVectorView@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@4@@Z; Windows::Media::Devices::AudioDeviceModulesManager::FindAllByIdAndInstance(HSTRING__ *,uint,Windows::Foundation::Collections::IVectorView<Windows::Media::Devices::AudioDeviceModule *> * *)
0x1400506a4  mov     esi, eax
0x1400506a6  test    eax, eax
0x1400506a8  jns     short loc_1400506B4
0x1400506aa  mov     edx, 385h
0x1400506af  jmp     loc_1400505A5
0x1400506b4  mov     rcx, [rbp+57h+var_A8]
0x1400506b8  mov     rax, [rcx]
0x1400506bb  lea     rdx, [rbp+57h+var_78]
0x1400506bf  mov     rax, [rax+38h]
0x1400506c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400506c8  mov     esi, eax
0x1400506ca  test    eax, eax
0x1400506cc  jns     short loc_1400506D8
0x1400506ce  mov     edx, 389h
0x1400506d3  jmp     loc_1400505A5
0x1400506d8  cmp     [rbp+57h+var_78], 1
0x1400506dc  jz      short loc_1400506ED
0x1400506de  mov     edi, 80004005h
0x1400506e3  mov     edx, 38Ah
0x1400506e8  jmp     loc_14005086F
0x1400506ed  mov     rsi, [rbp+57h+var_A8]
0x1400506f1  mov     rax, [rsi]
0x1400506f4  mov     r14, [rax+30h]
0x1400506f8  mov     rcx, [rbp+57h+var_B0]
0x1400506fc  mov     [rbp+57h+var_B0], r15
0x140050700  test    rcx, rcx
0x140050703  jz      short loc_140050712
0x140050705  mov     rdx, [rcx]
0x140050708  mov     rax, [rdx+10h]
0x14005070c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050711  nop
0x140050712  lea     r8, [rbp+57h+var_B0]
0x140050716  xor     edx, edx
0x140050718  mov     rcx, rsi
0x14005071b  mov     rax, r14
0x14005071e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050723  mov     esi, eax
0x140050725  test    eax, eax
0x140050727  jns     short loc_140050733
0x140050729  mov     edx, 38Dh
0x14005072e  jmp     loc_1400505A5
0x140050733  cmp     [rbp+57h+var_B0], r15
0x140050737  jnz     short loc_140050748
0x140050739  mov     edi, 80004005h
0x14005073e  mov     edx, 38Eh
0x140050743  jmp     loc_14005086F
0x140050748  mov     rcx, [rbp+57h+var_A0]
0x14005074c  mov     [rbp+57h+var_A0], r15
0x140050750  test    rcx, rcx
0x140050753  jz      short loc_140050762
0x140050755  mov     rax, [rcx]
0x140050758  mov     rax, [rax+10h]
0x14005075c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050761  nop
0x140050762  mov     [rbp+57h+var_38], r15
0x140050766  mov     r9d, 22h ; '"'; unsigned int
0x14005076c  lea     r8d, [r9+1]; unsigned int
0x140050770  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x140050777  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14005077b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140050780  nop
0x140050781  lea     rdx, [rbp+57h+var_A0]
0x140050785  mov     rcx, [rbp+57h+var_38]
0x140050789  call    ??$ActivateInstance@UIDataWriter@Streams@Storage@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIDataWriter@Streams@Storage@1@@Z; Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(HSTRING__ *,Windows::Storage::Streams::IDataWriter * *)
0x14005078e  mov     esi, eax
0x140050790  test    eax, eax
0x140050792  jns     short loc_14005079E
0x140050794  mov     edx, 392h
0x140050799  jmp     loc_1400505A5
0x14005079e  mov     rcx, [rbp+57h+var_A0]
0x1400507a2  test    rcx, rcx
0x1400507a5  jz      short loc_140050814
0x1400507a7  mov     rax, [rcx]
0x1400507aa  lea     r8, [rbx+28h]
0x1400507ae  mov     edx, dword ptr [rbp+57h+cb]
0x1400507b1  add     edx, 0FFFFFFD8h
0x1400507b4  mov     rax, [rax+60h]
0x1400507b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400507bd  mov     esi, eax
0x1400507bf  test    eax, eax
0x1400507c1  jns     short loc_1400507CD
0x1400507c3  mov     edx, 396h
0x1400507c8  jmp     loc_1400505A5
0x1400507cd  mov     rsi, [rbp+57h+var_A0]
0x1400507d1  mov     rax, [rsi]
0x1400507d4  mov     r14, [rax+0F8h]
0x1400507db  mov     rcx, [rbp+57h+var_98]
0x1400507df  mov     [rbp+57h+var_98], r15
0x1400507e3  test    rcx, rcx
0x1400507e6  jz      short loc_1400507F5
0x1400507e8  mov     rdx, [rcx]
0x1400507eb  mov     rax, [rdx+10h]
0x1400507ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400507f4  nop
0x1400507f5  lea     rdx, [rbp+57h+var_98]
0x1400507f9  mov     rcx, rsi
0x1400507fc  mov     rax, r14
0x1400507ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050804  mov     esi, eax
0x140050806  test    eax, eax
0x140050808  jns     short loc_140050814
0x14005080a  mov     edx, 397h
0x14005080f  jmp     loc_1400505A5
0x140050814  mov     rax, [rbp+57h+var_98]
0x140050818  mov     [rbp+57h+var_70], rax
0x14005081c  mov     rax, [rbp+57h+var_B0]
0x140050820  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x140050824  lea     r8, [rbp+57h+var_70]
0x140050828  lea     rdx, [rbp+57h+hstringHeader]
0x14005082c  lea     rcx, [rbp+57h+var_68]
0x140050830  call    ??$Make@VAudioDeviceModuleNotificationEventArgs@Devices@Media@Windows@@PEAUIAudioDeviceModule@234@PEAUIBuffer@Streams@Storage@4@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAudioDeviceModuleNotificationEventArgs@Devices@Media@Windows@@@12@$$QEAPEAUIAudioDeviceModule@Devices@Media@Windows@@$$QEAPEAUIBuffer@Streams@Storage@7@@Z; Microsoft::WRL::Details::Make<Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs,Windows::Media::Devices::IAudioDeviceModule *,Windows::Storage::Streams::IBuffer *>(Windows::Media::Devices::IAudioDeviceModule * &&,Windows::Storage::Streams::IBuffer * &&)
0x140050835  mov     rsi, [rax]
0x140050838  mov     [rax], r15
0x14005083b  mov     [rbp+57h+var_70], rsi
0x14005083f  mov     rcx, [rbp+57h+var_68]
0x140050843  test    rcx, rcx
0x140050846  jz      short loc_140050851
0x140050848  mov     [rbp+57h+var_68], r15
0x14005084c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioDeviceModuleNotificationEventArgs@Devices@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Devices::IAudioDeviceModuleNotificationEventArgs,Microsoft::WRL::FtmBase>::Release(void)
0x140050851  lea     rcx, [rdi+50h]
0x140050855  mov     r8, rsi
0x140050858  mov     rdx, rdi
0x14005085b  call    ??$InvokeAll@PEAVAudioDeviceModulesManager@Devices@Media@Windows@@PEAVAudioDeviceModuleNotificationEventArgs@234@@?$EventSource@U?$ITypedEventHandler@PEAVAudioDeviceModulesManager@Devices@Media@Windows@@PEAVAudioDeviceModuleNotificationEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVAudioDeviceModulesManager@Devices@Media@Windows@@PEAVAudioDeviceModuleNotificationEventArgs@456@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>(Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *)
0x140050860  mov     edi, eax
0x140050862  test    eax, eax
0x140050864  jns     loc_1400508FC
0x14005086a  mov     edx, 39Eh; void *
0x14005086f  mov     r9d, edi; char *
0x140050872  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x140050879  mov     rcx, [rbp+5Fh]; this
0x14005087d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050882  nop
0x140050883  mov     rcx, [rbp+57h+string]; string
0x140050887  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
