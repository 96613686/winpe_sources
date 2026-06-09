# CLPInstallHandler::SearchForPackage(ushort const *,wil::Variant * *)

- ea: `0x140042a40`
- end: `0x140042edc`
- name: `?SearchForPackage@CLPInstallHandler@@QEAAJPEBGPEAPEAVVariant@wil@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(CLPInstallHandler *__hidden this, const unsigned __int16 *, struct wil::Variant **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040c30`

## callees

- `0x140005f60`
- `0x14000e624`
- `0x14001a2a0`
- `0x14002dd70`
- `0x14002de74`
- `0x14003aed0`
- `0x14003f000`
- `0x140040ebc`
- `0x140041054`
- `0x1400414e8`
- `0x1400415ac`
- `0x140042a40`
- `0x1400430c0`
- `0x1400692f8`
- `0x14007d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140042b31`
- `KERNEL32!EnterCriticalSection` at `0x140042b31`
- `KERNEL32!TlsGetValue` at `0x140042a6f`
- `KERNEL32!TlsGetValue` at `0x140042a6f`
- `KERNEL32!TlsSetValue` at `0x140042aa3`
- `KERNEL32!TlsSetValue` at `0x140042aa3`
- `ole32!CoWaitForMultipleHandles` at `0x140042bc3`
- `ole32!CoWaitForMultipleHandles` at `0x140042bc3`
- `ole32!CoCreateInstance` at `0x140042d26`
- `ole32!CoCreateInstance` at `0x140042d26`
- `OLEAUT32!__imp_VariantClear` at `0x140042d8a`
- `OLEAUT32!__imp_VariantClear` at `0x140042d8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLPInstallHandler::SearchForPackage(
        CLPInstallHandler *this,
        const unsigned __int16 *a2,
        struct wil::Variant **a3)
{
  CLPInstallHandler *v4; // r13
  __int64 *Value; // rax
  __int64 *p_TlsValue; // rdi
  __int64 *v7; // r15
  unsigned int v8; // ecx
  __int64 v9; // rcx
  HRESULT v10; // ebx
  unsigned int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // ebx
  PVOID *v16; // r10
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  VARIANTARG *v21; // rax
  VARIANTARG *v22; // rbx
  LPVOID v23; // r15
  unsigned int v24; // ecx
  __int64 v25; // rcx
  unsigned int v26; // edx
  __int64 v27; // r14
  __int64 v29; // [rsp+28h] [rbp-80h]
  LPVOID ppv; // [rsp+30h] [rbp-78h] BYREF
  DWORD v31; // [rsp+38h] [rbp-70h] BYREF
  DWORD dwindex; // [rsp+3Ch] [rbp-6Ch] BYREF
  struct IUnknown *v33; // [rsp+40h] [rbp-68h] BYREF
  struct IUnknown *v34; // [rsp+48h] [rbp-60h] BYREF
  __int64 TlsValue; // [rsp+50h] [rbp-58h] BYREF
  __int64 *v36; // [rsp+58h] [rbp-50h]
  __int64 *v37; // [rsp+60h] [rbp-48h]
  __int64 *v38; // [rsp+68h] [rbp-40h]
  char *v39; // [rsp+70h] [rbp-38h] BYREF
  long *v40; // [rsp+78h] [rbp-30h] BYREF
  CLPInstallHandler *v41; // [rsp+B0h] [rbp+8h] BYREF
  struct wil::Variant **v42; // [rsp+C0h] [rbp+18h]
  int v43; // [rsp+C8h] [rbp+20h] BYREF

  v42 = a3;
  v41 = this;
  v4 = this;
  v43 = 0;
  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v31 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v36 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v36 = &TlsValue;
    v31 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
  }
  v38 = p_TlsValue;
  v7 = p_TlsValue;
  v37 = p_TlsValue;
  ++*(_DWORD *)p_TlsValue;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v8 = 5 * *(_DWORD *)p_TlsValue;
    if ( v8 > 0x1E1 )
      v9 = 0;
    else
      v9 = 479LL - v8;
    WPP_SF_sqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v9],
      (char)v4,
      (__int64)a2);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  v39 = (char *)v4 + 8;
  v10 = CLPInstallHandler::BeginSearch(v4);
  if ( v10 < 0 )
    goto LABEL_50;
  dwindex = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v11 = 5 * (*(_DWORD *)p_TlsValue + 1);
    if ( v11 > 0x1E1 )
      v12 = 0;
    else
      v12 = 479LL - v11;
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      &asc_14008A110[v12]);
  }
  v10 = CoWaitForMultipleHandles(8u, 0x493E0u, 1u, (LPHANDLE)v4 + 13, &dwindex);
  if ( v10 < 0 )
    goto LABEL_49;
  v10 = *((_DWORD *)v4 + 18);
  if ( v10 < 0 )
    goto LABEL_49;
  ppv = 0;
  v13 = *((_QWORD *)v4 + 10);
  v43 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 80LL))(v13, &v43);
  THROW_HR_IF_FAILED(v14);
  v15 = v43;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v17 = 5 * (*(_DWORD *)p_TlsValue + 1);
    if ( v17 > 0x1E1 )
      v18 = 0;
    else
      v18 = 479LL - v17;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v18],
      v43);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 > 0 )
  {
    v34 = 0;
    try
    {
      v19 = *((_QWORD *)v4 + 10);
      v33 = 0;
      v43 = 1;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v19 + 56LL))(v19, 0, &v33);
      THROW_HR_IF_FAILED(v20);
      if ( v33 )
        ATL::AtlComPtrAssign(&v34, v33);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v33);
    }
    catch ( long *v40 )
    {
      v43 = *(_DWORD *)v40;
      v10 = v43;
      v4 = v41;
      if ( v43 < 0 )
      {
        p_TlsValue = v37;
LABEL_41:
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v34);
        goto LABEL_48;
      }
      p_TlsValue = v36;
      v7 = v37;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v10 = CoCreateInstance(
            &GUID_13639463_00db_4646_803d_528026140d88,
            0,
            1u,
            &GUID_07f7438c_7709_4ca5_b518_91279288134e,
            &ppv);
    if ( v10 < 0
      || (LODWORD(v41) = 0,
          v10 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, CLPInstallHandler **))(*(_QWORD *)ppv + 96LL))(
                  ppv,
                  v34,
                  &v41),
          v10 < 0) )
    {
      p_TlsValue = v7;
    }
    else
    {
      v21 = (VARIANTARG *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      v22 = v21;
      if ( v21 )
      {
        v23 = ppv;
        ppv = 0;
        v21->vt = 0;
        VariantClear(v21);
        v22->vt = 9;
        v22->llVal = (LONGLONG)v23;
        if ( v23 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 8LL))(v23);
        *v42 = (struct wil::Variant *)v22;
        v10 = 0;
      }
      else
      {
        *v42 = 0;
        v10 = -2147024882;
      }
    }
    goto LABEL_41;
  }
  v10 = -2146498224;
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
  {
    v24 = 5 * (*(_DWORD *)p_TlsValue + 1);
    if ( v24 > 0x1E1 )
      v25 = 0;
    else
      v25 = 479LL - v24;
    WPP_SF_sd(
      (unsigned int)v16[2],
      15,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v25],
      80);
  }
LABEL_48:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( v10 < 0 )
LABEL_49:
    CUpdateSearcher::StopSearch(*((CUpdateSearcher **)v4 + 7));
LABEL_50:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v26 = 5 * *(_DWORD *)p_TlsValue;
    if ( v26 > 0x1E1 )
      v27 = 0;
    else
      v27 = 479LL - v26;
    LODWORD(v29) = v10;
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v27],
      (char)v4,
      v29);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v39);
  if ( p_TlsValue )
    --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140042a40  mov     rax, rsp
0x140042a43  mov     [rax+10h], rbx
0x140042a47  mov     [rax+18h], r8
0x140042a4b  mov     [rax+8], rcx
0x140042a4f  push    rsi
0x140042a50  push    rdi
0x140042a51  push    r13
0x140042a53  push    r14
0x140042a55  push    r15
0x140042a57  sub     rsp, 80h
0x140042a5e  mov     rbx, rdx
0x140042a61  mov     r13, rcx
0x140042a64  xor     esi, esi
0x140042a66  mov     [rax+20h], esi
0x140042a69  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140042a6f  call    cs:__imp_TlsGetValue
0x140042a75  mov     rdi, rax
0x140042a78  mov     [rsp+0A8h+var_70], 0FFFFFFFFh
0x140042a80  mov     [rsp+0A8h+TlsValue], rsi
0x140042a85  test    rax, rax
0x140042a88  jnz     short loc_140042AAB
0x140042a8a  lea     rdi, [rsp+0A8h+TlsValue]
0x140042a8f  mov     [rsp+0A8h+var_50], rdi
0x140042a94  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140042a9a  mov     [rsp+0A8h+var_70], ecx
0x140042a9e  lea     rdx, [rsp+0A8h+TlsValue]; lpTlsValue
0x140042aa3  call    cs:__imp_TlsSetValue
0x140042aa9  jmp     short loc_140042AB0
0x140042aab  mov     [rsp+0A8h+var_50], rdi
0x140042ab0  mov     [rsp+0A8h+var_40], rdi
0x140042ab5  mov     r15, rdi
0x140042ab8  mov     [rsp+0A8h+var_48], rdi
0x140042abd  inc     dword ptr [rdi]
0x140042abf  lea     rax, WPP_GLOBAL_Control
0x140042ac6  mov     r10, cs:WPP_GLOBAL_Control
0x140042acd  cmp     r10, rax
0x140042ad0  jz      short loc_140042B24
0x140042ad2  test    byte ptr [r10+1Ch], 80h
0x140042ad7  jz      short loc_140042B24
0x140042ad9  mov     eax, [rdi]
0x140042adb  lea     ecx, [rax+rax*4]
0x140042ade  mov     r14d, 1DFh
0x140042ae4  cmp     ecx, 1E1h
0x140042aea  ja      short loc_140042AF6
0x140042aec  mov     eax, ecx
0x140042aee  mov     ecx, r14d
0x140042af1  sub     rcx, rax
0x140042af4  jmp     short loc_140042AF9
0x140042af6  mov     rcx, rsi
0x140042af9  lea     r9, asc_14008A110; "                                       "...
0x140042b00  add     r9, rcx
0x140042b03  mov     edx, 0Ch
0x140042b08  mov     [rsp+0A8h+var_80], rbx
0x140042b0d  mov     [rsp+0A8h+lpdwindex], r13
0x140042b12  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042b19  mov     rcx, [r10+10h]
0x140042b1d  call    WPP_SF_sqS
0x140042b22  jmp     short loc_140042B2A
0x140042b24  mov     r14d, 1DFh
0x140042b2a  lea     rbx, [r13+8]
0x140042b2e  mov     rcx, rbx; lpCriticalSection
0x140042b31  call    cs:__imp_EnterCriticalSection
0x140042b37  mov     [rsp+0A8h+var_38], rbx
0x140042b3c  mov     rcx, r13; this
0x140042b3f  call    ?BeginSearch@CLPInstallHandler@@AEAAJXZ; CLPInstallHandler::BeginSearch(void)
0x140042b44  mov     ebx, eax
0x140042b46  test    eax, eax
0x140042b48  js      loc_140042E4D
0x140042b4e  mov     [rsp+0A8h+dwindex], esi
0x140042b52  mov     r10, cs:WPP_GLOBAL_Control
0x140042b59  lea     rax, WPP_GLOBAL_Control
0x140042b60  cmp     r10, rax
0x140042b63  jz      short loc_140042BA7
0x140042b65  test    byte ptr [r10+1Ch], 8
0x140042b6a  jz      short loc_140042BA7
0x140042b6c  mov     eax, [rdi]
0x140042b6e  inc     eax
0x140042b70  lea     ecx, [rax+rax*4]
0x140042b73  cmp     ecx, 1E1h
0x140042b79  ja      short loc_140042B85
0x140042b7b  mov     eax, ecx
0x140042b7d  mov     rcx, r14
0x140042b80  sub     rcx, rax
0x140042b83  jmp     short loc_140042B88
0x140042b85  mov     rcx, rsi
0x140042b88  lea     r9, asc_14008A110; "                                       "...
0x140042b8f  add     r9, rcx
0x140042b92  mov     edx, 0Dh
0x140042b97  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042b9e  mov     rcx, [r10+10h]
0x140042ba2  call    WPP_SF_s
0x140042ba7  lea     r9, [r13+68h]; pHandles
0x140042bab  lea     rax, [rsp+0A8h+dwindex]
0x140042bb0  mov     [rsp+0A8h+lpdwindex], rax; lpdwindex
0x140042bb5  mov     edx, 493E0h; dwTimeout
0x140042bba  mov     ecx, 8; dwFlags
0x140042bbf  lea     r8d, [rcx-7]; cHandles
0x140042bc3  call    cs:__imp_CoWaitForMultipleHandles
0x140042bc9  mov     ebx, eax
0x140042bcb  test    eax, eax
0x140042bcd  js      loc_140042E44
0x140042bd3  mov     ebx, [r13+48h]
0x140042bd7  test    ebx, ebx
0x140042bd9  js      loc_140042E44
0x140042bdf  mov     [rsp+0A8h+ppv], rsi
0x140042be4  mov     rcx, [r13+50h]
0x140042be8  mov     [rsp+0A8h+arg_18], esi
0x140042bef  mov     rax, [rcx]
0x140042bf2  lea     rdx, [rsp+0A8h+arg_18]
0x140042bfa  mov     rax, [rax+50h]
0x140042bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042c03  mov     ecx, eax; int
0x140042c05  call    ?THROW_HR_IF_FAILED@@YAXJ@Z; THROW_HR_IF_FAILED(long)
0x140042c0a  mov     ebx, [rsp+0A8h+arg_18]
0x140042c11  mov     r10, cs:WPP_GLOBAL_Control
0x140042c18  lea     rax, WPP_GLOBAL_Control
0x140042c1f  cmp     r10, rax
0x140042c22  jz      short loc_140042C78
0x140042c24  test    byte ptr [r10+1Ch], 8
0x140042c29  jz      short loc_140042C78
0x140042c2b  mov     eax, [rdi]
0x140042c2d  inc     eax
0x140042c2f  lea     ecx, [rax+rax*4]
0x140042c32  cmp     ecx, 1E1h
0x140042c38  ja      short loc_140042C44
0x140042c3a  mov     eax, ecx
0x140042c3c  mov     rcx, r14
0x140042c3f  sub     rcx, rax
0x140042c42  jmp     short loc_140042C47
0x140042c44  mov     rcx, rsi
0x140042c47  lea     r9, asc_14008A110; "                                       "...
0x140042c4e  add     r9, rcx
0x140042c51  mov     edx, 0Eh
0x140042c56  mov     dword ptr [rsp+0A8h+lpdwindex], ebx
0x140042c5a  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042c61  mov     rcx, [r10+10h]
0x140042c65  call    WPP_SF_sd
0x140042c6a  mov     r10, cs:WPP_GLOBAL_Control
0x140042c71  lea     rax, WPP_GLOBAL_Control
0x140042c78  test    ebx, ebx
0x140042c7a  jle     loc_140042DE5
0x140042c80  mov     [rsp+0A8h+var_60], rsi
0x140042c85  mov     rcx, [r13+50h]
0x140042c89  mov     [rsp+0A8h+var_68], rsi
0x140042c8e  mov     [rsp+0A8h+arg_18], 1
0x140042c99  mov     rax, [rcx]
0x140042c9c  lea     r8, [rsp+0A8h+var_68]
0x140042ca1  xor     edx, edx
0x140042ca3  mov     rax, [rax+38h]
0x140042ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042cac  mov     ecx, eax; int
0x140042cae  call    ?THROW_HR_IF_FAILED@@YAXJ@Z; THROW_HR_IF_FAILED(long)
0x140042cb3  mov     rdx, [rsp+0A8h+var_68]; struct IUnknown *
0x140042cb8  test    rdx, rdx
0x140042cbb  jz      short loc_140042CC8
0x140042cbd  lea     rcx, [rsp+0A8h+var_60]; struct IUnknown **
0x140042cc2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140042cc7  nop
0x140042cc8  lea     rcx, [rsp+0A8h+var_68]
0x140042ccd  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140042cd2  nop
0x140042cd3  jmp     short loc_140042CFE
0x140042cd5  mov     ebx, [rsp+0A8h+arg_18]
0x140042cdc  xor     esi, esi
0x140042cde  mov     r14d, 1DFh
0x140042ce4  mov     r13, [rsp+0A8h+arg_0]
0x140042cec  test    ebx, ebx
0x140042cee  js      loc_140042DD4
0x140042cf4  mov     rdi, [rsp+0A8h+var_50]
0x140042cf9  mov     r15, [rsp+0A8h+var_48]
0x140042cfe  lea     rcx, [rsp+0A8h+ppv]
0x140042d03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140042d08  lea     rax, [rsp+0A8h+ppv]
0x140042d0d  mov     [rsp+0A8h+lpdwindex], rax; ppv
0x140042d12  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x140042d19  xor     edx, edx; pUnkOuter
0x140042d1b  lea     r8d, [rdx+1]; dwClsContext
0x140042d1f  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x140042d26  call    cs:__imp_CoCreateInstance
0x140042d2c  mov     ebx, eax
0x140042d2e  test    eax, eax
0x140042d30  js      loc_140042DCF
0x140042d36  mov     dword ptr [rsp+0A8h+arg_0], esi
0x140042d3d  mov     rcx, [rsp+0A8h+ppv]
0x140042d42  mov     rax, [rcx]
0x140042d45  lea     r8, [rsp+0A8h+arg_0]
0x140042d4d  mov     rdx, [rsp+0A8h+var_60]
0x140042d52  mov     rax, [rax+60h]
0x140042d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042d5b  mov     ebx, eax
0x140042d5d  test    eax, eax
0x140042d5f  js      short loc_140042DCF
0x140042d61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140042d68  mov     ecx, 18h; unsigned __int64
0x140042d6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140042d72  mov     rbx, rax
0x140042d75  test    rax, rax
0x140042d78  jz      short loc_140042DBD
0x140042d7a  mov     r15, [rsp+0A8h+ppv]
0x140042d7f  mov     [rsp+0A8h+ppv], rsi
0x140042d84  mov     [rax], si
0x140042d87  mov     rcx, rax; pvarg
0x140042d8a  call    cs:__imp_VariantClear
0x140042d90  mov     word ptr [rbx], 9
0x140042d95  mov     [rbx+8], r15
0x140042d99  test    r15, r15
0x140042d9c  jz      short loc_140042DAE
0x140042d9e  mov     rax, [r15]
0x140042da1  mov     rcx, r15
0x140042da4  mov     rax, [rax+8]
0x140042da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042dad  nop
0x140042dae  mov     rax, [rsp+0A8h+arg_10]
0x140042db6  mov     [rax], rbx
0x140042db9  mov     ebx, esi
0x140042dbb  jmp     short loc_140042DD9
0x140042dbd  mov     rax, [rsp+0A8h+arg_10]
0x140042dc5  mov     [rax], rsi
0x140042dc8  mov     ebx, 8007000Eh
0x140042dcd  jmp     short loc_140042DD9
0x140042dcf  mov     rdi, r15
0x140042dd2  jmp     short loc_140042DD9
0x140042dd4  mov     rdi, [rsp+0A8h+var_48]
0x140042dd9  lea     rcx, [rsp+0A8h+var_60]
0x140042dde  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140042de3  jmp     short loc_140042E36
0x140042de5  mov     ebx, 800F0950h
0x140042dea  cmp     r10, rax
0x140042ded  jz      short loc_140042E36
0x140042def  test    byte ptr [r10+1Ch], 2
0x140042df4  jz      short loc_140042E36
0x140042df6  mov     eax, [rdi]
0x140042df8  inc     eax
0x140042dfa  lea     ecx, [rax+rax*4]
0x140042dfd  cmp     ecx, 1E1h
0x140042e03  ja      short loc_140042E0F
0x140042e05  mov     eax, ecx
0x140042e07  mov     rcx, r14
0x140042e0a  sub     rcx, rax
0x140042e0d  jmp     short loc_140042E12
0x140042e0f  mov     rcx, rsi
0x140042e12  lea     r9, asc_14008A110; "                                       "...
0x140042e19  add     r9, rcx
0x140042e1c  mov     edx, 0Fh
0x140042e21  mov     dword ptr [rsp+0A8h+lpdwindex], ebx
0x140042e25  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042e2c  mov     rcx, [r10+10h]
0x140042e30  call    WPP_SF_sd
0x140042e35  nop
0x140042e36  lea     rcx, [rsp+0A8h+ppv]
0x140042e3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140042e40  test    ebx, ebx
0x140042e42  jns     short loc_140042E4D
0x140042e44  mov     rcx, [r13+38h]; this
0x140042e48  call    ?StopSearch@CUpdateSearcher@@QEAAXXZ; CUpdateSearcher::StopSearch(void)
0x140042e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140042e54  lea     rax, WPP_GLOBAL_Control
0x140042e5b  cmp     rcx, rax
0x140042e5e  jz      short loc_140042EA6
0x140042e60  test    byte ptr [rcx+1Ch], 80h
0x140042e64  jz      short loc_140042EA6
0x140042e66  mov     eax, [rdi]
0x140042e68  lea     edx, [rax+rax*4]
0x140042e6b  cmp     edx, 1E1h
0x140042e71  ja      short loc_140042E7A
0x140042e73  mov     eax, edx
0x140042e75  sub     r14, rax
0x140042e78  jmp     short loc_140042E7D
0x140042e7a  mov     r14, rsi
0x140042e7d  lea     r9, asc_14008A110; "                                       "...
0x140042e84  add     r9, r14
0x140042e87  mov     edx, 10h
0x140042e8c  mov     dword ptr [rsp+0A8h+var_80], ebx
0x140042e90  mov     [rsp+0A8h+lpdwindex], r13
0x140042e95  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042e9c  mov     rcx, [rcx+10h]
0x140042ea0  call    WPP_SF_sqd
0x140042ea5  nop
0x140042ea6  lea     rcx, [rsp+0A8h+var_38]; this
0x140042eab  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x140042eb0  nop
0x140042eb1  test    rdi, rdi
0x140042eb4  jz      short loc_140042EB8
0x140042eb6  dec     dword ptr [rdi]
0x140042eb8  lea     rcx, [rsp+0A8h+var_70]
0x140042ebd  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x140042ec2  mov     eax, ebx
0x140042ec4  mov     rbx, [rsp+0A8h+arg_8]
0x140042ecc  add     rsp, 80h
0x140042ed3  pop     r15
0x140042ed5  pop     r14
0x140042ed7  pop     r13
0x140042ed9  pop     rdi
0x140042eda  pop     rsi
0x140042edb  retn
```
