# WpnService::OnStartedHelper(void)

- ea: `0x180029794`
- end: `0x1800298c1`
- name: `?OnStartedHelper@WpnService@@AEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(WpnService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029750`

## callees

- `0x180003190`
- `0x1800109d4`
- `0x180012140`
- `0x1800202bc`
- `0x18002451c`
- `0x180029794`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029822`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029822`
- `ntdll!RtlPublishWnfStateData` at `0x1800297c5`
- `ntdll!RtlPublishWnfStateData` at `0x1800297c5`

## string_xrefs

- `0x1800297da`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`
- `0x180029836`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`
- `0x18002988d`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::OnStartedHelper(WpnService *this)
{
  int v2; // eax
  LPVOID *v3; // rdi
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  int v7; // eax
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v11; // [rsp+48h] [rbp+10h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v11 = 1;
  v2 = RtlPublishWnfStateData(WNF_WPN_SYSTEM_PLATFORM_READY, 0, &v11, 4, 0) | 0x10000000;
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBC,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)(unsigned int)v2);
  if ( !IsMultiUsersInSessionSku() )
  {
    v3 = (LPVOID *)((char *)this + 208);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
    Instance = CoCreateInstance(
                 &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9,
                 0,
                 0x404u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 v3);
    v5 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      return v5;
    }
    v12 = 0;
    v7 = Microsoft::WRL::ComPtr<IWpnPlatform>::As<IWpnPlatformInternal>(
           (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v3,
           (__int64)&v12);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 199;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      return v5;
    }
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 200;
      goto LABEL_11;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180029794  mov     rax, rsp
0x180029797  mov     [rax+8], rbx
0x18002979b  push    rdi
0x18002979c  sub     rsp, 30h
0x1800297a0  mov     rdi, rcx
0x1800297a3  mov     dword ptr [rax+10h], 1
0x1800297aa  mov     qword ptr [rax-18h], 0
0x1800297b2  mov     r9d, 4
0x1800297b8  lea     r8, [rax+10h]
0x1800297bc  xor     edx, edx
0x1800297be  mov     rcx, cs:WNF_WPN_SYSTEM_PLATFORM_READY
0x1800297c5  call    cs:__imp_RtlPublishWnfStateData
0x1800297cb  or      eax, 10000000h
0x1800297d0  jge     short loc_1800297EB
0x1800297d2  mov     rcx, [rsp+38h]; this
0x1800297d7  mov     r9d, eax; char *
0x1800297da  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800297e1  mov     edx, 0BCh; void *
0x1800297e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800297eb  call    ?IsMultiUsersInSessionSku@@YA_NXZ; IsMultiUsersInSessionSku(void)
0x1800297f0  test    al, al
0x1800297f2  jnz     loc_1800298B4
0x1800297f8  add     rdi, 0D0h
0x1800297ff  mov     rcx, rdi
0x180029802  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029807  mov     qword ptr [rsp+38h+ppv], rdi; int
0x18002980c  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180029813  xor     edx, edx; pUnkOuter
0x180029815  mov     r8d, 404h; dwClsContext
0x18002981b  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x180029822  call    cs:__imp_CoCreateInstance
0x180029828  mov     ebx, eax
0x18002982a  test    eax, eax
0x18002982c  jns     short loc_18002984B
0x18002982e  mov     rcx, [rsp+38h]; this
0x180029833  mov     r9d, eax; char *
0x180029836  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002983d  mov     edx, 0C4h; void *
0x180029842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029847  mov     eax, ebx
0x180029849  jmp     short loc_1800298B6
0x18002984b  mov     [rsp+38h+arg_10], 0
0x180029854  lea     rdx, [rsp+38h+arg_10]
0x180029859  mov     rcx, rdi
0x18002985c  call    ??$As@UIWpnPlatformInternal@@@?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnPlatformInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnPlatform>::As<IWpnPlatformInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatformInternal>>)
0x180029861  mov     ebx, eax
0x180029863  test    eax, eax
0x180029865  jns     short loc_18002986E
0x180029867  mov     edx, 0C7h
0x18002986c  jmp     short loc_18002988A
0x18002986e  mov     rcx, [rsp+38h+arg_10]
0x180029873  mov     rax, [rcx]
0x180029876  mov     rax, [rax+20h]
0x18002987a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987f  mov     ebx, eax
0x180029881  test    eax, eax
0x180029883  jns     short loc_1800298AA
0x180029885  mov     edx, 0C8h; void *
0x18002988a  mov     r9d, eax; char *
0x18002988d  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029894  mov     rcx, [rsp+38h]; this
0x180029899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002989e  lea     rcx, [rsp+38h+arg_10]
0x1800298a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800298a8  jmp     short loc_180029847
0x1800298aa  lea     rcx, [rsp+38h+arg_10]
0x1800298af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800298b4  xor     eax, eax
0x1800298b6  mov     rbx, [rsp+38h+arg_0]
0x1800298bb  add     rsp, 30h
0x1800298bf  pop     rdi
0x1800298c0  retn
```
