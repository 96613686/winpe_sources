# Windows::Management::Setup::DeploymentWorkload::RuntimeClassInitialize(HSTRING__ *)

- ea: `0x1800f814c`
- end: `0x1800f8417`
- name: `?RuntimeClassInitialize@DeploymentWorkload@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `715`
- prototype: `int(Windows::Management::Setup::DeploymentWorkload *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006a4ec`

## callees

- `0x180067a54`
- `0x18006e0a8`
- `0x18007748c`
- `0x1800aa0d4`
- `0x1800f7c74`
- `0x1800f814c`
- `0x1800fb4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f81e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f81e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f824d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f829e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f82ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f8340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f838e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f824d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f829e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f82ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f8340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f838e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f819e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f819e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f8235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f828d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f82de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f832f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f837d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f8235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f828d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f82de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f832f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f837d`

## string_xrefs

- `0x1800f817a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f81cd`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f820c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f8261`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f82b2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f8303`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f8354`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f83a2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f83ef`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`

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
0x1800f814c  mov     [rsp+arg_0], rbx
0x1800f8151  mov     [rsp+arg_8], rdx
0x1800f8156  push    rsi
0x1800f8157  push    rdi
0x1800f8158  push    r14; int
0x1800f815a  sub     rsp, 20h
0x1800f815e  mov     rsi, rdx
0x1800f8161  mov     rdi, rcx
0x1800f8164  call    ?ValidateDppOobeMode@ProvisioningHelpers@Setup@Management@Windows@@SAJXZ; Windows::Management::Setup::ProvisioningHelpers::ValidateDppOobeMode(void)
0x1800f8169  mov     ebx, eax
0x1800f816b  xor     r14d, r14d
0x1800f816e  test    eax, eax
0x1800f8170  jns     short loc_1800F8191
0x1800f8172  mov     rcx, [rsp+38h]; this
0x1800f8177  mov     r9d, eax; char *
0x1800f817a  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f8181  lea     edx, [r14+71h]; void *
0x1800f8185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f818a  mov     eax, ebx
0x1800f818c  jmp     loc_1800F8408
0x1800f8191  mov     [rsp+38h+length], r14d
0x1800f8196  lea     rdx, [rsp+38h+length]; length
0x1800f819b  mov     rcx, rsi; string
0x1800f819e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f81a4  cmp     [rsp+38h+length], r14d
0x1800f81a9  jz      loc_1800F83E2
0x1800f81af  cmp     [rax], r14w
0x1800f81b3  jz      loc_1800F83E2
0x1800f81b9  mov     rdx, rsi; HSTRING
0x1800f81bc  call    ?AddWorkloadId@DeploymentWorkloadIdUniquenessMap@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::AddWorkloadId(HSTRING__ *)
0x1800f81c1  mov     rcx, [rsp+38h]; this
0x1800f81c6  test    eax, eax
0x1800f81c8  jns     short loc_1800F81DE
0x1800f81ca  mov     r9d, eax; char *
0x1800f81cd  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f81d4  mov     edx, 76h ; 'v'; void *
0x1800f81d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f81de  lea     rbx, [rdi+20h]
0x1800f81e2  mov     rcx, rbx; SRWLock
0x1800f81e5  call    cs:__imp_AcquireSRWLockExclusive
0x1800f81eb  mov     [rsp+38h+arg_18], rbx
0x1800f81f0  lea     rcx, [rdi+40h]; newString
0x1800f81f4  lea     rdx, [rsp+38h+arg_8]; HSTRING *
0x1800f81f9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800f81fe  mov     ebx, eax
0x1800f8200  test    eax, eax
0x1800f8202  jns     short loc_1800F822E
0x1800f8204  mov     rcx, [rsp+38h]; this
0x1800f8209  mov     r9d, eax; char *
0x1800f820c  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f8213  mov     edx, 79h ; 'y'; void *
0x1800f8218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f821d  lea     rcx, [rsp+38h+arg_18]
0x1800f8222  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f8227  mov     eax, ebx
0x1800f8229  jmp     loc_1800F8408
0x1800f822e  lea     rbx, [rdi+48h]
0x1800f8232  mov     rcx, [rbx]; string
0x1800f8235  call    cs:__imp_WindowsDeleteString
0x1800f823b  mov     [rbx], r14
0x1800f823e  mov     r8, rbx; string
0x1800f8241  xor     edx, edx; length
0x1800f8243  lea     rsi, sourceString
0x1800f824a  mov     rcx, rsi; sourceString
0x1800f824d  call    cs:__imp_WindowsCreateString
0x1800f8253  mov     ebx, eax
0x1800f8255  test    eax, eax
0x1800f8257  jns     short loc_1800F8283
0x1800f8259  mov     rcx, [rsp+38h]; this
0x1800f825e  mov     r9d, eax; char *
0x1800f8261  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f8268  mov     edx, 7Ah ; 'z'; void *
0x1800f826d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8272  lea     rcx, [rsp+38h+arg_18]
0x1800f8277  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f827c  mov     eax, ebx
0x1800f827e  jmp     loc_1800F8408
0x1800f8283  lea     rbx, [rdi+88h]
0x1800f828a  mov     rcx, [rbx]; string
0x1800f828d  call    cs:__imp_WindowsDeleteString
0x1800f8293  mov     [rbx], r14
0x1800f8296  mov     r8, rbx; string
0x1800f8299  xor     edx, edx; length
0x1800f829b  mov     rcx, rsi; sourceString
0x1800f829e  call    cs:__imp_WindowsCreateString
0x1800f82a4  mov     ebx, eax
0x1800f82a6  test    eax, eax
0x1800f82a8  jns     short loc_1800F82D4
0x1800f82aa  mov     rcx, [rsp+38h]; this
0x1800f82af  mov     r9d, eax; char *
0x1800f82b2  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f82b9  mov     edx, 7Bh ; '{'; void *
0x1800f82be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f82c3  lea     rcx, [rsp+38h+arg_18]
0x1800f82c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f82cd  mov     eax, ebx
0x1800f82cf  jmp     loc_1800F8408
0x1800f82d4  lea     rbx, [rdi+90h]
0x1800f82db  mov     rcx, [rbx]; string
0x1800f82de  call    cs:__imp_WindowsDeleteString
0x1800f82e4  mov     [rbx], r14
0x1800f82e7  mov     r8, rbx; string
0x1800f82ea  xor     edx, edx; length
0x1800f82ec  mov     rcx, rsi; sourceString
0x1800f82ef  call    cs:__imp_WindowsCreateString
0x1800f82f5  mov     ebx, eax
0x1800f82f7  test    eax, eax
0x1800f82f9  jns     short loc_1800F8325
0x1800f82fb  mov     rcx, [rsp+38h]; this
0x1800f8300  mov     r9d, eax; char *
0x1800f8303  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f830a  mov     edx, 7Ch ; '|'; void *
0x1800f830f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8314  lea     rcx, [rsp+38h+arg_18]
0x1800f8319  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f831e  mov     eax, ebx
0x1800f8320  jmp     loc_1800F8408
0x1800f8325  lea     rbx, [rdi+98h]
0x1800f832c  mov     rcx, [rbx]; string
0x1800f832f  call    cs:__imp_WindowsDeleteString
0x1800f8335  mov     [rbx], r14
0x1800f8338  mov     r8, rbx; string
0x1800f833b  xor     edx, edx; length
0x1800f833d  mov     rcx, rsi; sourceString
0x1800f8340  call    cs:__imp_WindowsCreateString
0x1800f8346  mov     ebx, eax
0x1800f8348  test    eax, eax
0x1800f834a  jns     short loc_1800F8376
0x1800f834c  mov     rcx, [rsp+38h]; this
0x1800f8351  mov     r9d, eax; char *
0x1800f8354  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f835b  mov     edx, 7Dh ; '}'; void *
0x1800f8360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8365  lea     rcx, [rsp+38h+arg_18]
0x1800f836a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f836f  mov     eax, ebx
0x1800f8371  jmp     loc_1800F8408
0x1800f8376  lea     rbx, [rdi+58h]
0x1800f837a  mov     rcx, [rbx]; string
0x1800f837d  call    cs:__imp_WindowsDeleteString
0x1800f8383  mov     [rbx], r14
0x1800f8386  mov     r8, rbx; string
0x1800f8389  xor     edx, edx; length
0x1800f838b  mov     rcx, rsi; sourceString
0x1800f838e  call    cs:__imp_WindowsCreateString
0x1800f8394  mov     ebx, eax
0x1800f8396  test    eax, eax
0x1800f8398  jns     short loc_1800F83C1
0x1800f839a  mov     rcx, [rsp+38h]; this
0x1800f839f  mov     r9d, eax; char *
0x1800f83a2  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f83a9  mov     edx, 7Eh ; '~'; void *
0x1800f83ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f83b3  lea     rcx, [rsp+38h+arg_18]
0x1800f83b8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f83bd  mov     eax, ebx
0x1800f83bf  jmp     short loc_1800F8408
0x1800f83c1  mov     [rdi+50h], r14d
0x1800f83c5  mov     [rdi+68h], r14b
0x1800f83c9  mov     [rdi+78h], r14b
0x1800f83cd  mov     [rdi+80h], r14d
0x1800f83d4  lea     rcx, [rsp+38h+arg_18]
0x1800f83d9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800f83de  xor     eax, eax
0x1800f83e0  jmp     short loc_1800F8408
0x1800f83e2  mov     rcx, [rsp+38h]; this
0x1800f83e7  mov     ebx, 80070057h
0x1800f83ec  mov     r9d, ebx; char *
0x1800f83ef  lea     r8, aOnecoreuapAdmi_115; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f83f6  mov     edx, 75h ; 'u'; void *
0x1800f83fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8400  mov     eax, ebx
0x1800f8402  jmp     short loc_1800F8408
0x1800f8404  mov     eax, [rsp+38h+length]
0x1800f8408  mov     rbx, [rsp+38h+arg_0]
0x1800f840d  add     rsp, 20h
0x1800f8411  pop     r14
0x1800f8413  pop     rdi
0x1800f8414  pop     rsi
0x1800f8415  retn
```
