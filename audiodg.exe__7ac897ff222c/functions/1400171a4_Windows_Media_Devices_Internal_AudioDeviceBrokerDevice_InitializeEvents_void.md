# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::InitializeEvents(void)

- ea: `0x1400171a4`
- end: `0x1400174d7`
- name: `?InitializeEvents@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140015d14`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140011e00`
- `0x140012724`
- `0x1400127bc`
- `0x140016ba8`
- `0x140016f68`
- `0x1400171a4`
- `0x140017ef8`
- `0x14001d790`
- `0x1400378e4`
- `0x14004c130`
- `0x14005d0e0`
- `0x14005e168`
- `0x140086700`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017270`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017210`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017210`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140017321`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140017321`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400172e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400172e1`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140017451`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140017451`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400173e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400173e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017281`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::InitializeEvents(RTL_SRWLOCK *pv)
{
  char *Ptr; // r14
  PVOID v3; // rcx
  int v4; // eax
  unsigned int LastError; // ebx
  int Error; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, LPVOID *); // rbx
  int v14; // eax
  HANDLE FileW; // rax
  const char *v16; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pva; // [rsp+48h] [rbp-B8h] BYREF
  char *v21; // [rsp+50h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v22; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  char *v24; // [rsp+70h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  memset_0(v23, 0, 0x1A0u);
  v21 = 0;
  Ptr = (char *)pv[14].Ptr;
  v19 = 0;
  pva = 0;
  AcquireSRWLockExclusive(pv + 25);
  v22 = pv + 25;
  v3 = pv[24].Ptr;
  pv[24].Ptr = 0;
  if ( v3 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Streams::IBuffer,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>>>(
         v3,
         &pv[24]);
  LastError = v4;
  if ( v4 >= 0 )
  {
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &pv[23],
      0);
    if ( pv[23].Ptr )
    {
      ThreadpoolWait = CreateThreadpoolWait(
                         Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::ThreadpoolCallback,
                         pv,
                         0);
      pv[22].Ptr = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        SetThreadpoolWait(ThreadpoolWait, pv[23].Ptr, 0);
        if ( (unsigned __int64)(Ptr - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v10 = v19;
          v19 = 0;
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))pv[13].Ptr)(
                  pv[13].Ptr,
                  &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
                  &v19);
          LastError = v11;
          if ( v11 < 0 )
          {
            v7 = (unsigned int)v11;
            v8 = 2150;
            goto LABEL_17;
          }
          v12 = v19;
          v13 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 32LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pva,
            0);
          v14 = v13(v12, &pva);
          LastError = v14;
          if ( v14 < 0 )
          {
            v7 = (unsigned int)v14;
            v8 = 2153;
            goto LABEL_17;
          }
          FileW = CreateFileW((LPCWSTR)pva, 0x80000000, 3u, 0, 3u, 0x800080u, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v21,
            FileW);
          Ptr = v21;
          if ( !v21 || v21 == (char *)-1LL )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x879,
                          (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
                          v16);
            goto LABEL_31;
          }
        }
        memset_0(v23, 0, 0x1A0u);
        v23[0] = 416;
        v23[2] = 1;
        v24 = Ptr;
        wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
          &pv[18],
          0);
        if ( !(unsigned int)CM_Register_Notification(
                              v23,
                              pv,
                              &Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::CMModulesNotificationCallback,
                              &pv[18]) )
        {
          LastError = 0;
          goto LABEL_31;
        }
        v8 = 2181;
      }
      else
      {
        v8 = 2141;
      }
      LastError = -2147467259;
      v7 = 2147500037LL;
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
      LastError = Error;
      if ( Error >= 0 )
      {
LABEL_31:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pva);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
        return LastError;
      }
      v7 = (unsigned int)Error;
      v8 = 2138;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
      (const char *)v7,
      dwCreationDisposition);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x857,
    (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
    (const char *)(unsigned int)v4,
    dwCreationDisposition);
  if ( pv != (RTL_SRWLOCK *)-200LL )
    ReleaseSRWLockExclusive(pv + 25);
  if ( pva )
    CoTaskMemFree(pva);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return LastError;
}

```

## disassembly

```asm
0x1400171a4  mov     [rsp-8+arg_8], rbx
0x1400171a9  mov     [rsp-8+arg_10], rsi
0x1400171ae  push    rbp
0x1400171af  push    rdi
0x1400171b0  push    r14
0x1400171b2  lea     rbp, [rsp-110h]
0x1400171ba  sub     rsp, 210h
0x1400171c1  mov     rax, cs:__security_cookie
0x1400171c8  xor     rax, rsp
0x1400171cb  mov     [rbp+120h+var_20], rax
0x1400171d2  mov     rsi, rcx
0x1400171d5  xor     edx, edx; Val
0x1400171d7  mov     r8d, 1A0h; Size
0x1400171dd  lea     rcx, [rsp+220h+var_1C0]; void *
0x1400171e2  call    memset_0
0x1400171e7  mov     [rsp+220h+var_1D0], 0
0x1400171f0  mov     r14, [rsi+70h]
0x1400171f4  mov     [rsp+220h+var_1E0], 0
0x1400171fd  mov     [rsp+220h+pv], 0
0x140017206  lea     rdi, [rsi+0C8h]
0x14001720d  mov     rcx, rdi; SRWLock
0x140017210  call    cs:__imp_AcquireSRWLockExclusive
0x140017216  mov     [rsp+220h+var_1C8], rdi
0x14001721b  lea     rbx, [rsi+0C0h]
0x140017222  mov     rcx, [rbx]
0x140017225  mov     qword ptr [rbx], 0
0x14001722c  test    rcx, rcx
0x14001722f  jz      short loc_14001723E
0x140017231  mov     rax, [rcx]
0x140017234  mov     rax, [rax+10h]
0x140017238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001723d  nop
0x14001723e  mov     rdx, rbx
0x140017241  call    ??$CreateExternalObjectVector@UIBuffer@Streams@Storage@Windows@@V?$Vector@PEAUIBuffer@Streams@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIBuffer@Streams@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIBuffer@Streams@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIBuffer@Streams@Storage@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIBuffer@Streams@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIBuffer@Streams@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIBuffer@Streams@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIBuffer@Streams@Storage@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Streams::IBuffer,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Streams::IBuffer *>> * *)
0x140017246  mov     ebx, eax
0x140017248  test    eax, eax
0x14001724a  jns     short loc_1400172A4
0x14001724c  mov     rcx, [rbp+128h]; this
0x140017253  mov     r9d, eax; char *
0x140017256  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14001725d  mov     edx, 857h; void *
0x140017262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017267  nop
0x140017268  test    rdi, rdi
0x14001726b  jz      short loc_140017277
0x14001726d  mov     rcx, rdi; SRWLock
0x140017270  call    cs:__imp_ReleaseSRWLockExclusive
0x140017276  nop
0x140017277  mov     rcx, [rsp+220h+pv]; pv
0x14001727c  test    rcx, rcx
0x14001727f  jz      short loc_140017288
0x140017281  call    cs:__imp_CoTaskMemFree
0x140017287  nop
0x140017288  mov     rcx, [rsp+220h+var_1E0]
0x14001728d  test    rcx, rcx
0x140017290  jz      short loc_14001729F
0x140017292  mov     rax, [rcx]
0x140017295  mov     rax, [rax+10h]
0x140017299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001729e  nop
0x14001729f  jmp     loc_1400174AE
0x1400172a4  lea     rbx, [rsi+0B8h]
0x1400172ab  xor     edx, edx
0x1400172ad  mov     rcx, rbx
0x1400172b0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400172b5  cmp     qword ptr [rbx], 0
0x1400172b9  jnz     short loc_1400172D4
0x1400172bb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400172c0  mov     ebx, eax
0x1400172c2  test    eax, eax
0x1400172c4  jns     loc_140017483
0x1400172ca  mov     r9d, eax
0x1400172cd  mov     edx, 85Ah
0x1400172d2  jmp     short loc_140017300
0x1400172d4  xor     r8d, r8d; pcbe
0x1400172d7  mov     rdx, rsi; pv
0x1400172da  lea     rcx, ?ThreadpoolCallback@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1400172e1  call    cs:__imp_CreateThreadpoolWait
0x1400172e7  mov     [rsi+0B0h], rax
0x1400172ee  test    rax, rax
0x1400172f1  jnz     short loc_140017318
0x1400172f3  mov     edx, 85Dh; void *
0x1400172f8  mov     ebx, 80004005h
0x1400172fd  mov     r9d, ebx; char *
0x140017300  mov     rcx, [rbp+128h]; this
0x140017307  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14001730e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017313  jmp     loc_140017483
0x140017318  xor     r8d, r8d; pftTimeout
0x14001731b  mov     rdx, [rbx]; h
0x14001731e  mov     rcx, rax; pwa
0x140017321  call    cs:__imp_SetThreadpoolWait
0x140017327  lea     rax, [r14-1]
0x14001732b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001732f  jbe     loc_140017407
0x140017335  mov     rcx, [rsp+220h+var_1E0]
0x14001733a  mov     [rsp+220h+var_1E0], 0
0x140017343  test    rcx, rcx
0x140017346  jz      short loc_140017355
0x140017348  mov     rax, [rcx]
0x14001734b  mov     rax, [rax+10h]
0x14001734f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017354  nop
0x140017355  mov     rcx, [rsi+68h]
0x140017359  mov     rax, [rcx]
0x14001735c  lea     r8, [rsp+220h+var_1E0]
0x140017361  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x140017368  mov     rax, [rax]
0x14001736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017370  mov     ebx, eax
0x140017372  test    eax, eax
0x140017374  jns     short loc_140017380
0x140017376  mov     r9d, eax
0x140017379  mov     edx, 866h
0x14001737e  jmp     short loc_140017300
0x140017380  mov     rdi, [rsp+220h+var_1E0]
0x140017385  mov     rax, [rdi]
0x140017388  mov     rbx, [rax+20h]
0x14001738c  xor     edx, edx
0x14001738e  lea     rcx, [rsp+220h+pv]
0x140017393  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140017398  lea     rdx, [rsp+220h+pv]
0x14001739d  mov     rcx, rdi
0x1400173a0  mov     rax, rbx
0x1400173a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400173a8  mov     ebx, eax
0x1400173aa  test    eax, eax
0x1400173ac  jns     short loc_1400173BB
0x1400173ae  mov     r9d, eax
0x1400173b1  mov     edx, 869h
0x1400173b6  jmp     loc_140017300
0x1400173bb  mov     [rsp+220h+hTemplateFile], 0; hTemplateFile
0x1400173c4  mov     [rsp+220h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x1400173cc  mov     r8d, 3; dwShareMode
0x1400173d2  mov     [rsp+220h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400173d7  xor     r9d, r9d; lpSecurityAttributes
0x1400173da  mov     edx, 80000000h; dwDesiredAccess
0x1400173df  mov     rcx, [rsp+220h+pv]; lpFileName
0x1400173e4  call    cs:__imp_CreateFileW
0x1400173ea  mov     rdx, rax
0x1400173ed  lea     rcx, [rsp+220h+var_1D0]
0x1400173f2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400173f7  mov     r14, [rsp+220h+var_1D0]
0x1400173fc  test    r14, r14
0x1400173ff  jz      short loc_140017469
0x140017401  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140017405  jz      short loc_140017469
0x140017407  xor     edx, edx; Val
0x140017409  mov     r8d, 1A0h; Size
0x14001740f  lea     rcx, [rsp+220h+var_1C0]; void *
0x140017414  call    memset_0
0x140017419  mov     [rsp+220h+var_1C0], 1A0h
0x140017421  mov     [rsp+220h+var_1B8], 1
0x140017429  mov     [rsp+220h+var_1B0], r14
0x14001742e  lea     rbx, [rsi+90h]
0x140017435  xor     edx, edx
0x140017437  mov     rcx, rbx
0x14001743a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x14001743f  mov     r9, rbx
0x140017442  lea     r8, ?CMModulesNotificationCallback@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::CMModulesNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x140017449  mov     rdx, rsi
0x14001744c  lea     rcx, [rsp+220h+var_1C0]
0x140017451  call    cs:__imp_CM_Register_Notification
0x140017457  test    eax, eax
0x140017459  jz      short loc_140017465
0x14001745b  mov     edx, 885h
0x140017460  jmp     loc_1400172F8
0x140017465  xor     ebx, ebx
0x140017467  jmp     short loc_140017483
0x140017469  mov     rcx, [rbp+128h]; this
0x140017470  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x140017477  mov     edx, 879h; void *
0x14001747c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140017481  mov     ebx, eax
0x140017483  lea     rcx, [rsp+220h+var_1C8]
0x140017488  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001748d  nop
0x14001748e  lea     rcx, [rsp+220h+pv]
0x140017493  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140017498  nop
0x140017499  lea     rcx, [rsp+220h+var_1E0]
0x14001749e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400174a3  nop
0x1400174a4  lea     rcx, [rsp+220h+var_1D0]
0x1400174a9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400174ae  mov     eax, ebx
0x1400174b0  mov     rcx, [rbp+120h+var_20]
0x1400174b7  xor     rcx, rsp; StackCookie
0x1400174ba  call    __security_check_cookie
0x1400174bf  lea     r11, [rsp+220h+var_10]
0x1400174c7  mov     rbx, [r11+28h]
0x1400174cb  mov     rsi, [r11+30h]
0x1400174cf  mov     rsp, r11
0x1400174d2  pop     r14
0x1400174d4  pop     rdi
0x1400174d5  pop     rbp
0x1400174d6  retn
```
