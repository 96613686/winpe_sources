# CDSAppDataStore::GetCompatibleAppInfo(winrt::hstring)

- ea: `0x1800604f0`
- end: `0x18006068b`
- name: `?GetCompatibleAppInfo@CDSAppDataStore@@UEAA?AUCompatibleAppInfo@AppRestore@Shell@Internal@Windows@winrt@@Uhstring@7@@Z`
- size: `411`
- prototype: `struct winrt::Windows::Internal::Shell::AppRestore::CompatibleAppInfo __high(struct winrt::hstring)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18000cbbc`
- `0x180012b84`
- `0x180012c0c`
- `0x18001cf84`
- `0x1800350ac`
- `0x180035d88`
- `0x1800411a4`
- `0x1800556d4`
- `0x18005c388`
- `0x1800604f0`
- `0x1800616c4`
- `0x180062880`
- `0x180072fcc`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800605d9`
- `KERNEL32!CompareStringOrdinal` at `0x1800605d9`

## string_xrefs

- `0x18006052e`: `CDSAppDataStore_GetCompatibleAppInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall CDSAppDataStore::GetCompatibleAppInfo(
        union _RTL_RUN_ONCE *a1,
        _QWORD *a2,
        const struct winrt::hstring *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int *Ptr; // rdi
  int *i; // rsi
  const WCHAR *v10; // rax
  int v11; // edx
  LPCWCH v12; // r8
  winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo *v13; // rbx
  winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo *v15; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v17[42]; // [rsp+50h] [rbp-B0h] BYREF

  v16[0] = a2;
  v16[2] = a3;
  wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v17);
  v17[0] = &CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::`vftable';
  CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::StartActivity((CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo *)v17);
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARFIO>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ARFIO>::GetImpl'::`2'::impl,
    v6);
  wil::init_once_nothrow__lambda_d61325500fdac13b057b26824d96c668___(a1 + 25, (__int64)a1, v7);
  winrt::hstring::hstring((winrt::hstring *)v16, a3);
  winrt::hstring::hstring((winrt::hstring *)&v15, (const struct winrt::hstring *)v16);
  Ptr = (int *)a1[23].Ptr;
  for ( i = (int *)a1[22].Ptr; i != Ptr; i += 46 )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 8);
    v10 = winrt::hstring::c_str((winrt::hstring *)&v15);
    if ( CompareStringOrdinal(v10, v11, v12, i[12], 1) == 2 )
      break;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
  if ( i == a1[23].Ptr )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    *a2 = 0;
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    v13 = (winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo *)operator new(0x40u);
    v15 = v13;
    winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo::CompatibleAppInfo(
      v13,
      (const struct AppCompatInfo *)i);
    *(_QWORD *)v13 = &winrt::impl::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo>::`vftable';
    *a2 = (char *)v13 + 16;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(v16);
  CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::~CDSAppDataStore_GetCompatibleAppInfo((CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo *)v17);
  winrt::handle_type<winrt::impl::hstring_traits>::close(a3);
  return a2;
}

```

## disassembly

```asm
0x1800604f0  push    rbp
0x1800604f2  push    rbx
0x1800604f3  push    rsi
0x1800604f4  push    rdi
0x1800604f5  push    r13
0x1800604f7  push    r14
0x1800604f9  push    r15
0x1800604fb  lea     rbp, [rsp-0B0h]
0x180060503  sub     rsp, 1B0h
0x18006050a  mov     rax, cs:__security_cookie
0x180060511  xor     rax, rsp
0x180060514  mov     [rbp+0E0h+var_40], rax
0x18006051b  mov     r15, r8
0x18006051e  mov     r14, rdx
0x180060521  mov     r13, rcx
0x180060524  mov     [rsp+1E0h+var_1A8], rdx
0x180060529  mov     [rsp+1E0h+var_198], r8
0x18006052e  lea     rdx, aCdsappdatastor_5; "CDSAppDataStore_GetCompatibleAppInfo"
0x180060535  lea     rcx, [rsp+1E0h+var_190]; struct wil::details::IFailureCallback *
0x18006053a  call    ??0?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006053f  lea     rax, ??_7CDSAppDataStore_GetCompatibleAppInfo@CloudRestoreLauncherTelemetry@@6B@; const CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::`vftable'
0x180060546  mov     [rsp+1E0h+var_190], rax
0x18006054b  lea     rcx, [rsp+1E0h+var_190]; this
0x180060550  call    ?StartActivity@CDSAppDataStore_GetCompatibleAppInfo@CloudRestoreLauncherTelemetry@@QEAAXXZ; CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::StartActivity(void)
0x180060555  nop
0x180060556  mov     dl, 1
0x180060558  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ARFIO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ARFIO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARFIO> `wil::Feature<__WilFeatureTraits_Feature_ARFIO>::GetImpl(void)'::`2'::impl
0x18006055f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ARFIO@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARFIO>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180060564  lea     rcx, [r13+0C8h]; lpInitOnce
0x18006056b  mov     rdx, r13
0x18006056e  call    wil__init_once_nothrow__lambda_d61325500fdac13b057b26824d96c668___
0x180060573  mov     rdx, r15; struct winrt::hstring *
0x180060576  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18006057b  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180060580  nop
0x180060581  lea     rdx, [rsp+1E0h+var_1A8]; struct winrt::hstring *
0x180060586  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18006058b  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180060590  mov     rdi, [r13+0B8h]
0x180060597  mov     rsi, [r13+0B0h]
0x18006059e  cmp     rsi, rdi
0x1800605a1  jz      short loc_1800605F0
0x1800605a3  mov     rbx, [rsp+1E0h+var_1B0]
0x1800605a8  lea     rcx, [rsi+20h]
0x1800605ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800605b1  mov     r8, rax
0x1800605b4  test    rbx, rbx
0x1800605b7  jz      short loc_1800605BE
0x1800605b9  mov     edx, [rbx+4]
0x1800605bc  jmp     short loc_1800605C0
0x1800605be  xor     edx, edx
0x1800605c0  lea     rcx, [rsp+1E0h+var_1B0]; this
0x1800605c5  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800605ca  mov     rcx, rax; lpString1
0x1800605cd  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x1800605d5  mov     r9d, [rsi+30h]; cchCount2
0x1800605d9  call    cs:__imp_CompareStringOrdinal
0x1800605df  cmp     eax, 2
0x1800605e2  jz      short loc_1800605F0
0x1800605e4  add     rsi, 0B8h
0x1800605eb  cmp     rsi, rdi
0x1800605ee  jnz     short loc_1800605A8
0x1800605f0  lea     rcx, [rsp+1E0h+var_1B0]
0x1800605f5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800605fa  lea     rcx, [rsp+1E0h+var_190]
0x1800605ff  cmp     rsi, [r13+0B8h]
0x180060606  jz      short loc_18006063D
0x180060608  call    ?Stop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006060d  mov     ecx, 40h ; '@'; Size
0x180060612  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060617  mov     rbx, rax
0x18006061a  mov     [rsp+1E0h+var_1B0], rax
0x18006061f  mov     rdx, rsi; struct AppCompatInfo *
0x180060622  mov     rcx, rax; this
0x180060625  call    ??0CompatibleAppInfo@implementation@AppRestore@Shell@Internal@Windows@winrt@@QEAA@AEBUAppCompatInfo@Apps@Data@5@@Z; winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo::CompatibleAppInfo(Windows::Data::Apps::AppCompatInfo const &)
0x18006062a  lea     rax, ??_7?$heap_implements@UCompatibleAppInfo@implementation@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::CompatibleAppInfo>::`vftable'
0x180060631  mov     [rbx], rax
0x180060634  lea     rdx, [rbx+10h]
0x180060638  mov     [r14], rdx
0x18006063b  jmp     short loc_180060649
0x18006063d  call    ?Stop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180060642  mov     qword ptr [r14], 0
0x180060649  lea     rcx, [rsp+1E0h+var_1A8]
0x18006064e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180060653  nop
0x180060654  lea     rcx, [rsp+1E0h+var_190]; this
0x180060659  call    ??1CDSAppDataStore_GetCompatibleAppInfo@CloudRestoreLauncherTelemetry@@QEAA@XZ; CloudRestoreLauncherTelemetry::CDSAppDataStore_GetCompatibleAppInfo::~CDSAppDataStore_GetCompatibleAppInfo(void)
0x18006065e  nop
0x18006065f  mov     rcx, r15
0x180060662  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180060667  mov     rax, r14
0x18006066a  mov     rcx, [rbp+0E0h+var_40]
0x180060671  xor     rcx, rsp; StackCookie
0x180060674  call    __security_check_cookie
0x180060679  add     rsp, 1B0h
0x180060680  pop     r15
0x180060682  pop     r14
0x180060684  pop     r13
0x180060686  pop     rdi
0x180060687  pop     rsi
0x180060688  pop     rbx
0x180060689  pop     rbp
0x18006068a  retn
```
