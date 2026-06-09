# RunHost(void)

- ea: `0x140001d80`
- end: `0x1400021cd`
- name: `?RunHost@@YAJXZ`
- size: `1101`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001d60`

## callees

- `0x140001d80`
- `0x1400025a0`
- `0x140002a14`
- `0x140002ce0`
- `0x14000347c`
- `0x14000a26c`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140001f41`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140001f41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140002094`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140002094`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140001d97`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140001d97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400020d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400021b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400020d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400021b0`
- `UxTheme!__imp_SetPreferredAppMode` at `0x140002086`
- `UxTheme!__imp_SetPreferredAppMode` at `0x140002086`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001ded`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001eee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001ded`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001eee`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000209d`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000209d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140001e47`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140001e47`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140001f8f`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140001f8f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001da4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001da4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140001fe1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000206c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400020f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002135`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400021c0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140001fe1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000206c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400020f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002135`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400021c0`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x140001f5b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1400020a7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x140001f5b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1400020a7`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x140001dfb`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x140001dfb`

## pseudocode

```c
__int64 RunHost(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HRESULT v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  char *v5; // rdi
  LPUNKNOWN v6; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  __int64 v8; // rdx
  LPUNKNOWN v9; // rcx
  HRESULT Instance; // ebx
  __int64 v11; // rax
  HANDLE Event; // rax
  const char *v13; // r9
  void *v14; // rdi
  int v15; // eax
  unsigned int v16; // ebx
  HRESULT v17; // eax
  LPUNKNOWN v18; // rcx
  int *v19; // rbx
  LPUNKNOWN v20; // rdx
  LPUNKNOWN v21; // rcx
  LPUNKNOWN v22; // rcx
  LPUNKNOWN v24; // rdx
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  int ppvb; // [rsp+20h] [rbp-28h]
  int v28; // [rsp+30h] [rbp-18h] BYREF
  __int64 v29; // [rsp+38h] [rbp-10h]
  char v30; // [rsp+40h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  DWORD dwRegister; // [rsp+88h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+90h] [rbp+48h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+98h] [rbp+50h] BYREF

  SetProcessShutdownParameters(2u, 0);
  v0 = CoInitializeEx(0, 4u);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"pcshell\\shell\\applicationframe\\host\\host.cpp",
      (const char *)(unsigned int)v0,
      ppv);
    return v1;
  }
  v28 = 1;
  v29 = 2;
  ppunkMarshal = 0;
  if ( CoCreateInstance(
         &CLSID_GlobalOptions,
         0,
         1u,
         &GUID_0000015b_0000_0000_c000_000000000046,
         (LPVOID *)&ppunkMarshal) >= 0 )
  {
    v19 = &v28;
    do
    {
      ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD))ppunkMarshal->lpVtbl[1].QueryInterface)(
        ppunkMarshal,
        (unsigned int)*v19,
        *((_QWORD *)v19 + 1));
      v19 += 4;
    }
    while ( v19 != (int *)&v30 );
    ((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->Release)(ppunkMarshal);
  }
  v2 = DXGIDeclareAdapterRemovalSupport();
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, ppva);
  pUnk = 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    Instance = -2147024882;
    goto LABEL_35;
  }
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)v5 + 4) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v6 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v8 = *((_QWORD *)v5 + 4);
    if ( v8 )
    {
      *((_QWORD *)v5 + 4) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v6,
      &GUID_00000003_0000_0000_c000_000000000046,
      v5 + 32);
  }
  v9 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v9->lpVtbl->Release)(v9);
  }
  *((_DWORD *)v5 + 11) = 1;
  *((_DWORD *)v5 + 13) = 4;
  *(_QWORD *)v5 = &CSingletonEnforcingClassFactory::`vftable'{for `IClassFactory'};
  *((_QWORD *)v5 + 1) = &CSingletonEnforcingClassFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)v5 + 7) = 0;
  Instance = CoCreateInstance(
               &GUID_ddc05a5a_351a_4e06_8eaf_54ec1bc2dcea,
               0,
               1u,
               &GUID_a914f499_4633_4b26_a93e_707eb5bdc0b6,
               (LPVOID *)v5 + 7);
  v11 = *(_QWORD *)v5;
  if ( Instance < 0 )
  {
    (*(void (__fastcall **)(char *))(v11 + 16))(v5);
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"pcshell\\shell\\applicationframe\\host\\host.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    v24 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v24->lpVtbl->Release)(v24);
    }
    goto LABEL_37;
  }
  Instance = (*(__int64 (__fastcall **)(char *, GUID *, LPUNKNOWN *))v11)(
               v5,
               &GUID_00000001_0000_0000_c000_000000000046,
               &pUnk);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( Instance < 0 )
    goto LABEL_35;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  v14 = Event;
  if ( !Event )
  {
    Instance = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3A,
                 (unsigned int)"pcshell\\shell\\applicationframe\\host\\host.cpp",
                 v13);
    v20 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v20->lpVtbl->Release)(v20);
    }
    goto LABEL_37;
  }
  v15 = CoRegisterServerShutdownDelay(Event, 60000);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"pcshell\\shell\\applicationframe\\host\\host.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    if ( v14 != (void *)-1LL )
      CloseHandle(v14);
    Microsoft::WRL::ComPtr<IMarshal>::InternalRelease(&pUnk);
    CoUninitialize();
    return v16;
  }
  else
  {
    dwRegister = 0;
    v17 = CoRegisterClassObject(&GUID_b9b05098_3e30_483f_87f7_027ca78da287, pUnk, 4u, 1u, &dwRegister);
    Instance = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"pcshell\\shell\\applicationframe\\host\\host.cpp",
        (const char *)(unsigned int)v17,
        ppvb);
      if ( v14 != (void *)-1LL )
        CloseHandle(v14);
      v18 = pUnk;
      if ( pUnk )
      {
        pUnk = 0;
        ((void (__fastcall *)(LPUNKNOWN))v18->lpVtbl->Release)(v18);
      }
LABEL_37:
      CoUninitialize();
      return (unsigned int)Instance;
    }
    SetPreferredAppMode(1);
    WaitForSingleObject(v14, 0xFFFFFFFF);
    CoRevokeClassObject(dwRegister);
    CoRegisterServerShutdownDelay(0, 0);
    v21 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v21->lpVtbl->Release)(v21);
    }
    if ( v14 != (void *)-1LL )
      CloseHandle(v14);
    v22 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v22->lpVtbl->Release)(v22);
    }
    CoUninitialize();
    return 0;
  }
}

```

## disassembly

```asm
0x140001d80  push    rbp
0x140001d82  push    rbx
0x140001d83  push    rsi
0x140001d84  push    rdi
0x140001d85  push    r14
0x140001d87  push    r15
0x140001d89  mov     rbp, rsp
0x140001d8c  sub     rsp, 48h
0x140001d90  xor     edx, edx; dwFlags
0x140001d92  mov     ecx, 2; dwLevel
0x140001d97  call    cs:__imp_SetProcessShutdownParameters
0x140001d9d  mov     edx, 4; dwCoInit
0x140001da2  xor     ecx, ecx; pvReserved
0x140001da4  call    cs:__imp_CoInitializeEx
0x140001daa  mov     ebx, eax
0x140001dac  test    eax, eax
0x140001dae  js      loc_14000214A
0x140001db4  mov     [rbp+arg_1], 1
0x140001db8  mov     [rbp+var_18], 1
0x140001dbf  mov     [rbp+var_10], 2
0x140001dc7  xor     r15d, r15d
0x140001dca  mov     [rbp+ppunkMarshal], r15
0x140001dce  lea     rax, [rbp+ppunkMarshal]
0x140001dd2  mov     qword ptr [rsp+48h+ppv], rax; int
0x140001dd7  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140001dde  xor     edx, edx; pUnkOuter
0x140001de0  mov     r8d, 1; dwClsContext
0x140001de6  lea     rcx, CLSID_GlobalOptions; rclsid
0x140001ded  call    cs:__imp_CoCreateInstance
0x140001df3  test    eax, eax
0x140001df5  jns     loc_140001FF6
0x140001dfb  call    cs:__imp_DXGIDeclareAdapterRemovalSupport
0x140001e01  mov     rcx, [rbp+30h]; this
0x140001e05  test    eax, eax
0x140001e07  js      loc_140002169
0x140001e0d  mov     [rbp+pUnk], r15
0x140001e11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140001e18  mov     ecx, 40h ; '@'; unsigned __int64
0x140001e1d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140001e22  mov     rdi, rax
0x140001e25  test    rax, rax
0x140001e28  jz      loc_140002176
0x140001e2e  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140001e35  mov     [rdi+8], rax
0x140001e39  mov     [rdi+20h], r15
0x140001e3d  mov     [rbp+ppunkMarshal], r15
0x140001e41  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x140001e45  xor     ecx, ecx; punkOuter
0x140001e47  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140001e4d  test    eax, eax
0x140001e4f  js      short loc_140001E8F
0x140001e51  mov     rbx, [rbp+ppunkMarshal]
0x140001e55  mov     rax, [rbx]
0x140001e58  mov     r14, [rax]
0x140001e5b  mov     rdx, [rdi+20h]
0x140001e5f  test    rdx, rdx
0x140001e62  jz      short loc_140001E78
0x140001e64  mov     [rdi+20h], r15
0x140001e68  mov     rcx, [rdx]
0x140001e6b  mov     rax, [rcx+10h]
0x140001e6f  mov     rcx, rdx
0x140001e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e77  nop
0x140001e78  lea     r8, [rdi+20h]
0x140001e7c  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140001e83  mov     rcx, rbx
0x140001e86  mov     rax, r14
0x140001e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e8e  nop
0x140001e8f  mov     rcx, [rbp+ppunkMarshal]
0x140001e93  test    rcx, rcx
0x140001e96  jz      short loc_140001EA9
0x140001e98  mov     [rbp+ppunkMarshal], r15
0x140001e9c  mov     rax, [rcx]
0x140001e9f  mov     rax, [rax+10h]
0x140001ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ea8  nop
0x140001ea9  mov     dword ptr [rdi+2Ch], 1
0x140001eb0  mov     dword ptr [rdi+34h], 4
0x140001eb7  lea     rax, ??_7CSingletonEnforcingClassFactory@@6BIClassFactory@@@; const CSingletonEnforcingClassFactory::`vftable'{for `IClassFactory'}
0x140001ebe  mov     [rdi], rax
0x140001ec1  lea     rax, ??_7CSingletonEnforcingClassFactory@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const CSingletonEnforcingClassFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x140001ec8  mov     [rdi+8], rax
0x140001ecc  lea     rax, [rdi+38h]
0x140001ed0  mov     [rax], r15
0x140001ed3  mov     qword ptr [rsp+48h+ppv], rax; int
0x140001ed8  lea     r9, _GUID_a914f499_4633_4b26_a93e_707eb5bdc0b6; riid
0x140001edf  xor     edx, edx; pUnkOuter
0x140001ee1  mov     r8d, 1; dwClsContext
0x140001ee7  lea     rcx, _GUID_ddc05a5a_351a_4e06_8eaf_54ec1bc2dcea; rclsid
0x140001eee  call    cs:__imp_CoCreateInstance
0x140001ef4  mov     ebx, eax
0x140001ef6  mov     rax, [rdi]
0x140001ef9  test    ebx, ebx
0x140001efb  js      loc_14000217D
0x140001f01  lea     r8, [rbp+pUnk]
0x140001f05  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x140001f0c  mov     rcx, rdi
0x140001f0f  mov     rax, [rax]
0x140001f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f17  mov     ebx, eax
0x140001f19  mov     rax, [rdi]
0x140001f1c  mov     rcx, rdi
0x140001f1f  mov     rax, [rax+10h]
0x140001f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f28  nop
0x140001f29  test    ebx, ebx
0x140001f2b  js      loc_1400020FF
0x140001f31  xor     edx, edx; lpName
0x140001f33  xor     ecx, ecx; lpEventAttributes
0x140001f35  mov     r9d, 1F0003h; dwDesiredAccess
0x140001f3b  mov     r8d, 1; dwFlags
0x140001f41  call    cs:__imp_CreateEventExW
0x140001f47  mov     rdi, rax
0x140001f4a  test    rax, rax
0x140001f4d  jz      loc_140002038
0x140001f53  mov     edx, 0EA60h
0x140001f58  mov     rcx, rax
0x140001f5b  call    cs:__imp_CoRegisterServerShutdownDelay
0x140001f61  mov     ebx, eax
0x140001f63  test    eax, eax
0x140001f65  js      loc_14000218F
0x140001f6b  mov     [rbp+dwRegister], r15d
0x140001f6f  lea     rax, [rbp+dwRegister]
0x140001f73  mov     qword ptr [rsp+48h+ppv], rax; int
0x140001f78  mov     r9d, 1; flags
0x140001f7e  mov     r8d, 4; dwClsContext
0x140001f84  mov     rdx, [rbp+pUnk]; pUnk
0x140001f88  lea     rcx, _GUID_b9b05098_3e30_483f_87f7_027ca78da287; rclsid
0x140001f8f  call    cs:__imp_CoRegisterClassObject
0x140001f95  mov     ebx, eax
0x140001f97  test    eax, eax
0x140001f99  jns     loc_140002081
0x140001f9f  mov     rcx, [rbp+30h]; this
0x140001fa3  mov     r9d, eax; char *
0x140001fa6  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\host"...
0x140001fad  mov     edx, 42h ; 'B'; void *
0x140001fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001fb7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140001fbb  jz      short loc_140001FC7
0x140001fbd  mov     rcx, rdi; hObject
0x140001fc0  call    cs:__imp_CloseHandle
0x140001fc6  nop
0x140001fc7  mov     rcx, [rbp+pUnk]
0x140001fcb  test    rcx, rcx
0x140001fce  jz      short loc_140001FE1
0x140001fd0  mov     [rbp+pUnk], r15
0x140001fd4  mov     rax, [rcx]
0x140001fd7  mov     rax, [rax+10h]
0x140001fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fe0  nop
0x140001fe1  call    cs:__imp_CoUninitialize
0x140001fe7  mov     eax, ebx
0x140001fe9  add     rsp, 48h
0x140001fed  pop     r15
0x140001fef  pop     r14
0x140001ff1  pop     rdi
0x140001ff2  pop     rsi
0x140001ff3  pop     rbx
0x140001ff4  pop     rbp
0x140001ff5  retn
0x140001ff6  lea     rbx, [rbp+var_18]
0x140001ffa  nop     word ptr [rax+rax+00h]
0x140002000  mov     rcx, [rbp+ppunkMarshal]
0x140002004  mov     rax, [rcx]
0x140002007  mov     r8, [rbx+8]
0x14000200b  mov     edx, [rbx]
0x14000200d  mov     rax, [rax+18h]
0x140002011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002016  add     rbx, 10h
0x14000201a  lea     rax, [rbp+var_8]
0x14000201e  cmp     rbx, rax
0x140002021  jnz     short loc_140002000
0x140002023  mov     rcx, [rbp+ppunkMarshal]
0x140002027  mov     rax, [rcx]
0x14000202a  mov     rax, [rax+10h]
0x14000202e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002033  jmp     loc_140001DFB
0x140002038  mov     rcx, [rbp+30h]; this
0x14000203c  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\host"...
0x140002043  mov     edx, 3Ah ; ':'; void *
0x140002048  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000204d  mov     ebx, eax
0x14000204f  mov     rdx, [rbp+pUnk]
0x140002053  test    rdx, rdx
0x140002056  jz      short loc_14000206C
0x140002058  mov     [rbp+pUnk], r15
0x14000205c  mov     rcx, [rdx]
0x14000205f  mov     rax, [rcx+10h]
0x140002063  mov     rcx, rdx
0x140002066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000206b  nop
0x14000206c  call    cs:__imp_CoUninitialize
0x140002072  mov     eax, ebx
0x140002074  add     rsp, 48h
0x140002078  pop     r15
0x14000207a  pop     r14
0x14000207c  pop     rdi
0x14000207d  pop     rsi
0x14000207e  pop     rbx
0x14000207f  pop     rbp
0x140002080  retn
0x140002081  mov     ecx, 1
0x140002086  call    cs:__imp_SetPreferredAppMode
0x14000208c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140002091  mov     rcx, rdi; hHandle
0x140002094  call    cs:__imp_WaitForSingleObject
0x14000209a  mov     ecx, [rbp+dwRegister]; dwRegister
0x14000209d  call    cs:__imp_CoRevokeClassObject
0x1400020a3  xor     edx, edx
0x1400020a5  xor     ecx, ecx
0x1400020a7  call    cs:__imp_CoRegisterServerShutdownDelay
0x1400020ad  nop
0x1400020ae  mov     rcx, [rbp+pUnk]
0x1400020b2  test    rcx, rcx
0x1400020b5  jz      short loc_1400020C8
0x1400020b7  mov     [rbp+pUnk], r15
0x1400020bb  mov     rax, [rcx]
0x1400020be  mov     rax, [rax+10h]
0x1400020c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020c7  nop
0x1400020c8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400020cc  jz      short loc_1400020D8
0x1400020ce  mov     rcx, rdi; hObject
0x1400020d1  call    cs:__imp_CloseHandle
0x1400020d7  nop
0x1400020d8  mov     rcx, [rbp+pUnk]
0x1400020dc  test    rcx, rcx
0x1400020df  jz      short loc_1400020F2
0x1400020e1  mov     [rbp+pUnk], r15
0x1400020e5  mov     rax, [rcx]
0x1400020e8  mov     rax, [rax+10h]
0x1400020ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020f1  nop
0x1400020f2  call    cs:__imp_CoUninitialize
0x1400020f8  xor     eax, eax
0x1400020fa  jmp     loc_140001FE9
0x1400020ff  mov     rcx, [rbp+30h]; this
0x140002103  mov     r9d, ebx; char *
0x140002106  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\host"...
0x14000210d  mov     edx, 36h ; '6'; void *
0x140002112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002117  nop
0x140002118  mov     rdx, [rbp+pUnk]
0x14000211c  test    rdx, rdx
0x14000211f  jz      short loc_140002135
0x140002121  mov     [rbp+pUnk], r15
0x140002125  mov     rcx, [rdx]
0x140002128  mov     rax, [rcx+10h]
0x14000212c  mov     rcx, rdx
0x14000212f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002134  nop
0x140002135  call    cs:__imp_CoUninitialize
0x14000213b  mov     eax, ebx
0x14000213d  add     rsp, 48h
0x140002141  pop     r15
0x140002143  pop     r14
0x140002145  pop     rdi
0x140002146  pop     rsi
0x140002147  pop     rbx
0x140002148  pop     rbp
0x140002149  retn
0x14000214a  mov     rcx, [rbp+30h]; this
0x14000214e  mov     r9d, ebx; char *
0x140002151  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\host"...
0x140002158  mov     edx, 26h ; '&'; void *
0x14000215d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002162  mov     eax, ebx
0x140002164  jmp     loc_140001FE9
0x140002169  mov     r9d, eax; char *
0x14000216c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140002171  jmp     loc_140001E0D
0x140002176  mov     ebx, 8007000Eh
0x14000217b  jmp     short loc_1400020FF
0x14000217d  mov     rcx, rdi
0x140002180  mov     rax, [rax+10h]
0x140002184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002189  nop
0x14000218a  jmp     loc_1400020FF
0x14000218f  mov     rcx, [rbp+30h]; this
0x140002193  mov     r9d, ebx; char *
0x140002196  lea     r8, aPcshellShellAp_0; "pcshell\\shell\\applicationframe\\host"...
0x14000219d  mov     edx, 3Eh ; '>'; void *
0x1400021a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400021a7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400021ab  jz      short loc_1400021B6
0x1400021ad  mov     rcx, rdi; hObject
0x1400021b0  call    cs:__imp_CloseHandle
0x1400021b6  lea     rcx, [rbp+pUnk]
0x1400021ba  call    ?InternalRelease@?$ComPtr@UIMarshal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMarshal>::InternalRelease(void)
0x1400021bf  nop
0x1400021c0  call    cs:__imp_CoUninitialize
0x1400021c6  mov     eax, ebx
0x1400021c8  jmp     loc_140001FE9
```
