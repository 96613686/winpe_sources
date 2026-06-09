# Windows::Management::Setup::DeploymentWorkloadBatch::RuntimeClassInitialize(uint)

- ea: `0x1800f9de8`
- end: `0x1800f9f17`
- name: `?RuntimeClassInitialize@DeploymentWorkloadBatch@Setup@Management@Windows@@QEAAJI@Z`
- size: `303`
- prototype: `int(Windows::Management::Setup::DeploymentWorkloadBatch *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006a598`

## callees

- `0x180067008`
- `0x180067a54`
- `0x18006e0a8`
- `0x18007748c`
- `0x1800f9958`
- `0x1800f9a7c`
- `0x1800f9de8`
- `0x1800fb4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9e52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f9e80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f9e80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9e67`

## string_xrefs

- `0x1800f9e0f`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800f9e3a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800f9e94`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`
- `0x1800f9ed4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkloadbatch.cpp`

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
        Vector = Windows::Management::Setup::VectorWrapperT<Windows::Management::Setup::DeploymentWorkload,Windows::Management::Setup::IDeploymentWorkload>::CreateVector((__int64)this + 80);
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
0x1800f9de8  mov     [rsp+arg_0], rbx
0x1800f9ded  mov     [rsp+arg_8], rsi
0x1800f9df2  push    rdi; int
0x1800f9df3  sub     rsp, 20h
0x1800f9df7  mov     esi, edx
0x1800f9df9  mov     rdi, rcx
0x1800f9dfc  call    ?ValidateDppOobeMode@ProvisioningHelpers@Setup@Management@Windows@@SAJXZ; Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode(void)
0x1800f9e01  mov     ebx, eax
0x1800f9e03  test    eax, eax
0x1800f9e05  jns     short loc_1800F9E27
0x1800f9e07  mov     rcx, [rsp+28h]; this
0x1800f9e0c  mov     r9d, eax; char *
0x1800f9e0f  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f9e16  mov     edx, 5Bh ; '['; void *
0x1800f9e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9e20  mov     eax, ebx
0x1800f9e22  jmp     loc_1800F9F06
0x1800f9e27  mov     edx, esi; unsigned int
0x1800f9e29  call    ?AddWorkloadBatchId@DeploymentWorkloadBatchIdUniquenessMap@Setup@Management@Windows@@QEAAJI@Z; Windows::Management::Setup::DeploymentWorkloadBatchIdUniquenessMap::AddWorkloadBatchId(uint)
0x1800f9e2e  mov     rcx, [rsp+28h]; this
0x1800f9e33  test    eax, eax
0x1800f9e35  jns     short loc_1800F9E4B
0x1800f9e37  mov     r9d, eax; char *
0x1800f9e3a  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f9e41  mov     edx, 5Eh ; '^'; void *
0x1800f9e46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9e4b  lea     rbx, [rdi+20h]
0x1800f9e4f  mov     rcx, rbx; SRWLock
0x1800f9e52  call    cs:__imp_AcquireSRWLockExclusive
0x1800f9e58  mov     [rsp+28h+arg_10], rbx
0x1800f9e5d  mov     [rdi+48h], esi
0x1800f9e60  lea     rbx, [rdi+40h]
0x1800f9e64  mov     rcx, [rbx]; string
0x1800f9e67  call    cs:__imp_WindowsDeleteString
0x1800f9e6d  mov     qword ptr [rbx], 0
0x1800f9e74  mov     r8, rbx; string
0x1800f9e77  xor     edx, edx; length
0x1800f9e79  lea     rcx, sourceString; sourceString
0x1800f9e80  call    cs:__imp_WindowsCreateString
0x1800f9e86  mov     ebx, eax
0x1800f9e88  test    eax, eax
0x1800f9e8a  jns     short loc_1800F9EB4
0x1800f9e8c  mov     rcx, [rsp+28h]; this
0x1800f9e91  mov     r9d, eax; char *
0x1800f9e94  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f9e9b  mov     edx, 62h ; 'b'; void *
0x1800f9ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ea5  nop
0x1800f9ea6  lea     rcx, [rsp+28h+arg_10]
0x1800f9eab  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f9eb0  mov     eax, ebx
0x1800f9eb2  jmp     short loc_1800F9F06
0x1800f9eb4  lea     rcx, [rdi+50h]
0x1800f9eb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9ebd  lea     rcx, [rdi+50h]
0x1800f9ec1  call    ?CreateVector@?$VectorWrapperT@VDeploymentWorkload@Setup@Management@Windows@@UIDeploymentWorkload@234@@Setup@Management@Windows@@SAJPEAPEAU?$IVector@PEAVDeploymentWorkload@Setup@Management@Windows@@@Collections@Foundation@4@@Z; Windows::Management::Setup::VectorWrapperT<Windows::Management::Setup::DeploymentWorkload,Windows::Management::Setup::IDeploymentWorkload>::CreateVector(Windows::Foundation::Collections::IVector<Windows::Management::Setup::DeploymentWorkload *> * *)
0x1800f9ec6  mov     ebx, eax
0x1800f9ec8  test    eax, eax
0x1800f9eca  jns     short loc_1800F9EF4
0x1800f9ecc  mov     rcx, [rsp+28h]; this
0x1800f9ed1  mov     r9d, eax; char *
0x1800f9ed4  lea     r8, aOnecoreuapAdmi_145; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f9edb  mov     edx, 64h ; 'd'; void *
0x1800f9ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ee5  nop
0x1800f9ee6  lea     rcx, [rsp+28h+arg_10]
0x1800f9eeb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f9ef0  mov     eax, ebx
0x1800f9ef2  jmp     short loc_1800F9F06
0x1800f9ef4  lea     rcx, [rsp+28h+arg_10]
0x1800f9ef9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f9efe  xor     eax, eax
0x1800f9f00  jmp     short loc_1800F9F06
0x1800f9f02  mov     eax, dword ptr [rsp+28h+arg_10]
0x1800f9f06  mov     rbx, [rsp+28h+arg_0]
0x1800f9f0b  mov     rsi, [rsp+28h+arg_8]
0x1800f9f10  add     rsp, 20h
0x1800f9f14  pop     rdi
0x1800f9f15  retn
```
