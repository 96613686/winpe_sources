# _anonymous_namespace_::SetRemoteWipeCSPError

- ea: `0x140006ec0`
- end: `0x140007127`
- name: `_anonymous_namespace_::SetRemoteWipeCSPError`
- size: `615`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140002930`
- `0x140004578`
- `0x140004a40`
- `0x140004b0c`
- `0x140005888`
- `0x140006984`
- `0x1400069a8`
- `0x140006ec0`
- `0x140007724`
- `0x140007b20`
- `0x140007b34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006f38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006f38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006f95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400070af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006f95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400070af`

## string_xrefs

- `0x140006f4d`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140006faa`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140006ff4`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140007055`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x1400070c4`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 anonymous_namespace_::SetRemoteWipeCSPError()
{
  unsigned int Key; // eax
  unsigned int v1; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int SystemTimeString; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  const BYTE *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-88h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-88h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-88h]
  HKEY hKey[2]; // [rsp+50h] [rbp-58h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-38h] BYREF
  _BYTE v18[16]; // [rsp+78h] [rbp-30h] BYREF
  __int64 v19; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *(_DWORD *)Data = 0;
  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Provisioning\\Diagnostics\\RemoteWipe",
          0,
          0,
          0,
          0x20006u,
          0,
          hKey,
          0);
  if ( Key )
  {
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9F,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
           (const char *)Key,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v1;
  }
  else
  {
    v3 = RegSetValueExW(hKey[0], L"Error", 0, 4u, Data, 4u);
    if ( v3 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA7,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
             (const char *)v3,
             dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
      return v4;
    }
    else
    {
      std::wstring::wstring(v18);
      SystemTimeString = anonymous_namespace_::GetSystemTimeString((__int64)v18);
      v6 = SystemTimeString;
      if ( SystemTimeString >= 0 )
      {
        cbData = 0;
        v7 = ULongLongToULong(2 * v19 + 2, &cbData);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v9 = (const BYTE *)std::wstring::data(v18);
          v10 = RegSetValueExW(hKey[0], L"Time", 0, 1u, v9, cbData);
          if ( v10 )
          {
            v11 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xB7,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
                    (const char *)v10,
                    dwOptionsb);
            std::wstring::~wstring(v18);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
            return v11;
          }
          else
          {
            std::wstring::~wstring(v18);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
            return 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF,
            (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
            (const char *)(unsigned int)v7);
          std::wstring::~wstring(v18);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
          return v8;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
          (const char *)(unsigned int)SystemTimeString);
        std::wstring::~wstring(v18);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
        return v6;
      }
    }
  }
}

```

## disassembly

```asm
0x140006ec0  push    rbx
0x140006ec2  sub     rsp, 0A0h
0x140006ec9  mov     rax, cs:__security_cookie
0x140006ed0  xor     rax, rsp
0x140006ed3  mov     [rsp+0A8h+var_10], rax
0x140006edb  mov     dword ptr [rsp+0A8h+Data], 0
0x140006ee3  mov     [rsp+0A8h+hKey], 0
0x140006eec  xor     edx, edx
0x140006eee  lea     rcx, [rsp+0A8h+hKey]
0x140006ef3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140006ef8  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x140006f01  lea     rax, [rsp+0A8h+hKey]
0x140006f06  mov     [rsp+0A8h+phkResult], rax; phkResult
0x140006f0b  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140006f14  mov     [rsp+0A8h+samDesired], 20006h; samDesired
0x140006f1c  mov     [rsp+0A8h+dwOptions], 0; unsigned int
0x140006f24  xor     r9d, r9d; lpClass
0x140006f27  xor     r8d, r8d; Reserved
0x140006f2a  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Diag"...
0x140006f31  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006f38  call    cs:__imp_RegCreateKeyExW
0x140006f3e  test    eax, eax
0x140006f40  jz      short loc_140006F71
0x140006f42  mov     rcx, [rsp+0A8h]; this
0x140006f4a  mov     r9d, eax; char *
0x140006f4d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140006f54  mov     edx, 9Fh; void *
0x140006f59  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140006f5e  mov     ebx, eax
0x140006f60  lea     rcx, [rsp+0A8h+hKey]
0x140006f65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140006f6a  mov     eax, ebx
0x140006f6c  jmp     loc_14000710D
0x140006f71  mov     r9d, 4; dwType
0x140006f77  mov     [rsp+0A8h+samDesired], r9d; cbData
0x140006f7c  lea     rax, [rsp+0A8h+Data]
0x140006f81  mov     qword ptr [rsp+0A8h+dwOptions], rax; int
0x140006f86  xor     r8d, r8d; Reserved
0x140006f89  lea     rdx, ValueName; "Error"
0x140006f90  mov     rcx, [rsp+0A8h+hKey]; hKey
0x140006f95  call    cs:__imp_RegSetValueExW
0x140006f9b  test    eax, eax
0x140006f9d  jz      short loc_140006FCE
0x140006f9f  mov     rcx, [rsp+0A8h]; this
0x140006fa7  mov     r9d, eax; char *
0x140006faa  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140006fb1  mov     edx, 0A7h; void *
0x140006fb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140006fbb  mov     ebx, eax
0x140006fbd  lea     rcx, [rsp+0A8h+hKey]
0x140006fc2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140006fc7  mov     eax, ebx
0x140006fc9  jmp     loc_14000710D
0x140006fce  lea     rcx, [rsp+0A8h+var_30]
0x140006fd3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140006fd8  nop
0x140006fd9  lea     rcx, [rsp+0A8h+var_30]
0x140006fde  call    _anonymous_namespace___GetSystemTimeString
0x140006fe3  mov     ebx, eax
0x140006fe5  test    eax, eax
0x140006fe7  jns     short loc_140007022
0x140006fe9  mov     rcx, [rsp+0A8h]; this
0x140006ff1  mov     r9d, eax; char *
0x140006ff4  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140006ffb  mov     edx, 0ABh; void *
0x140007000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007005  nop
0x140007006  lea     rcx, [rsp+0A8h+var_30]; void *
0x14000700b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007010  nop
0x140007011  lea     rcx, [rsp+0A8h+hKey]
0x140007016  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000701b  mov     eax, ebx
0x14000701d  jmp     loc_14000710D
0x140007022  mov     [rsp+0A8h+cbData], 0
0x14000702a  mov     rcx, [rsp+0A8h+var_20]
0x140007032  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x14000703a  lea     rdx, [rsp+0A8h+cbData]; unsigned int *
0x14000703f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140007044  mov     ebx, eax
0x140007046  test    eax, eax
0x140007048  jns     short loc_140007083
0x14000704a  mov     rcx, [rsp+0A8h]; this
0x140007052  mov     r9d, eax; char *
0x140007055  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x14000705c  mov     edx, 0AFh; void *
0x140007061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007066  nop
0x140007067  lea     rcx, [rsp+0A8h+var_30]; void *
0x14000706c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007071  nop
0x140007072  lea     rcx, [rsp+0A8h+hKey]
0x140007077  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000707c  mov     eax, ebx
0x14000707e  jmp     loc_14000710D
0x140007083  lea     rcx, [rsp+0A8h+var_30]
0x140007088  call    ?data@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAGXZ; std::wstring::data(void)
0x14000708d  mov     edx, [rsp+0A8h+cbData]
0x140007091  mov     [rsp+0A8h+samDesired], edx; cbData
0x140007095  mov     qword ptr [rsp+0A8h+dwOptions], rax; unsigned int
0x14000709a  mov     r9d, 1; dwType
0x1400070a0  xor     r8d, r8d; Reserved
0x1400070a3  lea     rdx, aTime; "Time"
0x1400070aa  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1400070af  call    cs:__imp_RegSetValueExW
0x1400070b5  test    eax, eax
0x1400070b7  jz      short loc_1400070F0
0x1400070b9  mov     rcx, [rsp+0A8h]; this
0x1400070c1  mov     r9d, eax; char *
0x1400070c4  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400070cb  mov     edx, 0B7h; void *
0x1400070d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400070d5  mov     ebx, eax
0x1400070d7  lea     rcx, [rsp+0A8h+var_30]; void *
0x1400070dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400070e1  nop
0x1400070e2  lea     rcx, [rsp+0A8h+hKey]
0x1400070e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400070ec  mov     eax, ebx
0x1400070ee  jmp     short loc_14000710D
0x1400070f0  lea     rcx, [rsp+0A8h+var_30]; void *
0x1400070f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400070fa  nop
0x1400070fb  lea     rcx, [rsp+0A8h+hKey]
0x140007100  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140007105  xor     eax, eax
0x140007107  jmp     short loc_14000710D
0x140007109  mov     eax, dword ptr [rsp+0A8h+Data]
0x14000710d  mov     rcx, [rsp+0A8h+var_10]
0x140007115  xor     rcx, rsp; StackCookie
0x140007118  call    __security_check_cookie
0x14000711d  add     rsp, 0A0h
0x140007124  pop     rbx
0x140007125  retn
```
