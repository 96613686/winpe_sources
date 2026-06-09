# SystemSettings::StorageSenseHandlers::CAppOperationSetting::_UninstallAppModern(HWND__ *)

- ea: `0x1800496a4`
- end: `0x1800499ac`
- name: `?_UninstallAppModern@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEAUHWND__@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180043ac0`

## callees

- `0x18000171c`
- `0x180001998`
- `0x180006e50`
- `0x18000c964`
- `0x180011280`
- `0x18001f468`
- `0x18001fe08`
- `0x180035f2c`
- `0x1800369a4`
- `0x180036d58`
- `0x18003c2c0`
- `0x18003e3e4`
- `0x1800402fc`
- `0x180044e28`
- `0x180046b50`
- `0x1800496a4`
- `0x1800a8ee4`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049908`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004976d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004976d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800498d4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800498d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::_UninstallAppModern(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this,
        HWND a2)
{
  __int64 v4; // rsi
  const WCHAR *v5; // r15
  char v6; // r12
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HSTRING *v12; // rax
  _QWORD *v13; // rax
  int v14; // ecx
  int v15; // r9d
  SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton *v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  int v18; // edi
  int v19; // r8d
  int v20; // r9d
  bool v22; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  const WCHAR *v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  __int64 v30; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v31; // [rsp+78h] [rbp-1h] BYREF

  v27 = 0;
  v25 = 0;
  v4 = 0;
  v30 = 0;
  v5 = (const WCHAR *)*((_QWORD *)this + 31);
  StringRawBuffer = v5;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&StringRawBuffer);
  string = 0;
  v6 = 0;
  v7 = *((_QWORD *)this + 31);
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v7 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(v7, &string);
  if ( v9 >= 0 )
  {
    v26 = 0;
    v22 = 1;
    SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetIsUninstallableAndToolTipMessage(
      *((SystemSettings::StorageSenseHandlers::CPackageSizeSetting **)this + 31),
      &v22,
      &v26);
    if ( !v22 )
    {
      v9 = -2147024809;
LABEL_4:
      v10 = (_QWORD *)*((_QWORD *)this + 31);
LABEL_18:
      (*(void (__fastcall **)(_QWORD *, _QWORD, __int64, HWND))(*v10 + 232LL))(v10, (unsigned int)v9, 1, a2);
      SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*((_QWORD *)this + 31), 0, 1);
      goto LABEL_21;
    }
    v9 = RoInitialize(1);
    if ( v9 >= 0 )
    {
      v6 = 1;
      LOBYTE(v11) = 1;
      SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*((_QWORD *)this + 31), v11, 1);
      v24 = v5;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v24);
      v12 = (HSTRING *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationProgressHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::IDeploymentResult____Windows::Management::Deployment::DeploymentProgress_::___Windows::Foundation::IAsyncOperationWithProgress_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress____Windows::Management::Deployment::DeploymentProgress__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationProgressHandler_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress___lambda_72a5cac1df5ce38422590f92c516ecd8___1_Windows::Foundation::IAsyncOperationWithProgress_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress____Windows::Management::Deployment::DeploymentProgress___lambda_72a5cac1df5ce38422590f92c516ecd8___(
                         &v29,
                         &v24);
      v26 = *v12;
      *v12 = 0;
      if ( v29 )
      {
        v29 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        &v30,
        &v26);
      if ( v26 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v24 )
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v24 + 16LL))(v24);
      v4 = v30;
      if ( !v30 )
      {
        v9 = -2147024882;
        goto LABEL_4;
      }
      v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                        &v31,
                        L"Windows.Management.Deployment.PackageManager");
      v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
             *v13,
             &v27);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v27 + 64LL))(v27, string, &v25);
        if ( v9 >= 0 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 48LL))(v25, v4);
          v9 = Windows::Management::Deployment::WaitForDeploymentOperation(v14, v25, 0, v15, 0);
        }
      }
    }
  }
  v10 = (_QWORD *)*((_QWORD *)this + 31);
  if ( v9 < 0 )
    goto LABEL_18;
  if ( (unsigned int)SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(v10[30]) == 32 )
    SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::ForceListRefresh(v16);
LABEL_21:
  if ( v6 )
    RoUninitialize();
  v17 = SettingsHandlersStorageSenseLogging::Provider();
  v18 = (int)v17;
  if ( *(_DWORD *)v17 > 3u && (unsigned __int8)tlgKeywordOn(v17, 0x200000000000LL) )
  {
    LODWORD(v24) = v9;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&unk_18014FE7A,
      v19,
      v20,
      (__int64)&StringRawBuffer,
      (__int64)&v24);
  }
  WindowsDeleteString(string);
  string = 0;
  if ( v5 )
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800496a4  mov     [rsp-8+arg_10], rbx
0x1800496a9  push    rbp
0x1800496aa  push    rsi
0x1800496ab  push    rdi
0x1800496ac  push    r12
0x1800496ae  push    r13
0x1800496b0  push    r14
0x1800496b2  push    r15
0x1800496b4  lea     rbp, [rsp-27h]
0x1800496b9  sub     rsp, 0A0h
0x1800496c0  mov     rax, cs:__security_cookie
0x1800496c7  xor     rax, rsp
0x1800496ca  mov     [rbp+57h+var_38], rax
0x1800496ce  mov     r13, rdx
0x1800496d1  mov     r14, rcx
0x1800496d4  xor     ebx, ebx
0x1800496d6  mov     [rbp+57h+var_78], rbx
0x1800496da  mov     [rbp+57h+var_88], rbx
0x1800496de  mov     esi, ebx
0x1800496e0  mov     [rbp+57h+var_60], rbx
0x1800496e4  mov     r15, [rcx+0F8h]
0x1800496eb  mov     [rbp+57h+var_70], r15
0x1800496ef  lea     rcx, [rbp+57h+var_70]
0x1800496f3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800496f8  nop
0x1800496f9  mov     [rbp+57h+string], rbx
0x1800496fd  mov     r12b, bl
0x180049700  mov     rdi, [r14+0F8h]
0x180049707  mov     rax, [rdi]
0x18004970a  mov     rbx, [rax+30h]
0x18004970e  xor     ecx, ecx; string
0x180049710  call    cs:__imp_WindowsDeleteString
0x180049716  mov     [rbp+57h+string], rsi
0x18004971a  lea     rdx, [rbp+57h+string]
0x18004971e  mov     rcx, rdi
0x180049721  mov     rax, rbx
0x180049724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049729  mov     ebx, eax
0x18004972b  xor     edi, edi
0x18004972d  test    eax, eax
0x18004972f  js      loc_18004987E
0x180049735  mov     [rbp+57h+var_80], rdi
0x180049739  mov     [rbp+57h+var_A0], 1
0x18004973d  lea     r8, [rbp+57h+var_80]; HSTRING *
0x180049741  lea     rdx, [rbp+57h+var_A0]; bool *
0x180049745  mov     rcx, [r14+0F8h]; this
0x18004974c  call    ?GetIsUninstallableAndToolTipMessage@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEA_NPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetIsUninstallableAndToolTipMessage(bool *,HSTRING__ * *)
0x180049751  cmp     [rbp+57h+var_A0], dil
0x180049755  jnz     short loc_180049768
0x180049757  mov     ebx, 80070057h
0x18004975c  mov     rcx, [r14+0F8h]
0x180049763  jmp     loc_180049889
0x180049768  mov     ecx, 1
0x18004976d  call    cs:__imp_RoInitialize
0x180049773  mov     ebx, eax
0x180049775  test    eax, eax
0x180049777  js      loc_18004987E
0x18004977d  mov     r12b, 1
0x180049780  mov     r8d, 1
0x180049786  mov     dl, r8b
0x180049789  mov     rcx, [r14+0F8h]
0x180049790  call    ?SetIsAppBusy@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_NW4AppOperationType@23@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(bool,SystemSettings::StorageSenseHandlers::AppOperationType)
0x180049795  mov     [rbp+57h+var_90], r15
0x180049799  lea     rcx, [rbp+57h+var_90]
0x18004979d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800497a2  lea     rdx, [rbp+57h+var_90]
0x1800497a6  lea     rcx, [rbp+57h+var_68]
0x1800497aa  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationProgressHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__IDeploymentResult____Windows__Management__Deployment__DeploymentProgress______Windows__Foundation__IAsyncOperationWithProgress_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress____Windows__Management__Deployment__DeploymentProgress____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationProgressHandler_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress___lambda_72a5cac1df5ce38422590f92c516ecd8___1_Windows__Foundation__IAsyncOperationWithProgress_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress____Windows__Management__Deployment__DeploymentProgress___lambda_72a5cac1df5ce38422590f92c516ecd8___
0x1800497af  mov     rcx, [rax]
0x1800497b2  mov     [rbp+57h+var_80], rcx
0x1800497b6  mov     [rax], rdi
0x1800497b9  mov     rcx, [rbp+57h+var_68]
0x1800497bd  test    rcx, rcx
0x1800497c0  jz      short loc_1800497CB
0x1800497c2  mov     [rbp+57h+var_68], rdi
0x1800497c6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800497cb  lea     rdx, [rbp+57h+var_80]
0x1800497cf  lea     rcx, [rbp+57h+var_60]
0x1800497d3  call    ??4?$ComPtr@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> &&)
0x1800497d8  nop
0x1800497d9  mov     rcx, [rbp+57h+var_80]
0x1800497dd  test    rcx, rcx
0x1800497e0  jz      short loc_1800497EF
0x1800497e2  mov     rax, [rcx]
0x1800497e5  mov     rax, [rax+10h]
0x1800497e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497ee  nop
0x1800497ef  mov     rcx, [rbp+57h+var_90]
0x1800497f3  test    rcx, rcx
0x1800497f6  jz      short loc_180049805
0x1800497f8  mov     rax, [rcx]
0x1800497fb  mov     rax, [rax+10h]
0x1800497ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049804  nop
0x180049805  mov     rsi, [rbp+57h+var_60]
0x180049809  test    rsi, rsi
0x18004980c  jnz     short loc_180049818
0x18004980e  mov     ebx, 8007000Eh
0x180049813  jmp     loc_18004975C
0x180049818  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18004981f  lea     rcx, [rbp+57h+var_58]; string
0x180049823  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180049828  lea     rdx, [rbp+57h+var_78]
0x18004982c  mov     rcx, [rax]
0x18004982f  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180049834  mov     ebx, eax
0x180049836  test    eax, eax
0x180049838  js      short loc_18004987E
0x18004983a  mov     rcx, [rbp+57h+var_78]
0x18004983e  mov     rax, [rcx]
0x180049841  lea     r8, [rbp+57h+var_88]
0x180049845  mov     rdx, [rbp+57h+string]
0x180049849  mov     rax, [rax+40h]
0x18004984d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049852  mov     ebx, eax
0x180049854  test    eax, eax
0x180049856  js      short loc_18004987E
0x180049858  mov     rcx, [rbp+57h+var_88]
0x18004985c  mov     rax, [rcx]
0x18004985f  mov     rdx, rsi
0x180049862  mov     rax, [rax+30h]
0x180049866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004986b  mov     [rsp+0D0h+var_B0], rdi
0x180049870  xor     r8d, r8d
0x180049873  mov     rdx, [rbp+57h+var_88]
0x180049877  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x18004987c  mov     ebx, eax
0x18004987e  mov     rcx, [r14+0F8h]
0x180049885  test    ebx, ebx
0x180049887  jns     short loc_1800498B9
0x180049889  mov     rax, [rcx]
0x18004988c  mov     r9, r13
0x18004988f  mov     r13d, 1
0x180049895  mov     r8d, r13d
0x180049898  mov     edx, ebx
0x18004989a  mov     rax, [rax+0E8h]
0x1800498a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498a6  mov     r8d, r13d
0x1800498a9  xor     edx, edx
0x1800498ab  mov     rcx, [r14+0F8h]
0x1800498b2  call    ?SetIsAppBusy@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_NW4AppOperationType@23@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(bool,SystemSettings::StorageSenseHandlers::AppOperationType)
0x1800498b7  jmp     short loc_1800498CF
0x1800498b9  mov     rcx, [rcx+0F0h]
0x1800498c0  call    ?GetPackageType@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA?AW4PackageType@StateRepository@Internal@Windows@@XZ; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(void)
0x1800498c5  cmp     eax, 20h ; ' '
0x1800498c8  jnz     short loc_1800498CF
0x1800498ca  call    ?ForceListRefresh@CAppSizesDriveSelectionSingleton@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::ForceListRefresh(void)
0x1800498cf  test    r12b, r12b
0x1800498d2  jz      short loc_1800498DA
0x1800498d4  call    cs:__imp_RoUninitialize
0x1800498da  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800498df  mov     rdi, rax
0x1800498e2  mov     ecx, [rax]
0x1800498e4  cmp     ecx, 3
0x1800498e7  jbe     short loc_180049934
0x1800498e9  mov     rdx, 200000000000h
0x1800498f3  mov     rcx, rax
0x1800498f6  call    _tlgKeywordOn
0x1800498fb  test    al, al
0x1800498fd  jz      short loc_180049934
0x1800498ff  mov     dword ptr [rbp+57h+var_90], ebx
0x180049902  xor     edx, edx; length
0x180049904  mov     rcx, [rbp+57h+string]; string
0x180049908  call    cs:__imp_WindowsGetStringRawBuffer
0x18004990e  mov     [rbp+57h+var_70], rax
0x180049912  lea     rax, [rbp+57h+var_90]
0x180049916  mov     [rsp+0D0h+var_A8], rax
0x18004991b  lea     rax, [rbp+57h+var_70]
0x18004991f  mov     [rsp+0D0h+var_B0], rax
0x180049924  lea     rdx, unk_18014FE7A
0x18004992b  mov     rcx, rdi
0x18004992e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180049933  nop
0x180049934  mov     rcx, [rbp+57h+string]; string
0x180049938  call    cs:__imp_WindowsDeleteString
0x18004993e  mov     [rbp+57h+string], 0
0x180049946  test    r15, r15
0x180049949  jz      short loc_18004995B
0x18004994b  mov     rax, [r15]
0x18004994e  mov     rcx, r15
0x180049951  mov     rax, [rax+10h]
0x180049955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004995a  nop
0x18004995b  test    rsi, rsi
0x18004995e  jz      short loc_180049970
0x180049960  mov     rax, [rsi]
0x180049963  mov     rcx, rsi
0x180049966  mov     rax, [rax+10h]
0x18004996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004996f  nop
0x180049970  lea     rcx, [rbp+57h+var_88]
0x180049974  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180049979  nop
0x18004997a  lea     rcx, [rbp+57h+var_78]
0x18004997e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180049983  mov     eax, ebx
0x180049985  mov     rcx, [rbp+57h+var_38]
0x180049989  xor     rcx, rsp; StackCookie
0x18004998c  call    __security_check_cookie
0x180049991  mov     rbx, [rsp+0D0h+arg_10]
0x180049999  add     rsp, 0A0h
0x1800499a0  pop     r15
0x1800499a2  pop     r14
0x1800499a4  pop     r13
0x1800499a6  pop     r12
0x1800499a8  pop     rdi
0x1800499a9  pop     rsi
0x1800499aa  pop     rbp
0x1800499ab  retn
```
