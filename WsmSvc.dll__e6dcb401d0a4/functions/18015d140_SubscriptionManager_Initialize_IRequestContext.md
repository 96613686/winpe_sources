# SubscriptionManager::Initialize(IRequestContext &)

- ea: `0x18015d140`
- end: `0x18015d536`
- name: `?Initialize@SubscriptionManager@@UEAA_NAEAVIRequestContext@@@Z`
- size: `1014`
- prototype: `bool(SubscriptionManager *__hidden this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000fc50`
- `0x180010030`
- `0x1800621e0`
- `0x180076d18`
- `0x1800e1ef0`
- `0x1800f5280`
- `0x1801123a8`
- `0x18011a6d4`
- `0x180122da4`
- `0x18015d140`
- `0x180170c60`
- `0x1801717c8`
- `0x180175338`
- `0x18017af4c`
- `0x18017f2b8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015d440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015d440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d4b0`
- `WS2_32!__imp_WSAStartup` at `0x18015d190`
- `WS2_32!__imp_WSAStartup` at `0x18015d190`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18015d206`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18015d26c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18015d206`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18015d26c`

## string_xrefs

- `0x18015d42b`: `EventCollectorService`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall SubscriptionManager::Initialize(SubscriptionManager *this, struct IRequestContext *a2)
{
  unsigned int v4; // ecx
  DWORD LastError; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  CSoapProcessor *v9; // rax
  CSoapProcessor *v10; // rsi
  SubscriptionManagerSoapProcessor *v11; // rbx
  ConfigSoapProcessor *v12; // rax
  ConfigSoapProcessor *v13; // rbx
  DWORD v14; // eax
  void (__fastcall *v15)(struct IRequestContext *, _QWORD); // rbx
  DWORD v16; // eax
  void (__fastcall *v17)(struct IRequestContext *, _QWORD); // rbx
  DWORD v18; // eax
  CSoapProcessor *v19; // [rsp+20h] [rbp-E0h] BYREF
  CSoapProcessor *v20; // [rsp+28h] [rbp-D8h] BYREF
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int *v22; // [rsp+38h] [rbp-C8h]
  ConfigSoapProcessor *v23; // [rsp+40h] [rbp-C0h]
  struct WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v4 = WSAStartup(0x202u, &WSAData);
  if ( v4 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v4);
    return 0;
  }
  *((_BYTE *)this + 136) = 1;
  if ( !(**((unsigned __int8 (__fastcall ***)(char *, struct IRequestContext *))this + 1))((char *)this + 8, a2) )
    return 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:NSG:BAD:P(A;;GA;;;WD)S:",
          1u,
          (PSECURITY_DESCRIPTOR *)this + 13,
          0) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_10;
    v8 = 10;
LABEL_9:
    WPP_SF_d(v7[2], v8, WPP_e0807a6b15c83dd8ce14c34fc5827569_Traceguids, LastError);
LABEL_10:
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, LastError);
    return 0;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:NSG:BAD:P(D;;GA;;;WD)S:P(AU;FA;GA;;;WD)",
          1u,
          (PSECURITY_DESCRIPTOR *)this + 14,
          0) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_10;
    v8 = 11;
    goto LABEL_9;
  }
  if ( !ValidateSecurityDescriptor(a2, *((void **)this + 13)) || !ValidateSecurityDescriptor(a2, *((void **)this + 14)) )
    return 0;
  v21 = 0;
  v20 = (CSoapProcessor *)&v21;
  v9 = (CSoapProcessor *)WSManMemory::Alloc(1912, 0, 0);
  v10 = v9;
  v19 = v9;
  if ( v9 )
  {
    CSoapProcessor::CSoapProcessor(v9);
    *(_QWORD *)v10 = &EventSoapProcessor::`vftable';
    CSoapProcessor::CreateObserverFactory(v10);
  }
  else
  {
    v10 = 0;
  }
  v20 = v10;
  if ( !v10 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
    return 0;
  }
  v11 = 0;
  v19 = 0;
  if ( *((_BYTE *)this + 137) )
  {
    v21 = 0;
    v22 = &v21;
    v12 = (ConfigSoapProcessor *)WSManMemory::Alloc(6048, 0, 0);
    v13 = v12;
    v23 = v12;
    if ( v12 )
    {
      ConfigSoapProcessor::ConfigSoapProcessor(v12, L"SubscriptionManager/WEC");
      *(_QWORD *)v13 = &SubscriptionManagerSoapProcessor::`vftable'{for `CSoapProcessor'};
      *((_QWORD *)v13 + 239) = &SubscriptionManagerSoapProcessor::`vftable'{for `IServiceConfigObserver'};
      *((_QWORD *)v13 + 755) = 0;
    }
    else
    {
      v13 = 0;
    }
    AutoRelease<CServiceConfigCache>::operator=(&v19, v13);
    v11 = v19;
    if ( !v19 )
    {
      (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v19);
      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
      return 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4a94fa90dde23d5de7b70f3dffeb5ead_Traceguids, v10);
  v14 = CSoapProcessor::InternalInitialize(v10, L"EventCollectorService");
  if ( v14 )
  {
    SetLastError(v14);
LABEL_34:
    v15 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v16 = GetLastError();
    v15(a2, v16);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v19);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
    return 0;
  }
  if ( !(unsigned int)CSoapProcessor::StartHttpListening(v10, 0x1000u, 1) )
    goto LABEL_34;
  if ( v11 && !(unsigned int)SubscriptionManagerSoapProcessor::Initialize(v11, this) )
  {
    v17 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v18 = GetLastError();
    v17(a2, v18);
    EventSoapProcessor::DeInitialize(v10);
    v20 = 0;
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v19);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
    return 0;
  }
  v19 = 0;
  *((_QWORD *)this + 15) = v11;
  v20 = 0;
  *((_QWORD *)this + 16) = v10;
  WSManCreateUuidString((unsigned __int16 *const)this + 72);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v19);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
  return 1;
}

```

## disassembly

```asm
0x18015d140  mov     [rsp-8+arg_10], rbx
0x18015d145  mov     [rsp-8+arg_18], rsi
0x18015d14a  push    rbp
0x18015d14b  push    rdi
0x18015d14c  push    r14
0x18015d14e  lea     rbp, [rsp-100h]
0x18015d156  sub     rsp, 200h
0x18015d15d  mov     rax, cs:__security_cookie
0x18015d164  xor     rax, rsp
0x18015d167  mov     [rbp+110h+var_20], rax
0x18015d16e  mov     rdi, rdx
0x18015d171  mov     r14, rcx
0x18015d174  xor     edx, edx; Val
0x18015d176  mov     r8d, 198h; Size
0x18015d17c  lea     rcx, [rsp+210h+WSAData]; void *
0x18015d181  call    memset_0
0x18015d186  mov     ecx, 202h; wVersionRequested
0x18015d18b  lea     rdx, [rsp+210h+WSAData]; lpWSAData
0x18015d190  call    cs:__imp_WSAStartup
0x18015d196  mov     ecx, eax
0x18015d198  test    eax, eax
0x18015d19a  jz      short loc_18015D1D6
0x18015d19c  mov     rdx, [rdi]
0x18015d19f  mov     rax, [rdx+48h]
0x18015d1a3  mov     edx, ecx
0x18015d1a5  mov     rcx, rdi
0x18015d1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d1ad  xor     al, al
0x18015d1af  mov     rcx, [rbp+110h+var_20]
0x18015d1b6  xor     rcx, rsp; StackCookie
0x18015d1b9  call    __security_check_cookie
0x18015d1be  lea     r11, [rsp+210h+var_10]
0x18015d1c6  mov     rbx, [r11+30h]
0x18015d1ca  mov     rsi, [r11+38h]
0x18015d1ce  mov     rsp, r11
0x18015d1d1  pop     r14
0x18015d1d3  pop     rdi
0x18015d1d4  pop     rbp
0x18015d1d5  retn
0x18015d1d6  mov     byte ptr [r14+88h], 1
0x18015d1de  lea     rcx, [r14+8]
0x18015d1e2  mov     rax, [rcx]
0x18015d1e5  mov     rdx, rdi
0x18015d1e8  mov     rax, [rax]
0x18015d1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d1f0  test    al, al
0x18015d1f2  jz      short loc_18015D1AD
0x18015d1f4  xor     r9d, r9d; SecurityDescriptorSize
0x18015d1f7  lea     r8, [r14+68h]; SecurityDescriptor
0x18015d1fb  lea     edx, [r9+1]; StringSDRevision
0x18015d1ff  lea     rcx, aONsgBadPAGaWdS; "O:NSG:BAD:P(A;;GA;;;WD)S:"
0x18015d206  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18015d20c  test    eax, eax
0x18015d20e  jnz     short loc_18015D25A
0x18015d210  call    cs:__imp_GetLastError
0x18015d216  mov     ebx, eax
0x18015d218  lea     rdx, WPP_GLOBAL_Control
0x18015d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18015d226  cmp     rcx, rdx
0x18015d229  jz      short loc_18015D24C
0x18015d22b  test    dword ptr [rcx+1Ch], 8000h
0x18015d232  jz      short loc_18015D24C
0x18015d234  mov     edx, 0Ah
0x18015d239  mov     r9d, ebx
0x18015d23c  lea     r8, WPP_e0807a6b15c83dd8ce14c34fc5827569_Traceguids
0x18015d243  mov     rcx, [rcx+10h]
0x18015d247  call    WPP_SF_d
0x18015d24c  mov     rax, [rdi]
0x18015d24f  mov     edx, ebx
0x18015d251  mov     rax, [rax+48h]
0x18015d255  jmp     loc_18015D1A5
0x18015d25a  xor     r9d, r9d; SecurityDescriptorSize
0x18015d25d  lea     r8, [r14+70h]; SecurityDescriptor
0x18015d261  lea     edx, [r9+1]; StringSDRevision
0x18015d265  lea     rcx, aONsgBadPDGaWdS; "O:NSG:BAD:P(D;;GA;;;WD)S:P(AU;FA;GA;;;W"...
0x18015d26c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18015d272  test    eax, eax
0x18015d274  jnz     short loc_18015D2A1
0x18015d276  call    cs:__imp_GetLastError
0x18015d27c  mov     ebx, eax
0x18015d27e  lea     rdx, WPP_GLOBAL_Control
0x18015d285  mov     rcx, cs:WPP_GLOBAL_Control
0x18015d28c  cmp     rcx, rdx
0x18015d28f  jz      short loc_18015D24C
0x18015d291  test    dword ptr [rcx+1Ch], 8000h
0x18015d298  jz      short loc_18015D24C
0x18015d29a  mov     edx, 0Bh
0x18015d29f  jmp     short loc_18015D239
0x18015d2a1  mov     rdx, [r14+68h]; void *
0x18015d2a5  mov     rcx, rdi; struct IRequestContext *
0x18015d2a8  call    ?ValidateSecurityDescriptor@@YA_NAEAVIRequestContext@@PEAX@Z; ValidateSecurityDescriptor(IRequestContext &,void *)
0x18015d2ad  test    al, al
0x18015d2af  jz      loc_18015D1AD
0x18015d2b5  mov     rdx, [r14+70h]; void *
0x18015d2b9  mov     rcx, rdi; struct IRequestContext *
0x18015d2bc  call    ?ValidateSecurityDescriptor@@YA_NAEAVIRequestContext@@PEAX@Z; ValidateSecurityDescriptor(IRequestContext &,void *)
0x18015d2c1  test    al, al
0x18015d2c3  jz      loc_18015D1AD
0x18015d2c9  mov     [rsp+210h+var_1E0], 0
0x18015d2d1  lea     rax, [rsp+210h+var_1E0]
0x18015d2d6  mov     [rsp+210h+var_1E8], rax
0x18015d2db  xor     r8d, r8d
0x18015d2de  xor     edx, edx
0x18015d2e0  mov     ecx, 778h
0x18015d2e5  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18015d2ea  mov     rsi, rax
0x18015d2ed  mov     [rsp+210h+var_1F0], rax
0x18015d2f2  test    rax, rax
0x18015d2f5  jz      short loc_18015D315
0x18015d2f7  mov     rcx, rax; this
0x18015d2fa  call    ??0CSoapProcessor@@QEAA@XZ; CSoapProcessor::CSoapProcessor(void)
0x18015d2ff  nop
0x18015d300  lea     rax, ??_7EventSoapProcessor@@6B@; const EventSoapProcessor::`vftable'
0x18015d307  mov     [rsi], rax
0x18015d30a  mov     rcx, rsi; this
0x18015d30d  call    ?CreateObserverFactory@CSoapProcessor@@UEAAXXZ; CSoapProcessor::CreateObserverFactory(void)
0x18015d312  nop
0x18015d313  jmp     short loc_18015D317
0x18015d315  xor     esi, esi
0x18015d317  mov     [rsp+210h+var_1E8], rsi
0x18015d31c  test    rsi, rsi
0x18015d31f  jnz     short loc_18015D341
0x18015d321  mov     rax, [rdi]
0x18015d324  mov     rcx, rdi
0x18015d327  mov     rax, [rax+18h]
0x18015d32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d330  nop
0x18015d331  lea     rcx, [rsp+210h+var_1E8]
0x18015d336  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d33b  nop
0x18015d33c  jmp     loc_18015D1AD
0x18015d341  xor     ebx, ebx
0x18015d343  mov     [rsp+210h+var_1F0], rbx
0x18015d348  cmp     [r14+89h], bl
0x18015d34f  jz      loc_18015D3F7
0x18015d355  mov     [rsp+210h+var_1E0], ebx
0x18015d359  lea     rax, [rsp+210h+var_1E0]
0x18015d35e  mov     [rsp+210h+var_1D8], rax
0x18015d363  xor     r8d, r8d
0x18015d366  xor     edx, edx
0x18015d368  mov     ecx, 17A0h
0x18015d36d  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18015d372  mov     rbx, rax
0x18015d375  mov     [rsp+210h+var_1D0], rax
0x18015d37a  test    rax, rax
0x18015d37d  jz      short loc_18015D3B3
0x18015d37f  lea     rdx, aSubscriptionma_0; "SubscriptionManager/WEC"
0x18015d386  mov     rcx, rax; this
0x18015d389  call    ??0ConfigSoapProcessor@@QEAA@PEBG@Z; ConfigSoapProcessor::ConfigSoapProcessor(ushort const *)
0x18015d38e  lea     rax, ??_7SubscriptionManagerSoapProcessor@@6BCSoapProcessor@@@; const SubscriptionManagerSoapProcessor::`vftable'{for `CSoapProcessor'}
0x18015d395  mov     [rbx], rax
0x18015d398  lea     rax, ??_7SubscriptionManagerSoapProcessor@@6BIServiceConfigObserver@@@; const SubscriptionManagerSoapProcessor::`vftable'{for `IServiceConfigObserver'}
0x18015d39f  mov     [rbx+778h], rax
0x18015d3a6  mov     qword ptr [rbx+1798h], 0
0x18015d3b1  jmp     short loc_18015D3B5
0x18015d3b3  xor     ebx, ebx
0x18015d3b5  mov     rdx, rbx
0x18015d3b8  lea     rcx, [rsp+210h+var_1F0]
0x18015d3bd  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x18015d3c2  mov     rbx, [rsp+210h+var_1F0]
0x18015d3c7  test    rbx, rbx
0x18015d3ca  jnz     short loc_18015D3F7
0x18015d3cc  mov     rax, [rdi]
0x18015d3cf  mov     rcx, rdi
0x18015d3d2  mov     rax, [rax+18h]
0x18015d3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d3db  nop
0x18015d3dc  lea     rcx, [rsp+210h+var_1F0]
0x18015d3e1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d3e6  nop
0x18015d3e7  lea     rcx, [rsp+210h+var_1E8]
0x18015d3ec  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d3f1  nop
0x18015d3f2  jmp     loc_18015D1AD
0x18015d3f7  lea     rdx, WPP_GLOBAL_Control
0x18015d3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18015d405  cmp     rcx, rdx
0x18015d408  jz      short loc_18015D42B
0x18015d40a  test    dword ptr [rcx+1Ch], 10000h
0x18015d411  jz      short loc_18015D42B
0x18015d413  mov     edx, 0Ah
0x18015d418  mov     r9, rsi
0x18015d41b  lea     r8, WPP_4a94fa90dde23d5de7b70f3dffeb5ead_Traceguids
0x18015d422  mov     rcx, [rcx+10h]
0x18015d426  call    WPP_SF_q
0x18015d42b  lea     rdx, aEventcollector_0; "EventCollectorService"
0x18015d432  mov     rcx, rsi; this
0x18015d435  call    ?InternalInitialize@CSoapProcessor@@IEAAKPEBG@Z; CSoapProcessor::InternalInitialize(ushort const *)
0x18015d43a  test    eax, eax
0x18015d43c  jz      short loc_18015D448
0x18015d43e  mov     ecx, eax; dwErrCode
0x18015d440  call    cs:__imp_SetLastError
0x18015d446  jmp     short loc_18015D45F
0x18015d448  mov     edx, 1000h; unsigned int
0x18015d44d  mov     r8d, 1; int
0x18015d453  mov     rcx, rsi; this
0x18015d456  call    ?StartHttpListening@CSoapProcessor@@IEAAHKH@Z; CSoapProcessor::StartHttpListening(ulong,int)
0x18015d45b  test    eax, eax
0x18015d45d  jnz     short loc_18015D495
0x18015d45f  mov     rax, [rdi]
0x18015d462  mov     rbx, [rax+48h]
0x18015d466  call    cs:__imp_GetLastError
0x18015d46c  mov     edx, eax
0x18015d46e  mov     rcx, rdi
0x18015d471  mov     rax, rbx
0x18015d474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d479  nop
0x18015d47a  lea     rcx, [rsp+210h+var_1F0]
0x18015d47f  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d484  nop
0x18015d485  lea     rcx, [rsp+210h+var_1E8]
0x18015d48a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d48f  nop
0x18015d490  jmp     loc_18015D1AD
0x18015d495  test    rbx, rbx
0x18015d498  jz      short loc_18015D4EF
0x18015d49a  mov     rdx, r14; void *
0x18015d49d  mov     rcx, rbx; this
0x18015d4a0  call    ?Initialize@SubscriptionManagerSoapProcessor@@QEAAHPEAX@Z; SubscriptionManagerSoapProcessor::Initialize(void *)
0x18015d4a5  test    eax, eax
0x18015d4a7  jnz     short loc_18015D4EF
0x18015d4a9  mov     rax, [rdi]
0x18015d4ac  mov     rbx, [rax+48h]
0x18015d4b0  call    cs:__imp_GetLastError
0x18015d4b6  mov     edx, eax
0x18015d4b8  mov     rcx, rdi
0x18015d4bb  mov     rax, rbx
0x18015d4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d4c3  mov     rcx, rsi; this
0x18015d4c6  call    ?DeInitialize@EventSoapProcessor@@QEAAHXZ; EventSoapProcessor::DeInitialize(void)
0x18015d4cb  mov     [rsp+210h+var_1E8], 0
0x18015d4d4  lea     rcx, [rsp+210h+var_1F0]
0x18015d4d9  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d4de  nop
0x18015d4df  lea     rcx, [rsp+210h+var_1E8]
0x18015d4e4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d4e9  nop
0x18015d4ea  jmp     loc_18015D1AD
0x18015d4ef  mov     [rsp+210h+var_1F0], 0
0x18015d4f8  mov     [r14+78h], rbx
0x18015d4fc  mov     [rsp+210h+var_1E8], 0
0x18015d505  mov     [r14+80h], rsi
0x18015d50c  lea     rcx, [r14+90h]; unsigned __int16 *
0x18015d513  call    ?WSManCreateUuidString@@YAXQEAG@Z; WSManCreateUuidString(ushort * const)
0x18015d518  nop
0x18015d519  lea     rcx, [rsp+210h+var_1F0]
0x18015d51e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d523  nop
0x18015d524  lea     rcx, [rsp+210h+var_1E8]
0x18015d529  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18015d52e  nop
0x18015d52f  mov     al, 1
0x18015d531  jmp     loc_18015D1AF
```
