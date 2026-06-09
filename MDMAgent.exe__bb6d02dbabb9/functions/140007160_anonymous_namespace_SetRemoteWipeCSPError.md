# _anonymous_namespace_::SetRemoteWipeCSPError

- ea: `0x140007160`
- end: `0x1400073d9`
- name: `_anonymous_namespace_::SetRemoteWipeCSPError`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400029c0`
- `0x140004640`
- `0x140004ac0`
- `0x140004b94`
- `0x140005a44`
- `0x140006bf4`
- `0x140006c1c`
- `0x140007160`
- `0x1400079f8`
- `0x140007e24`
- `0x140007e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400071d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400071d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000723b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000735b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000723b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000735b`

## string_xrefs

- `0x1400071f3`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140007256`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x1400072a0`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140007301`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140007376`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
      SystemTimeString = anonymous_namespace_::GetSystemTimeString(v18);
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
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
            (const char *)(unsigned int)v7,
            dwOptionsa);
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
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
          (const char *)(unsigned int)SystemTimeString,
          dwOptionsa);
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
0x140007160  push    rbx
0x140007162  sub     rsp, 0A0h
0x140007169  mov     rax, cs:__security_cookie
0x140007170  xor     rax, rsp
0x140007173  mov     [rsp+0A8h+var_10], rax
0x14000717b  mov     dword ptr [rsp+0A8h+Data], 0
0x140007183  mov     [rsp+0A8h+hKey], 0
0x14000718c  xor     edx, edx
0x14000718e  lea     rcx, [rsp+0A8h+hKey]
0x140007193  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140007198  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1400071a1  lea     rax, [rsp+0A8h+hKey]
0x1400071a6  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1400071ab  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400071b4  mov     [rsp+0A8h+samDesired], 20006h; samDesired
0x1400071bc  mov     [rsp+0A8h+dwOptions], 0; unsigned int
0x1400071c4  xor     r9d, r9d; lpClass
0x1400071c7  xor     r8d, r8d; Reserved
0x1400071ca  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Diag"...
0x1400071d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400071d8  call    cs:__imp_RegCreateKeyExW
0x1400071df  nop     dword ptr [rax+rax+00h]
0x1400071e4  test    eax, eax
0x1400071e6  jz      short loc_140007217
0x1400071e8  mov     rcx, [rsp+0A8h]; this
0x1400071f0  mov     r9d, eax; char *
0x1400071f3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400071fa  mov     edx, 9Fh; void *
0x1400071ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140007204  mov     ebx, eax
0x140007206  lea     rcx, [rsp+0A8h+hKey]
0x14000720b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140007210  mov     eax, ebx
0x140007212  jmp     loc_1400073BF
0x140007217  mov     r9d, 4; dwType
0x14000721d  mov     [rsp+0A8h+samDesired], r9d; cbData
0x140007222  lea     rax, [rsp+0A8h+Data]
0x140007227  mov     qword ptr [rsp+0A8h+dwOptions], rax; int
0x14000722c  xor     r8d, r8d; Reserved
0x14000722f  lea     rdx, ValueName; "Error"
0x140007236  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14000723b  call    cs:__imp_RegSetValueExW
0x140007242  nop     dword ptr [rax+rax+00h]
0x140007247  test    eax, eax
0x140007249  jz      short loc_14000727A
0x14000724b  mov     rcx, [rsp+0A8h]; this
0x140007253  mov     r9d, eax; char *
0x140007256  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x14000725d  mov     edx, 0A7h; void *
0x140007262  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140007267  mov     ebx, eax
0x140007269  lea     rcx, [rsp+0A8h+hKey]
0x14000726e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140007273  mov     eax, ebx
0x140007275  jmp     loc_1400073BF
0x14000727a  lea     rcx, [rsp+0A8h+var_30]
0x14000727f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140007284  nop
0x140007285  lea     rcx, [rsp+0A8h+var_30]
0x14000728a  call    _anonymous_namespace___GetSystemTimeString
0x14000728f  mov     ebx, eax
0x140007291  test    eax, eax
0x140007293  jns     short loc_1400072CE
0x140007295  mov     rcx, [rsp+0A8h]; this
0x14000729d  mov     r9d, eax; char *
0x1400072a0  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400072a7  mov     edx, 0ABh; void *
0x1400072ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400072b1  nop
0x1400072b2  lea     rcx, [rsp+0A8h+var_30]; void *
0x1400072b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400072bc  nop
0x1400072bd  lea     rcx, [rsp+0A8h+hKey]
0x1400072c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400072c7  mov     eax, ebx
0x1400072c9  jmp     loc_1400073BF
0x1400072ce  mov     [rsp+0A8h+cbData], 0
0x1400072d6  mov     rcx, [rsp+0A8h+var_20]
0x1400072de  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x1400072e6  lea     rdx, [rsp+0A8h+cbData]; unsigned int *
0x1400072eb  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400072f0  mov     ebx, eax
0x1400072f2  test    eax, eax
0x1400072f4  jns     short loc_14000732F
0x1400072f6  mov     rcx, [rsp+0A8h]; this
0x1400072fe  mov     r9d, eax; char *
0x140007301  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140007308  mov     edx, 0AFh; void *
0x14000730d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007312  nop
0x140007313  lea     rcx, [rsp+0A8h+var_30]; void *
0x140007318  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000731d  nop
0x14000731e  lea     rcx, [rsp+0A8h+hKey]
0x140007323  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140007328  mov     eax, ebx
0x14000732a  jmp     loc_1400073BF
0x14000732f  lea     rcx, [rsp+0A8h+var_30]
0x140007334  call    ?data@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAGXZ; std::wstring::data(void)
0x140007339  mov     edx, [rsp+0A8h+cbData]
0x14000733d  mov     [rsp+0A8h+samDesired], edx; cbData
0x140007341  mov     qword ptr [rsp+0A8h+dwOptions], rax; unsigned int
0x140007346  mov     r9d, 1; dwType
0x14000734c  xor     r8d, r8d; Reserved
0x14000734f  lea     rdx, aTime; "Time"
0x140007356  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14000735b  call    cs:__imp_RegSetValueExW
0x140007362  nop     dword ptr [rax+rax+00h]
0x140007367  test    eax, eax
0x140007369  jz      short loc_1400073A2
0x14000736b  mov     rcx, [rsp+0A8h]; this
0x140007373  mov     r9d, eax; char *
0x140007376  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x14000737d  mov     edx, 0B7h; void *
0x140007382  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140007387  mov     ebx, eax
0x140007389  lea     rcx, [rsp+0A8h+var_30]; void *
0x14000738e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007393  nop
0x140007394  lea     rcx, [rsp+0A8h+hKey]
0x140007399  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000739e  mov     eax, ebx
0x1400073a0  jmp     short loc_1400073BF
0x1400073a2  lea     rcx, [rsp+0A8h+var_30]; void *
0x1400073a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400073ac  nop
0x1400073ad  lea     rcx, [rsp+0A8h+hKey]
0x1400073b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400073b7  xor     eax, eax
0x1400073b9  jmp     short loc_1400073BF
0x1400073bb  mov     eax, dword ptr [rsp+0A8h+Data]
0x1400073bf  mov     rcx, [rsp+0A8h+var_10]
0x1400073c7  xor     rcx, rsp; StackCookie
0x1400073ca  call    __security_check_cookie
0x1400073cf  add     rsp, 0A0h
0x1400073d6  pop     rbx
0x1400073d7  retn
```
