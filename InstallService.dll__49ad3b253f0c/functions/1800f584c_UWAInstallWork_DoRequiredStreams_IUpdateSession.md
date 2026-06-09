# UWAInstallWork::_DoRequiredStreams(IUpdateSession *)

- ea: `0x1800f584c`
- end: `0x1800f5ab5`
- name: `?_DoRequiredStreams@UWAInstallWork@@AEAAJPEAUIUpdateSession@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5020`

## callees

- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x18001c414`
- `0x18003dcd4`
- `0x180044bc0`
- `0x180044cf4`
- `0x1800ec8ec`
- `0x1800ee950`
- `0x1800f17e0`
- `0x1800f584c`
- `0x1800fba28`
- `0x1800fd054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f597f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f597f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f5a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f5a53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f5a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f5a53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f59e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f5a26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f5a45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f59e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f5a26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f5a45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f596c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f596c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f59ab`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f59ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f58b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f58c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f58b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f58c7`

## string_xrefs

- `0x1800f5904`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f58f7`: `UWAInstallWork::_DoRequiredStreams`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall UWAInstallWork::_DoRequiredStreams(UWAInstallWork *this, struct IUpdateSession *a2)
{
  bool DisableAsyncLicensing; // al
  PCWSTR StringRawBuffer; // rbx
  const unsigned __int16 *v7; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int result; // eax
  const char *v10; // r9
  bool v11; // bl
  signed int v12; // esi
  int v13; // ebx
  bool v14; // bl
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct _TP_WORK *pwk; // [rsp+90h] [rbp+18h]
  char v17; // [rsp+98h] [rbp+20h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl)
    || (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl'::`2'::impl)
      ? (DisableAsyncLicensing = GetDisableAsyncLicensing())
      : (DisableAsyncLicensing = !UWAInstallWork::_ShouldUseAsyncLicensing(this)),
        DisableAsyncLicensing) )
  {
    result = UWAInstallWork::_DoAcquireLicense(this, *((struct IUpdateCollection **)this + 13));
    if ( result >= 0 )
    {
      if ( *((_DWORD *)this + 32) == 1 )
      {
        v14 = 0;
        UWAInstallWork::SetStreamingType(this, 1);
      }
      else
      {
        v14 = 1;
      }
      return UWAInstallWork::_DoDownload(this, a2, v14);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl'::`2'::impl) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
      v7 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x8BBu,
        "UWAInstallWork::_DoRequiredStreams",
        -1,
        L"Async licensing enabled for %s",
        (const char *)this + 304,
        v7,
        StringRawBuffer);
    }
    try
    {
      wil::AcquireSRWLockExclusive(&v17, (char *)this + 1048);
      *((_DWORD *)this + 281) = -2147483638;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensingThreading>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensingThreading>::GetImpl'::`2'::impl) )
        *((_DWORD *)this + 265) = 2;
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
      ThreadpoolWork = CreateThreadpoolWork(UWAInstallWork::s_AcquireLicenseCallback, this, 0);
      pwk = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        if ( *((_DWORD *)this + 32) == 1 )
        {
          v11 = 0;
          UWAInstallWork::SetStreamingType(this, 1);
        }
        else
        {
          v11 = 1;
        }
        v12 = UWAInstallWork::_DoDownload(this, a2, v11);
        WaitForThreadpoolWorkCallbacks(pwk, 0);
        Microsoft::WRL::Wrappers::SRWLock::LockShared(&v17, (char *)this + 1048);
        v13 = *((_DWORD *)this + 281);
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v17);
        if ( v13 >= 0 )
        {
          if ( pwk )
          {
            WaitForThreadpoolWorkCallbacks(pwk, 0);
            CloseThreadpoolWork(pwk);
          }
          result = v12;
        }
        else
        {
          if ( pwk )
          {
            WaitForThreadpoolWorkCallbacks(pwk, 0);
            CloseThreadpoolWork(pwk);
          }
          result = v13;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
      }
    }
    catch ( ... )
    {
      return wil::details::in1diag3::Log_CaughtException(
               retaddr,
               (void *)0x904,
               (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
               v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f584c  mov     [rsp+arg_0], rbx
0x1800f5851  push    rsi
0x1800f5852  push    rdi
0x1800f5853  push    r14
0x1800f5855  sub     rsp, 60h
0x1800f5859  mov     rsi, rdx
0x1800f585c  mov     rdi, rcx
0x1800f585f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f5866  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(void)
0x1800f586b  test    al, al
0x1800f586d  jz      loc_1800F5A66
0x1800f5873  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f587a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(void)
0x1800f587f  test    al, al
0x1800f5881  jz      short loc_1800F588F
0x1800f5883  mov     rcx, rdi; this
0x1800f5886  call    ?_ShouldUseAsyncLicensing@UWAInstallWork@@AEBA_NXZ; UWAInstallWork::_ShouldUseAsyncLicensing(void)
0x1800f588b  xor     al, 1
0x1800f588d  jmp     short loc_1800F5894
0x1800f588f  call    ?GetDisableAsyncLicensing@@YA_NXZ; GetDisableAsyncLicensing(void)
0x1800f5894  test    al, al
0x1800f5896  jnz     loc_1800F5A66
0x1800f589c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f58a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(void)
0x1800f58a8  test    al, al
0x1800f58aa  jz      short loc_1800F5916
0x1800f58ac  xor     edx, edx; length
0x1800f58ae  mov     rcx, [rdi+1D8h]; string
0x1800f58b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f58bb  mov     rbx, rax
0x1800f58be  xor     edx, edx; length
0x1800f58c0  mov     rcx, [rdi+1D8h]; string
0x1800f58c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f58cd  lea     rcx, [rdi+130h]
0x1800f58d4  mov     [rsp+78h+var_38], rbx
0x1800f58d9  mov     [rsp+78h+var_40], rax; unsigned __int16 *
0x1800f58de  mov     [rsp+78h+var_48], rcx; char *
0x1800f58e3  lea     rax, aAsyncLicensing; "Async licensing enabled for %s"
0x1800f58ea  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800f58ef  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x1800f58f7  lea     r9, aUwainstallwork_37; "UWAInstallWork::_DoRequiredStreams"
0x1800f58fe  mov     r8d, 8BBh; unsigned int
0x1800f5904  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f590b  mov     ecx, 3; unsigned int
0x1800f5910  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f5915  nop
0x1800f5916  lea     r14, [rdi+418h]
0x1800f591d  mov     rdx, r14
0x1800f5920  lea     rcx, [rsp+78h+arg_18]
0x1800f5928  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f592d  nop
0x1800f592e  mov     dword ptr [rdi+464h], 8000000Ah
0x1800f5938  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensingThreading@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensingThreading@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensingThreading> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensingThreading>::GetImpl(void)'::`2'::impl
0x1800f593f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensingThreading@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensingThreading>::__private_IsEnabled(void)
0x1800f5944  test    al, al
0x1800f5946  jz      short loc_1800F5952
0x1800f5948  mov     dword ptr [rdi+424h], 2
0x1800f5952  lea     rcx, [rsp+78h+arg_18]; this
0x1800f595a  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f595f  xor     r8d, r8d; pcbe
0x1800f5962  mov     rdx, rdi; pv
0x1800f5965  lea     rcx, ?s_AcquireLicenseCallback@UWAInstallWork@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f596c  call    cs:__imp_CreateThreadpoolWork
0x1800f5972  mov     [rsp+78h+pwk], rax
0x1800f597a  test    rax, rax
0x1800f597d  jnz     short loc_1800F5996
0x1800f597f  call    cs:__imp_GetLastError
0x1800f5985  test    eax, eax
0x1800f5987  jle     short loc_1800F5991
0x1800f5989  movzx   eax, ax
0x1800f598c  or      eax, 80070000h
0x1800f5991  jmp     loc_1800F5AA3
0x1800f5996  lea     rcx, [rsp+78h+pwk]
0x1800f599e  mov     [rsp+78h+var_28], rcx
0x1800f59a3  mov     [rsp+78h+var_20], 1
0x1800f59a8  mov     rcx, rax; pwk
0x1800f59ab  call    cs:__imp_SubmitThreadpoolWork
0x1800f59b1  cmp     dword ptr [rdi+80h], 1
0x1800f59b8  jz      short loc_1800F59BE
0x1800f59ba  mov     bl, 1
0x1800f59bc  jmp     short loc_1800F59CF
0x1800f59be  xor     bl, bl
0x1800f59c0  xor     r8d, r8d
0x1800f59c3  lea     edx, [r8+1]
0x1800f59c7  mov     rcx, rdi
0x1800f59ca  call    ?SetStreamingType@UWAInstallWork@@QEAAXW4StreamingType@Internal@WindowsUpdate@@_K@Z; UWAInstallWork::SetStreamingType(WindowsUpdate::Internal::StreamingType,unsigned __int64)
0x1800f59cf  mov     r8b, bl; bool
0x1800f59d2  mov     rdx, rsi; struct IUpdateSession *
0x1800f59d5  mov     rcx, rdi; this
0x1800f59d8  call    ?_DoDownload@UWAInstallWork@@AEAAJPEAUIUpdateSession@@_N@Z; UWAInstallWork::_DoDownload(IUpdateSession *,bool)
0x1800f59dd  mov     esi, eax
0x1800f59df  xor     edx, edx; fCancelPendingCallbacks
0x1800f59e1  mov     rcx, [rsp+78h+pwk]; pwk
0x1800f59e9  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800f59ef  mov     rdx, r14
0x1800f59f2  lea     rcx, [rsp+78h+arg_18]
0x1800f59fa  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f59ff  mov     ebx, [rdi+464h]
0x1800f5a05  lea     rcx, [rsp+78h+arg_18]; this
0x1800f5a0d  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f5a12  nop
0x1800f5a13  mov     rcx, [rsp+78h+pwk]; pwk
0x1800f5a1b  test    ebx, ebx
0x1800f5a1d  jns     short loc_1800F5A3E
0x1800f5a1f  test    rcx, rcx
0x1800f5a22  jz      short loc_1800F5A3A
0x1800f5a24  xor     edx, edx; fCancelPendingCallbacks
0x1800f5a26  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800f5a2c  mov     rcx, [rsp+78h+pwk]; pwk
0x1800f5a34  call    cs:__imp_CloseThreadpoolWork
0x1800f5a3a  mov     eax, ebx
0x1800f5a3c  jmp     short loc_1800F5AA3
0x1800f5a3e  test    rcx, rcx
0x1800f5a41  jz      short loc_1800F5A59
0x1800f5a43  xor     edx, edx; fCancelPendingCallbacks
0x1800f5a45  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800f5a4b  mov     rcx, [rsp+78h+pwk]; pwk
0x1800f5a53  call    cs:__imp_CloseThreadpoolWork
0x1800f5a59  mov     eax, esi
0x1800f5a5b  jmp     short loc_1800F5AA3
0x1800f5a5d  mov     eax, dword ptr [rsp+78h+pwk]
0x1800f5a64  jmp     short loc_1800F5AA3
0x1800f5a66  mov     rdx, [rdi+68h]; struct IUpdateCollection *
0x1800f5a6a  mov     rcx, rdi; this
0x1800f5a6d  call    ?_DoAcquireLicense@UWAInstallWork@@AEAAJPEAUIUpdateCollection@@@Z; UWAInstallWork::_DoAcquireLicense(IUpdateCollection *)
0x1800f5a72  test    eax, eax
0x1800f5a74  js      short loc_1800F5AA3
0x1800f5a76  cmp     dword ptr [rdi+80h], 1
0x1800f5a7d  jz      short loc_1800F5A83
0x1800f5a7f  mov     bl, 1
0x1800f5a81  jmp     short loc_1800F5A94
0x1800f5a83  xor     bl, bl
0x1800f5a85  xor     r8d, r8d
0x1800f5a88  lea     edx, [r8+1]
0x1800f5a8c  mov     rcx, rdi
0x1800f5a8f  call    ?SetStreamingType@UWAInstallWork@@QEAAXW4StreamingType@Internal@WindowsUpdate@@_K@Z; UWAInstallWork::SetStreamingType(WindowsUpdate::Internal::StreamingType,unsigned __int64)
0x1800f5a94  mov     r8b, bl; bool
0x1800f5a97  mov     rdx, rsi; struct IUpdateSession *
0x1800f5a9a  mov     rcx, rdi; this
0x1800f5a9d  call    ?_DoDownload@UWAInstallWork@@AEAAJPEAUIUpdateSession@@_N@Z; UWAInstallWork::_DoDownload(IUpdateSession *,bool)
0x1800f5aa2  nop
0x1800f5aa3  mov     rbx, [rsp+78h+arg_0]
0x1800f5aab  add     rsp, 60h
0x1800f5aaf  pop     r14
0x1800f5ab1  pop     rdi
0x1800f5ab2  pop     rsi
0x1800f5ab3  retn
```
