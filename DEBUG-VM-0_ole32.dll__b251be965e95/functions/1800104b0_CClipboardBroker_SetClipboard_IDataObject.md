# CClipboardBroker::SetClipboard(IDataObject *)

- ea: `0x1800104b0`
- end: `0x18001089b`
- name: `?SetClipboard@CClipboardBroker@@UEAAJPEAUIDataObject@@@Z`
- size: `1003`
- prototype: `HRESULT __fastcall(CClipboardBroker *this, IDataObject *pDataObject)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a0e8`
- `0x18000f900`
- `0x1800104b0`
- `0x180010afc`
- `0x180010fb0`
- `0x18001933c`
- `0x180019454`
- `0x180036370`
- `0x180036d78`
- `0x1800393d0`
- `0x180040a6c`
- `0x180047080`
- `0x180052390`
- `0x180053014`
- `0x18008e4d0`
- `0x18008e50c`
- `0x18008e908`
- `0x18008e988`
- `0x18008edb0`
- `0x18008ef50`
- `0x18008fd68`
- `0x18008ffac`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x1800105d4`
- `KERNELBASE!GetPackageFullName` at `0x1800105d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106a9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001060d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001060d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010688`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010843`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180010657`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180010657`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800107cf`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800107cf`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180010588`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180010588`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010815`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010815`

## pseudocode

```c
__int64 __fastcall CClipboardBroker::SetClipboard(CClipboardBroker *this, IDataObject *pDataObject)
{
  AppModelPolicy_PolicyValue v3; // esi
  HRESULT v4; // edi
  bool v5; // r15
  LONG PackageFullName; // eax
  HRESULT v7; // ebx
  Windows::Internal::GitPtr_vtbl *v8; // rcx
  Windows::Internal::GitPtr_vtbl *v9; // rbx
  AppModelPolicy_Type v10; // edx
  HRESULT Policy; // eax
  signed int LastError; // eax
  Windows::Internal::Details::Git *v13; // rcx
  Windows::Internal::Details::Git *v14; // rcx
  const wchar_t *v15; // rbx
  IDataObject *ptr; // rcx
  bool fPlmManaged; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int dwSourceProcessId; // [rsp+34h] [rbp-CCh] BYREF
  Windows::Internal::GitPtr GITWrappedDataObject; // [rsp+38h] [rbp-C8h] BYREF
  Windows::Internal::GitPtr GITSourceDataObject; // [rsp+48h] [rbp-B8h] BYREF
  int fAllowed; // [rsp+58h] [rbp-A8h] BYREF
  AppModelPolicy_PolicyValue lifecyclePolicy; // [rsp+5Ch] [rbp-A4h] BYREF
  void *pMTAWrapperRawAddress; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::WRL::ComPtr<IDataObject> pWrappedDataObjectSTAProxy; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFullNameLength; // [rsp+70h] [rbp-90h] BYREF
  void *hCallerToken; // [rsp+78h] [rbp-88h] BYREF
  CClipboardBroker::SetClipboard::__l34::<lambda_be18d0e1c9460e7bb92c1a447c19d4fe> v28; // [rsp+80h] [rbp-80h] BYREF
  wchar_t packagedProcessName[128]; // [rsp+B0h] [rbp-50h] BYREF

  hCallerToken = 0;
  memset_0(packagedProcessName, 0, sizeof(packagedProcessName));
  v3 = AppModelPolicy_LifecycleManager_Unmanaged;
  fPlmManaged = 0;
  lifecyclePolicy = AppModelPolicy_LifecycleManager_Unmanaged;
  dwSourceProcessId = 0;
  pWrappedDataObjectSTAProxy.ptr_ = 0;
  pMTAWrapperRawAddress = 0;
  fAllowed = 0;
  v4 = OleCheckClipboardCallerIntegrityLevel();
  if ( v4 >= 0 )
  {
    v4 = OleCheckCallerForClipboardAccess(&fAllowed);
    if ( v4 >= 0 )
    {
      if ( fAllowed )
      {
        dwSourceProcessId = 0;
        v5 = 0;
        packagedProcessName[0] = 0;
        GITSourceDataObject.__vftable = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&GITSourceDataObject);
        v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, (void **)&GITSourceDataObject.__vftable);
        if ( v4 >= 0 )
        {
          GITWrappedDataObject.__vftable = 0;
          v4 = (*((__int64 (__fastcall **)(Windows::Internal::GitPtr_vtbl *, __int64, Windows::Internal::GitPtr *))GITSourceDataObject.~Windows::Internal::GitPtr
                + 3))(
                 GITSourceDataObject.__vftable,
                 1024,
                 &GITWrappedDataObject);
          if ( v4 >= 0 )
          {
            packageFullNameLength = 128;
            PackageFullName = GetPackageFullName(
                                GITWrappedDataObject.__vftable,
                                &packageFullNameLength,
                                packagedProcessName);
            v7 = PackageFullName;
            if ( !PackageFullName || PackageFullName == 15700 )
            {
              dwSourceProcessId = GetProcessId(GITWrappedDataObject.__vftable);
              v5 = v7 == 0;
            }
            else
            {
              if ( PackageFullName <= 0 )
              {
                v4 = PackageFullName;
              }
              else
              {
                v4 = (unsigned __int16)PackageFullName | 0x80070000;
                v7 = v4;
              }
              OleInternalOriginateError(v7, 0x12Du);
            }
            CloseHandle(GITWrappedDataObject.__vftable);
          }
        }
        v8 = GITSourceDataObject.__vftable;
        if ( GITSourceDataObject.__vftable )
        {
          GITSourceDataObject.__vftable = 0;
          (*((void (__fastcall **)(Windows::Internal::GitPtr_vtbl *))v8->~Windows::Internal::GitPtr + 2))(v8);
        }
        if ( v4 >= 0 )
        {
          GITSourceDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)OpenProcess(0x400u, 0, dwSourceProcessId);
          v9 = GITSourceDataObject.__vftable;
          if ( GITSourceDataObject.__vftable )
          {
            GITWrappedDataObject.__vftable = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITWrappedDataObject,
              0);
            if ( OpenProcessToken(v9, 8u, (PHANDLE)&GITWrappedDataObject.__vftable) )
            {
              Policy = AppModelPolicy_GetPolicy(GITWrappedDataObject.__vftable, v10, &lifecyclePolicy);
              v3 = lifecyclePolicy;
              v4 = Policy;
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError > 0 )
                v4 = (unsigned __int16)LastError | 0x80070000;
              OleInternalOriginateError(v4, 0x13Bu);
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITWrappedDataObject);
          }
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&GITSourceDataObject);
          if ( v4 >= 0 )
          {
            if ( v3 == AppModelPolicy_LifecycleManager_ManagedByPLM )
              fPlmManaged = 1;
            v4 = CaptureCallerToken(&hCallerToken);
            if ( v4 >= 0 )
            {
              if ( !pDataObject )
                goto LABEL_34;
              GITSourceDataObject._cookie = 0;
              GITSourceDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              GITSourceDataObject._hrInitGit = Windows::Internal::Details::Git::Acquire(v13);
              GITSourceDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              GITWrappedDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              GITWrappedDataObject._cookie = 0;
              GITWrappedDataObject._hrInitGit = Windows::Internal::Details::Git::Acquire(v14);
              GITWrappedDataObject.__vftable = (Windows::Internal::GitPtr_vtbl *)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
              v4 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IDataObject>(
                     &GITSourceDataObject,
                     pDataObject);
              if ( v4 >= 0 )
              {
                v28.GITSourceDataObject = &GITSourceDataObject;
                v28.hCallerToken = &hCallerToken;
                v28.GITWrappedDataObject = &GITWrappedDataObject;
                v28.pMTAWrapperRawAddress = &pMTAWrapperRawAddress;
                v28.dwSourceProcessId = &dwSourceProcessId;
                v28.fPlmManaged = &fPlmManaged;
                v4 = RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(&v28);
                if ( v4 >= 0 )
                  v4 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IDataObject>(
                         &GITWrappedDataObject,
                         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDataObject> >)&pWrappedDataObjectSTAProxy);
              }
              Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(&GITWrappedDataObject);
              Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(&GITSourceDataObject);
              if ( v4 >= 0 )
              {
LABEL_34:
                v4 = CoImpersonateClient();
                if ( v4 >= 0 )
                {
                  v15 = (const wchar_t *)((unsigned __int64)packagedProcessName & -(__int64)v5);
                  v4 = OleSetClipboardInternal(
                         pWrappedDataObjectSTAProxy.ptr_,
                         pDataObject,
                         &pMTAWrapperRawAddress,
                         v15,
                         dwSourceProcessId);
                  OleFlushClipboardInternal(v15, 1, 1);
                  CoRevertToSelf();
                  if ( v4 >= 0 )
                    MoniterBrokeredClipboardOwner(dwSourceProcessId);
                }
              }
            }
          }
        }
      }
      else
      {
        v4 = -2147024891;
        OleInternalOriginateError(-2147024891, 0x131u);
      }
    }
  }
  if ( pMTAWrapperRawAddress )
    RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>((CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5>)&pMTAWrapperRawAddress);
  if ( hCallerToken )
    CloseHandle(hCallerToken);
  OleClipboardTracing::CClipboardBroker_SetClipboardEtw(v4, pDataObject);
  ptr = pWrappedDataObjectSTAProxy.ptr_;
  if ( pWrappedDataObjectSTAProxy.ptr_ )
  {
    pWrappedDataObjectSTAProxy.ptr_ = 0;
    ((void (__fastcall *)(IDataObject *))ptr->lpVtbl->Release)(ptr);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800104b0  mov     [rsp-8+arg_0], rbx
0x1800104b5  mov     [rsp-8+arg_10], rsi
0x1800104ba  push    rbp
0x1800104bb  push    rdi
0x1800104bc  push    r12
0x1800104be  push    r14
0x1800104c0  push    r15
0x1800104c2  lea     rbp, [rsp-0C0h]
0x1800104ca  sub     rsp, 1C0h
0x1800104d1  mov     rax, cs:__security_cookie
0x1800104d8  xor     rax, rsp
0x1800104db  mov     [rbp+0E0h+var_30], rax
0x1800104e2  mov     r14, pDataObject
0x1800104e5  lea     this, [rbp+0E0h+packagedProcessName]; void *
0x1800104e9  xor     r12d, r12d
0x1800104ec  xor     edx, edx; Val
0x1800104ee  mov     r8d, 100h; Size
0x1800104f4  mov     [rsp+1E0h+hCallerToken], r12
0x1800104f9  call    memset_0
0x1800104fe  mov     esi, 10000h
0x180010503  mov     [rsp+1E0h+fPlmManaged], r12b
0x180010508  mov     [rsp+1E0h+lifecyclePolicy], esi
0x18001050c  mov     [rsp+1E0h+dwSourceProcessId], r12d
0x180010511  mov     [rsp+1E0h+pWrappedDataObjectSTAProxy.ptr_], r12
0x180010516  mov     [rsp+1E0h+pMTAWrapperRawAddress], r12
0x18001051b  mov     [rsp+1E0h+fAllowed], r12d
0x180010520  call    ?OleCheckClipboardCallerIntegrityLevel@@YAJXZ; OleCheckClipboardCallerIntegrityLevel(void)
0x180010525  mov     edi, eax
0x180010527  test    eax, eax
0x180010529  js      loc_180010828
0x18001052f  lea     this, [rsp+1E0h+fAllowed]; pfAllowed
0x180010534  call    ?OleCheckCallerForClipboardAccess@@YAJPEAH@Z; OleCheckCallerForClipboardAccess(int *)
0x180010539  mov     edi, eax
0x18001053b  test    eax, eax
0x18001053d  js      loc_180010828
0x180010543  cmp     [rsp+1E0h+fAllowed], r12d
0x180010548  jnz     short loc_180010560
0x18001054a  mov     edi, 80070005h
0x18001054f  mov     edx, 131h; messageID
0x180010554  mov     ecx, edi; hr
0x180010556  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001055b  jmp     loc_180010828
0x180010560  lea     this, [rsp+1E0h+GITSourceDataObject]; this
0x180010565  mov     [rsp+1E0h+dwSourceProcessId], r12d
0x18001056a  mov     r15b, r12b
0x18001056d  mov     [rbp+0E0h+packagedProcessName], r12w
0x180010572  mov     [rsp+1E0h+GITSourceDataObject.__vftable], r12
0x180010577  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001057c  lea     pDataObject, [rsp+1E0h+GITSourceDataObject]; ppInterface
0x180010581  lea     this, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180010588  call    cs:__imp_CoGetCallContext
0x18001058e  mov     edi, eax
0x180010590  test    eax, eax
0x180010592  js      loc_180010628
0x180010598  mov     this, [rsp+1E0h+GITSourceDataObject.__vftable]
0x18001059d  lea     r8, [rsp+1E0h+GITWrappedDataObject]
0x1800105a2  mov     [rsp+1E0h+GITWrappedDataObject.__vftable], r12
0x1800105a7  mov     edx, 400h
0x1800105ac  mov     rax, [this]
0x1800105af  mov     rax, [rax+18h]
0x1800105b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b8  mov     edi, eax
0x1800105ba  test    eax, eax
0x1800105bc  js      short loc_180010628
0x1800105be  mov     this, [rsp+1E0h+GITWrappedDataObject.__vftable]; hProcess
0x1800105c3  lea     r8, [rbp+0E0h+packagedProcessName]; packageFullName
0x1800105c7  lea     pDataObject, [rsp+1E0h+packageFullNameLength]; packageFullNameLength
0x1800105cc  mov     [rsp+1E0h+packageFullNameLength], 80h
0x1800105d4  call    cs:__imp_GetPackageFullName
0x1800105da  mov     ebx, eax
0x1800105dc  test    eax, eax
0x1800105de  jz      short loc_180010608
0x1800105e0  cmp     eax, 3D54h
0x1800105e5  jz      short loc_180010608
0x1800105e7  test    eax, eax
0x1800105e9  jle     short loc_1800105F8
0x1800105eb  movzx   edi, bx
0x1800105ee  or      edi, 80070000h
0x1800105f4  mov     ebx, edi
0x1800105f6  jmp     short loc_1800105FA
0x1800105f8  mov     edi, ebx
0x1800105fa  mov     edx, 12Dh; messageID
0x1800105ff  mov     ecx, ebx; hr
0x180010601  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180010606  jmp     short loc_18001061D
0x180010608  mov     this, [rsp+1E0h+GITWrappedDataObject.__vftable]; Process
0x18001060d  call    cs:__imp_GetProcessId
0x180010613  test    ebx, ebx
0x180010615  mov     [rsp+1E0h+dwSourceProcessId], eax
0x180010619  setz    r15b
0x18001061d  mov     this, [rsp+1E0h+GITWrappedDataObject.__vftable]; hObject
0x180010622  call    cs:__imp_CloseHandle
0x180010628  mov     this, [rsp+1E0h+GITSourceDataObject.__vftable]
0x18001062d  test    this, this
0x180010630  jz      short loc_180010643
0x180010632  mov     [rsp+1E0h+GITSourceDataObject.__vftable], r12
0x180010637  mov     rax, [this]
0x18001063a  mov     rax, [rax+10h]
0x18001063e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010643  test    edi, edi
0x180010645  js      loc_180010828
0x18001064b  mov     r8d, [rsp+1E0h+dwSourceProcessId]; dwProcessId
0x180010650  xor     edx, edx; bInheritHandle
0x180010652  mov     ecx, 400h; dwDesiredAccess
0x180010657  call    cs:__imp_OpenProcess
0x18001065d  mov     [rsp+1E0h+GITSourceDataObject.__vftable], rax
0x180010662  mov     rbx, rax
0x180010665  test    rax, rax
0x180010668  jz      short loc_1800106D4
0x18001066a  xor     edx, edx; ptr
0x18001066c  mov     [rsp+1E0h+GITWrappedDataObject.__vftable], r12
0x180010671  lea     this, [rsp+1E0h+GITWrappedDataObject]; this
0x180010676  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001067b  lea     r8, [rsp+1E0h+GITWrappedDataObject]; TokenHandle
0x180010680  mov     edx, 8; DesiredAccess
0x180010685  mov     this, rbx; ProcessHandle
0x180010688  call    cs:__imp_OpenProcessToken
0x18001068e  test    eax, eax
0x180010690  jz      short loc_1800106A9
0x180010692  mov     this, [rsp+1E0h+GITWrappedDataObject.__vftable]; token
0x180010697  lea     r8, [rsp+1E0h+lifecyclePolicy]; token
0x18001069c  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x1800106a1  mov     esi, [rsp+1E0h+lifecyclePolicy]
0x1800106a5  mov     edi, eax
0x1800106a7  jmp     short loc_1800106CA
0x1800106a9  call    cs:__imp_GetLastError
0x1800106af  mov     edi, eax
0x1800106b1  test    eax, eax
0x1800106b3  jle     short loc_1800106BE
0x1800106b5  movzx   edi, ax
0x1800106b8  or      edi, 80070000h
0x1800106be  mov     edx, 13Bh; messageID
0x1800106c3  mov     ecx, edi; hr
0x1800106c5  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800106ca  lea     this, [rsp+1E0h+GITWrappedDataObject]; this
0x1800106cf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800106d4  lea     this, [rsp+1E0h+GITSourceDataObject]; this
0x1800106d9  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800106de  test    edi, edi
0x1800106e0  js      loc_180010828
0x1800106e6  cmp     esi, 10001h
0x1800106ec  jnz     short loc_1800106F3
0x1800106ee  mov     [rsp+1E0h+fPlmManaged], 1
0x1800106f3  lea     this, [rsp+1E0h+hCallerToken]; phToken
0x1800106f8  call    ?CaptureCallerToken@@YAJPEAPEAX@Z; CaptureCallerToken(void * *)
0x1800106fd  mov     edi, eax
0x1800106ff  test    eax, eax
0x180010701  js      loc_180010828
0x180010707  test    r14, r14
0x18001070a  jz      loc_1800107CF
0x180010710  lea     rdi, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x180010717  mov     [rsp+1E0h+GITSourceDataObject._cookie], r12d
0x18001071c  mov     [rsp+1E0h+GITSourceDataObject.__vftable], rdi
0x180010721  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x180010726  lea     rbx, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18001072d  mov     [rsp+1E0h+GITSourceDataObject._hrInitGit], eax
0x180010731  mov     [rsp+1E0h+GITSourceDataObject.__vftable], rbx
0x180010736  mov     [rsp+1E0h+GITWrappedDataObject.__vftable], rdi
0x18001073b  mov     [rsp+1E0h+GITWrappedDataObject._cookie], r12d
0x180010740  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x180010745  mov     pDataObject, r14; ptr
0x180010748  mov     [rsp+1E0h+GITWrappedDataObject._hrInitGit], eax
0x18001074c  lea     this, [rsp+1E0h+GITSourceDataObject]; this
0x180010751  mov     [rsp+1E0h+GITWrappedDataObject.__vftable], rbx
0x180010756  call    ??$Initialize@UIDataObject@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJPEAUIDataObject@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IDataObject>(IDataObject *)
0x18001075b  mov     edi, eax
0x18001075d  test    eax, eax
0x18001075f  js      short loc_1800107B7
0x180010761  lea     rax, [rsp+1E0h+GITSourceDataObject]
0x180010766  mov     [rbp+0E0h+var_160], rax
0x18001076a  lea     this, [rbp+0E0h+var_160]
0x18001076e  lea     rax, [rsp+1E0h+hCallerToken]
0x180010773  mov     [rbp+0E0h+var_158], rax
0x180010777  lea     rax, [rsp+1E0h+GITWrappedDataObject]
0x18001077c  mov     [rbp+0E0h+var_150], rax
0x180010780  lea     rax, [rsp+1E0h+pMTAWrapperRawAddress]
0x180010785  mov     [rbp+0E0h+var_148], rax
0x180010789  lea     rax, [rsp+1E0h+dwSourceProcessId]
0x18001078e  mov     [rbp+0E0h+var_140], rax
0x180010792  lea     rax, [rsp+1E0h+fPlmManaged]
0x180010797  mov     [rbp+0E0h+var_138], rax
0x18001079b  call    ??$RunSyncOnMTAThread@V_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@@YAJV_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@Z; RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_)
0x1800107a0  mov     edi, eax
0x1800107a2  test    eax, eax
0x1800107a4  js      short loc_1800107B7
0x1800107a6  lea     pDataObject, [rsp+1E0h+pWrappedDataObjectSTAProxy]; ptr
0x1800107ab  lea     this, [rsp+1E0h+GITWrappedDataObject]; this
0x1800107b0  call    ??$CopyLocal@UIDataObject@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UIDataObject@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IDataObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDataObject>>)
0x1800107b5  mov     edi, eax
0x1800107b7  lea     this, [rsp+1E0h+GITWrappedDataObject]; this
0x1800107bc  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x1800107c1  lea     this, [rsp+1E0h+GITSourceDataObject]; this
0x1800107c6  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x1800107cb  test    edi, edi
0x1800107cd  js      short loc_180010828
0x1800107cf  call    cs:__imp_CoImpersonateClient
0x1800107d5  mov     edi, eax
0x1800107d7  test    eax, eax
0x1800107d9  js      short loc_180010828
0x1800107db  mov     eax, [rsp+1E0h+dwSourceProcessId]
0x1800107df  lea     this, [rbp+0E0h+packagedProcessName]
0x1800107e3  neg     r15b
0x1800107e6  mov     [rsp+1E0h+pid], eax; pid
0x1800107ea  lea     r8, [rsp+1E0h+pMTAWrapperRawAddress]; ppDataObjectMTAAddress
0x1800107ef  mov     pDataObject, r14; pSourceDataObject
0x1800107f2  sbb     rbx, rbx
0x1800107f5  and     rbx, this
0x1800107f8  mov     this, [rsp+1E0h+pWrappedDataObjectSTAProxy.ptr_]; pDataObject
0x1800107fd  mov     r9, rbx; pszCallerPackageFullName
0x180010800  call    ?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z; OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)
0x180010805  mov     r8b, 1; fTextOnly
0x180010808  mov     this, rbx; pszCallerPackgeFullName
0x18001080b  mov     dl, r8b; fInBroker
0x18001080e  mov     edi, eax
0x180010810  call    ?OleFlushClipboardInternal@@YAJPEBG_N1@Z; OleFlushClipboardInternal(ushort const *,bool,bool)
0x180010815  call    cs:__imp_CoRevertToSelf
0x18001081b  test    edi, edi
0x18001081d  js      short loc_180010828
0x18001081f  mov     ecx, [rsp+1E0h+dwSourceProcessId]; dwSourceProcessId
0x180010823  call    ?MoniterBrokeredClipboardOwner@@YAXK@Z; MoniterBrokeredClipboardOwner(ulong)
0x180010828  cmp     [rsp+1E0h+pMTAWrapperRawAddress], r12
0x18001082d  jz      short loc_180010839
0x18001082f  lea     this, [rsp+1E0h+pMTAWrapperRawAddress]; operation
0x180010834  call    ??$RunSyncOnMTAThread@V_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@@YAJV_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@Z; RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>(_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_)
0x180010839  mov     this, [rsp+1E0h+hCallerToken]; hObject
0x18001083e  test    this, this
0x180010841  jz      short loc_180010849
0x180010843  call    cs:__imp_CloseHandle
0x180010849  mov     pDataObject, r14; pDataObject
0x18001084c  mov     ecx, edi; hr
0x18001084e  call    ?CClipboardBroker_SetClipboardEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@@Z; OleClipboardTracing::CClipboardBroker_SetClipboardEtw(long,IDataObject *)
0x180010853  mov     this, [rsp+1E0h+pWrappedDataObjectSTAProxy.ptr_]
0x180010858  test    this, this
0x18001085b  jz      short loc_18001086E
0x18001085d  mov     [rsp+1E0h+pWrappedDataObjectSTAProxy.ptr_], r12
0x180010862  mov     rax, [this]
0x180010865  mov     rax, [rax+10h]
0x180010869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001086e  mov     eax, edi
0x180010870  mov     this, [rbp+0E0h+var_30]
0x180010877  xor     this, rsp; StackCookie
0x18001087a  call    __security_check_cookie
0x18001087f  lea     r11, [rsp+1E0h+var_20]
0x180010887  mov     rbx, [r11+30h]
0x18001088b  mov     rsi, [r11+40h]
0x18001088f  mov     rsp, r11
0x180010892  pop     r15
0x180010894  pop     r14
0x180010896  pop     r12
0x180010898  pop     rdi
0x180010899  pop     rbp
0x18001089a  retn
```
