# StorageService::RemoveAppxPackagesForCurrentUser(Windows::Management::Deployment::IPackageVolume *)

- ea: `0x18002839c`
- end: `0x1800286ec`
- name: `?RemoveAppxPackagesForCurrentUser@StorageService@@IEAAJPEAUIPackageVolume@Deployment@Management@Windows@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(StorageService *__hidden this, struct Windows::Management::Deployment::IPackageVolume *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800286f4`

## callees

- `0x180001548`
- `0x180001c80`
- `0x18000d030`
- `0x180014a00`
- `0x18001ea50`
- `0x18001eb88`
- `0x18001fb78`
- `0x18002839c`
- `0x18002c460`
- `0x18002ce44`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028449`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800285d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800285d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002846a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002846a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StorageService::RemoveAppxPackagesForCurrentUser(
        StorageService *this,
        struct Windows::Management::Deployment::IPackageVolume *a2)
{
  __int64 *v3; // rax
  int ActivationFactory; // ebx
  __int64 v5; // r9
  HSTRING v6; // rbx
  unsigned int i; // esi
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-59h]
  char v21[4]; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-45h] BYREF
  int v23; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  __int64 v26; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp-9h] BYREF
  __int64 v31; // [rsp+78h] [rbp-1h] BYREF
  __int64 v32; // [rsp+80h] [rbp+7h] BYREF
  __int64 v33; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+1Fh] BYREF

  v32 = 0;
  v33 = 0;
  v25 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v22 = 0;
  v21[0] = 0;
  v3 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[45])a2);
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
                        *v3,
                        &v32);
  if ( ActivationFactory >= 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::GetImpl'::`2'::impl) )
      goto LABEL_6;
    if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v27);
    if ( ActivationFactory >= 0 )
    {
LABEL_6:
      ActivationFactory = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageVolume *, _QWORD, __int64 *))(*(_QWORD *)a2 + 152LL))(
                            a2,
                            0,
                            &v25);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v22);
        if ( ActivationFactory >= 0 )
        {
          for ( i = 0; i < v22; ++i )
          {
            v24 = 0;
            v31 = 0;
            v8 = v25;
            v9 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
            if ( v9(v8, i, &v29) >= 0
              && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v28) >= 0
              && (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 96LL))(v28, &v24) >= 0 )
            {
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::GetImpl'::`2'::impl)
                || (v10 = v27,
                    v11 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v27 + 176LL),
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26),
                    v11(v10, v24, &v26) >= 0)
                && (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 320LL))(v26, v21) >= 0
                && !v21[0] )
              {
                if ( (*(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v32 + 64LL))(v32, v24, &v31) >= 0 )
                {
                  v15 = Windows::Management::Deployment::WaitForDeploymentOperation(v12, v31, v13, v14, v20);
                  if ( (unsigned int)dword_1800BF000 > 5 )
                  {
                    v23 = v15;
                    StringRawBuffer = WindowsGetStringRawBuffer(v24, 0);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                      (__int64)&dword_1800BF000,
                      (__int64)byte_1800A5A99,
                      0,
                      v16,
                      &StringRawBuffer,
                      (__int64)&v23);
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
            Windows::Internal::String::~String((Windows::Internal::String *)&v24);
          }
          ActivationFactory = 0;
        }
      }
    }
  }
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    v23 = ActivationFactory;
    LODWORD(StringRawBuffer) = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BF000,
      (__int64)byte_1800A5AD1,
      0,
      v5,
      (__int64)&StringRawBuffer,
      (__int64)&v23);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  v17 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  v18 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002839c  mov     [rsp-8+arg_0], rbx
0x1800283a1  mov     [rsp-8+arg_10], rsi
0x1800283a6  push    rbp
0x1800283a7  push    rdi
0x1800283a8  push    r14
0x1800283aa  lea     rbp, [rsp-47h]
0x1800283af  sub     rsp, 0C0h
0x1800283b6  mov     rax, cs:__security_cookie
0x1800283bd  xor     rax, rsp
0x1800283c0  mov     [rbp+57h+var_20], rax
0x1800283c4  mov     rdi, rdx
0x1800283c7  xor     r14d, r14d
0x1800283ca  mov     [rbp+57h+var_50], r14
0x1800283ce  mov     [rbp+57h+var_48], r14
0x1800283d2  mov     [rbp+57h+var_88], r14
0x1800283d6  mov     [rbp+57h+var_68], r14
0x1800283da  mov     [rbp+57h+var_70], r14
0x1800283de  mov     [rbp+57h+var_78], r14
0x1800283e2  mov     [rbp+57h+var_80], r14
0x1800283e6  mov     [rbp+57h+var_9C], r14d
0x1800283ea  mov     [rbp+57h+var_A0], r14b
0x1800283ee  lea     rcx, [rbp+57h+string]; string
0x1800283f2  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800283f7  lea     rdx, [rbp+57h+var_50]
0x1800283fb  mov     rcx, [rax]
0x1800283fe  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180028403  mov     ebx, eax
0x180028405  test    eax, eax
0x180028407  js      loc_180028624
0x18002840d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix> `wil::Feature<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::GetImpl(void)'::`2'::impl
0x180028414  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::__private_IsEnabled(void)
0x180028419  test    al, al
0x18002841b  jz      short loc_18002847A
0x18002841d  lea     r9, [rbp+57h+string]; string
0x180028421  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180028425  lea     edx, [r14+28h]; length
0x180028429  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180028430  call    cs:__imp_WindowsCreateStringReference
0x180028436  test    eax, eax
0x180028438  jns     short loc_18002844F
0x18002843a  xor     r9d, r9d; lpArguments
0x18002843d  xor     r8d, r8d; nNumberOfArguments
0x180028440  lea     edx, [r14+1]; dwExceptionFlags
0x180028444  mov     ecx, 0C000000Dh; dwExceptionCode
0x180028449  call    cs:__imp_RaiseException
0x18002844f  mov     rbx, [rbp+57h+string]
0x180028453  lea     rcx, [rbp+57h+var_78]
0x180028457  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002845c  lea     r8, [rbp+57h+var_78]
0x180028460  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180028467  mov     rcx, rbx
0x18002846a  call    cs:__imp_RoGetActivationFactory
0x180028470  mov     ebx, eax
0x180028472  test    eax, eax
0x180028474  js      loc_180028624
0x18002847a  mov     rax, [rdi]
0x18002847d  lea     r8, [rbp+57h+var_88]
0x180028481  xor     edx, edx
0x180028483  mov     rcx, rdi
0x180028486  mov     rax, [rax+98h]
0x18002848d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028492  mov     ebx, eax
0x180028494  test    eax, eax
0x180028496  js      loc_180028624
0x18002849c  mov     rcx, [rbp+57h+var_88]
0x1800284a0  mov     rax, [rcx]
0x1800284a3  lea     rdx, [rbp+57h+var_9C]
0x1800284a7  mov     rax, [rax+38h]
0x1800284ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284b0  mov     ebx, eax
0x1800284b2  test    eax, eax
0x1800284b4  js      loc_180028624
0x1800284ba  mov     esi, r14d
0x1800284bd  cmp     [rbp+57h+var_9C], r14d
0x1800284c1  jbe     loc_180028621
0x1800284c7  mov     [rbp+57h+var_90], r14
0x1800284cb  mov     [rbp+57h+var_58], r14
0x1800284cf  mov     rdi, [rbp+57h+var_88]
0x1800284d3  mov     rax, [rdi]
0x1800284d6  mov     rbx, [rax+30h]
0x1800284da  lea     rcx, [rbp+57h+var_68]
0x1800284de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800284e3  lea     r8, [rbp+57h+var_68]
0x1800284e7  mov     edx, esi
0x1800284e9  mov     rcx, rdi
0x1800284ec  mov     rax, rbx
0x1800284ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284f4  test    eax, eax
0x1800284f6  js      loc_180028603
0x1800284fc  mov     rcx, [rbp+57h+var_68]
0x180028500  mov     rax, [rcx]
0x180028503  lea     rdx, [rbp+57h+var_70]
0x180028507  mov     rax, [rax+30h]
0x18002850b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028510  test    eax, eax
0x180028512  js      loc_180028603
0x180028518  mov     rcx, [rbp+57h+var_70]
0x18002851c  mov     rax, [rcx]
0x18002851f  lea     rdx, [rbp+57h+var_90]
0x180028523  mov     rax, [rax+60h]
0x180028527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852c  test    eax, eax
0x18002852e  js      loc_180028603
0x180028534  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix> `wil::Feature<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::GetImpl(void)'::`2'::impl
0x18002853b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XboxMsixvcAppxRemovalFix>::__private_IsEnabled(void)
0x180028540  test    al, al
0x180028542  jz      short loc_180028597
0x180028544  mov     rdi, [rbp+57h+var_78]
0x180028548  mov     rax, [rdi]
0x18002854b  mov     rbx, [rax+0B0h]
0x180028552  lea     rcx, [rbp+57h+var_80]
0x180028556  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002855b  lea     r8, [rbp+57h+var_80]
0x18002855f  mov     rdx, [rbp+57h+var_90]
0x180028563  mov     rcx, rdi
0x180028566  mov     rax, rbx
0x180028569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002856e  test    eax, eax
0x180028570  js      loc_180028603
0x180028576  mov     rcx, [rbp+57h+var_80]
0x18002857a  mov     rax, [rcx]
0x18002857d  lea     rdx, [rbp+57h+var_A0]
0x180028581  mov     rax, [rax+140h]
0x180028588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002858d  test    eax, eax
0x18002858f  js      short loc_180028603
0x180028591  cmp     [rbp+57h+var_A0], r14b
0x180028595  jnz     short loc_180028603
0x180028597  mov     rcx, [rbp+57h+var_50]
0x18002859b  mov     rax, [rcx]
0x18002859e  lea     r8, [rbp+57h+var_58]
0x1800285a2  mov     rdx, [rbp+57h+var_90]
0x1800285a6  mov     rax, [rax+40h]
0x1800285aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285af  test    eax, eax
0x1800285b1  js      short loc_180028603
0x1800285b3  mov     rdx, [rbp+57h+var_58]
0x1800285b7  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x1800285bc  mov     ecx, cs:dword_1800BF000
0x1800285c2  cmp     ecx, 5
0x1800285c5  jbe     short loc_180028603
0x1800285c7  mov     [rbp+57h+var_98], eax
0x1800285ca  xor     edx, edx; length
0x1800285cc  mov     rcx, [rbp+57h+var_90]; string
0x1800285d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800285d6  mov     [rbp+57h+var_60], rax
0x1800285da  lea     rax, [rbp+57h+var_98]
0x1800285de  mov     [rsp+0D0h+var_A8], rax
0x1800285e3  lea     rax, [rbp+57h+var_60]
0x1800285e7  mov     [rsp+0D0h+var_B0], rax
0x1800285ec  xor     r8d, r8d
0x1800285ef  lea     rdx, byte_1800A5A99
0x1800285f6  lea     rcx, dword_1800BF000
0x1800285fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180028602  nop
0x180028603  lea     rcx, [rbp+57h+var_58]
0x180028607  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002860c  nop
0x18002860d  lea     rcx, [rbp+57h+var_90]; this
0x180028611  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180028616  inc     esi
0x180028618  cmp     esi, [rbp+57h+var_9C]
0x18002861b  jb      loc_1800284C7
0x180028621  mov     ebx, r14d
0x180028624  mov     eax, cs:dword_1800BF000
0x18002862a  cmp     eax, 5
0x18002862d  jbe     short loc_180028661
0x18002862f  mov     [rbp+57h+var_98], ebx
0x180028632  mov     eax, [rbp+57h+var_9C]
0x180028635  mov     dword ptr [rbp+57h+var_60], eax
0x180028638  lea     rax, [rbp+57h+var_98]
0x18002863c  mov     [rsp+0D0h+var_A8], rax
0x180028641  lea     rax, [rbp+57h+var_60]
0x180028645  mov     [rsp+0D0h+var_B0], rax
0x18002864a  xor     r8d, r8d
0x18002864d  lea     rdx, byte_1800A5AD1
0x180028654  lea     rcx, dword_1800BF000
0x18002865b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180028660  nop
0x180028661  lea     rcx, [rbp+57h+var_80]
0x180028665  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002866a  nop
0x18002866b  lea     rcx, [rbp+57h+var_78]
0x18002866f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028674  nop
0x180028675  mov     rcx, [rbp+57h+var_70]
0x180028679  test    rcx, rcx
0x18002867c  jz      short loc_18002868F
0x18002867e  mov     [rbp+57h+var_70], r14
0x180028682  mov     rax, [rcx]
0x180028685  mov     rax, [rax+10h]
0x180028689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868e  nop
0x18002868f  lea     rcx, [rbp+57h+var_68]
0x180028693  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028698  nop
0x180028699  mov     rcx, [rbp+57h+var_88]
0x18002869d  test    rcx, rcx
0x1800286a0  jz      short loc_1800286B3
0x1800286a2  mov     [rbp+57h+var_88], r14
0x1800286a6  mov     rax, [rcx]
0x1800286a9  mov     rax, [rax+10h]
0x1800286ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286b2  nop
0x1800286b3  lea     rcx, [rbp+57h+var_48]
0x1800286b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800286bc  nop
0x1800286bd  lea     rcx, [rbp+57h+var_50]
0x1800286c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800286c6  mov     eax, ebx
0x1800286c8  mov     rcx, [rbp+57h+var_20]
0x1800286cc  xor     rcx, rsp; StackCookie
0x1800286cf  call    __security_check_cookie
0x1800286d4  lea     r11, [rsp+0D0h+var_10]
0x1800286dc  mov     rbx, [r11+20h]
0x1800286e0  mov     rsi, [r11+30h]
0x1800286e4  mov     rsp, r11
0x1800286e7  pop     r14
0x1800286e9  pop     rdi
0x1800286ea  pop     rbp
0x1800286eb  retn
```
