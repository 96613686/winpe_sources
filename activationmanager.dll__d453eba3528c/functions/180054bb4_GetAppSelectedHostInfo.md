# GetAppSelectedHostInfo

- ea: `0x180054bb4`
- end: `0x180054eee`
- name: `GetAppSelectedHostInfo`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180023f20`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180015b7c`
- `0x180027c60`
- `0x180027ce8`
- `0x18002b6a0`
- `0x180044514`
- `0x180054bb4`
- `0x180054ef4`
- `0x18005ae90`
- `0x18005ba40`
- `0x18007b3a4`
- `0x18007b6e8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180054d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180054d87`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180054d93`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180054d93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054c6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054c6e`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x180054e40`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x180054e40`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdRetrieveDynamicId` at `0x180054db0`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdRetrieveDynamicId` at `0x180054db0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAppSelectedHostInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int128 *a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8,
        __int64 a9)
{
  int HamActivity; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(_QWORD, _QWORD, _QWORD, _QWORD); // rdi
  __int64 v17; // r9
  __int128 *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rbx
  DWORD CurrentProcessId; // eax
  _DWORD *v25; // rbx
  int DynamicId; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 *v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  DWORD pSessionId[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[464]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v37 = a3;
  *(_QWORD *)pSessionId = a1;
  v38 = a4;
  v33 = a7;
  v36 = a8;
  v34 = 0;
  if ( *(_DWORD *)(a2 + 60) == 4
    || (Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34),
        v32 = &v34,
        HamActivity = GetHamActivity(a3, a6, a4, *(unsigned int *)(a2 + 56)),
        v14 = HamActivity,
        HamActivity >= 0) )
  {
    QueryPerformanceCounter((LARGE_INTEGER *)(a9 + 56));
    v16 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 80LL);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a9 + 32,
      0);
    v39 = *a5;
    v32 = *(__int64 **)(a2 + 32);
    HamActivity = v16(*(_QWORD *)pSessionId, *(_QWORD *)a2, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 24));
    v14 = HamActivity;
    if ( HamActivity < 0 )
    {
      v15 = 129;
      goto LABEL_6;
    }
    v18 = (__int128 *)(a9 + 8);
    if ( *(_QWORD *)a9 == a4 )
    {
      *v18 = *a5;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        a9 + 24,
        0);
      HamActivity = _AllocString<CTCoAllocPolicy>(v20, v19, a6, a9 + 24);
      v14 = HamActivity;
      if ( HamActivity < 0 )
      {
        v15 = 135;
        goto LABEL_6;
      }
      v23 = v34;
      if ( *(_QWORD *)(a9 + 40) != v34 )
      {
        v33 = v34;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v33, v21, v22);
        v33 = *(_QWORD *)(a9 + 40);
        *(_QWORD *)(a9 + 40) = v23;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      }
LABEL_27:
      v14 = 0;
      goto LABEL_28;
    }
    *(_BYTE *)(a9 + 48) = 1;
    pSessionId[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    ProcessIdToSessionId(CurrentProcessId, pSessionId);
    v25 = v36;
    *v36 = 36;
    DynamicId = HamHostIdRetrieveDynamicId(v37, pSessionId[0], *(_QWORD *)a9, a9 + 8);
    if ( DynamicId >= 0 )
    {
      *v25 = 0;
      v28 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)v18;
      if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)v18 )
        v28 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)(a9 + 16);
      if ( !v28 )
      {
        v14 = -2147024809;
        v17 = 2147942487LL;
        v15 = 149;
        goto LABEL_7;
      }
      memset_0(v40, 0, sizeof(v40));
      LODWORD(v33) = 464;
      v32 = &v33;
      DynamicId = PsmCreateKeyWithDynamicId(*(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 16), a9 + 8, v40);
      if ( DynamicId >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          a9 + 24,
          0);
        HamActivity = _AllocString<CTCoAllocPolicy>(v30, v29, v40, a9 + 24);
        v14 = HamActivity;
        if ( HamActivity < 0 )
        {
          v15 = 155;
          goto LABEL_6;
        }
        if ( v34 )
          HamActivityWrapper::TerminateHost(v34, 1, 3840);
        AAMTraceProvider::ActivationRedirected<unsigned __int64 const &,unsigned short const * const &,unsigned __int64 &,_GUID &,unsigned __int64 &,_GUID &,unsigned short (&)[232]>(
          a2 + 8,
          a2 + 24,
          (unsigned int)&v38,
          (_DWORD)a5,
          a9,
          a9 + 8,
          (__int64)v40);
        goto LABEL_27;
      }
      v27 = 154;
    }
    else
    {
      v27 = 146;
    }
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v27,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
            (const char *)(unsigned int)DynamicId,
            (int)v32);
    goto LABEL_28;
  }
  v15 = 121;
LABEL_6:
  v17 = (unsigned int)HamActivity;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
    (const char *)v17,
    (int)v32);
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  return v14;
}

```

## disassembly

```asm
0x180054bb4  push    rbp
0x180054bb6  push    rbx
0x180054bb7  push    rsi
0x180054bb8  push    rdi
0x180054bb9  push    r12
0x180054bbb  push    r13
0x180054bbd  push    r14
0x180054bbf  push    r15
0x180054bc1  lea     rbp, [rsp-198h]
0x180054bc9  sub     rsp, 298h
0x180054bd0  mov     rax, cs:__security_cookie
0x180054bd7  xor     rax, rsp
0x180054bda  mov     [rbp+1D0h+var_50], rax
0x180054be1  mov     r15, r9
0x180054be4  mov     rbx, r8
0x180054be7  mov     [rbp+1D0h+var_240], rbx
0x180054beb  mov     r14, rdx
0x180054bee  mov     rdi, rcx
0x180054bf1  mov     qword ptr [rbp+1D0h+pSessionId], rcx
0x180054bf5  mov     rsi, [rbp+1D0h+arg_40]
0x180054bfc  mov     [rbp+1D0h+var_238], r9
0x180054c00  mov     r12, [rbp+1D0h+arg_20]
0x180054c07  mov     r13, [rbp+1D0h+arg_28]
0x180054c0e  mov     rax, [rbp+1D0h+arg_30]
0x180054c15  mov     [rsp+2D0h+var_260], rax
0x180054c1a  mov     rax, [rbp+1D0h+arg_38]
0x180054c21  mov     [rbp+1D0h+var_248], rax
0x180054c25  mov     [rsp+2D0h+var_258], 0
0x180054c2e  cmp     dword ptr [rdx+3Ch], 4
0x180054c32  jz      short loc_180054C6A
0x180054c34  lea     rcx, [rsp+2D0h+var_258]
0x180054c39  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054c3e  lea     rax, [rsp+2D0h+var_258]
0x180054c43  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x180054c48  mov     r9d, [r14+38h]
0x180054c4c  mov     r8, r15
0x180054c4f  mov     rdx, r13
0x180054c52  mov     rcx, rbx
0x180054c55  call    GetHamActivity
0x180054c5a  mov     ebx, eax
0x180054c5c  test    eax, eax
0x180054c5e  jns     short loc_180054C6A
0x180054c60  mov     edx, 79h ; 'y'
0x180054c65  jmp     loc_180054CF1
0x180054c6a  lea     rcx, [rsi+38h]; lpPerformanceCount
0x180054c6e  call    cs:__imp_QueryPerformanceCounter
0x180054c74  mov     rax, [rdi]
0x180054c77  mov     rdi, [rax+50h]
0x180054c7b  lea     rbx, [rsi+20h]
0x180054c7f  xor     edx, edx
0x180054c81  mov     rcx, rbx
0x180054c84  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180054c89  movaps  xmm0, xmmword ptr [r12]
0x180054c8e  movdqa  [rbp+1D0h+var_230], xmm0
0x180054c93  mov     [rsp+2D0h+var_278], rbx
0x180054c98  mov     [rsp+2D0h+var_280], rsi
0x180054c9d  mov     [rsp+2D0h+var_288], 1D4C0h
0x180054ca5  mov     rax, [rsp+2D0h+var_260]
0x180054caa  mov     [rsp+2D0h+var_290], rax
0x180054caf  lea     rax, [rbp+1D0h+var_230]
0x180054cb3  mov     [rsp+2D0h+var_298], rax
0x180054cb8  mov     [rsp+2D0h+var_2A0], r15
0x180054cbd  mov     rdx, [r14+30h]
0x180054cc1  mov     [rsp+2D0h+var_2A8], rdx
0x180054cc6  mov     rdx, [r14+20h]
0x180054cca  mov     qword ptr [rsp+2D0h+var_2B0], rdx; int
0x180054ccf  mov     r9, [r14+18h]
0x180054cd3  mov     r8, [r14+8]
0x180054cd7  mov     rdx, [r14]
0x180054cda  mov     rcx, qword ptr [rbp+1D0h+pSessionId]
0x180054cde  mov     rax, rdi
0x180054ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ce6  mov     ebx, eax
0x180054ce8  test    eax, eax
0x180054cea  jns     short loc_180054D0C
0x180054cec  mov     edx, 81h; void *
0x180054cf1  mov     r9d, eax; char *
0x180054cf4  mov     rcx, [rbp+1D8h]; this
0x180054cfb  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180054d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054d07  jmp     loc_180054EBF
0x180054d0c  lea     rdi, [rsi+8]
0x180054d10  cmp     [rsi], r15
0x180054d13  jnz     short loc_180054D7C
0x180054d15  movaps  xmm0, xmmword ptr [r12]
0x180054d1a  movdqu  xmmword ptr [rdi], xmm0
0x180054d1e  xor     edx, edx
0x180054d20  lea     rcx, [rsi+18h]
0x180054d24  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180054d29  lea     r9, [rsi+18h]
0x180054d2d  mov     r8, r13
0x180054d30  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180054d35  mov     ebx, eax
0x180054d37  test    eax, eax
0x180054d39  jns     short loc_180054D42
0x180054d3b  mov     edx, 87h
0x180054d40  jmp     short loc_180054CF1
0x180054d42  mov     rbx, [rsp+2D0h+var_258]
0x180054d47  cmp     [rsi+28h], rbx
0x180054d4b  jz      loc_180054EBD
0x180054d51  mov     [rsp+2D0h+var_260], rbx
0x180054d56  lea     rcx, [rsp+2D0h+var_260]
0x180054d5b  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180054d60  mov     rax, [rsi+28h]
0x180054d64  mov     [rsp+2D0h+var_260], rax
0x180054d69  mov     [rsi+28h], rbx
0x180054d6d  lea     rcx, [rsp+2D0h+var_260]
0x180054d72  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054d77  jmp     loc_180054EBD
0x180054d7c  mov     byte ptr [rsi+30h], 1
0x180054d80  mov     [rbp+1D0h+pSessionId], 0
0x180054d87  call    cs:__imp_GetCurrentProcessId
0x180054d8d  mov     ecx, eax; dwProcessId
0x180054d8f  lea     rdx, [rbp+1D0h+pSessionId]; pSessionId
0x180054d93  call    cs:__imp_ProcessIdToSessionId
0x180054d99  mov     rbx, [rbp+1D0h+var_248]
0x180054d9d  mov     dword ptr [rbx], 24h ; '$'
0x180054da3  mov     r9, rdi
0x180054da6  mov     r8, [rsi]
0x180054da9  mov     edx, [rbp+1D0h+pSessionId]
0x180054dac  mov     rcx, [rbp+1D0h+var_240]
0x180054db0  call    cs:__imp_HamHostIdRetrieveDynamicId
0x180054db6  test    eax, eax
0x180054db8  jns     short loc_180054DDC
0x180054dba  mov     edx, 92h; void *
0x180054dbf  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180054dc6  mov     r9d, eax; char *
0x180054dc9  mov     rcx, [rbp+1D8h]; this
0x180054dd0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180054dd5  mov     ebx, eax
0x180054dd7  jmp     loc_180054EBF
0x180054ddc  mov     dword ptr [rbx], 0
0x180054de2  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180054de9  sub     rax, [rdi]
0x180054dec  jnz     short loc_180054DF9
0x180054dee  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180054df5  sub     rax, [rdi+8]
0x180054df9  test    rax, rax
0x180054dfc  jnz     short loc_180054E10
0x180054dfe  mov     ebx, 80070057h
0x180054e03  mov     r9d, ebx
0x180054e06  mov     edx, 95h
0x180054e0b  jmp     loc_180054CF4
0x180054e10  mov     ebx, 1D0h
0x180054e15  mov     r8d, ebx; Size
0x180054e18  xor     edx, edx; Val
0x180054e1a  lea     rcx, [rbp+1D0h+var_220]; void *
0x180054e1e  call    memset_0
0x180054e23  mov     dword ptr [rsp+2D0h+var_260], ebx
0x180054e27  lea     rax, [rsp+2D0h+var_260]
0x180054e2c  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x180054e31  lea     r9, [rbp+1D0h+var_220]
0x180054e35  mov     r8, rdi
0x180054e38  mov     rdx, [r14+10h]
0x180054e3c  mov     rcx, [r14+28h]
0x180054e40  call    cs:__imp_PsmCreateKeyWithDynamicId
0x180054e46  test    eax, eax
0x180054e48  jns     short loc_180054E54
0x180054e4a  mov     edx, 9Ah
0x180054e4f  jmp     loc_180054DBF
0x180054e54  xor     edx, edx
0x180054e56  lea     rcx, [rsi+18h]
0x180054e5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180054e5f  lea     r9, [rsi+18h]
0x180054e63  lea     r8, [rbp+1D0h+var_220]
0x180054e67  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180054e6c  mov     ebx, eax
0x180054e6e  test    eax, eax
0x180054e70  jns     short loc_180054E7C
0x180054e72  mov     edx, 9Bh
0x180054e77  jmp     loc_180054CF1
0x180054e7c  mov     rcx, [rsp+2D0h+var_258]
0x180054e81  test    rcx, rcx
0x180054e84  jz      short loc_180054E96
0x180054e86  mov     edx, 1
0x180054e8b  mov     r8d, 0F00h
0x180054e91  call    ?TerminateHost@HamActivityWrapper@@QEAAJW4_HAM_TERMINATE_TYPE@@W4_HAM_TERMINATE_REASON@@@Z; HamActivityWrapper::TerminateHost(_HAM_TERMINATE_TYPE,_HAM_TERMINATE_REASON)
0x180054e96  lea     rax, [rbp+1D0h+var_220]
0x180054e9a  mov     [rsp+2D0h+var_2A0], rax
0x180054e9f  mov     [rsp+2D0h+var_2A8], rdi
0x180054ea4  mov     qword ptr [rsp+2D0h+var_2B0], rsi
0x180054ea9  mov     r9, r12
0x180054eac  lea     r8, [rbp+1D0h+var_238]
0x180054eb0  lea     rdx, [r14+18h]
0x180054eb4  lea     rcx, [r14+8]
0x180054eb8  call    ??$ActivationRedirected@AEB_KAEBQEBGAEA_KAEAU_GUID@@AEA_KAEAU1@AEAY0OI@G@AAMTraceProvider@@SAXAEB_KAEBQEBGAEA_KAEAU_GUID@@23AEAY0OI@G@Z; AAMTraceProvider::ActivationRedirected<unsigned __int64 const &,ushort const * const &,unsigned __int64 &,_GUID &,unsigned __int64 &,_GUID &,ushort (&)[232]>(unsigned __int64 const &,ushort const * const &,unsigned __int64 &,_GUID &,unsigned __int64 &,_GUID &,ushort (&)[232])
0x180054ebd  xor     ebx, ebx
0x180054ebf  lea     rcx, [rsp+2D0h+var_258]
0x180054ec4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054ec9  mov     eax, ebx
0x180054ecb  mov     rcx, [rbp+1D0h+var_50]
0x180054ed2  xor     rcx, rsp; StackCookie
0x180054ed5  call    __security_check_cookie
0x180054eda  add     rsp, 298h
0x180054ee1  pop     r15
0x180054ee3  pop     r14
0x180054ee5  pop     r13
0x180054ee7  pop     r12
0x180054ee9  pop     rdi
0x180054eea  pop     rsi
0x180054eeb  pop     rbx
0x180054eec  pop     rbp
0x180054eed  retn
```
