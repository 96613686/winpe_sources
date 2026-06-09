# ModernDeployment::Autopilot::Core::FwtRecordId::GetNextRecordId(ulong &)

- ea: `0x1800e4ef8`
- end: `0x1800e5171`
- name: `?GetNextRecordId@FwtRecordId@Core@Autopilot@ModernDeployment@@SAJAEAK@Z`
- size: `633`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dd23c`

## callees

- `0x180067e54`
- `0x18006e608`
- `0x180077e54`
- `0x180080984`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1800e4ef8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e4f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e4f44`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e50b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e50b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e4fbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e4fbc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5064`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5064`

## string_xrefs

- `0x1800e4f22`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e4fe3`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e50de`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e5130`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`

## pseudocode

```c
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtRecordId::GetNextRecordId(unsigned int *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  bool v4; // al
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int ValueW; // eax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  int dwOptions; // [rsp+20h] [rbp-58h]
  int dwOptionsa; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-58h]
  int dwOptionsc; // [rsp+20h] [rbp-58h]
  DWORD pdwType; // [rsp+50h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v18[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int pvData; // [rsp+88h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
    {
      AcquireSRWLockExclusive(&stru_1802B7460);
      v18[0] = &stru_1802B7460;
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v4 = ZTPIsStateSeparationEnabled();
      v5 = (const WCHAR *)&stru_18022EC60;
      if ( !v4 )
        v5 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
      {
        pvData = 0;
        pcbData = 4;
        pdwType = 0;
        ValueW = RegGetValueW(hkey, 0, L"FwtRecordId", 0x10u, &pdwType, &pvData, &pcbData);
        if ( (ValueW & 0xFFFFFFFC) != 0 || ValueW == 1 )
        {
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x32,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
                  (const char *)ValueW,
                  dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
          result = v11;
        }
        else
        {
          Data = pvData + 1;
          v9 = RegSetValueExW(hkey, L"FwtRecordId", 0, 4u, (const BYTE *)&Data, 4u);
          v10 = v9;
          if ( v9 > 0 )
            v10 = (unsigned __int16)v9 | 0x80070000;
          if ( (v10 & 0x80000000) == 0 )
          {
            *a1 = Data;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3D,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
              (const char *)v10,
              dwOptionsc);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
            result = v10;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
          (const char *)v7,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
        result = v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
        (const char *)0x80004001LL,
        dwOptions);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800e4ef8  mov     [rsp+arg_0], rbx
0x1800e4efd  push    rdi
0x1800e4efe  sub     rsp, 70h
0x1800e4f02  mov     rdi, rcx
0x1800e4f05  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e4f0c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e4f11  test    al, al
0x1800e4f13  jnz     short loc_1800E4F3A
0x1800e4f15  mov     rcx, [rsp+78h]; this
0x1800e4f1a  mov     ebx, 80004001h
0x1800e4f1f  mov     r9d, ebx; char *
0x1800e4f22  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4f29  mov     edx, 12h; void *
0x1800e4f2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4f33  mov     eax, ebx
0x1800e4f35  jmp     loc_1800E5162
0x1800e4f3a  lea     rbx, stru_1802B7460
0x1800e4f41  mov     rcx, rbx; SRWLock
0x1800e4f44  call    cs:__imp_AcquireSRWLockExclusive
0x1800e4f4b  nop     dword ptr [rax+rax+00h]
0x1800e4f50  mov     [rsp+78h+var_18], rbx
0x1800e4f55  mov     [rsp+78h+hkey], 0
0x1800e4f5e  xor     edx, edx
0x1800e4f60  lea     rcx, [rsp+78h+hkey]
0x1800e4f65  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800e4f6a  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e4f6f  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800e4f76  lea     rdx, stru_18022EC60
0x1800e4f7d  test    al, al
0x1800e4f7f  cmovz   rdx, rcx; lpSubKey
0x1800e4f83  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800e4f8c  lea     rax, [rsp+78h+hkey]
0x1800e4f91  mov     [rsp+78h+phkResult], rax; phkResult
0x1800e4f96  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800e4f9f  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800e4fa7  mov     [rsp+78h+dwOptions], 0; int
0x1800e4faf  xor     r9d, r9d; lpClass
0x1800e4fb2  xor     r8d, r8d; Reserved
0x1800e4fb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e4fbc  call    cs:__imp_RegCreateKeyExW
0x1800e4fc3  nop     dword ptr [rax+rax+00h]
0x1800e4fc8  mov     ebx, eax
0x1800e4fca  test    eax, eax
0x1800e4fcc  jle     short loc_1800E4FD7
0x1800e4fce  movzx   ebx, ax
0x1800e4fd1  or      ebx, 80070000h
0x1800e4fd7  test    ebx, ebx
0x1800e4fd9  jns     short loc_1800E500F
0x1800e4fdb  mov     rcx, [rsp+78h]; this
0x1800e4fe0  mov     r9d, ebx; char *
0x1800e4fe3  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4fea  mov     edx, 21h ; '!'; void *
0x1800e4fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4ff4  lea     rcx, [rsp+78h+hkey]
0x1800e4ff9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e4ffe  lea     rcx, [rsp+78h+var_18]
0x1800e5003  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e5008  mov     eax, ebx
0x1800e500a  jmp     loc_1800E5162
0x1800e500f  mov     [rsp+78h+pvData], 0
0x1800e501a  mov     ebx, 4
0x1800e501f  mov     [rsp+78h+pcbData], ebx
0x1800e5026  mov     [rsp+78h+pdwType], 0
0x1800e502e  lea     rax, [rsp+78h+pcbData]
0x1800e5036  mov     [rsp+78h+lpSecurityAttributes], rax; pcbData
0x1800e503b  lea     rax, [rsp+78h+pvData]
0x1800e5043  mov     qword ptr [rsp+78h+samDesired], rax; pvData
0x1800e5048  lea     rax, [rsp+78h+pdwType]
0x1800e504d  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int
0x1800e5052  lea     r9d, [rbx+0Ch]; dwFlags
0x1800e5056  lea     r8, aFwtrecordid; "FwtRecordId"
0x1800e505d  xor     edx, edx; lpSubKey
0x1800e505f  mov     rcx, [rsp+78h+hkey]; hkey
0x1800e5064  call    cs:__imp_RegGetValueW
0x1800e506b  nop     dword ptr [rax+rax+00h]
0x1800e5070  test    eax, 0FFFFFFFCh
0x1800e5075  jnz     loc_1800E5128
0x1800e507b  cmp     eax, 1
0x1800e507e  jz      loc_1800E5128
0x1800e5084  mov     eax, [rsp+78h+pvData]
0x1800e508b  inc     eax
0x1800e508d  mov     [rsp+78h+Data], eax
0x1800e5094  mov     [rsp+78h+samDesired], ebx; cbData
0x1800e5098  lea     rax, [rsp+78h+Data]
0x1800e50a0  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x1800e50a5  mov     r9d, ebx; dwType
0x1800e50a8  xor     r8d, r8d; Reserved
0x1800e50ab  lea     rdx, aFwtrecordid; "FwtRecordId"
0x1800e50b2  mov     rcx, [rsp+78h+hkey]; hKey
0x1800e50b7  call    cs:__imp_RegSetValueExW
0x1800e50be  nop     dword ptr [rax+rax+00h]
0x1800e50c3  mov     ebx, eax
0x1800e50c5  test    eax, eax
0x1800e50c7  jle     short loc_1800E50D2
0x1800e50c9  movzx   ebx, ax
0x1800e50cc  or      ebx, 80070000h
0x1800e50d2  test    ebx, ebx
0x1800e50d4  jns     short loc_1800E5107
0x1800e50d6  mov     rcx, [rsp+78h]; this
0x1800e50db  mov     r9d, ebx; char *
0x1800e50de  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e50e5  mov     edx, 3Dh ; '='; void *
0x1800e50ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e50ef  lea     rcx, [rsp+78h+hkey]
0x1800e50f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e50f9  lea     rcx, [rsp+78h+var_18]
0x1800e50fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e5103  mov     eax, ebx
0x1800e5105  jmp     short loc_1800E5162
0x1800e5107  mov     eax, [rsp+78h+Data]
0x1800e510e  mov     [rdi], eax
0x1800e5110  lea     rcx, [rsp+78h+hkey]
0x1800e5115  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e511a  lea     rcx, [rsp+78h+var_18]
0x1800e511f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e5124  xor     eax, eax
0x1800e5126  jmp     short loc_1800E5162
0x1800e5128  mov     rcx, [rsp+78h]; this
0x1800e512d  mov     r9d, eax; char *
0x1800e5130  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e5137  mov     edx, 32h ; '2'; void *
0x1800e513c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e5141  mov     ebx, eax
0x1800e5143  lea     rcx, [rsp+78h+hkey]
0x1800e5148  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e514d  lea     rcx, [rsp+78h+var_18]
0x1800e5152  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e5157  mov     eax, ebx
0x1800e5159  jmp     short loc_1800E5162
0x1800e515b  mov     eax, [rsp+78h+pvData]
0x1800e5162  mov     rbx, [rsp+78h+arg_0]
0x1800e516a  add     rsp, 70h
0x1800e516e  pop     rdi
0x1800e516f  retn
```
