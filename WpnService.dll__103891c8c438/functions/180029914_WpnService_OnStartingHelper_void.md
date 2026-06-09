# WpnService::OnStartingHelper(void)

- ea: `0x180029914`
- end: `0x180029aa9`
- name: `?OnStartingHelper@WpnService@@AEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800298d0`

## callees

- `0x180003190`
- `0x1800202bc`
- `0x180020ee4`
- `0x18002867c`
- `0x180029914`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002994b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800299b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002994b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800299b3`
- `combase!__imp_CoGetSharedServiceId` at `0x1800299f8`
- `combase!__imp_CoGetSharedServiceId` at `0x1800299f8`

## string_xrefs

- `0x180029a64`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::OnStartingHelper(LPVOID *this)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int ppv; // [rsp+20h] [rbp-48h]
  _QWORD v7[2]; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v8[2]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID v10; // [rsp+70h] [rbp+8h] BYREF

  v10 = 0;
  Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v10);
  v3 = Instance;
  if ( Instance < 0 )
  {
    v4 = 138;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(&v10);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 24);
    return v3;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, 5, 1);
  v3 = Instance;
  if ( Instance < 0 )
  {
    v4 = 139;
    goto LABEL_11;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 24);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, this + 24);
  v3 = Instance;
  if ( Instance < 0 )
  {
    v4 = 145;
    goto LABEL_11;
  }
  v7[0] = this + 25;
  v7[1] = this;
  v8[0] = 0;
  v8[1] = v7;
  CoGetSharedServiceId((char *)module + 16);
  ppv = 5;
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)this[24] + 24LL))(
               this[24],
               WpnService::RegisterClassFactoryCallback,
               v8,
               &IID_IContextCallback);
  v3 = Instance;
  if ( Instance < 0 )
  {
    v4 = 163;
    goto LABEL_11;
  }
  (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)module + 8LL))(module);
  Instance = ConnectionManagerFactoryPrivate::Initialize();
  v3 = Instance;
  if ( Instance < 0 )
  {
    v4 = 169;
    goto LABEL_11;
  }
  wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(&v10);
  return 0;
}

```

## disassembly

```asm
0x180029914  mov     r11, rsp
0x180029917  mov     [r11+10h], rbx
0x18002991b  mov     [r11+18h], rsi
0x18002991f  push    rdi
0x180029920  sub     rsp, 60h
0x180029924  mov     rsi, rcx
0x180029927  mov     qword ptr [r11+8], 0
0x18002992f  lea     rax, [r11+8]
0x180029933  mov     [r11-48h], rax
0x180029937  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002993e  xor     edx, edx; pUnkOuter
0x180029940  lea     r8d, [rdx+1]; dwClsContext
0x180029944  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002994b  call    cs:__imp_CoCreateInstance
0x180029951  mov     ebx, eax
0x180029953  lea     rdi, [rsi+0C0h]
0x18002995a  test    eax, eax
0x18002995c  jns     short loc_180029968
0x18002995e  mov     edx, 8Ah
0x180029963  jmp     loc_180029A61
0x180029968  mov     rcx, [rsp+68h+arg_0]
0x18002996d  mov     rax, [rcx]
0x180029970  mov     edx, 5
0x180029975  lea     r8d, [rdx-4]
0x180029979  mov     rax, [rax+18h]
0x18002997d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029982  mov     ebx, eax
0x180029984  test    eax, eax
0x180029986  jns     short loc_180029992
0x180029988  mov     edx, 8Bh
0x18002998d  jmp     loc_180029A61
0x180029992  mov     rcx, rdi
0x180029995  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002999a  mov     [rsp+68h+ppv], rdi; ppv
0x18002999f  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800299a6  xor     edx, edx; pUnkOuter
0x1800299a8  lea     r8d, [rdx+1]; dwClsContext
0x1800299ac  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800299b3  call    cs:__imp_CoCreateInstance
0x1800299b9  mov     ebx, eax
0x1800299bb  test    eax, eax
0x1800299bd  jns     short loc_1800299C9
0x1800299bf  mov     edx, 91h
0x1800299c4  jmp     loc_180029A61
0x1800299c9  lea     rax, [rsi+0C8h]
0x1800299d0  mov     [rsp+68h+var_28], rax
0x1800299d5  mov     [rsp+68h+var_20], rsi
0x1800299da  mov     [rsp+68h+var_18], 0
0x1800299e3  lea     rax, [rsp+68h+var_28]
0x1800299e8  mov     [rsp+68h+var_10], rax
0x1800299ed  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; WpnServiceModule & module
0x1800299f4  add     rcx, 10h
0x1800299f8  call    cs:__imp_CoGetSharedServiceId
0x1800299fe  mov     rcx, [rdi]
0x180029a01  mov     rax, [rcx]
0x180029a04  mov     [rsp+68h+var_40], 0
0x180029a0d  mov     dword ptr [rsp+68h+ppv], 5; int
0x180029a15  lea     r9, IID_IContextCallback
0x180029a1c  lea     r8, [rsp+68h+var_18]
0x180029a21  lea     rdx, ?RegisterClassFactoryCallback@WpnService@@SAJPEAUtagComCallData@@@Z; WpnService::RegisterClassFactoryCallback(tagComCallData *)
0x180029a28  mov     rax, [rax+18h]
0x180029a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a31  mov     ebx, eax
0x180029a33  test    eax, eax
0x180029a35  jns     short loc_180029A3E
0x180029a37  mov     edx, 0A3h
0x180029a3c  jmp     short loc_180029A61
0x180029a3e  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; WpnServiceModule & module
0x180029a45  mov     rax, [rcx]
0x180029a48  mov     rax, [rax+8]
0x180029a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a51  call    ?Initialize@ConnectionManagerFactoryPrivate@@SAJXZ; ConnectionManagerFactoryPrivate::Initialize(void)
0x180029a56  mov     ebx, eax
0x180029a58  test    eax, eax
0x180029a5a  jns     short loc_180029A8B
0x180029a5c  mov     edx, 0A9h; void *
0x180029a61  mov     r9d, eax; char *
0x180029a64  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029a6b  mov     rcx, [rsp+68h]; this
0x180029a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a75  lea     rcx, [rsp+68h+arg_0]
0x180029a7a  call    ??1?$com_ptr_t@UIGlobalOptions@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(void)
0x180029a7f  mov     rcx, rdi
0x180029a82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a87  mov     eax, ebx
0x180029a89  jmp     short loc_180029A97
0x180029a8b  lea     rcx, [rsp+68h+arg_0]
0x180029a90  call    ??1?$com_ptr_t@UIGlobalOptions@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(void)
0x180029a95  xor     eax, eax
0x180029a97  lea     r11, [rsp+68h+var_8]
0x180029a9c  mov     rbx, [r11+18h]
0x180029aa0  mov     rsi, [r11+20h]
0x180029aa4  mov     rsp, r11
0x180029aa7  pop     rdi
0x180029aa8  retn
```
