# Windows::Management::Setup::DeploymentWorkload::RuntimeClassInitialize(HSTRING__ *)

- ea: `0x1800fb0c0`
- end: `0x1800fb3d3`
- name: `?RuntimeClassInitialize@DeploymentWorkload@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `787`
- prototype: `int(Windows::Management::Setup::DeploymentWorkload *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006a9d8`

## callees

- `0x180067e54`
- `0x18006e608`
- `0x180077d0c`
- `0x1800ab988`
- `0x1800fabd8`
- `0x1800fb0c0`
- `0x1800fe5b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fb15f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fb15f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb1d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb1d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800fb344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fb112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fb112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb1b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb2d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb1b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb2d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb32d`

## string_xrefs

- `0x1800fb0ee`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb147`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb18c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb1ed`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb24a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb2a7`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb304`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb35e`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800fb3ab`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Management::Setup::DeploymentWorkload::RuntimeClassInitialize(
        Windows::Management::Setup::DeploymentWorkload *this,
        HSTRING a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap *v9; // rcx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  HRESULT String; // eax
  unsigned int v14; // ebx
  HRESULT v15; // eax
  unsigned int v16; // ebx
  HRESULT v17; // eax
  unsigned int v18; // ebx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  HRESULT v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING v25; // [rsp+48h] [rbp+10h] BYREF
  UINT32 length; // [rsp+50h] [rbp+18h] BYREF
  char *v27; // [rsp+58h] [rbp+20h] BYREF

  v25 = a2;
  try
  {
    v4 = Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode();
    v5 = v4;
    if ( v4 >= 0 )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
      if ( length && *StringRawBuffer )
      {
        v10 = Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::AddWorkloadId(v9, a2);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
            (const char *)(unsigned int)v10,
            v23);
        AcquireSRWLockExclusive((PSRWLOCK)this + 4);
        v27 = (char *)this + 32;
        v11 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 8, &v25);
        v12 = v11;
        if ( v11 >= 0 )
        {
          WindowsDeleteString(*((HSTRING *)this + 9));
          *((_QWORD *)this + 9) = 0;
          String = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 9);
          v14 = String;
          if ( String >= 0 )
          {
            WindowsDeleteString(*((HSTRING *)this + 17));
            *((_QWORD *)this + 17) = 0;
            v15 = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 17);
            v16 = v15;
            if ( v15 >= 0 )
            {
              WindowsDeleteString(*((HSTRING *)this + 18));
              *((_QWORD *)this + 18) = 0;
              v17 = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 18);
              v18 = v17;
              if ( v17 >= 0 )
              {
                WindowsDeleteString(*((HSTRING *)this + 19));
                *((_QWORD *)this + 19) = 0;
                v19 = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 19);
                v20 = v19;
                if ( v19 >= 0 )
                {
                  WindowsDeleteString(*((HSTRING *)this + 11));
                  *((_QWORD *)this + 11) = 0;
                  v21 = WindowsCreateString(&sourceString, 0, (HSTRING *)this + 11);
                  v22 = v21;
                  if ( v21 >= 0 )
                  {
                    *((_DWORD *)this + 20) = 0;
                    *((_BYTE *)this + 104) = 0;
                    *((_BYTE *)this + 120) = 0;
                    *((_DWORD *)this + 32) = 0;
                    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
                    result = 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x7E,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploy"
                                    "mentworkload.cpp",
                      (const char *)(unsigned int)v21,
                      v23);
                    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
                    result = v22;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7D,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
                    (const char *)(unsigned int)v19,
                    v23);
                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
                  result = v20;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7C,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
                  (const char *)(unsigned int)v17,
                  v23);
                wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
                result = v18;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7B,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
                (const char *)(unsigned int)v15,
                v23);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
              result = v16;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7A,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
              (const char *)(unsigned int)String,
              v23);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
            result = v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x79,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
            (const char *)(unsigned int)v11,
            v23);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
          result = v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x75,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
          (const char *)0x80070057LL,
          v23);
        result = 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\deploymentworkload.cpp",
        (const char *)(unsigned int)v4,
        v23);
      result = v5;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x86,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\d"
                                         "eploymentworkload.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800fb0c0  mov     [rsp+arg_0], rbx
0x1800fb0c5  mov     [rsp+arg_8], rdx
0x1800fb0ca  push    rsi
0x1800fb0cb  push    rdi
0x1800fb0cc  push    r14; int
0x1800fb0ce  sub     rsp, 20h
0x1800fb0d2  mov     rsi, rdx
0x1800fb0d5  mov     rdi, rcx
0x1800fb0d8  call    ?ValidateDppOobeMode@ProvisioningHelpers@Setup@Management@Windows@@SAJXZ; Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode(void)
0x1800fb0dd  mov     ebx, eax
0x1800fb0df  xor     r14d, r14d
0x1800fb0e2  test    eax, eax
0x1800fb0e4  jns     short loc_1800FB105
0x1800fb0e6  mov     rcx, [rsp+38h]; this
0x1800fb0eb  mov     r9d, eax; char *
0x1800fb0ee  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb0f5  lea     edx, [r14+71h]; void *
0x1800fb0f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb0fe  mov     eax, ebx
0x1800fb100  jmp     loc_1800FB3C4
0x1800fb105  mov     [rsp+38h+length], r14d
0x1800fb10a  lea     rdx, [rsp+38h+length]; length
0x1800fb10f  mov     rcx, rsi; string
0x1800fb112  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fb119  nop     dword ptr [rax+rax+00h]
0x1800fb11e  cmp     [rsp+38h+length], r14d
0x1800fb123  jz      loc_1800FB39E
0x1800fb129  cmp     [rax], r14w
0x1800fb12d  jz      loc_1800FB39E
0x1800fb133  mov     rdx, rsi; HSTRING
0x1800fb136  call    ?AddWorkloadId@DeploymentWorkloadIdUniquenessMap@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::AddWorkloadId(HSTRING__ *)
0x1800fb13b  mov     rcx, [rsp+38h]; this
0x1800fb140  test    eax, eax
0x1800fb142  jns     short loc_1800FB158
0x1800fb144  mov     r9d, eax; char *
0x1800fb147  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb14e  mov     edx, 76h ; 'v'; void *
0x1800fb153  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fb158  lea     rbx, [rdi+20h]
0x1800fb15c  mov     rcx, rbx; SRWLock
0x1800fb15f  call    cs:__imp_AcquireSRWLockExclusive
0x1800fb166  nop     dword ptr [rax+rax+00h]
0x1800fb16b  mov     [rsp+38h+arg_18], rbx
0x1800fb170  lea     rcx, [rdi+40h]; newString
0x1800fb174  lea     rdx, [rsp+38h+arg_8]; HSTRING *
0x1800fb179  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800fb17e  mov     ebx, eax
0x1800fb180  test    eax, eax
0x1800fb182  jns     short loc_1800FB1AE
0x1800fb184  mov     rcx, [rsp+38h]; this
0x1800fb189  mov     r9d, eax; char *
0x1800fb18c  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb193  mov     edx, 79h ; 'y'; void *
0x1800fb198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb19d  lea     rcx, [rsp+38h+arg_18]
0x1800fb1a2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb1a7  mov     eax, ebx
0x1800fb1a9  jmp     loc_1800FB3C4
0x1800fb1ae  lea     rbx, [rdi+48h]
0x1800fb1b2  mov     rcx, [rbx]; string
0x1800fb1b5  call    cs:__imp_WindowsDeleteString
0x1800fb1bc  nop     dword ptr [rax+rax+00h]
0x1800fb1c1  mov     [rbx], r14
0x1800fb1c4  mov     r8, rbx; string
0x1800fb1c7  xor     edx, edx; length
0x1800fb1c9  lea     rsi, sourceString
0x1800fb1d0  mov     rcx, rsi; sourceString
0x1800fb1d3  call    cs:__imp_WindowsCreateString
0x1800fb1da  nop     dword ptr [rax+rax+00h]
0x1800fb1df  mov     ebx, eax
0x1800fb1e1  test    eax, eax
0x1800fb1e3  jns     short loc_1800FB20F
0x1800fb1e5  mov     rcx, [rsp+38h]; this
0x1800fb1ea  mov     r9d, eax; char *
0x1800fb1ed  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb1f4  mov     edx, 7Ah ; 'z'; void *
0x1800fb1f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb1fe  lea     rcx, [rsp+38h+arg_18]
0x1800fb203  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb208  mov     eax, ebx
0x1800fb20a  jmp     loc_1800FB3C4
0x1800fb20f  lea     rbx, [rdi+88h]
0x1800fb216  mov     rcx, [rbx]; string
0x1800fb219  call    cs:__imp_WindowsDeleteString
0x1800fb220  nop     dword ptr [rax+rax+00h]
0x1800fb225  mov     [rbx], r14
0x1800fb228  mov     r8, rbx; string
0x1800fb22b  xor     edx, edx; length
0x1800fb22d  mov     rcx, rsi; sourceString
0x1800fb230  call    cs:__imp_WindowsCreateString
0x1800fb237  nop     dword ptr [rax+rax+00h]
0x1800fb23c  mov     ebx, eax
0x1800fb23e  test    eax, eax
0x1800fb240  jns     short loc_1800FB26C
0x1800fb242  mov     rcx, [rsp+38h]; this
0x1800fb247  mov     r9d, eax; char *
0x1800fb24a  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb251  mov     edx, 7Bh ; '{'; void *
0x1800fb256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb25b  lea     rcx, [rsp+38h+arg_18]
0x1800fb260  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb265  mov     eax, ebx
0x1800fb267  jmp     loc_1800FB3C4
0x1800fb26c  lea     rbx, [rdi+90h]
0x1800fb273  mov     rcx, [rbx]; string
0x1800fb276  call    cs:__imp_WindowsDeleteString
0x1800fb27d  nop     dword ptr [rax+rax+00h]
0x1800fb282  mov     [rbx], r14
0x1800fb285  mov     r8, rbx; string
0x1800fb288  xor     edx, edx; length
0x1800fb28a  mov     rcx, rsi; sourceString
0x1800fb28d  call    cs:__imp_WindowsCreateString
0x1800fb294  nop     dword ptr [rax+rax+00h]
0x1800fb299  mov     ebx, eax
0x1800fb29b  test    eax, eax
0x1800fb29d  jns     short loc_1800FB2C9
0x1800fb29f  mov     rcx, [rsp+38h]; this
0x1800fb2a4  mov     r9d, eax; char *
0x1800fb2a7  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb2ae  mov     edx, 7Ch ; '|'; void *
0x1800fb2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb2b8  lea     rcx, [rsp+38h+arg_18]
0x1800fb2bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb2c2  mov     eax, ebx
0x1800fb2c4  jmp     loc_1800FB3C4
0x1800fb2c9  lea     rbx, [rdi+98h]
0x1800fb2d0  mov     rcx, [rbx]; string
0x1800fb2d3  call    cs:__imp_WindowsDeleteString
0x1800fb2da  nop     dword ptr [rax+rax+00h]
0x1800fb2df  mov     [rbx], r14
0x1800fb2e2  mov     r8, rbx; string
0x1800fb2e5  xor     edx, edx; length
0x1800fb2e7  mov     rcx, rsi; sourceString
0x1800fb2ea  call    cs:__imp_WindowsCreateString
0x1800fb2f1  nop     dword ptr [rax+rax+00h]
0x1800fb2f6  mov     ebx, eax
0x1800fb2f8  test    eax, eax
0x1800fb2fa  jns     short loc_1800FB326
0x1800fb2fc  mov     rcx, [rsp+38h]; this
0x1800fb301  mov     r9d, eax; char *
0x1800fb304  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb30b  mov     edx, 7Dh ; '}'; void *
0x1800fb310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb315  lea     rcx, [rsp+38h+arg_18]
0x1800fb31a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb31f  mov     eax, ebx
0x1800fb321  jmp     loc_1800FB3C4
0x1800fb326  lea     rbx, [rdi+58h]
0x1800fb32a  mov     rcx, [rbx]; string
0x1800fb32d  call    cs:__imp_WindowsDeleteString
0x1800fb334  nop     dword ptr [rax+rax+00h]
0x1800fb339  mov     [rbx], r14
0x1800fb33c  mov     r8, rbx; string
0x1800fb33f  xor     edx, edx; length
0x1800fb341  mov     rcx, rsi; sourceString
0x1800fb344  call    cs:__imp_WindowsCreateString
0x1800fb34b  nop     dword ptr [rax+rax+00h]
0x1800fb350  mov     ebx, eax
0x1800fb352  test    eax, eax
0x1800fb354  jns     short loc_1800FB37D
0x1800fb356  mov     rcx, [rsp+38h]; this
0x1800fb35b  mov     r9d, eax; char *
0x1800fb35e  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb365  mov     edx, 7Eh ; '~'; void *
0x1800fb36a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb36f  lea     rcx, [rsp+38h+arg_18]
0x1800fb374  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb379  mov     eax, ebx
0x1800fb37b  jmp     short loc_1800FB3C4
0x1800fb37d  mov     [rdi+50h], r14d
0x1800fb381  mov     [rdi+68h], r14b
0x1800fb385  mov     [rdi+78h], r14b
0x1800fb389  mov     [rdi+80h], r14d
0x1800fb390  lea     rcx, [rsp+38h+arg_18]
0x1800fb395  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800fb39a  xor     eax, eax
0x1800fb39c  jmp     short loc_1800FB3C4
0x1800fb39e  mov     rcx, [rsp+38h]; this
0x1800fb3a3  mov     ebx, 80070057h
0x1800fb3a8  mov     r9d, ebx; char *
0x1800fb3ab  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fb3b2  mov     edx, 75h ; 'u'; void *
0x1800fb3b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb3bc  mov     eax, ebx
0x1800fb3be  jmp     short loc_1800FB3C4
0x1800fb3c0  mov     eax, [rsp+38h+length]
0x1800fb3c4  mov     rbx, [rsp+38h+arg_0]
0x1800fb3c9  add     rsp, 20h
0x1800fb3cd  pop     r14
0x1800fb3cf  pop     rdi
0x1800fb3d0  pop     rsi
0x1800fb3d1  retn
```
