# CProcess::RpcCheckDataFlowAccess(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ulong,int *)

- ea: `0x180021450`
- end: `0x180021746`
- name: `?RpcCheckDataFlowAccess@CProcess@@UEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@KPEAH@Z`
- size: `758`
- prototype: `__int64 __fastcall(CProcess *__hidden this, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, unsigned int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001c74`
- `0x18000a384`
- `0x180012844`
- `0x180021450`
- `0x180031960`
- `0x18003a850`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002151e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021632`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002151e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021632`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800214d6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800214d6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800215b6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800215b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216cf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021708`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216cf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021645`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021533`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021533`
- `RPCRT4!RpcRevertToSelf` at `0x1800215db`
- `RPCRT4!RpcRevertToSelf` at `0x1800216c0`
- `RPCRT4!RpcRevertToSelf` at `0x1800216f9`
- `RPCRT4!RpcRevertToSelf` at `0x1800215db`
- `RPCRT4!RpcRevertToSelf` at `0x1800216c0`
- `RPCRT4!RpcRevertToSelf` at `0x1800216f9`
- `RPCRT4!RpcImpersonateClient` at `0x18002155e`
- `RPCRT4!RpcImpersonateClient` at `0x18002155e`

## string_xrefs

- `0x1800214fe`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcess::RpcCheckDataFlowAccess(
        CProcess *this,
        enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 a2,
        unsigned int a3,
        int *a4)
{
  unsigned int v6; // ebx
  __int64 v8; // rdi
  HRESULT v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int ActivationFactory; // eax
  unsigned int v13; // eax
  unsigned __int64 v14; // rbx
  HRESULT v15; // eax
  HRESULT v16; // r14d
  IUnknown *v17; // r12
  unsigned int v18; // r13d
  int v19; // eax
  __int64 v20; // rdx
  unsigned int dwAuthnLevel; // [rsp+20h] [rbp-59h]
  int dwAuthnLevela; // [rsp+20h] [rbp-59h]
  int v23; // [rsp+40h] [rbp-39h] BYREF
  int v24[2]; // [rsp+48h] [rbp-31h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-21h]
  ULONG (__stdcall *Release)(IUnknown *); // [rsp+60h] [rbp-19h]
  HSTRING string; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v26 = a3;
  if ( a2 )
  {
    if ( a2 != eCapture )
    {
      v6 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xABA,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
        (const char *)0x80070057LL,
        dwAuthnLevel);
      return v6;
    }
    v8 = 1;
  }
  else
  {
    v8 = 0;
    *((_DWORD *)this + 54) = 0;
  }
  if ( *((_DWORD *)this + v8 + 54) == -2147023728 )
  {
    v9 = CoInitializeEx(0, 0);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v10, v11, (const char *)(unsigned int)v9, dwAuthnLevel);
    pProxy = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.CapabilityAccess.CapabilityAccess",
           0x32u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(string, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &pProxy);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xACD,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
        (const char *)(unsigned int)ActivationFactory,
        dwAuthnLevel);
LABEL_27:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
      CoUninitialize();
      return v6;
    }
    v13 = RpcImpersonateClient(0);
    if ( v13 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xACF,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
             (const char *)v13,
             dwAuthnLevel);
      goto LABEL_27;
    }
    v14 = -1;
    v15 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x40u);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD9,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
        (const char *)(unsigned int)v15,
        dwAuthnLevela);
      RpcRevertToSelf();
      v6 = v16;
      goto LABEL_27;
    }
    *(_QWORD *)v24 = 0;
    v17 = pProxy;
    Release = pProxy->lpVtbl[2].Release;
    v18 = *((_DWORD *)this + 40);
    do
      ++v14;
    while ( c_szCapabilityMicrophone[v14] );
    if ( v14 > 0xFFFFFFFF )
    {
      LODWORD(v14) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(c_szCapabilityMicrophone, v14, &hstringHeader, &string);
    v19 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, _QWORD, _QWORD))Release)(v17, string, v18, v26);
    v6 = v19;
    if ( v19 < 0 )
    {
      v20 = 2783;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
        (const char *)(unsigned int)v19,
        (int)v24);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v24);
      RpcRevertToSelf();
      goto LABEL_27;
    }
    v23 = 3;
    v19 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v24 + 152LL))(*(_QWORD *)v24, &v23);
    v6 = v19;
    if ( v19 < 0 )
    {
      v20 = 2786;
      goto LABEL_26;
    }
    *((_DWORD *)this + v8 + 54) = v23 != 3 ? 0x887C0076 : 0;
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v24);
    RpcRevertToSelf();
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
    CoUninitialize();
  }
  if ( a4 )
    *a4 = *((_DWORD *)this + v8 + 54) == 0;
  return 0;
}

```

## disassembly

```asm
0x180021450  push    rbp
0x180021452  push    rbx
0x180021453  push    rsi
0x180021454  push    rdi
0x180021455  push    r12
0x180021457  push    r13
0x180021459  push    r14
0x18002145b  push    r15
0x18002145d  lea     rbp, [rsp-1Fh]
0x180021462  sub     rsp, 98h
0x180021469  mov     rax, cs:__security_cookie
0x180021470  xor     rax, rsp
0x180021473  mov     [rbp+57h+var_48], rax
0x180021477  mov     r15, r9
0x18002147a  mov     [rbp+57h+var_78], r8d
0x18002147e  mov     rsi, rcx
0x180021481  xor     r12d, r12d
0x180021484  test    edx, edx
0x180021486  jz      short loc_1800214B6
0x180021488  cmp     edx, 1
0x18002148b  jz      short loc_1800214B1
0x18002148d  mov     rcx, [rbp+5Fh]; this
0x180021491  mov     ebx, 80070057h
0x180021496  mov     r9d, ebx; char *
0x180021499  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x1800214a0  mov     edx, 0ABAh; void *
0x1800214a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800214aa  mov     eax, ebx
0x1800214ac  jmp     loc_180021726
0x1800214b1  movsxd  rdi, edx
0x1800214b4  jmp     short loc_1800214C1
0x1800214b6  movsxd  rdi, edx
0x1800214b9  mov     [rcx+rdi*4+0D8h], r12d
0x1800214c1  cmp     dword ptr [rcx+rdi*4+0D8h], 80070490h
0x1800214cc  jnz     loc_18002170E
0x1800214d2  xor     edx, edx; dwCoInit
0x1800214d4  xor     ecx, ecx; pvReserved
0x1800214d6  call    cs:__imp_CoInitializeEx
0x1800214dc  mov     rcx, [rbp+5Fh]; this
0x1800214e0  test    eax, eax
0x1800214e2  jns     short loc_1800214ED
0x1800214e4  mov     r9d, eax; char *
0x1800214e7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800214ed  mov     [rbp+57h+pProxy], r12
0x1800214f1  lea     r9, [rbp+57h+string]; string
0x1800214f5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800214f9  mov     edx, 32h ; '2'; length
0x1800214fe  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x180021505  call    cs:__imp_WindowsCreateStringReference
0x18002150b  test    eax, eax
0x18002150d  jns     short loc_180021524
0x18002150f  xor     r9d, r9d; lpArguments
0x180021512  xor     r8d, r8d; nNumberOfArguments
0x180021515  lea     edx, [r9+1]; dwExceptionFlags
0x180021519  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002151e  call    cs:__imp_RaiseException
0x180021524  lea     r8, [rbp+57h+pProxy]
0x180021528  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18002152f  mov     rcx, [rbp+57h+string]
0x180021533  call    cs:__imp_RoGetActivationFactory
0x180021539  mov     ebx, eax
0x18002153b  test    eax, eax
0x18002153d  jns     short loc_18002155C
0x18002153f  mov     rcx, [rbp+5Fh]; this
0x180021543  mov     r9d, eax; char *
0x180021546  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x18002154d  mov     edx, 0ACDh; void *
0x180021552  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021557  jmp     loc_1800216C6
0x18002155c  xor     ecx, ecx; BindingHandle
0x18002155e  call    cs:__imp_RpcImpersonateClient
0x180021564  test    eax, eax
0x180021566  jz      short loc_180021587
0x180021568  mov     rcx, [rbp+5Fh]; this
0x18002156c  mov     r9d, eax; char *
0x18002156f  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180021576  mov     edx, 0ACFh; void *
0x18002157b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021580  mov     ebx, eax
0x180021582  jmp     loc_1800216C6
0x180021587  mov     [rsp+0D0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002158f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021593  mov     [rsp+0D0h+pAuthInfo], rbx; pAuthInfo
0x180021598  mov     [rsp+0D0h+dwImpLevel], 3; dwImpLevel
0x1800215a0  mov     [rsp+0D0h+dwAuthnLevel], r12d; int
0x1800215a5  mov     r9, rbx; pServerPrincName
0x1800215a8  mov     eax, 0FFFFFFFFh
0x1800215ad  mov     r8d, eax; dwAuthzSvc
0x1800215b0  mov     edx, eax; dwAuthnSvc
0x1800215b2  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800215b6  call    cs:__imp_CoSetProxyBlanket
0x1800215bc  mov     r14d, eax
0x1800215bf  test    eax, eax
0x1800215c1  jns     short loc_1800215E9
0x1800215c3  mov     rcx, [rbp+5Fh]; this
0x1800215c7  mov     r9d, eax; char *
0x1800215ca  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x1800215d1  mov     edx, 0AD9h; void *
0x1800215d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800215db  call    cs:__imp_RpcRevertToSelf
0x1800215e1  mov     ebx, r14d
0x1800215e4  jmp     loc_1800216C6
0x1800215e9  mov     qword ptr [rbp+57h+var_88], r12
0x1800215ed  mov     r12, [rbp+57h+pProxy]
0x1800215f1  mov     rax, [r12]
0x1800215f5  mov     rax, [rax+40h]
0x1800215f9  mov     [rbp+57h+var_70], rax
0x1800215fd  mov     r13d, [rsi+0A0h]
0x180021604  mov     r14, cs:?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x18002160b  xor     eax, eax
0x18002160d  inc     rbx
0x180021610  cmp     [r14+rbx*2], ax
0x180021615  jnz     short loc_18002160D
0x180021617  mov     eax, 0FFFFFFFFh
0x18002161c  cmp     rbx, rax
0x18002161f  jbe     short loc_180021638
0x180021621  mov     ebx, eax
0x180021623  xor     r9d, r9d; lpArguments
0x180021626  xor     r8d, r8d; nNumberOfArguments
0x180021629  lea     edx, [r9+1]; dwExceptionFlags
0x18002162d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180021632  call    cs:__imp_RaiseException
0x180021638  lea     r9, [rbp+57h+string]; string
0x18002163c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021640  mov     edx, ebx; length
0x180021642  mov     rcx, r14; sourceString
0x180021645  call    cs:__imp_WindowsCreateStringReference
0x18002164b  lea     rax, [rbp+57h+var_88]
0x18002164f  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rax; int
0x180021654  mov     r9d, [rbp+57h+var_78]
0x180021658  mov     r8d, r13d
0x18002165b  mov     rdx, [rbp+57h+string]
0x18002165f  mov     rcx, r12
0x180021662  mov     rax, [rbp+57h+var_70]
0x180021666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002166b  mov     ebx, eax
0x18002166d  xor     r12d, r12d
0x180021670  test    eax, eax
0x180021672  jns     short loc_18002167B
0x180021674  mov     edx, 0ADFh
0x180021679  jmp     short loc_1800216A4
0x18002167b  mov     [rbp+57h+var_90], 3
0x180021682  mov     rcx, qword ptr [rbp+57h+var_88]
0x180021686  mov     rax, [rcx]
0x180021689  lea     rdx, [rbp+57h+var_90]
0x18002168d  mov     rax, [rax+98h]
0x180021694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021699  mov     ebx, eax
0x18002169b  test    eax, eax
0x18002169d  jns     short loc_1800216DA
0x18002169f  mov     edx, 0AE2h; void *
0x1800216a4  mov     r9d, eax; char *
0x1800216a7  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x1800216ae  mov     rcx, [rbp+5Fh]; this
0x1800216b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216b7  lea     rcx, [rbp+57h+var_88]
0x1800216bb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800216c0  call    cs:__imp_RpcRevertToSelf
0x1800216c6  lea     rcx, [rbp+57h+pProxy]
0x1800216ca  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800216cf  call    cs:__imp_CoUninitialize
0x1800216d5  jmp     loc_1800214AA
0x1800216da  mov     eax, [rbp+57h+var_90]
0x1800216dd  sub     eax, 3
0x1800216e0  neg     eax
0x1800216e2  sbb     eax, eax
0x1800216e4  and     eax, 887C0076h
0x1800216e9  mov     [rsi+rdi*4+0D8h], eax
0x1800216f0  lea     rcx, [rbp+57h+var_88]
0x1800216f4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800216f9  call    cs:__imp_RpcRevertToSelf
0x1800216ff  lea     rcx, [rbp+57h+pProxy]
0x180021703  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180021708  call    cs:__imp_CoUninitialize
0x18002170e  test    r15, r15
0x180021711  jz      short loc_180021724
0x180021713  mov     eax, r12d
0x180021716  cmp     [rsi+rdi*4+0D8h], r12d
0x18002171e  setz    al
0x180021721  mov     [r15], eax
0x180021724  xor     eax, eax
0x180021726  mov     rcx, [rbp+57h+var_48]
0x18002172a  xor     rcx, rsp; StackCookie
0x18002172d  call    __security_check_cookie
0x180021732  add     rsp, 98h
0x180021739  pop     r15
0x18002173b  pop     r14
0x18002173d  pop     r13
0x18002173f  pop     r12
0x180021741  pop     rdi
0x180021742  pop     rsi
0x180021743  pop     rbx
0x180021744  pop     rbp
0x180021745  retn
```
