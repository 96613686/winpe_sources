# CLPInstallHandler::DownloadAndInstallPackage(ushort const *,wil::Variant const *)

- ea: `0x140041b08`
- end: `0x14004220b`
- name: `?DownloadAndInstallPackage@CLPInstallHandler@@QEAAJPEBGPEBVVariant@wil@@@Z`
- size: `1795`
- prototype: `int(CLPInstallHandler *__hidden this, const unsigned __int16 *, const struct wil::Variant *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040c30`

## callees

- `0x14000e624`
- `0x14001a2a0`
- `0x14002dd70`
- `0x14002de74`
- `0x14003aed0`
- `0x14003d630`
- `0x14003e03c`
- `0x14003e8f4`
- `0x14003f000`
- `0x140041054`
- `0x1400410dc`
- `0x1400411a4`
- `0x140041b08`
- `0x1400429d0`
- `0x140042ee4`
- `0x14007d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140041f5c`
- `KERNEL32!EnterCriticalSection` at `0x140041f5c`
- `KERNEL32!CreateEventW` at `0x140041cba`
- `KERNEL32!CreateEventW` at `0x140041cba`
- `KERNEL32!TlsGetValue` at `0x140041b38`
- `KERNEL32!TlsGetValue` at `0x140041b38`
- `KERNEL32!TlsSetValue` at `0x140041b65`
- `KERNEL32!TlsSetValue` at `0x140041b65`
- `ole32!CoWaitForMultipleHandles` at `0x140041dec`
- `ole32!CoWaitForMultipleHandles` at `0x140041dec`
- `OLEAUT32!__imp_VariantInit` at `0x140041ca6`
- `OLEAUT32!__imp_VariantInit` at `0x140041fbd`
- `OLEAUT32!__imp_VariantInit` at `0x140041ca6`
- `OLEAUT32!__imp_VariantInit` at `0x140041fbd`
- `OLEAUT32!__imp_VariantClear` at `0x140041ebc`
- `OLEAUT32!__imp_VariantClear` at `0x140042145`
- `OLEAUT32!__imp_VariantClear` at `0x140041ebc`
- `OLEAUT32!__imp_VariantClear` at `0x140042145`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CLPInstallHandler::DownloadAndInstallPackage(
        CLPInstallHandler *this,
        const unsigned __int16 *a2,
        const struct wil::Variant *a3)
{
  const unsigned __int16 *v4; // r13
  __int64 *Value; // rax
  __int64 *p_TlsValue; // rsi
  PVOID *v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // r9
  int Error; // ebx
  _QWORD *v13; // r14
  HANDLE EventW; // rax
  CLPInstallHandler *v15; // rcx
  char *v16; // r13
  unsigned int v17; // ecx
  __int64 v18; // rcx
  struct IUnknown *v19; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  unsigned int v21; // edx
  __int64 v22; // rdx
  char *v23; // rbx
  CLPInstallHandler *v24; // rcx
  __int64 v25; // rdi
  unsigned int v26; // ecx
  __int64 v27; // rcx
  unsigned int v28; // edx
  __int64 v29; // r15
  __int64 v31; // [rsp+30h] [rbp-79h] BYREF
  DWORD dwindex[2]; // [rsp+38h] [rbp-71h] BYREF
  struct IUnknown *v33; // [rsp+40h] [rbp-69h] BYREF
  __int64 v34; // [rsp+48h] [rbp-61h] BYREF
  DWORD v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+58h] [rbp-51h] BYREF
  char *v37; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-39h] BYREF
  __int64 TlsValue; // [rsp+88h] [rbp-21h] BYREF
  void **v41; // [rsp+90h] [rbp-19h] BYREF
  HANDLE pHandles; // [rsp+98h] [rbp-11h] BYREF
  __int64 *v43; // [rsp+A0h] [rbp-9h]
  VARIANTARG v44[3]; // [rsp+B0h] [rbp+7h] BYREF
  const unsigned __int16 *v45; // [rsp+118h] [rbp+6Fh] BYREF
  HANDLE v46; // [rsp+120h] [rbp+77h] BYREF
  int v47; // [rsp+128h] [rbp+7Fh] BYREF

  v45 = a2;
  v4 = a2;
  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v35 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v43 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v35 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
    v43 = &TlsValue;
  }
  ++*(_DWORD *)p_TlsValue;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v9 = 5 * *(_DWORD *)p_TlsValue;
    if ( v9 > 0x1E1 )
      v10 = 0;
    else
      v10 = 479LL - v9;
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v10],
      (char)this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v33 = 0;
  v36 = 0;
  if ( *(_WORD *)a3 != 13 || (v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a3 + 1)) == 0 )
  {
    Error = -2147467262;
    if ( *(_WORD *)a3 != 9 )
      goto LABEL_45;
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a3 + 1);
    if ( !v11 )
      goto LABEL_45;
  }
  Error = (**v11)(v11, &GUID_07f7438c_7709_4ca5_b518_91279288134e, &v36);
  if ( Error < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
    v13 = (_QWORD *)((char *)this + 48);
    goto LABEL_46;
  }
  v13 = (_QWORD *)((char *)this + 48);
  Error = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown **))(**((_QWORD **)this + 6) + 104LL))(
            *((_QWORD *)this + 6),
            &v33);
  if ( Error < 0 )
    goto LABEL_43;
  if ( *((_BYTE *)this + 88) )
    ((void (__fastcall *)(struct IUnknown *, __int64))v33->lpVtbl[3].AddRef)(v33, 0xFFFFFFFFLL);
  Error = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v33->lpVtbl[4].Release)(v33, v36);
  if ( Error < 0 )
    goto LABEL_43;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  EventW = CreateEventW(0, 1, 0, 0);
  pHandles = EventW;
  v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( EventW )
    goto LABEL_22;
  Error = ResultFromKnownLastError();
  if ( Error >= 0 )
  {
    EventW = pHandles;
LABEL_22:
    v46 = EventW;
    Microsoft::WRL::Details::Make<CDownloadProgressHandler,unsigned short const * &,void *>(
      &v37,
      (__int64 *)&v45,
      (__int64 *)&v46);
    v34 = 0;
    Error = CLPInstallHandler::SetUUPSessionData(v15, v4, v33, 0x3000Du);
    v16 = v37;
    if ( Error >= 0 )
    {
      v44[0] = pvarg;
      Error = ((__int64 (__fastcall *)(struct IUnknown *, char *, unsigned __int64, VARIANTARG *, __int64 *))v33->lpVtbl[5].QueryInterface)(
                v33,
                v37,
                (unsigned __int64)(v37 + 8) & -(__int64)(v37 != 0),
                v44,
                &v34);
      if ( Error >= 0 )
      {
        v38 = 0;
        dwindex[0] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v17 = 5 * (*(_DWORD *)p_TlsValue + 1);
          if ( v17 > 0x1E1 )
            v18 = 0;
          else
            v18 = 479LL - v17;
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
            &asc_14008A110[v18]);
        }
        Error = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, dwindex);
        if ( Error >= 0 )
        {
          v31 = 0;
          v19 = v33;
          Release = v33->lpVtbl[5].Release;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Error = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))Release)(v19, v34, &v31);
          if ( Error >= 0 )
          {
            LODWORD(v46) = 0;
            Error = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v31 + 64LL))(v31, &v46);
            if ( Error >= 0 && (_DWORD)v46 != 2 )
            {
              v47 = 0;
              Error = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v47);
              if ( Error >= 0 )
              {
                Error = v47;
                if ( v47 >= 0 )
                  Error = -2147467259;
              }
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      }
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v34);
    if ( v16 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDownloadProgressChangedCallback,IDownloadCompletedCallback>::Release(v16);
    v4 = v45;
  }
  VariantClear(&pvarg);
  v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v41);
LABEL_43:
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_46:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
  {
    v21 = 5 * (*(_DWORD *)p_TlsValue + 1);
    if ( v21 > 0x1E1 )
      v22 = 0;
    else
      v22 = 479LL - v21;
    WPP_SF_sd(
      (unsigned int)v8[2],
      19,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v22],
      Error);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Error >= 0 )
  {
    v23 = (char *)CLanguagePackInstallerSingleton::s_pInstance + 176;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)CLanguagePackInstallerSingleton::s_pInstance + 176));
    v37 = v23;
    *(_QWORD *)dwindex = 0;
    Error = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(*(_QWORD *)*v13 + 112LL))(*v13, dwindex);
    if ( Error >= 0 )
    {
      Error = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)dwindex + 128LL))(*(_QWORD *)dwindex, v36);
      if ( Error >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        Microsoft::WRL::Details::Make<CInstallProgressHandler,unsigned short const * &>(&v38, (__int64 *)&v45);
        v34 = 0;
        Error = CLPInstallHandler::SetUUPSessionData(v24, v4, *(struct IUnknown **)dwindex, 0x50004u);
        v25 = v38;
        if ( Error >= 0 )
        {
          if ( *((_BYTE *)this + 88) )
            Error = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)dwindex + 80LL))(
                      *(_QWORD *)dwindex,
                      0xFFFFFFFFLL);
          if ( Error >= 0 )
          {
            v44[0] = pvarg;
            Error = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, VARIANTARG *, __int64 *))(**(_QWORD **)dwindex
                                                                                                 + 136LL))(
                      *(_QWORD *)dwindex,
                      v25,
                      (v25 + 8) & -(__int64)(v25 != 0),
                      v44,
                      &v34);
            if ( Error >= 0 )
            {
              v31 = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v26 = 5 * (*(_DWORD *)p_TlsValue + 1);
                if ( v26 > 0x1E1 )
                  v27 = 0;
                else
                  v27 = 479LL - v26;
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
                  &asc_14008A110[v27]);
              }
              Error = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)dwindex + 152LL))(
                        *(_QWORD *)dwindex,
                        v34,
                        &v31);
              if ( Error >= 0 )
              {
                LODWORD(v46) = 0;
                Error = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v31 + 72LL))(v31, &v46);
                if ( Error >= 0 && (_DWORD)v46 != 2 )
                {
                  v47 = 0;
                  Error = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v47);
                  if ( Error >= 0 )
                  {
                    Error = v47;
                    if ( v47 >= 0 )
                      Error = -2147467259;
                  }
                }
              }
              wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v31);
            }
          }
        }
        VariantClear(&pvarg);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v34);
        if ( v25 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDownloadProgressChangedCallback,IDownloadCompletedCallback>::Release(v25);
      }
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)dwindex);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v37);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && *((char *)v8 + 28) < 0 )
  {
    v28 = 5 * *(_DWORD *)p_TlsValue;
    if ( v28 > 0x1E1 )
      v29 = 0;
    else
      v29 = 479LL - v28;
    WPP_SF_sqd(
      (unsigned int)v8[2],
      21,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v29],
      (char)this,
      Error);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v36);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v33);
  --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v35);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140041b08  mov     [rsp-8+arg_0], rbx
0x140041b0d  mov     [rsp-8+arg_8], rdx
0x140041b12  push    rbp
0x140041b13  push    rsi
0x140041b14  push    rdi
0x140041b15  push    r12
0x140041b17  push    r13
0x140041b19  push    r14
0x140041b1b  push    r15
0x140041b1d  lea     rbp, [rsp-27h]
0x140041b22  sub     rsp, 0D0h
0x140041b29  mov     rdi, r8
0x140041b2c  mov     r13, rdx
0x140041b2f  mov     r12, rcx
0x140041b32  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140041b38  call    cs:__imp_TlsGetValue
0x140041b3e  mov     rsi, rax
0x140041b41  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x140041b48  xor     r14d, r14d
0x140041b4b  mov     [rbp+57h+TlsValue], r14
0x140041b4f  test    rax, rax
0x140041b52  jnz     short loc_140041B71
0x140041b54  lea     rsi, [rbp+57h+TlsValue]
0x140041b58  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140041b5e  mov     [rbp+57h+var_B0], ecx
0x140041b61  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x140041b65  call    cs:__imp_TlsSetValue
0x140041b6b  mov     [rbp+57h+var_60], rsi
0x140041b6f  jmp     short loc_140041B75
0x140041b71  mov     [rbp+57h+var_60], rax
0x140041b75  inc     dword ptr [rsi]
0x140041b77  lea     rax, WPP_GLOBAL_Control
0x140041b7e  mov     r15d, 1DFh
0x140041b84  lea     r8, asc_14008A110; "                                       "...
0x140041b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b92  cmp     rcx, rax
0x140041b95  jz      short loc_140041BDC
0x140041b97  test    byte ptr [rcx+1Ch], 80h
0x140041b9b  jz      short loc_140041BDC
0x140041b9d  mov     eax, [rsi]
0x140041b9f  lea     edx, [rax+rax*4]
0x140041ba2  cmp     edx, 1E1h
0x140041ba8  ja      short loc_140041BB4
0x140041baa  mov     eax, edx
0x140041bac  mov     edx, r15d
0x140041baf  sub     rdx, rax
0x140041bb2  jmp     short loc_140041BB7
0x140041bb4  mov     rdx, r14
0x140041bb7  lea     r9, [rdx+r8]
0x140041bbb  mov     edx, 11h
0x140041bc0  mov     [rsp+100h+lpdwindex], r12
0x140041bc5  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140041bcc  mov     rcx, [rcx+10h]
0x140041bd0  call    WPP_SF_sq
0x140041bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140041bdc  mov     [rbp+57h+var_C0], r14
0x140041be0  mov     [rbp+57h+var_A8], r14
0x140041be4  mov     eax, 0Dh
0x140041be9  cmp     ax, [rdi]
0x140041bec  jnz     short loc_140041BF7
0x140041bee  mov     r9, [rdi+8]
0x140041bf2  test    r9, r9
0x140041bf5  jnz     short loc_140041C17
0x140041bf7  mov     ebx, 80004002h
0x140041bfc  mov     eax, 9
0x140041c01  cmp     ax, [rdi]
0x140041c04  jnz     loc_140041EE7
0x140041c0a  mov     r9, [rdi+8]
0x140041c0e  test    r9, r9
0x140041c11  jz      loc_140041EE7
0x140041c17  mov     rax, [r9]
0x140041c1a  lea     r8, [rbp+57h+var_A8]
0x140041c1e  lea     rdx, _GUID_07f7438c_7709_4ca5_b518_91279288134e
0x140041c25  mov     rcx, r9
0x140041c28  mov     rax, [rax]
0x140041c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c30  mov     ebx, eax
0x140041c32  test    eax, eax
0x140041c34  js      loc_140041EE0
0x140041c3a  lea     r14, [r12+30h]
0x140041c3f  mov     rcx, [r14]
0x140041c42  mov     rax, [rcx]
0x140041c45  lea     rdx, [rbp+57h+var_C0]
0x140041c49  mov     rax, [rax+68h]
0x140041c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c52  mov     ebx, eax
0x140041c54  test    eax, eax
0x140041c56  js      loc_140041ED7
0x140041c5c  cmp     byte ptr [r12+58h], 0
0x140041c62  jz      short loc_140041C77
0x140041c64  mov     rcx, [rbp+57h+var_C0]
0x140041c68  mov     rax, [rcx]
0x140041c6b  or      edx, 0FFFFFFFFh
0x140041c6e  mov     rax, [rax+50h]
0x140041c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c77  mov     rcx, [rbp+57h+var_C0]
0x140041c7b  mov     rax, [rcx]
0x140041c7e  mov     rdx, [rbp+57h+var_A8]
0x140041c82  mov     rax, [rax+70h]
0x140041c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041c8b  mov     ebx, eax
0x140041c8d  test    eax, eax
0x140041c8f  js      loc_140041ED7
0x140041c95  xorps   xmm0, xmm0
0x140041c98  xor     eax, eax
0x140041c9a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x140041c9e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140041ca2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041ca6  call    cs:__imp_VariantInit
0x140041cac  xor     r9d, r9d; lpName
0x140041caf  xor     r8d, r8d; bInitialState
0x140041cb2  lea     edi, [r9+1]
0x140041cb6  mov     edx, edi; bManualReset
0x140041cb8  xor     ecx, ecx; lpEventAttributes
0x140041cba  call    cs:__imp_CreateEventW
0x140041cc0  mov     [rbp+57h+pHandles], rax
0x140041cc4  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x140041ccb  mov     [rbp+57h+var_70], rcx
0x140041ccf  test    rax, rax
0x140041cd2  jnz     short loc_140041CE7
0x140041cd4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140041cd9  mov     ebx, eax
0x140041cdb  test    eax, eax
0x140041cdd  js      loc_140041EB8
0x140041ce3  mov     rax, [rbp+57h+pHandles]
0x140041ce7  mov     [rbp+57h+arg_10], rax
0x140041ceb  lea     r8, [rbp+57h+arg_10]
0x140041cef  lea     rdx, [rbp+57h+arg_8]
0x140041cf3  lea     rcx, [rbp+57h+var_A0]
0x140041cf7  call    ??$Make@VCDownloadProgressHandler@@AEAPEBGPEAX@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDownloadProgressHandler@@@12@AEAPEBG$$QEAPEAX@Z; Microsoft::WRL::Details::Make<CDownloadProgressHandler,ushort const * &,void *>(ushort const * &,void * &&)
0x140041cfc  nop
0x140041cfd  mov     [rbp+57h+var_B8], 0
0x140041d05  mov     r9d, 3000Dh; unsigned int
0x140041d0b  mov     r8, [rbp+57h+var_C0]; struct IUnknown *
0x140041d0f  mov     rdx, r13; unsigned __int16 *
0x140041d12  call    ?SetUUPSessionData@CLPInstallHandler@@AEAAJPEBGPEAUIUnknown@@K@Z; CLPInstallHandler::SetUUPSessionData(ushort const *,IUnknown *,ulong)
0x140041d17  mov     ebx, eax
0x140041d19  mov     r13, [rbp+57h+var_A0]
0x140041d1d  test    eax, eax
0x140041d1f  js      loc_140041E9D
0x140041d25  mov     rcx, [rbp+57h+var_C0]
0x140041d29  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140041d2d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140041d32  movaps  [rbp+57h+var_50], xmm0
0x140041d36  movsd   [rbp+57h+var_40], xmm1
0x140041d3b  mov     r9, [rcx]
0x140041d3e  mov     rax, r13
0x140041d41  lea     rdx, [r13+8]
0x140041d45  neg     rax
0x140041d48  sbb     r8, r8
0x140041d4b  and     r8, rdx
0x140041d4e  mov     rax, [r9+78h]
0x140041d52  lea     rdx, [rbp+57h+var_B8]
0x140041d56  mov     [rsp+100h+lpdwindex], rdx
0x140041d5b  lea     r9, [rbp+57h+var_50]
0x140041d5f  mov     rdx, r13
0x140041d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041d67  mov     ebx, eax
0x140041d69  test    eax, eax
0x140041d6b  js      loc_140041E9D
0x140041d71  mov     [rbp+57h+var_98], 0
0x140041d79  mov     [rbp+57h+dwindex], 0
0x140041d80  mov     r10, cs:WPP_GLOBAL_Control
0x140041d87  lea     rax, WPP_GLOBAL_Control
0x140041d8e  cmp     r10, rax
0x140041d91  jz      short loc_140041DD4
0x140041d93  test    byte ptr [r10+1Ch], 8
0x140041d98  jz      short loc_140041DD4
0x140041d9a  mov     eax, [rsi]
0x140041d9c  add     eax, edi
0x140041d9e  lea     ecx, [rax+rax*4]
0x140041da1  cmp     ecx, 1E1h
0x140041da7  ja      short loc_140041DB3
0x140041da9  mov     eax, ecx
0x140041dab  mov     rcx, r15
0x140041dae  sub     rcx, rax
0x140041db1  jmp     short loc_140041DB5
0x140041db3  xor     ecx, ecx
0x140041db5  lea     r9, asc_14008A110; "                                       "...
0x140041dbc  add     r9, rcx
0x140041dbf  mov     edx, 12h
0x140041dc4  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140041dcb  mov     rcx, [r10+10h]
0x140041dcf  call    WPP_SF_s
0x140041dd4  lea     rax, [rbp+57h+dwindex]
0x140041dd8  mov     [rsp+100h+lpdwindex], rax; lpdwindex
0x140041ddd  lea     r9, [rbp+57h+pHandles]; pHandles
0x140041de1  mov     r8d, edi; cHandles
0x140041de4  or      edx, 0FFFFFFFFh; dwTimeout
0x140041de7  mov     ecx, 8; dwFlags
0x140041dec  call    cs:__imp_CoWaitForMultipleHandles
0x140041df2  mov     ebx, eax
0x140041df4  test    eax, eax
0x140041df6  js      loc_140041E93
0x140041dfc  mov     [rbp+57h+var_D0], 0
0x140041e04  mov     rdi, [rbp+57h+var_C0]
0x140041e08  mov     rax, [rdi]
0x140041e0b  mov     rbx, [rax+88h]
0x140041e12  lea     rcx, [rbp+57h+var_D0]
0x140041e16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041e1b  lea     r8, [rbp+57h+var_D0]
0x140041e1f  mov     rdx, [rbp+57h+var_B8]
0x140041e23  mov     rcx, rdi
0x140041e26  mov     rax, rbx
0x140041e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041e2e  mov     ebx, eax
0x140041e30  test    eax, eax
0x140041e32  js      short loc_140041E89
0x140041e34  mov     dword ptr [rbp+57h+arg_10], 0
0x140041e3b  mov     rcx, [rbp+57h+var_D0]
0x140041e3f  mov     rax, [rcx]
0x140041e42  lea     rdx, [rbp+57h+arg_10]
0x140041e46  mov     rax, [rax+40h]
0x140041e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041e4f  mov     ebx, eax
0x140041e51  test    eax, eax
0x140041e53  js      short loc_140041E89
0x140041e55  cmp     dword ptr [rbp+57h+arg_10], 2
0x140041e59  jz      short loc_140041E89
0x140041e5b  mov     [rbp+57h+arg_18], 0
0x140041e62  mov     rcx, [rbp+57h+var_D0]
0x140041e66  mov     rax, [rcx]
0x140041e69  lea     rdx, [rbp+57h+arg_18]
0x140041e6d  mov     rax, [rax+38h]
0x140041e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041e76  mov     ebx, eax
0x140041e78  test    eax, eax
0x140041e7a  js      short loc_140041E89
0x140041e7c  mov     ebx, [rbp+57h+arg_18]
0x140041e7f  test    ebx, ebx
0x140041e81  mov     eax, 80004005h
0x140041e86  cmovns  ebx, eax
0x140041e89  lea     rcx, [rbp+57h+var_D0]
0x140041e8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041e92  nop
0x140041e93  lea     rcx, [rbp+57h+var_98]
0x140041e97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140041e9c  nop
0x140041e9d  lea     rcx, [rbp+57h+var_B8]
0x140041ea1  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140041ea6  nop
0x140041ea7  test    r13, r13
0x140041eaa  jz      short loc_140041EB4
0x140041eac  mov     rcx, r13
0x140041eaf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDownloadProgressChangedCallback@@UIDownloadCompletedCallback@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDownloadProgressChangedCallback,IDownloadCompletedCallback>::Release(void)
0x140041eb4  mov     r13, [rbp+57h+arg_8]
0x140041eb8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041ebc  call    cs:__imp_VariantClear
0x140041ec2  nop
0x140041ec3  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x140041eca  mov     [rbp+57h+var_70], rax
0x140041ece  lea     rcx, [rbp+57h+var_70]
0x140041ed2  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x140041ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ede  jmp     short loc_140041EEC
0x140041ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ee7  lea     r14, [r12+30h]
0x140041eec  lea     rdi, WPP_GLOBAL_Control
0x140041ef3  cmp     rcx, rdi
0x140041ef6  jz      short loc_140041F43
0x140041ef8  test    byte ptr [rcx+1Ch], 8
0x140041efc  jz      short loc_140041F43
0x140041efe  mov     eax, [rsi]
0x140041f00  inc     eax
0x140041f02  lea     edx, [rax+rax*4]
0x140041f05  cmp     edx, 1E1h
0x140041f0b  ja      short loc_140041F17
0x140041f0d  mov     eax, edx
0x140041f0f  mov     rdx, r15
0x140041f12  sub     rdx, rax
0x140041f15  jmp     short loc_140041F19
0x140041f17  xor     edx, edx
0x140041f19  lea     r9, asc_14008A110; "                                       "...
0x140041f20  add     r9, rdx
0x140041f23  mov     edx, 13h
0x140041f28  mov     dword ptr [rsp+100h+lpdwindex], ebx
0x140041f2c  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140041f33  mov     rcx, [rcx+10h]
0x140041f37  call    WPP_SF_sd
0x140041f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041f43  test    ebx, ebx
0x140041f45  js      loc_140042184
0x140041f4b  mov     rbx, cs:?s_pInstance@CLanguagePackInstallerSingleton@@0PEAV1@EA; CLanguagePackInstallerSingleton * CLanguagePackInstallerSingleton::s_pInstance
0x140041f52  add     rbx, 0B0h
0x140041f59  mov     rcx, rbx; lpCriticalSection
0x140041f5c  call    cs:__imp_EnterCriticalSection
0x140041f62  mov     [rbp+57h+var_A0], rbx
0x140041f66  mov     qword ptr [rbp+57h+dwindex], 0
0x140041f6e  mov     rcx, [r14]
0x140041f71  mov     rax, [rcx]
0x140041f74  lea     rdx, [rbp+57h+dwindex]
0x140041f78  mov     rax, [rax+70h]
0x140041f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f81  mov     ebx, eax
0x140041f83  test    eax, eax
0x140041f85  js      loc_14004216A
0x140041f8b  mov     rcx, qword ptr [rbp+57h+dwindex]
0x140041f8f  mov     rax, [rcx]
0x140041f92  mov     rdx, [rbp+57h+var_A8]
0x140041f96  mov     rax, [rax+80h]
  ... truncated ...
```
