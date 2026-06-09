# Windows::Management::Setup::DeploymentWorkloadBatch::RuntimeClassInitialize(uint)

- ea: `0x1800fce34`
- end: `0x1800fcf75`
- name: `?RuntimeClassInitialize@DeploymentWorkloadBatch@Setup@Management@Windows@@QEAAJI@Z`
- size: `321`
- prototype: `int(Windows::Management::Setup::DeploymentWorkloadBatch *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006aa88`

## callees

- `0x180067398`
- `0x180067e54`
- `0x18006e608`
- `0x180077d0c`
- `0x1800fc994`
- `0x1800fcabc`
- `0x1800fce34`
- `0x1800fe5b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fce9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fce9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fced8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fced8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fceb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fceb9`

## string_xrefs

- `0x1800fce5b`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800fce86`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800fcef2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800fcf32`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Management::Setup::DeploymentWorkloadBatch::RuntimeClassInitialize(
        Windows::Management::Setup::DeploymentWorkloadBatch *this,
        unsigned int a2)
{
  int v4; // eax
  Windows::Management::Setup::DeploymentWorkloadBatchIdUniquenessMap *v5; // rcx
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  HRESULT String; // eax
  unsigned int v11; // ebx
  int Vector; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v16; // [rsp+40h] [rbp+18h] BYREF

  try
  {
    v4 = Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode();
    v6 = v4;
    if ( v4 >= 0 )
    {
      v9 = Windows::Management::Setup::DeploymentWorkloadBatchIdUniquenessMap::AddWorkloadBatchId(v5, a2);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkloadbatch.cpp",
          (const char *)(unsigned int)v9,
          v14);
      AcquireSRWLockExclusive((PSRWLOCK)this + 4);
      v16 = (char *)this + 32;
      *((_DWORD *)this + 18) = a2;
      WindowsDeleteString(*((HSTRING *)this + 8));
      *((_QWORD *)this + 8) = 0;
      String = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 8);
      v11 = String;
      if ( String >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
        Vector = Windows::Management::Setup::VectorWrapperT<Windows::Management::Setup::DeploymentWorkload,Windows::Management::Setup::IDeploymentWorkload>::CreateVector((char *)this + 80);
        v13 = Vector;
        if ( Vector >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x64,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkloadbatch.cpp",
            (const char *)(unsigned int)Vector,
            v14);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
          result = v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkloadbatch.cpp",
          (const char *)(unsigned int)String,
          v14);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkloadbatch.cpp",
        (const char *)(unsigned int)v4,
        v14);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\d"
                                         "eploymentworkloadbatch.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800fce34  mov     [rsp+arg_0], rbx
0x1800fce39  mov     [rsp+arg_8], rsi
0x1800fce3e  push    rdi; int
0x1800fce3f  sub     rsp, 20h
0x1800fce43  mov     esi, edx
0x1800fce45  mov     rdi, rcx
0x1800fce48  call    ?ValidateDppOobeMode@ProvisioningHelpers@Setup@Management@Windows@@SAJXZ; Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode(void)
0x1800fce4d  mov     ebx, eax
0x1800fce4f  test    eax, eax
0x1800fce51  jns     short loc_1800FCE73
0x1800fce53  mov     rcx, [rsp+28h]; this
0x1800fce58  mov     r9d, eax; char *
0x1800fce5b  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fce62  mov     edx, 5Bh ; '['; void *
0x1800fce67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fce6c  mov     eax, ebx
0x1800fce6e  jmp     loc_1800FCF64
0x1800fce73  mov     edx, esi; unsigned int
0x1800fce75  call    ?AddWorkloadBatchId@DeploymentWorkloadBatchIdUniquenessMap@Setup@Management@Windows@@QEAAJI@Z; Windows::Management::Setup::DeploymentWorkloadBatchIdUniquenessMap::AddWorkloadBatchId(uint)
0x1800fce7a  mov     rcx, [rsp+28h]; this
0x1800fce7f  test    eax, eax
0x1800fce81  jns     short loc_1800FCE97
0x1800fce83  mov     r9d, eax; char *
0x1800fce86  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fce8d  mov     edx, 5Eh ; '^'; void *
0x1800fce92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fce97  lea     rbx, [rdi+20h]
0x1800fce9b  mov     rcx, rbx; SRWLock
0x1800fce9e  call    cs:__imp_AcquireSRWLockExclusive
0x1800fcea5  nop     dword ptr [rax+rax+00h]
0x1800fceaa  mov     [rsp+28h+arg_10], rbx
0x1800fceaf  mov     [rdi+48h], esi
0x1800fceb2  lea     rbx, [rdi+40h]
0x1800fceb6  mov     rcx, [rbx]; string
0x1800fceb9  call    cs:__imp_WindowsDeleteString
0x1800fcec0  nop     dword ptr [rax+rax+00h]
0x1800fcec5  mov     qword ptr [rbx], 0
0x1800fcecc  mov     r8, rbx; string
0x1800fcecf  xor     edx, edx; length
0x1800fced1  lea     rcx, sourceString; sourceString
0x1800fced8  call    cs:__imp_WindowsCreateString
0x1800fcedf  nop     dword ptr [rax+rax+00h]
0x1800fcee4  mov     ebx, eax
0x1800fcee6  test    eax, eax
0x1800fcee8  jns     short loc_1800FCF12
0x1800fceea  mov     rcx, [rsp+28h]; this
0x1800fceef  mov     r9d, eax; char *
0x1800fcef2  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fcef9  mov     edx, 62h ; 'b'; void *
0x1800fcefe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fcf03  nop
0x1800fcf04  lea     rcx, [rsp+28h+arg_10]
0x1800fcf09  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fcf0e  mov     eax, ebx
0x1800fcf10  jmp     short loc_1800FCF64
0x1800fcf12  lea     rcx, [rdi+50h]
0x1800fcf16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fcf1b  lea     rcx, [rdi+50h]
0x1800fcf1f  call    ?CreateVector@?$VectorWrapperT@VDeploymentWorkload@Setup@Management@Windows@@UIDeploymentWorkload@234@@Setup@Management@Windows@@SAJPEAPEAU?$IVector@PEAVDeploymentWorkload@Setup@Management@Windows@@@Collections@Foundation@4@@Z; Windows::Management::Setup::VectorWrapperT<Windows::Management::Setup::DeploymentWorkload,Windows::Management::Setup::IDeploymentWorkload>::CreateVector(Windows::Foundation::Collections::IVector<Windows::Management::Setup::DeploymentWorkload *> * *)
0x1800fcf24  mov     ebx, eax
0x1800fcf26  test    eax, eax
0x1800fcf28  jns     short loc_1800FCF52
0x1800fcf2a  mov     rcx, [rsp+28h]; this
0x1800fcf2f  mov     r9d, eax; char *
0x1800fcf32  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fcf39  mov     edx, 64h ; 'd'; void *
0x1800fcf3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fcf43  nop
0x1800fcf44  lea     rcx, [rsp+28h+arg_10]
0x1800fcf49  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fcf4e  mov     eax, ebx
0x1800fcf50  jmp     short loc_1800FCF64
0x1800fcf52  lea     rcx, [rsp+28h+arg_10]
0x1800fcf57  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fcf5c  xor     eax, eax
0x1800fcf5e  jmp     short loc_1800FCF64
0x1800fcf60  mov     eax, dword ptr [rsp+28h+arg_10]
0x1800fcf64  mov     rbx, [rsp+28h+arg_0]
0x1800fcf69  mov     rsi, [rsp+28h+arg_8]
0x1800fcf6e  add     rsp, 20h
0x1800fcf72  pop     rdi
0x1800fcf73  retn
```
