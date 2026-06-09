# CDsmMetadataTask::s_LoadSourceProviders(void)

- ea: `0x1800278a0`
- end: `0x180027a47`
- name: `?s_LoadSourceProviders@CDsmMetadataTask@@SAJXZ`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005200`
- `0x18000e12c`
- `0x180033a60`

## callees

- `0x180017274`
- `0x180018678`
- `0x1800186a4`
- `0x1800186d8`
- `0x180022070`
- `0x1800278a0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800279ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800279ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800278b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800278b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180027943`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180027943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002795c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002795c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800278fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027929`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800278fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027929`

## pseudocode

```c
__int64 CDsmMetadataTask::s_LoadSourceProviders(void)
{
  char v0; // di
  int v1; // ebx
  HRESULT Instance; // eax
  signed int LastError; // eax
  IUnknown **v4; // rax
  IUnknown *v5; // rcx
  LPUNKNOWN v6; // rax
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  char v9; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  AcquireSRWLockExclusive(&CDsmMetadataTask::s_srwLock);
  if ( !CDsmMetadataTask::s_fProviderAvailable )
  {
    v1 = -2147221164;
    goto LABEL_19;
  }
  v1 = 0;
  if ( !CDsmMetadataTask::s_fProviderLoaded )
  {
    Instance = CoCreateInstance(
                 &GUID_6c752774_29fb_4e50_8bb1_97098425a77c,
                 0,
                 0x10004u,
                 &GUID_07cd5126_ded0_473e_a39d_ba45ae10146f,
                 &CDsmMetadataTask::s_pPkgSrc);
    v1 = Instance;
    if ( Instance < 0 )
    {
      if ( Instance == -2147221164 )
        CDsmMetadataTask::s_fProviderAvailable = 0;
      goto LABEL_16;
    }
    v1 = CoCreateInstance(
           &GUID_34996c91_9897_40eb_944b_28b5c9308383,
           0,
           1u,
           &GUID_39aa7cbe_39c5_4ea0_b8db_899dd8cc8742,
           &CDsmMetadataTask::s_pParser);
    if ( v1 >= 0 )
    {
      CDsmMetadataTask::s_fProviderLoaded = 1;
      CDsmMetadataTask::s_hMutex = CreateMutexW(0, 0, 0);
      if ( CDsmMetadataTask::s_hMutex )
      {
        v1 = 0;
LABEL_8:
        v0 = 1;
LABEL_16:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_06df393cd1103d62962c75dbf951854a_Traceguids,
            (unsigned int)v1);
        goto LABEL_19;
      }
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 >= 0 )
        goto LABEL_8;
      ATL::CComPtrBase<IDsmPropertySource>::Release();
    }
    ATL::CComPtrBase<IDsmMetadataPackageSource>::Release();
    CDsmMetadataTask::s_fProviderLoaded = 0;
    goto LABEL_16;
  }
LABEL_19:
  ReleaseSRWLockExclusive(&CDsmMetadataTask::s_srwLock);
  if ( v0 )
  {
    v4 = (IUnknown **)Microsoft::WRL::Details::Make<CDsmMetadataNotificationHandler,>(&v9);
    v5 = 0;
    if ( v8 != v4 )
    {
      v5 = *v4;
      *v4 = 0;
    }
    v6 = CDsmMetadataTask::s_MetadataNotificationHandler;
    CDsmMetadataTask::s_MetadataNotificationHandler = v5;
    v8[0] = v6;
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(v8);
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v9);
    (*(void (__fastcall **)(LPVOID, LPUNKNOWN))(*(_QWORD *)CDsmMetadataTask::s_pPkgSrc + 72LL))(
      CDsmMetadataTask::s_pPkgSrc,
      CDsmMetadataTask::s_MetadataNotificationHandler);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800278a0  mov     [rsp+arg_8], rbx
0x1800278a5  push    rdi
0x1800278a6  sub     rsp, 40h
0x1800278aa  lea     rcx, ?s_srwLock@CDsmMetadataTask@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800278b1  xor     dil, dil
0x1800278b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800278ba  cmp     cs:?s_fProviderAvailable@CDsmMetadataTask@@0_NA, dil; bool CDsmMetadataTask::s_fProviderAvailable
0x1800278c1  jnz     short loc_1800278CD
0x1800278c3  mov     ebx, 80040154h
0x1800278c8  jmp     loc_1800279C7
0x1800278cd  xor     ebx, ebx
0x1800278cf  cmp     cs:?s_fProviderLoaded@CDsmMetadataTask@@0_NA, bl; bool CDsmMetadataTask::s_fProviderLoaded
0x1800278d5  jnz     loc_1800279C7
0x1800278db  lea     rax, ?s_pPkgSrc@CDsmMetadataTask@@0V?$CComPtr@UIDsmMetadataPackageSource@@@ATL@@A; ATL::CComPtr<IDsmMetadataPackageSource> CDsmMetadataTask::s_pPkgSrc
0x1800278e2  xor     edx, edx; pUnkOuter
0x1800278e4  lea     r9, _GUID_07cd5126_ded0_473e_a39d_ba45ae10146f; riid
0x1800278eb  mov     [rsp+48h+ppv], rax; ppv
0x1800278f0  mov     r8d, 10004h; dwClsContext
0x1800278f6  lea     rcx, _GUID_6c752774_29fb_4e50_8bb1_97098425a77c; rclsid
0x1800278fd  call    cs:__imp_CoCreateInstance
0x180027903  mov     ebx, eax
0x180027905  test    eax, eax
0x180027907  js      short loc_180027988
0x180027909  xor     edx, edx; pUnkOuter
0x18002790b  lea     rax, ?s_pParser@CDsmMetadataTask@@0V?$CComPtr@UIDsmPropertySource@@@ATL@@A; ATL::CComPtr<IDsmPropertySource> CDsmMetadataTask::s_pParser
0x180027912  lea     r9, _GUID_39aa7cbe_39c5_4ea0_b8db_899dd8cc8742; riid
0x180027919  mov     [rsp+48h+ppv], rax; ppv
0x18002791e  lea     rcx, _GUID_34996c91_9897_40eb_944b_28b5c9308383; rclsid
0x180027925  lea     r8d, [rdx+1]; dwClsContext
0x180027929  call    cs:__imp_CoCreateInstance
0x18002792f  mov     ebx, eax
0x180027931  test    eax, eax
0x180027933  js      short loc_18002797A
0x180027935  xor     r8d, r8d; lpName
0x180027938  mov     cs:?s_fProviderLoaded@CDsmMetadataTask@@0_NA, 1; bool CDsmMetadataTask::s_fProviderLoaded
0x18002793f  xor     edx, edx; bInitialOwner
0x180027941  xor     ecx, ecx; lpMutexAttributes
0x180027943  call    cs:__imp_CreateMutexW
0x180027949  mov     cs:?s_hMutex@CDsmMetadataTask@@0PEAXEA, rax; void * CDsmMetadataTask::s_hMutex
0x180027950  test    rax, rax
0x180027953  jz      short loc_18002795C
0x180027955  xor     ebx, ebx
0x180027957  mov     dil, 1
0x18002795a  jmp     short loc_180027996
0x18002795c  call    cs:__imp_GetLastError
0x180027962  mov     ebx, eax
0x180027964  test    eax, eax
0x180027966  jle     short loc_180027971
0x180027968  movzx   ebx, ax
0x18002796b  or      ebx, 80070000h
0x180027971  test    ebx, ebx
0x180027973  jns     short loc_180027957
0x180027975  call    ?Release@?$CComPtrBase@UIDsmPropertySource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDsmPropertySource>::Release(void)
0x18002797a  call    ?Release@?$CComPtrBase@UIDsmMetadataPackageSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDsmMetadataPackageSource>::Release(void)
0x18002797f  mov     cs:?s_fProviderLoaded@CDsmMetadataTask@@0_NA, dil; bool CDsmMetadataTask::s_fProviderLoaded
0x180027986  jmp     short loc_180027996
0x180027988  cmp     eax, 80040154h
0x18002798d  jnz     short loc_180027996
0x18002798f  mov     cs:?s_fProviderAvailable@CDsmMetadataTask@@0_NA, dil; bool CDsmMetadataTask::s_fProviderAvailable
0x180027996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002799d  lea     rax, WPP_GLOBAL_Control
0x1800279a4  cmp     rcx, rax
0x1800279a7  jz      short loc_1800279C7
0x1800279a9  test    byte ptr [rcx+1Ch], 1
0x1800279ad  jz      short loc_1800279C7
0x1800279af  mov     rcx, [rcx+10h]
0x1800279b3  lea     r8, WPP_06df393cd1103d62962c75dbf951854a_Traceguids
0x1800279ba  mov     edx, 0Ch
0x1800279bf  mov     r9d, ebx
0x1800279c2  call    WPP_SF_d
0x1800279c7  lea     rcx, ?s_srwLock@CDsmMetadataTask@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800279ce  call    cs:__imp_ReleaseSRWLockExclusive
0x1800279d4  test    dil, dil
0x1800279d7  jz      short loc_180027A3A
0x1800279d9  lea     rcx, [rsp+48h+arg_0]
0x1800279de  call    ??$Make@VCDsmMetadataNotificationHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDsmMetadataNotificationHandler@@@12@XZ; Microsoft::WRL::Details::Make<CDsmMetadataNotificationHandler,>(void)
0x1800279e3  xor     ecx, ecx
0x1800279e5  lea     rdx, [rsp+48h+var_18]
0x1800279ea  cmp     rdx, rax
0x1800279ed  jz      short loc_1800279F9
0x1800279ef  mov     rcx, [rax]
0x1800279f2  mov     qword ptr [rax], 0
0x1800279f9  mov     rax, cs:?s_MetadataNotificationHandler@CDsmMetadataTask@@0V?$ComPtr@VCDsmMetadataNotificationHandler@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CDsmMetadataNotificationHandler> CDsmMetadataTask::s_MetadataNotificationHandler
0x180027a00  mov     cs:?s_MetadataNotificationHandler@CDsmMetadataTask@@0V?$ComPtr@VCDsmMetadataNotificationHandler@@@WRL@Microsoft@@A, rcx; Microsoft::WRL::ComPtr<CDsmMetadataNotificationHandler> CDsmMetadataTask::s_MetadataNotificationHandler
0x180027a07  lea     rcx, [rsp+48h+var_18]
0x180027a0c  mov     [rsp+48h+var_18], rax
0x180027a11  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x180027a16  lea     rcx, [rsp+48h+arg_0]
0x180027a1b  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x180027a20  mov     rcx, cs:?s_pPkgSrc@CDsmMetadataTask@@0V?$CComPtr@UIDsmMetadataPackageSource@@@ATL@@A; ATL::CComPtr<IDsmMetadataPackageSource> CDsmMetadataTask::s_pPkgSrc
0x180027a27  mov     rdx, cs:?s_MetadataNotificationHandler@CDsmMetadataTask@@0V?$ComPtr@VCDsmMetadataNotificationHandler@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CDsmMetadataNotificationHandler> CDsmMetadataTask::s_MetadataNotificationHandler
0x180027a2e  mov     rax, [rcx]
0x180027a31  mov     rax, [rax+48h]
0x180027a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a3a  mov     eax, ebx
0x180027a3c  mov     rbx, [rsp+48h+arg_8]
0x180027a41  add     rsp, 40h
0x180027a45  pop     rdi
0x180027a46  retn
```
