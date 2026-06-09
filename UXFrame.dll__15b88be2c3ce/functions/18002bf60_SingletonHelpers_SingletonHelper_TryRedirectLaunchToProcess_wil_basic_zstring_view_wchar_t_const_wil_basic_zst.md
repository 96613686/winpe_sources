# SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool,StandardMessage,FlowEndpointBase *)

- ea: `0x18002bf60`
- end: `0x18002c0d7`
- name: `?TryRedirectLaunchToProcess@SingletonHelper@SingletonHelpers@@KA?AW4RedirectionResult@details@2@AEBV?$basic_zstring_view@_W@wil@@0KAEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_NW4StandardMessage@@PEAVFlowEndpointBase@@@Z`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002be58`
- `0x18004b86c`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x18000e224`
- `0x18000e510`
- `0x180013174`
- `0x18002154c`
- `0x180027bf4`
- `0x1800282b8`
- `0x18002bf60`
- `0x18002c4c0`

## import_xrefs

- `USER32!IsWindow` at `0x18002c0a3`
- `USER32!IsWindow` at `0x18002c0a3`
- `USER32!AllowSetForegroundWindow` at `0x18002c02e`
- `USER32!AllowSetForegroundWindow` at `0x18002c02e`
- `USER32!GetWindowThreadProcessId` at `0x18002c014`
- `USER32!GetWindowThreadProcessId` at `0x18002c014`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bfe8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bfe8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(
        __int64 *a1,
        HKEY *a2,
        int a3,
        __int64 a4,
        int a5,
        char a6)
{
  HWND v8; // rdi
  __int64 v9; // r8
  char v10; // bl
  HKEY hkey; // [rsp+40h] [rbp-99h] BYREF
  char v13; // [rsp+48h] [rbp-91h]
  unsigned int hWnd; // [rsp+50h] [rbp-89h] BYREF
  DWORD hWnd_4; // [rsp+54h] [rbp-85h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v17[112]; // [rsp+60h] [rbp-79h] BYREF
  int v18; // [rsp+D0h] [rbp-9h]

  hkey = 0;
  SingletonHelpers::details::GetSingletonSessionSubKey(&hkey, a1, a2, 0x20019u);
  hWnd = 0;
  pcbData = 4;
  RegGetValueW(hkey, 0, L"CommunicationHWND", 0x18u, 0, &hWnd, &pcbData);
  v8 = (HWND)hWnd;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( !v8 )
    return 1;
  hWnd_4 = 0;
  if ( !GetWindowThreadProcessId((HWND)(unsigned int)v8, &hWnd_4) || a3 != hWnd_4 )
    return 1;
  AllowSetForegroundWindow(hWnd_4);
  memset_0(v17, 0, 0x88u);
  ConnectionlessEndpoint::ConnectionlessEndpoint((ConnectionlessEndpoint *)v17);
  v17[92] = a6;
  FlowEndpointBase::Initialize((__int64)v17, 0);
  v18 = 4;
  hkey = (HKEY)v17;
  v13 = 1;
  v10 = FlowEndpointBase::InvokeMessageToEndpointSync(v17, (unsigned int)v8, v9, a4);
  FlowEndpointBase::Uninitialize((FlowEndpointBase *)v17);
  FlowEndpointBase::~FlowEndpointBase((FlowEndpointBase *)v17);
  if ( v10 )
    return 0;
  else
    return (unsigned int)IsWindow(v8) + 1;
}

```

## disassembly

```asm
0x18002bf60  mov     [rsp-8+arg_10], rbx
0x18002bf65  push    rbp
0x18002bf66  push    rsi
0x18002bf67  push    rdi
0x18002bf68  lea     rbp, [rsp-27h]
0x18002bf6d  sub     rsp, 100h
0x18002bf74  mov     rax, cs:__security_cookie
0x18002bf7b  xor     rax, rsp
0x18002bf7e  mov     [rbp+37h+var_20], rax
0x18002bf82  mov     rsi, r9
0x18002bf85  mov     ebx, r8d
0x18002bf88  mov     [rsp+110h+hkey], 0
0x18002bf91  mov     r9d, 20019h
0x18002bf97  mov     r8, rdx
0x18002bf9a  mov     rdx, rcx
0x18002bf9d  lea     rcx, [rsp+110h+hkey]
0x18002bfa2  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)
0x18002bfa7  mov     dword ptr [rsp+110h+hWnd], 0
0x18002bfaf  mov     [rsp+110h+var_B8], 4
0x18002bfb7  lea     rax, [rsp+110h+var_B8]
0x18002bfbc  mov     [rsp+110h+pcbData], rax; pcbData
0x18002bfc1  lea     rax, [rsp+110h+hWnd]
0x18002bfc6  mov     [rsp+110h+pvData], rax; pvData
0x18002bfcb  mov     [rsp+110h+pdwType], 0; pdwType
0x18002bfd4  mov     r9d, 18h; dwFlags
0x18002bfda  mov     r8, cs:off_180061858; lpValue
0x18002bfe1  xor     edx, edx; lpSubKey
0x18002bfe3  mov     rcx, [rsp+110h+hkey]; hkey
0x18002bfe8  call    cs:__imp_RegGetValueW
0x18002bfee  mov     edi, dword ptr [rsp+110h+hWnd]
0x18002bff2  lea     rcx, [rsp+110h+hkey]
0x18002bff7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002bffc  test    rdi, rdi
0x18002bfff  jz      loc_18002C0B3
0x18002c005  mov     dword ptr [rsp+110h+hWnd+4], 0
0x18002c00d  lea     rdx, [rsp+110h+hWnd+4]; lpdwProcessId
0x18002c012  mov     ecx, edi; hWnd
0x18002c014  call    cs:__imp_GetWindowThreadProcessId
0x18002c01a  test    eax, eax
0x18002c01c  jz      loc_18002C0B3
0x18002c022  mov     ecx, dword ptr [rsp+110h+hWnd+4]; dwProcessId
0x18002c026  cmp     ebx, ecx
0x18002c028  jnz     loc_18002C0B3
0x18002c02e  call    cs:__imp_AllowSetForegroundWindow
0x18002c034  xor     edx, edx; Val
0x18002c036  mov     r8d, 88h; Size
0x18002c03c  lea     rcx, [rbp+37h+var_B0]; void *
0x18002c040  call    memset_0
0x18002c045  lea     rcx, [rbp+37h+var_B0]; this
0x18002c049  call    ??0ConnectionlessEndpoint@@QEAA@XZ; ConnectionlessEndpoint::ConnectionlessEndpoint(void)
0x18002c04e  nop
0x18002c04f  mov     al, [rbp+37h+arg_28]
0x18002c052  mov     [rbp+37h+var_54], al
0x18002c055  xor     edx, edx
0x18002c057  lea     rcx, [rbp+37h+var_B0]
0x18002c05b  call    ?Initialize@FlowEndpointBase@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z; FlowEndpointBase::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)
0x18002c060  mov     [rbp+37h+var_40], 4
0x18002c067  lea     rax, [rbp+37h+var_B0]
0x18002c06b  mov     [rsp+110h+hkey], rax
0x18002c070  mov     [rsp+110h+var_C8], 1
0x18002c075  mov     r9, rsi
0x18002c078  mov     edx, edi
0x18002c07a  lea     rcx, [rbp+37h+var_B0]
0x18002c07e  call    ?InvokeMessageToEndpointSync@FlowEndpointBase@@QEAA_NPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessageToEndpointSync(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002c083  mov     bl, al
0x18002c085  lea     rcx, [rbp+37h+var_B0]; this
0x18002c089  call    ?Uninitialize@FlowEndpointBase@@QEAAXXZ; FlowEndpointBase::Uninitialize(void)
0x18002c08e  nop
0x18002c08f  lea     rcx, [rbp+37h+var_B0]; this
0x18002c093  call    ??1FlowEndpointBase@@UEAA@XZ; FlowEndpointBase::~FlowEndpointBase(void)
0x18002c098  test    bl, bl
0x18002c09a  jz      short loc_18002C0A0
0x18002c09c  xor     eax, eax
0x18002c09e  jmp     short loc_18002C0B8
0x18002c0a0  mov     rcx, rdi; hWnd
0x18002c0a3  call    cs:__imp_IsWindow
0x18002c0a9  neg     eax
0x18002c0ab  sbb     eax, eax
0x18002c0ad  neg     eax
0x18002c0af  inc     eax
0x18002c0b1  jmp     short loc_18002C0B8
0x18002c0b3  mov     eax, 1
0x18002c0b8  mov     rcx, [rbp+37h+var_20]
0x18002c0bc  xor     rcx, rsp; StackCookie
0x18002c0bf  call    __security_check_cookie
0x18002c0c4  mov     rbx, [rsp+110h+arg_10]
0x18002c0cc  add     rsp, 100h
0x18002c0d3  pop     rdi
0x18002c0d4  pop     rsi
0x18002c0d5  pop     rbp
0x18002c0d6  retn
```
